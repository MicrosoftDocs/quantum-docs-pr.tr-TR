---
title: Kuantum Rastgele Sayı Oluşturucusu Oluşturma
description: Q#Hisse rastgele sayı Oluşturucu oluşturarak üst konum gibi temel hisse kavramları gösteren bir proje oluşturun.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
no-loc:
- Q#
- $$v
ms.openlocfilehash: d80f1c640ac7ddb0104ccbbb6de6d0e26ba05fd6
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863620"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="e3518-103">Öğretici: Q\# dilinde Kuantum Rastgele Sayı Oluşturucusu uygulama</span><span class="sxs-lookup"><span data-stu-id="e3518-103">Tutorial: Implement a Quantum Random Number Generator in Q\#</span></span>

<span data-ttu-id="e3518-104">' De yazılı bir hisse algoritması örneği Q# , hisse rastgele sayı üreticisidir.</span><span class="sxs-lookup"><span data-stu-id="e3518-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="e3518-105">Bu algoritma, kuantum mekaniklerinin özelliklerinden faydalanarak rastgele bir sayı üretir.</span><span class="sxs-lookup"><span data-stu-id="e3518-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e3518-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="e3518-106">Prerequisites</span></span>

- <span data-ttu-id="e3518-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="e3518-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="e3518-108">Bir Q# [ Q# uygulama](xref:microsoft.quantum.install.standalone)için bir [Python ana bilgisayar programıyla](xref:microsoft.quantum.install.python)veya bir [C# ana bilgisayar programıyla](xref:microsoft.quantum.install.cs)bir proje oluşturun.</span><span class="sxs-lookup"><span data-stu-id="e3518-108">Create a Q# project for either a [Q# application](xref:microsoft.quantum.install.standalone), with a [Python host program](xref:microsoft.quantum.install.python), or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="write-a-no-locq-operation"></a><span data-ttu-id="e3518-109">İşlem yazma Q#</span><span class="sxs-lookup"><span data-stu-id="e3518-109">Write a Q# operation</span></span>

### <a name="no-locq-operation-code"></a><span data-ttu-id="e3518-110">Q# işlem kodu</span><span class="sxs-lookup"><span data-stu-id="e3518-110">Q# operation code</span></span>

1. <span data-ttu-id="e3518-111">Program.qs dosyasının içeriğini aşağıdaki kodla değiştirin:</span><span class="sxs-lookup"><span data-stu-id="e3518-111">Replace the contents of the Program.qs file with the following code:</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

<span data-ttu-id="e3518-112">[Kuantum bilişimini anlama](xref:microsoft.quantum.overview.understanding) makalemizde de belirtildiği gibi kubit, süper konumda olabilen bir kuantum bilgi birimidir.</span><span class="sxs-lookup"><span data-stu-id="e3518-112">As mentioned in our [Understanding quantum computing](xref:microsoft.quantum.overview.understanding) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="e3518-113">Bir kubit ölçüldüğünde yalnızca 0 veya 1 olabilir.</span><span class="sxs-lookup"><span data-stu-id="e3518-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="e3518-114">Ancak yürütme sırasında kubitin durumu bir ölçümle 0 veya 1 değerini elde etme olasılığını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="e3518-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="e3518-115">Olasılığa dayalı olan bu durum, süper konum olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="e3518-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="e3518-116">Bu olasılığı kullanarak rastgele sayı oluşturabiliriz.</span><span class="sxs-lookup"><span data-stu-id="e3518-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="e3518-117">Bizim işlem sırasında, Q# `Qubit` yerel veri türüne Q#</span><span class="sxs-lookup"><span data-stu-id="e3518-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="e3518-118">`Qubit` ayırmak için `using` deyimi kullanmamız gerekir.</span><span class="sxs-lookup"><span data-stu-id="e3518-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="e3518-119">Ayrılan kubit her zaman `Zero` durumunda olur.</span><span class="sxs-lookup"><span data-stu-id="e3518-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="e3518-120">`H` işlemini kullanarak, `Qubit` öğemizi süper konuma alabiliriz.</span><span class="sxs-lookup"><span data-stu-id="e3518-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="e3518-121">Kubiti ölçmek ve değerini okumak için `M` iç işlemi kullanılır.</span><span class="sxs-lookup"><span data-stu-id="e3518-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="e3518-122">`Qubit` öğemizi üst konuma alıp ölçtüğümüzde elde ettiğimiz sonuç, kod her çağrıldığında farklı bir değer verecektir.</span><span class="sxs-lookup"><span data-stu-id="e3518-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span>

