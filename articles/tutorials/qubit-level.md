---
title: İçindeki qubit düzeyi programları yazın ve benzetimini yapın Q#
description: Bireysel qubit düzeyinde çalışan bir hisse programını yazma ve benzetimi yapma hakkında adım adım öğretici
author: gillenhaalb
ms.author: a-gibec
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0dbeee8e092c830576ba8f79733035cdeeac11de
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834967"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a><span data-ttu-id="49a8c-103">Öğretici: Q 'da qubit düzeyi programları yazma ve benzetimini yapma\#</span><span class="sxs-lookup"><span data-stu-id="49a8c-103">Tutorial: Write and simulate qubit-level programs in Q\#</span></span>

<span data-ttu-id="49a8c-104">Her bir qubit üzerinde çalışan temel bir hisse dili programını yazma ve benzetimi yapma hakkında hisse geliştirme seti öğreticisine hoş geldiniz.</span><span class="sxs-lookup"><span data-stu-id="49a8c-104">Welcome to the Quantum Development Kit tutorial on writing and simulating a basic quantum program that operates on individual qubits.</span></span> 

<span data-ttu-id="49a8c-105">Q#Büyük ölçekli hisse programları için öncelikli olarak yüksek düzeyde bir programlama dili olarak oluşturulsa da, daha düşük hisse düzeyi programlarının düzeyini araştırmak için kolayca kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-105">Although Q# was primarily created as a high-level programming language for large-scale quantum programs, it can just as easily be used to explore the lower level of quantum programs: directly addressing specific qubits.</span></span>
<span data-ttu-id="49a8c-106">' Nin esnekliği, Q# kullanıcıların her türlü soyutlama düzeyinden elde etmesine izin verir ve bu öğreticide, qubits 'e de yaklaşıyoruz.</span><span class="sxs-lookup"><span data-stu-id="49a8c-106">The flexibility of Q# allows users to approach quantum systems from any such level of abstraction, and in this tutorial we dive into the qubits themselves.</span></span>
<span data-ttu-id="49a8c-107">Özellikle de, birçok büyük hisse algoritmaya integral olan bir alt yordam olan [hisse](https://en.wikipedia.org/wiki/Quantum_Fourier_transform)</span><span class="sxs-lookup"><span data-stu-id="49a8c-107">Specifically, we take a look under the hood of the [quantum Fourier transform](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), a subroutine that is integral to many larger quantum algorithms.</span></span>

<span data-ttu-id="49a8c-108">Hisse senedi bilgi işlemenin bu alt düzey görünümünün genellikle, bir sistemin belirli qugeler için sıralı uygulamayı temsil eden "[hisse devreleri](xref:microsoft.quantum.concepts.circuits)" bakımından açıklandığına bakın.</span><span class="sxs-lookup"><span data-stu-id="49a8c-108">Note that this low-level view of quantum information processing is often described in terms of "[quantum circuits](xref:microsoft.quantum.concepts.circuits)," which represent the sequential application of gates to specific qubits of a system.</span></span>

<span data-ttu-id="49a8c-109">Bu nedenle, ardışık olarak uygulanan tek ve Multi-qubit işlemleri "devre diyagramı" içinde kolayca temsil edilebilir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-109">Thus, the single- and multi-qubit operations we sequentially apply can be readily represented in a "circuit diagram."</span></span>
<span data-ttu-id="49a8c-110">Bizim örneğimizde, Q# aşağıdaki gösterimi bir devre olarak bulunan tam üç qubit hisse Fourier dönüşümünü gerçekleştirmeye yönelik bir işlem tanımlayacağız:</span><span class="sxs-lookup"><span data-stu-id="49a8c-110">In our case, we will define a Q# operation to perform the full three-qubit quantum Fourier transform, which has the following representation as a circuit:</span></span>

<br/>
<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a><span data-ttu-id="49a8c-111">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="49a8c-111">Prerequisites</span></span>

* <span data-ttu-id="49a8c-112">[Install](xref:microsoft.quantum.install) Tercih ettiğiniz dil ve geliştirme ortamınızı kullanarak hisse geliştirme setini kullanın.</span><span class="sxs-lookup"><span data-stu-id="49a8c-112">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment.</span></span>
* <span data-ttu-id="49a8c-113">Makinenizde QDK zaten yüklüyse en son sürüme [güncelleştirdiğinizden](xref:microsoft.quantum.update) emin olun</span><span class="sxs-lookup"><span data-stu-id="49a8c-113">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>


## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="49a8c-114">Bu öğreticide aşağıdakilerin nasıl yapılacağını öğreneceksiniz:</span><span class="sxs-lookup"><span data-stu-id="49a8c-114">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="49a8c-115">İçinde hisse işlemleri tanımlayın Q#</span><span class="sxs-lookup"><span data-stu-id="49a8c-115">Define quantum operations in Q#</span></span>
> * <span data-ttu-id="49a8c-116">Q#İşlemleri doğrudan komut isteminden veya klasik ana bilgisayar programını kullanarak çağırma</span><span class="sxs-lookup"><span data-stu-id="49a8c-116">Call Q# operations directly from the command prompt or using a classical host program</span></span>
> * <span data-ttu-id="49a8c-117">Ölçüm çıkışına qubit ayırmayı bir hisse alma işlemi benzetimi yap</span><span class="sxs-lookup"><span data-stu-id="49a8c-117">Simulate a quantum operation from qubit allocation to measurement output</span></span>
> * <span data-ttu-id="49a8c-118">Hisse sisteminin sanal dalga işlevinin işlem boyunca nasıl gelişdiğini gözlemleyin</span><span class="sxs-lookup"><span data-stu-id="49a8c-118">Observe how the quantum system's simulated wavefunction evolves throughout the operation</span></span>

<span data-ttu-id="49a8c-119">Microsoft 'un hisse geliştirme seti ile bir hisse programın çalıştırılması genellikle iki bölümden oluşur:</span><span class="sxs-lookup"><span data-stu-id="49a8c-119">Running a quantum program with Microsoft's Quantum Development Kit typically consists of two parts:</span></span>
1. <span data-ttu-id="49a8c-120">Programın kendisi, Q# hisse dili programlama dili kullanılarak uygulanır ve ardından hisse bir bilgisayar veya hisse Benzetici üzerinde çalışmak üzere çağırılır.</span><span class="sxs-lookup"><span data-stu-id="49a8c-120">The program itself, which is implemented using the Q# quantum programming language, and then invoked to run on a quantum computer or quantum simulator.</span></span> <span data-ttu-id="49a8c-121">Bunlardan oluşur</span><span class="sxs-lookup"><span data-stu-id="49a8c-121">These consist of</span></span> 
    - <span data-ttu-id="49a8c-122">Q# işlemler: hisse kayıtları için davranan alt yordamlar ve</span><span class="sxs-lookup"><span data-stu-id="49a8c-122">Q# operations: subroutines acting on quantum registers, and</span></span> 
    - <span data-ttu-id="49a8c-123">Q# işlevler: hisse algoritması içinde kullanılan klasik alt yordamlar.</span><span class="sxs-lookup"><span data-stu-id="49a8c-123">Q# functions: classical subroutines used within the quantum algorithm.</span></span>
2. <span data-ttu-id="49a8c-124">Hisse programını çağırmak ve üzerinde çalıştırılması gereken hedef makineyi belirtmek için kullanılan giriş noktası.</span><span class="sxs-lookup"><span data-stu-id="49a8c-124">The entry point used to call the quantum program and specify the target machine on which it should be run.</span></span>
    <span data-ttu-id="49a8c-125">Bu işlem doğrudan komut isteminden veya Python veya C# gibi bir klasik programlama dilinde yazılmış bir konak programı aracılığıyla yapılabilir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-125">This can be done directly from the command prompt, or through a host program written in a classical programming language like Python or C#.</span></span>
    <span data-ttu-id="49a8c-126">Bu öğretici, tercih ettiğiniz yönteme ilişkin yönergeleri içerir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-126">This tutorial includes instructions for whichever method you prefer.</span></span>

## <a name="allocate-qubits-and-define-quantum-operations"></a><span data-ttu-id="49a8c-127">Qubits ayırın ve hisse alma işlemlerini tanımlayın</span><span class="sxs-lookup"><span data-stu-id="49a8c-127">Allocate qubits and define quantum operations</span></span>

<span data-ttu-id="49a8c-128">Bu öğreticinin ilk bölümü, Q# `Perform3qubitQFT` üç qubit üzerinde hisse Fourier dönüşümünü gerçekleştiren işlemi tanımlamayı içerir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-128">The first part of this tutorial consists of defining the Q# operation `Perform3qubitQFT`, which performs the quantum Fourier transform on three qubits.</span></span> 

<span data-ttu-id="49a8c-129">Ayrıca, [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) üç qubit sistemimizin benzetilen dalga işlevinin işlem genelinde geliştikçe, işlevini kullanacağız.</span><span class="sxs-lookup"><span data-stu-id="49a8c-129">In addition, we will use the [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) function to observe how the simulated wavefunction of our three qubit system evolves across the operation.</span></span>

<span data-ttu-id="49a8c-130">İlk adım, Q# projenizi ve dosyanızı oluşturmaktır.</span><span class="sxs-lookup"><span data-stu-id="49a8c-130">The first step is creating your Q# project and file.</span></span>
<span data-ttu-id="49a8c-131">Bunun adımları programı çağırmak için kullanacağınız ortama bağlıdır ve ilgili [yükleme kılavuzlarındaki](xref:microsoft.quantum.install)ayrıntıları bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="49a8c-131">The steps for this depend on the environment you will use to call the program, and you can find the details in the respective [installation guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="49a8c-132">Adım adım, dosyanın bileşenlerinde size kılavuzluk ederiz, ancak kod aşağıdaki tam bir blok olarak da kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-132">We will walk you through the components of the file step-by-step, but the code is also available as a full block below.</span></span>

### <a name="namespaces-to-access-other-no-locq-operations"></a><span data-ttu-id="49a8c-133">Diğer işlemlere erişmek için ad alanları Q#</span><span class="sxs-lookup"><span data-stu-id="49a8c-133">Namespaces to access other Q# operations</span></span>
<span data-ttu-id="49a8c-134">Dosya içinde, önce derleyici tarafından erişilecek ad alanını tanımlayacağız `NamespaceQFT` .</span><span class="sxs-lookup"><span data-stu-id="49a8c-134">Inside the file, we first define the namespace `NamespaceQFT` which will be accessed by the compiler.</span></span>
<span data-ttu-id="49a8c-135">Operasyonumuz mevcut işlemleri kullanmak için Q# ilgili `Microsoft.Quantum.<>` ad alanlarını açıyoruz.</span><span class="sxs-lookup"><span data-stu-id="49a8c-135">For our operation to make use of existing Q# operations, we open the relevant `Microsoft.Quantum.<>` namespaces.</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a><span data-ttu-id="49a8c-136">Bağımsız değişkenlerle işlemleri tanımlama ve geri dönüş</span><span class="sxs-lookup"><span data-stu-id="49a8c-136">Define operations with arguments and returns</span></span>
<span data-ttu-id="49a8c-137">Sonra, işlemi tanımladık `Perform3qubitQFT` :</span><span class="sxs-lookup"><span data-stu-id="49a8c-137">Next, we define the `Perform3qubitQFT` operation:</span></span>

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

<span data-ttu-id="49a8c-138">Şimdilik işlem herhangi bir bağımsız değişken almaz ve bu durumda---hiçbir şey döndürmez; bu durumda, `Unit` `void` Python 'Da C# veya boş bir tanımlama alanı olan bir nesneyi döndüren bir nesne döndürür `Tuple[()]` .</span><span class="sxs-lookup"><span data-stu-id="49a8c-138">For now, the operation takes no arguments and does not return anything---in this case we write that it returns a `Unit` object, which is akin to `void` in C# or an empty tuple, `Tuple[()]`, in Python.</span></span>
<span data-ttu-id="49a8c-139">Daha sonra, bunu bir dizi ölçüm sonucu döndürecek şekilde değiştirecek ve bu noktada `Unit` Değiştirilecek `Result[]` .</span><span class="sxs-lookup"><span data-stu-id="49a8c-139">Later, we will modify it to return an array of measurement results, at which point `Unit` will be replaced by `Result[]`.</span></span> 

### <a name="allocate-qubits-with-using"></a><span data-ttu-id="49a8c-140">İle qubit ayırın `using`</span><span class="sxs-lookup"><span data-stu-id="49a8c-140">Allocate qubits with `using`</span></span>
<span data-ttu-id="49a8c-141">Bizim Q# işlem dahilinde, öncelikle şu deyimle üç qubit kaydı ayırdık `using` :</span><span class="sxs-lookup"><span data-stu-id="49a8c-141">Within our Q# operation, we first allocate a register of three qubits with the `using` statement:</span></span>

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

<span data-ttu-id="49a8c-142">İle `using` , qubits $ \ket $ durumunda otomatik olarak ayrılır {0} .</span><span class="sxs-lookup"><span data-stu-id="49a8c-142">With `using`, the qubits are automatically allocated in the $\ket{0}$ state.</span></span> <span data-ttu-id="49a8c-143">Bunu [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , ve ' ı kullanarak, bir dizeyi ve sistemin geçerli durumunu konsola yazdıracak şekilde doğrulayabiliriz.</span><span class="sxs-lookup"><span data-stu-id="49a8c-143">We can verify this by using [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) and [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine), which print a string and the system's current state to the console.</span></span>

> [!NOTE]
> <span data-ttu-id="49a8c-144">`Message(<string>)`Ve `DumpMachine()` işlevleri ( [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) ve [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) sırasıyla), her ikisi de doğrudan konsola yazdırılır.</span><span class="sxs-lookup"><span data-stu-id="49a8c-144">The `Message(<string>)` and `DumpMachine()` functions (from [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics), respectively) both print directly to the console.</span></span> <span data-ttu-id="49a8c-145">Tıpkı gerçek bir hisse hesaplamasına benzer şekilde, Q# qubit durumlarına doğrudan erişememize izin vermez.</span><span class="sxs-lookup"><span data-stu-id="49a8c-145">Just like a real quantum computation, Q# does not allow us to directly access qubit states.</span></span>
> <span data-ttu-id="49a8c-146">Ancak, `DumpMachine` hedef makinenin geçerli durumunu yazdırdığından, tam durum simülatörü ile birlikte kullanıldığında hata ayıklama ve öğrenimi için değerli öngörüler sağlayabilir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-146">However, as `DumpMachine` prints the target machine's current state, it can provide valuable insight for debugging and learning when used in conjunction with the full state simulator.</span></span>


### <a name="applying-single-qubit-and-controlled-gates"></a><span data-ttu-id="49a8c-147">Tek qubit ve denetimli kapıları uygulama</span><span class="sxs-lookup"><span data-stu-id="49a8c-147">Applying single-qubit and controlled gates</span></span>

<span data-ttu-id="49a8c-148">Daha sonra, işlemin kendisini oluşturan kapıları uyguladık.</span><span class="sxs-lookup"><span data-stu-id="49a8c-148">Next, we apply the gates which comprise the operation itself.</span></span>
<span data-ttu-id="49a8c-149">Q# , ad alanında işlem olarak birçok temel hisse kapısı zaten içeriyor [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) ve bunlar özel durum değildir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-149">Q# already contains many basic quantum gates as operations in the [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) namespace, and these are no exception.</span></span> 

<span data-ttu-id="49a8c-150">Bir işlem içinde, Q# callables çağıran deyimler, tabii ki sıralı sırayla çalıştırılır.</span><span class="sxs-lookup"><span data-stu-id="49a8c-150">Within a Q# operation, the statements invoking callables will, of course, be run in sequential order.</span></span>
<span data-ttu-id="49a8c-151">Bu nedenle, uygulanacak ilk kapı [`H`](xref:microsoft.quantum.intrinsic.h) ilk qubit 'e (Hadamard) sahiptir:</span><span class="sxs-lookup"><span data-stu-id="49a8c-151">Hence, the first gate to apply is the [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) to the first qubit:</span></span>

<br/>
<img src="../media/qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

<span data-ttu-id="49a8c-152">Bir kayıttaki belirli bir qubit 'e bir işlem uygulamak için (bir dizideki tek bir `Qubit` dizi `Qubit[]` ) standart dizin gösterimini kullanırız.</span><span class="sxs-lookup"><span data-stu-id="49a8c-152">To apply an operation to a specific qubit from a register (i.e. a single `Qubit` from an array `Qubit[]`) we use standard index notation.</span></span>
<span data-ttu-id="49a8c-153">Bu nedenle, [`H`](xref:microsoft.quantum.intrinsic.h) kayıt yaptığımız ilk qubit 'e uygulamak şu `qs` biçimdedir:</span><span class="sxs-lookup"><span data-stu-id="49a8c-153">So, applying the [`H`](xref:microsoft.quantum.intrinsic.h) to the first qubit of our register `qs` takes the form:</span></span>

```qsharp
            H(qs[0]);
```

<span data-ttu-id="49a8c-154">`H`(Hadamard) geçidini tek bir qubits 'e uygulamanın yanı sıra, QFT devresi öncelikle denetlenen döndürmeler ' i içerir [`R1`](xref:microsoft.quantum.intrinsic.r1) .</span><span class="sxs-lookup"><span data-stu-id="49a8c-154">Besides applying the `H` (Hadamard) gate to individual qubits, the QFT circuit consists primarily of controlled [`R1`](xref:microsoft.quantum.intrinsic.r1) rotations.</span></span>
<span data-ttu-id="49a8c-155">`R1(θ, <qubit>)`Genel içindeki bir işlem {0} , qubit 'in $ \ket $ bileşenini $ \ket $ bileşenine bir $e dönüşü uygulanırken, aynı şekilde değişmeden bırakır {1} .</span><span class="sxs-lookup"><span data-stu-id="49a8c-155">An `R1(θ, <qubit>)` operation in general leaves the $\ket{0}$ component of the qubit unchanged, while applying a rotation of $e^{i\theta}$ to the $\ket{1}$ component.</span></span>

#### <a name="controlled-operations"></a><span data-ttu-id="49a8c-156">Denetlenen işlemler</span><span class="sxs-lookup"><span data-stu-id="49a8c-156">Controlled operations</span></span>

<span data-ttu-id="49a8c-157">Q# bir veya birden fazla denetim qubit üzerinde bir işlemin çalıştırılmasına son derece kolay hale getirir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-157">Q# makes it extremely easy to condition the run of an operation upon one or multiple control qubits.</span></span>
<span data-ttu-id="49a8c-158">Genel olarak, yalnızca ile çağrıyı önliyoruz `Controlled` ve işlem bağımsız değişkenleri şu şekilde değişir:</span><span class="sxs-lookup"><span data-stu-id="49a8c-158">In general, we merely preface the call with `Controlled`, and the operation arguments change as:</span></span>

 <span data-ttu-id="49a8c-159">`Op(<normal args>)` $ \-$ `Controlled Op([<control qubits>], (<normal args>))` .</span><span class="sxs-lookup"><span data-stu-id="49a8c-159">`Op(<normal args>)` $\to$ `Controlled Op([<control qubits>], (<normal args>))`.</span></span>

<span data-ttu-id="49a8c-160">Tek bir qubit olsa bile denetim qubits 'in bir dizi olarak sağlanması gerektiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="49a8c-160">Note that the control qubits must be provided as an array, even if it is a single qubit.</span></span>

<span data-ttu-id="49a8c-161">Sonrasında, `H` sonraki kapıların `R1` ilk qubit üzerinde hareket eden kapıları olduğunu ve ikinci/üçüncü tarafından denetlendiğini görüyoruz:</span><span class="sxs-lookup"><span data-stu-id="49a8c-161">After the `H`, we see that the next gates are the `R1` gates acting on the first qubit (and controlled by the second/third):</span></span>

<br/>
<img src="../media/qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

<span data-ttu-id="49a8c-162">Bunları şu şekilde çağırır</span><span class="sxs-lookup"><span data-stu-id="49a8c-162">We call these with</span></span>

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

<span data-ttu-id="49a8c-163">Bu [`PI()`](xref:microsoft.quantum.math.pi) işlevi, [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) ad alanından Pi radyana kadar olan işlevleri tanımlamak için kullandığımızda aklınızda olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="49a8c-163">Note that we use the [`PI()`](xref:microsoft.quantum.math.pi) function from the [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) namespace to define the rotations in terms of pi radians.</span></span>
<span data-ttu-id="49a8c-164">Ayrıca, bir `Double` (örn.), bir `2.0` tamsayı ile bölmek bir `2` tür hatası oluşturacak.</span><span class="sxs-lookup"><span data-stu-id="49a8c-164">Additionally, we divide by a `Double` (e.g. `2.0`) because dividing by an integer `2` would throw a type error.</span></span> 

> [!TIP]
> <span data-ttu-id="49a8c-165">`R1(π/2)` ve `R1(π/4)` , `S` ve `T` işlemlerine eşdeğerdir (Ayrıca içinde `Microsoft.Quantum.Intrinsic` ).</span><span class="sxs-lookup"><span data-stu-id="49a8c-165">`R1(π/2)` and `R1(π/4)` are equivalent to the `S` and `T` operations (also in `Microsoft.Quantum.Intrinsic`).</span></span>


<span data-ttu-id="49a8c-166">`H`İkinci ve üçüncü qubits 'e ilgili işlemler ve denetlenen döndürmeler uygulandıktan sonra:</span><span class="sxs-lookup"><span data-stu-id="49a8c-166">After applying the relevant `H` operations and controlled rotations to the second and third qubits:</span></span>

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

<span data-ttu-id="49a8c-167">[`SWAP`](xref:microsoft.quantum.intrinsic.swap)devresini tamamlamaya yönelik yalnızca bir geçit uygulamanız gerekir:</span><span class="sxs-lookup"><span data-stu-id="49a8c-167">we need only apply a [`SWAP`](xref:microsoft.quantum.intrinsic.swap) gate to complete the circuit:</span></span>

```qsharp
            SWAP(qs[2], qs[0]);
```

<span data-ttu-id="49a8c-168">Bu gereklidir çünkü, bu işlem, bu, boyut ve alt yordamın daha büyük algoritmalara sorunsuz bir şekilde tümleştirilmesini sağlar.</span><span class="sxs-lookup"><span data-stu-id="49a8c-168">This is necessary because the nature of the quantum Fourier transform outputs the qubits in reverse order, so the swaps allow for seamless integration of the subroutine into larger algorithms.</span></span>

<span data-ttu-id="49a8c-169">Bu nedenle, bu nedenle, hisse bir şekilde hisse Q#</span><span class="sxs-lookup"><span data-stu-id="49a8c-169">Hence we have finished writing the qubit-level operations of the quantum Fourier transform into our Q# operation:</span></span>

<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

<span data-ttu-id="49a8c-170">Ancak henüz bir gün arayamıyoruz.</span><span class="sxs-lookup"><span data-stu-id="49a8c-170">However, we can't call it a day just yet.</span></span>
<span data-ttu-id="49a8c-171">Qubits 'lerimiz {0} , ayrıldığımızda $ \demet $ durumunda ve çok benzer şekilde, Q# her şeyi bulduğumuz gibi bırakmamız gerekir (veya daha iyi!).</span><span class="sxs-lookup"><span data-stu-id="49a8c-171">Our qubits were in state $\ket{0}$ when we allocated them, and much like in life, in Q# we should leave things the same way we found them (or better!).</span></span>

### <a name="deallocate-qubits"></a><span data-ttu-id="49a8c-172">Qubit serbest bırakma</span><span class="sxs-lookup"><span data-stu-id="49a8c-172">Deallocate qubits</span></span>

<span data-ttu-id="49a8c-173">[`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine)İşlem sonrası durumunu görmek için yeniden çağrımız ve son olarak, [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) işlemi tamamlamadan önce qubits 'i $ \ket $ ile sıfırlamak için qubit kayıt için geçerlidir {0} :</span><span class="sxs-lookup"><span data-stu-id="49a8c-173">We call [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) again to see the post-operation state, and finally apply [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) to the qubit register to reset our qubits to $\ket{0}$ before completing the operation:</span></span>

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

<span data-ttu-id="49a8c-174">Tüm serbest bırakılmış qubits 'in, {0} Q# aynı qubit (bir nadir kaynağı) ile çalışmaya başladıklarında durumlarını tam olarak öğrenmesini sağlayan temel bir özelliğidir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-174">Requiring that all deallocated qubits be explicitly set to $\ket{0}$ is a basic feature of Q#, as it allows other operations to know their state precisely when they begin using those same qubits (a scarce resource).</span></span>
<span data-ttu-id="49a8c-175">Buna ek olarak, bu, sistemdeki diğer qubits ile zenginler olmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="49a8c-175">Additionally, this assures that they not be entangled with any other qubits in the system.</span></span>
<span data-ttu-id="49a8c-176">Bir ayırma bloğunun sonunda sıfırlama gerçekleştirildiyse `using` , bir çalışma zamanı hatası oluşur.</span><span class="sxs-lookup"><span data-stu-id="49a8c-176">If the reset is not performed at the end of a `using` allocation block, a runtime error will be thrown.</span></span>

<span data-ttu-id="49a8c-177">Tam Q# dosyanız şu şekilde görünmelidir:</span><span class="sxs-lookup"><span data-stu-id="49a8c-177">Your full Q# file should now look like this:</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


<span data-ttu-id="49a8c-178">Q#Dosya ve işlem tamamlandıktan sonra, hisse mamızda program çağrılmaya ve benzetimine hazırlanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="49a8c-178">With the Q# file and operation complete, our quantum program is ready to be called and simulated.</span></span>

## <a name="run-the-program"></a><span data-ttu-id="49a8c-179">Programı çalıştırma</span><span class="sxs-lookup"><span data-stu-id="49a8c-179">Run the program</span></span>

<span data-ttu-id="49a8c-180">Q#İşleminizi bir `.qs` dosyada tanımladık, şimdi bu işlemi çağırmalı ve döndürülen klasik verileri gözlemleyeceğiz.</span><span class="sxs-lookup"><span data-stu-id="49a8c-180">Having defined our Q# operation in a `.qs` file, we now need to call that operation and observe any returned classical data.</span></span>
<span data-ttu-id="49a8c-181">Şimdilik, döndürülen hiçbir şey yok (daha sonra işlem tarafından tanımlanan işlemin döndürdüğü geri çek `Unit` ), ancak daha sonra işlemi daha sonra Q# ölçüm sonuçları dizisi döndürecek şekilde değiştirdiğimiz zaman, `Result[]` bunu ele alınacaktır.</span><span class="sxs-lookup"><span data-stu-id="49a8c-181">For now, there isn't anything returned (recall that our operation defined above returns `Unit`), but when we later modify the Q# operation to return an array of measurement results (`Result[]`), we will address this.</span></span>

<span data-ttu-id="49a8c-182">Program, Q# Bu işlemi çağırmak için kullanılan ortamlarda bizden gerçekleşirken, bunu yapmanın yolu da farklılık gösterir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-182">While the Q# program is ubiquitous across the environments used to call it, the manner of doing so will of course vary.</span></span> <span data-ttu-id="49a8c-183">Bu nedenle, kuruluma karşılık gelen sekmedeki yönergeleri izlemeniz yeterlidir: Q# uygulamadan çalışma veya Python ya da C# ' de bir konak programı kullanma.</span><span class="sxs-lookup"><span data-stu-id="49a8c-183">As such, simply follow the instructions in the tab corresponding to your setup: working from the Q# application or using a host program in Python or C#.</span></span>

#### <a name="command-prompt"></a>[<span data-ttu-id="49a8c-184">Komut istemi</span><span class="sxs-lookup"><span data-stu-id="49a8c-184">Command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="49a8c-185">Q#Programı komut isteminden çalıştırmak, dosyada yalnızca küçük bir değişiklik yapılmasını gerektirir Q# .</span><span class="sxs-lookup"><span data-stu-id="49a8c-185">Running the Q# program from the command prompt requires only a small change to the Q# file.</span></span>

<span data-ttu-id="49a8c-186">`@EntryPoint()`İşlem tanımından önceki bir satıra eklemeniz yeterlidir:</span><span class="sxs-lookup"><span data-stu-id="49a8c-186">Simply add `@EntryPoint()` to a line preceding the operation definition:</span></span>

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

<span data-ttu-id="49a8c-187">Programı çalıştırmak için, terminali projenizin klasöründe açın ve şunu girin</span><span class="sxs-lookup"><span data-stu-id="49a8c-187">To run the program, open the terminal in the folder of your project and enter</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="49a8c-188">Tamamlandıktan sonra, `Message` `DumpMachine` aşağıda ve aşağıdaki çıktıları konsolunuza görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-188">Upon completion, you should see the `Message` and `DumpMachine` outputs below printed in your console.</span></span>


#### <a name="python"></a>[<span data-ttu-id="49a8c-189">Python</span><span class="sxs-lookup"><span data-stu-id="49a8c-189">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="49a8c-190">Python ana bilgisayar dosyası oluştur: `host.py` .</span><span class="sxs-lookup"><span data-stu-id="49a8c-190">Create a Python host file: `host.py`.</span></span>

<span data-ttu-id="49a8c-191">Ana bilgisayar dosyası şu şekilde oluşturulur:</span><span class="sxs-lookup"><span data-stu-id="49a8c-191">The host file is constructed as follows:</span></span> 
1. <span data-ttu-id="49a8c-192">Öncelikle modül `qsharp` yükleyicisini birlikte çalışabilirlik için kaydeden modülünü içeri aktardık Q# .</span><span class="sxs-lookup"><span data-stu-id="49a8c-192">First, we import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="49a8c-193">Bu Q# , ad alanlarını (ör. `NamespaceQFT` bizim örneğimizde tanımladığımız Q# ), içinden içeri aktarabilmemiz için Python modülleri olarak görünmesini sağlar Q# .</span><span class="sxs-lookup"><span data-stu-id="49a8c-193">This allows Q# namespaces (e.g. the `NamespaceQFT` we defined in our Q# file) to appear as Python modules, from which we can import Q# operations.</span></span>
2. <span data-ttu-id="49a8c-194">Ardından, Q# Bu durumda---doğrudan çağıracağız işlemleri içeri aktarın `Perform3qubitQFT` .</span><span class="sxs-lookup"><span data-stu-id="49a8c-194">Then, import the Q# operations which we will directly invoke---in this case, `Perform3qubitQFT`.</span></span>
    <span data-ttu-id="49a8c-195">Giriş noktasını yalnızca bir Q# programa (ve gibi _değil_ `H` `R1` , başka işlemler tarafından çağrılan Q# ancak hiçbir şekilde klasik ana bilgisayar tarafından çağırılan) içeri aktarmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-195">We need only import the entry point into a Q# program (i.e. _not_ operations like `H` and `R1`, which are called by other Q# operations but never by the classical host).</span></span>
3. <span data-ttu-id="49a8c-196">Q#İşlem veya işlevlerin benzetimini yaparken, `<Q#callable>.simulate(<args>)` hedef makinede çalıştırmak için formunu kullanın `QuantumSimulator()` .</span><span class="sxs-lookup"><span data-stu-id="49a8c-196">In simulating Q# operations or functions, use the form `<Q#callable>.simulate(<args>)` to run them on the `QuantumSimulator()` target machine.</span></span> 

> [!NOTE]
> <span data-ttu-id="49a8c-197">İşlemi farklı bir makinede çağırmak isteseyk, örneğin, `ResourceEstimator()` yalnızca kullanacağız `<Q#callable>.estimate_resources(<args>)` .</span><span class="sxs-lookup"><span data-stu-id="49a8c-197">If we wanted to call the operation on a different machine, for example the `ResourceEstimator()`, we would simply use `<Q#callable>.estimate_resources(<args>)`.</span></span>
> <span data-ttu-id="49a8c-198">Genel olarak, Q# işlemler çalıştıkları makinelere belirsizdir, ancak gibi bazı özellikler `DumpMachine` farklı davranabilir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-198">In general, Q# operations are agnostic to the machines on which they're run, but some features such as `DumpMachine` may behave differently.</span></span>

4. <span data-ttu-id="49a8c-199">Benzetimi gerçekleştirdikten sonra işlem çağrısı, dosyada tanımlanan şekilde değerleri döndürür Q# .</span><span class="sxs-lookup"><span data-stu-id="49a8c-199">Upon performing the simulation, the operation call will return values as defined in the Q# file.</span></span>
    <span data-ttu-id="49a8c-200">Şimdilik hiçbir şey döndürülmedi, ancak daha sonra bu değerleri atamaya ve işlemeye yönelik bir örnek görüyoruz.</span><span class="sxs-lookup"><span data-stu-id="49a8c-200">For now there is nothing returned, but later on we will see an example of assigning and processing these values.</span></span>
    <span data-ttu-id="49a8c-201">Uygulamalı ve tamamen klasik verileri elde ettiğimiz için, beğendiğimiz her şeyi yapabiliriz.</span><span class="sxs-lookup"><span data-stu-id="49a8c-201">With the resultant data in our hands and totally classical, we can do whatever we'd like with it.</span></span>

<span data-ttu-id="49a8c-202">Tam `host.py` dosyanız şu şekilde olmalıdır:</span><span class="sxs-lookup"><span data-stu-id="49a8c-202">Your full `host.py` file should be this:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

<span data-ttu-id="49a8c-203">Python dosyasını çalıştırın ve konsolunuza yazdırıldıktan `Message` sonra aşağıdaki ve çıkışları görmeniz gerekir `DumpMachine` .</span><span class="sxs-lookup"><span data-stu-id="49a8c-203">Run the Python file, and printed in your console you should see the `Message` and `DumpMachine` outputs below.</span></span> 


#### <a name="c"></a>[<span data-ttu-id="49a8c-204">C#</span><span class="sxs-lookup"><span data-stu-id="49a8c-204">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="49a8c-205">[Install kılavuzundaki](xref:microsoft.quantum.install.cs)ile aynı yönergeleri Izleyerek bir C# konak dosyası oluşturun ve olarak yeniden adlandırın `host.cs` .</span><span class="sxs-lookup"><span data-stu-id="49a8c-205">Following the same instructions as in the [install guide](xref:microsoft.quantum.install.cs), create a C# host file, and rename it to `host.cs`.</span></span>

<span data-ttu-id="49a8c-206">C# ana bilgisayarının dört bölümü vardır:</span><span class="sxs-lookup"><span data-stu-id="49a8c-206">The C# host has four parts:</span></span>
1. <span data-ttu-id="49a8c-207">Kuantum simülatörünü oluşturma.</span><span class="sxs-lookup"><span data-stu-id="49a8c-207">Construct a quantum simulator.</span></span>
    <span data-ttu-id="49a8c-208">Aşağıdaki kodda, bu değişkendir `qsim` .</span><span class="sxs-lookup"><span data-stu-id="49a8c-208">In the code below, this is the variable `qsim`.</span></span>
2. <span data-ttu-id="49a8c-209">Kuantum algoritması için gereken tüm bağımsız değişkenleri hesaplama.</span><span class="sxs-lookup"><span data-stu-id="49a8c-209">Compute any arguments required for the quantum algorithm.</span></span>
    <span data-ttu-id="49a8c-210">Bu örnekte hiçbiri yok.</span><span class="sxs-lookup"><span data-stu-id="49a8c-210">There are none in this example.</span></span>
3. <span data-ttu-id="49a8c-211">Kuantum algoritmasını çalıştırma.</span><span class="sxs-lookup"><span data-stu-id="49a8c-211">Run the quantum algorithm.</span></span> 
    <span data-ttu-id="49a8c-212">Her Q# işlem aynı ada sahip bir C# sınıfı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="49a8c-212">Each Q# operation generates a C# class with the same name.</span></span> 
    <span data-ttu-id="49a8c-213">Bu sınıfın `Run` işlemi **zaman uyumsuz**olarak çalıştıran bir yöntemi vardır.</span><span class="sxs-lookup"><span data-stu-id="49a8c-213">This class has a `Run` method that runs the operation **asynchronously**.</span></span>
    <span data-ttu-id="49a8c-214">Çalışma zaman uyumsuz çünkü gerçek donanımda çalıştırmak zaman uyumsuz olacaktır.</span><span class="sxs-lookup"><span data-stu-id="49a8c-214">The run is asynchronous because running it on actual hardware will be asynchronous.</span></span> 
    <span data-ttu-id="49a8c-215">`Run`Yöntemi zaman uyumsuz olduğundan, yöntemi çağırıyoruz `Wait()` ; Bu işlem, görev tamamlanana kadar çalışmayı engeller ve sonucu zaman uyumlu olarak döndürür.</span><span class="sxs-lookup"><span data-stu-id="49a8c-215">Because the `Run` method is asynchronous, we call the `Wait()` method; this blocks the run until the task completes and returns the result synchronously.</span></span> 
4. <span data-ttu-id="49a8c-216">İşlemin döndürülen sonucunu işleyin.</span><span class="sxs-lookup"><span data-stu-id="49a8c-216">Process the returned result of the operation.</span></span>
    <span data-ttu-id="49a8c-217">Şimdilik işlem hiçbir şey döndürmez.</span><span class="sxs-lookup"><span data-stu-id="49a8c-217">For now, the operation returns nothing.</span></span>


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
<span data-ttu-id="49a8c-218">Uygulamayı çalıştırın ve çıktın aşağıdaki ile eşleşmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-218">Run the application, and your output should match that below.</span></span>
<span data-ttu-id="49a8c-219">Bir tuşa bastığınızda programdan çıkılır.</span><span class="sxs-lookup"><span data-stu-id="49a8c-219">The program will exit after you press a key.</span></span>
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

<span data-ttu-id="49a8c-220">Tam durum simülatörü üzerinde çağrıldığında, `DumpMachine()` hisse Eyaleti 'nin dalga işlevinin bu çoklu gösterimlerini sağlar.</span><span class="sxs-lookup"><span data-stu-id="49a8c-220">When called on the full-state simulator, `DumpMachine()` provides these mutliple representations of the quantum state's wavefunction.</span></span> <span data-ttu-id="49a8c-221">Bir $n $-qubit sisteminin olası durumları, her biri karşılık gelen bir karmaşık katsayı (yalnızca genliği ve bir aşama) olan $2 ^ n $ hesaplama tabanlı durumlar ile temsil edilebilir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-221">The possible states of an $n$-qubit system can be represented by $2^n$ computational basis states, each with a corresponding complex coefficient (simply an amplitude and a phase).</span></span>
<span data-ttu-id="49a8c-222">Hesaplama tabanlı durumlar, {0} {1} her ikili basamağın tek bir qubit 'e karşılık geldiği, qubit durumlarının $ \tus$ ve $ \ket $ ' nin olası tüm birleşimleri olan $n $---uzunluğunun tüm olası ikili dizelerine karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-222">The computational basis states correspond to all the possible binary strings of length $n$---that is, all the possible combinations of qubit states $\ket{0}$ and $\ket{1}$, where each binary digit corresponds to an individual qubit.</span></span>

<span data-ttu-id="49a8c-223">İlk satır, karşılık gelen qubits kimlikleri için önemli sırayla bir açıklama sağlar.</span><span class="sxs-lookup"><span data-stu-id="49a8c-223">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="49a8c-224">`2`"En önemli" olan qubit, taban durum vektörü $ \ket{i} $ öğesinin ikili gösteriminde, qubit durumunun `2` en soldaki basamağa karşılık geldiğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-224">Qubit `2` being the "most significant" simply means that in the binary representation of basis state vector $\ket{i}$, the state of qubit `2` corresponds to the left-most digit.</span></span> <span data-ttu-id="49a8c-225">Örneğin, $ \ket {6} = \ket $, qubit ve her ikisi de $ \gre$ ' da $ {110} `2` `1` {1} \gre$ ve qubit ' te `0` {0} .</span><span class="sxs-lookup"><span data-stu-id="49a8c-225">For example, $\ket{6} = \ket{110}$ comprises qubits `2` and `1` both in $\ket{1}$ and qubit `0` in $\ket{0}$.</span></span>


<span data-ttu-id="49a8c-226">Satırların geri kalanı, hem Kartezyen hem de kutupsal biçimlerdeki temel eyalet vektörü $ \ket{i} $ ölçgenin olasılığını anlatmaktadır.</span><span class="sxs-lookup"><span data-stu-id="49a8c-226">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{i}$ in both Cartesian and polar formats.</span></span>
<span data-ttu-id="49a8c-227">Giriş durumumuz ilk satırı için ayrıntılı $ \ ayraç {000} $:</span><span class="sxs-lookup"><span data-stu-id="49a8c-227">In detail for the first row of our input state $\ket{000}$:</span></span>
* <span data-ttu-id="49a8c-228">**`|0>:`** Bu satır, `0` Hesaplama esası durumuna karşılık gelir (ilk durum ayırma sonrası $ \ket {000} $ olur, bunun için bu noktada olasılık genliği olan tek durum olması beklenir).</span><span class="sxs-lookup"><span data-stu-id="49a8c-228">**`|0>:`** this row corresponds to the `0` computational basis state (given that our initial state post-allocation was $\ket{000}$, we would expect this to be the only state with probability amplitude at this point).</span></span>
* <span data-ttu-id="49a8c-229">**`1.000000 +  0.000000 i`**: Kartezyen biçiminde olasılık genliği.</span><span class="sxs-lookup"><span data-stu-id="49a8c-229">**`1.000000 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="49a8c-230">**` == `**: `equal` işaret, her iki eşdeğer temsili de ayırır.</span><span class="sxs-lookup"><span data-stu-id="49a8c-230">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="49a8c-231">**`********************`**: Büyüklük grafik gösterimi, sayısı `*` Bu durum vektörünü ölçme olasılığının müşterinizin istekleriyle orantılı.</span><span class="sxs-lookup"><span data-stu-id="49a8c-231">**`********************`**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span> 
* <span data-ttu-id="49a8c-232">**`[ 1.000000 ]`**: büyüklük sayısal değeri</span><span class="sxs-lookup"><span data-stu-id="49a8c-232">**`[ 1.000000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="49a8c-233">**`    ---`**: Genin aşamasının grafik gösterimi.</span><span class="sxs-lookup"><span data-stu-id="49a8c-233">**`    ---`**: A graphical representation of the amplitude's phase.</span></span>
* <span data-ttu-id="49a8c-234">**`[ 0.0000 rad ]`**: aşamanın sayısal değeri (radyan cinsinden).</span><span class="sxs-lookup"><span data-stu-id="49a8c-234">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="49a8c-235">Büyüklük ve aşama bir grafik gösterimiyle birlikte görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-235">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="49a8c-236">Büyüklük temsili basittir: bir çubuğu gösterir `*` ve olasılık arttıkça, çubuk ne kadar büyük olur.</span><span class="sxs-lookup"><span data-stu-id="49a8c-236">The magnitude representation is straightforward: it shows a bar of `*`, and the higher the probability, the larger the bar will be.</span></span> <span data-ttu-id="49a8c-237">Aşama için bkz. [test ve hata ayıklama:](xref:microsoft.quantum.guide.testingdebugging#dump-functions) açı aralıklarına dayanan olası sembol temsilleri için döküm işlevleri.</span><span class="sxs-lookup"><span data-stu-id="49a8c-237">For the phase, see [Testing and debugging: dump functions](xref:microsoft.quantum.guide.testingdebugging#dump-functions) for the possible symbol representations based on angle ranges.</span></span>


<span data-ttu-id="49a8c-238">Bu nedenle, yazdırılan çıktı, programlanmış kapıları durumumuzu dönüştürdüğünü gösterir</span><span class="sxs-lookup"><span data-stu-id="49a8c-238">So, the printed output is illustrating that our programmed gates transformed our state from</span></span>

<span data-ttu-id="49a8c-239">$ $ \ket{\psı} \_ {Initial} = \ket {000} $ $</span><span class="sxs-lookup"><span data-stu-id="49a8c-239">$$ \ket{\psi}\_{initial} = \ket{000} $$</span></span>

<span data-ttu-id="49a8c-240">şöyle değiştirin:</span><span class="sxs-lookup"><span data-stu-id="49a8c-240">to</span></span> 

<span data-ttu-id="49a8c-241">$ $ \begin{hizalaması} \ket{\psı} \_ {final} &= \frac {\sqrt} \left (\ket + \tus+ \tus+ \tus+ \tus+ \ket {1} {8} {000} {001} {010} {011} {100} {101} + \ket {110} + \ ayraç {111} \ sağ) \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}, \end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="49a8c-241">$$ \begin{align} \ket{\psi}\_{final} &= \frac{1}{\sqrt{8}} \left( \ket{000} + \ket{001} + \ket{010} + \ket{011} + \ket{100} + \ket{101} + \ket{110} + \ket{111}  \right) \\\\ &= \frac{1}{\sqrt{2^n}}\sum\_{j=0}^{2^n-1} \ket{j}, \end{align} $$</span></span>

<span data-ttu-id="49a8c-242">Bu, 3-qubit Fourier dönüştürmesinin kesin bir davranıştır.</span><span class="sxs-lookup"><span data-stu-id="49a8c-242">which is precisely the behavior of the 3-qubit Fourier transform.</span></span> 

<span data-ttu-id="49a8c-243">Diğer giriş durumlarının nasıl etkilendiğini merak ediyorsanız, dönüşümden önce qubit işlemleri uygulamayla birlikte oynamanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="49a8c-243">If you are curious about how other input states are affected, we encourage you to play around with applying qubit operations before the transform.</span></span>

## <a name="adding-measurements"></a><span data-ttu-id="49a8c-244">Ölçümler ekleme</span><span class="sxs-lookup"><span data-stu-id="49a8c-244">Adding measurements</span></span>

<span data-ttu-id="49a8c-245">Ne yazık ki hisse kuyadan oluşan bir temel taş, gerçek bir hisse sisteminin böyle bir işleve sahip olmadığını bize söyler `DumpMachine` .</span><span class="sxs-lookup"><span data-stu-id="49a8c-245">Unfortunately, a cornerstone of quantum mechanics tells us that a real quantum system cannot have such a `DumpMachine` function.</span></span> <span data-ttu-id="49a8c-246">Bunun yerine, bilgileri ölçümler aracılığıyla ayıklamaya zorlıyoruz. Bu, genel olarak yalnızca bize tam hisse alım durumunu sağlamayarak, ancak sistemin kendisini büyük ölçüde değiştirebilir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-246">Instead, we're forced to extract information through measurements, which in general not only fail to provide us the full quantum state, but can also drastically alter the system itself.</span></span>
<span data-ttu-id="49a8c-247">Birçok hisse ölçüm ölçümü vardır ancak tek bir qubit üzerinde en temel: çoklu ölçümler üzerinde odaklanacağız.</span><span class="sxs-lookup"><span data-stu-id="49a8c-247">There are many sorts of quantum measurements, but we will focus on the most basic: projective measurements on single qubits.</span></span>
<span data-ttu-id="49a8c-248">Belirli bir temelde ölçülerek (örn. hesaplama tabanlı $ \{ \demet {0} , \demet {1} \} $), qubit durumu, bu nedenle ikisi arasındaki herhangi bir üst konuma yok edilirken, her bir temel duruma göre yansıtılmıştır---.</span><span class="sxs-lookup"><span data-stu-id="49a8c-248">Upon measurement in a given basis (e.g. the computational basis $ \{ \ket{0}, \ket{1} \} $), the qubit state is projected onto whichever basis state was measured---hence destroying any superposition between the two.</span></span>

<span data-ttu-id="49a8c-249">Bir program içindeki ölçümleri uygulamak için, Q# `M` `Microsoft.Quantum.Intrinsic` bir türü döndüren (from) işlemini kullanırız `Result` .</span><span class="sxs-lookup"><span data-stu-id="49a8c-249">To implement measurements within a Q# program, we use the `M` operation (from `Microsoft.Quantum.Intrinsic`), which returns a `Result` type.</span></span>

<span data-ttu-id="49a8c-250">İlk olarak, `Perform3QubitQFT` işlem yerine, ölçüm sonuçlarının bir dizisini döndürecek şekilde değişiklik yaptık `Result[]` `Unit` .</span><span class="sxs-lookup"><span data-stu-id="49a8c-250">First, we modify our `Perform3QubitQFT` operation to return an array of measurement results, `Result[]`, instead of `Unit`.</span></span>

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a><span data-ttu-id="49a8c-251">Diziyi tanımlama ve başlatma `Result[]`</span><span class="sxs-lookup"><span data-stu-id="49a8c-251">Define and initialize `Result[]` array</span></span>

<span data-ttu-id="49a8c-252">Qubits (yani, `using` deyimden önce) ayırmadan önce bu length 3 diziyi (her bir qubit için bir tane) bildiririz ve bağladık `Result` :</span><span class="sxs-lookup"><span data-stu-id="49a8c-252">Before even allocating qubits (i.e. before the `using` statement), we declare and bind this length-3 array (one `Result` for each qubit):</span></span> 

```qsharp
        mutable resultArray = new Result[3];
```

<span data-ttu-id="49a8c-253">Kullanım `mutable` öncesi anahtar sözcüğü, `resultArray` değişkenin kod içinde daha sonra yeniden bağlanmasını sağlar---örneğin ölçüm sonuçlarımızı eklerken.</span><span class="sxs-lookup"><span data-stu-id="49a8c-253">The `mutable` keyword prefacing `resultArray` allows the variable to be rebound later in the code---for example, when adding our measurement results.</span></span>

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a><span data-ttu-id="49a8c-254">Ölçümleri bir döngüde gerçekleştirin `for` ve sonuçları diziye ekleyin</span><span class="sxs-lookup"><span data-stu-id="49a8c-254">Perform measurements in a `for` loop and add results to array</span></span>

<span data-ttu-id="49a8c-255">Blok içindeki Fourier dönüştürme işlemlerinden sonra `using` aşağıdaki kodu ekleyin:</span><span class="sxs-lookup"><span data-stu-id="49a8c-255">After the Fourier transform operations inside the `using` block, insert the following code:</span></span>

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
<span data-ttu-id="49a8c-256">[`IndexRange`](xref:microsoft.quantum.arrays.indexrange)Bir dizide çağrılan işlev (örn. qubits dizimiz `qs` ) dizinin dizinlerinin üzerinde bir Aralık döndürür.</span><span class="sxs-lookup"><span data-stu-id="49a8c-256">The [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) function called on an array (e.g. our array of qubits, `qs`) returns a range over the indices of the array.</span></span> <span data-ttu-id="49a8c-257">Burada, `for` ifadesini kullanarak her bir qubit 'i sırayla ölçmek için döngüümüzde kullanırız `M(qs[i])` .</span><span class="sxs-lookup"><span data-stu-id="49a8c-257">Here, we use it in our `for` loop to sequentially measure each qubit using the `M(qs[i])` statement.</span></span>
<span data-ttu-id="49a8c-258">Her ölçülen `Result` tür ( `Zero` ya da `One` ), `resultArray` bir Update ve-yeniden atama ifadesiyle ilgili dizin konumuna eklenir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-258">Each measured `Result` type (either `Zero` or `One`) is then added to the corresponding index position in `resultArray` with an update-and-reassign statement.</span></span>

> [!NOTE]
> <span data-ttu-id="49a8c-259">Bu deyimin sözdizimi, için benzersizdir Q# , ancak `resultArray[i] <- M(qs[i])` F # ve R gibi diğer dillerde görülen benzer değişken yeniden atamaya karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-259">The syntax of this statement is unique to Q#, but corresponds to the similar variable reassignment `resultArray[i] <- M(qs[i])` seen in other languages such as F# and R.</span></span>

<span data-ttu-id="49a8c-260">Anahtar sözcüğü, `set` kullanarak değişkenlerin bağlanmasını yeniden atamak için her zaman kullanılır `mutable` .</span><span class="sxs-lookup"><span data-stu-id="49a8c-260">The keyword `set` is always used to reassign variables bound using `mutable`.</span></span>

#### <a name="return-resultarray"></a><span data-ttu-id="49a8c-261">Döndürülmesini `resultArray`</span><span class="sxs-lookup"><span data-stu-id="49a8c-261">Return `resultArray`</span></span>

<span data-ttu-id="49a8c-262">Üç qubit ölçülmüş ve sonuçları öğesine eklendiğinde `resultArray` , qubits 'i daha önce sıfırlamak ve serbest bırakmak güvenlidir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-262">With all three qubits measured and the results added to `resultArray`, we are safe to reset and deallocate the qubits as before.</span></span>
<span data-ttu-id="49a8c-263">Blok kapatıldıktan sonra `using` Ekle</span><span class="sxs-lookup"><span data-stu-id="49a8c-263">After the `using` block's close, insert</span></span>

```qsharp
        return resultArray;
```
<span data-ttu-id="49a8c-264">son olarak, işlem çıktısını geri döndürür.</span><span class="sxs-lookup"><span data-stu-id="49a8c-264">to ultimately return the output of our operation.</span></span> 

### <a name="understanding-the-effects-of-measurement"></a><span data-ttu-id="49a8c-265">Ölçümün etkilerini anlama</span><span class="sxs-lookup"><span data-stu-id="49a8c-265">Understanding the effects of measurement</span></span>

<span data-ttu-id="49a8c-266">`DumpMachine`Ölçümlere daha önce ve sonra durum çıkarmak için işlevlerimizin yerleşimini değiştirelim.</span><span class="sxs-lookup"><span data-stu-id="49a8c-266">Let's change the placement of our `DumpMachine` functions to output the state before and after the measurements.</span></span>
<span data-ttu-id="49a8c-267">Son işlem kodu şöyle görünmelidir:</span><span class="sxs-lookup"><span data-stu-id="49a8c-267">The final operation code should look like:</span></span> 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

<span data-ttu-id="49a8c-268">Komut isteminden çalışıyorsanız, döndürülen dizi yalnızca, çalıştırma sonunda konsola doğrudan görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-268">If you are working from the command prompt, the returned array will simply be displayed directly to the console at the end of the run.</span></span>
<span data-ttu-id="49a8c-269">Aksi takdirde, döndürülen diziyi işlemek için ana bilgisayar programınızı güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="49a8c-269">Otherwise, update your host program to process the returned array.</span></span>

#### <a name="command-prompt"></a>[<span data-ttu-id="49a8c-270">Komut istemi</span><span class="sxs-lookup"><span data-stu-id="49a8c-270">Command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="49a8c-271">Konsolda yazdırılacak döndürülen diziyi daha fazla anlamak için, `Message` Q# yalnızca deyimden hemen önce dosyaya bir tane ekleyebiliriz `return` :</span><span class="sxs-lookup"><span data-stu-id="49a8c-271">To have more understanding of the returned array which will be printed in the console, we can add another `Message` in the Q# file just before the `return` statement:</span></span>

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

<span data-ttu-id="49a8c-272">Projeyi çalıştırın ve çıktımızda aşağıdakine benzer görünmelidir:</span><span class="sxs-lookup"><span data-stu-id="49a8c-272">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[<span data-ttu-id="49a8c-273">Python</span><span class="sxs-lookup"><span data-stu-id="49a8c-273">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="49a8c-274">Python programınızı şu şekilde güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="49a8c-274">Update your Python program to the following:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

<span data-ttu-id="49a8c-275">Dosyasını çalıştırın ve çıktlarınızın aşağıdakine benzer olması gerekir:</span><span class="sxs-lookup"><span data-stu-id="49a8c-275">Run the file, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[<span data-ttu-id="49a8c-276">C#</span><span class="sxs-lookup"><span data-stu-id="49a8c-276">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="49a8c-277">İşlem bir sonuç döndürdüğünü artık, özelliği getirilirken yöntem çağrısını değiştirin `Wait()` `Result` .</span><span class="sxs-lookup"><span data-stu-id="49a8c-277">Now that our operation is returning a result, replace the method call `Wait()` with fetching the `Result` property.</span></span> <span data-ttu-id="49a8c-278">Bu, daha önce bahsedilen aynı eşitlemeyi yine de gerçekleştirir ve bu değeri doğrudan değişkene bağlayabiliriz `measurementResult` .</span><span class="sxs-lookup"><span data-stu-id="49a8c-278">This still accomplishes the same synchronicity discussed earlier, and we can directly bind this value to the variable `measurementResult`.</span></span>

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="49a8c-279">Projeyi çalıştırın ve çıktımızda aşağıdakine benzer görünmelidir:</span><span class="sxs-lookup"><span data-stu-id="49a8c-279">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

<span data-ttu-id="49a8c-280">Bu çıktı birkaç farklı şeyi gösterir:</span><span class="sxs-lookup"><span data-stu-id="49a8c-280">This output illustrates a few different things:</span></span>
1. <span data-ttu-id="49a8c-281">Döndürülen sonucu ön ölçüyle karşılaştıran `DumpMachine` , bu durum, temel olarak son _not_ olarak QFT üst konumunu göstermez.</span><span class="sxs-lookup"><span data-stu-id="49a8c-281">Comparing the returned result to the pre-measurement `DumpMachine`, it clearly does _not_ illustrate the post-QFT superposition over basis states.</span></span>
    <span data-ttu-id="49a8c-282">Ölçüm, sistemin dalga işlevindeki bu durumun genliğini tespit eden bir olasılık ile yalnızca tek bir temel durum döndürür.</span><span class="sxs-lookup"><span data-stu-id="49a8c-282">A measurement only returns a single basis state, with a probability determined by the amplitude of that state in the system's wavefunction.</span></span>
2. <span data-ttu-id="49a8c-283">Ölçüm sonrası `DumpMachine` , ölçümün durumunun kendisini _değiştirmekte_ olduğunu görüyoruz ve bu ölçüyü, ilk üst konumdan temel durumlar üzerinden, ölçülen değere karşılık gelen tek başına duruma yansıdık.</span><span class="sxs-lookup"><span data-stu-id="49a8c-283">From the post-measurement `DumpMachine`, we see that measurement _changes_ the state itself, projecting it from the initial superposition over basis states to the single basis state that corresponds to the measured value.</span></span>

<span data-ttu-id="49a8c-284">Bu işlemi birçok kez tekrarlıyoruz, sonuç istatistiklerinin, her bir görüntüsündeki rastgele sonuca artmaya yönelik QFT durumunun eşit ağırlıklı konumunu göstermeye başladığımızda görüyoruz.</span><span class="sxs-lookup"><span data-stu-id="49a8c-284">If we were to repeat this operation many times, we would see the result statistics begin to illustrate the equally weighted superposition of the post-QFT state that gives rise to a random result on each shot.</span></span>
<span data-ttu-id="49a8c-285">_Ancak_, verimsiz olmasının yanı sıra yine de, bu, aralarındaki göreli aşamalara göre değil, yalnızca temel durumların göreli bir şekilde yeniden oluşturulmasını ister.</span><span class="sxs-lookup"><span data-stu-id="49a8c-285">_However_, besides being inefficient and still imperfect, this would nevertheless only reproduce the relative amplitudes of the basis states, not the relative phases between them.</span></span>
<span data-ttu-id="49a8c-286">İkincisi bu örnekteki bir sorun değildir, ancak QFT 'ye $ \ket $ ' den daha karmaşık bir giriş verildiyse, göreli aşamalar görüneceğiz {000} .</span><span class="sxs-lookup"><span data-stu-id="49a8c-286">The latter is not an issue in this example, but we would see relative phases appear if given a more complex input to the QFT than $\ket{000}$.</span></span>

#### <a name="partial-measurements"></a><span data-ttu-id="49a8c-287">Kısmi ölçümler</span><span class="sxs-lookup"><span data-stu-id="49a8c-287">Partial measurements</span></span> 
<span data-ttu-id="49a8c-288">Kaydın yalnızca bazı qubits 'in sistem durumunu nasıl etkileyebileceğini öğrenmek için, `for` ölçüm satırından sonra, döngünün içine aşağıdakileri eklemeyi deneyin:</span><span class="sxs-lookup"><span data-stu-id="49a8c-288">To explore how measuring only some qubits of the register can affect the system's state, try adding the following inside the `for` loop, after the measurement line:</span></span>
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

<span data-ttu-id="49a8c-289">Eklemeniz gereken işleve erişmek için `IntAsString`</span><span class="sxs-lookup"><span data-stu-id="49a8c-289">Note that to access the `IntAsString` function you will have to add</span></span> 
```qsharp
    open Microsoft.Quantum.Convert;
```
<span data-ttu-id="49a8c-290">diğer ad alanı `open` deyimleriyle.</span><span class="sxs-lookup"><span data-stu-id="49a8c-290">with the rest of the namespace `open` statements.</span></span>

<span data-ttu-id="49a8c-291">Sonuçta elde edilen çıktıda, her bir qubit ölçülerek dereceli projeksiyonları alt boşluklara görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="49a8c-291">In the resulting output, you will see the gradual projection into subspaces as each qubit is measured.</span></span>


## <a name="use-the-no-locq-libraries"></a><span data-ttu-id="49a8c-292">Kitaplıkları kullanma Q#</span><span class="sxs-lookup"><span data-stu-id="49a8c-292">Use the Q# libraries</span></span>
<span data-ttu-id="49a8c-293">Giriş bölümünde bahsedildiği gibi, dünyanın çoğu, Q# bireysel qubits ile ilgilenme dünyadan yararlanın.</span><span class="sxs-lookup"><span data-stu-id="49a8c-293">As we mentioned in the introduction, much of Q#'s power rests in the fact that it allows you to abstract-away the worries of dealing with individual qubits.</span></span>
<span data-ttu-id="49a8c-294">Gerçekten de, tam ölçekli, uygun hisse programları geliştirmek istiyorsanız, `H` belirli bir dönüşten önce veya sonra bir işlemin, yalnızca sizi yavaşlatıp yavaşlamadığını endişelenmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-294">Indeed, if you want to develop full-scale, applicable quantum programs, worrying about whether an `H` operation goes before or after a particular rotation would only slow you down.</span></span> 

<span data-ttu-id="49a8c-295">Q#Kitaplıklar, herhangi bir sayıda qubit için uygulayabileceğiniz ve uygulayabileceğiniz [QFT](xref:microsoft.quantum.canon.qft) işlemini içerir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-295">The Q# libraries contain the [QFT](xref:microsoft.quantum.canon.qft) operation, which you can simply take and apply for any number of qubits.</span></span>
<span data-ttu-id="49a8c-296">Denemek için, Q# dosyanızda aynı içeriğe sahip olan `Perform3QubitQFT` , ancak ilk `H` `SWAP` yerine iki kolay satıra sahip olan her şeyi içeren yeni bir işlem tanımlayın:</span><span class="sxs-lookup"><span data-stu-id="49a8c-296">To give it a try, define a new operation in your Q# file which has the same contents of `Perform3QubitQFT`, but with everything from the first `H` to the `SWAP` replaced by two easy lines:</span></span>
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
<span data-ttu-id="49a8c-297">İlk satır yalnızca, [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) `qs` [QFT](xref:microsoft.quantum.canon.qft) işleminin bağımsız değişken olarak aldığı bir qubit dizisinin ayrılmış dizisinin bir ifadesini oluşturur.</span><span class="sxs-lookup"><span data-stu-id="49a8c-297">The first line simply creates a [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) expression of the allocated array of qubits, `qs`, which is what the [QFT](xref:microsoft.quantum.canon.qft) operation takes as an argument.</span></span>
<span data-ttu-id="49a8c-298">Bu, kayıttaki qubits 'in Dizin sıralamasına karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="49a8c-298">This corresponds to index ordering of the qubits in the register.</span></span>

<span data-ttu-id="49a8c-299">Bu işlemlere erişebilmek için, `open` dosyanın başlangıcında ilgili ad alanları için deyimler ekleyin Q# :</span><span class="sxs-lookup"><span data-stu-id="49a8c-299">To have access to these operations, add `open` statements for their respective namespaces at the beginning of the Q# file:</span></span>
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

<span data-ttu-id="49a8c-300">Şimdi, ana bilgisayar programınızı yeni işleminizi (ör.) çağırmak için ayarlayın `PerformIntrinsicQFT` ve bir yanıt verin.</span><span class="sxs-lookup"><span data-stu-id="49a8c-300">Now, adjust your host program to call the name of your new operation (e.g. `PerformIntrinsicQFT`), and give it a whirl.</span></span>

<span data-ttu-id="49a8c-301">Kitaplık işlemlerini kullanmanın gerçek avantajını görmek için Q# qubits sayısını şundan farklı bir şekilde değiştirin `3` :</span><span class="sxs-lookup"><span data-stu-id="49a8c-301">To see the real benefit of using the Q# library operations, change the number of qubits to something other than `3`:</span></span>
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
<span data-ttu-id="49a8c-302">Bu nedenle, `H` her bir qubit üzerinde yeni işlemler ve döndürmeler hakkında endişelenmenize gerek kalmadan, belirli sayıda qubit için uygun QFT 'leri uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="49a8c-302">You can thus apply the proper QFT for any given number of qubits, without having to worry about the mess of new `H` operations and rotations on each qubit.</span></span>

<span data-ttu-id="49a8c-303">Hisse senedi simülatörü, gerçek hisse donanımı için neden ilerletireceğiz kesin olarak---, tam olarak çalışır şekilde daha fazla zaman kaplar!</span><span class="sxs-lookup"><span data-stu-id="49a8c-303">Note that the quantum simulator takes exponentially more time to run as you increase the number of qubits---precisely why we look forward to real quantum hardware!</span></span>













