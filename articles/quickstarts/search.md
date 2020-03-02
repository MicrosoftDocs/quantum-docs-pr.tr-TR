---
title: Q# dilinde Grover arama algoritmasını çalıştırma - Quantum Development Kit
description: Standart kuantum algoritmalarından biri olan Grover algoritmasını gösteren bir Q# projesi derleyin.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 0e64fcd56929fa33397c45bf1b2e99bf687eca6f
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906959"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="03804-103">Hızlı Başlangıç: Q# dilinde Grover arama algoritmasını uygulama</span><span class="sxs-lookup"><span data-stu-id="03804-103">Quickstart: Implement Grover's search algorithm in Q#</span></span>

<span data-ttu-id="03804-104">Bu Hızlı Başlangıç’ta, yapılandırılmamış veri aramasını hızlandırmak için Grover araması derlemeyi ve çalıştırmayı öğrenebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="03804-104">In this Quickstart, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="03804-105">Grover araması en popüler kuantum bilişimi algoritmalarından biridir ve görece küçük olan bu Q# uygulaması, kuantum algoritmalarını ifade etmek için üst düzey Q# kuantum programlama dili ile kuantum çözümü programlamanın avantajlarını sunar.</span><span class="sxs-lookup"><span data-stu-id="03804-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="03804-106">Kılavuzun sonunda, klasik bir bilgisayara kıyasla çok daha az sürede sıralı olmayan girişlerden oluşan bir listede belirli bir dizeyi başarıyla bulma sonucunu gösteren simülasyon çıktısını göreceksiniz.</span><span class="sxs-lookup"><span data-stu-id="03804-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of onordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="03804-107">Grover algoritması belirli öğeleri bulmak için yapılandırılmamış bir veri listesinde arama yapar.</span><span class="sxs-lookup"><span data-stu-id="03804-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="03804-108">Örneğin şu soruyu yanıtlayabilir: Bir deste iskambil kağıdından çekilen bu kağıt kupa ası mı?</span><span class="sxs-lookup"><span data-stu-id="03804-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="03804-109">Belirli öğenin etiketlenmesi _işaretlenmiş giriş_ olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="03804-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="03804-110">Grover arama algoritması kullanıldığında, kuantum bilgisayarın bu aramayı aradığınız listedeki öğelerin sayısından daha az adımda çalıştıracağı garantidir; bu klasik algoritmanın yapamayacağı bir şeydir.</span><span class="sxs-lookup"><span data-stu-id="03804-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="03804-111">Bir deste iskambil kağıdı örneğinde hız artışı göz ardı edilebilir ama milyonlarca veya milyarlarca öğe içeren listelerde ciddi bir artış anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="03804-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="03804-112">Grover arama algoritmasını yalnızca birkaç kod satırıyla oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="03804-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="03804-113">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="03804-113">Prerequisites</span></span>

- <span data-ttu-id="03804-114">Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="03804-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="03804-115">Grover arama algoritması ne yapar?</span><span class="sxs-lookup"><span data-stu-id="03804-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="03804-116">Grover algoritması, listedeki bir öğenin bizim aradığımız öğe olup olmadığını sorar.</span><span class="sxs-lookup"><span data-stu-id="03804-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="03804-117">Bunu yapmak için listenin dizinlerinin bir kuantum süper konumunu oluşturur; burada her katsayı veya olasılık genliği belirli bir dizinin aradığınız dizin olma olasılığını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="03804-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="03804-118">Algoritmanın merkezinde aradığımız dizinin katsayısını, bu katsayının olasılık genliği bire yaklaşana kadar aşamalı olarak artıran iki adım vardır.</span><span class="sxs-lookup"><span data-stu-id="03804-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="03804-119">Aşamalı artışların sayısı listedeki öğelerin sayısından azdır.</span><span class="sxs-lookup"><span data-stu-id="03804-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="03804-120">İşte bundan dolayı Grover arama algoritması aramayı klasik algoritmalardan daha az adımda gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="03804-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Grover arama algoritmasının işlevsel diyagramı](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="03804-122">Kodu yazma</span><span class="sxs-lookup"><span data-stu-id="03804-122">Write the code</span></span>

1. <span data-ttu-id="03804-123">Quantum Development Kit'i kullanarak tercih ettiğiniz geliştirme ortamında `Grover` adlı [yeni bir Q# projesi oluşturun](xref:microsoft.quantum.howto.createproject).</span><span class="sxs-lookup"><span data-stu-id="03804-123">Using the Quantum Development Kit, [create a new Q# project](xref:microsoft.quantum.howto.createproject) called `Grover`, in your development environment of choice.</span></span>

