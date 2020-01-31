---
title: 'Tümünü birlikte yerleştirme-Q # teknikleri | Microsoft Docs'
description: 'Tümünü birlikte yerleştirme-Q # teknikleri'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3605826da159757d4b321dbf4ec6acd7f4e6be05
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820173"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="f073b-103">Hepsini birlikte yerleştirme: Teleporsyon</span><span class="sxs-lookup"><span data-stu-id="f073b-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="f073b-104">Şimdi, [hisse devrelerin](xref:microsoft.quantum.concepts.circuits)içinde tanımlanan teleporsyon devresi örneğine dönelim.</span><span class="sxs-lookup"><span data-stu-id="f073b-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="f073b-105">Şimdiye kadar öğrendiğimiz kavramları göstermek için bunu kullanacağız.</span><span class="sxs-lookup"><span data-stu-id="f073b-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="f073b-106">Aşağıda, teorik ve Q # içindeki kod uygulamasına yönelik bir adım adım yol açan bir işlem için aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="f073b-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="f073b-107">Hisse ve Teleporsyon: teorisi</span><span class="sxs-lookup"><span data-stu-id="f073b-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="f073b-108">Hisse atısyon, bir konumdaki qubitden başka bir konumdaki qubit 'e ('__ileti__' olarak adlandırılıyoruz) bilinmeyen bir hisse durumu göndermeye yönelik bir tekniktir (sırasıyla ' buraya ' ve '__burada__ __',__ bu qubits 'e başvuracağız).</span><span class="sxs-lookup"><span data-stu-id="f073b-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="f073b-109">Dirac gösterimini kullanarak __iletinizi__ bir vektör olarak temsil edebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="f073b-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="f073b-110">$ $ \ket{\psı} = \harfler \ ayraç{0} + \beta\ayraç{1} $ $</span><span class="sxs-lookup"><span data-stu-id="f073b-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="f073b-111">$ \Alpha $ ve $ \beta $ değerlerini bildiğimiz için, __iletinin__ qubit durumu bizim için bilinmiyor şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="f073b-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="f073b-112">1\. Adım: bir entangled durumu oluşturma</span><span class="sxs-lookup"><span data-stu-id="f073b-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="f073b-113">__Burada__ __qubit için__ihtiyacımız olan __iletiyi__ , bu adreste qubit ile zenginbir şekilde göndermek için.</span><span class="sxs-lookup"><span data-stu-id="f073b-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="f073b-114">Bu, bir Hadamard kapısı ve ardından bir CNOT kapısı uygulanarak elde edilir.</span><span class="sxs-lookup"><span data-stu-id="f073b-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="f073b-115">Bu kapı işlemlerinin arkasındaki matematik bölümüne bakalım.</span><span class="sxs-lookup"><span data-stu-id="f073b-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="f073b-116">__Burada__ qubits ile başlayacağız ve $ \demet{0}$ __durumunda olacak.__</span><span class="sxs-lookup"><span data-stu-id="f073b-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="f073b-117">Bu qubits 'i doğruladıktan sonra, bu durum şu durumlardır:</span><span class="sxs-lookup"><span data-stu-id="f073b-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="f073b-118">$ $ \ket{\phi ^ +} = \frac{1}{\sqrt{2}} (\ayraç{00} + \ket{11}) $ $</span><span class="sxs-lookup"><span data-stu-id="f073b-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="f073b-119">2\. Adım: iletiyi gönderin</span><span class="sxs-lookup"><span data-stu-id="f073b-119">Step 2: Send the message</span></span>
<span data-ttu-id="f073b-120">__İletiyi__ göndermek için öncelikle __ileti__ qubit ve __burada__ giriş olarak bir cnot kapısı uyguladık (Bu örnekte, __ileti__ qubit ve hedef qubit __, bu__ örnekte bu durumda).</span><span class="sxs-lookup"><span data-stu-id="f073b-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="f073b-121">Bu giriş durumu yazılabilir:</span><span class="sxs-lookup"><span data-stu-id="f073b-121">This input state can be written:</span></span>

<span data-ttu-id="f073b-122">$ $ \ket{\psi}\ket{\phi ^ +} = (\harfler \ ayraç{0} + \beta\ayraç{1}) (\frac{1}{\sqrt{2}} (\demet{00} + \tus{11})) $ $</span><span class="sxs-lookup"><span data-stu-id="f073b-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="f073b-123">Bu, şu şekilde genişletilir:</span><span class="sxs-lookup"><span data-stu-id="f073b-123">This expands to:</span></span>

