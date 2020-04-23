---
title: Q# teknikleri - Hepsini bir araya getirmek
description: 'Kuantum ışınlama gösteren temel bir Q # programı ile yürüyün.'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030574"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="1d916-103">Hepsini Bir Araya Getirmek: Işınlama</span><span class="sxs-lookup"><span data-stu-id="1d916-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="1d916-104">[Kuantum Devreleri'nde](xref:microsoft.quantum.concepts.circuits)tanımlanan ışınlama devresi örneğine dönelim.</span><span class="sxs-lookup"><span data-stu-id="1d916-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="1d916-105">Bunu şimdiye kadar öğrendiğimiz kavramları göstermek için kullanacağız.</span><span class="sxs-lookup"><span data-stu-id="1d916-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="1d916-106">Kuantum ışınlanmasının açıklaması, teoriye aşina olmayanlar için aşağıda ve ardından Q#'daki kod uygulamasının bir gözden geçirilmesi sağlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="1d916-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="1d916-107">Kuantum Işınlama: Teori</span><span class="sxs-lookup"><span data-stu-id="1d916-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="1d916-108">Kuantum ışınlama bilinmeyen bir kuantum durumu göndermek için bir tekniktir (biz bir yerde bir qubit olarak bakın __'mesaj__') başka bir yerde bir qubit (biz bu qubits için '__burada__' ve '__orada__'sırasıyla) olarak bakın.</span><span class="sxs-lookup"><span data-stu-id="1d916-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="1d916-109">__Mesajımızı__ Dirac gösterimini kullanarak bir vektör olarak temsil edebiliriz:</span><span class="sxs-lookup"><span data-stu-id="1d916-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="1d916-110">$$ \ket{\psi} = \alfa\ket{0} +{1} \beta\ket $$</span><span class="sxs-lookup"><span data-stu-id="1d916-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="1d916-111">Biz __message__ $\alpha$ ve $\beta$ değerlerini bilmediğimiz için qubit'in durumu bizim için bilinmemektedir.</span><span class="sxs-lookup"><span data-stu-id="1d916-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="1d916-112">Adım 1: Karışık bir durum oluşturma</span><span class="sxs-lookup"><span data-stu-id="1d916-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="1d916-113">Burada __qubit__ orada __qubit__ile dolaşmış olması için gereken __mesajı__ göndermek için .</span><span class="sxs-lookup"><span data-stu-id="1d916-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="1d916-114">Bu bir Hadamard kapısı uygulanarak elde edilir, ardından bir CNOT kapısı.</span><span class="sxs-lookup"><span data-stu-id="1d916-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="1d916-115">Bu geçit işlemlerinin arkasındaki matematiğe bakalım.</span><span class="sxs-lookup"><span data-stu-id="1d916-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="1d916-116">Biz __burada__ qubits ile başlayacak ve __orada__ hem{0}$\ket $ devlet.</span><span class="sxs-lookup"><span data-stu-id="1d916-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="1d916-117">Bu qubits dolaşmış sonra, onlar devlet vardır:</span><span class="sxs-lookup"><span data-stu-id="1d916-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="1d916-118">$$ \ket{\phi^+} ={1}\frac{2}{\sqrt{00} }(\ket + \ket{11}) $$</span><span class="sxs-lookup"><span data-stu-id="1d916-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="1d916-119">Adım 2: İletiyi gönderme</span><span class="sxs-lookup"><span data-stu-id="1d916-119">Step 2: Send the message</span></span>
<span data-ttu-id="1d916-120">__Mesajı__ göndermek için önce __qubit iletisi__ ile bir CNOT kapısı ve __burada__ giriş olarak qubit __(mesaj__ qubit kontrol olmak ve __burada__ qubit hedef qubit olmak, bu durumda) uygulayın.</span><span class="sxs-lookup"><span data-stu-id="1d916-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="1d916-121">Bu giriş durumu yazılabilir:</span><span class="sxs-lookup"><span data-stu-id="1d916-121">This input state can be written:</span></span>

<span data-ttu-id="1d916-122">{0} $$ \ket{\psi}\ket{\phi^+} = (\alfa\ket +{1}\beta\ket{1})(\frac {\sqrt{2}}(\ket{00} + \ket{11})) $$</span><span class="sxs-lookup"><span data-stu-id="1d916-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="1d916-123">Bu genişletir:</span><span class="sxs-lookup"><span data-stu-id="1d916-123">This expands to:</span></span>

<span data-ttu-id="1d916-124">$$ \ket\\psi}\ket{\phi^+}{2}= \frac{\alpha}\\sqrt{000} }\ket }\ket \{2}\frac\\ket}\ket}\ket }\ket + \frac{\beta}\ket{011} {2}{100} \ \\sqrt}\ket\ \sqrt }\sqrt }\sqrt }\sqrt }\\ket}\sqrt{2}{111} }\ket\\ket}\ket}\ket}\ket}\ket}\ket}\ket}\ket}\ket}\ket\ket}\\ket$$$\sqrt</span><span class="sxs-lookup"><span data-stu-id="1d916-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="1d916-125">Bir hatırlatma olarak, CNOT kapısı, kontrol qubit1 olduğunda hedef qubit çevirir.</span><span class="sxs-lookup"><span data-stu-id="1d916-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="1d916-126">Örneğin, $\ket{000}$ girişi ilk qubit (denetim) 0 olduğundan hiçbir değişiklikle sonuçlanmaz.</span><span class="sxs-lookup"><span data-stu-id="1d916-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="1d916-127">Ancak, ilk qubit 1 olduğu bir durumda almak - örneğin{100}$\ket $ bir giriş.</span><span class="sxs-lookup"><span data-stu-id="1d916-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="1d916-128">Bu durumda, ikinci qubit{110}(hedef) CNOT kapısı tarafından döndürülür gibi çıktı $\ket $ olduğunu.</span><span class="sxs-lookup"><span data-stu-id="1d916-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="1d916-129">CNOT kapısı yukarıdaki girdimize göre hareket ettikten sonra çıktımızı şimdi düşünelim.</span><span class="sxs-lookup"><span data-stu-id="1d916-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="1d916-130">Sonuç şudur:</span><span class="sxs-lookup"><span data-stu-id="1d916-130">The result is:</span></span>

