---
title: Hisse Oracles | Microsoft Docs
description: Hisse Oracles
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
ms.openlocfilehash: 96949b371a3a5a1135d624690933a48ea0214a2e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184721"
---
# <a name="quantum-oracles"></a><span data-ttu-id="7656a-103">Hisse Oracles</span><span class="sxs-lookup"><span data-stu-id="7656a-103">Quantum Oracles</span></span>

<span data-ttu-id="7656a-104">Oracle $O $, başka bir algoritmaya girdi olarak kullanılan "kara kutu" işlemidir.</span><span class="sxs-lookup"><span data-stu-id="7656a-104">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="7656a-105">Genellikle, bu gibi işlemler klasik bir işlev kullanılarak tanımlanır $f: \\{0, 1\\} ^ n \ \\{0, 1\\} ^ d $ $n $-bit ikili girişi alan ve bir $m $-bit ikili çıktısı üreten.</span><span class="sxs-lookup"><span data-stu-id="7656a-105">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="7656a-106">Bunu yapmak için belirli bir ikili girişi $x = (X_{0}, X_{1}, \noktalar, X_ {n-1}) $ kullanın.</span><span class="sxs-lookup"><span data-stu-id="7656a-106">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="7656a-107">Qubit durumları $ \ket{\vec{x}} = \ket{X_{0}} \otimes \ket{X_{1}} \otimes \cnoktalar \otimes \ket{X_{n-1}} $ olarak etiketliyoruz.</span><span class="sxs-lookup"><span data-stu-id="7656a-107">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="7656a-108">İlk olarak, \ket{x} = \ket{f (x)} $ $O için $O $ tanımlamalısınız, ancak bu birkaç soruna neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="7656a-108">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="7656a-109">İlk olarak, $f $, kayıttaki qubits sayısını değiştirecek $O şekilde farklı bir giriş ve çıkış boyutuna sahip olabilir ($n \ne m $).</span><span class="sxs-lookup"><span data-stu-id="7656a-109">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="7656a-110">İkinci olarak, $n = m $ olsa bile, işlev ters çevrilebilir olamaz: bazı $x \ne y $ için $f (x) = f (y) $, sonra $O \ket{x} = O\ket {y} $ ancak $O ^ \hanger O\ket {x} \ne O ^ \dağılım O\ket {y} $.</span><span class="sxs-lookup"><span data-stu-id="7656a-110">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="7656a-111">Bu, ^ \dağılım $ $O adjoint işlemini oluşturmayamayacağız ve Oracles için tanımlanmış bir adekin olması gerektiğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="7656a-111">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="7656a-112">Bir Oracle 'ı hesaplama tabanlı durumlar üzerinde etkile tanımlama</span><span class="sxs-lookup"><span data-stu-id="7656a-112">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="7656a-113">Yanıtınızı tutmak için $m $ qubits ikinci bir kaydına bakarak bu sorunlardan her ikisiyle de ilgilenebiliriz.</span><span class="sxs-lookup"><span data-stu-id="7656a-113">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="7656a-114">Ardından, Oracle 'ın tüm hesaplama tabanlı durumlarında etkisini tanımlayacağız: tüm $x \ \\{0, 1\\} ^ n $ ve $y \ \\{0, 1\\} ^ d $,</span><span class="sxs-lookup"><span data-stu-id="7656a-114">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

<span data-ttu-id="7656a-115">$ $ \begin{hizalaması} O (\ket{x} \otimes \ket{yı}) = \ket{x} \otimes \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="7656a-115">$$ \begin{align} O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="7656a-116">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="7656a-116">\end{align} $$</span></span>

<span data-ttu-id="7656a-117">Şimdi $O = O ^ \dağılım $, bu nedenle, daha önceki sorunları çöztik.</span><span class="sxs-lookup"><span data-stu-id="7656a-117">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
> <span data-ttu-id="7656a-118">Bu $O = O ^ {\abger} $ olduğunu görmek için, $O ^ 2 = \cıvadone $ $a \oplus b \ OPG $ = a $, her $a için, b \ in \{0, 1\}$ olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="7656a-118">To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
> <span data-ttu-id="7656a-119">Sonuç olarak, \ket{x} \ket{y \oplus f (x)} = \ket{x} \ket{y \oplus f (x) \oplus f (x)} = \ket{x} \ket{i} $ $O.</span><span class="sxs-lookup"><span data-stu-id="7656a-119">As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="7656a-120">Bu şekilde, her hesaplama tabanlı durum $ \ket{x}\ket{y} $ için Oracle bu şekilde tanımlanması, $O $ ' in diğer tüm durumları için nasıl davrandığını da tanımlar.</span><span class="sxs-lookup"><span data-stu-id="7656a-120">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="7656a-121">Bu, tüm hisse işlemleri gibi $O $ ' nin, üzerinde çalıştığı durumda doğrusal olduğunu bulmanızdan hemen sonra takip eder.</span><span class="sxs-lookup"><span data-stu-id="7656a-121">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="7656a-122">Örneğin, $H \demet{0} = \ket{+} $ ve $H \ket{1} = \tus{-}$ tarafından tanımlanan Hadamard işlemini göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="7656a-122">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="7656a-123">$ \Ket{+} $ üzerinde $H $ ' nin nasıl çalıştığını öğrenmek istiyorsanız, bu $H $ ' nin doğrusal olduğunu,</span><span class="sxs-lookup"><span data-stu-id="7656a-123">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

