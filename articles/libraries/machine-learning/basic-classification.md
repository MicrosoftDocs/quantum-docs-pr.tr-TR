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
# <a name="basic-classification-classify-data-with-the-qdk"></a><span data-ttu-id="f7f0d-103">Temel sınıflandırma: verileri QDK ile sınıflandırma</span><span class="sxs-lookup"><span data-stu-id="f7f0d-103">Basic classification: Classify data with the QDK</span></span>

<span data-ttu-id="f7f0d-104">Bu hızlı başlangıçta, QDK 'nin hisse Machine Learning kitaplığını kullanarak Q # dilinde yazılmış bir hisse ve sıralı sınıflandırıcının nasıl yürütüleceğini öğreneceksiniz.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-104">In this Quickstart, you will learn how to execute a quantum sequential classifier written in Q# using the Quantum Machine Learning library of the QDK.</span></span> 

<span data-ttu-id="f7f0d-105">Bu kılavuzda, Q # içinde tanımlanan bir sınıflandırıcı yapısını kullanarak yarı ay veri kümesini kullanacağız.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-105">In this guide we will use the half-moon dataset, using a classifier structure defined in Q#.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f7f0d-106">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="f7f0d-106">Prerequisites</span></span>

- <span data-ttu-id="f7f0d-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="f7f0d-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="f7f0d-108">Q# projesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="f7f0d-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)

## <a name="host-program"></a><span data-ttu-id="f7f0d-109">Konak programı</span><span class="sxs-lookup"><span data-stu-id="f7f0d-109">Host program</span></span>

<span data-ttu-id="f7f0d-110">Ana bilgisayar programınız üç bölümden oluşur:</span><span class="sxs-lookup"><span data-stu-id="f7f0d-110">Your host program consists of three parts:</span></span>

- <span data-ttu-id="f7f0d-111">Veri kümesini yükleyin ve modelinize yönelik bir başlangıç parametreleri kümesi seçin.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-111">Load the dataset and choose a set of starting parameters for your model.</span></span>
- <span data-ttu-id="f7f0d-112">Modelin parametrelerini ve sapmasını öğrenmek için eğitimi yürütün.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-112">Execute training to determine the parameters and bias of the model.</span></span>
- <span data-ttu-id="f7f0d-113">Doğru olduğunu öğrenmek için modeli doğrulayın</span><span class="sxs-lookup"><span data-stu-id="f7f0d-113">Validate the model to determine its accuracy</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="f7f0d-114">Visual Studio Code veya Komut Satırı ile Python</span><span class="sxs-lookup"><span data-stu-id="f7f0d-114">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="f7f0d-115">Python 'dan gelen Q # sınıflandırıcınızı çalıştırmak için aşağıdaki kodu `host.py`olarak kaydedin.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-115">To run your the Q# classifier from Python, save the following code as `host.py`.</span></span> <span data-ttu-id="f7f0d-116">Bu öğreticinin ilerleyen kısımlarında açıklanan Q # dosyası `Training.qs` de ihtiyacınız olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-116">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    <span data-ttu-id="f7f0d-117">Ardından Python konak programınızı komut satırından çalıştırabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="f7f0d-117">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="f7f0d-118">Visual Studio Code veya Komut Satırı ile C#</span><span class="sxs-lookup"><span data-stu-id="f7f0d-118">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="f7f0d-119">Size gelen C#Q # sınıflandırıcınızı çalıştırmak için aşağıdaki kodu `Host.cs`olarak kaydedin.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-119">To run your the Q# classifier from C#, save the following code as `Host.cs`.</span></span> <span data-ttu-id="f7f0d-120">Bu öğreticinin ilerleyen kısımlarında açıklanan Q # dosyası `Training.qs` de ihtiyacınız olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-120">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="f7f0d-121">Ardından C# konak programınızı komut satırından çalıştırabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="f7f0d-121">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="f7f0d-122">Visual Studio 2019 ile C#</span><span class="sxs-lookup"><span data-stu-id="f7f0d-122">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="f7f0d-123">Yeni Q # programınızı Visual Studio C# 'da çalıştırmak için `Host.cs` aşağıdaki C# kodu içerecek şekilde değiştirin.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-123">To run your new Q# program from C# in Visual Studio, modify `Host.cs` to include the following C# code.</span></span> <span data-ttu-id="f7f0d-124">Bu öğreticinin ilerleyen kısımlarında açıklanan Q # dosyası `Training.qs` de ihtiyacınız olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-124">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="f7f0d-125">Ardından F5 tuşuna basın; program yürütülmeye başlayacak ve aşağıdaki sonuçları içeren yeni bir pencere açılacaktır:</span><span class="sxs-lookup"><span data-stu-id="f7f0d-125">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a><span data-ttu-id="f7f0d-126">Soru\# sınıflandırıcı kodu</span><span class="sxs-lookup"><span data-stu-id="f7f0d-126">Q\# classifier code</span></span>

