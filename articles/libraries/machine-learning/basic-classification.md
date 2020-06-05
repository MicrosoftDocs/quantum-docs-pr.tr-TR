---
title: Hisse Machine Learning kitaplığı ile temel sınıflandırma
description: "Microsoft QDK 'nin hisse Machine Learning kitaplığını kullanarak Q # dilinde yazılmış bir hisse ve sıralı sınıflandırıcının nasıl yürütüleceğini öğrenin."
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
ms.openlocfilehash: 1d2538fd164c4c61c2712978d3b5c57b0eb766e6
ms.sourcegitcommit: 8d9d392bf5e114ae223e6f689ba80d25866ff586
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84422181"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a>Temel sınıflandırma: verileri QDK ile sınıflandırma

Bu hızlı başlangıçta, QDK 'nin hisse Machine Learning kitaplığını kullanarak Q # dilinde yazılmış bir hisse ve sıralı sınıflandırıcının nasıl yürütüleceğini öğreneceksiniz. 

Bu kılavuzda, Q # içinde tanımlanan bir sınıflandırıcı yapısını kullanarak yarı ay veri kümesini kullanacağız.

## <a name="prerequisites"></a>Ön koşullar

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Bir [Python konak programı](xref:microsoft.quantum.install.python) veya [C# ana bilgisayar programı](xref:microsoft.quantum.install.cs)için bir Q # projesi oluşturun.

## <a name="host-program"></a>Konak programı

Ana bilgisayar programınız üç bölümden oluşur:

- Veri kümesini yükleyin ve modelinize yönelik bir başlangıç parametreleri kümesi seçin.
- Modelin parametrelerini ve sapmasını öğrenmek için eğitimi yürütün.
- Doğru olduğunu öğrenmek için modeli doğrulayın

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Visual Studio Code veya Komut Satırı ile Python](#tab/tabid-python)

    Python 'dan gelen Q # sınıflandırıcınızı çalıştırmak için aşağıdaki kodu olarak kaydedin `host.py` . Bu öğreticinin ilerleyen kısımlarında açıklanan Q # dosyasına da ihtiyacınız olduğunu unutmayın `Training.qs` .

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    Ardından Python konak programınızı komut satırından çalıştırabilirsiniz:

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[Visual Studio Code veya Komut Satırı ile C#](#tab/tabid-csharp)

    C# ' den gelen Q # sınıflandırıcınızı çalıştırmak için aşağıdaki kodu olarak kaydedin `Host.cs` . Bu öğreticinin ilerleyen kısımlarında açıklanan Q # dosyasına da ihtiyacınız olduğunu unutmayın `Training.qs` .

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Ardından C# konak programınızı komut satırından çalıştırabilirsiniz:

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[Visual Studio 2019 ile C#](#tab/tabid-vs2019)

    Visual Studio 'Da C# ' den yeni Q # programınızı çalıştırmak için `Host.cs` Aşağıdaki C# kodunu içerecek şekilde değiştirin. Bu öğreticinin ilerleyen kısımlarında açıklanan Q # dosyasına da ihtiyacınız olduğunu unutmayın `Training.qs` .

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Ardından F5 tuşuna basın; program yürütülmeye başlayacak ve aşağıdaki sonuçları içeren yeni bir pencere açılacaktır: 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>Q \# sınıflandırıcı kodu

Şimdi, ana bilgisayar programı tarafından çağrılan işlemlerin Q # içinde nasıl tanımlandığını görelim.
Aşağıdaki kodu adlı bir dosyaya kaydettik `Training.qs` .

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

Yukarıdaki kodda tanımlanan en önemli işlevler ve işlemler şunlardır:

- `ClassifierStructure() : ControlledRotation[]`: Bu işlevde, düşüntiğimiz denetimli kapıların katmanlarını ekleyerek devre modelimizin yapısını ayarlayacağız. Bu adım, sıralı bir ayrıntılı öğrenme modelinde, neurlanlar katmanlarının bir bildirimine benzerdir.
- `TrainHalfMoonModel() : (Double[], Double)`: Bu işlem kodun temel kısmıdır ve eğitimi tanımlar. Burada, kitaplıkta yer alan veri kümesinden örnekleri yüklediğimiz için, eğitimin Hyper parametrelerini ve başlangıç parametrelerini ayarlayacağız ve kitaplığa dahil edilen işlemi çağırarak eğitime başladık `TrainSequentialClassifier` . Sınıflandırıcının belirlenmesi için parametreleri ve farkı verir.
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`: Bu işlem, modeli değerlendirmek için doğrulama işlemini tanımlar. Burada doğrulama için örnekleri, örnek başına ölçüm sayısını ve toleransı yükledik. Doğrulama için seçilen örnek toplu iş üzerindeki hatalı sınıflandırmaların sayısını verir.

## <a name="next-steps"></a>Sonraki adımlar

İlk olarak, kodla oynatabilir ve öğreticiden nasıl etkilendiğine bakmak için bazı parametreleri değiştirmeyi deneyebilirsiniz. Daha sonra, bir sonraki öğreticide [kendi sınıflandırıcınızı tasarlayabilmeniz](xref:microsoft.quantum.libraries.machine-learning.design)için sınıflandırıcının yapısını nasıl tanımlayacağınızı öğreneceksiniz.
