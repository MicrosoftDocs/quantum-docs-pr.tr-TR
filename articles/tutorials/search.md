---
title: Q# dilinde Grover arama algoritmasını çalıştırma - Quantum Development Kit
description: Standart kuantum algoritmalarından biri olan Grover algoritmasını gösteren bir Q# projesi derleyin.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 9e4c53b4d5159cf07f0654603c1d477ad09eb7c6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275264"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="723a0-103">Öğretici: Q\# dilinde Grover arama algoritmasını uygulama</span><span class="sxs-lookup"><span data-stu-id="723a0-103">Tutorial: Implement Grover's search algorithm in Q\#</span></span>

<span data-ttu-id="723a0-104">Bu öğreticide, yapılandırılmamış veri aramasını hızlandırmak için Grover araması oluşturmayı ve çalıştırmayı öğrenebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="723a0-104">In this tutorial, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="723a0-105">Grover araması en popüler kuantum bilişimi algoritmalarından biridir ve görece küçük olan bu Q# uygulaması, kuantum algoritmalarını ifade etmek için üst düzey Q# kuantum programlama dili ile kuantum çözümü programlamanın avantajlarını sunar.</span><span class="sxs-lookup"><span data-stu-id="723a0-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="723a0-106">Kılavuzun sonunda, klasik bir bilgisayara kıyasla çok daha kısa sürede, sıralı olmayan girişlerden oluşan bir listede belirli bir dizeyi başarıyla bulma sonucunu gösteren simülasyon çıktısını göreceksiniz.</span><span class="sxs-lookup"><span data-stu-id="723a0-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of unordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="723a0-107">Grover algoritması belirli öğeleri bulmak için yapılandırılmamış bir veri listesinde arama yapar.</span><span class="sxs-lookup"><span data-stu-id="723a0-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="723a0-108">Örneğin şu soruyu yanıtlayabilir: Bir deste iskambil kağıdından çekilen bu kağıt kupa ası mı?</span><span class="sxs-lookup"><span data-stu-id="723a0-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="723a0-109">Belirli öğenin etiketlenmesi _işaretlenmiş giriş_ olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="723a0-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="723a0-110">Grover arama algoritması kullanıldığında, kuantum bilgisayarın bu aramayı aradığınız listedeki öğelerin sayısından daha az adımda çalıştıracağı garantidir; bu klasik algoritmanın yapamayacağı bir şeydir.</span><span class="sxs-lookup"><span data-stu-id="723a0-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="723a0-111">Bir deste iskambil kağıdı örneğinde hız artışı göz ardı edilebilir ama milyonlarca veya milyarlarca öğe içeren listelerde ciddi bir artış anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="723a0-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="723a0-112">Grover arama algoritmasını yalnızca birkaç kod satırıyla oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="723a0-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="723a0-113">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="723a0-113">Prerequisites</span></span>

- <span data-ttu-id="723a0-114">Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="723a0-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="723a0-115">Grover arama algoritması ne yapar?</span><span class="sxs-lookup"><span data-stu-id="723a0-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="723a0-116">Grover algoritması, listedeki bir öğenin bizim aradığımız öğe olup olmadığını sorar.</span><span class="sxs-lookup"><span data-stu-id="723a0-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="723a0-117">Bunu yapmak için listenin dizinlerinin bir kuantum süper konumunu oluşturur; burada her katsayı veya olasılık genliği belirli bir dizinin aradığınız dizin olma olasılığını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="723a0-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="723a0-118">Algoritmanın merkezinde aradığımız dizinin katsayısını, bu katsayının olasılık genliği bire yaklaşana kadar aşamalı olarak artıran iki adım vardır.</span><span class="sxs-lookup"><span data-stu-id="723a0-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="723a0-119">Aşamalı artışların sayısı listedeki öğelerin sayısından azdır.</span><span class="sxs-lookup"><span data-stu-id="723a0-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="723a0-120">İşte bundan dolayı Grover arama algoritması aramayı klasik algoritmalardan daha az adımda gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="723a0-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Grover arama algoritmasının işlevsel diyagramı](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="723a0-122">Kodu yazma</span><span class="sxs-lookup"><span data-stu-id="723a0-122">Write the code</span></span>