1. <span data-ttu-id="03804-124">Yeni projenizin `Operations.qs` dosyasına aşağıdaki kodu ekleyin:</span><span class="sxs-lookup"><span data-stu-id="03804-124">Add the following code to the `Operations.qs` file in your new project:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-40":::

1. <span data-ttu-id="03804-125">Arama yaptığımız listeyi tanımlamak için yeni bir dosya (`Reflections.qs`) oluşturun ve aşağıdaki kodu yapıştırın:</span><span class="sxs-lookup"><span data-stu-id="03804-125">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    <span data-ttu-id="03804-126">`ReflectAboutMarked` işlemi aradığınız işaretlenmiş girişi tanımlar: değişen sıfırlar ve birler dizesi.</span><span class="sxs-lookup"><span data-stu-id="03804-126">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="03804-127">Bu örnek işaretlenmiş girişin sabit kodlamasını yapar ve farklı girişleri aramak veya herhangi bir giriş için genelleştirmek üzere genişletilebilir.</span><span class="sxs-lookup"><span data-stu-id="03804-127">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="03804-128">Ardından `ReflectAboutMarked` ile işaretlenmiş öğeyi bulmak için yeni Q# programınızı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="03804-128">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="03804-129">Visual Studio Code veya Komut Satırı ile Python</span><span class="sxs-lookup"><span data-stu-id="03804-129">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="03804-130">Yeni Q# programınızı Python'dan çalıştırmak için aşağıdaki kodu `host.py` olarak kaydedin:</span><span class="sxs-lookup"><span data-stu-id="03804-130">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

    :::code language="python" source="~/quantum/samples/algorithms/simple-grover/host.py" range="9-14":::

    <span data-ttu-id="03804-131">Ardından Python konak programınızı komut satırından çalıştırabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="03804-131">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="03804-132">Visual Studio Code veya Komut Satırı ile C#</span><span class="sxs-lookup"><span data-stu-id="03804-132">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="03804-133">Yeni Q# programınızı C# dilinden çalıştırmak için `Driver.cs` dosyasını aşağıdaki C# kodunu içerecek şekilde değiştirin:</span><span class="sxs-lookup"><span data-stu-id="03804-133">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    <span data-ttu-id="03804-134">Ardından C# konak programınızı komut satırından çalıştırabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="03804-134">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="03804-135">Visual Studio 2019 ile C#</span><span class="sxs-lookup"><span data-stu-id="03804-135">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="03804-136">Yeni Q# programınızı Visual Studio'da C# dilinde çalıştırmak için `Driver.cs` dosyasını aşağıdaki C# kodunu içerecek şekilde değiştirin:</span><span class="sxs-lookup"><span data-stu-id="03804-136">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    <span data-ttu-id="03804-137">Ardından F5 tuşuna basın; program yürütülmeye başlayacak ve aşağıdaki sonuçları içeren yeni bir pencere açılacaktır:</span><span class="sxs-lookup"><span data-stu-id="03804-137">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

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

    <span data-ttu-id="03804-138">`ReflectAboutMarked` işlemi yalnızca dört kez çağrılır ama Q# programınız $2^{5} = 32$ olası giriş arasından "01010" girişini bulmuştur!</span><span class="sxs-lookup"><span data-stu-id="03804-138">The `ReflectAboutMarked` operation is called only four times, but your Q# program was able to find the "01010" input amongst $2^{5} = 32$ possible inputs!</span></span>

## <a name="next-steps"></a><span data-ttu-id="03804-139">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="03804-139">Next steps</span></span>

<span data-ttu-id="03804-140">Bu hızlı başlangıçtan keyif aldıysanız, Q# kullanarak kendi kuantum uygulamalarınızı nasıl yazabileceğiniz hakkında daha fazla bilgi edinmek için aşağıdaki kaynaklardan bazılarını gözden geçirin:</span><span class="sxs-lookup"><span data-stu-id="03804-140">If you enjoyed this quickstart, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="03804-141">QDK'yı Kullanmaya Başlama kılavuzuna dön</span><span class="sxs-lookup"><span data-stu-id="03804-141">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="03804-142">Daha genel bir Grover arama algoritması [örneğini](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) deneyin</span><span class="sxs-lookup"><span data-stu-id="03804-142">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="03804-143">Kuantum Katalarıyla Grover araması hakkında daha fazla bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="03804-143">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="03804-144">Grover arama algoritmasının arkasındaki kuantum bilişim tekniği olan [genliğini yükseltme](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification) hakkında daha fazla bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="03804-144">Read more about [Amplitude amplification](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="03804-145">Kuantum bilişimi kavramları</span><span class="sxs-lookup"><span data-stu-id="03804-145">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="03804-146">Quantum Development Kit Örnekleri</span><span class="sxs-lookup"><span data-stu-id="03804-146">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
