---
title: Kuantum oracle’ları
description: İle nasıl çalışacağınızı ve başka bir algoritmaya girdi olarak kullanılan hisse Oracles, kara Box işlemlerini tanımlama hakkında bilgi edinin.
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
no-loc:
- $
- $
- $
- $
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
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 747c08df110f1f10efe552628d15e3500509b690
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269567"
---
# <a name="quantum-oracles"></a><span data-ttu-id="1f232-103">Hisse Oracles</span><span class="sxs-lookup"><span data-stu-id="1f232-103">Quantum Oracles</span></span>

<span data-ttu-id="1f232-104">Oracle $O $ , başka bir algoritmaya girdi olarak kullanılan "kara kutu" işlemidir.</span><span class="sxs-lookup"><span data-stu-id="1f232-104">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="1f232-105">Genellikle, bu gibi işlemler klasik bir işlev kullanılarak tanımlanır $f: \\ {0, 1 \\ } ^ n \- \\ {0, 1 \\ } ^ d, $ $n $ bit ikili bir giriş alır ve bir $m $ bit ikili çıktı üretir.</span><span class="sxs-lookup"><span data-stu-id="1f232-105">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="1f232-106">Bunu yapmak için, belirli bir ikili girişi $x = (x_ {0 } , X_ {1 } , \noktalar, X_ {n-1 } ) $) göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="1f232-106">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="1f232-107">Qubit durumları $ \ket { \ VEC{x } } = \ket{X_ {0 } } \otimes \ket{X_ {1 } } \otimes \cnoktalar \otimes \ket{X_ {n-1 } } $ olarak etiketliyoruz.</span><span class="sxs-lookup"><span data-stu-id="1f232-107">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="1f232-108">İlk $ \ket } olarak, {x = \ket{f (x)} $ $O bir $O tanımlamaya çalışır, ancak bu birkaç soruna neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="1f232-108">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="1f232-109">İlk olarak, $f $ farklı bir giriş ve çıkış boyutuna sahip olabilir ($n \ne m $ ), bu nedenle $O uygulamak, $ kayıttaki qubit sayısını değiştirebilir.</span><span class="sxs-lookup"><span data-stu-id="1f232-109">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="1f232-110">İkinci olarak, $n = m olsa bile $ , işlev ters çevrilebilir olmayabilir: bazı $x \ne y için $f (x) = f (y) $ $ , sonra $O \ket {x } = O \ket {y } $, ancak $O ^ \hanger o { \ket x } \ne o ^ \hanger o \ket {y } $.</span><span class="sxs-lookup"><span data-stu-id="1f232-110">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="1f232-111">Bu, ^ \dağılım $O adjoint işlemini oluşturmayamayacağız $ ve Oracles için tanımlanmış bir adjoint 'ın olması anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="1f232-111">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="1f232-112">Bir Oracle 'ı hesaplama tabanlı durumlar üzerinde etkile tanımlama</span><span class="sxs-lookup"><span data-stu-id="1f232-112">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="1f232-113">Bu sorunlardan her ikisi de $ cevaplarımızı tutmak için $m qubits 'in ikinci bir kaydına bakarak ilgilenebiliriz.</span><span class="sxs-lookup"><span data-stu-id="1f232-113">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="1f232-114">Daha sonra, Oracle 'ın tüm hesaplama tabanlı durumlarında etkisini tanımlayacağız: tüm $x \< \\ 0, 1 \\ } ^ n $ ve $y \in \\ {0, 1 \\ } ^ d $ ,</span><span class="sxs-lookup"><span data-stu-id="1f232-114">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

<span data-ttu-id="1f232-115">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="1f232-115">$$ \begin{align}</span></span>
    <span data-ttu-id="1f232-116">O (\ket{x } \otimes \ket{y } ) = \ket{x } \otimes \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="1f232-116">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="1f232-117">\end{align}</span><span class="sxs-lookup"><span data-stu-id="1f232-117">\end{align}</span></span>
$$

