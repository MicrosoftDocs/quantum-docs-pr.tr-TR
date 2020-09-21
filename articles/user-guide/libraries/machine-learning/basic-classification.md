---
title: Hisse Machine Learning kitaplığı ile temel sınıflandırma
description: Q#Microsoft QDK 'Nin hisse Machine Learning kitaplığı kullanılarak yazılmış bir hisse ve sıralı sınıflandırıcının nasıl çalıştırılacağını öğrenin.
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5dc4614b9992e2c6b9f8ff4b839c0929ec8cab7c
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833715"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a>Temel sınıflandırma: verileri QDK ile sınıflandırma

Bu hızlı başlangıçta, Q# QDK 'Nin hisse Machine Learning kitaplığı kullanılarak yazılmış bir hisse ve sıralı sınıflandırıcının nasıl çalıştırılacağını öğreneceksiniz. 

Bu kılavuzda, içinde tanımlanan bir sınıflandırıcı yapısını kullanarak yarı ay veri kümesini kullanacağız Q# .

## <a name="prerequisites"></a>Ön koşullar

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Q# [Python konak programı](xref:microsoft.quantum.install.python) veya [C# ana bilgisayar programı](xref:microsoft.quantum.install.cs)için bir proje oluşturun.

## <a name="host-program"></a>Konak programı

Ana bilgisayar programınız üç bölümden oluşur:

- Veri kümesini yükleyin ve modelinize yönelik bir başlangıç parametreleri kümesi seçin.
- Modelin parametrelerini ve sapmasını öğrenmek için eğitimi çalıştırın.
- Doğru olduğunu öğrenmek için modeli doğrulayın

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Visual Studio Code veya Komut Satırı ile Python](#tab/tabid-python)

    Q#Python 'un sınıflandırıcılarından istediğinizi çalıştırmak için aşağıdaki kodu olarak kaydedin `host.py` . Q#Bu öğreticinin ilerleyen kısımlarında açıklanan dosyanın da gerekli olduğunu unutmayın `Training.qs` .

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    Ardından Python konak programınızı komut satırından çalıştırabilirsiniz:

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[Visual Studio Code veya Komut Satırı ile C#](#tab/tabid-csharp)

    Q#C# ' den sınıflandırıcıdır, aşağıdaki kodu olarak kaydedin `Host.cs` . Q#Bu öğreticinin ilerleyen kısımlarında açıklanan dosyanın da gerekli olduğunu unutmayın `Training.qs` .

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Ardından C# konak programınızı komut satırından çalıştırabilirsiniz:

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[Visual Studio 2019 ile C#](#tab/tabid-vs2019)

    Q#Visual Studio 'Da c# ' den yeni programınızı çalıştırmak için `Host.cs` Aşağıdaki c# kodunu içerecek şekilde değiştirin. Q#Bu öğreticinin ilerleyen kısımlarında açıklanan dosyanın da gerekli olduğunu unutmayın `Training.qs` .

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    F5 tuşuna basın ve program çalışmaya başlar. Yeni bir pencere, aşağıdaki sonuçları görüntüler: 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>Q \# sınıflandırıcı kodu

Şimdi konak program tarafından çağrılan işlemlerin nasıl tanımlandığını görelim Q# .
Aşağıdaki kodu adlı bir dosyaya kaydettik `Training.qs` .

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

Yukarıdaki kodda tanımlanan en önemli işlevler ve işlemler şunlardır:

- `ClassifierStructure() : ControlledRotation[]` : Bu işlevde, düşüntiğimiz denetimli kapıların katmanlarını ekleyerek devre modelimizin yapısını ayarlayacağız. Bu adım, sıralı bir ayrıntılı öğrenme modelinde, neurlanlar katmanlarının bir bildirimine benzerdir.
- `TrainHalfMoonModel() : (Double[], Double)` : Bu işlem kodun temel kısmıdır ve eğitimi tanımlar. Burada, kitaplıkta yer alan veri kümesinden örnekleri yüklediğimiz için, eğitimin Hyper parametrelerini ve başlangıç parametrelerini ayarlayacağız ve kitaplığa dahil edilen işlemi çağırarak eğitime başladık `TrainSequentialClassifier` . Sınıflandırıcının belirlenmesi için parametreleri ve farkı verir.
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : Bu işlem, modeli değerlendirmek için doğrulama işlemini tanımlar. Burada doğrulama için örnekleri, örnek başına ölçüm sayısını ve toleransı yükledik. Doğrulama için seçilen örnek toplu iş üzerindeki hatalı sınıflandırmaların sayısını verir.

## <a name="next-steps"></a>Sonraki adımlar

İlk olarak, kodla oynatabilir ve öğreticiden nasıl etkilendiğine bakmak için bazı parametreleri değiştirmeyi deneyebilirsiniz. Daha sonra, bir sonraki öğreticide [kendi sınıflandırıcınızı tasarlayabilmeniz](xref:microsoft.quantum.libraries.machine-learning.design)için sınıflandırıcının yapısını nasıl tanımlayacağınızı öğreneceksiniz.
