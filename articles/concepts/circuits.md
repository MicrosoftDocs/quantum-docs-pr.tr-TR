---
title: Hisse devreleri | Microsoft Docs
description: Hisse devreleri
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7c2afa58fd70d893529cf794ae07df480466aaec
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73210735"
---
# <a name="quantum-circuits"></a><span data-ttu-id="67a72-103">Hisse devreleri</span><span class="sxs-lookup"><span data-stu-id="67a72-103">Quantum Circuits</span></span>
<span data-ttu-id="67a72-104">Şu anda Unitary dönüştürmesi $ \Text{CNOT} _{01}(H\otimes 1) $ ' i göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="67a72-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="67a72-105">Bu ağ geçidi sırası, en yüksek düzeyde bir entangled bit durumu oluşturduğundan, hisse bilgi işlem için temel öneme sahiptir:</span><span class="sxs-lookup"><span data-stu-id="67a72-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="67a72-106">$ $ \mathrm{CNOT}_{01}(H\otimes 1) \ayraç{00} = \frac{1}{\sqrt{2}} \left (\demet{00} + \ayraç{11} \right), $ $</span><span class="sxs-lookup"><span data-stu-id="67a72-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="67a72-107">Bu ya da daha fazla karmaşıklığa sahip işlemler, hisse uygun bir şekilde bir hisse alım *Diyagramı*olarak adlandırılan görselleştirme için basit bir yöntem olduğundan harika bir sorun olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="67a72-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="67a72-108">Bu en yüksek düzeyde değerlendirme için devre diyagramı şu şekilde hazırlanıyor:</span><span class="sxs-lookup"><span data-stu-id="67a72-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="67a72-109">Hisse devre diyagramı kuralları</span><span class="sxs-lookup"><span data-stu-id="67a72-109">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="67a72-110">Hisse için bu görsel dil, bir hisse devresini ifade eden kuralları anladıktan sonra eşdeğer matrisinin yazılmasından daha kolay digestible olabilir.</span><span class="sxs-lookup"><span data-stu-id="67a72-110">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="67a72-111">Aşağıda bu kuralları gözden geçiririz.</span><span class="sxs-lookup"><span data-stu-id="67a72-111">We review these conventions below.</span></span>

<span data-ttu-id="67a72-112">Devre diyagramında, her katı çizgi bir qubit veya daha fazla genel olarak bir qubit kaydı gösterir.</span><span class="sxs-lookup"><span data-stu-id="67a72-112">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="67a72-113">Kurala göre, üst çizgi qubit yazmaç $0 $ ' dir ve geri kalan değerler sırayla etiketlenir.</span><span class="sxs-lookup"><span data-stu-id="67a72-113">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="67a72-114">Yukarıdaki örnek bağlantı hattı iki qubit üzerinde (veya bir qubitden oluşan equivalently iki kayıt) üzerinde işlem görecek şekilde gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="67a72-114">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="67a72-115">Bir veya daha fazla qubit kayıt üzerinde işlem gören kapıları kutu olarak gösterilir.</span><span class="sxs-lookup"><span data-stu-id="67a72-115">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="67a72-116">Örneğin, simge</span><span class="sxs-lookup"><span data-stu-id="67a72-116">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_2.png)

<span data-ttu-id="67a72-117">, tek qubit kayıt üzerinde işlem gören [Hadamard](xref:microsoft.quantum.primitive.h) kapısıdır.</span><span class="sxs-lookup"><span data-stu-id="67a72-117">is the [Hadamard](xref:microsoft.quantum.primitive.h) gate acting on a single-qubit register.</span></span>

<span data-ttu-id="67a72-118">Hisse kapıları, ilk olarak qubits 'e uygulanan kapıda en sol geçit ile kronolojik sırada sıralanır.</span><span class="sxs-lookup"><span data-stu-id="67a72-118">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="67a72-119">Diğer bir deyişle, kapıların hisse durumunu tutan şekilde fotoğrafını yaparsanız, kablolar diyagramdaki her bir kapıdan, soldan sağa doğru hisse ma durumunu getirir.</span><span class="sxs-lookup"><span data-stu-id="67a72-119">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="67a72-120">Yani</span><span class="sxs-lookup"><span data-stu-id="67a72-120">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_3.png)

