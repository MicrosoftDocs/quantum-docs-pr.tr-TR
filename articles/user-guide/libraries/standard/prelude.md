---
title: QDK 'deki iç işlemler ve işlevler
description: Klasik işlevler ve Unitary, döndürme ve ölçüm işlemleri dahil olmak üzere QDK 'deki iç işlemler ve işlevler hakkında bilgi edinin.
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 283504a5f5635a4996c804e514a6f52eb4966d22
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868449"
---
# <a name="the-prelude"></a><span data-ttu-id="dd0d7-103">Prelude dili</span><span class="sxs-lookup"><span data-stu-id="dd0d7-103">The Prelude</span></span> #

<span data-ttu-id="dd0d7-104">Q#Hisse geliştirme paketine dahil edilen derleyici ve hedef makineler, ' de hisse programları yazılırken kullanılabilecek bir dizi iç işlev ve işlem sağlar Q# .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-104">The Q# compiler and the target machines included with the Quantum Development Kit provide a set of intrinsic functions and operations that can be used when writing quantum programs in Q#.</span></span>

## <a name="intrinsic-operations-and-functions"></a><span data-ttu-id="dd0d7-105">İç Işlemler ve Işlevler</span><span class="sxs-lookup"><span data-stu-id="dd0d7-105">Intrinsic Operations and Functions</span></span> ##

<span data-ttu-id="dd0d7-106">Standart kitaplıkta tanımlanan iç işlemler kabaca birkaç kategoriden birine girer:</span><span class="sxs-lookup"><span data-stu-id="dd0d7-106">The intrinsic operations defined in the standard library roughly fall into one of several categories:</span></span>

