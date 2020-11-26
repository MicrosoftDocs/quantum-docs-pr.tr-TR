---
title: Soru-cevap
description: 'Soru-cevap programlarına hızlı giriş #'
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234320"
---
# <a name="q-quantum-programming-language"></a><span data-ttu-id="39bba-103">Q # hisse programlama dili</span><span class="sxs-lookup"><span data-stu-id="39bba-103">Q# Quantum Programming Language</span></span>

<span data-ttu-id="39bba-104">Q # programlama dili hakkında bilmeniz gereken her şey, [q # dil kılavuzunda](xref:microsoft.quantum.qsharp.index)ayrıntılı olarak açıklanmıştır.</span><span class="sxs-lookup"><span data-stu-id="39bba-104">Everything you need to know about the Q# programming language is detailed in the [Q# language guide](xref:microsoft.quantum.qsharp.index).</span></span> <span data-ttu-id="39bba-105">Diğer her şey gibi, [dil tasarım sürecimiz](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) açık kaynak ve hoş geldiniz katkılarımız olur.</span><span class="sxs-lookup"><span data-stu-id="39bba-105">Like anything else, our [language design process](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) is open source and we welcome contributions.</span></span>
<span data-ttu-id="39bba-106">Q # ' dan sonra kuruluş ve mosyon hakkında daha fazla arka plan için bkz. [neden soru-cevap veriyoruz?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span><span class="sxs-lookup"><span data-stu-id="39bba-106">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>  
<span data-ttu-id="39bba-107">S # hızlı bir genel bakış Için hisse geliştirme setinin (QDK) bir parçası olarak gönderilir, [QDK nedir?](xref:microsoft.quantum.overview.q-sharp)konusuna bakın.</span><span class="sxs-lookup"><span data-stu-id="39bba-107">Q# is shipped as part of the Quantum Development Kit (QDK) For a quick overview, check out [What is the QDK?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="39bba-108">Hisse bir program nedir?</span><span class="sxs-lookup"><span data-stu-id="39bba-108">What is a quantum program?</span></span>

<span data-ttu-id="39bba-109">Bir hisse bir program, çağrıldığında bir hisse sistemi ile etkileşimde bulunarak bir hesaplama gerçekleştirirken, belirli bir klasik alt yordamlar kümesi olarak görülebilir; Q # dilinde yazılmış bir program hisse durumunu doğrudan modellemez, bunun yerine bir klasik denetim bilgisayarının qubits ile nasıl etkileşime gireceğini açıklar.</span><span class="sxs-lookup"><span data-stu-id="39bba-109">A quantum program can be seen as a particular set of classical subroutines which, when called, perform a computation by interacting with a quantum system; a program written in Q# does not directly model the quantum state, but rather describes how a classical control computer interacts with qubits.</span></span>
<span data-ttu-id="39bba-110">Bu, makineye bağlı farklı yorumlamalar olabilecek her bir hedef makinede bile her bir hisse alım durumunun büyük bir yerde *olduğu* konusunda tamamen belirsiz bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="39bba-110">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="39bba-111">Bunun önemli bir sonucu olarak, Q # ' ın bir qubit ya da başka bir hisse ve diğer özellikleri için introspect, bir Q # programının fiziksel bir bilgisayar üzerinde fiziksel olarak yürütülüp yürütülmemesini güvence altına alma yeteneği yoktur.</span><span class="sxs-lookup"><span data-stu-id="39bba-111">An important consequence of that is that Q# has no ability to introspect into the state of a qubit or other properties of quantum mechanics directly, which guarantees that a Q# program can be physically executed on a quantum computer.</span></span>
<span data-ttu-id="39bba-112">Bunun yerine, bir program, [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) bir qubit 'den klasik bilgileri ayıklamak gibi işlemleri çağırabilir.</span><span class="sxs-lookup"><span data-stu-id="39bba-112">Instead, a program can call operations such as [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) to extract classical information from a qubit.</span></span>