<span data-ttu-id="67a72-121">Unitary matris $CBA $ ' dir.</span><span class="sxs-lookup"><span data-stu-id="67a72-121">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="67a72-122">Matris çarpıtına ters kural: en sağdaki matris önce uygulanır.</span><span class="sxs-lookup"><span data-stu-id="67a72-122">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="67a72-123">Ancak, bu arada en sol kapı, en sol kapı için uygulanır.</span><span class="sxs-lookup"><span data-stu-id="67a72-123">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="67a72-124">Bu fark, her zaman karışıklığa yol açabilir, bu nedenle doğrusal cebirsel gösterimi ve hisse senedi devre şemaları arasında önemli bir farklılık olduğunu fark etmek önemlidir.</span><span class="sxs-lookup"><span data-stu-id="67a72-124">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="67a72-125">Hisse devreleri giriş ve çıkışları</span><span class="sxs-lookup"><span data-stu-id="67a72-125">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="67a72-126">Verilen tüm önceki örneklerde, hisse kapıdan alınan kabloların sayısı kadar hisse kapıda aynı sayıda kablo (qubit) girişi gerekiyordu.</span><span class="sxs-lookup"><span data-stu-id="67a72-126">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="67a72-127">Bu ilk olarak, hisse devrelerin genel olarak girdilerden daha fazla veya daha az çıkış sahibi olabileceği makul görünebilir.</span><span class="sxs-lookup"><span data-stu-id="67a72-127">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="67a72-128">Ancak tüm hisse işlemleri, ölçümü Kaydet, Unitary ve bu nedenle ters çevrilebilir olduğundan bu olanaksızdır.</span><span class="sxs-lookup"><span data-stu-id="67a72-128">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="67a72-129">Girişlerle aynı sayıda çıkışı yoksa, geri alınamaz ve bu nedenle bir çelişki olan Unitary değildir.</span><span class="sxs-lookup"><span data-stu-id="67a72-129">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="67a72-130">Bu nedenle, bir devre diyagramında çizilen her kutu, tam olarak onunla aynı sayıda kabloda yer almalıdır.</span><span class="sxs-lookup"><span data-stu-id="67a72-130">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="67a72-131">Multi-qubit devre şemaları, tek qubit olanlara benzer kuralları izler.</span><span class="sxs-lookup"><span data-stu-id="67a72-131">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="67a72-132">Bir açıklığa kavuşturan örnek olarak, $ (H \ saat X) $ $ $ $ (H \ saat X) $ $ $ (H \ saat X) $ olarak $B</span><span class="sxs-lookup"><span data-stu-id="67a72-132">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_4.png)

<span data-ttu-id="67a72-133">Ayrıca, devre dışı bırakıldığına bağlı olarak 2 1-qubit kayıtları yerine tek bir iki-qubit kayıt üzerinde eyleme sahip $B $ ' i de görüntüleyebiliriz.</span><span class="sxs-lookup"><span data-stu-id="67a72-133">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="67a72-134">Bu tür soyut devre diyagramlarından en yararlı özellik, karmaşık hisse algoritmalarının, bunları temel kapıları derlemek zorunda kalmadan yüksek düzeyde açıklanmasına izin vermesidir.</span><span class="sxs-lookup"><span data-stu-id="67a72-134">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="67a72-135">Bu, algoritmadaki her bir alt yordamların nasıl çalıştığı hakkında tüm ayrıntıları anlamak zorunda kalmadan, büyük bir hisse algoritması için veri akışı hakkında bir bilgi edinebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="67a72-135">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="67a72-136">Denetlenen kapıları</span><span class="sxs-lookup"><span data-stu-id="67a72-136">Controlled gates</span></span>
<span data-ttu-id="67a72-137">Multi-qubit hisse devresini içinde yerleşik olan diğer yapı denetimdir.</span><span class="sxs-lookup"><span data-stu-id="67a72-137">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="67a72-138">Tek bir qubitin değerinin $G $ uygulamasını denetlediğini, belirtilen bir listedir kontrollü kapı (G) $, bir ürün durumu girişi $ \Lambda (G) (\Alpha \demet{0} + \ Beta \ @no__t_ ayraç) örneğine bakarak anlaşılabildiği bir işlem. 1_) \ket{\psı} = \Alpha \demet{0} \ket{\psı} + \beta \ ayraç{1} G\tus{\ PSI} $.</span><span class="sxs-lookup"><span data-stu-id="67a72-138">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="67a72-139">Yani, denetlenen kapı $ \psı $ öğesini içeren Register 'a $G $, ancak yalnızca denetim qubit $1 $ değerini alırsa bu şekilde geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="67a72-139">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="67a72-140">Genel olarak, bu tür denetimli işlemleri devre diyagramlarında</span><span class="sxs-lookup"><span data-stu-id="67a72-140">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_5.png)