<span data-ttu-id="1f232-118">Şimdi, oluşturma ile birlikte $O = O ^ \dağılım $ , bu nedenle daha önceki sorunlardan her ikisi çözümlendik.</span><span class="sxs-lookup"><span data-stu-id="1f232-118">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
> <span data-ttu-id="1f232-119">Bu $O = O ^ {\dağılım $ olduğunu görmek için } $O, $ tüm $a < \ OPLUS b \oplus b = a $a $ , b \ in \{ 0, 1 \} $.</span><span class="sxs-lookup"><span data-stu-id="1f232-119">To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
> <span data-ttu-id="1f232-120">Sonuç olarak, \ket{x } \ket{y \oplus f (x)} = \ket{x } \ket{y \oplus f (x) \oplus f (x)} = \ket{x } \ket{y $ $O } .</span><span class="sxs-lookup"><span data-stu-id="1f232-120">As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="1f232-121">Bu şekilde, her hesaplama tabanlı durum için Oracle bu şekilde tanımlanması, her bir } } $ durum için $O nasıl davrandığını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="1f232-121">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="1f232-122">Bu, $ tüm hisse işlemleri gibi $O, üzerinde işlem yaptığı durumda doğrusal bir şekilde.</span><span class="sxs-lookup"><span data-stu-id="1f232-122">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="1f232-123">Örneğin, $H \ket{0 } = { \tus+} $ ve $H \ket{1 } = { \tus-} $ tarafından tanımlanan Hadamard işlemini göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="1f232-123">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="1f232-124">$H $ $ \ket +} $ üzerinde nasıl davranması gerektiğini öğrenmek istiyoruz, { Bu $H, $ Doğrusal olduğunu,</span><span class="sxs-lookup"><span data-stu-id="1f232-124">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

<span data-ttu-id="1f232-125">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="1f232-125">$$ \begin{align}</span></span>
<span data-ttu-id="1f232-126">H \ket { +} & = \frac{1 } {\sqrt{2 } } H (\ket{0 } + \ket{1 } ) = \frac{1 } {\sqrt{2 } } (h \ket {0 } + H \ket {1 } ) \\ \\ & = \frac{1 } {\sqrt{2 } } (\ket { +} + \ demet { -}) = \frac12 (\ket{0 } + \ket{1 } + \ket{0 } -\ket{1 } ) = \ket{0 } .</span><span class="sxs-lookup"><span data-stu-id="1f232-126">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
<span data-ttu-id="1f232-127">\end{align}</span><span class="sxs-lookup"><span data-stu-id="1f232-127">\end{align}</span></span>
$$

<span data-ttu-id="1f232-128">Oracle $O tanımlama durumunda $ benzer şekilde, { } $n + m qubitleri üzerinde herhangi bir durum $ \ket \ PSI $ $ şöyle yazılabilir.</span><span class="sxs-lookup"><span data-stu-id="1f232-128">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

<span data-ttu-id="1f232-129">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="1f232-129">$$ \begin{align}</span></span>
<span data-ttu-id="1f232-130">\ket { \ psi } & = \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \ in \\ {0, 1 \\ } ^ d } \ Alpha (x, y) \ket{x } \ket{y}</span><span class="sxs-lookup"><span data-stu-id="1f232-130">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
<span data-ttu-id="1f232-131">\end{align}</span><span class="sxs-lookup"><span data-stu-id="1f232-131">\end{align}</span></span>
$$

<span data-ttu-id="1f232-132">Burada $ \Alpha: \\ {0, 1 \\ } ^ n \times \\ {0, 1 \\ } ^ d \ to \mathbb{C } $, $ \tus\psı $ durumunun katsayılarını temsil eder { } .</span><span class="sxs-lookup"><span data-stu-id="1f232-132">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="1f232-133">Bu nedenle,</span><span class="sxs-lookup"><span data-stu-id="1f232-133">Thus,</span></span>

