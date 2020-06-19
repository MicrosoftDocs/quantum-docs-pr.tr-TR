---
title: Q# ile dolanıklığı keşfetme
description: Q# dilinde kuantum programı yazmayı öğrenin. Quantum Development Kit'i (QDK) kullanarak Bell Durumu uygulaması geliştirme
author: natke
ms.author: nakersha
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 271eb7f496835f152573be930d0fe24e59f2d15d
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630086"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="fd562-104">Öğretici: Q\# ile dolaşıklığı keşfetme</span><span class="sxs-lookup"><span data-stu-id="fd562-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="fd562-105">Bu öğreticide, kubitleri düzenleyip ölçen ve süper konum ile dolaşıklığın etkilerini gösteren bir Q# programının nasıl yazılacağı gösterilir.</span><span class="sxs-lookup"><span data-stu-id="fd562-105">In this tutorial, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>
<span data-ttu-id="fd562-106">Bu rehber QDK'yı yükleme, programı oluşturma ve bir kuantum simülatörü üzerinde yürütme konusunda size yol gösterecektir.</span><span class="sxs-lookup"><span data-stu-id="fd562-106">This guides you on installing the QDK, building the program and executing that program on a quantum simulator.</span></span>  

<span data-ttu-id="fd562-107">Kuantum dolaşıklığı göstermek için Bell adında bir uygulama yazacaksınız.</span><span class="sxs-lookup"><span data-stu-id="fd562-107">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="fd562-108">Bell adı, en basit süper konum ve kuantum dolaşıklığı örneklerini göstermek için kullanılan iki kubitin belirli kuantum durumları olan Bell durumlarını ifade eder.</span><span class="sxs-lookup"><span data-stu-id="fd562-108">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fd562-109">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="fd562-109">Prerequisites</span></span>

<span data-ttu-id="fd562-110">Kodlamaya başlamaya hazırsanız devam etmeden önce şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="fd562-110">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="fd562-111">[Python](xref:microsoft.quantum.install.python) veya [.NET](xref:microsoft.quantum.install.cs) için Quantum geliştirme setini yükleyin.</span><span class="sxs-lookup"><span data-stu-id="fd562-111">Install the Quantum Development Kit for [Python](xref:microsoft.quantum.install.python) or [.NET](xref:microsoft.quantum.install.cs).</span></span>
* <span data-ttu-id="fd562-112">Makinenizde QDK zaten yüklüyse en son sürüme [güncelleştirdiğinizden](xref:microsoft.quantum.update) emin olun</span><span class="sxs-lookup"><span data-stu-id="fd562-112">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="fd562-113">Dilerseniz QDK'yı yüklemeden anlatımı takip ederek Q# programlama diline genel bir bakış elde edebilir ve kuantum bilişiminin ilk kavramlarını öğrenebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fd562-113">You can also follow along with the narrative without installing the QDK, reviewing the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="demonstrating-qubit-behavior-with-q"></a><span data-ttu-id="fd562-114">Q# ile kubit davranışını gösterme</span><span class="sxs-lookup"><span data-stu-id="fd562-114">Demonstrating qubit behavior with Q#</span></span>