<span data-ttu-id="e3518-123">`Qubit` serbest bırakıldığında yeniden açıkça `Zero` durumuna ayarlanmalıdır, aksi halde simülatörde çalışma zamanı hatası bildirilir.</span><span class="sxs-lookup"><span data-stu-id="e3518-123">When a `Qubit` is deallocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="e3518-124">Bunu yapmanın kolay yollarından biri `Reset` çağırmaktır.</span><span class="sxs-lookup"><span data-stu-id="e3518-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="e3518-125">Bloch küresi ile kodu görselleştirme</span><span class="sxs-lookup"><span data-stu-id="e3518-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="e3518-126">Bloch küresinde kuzey kutbu klasik **0** değerini, güney kutbu ise klasik **1** değerini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="e3518-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="e3518-127">Süper konum, küredeki bir nokta ile gösterilebilir (ok simgesi kullanılır).</span><span class="sxs-lookup"><span data-stu-id="e3518-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="e3518-128">Okun ucu kutba ne kadar yakın olursa kubitin ölçüm sonrasında o kutba atanmış olan klasik değeri alma ihtimali o kadar yüksek olur.</span><span class="sxs-lookup"><span data-stu-id="e3518-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="e3518-129">Örneğin aşağıda kırmızı ok ile gösterilen kubit durumunun ölçüldüğünde **0** değerini verme olasılığı yüksektir.</span><span class="sxs-lookup"><span data-stu-id="e3518-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

<span data-ttu-id="e3518-130">Kodun gerçekleştirdiği işlemleri görselleştirmek için şu gösterimi kullanabiliriz:</span><span class="sxs-lookup"><span data-stu-id="e3518-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="e3518-131">İlk olarak **0** durumunda başlatılan bir kubitle başlıyoruz ve **0** ile **1** olasılıklarının aynı olduğu bir süper konum oluşturmak için buna `H` uyguluyoruz.</span><span class="sxs-lookup"><span data-stu-id="e3518-131">First we start with a qubit initialized in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* <span data-ttu-id="e3518-132">Ardından kubiti ölçüp çıktıyı kaydediyoruz:</span><span class="sxs-lookup"><span data-stu-id="e3518-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

<span data-ttu-id="e3518-133">Ölçümün sonucu tamamen rastgele olduğundan rastgele bir bit elde ettik.</span><span class="sxs-lookup"><span data-stu-id="e3518-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="e3518-134">Bu işlemi birkaç kere çağırarak farklı tamsayılar oluşturabiliriz.</span><span class="sxs-lookup"><span data-stu-id="e3518-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="e3518-135">Örneğin üç rastgele bit elde etmek için işlemi üç kez çağırarak rastgele 3 bitlik sayılar (0 ile 7 arasında rastgele bir sayı) oluşturabiliriz.</span><span class="sxs-lookup"><span data-stu-id="e3518-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>


## <a name="creating-a-complete-random-number-generator"></a><span data-ttu-id="e3518-136">Eksiksiz bir rastgele sayı oluşturucu oluşturma</span><span class="sxs-lookup"><span data-stu-id="e3518-136">Creating a complete random number generator</span></span>

