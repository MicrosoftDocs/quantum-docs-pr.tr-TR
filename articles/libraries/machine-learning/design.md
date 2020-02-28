---
title: QDK ile kendi sınıflandırıcınızı tasarlama
description: Hisse devresini merkezli sınıflandırıcı için devre modellerini tasarlamaya yönelik temel kavramları öğrenin.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
ms.openlocfilehash: 4899336f437c1b7712a7831b97fd6ec1431b59a2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909730"
---
# <a name="design-your-own-classifier"></a>Kendi sınıflandırıcınızı tasarlama

Bu kılavuzda, hisse kullanım merkezli sınıflandırıcılara yönelik devre modelleri tasarımının arkasındaki temel kavramları öğreneceksiniz.

Klasik derinlemesine öğrenime göre, belirli bir mimari seçmek için genel bir kural yoktur. Soruna bağlı olarak bazı mimarilerin diğerlerinden daha iyi hale getirecektir. Ancak, devre tasarımı sırasında yararlı olabilecek bazı kavramlar vardır:

- Çok sayıda parametre daha esnek bir model anlamına gelir. Bu, karmaşık sınıflandırma sınırlarını çizmek için uygun olabilecek, ancak büyük/veya çok daha da savunmasız olabilir.

- Qugeler arasındaki kapıları, hisse ilişkilerimiz arasındaki bağıntıları yakalamak için gereklidir.

## <a name="how-to-build-a-classifier-with-q"></a>Soru-cevap ile sınıflandırıcı derleme\#

Bir sınıflandırıcı oluşturmak için, devre modelimizde parametrized kontrollü döndürmeler birleştirilecek. Bunu yapmak için, hisse Machine Learning kitaplığında tanımlanan [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) türünü kullanabiliriz. Bu tür, tanımlayan dört bağımsız değişkeni kabul eder: hedef qubit dizinini, denetim qubits 'in Dizin dizisini, döndürme eksenini ve modeli tanımlayan parametrelerin dizisindeki ilişkili parametrenin dizinini.

Sınıflandırıcının bir örneğini görelim. [Yarım Moons örneğinde](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons), `Training.qs`dosyada tanımlanan aşağıdaki sınıflandırıcıyı bulabilirsiniz.

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

Burada tanımladığımız özellikler, bir dizi parametre ile birlikte bir dizi `ControlledRotation` öğesi döndüren ve [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel)bir sapma tanımlayan bir işlevdir. Bu tür, hisse Machine Learning kitaplığı 'nda temel ve sınıflandırıcının tanımlanandır. Yukarıdaki işlevde tanımlanan devre, veri kümesinin her bir örneğinin iki özellik içerdiği bir sınıflandırıcının parçasıdır. Bu nedenle, yalnızca iki qubit gerekir. Devresinin grafik gösterimi:

 ![Devre modeli örneği](~/media/circuit_model_1.PNG)

## <a name="use-the-library-functions-to-write-layers-of-gates"></a>Kapı katmanlarını yazmak için kitaplık işlevlerini kullanma

Örnek başına 784 özelliklerine sahip bir veri kümeniz olduğunu varsayalım, örneğin, bir veri kümesi gibi 28 × 28 piksel görüntüler. Bu durumda, devreninin genişliği yeterince büyük hale gelir. böylece her bir kapı, her bir ağ geçidinin olası ancak pratik bir görev haline gelir. Bu nedenle hisse Machine Learning kitaplığı, otomatik olarak parametrized döndürmeler katmanları oluşturmak için bir araç kümesi sağlar. Örnek olarak, işlev [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) , her bir qubit için tek bir dönüşle, her bir parametrized farklı bir model parametresi tarafından bir dönüşle, belirli bir eksen boyunca denetlenmeyen tek qubit döndürmeler dizisini döndürür. Örneğin, `LocalRotationsLayer(4, X)` aşağıdaki kapı kümesini döndürür:

 ![Yerel döndürmeler katmanı](~/media/local_rotations_layer.PNG)

Devre tasarımını kolaylaştırmak için kullanılabilen tüm araçları öğrenmek amacıyla [hisse Machine Learning kitaplığının API referenece](xref:microsoft.quantum.machinelearning) 'yi araştırmanızı öneririz.

## <a name="next-steps"></a>Sonraki adımlar

 Örnekler tarafından sağlanan örneklerde farklı yapılar deneyin. Modelin performansına ilişkin herhangi bir değişiklik mi görüyorsunuz? Sonraki öğreticide [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load), sınıflandırıcıın yeni mimarilerini denemek ve araştırmak için veri kümelerinin nasıl yükleneceğini öğreneceksiniz.