<span data-ttu-id="f073b-124">$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\harflerden}{\sqrt{2}} \tus{000} + \frac{\harflerden} {\sqrt{2}} \tus{011} + \frac{\beta}{\sqrt{2}} \tus{100} + \frac{\beta}{\sqrt{2}} \tus{111} $ $</span><span class="sxs-lookup"><span data-stu-id="f073b-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="f073b-125">Bir anımsatıcı olarak, CNOT kapısı, denetim qubit 1 olduğunda hedef qubit 'i çevirir.</span><span class="sxs-lookup"><span data-stu-id="f073b-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="f073b-126">Örneğin, $ \ket{000}$ girişi, ilk qubit (denetim) 0 olduğunda hiçbir değişikliğe neden olmaz.</span><span class="sxs-lookup"><span data-stu-id="f073b-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="f073b-127">Ancak, ilk qubitin 1 olduğu, örneğin $ \ket{100}$ girişi gibi bir durum alın.</span><span class="sxs-lookup"><span data-stu-id="f073b-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="f073b-128">Bu örnekte çıktı, ikinci qubit (hedef) CNOT kapısı tarafından çevrilmiş olarak $ \ket{110}$ şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="f073b-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="f073b-129">Şimdi, CNOT kapısı yukarıdaki girişte işlem yaptıktan sonra Çıktımızı göz atalım.</span><span class="sxs-lookup"><span data-stu-id="f073b-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="f073b-130">Sonuç:</span><span class="sxs-lookup"><span data-stu-id="f073b-130">The result is:</span></span>

