---
title: Hisse Machine Learning kitaplığı ile temel sınıflandırma
description: "Microsoft QDK 'nin hisse Machine Learning kitaplığını kullanarak Q # dilinde yazılmış bir hisse ve sıralı sınıflandırıcının nasıl yürütüleceğini öğrenin."
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
ms.openlocfilehash: f42e3e4492f934d7a8f03d4fec6fa0de765401d7
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909934"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a>Temel sınıflandırma: verileri QDK ile sınıflandırma

Bu hızlı başlangıçta, QDK 'nin hisse Machine Learning kitaplığını kullanarak Q # dilinde yazılmış bir hisse ve sıralı sınıflandırıcının nasıl yürütüleceğini öğreneceksiniz. 

Bu kılavuzda, Q # içinde tanımlanan bir sınıflandırıcı yapısını kullanarak yarı ay veri kümesini kullanacağız.

## <a name="prerequisites"></a>Önkoşullar

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Q# projesi oluşturma](xref:microsoft.quantum.howto.createproject)

## <a name="host-program"></a>Konak programı

Ana bilgisayar programınız üç bölümden oluşur:

- Veri kümesini yükleyin ve modelinize yönelik bir başlangıç parametreleri kümesi seçin.
- Modelin parametrelerini ve sapmasını öğrenmek için eğitimi yürütün.
- Doğru olduğunu öğrenmek için modeli doğrulayın

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Visual Studio Code veya Komut Satırı ile Python](#tab/tabid-python)

    Python 'dan gelen Q # sınıflandırıcınızı çalıştırmak için aşağıdaki kodu `host.py`olarak kaydedin. Bu öğreticinin ilerleyen kısımlarında açıklanan Q # dosyası `Training.qs` de ihtiyacınız olduğunu unutmayın.

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    Ardından Python konak programınızı komut satırından çalıştırabilirsiniz:

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[Visual Studio Code veya Komut Satırı ile C#](#tab/tabid-csharp)

    Size gelen C#Q # sınıflandırıcınızı çalıştırmak için aşağıdaki kodu `Host.cs`olarak kaydedin. Bu öğreticinin ilerleyen kısımlarında açıklanan Q # dosyası `Training.qs` de ihtiyacınız olduğunu unutmayın.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Ardından C# konak programınızı komut satırından çalıştırabilirsiniz:

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[Visual Studio 2019 ile C#](#tab/tabid-vs2019)

    Yeni Q # programınızı Visual Studio C# 'da çalıştırmak için `Host.cs` aşağıdaki C# kodu içerecek şekilde değiştirin. Bu öğreticinin ilerleyen kısımlarında açıklanan Q # dosyası `Training.qs` de ihtiyacınız olduğunu unutmayın.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Ardından F5 tuşuna basın; program yürütülmeye başlayacak ve aşağıdaki sonuçları içeren yeni bir pencere açılacaktır: 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>Soru\# sınıflandırıcı kodu

Şimdi, ana bilgisayar programı tarafından çağrılan işlemlerin Q # içinde nasıl tanımlandığını görelim.
Aşağıdaki kodu `Training.qs`adlı bir dosyaya kaydettik.

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

Yukarıdaki kodda tanımlanan en önemli işlevler ve işlemler şunlardır:

- `ClassifierStructure() : ControlledRotation[]`: Bu işlevde, düşüntiğimiz denetimli kapıların katmanlarını ekleyerek devre modelimizin yapısını ayarlayacağız. Bu adım, sıralı bir ayrıntılı öğrenme modelinde, neurlanlar katmanlarının bir bildirimine benzerdir.
- `TrainHalfMoonModel() : TrainWineModel() : (Double[], Double)`: Bu işlem kodun temel kısmıdır ve eğitimi tanımlar. Burada, kitaplıkta yer alan veri kümesinden örnekleri yüklediğimiz için, eğitimin Hyper parametrelerini ve başlangıç parametrelerini ayarlayacağız ve kitaplığa dahil edilen işlemi `TrainSequentialClassifier` çağırarak eğitime başladık. Sınıflandırıcının belirlenmesi için parametreleri ve farkı verir.
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`: Bu işlem, modeli değerlendirmek için doğrulama işlemini tanımlar. Burada doğrulama için örnekleri, örnek başına ölçüm sayısını ve toleransı yükledik. Doğrulama için seçilen örnek toplu iş üzerindeki hatalı sınıflandırmaların sayısını verir.

## <a name="next-steps"></a>Sonraki adımlar

İlk olarak, kodla oynatabilir ve öğreticiden nasıl etkilendiğine bakmak için bazı parametreleri değiştirmeyi deneyebilirsiniz. Daha sonra, bir sonraki öğreticide [kendi sınıflandırıcınızı tasarlayabilmeniz](xref:microsoft.quantum.libraries.machine-learning.design)için sınıflandırıcının yapısını nasıl tanımlayacağınızı öğreneceksiniz.