<span data-ttu-id="e3518-137">Artık Q# rastgele bitler üreten bir işlem olduğuna göre, bunu bir tamamen hisse rastgele sayı Oluşturucu oluşturmak için kullanabiliriz.</span><span class="sxs-lookup"><span data-stu-id="e3518-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator.</span></span> <span data-ttu-id="e3518-138">Bir Q# uygulamayı kullanabilir veya bir konak programı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e3518-138">We can use a Q# application or use a host program.</span></span>



### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a>[<span data-ttu-id="e3518-139">Q# Visual Studio veya Visual Studio Code ile uygulamalar</span><span class="sxs-lookup"><span data-stu-id="e3518-139">Q# applications with Visual Studio or Visual Studio Code</span></span>](#tab/tabid-qsharp)

<span data-ttu-id="e3518-140">Tam uygulamayı oluşturmak için Q# , aşağıdaki giriş noktasını Q# programınıza ekleyin:</span><span class="sxs-lookup"><span data-stu-id="e3518-140">To create the full Q# application, add the following entry point to your Q# program:</span></span> 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

<span data-ttu-id="e3518-141">Yürütülebilir dosya, proje yapılandırmasına ve komut satırı seçeneklerine bağlı olarak simülatör veya kaynak tahmini aracında `@EntryPoint()` özniteliğiyle işaretlenmiş işlemi ya da işlevi çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="e3518-141">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

<span data-ttu-id="e3518-142">Visual Studio’da betiği yürütmek için Ctrl + F5 tuşlarına basmanız yeterlidir.</span><span class="sxs-lookup"><span data-stu-id="e3518-142">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="e3518-143">VS Code’da terminale aşağıdakileri yazarak Program.qs dosyasını ilk kez derleyin:</span><span class="sxs-lookup"><span data-stu-id="e3518-143">In VS Code, build the Program.qs the first time by typing the below in the terminal:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="e3518-144">Sonraki çalıştırmalar için tekrar derlenmesi gerekmez.</span><span class="sxs-lookup"><span data-stu-id="e3518-144">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="e3518-145">Çalıştırmak için aşağıdaki komutu girin ve Enter tuşuna basın:</span><span class="sxs-lookup"><span data-stu-id="e3518-145">To run it, type the following command and press enter:</span></span>

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-prompt"></a>[<span data-ttu-id="e3518-146">Visual Studio Code veya komut istemiyle Python</span><span class="sxs-lookup"><span data-stu-id="e3518-146">Python with Visual Studio Code or the command prompt</span></span>](#tab/tabid-python)

<span data-ttu-id="e3518-147">Yeni Q# programınızı Python 'da çalıştırmak için aşağıdaki kodu şu şekilde kaydedin `host.py` :</span><span class="sxs-lookup"><span data-stu-id="e3518-147">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

<span data-ttu-id="e3518-148">Ardından, komut isteminden Python ana bilgisayar programınızı çalıştırabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="e3518-148">You can then run your Python host program from the command prompt:</span></span>

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[<span data-ttu-id="e3518-149">Visual Studio Code veya Visual Studio ile C#</span><span class="sxs-lookup"><span data-stu-id="e3518-149">C# with Visual Studio Code or Visual Studio</span></span>](#tab/tabid-csharp)

<span data-ttu-id="e3518-150">Q#C# ' deki yeni programınızı çalıştırmak için `Driver.cs` Aşağıdaki c# kodunu içerecek şekilde değiştirin:</span><span class="sxs-lookup"><span data-stu-id="e3518-150">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

<span data-ttu-id="e3518-151">Ardından, komut isteminden C# ana bilgisayar programınızı çalıştırabilirsiniz (Visual Studio 'da F5 'e basmalısınız):</span><span class="sxs-lookup"><span data-stu-id="e3518-151">You can then run your C# host program from the command prompt (in Visual Studio you should press F5):</span></span>

```bash
$ dotnet run
The random number generated is 42
```

***
