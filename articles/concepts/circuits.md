---
title: Hisse devreleri
description: Hisse bağlantı diyagramlarında basit ve karmaşık hisse işlemlerini görsel olarak nasıl temsil ettiğini öğrenin.
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 745f0570bf62c5d98c2896cdc893ec385abd7115
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630401"
---
# <a name="quantum-circuits"></a><span data-ttu-id="fb51d-103">Hisse devreleri</span><span class="sxs-lookup"><span data-stu-id="fb51d-103">Quantum Circuits</span></span>
<span data-ttu-id="fb51d-104">Bir süre için Unitary dönüştürme $ \ metin { cnot} _ {01 } (H \otimes 1) $ değerini göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="fb51d-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="fb51d-105">Bu ağ geçidi sırası, en yüksek düzeyde bir entangled bit durumu oluşturduğundan, hisse bilgi işlem için temel öneme sahiptir:</span><span class="sxs-lookup"><span data-stu-id="fb51d-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="fb51d-106">$ $ \mathrm{CNOT}_{01 } (H \otimes 1) \ket{00 } = \frac{1 } {\sqrt{2 } } \left (\ket{00 } + \ket{11 } \ right), $ $</span><span class="sxs-lookup"><span data-stu-id="fb51d-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="fb51d-107">Bu ya da daha fazla karmaşıklığa sahip işlemler, hisse uygun bir şekilde bir hisse alım *Diyagramı*olarak adlandırılan görselleştirme için basit bir yöntem olduğundan harika bir sorun olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="fb51d-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="fb51d-108">Bu en yüksek düzeyde değerlendirme için devre diyagramı şu şekilde hazırlanıyor:</span><span class="sxs-lookup"><span data-stu-id="fb51d-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="fb51d-109">![En yüksek düzeyde bir entaninal iki-qubit durumu için devre diyagramı](~/media/1.svg)</span><span class="sxs-lookup"><span data-stu-id="fb51d-109">![Circuit diagram for a maximally entangled two-qubit state](~/media/1.svg)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="fb51d-110">Hisse devre diyagramı kuralları</span><span class="sxs-lookup"><span data-stu-id="fb51d-110">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="fb51d-111">Hisse için bu görsel dil, bir hisse devresini ifade eden kuralları anladıktan sonra eşdeğer matrisinin yazılmasından daha kolay digestible olabilir.</span><span class="sxs-lookup"><span data-stu-id="fb51d-111">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="fb51d-112">Aşağıda bu kuralları gözden geçiririz.</span><span class="sxs-lookup"><span data-stu-id="fb51d-112">We review these conventions below.</span></span>

<span data-ttu-id="fb51d-113">Devre diyagramında, her katı çizgi bir qubit veya daha fazla genel olarak bir qubit kaydı gösterir.</span><span class="sxs-lookup"><span data-stu-id="fb51d-113">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="fb51d-114">Kurala göre, üst çizgi qubit kayıt $0 ' dir $ ve geri kalan değerler sırayla etiketlenir.</span><span class="sxs-lookup"><span data-stu-id="fb51d-114">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="fb51d-115">Yukarıdaki örnek bağlantı hattı iki qubit üzerinde (veya bir qubitden oluşan equivalently iki kayıt) üzerinde işlem görecek şekilde gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="fb51d-115">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="fb51d-116">Bir veya daha fazla qubit kayıt üzerinde işlem gören kapıları kutu olarak gösterilir.</span><span class="sxs-lookup"><span data-stu-id="fb51d-116">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="fb51d-117">Örneğin, simge</span><span class="sxs-lookup"><span data-stu-id="fb51d-117">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="fb51d-118">![Tek qubit kayıt üzerinde işlem gören Hadamard işlemi sembolü](~/media/2.svg)</span><span class="sxs-lookup"><span data-stu-id="fb51d-118">![Symbol for a Hadamard operation acting on a single-qubit register](~/media/2.svg)</span></span>