<span data-ttu-id="f073b-131">$ $ \frac{\harflerden}{\sqrt{2}} \tus{000} + \frac{\harflerden}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \tus{110} + \frac{\beta}{\sqrt{2}} \tus{101} $ $</span><span class="sxs-lookup"><span data-stu-id="f073b-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="f073b-132">__İletiyi__ göndermek için bir sonraki adım, __ileti__ qubit 'e bir Hadamard Gate (her bir terimin ilk qubıdır) uygulamaktır.</span><span class="sxs-lookup"><span data-stu-id="f073b-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="f073b-133">Anımsatıcı olarak Hadamard kapısı şunları yapar:</span><span class="sxs-lookup"><span data-stu-id="f073b-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="f073b-134">Girdi</span><span class="sxs-lookup"><span data-stu-id="f073b-134">Input</span></span> | <span data-ttu-id="f073b-135">Çıktı</span><span class="sxs-lookup"><span data-stu-id="f073b-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="f073b-136">$ \demet{0}$</span><span class="sxs-lookup"><span data-stu-id="f073b-136">$\ket{0}$</span></span>  | <span data-ttu-id="f073b-137">$ \frac{1}{\sqrt{2}} (\ayraç{0} + \ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="f073b-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="f073b-138">$ \demet{1}$</span><span class="sxs-lookup"><span data-stu-id="f073b-138">$\ket{1}$</span></span>  | <span data-ttu-id="f073b-139">$ \frac{1}{\sqrt{2}} (\ayraç{0}-\demet{1}) $</span><span class="sxs-lookup"><span data-stu-id="f073b-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="f073b-140">Yukarıdaki çıktımızın her bir teriminin ilk qubit ' i için Hadamard geçidini uygulıyoruz, aşağıdaki sonucu elde ediyoruz:</span><span class="sxs-lookup"><span data-stu-id="f073b-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="f073b-141">$ $ \frac{\harflerden}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\demet{0} + \tus{1})) \ayraç{00} + \frac{\harflerden}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\tus{0} + \tus{1})) \tus{11} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\demet{0}-\ayraç{1})) \ayraç{10} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\demet{0}-\demet{1})) \tus{01} $ $</span><span class="sxs-lookup"><span data-stu-id="f073b-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="f073b-142">Her dönemde $2 \frac{1}{\sqrt{2}} $ faktörlerinin olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="f073b-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="f073b-143">Aşağıdaki sonucu vererek bunları çarpıyoruz:</span><span class="sxs-lookup"><span data-stu-id="f073b-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="f073b-144">$ $ \frac{\harflerden}{2}(\demet{0} + \ ayraç{1}) \ayraç{00} + \frac{\harflerden}{2}(\demet{0} + \tus{1}) \tus{11} + \frac{\beta}{2}(\demet{0}-\ayraç{1}) \ayraç{10} + \frac{\beta}{2}(\demet{0}-\ayraç{1}) \ayraç{01} $ $</span><span class="sxs-lookup"><span data-stu-id="f073b-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="f073b-145">$ \Frac{1}{2}$ faktörü her bir terim için ortaktır, bu sayede artık köşeli ayracın dışına götürebiliriz:</span><span class="sxs-lookup"><span data-stu-id="f073b-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="f073b-146">$ $ \frac{1}{2}\big [\Alpha (\demet{0} + \ket{1}) \ayraç{00} + \alfa (\ayraç{0} + \ayraç{1}) \ayraç{11} + \beta (\demet{0}-\ayraç{1}) \demet{10} + \beta (\demet{0}</span><span class="sxs-lookup"><span data-stu-id="f073b-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="f073b-147">Böylece, her dönem için köşeli ayraçları derecelebiliriz:</span><span class="sxs-lookup"><span data-stu-id="f073b-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="f073b-148">$ $ \frac{1}{2}\Büyük [\harfler \ ayraç{000} + \ harfler \ ayraç{100} + \ harfler \ ayraç{011} + \ harfler \ ayraç{111} + \beta\ayraç{010}-\beta\demet{110} + \beta\ayraç{001}-\beta\demet{101}\big] $ $</span><span class="sxs-lookup"><span data-stu-id="f073b-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="f073b-149">3\. Adım: sonucu ölçme</span><span class="sxs-lookup"><span data-stu-id="f073b-149">Step 3: Measure the result</span></span>

<span data-ttu-id="f073b-150">__Burada__ __olduğu gibi__ , __burada__ bulunan her türlü ölçüm bu __durumun durumunu etkiler.__</span><span class="sxs-lookup"><span data-stu-id="f073b-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="f073b-151">Birinci ve ikinci qubit ' i (__ileti__ ve __burada__) ölçyoruz, bu entanglement özelliği nedeniyle __hangi durumda olduğunu__ öğreniyoruz.</span><span class="sxs-lookup"><span data-stu-id="f073b-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="f073b-152">Bir sonucu ölçyoruz ve elde ediyorsanız, üst konum daraltılır ve bu sonuçla yalnızca koşulların tutarlılığını bırakır.</span><span class="sxs-lookup"><span data-stu-id="f073b-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="f073b-153">Bu, $ \ harfler \ ayraç{000} + \beta\ayraç{001}$.</span><span class="sxs-lookup"><span data-stu-id="f073b-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="f073b-154">Bu, yeniden düzenlenmiş to $ \ket{00}(\harflerden \ayraç{0} + \beta\ayraç{1}) $.</span><span class="sxs-lookup"><span data-stu-id="f073b-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="f073b-155">Bu nedenle, birinci ve ikinci qubit 'i 00 olarak ölçyoruz, burada üçüncü qubit, __burada__$ (\harflerden \demet{0} + \beta\tus{1}) $ olduğunu biliyoruz.</span><span class="sxs-lookup"><span data-stu-id="f073b-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="f073b-156">Bir sonucu ölçyoruz ve elde ediyorsanız, üst konum daraltılır ve yalnızca bu sonuçla tutarlı şartlar bırakılır.</span><span class="sxs-lookup"><span data-stu-id="f073b-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="f073b-157">Bu, $ \ harfler \ ayraç{011} + \beta\ayraç{010}$.</span><span class="sxs-lookup"><span data-stu-id="f073b-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="f073b-158">Bu, yeniden düzenlenmiş to $ \ket{01}(\harflerden \ayraç{1} + \beta\ayraç{0}) $.</span><span class="sxs-lookup"><span data-stu-id="f073b-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="f073b-159">Bu nedenle, birinci ve ikinci qubit 'i 01 olarak ölçyoruz, burada üçüncü qubit, __burada__$ (\harflerden \demet{1} + \beta\tus{0}) $ olduğunu biliyoruz.</span><span class="sxs-lookup"><span data-stu-id="f073b-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="f073b-160">Bir sonuç 10 ' u ölçyoruz ve elde etmemiz durumunda, üst konum daraltılır ve bu sonuçla yalnızca koşulların tutarlılığını bırakır.</span><span class="sxs-lookup"><span data-stu-id="f073b-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="f073b-161">Bu, $ \ harfler \ ayraç{100}-\beta\ayraç{101}$.</span><span class="sxs-lookup"><span data-stu-id="f073b-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="f073b-162">Bu, yeniden düzenlenmiş to $ \ket{10}(\harflerden \ayraç{0}-\beta\ayraç{1}) $ olur.</span><span class="sxs-lookup"><span data-stu-id="f073b-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="f073b-163">Bu nedenle, birinci ve ikinci qubit ' i 10 olarak ölçyoruz, burada üçüncü qubit, __burada__$ (\harflerden \demet{0}-\beta\demet{1}) $ olduğunu biliyoruz.</span><span class="sxs-lookup"><span data-stu-id="f073b-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="f073b-164">Bir sonuç 11 ' i ölçyoruz ve elde ediyorsanız, üst konum daraltılır ve yalnızca bu sonuçla tutarlı şartlar bırakılır.</span><span class="sxs-lookup"><span data-stu-id="f073b-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="f073b-165">Bu, $ \ harfler \ ayraç{111}-\beta\ayraç{110}$.</span><span class="sxs-lookup"><span data-stu-id="f073b-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="f073b-166">Bu, yeniden düzenlenmiş to $ \ket{11}(\harflerden \ayraç{1}-\beta\ayraç{0}) $ olur.</span><span class="sxs-lookup"><span data-stu-id="f073b-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="f073b-167">Bu nedenle, birinci ve ikinci qubit 'i 11 olarak ölçyoruz, burada üçüncü qubit, __burada__$ (\harflerden \demet{1}-\beta\demet{0}) $ olduğunu biliyoruz.</span><span class="sxs-lookup"><span data-stu-id="f073b-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="f073b-168">4\. Adım: sonucu yorumlama</span><span class="sxs-lookup"><span data-stu-id="f073b-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="f073b-169">Anımsatıcı olarak, daha önce gönderilmek üzere sunduğumuz özgün __ileti__ :</span><span class="sxs-lookup"><span data-stu-id="f073b-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="f073b-170">$ $ \ket{\psı} = \harfler \ ayraç{0} + \beta\ayraç{1} $ $</span><span class="sxs-lookup"><span data-stu-id="f073b-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="f073b-171">Alınan durumun amaçlanan durum olması için bu duruma __kadar quge almamız__ gerekir.</span><span class="sxs-lookup"><span data-stu-id="f073b-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="f073b-172">00 değerini ölçtüğünüz ve elde ettiğimiz takdirde, üçüncü qubit __, $__ (\harflerden \demet{0} + \beta\demet{1}) $ durumunda olur.</span><span class="sxs-lookup"><span data-stu-id="f073b-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="f073b-173">Bu istenen __ileti__olduğundan, hiçbir değişiklik yapılması gerekmez.</span><span class="sxs-lookup"><span data-stu-id="f073b-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="f073b-174">01 değerini ölçtüğünüz ve sonucu elde etmemiz durumunda üçüncü qubit __, $__ (\harflerden \demet{1} + \beta\demet{0}) $ şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="f073b-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="f073b-175">Bu, amaçlanan __iletiden__farklıdır, ancak Not kapısı uygulandığında istenen durum $ (\harfler \ ayraç{0} + \beta\ayraç{1}) $ sunulmaktadır.</span><span class="sxs-lookup"><span data-stu-id="f073b-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="f073b-176">10 ' un bir sonucu ölçtüğünüz ve elde etmemiz durumunda, üçüncü qubit __, $__ (\harflerden \demet{0}-\beta\demet{1}) $ şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="f073b-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="f073b-177">Bu, hedeflenen __iletiden__farklıdır, ancak Z kapısı uygulandığında istenen durum $ (\harflerden \ayraç{0} + \beta\ayraç{1}) $ sunulmaktadır.</span><span class="sxs-lookup"><span data-stu-id="f073b-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="f073b-178">11 değerini ölçtüğünüz ve sonucu elde ediyorsanız, üçüncü qubit __, $__ (\harflerden \demet{1}-\beta\demet{0}) $ durumunda olur.</span><span class="sxs-lookup"><span data-stu-id="f073b-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="f073b-179">Bu, hedeflenen __iletiden__farklıdır, ancak bir Z kapısı ve ardından bir Z kapısı, istenen durum $ (\harflerden \ayraç{0} + \beta\ayraç{1}) $ değerini verir.</span><span class="sxs-lookup"><span data-stu-id="f073b-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="f073b-180">Özetlemek gerekirse, ölçyoruz ve ilk qubit 1 ise, Z kapısı uygulanır.</span><span class="sxs-lookup"><span data-stu-id="f073b-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="f073b-181">Ölçyoruz ve ikinci qubit 1 ise, NOT kapısı uygulanır.</span><span class="sxs-lookup"><span data-stu-id="f073b-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="f073b-182">Özet</span><span class="sxs-lookup"><span data-stu-id="f073b-182">Summary</span></span>
<span data-ttu-id="f073b-183">Aşağıda gösterildiği gibi, teleporsyon uygulayan bir metin kitabı hisse devresi verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="f073b-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="f073b-184">Soldan sağa doğru hareket etmek için şunları görebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="f073b-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="f073b-185">1\. Adım: bir Hadamard kapısı __ve__ cnot kapısı uygulayarak __burada__ bir göz atın.</span><span class="sxs-lookup"><span data-stu-id="f073b-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="f073b-186">2\. Adım: bir CNOT kapısı ve Hadamard kapısı kullanarak __Ileti__ gönderme.</span><span class="sxs-lookup"><span data-stu-id="f073b-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="f073b-187">3\. Adım: birinci ve ikinci qubit, __ileti__ ve __burada__ölçüm alma.</span><span class="sxs-lookup"><span data-stu-id="f073b-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="f073b-188">4\. Adım: 3. adımdaki ölçümün sonucuna bağlı olarak NOT kapısı veya Z kapısı uygulama.</span><span class="sxs-lookup"><span data-stu-id="f073b-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

![' Teleport (MSG: qubit, burada: qubit): Unit '](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="f073b-190">Hisse ve Teleporsyon: kod</span><span class="sxs-lookup"><span data-stu-id="f073b-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="f073b-191">Hisse için bağlantı hattı için devreniz:</span><span class="sxs-lookup"><span data-stu-id="f073b-191">We have our circuit for quantum teleportation:</span></span>

![' Teleport (MSG: qubit, burada: qubit): Unit '](~/media/teleportation.svg)

<span data-ttu-id="f073b-193">Artık bu hisse içindeki adımların her birini Q # olarak çevirebiliriz.</span><span class="sxs-lookup"><span data-stu-id="f073b-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="f073b-194">Adım 0: tanım</span><span class="sxs-lookup"><span data-stu-id="f073b-194">Step 0: Definition</span></span>
<span data-ttu-id="f073b-195">Teleporsyon gerçekleştirdiğimiz zaman, göndermek istediğimiz __iletiyi__ ve nereye__gönderileceğini (burada__) öğrenmemiz gerekir.</span><span class="sxs-lookup"><span data-stu-id="f073b-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="f073b-196">Bu nedenle, `msg` ve `there`bağımsız değişken olarak iki qubit verilen yeni bir teleport işlemi tanımlayarak başlayacağız:</span><span class="sxs-lookup"><span data-stu-id="f073b-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="f073b-197">Ayrıca, bir `using` bloğuyla elde ettiğimiz bir qubit `here` de ayırmanız gerekir:</span><span class="sxs-lookup"><span data-stu-id="f073b-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="f073b-198">1\. Adım: bir entangled durumu oluşturma</span><span class="sxs-lookup"><span data-stu-id="f073b-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="f073b-199">Daha sonra, @"microsoft.quantum.intrinsic.h" ve @"microsoft.quantum.intrinsic.cnot" işlemlerini kullanarak `here` ve `there` arasında entangled çiftini oluşturarız:</span><span class="sxs-lookup"><span data-stu-id="f073b-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="f073b-200">2\. Adım: iletiyi gönderin</span><span class="sxs-lookup"><span data-stu-id="f073b-200">Step 2: Send the message</span></span>
<span data-ttu-id="f073b-201">Daha sonra, ileti qubit bitini taşımak için sonraki $ \operatorname{CNOT} $ ve $H $ kapıları kullanın:</span><span class="sxs-lookup"><span data-stu-id="f073b-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="f073b-202">3\. adım & 4: sonucu ölçme ve yorumlama</span><span class="sxs-lookup"><span data-stu-id="f073b-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="f073b-203">Son olarak, ölçümleri gerçekleştirmek ve `if` deyimleriyle gösterildiği gibi istenen durumu almak için gerekli olan geçit işlemlerini gerçekleştirmek üzere @"microsoft.quantum.intrinsic.m" kullanırız:</span><span class="sxs-lookup"><span data-stu-id="f073b-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

<span data-ttu-id="f073b-204">Bu, teleporsyon operatörünüzün tanımını tamamlar, bu nedenle `here`serbest bırakabilir, gövdeyi sonlandırabilmeniz ve işlemi sonlandırabiliriz.</span><span class="sxs-lookup"><span data-stu-id="f073b-204">This finishes the definition of our teleportation operator, so we can deallocate `here`, end the body, and end the operation.</span></span>

```qsharp
    }
}
```