<span data-ttu-id="fd562-115">Basit [kubit tanımımızı](xref:microsoft.quantum.overview.understanding) hatırlayalım.</span><span class="sxs-lookup"><span data-stu-id="fd562-115">Recall our simple [definition of a qubit](xref:microsoft.quantum.overview.understanding).</span></span>  <span data-ttu-id="fd562-116">Klasik bitler 0 veya 1 gibi tek bir ikili değeri barındırırken, [kubitin](xref:microsoft.quantum.glossary#qubit) durumu 0 ve 1’in bir **süper konumunda** olabilir.</span><span class="sxs-lookup"><span data-stu-id="fd562-116">Where classical bits hold a single binary value such as a 0 or 1, the state of a [qubit](xref:microsoft.quantum.glossary#qubit) can be in a **superposition** of 0 and 1.</span></span>  <span data-ttu-id="fd562-117">Kavramsal olarak bir kubit, boşluktaki bir yön (vektör olarak da bilinir) olarak düşünülebilir.</span><span class="sxs-lookup"><span data-stu-id="fd562-117">Conceptually, a qubit can be thought of as a direction in space (also known as a vector).</span></span>  <span data-ttu-id="fd562-118">Bir kubit herhangi bir yönde olabilir.</span><span class="sxs-lookup"><span data-stu-id="fd562-118">A qubit can be in any of the possible directions.</span></span> <span data-ttu-id="fd562-119">İki **klasik durum**, iki yöndür. Bu da %100 oranında 0 ölçme şansını ve %100 oranında 1 ölçme şansını gösterir.</span><span class="sxs-lookup"><span data-stu-id="fd562-119">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>  <span data-ttu-id="fd562-120">Bu gösterim ayrıca [Bloch küresi](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) ile daha anlaşılır bir şekilde gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="fd562-120">This representation is also more formally visualized by the [bloch sphere](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>

<span data-ttu-id="fd562-121">Ölçüm işlemi ikili sonuç üretir ve bir kubit durumunu değiştirir.</span><span class="sxs-lookup"><span data-stu-id="fd562-121">The act of measurement produces a binary result and changes a qubit state.</span></span> <span data-ttu-id="fd562-122">Ölçüm, 0 veya 1 ikili değerini verir.</span><span class="sxs-lookup"><span data-stu-id="fd562-122">Measurement produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="fd562-123">Kubit, süper konumdan (herhangi bir yöne) klasik durumlardan birine geçer.</span><span class="sxs-lookup"><span data-stu-id="fd562-123">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="fd562-124">Bundan sonra aynı ölçümün başka bir işlemle müdahale edilmeden yinelenmesi durumunda aynı ikili sonuç ortaya çıkar.</span><span class="sxs-lookup"><span data-stu-id="fd562-124">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="fd562-125">Birden çok kubit [**dolaşık hale getirilebilir**](xref:microsoft.quantum.glossary#entanglement).</span><span class="sxs-lookup"><span data-stu-id="fd562-125">Multiple qubits can be [**entangled**](xref:microsoft.quantum.glossary#entanglement).</span></span> <span data-ttu-id="fd562-126">Dolaşık bir kubitin ölçümünü yaptığınızda, diğerinin durumuna ilişkin bilginiz de güncelleştirilir.</span><span class="sxs-lookup"><span data-stu-id="fd562-126">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="fd562-127">Şimdi bu davranışın Q# ile nasıl ifade edildiğine bakalım.</span><span class="sxs-lookup"><span data-stu-id="fd562-127">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="fd562-128">Mümkün olan en basit programla başlayıp kuantum süper konumu ile kuantum dolaşıklığını göstermek için bunu geliştirirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fd562-128">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="setup"></a><span data-ttu-id="fd562-129">Kurulum</span><span class="sxs-lookup"><span data-stu-id="fd562-129">Setup</span></span>

<span data-ttu-id="fd562-130">Bu öğretici, bir konak program kullanır ve iki bölümden oluşur:</span><span class="sxs-lookup"><span data-stu-id="fd562-130">This tutorial uses a host programs and consists of two parts:</span></span>

1. <span data-ttu-id="fd562-131">Q# kuantum programlama dili kullanılarak uygulanan bir dizi kuantum algoritması.</span><span class="sxs-lookup"><span data-stu-id="fd562-131">A series of quantum algorithms, implemented using the Q# quantum programming language.</span></span>
1. <span data-ttu-id="fd562-132">Python veya C# gibi bir dilde uygulanan, ana giriş noktası işlevi gören ve kuantum algoritmalarını yürütmek üzere Q# işlemlerini çağıran bir konak program.</span><span class="sxs-lookup"><span data-stu-id="fd562-132">A host program, implemented in either Python or C#, that serves as the main entry point and invokes Q# operations to execute the quantum algorithms.</span></span>

#### <a name="python"></a>[<span data-ttu-id="fd562-133">Python</span><span class="sxs-lookup"><span data-stu-id="fd562-133">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="fd562-134">Uygulamanız için bir konum seçin</span><span class="sxs-lookup"><span data-stu-id="fd562-134">Choose a location for your application</span></span>

1. <span data-ttu-id="fd562-135">`Bell.qs` adlı bir dosya oluşturun.</span><span class="sxs-lookup"><span data-stu-id="fd562-135">Create a file called `Bell.qs`.</span></span> <span data-ttu-id="fd562-136">Bu dosya Q# kodunuzu içerecektir.</span><span class="sxs-lookup"><span data-stu-id="fd562-136">This file will contain your Q# code.</span></span>

1. <span data-ttu-id="fd562-137">`host.py` adlı bir dosya oluşturun.</span><span class="sxs-lookup"><span data-stu-id="fd562-137">Create a file called `host.py`.</span></span> <span data-ttu-id="fd562-138">Bu dosya Python konak kodunuzu içerecektir.</span><span class="sxs-lookup"><span data-stu-id="fd562-138">This file will contain your Python host code.</span></span>

#### <a name="c-command-line"></a>[<span data-ttu-id="fd562-139">C# Komut Satırı</span><span class="sxs-lookup"><span data-stu-id="fd562-139">C# Command Line</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="fd562-140">Yeni Q# projesi oluşturma:</span><span class="sxs-lookup"><span data-stu-id="fd562-140">Create a new Q# project:</span></span>

    ```
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    <span data-ttu-id="fd562-141">`.csproj` dosyasını, `Operations.qs` adlı Q# dosyasını ve `Driver.cs` adlı konak programını görüyor olmalısınız</span><span class="sxs-lookup"><span data-stu-id="fd562-141">You should see a `.csproj` file, a Q# file called `Operations.qs`, and a host program file called `Driver.cs`</span></span>

1. <span data-ttu-id="fd562-142">Q# dosyasını yeniden adlandırın</span><span class="sxs-lookup"><span data-stu-id="fd562-142">Rename the Q# file</span></span>

    ```
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[<span data-ttu-id="fd562-143">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fd562-143">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="fd562-144">Yeni bir proje oluşturma</span><span class="sxs-lookup"><span data-stu-id="fd562-144">Create a new project</span></span>

   * <span data-ttu-id="fd562-145">Visual Studio’yu açın</span><span class="sxs-lookup"><span data-stu-id="fd562-145">Open Visual Studio</span></span>
   * <span data-ttu-id="fd562-146">**Dosya** menüsüne gidin ve **Yeni** -> **Proje...** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="fd562-146">Go to the **File** menu and select **New** -> **Project...**</span></span>
   * <span data-ttu-id="fd562-147">Proje şablonu gezginindeki arama alanına `Q#` yazın ve `Q# Application` şablonunu seçin</span><span class="sxs-lookup"><span data-stu-id="fd562-147">In the project template explorer, type `Q#` into the search field and select the `Q# Application` template</span></span>
   * <span data-ttu-id="fd562-148">Projenize `Bell` adını verin</span><span class="sxs-lookup"><span data-stu-id="fd562-148">Give your project the name `Bell`</span></span>

1. <span data-ttu-id="fd562-149">Q# dosyasını yeniden adlandırın</span><span class="sxs-lookup"><span data-stu-id="fd562-149">Rename the Q# file</span></span>

   * <span data-ttu-id="fd562-150">**Çözüm Gezgini**'ne gidin</span><span class="sxs-lookup"><span data-stu-id="fd562-150">Navigate to the **Solution Explorer**</span></span>
   * <span data-ttu-id="fd562-151">`Operations.qs` dosyasına sağ tıklayın</span><span class="sxs-lookup"><span data-stu-id="fd562-151">Right click on the `Operations.qs` file</span></span>
   * <span data-ttu-id="fd562-152">Dosyayı `Bell.qs` olarak yeniden adlandırın</span><span class="sxs-lookup"><span data-stu-id="fd562-152">Rename it to `Bell.qs`</span></span>

* * *

## <a name="write-a-q-operation"></a><span data-ttu-id="fd562-153">Q# işlemi yazma</span><span class="sxs-lookup"><span data-stu-id="fd562-153">Write a Q# operation</span></span>

<span data-ttu-id="fd562-154">Burada hedefimiz, belirli bir kuantum durumunda iki kubit hazırlayarak Q# ile kubitlerin durumunu değiştirme işlemlerinin yanı sıra süper konum ve dolaşıklık etkilerini göstermektir.</span><span class="sxs-lookup"><span data-stu-id="fd562-154">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="fd562-155">Kubit durumlarını, işlemleri ve ölçümü göstermek için bunu parça parça oluşturacağız.</span><span class="sxs-lookup"><span data-stu-id="fd562-155">We will build this up piece by piece to demonstrate qubit states, operations, and measurement.</span></span>

<span data-ttu-id="fd562-156">**Genel bakış:**  Aşağıdaki ilk kodda Q# içinde kubitlerle nasıl çalışacağınız gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="fd562-156">**Overview:**  In the first code below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="fd562-157">Bir kubitin durumunu değiştiren iki işlem olan `M` ve `X` işlemlerini tanıtacağız.</span><span class="sxs-lookup"><span data-stu-id="fd562-157">We’ll introduce two operations, `M` and `X` that transform the state of a qubit.</span></span> 

<span data-ttu-id="fd562-158">Bu kod parçacığında parametre olarak bir kubit ile kubitin içinde bulunmasını istediğimiz durumu temsil eden `desired` parametresini alan `Set` işlemi tanımlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="fd562-158">In this code snippet, an operation `Set` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="fd562-159">`Set` işlemi, `M` işlemini kullanarak kubit üzerinde bir ölçüm gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="fd562-159">The operation `Set` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="fd562-160">Q# dilinde bir kubit ölçümü her zaman `Zero` veya `One` döndürür.</span><span class="sxs-lookup"><span data-stu-id="fd562-160">In Q#, a qubit measurement always returns either  `Zero` or `One`.</span></span>  <span data-ttu-id="fd562-161">Ölçümün istenen değere eşit olmayan bir değer döndürmesi halinde Set işlemi kubiti "çevirir". Bu durumda bir `X` işlemi yürüterek kubit durumunu ölçümün `Zero` ve `One` döndürme olasılıklarının tersine çevrilmiş olduğu yeni bir durum olarak değiştirir.</span><span class="sxs-lookup"><span data-stu-id="fd562-161">If the measurement returns a value not equal to a desired value, Set “flips” the qubit; that is, it executes an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span>  <span data-ttu-id="fd562-162">Sonrasında `Set` işleminin etkisini göstermek için bir `TestBellState` işlemi eklenir.</span><span class="sxs-lookup"><span data-stu-id="fd562-162">To demonstrate the effect of the `Set` operation, a `TestBellState` operation is then added.</span></span>  <span data-ttu-id="fd562-163">Bu işlem giriş olarak `Zero` veya `One` alır. Ardından `Set` işlemini bu girişle birkaç kez çağırıp kubitin ölçümünden döndürülen `Zero` sayısı ile döndürülen `One` sayısını hesaplar.</span><span class="sxs-lookup"><span data-stu-id="fd562-163">This operation takes as input a `Zero` or `One`, and calls the `Set` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="fd562-164">Elbette bu ilk `TestBellState` işlemi simülasyonunda çıkışın parametre girişi `Zero` döndüreceğinden, tüm kubit ölçümlerinin `Zero` ile ayarlanmış olduğunu ve parametre girişi `One` döndüreceğinden tüm kubit ölçümlerinin `One` ile ayarlanmış olduğunu göstermesi beklenir.</span><span class="sxs-lookup"><span data-stu-id="fd562-164">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span>  <span data-ttu-id="fd562-165">Sonrasında süper konumu ve dolaşıklığı göstermek için `TestBellState` içine kod ekleyeceğiz.</span><span class="sxs-lookup"><span data-stu-id="fd562-165">Further on, we’ll add code to `TestBellState` to demonstrating superposition and entanglement.</span></span>


### <a name="q-operation-code"></a><span data-ttu-id="fd562-166">Q# işlem kodu</span><span class="sxs-lookup"><span data-stu-id="fd562-166">Q# operation code</span></span>

1. <span data-ttu-id="fd562-167">Bell.qs dosyasının içeriğini aşağıdaki kodla değiştirin:</span><span class="sxs-lookup"><span data-stu-id="fd562-167">Replace the contents of the Bell.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    <span data-ttu-id="fd562-168">Bu işlem artık kubiti klasik bir duruma getirerek %100 `Zero` veya %100 `One` döndürmesi sağlanabilir.</span><span class="sxs-lookup"><span data-stu-id="fd562-168">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>  <span data-ttu-id="fd562-169">`Zero` ve `One`, bir kubit ölçümünün mümkün olan iki sonucunu gösteren sabitlerdir.</span><span class="sxs-lookup"><span data-stu-id="fd562-169">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

    <span data-ttu-id="fd562-170">`Set` işlemi kubiti ölçer.</span><span class="sxs-lookup"><span data-stu-id="fd562-170">The operation `Set` measures the qubit.</span></span>
    <span data-ttu-id="fd562-171">Kubit istediğimiz durumdaysa `Set` başka bir işlem gerçekleştirmez, değilse `X` işlemini çalıştırarak kubitin durumunu istediğimiz duruma getirebiliriz.</span><span class="sxs-lookup"><span data-stu-id="fd562-171">If the qubit is in the state we want, `Set` leaves it alone; otherwise, by executing the `X` operation, we change the qubit state to the desired state.</span></span>

### <a name="about-q-operations"></a><span data-ttu-id="fd562-172">Q# işlemleri hakkında</span><span class="sxs-lookup"><span data-stu-id="fd562-172">About Q# operations</span></span>

<span data-ttu-id="fd562-173">Q# işlemi bir kuantum alt yordamıdır.</span><span class="sxs-lookup"><span data-stu-id="fd562-173">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="fd562-174">Başka bir deyişle kuantum işlemlerini içeren çağrılabilir bir yordamdır.</span><span class="sxs-lookup"><span data-stu-id="fd562-174">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="fd562-175">İşlemin bağımsız değişkenleri parantez içinde tanımlama grubu olarak belirtilir.</span><span class="sxs-lookup"><span data-stu-id="fd562-175">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="fd562-176">Bir iki nokta işareti eklendikten sonra işlemin dönüş türü belirtilir.</span><span class="sxs-lookup"><span data-stu-id="fd562-176">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="fd562-177">Bu örnekte `Set` işleminin dönüşü yoktur, dolayısıyla `Unit` döndürüyor olarak işaret edilir.</span><span class="sxs-lookup"><span data-stu-id="fd562-177">In this case, the `Set` operation has no return, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="fd562-178">Bu F# dilindeki `unit` öğesinin Q# eşdeğeridir, kabaca C# dilindeki `void` ve Python'daki boş bir tanımlama grubuyla (`Tuple[()]`) karşılaştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="fd562-178">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple (`Tuple[()]`) in Python.</span></span>

<span data-ttu-id="fd562-179">İlk Q# işleminizde iki kuantum işlemi kullandınız:</span><span class="sxs-lookup"><span data-stu-id="fd562-179">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="fd562-180">Kubitin durumunu ölçen [M](xref:microsoft.quantum.intrinsic.m) işlemi</span><span class="sxs-lookup"><span data-stu-id="fd562-180">The [M](xref:microsoft.quantum.intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="fd562-181">Kubitin durumunu çeviren [X](xref:microsoft.quantum.intrinsic.x) işlemi</span><span class="sxs-lookup"><span data-stu-id="fd562-181">The [X](xref:microsoft.quantum.intrinsic.x) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="fd562-182">Kuantum işlemi, kubitin durumunu dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="fd562-182">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="fd562-183">Bazen kuantum işlemleri, klasik mantıksal geçitlere benzetildiğinden geçit olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="fd562-183">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="fd562-184">Bu kullanım kuantum bilgisayarların ilk dönemlerine dayanır. Bu dönemde algoritmaların yalnızca teorik yapılardı ve klasik bilgi işlem devre şemalarına benzer şekilde görselleştirilirdi.</span><span class="sxs-lookup"><span data-stu-id="fd562-184">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="add-q-test-code"></a><span data-ttu-id="fd562-185">Q# test kodu ekleme</span><span class="sxs-lookup"><span data-stu-id="fd562-185">Add Q# test code</span></span>

1. <span data-ttu-id="fd562-186">Aşağıdaki işlemi `Bell.qs` dosyasında ad alanının içine, `Set` işleminin sonuna ekleyin:</span><span class="sxs-lookup"><span data-stu-id="fd562-186">Add the following operation to the `Bell.qs` file, inside the namespace, after the end of the `Set` operation:</span></span>

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    <span data-ttu-id="fd562-187">Bu işlem (`TestBellState`) `count` yinelemeleri için döngü yapar, bir kubitte belirtilen `initial` değerini ayarlar ve ardından sonucu ölçer (`M`).</span><span class="sxs-lookup"><span data-stu-id="fd562-187">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="fd562-188">Kaç sıfır ve bir ölçtüğümüzle ilgili istatistikleri toplar ve bunları çağrıyı yapana döndürür.</span><span class="sxs-lookup"><span data-stu-id="fd562-188">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="fd562-189">Bir gerekli işlem daha gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="fd562-189">It performs one other necessary operation.</span></span> <span data-ttu-id="fd562-190">Kubiti döndürmeden önce bilinen bir duruma (`Zero`) sıfırlayarak diğerlerinin bu kubiti bilinen durumda ayırmasına olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="fd562-190">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="fd562-191">Bu, `using` deyimi için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="fd562-191">This is required by the `using` statement.</span></span>

### <a name="about-variables-in-q"></a><span data-ttu-id="fd562-192">Q# dilindeki değişkenler hakkında</span><span class="sxs-lookup"><span data-stu-id="fd562-192">About variables in Q#</span></span>

<span data-ttu-id="fd562-193">Varsayılan olarak Q# dilinde değişkenler sabittir; bunların değeri bağlandıktan sonra değiştirilemez.</span><span class="sxs-lookup"><span data-stu-id="fd562-193">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="fd562-194">Sabit bir değişkenin bağlamasını göstermek için `let` anahtar sözcüğü kullanılır.</span><span class="sxs-lookup"><span data-stu-id="fd562-194">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="fd562-195">İşlem bağımsız değişkenleri her zaman sabittir.</span><span class="sxs-lookup"><span data-stu-id="fd562-195">Operation arguments are always immutable.</span></span>

<span data-ttu-id="fd562-196">Değeri değişebilen `numOnes` gibi bir değişkene ihtiyacınız varsa değişkeni `mutable` anahtar sözcüğüyle bildirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fd562-196">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="fd562-197">Değişebilir değişkenin değeri `set` deyimi kullanılarak değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="fd562-197">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="fd562-198">Her iki durumda da, değişkenin türü derleyici tarafından çıkarsanır.</span><span class="sxs-lookup"><span data-stu-id="fd562-198">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="fd562-199">Q# dilinde değişkenler için herhangi bir türde ek açıklama gerekmez.</span><span class="sxs-lookup"><span data-stu-id="fd562-199">Q# doesn't require any type annotations for variables.</span></span>

### <a name="about-using-statements-in-q"></a><span data-ttu-id="fd562-200">Q# dilindeki `using` deyimleri hakkında</span><span class="sxs-lookup"><span data-stu-id="fd562-200">About `using` statements in Q#</span></span>

<span data-ttu-id="fd562-201">Q# dilinde `using` deyimi de özeldir.</span><span class="sxs-lookup"><span data-stu-id="fd562-201">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="fd562-202">Kubitleri bir kod bloğunda kullanım amacıyla ayırmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="fd562-202">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="fd562-203">Q# dilinde tüm kubitler dinamik olarak ayrılır ve serbest bırakılır; karmaşık bir algoritmanın tüm yaşam süresi boyunca orada olan sabit kaynaklar değillerdir.</span><span class="sxs-lookup"><span data-stu-id="fd562-203">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="fd562-204">Başlangıçta `using` deyimi bir kubit kümesi ayırır ve bloğun sonunda bu kubitleri serbest bırakır.</span><span class="sxs-lookup"><span data-stu-id="fd562-204">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="create-the-host-application-code"></a><span data-ttu-id="fd562-205">Konak uygulama kodunu oluşturma</span><span class="sxs-lookup"><span data-stu-id="fd562-205">Create the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="fd562-206">Python</span><span class="sxs-lookup"><span data-stu-id="fd562-206">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="fd562-207">`host.py` dosyasını açın ve aşağıdaki kodu ekleyin:</span><span class="sxs-lookup"><span data-stu-id="fd562-207">Open the `host.py` file and add the following code:</span></span>

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[<span data-ttu-id="fd562-208">C#</span><span class="sxs-lookup"><span data-stu-id="fd562-208">C#</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="fd562-209">`Driver.cs` dosyasının içeriğini aşağıdaki kodla değiştirin:</span><span class="sxs-lookup"><span data-stu-id="fd562-209">Replace the contents of the `Driver.cs` file with the following code:</span></span>

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a><span data-ttu-id="fd562-210">Konak uygulama kodu hakkında</span><span class="sxs-lookup"><span data-stu-id="fd562-210">About the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="fd562-211">Python</span><span class="sxs-lookup"><span data-stu-id="fd562-211">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="fd562-212">Python konak uygulamasının üç bölümü vardır:</span><span class="sxs-lookup"><span data-stu-id="fd562-212">The Python host application has three parts:</span></span>

* <span data-ttu-id="fd562-213">Kuantum algoritması için gereken tüm bağımsız değişkenleri hesaplama.</span><span class="sxs-lookup"><span data-stu-id="fd562-213">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="fd562-214">Örnekte `count` 1000 değerine sabitlenmiştir ve `initial` kubitin ilk değeridir.</span><span class="sxs-lookup"><span data-stu-id="fd562-214">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="fd562-215">İçeri aktarılan Q# işleminin `simulate()` yöntemini çağırarak kuantum algoritmasını çalıştırma.</span><span class="sxs-lookup"><span data-stu-id="fd562-215">Run the quantum algorithm by calling the `simulate()` method of the imported Q# operation.</span></span>
* <span data-ttu-id="fd562-216">İşlemin sonucunu işleme.</span><span class="sxs-lookup"><span data-stu-id="fd562-216">Process the result of the operation.</span></span> <span data-ttu-id="fd562-217">Örnekte işlemin sonucunu `res` alır.</span><span class="sxs-lookup"><span data-stu-id="fd562-217">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="fd562-218">Burada sonuç, simülatör tarafından hesaplanan sıfırların sayısından (`num_zeros`) ve birlerin sayısından (`num_ones`) oluşmuş bir tanımlama grubudur.</span><span class="sxs-lookup"><span data-stu-id="fd562-218">Here the result is a tuple of the number of zeros (`num_zeros`) and number of ones (`num_ones`) measured by the simulator.</span></span> <span data-ttu-id="fd562-219">Tanımlama grubunu ayrıştırıp iki alan elde eder ve sonuçları yazdırırız.</span><span class="sxs-lookup"><span data-stu-id="fd562-219">We deconstruct the tuple to get the two fields, and print the results.</span></span>

#### <a name="c"></a>[<span data-ttu-id="fd562-220">C#</span><span class="sxs-lookup"><span data-stu-id="fd562-220">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="fd562-221">C# konak uygulamasının dört bölümü vardır:</span><span class="sxs-lookup"><span data-stu-id="fd562-221">The C# host application has four parts:</span></span>

* <span data-ttu-id="fd562-222">Kuantum simülatörünü oluşturma.</span><span class="sxs-lookup"><span data-stu-id="fd562-222">Construct a quantum simulator.</span></span> <span data-ttu-id="fd562-223">Örnekte simülatör olarak `qsim` kullanılmıştır.</span><span class="sxs-lookup"><span data-stu-id="fd562-223">In the example, `qsim` is the simulator.</span></span>
* <span data-ttu-id="fd562-224">Kuantum algoritması için gereken tüm bağımsız değişkenleri hesaplama.</span><span class="sxs-lookup"><span data-stu-id="fd562-224">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="fd562-225">Örnekte `count` 1000 değerine sabitlenmiştir ve `initial` kubitin ilk değeridir.</span><span class="sxs-lookup"><span data-stu-id="fd562-225">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="fd562-226">Kuantum algoritmasını çalıştırma.</span><span class="sxs-lookup"><span data-stu-id="fd562-226">Run the quantum algorithm.</span></span> <span data-ttu-id="fd562-227">Her Q# işlemi aynı adda bir C# sınıfı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="fd562-227">Each Q# operation generates a C# class with the same name.</span></span> <span data-ttu-id="fd562-228">Bu sınıfın, işlemi **zaman uyumsuz** olarak yürüten bir `Run` yöntemi vardır.</span><span class="sxs-lookup"><span data-stu-id="fd562-228">This class has a `Run` method that **asynchronously** executes the operation.</span></span> <span data-ttu-id="fd562-229">Yürütmenin zaman uyumsuz olmasının nedeni gerçek donanım üzerindeki yürütmenin zaman uyumsuz yapılacağıdır.</span><span class="sxs-lookup"><span data-stu-id="fd562-229">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> <span data-ttu-id="fd562-230">`Run` yöntemi zaman uyumsuz olduğundan `Result` özelliğini getiririz; bu özellik, görev tamamlanana ve zaman uyumlu olarak sonucu döndürene kadar yürütmeyi engeller.</span><span class="sxs-lookup"><span data-stu-id="fd562-230">Because the `Run` method is asynchronous, we fetch the `Result` property; this blocks execution until the task completes and returns the result synchronously.</span></span>
* <span data-ttu-id="fd562-231">İşlemin sonucunu işleme.</span><span class="sxs-lookup"><span data-stu-id="fd562-231">Process the result of the operation.</span></span> <span data-ttu-id="fd562-232">Örnekte işlemin sonucunu `res` alır.</span><span class="sxs-lookup"><span data-stu-id="fd562-232">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="fd562-233">Burada sonuç, simülatör tarafından hesaplanan sıfırların sayısından (`numZeros`) ve birlerin sayısından (`numOnes`) oluşmuş bir tanımlama grubudur.</span><span class="sxs-lookup"><span data-stu-id="fd562-233">Here the result is a tuple of the number of zeros (`numZeros`) and number of ones (`numOnes`) measured by the simulator.</span></span> <span data-ttu-id="fd562-234">Bu sonuç C# dilinde ValueTuple olarak döndürülür.</span><span class="sxs-lookup"><span data-stu-id="fd562-234">This is returned as a ValueTuple in C#.</span></span> <span data-ttu-id="fd562-235">Tanımlama grubunu ayrıştırıp iki alan elde eder, sonuçları yazdırır ve tuşa basılmasını bekleriz.</span><span class="sxs-lookup"><span data-stu-id="fd562-235">We deconstruct the tuple to get the two fields, print the results, and wait for a keypress.</span></span>

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a><span data-ttu-id="fd562-236">Derleme ve çalıştırma</span><span class="sxs-lookup"><span data-stu-id="fd562-236">Build and run</span></span>

#### <a name="python"></a>[<span data-ttu-id="fd562-237">Python</span><span class="sxs-lookup"><span data-stu-id="fd562-237">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="fd562-238">Terminalinizde aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="fd562-238">Run the following command at your terminal:</span></span>

    ```
    python host.py
    ```

    <span data-ttu-id="fd562-239">Bu komut Q# işleminin benzetimini yapan konak uygulamayı çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="fd562-239">This command runs the host application, which simulates the Q# operation.</span></span>

<span data-ttu-id="fd562-240">Sonuçlar şöyle olmalıdır:</span><span class="sxs-lookup"><span data-stu-id="fd562-240">The results should be:</span></span>

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="fd562-241">Komut Satırı / Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="fd562-241">Command Line / Visual Studio Code</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="fd562-242">Terminalinizde aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="fd562-242">Run the following at your terminal:</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="fd562-243">Bu komut otomatik olarak tüm gerekli paketleri indirir, uygulamayı derler ve sonra da bunu komut satırında çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="fd562-243">This command will automatically download all required packages, build the application, then run it at the command line.</span></span>

1. <span data-ttu-id="fd562-244">Alternatif olarak **F1** tuşuna basarak Komut Paletini açın ve **Hata Ayıkla: Hata Ayıklama Olmadan Başlat**'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="fd562-244">Alternatively, press **F1** to open the Command Palette and select **Debug: Start Without Debugging.**</span></span>
<span data-ttu-id="fd562-245">Programın nasıl başlatılacağını açıklayan yeni bir ``launch.json`` dosyası oluşturmanız istenebilir.</span><span class="sxs-lookup"><span data-stu-id="fd562-245">You may be prompted to create a new ``launch.json`` file describing how to start the program.</span></span>
<span data-ttu-id="fd562-246">Çoğu uygulama için varsayılan ``launch.json`` dosyası yeterli olacaktır.</span><span class="sxs-lookup"><span data-stu-id="fd562-246">The default ``launch.json`` should work well for most applications.</span></span>

<span data-ttu-id="fd562-247">Sonuçlar şöyle olmalıdır:</span><span class="sxs-lookup"><span data-stu-id="fd562-247">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[<span data-ttu-id="fd562-248">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fd562-248">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="fd562-249">Yalnızca `F5` tuşuna basın, programınız derlenir ve çalıştırılır!</span><span class="sxs-lookup"><span data-stu-id="fd562-249">Just hit `F5`, and your program should build and run!</span></span>

<span data-ttu-id="fd562-250">Sonuçlar şöyle olmalıdır:</span><span class="sxs-lookup"><span data-stu-id="fd562-250">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

<span data-ttu-id="fd562-251">Bir tuşa bastığınızda programdan çıkılır.</span><span class="sxs-lookup"><span data-stu-id="fd562-251">The program will exit after you press a key.</span></span>

* * *

## <a name="prepare-superposition"></a><span data-ttu-id="fd562-252">Süper konumu hazırlama</span><span class="sxs-lookup"><span data-stu-id="fd562-252">Prepare superposition</span></span>

<span data-ttu-id="fd562-253">**Genel bakış** Şimdi Q# dilinin kubitleri süper konuma alma şeklini nasıl ifade ettiğine bakalım.</span><span class="sxs-lookup"><span data-stu-id="fd562-253">**Overview** Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="fd562-254">Hatırlayacağınız gibi bir kubit 0 ve 1 süper konumlarında olabilir.</span><span class="sxs-lookup"><span data-stu-id="fd562-254">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="fd562-255">Bunu gerçekleştirmek için `Hadamard` işlemini kullanacağız.</span><span class="sxs-lookup"><span data-stu-id="fd562-255">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="fd562-256">Kubitin klasik durumlardan birine olması halinde (ölçümün her zaman `Zero` veya her zaman `One` döndürmesi durumunda) `Hadamard` ya da `H` işlemi kubiti ölçümün %50 oranında `Zero` ve %50 oranında `One` döndüreceği bir duruma alır.</span><span class="sxs-lookup"><span data-stu-id="fd562-256">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="fd562-257">Kavramsal olarak kubitin `Zero` ile `One` arasındaki bir noktada olduğu düşünülebilir.</span><span class="sxs-lookup"><span data-stu-id="fd562-257">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="fd562-258">Şimdi `TestBellState` işleminin simülasyonunu yaptığımızda, ölçüm sonrasında elde edilen sonuçların `Zero` ve `One` için yaklaşık olarak eşit değerler verdiğini göreceğiz.</span><span class="sxs-lookup"><span data-stu-id="fd562-258">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

<span data-ttu-id="fd562-259">İlk olarak kubiti çevirmeyi deneyeceğiz. (Kubit `Zero` durumundaysa `One` durumuna çevireceğiz veya aksi halde işlemin tam tersini yapacağız.)</span><span class="sxs-lookup"><span data-stu-id="fd562-259">First we'll just try to flip the qubit (if the qubit is in `Zero` state will flip to `One` and vice versa).</span></span> <span data-ttu-id="fd562-260">Bu, kubiti `TestBellState` işleminde ölçmeden önce bir `X` işlemi gerçekleştirilerek yapılır:</span><span class="sxs-lookup"><span data-stu-id="fd562-260">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="fd562-261">Şimdi sonuçlar (`F5` tuşuna basıldıktan sonra) tersine çevrilir:</span><span class="sxs-lookup"><span data-stu-id="fd562-261">Now the results (after pressing `F5`) are reversed:</span></span>

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

<span data-ttu-id="fd562-262">Ama şimdiye kadar gördüğümüz her şey klasikti.</span><span class="sxs-lookup"><span data-stu-id="fd562-262">However, everything we've seen so far is classical.</span></span> <span data-ttu-id="fd562-263">Şimdi de bir kuantum sonucu alalım.</span><span class="sxs-lookup"><span data-stu-id="fd562-263">Let's get a quantum result.</span></span> <span data-ttu-id="fd562-264">Önceki çalıştırmadaki `X` işlemini bir `H` veya Hadamard işlemiyle değiştirmemiz yeterli olacaktır.</span><span class="sxs-lookup"><span data-stu-id="fd562-264">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="fd562-265">Kubiti 0'dan 1'e kadar tümüyle çevirmek yerine yalnızca yarı yola kadar çevireceğiz.</span><span class="sxs-lookup"><span data-stu-id="fd562-265">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="fd562-266">`TestBellState` işleminde değiştirilen satırlar şöyle görünür:</span><span class="sxs-lookup"><span data-stu-id="fd562-266">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="fd562-267">Daha ilginç sonuçlar görülmeye başlar:</span><span class="sxs-lookup"><span data-stu-id="fd562-267">Now the results get more interesting:</span></span>

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

<span data-ttu-id="fd562-268">Her ölçtüğümüzde klasik bir değer bekleriz ama kubit 0 ile 1 arasında yarı yoldadır, dolayısıyla (istatistiksel olarak) ölçülerin yarısında 0 ve yarısında da 1 elde ederiz.</span><span class="sxs-lookup"><span data-stu-id="fd562-268">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span> <span data-ttu-id="fd562-269">Bu __süper konum__ olarak bilinir ve bize kuantum durumunun ilk gerçek görünümünü verir.</span><span class="sxs-lookup"><span data-stu-id="fd562-269">This is known as __superposition__ and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="fd562-270">Dolaşıklığı hazırlama</span><span class="sxs-lookup"><span data-stu-id="fd562-270">Prepare entanglement</span></span>

<span data-ttu-id="fd562-271">**Genel bakış:**  Şimdi Q# ile kubitleri dolaşık hale getirme işleminin nasıl ifade edildiğine bakalım.</span><span class="sxs-lookup"><span data-stu-id="fd562-271">**Overview:**  Now let’s look at how Q# expresses ways to entangle qubits.</span></span>  <span data-ttu-id="fd562-272">İlk olarak kubiti başlangıç durumuna getireceğiz ve ardından `H` işlemini kullanarak süper konuma alacağız.</span><span class="sxs-lookup"><span data-stu-id="fd562-272">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="fd562-273">Ardından, ilk kubiti ölçmeden önce Controlled-Not (Kontrollü Değil) anlamına gelen yeni bir işlem (`CNOT`) kullanacağız.</span><span class="sxs-lookup"><span data-stu-id="fd562-273">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for Controlled-Not.</span></span>  <span data-ttu-id="fd562-274">Bu işlemi yürütmenin iki kubit üzerindeki sonucu, birinci kubitin `One` olması durumunda ikinci kubiti çevirmektir.</span><span class="sxs-lookup"><span data-stu-id="fd562-274">The result of executing this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="fd562-275">Şimdi iki kubit de dolaşık hale geldi.</span><span class="sxs-lookup"><span data-stu-id="fd562-275">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="fd562-276">İlk kubit için istatistiklerimiz değişmemiştir (ölçüm sonrasında `Zero` veya `One` olma olasılığı %50’dir) ama şimdi ikinci kubiti ölçtüğümüzde ilk kubitte ölçülenle __her zaman__ aynı olduğu görülür.</span><span class="sxs-lookup"><span data-stu-id="fd562-276">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="fd562-277">`CNOT` geçidimiz iki kubiti dolaşık hale getirmiş, bu şekilde ilkine olanın aynısı diğerine de olmuştur.</span><span class="sxs-lookup"><span data-stu-id="fd562-277">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="fd562-278">Ölçümleri ters çevirirseniz (ilk kubitten önce ikincisini yaparsanız), aynı durum ortaya çıkar.</span><span class="sxs-lookup"><span data-stu-id="fd562-278">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="fd562-279">İlk ölçüm rastgele olacak ve ikincisi ilkinde bulunanla aynı yolu izleyecektir.</span><span class="sxs-lookup"><span data-stu-id="fd562-279">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="fd562-280">İlk yapmamız gereken `TestBellState` işlemine bir kubit yerine 2 kubit ayırmaktır:</span><span class="sxs-lookup"><span data-stu-id="fd562-280">The first thing we'll need to do is allocate 2 qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="fd562-281">Bu sayede `TestBellState` işleminde ölçüm yapmadan (`M`) önce yeni bir işlem (`CNOT`) ekleyebileceğiz:</span><span class="sxs-lookup"><span data-stu-id="fd562-281">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="fd562-282">İlk kubiti başlatarak, başladığımızda kubitin her zaman `Zero` durumunda olduğundan emin olmak için bir `Set` işlemi daha eklemiştik.</span><span class="sxs-lookup"><span data-stu-id="fd562-282">We've added another `Set` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="fd562-283">Serbest bırakmadan önce ikinci kubiti de sıfırlamamız gerekiyor.</span><span class="sxs-lookup"><span data-stu-id="fd562-283">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

<span data-ttu-id="fd562-284">Yordamın tamamı şimdi şöyle görünür:</span><span class="sxs-lookup"><span data-stu-id="fd562-284">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="fd562-285">Bunu çalıştırırsak yine daha önce aldığımız 50-50 sonucunun aynısını alırız.</span><span class="sxs-lookup"><span data-stu-id="fd562-285">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="fd562-286">Öte yandan biz, ölçülen ilk kubite ikinci kubitin nasıl tepki gösterdiğiyle ilgileniyoruz.</span><span class="sxs-lookup"><span data-stu-id="fd562-286">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="fd562-287">Bu istatistiği `TestBellState` işleminin yeni bir sürümüyle ekleriz:</span><span class="sxs-lookup"><span data-stu-id="fd562-287">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="fd562-288">Yeni dönüş değeri (`agree`), ilk kubitten gelen ölçümün ikinci kubitin ölçümüyle her eşleşmesinin kaydını tutar.</span><span class="sxs-lookup"><span data-stu-id="fd562-288">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span> <span data-ttu-id="fd562-289">Ayrıca konak uygulamayı buna göre güncelleştirmemiz gerekir:</span><span class="sxs-lookup"><span data-stu-id="fd562-289">We also have to update the host application accordingly:</span></span>

#### <a name="python"></a>[<span data-ttu-id="fd562-290">Python</span><span class="sxs-lookup"><span data-stu-id="fd562-290">Python</span></span>](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[<span data-ttu-id="fd562-291">C#</span><span class="sxs-lookup"><span data-stu-id="fd562-291">C#</span></span>](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

<span data-ttu-id="fd562-292">Artık çalıştırdığımızda çok şaşırtıcı bir şey elde ederiz:</span><span class="sxs-lookup"><span data-stu-id="fd562-292">Now when we run, we get something pretty amazing:</span></span>

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

<span data-ttu-id="fd562-293">Genel bakışta belirtildiği üzere ilk kubit için istatistiklerimiz değişmemiştir (0 veya 1 olma olasılığı %50’dir) ama şimdi ikinci kubiti ölçtüğümüzde ilk kubitte ölçülenle __her zaman__ aynı olduğu görülür. Bunun nedeni bu kubitlerin dolaşık olmasıdır!</span><span class="sxs-lookup"><span data-stu-id="fd562-293">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

<span data-ttu-id="fd562-294">Tebrikler, ilk kuantum programınızı yazdınız!</span><span class="sxs-lookup"><span data-stu-id="fd562-294">Congratulations, you've written your first quantum program!</span></span>

## <a name="next-steps"></a><span data-ttu-id="fd562-295">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="fd562-295">Next steps</span></span>

<span data-ttu-id="fd562-296">[Grover araması](xref:microsoft.quantum.quickstarts.search) başlıklı öğreticide kuantum bilişiminin en popüler algoritmalarından biri olan Grover aramasını oluşturup çalıştırma adımları gösterilir ve kuantum bilişimiyle gerçek sorunları çözmek için kullanılabilecek güzel bir Q# programı örneği sunulur.</span><span class="sxs-lookup"><span data-stu-id="fd562-296">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="fd562-297">[Quantum Geliştirme Seti'ni Kullanmaya Başlama](xref:microsoft.quantum.welcome) sayfasında, Q# dilini ve kuantum programlamayı öğrenmek için başvurabileceğiniz diğer yöntemlerle ilgili öneriler sunulur.</span><span class="sxs-lookup"><span data-stu-id="fd562-297">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>