<span data-ttu-id="fb51d-119">, tek qubit kayıt üzerinde işlem gören bir [Hadamard](xref:microsoft.quantum.intrinsic.h) işlemidir.</span><span class="sxs-lookup"><span data-stu-id="fb51d-119">is a [Hadamard](xref:microsoft.quantum.intrinsic.h) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="fb51d-120">Hisse kapıları, ilk olarak qubits 'e uygulanan kapıda en sol geçit ile kronolojik sırada sıralanır.</span><span class="sxs-lookup"><span data-stu-id="fb51d-120">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="fb51d-121">Diğer bir deyişle, kapıların hisse durumunu tutan şekilde fotoğrafını yaparsanız, kablolar diyagramdaki her bir kapıdan, soldan sağa doğru hisse ma durumunu getirir.</span><span class="sxs-lookup"><span data-stu-id="fb51d-121">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="fb51d-122">Yani</span><span class="sxs-lookup"><span data-stu-id="fb51d-122">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="fb51d-123">![Soldan sağa uygulanan hisse kapıları diyagramı](~/media/3.svg)</span><span class="sxs-lookup"><span data-stu-id="fb51d-123">![Diagram of quantum gates being applied left-to-right](~/media/3.svg)</span></span>

<span data-ttu-id="fb51d-124">Unitary matrisi $CBA $ .</span><span class="sxs-lookup"><span data-stu-id="fb51d-124">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="fb51d-125">Matris çarpıtına ters kural: en sağdaki matris önce uygulanır.</span><span class="sxs-lookup"><span data-stu-id="fb51d-125">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="fb51d-126">Ancak, bu arada en sol kapı, en sol kapı için uygulanır.</span><span class="sxs-lookup"><span data-stu-id="fb51d-126">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="fb51d-127">Bu fark, her zaman karışıklığa yol açabilir, bu nedenle doğrusal cebirsel gösterimi ve hisse senedi devre şemaları arasında önemli bir farklılık olduğunu fark etmek önemlidir.</span><span class="sxs-lookup"><span data-stu-id="fb51d-127">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="fb51d-128">Hisse devreleri giriş ve çıkışları</span><span class="sxs-lookup"><span data-stu-id="fb51d-128">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="fb51d-129">Verilen tüm önceki örneklerde, hisse kapıdan alınan kabloların sayısı kadar hisse kapıda aynı sayıda kablo (qubit) girişi gerekiyordu.</span><span class="sxs-lookup"><span data-stu-id="fb51d-129">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="fb51d-130">Bu ilk olarak, hisse devrelerin genel olarak girdilerden daha fazla veya daha az çıkış sahibi olabileceği makul görünebilir.</span><span class="sxs-lookup"><span data-stu-id="fb51d-130">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="fb51d-131">Ancak tüm hisse işlemleri, ölçümü Kaydet, Unitary ve bu nedenle ters çevrilebilir olduğundan bu olanaksızdır.</span><span class="sxs-lookup"><span data-stu-id="fb51d-131">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="fb51d-132">Girişlerle aynı sayıda çıkışı yoksa, geri alınamaz ve bu nedenle bir çelişki olan Unitary değildir.</span><span class="sxs-lookup"><span data-stu-id="fb51d-132">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="fb51d-133">Bu nedenle, bir devre diyagramında çizilen her kutu, tam olarak onunla aynı sayıda kabloda yer almalıdır.</span><span class="sxs-lookup"><span data-stu-id="fb51d-133">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="fb51d-134">Multi-qubit devre şemaları, tek qubit olanlara benzer kuralları izler.</span><span class="sxs-lookup"><span data-stu-id="fb51d-134">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="fb51d-135">Bir açıklığa kavuşturan örnek olarak, $ $ (H S X) $ olarak $B iki-qubit Unitary işlemi tanımlayabilir \otimes ve devre equivalently şu şekilde ifade edebilirsiniz</span><span class="sxs-lookup"><span data-stu-id="fb51d-135">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="fb51d-136">![İki-qubit Unitary işleminin devre diyagramı](~/media/4.svg)</span><span class="sxs-lookup"><span data-stu-id="fb51d-136">![Circuit diagram of a two-qubit unitary operation](~/media/4.svg)</span></span>

