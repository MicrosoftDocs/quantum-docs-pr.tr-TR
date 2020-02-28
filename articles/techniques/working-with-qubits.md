---
title: Qubits ile çalışma
description: Qubit ayırmayı öğrenin, bunları işlemler ve işlevlerde kullanın ve sonuçları ölçün.
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: 1aa2432996dda61d099e3b5bb4db78379ce43d97
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907656"
---
# <a name="working-with-qubits"></a><span data-ttu-id="c4893-103">Qubits ile çalışma</span><span class="sxs-lookup"><span data-stu-id="c4893-103">Working with Qubits</span></span>

<span data-ttu-id="c4893-104">Artık, Q # dilinin çeşitli farklı parçalarını gördüğünüze göre, bunun kalın olmasını sağlamamıza ve qubits 'in kendisini nasıl kullanacağınızı görelim.</span><span class="sxs-lookup"><span data-stu-id="c4893-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="c4893-105">Qubit ayırma</span><span class="sxs-lookup"><span data-stu-id="c4893-105">Allocating Qubits</span></span>

<span data-ttu-id="c4893-106">İlk olarak, Q # ' da kullanabilmemiz için bir qubit elde etmek üzere `using` bloğu içinde qubit *ayırdık* :</span><span class="sxs-lookup"><span data-stu-id="c4893-106">First, to obtain a qubit that we can use in Q#, we *allocate* qubits within a `using` block:</span></span>

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

<span data-ttu-id="c4893-107">Bu şekilde ayrılan her türlü qubit $ \ket{0}$ State; Yukarıdaki örnekte `register`, bu durumda $ \demet{00000} = \ayraç{0} \otimes \tus{0} \otimes \cnoktalar \otimes \tus{0}$ şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="c4893-107">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="c4893-108">`using` bloğunun sonunda, bu blok tarafından ayrılan tüm qubitleri hemen serbest bırakılır ve daha fazla kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="c4893-108">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="c4893-109">Hedef makineler, daha sonra yeniden kullanılabilmesi ve ayrılmak üzere diğer `using` bloklara sunulabilmeleri için, qubits 'in $ \ket{0}$ durumunda olmasını bekler.</span><span class="sxs-lookup"><span data-stu-id="c4893-109">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="c4893-110">Mümkün olduğunda, tüm ayrılmış qubitleri $ \ket{0}$ ' e döndürmek için Unitary işlemlerini kullanın.</span><span class="sxs-lookup"><span data-stu-id="c4893-110">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="c4893-111">Gerekirse, @"microsoft.quantum.intrinsic.reset" işlemi bir qubit ' i ölçmek için ve bu ölçüm sonucunu kullanarak ölçülen qubitin $ \tus{0}$ ' e döndürüldüğünden emin olmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="c4893-111">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="c4893-112">Bu tür bir ölçü, kalan qubits ile herhangi bir entanglement 'i yok eder ve bu sayede hesaplamayı etkileyebilir.</span><span class="sxs-lookup"><span data-stu-id="c4893-112">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="c4893-113">İç Işlemler</span><span class="sxs-lookup"><span data-stu-id="c4893-113">Intrinsic Operations</span></span>

