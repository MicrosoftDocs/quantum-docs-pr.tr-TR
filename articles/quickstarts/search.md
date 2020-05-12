---
title: Q# dilinde Grover arama algoritmasını çalıştırma - Quantum Development Kit
description: Standart kuantum algoritmalarından biri olan Grover algoritmasını gösteren bir Q# projesi derleyin.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: c67ccd16957ceef694552bdd9c073ba5a35d8aaf
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82686838"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="1ac5d-103">Hızlı Başlangıç: Q\# dilinde Grover arama algoritmasını uygulama</span><span class="sxs-lookup"><span data-stu-id="1ac5d-103">Quickstart: Implement Grover's search algorithm in Q\#</span></span>

<span data-ttu-id="1ac5d-104">Bu Hızlı Başlangıç’ta, yapılandırılmamış veri aramasını hızlandırmak için Grover araması derlemeyi ve çalıştırmayı öğrenebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-104">In this Quickstart, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="1ac5d-105">Grover araması en popüler kuantum bilişimi algoritmalarından biridir ve görece küçük olan bu Q# uygulaması, kuantum algoritmalarını ifade etmek için üst düzey Q# kuantum programlama dili ile kuantum çözümü programlamanın avantajlarını sunar.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="1ac5d-106">Kılavuzun sonunda, klasik bir bilgisayara kıyasla çok daha kısa sürede, sıralı olmayan girişlerden oluşan bir listede belirli bir dizeyi başarıyla bulma sonucunu gösteren simülasyon çıktısını göreceksiniz.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of unordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="1ac5d-107">Grover algoritması belirli öğeleri bulmak için yapılandırılmamış bir veri listesinde arama yapar.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="1ac5d-108">Örneğin şu soruyu yanıtlayabilir: Bir deste iskambil kağıdından çekilen bu kağıt kupa ası mı?</span><span class="sxs-lookup"><span data-stu-id="1ac5d-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="1ac5d-109">Belirli öğenin etiketlenmesi _işaretlenmiş giriş_ olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="1ac5d-110">Grover arama algoritması kullanıldığında, kuantum bilgisayarın bu aramayı aradığınız listedeki öğelerin sayısından daha az adımda çalıştıracağı garantidir; bu klasik algoritmanın yapamayacağı bir şeydir.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="1ac5d-111">Bir deste iskambil kağıdı örneğinde hız artışı göz ardı edilebilir ama milyonlarca veya milyarlarca öğe içeren listelerde ciddi bir artış anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="1ac5d-112">Grover arama algoritmasını yalnızca birkaç kod satırıyla oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1ac5d-113">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="1ac5d-113">Prerequisites</span></span>

