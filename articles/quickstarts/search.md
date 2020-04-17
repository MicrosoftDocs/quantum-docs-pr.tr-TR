---
title: Q# dilinde Grover arama algoritmasını çalıştırma - Quantum Development Kit
description: Standart kuantum algoritmalarından biri olan Grover algoritmasını gösteren bir Q# projesi derleyin.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 0e64fcd56929fa33397c45bf1b2e99bf687eca6f
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906959"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a>Hızlı Başlangıç: Q# dilinde Grover arama algoritmasını uygulama

Bu Hızlı Başlangıç’ta, yapılandırılmamış veri aramasını hızlandırmak için Grover araması derlemeyi ve çalıştırmayı öğrenebilirsiniz.  Grover araması en popüler kuantum bilişimi algoritmalarından biridir ve görece küçük olan bu Q# uygulaması, kuantum algoritmalarını ifade etmek için üst düzey Q# kuantum programlama dili ile kuantum çözümü programlamanın avantajlarını sunar.  Kılavuzun sonunda, klasik bir bilgisayara kıyasla çok daha az sürede sıralı olmayan girişlerden oluşan bir listede belirli bir dizeyi başarıyla bulma sonucunu gösteren simülasyon çıktısını göreceksiniz.

Grover algoritması belirli öğeleri bulmak için yapılandırılmamış bir veri listesinde arama yapar. Örneğin şu soruyu yanıtlayabilir: Bir deste iskambil kağıdından çekilen bu kağıt kupa ası mı? Belirli öğenin etiketlenmesi _işaretlenmiş giriş_ olarak adlandırılır.

Grover arama algoritması kullanıldığında, kuantum bilgisayarın bu aramayı aradığınız listedeki öğelerin sayısından daha az adımda çalıştıracağı garantidir; bu klasik algoritmanın yapamayacağı bir şeydir. Bir deste iskambil kağıdı örneğinde hız artışı göz ardı edilebilir ama milyonlarca veya milyarlarca öğe içeren listelerde ciddi bir artış anlamına gelir.

Grover arama algoritmasını yalnızca birkaç kod satırıyla oluşturabilirsiniz.

## <a name="prerequisites"></a>Ön koşullar

- Microsoft [Quantum Development Kit][install].

## <a name="what-does-grovers-search-algorithm-do"></a>Grover arama algoritması ne yapar?

Grover algoritması, listedeki bir öğenin bizim aradığımız öğe olup olmadığını sorar. Bunu yapmak için listenin dizinlerinin bir kuantum süper konumunu oluşturur; burada her katsayı veya olasılık genliği belirli bir dizinin aradığınız dizin olma olasılığını temsil eder.

Algoritmanın merkezinde aradığımız dizinin katsayısını, bu katsayının olasılık genliği bire yaklaşana kadar aşamalı olarak artıran iki adım vardır.

Aşamalı artışların sayısı listedeki öğelerin sayısından azdır. İşte bundan dolayı Grover arama algoritması aramayı klasik algoritmalardan daha az adımda gerçekleştirir.

![Grover arama algoritmasının işlevsel diyagramı](~/media/grover.png)

## <a name="write-the-code"></a>Kodu yazma

1. Quantum Development Kit'i kullanarak tercih ettiğiniz geliştirme ortamında `Grover` adlı [yeni bir Q# projesi oluşturun](xref:microsoft.quantum.howto.createproject).

1. Yeni projenizin `Operations.qs` dosyasına aşağıdaki kodu ekleyin:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-40":::

1. Arama yaptığımız listeyi tanımlamak için yeni bir dosya (`Reflections.qs`) oluşturun ve aşağıdaki kodu yapıştırın:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    `ReflectAboutMarked` işlemi aradığınız işaretlenmiş girişi tanımlar: değişen sıfırlar ve birler dizesi. Bu örnek işaretlenmiş girişin sabit kodlamasını yapar ve farklı girişleri aramak veya herhangi bir giriş için genelleştirmek üzere genişletilebilir.

1. Ardından `ReflectAboutMarked` ile işaretlenmiş öğeyi bulmak için yeni Q# programınızı çalıştırın.

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Visual Studio Code veya Komut Satırı ile Python](#tab/tabid-python)

    Yeni Q# programınızı Python'dan çalıştırmak için aşağıdaki kodu `host.py` olarak kaydedin:

    :::code language="python" source="~/quantum/samples/algorithms/simple-grover/host.py" range="9-14":::

    Ardından Python konak programınızı komut satırından çalıştırabilirsiniz:

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[Visual Studio Code veya Komut Satırı ile C#](#tab/tabid-csharp)

    Yeni Q# programınızı C# dilinden çalıştırmak için `Driver.cs` dosyasını aşağıdaki C# kodunu içerecek şekilde değiştirin:

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    Ardından C# konak programınızı komut satırından çalıştırabilirsiniz:

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019"></a>[Visual Studio 2019 ile C#](#tab/tabid-vs2019)

    Yeni Q# programınızı Visual Studio'da C# dilinde çalıştırmak için `Driver.cs` dosyasını aşağıdaki C# kodunu içerecek şekilde değiştirin:

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    Ardından F5 tuşuna basın; program yürütülmeye başlayacak ve aşağıdaki sonuçları içeren yeni bir pencere açılacaktır: 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    `ReflectAboutMarked` işlemi yalnızca dört kez çağrılır ama Q# programınız $2^{5} = 32$ olası giriş arasından "01010" girişini bulmuştur!

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçtan keyif aldıysanız, Q# kullanarak kendi kuantum uygulamalarınızı nasıl yazabileceğiniz hakkında daha fazla bilgi edinmek için aşağıdaki kaynaklardan bazılarını gözden geçirin:

- [QDK'yı Kullanmaya Başlama kılavuzuna dön](xref:microsoft.quantum.welcome)
- Daha genel bir Grover arama algoritması [örneğini](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) deneyin
- [Kuantum Katalarıyla Grover araması hakkında daha fazla bilgi edinin](xref:microsoft.quantum.overview.katas)
- Grover arama algoritmasının arkasındaki kuantum bilişim tekniği olan [genliğini yükseltme](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification) hakkında daha fazla bilgi edinin
- [Kuantum bilişimi kavramları](xref:microsoft.quantum.concepts.intro)
- [Quantum Development Kit Örnekleri](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