<span data-ttu-id="67a72-141">Burada siyah daire, kapıın kontrol edeceği hisse bitini ve bir dikey tel, denetim qubit $1 $ değerini alırken uygulanan Unitary 'ı gösterir.</span><span class="sxs-lookup"><span data-stu-id="67a72-141">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="67a72-142">$G = X $ ve $G = Z $ olan özel durumlar için, kapıların denetlenen sürümünü (denetlenen-X kapısı [$CNOT $ Gate](xref:microsoft.quantum.primitive.cnot)olduğunu unutmayın) anlatmak için aşağıdaki gösterimi tanıtıldık:</span><span class="sxs-lookup"><span data-stu-id="67a72-142">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.primitive.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_6.png)

<span data-ttu-id="67a72-143">Q #, bir işlemin denetlenen sürümünü otomatik olarak oluşturmak için yöntemler sağlar. Bu işlem, programcının bu işlemleri ele almak zorunda kalmadan kaydeder.</span><span class="sxs-lookup"><span data-stu-id="67a72-143">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="67a72-144">Buna bir örnek aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="67a72-144">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="67a72-145">Ölçüm işleci</span><span class="sxs-lookup"><span data-stu-id="67a72-145">Measurement operator</span></span>
<span data-ttu-id="67a72-146">Devre diyagramlarında görselleştirilecek kalan işlem ölçümdür.</span><span class="sxs-lookup"><span data-stu-id="67a72-146">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="67a72-147">Ölçüm bir qubit kaydı alır, bunu ölçer ve sonucu klasik bilgiler olarak verir.</span><span class="sxs-lookup"><span data-stu-id="67a72-147">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="67a72-148">Ölçüm bir işlem, ölçüm simgesiyle gösterilir ve her zaman bir qubit yazmaç girişi (katı bir satırla gösterilir) ve klasik bilgiler verir (bir Double satırıyla gösterilir).</span><span class="sxs-lookup"><span data-stu-id="67a72-148">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="67a72-149">Özellikle, bu tür bir alt devre şöyle görünür:</span><span class="sxs-lookup"><span data-stu-id="67a72-149">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="67a72-150">![ölçüm devresi](~/media/concepts_7.png)</span><span class="sxs-lookup"><span data-stu-id="67a72-150">![Measurement circuit](~/media/concepts_7.png)</span></span>

<span data-ttu-id="67a72-151">Q # Bu amaçla bir [Ölçü işleci](xref:microsoft.quantum.primitive.measure) uygular.</span><span class="sxs-lookup"><span data-stu-id="67a72-151">Q# implements a [Measure operator](xref:microsoft.quantum.primitive.measure) for this purpose.</span></span>
<span data-ttu-id="67a72-152">Daha fazla bilgi için [ölçümlerle ilgili bölüme](xref:microsoft.quantum.libraries.standard.prelude#measurements) bakın.</span><span class="sxs-lookup"><span data-stu-id="67a72-152">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="67a72-153">Benzer şekilde, subdevı</span><span class="sxs-lookup"><span data-stu-id="67a72-153">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_8.png)

<span data-ttu-id="67a72-154">$G $ değerinin klasik denetim bit değeri $1 $ değerine göre uygulandığı, bir sınıf denetimli geçit sağlar.</span><span class="sxs-lookup"><span data-stu-id="67a72-154">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="67a72-155">Teleporsyon devre diyagramı</span><span class="sxs-lookup"><span data-stu-id="67a72-155">Teleportation circuit diagram</span></span>
<span data-ttu-id="67a72-156">[Hisse teleporsyon](xref:microsoft.quantum.techniques.puttingittogether) , bu bileşenleri göstermek için büyük olasılıkla en iyi hisse algoritmadır.</span><span class="sxs-lookup"><span data-stu-id="67a72-156">[Quantum teleportation](xref:microsoft.quantum.techniques.puttingittogether) is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="67a72-157">Hisse salarasyon, entanglement ve ölçüm kullanımı aracılığıyla bir hisse bilgisayarı içindeki verileri (ya da bir hisse ağı içindeki uzak hisse bilgisayarları arasında) taşımak için kullanılan bir yöntemdir.</span><span class="sxs-lookup"><span data-stu-id="67a72-157">Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="67a72-158">Her ne kadar, bu, bir derece bitden diğerine, bir qubit 'in değerinin ne olduğunu bilmeksizin, belirli bir qubit içindeki değeri bir ile diğerine söylemeden, gerçekten de bir hisse cısına geçiş yeteneğine sahiptir!</span><span class="sxs-lookup"><span data-stu-id="67a72-158">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="67a72-159">Bu, protokol için hisse uzayı yasaları uyarınca çalışması için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="67a72-159">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="67a72-160">Hisse ve teleporsyon devresi aşağıda verilmiştir; Ayrıca, hisse öğesinin nasıl okunacağını göstermek için devresinin açıklamalı bir sürümünü sunuyoruz.</span><span class="sxs-lookup"><span data-stu-id="67a72-160">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
![](~/media/concepts_tp2.png)