<span data-ttu-id="c4893-114">Ayrıldıktan sonra, bir qubit daha sonra işlevlere ve işlemlere geçirilebilirler.</span><span class="sxs-lookup"><span data-stu-id="c4893-114">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="c4893-115">Bazı bir deyişle, bu, bir Q # programının bir qubit ile yapamalarıdır, ancak gerçekleştirilebilecek eylemler tüm işlemler olarak tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="c4893-115">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="c4893-116">Bu işlemleri, [Iç işlemler ve işlevlerde](xref:microsoft.quantum.libraries.standard.prelude)daha ayrıntılı bir şekilde görebiliyoruz, ancak şimdilik, qubits ile etkileşim kurmak için kullanılabilecek birkaç faydalı işlemden bahsedin.</span><span class="sxs-lookup"><span data-stu-id="c4893-116">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="c4893-117">İlk olarak, tek qubit Pauli Operators $X $, $Y $ ve $Z $, her birinin türü `Y`olan iç işlemler `X`, `Z`ve `(Qubit => Unit is Adj + Ctl)`tarafından Q # içinde temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="c4893-117">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="c4893-118">[Iç işlemler ve işlevler](xref:microsoft.quantum.libraries.standard.prelude)bölümünde açıklandığı gibi, $X $ ve bu nedenle `X` bir bit çevirme işlemi olarak veya ağ geçidi olmayan bir işlem olarak düşünebiliriz.</span><span class="sxs-lookup"><span data-stu-id="c4893-118">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="c4893-119">`X` işlemi, bazı klasik bit dizeler için $ \ket{s_0 s_1 \noktalara s_n} $ biçimindeki durumları hazırlanmamızı sağlar $s $:</span><span class="sxs-lookup"><span data-stu-id="c4893-119">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

```qsharp
operation PrepareBitString(bitstring : Bool[], register : Qubit[]) : Unit
is Adj + Ctl {
    let nQubits = Length(register);
    for (idxQubit in 0..nQubits - 1) {
        if (bitstring[idxQubit]) {
            X(register[idxQubit]);
        }
    }
}

operation RunExample() : Unit {
    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
        // Resetting the qubits will allow us to deallocate them properly.
        ResetAll(register);
    }
}
```

> [!TIP]
> <span data-ttu-id="c4893-120">Daha sonra, bu işlemi yazmak için el ile akış denetimi gerektirmeyen daha kompakt yollar görüyoruz.</span><span class="sxs-lookup"><span data-stu-id="c4893-120">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="c4893-121">Ayrıca, iç işlem{0} Q # içinde temsil edilen Hadamard Transform{1}$ ' i kullanarak $ \ket{+} = \left (\demet{0} + \tus{1}\right)/\sqrt{2}$ ve $ \tus{-} = \left (\ket{2}-\tus$H \right)/\sqrt `H : (Qubit => Unit is Adj + Ctl)`$ gibi durumları hazırlayabiliriz:</span><span class="sxs-lookup"><span data-stu-id="c4893-121">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString, above.
    PrepareBitString(bitstring, register);
    // Next, we use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the state we want.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a><span data-ttu-id="c4893-122">Ölçümler</span><span class="sxs-lookup"><span data-stu-id="c4893-122">Measurements</span></span>

<span data-ttu-id="c4893-123">Yerleşik bir içsel Unitary işlemi olan `Measure` işlemini kullanarak, `Qubit` türünde bir nesneden klasik bilgileri ayıklayabilir ve bir klasik değeri, ayrılmış bir tür `Result`olan sonuç olarak atayabiliriz ve bu da sonucun artık hisse amadığı anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="c4893-123">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="c4893-124">`Measure` girişi, Bloch Sphere üzerinde `Pauli` (örneğin `PauliX`) ve `Qubit`türünde bir değer ile temsil edilen Pauli eksenindedir.</span><span class="sxs-lookup"><span data-stu-id="c4893-124">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="c4893-125">Basit bir örnek, $ \demet{0}$ durumunda bir qubit ayıran aşağıdaki işlemdir ve sonra bu `H` bir Hadamard işlemi uygular ve sonucu `PauliZ` temelinde ölçer.</span><span class="sxs-lookup"><span data-stu-id="c4893-125">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

<span data-ttu-id="c4893-126">Aşağıdaki işlem tarafından biraz daha karmaşık bir örnek verilmiştir ve bu `Qubit[]` tür bir kayıttaki tüm qubits 'ler belirtilen bir Pauli tabanında ölçülerek sıfır durumunda ise ve bu, aksi halde `false` döndüren `true` Boole değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="c4893-126">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

```qsharp
operation MeasureIfAllQubitsAreZero(qubits : Qubit[], pauli : Pauli) : Bool {
    mutable value = true;
    for (qubit in qubits) {
        if (Measure([pauli], [qubit]) == One) {
            set value = false;
        }
    }
    return value;
}
```