<span data-ttu-id="1d916-131">$${2}\frac{\alpha}\\sqrt{000} }\ket \ \frac{\alpha}\\sqrt{2}}\ket }\ket{011} \ \frac{\beta}\sqrt}\ket{2}{110} +{2}\ket{101} }\ket}\ket $$</span><span class="sxs-lookup"><span data-stu-id="1d916-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="1d916-132">__İleti__ göndermek için bir sonraki adım __mesaj__ qubit (her terimin ilk qubit) bir Hadamard kapısı uygulamaktır.</span><span class="sxs-lookup"><span data-stu-id="1d916-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="1d916-133">Bir hatırlatma olarak, Hadamard kapısı aşağıdakileri yapar:</span><span class="sxs-lookup"><span data-stu-id="1d916-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="1d916-134">Girdi</span><span class="sxs-lookup"><span data-stu-id="1d916-134">Input</span></span> | <span data-ttu-id="1d916-135">Çıktı</span><span class="sxs-lookup"><span data-stu-id="1d916-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="1d916-136">$\ket{0}$</span><span class="sxs-lookup"><span data-stu-id="1d916-136">$\ket{0}$</span></span>  | <span data-ttu-id="1d916-137">$\frac{1}{\sqrt{2}}(\ket{0} {1}+ \ket )$</span><span class="sxs-lookup"><span data-stu-id="1d916-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="1d916-138">$\ket{1}$</span><span class="sxs-lookup"><span data-stu-id="1d916-138">$\ket{1}$</span></span>  | <span data-ttu-id="1d916-139">$\frac{1}{\sqrt{2}}(\ket{0} {1}- \ket )$</span><span class="sxs-lookup"><span data-stu-id="1d916-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="1d916-140">Yukarıdaki çıktımızın her döneminin ilk qubitine Hadamard kapısını uygularsak, aşağıdaki sonucu elde etmiş oluruz:</span><span class="sxs-lookup"><span data-stu-id="1d916-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="1d916-141">$${2}\frac{\alpha}{\sqrt }(\frac{1}{\sqrt{2}{0} }(\ket } (\ket + \ket{1}))\ket{2}{1}{2}{0} {1}{11} {2}{1}{2}{0} {1}{10} {2}{1}{2}{0} {00} + \frac{\alpha}\\sqrt }(\frac {\sqrt }(\ket + \ket ))\ket + \frac{\beta}\\sqrt }(\frac {\sqrt }(\ket - \ket)\ket ){1}\ket)\ket + \frac{\beta}\\sqrt }(\frac {\sqrt }(\ket - \ket ))ket{01} $$</span><span class="sxs-lookup"><span data-stu-id="1d916-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="1d916-142">Her terimin iki $\frac{1}{\sqrt{2}}$ faktörü olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="1d916-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="1d916-143">Aşağıdaki sonucu vererek bunları çoğaltabiliriz:</span><span class="sxs-lookup"><span data-stu-id="1d916-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="1d916-144">$${2}\frac{\alpha}{0} (\ket{1}+ \ket )\ket{00} +{2}\frac{\alfa}{0} (\ket + \ket{2}\ket{0} {1}{10} {2}{0} {1}{11} )\ket ) \frac{\beta} (\ket -{1}\ket\beta} (\ket\ket )\ket{01} $$</span><span class="sxs-lookup"><span data-stu-id="1d916-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="1d916-145">$\frac{1}{2}$ faktörü her dönem için yaygındır, bu yüzden artık parantez dışında alabilir:</span><span class="sxs-lookup"><span data-stu-id="1d916-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="1d916-146">{1}{2}$$ \frac{0} \big[\alpha(\ket{1}+ \ket{00} )\ket{0} + \ket{1})\ket{11} + \ket ) \ket + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket - \ket{1})\ket )\ket{01}\big] $$</span><span class="sxs-lookup"><span data-stu-id="1d916-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="1d916-147">Daha sonra veren her dönem için parantez leri çoğaltabiliriz:</span><span class="sxs-lookup"><span data-stu-id="1d916-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="1d916-148">{1}{2}$$ \frac{000} \big[\alpha\ket +{100} \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} -{110} \beta\ket{001} + \beta\ket + \beta\ket \ \beta\ket - \beta\ket{101}\big] $$</span><span class="sxs-lookup"><span data-stu-id="1d916-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="1d916-149">Adım 3: Sonucu ölçün</span><span class="sxs-lookup"><span data-stu-id="1d916-149">Step 3: Measure the result</span></span>