- <span data-ttu-id="1ac5d-114">Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="1ac5d-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="1ac5d-115">Grover arama algoritması ne yapar?</span><span class="sxs-lookup"><span data-stu-id="1ac5d-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="1ac5d-116">Grover algoritması, listedeki bir öğenin bizim aradığımız öğe olup olmadığını sorar.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="1ac5d-117">Bunu yapmak için listenin dizinlerinin bir kuantum süper konumunu oluşturur; burada her katsayı veya olasılık genliği belirli bir dizinin aradığınız dizin olma olasılığını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="1ac5d-118">Algoritmanın merkezinde aradığımız dizinin katsayısını, bu katsayının olasılık genliği bire yaklaşana kadar aşamalı olarak artıran iki adım vardır.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="1ac5d-119">Aşamalı artışların sayısı listedeki öğelerin sayısından azdır.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="1ac5d-120">İşte bundan dolayı Grover arama algoritması aramayı klasik algoritmalardan daha az adımda gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Grover arama algoritmasının işlevsel diyagramı](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="1ac5d-122">Kodu yazma</span><span class="sxs-lookup"><span data-stu-id="1ac5d-122">Write the code</span></span>

1. <span data-ttu-id="1ac5d-123">Quantum Development Kit'i kullanarak tercih ettiğiniz geliştirme ortamında `Grover` adlı [yeni bir Q# projesi oluşturun](xref:microsoft.quantum.howto.createproject).</span><span class="sxs-lookup"><span data-stu-id="1ac5d-123">Using the Quantum Development Kit, [create a new Q# project](xref:microsoft.quantum.howto.createproject) called `Grover`, in your development environment of choice.</span></span>

1. <span data-ttu-id="1ac5d-124">Yeni projenizin `Program.qs` dosyasına aşağıdaki kodu ekleyin:</span><span class="sxs-lookup"><span data-stu-id="1ac5d-124">Add the following code to the `Program.qs` file in your new project:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. <span data-ttu-id="1ac5d-125">Arama yaptığımız listeyi tanımlamak için yeni bir dosya (`Reflections.qs`) oluşturun ve aşağıdaki kodu yapıştırın:</span><span class="sxs-lookup"><span data-stu-id="1ac5d-125">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    <span data-ttu-id="1ac5d-126">`ReflectAboutMarked` işlemi aradığınız işaretlenmiş girişi tanımlar: değişen sıfırlar ve birler dizesi.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-126">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="1ac5d-127">Bu örnek işaretlenmiş girişin sabit kodlamasını yapar ve farklı girişleri aramak veya herhangi bir giriş için genelleştirmek üzere genişletilebilir.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-127">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="1ac5d-128">Ardından `ReflectAboutMarked` ile işaretlenmiş öğeyi bulmak için yeni Q# programınızı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-128">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a><span data-ttu-id="1ac5d-129">Visual Studio veya Visual Studio Code ile Q# komut satırı uygulamaları</span><span class="sxs-lookup"><span data-stu-id="1ac5d-129">Q# command line applications with Visual Studio or Visual Studio Code</span></span>

<span data-ttu-id="1ac5d-130">Yürütülebilir dosya, proje yapılandırmasına ve komut satırı seçeneklerine bağlı olarak simülatör veya kaynak tahmini aracında `@EntryPoint()` özniteliğiyle işaretlenmiş işlemi ya da işlevi çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-130">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

<span data-ttu-id="1ac5d-131">Visual Studio’da betiği yürütmek için Ctrl + F5 tuşlarına basmanız yeterlidir.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-131">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="1ac5d-132">VS Code’da terminale aşağıdakileri yazarak `Program.qs` dosyasını ilk kez derleyin:</span><span class="sxs-lookup"><span data-stu-id="1ac5d-132">In VS Code, build the `Program.qs` the first time by typing the below in the terminal:</span></span>

```Command line
dotnet build
```

<span data-ttu-id="1ac5d-133">Sonraki çalıştırmalar için tekrar derlenmesi gerekmez.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-133">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="1ac5d-134">Çalıştırmak için aşağıdaki komutu girin ve Enter tuşuna basın:</span><span class="sxs-lookup"><span data-stu-id="1ac5d-134">To run it, type the following command and press enter:</span></span>

```Command line
dotnet run --no-build
```

<span data-ttu-id="1ac5d-135">Terminalde şu ileti görüntülenmelidir:</span><span class="sxs-lookup"><span data-stu-id="1ac5d-135">You should see the following message displayed in the terminal:</span></span>

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

<span data-ttu-id="1ac5d-136">Bu, kullanmak istediğiniz kubit sayısını belirtmemeniz nedeniyle terminalin yürütülebilir dosya için kullanılabilir olan komutları size bildirmesinden kaynaklanır.</span><span class="sxs-lookup"><span data-stu-id="1ac5d-136">This is because you didn't specify the number of qubits you wanted to use, so the terminal tells you the commands available for the executable.</span></span> <span data-ttu-id="1ac5d-137">5 kubit kullanmak istiyorsak şunu yazmamız gerekir:</span><span class="sxs-lookup"><span data-stu-id="1ac5d-137">If we want to use 5 qubits we should type:</span></span>

```Command line
dotnet run --n-qubits 5
```

<span data-ttu-id="1ac5d-138">Enter tuşuna bastığınızda şu çıktıyı görmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="1ac5d-138">Pressing enter you should see the following output:</span></span>

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a><span data-ttu-id="1ac5d-139">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="1ac5d-139">Next steps</span></span>

<span data-ttu-id="1ac5d-140">Bu hızlı başlangıçtan keyif aldıysanız, Q# kullanarak kendi kuantum uygulamalarınızı nasıl yazabileceğiniz hakkında daha fazla bilgi edinmek için aşağıdaki kaynaklardan bazılarını gözden geçirin:</span><span class="sxs-lookup"><span data-stu-id="1ac5d-140">If you enjoyed this quickstart, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="1ac5d-141">QDK'yı Kullanmaya Başlama kılavuzuna dön</span><span class="sxs-lookup"><span data-stu-id="1ac5d-141">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="1ac5d-142">Daha genel bir Grover arama algoritması [örneğini](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) deneyin</span><span class="sxs-lookup"><span data-stu-id="1ac5d-142">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="1ac5d-143">Kuantum Katalarıyla Grover araması hakkında daha fazla bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="1ac5d-143">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="1ac5d-144">Grover arama algoritmasının arkasındaki kuantum bilişim tekniği olan [genliğini yükseltme][amplitude-amplification] hakkında daha fazla bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="1ac5d-144">Read more about [Amplitude amplification][amplitude-amplification], the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="1ac5d-145">Kuantum bilişimi kavramları</span><span class="sxs-lookup"><span data-stu-id="1ac5d-145">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="1ac5d-146">Quantum Development Kit Örnekleri</span><span class="sxs-lookup"><span data-stu-id="1ac5d-146">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