<span data-ttu-id="c4893-127">Q # dili, mebitleri ölçmeye yönelik sonuçlara bağlı olarak klasik denetim akışına izin verir.</span><span class="sxs-lookup"><span data-stu-id="c4893-127">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="c4893-128">Bu özellik sırasıyla, birimlere uygulama için hesaplama maliyetini azaltabilecekleri güçlü dayalı araçları uygulamaya olanak tanıyor.</span><span class="sxs-lookup"><span data-stu-id="c4893-128">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="c4893-129">Örnek olarak, Q # içinde *Yinele-başarılı* (ru) desenleri uygulamak çok kolaydır.</span><span class="sxs-lookup"><span data-stu-id="c4893-129">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="c4893-130">Bu RUS desenleri, temel kapıların bakımından *beklenen* düşük maliyetli dayalı programlarıdır, ancak gerçek maliyetten gerçek bir çalıştırmaya ve çeşitli olası branchlerin gerçek bir aramasına bağlı olarak değişir.</span><span class="sxs-lookup"><span data-stu-id="c4893-130">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="c4893-131">Yinele-başarılı (RUS) desenleri kolaylaştırmak için, Q # yapıyı destekler</span><span class="sxs-lookup"><span data-stu-id="c4893-131">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the construct</span></span>

```qsharp
repeat {
    statementBlock1
}
until (expression)
fixup {
    statementBlock2
}
```

<span data-ttu-id="c4893-132">`statementBlock1` ve `statementBlock2` sıfır veya daha fazla Q # deyimi ve `Bool`türünde bir değer değerlendirilen herhangi bir geçerli ifade `expression`.</span><span class="sxs-lookup"><span data-stu-id="c4893-132">where `statementBlock1` and `statementBlock2` are zero or more Q# statements, and `expression` any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="c4893-133">Tipik bir kullanım durumunda, aşağıdaki Q # işlemi Bloch Sphere üzerinde $ (I + 2i Z)/\sqrt{5}$ bir ırrational Axis etrafında bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="c4893-133">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="c4893-134">Bu, bilinen bir RUS kalıbı kullanılarak gerçekleştirilir:</span><span class="sxs-lookup"><span data-stu-id="c4893-134">This is accomplished by using a known RUS pattern:</span></span>

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

<span data-ttu-id="c4893-135">Bu örnek, tüm yineleme-sonu-düzeltme döngüsü kapsamında olan ve düzeltme adımında yüklenmeden önce başlatılan bir kesilebilir değişken `finished` kullanımını gösterir.</span><span class="sxs-lookup"><span data-stu-id="c4893-135">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

<span data-ttu-id="c4893-136">Son olarak, $ \ket{+} $ durumundan başlayarak bir hisse durumu $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\tus{0}+ \tus{1}\right) $ ' ı hazırlamak için bir RUS deseninin örneğini gösteririz.</span><span class="sxs-lookup"><span data-stu-id="c4893-136">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="c4893-137">Ayrıca bkz. [Standart kitaplıkla birlikte sunulan birim testi örneği](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="c4893-137">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+⟩ state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+⟩ state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+⟩ state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+⟩ in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+⟩ state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

<span data-ttu-id="c4893-138">Bu işlemde gösterilen önemli programlı özellikler, bir döngünün daha karmaşık `fixup` bir parçasıdır. Bu, hisse kullanımı ve programda belirtilen belirli noktalarda hisse TI ölçme olasılığını belirlemek için `AssertProb` deyimlerinin kullanılmasını içerir.</span><span class="sxs-lookup"><span data-stu-id="c4893-138">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="c4893-139">Ayrıca, [`Assert`](xref:microsoft.quantum.intrinsic.assert) ve [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) işlemleri hakkında daha fazla bilgi için bkz. [test ve hata ayıklama](xref:microsoft.quantum.techniques.testing-and-debugging) .</span><span class="sxs-lookup"><span data-stu-id="c4893-139">See also [Testing and debugging](xref:microsoft.quantum.techniques.testing-and-debugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>