<span data-ttu-id="fb51d-137">$B, bağlantı hattının $ kullanıldığı içeriğe göre 2 1-qubit kayıt yerine tek bir iki-qubit kaydı üzerinde bir eyleme sahip olarak da görüntülenebilir.</span><span class="sxs-lookup"><span data-stu-id="fb51d-137">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="fb51d-138">Bu tür soyut devre diyagramlarından en yararlı özellik, karmaşık hisse algoritmalarının, bunları temel kapıları derlemek zorunda kalmadan yüksek düzeyde açıklanmasına izin vermesidir.</span><span class="sxs-lookup"><span data-stu-id="fb51d-138">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="fb51d-139">Bu, algoritmadaki her bir alt yordamların nasıl çalıştığı hakkında tüm ayrıntıları anlamak zorunda kalmadan, büyük bir hisse algoritması için veri akışı hakkında bir bilgi edinebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fb51d-139">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="fb51d-140">Denetlenen kapıları</span><span class="sxs-lookup"><span data-stu-id="fb51d-140">Controlled gates</span></span>
<span data-ttu-id="fb51d-141">Multi-qubit hisse devresini içinde yerleşik olan diğer yapı denetimdir.</span><span class="sxs-lookup"><span data-stu-id="fb51d-141">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="fb51d-142">Bir hisse listedir kontrollü kapı eylemi, belirtilen $ \Lambda (G) $, tek bir qubitin değerinin $G uygulamasını denetliyorsa $ , bir ürün durumu girişi $ \Lambda (G) (\Alpha \ket{0 } + \beta \ket{1 } ) { \tus\psı } = \Alpha \ket{0 } \tus\psı { } + \beta \ket{1 } G \ket { \ PSI } $ şeklinde aşağıdaki örneğe bakarak anlaşılabilirler.</span><span class="sxs-lookup"><span data-stu-id="fb51d-142">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="fb51d-143">Yani, denetlenen kapı $ $ \psı içeren kayda $G uygular $ ve yalnızca denetim qubit $1 değerini alırsa $ .</span><span class="sxs-lookup"><span data-stu-id="fb51d-143">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="fb51d-144">Genel olarak, bu tür denetimli işlemleri devre diyagramlarında</span><span class="sxs-lookup"><span data-stu-id="fb51d-144">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="fb51d-145">![Listedir denetimli bir ağ geçidinin devre diyagramı](~/media/5.svg)</span><span class="sxs-lookup"><span data-stu-id="fb51d-145">![Circuit diagram of a singly controlled gate](~/media/5.svg)</span></span>

<span data-ttu-id="fb51d-146">Burada siyah daire, kapıdan denetlediğiniz ve dikey bir tel, denetim qubit $1 değerini alırken uygulanan Unitary 'ı gösterir $ .</span><span class="sxs-lookup"><span data-stu-id="fb51d-146">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="fb51d-147">$G = X $ ve $G = Z olduğu özel durumlar için, $ kapıların denetlenen sürümünü (denetlenen-X kapısıdır [$CNOT $ kapısı](xref:microsoft.quantum.intrinsic.cnot)olduğunu unutmayın) aşağıdaki gösterimi tanıtıldık:</span><span class="sxs-lookup"><span data-stu-id="fb51d-147">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.intrinsic.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="fb51d-148">![Denetlenen kapıların özel durumları için devre diyagramı](~/media/6.svg)</span><span class="sxs-lookup"><span data-stu-id="fb51d-148">![Circuit diagram for special cases of controlled gates](~/media/6.svg)</span></span>