<span data-ttu-id="39bba-113">Ayrıldıktan sonra, *callables* olarak da adlandırılan işlemlere ve işlevlere qubit iletilebilir.</span><span class="sxs-lookup"><span data-stu-id="39bba-113">Once allocated, a qubit can be passed to operations and functions, also referred to as *callables*.</span></span> <span data-ttu-id="39bba-114">Bazı anlamda, bir Q # programının bir qubit ile yapamalarıdır. Bir qubit durumu üzerinde herhangi bir doğrudan eylem, ve gibi *iç* callables tarafından tanımlanır, [`X`](xref:Microsoft.Quantum.Intrinsic.X) [`H`](xref:Microsoft.Quantum.Intrinsic.H) ancak uygulamaları Q # içinde tanımlanmamıştır ancak hedef makine tarafından tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="39bba-114">In some sense, this is all that a Q# program can do with a qubit; Any direct actions on state of a qubit are all defined by *intrinsic* callables such as [`X`](xref:Microsoft.Quantum.Intrinsic.X) and [`H`](xref:Microsoft.Quantum.Intrinsic.H) - i.e. callables whose implementations are not defined within Q# but are instead defined by the target machine.</span></span> <span data-ttu-id="39bba-115">Bu *işlemlerin gerçekten ne* olduğunu yalnızca belirli bir Q # programını çalıştırmak için kullandığımız hedef makine tarafından somut hale getirilir.</span><span class="sxs-lookup"><span data-stu-id="39bba-115">What these operations actually *do* is only made concrete by the target machine we use to run the particular Q# program.</span></span>

<span data-ttu-id="39bba-116">Örneğin, programı [tam durum benzeticimizde](xref:microsoft.quantum.machines.full-state-simulator)çalıştırırsanız simülatör, sanal hisse sisteme karşılık gelen matematiksel işlemleri gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="39bba-116">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="39bba-117">Ancak geleceğe bakıyorum, hedef makine gerçek bir hisse bilgisayar olduğunda, Q # ' da bu gibi işlemleri çağırmak, hisse bilgisayarını *Gerçek* hisse sisteminde ilgili *gerçek* işlemleri gerçekleştirmeye yönlendirir (örneğin, tam olarak süreli lazer pulu).</span><span class="sxs-lookup"><span data-stu-id="39bba-117">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# will direct the quantum computer to perform the corresponding *real* operations on the *real* quantum system (e.g. precisely timed laser pulses).</span></span>

<span data-ttu-id="39bba-118">Bir Q # programı, Express hisse hesaplamasına yeni ve daha üst düzey işlemler oluşturmak için bu işlemleri bir hedef makine tarafından tanımlanan şekilde yeniden birleştirir.</span><span class="sxs-lookup"><span data-stu-id="39bba-118">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="39bba-119">Bu şekilde, Q #, temel alınan hisse ve hibrit, klasik algoritmaların yanı sıra bir hedef makine ya da simülatör yapısına göre genel de olacak şekilde ifade yapmayı kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="39bba-119">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

<span data-ttu-id="39bba-120">Basit bir örnek aşağıdaki programdır ve $ \ket $ durumunda bir qubit ayırır {0} , ardından buna bir Hadamard işlemi uygular `H` ve sonucu `PauliZ` temelde ölçer.</span><span class="sxs-lookup"><span data-stu-id="39bba-120">A simple example is the following program, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
@EntryPoint()
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

<span data-ttu-id="39bba-121">[Hisse kamız](https://github.com/microsoft/QuantumKatas#introduction) , genel hisse alma işlemleri ve qubits 'in nasıl kullanılacağı gibi [hisse bilgi işlem kavramları](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) hakkında iyi bir giriş sağlar.</span><span class="sxs-lookup"><span data-stu-id="39bba-121">Our [Quantum Katas](https://github.com/microsoft/QuantumKatas#introduction) give a good introduction on [Quantum Computing Concepts](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) such as common quantum operations and how to manipulate qubits.</span></span> <span data-ttu-id="39bba-122">Ayrıca, [Iç işlemlerde ve işlevlerde](xref:microsoft.quantum.libraries.standard.prelude)daha fazla örnek bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="39bba-122">More examples can also be found in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span>



