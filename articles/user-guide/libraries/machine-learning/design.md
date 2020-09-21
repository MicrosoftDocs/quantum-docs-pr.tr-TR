---
title: QDK ile kendi sınıflandırıcınızı tasarlama
description: Hisse devresini merkezli sınıflandırıcı için devre modellerini tasarlamaya yönelik temel kavramları öğrenin.
author: geduardo
ms.author: v-edsanc
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3515279dd4d03b2a512035af0b13e084dd91f9dc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835715"
---
# <a name="design-your-own-classifier"></a>Kendi sınıflandırıcınızı tasarlama

Bu kılavuzda, hisse kullanım merkezli sınıflandırıcılara yönelik devre modelleri tasarımının arkasındaki temel kavramları öğreneceksiniz.

Klasik derinlemesine öğrenime göre, belirli bir mimari seçmek için genel bir kural yoktur. Soruna bağlı olarak bazı mimarilerin diğerlerinden daha iyi hale getirecektir. Ancak, devre tasarımı sırasında yararlı olabilecek bazı kavramlar vardır:

- Çok sayıda parametre daha esnek bir model anlamına gelir. Bu, karmaşık sınıflandırma sınırlarını çizmek için uygun olabilecek, ancak büyük/veya çok daha da savunmasız olabilir.

- Qugeler arasındaki kapıları, hisse ilişkilerimiz arasındaki bağıntıları yakalamak için gereklidir.

## <a name="how-to-build-a-classifier-with-q"></a>Soru-cevap ile bir sınıflandırıcı oluşturma\#

Bir sınıflandırıcı oluşturmak için, devre modelimizde parametrized kontrollü döndürmeler birleştirilecek. Bunu yapmak için, [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) hisse Machine Learning kitaplığı 'nda tanımlanan türü kullanabiliriz. Bu tür, tanımlayan dört bağımsız değişkeni kabul eder: hedef qubit dizinini, denetim qubits 'in Dizin dizisini, döndürme eksenini ve modeli tanımlayan parametrelerin dizisindeki ilişkili parametrenin dizinini.

Sınıflandırıcının bir örneğini görelim. [Yarım Moons örneğinde](https://github.com/microsoft/Quantum/tree/main/samples/machine-learning/half-moons), dosyasında tanımlı olan aşağıdaki sınıflandırıcıyı bulabiliriz `Training.qs` .

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

Burada tanımladığımız özellikler, bir dizi parametre ile birlikte bir dizi öğe döndüren bir işlev `ControlledRotation` ve bir sapma de tanımlayacağız [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel) . Bu tür, hisse Machine Learning kitaplığı 'nda temel ve sınıflandırıcının tanımlanandır. Yukarıdaki işlevde tanımlanan devre, veri kümesinin her bir örneğinin iki özellik içerdiği bir sınıflandırıcının parçasıdır. Bu nedenle, yalnızca iki qubit gerekir. Devresinin grafik gösterimi:

 ![Devre modeli örneği](~/media/circuit_model_1.PNG)

Varsayılan olarak, hisse senedi Machine Learning kitaplığı işlemlerinin, sınıflandırma olasılıkların tahmin edilmesi için kaydın son qubit ' i ölçüsünde olduğunu unutmayın. Devrenizi tasarlarken bu olguyu göz önünde bulundurmanız gerekir.

## <a name="use-the-library-functions-to-write-layers-of-gates"></a>Kapı katmanlarını yazmak için kitaplık işlevlerini kullanma

Örnek başına 784 özelliklerine sahip bir veri kümeniz olduğunu varsayalım, örneğin, bir veri kümesi gibi 28 × 28 piksel görüntüler. Bu durumda, devreninin genişliği yeterince büyük hale gelir. böylece her bir kapı, her bir ağ geçidinin olası ancak pratik bir görev haline gelir. Bu nedenle hisse Machine Learning kitaplığı, otomatik olarak parametrized döndürmeler katmanları oluşturmak için bir araç kümesi sağlar. Örneğin, işlev, [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) her bir qubit için tek bir dönüşle, her bir parametrized farklı bir model parametresi tarafından bir dönüşle, belirli bir eksen boyunca denetlenmeyen tek qubit döndürmeler dizisini döndürür. Örneğin, `LocalRotationsLayer(4, X)` Aşağıdaki kapı kümesini döndürür:

 ![Yerel döndürmeler katmanı](~/media/local_rotations_layer.PNG)

Devre tasarımını kolaylaştırmak için kullanılabilen tüm araçları öğrenmek için [hisse Machine Learning kitaplığının API başvurusunu](xref:microsoft.quantum.machinelearning) araştırmanızı öneririz.

## <a name="next-steps"></a>Sonraki adımlar

 Örnekler tarafından sağlanan örneklerde farklı yapılar deneyin. Modelin performansına ilişkin herhangi bir değişiklik mi görüyorsunuz? Sonraki öğreticide, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) sınıflandırıcıın yeni mimarilerini denemek ve araştırmak için veri kümelerinin nasıl yükleneceğini öğreneceksiniz.