<span data-ttu-id="fb51d-149">Q #, bir işlemin denetlenen sürümünü otomatik olarak oluşturmak için yöntemler sağlar. Bu işlem, programcının bu işlemleri ele almak zorunda kalmadan kaydeder.</span><span class="sxs-lookup"><span data-stu-id="fb51d-149">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="fb51d-150">Buna bir örnek aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="fb51d-150">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="fb51d-151">Ölçüm işleci</span><span class="sxs-lookup"><span data-stu-id="fb51d-151">Measurement operator</span></span>
<span data-ttu-id="fb51d-152">Devre diyagramlarında görselleştirilecek kalan işlem ölçümdür.</span><span class="sxs-lookup"><span data-stu-id="fb51d-152">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="fb51d-153">Ölçüm bir qubit kaydı alır, bunu ölçer ve sonucu klasik bilgiler olarak verir.</span><span class="sxs-lookup"><span data-stu-id="fb51d-153">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="fb51d-154">Ölçüm bir işlem, ölçüm simgesiyle gösterilir ve her zaman bir qubit yazmaç girişi (katı bir satırla gösterilir) ve klasik bilgiler verir (bir Double satırıyla gösterilir).</span><span class="sxs-lookup"><span data-stu-id="fb51d-154">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="fb51d-155">Özellikle, bu tür bir alt devre şöyle görünür:</span><span class="sxs-lookup"><span data-stu-id="fb51d-155">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="fb51d-156">![Ölçüm işlemini temsil eden sembol](~/media/7.svg)</span><span class="sxs-lookup"><span data-stu-id="fb51d-156">![Symbol representing a measurement operation](~/media/7.svg)</span></span>

<span data-ttu-id="fb51d-157">Q # Bu amaçla bir [Ölçü işleci](xref:microsoft.quantum.intrinsic.measure) uygular.</span><span class="sxs-lookup"><span data-stu-id="fb51d-157">Q# implements a [Measure operator](xref:microsoft.quantum.intrinsic.measure) for this purpose.</span></span>
<span data-ttu-id="fb51d-158">Daha fazla bilgi için [ölçümlerle ilgili bölüme](xref:microsoft.quantum.libraries.standard.prelude#measurements) bakın.</span><span class="sxs-lookup"><span data-stu-id="fb51d-158">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="fb51d-159">Benzer şekilde, subdevı</span><span class="sxs-lookup"><span data-stu-id="fb51d-159">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="fb51d-160">![Denetlenen bir işlemi temsil eden devre diyagramı](~/media/8.svg)</span><span class="sxs-lookup"><span data-stu-id="fb51d-160">![Circuit diagram representing a controlled operation](~/media/8.svg)</span></span>

<span data-ttu-id="fb51d-161">$G, $ Klasik denetim bit $1 değeri olan ' de uygulandığı şekilde, sınıf denetimli bir geçit sağlar $ .</span><span class="sxs-lookup"><span data-stu-id="fb51d-161">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="fb51d-162">Teleporsyon devre diyagramı</span><span class="sxs-lookup"><span data-stu-id="fb51d-162">Teleportation circuit diagram</span></span>
<span data-ttu-id="fb51d-163">Hisse teleporsyon, bu bileşenleri göstermek için büyük olasılıkla en iyi hisse algoritmadır.</span><span class="sxs-lookup"><span data-stu-id="fb51d-163">Quantum teleportation is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="fb51d-164">Karşılık gelen [hisse küçon](xref:microsoft.quantum.overview.katas) ile uygulamalı teleporsyon, verileri bir hisse bir bilgisayar içinde (veya hatta bir hisse ağı içindeki uzak hisse bilgisayarları arasında), entanglement ve ölçüm kullanımıyla birlikte taşımaya yönelik bir yöntemdir.</span><span class="sxs-lookup"><span data-stu-id="fb51d-164">You can learn hands-on with the corresponding [Quantum Kata](xref:microsoft.quantum.overview.katas) Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="fb51d-165">Her ne kadar, bu, bir derece bitden diğerine, bir qubit 'in değerinin ne olduğunu bilmeksizin, belirli bir qubit içindeki değeri bir ile diğerine söylemeden, gerçekten de bir hisse cısına geçiş yeteneğine sahiptir!</span><span class="sxs-lookup"><span data-stu-id="fb51d-165">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="fb51d-166">Bu, protokol için hisse uzayı yasaları uyarınca çalışması için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="fb51d-166">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="fb51d-167">Hisse ve teleporsyon devresi aşağıda verilmiştir; Ayrıca, hisse öğesinin nasıl okunacağını göstermek için devresinin açıklamalı bir sürümünü sunuyoruz.</span><span class="sxs-lookup"><span data-stu-id="fb51d-167">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
<span data-ttu-id="fb51d-168">![Hisse ve teleporsyon devresi](~/media/tp2.svg)</span><span class="sxs-lookup"><span data-stu-id="fb51d-168">![Quantum teleportation circuit](~/media/tp2.svg)</span></span>