<span data-ttu-id="1f232-134">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="1f232-134">$$ \begin{align}</span></span>
<span data-ttu-id="1f232-135">O \ket \ { psi } & = O \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \ in \\ {0, 1 \\ } ^ m } \ Alpha (x, y) \ket{x } \ket{y } \\ \\ & = \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \ in \\ {0, 1 \\ } ^ m } \ Alpha (x, y) O \ket{x } \ket{y } \\ \\ & = \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \ içinde { \\ 0, 1 \\ } ^ m } \Alpha (x, y) \ket{x } \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="1f232-135">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="1f232-136">\end{align}</span><span class="sxs-lookup"><span data-stu-id="1f232-136">\end{align}</span></span>
$$

## <a name="phase-oracles"></a><span data-ttu-id="1f232-137">Phase Oracles</span><span class="sxs-lookup"><span data-stu-id="1f232-137">Phase oracles</span></span>
<span data-ttu-id="1f232-138">Alternatif olarak, $ $ $O girişine göre bir _aşama_ uygulayarak bir Oracle $O $f kodlayabiliriz $ .</span><span class="sxs-lookup"><span data-stu-id="1f232-138">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$.</span></span>
<span data-ttu-id="1f232-139">Örneğin, $ $ $ \begin{align gibi $O tanımlayabiliriz}</span><span class="sxs-lookup"><span data-stu-id="1f232-139">For instance, we might define $O$ such that $$ \begin{align}</span></span>
    <span data-ttu-id="1f232-140">O \ket{x } = (-1) ^ {f (x)} \ket{x } .</span><span class="sxs-lookup"><span data-stu-id="1f232-140">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
<span data-ttu-id="1f232-141">\end{align}</span><span class="sxs-lookup"><span data-stu-id="1f232-141">\end{align}</span></span>
<span data-ttu-id="1f232-142">$ $ Bir evre, başlangıçta hesaplama tabanlı bir durum $ \ket{x $ ile bir yazmaç üzerinde işlem yaptığı takdirde } Bu aşama genel bir aşamadır ve bu nedenle observable değildir.</span><span class="sxs-lookup"><span data-stu-id="1f232-142">$$ If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="1f232-143">Ancak bu tür bir Oracle, bir üst konuma veya denetimli bir işleme uygulandığında çok güçlü bir kaynak olabilir.</span><span class="sxs-lookup"><span data-stu-id="1f232-143">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="1f232-144">Örneğin, $ tek bir-qubit işlevi $f _F bir aşamayı veya $O düşünün $ .</span><span class="sxs-lookup"><span data-stu-id="1f232-144">For example, consider a phase orcale $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="1f232-145">Sonra, $ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="1f232-145">Then, $$ \begin{align}</span></span>
    <span data-ttu-id="1f232-146">O_f \ket { +} & = O_f (\ket{0 } + \ket{1 } )/\sqrt{2 } \\ \\ & = ((-1) ^ {f (0)} \ket{0 } + (-1) ^ {f (1)} \sı{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} (\ket{0 } + (-1) ^ {f (1)-f (0)} \ket{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} { \tus+}.</span><span class="sxs-lookup"><span data-stu-id="1f232-146">O_f \ket{+} & = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\ & = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
<span data-ttu-id="1f232-147">\end{align}</span><span class="sxs-lookup"><span data-stu-id="1f232-147">\end{align}</span></span>
$$

<span data-ttu-id="1f232-148">Daha genel olarak, Oracles görünümlerinin her ikisi de yalnızca tek bir bit yerine gerçek sayılar döndüren klasik işlevleri temsil edecek şekilde ayarlanabilir.</span><span class="sxs-lookup"><span data-stu-id="1f232-148">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="1f232-149">Oracle 'ı uygulamak için en iyi yolu seçmek, bu Oracle 'ın belirli bir algoritma içinde nasıl kullanılacağına bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="1f232-149">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="1f232-150">Örneğin, [Deutsch-Jozsa algoritması](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) , Oracle 'ın birinci şekilde uygulandığı, [Grover 'in algoritması](https://en.wikipedia.org/wiki/Grover's_algorithm) ikinci şekilde uygulanan Oracle 'ı temel alır.</span><span class="sxs-lookup"><span data-stu-id="1f232-150">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="1f232-151">Daha fazla ayrıntı için [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465)' deki tartışmayı öneririz.</span><span class="sxs-lookup"><span data-stu-id="1f232-151">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