1. <span data-ttu-id="723a0-123">Quantum geliştirme setini kullanarak, [komut satırı uygulaması için yeni bir Q# projesi oluşturun](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="723a0-123">Using the Quantum Development Kit, [create a new Q# project for the command line application](xref:microsoft.quantum.install.standalone).</span></span> <span data-ttu-id="723a0-124">Projeye `Grover` başlığını verin.</span><span class="sxs-lookup"><span data-stu-id="723a0-124">Title the project `Grover`.</span></span>

1. <span data-ttu-id="723a0-125">Yeni projenizin `Program.qs` dosyasına aşağıdaki kodu ekleyin:</span><span class="sxs-lookup"><span data-stu-id="723a0-125">Add the following code to the `Program.qs` file in your new project:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. <span data-ttu-id="723a0-126">Arama yaptığımız listeyi tanımlamak için yeni bir dosya (`Reflections.qs`) oluşturun ve aşağıdaki kodu yapıştırın:</span><span class="sxs-lookup"><span data-stu-id="723a0-126">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    <span data-ttu-id="723a0-127">`ReflectAboutMarked` işlemi aradığınız işaretlenmiş girişi tanımlar: değişen sıfırlar ve birler dizesi.</span><span class="sxs-lookup"><span data-stu-id="723a0-127">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="723a0-128">Bu örnek işaretlenmiş girişin sabit kodlamasını yapar ve farklı girişleri aramak veya herhangi bir giriş için genelleştirmek üzere genişletilebilir.</span><span class="sxs-lookup"><span data-stu-id="723a0-128">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="723a0-129">Ardından `ReflectAboutMarked` ile işaretlenmiş öğeyi bulmak için yeni Q# programınızı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="723a0-129">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a><span data-ttu-id="723a0-130">Visual Studio veya Visual Studio Code ile Q# komut satırı uygulamaları</span><span class="sxs-lookup"><span data-stu-id="723a0-130">Q# command line applications with Visual Studio or Visual Studio Code</span></span>

<span data-ttu-id="723a0-131">Yürütülebilir dosya, proje yapılandırmasına ve komut satırı seçeneklerine bağlı olarak simülatör veya kaynak tahmini aracında `@EntryPoint()` özniteliğiyle işaretlenmiş işlemi ya da işlevi çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="723a0-131">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

<span data-ttu-id="723a0-132">Visual Studio’da betiği yürütmek için Ctrl + F5 tuşlarına basmanız yeterlidir.</span><span class="sxs-lookup"><span data-stu-id="723a0-132">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="723a0-133">VS Code’da terminale aşağıdakileri yazarak `Program.qs` dosyasını ilk kez derleyin:</span><span class="sxs-lookup"><span data-stu-id="723a0-133">In VS Code, build the `Program.qs` the first time by typing the below in the terminal:</span></span>

```Command line
dotnet build
```

<span data-ttu-id="723a0-134">Sonraki çalıştırmalar için tekrar derlenmesi gerekmez.</span><span class="sxs-lookup"><span data-stu-id="723a0-134">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="723a0-135">Çalıştırmak için aşağıdaki komutu girin ve Enter tuşuna basın:</span><span class="sxs-lookup"><span data-stu-id="723a0-135">To run it, type the following command and press enter:</span></span>

```Command line
dotnet run --no-build
```

<span data-ttu-id="723a0-136">Terminalde şu ileti görüntülenmelidir:</span><span class="sxs-lookup"><span data-stu-id="723a0-136">You should see the following message displayed in the terminal:</span></span>

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

<span data-ttu-id="723a0-137">Bu, kullanmak istediğiniz kubit sayısını belirtmemeniz nedeniyle terminalin yürütülebilir dosya için kullanılabilir olan komutları size bildirmesinden kaynaklanır.</span><span class="sxs-lookup"><span data-stu-id="723a0-137">This is because you didn't specify the number of qubits you wanted to use, so the terminal tells you the commands available for the executable.</span></span> <span data-ttu-id="723a0-138">5 kubit kullanmak istiyorsak şunu yazmamız gerekir:</span><span class="sxs-lookup"><span data-stu-id="723a0-138">If we want to use 5 qubits we should type:</span></span>

```Command line
dotnet run --n-qubits 5
```

<span data-ttu-id="723a0-139">Enter tuşuna bastığınızda şu çıktıyı görmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="723a0-139">Pressing enter you should see the following output:</span></span>

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a><span data-ttu-id="723a0-140">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="723a0-140">Next steps</span></span>

<span data-ttu-id="723a0-141">Bu öğreticiden keyif aldıysanız, Q# kullanarak kendi kuantum uygulamalarınızı nasıl yazabileceğiniz hakkında daha fazla bilgi edinmek için aşağıdaki kaynaklardan bazılarını gözden geçirin:</span><span class="sxs-lookup"><span data-stu-id="723a0-141">If you enjoyed this tutorial, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="723a0-142">QDK'yı Kullanmaya Başlama kılavuzuna dön</span><span class="sxs-lookup"><span data-stu-id="723a0-142">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="723a0-143">Daha genel bir Grover arama algoritması [örneğini](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) deneyin</span><span class="sxs-lookup"><span data-stu-id="723a0-143">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="723a0-144">Kuantum Katalarıyla Grover araması hakkında daha fazla bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="723a0-144">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="723a0-145">Grover arama algoritmasının arkasındaki kuantum bilişim tekniği olan [genliğini yükseltme][amplitude-amplification] hakkında daha fazla bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="723a0-145">Read more about [Amplitude amplification][amplitude-amplification], the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="723a0-146">Kuantum bilişimi kavramları</span><span class="sxs-lookup"><span data-stu-id="723a0-146">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="723a0-147">Quantum Development Kit Örnekleri</span><span class="sxs-lookup"><span data-stu-id="723a0-147">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification