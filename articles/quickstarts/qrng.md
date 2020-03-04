---
title: Kuantum Rastgele Sayı Oluşturucusu Oluşturma
description: Kuantum rastgele sayı oluşturucusu tasarlayarak süper konum gibi temel kuantum kavramlarını gösteren bir Q# projesi oluşturun.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: b9c8592b1296a7de1b9ad5d0538ad1972ec25e31
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906993"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="6d972-103">Hızlı Başlangıç: Q# ile Kuantum Rastgele Sayı Oluşturucusu Oluşturma Tasarlama</span><span class="sxs-lookup"><span data-stu-id="6d972-103">Quickstart: Implement a Quantum Random Number Generator in Q#</span></span>
<span data-ttu-id="6d972-104">Kuantum rastgele sayı oluşturucusu, Q# dilinde yazılmış kuantum algoritmalarına örnek olarak gösterilebilir.</span><span class="sxs-lookup"><span data-stu-id="6d972-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="6d972-105">Bu algoritma, kuantum mekaniklerinin özelliklerinden faydalanarak rastgele bir sayı üretir.</span><span class="sxs-lookup"><span data-stu-id="6d972-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="6d972-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="6d972-106">Prerequisites</span></span>

- <span data-ttu-id="6d972-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="6d972-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="6d972-108">Q# projesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="6d972-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a><span data-ttu-id="6d972-109">Q# işlemi yazma</span><span class="sxs-lookup"><span data-stu-id="6d972-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="6d972-110">Q# işlem kodu</span><span class="sxs-lookup"><span data-stu-id="6d972-110">Q# operation code</span></span>

1. <span data-ttu-id="6d972-111">Operation.qs dosyasının içeriğini aşağıdaki kodla değiştirin:</span><span class="sxs-lookup"><span data-stu-id="6d972-111">Replace the contents of the Operation.qs file with the following code:</span></span>

 :::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-14":::

<span data-ttu-id="6d972-112">[Kuantum Bilişimi nedir?](xref:microsoft.quantum.overview.what) makalesinde de belirttiğimiz gibi kubit, süper konumda olabilen bir kuantum bilgi birimidir.</span><span class="sxs-lookup"><span data-stu-id="6d972-112">As mentioned in our [What is Quantum Computing?](xref:microsoft.quantum.overview.what) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="6d972-113">Bir kubit ölçüldüğünde yalnızca 0 veya 1 olabilir.</span><span class="sxs-lookup"><span data-stu-id="6d972-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="6d972-114">Ancak yürütme sırasında kubitin durumu bir ölçümle 0 veya 1 değerini elde etme olasılığını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="6d972-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="6d972-115">Olasılığa dayalı olan bu durum, süper konum olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="6d972-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="6d972-116">Bu olasılığı kullanarak rastgele sayı oluşturabiliriz.</span><span class="sxs-lookup"><span data-stu-id="6d972-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="6d972-117">Q# işlemimizde yerel bir Q# veri türü olan `Qubit` veri türünü kullanacağız.</span><span class="sxs-lookup"><span data-stu-id="6d972-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="6d972-118">`Qubit` ayırmak için `using` deyimi kullanmamız gerekir.</span><span class="sxs-lookup"><span data-stu-id="6d972-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="6d972-119">Ayrılan kubit her zaman `Zero` durumunda olur.</span><span class="sxs-lookup"><span data-stu-id="6d972-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="6d972-120">`H` işlemini kullanarak, `Qubit` öğemizi süper konuma alabiliriz.</span><span class="sxs-lookup"><span data-stu-id="6d972-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="6d972-121">Kubiti ölçmek ve değerini okumak için `M` iç işlemi kullanılır.</span><span class="sxs-lookup"><span data-stu-id="6d972-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="6d972-122">`Qubit` öğemizi üst konuma alıp ölçtüğümüzde elde ettiğimiz sonuç, kod her çağrıldığında farklı bir değer verecektir.</span><span class="sxs-lookup"><span data-stu-id="6d972-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span> 

<span data-ttu-id="6d972-123">`Qubit` serbest bırakıldığında açıkça `Zero` durumuna geri alınmalıdır, aksi halde simülatörde çalışma zamanı hatası oluşur.</span><span class="sxs-lookup"><span data-stu-id="6d972-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="6d972-124">Bunu yapmanın kolay yollarından biri `Reset` çağırmaktır.</span><span class="sxs-lookup"><span data-stu-id="6d972-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="6d972-125">Bloch küresi ile kodu görselleştirme</span><span class="sxs-lookup"><span data-stu-id="6d972-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="6d972-126">Bloch küresinde kuzey kutbu klasik **0** değerini, güney kutbu ise klasik **1** değerini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="6d972-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="6d972-127">Süper konum, küredeki bir nokta ile gösterilebilir (ok simgesi kullanılır).</span><span class="sxs-lookup"><span data-stu-id="6d972-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="6d972-128">Okun ucu kutba ne kadar yakın olursa kubitin ölçüm sonrasında o kutba atanmış olan klasik değeri alma ihtimali o kadar yüksek olur.</span><span class="sxs-lookup"><span data-stu-id="6d972-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="6d972-129">Örneğin aşağıda kırmızı ok ile gösterilen kubit durumunun ölçüldüğünde **0** değerini verme olasılığı yüksektir.</span><span class="sxs-lookup"><span data-stu-id="6d972-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

<span data-ttu-id="6d972-130">Kodun gerçekleştirdiği işlemleri görselleştirmek için şu gösterimi kullanabiliriz:</span><span class="sxs-lookup"><span data-stu-id="6d972-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="6d972-131">İlk olarak **0** durumunda başlatılan bir kubitle başlıyoruz ve **0** ile **1** olasılıklarının aynı olduğu bir süper konum oluşturmak için buna `H` uyguluyoruz.</span><span class="sxs-lookup"><span data-stu-id="6d972-131">First we start with a qubit initialized in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">


* <span data-ttu-id="6d972-132">Ardından kubiti ölçüp çıktıyı kaydediyoruz:</span><span class="sxs-lookup"><span data-stu-id="6d972-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

<span data-ttu-id="6d972-133">Ölçümün sonucu tamamen rastgele olduğundan rastgele bir bit elde ettik.</span><span class="sxs-lookup"><span data-stu-id="6d972-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="6d972-134">Bu işlemi birkaç kere çağırarak farklı tamsayılar oluşturabiliriz.</span><span class="sxs-lookup"><span data-stu-id="6d972-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="6d972-135">Örneğin üç rastgele bit elde etmek için işlemi üç kez çağırarak rastgele 3 bitlik sayılar (0 ile 7 arasında rastgele bir sayı) oluşturabiliriz.</span><span class="sxs-lookup"><span data-stu-id="6d972-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a><span data-ttu-id="6d972-136">Konak program kullanarak eksiksiz bir rastgele sayı oluşturucu oluşturma</span><span class="sxs-lookup"><span data-stu-id="6d972-136">Creating a complete random number generator using a host program</span></span>

<span data-ttu-id="6d972-137">Artık rastgele bitler oluşturan bir Q# işlemimiz olduğuna göre, bu işlemi kullanarak konak programla eksiksiz bir kuantum rastgele sayı oluşturucu oluşturabiliriz.</span><span class="sxs-lookup"><span data-stu-id="6d972-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator with a host program.</span></span>

 ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="6d972-138">Visual Studio Code veya Komut Satırı ile Python</span><span class="sxs-lookup"><span data-stu-id="6d972-138">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)
 
 <span data-ttu-id="6d972-139">Yeni Q# programınızı Python'dan çalıştırmak için aşağıdaki kodu `host.py` olarak kaydedin:</span><span class="sxs-lookup"><span data-stu-id="6d972-139">To run your new Q# program from Python, save the following code as `host.py`:</span></span>
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 <span data-ttu-id="6d972-140">Ardından Python konak programınızı komut satırından çalıştırabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="6d972-140">You can then run your Python host program from the command line:</span></span>
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="6d972-141">Visual Studio Code veya Komut Satırı ile C#</span><span class="sxs-lookup"><span data-stu-id="6d972-141">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)
 
 <span data-ttu-id="6d972-142">Yeni Q# programınızı C# dilinden çalıştırmak için `Driver.cs` dosyasını aşağıdaki C# kodunu içerecek şekilde değiştirin:</span><span class="sxs-lookup"><span data-stu-id="6d972-142">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 <span data-ttu-id="6d972-143">Ardından C# konak programınızı komut satırından çalıştırabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="6d972-143">You can then run your C# host program from the command line:</span></span>
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="6d972-144">Visual Studio 2019 ile C#</span><span class="sxs-lookup"><span data-stu-id="6d972-144">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

 <span data-ttu-id="6d972-145">Yeni Q# programınızı Visual Studio'da C# dilinde çalıştırmak için `Driver.cs` dosyasını aşağıdaki C# kodunu içerecek şekilde değiştirin:</span><span class="sxs-lookup"><span data-stu-id="6d972-145">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 <span data-ttu-id="6d972-146">Ardından F5 tuşuna bastığınızda program yürütülmeye başlayacak ve rastgele oluşturulan sayılar içeren yeni bir pencere açılacaktır:</span><span class="sxs-lookup"><span data-stu-id="6d972-146">Then press F5, the program will start execution and a new window will pop up with the random number generated:</span></span> 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***