<span data-ttu-id="f7f0d-127">Şimdi, ana bilgisayar programı tarafından çağrılan işlemlerin Q # içinde nasıl tanımlandığını görelim.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-127">Now let's see how the operations invoked by the host program are defined in Q#.</span></span>
<span data-ttu-id="f7f0d-128">Aşağıdaki kodu `Training.qs`adlı bir dosyaya kaydettik.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-128">We save the following code in a file named `Training.qs`.</span></span>

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

<span data-ttu-id="f7f0d-129">Yukarıdaki kodda tanımlanan en önemli işlevler ve işlemler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="f7f0d-129">The most important functions and operations defined in the code above are:</span></span>

- <span data-ttu-id="f7f0d-130">`ClassifierStructure() : ControlledRotation[]`: Bu işlevde, düşüntiğimiz denetimli kapıların katmanlarını ekleyerek devre modelimizin yapısını ayarlayacağız.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-130">`ClassifierStructure() : ControlledRotation[]` : in this function we set the structure of our circuit model by adding the layers of the controlled gates we consider.</span></span> <span data-ttu-id="f7f0d-131">Bu adım, sıralı bir ayrıntılı öğrenme modelinde, neurlanlar katmanlarının bir bildirimine benzerdir.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-131">This step is analogous to the declaration of layers of neurons in a sequential deep learning model.</span></span>
- <span data-ttu-id="f7f0d-132">`TrainHalfMoonModel() : TrainWineModel() : (Double[], Double)`: Bu işlem kodun temel kısmıdır ve eğitimi tanımlar.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-132">`TrainHalfMoonModel() : TrainWineModel() : (Double[], Double)` : this operation is the core part of the code and defines the training.</span></span> <span data-ttu-id="f7f0d-133">Burada, kitaplıkta yer alan veri kümesinden örnekleri yüklediğimiz için, eğitimin Hyper parametrelerini ve başlangıç parametrelerini ayarlayacağız ve kitaplığa dahil edilen işlemi `TrainSequentialClassifier` çağırarak eğitime başladık.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-133">Here we load the samples from the dataset included in the library, we set the hyper parameters and the initial parameters for the training and we start the training by calling the operation `TrainSequentialClassifier` included in the library.</span></span> <span data-ttu-id="f7f0d-134">Sınıflandırıcının belirlenmesi için parametreleri ve farkı verir.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-134">It outputs the parameters and the bias that determine the classifier.</span></span>
- <span data-ttu-id="f7f0d-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`: Bu işlem, modeli değerlendirmek için doğrulama işlemini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : this operation defines the validation process to evaluate the model.</span></span> <span data-ttu-id="f7f0d-136">Burada doğrulama için örnekleri, örnek başına ölçüm sayısını ve toleransı yükledik.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-136">Here we load the samples for validation, the number of measurements per sample and the tolerance.</span></span> <span data-ttu-id="f7f0d-137">Doğrulama için seçilen örnek toplu iş üzerindeki hatalı sınıflandırmaların sayısını verir.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-137">It outputs the number of misclassifications on the chosen batch of samples for validation.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f7f0d-138">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="f7f0d-138">Next steps</span></span>

<span data-ttu-id="f7f0d-139">İlk olarak, kodla oynatabilir ve öğreticiden nasıl etkilendiğine bakmak için bazı parametreleri değiştirmeyi deneyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-139">First, you can play with the code and try to change some parameters to see how it affects the training.</span></span> <span data-ttu-id="f7f0d-140">Daha sonra, bir sonraki öğreticide [kendi sınıflandırıcınızı tasarlayabilmeniz](xref:microsoft.quantum.libraries.machine-learning.design)için sınıflandırıcının yapısını nasıl tanımlayacağınızı öğreneceksiniz.</span><span class="sxs-lookup"><span data-stu-id="f7f0d-140">Then, in the next tutorial, [Design your own classifier](xref:microsoft.quantum.libraries.machine-learning.design),  you will learn how to define the structure of the classifier.</span></span>
