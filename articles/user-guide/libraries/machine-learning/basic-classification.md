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
# <a name="basic-classification-classify-data-with-the-qdk"></a><span data-ttu-id="a317d-103">Temel sınıflandırma: verileri QDK ile sınıflandırma</span><span class="sxs-lookup"><span data-stu-id="a317d-103">Basic classification: Classify data with the QDK</span></span>

<span data-ttu-id="a317d-104">Bu hızlı başlangıçta, Q# QDK 'Nin hisse Machine Learning kitaplığı kullanılarak yazılmış bir hisse ve sıralı sınıflandırıcının nasıl çalıştırılacağını öğreneceksiniz.</span><span class="sxs-lookup"><span data-stu-id="a317d-104">In this Quickstart, you will learn how to run a quantum sequential classifier written in Q# using the Quantum Machine Learning library of the QDK.</span></span> 

<span data-ttu-id="a317d-105">Bu kılavuzda, içinde tanımlanan bir sınıflandırıcı yapısını kullanarak yarı ay veri kümesini kullanacağız Q# .</span><span class="sxs-lookup"><span data-stu-id="a317d-105">In this guide we will use the half-moon dataset, using a classifier structure defined in Q#.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a317d-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="a317d-106">Prerequisites</span></span>

- <span data-ttu-id="a317d-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="a317d-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="a317d-108">Q# [Python konak programı](xref:microsoft.quantum.install.python) veya [C# ana bilgisayar programı](xref:microsoft.quantum.install.cs)için bir proje oluşturun.</span><span class="sxs-lookup"><span data-stu-id="a317d-108">Create a Q# project for either a [Python host program](xref:microsoft.quantum.install.python) or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="host-program"></a><span data-ttu-id="a317d-109">Konak programı</span><span class="sxs-lookup"><span data-stu-id="a317d-109">Host program</span></span>

<span data-ttu-id="a317d-110">Ana bilgisayar programınız üç bölümden oluşur:</span><span class="sxs-lookup"><span data-stu-id="a317d-110">Your host program consists of three parts:</span></span>

- <span data-ttu-id="a317d-111">Veri kümesini yükleyin ve modelinize yönelik bir başlangıç parametreleri kümesi seçin.</span><span class="sxs-lookup"><span data-stu-id="a317d-111">Load the dataset and choose a set of starting parameters for your model.</span></span>
- <span data-ttu-id="a317d-112">Modelin parametrelerini ve sapmasını öğrenmek için eğitimi çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="a317d-112">Run training to determine the parameters and bias of the model.</span></span>
- <span data-ttu-id="a317d-113">Doğru olduğunu öğrenmek için modeli doğrulayın</span><span class="sxs-lookup"><span data-stu-id="a317d-113">Validate the model to determine its accuracy</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="a317d-114">Visual Studio Code veya Komut Satırı ile Python</span><span class="sxs-lookup"><span data-stu-id="a317d-114">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="a317d-115">Q#Python 'un sınıflandırıcılarından istediğinizi çalıştırmak için aşağıdaki kodu olarak kaydedin `host.py` .</span><span class="sxs-lookup"><span data-stu-id="a317d-115">To run your the Q# classifier from Python, save the following code as `host.py`.</span></span> <span data-ttu-id="a317d-116">Q#Bu öğreticinin ilerleyen kısımlarında açıklanan dosyanın da gerekli olduğunu unutmayın `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="a317d-116">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    <span data-ttu-id="a317d-117">Ardından Python konak programınızı komut satırından çalıştırabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="a317d-117">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="a317d-118">Visual Studio Code veya Komut Satırı ile C#</span><span class="sxs-lookup"><span data-stu-id="a317d-118">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="a317d-119">Q#C# ' den sınıflandırıcıdır, aşağıdaki kodu olarak kaydedin `Host.cs` .</span><span class="sxs-lookup"><span data-stu-id="a317d-119">To run your the Q# classifier from C#, save the following code as `Host.cs`.</span></span> <span data-ttu-id="a317d-120">Q#Bu öğreticinin ilerleyen kısımlarında açıklanan dosyanın da gerekli olduğunu unutmayın `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="a317d-120">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="a317d-121">Ardından C# konak programınızı komut satırından çalıştırabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="a317d-121">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="a317d-122">Visual Studio 2019 ile C#</span><span class="sxs-lookup"><span data-stu-id="a317d-122">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="a317d-123">Q#Visual Studio 'Da c# ' den yeni programınızı çalıştırmak için `Host.cs` Aşağıdaki c# kodunu içerecek şekilde değiştirin.</span><span class="sxs-lookup"><span data-stu-id="a317d-123">To run your new Q# program from C# in Visual Studio, modify `Host.cs` to include the following C# code.</span></span> <span data-ttu-id="a317d-124">Q#Bu öğreticinin ilerleyen kısımlarında açıklanan dosyanın da gerekli olduğunu unutmayın `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="a317d-124">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="a317d-125">F5 tuşuna basın ve program çalışmaya başlar.</span><span class="sxs-lookup"><span data-stu-id="a317d-125">Press F5, and the program will start to run.</span></span> <span data-ttu-id="a317d-126">Yeni bir pencere, aşağıdaki sonuçları görüntüler:</span><span class="sxs-lookup"><span data-stu-id="a317d-126">A new window will display the following results:</span></span> 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a><span data-ttu-id="a317d-127">Q \# sınıflandırıcı kodu</span><span class="sxs-lookup"><span data-stu-id="a317d-127">Q\# classifier code</span></span>

