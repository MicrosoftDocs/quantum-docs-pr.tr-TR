---
title: Grover 'in arama algoritmasını Q# -hisse geliştirme seti 'nde Çalıştır
description: Q#Kurallı hisse algoritmalarından biri olan Grover 'in algoritmasını gösteren bir proje oluşturun.
author: cgranade
ms.author: chgranad
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
no-loc:
- Q#
- $$v
ms.openlocfilehash: 86c6a651a117b788eb4c8fdd805ead7ab8f54dd7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834814"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a>Öğretici: Q\# dilinde Grover arama algoritmasını uygulama

Bu öğreticide, yapılandırılmamış veri aramasını hızlandırmak için Grover araması oluşturmayı ve çalıştırmayı öğrenebilirsiniz.  Grover 'in arama en popüler hisse bilgi işlem algoritmalarından biridir ve bu görece küçük uygulama, Q# hızlı bir şekilde yüksek düzeyde bir hisse programlama diliyle hızlı bir şekilde daha fazla bilgi sahibi olmak için bir miktar çözüm sunan bazı avantajlardan yararlanmanızı sağlar Q# .  Kılavuzun sonunda, klasik bir bilgisayara kıyasla çok daha kısa sürede, sıralı olmayan girişlerden oluşan bir listede belirli bir dizeyi başarıyla bulma sonucunu gösteren simülasyon çıktısını göreceksiniz.

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

1. Hisse geliştirme setini kullanarak, [ Q# uygulama için yeni bir proje oluşturun](xref:microsoft.quantum.install.standalone). Projeye `Grover` başlığını verin.

1. Yeni projenizin `Program.qs` dosyasına aşağıdaki kodu ekleyin:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. Arama yaptığımız listeyi tanımlamak için yeni bir dosya (`Reflections.qs`) oluşturun ve aşağıdaki kodu yapıştırın:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    `ReflectAboutMarked` işlemi aradığınız işaretlenmiş girişi tanımlar: değişen sıfırlar ve birler dizesi. Bu örnek işaretlenmiş girişin sabit kodlamasını yapar ve farklı girişleri aramak veya herhangi bir giriş için genelleştirmek üzere genişletilebilir.

1. Sonra, Q# tarafından işaretlenmiş öğeyi bulmak için yeni programınızı çalıştırın `ReflectAboutMarked` .

### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a>Q# Visual Studio veya Visual Studio Code ile uygulamalar

Program, `@EntryPoint()` Proje yapılandırmasına ve komut satırı seçeneklerine bağlı olarak, bir simülatör veya kaynak Estimator üzerinde özniteliğiyle işaretlenmiş işlem veya işlevi çalıştırır.

Visual Studio 'da, komut dosyasını çalıştırmak için CTRL + F5 tuşlarına basmanız yeterlidir.

VS Code’da terminale aşağıdakileri yazarak `Program.qs` dosyasını ilk kez derleyin:

```Command line
dotnet build
```

Sonraki çalıştırmalar için tekrar derlenmesi gerekmez. Çalıştırmak için aşağıdaki komutu girin ve Enter tuşuna basın:

```Command line
dotnet run --no-build
```

Terminalde şu ileti görüntülenmelidir:

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

Bunun nedeni, kullanmak istediğiniz qubit sayısını belirtmediğinizden, Terminal, yürütülebilir program için kullanılabilen komutları gösterir. 5 qubit kullanmak istiyoruz, şunu yazmalıyım:

```Command line
dotnet run --n-qubits 5
```

Enter tuşuna bastığınızda şu çıktıyı görmeniz gerekir:

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticiyi kullandıysanız, Q# kendi hisse ve uygulamalarınızı yazmak üzere nasıl kullanabileceğiniz hakkında daha fazla bilgi edinmek için aşağıdaki kaynaklara göz atın:

- [QDK'yı Kullanmaya Başlama kılavuzuna dön](xref:microsoft.quantum.welcome)
- Daha genel bir Grover arama algoritması [örneğini](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/database-search) deneyin
- [Kuantum Katalarıyla Grover araması hakkında daha fazla bilgi edinin](xref:microsoft.quantum.overview.katas)
- Grover arama algoritmasının arkasındaki kuantum bilişim tekniği olan [genliğini yükseltme][amplitude-amplification] hakkında daha fazla bilgi edinin
- [Kuantum bilişimi kavramları](xref:microsoft.quantum.concepts.intro)
- [Quantum Development Kit Örnekleri](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