<span data-ttu-id="7656a-124">$ $ \begin{hizalaması} H\ket {+} & = \frac{1}{\sqrt{2}} H (\ket{0} + \ayraç{1}) = \frac{1}{\sqrt{2}} (H\demet{0} + H\demet{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ ayraç {+} + \ ayraç{-}) = \frac12 (\demet{0} + \ ayraç{1} + \ ayraç{0}-\ayraç{1}) = \demet{0}.</span><span class="sxs-lookup"><span data-stu-id="7656a-124">$$ \begin{align} H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
<span data-ttu-id="7656a-125">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="7656a-125">\end{align} $$</span></span>

<span data-ttu-id="7656a-126">Oracle $O $ ' mimizin tanımlanması durumunda benzer bir şekilde $ \ket{\psı} $ $n + m $ qubits olarak yazılabilir</span><span class="sxs-lookup"><span data-stu-id="7656a-126">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

<span data-ttu-id="7656a-127">$ $ \begin{hizalaması} \ket{\psı} & = \sum_{x \\\{0, 1\\} ^ n, y \in \\{0, 1\\} ^ ı} \Alpha (x, y) \ket{x} \ket{i} \end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="7656a-127">$$ \begin{align} \ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \end{align} $$</span></span>

<span data-ttu-id="7656a-128">$ \Alpha: \\{0, 1\\} ^ n \times \\{0, 1\\} ^ d \ to \mathbb{C} $, $ \ket{\psı} $ durumunun katsayılarını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="7656a-128">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="7656a-129">Yani</span><span class="sxs-lookup"><span data-stu-id="7656a-129">Thus,</span></span>

<span data-ttu-id="7656a-130">$ $ \begin{hizalaması} O \ket{\psı} & = O \sum_{x \\\{0, 1\\} ^ n, y \ \\{0, 1\\} ^ ı} \Alpha (x, y) \ket{x} \ket{yı} \\\\ & = \sum_{x \\\{0 , 1\\} ^ n, y \ \\{0, 1\\} ^ m} \Alpha (x, y) O \ket{x} \ket{yı} \\\\ & = \sum_{x \In \\{0, 1\\} ^ n, y \ ın \\{0 , 1\\} ^ e} \alfa (x, y) \ket{x} \ket{y \ OPLUS f (x)}.</span><span class="sxs-lookup"><span data-stu-id="7656a-130">$$ \begin{align} O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="7656a-131">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="7656a-131">\end{align} $$</span></span>

## <a name="phase-oracles"></a><span data-ttu-id="7656a-132">Phase Oracles</span><span class="sxs-lookup"><span data-stu-id="7656a-132">Phase oracles</span></span>
<span data-ttu-id="7656a-133">Alternatif olarak, $O $ girişine göre bir _aşama_ uygulayarak bir Oracle $O $ ' a $f $ ' i kodlayabiliriz.</span><span class="sxs-lookup"><span data-stu-id="7656a-133">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$.</span></span>
<span data-ttu-id="7656a-134">Örneğin, $ $ \begin{hizalaması} O \ket{x} = (-1) ^ {f (x)} \ket{x} gibi $O $ tanımlayabiliriz.</span><span class="sxs-lookup"><span data-stu-id="7656a-134">For instance, we might define $O$ such that $$ \begin{align} O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
<span data-ttu-id="7656a-135">\end{hizalaması} $ $ bir evre, başlangıçta hesaplama tabanlı bir durum $ \ket{x} $ içinde bir yazmaç üzerinde işlem yaparken, bu aşama genel bir aşamadır ve bu nedenle observable değildir.</span><span class="sxs-lookup"><span data-stu-id="7656a-135">\end{align} $$ If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="7656a-136">Ancak bu tür bir Oracle, bir üst konuma veya denetimli bir işleme uygulandığında çok güçlü bir kaynak olabilir.</span><span class="sxs-lookup"><span data-stu-id="7656a-136">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="7656a-137">Örneğin, $f $ bir tek qubit işlevi için bir Phase Orcale $O _F $ düşünün.</span><span class="sxs-lookup"><span data-stu-id="7656a-137">For example, consider a phase orcale $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="7656a-138">Ardından, $ $ \begin{hizalaması} O_f \ket{+} & = O_f (\demet{0} + \ayraç{1})/\sqrt{2} \\\\ & = ((-1) ^ {f (0)} \demet{0} + (-1) ^ {f (1)} \ayraç{1})/\sqrt{2} \\\\ & = (-1) ^ {f ( 0)} (\ket{0} + (-1) ^ {f (1)-f (0)} \ayraç{1})/\sqrt{2} \\\\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket{+}.</span><span class="sxs-lookup"><span data-stu-id="7656a-138">Then, $$ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\ & = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
<span data-ttu-id="7656a-139">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="7656a-139">\end{align} $$</span></span>

<span data-ttu-id="7656a-140">Daha genel olarak, Oracles görünümlerinin her ikisi de yalnızca tek bir bit yerine gerçek sayılar döndüren klasik işlevleri temsil edecek şekilde ayarlanabilir.</span><span class="sxs-lookup"><span data-stu-id="7656a-140">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="7656a-141">Oracle 'ı uygulamak için en iyi yolu seçmek, bu Oracle 'ın belirli bir algoritma içinde nasıl kullanılacağına bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="7656a-141">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="7656a-142">Örneğin, [Deutsch-Jozsa algoritması](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) , Oracle 'ın birinci şekilde uygulandığı, [Grover 'in algoritması](https://en.wikipedia.org/wiki/Grover's_algorithm) ikinci şekilde uygulanan Oracle 'ı temel alır.</span><span class="sxs-lookup"><span data-stu-id="7656a-142">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="7656a-143">Daha fazla ayrıntı için [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465)' deki tartışmayı öneririz.</span><span class="sxs-lookup"><span data-stu-id="7656a-143">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