- <span data-ttu-id="dd0d7-107">Ad alanında toplanan, önemli klasik işlevler <xref:microsoft.quantum.core> .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-107">Essential classical functions, collected in the <xref:microsoft.quantum.core> namespace.</span></span>
- <span data-ttu-id="dd0d7-108">[Clienfford ve $T $ Gates 'ten oluşan unitfıerlerini](xref:microsoft.quantum.concepts.qubit)temsil eden işlemler.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-108">Operations representing unitaries composed of [Clifford and $T$ gates](xref:microsoft.quantum.concepts.qubit).</span></span>
- <span data-ttu-id="dd0d7-109">Çeşitli işleçlerle ilgili döndürmeler temsil eden işlemler.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-109">Operations representing rotations about various operators.</span></span>
- <span data-ttu-id="dd0d7-110">Ölçümleri uygulayan işlemler.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-110">Operations implementing measurements.</span></span>

<span data-ttu-id="dd0d7-111">Clienfford + $T $ Gate kümesi, hisse bilgi işlem için [evrensel](xref:microsoft.quantum.concepts.multiple-qubits) olduğundan, bu işlemler, eksik küçük bir hata içinde yaklaşık bir hisse algoritması uygulamak için yeterli olacaktır.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-111">Since the Clifford + $T$ gate set is [universal](xref:microsoft.quantum.concepts.multiple-qubits) for quantum computing, these operations suffice to approximately implement any quantum algorithm within negligibly small error.</span></span>
<span data-ttu-id="dd0d7-112">Rosalar da sunarak, Q# Programcının tek qubit Unitary ve CNOT kapısı kitaplığı içinde çalışmasına izin verir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-112">By providing rotations as well, Q# allows the programmer to work within the single qubit unitary and CNOT gate library.</span></span> <span data-ttu-id="dd0d7-113">Bu kitaplık, programcının Clienfford + $T $ ayrıştırma 'yı doğrudan hızlı bir şekilde ifade ettiğinden ve tek qubit birimlere Clienfford ve $T $ Gates 'e (daha fazla bilgi için bkz. [buraya](xref:microsoft.quantum.more-information) bakın) yönelik yüksek verimli yöntemler içerdiğinden düşünmek çok daha kolay.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-113">This library is much easier to think about because it does not  require the programmer to directly express the Clifford + $T$ decomposition and because highly efficient methods exist for compiling single qubit unitaries into Clifford and $T$ gates (see [here](xref:microsoft.quantum.more-information) for more information).</span></span>

<span data-ttu-id="dd0d7-114">Mümkün olduğu durumlarda, ilgeler üzerinde işlem yapan ve `Controlled` hedef makinenin uygun Ayrıştırma işlemini gerçekleştirmesini sağlayan, bu, ilgeler 'yi uygulamaya izin veren bir işlem.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-114">Where possible, the operations defined in the prelude which act on qubits allow for applying the `Controlled` variant, such that the target machine will perform the appropriate decomposition.</span></span>

<span data-ttu-id="dd0d7-115">Prelude 'nun bu bölümünde tanımlanan işlevlerin ve işlemlerin birçoğu @"microsoft.quantum.intrinsic" ad alanında, çoğu Q# kaynak dosyanın `open Microsoft.Quantum.Intrinsic;` ilk ad alanı bildiriminden hemen sonra gelen bir yönergesi olacaktır.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-115">Many of the functions and operations defined in this portion of the prelude are in the @"microsoft.quantum.intrinsic" namespace, such that most Q# source files will have an `open Microsoft.Quantum.Intrinsic;` directive immediately following the initial namespace declaration.</span></span>
<span data-ttu-id="dd0d7-116"><xref:microsoft.quantum.core>Ad alanı otomatik olarak açılır, böylece gibi işlevler <xref:microsoft.quantum.core.length> hiç bir beyan olmadan kullanılabilir `open` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-116">The <xref:microsoft.quantum.core> namespace is automatically opened, so that functions such as <xref:microsoft.quantum.core.length> can be used without an `open` statement at all.</span></span>

### <a name="common-single-qubit-unitary-operations"></a><span data-ttu-id="dd0d7-117">Yaygın tek qubit Unitary Işlemleri</span><span class="sxs-lookup"><span data-stu-id="dd0d7-117">Common Single-Qubit Unitary Operations</span></span> ###

<span data-ttu-id="dd0d7-118">Prelude, birçok yaygın [tek qubit işlemini](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)de tanımlar.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-118">The prelude also defines many common [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>
<span data-ttu-id="dd0d7-119">Bu işlemlerin tümü hem `Controlled` hem de `Adjoint` funlarına izin verir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-119">All of these operations allow both the `Controlled` and `Adjoint` functors.</span></span>

#### <a name="pauli-operators"></a><span data-ttu-id="dd0d7-120">Pauli Işleçleri</span><span class="sxs-lookup"><span data-stu-id="dd0d7-120">Pauli Operators</span></span> ####

<span data-ttu-id="dd0d7-121"><xref:microsoft.quantum.intrinsic.x>Işlem Pauli $X $ işlecini uygular.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-121">The <xref:microsoft.quantum.intrinsic.x> operation implements the Pauli $X$ operator.</span></span>
<span data-ttu-id="dd0d7-122">Bu, bazen ağ geçidi olarak da bilinir `NOT` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-122">This is sometimes also known as the `NOT` gate.</span></span>
<span data-ttu-id="dd0d7-123">İmza içeriyor `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-123">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="dd0d7-124">Tek qubit Unitary öğesine karşılık gelir:</span><span class="sxs-lookup"><span data-stu-id="dd0d7-124">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="dd0d7-125">\begin{Equation} \begin{bmatrix} 0 & 1 \\ \\ % fixme: Bu şu anda quadwhack Hack 'ı kullanıyor.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-125">\begin{equation} \begin{bmatrix} 0 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="dd0d7-126">1 & 0 \ End{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="dd0d7-126">1 & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="dd0d7-127"><xref:microsoft.quantum.intrinsic.y>Işlem Pauli $Y $ işlecini uygular.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-127">The <xref:microsoft.quantum.intrinsic.y> operation implements the Pauli $Y$ operator.</span></span>
<span data-ttu-id="dd0d7-128">İmza içeriyor `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-128">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="dd0d7-129">Tek qubit Unitary öğesine karşılık gelir:</span><span class="sxs-lookup"><span data-stu-id="dd0d7-129">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="dd0d7-130">\begin{Equation} \begin{bmatrix} 0 &-ı \\ \\ % fixme: Bu şu anda quadwhack Hack 'ı kullanıyor.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-130">\begin{equation} \begin{bmatrix} 0 & -i \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="dd0d7-131">ı & 0 \ End{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="dd0d7-131">i & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="dd0d7-132"><xref:microsoft.quantum.intrinsic.z>Işlem Pauli $Z $ işlecini uygular.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-132">The <xref:microsoft.quantum.intrinsic.z> operation implements the Pauli $Z$ operator.</span></span>
<span data-ttu-id="dd0d7-133">İmza içeriyor `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-133">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="dd0d7-134">Tek qubit Unitary öğesine karşılık gelir:</span><span class="sxs-lookup"><span data-stu-id="dd0d7-134">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="dd0d7-135">\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % fixme: Bu şu anda quadwhack Hack 'ı kullanıyor.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-135">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="dd0d7-136">0 &-1 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="dd0d7-136">0 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="dd0d7-137">Aşağıda [Bloch Sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) ile eşleştirilmiş olan bu dönüşümleri görtik (her durumda döndürme ekseni kırmızı vurgulanır):</span><span class="sxs-lookup"><span data-stu-id="dd0d7-137">Below we see these transformations mapped to the [Bloch sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (the rotation axis in each case is highlighted red):</span></span>

![Bloch sphere üzerine eşlenmiş Pauli işlemleri](~/media/prelude_pauliBloch.png)

<span data-ttu-id="dd0d7-139">Aynı Pauli Gate 'in aynı qubit 'e iki kez uygulanması işlemi iptal eder (bundan böyle, daha sonra başlangıç noktasına geri dönerek, bir 2π (360 °) yüzeyi üzerinde tam bir döndürme gerçekleştirdiniz.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-139">It is important to note that applying the same Pauli gate twice to the same qubit cancels out the operation (because you have now performed a full rotation of 2π (360°) over the surface to the Bloch Sphere, thus arriving back at the starting point).</span></span> <span data-ttu-id="dd0d7-140">Bu, bize aşağıdaki kimliğe getirir:</span><span class="sxs-lookup"><span data-stu-id="dd0d7-140">This brings us to the following identity:</span></span>

<span data-ttu-id="dd0d7-141">$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \ cıvabitti $ $</span><span class="sxs-lookup"><span data-stu-id="dd0d7-141">$$ X^2=Y^2=Z^2=\boldone $$</span></span>

<span data-ttu-id="dd0d7-142">Bu, Bloch Sphere üzerinde görselleştirmelere neden olabilir:</span><span class="sxs-lookup"><span data-stu-id="dd0d7-142">This can be visualised on the Bloch sphere:</span></span>

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a><span data-ttu-id="dd0d7-144">Diğer tek qubit Clienffords</span><span class="sxs-lookup"><span data-stu-id="dd0d7-144">Other Single-Qubit Cliffords</span></span> ####

<span data-ttu-id="dd0d7-145"><xref:microsoft.quantum.intrinsic.h>Işlem Hadamard geçidini uygular.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-145">The <xref:microsoft.quantum.intrinsic.h> operation implements the Hadamard gate.</span></span>
<span data-ttu-id="dd0d7-146">Bu, hedef qubit 'in Pauli $X $ ve $Z $ eksenlerinin $H {0} \tus= \ket{+} \mathrel{: =} ( {0} \tus+ \ket {1} )/\sqrt {2} $ ve $H \ket{+} = \ket {0} $ olduğunu birbirine dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-146">This interchanges the Pauli $X$ and $Z$ axes of the target qubit, such that $H\ket{0} = \ket{+} \mathrel{:=} (\ket{0} + \ket{1}) / \sqrt{2}$ and $H\ket{+} = \ket{0}$.</span></span>
<span data-ttu-id="dd0d7-147">İmzaya sahiptir `(Qubit => Unit is Adj + Ctl)` ve tek qubit Unitary öğesine karşılık gelir:</span><span class="sxs-lookup"><span data-stu-id="dd0d7-147">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="dd0d7-148">\begin{Equation} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ % fixme: Bu şu anda quadwhack Hack 'ı kullanıyor.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-148">\begin{equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="dd0d7-149">1 &-1 \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="dd0d7-149">1 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="dd0d7-150">Hadamard geçidi, $ \ket {0} $ ve $ \ket $ durumlarının bir üst konumunu oluşturmak için kullanılabilir {1} .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-150">The Hadamard gate is particularly important as it can be used to create a superposition of the $\ket{0}$ and $\ket{1}$ states.</span></span> <span data-ttu-id="dd0d7-151">Bloch Sphere gösteriminde, $ \ Pi $ radyan ($ 180 ^ \circ $) x ekseni etrafında $ \ket{\psı} $ öğesinin bir dönüşü olarak düşünmek en kolay yoldur. Bu, x/pi/2 $ radyanlara ($ 90 ^ \circ $) göre y ekseni etrafında (saat yönünde) bir döndürme işlemi izlemelidir:</span><span class="sxs-lookup"><span data-stu-id="dd0d7-151">In the Bloch sphere representation, it is easiest to think of this as a rotation of $\ket{\psi}$ around the x-axis by $\pi$ radians ($180^\circ$) followed by a (clockwise) rotation around the y-axis by $\pi/2$ radians ($90^\circ$):</span></span>

![Hadamard işlemi Bloch sphere üzerine eşlendi](~/media/prelude_hadamardBloch.png)

<span data-ttu-id="dd0d7-153"><xref:microsoft.quantum.intrinsic.s>İşlem, $S $ aşama kapısını uygular.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-153">The <xref:microsoft.quantum.intrinsic.s> operation implements the phase gate $S$.</span></span>
<span data-ttu-id="dd0d7-154">Bu, Pauli $Z $ işleminin matris kare köküdür.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-154">This is the matrix square root of the Pauli $Z$ operation.</span></span>
<span data-ttu-id="dd0d7-155">Yani, $S ^ 2 = Z $.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-155">That is, $S^2 = Z$.</span></span>
<span data-ttu-id="dd0d7-156">İmzaya sahiptir `(Qubit => Unit is Adj + Ctl)` ve tek qubit Unitary öğesine karşılık gelir:</span><span class="sxs-lookup"><span data-stu-id="dd0d7-156">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="dd0d7-157">\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % fixme: Bu şu anda quadwhack Hack 'ı kullanıyor.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-157">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="dd0d7-158">0 & ı \end{bmatrix} \end{Equation}</span><span class="sxs-lookup"><span data-stu-id="dd0d7-158">0 & i \end{bmatrix} \end{equation}</span></span>

#### <a name="rotations"></a><span data-ttu-id="dd0d7-159">Rotasyonlar</span><span class="sxs-lookup"><span data-stu-id="dd0d7-159">Rotations</span></span> ####

<span data-ttu-id="dd0d7-160">Yukarıdaki Pauli ve Clifford işlemlerine ek olarak, Q# Prelude, döndürmeler ifade etmenin çeşitli yollarını sağlar.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-160">In addition to the Pauli and Clifford operations above, the Q# prelude provides a variety of ways of expressing rotations.</span></span>
<span data-ttu-id="dd0d7-161">[Tek qubit işlemlerinde](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)açıklandığı gibi, döndürme özelliği, hisse algoritması için kritik öneme sahiptir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-161">As described in [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), the ability to rotate is critical to quantum algorithms.</span></span>

<span data-ttu-id="dd0d7-162">$H $ ve $T $ kapıları kullanarak herhangi bir tek qubit işlemi hızlı bir şekilde ifade edebiliyoruz; $H burada \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ % fixme: Bu, şu anda dörtlü geri Whack Hack 'ı kullanıyor.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-162">We start by recalling that we can express any single-qubit operation using the $H$ and $T$ gates, where $H$ is the Hadamard operation, and where \begin{equation} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quad back whack hack.</span></span>
<span data-ttu-id="dd0d7-163">0 & e ^ {i \ Pi/4} \end{bmatrix} \end{Equation} bu, <xref:microsoft.quantum.intrinsic.s> işlemin karekökünü, yani $T ^ 2 = S $ olur.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-163">0 & e^{i \pi / 4} \end{bmatrix} \end{equation} This is the square root of the <xref:microsoft.quantum.intrinsic.s> operation, such that $T^2 = S$.</span></span>
<span data-ttu-id="dd0d7-164">$T $ Gate, işlem tarafından uygulanır <xref:microsoft.quantum.intrinsic.t> ve `(Qubit => Unit is Adj + Ctl)` tek bir-qubit üzerinde Unitary işlemi olduğunu belirten imzaya sahiptir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-164">The $T$ gate is in turn implemented by the <xref:microsoft.quantum.intrinsic.t> operation, and has signature `(Qubit => Unit is Adj + Ctl)`, indicating that it is a unitary operation on a single-qubit.</span></span>

<span data-ttu-id="dd0d7-165">Bu, herhangi bir rastgele tek qubit işlemi açıklamaya yetecek olsa da, farklı hedef makineler Pauli işleçleri hakkında daha etkili temsiller olabilir. bu nedenle, Prelude, bu tür döndürmeler için çeşitli yollar içerir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-165">Even though this is in principle sufficient to describe any arbitrary single-qubit operation, different target machines may have more efficient representations for rotations about Pauli operators, such that the prelude includes a variety of ways to convienently express such rotations.</span></span>
<span data-ttu-id="dd0d7-166">Bunların en temel değeri, <xref:microsoft.quantum.intrinsic.r> belirtilen Pauli ekseninin etrafında bir döndürme uygulayan işlemdir. \begin{Equation} R (\sigma, \fi) \mathrel{: =} \exp (-i \phi \ Sigma/2), \end{Equation}; burada $ \sigma $ bir Pauli işleci, $ \phi $ bir açı ve $ \exp $, matris üstel değerini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-166">The most basic of these is the <xref:microsoft.quantum.intrinsic.r> operation, which implements a rotation around a specified Pauli axis, \begin{equation} R(\sigma, \phi) \mathrel{:=} \exp(-i \phi \sigma / 2), \end{equation} where $\sigma$ is a Pauli operator, $\phi$ is an angle, and where $\exp$ represents the matrix exponential.</span></span>
<span data-ttu-id="dd0d7-167">`((Pauli, Double, Qubit) => Unit is Adj + Ctl)`Girişin ilk iki bölümü, Unitary işleci $R (\sigma, \fi) $ ' i belirtmek için gereken klasik bağımsız değişkenleri $ \sigma $ ve $ \phi $ olarak temsil eden imzaya sahiptir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-167">It has signature `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`, where the first two parts of the input represent the classical arguments $\sigma$ and $\phi$ needed to specify the unitary operator $R(\sigma, \phi)$.</span></span>
<span data-ttu-id="dd0d7-168">Türü tek qubit Unitary olan bir işlem elde etmek için $ \sigma $ ve $ \phi $ öğesini kısmen uygulayabiliriz.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-168">We can partially apply $\sigma$ and $\phi$ to obtain an operation whose type is that of a single-qubit unitary.</span></span>
<span data-ttu-id="dd0d7-169">Örneğin, `R(PauliZ, PI() / 4, _)` türü vardır `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-169">For example, `R(PauliZ, PI() / 4, _)` has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

> [!NOTE]
> <span data-ttu-id="dd0d7-170"><xref:microsoft.quantum.intrinsic.r>İşlem giriş açısını 2 ' ye böler ve-1 ile çarpar.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-170">The <xref:microsoft.quantum.intrinsic.r> operation divides the input angle by 2 and multiplies it by -1.</span></span>
> <span data-ttu-id="dd0d7-171">$Z $ döndürmeler için bu, $ \ket {0} $ eigenstate 'in $-\phi/$2 ile döndürüldüğü ve $ \ket $ eigenstate $ \phi/$2 tarafından döndürülerek $ \ket $ eigenstate 'in $ {1} {1} \ket $ eigenstate 'e göreli olarak $ \phi $ ile döndürüldüğü anlamına gelir {0} .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-171">For $Z$ rotations, this means that the $\ket{0}$ eigenstate is rotated by $-\phi / 2$ and the $\ket{1}$ eigenstate is rotated by $\phi / 2$, so that the $\ket{1}$ eigenstate is rotated by $\phi$ relative to the $\ket{0}$ eigenstate.</span></span>
>
> <span data-ttu-id="dd0d7-172">Bu, özellikle de `T` `R(PauliZ, PI() / 8, _)` ilgisiz [küresel bir aşamaya](xref:microsoft.quantum.glossary#global-phase)göre farklılık gösterir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-172">In particular, this means that `T` and `R(PauliZ, PI() / 8, _)` differ only by an irrelevant [global phase](xref:microsoft.quantum.glossary#global-phase).</span></span>
> <span data-ttu-id="dd0d7-173">Bu nedenle $T $, bazen $ \frac{\pi} {8} $-Gate olarak bilinir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-173">For this reason, $T$ is sometimes known as the $\frac{\pi}{8}$-gate.</span></span>
>
> <span data-ttu-id="dd0d7-174">Ayrıca, etrafında döndürme `PauliI` , $ \phi/$2 genel aşamasını uygular.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-174">Note also that rotating around `PauliI` simply applies a global phase of $\phi / 2$.</span></span> <span data-ttu-id="dd0d7-175">Bu tür aşamalar ilgisiz olsa da, [kavramsal belgelerde](xref:microsoft.quantum.concepts.qubit)olduğu gibi, denetlenen döndürmeler için de uygundur `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-175">While such phases are irrelevant, as argued in [the conceptual documents](xref:microsoft.quantum.concepts.qubit), they are relevant for controlled `PauliI` rotations.</span></span>

<span data-ttu-id="dd0d7-176">Hisse algoritmaları dahilinde, her zaman {\phi = \pi k/2 ^ n $ for \mathbb{Z} $ ve \mathbb{N} $ içinde $n \ $ adlı bazı $k \jyadic kesirleri olarak ifade etmek yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-176">Within quantum algorithms, it is often useful to express rotations as dyadic fractions, such that $\phi = \pi k / 2^n$ for some $k \in \mathbb{Z}$ and $n \in \mathbb{N}$.</span></span>
<span data-ttu-id="dd0d7-177"><xref:microsoft.quantum.intrinsic.rfrac>İşlem, bu kuralı kullanarak belirtilen Pauli ekseninin etrafında bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-177">The <xref:microsoft.quantum.intrinsic.rfrac> operation implements a rotation around a specified Pauli axis using this convention.</span></span>
<span data-ttu-id="dd0d7-178">Bu, <xref:microsoft.quantum.intrinsic.r> döndürme açısının, `Int` dyadic kesri olarak yorumlanan iki tür giriş olarak belirtildiğinden farklıdır.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-178">It differs from <xref:microsoft.quantum.intrinsic.r> in that the rotation angle is specified as two inputs of type `Int`, interpreted as a dyadic fraction.</span></span>
<span data-ttu-id="dd0d7-179">Bu nedenle, `RFrac` imzası vardır `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-179">Thus, `RFrac` has signature `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="dd0d7-180">Tek qubit Unitary $ \ exp (i \pı k \ Sigma/2 ^ n) $, burada $ \sigma $ ilk bağımsız değişkene karşılık gelen Pauli matrisi, $k $ ikinci bağımsız değişkendir ve $n $ üçüncü bağımsız değişkendir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-180">It implements the single-qubit unitary $\exp(i \pi k \sigma / 2^n)$, where $\sigma$ is the Pauli matrix corresponding to the first argument, $k$ is the second argument, and $n$ is the third argument.</span></span>
<span data-ttu-id="dd0d7-181">`RFrac(_,k,n,_)`ile aynıdır `R(_,-πk/2^n,_)` ; açının kesirin *negatifi* olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-181">`RFrac(_,k,n,_)` is the same as `R(_,-πk/2^n,_)`; note that the angle is the *negative* of the fraction.</span></span>

<span data-ttu-id="dd0d7-182"><xref:microsoft.quantum.intrinsic.rx>Işlem Pauli $X $ ekseninin etrafında bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-182">The <xref:microsoft.quantum.intrinsic.rx> operation implements a rotation around the Pauli $X$ axis.</span></span>
<span data-ttu-id="dd0d7-183">İmza içeriyor `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-183">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="dd0d7-184">`Rx(_, _)`, ile aynıdır `R(PauliX, _, _)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-184">`Rx(_, _)` is the same as `R(PauliX, _, _)`.</span></span>

<span data-ttu-id="dd0d7-185"><xref:microsoft.quantum.intrinsic.ry>Işlem Pauli $Y $ ekseninin etrafında bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-185">The <xref:microsoft.quantum.intrinsic.ry> operation implements a rotation around the Pauli $Y$ axis.</span></span>
<span data-ttu-id="dd0d7-186">İmza içeriyor `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-186">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="dd0d7-187">`Ry(_, _)`, ile aynıdır `R(PauliY,_ , _)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-187">`Ry(_, _)` is the same as `R(PauliY,_ , _)`.</span></span>

<span data-ttu-id="dd0d7-188"><xref:microsoft.quantum.intrinsic.rz>Işlem Pauli $Z $ ekseninin etrafında bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-188">The <xref:microsoft.quantum.intrinsic.rz> operation implements a rotation around the Pauli $Z$ axis.</span></span>
<span data-ttu-id="dd0d7-189">İmza içeriyor `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-189">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="dd0d7-190">`Rz(_, _)`, ile aynıdır `R(PauliZ, _, _)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-190">`Rz(_, _)` is the same as `R(PauliZ, _, _)`.</span></span>

<span data-ttu-id="dd0d7-191"><xref:microsoft.quantum.intrinsic.r1>İşlem, {1} $Z $ $-$1 eigenstate of $ \ket $ etrafında verilen miktarda bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-191">The <xref:microsoft.quantum.intrinsic.r1> operation implements a rotation by the given amount around $\ket{1}$, the $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="dd0d7-192">İmza içeriyor `((Double, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-192">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="dd0d7-193">`R1(phi,_)`, `R(PauliZ,phi,_)` ve ile aynıdır `R(PauliI,-phi,_)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-193">`R1(phi,_)` is the same as `R(PauliZ,phi,_)` followed by `R(PauliI,-phi,_)`.</span></span>

<span data-ttu-id="dd0d7-194"><xref:microsoft.quantum.intrinsic.r1frac>İşlem, Z = 1 eigenstate etrafında verilen miktarda kesirli bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-194">The <xref:microsoft.quantum.intrinsic.r1frac> operation implements a fractional rotation by the given amount around the Z=1 eigenstate.</span></span>
<span data-ttu-id="dd0d7-195">İmza içeriyor `((Int,Int, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-195">It has signature `((Int,Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="dd0d7-196">`R1Frac(k,n,_)`, `RFrac(PauliZ,-k.n+1,_)` ve ile aynıdır `RFrac(PauliI,k,n+1,_)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-196">`R1Frac(k,n,_)` is the same as `RFrac(PauliZ,-k.n+1,_)` followed by `RFrac(PauliI,k,n+1,_)`.</span></span>

<span data-ttu-id="dd0d7-197">Bloch sphere üzerine eşlenmiş bir döndürme işlemi (Bu örnekteki Pauli $Z $ ekseni etrafında) örneği aşağıda gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="dd0d7-197">An example of a rotation operation (around the Pauli $Z$ axis, in this instance) mapped onto the Bloch sphere is shown below:</span></span>

![Bloch sphere üzerine eşlenen döndürme işlemi](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a><span data-ttu-id="dd0d7-199">Multi-Qubitoperations</span><span class="sxs-lookup"><span data-stu-id="dd0d7-199">Multi-Qubit Operations</span></span> ####

<span data-ttu-id="dd0d7-200">Yukarıdaki tek qubit işlemlerine ek olarak, Prelude birçok multi-qubit işlemini de tanımlar.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-200">In addition to the single-qubit operations above, the prelude also defines several multi-qubit operations.</span></span>

<span data-ttu-id="dd0d7-201">İlk olarak, <xref:microsoft.quantum.intrinsic.cnot> işlem standart kontrollü bir- `NOT` kapısı, \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 & 0 \\ \\ \\ \\ & 1 & 0 & 0 & 0 &</span><span class="sxs-lookup"><span data-stu-id="dd0d7-201">First, the <xref:microsoft.quantum.intrinsic.cnot> operation performs a standard controlled-`NOT` gate, \begin{equation} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.</span></span>
<span data-ttu-id="dd0d7-202">\end{Equation} `((Qubit, Qubit) => Unit is Adj + Ctl)` , iki bireysel qubit üzerinde $ \operatorname{CNOT} $ davranır unitarily öğesini temsil eden imzaya sahip.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-202">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`, representing that $\operatorname{CNOT}$ acts unitarily on two individual qubits.</span></span>
<span data-ttu-id="dd0d7-203">`CNOT(q1, q2)`, ile aynıdır `(Controlled X)([q1], q2)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-203">`CNOT(q1, q2)` is the same as `(Controlled X)([q1], q2)`.</span></span>
<span data-ttu-id="dd0d7-204">`Controlled`Functor bir yazmaç üzerinde denetlemeye izin verdiğinden, `[q1]` yalnızca bir denetim isteytiğimiz belirten dizi değişmez değerini kullanırız.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-204">Since the `Controlled` functor allows for controlling on a register, we use the array literal `[q1]` to indicate that we want only the one control.</span></span>

<span data-ttu-id="dd0d7-205">Bu <xref:microsoft.quantum.intrinsic.ccnot> işlem, bazen Toffoli kapısı olarak da bilinen, düzenli olarak denetlenen bir kapısı gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-205">The <xref:microsoft.quantum.intrinsic.ccnot> operation performs doubly-controlled NOT gate, sometimes also known as the Toffoli gate.</span></span>
<span data-ttu-id="dd0d7-206">İmza içeriyor `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-206">It has signature `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="dd0d7-207">`CCNOT(q1, q2, q3)`, ile aynıdır `(Controlled X)([q1, q2], q3)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-207">`CCNOT(q1, q2, q3)` is the same as `(Controlled X)([q1, q2], q3)`.</span></span>

<span data-ttu-id="dd0d7-208"><xref:microsoft.quantum.intrinsic.swap>İşlem iki qubit 'in hisse durumlarını değiştirir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-208">The <xref:microsoft.quantum.intrinsic.swap> operation swaps the quantum states of two qubits.</span></span>
<span data-ttu-id="dd0d7-209">Diğer bir deyişle, Unitary matrisi \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 0 & \\ \\ 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix} uygular.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-209">That is, it implements the unitary matrix \begin{equation} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.</span></span>
<span data-ttu-id="dd0d7-210">\end{Equation} öğesinde imza var `((Qubit, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-210">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="dd0d7-211">`SWAP(q1,q2)`, `CNOT(q1, q2)` ve sonrasında ile eşdeğerdir `CNOT(q2, q1)` `CNOT(q1, q2)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-211">`SWAP(q1,q2)` is equivalent to `CNOT(q1, q2)` followed by `CNOT(q2, q1)` and then `CNOT(q1, q2)`.</span></span>

> [!NOTE]
> <span data-ttu-id="dd0d7-212">TAKAS kapısı, türünde bir değişkenin öğelerinin yeniden düzenleme işlemiyle aynı *değil* `Qubit[]` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-212">The SWAP gate is *not* the same as rearranging the elements of a variable with type `Qubit[]`.</span></span>
> <span data-ttu-id="dd0d7-213">Uygulama, `SWAP(q1, q2)` ve tarafından başvurulan qubits 'in durumuna bir değişikliğe neden olur `q1` `q2` , `let swappedRegister = [q2, q1];` ancak bu qubits 'e nasıl başvurduğumuz ile ilgili olarak yalnızca bunları etkiler.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-213">Applying `SWAP(q1, q2)` causes a change to the state of the qubits referred to by `q1` and `q2`, while `let swappedRegister = [q2, q1];` only affects how we refer to those qubits.</span></span>
> <span data-ttu-id="dd0d7-214">Üstelik, `(Controlled SWAP)([q0], (q1, q2))` öğeleri yeniden `SWAP` düzenleyerek temsil ettiğimiz üçüncü bir qubit durumunda koşullu olmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-214">Moreover, `(Controlled SWAP)([q0], (q1, q2))` allows for `SWAP` to be conditioned on the state of a third qubit, which we cannot represent by rearranging elements.</span></span>
> <span data-ttu-id="dd0d7-215">Fredkabağı kapısı olarak da bilinen denetimli-takas kapısı, tüm klasik hesaplamayı dahil etmek için yeterince güçlüdür.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-215">The controlled-SWAP gate, also known as the Fredkin gate, is powerful enough to include all classical computation.</span></span>

<span data-ttu-id="dd0d7-216">Son olarak, Prelude, Multi-qubit Pauli işleçlerinin üslerini temsil eden iki işlem sağlar.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-216">Finally, the prelude provides two operations for representing exponentials of multi-qubit Pauli operators.</span></span>
<span data-ttu-id="dd0d7-217"><xref:microsoft.quantum.intrinsic.exp>İşlem, çok-qubit Unitary \begin{Equation} \operatorname{exp} (\vec{\sigma}, \fi) \mathrel{: =} \exp\left (i \fi \ sigma_0 \otimes \ sigma_1 \otimes \cnoktalar \otimes \ sigma_n \right), \end{Equation}; burada $ \vec{\sigma} = (\ sigma_0, \ sigma_1, \noktalar, \ sigma_n) $ bir tek qubit Pauli işleçleri dizisi ve $ \phi $ bir açı.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-217">The <xref:microsoft.quantum.intrinsic.exp> operation performs a rotation based on a tensor product of Pauli matrices, as represented by the multi-qubit unitary \begin{equation} \operatorname{Exp}(\vec{\sigma}, \phi) \mathrel{:=} \exp\left(i \phi \sigma_0 \otimes \sigma_1 \otimes \cdots \otimes \sigma_n \right), \end{equation} where $\vec{\sigma} = (\sigma_0, \sigma_1, \dots, \sigma_n)$ is a sequence of single-qubit Pauli operators, and where $\phi$ is an angle.</span></span>
<span data-ttu-id="dd0d7-218">`Exp`Döndürme, imza içeren bir öğe dizisi olarak $ \vec{\sigma} $ öğesini temsil eder `Pauli` `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-218">The `Exp` rotation represents $\vec{\sigma}$ as an array of `Pauli` elements, such that it has signature `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="dd0d7-219"><xref:microsoft.quantum.intrinsic.expfrac>İşlem, yukarıda açıklanan dyadic kesir gösterimini kullanarak aynı dönüşü gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-219">The <xref:microsoft.quantum.intrinsic.expfrac> operation performs the same rotation, using the dyadic fraction notation discussed above.</span></span>
<span data-ttu-id="dd0d7-220">İmza içeriyor `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-220">It has signature `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

> [!WARNING]
> <span data-ttu-id="dd0d7-221">Pauli işleçleri için tencursor ürünlerinin üs öğeleri Pauli işleçleri 'nin üsünlerinin, tencursor ürünleriyle aynı değildir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-221">Exponentials of the tensor product of Pauli operators are not the same as tensor products of the exponentials of Pauli operators.</span></span>
> <span data-ttu-id="dd0d7-222">Yani, $e ^ {i (Z \otimes Z) \phi} \ne e ^ {i Z \ Phi} \otimes e ^ {i Z \ Phi} $.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-222">That is, $e^{i (Z \otimes Z) \phi} \ne e^{i Z \phi} \otimes e^{i Z \phi}$.</span></span>

### <a name="measurements"></a><span data-ttu-id="dd0d7-223">Ölçümler</span><span class="sxs-lookup"><span data-stu-id="dd0d7-223">Measurements</span></span> ###

<span data-ttu-id="dd0d7-224">Ölçtüğünde, ölçülen işlecin + 1 eigenvalue değeri bir sonuca karşılık gelir `Zero` ve-1 eigenvalue değeri bir sonuca karşılık gelir `One` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-224">When measuring, the +1 eigenvalue of the operator being measured corresponds to a `Zero` result, and the -1 eigenvalue to a `One` result.</span></span>

> [!NOTE]
> <span data-ttu-id="dd0d7-225">Bu kural tek görünebilir, ancak bu iki avantaja sahiptir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-225">While this convention might seem odd, it has two very nice advantages.</span></span>
> <span data-ttu-id="dd0d7-226">İlk olarak, $ \ket $ sonucunu gözlemleyerek {0} değer ile temsil `Result` edilir `Zero` , gözlemleme $ \ket {1} $, öğesine karşılık gelir `One` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-226">First, observing the outcome $\ket{0}$ is represented by the `Result` value `Zero`, while observing $\ket{1}$ corresponds to `One`.</span></span>
> <span data-ttu-id="dd0d7-227">İkinci olarak, bir sonuca karşılık gelen eigenvalue $ \lambda $ $r $ $ \lambda = (-1) ^ r $ olduğunu yazalım.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-227">Second, we can write out that the eigenvalue $\lambda$ corresponding to a result $r$ is $\lambda = (-1)^r$.</span></span>

<span data-ttu-id="dd0d7-228">Ölçüm işlemleri `Adjoint` ne ne de `Controlled` functor 'ı destekler.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-228">Measurement operations support neither the `Adjoint` nor the `Controlled` functor.</span></span>

<span data-ttu-id="dd0d7-229"><xref:microsoft.quantum.intrinsic.measure>İşlem, belirtilen Pauli işleçleri üründe bir veya daha fazla qubits 'in Birleşik ölçüsünü gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-229">The <xref:microsoft.quantum.intrinsic.measure> operation performs a joint measurement of one or more qubits in the specified product of Pauli operators.</span></span>
<span data-ttu-id="dd0d7-230">Pauli Array ve qubit dizisi farklı uzunluklardır, işlem başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-230">If the Pauli array and qubit array are different lengths, then the operation fails.</span></span>
<span data-ttu-id="dd0d7-231">`Measure`imza içeriyor `((Pauli[], Qubit[]) => Result)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-231">`Measure` has signature `((Pauli[], Qubit[]) => Result)`.</span></span>

<span data-ttu-id="dd0d7-232">Bir eklem ölçüsünün her bir qubit ayrı ayrı ölçüyle aynı olmadığına unutmayın.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-232">Note that a joint measurement is not the same as measuring each qubit individually.</span></span>
<span data-ttu-id="dd0d7-233">Örneğin, $ \ket {11} = \ket {1} \otimes {1} \Tus= X\otimes X \ket $ durumunu göz önünde bulundurun {00} .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-233">For example, consider the state $\ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.</span></span>
<span data-ttu-id="dd0d7-234">$Z _0 $ ve $Z _1 $ her biri ayrı ayrı, $r _0 = $1 ve $r _1 = $1 sonucunu elde ediyoruz.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-234">Measuring $Z_0$ and $Z_1$ each individually, we get the results $r_0 = 1$ and $r_1 = 1$.</span></span>
<span data-ttu-id="dd0d7-235">$Z _0 Z_1 $, ancak $ \ket $ değerinin pozitif olduğunu belirten _ {\textrm{Joint}} = $0 adlı tek bir $r sonuç elde ediyoruz {11} .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-235">Measuring $Z_0 Z_1$, however, we get the single result $r_{\textrm{joint}} = 0$, representing that the pairity of $\ket{11}$ is positive.</span></span>
<span data-ttu-id="dd0d7-236">Farklı, $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{Joint}}) $.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-236">Put differently, $(-1)^{r_0 + r_1} = (-1)^r_{\textrm{joint}})$.</span></span>
<span data-ttu-id="dd0d7-237">Kritik olarak, *yalnızca* bu ölçüden eşlik öğrendiğimiz için, pozitif eşlik için 2 2-qubit durumları, $ \ket {00} $ ve $ \tus$ arasındaki üst konumda temsil edilen tüm hisse bilgileri {11} korunur.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-237">Critically, since we *only* learn the parity from this measurement, any quantum information represented in the superposition between the two two-qubit states of positive parity, $\ket{00}$ and $\ket{11}$, is preserved.</span></span>
<span data-ttu-id="dd0d7-238">Hata düzeltmesini tartıştığımız için bu özellik daha sonra temel alınacaktır.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-238">This property will be essential later, as we discuss error correction.</span></span>

<span data-ttu-id="dd0d7-239">Kolaylık sağlaması için, Prelude, qubits 'i ölçmek için iki diğer işlem de sağlar.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-239">For convenience, the prelude also provides two other operations for measuring qubits.</span></span>
<span data-ttu-id="dd0d7-240">Birincisi, tek qubit ölçümleri gerçekleştirirken oldukça yaygın olduğundan, Prelude bu durum için bir toplu değer tanımlar.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-240">First, since performing single-qubit measurements is quite common, the prelude defines a shorthand for this case.</span></span>
<span data-ttu-id="dd0d7-241"><xref:microsoft.quantum.intrinsic.m>Işlem Pauli $Z $ işlecini tek bir qubit üzerinde ölçer ve imza içeriyor `(Qubit => Result)` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-241">The <xref:microsoft.quantum.intrinsic.m> operation measures the Pauli $Z$ operator on a single qubit, and has signature `(Qubit => Result)`.</span></span>
<span data-ttu-id="dd0d7-242">`M(q)`değerine eşdeğerdir `Measure([PauliZ], [q])` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-242">`M(q)` is equivalent to `Measure([PauliZ], [q])`.</span></span>

<span data-ttu-id="dd0d7-243"><xref:microsoft.quantum.measurement.multim>Pauli $Z $ işlecini her bir qubit dizisi üzerinde *ayrı olarak* ölçer ve her bir *array* `Result` qubit için elde edilen değer dizisini döndürür.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-243">The <xref:microsoft.quantum.measurement.multim> measures the Pauli $Z$ operator *separately* on each of an array of qubits, returning the *array* of `Result` values obtained for each qubit.</span></span>
<span data-ttu-id="dd0d7-244">Bazı durumlarda bu, iyileştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-244">In some cases this can be optimized.</span></span> <span data-ttu-id="dd0d7-245">İmza ( `Qubit[] => Result[])` .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-245">It has signature (`Qubit[] => Result[])`.</span></span>
<span data-ttu-id="dd0d7-246">`MultiM(qs)`eşittir:</span><span class="sxs-lookup"><span data-stu-id="dd0d7-246">`MultiM(qs)` is equivalent to:</span></span>

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a><span data-ttu-id="dd0d7-247">Uzantı Işlevleri ve Işlemler</span><span class="sxs-lookup"><span data-stu-id="dd0d7-247">Extension Functions and Operations</span></span> ##

<span data-ttu-id="dd0d7-248">Ayrıca, Prelude, kod içinde kullanılmak üzere .NET düzeyinde zengin bir matematik ve tür dönüştürme işlevleri tanımlar Q# .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-248">In addition, the prelude defines a rich set of mathematical and type conversion functions at the .NET level for use within Q# code.</span></span>
<span data-ttu-id="dd0d7-249">Örneğin, <xref:microsoft.quantum.math> ad alanı ve gibi faydalı işlemleri tanımlar <xref:microsoft.quantum.math.sin> <xref:microsoft.quantum.math.log> .</span><span class="sxs-lookup"><span data-stu-id="dd0d7-249">For instance, the <xref:microsoft.quantum.math> namespace defines useful operations such as <xref:microsoft.quantum.math.sin> and <xref:microsoft.quantum.math.log>.</span></span>
<span data-ttu-id="dd0d7-250">Hisse geliştirme seti tarafından sunulan uygulama klasik .NET temel sınıf kitaplığını kullanır ve bu nedenle hisse programları ve bunların klasik sürücüleri arasında ek bir iletişim gidiş gelişmesi içerebilir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-250">The implementation provided by the Quantum Development Kit uses the classical .NET base class library, and thus may involve an additional communications round trip between quantum programs and their classical drivers.</span></span>
<span data-ttu-id="dd0d7-251">Bu, yerel simülatör için bir sorun sunmadığından, bir hedef makine olarak uzak simülatör veya gerçek donanım kullanılırken bir performans sorunu olabilir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-251">While this does not present a problem for a local simulator, this can be a performance issue when using a remote simulator or actual hardware as a target machine.</span></span>
<span data-ttu-id="dd0d7-252">Yani, tek bir hedef makine, bu işlemleri söz konusu sistem için daha verimli olan sürümlerle geçersiz kılarak bu performans etkisini hafifletmeyebilir.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-252">That said, an individual target machine may mitigate this performance impact by overriding these operations with versions that are more efficient for that particular system.</span></span>

### <a name="math"></a><span data-ttu-id="dd0d7-253">Matematik</span><span class="sxs-lookup"><span data-stu-id="dd0d7-253">Math</span></span> ###

<span data-ttu-id="dd0d7-254"><xref:microsoft.quantum.math>Ad alanı, .net temel sınıf kitaplığının [ `System.Math` sınıfından](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1)birçok yararlı işlev sağlar.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-254">The <xref:microsoft.quantum.math> namespace provides many useful functions from the .NET base class library's [`System.Math` class](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1).</span></span>
<span data-ttu-id="dd0d7-255">Bu işlevler, diğer işlevlerle aynı şekilde kullanılabilir Q# :</span><span class="sxs-lookup"><span data-stu-id="dd0d7-255">These functions can be used in the same manner as any other Q# functions:</span></span>

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

<span data-ttu-id="dd0d7-256">.NET statik yönteminin bağımsız değişkenlerinin türüne göre aşırı yüklendiği yerlerde, karşılık gelen Q# işlev, girişinin türünü gösteren bir sonek ile açıklanmıştır:</span><span class="sxs-lookup"><span data-stu-id="dd0d7-256">Where a .NET static method has been overloaded based on the type of its arguments, the corresponding Q# function is annotated with a suffix indicating the type of its input:</span></span>

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a><span data-ttu-id="dd0d7-257">Bit düzeyinde Işlemler</span><span class="sxs-lookup"><span data-stu-id="dd0d7-257">Bitwise Operations</span></span> ###

<span data-ttu-id="dd0d7-258">Son olarak, <xref:microsoft.quantum.bitwise> ad alanı sayıların bit düzeyinde işleçler aracılığıyla işlenmesine yönelik çeşitli yararlı işlevler sağlar.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-258">Finally, the <xref:microsoft.quantum.bitwise> namespace provides several useful functions for manipulating integers through bitwise operators.</span></span>
<span data-ttu-id="dd0d7-259">Örneğin, <xref:microsoft.quantum.bitwise.parity> bir tamsayının bit düzeyinde eşlik sayısını başka bir tamsayı olarak döndürür.</span><span class="sxs-lookup"><span data-stu-id="dd0d7-259">For instance, <xref:microsoft.quantum.bitwise.parity> returns the bitwise parity of an integer as another integer.</span></span>