<span data-ttu-id="a317d-128">Şimdi konak program tarafından çağrılan işlemlerin nasıl tanımlandığını görelim Q# .</span><span class="sxs-lookup"><span data-stu-id="a317d-128">Now let's see how the operations invoked by the host program are defined in Q#.</span></span>
<span data-ttu-id="a317d-129">Aşağıdaki kodu adlı bir dosyaya kaydettik `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="a317d-129">We save the following code in a file named `Training.qs`.</span></span>

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

<span data-ttu-id="a317d-130">Yukarıdaki kodda tanımlanan en önemli işlevler ve işlemler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="a317d-130">The most important functions and operations defined in the code above are:</span></span>

- <span data-ttu-id="a317d-131">`ClassifierStructure() : ControlledRotation[]` : Bu işlevde, düşüntiğimiz denetimli kapıların katmanlarını ekleyerek devre modelimizin yapısını ayarlayacağız.</span><span class="sxs-lookup"><span data-stu-id="a317d-131">`ClassifierStructure() : ControlledRotation[]` : in this function we set the structure of our circuit model by adding the layers of the controlled gates we consider.</span></span> <span data-ttu-id="a317d-132">Bu adım, sıralı bir ayrıntılı öğrenme modelinde, neurlanlar katmanlarının bir bildirimine benzerdir.</span><span class="sxs-lookup"><span data-stu-id="a317d-132">This step is analogous to the declaration of layers of neurons in a sequential deep learning model.</span></span>
- <span data-ttu-id="a317d-133">`TrainHalfMoonModel() : (Double[], Double)` : Bu işlem kodun temel kısmıdır ve eğitimi tanımlar.</span><span class="sxs-lookup"><span data-stu-id="a317d-133">`TrainHalfMoonModel() : (Double[], Double)` : this operation is the core part of the code and defines the training.</span></span> <span data-ttu-id="a317d-134">Burada, kitaplıkta yer alan veri kümesinden örnekleri yüklediğimiz için, eğitimin Hyper parametrelerini ve başlangıç parametrelerini ayarlayacağız ve kitaplığa dahil edilen işlemi çağırarak eğitime başladık `TrainSequentialClassifier` .</span><span class="sxs-lookup"><span data-stu-id="a317d-134">Here we load the samples from the dataset included in the library, we set the hyper parameters and the initial parameters for the training and we start the training by calling the operation `TrainSequentialClassifier` included in the library.</span></span> <span data-ttu-id="a317d-135">Sınıflandırıcının belirlenmesi için parametreleri ve farkı verir.</span><span class="sxs-lookup"><span data-stu-id="a317d-135">It outputs the parameters and the bias that determine the classifier.</span></span>
- <span data-ttu-id="a317d-136">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : Bu işlem, modeli değerlendirmek için doğrulama işlemini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="a317d-136">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : this operation defines the validation process to evaluate the model.</span></span> <span data-ttu-id="a317d-137">Burada doğrulama için örnekleri, örnek başına ölçüm sayısını ve toleransı yükledik.</span><span class="sxs-lookup"><span data-stu-id="a317d-137">Here we load the samples for validation, the number of measurements per sample and the tolerance.</span></span> <span data-ttu-id="a317d-138">Doğrulama için seçilen örnek toplu iş üzerindeki hatalı sınıflandırmaların sayısını verir.</span><span class="sxs-lookup"><span data-stu-id="a317d-138">It outputs the number of misclassifications on the chosen batch of samples for validation.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a317d-139">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="a317d-139">Next steps</span></span>

<span data-ttu-id="a317d-140">İlk olarak, kodla oynatabilir ve öğreticiden nasıl etkilendiğine bakmak için bazı parametreleri değiştirmeyi deneyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a317d-140">First, you can play with the code and try to change some parameters to see how it affects the training.</span></span> <span data-ttu-id="a317d-141">Daha sonra, bir sonraki öğreticide [kendi sınıflandırıcınızı tasarlayabilmeniz](xref:microsoft.quantum.libraries.machine-learning.design)için sınıflandırıcının yapısını nasıl tanımlayacağınızı öğreneceksiniz.</span><span class="sxs-lookup"><span data-stu-id="a317d-141">Then, in the next tutorial, [Design your own classifier](xref:microsoft.quantum.libraries.machine-learning.design),  you will learn how to define the structure of the classifier.</span></span>