<span data-ttu-id="1d916-150">__Burada__ ve __orada__ dolaşmış olması nedeniyle, __burada__ herhangi bir ölçüm __orada__durumunu etkileyecektir.</span><span class="sxs-lookup"><span data-stu-id="1d916-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="1d916-151">Birinci ve ikinci qubiti __(mesaj__ ve __burada)__ ölçersek, bu dolaşıklık özelliğinden dolayı hangi durumda __olduğunu__ öğrenebiliriz.</span><span class="sxs-lookup"><span data-stu-id="1d916-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="1d916-152">Eğer 00'ı ölçer ve sonuç alırsak, süperpozisyon çöker ve sadece bu sonuca uygun şartlar bırakır.</span><span class="sxs-lookup"><span data-stu-id="1d916-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="1d916-153">Bu $\alpha\ket{000} +\beta\ket{001}$.</span><span class="sxs-lookup"><span data-stu-id="1d916-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="1d916-154">Bu $\ket{00}(\alfa\ket{0} +\beta\ket{1})$' olarak yeniden kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="1d916-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="1d916-155">Bu nedenle birinci ve ikinci qubit'i 00 olarak ölçersek, __there__üçüncü qubitin $(\alpha\ket{0} +\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="1d916-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="1d916-156">01'i ölçer ve elde edersek, süperpozisyon çöker ve yalnızca bu sonuca uygun şartlar bırakır.</span><span class="sxs-lookup"><span data-stu-id="1d916-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="1d916-157">Bu $\alpha\ket{011} +\beta\ket{010}$.</span><span class="sxs-lookup"><span data-stu-id="1d916-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="1d916-158">Bu $\ket{01}(\alfa\ket{1} +\beta\ket{0})$' olarak yeniden kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="1d916-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="1d916-159">Bu nedenle birinci ve ikinci qubit'i 01 olarak ölçersek, __there__üçüncü qubitin $(\alpha\ket{1} +\beta\ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="1d916-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="1d916-160">Eğer 10'u ölçer ve elde edersek, süperpozisyon çöker ve yalnızca bu sonuca uygun şartlar bırakır.</span><span class="sxs-lookup"><span data-stu-id="1d916-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="1d916-161">Bu $\alfa\ket{100} -\beta\ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="1d916-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="1d916-162">Bu $\ket{10}(\alfa\ket{0} -\beta\ket{1})$' olarak yeniden kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="1d916-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="1d916-163">Bu nedenle birinci ve ikinci qubit'i 10 olarak ölçersek, __there__üçüncü qubitin $(\alpha\ket{0} -\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="1d916-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="1d916-164">Eğer ölçer ve sonuç 11 alırsak, süperpozisyon çöker ve sadece bu sonuca uygun şartlar bırakır.</span><span class="sxs-lookup"><span data-stu-id="1d916-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="1d916-165">Bu $\alfa\ket{111} -\beta\ket{110}$.</span><span class="sxs-lookup"><span data-stu-id="1d916-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="1d916-166">Bu $\ket{11}(\alfa\ket{1} -\beta\ket{0})$' olarak yeniden kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="1d916-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="1d916-167">Bu nedenle birinci ve ikinci qubit'i 11 olarak ölçersek, __there__üçüncü qubitin $(\alpha\ket{1} -\beta\ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="1d916-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="1d916-168">Adım 4: Sonucu yorumlama</span><span class="sxs-lookup"><span data-stu-id="1d916-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="1d916-169">Bir hatırlatma olarak, göndermek istediğimiz orijinal __mesaj:__</span><span class="sxs-lookup"><span data-stu-id="1d916-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="1d916-170">$$ \ket{\psi} = \alfa\ket{0} +{1} \beta\ket $$</span><span class="sxs-lookup"><span data-stu-id="1d916-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="1d916-171">Biz bu duruma __orada__ qubit almak gerekir, böylece alınan devlet amaçlanan biridir.</span><span class="sxs-lookup"><span data-stu-id="1d916-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="1d916-172">Biz ölçülen ve 00 bir sonucu var, sonra üçüncü qubit, __orada__, devlet{0} $(\alpha\ket +\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="1d916-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="1d916-173">Amaçlanan __ileti__bu olduğundan, değişiklik gerekmez.</span><span class="sxs-lookup"><span data-stu-id="1d916-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="1d916-174">Biz ölçülen ve 01 bir sonucu var, sonra üçüncü qubit, __orada__, devlet{1} $(\alpha\ket +\beta\ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="1d916-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="1d916-175">Bu amaçlanan __ileti__farklıdır, ancak NOT kapısı uygulamak bize istenen durumu verir{0} $(\alpha\ket +\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="1d916-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="1d916-176">Biz ölçülen ve 10 bir sonucu var, o zaman üçüncü qubit, __orada__,{0} devlet $(\alpha\ket -\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="1d916-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="1d916-177">Bu amaçlanan __ileti__farklıdır, ancak Z kapısı uygulamak bize istenen durumu verir{0} $(\alpha\ket +\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="1d916-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="1d916-178">Biz ölçülen ve 11 bir sonucu var, sonra üçüncü qubit, __orada__, devlet{1} $(\alpha\ket -\beta\ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="1d916-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="1d916-179">Bu amaçlanan __ileti__farklıdır, ancak bir Not kapısı z kapısı takip uygulayarak bize istenen{0} durum $(\alpha\ket +\beta\ket{1})$verir.</span><span class="sxs-lookup"><span data-stu-id="1d916-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="1d916-180">Özetlemek gerekirse, ölçersek ve ilk qubit 1 ise, Z kapısı uygulanır.</span><span class="sxs-lookup"><span data-stu-id="1d916-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="1d916-181">Ölçersek ve ikinci qubit 1 ise, NOT kapısı uygulanır.</span><span class="sxs-lookup"><span data-stu-id="1d916-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="1d916-182">Özet</span><span class="sxs-lookup"><span data-stu-id="1d916-182">Summary</span></span>
<span data-ttu-id="1d916-183">Aşağıda gösterilen ışınlanma uygulayan bir metin kitabı kuantum devresi.</span><span class="sxs-lookup"><span data-stu-id="1d916-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="1d916-184">Soldan sağa hareket görebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="1d916-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="1d916-185">Adım 1: __Burada__ ve __orada__ bir Hadamard kapısı ve CNOT kapısı uygulayarak entangling.</span><span class="sxs-lookup"><span data-stu-id="1d916-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="1d916-186">Adım 2: __İletiyi__ CNOT kapısı ve Hadamard kapısı kullanarak gönderme.</span><span class="sxs-lookup"><span data-stu-id="1d916-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="1d916-187">Adım 3: Birinci ve ikinci qubits, __mesaj__ ve __burada__bir ölçüm alarak .</span><span class="sxs-lookup"><span data-stu-id="1d916-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="1d916-188">Adım 4: Adım 3'teki ölçüm sonucuna bağlı olarak NOT kapısı veya Z kapısı uygulamak.</span><span class="sxs-lookup"><span data-stu-id="1d916-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

!['Teleport(msg : Qubit, orada : Qubit) : Birim'](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="1d916-190">Kuantum Işınlama: Kod</span><span class="sxs-lookup"><span data-stu-id="1d916-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="1d916-191">Kuantum ışınlanması için devremiz var:</span><span class="sxs-lookup"><span data-stu-id="1d916-191">We have our circuit for quantum teleportation:</span></span>

!['Teleport(msg : Qubit, orada : Qubit) : Birim'](~/media/teleportation.svg)

<span data-ttu-id="1d916-193">Artık bu kuantum devresindeki her adımı Q#'a çevirebiliriz.</span><span class="sxs-lookup"><span data-stu-id="1d916-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="1d916-194">Adım 0: Tanım</span><span class="sxs-lookup"><span data-stu-id="1d916-194">Step 0: Definition</span></span>
<span data-ttu-id="1d916-195">Işınlanma gerçekleştirirken, göndermek istediğimiz __mesajı__ ve nereye göndermek istediğimizi bilmemiz gerekir (__orada).__</span><span class="sxs-lookup"><span data-stu-id="1d916-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="1d916-196">Bu nedenle, bağımsız değişken olarak iki qubit verilen yeni bir Teleport `msg` `there`işlemi tanımlayarak başlar ve:</span><span class="sxs-lookup"><span data-stu-id="1d916-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="1d916-197">Biz de bir `here` `using` blok ile elde qubit ayırmanız gerekir:</span><span class="sxs-lookup"><span data-stu-id="1d916-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="1d916-198">Adım 1: Karışık bir durum oluşturma</span><span class="sxs-lookup"><span data-stu-id="1d916-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="1d916-199">Daha sonra `here` ve `there` @"microsoft.quantum.intrinsic.h" işlemleri @"microsoft.quantum.intrinsic.cnot" kullanarak arasında dolaşmış çifti oluşturabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="1d916-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="1d916-200">Adım 2: İletiyi gönderme</span><span class="sxs-lookup"><span data-stu-id="1d916-200">Step 2: Send the message</span></span>
<span data-ttu-id="1d916-201">Daha sonra bir sonraki $\operatorname{CNOT}$ ve $H$ kapılarını kullanarak mesajımızı qubit'imizi hareket ettirici oluruz:</span><span class="sxs-lookup"><span data-stu-id="1d916-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="1d916-202">Adım 3 & 4: Sonucu ölçme ve yorumlama</span><span class="sxs-lookup"><span data-stu-id="1d916-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="1d916-203">Son olarak, @"microsoft.quantum.intrinsic.m" ölçümleri gerçekleştirmek ve istenilen durumu elde etmek için gerekli `if` geçit işlemlerini gerçekleştirmek için kullanırız, ifadelerde belirtildiği gibi:</span><span class="sxs-lookup"><span data-stu-id="1d916-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a><span data-ttu-id="1d916-204">Adım 5: Qubit kaydını yeniden başlatma</span><span class="sxs-lookup"><span data-stu-id="1d916-204">Step 5: Restarting the qubit register</span></span>

<span data-ttu-id="1d916-205">Her Q# operasyonunun sonunda qubitlerin $\ket{0}$ durumunda olmasını istiyoruz.</span><span class="sxs-lookup"><span data-stu-id="1d916-205">At the end of every Q# operation we need to let the qubits in the state $\ket{0}$.</span></span> <span data-ttu-id="1d916-206">Tüm qubitleri sıfır durumuna yeniden başlatmak için kullanabiliriz @"microsoft.quantum.intrinsic.reset" ve bu işlemimizi bitirir.</span><span class="sxs-lookup"><span data-stu-id="1d916-206">We can use @"microsoft.quantum.intrinsic.reset" to restart all the qubits to the zero state and this will finish our operation.</span></span>

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


