---
title: Hisse bilgi işlem sözlüğü
description: Hisse bilgi işlem için kullanılan ortak terimler, eylem ve nesnelerin bir sözlüğü.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
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
ms.openlocfilehash: ba4d171d84d808f082b919dcc6156d9c65df7c05
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275360"
---
# <a name="quantum-computing-glossary"></a><span data-ttu-id="63283-103">Hisse bilgi işlem sözlüğü</span><span class="sxs-lookup"><span data-stu-id="63283-103">Quantum computing glossary</span></span>

## <a name="adjoint"></a><span data-ttu-id="63283-104">Adjoint</span><span class="sxs-lookup"><span data-stu-id="63283-104">Adjoint</span></span>

<span data-ttu-id="63283-105">Bir [işlemin](xref:microsoft.quantum.glossary#operation)karmaşık eşleniği devrik.</span><span class="sxs-lookup"><span data-stu-id="63283-105">The complex conjugate transpose of an [operation](xref:microsoft.quantum.glossary#operation).</span></span> <span data-ttu-id="63283-106">Bir [Unitary](xref:microsoft.quantum.glossary#unitary-operator) işleci uygulayan işlemler için, adjoint işlemin tersidir ve bir dağılım simgesiyle belirtilir.</span><span class="sxs-lookup"><span data-stu-id="63283-106">For operations that implement a [unitary](xref:microsoft.quantum.glossary#unitary-operator) operator, the adjoint is the inverse of the operation and is indicated by a dagger symbol.</span></span> <span data-ttu-id="63283-107">Örneğin, işlem `U` Unitary işlecini $U temsil ediyorsa $ , `Adjoint U` $U ^ \ dağılım öğesini temsil eder $ .</span><span class="sxs-lookup"><span data-stu-id="63283-107">For example, if the operation `U` represents the unitary operator $U$, then `Adjoint U` represents $U^\dagger$.</span></span> <span data-ttu-id="63283-108">Daha fazla bilgi için bkz. [adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span><span class="sxs-lookup"><span data-stu-id="63283-108">For more information, see [Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span></span>

## <a name="ancilla"></a><span data-ttu-id="63283-109">Anek La</span><span class="sxs-lookup"><span data-stu-id="63283-109">Ancilla</span></span>

<span data-ttu-id="63283-110">Bir hisse bilgisayarı için geçici bellek görevi gören ve gerektiğinde ayrılan ve ayrılmış bir [qubit](xref:microsoft.quantum.glossary#qubit) .</span><span class="sxs-lookup"><span data-stu-id="63283-110">A [qubit](xref:microsoft.quantum.glossary#qubit) that serves as temporary memory for a quantum computer and is allocated and de-allocated as needed.</span></span>  <span data-ttu-id="63283-111">Daha fazla bilgi için bkz. [birden çok qubit](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="63283-111">For more information, see [Multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

## <a name="bell-state"></a><span data-ttu-id="63283-112">Zil durumu</span><span class="sxs-lookup"><span data-stu-id="63283-112">Bell state</span></span>

<span data-ttu-id="63283-113">İki qubit için en az dört adet en yüksek düzeyde, en önemli [hisse](xref:microsoft.quantum.glossary#quantum-state) [mandan](xref:microsoft.quantum.glossary#entanglement) biri.</span><span class="sxs-lookup"><span data-stu-id="63283-113">One of four specific maximally [entangled](xref:microsoft.quantum.glossary#entanglement) [quantum states](xref:microsoft.quantum.glossary#quantum-state) of two qubits.</span></span> <span data-ttu-id="63283-114">Dört durum tanımlanmıştır $ \ket { \ beta_ {ij } } = (\mathbb{I } \otimes X ^ iz ^ j) (\ket{00 } + \ket{11 } )/\sqrt{2 } $.</span><span class="sxs-lookup"><span data-stu-id="63283-114">The four states are defined $\ket{\beta_{ij}} = (\mathbb{I} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span> <span data-ttu-id="63283-115">Bir zil durumu, [EPR çifti](xref:microsoft.quantum.glossary#epr-pair)olarak da bilinir.</span><span class="sxs-lookup"><span data-stu-id="63283-115">A Bell state is also known as an [EPR pair](xref:microsoft.quantum.glossary#epr-pair).</span></span>

## <a name="bloch-sphere"></a><span data-ttu-id="63283-116">Bloch küre</span><span class="sxs-lookup"><span data-stu-id="63283-116">Bloch sphere</span></span>

<span data-ttu-id="63283-117">Üç boyutlu bir birim Sphere öğesinde nokta olarak tek[qubit](xref:microsoft.quantum.glossary#qubit) [hisse durumunun](xref:microsoft.quantum.glossary#quantum-state) grafik gösterimi.</span><span class="sxs-lookup"><span data-stu-id="63283-117">A graphical representation of a single-[qubit](xref:microsoft.quantum.glossary#qubit) [quantum state](xref:microsoft.quantum.glossary#quantum-state) as a point in a three-dimensional unit sphere.</span></span> <span data-ttu-id="63283-118">Daha fazla bilgi için bkz. [Bloch Sphere kullanarak qubits ve dönüşümleri görselleştirme](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="63283-118">For more information, see  [Visualizing Qubits and Transformations using the Bloch Sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>

## <a name="callable"></a><span data-ttu-id="63283-119">Çağrılabilir</span><span class="sxs-lookup"><span data-stu-id="63283-119">Callable</span></span>

<span data-ttu-id="63283-120">Q # dilinde bir [işlem](xref:microsoft.quantum.glossary#operation) veya [işlev](xref:microsoft.quantum.glossary#function) .</span><span class="sxs-lookup"><span data-stu-id="63283-120">An [operation](xref:microsoft.quantum.glossary#operation) or [function](xref:microsoft.quantum.glossary#function) in the Q# language.</span></span> <span data-ttu-id="63283-121">Daha fazla bilgi için bkz. [işlemler ve işlevler](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="63283-121">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="clifford-group"></a><span data-ttu-id="63283-122">Clienfford grubu</span><span class="sxs-lookup"><span data-stu-id="63283-122">Clifford group</span></span>

<span data-ttu-id="63283-123">[Şişörün](xref:microsoft.quantum.glossary#bloch-sphere) [Küçlerini ve Pauli işleçleri](xref:microsoft.quantum.glossary#pauli-operators)için efekt permütasyonları kaplayan işlem kümesi.</span><span class="sxs-lookup"><span data-stu-id="63283-123">The set of operations that occupy the octants of the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere) and effect permutations of the [Pauli operators](xref:microsoft.quantum.glossary#pauli-operators).</span></span> <span data-ttu-id="63283-124">Bunlar [$X $ ](xref:microsoft.quantum.intrinsic.x), [$Y $ ](xref:microsoft.quantum.intrinsic.y), [$Z $ ](xref:microsoft.quantum.intrinsic.z), [$H $ ](xref:microsoft.quantum.intrinsic.h) ve [$S $ ](xref:microsoft.quantum.intrinsic.s)işlemlerini içerir.</span><span class="sxs-lookup"><span data-stu-id="63283-124">These include the operations [$X$](xref:microsoft.quantum.intrinsic.x), [$Y$](xref:microsoft.quantum.intrinsic.y), [$Z$](xref:microsoft.quantum.intrinsic.z), [$H$](xref:microsoft.quantum.intrinsic.h) and [$S$](xref:microsoft.quantum.intrinsic.s).</span></span>

## <a name="controlled"></a><span data-ttu-id="63283-125">Tarafından</span><span class="sxs-lookup"><span data-stu-id="63283-125">Controlled</span></span>

<span data-ttu-id="63283-126">Hedef işlem için bir veya daha fazla [qubit](xref:microsoft.quantum.glossary#qubit) , etkinleştiriciler [olarak alan bir hisse.](xref:microsoft.quantum.glossary#operation)</span><span class="sxs-lookup"><span data-stu-id="63283-126">A quantum [operation](xref:microsoft.quantum.glossary#operation) that takes one or more [qubits](xref:microsoft.quantum.glossary#qubit) as enablers for the target operation.</span></span> <span data-ttu-id="63283-127">Daha fazla bilgi için bkz. [denetlenen ve Adjoint işlemleri](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span><span class="sxs-lookup"><span data-stu-id="63283-127">For more information, see [Controlled and adjoint operations](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span></span>

## <a name="dirac-notation"></a><span data-ttu-id="63283-128">Dirac gösterimi</span><span class="sxs-lookup"><span data-stu-id="63283-128">Dirac Notation</span></span>

<span data-ttu-id="63283-129">Aynı zamanda *köşeli ayraç* olarak da adlandırılan [hisse durumlarının](xref:microsoft.quantum.glossary#quantum-state)gösterimini kolaylaştıran bir sembolik kısayol.</span><span class="sxs-lookup"><span data-stu-id="63283-129">A symbolic shorthand that simplifies the representation of [quantum states](xref:microsoft.quantum.glossary#quantum-state), also called *bra-ket* notation.</span></span>  <span data-ttu-id="63283-130">*Köşeli* bölüm bir satır vektörünü temsil eder, örneğin $ \bra{a } = \begin{ bmatrix } a {_1 } & a {_2 } \end{ bmatrix } $ ve *demet* kısmı bir sütun vektörünü temsil eder, $ \ket{b } = \begin{ bmatrix } B {_1 } \\ \\ B {_2 } \end{ bmatrix } $.</span><span class="sxs-lookup"><span data-stu-id="63283-130">The *bra* portion represents a row vector, for example  $\bra{A} = \begin{bmatrix} A{_1} & A{_2} \end{bmatrix}$ and the *ket* portion represents a column vector, $\ket{B} = \begin{bmatrix} B{_1} \\\\ B{_2} \end{bmatrix}$.</span></span> <span data-ttu-id="63283-131">Daha fazla bilgi için bkz. [Dirac gösterimi](xref:microsoft.quantum.concepts.dirac).</span><span class="sxs-lookup"><span data-stu-id="63283-131">For more information, see [Dirac Notation](xref:microsoft.quantum.concepts.dirac).</span></span>

## <a name="eigenvalue"></a><span data-ttu-id="63283-132">Eigenvalue</span><span class="sxs-lookup"><span data-stu-id="63283-132">Eigenvalue</span></span>

<span data-ttu-id="63283-133">Belirli bir dönüşüme ait bir [egenvector](xref:microsoft.quantum.glossary#eigenvector) sayısının, dönüşüm uygulaması tarafından değiştirildiği faktör.</span><span class="sxs-lookup"><span data-stu-id="63283-133">The factor by which the magnitude of an [eigenvector](xref:microsoft.quantum.glossary#eigenvector) of a given transformation is changed by the application of the transformation.</span></span>  <span data-ttu-id="63283-134">$M kare matrisi ve bir $ eigenvector $v $ , $MV = CV $ , burada $c $ eigenvalue olduğu ve herhangi bir bağımsız değişken karmaşık bir sayı olabilir.</span><span class="sxs-lookup"><span data-stu-id="63283-134">Given a square matrix $M$ and an eigenvector $v$, then $Mv = cv$, where $c$ is the eigenvalue and can be a complex number of any argument.</span></span> <span data-ttu-id="63283-135">Daha fazla bilgi için bkz. [Gelişmiş matris kavramları](xref:microsoft.quantum.concepts.matrix-advanced).</span><span class="sxs-lookup"><span data-stu-id="63283-135">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="eigenvector"></a><span data-ttu-id="63283-136">Eigenvector</span><span class="sxs-lookup"><span data-stu-id="63283-136">Eigenvector</span></span>

<span data-ttu-id="63283-137">Yönü, belirli bir dönüşüm tarafından değiştirilmeyen ve büyüklüğü, bu vektörün [eigenine](xref:microsoft.quantum.glossary#eigenvalue)karşılık gelen bir faktörle değiştirilmiş olan bir vektör.</span><span class="sxs-lookup"><span data-stu-id="63283-137">A vector whose direction is unchanged by a given transformation and whose magnitude is changed by a factor corresponding to that vector's [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue).</span></span> <span data-ttu-id="63283-138">Kare matris $M ve bir $ eigenvalue $c verildiğinde $ $MV = CV $ , burada $v $ matrisin eigenbir vektörü ve herhangi bir bağımsız değişken karmaşık bir sayı olabilir.</span><span class="sxs-lookup"><span data-stu-id="63283-138">Given a square matrix $M$ and an eigenvalue $c$, then $Mv = cv$, where $v$ is an eigenvector of the matrix and can be a complex number of any argument.</span></span> <span data-ttu-id="63283-139">Daha fazla bilgi için bkz. [Gelişmiş matris kavramları](xref:microsoft.quantum.concepts.matrix-advanced).</span><span class="sxs-lookup"><span data-stu-id="63283-139">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="entanglement"></a><span data-ttu-id="63283-140">Dolaşıklık</span><span class="sxs-lookup"><span data-stu-id="63283-140">Entanglement</span></span>

<span data-ttu-id="63283-141">[Qubits](xref:microsoft.quantum.glossary#qubit)gibi hisse parçacıkların birbirleriyle bağımsız olarak açıklanamazlar şekilde *bağlı veya ayrılmış* olabilir.</span><span class="sxs-lookup"><span data-stu-id="63283-141">Quantum particles, such as [qubits](xref:microsoft.quantum.glossary#qubit), can be connected or *entangled* such that they cannot be described independently from each other.</span></span> <span data-ttu-id="63283-142">Ölçüm sonuçları, sonsuza kadar ayrıldıklarında bile bağıntılı olur.</span><span class="sxs-lookup"><span data-stu-id="63283-142">Their measurement results are correlated even when they are separated infinitely far away.</span></span> <span data-ttu-id="63283-143">Entanglement, bir qubit [durumunun](xref:microsoft.quantum.glossary#quantum-state) [ölçülmesi](xref:microsoft.quantum.glossary#measurement) için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="63283-143">Entanglement is essential to [measuring](xref:microsoft.quantum.glossary#measurement) the [state](xref:microsoft.quantum.glossary#quantum-state) of a qubit.</span></span>  <span data-ttu-id="63283-144">Daha fazla bilgi için bkz. [Gelişmiş matris kavramları](xref:microsoft.quantum.concepts.matrix-advanced).</span><span class="sxs-lookup"><span data-stu-id="63283-144">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="epr-pair"></a><span data-ttu-id="63283-145">EPR çifti</span><span class="sxs-lookup"><span data-stu-id="63283-145">EPR pair</span></span>

<span data-ttu-id="63283-146">İki [qubit](xref:microsoft.quantum.glossary#qubit)için en az dört adet en yüksek düzeyde, en önemli [hisse](xref:microsoft.quantum.glossary#quantum-state) mandan biri.</span><span class="sxs-lookup"><span data-stu-id="63283-146">One of four specific maximally entangled [quantum states](xref:microsoft.quantum.glossary#quantum-state) of two [qubits](xref:microsoft.quantum.glossary#qubit).</span></span> <span data-ttu-id="63283-147">Dört durum tanımlanmıştır $ \ket { \ beta_ {ij } } = (\mathbb{1 } \otimes X ^ iz ^ j) (\ket{00 } + \ket{11 } )/\sqrt{2 } $.</span><span class="sxs-lookup"><span data-stu-id="63283-147">The four states are defined $\ket{\beta_{ij}} = (\mathbb{1} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span> <span data-ttu-id="63283-148">Bir EPR çifti, [çan durumu](xref:microsoft.quantum.glossary#bell-state) olarak da bilinir</span><span class="sxs-lookup"><span data-stu-id="63283-148">An EPR pair is also known as a [Bell state](xref:microsoft.quantum.glossary#bell-state)</span></span>

## <a name="evolution"></a><span data-ttu-id="63283-149">Ri</span><span class="sxs-lookup"><span data-stu-id="63283-149">Evolution</span></span>

<span data-ttu-id="63283-150">[Hisse](xref:microsoft.quantum.glossary#quantum-state) , zaman içinde nasıl değişir.</span><span class="sxs-lookup"><span data-stu-id="63283-150">How a [quantum state](xref:microsoft.quantum.glossary#quantum-state) changes over time.</span></span> <span data-ttu-id="63283-151">Daha fazla bilgi için bkz. [matris üs öğeleri](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).</span><span class="sxs-lookup"><span data-stu-id="63283-151">For more information, see [Matrix exponentials](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).</span></span>

## <a name="function"></a><span data-ttu-id="63283-152">İşlev</span><span class="sxs-lookup"><span data-stu-id="63283-152">Function</span></span>
<span data-ttu-id="63283-153">Q # dilinde, tamamen klasik (hisse olmayan) bir altyordam türü.</span><span class="sxs-lookup"><span data-stu-id="63283-153">A type of subroutine in the Q# language that is purely classical (non-quantum).</span></span> <span data-ttu-id="63283-154">İşlevler, hisse algoritmaları içinde kullanıldığında, [qubits](xref:microsoft.quantum.glossary#qubit) veya çağrı [işlemleri](xref:microsoft.quantum.glossary#operation)üzerinde işlem yapılamaz.</span><span class="sxs-lookup"><span data-stu-id="63283-154">While functions are used within quantum algorithms, they cannot act on [qubits](xref:microsoft.quantum.glossary#qubit) or call [operations](xref:microsoft.quantum.glossary#operation).</span></span> <span data-ttu-id="63283-155">Daha fazla bilgi için bkz. [işlemler ve işlevler](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="63283-155">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="gate"></a><span data-ttu-id="63283-156">Kapısı</span><span class="sxs-lookup"><span data-stu-id="63283-156">Gate</span></span>

<span data-ttu-id="63283-157">Klasik Logic Gates kavramına bağlı olarak, hisse için bir [işlem](xref:microsoft.quantum.glossary#operation)için eski bir terim.</span><span class="sxs-lookup"><span data-stu-id="63283-157">A legacy term for a quantum [operation](xref:microsoft.quantum.glossary#operation), based on the concept of classical logic gates.</span></span> <span data-ttu-id="63283-158">[Hisse](xref:microsoft.quantum.glossary#quantum-circuit-diagram) bağlantı, klasik mantık devrelerinin benzer kavramına bağlı olarak, kapıların (veya işlemlerin) bir ağı olur.</span><span class="sxs-lookup"><span data-stu-id="63283-158">A [quantum circuit](xref:microsoft.quantum.glossary#quantum-circuit-diagram) is a network of gates (or operations), based on the similar concept of classical logic circuits.</span></span>

## <a name="global-phase"></a><span data-ttu-id="63283-159">Küresel aşama</span><span class="sxs-lookup"><span data-stu-id="63283-159">Global phase</span></span>

<span data-ttu-id="63283-160">İki [durum](xref:microsoft.quantum.glossary#quantum-state) , bir karmaşık sayının birden çok katı kadar özdeş olduğunda $e ^ {i \phi } $, genel bir aşamaya göre farklılık gösterir.</span><span class="sxs-lookup"><span data-stu-id="63283-160">When two [states](xref:microsoft.quantum.glossary#quantum-state) are identical up to a multiple of a complex number $e^{i\phi}$, they are said to differ up to a global phase.</span></span> <span data-ttu-id="63283-161">Yerel aşamaların aksine, genel aşamalar herhangi bir [Measurment](xref:microsoft.quantum.glossary#measurement)üzerinden gözlemlenemez.</span><span class="sxs-lookup"><span data-stu-id="63283-161">Unlike local phases, global phases cannot be observed through any [measurment](xref:microsoft.quantum.glossary#measurement).</span></span> <span data-ttu-id="63283-162">Daha fazla bilgi için bkz. [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="63283-162">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="hadamard"></a><span data-ttu-id="63283-163">Hadamard</span><span class="sxs-lookup"><span data-stu-id="63283-163">Hadamard</span></span>

<span data-ttu-id="63283-164">Hadamard işlemi (Hadamard kapısı veya dönüştürme olarak da bilinir), tek bir [qubit](xref:microsoft.quantum.glossary#qubit) üzerinde çalışır ve bu, [superposition](xref:microsoft.quantum.glossary#superposition) } } qubit başlangıçta $ \ket{0 $ durumunda olursa, bunu $ \ket{0 $ veya $ \ket{1 $ öğesinin hatta bir üst konumuna koyar } .</span><span class="sxs-lookup"><span data-stu-id="63283-164">The Hadamard operation (also referred to as the Hadamard gate or transform) acts on a single [qubit](xref:microsoft.quantum.glossary#qubit) and puts it in an even [superposition](xref:microsoft.quantum.glossary#superposition) of $\ket{0}$ or $\ket{1}$ if the qubit is initially in the $\ket{0}$ state.</span></span> <span data-ttu-id="63283-165">Q # içinde, bu işlem önceden tanımlı işlem tarafından uygulanır [`H`](xref:microsoft.quantum.intrinsic.h) .</span><span class="sxs-lookup"><span data-stu-id="63283-165">In Q#, this operation is applied by the pre-defined [`H`](xref:microsoft.quantum.intrinsic.h) operation.</span></span>

## <a name="immutable"></a><span data-ttu-id="63283-166">Değişmez</span><span class="sxs-lookup"><span data-stu-id="63283-166">Immutable</span></span>

<span data-ttu-id="63283-167">Değeri değiştirilemeyen bir değişken.</span><span class="sxs-lookup"><span data-stu-id="63283-167">A variable whose value cannot be changed.</span></span> <span data-ttu-id="63283-168">Anahtar sözcüğü kullanılarak Q # içinde sabit bir değişken oluşturulur `let` .</span><span class="sxs-lookup"><span data-stu-id="63283-168">An immutable variable in Q# is created using the `let` keyword.</span></span> <span data-ttu-id="63283-169">Değiştirilebilen değişkenleri bildirmek için *can* , öğesini bildirmek için [kesilebilir](xref:microsoft.quantum.glossary#immutable) anahtar sözcüğünü ve `set` değeri değiştirmek için anahtar sözcüğünü kullanın.</span><span class="sxs-lookup"><span data-stu-id="63283-169">To declare variables that *can* be changed, use the [mutable](xref:microsoft.quantum.glossary#immutable) keyword to declare and the `set` keyword to modify the value.</span></span> 

## <a name="measurement"></a><span data-ttu-id="63283-170">Ölçüm</span><span class="sxs-lookup"><span data-stu-id="63283-170">Measurement</span></span>

<span data-ttu-id="63283-171">Bir gözetmenin sonucunu veren bir [qubit](xref:microsoft.quantum.glossary#qubit) (veya qubits kümesi), klasik bir bit elde eden bir düzenleme.</span><span class="sxs-lookup"><span data-stu-id="63283-171">A manipulation of a [qubit](xref:microsoft.quantum.glossary#qubit) (or set of qubits) that yields the result of an observation, in effect obtaining a classical bit.</span></span> <span data-ttu-id="63283-172">Daha fazla bilgi için bkz. [qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).</span><span class="sxs-lookup"><span data-stu-id="63283-172">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).</span></span>

## <a name="mutable"></a><span data-ttu-id="63283-173">Değiştirilebilir</span><span class="sxs-lookup"><span data-stu-id="63283-173">Mutable</span></span>

<span data-ttu-id="63283-174">Değeri oluşturulduktan sonra değiştirilmiş olan bir değişken.</span><span class="sxs-lookup"><span data-stu-id="63283-174">A variable whose value may be changed after it is created.</span></span> <span data-ttu-id="63283-175">Q # ' da kesilebilir bir değişken anahtar sözcüğü kullanılarak, anahtar `mutable` sözcüğü kullanılarak değiştirilir `set` .</span><span class="sxs-lookup"><span data-stu-id="63283-175">A mutable variable in Q# is declared using the `mutable` keyword and modified using the `set` keyword.</span></span> <span data-ttu-id="63283-176">Anahtar sözcükle oluşturulan değişkenler `let` [sabittir](xref:microsoft.quantum.glossary#immutable) ve değerleri değiştirilemez.</span><span class="sxs-lookup"><span data-stu-id="63283-176">Variables created with the `let` keyword are [immutable](xref:microsoft.quantum.glossary#immutable) and their value cannot be changed.</span></span>

## <a name="namespace"></a><span data-ttu-id="63283-177">Ad Alanı</span><span class="sxs-lookup"><span data-stu-id="63283-177">Namespace</span></span>

<span data-ttu-id="63283-178">İlgili adların (yani, [işlemler](xref:microsoft.quantum.glossary#operation), [işlevler](xref:microsoft.quantum.glossary#function)ve [Kullanıcı tanımlı türler](xref:microsoft.quantum.glossary#user-defined-type)) toplanması için bir etiket.</span><span class="sxs-lookup"><span data-stu-id="63283-178">A label for a collection of related names (i.e., [operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function), and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type)).</span></span> <span data-ttu-id="63283-179">Örneğin, [Microsoft. hisse. hazırlama](xref:microsoft.quantum.preparation) ad alanı, standart kitaplıkta tanımlanan ve ilk durumları hazırlamaya yardımcı olan tüm sembolleri Etiketler.</span><span class="sxs-lookup"><span data-stu-id="63283-179">For instance the namespace [Microsoft.Quantum.Preparation](xref:microsoft.quantum.preparation) labels all of the symbols defined in the standard library that help with preparing initial states.</span></span>

## <a name="operation"></a><span data-ttu-id="63283-180">Çalışma</span><span class="sxs-lookup"><span data-stu-id="63283-180">Operation</span></span>

<span data-ttu-id="63283-181">Q # içinde temel hisse yürütme birimi.</span><span class="sxs-lookup"><span data-stu-id="63283-181">The basic unit of quantum execution in Q#.</span></span> <span data-ttu-id="63283-182">Bu, kabaca C, C++ veya Python içindeki bir işleve veya C# ya da Java 'daki statik bir yönteme eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="63283-182">It is roughly equivalent to a function in C, C++ or Python, or a static method in C# or Java.</span></span> <span data-ttu-id="63283-183">Daha fazla bilgi için bkz. [işlemler ve işlevler](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="63283-183">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="operator-application"></a><span data-ttu-id="63283-184">İşleç uygulaması</span><span class="sxs-lookup"><span data-stu-id="63283-184">Operator application</span></span>

<span data-ttu-id="63283-185">Hisse bir işlem gerçekleştiriliyor.</span><span class="sxs-lookup"><span data-stu-id="63283-185">Performing a quantum operation.</span></span> <span data-ttu-id="63283-186">Bu, genellikle geçerli hisse durumu vektörüne bir Unitary matrisi uygular.</span><span class="sxs-lookup"><span data-stu-id="63283-186">This typically applies a unitary matrix to the current quantum state vector.</span></span>

## <a name="oracle"></a><span data-ttu-id="63283-187">Oracle</span><span class="sxs-lookup"><span data-stu-id="63283-187">Oracle</span></span>

<span data-ttu-id="63283-188">Çalışma zamanında bir hisse algoritmasına veri bağımlı bilgiler sağlayan bir altyordam.</span><span class="sxs-lookup"><span data-stu-id="63283-188">A subroutine that provides data-dependent information to a quantum algorithm at runtime.</span></span> <span data-ttu-id="63283-189">Genellikle amaç, üst konumdaki girişlere karşılık gelen çıkışların [üst konumunu](xref:microsoft.quantum.glossary#superposition) sağlamaktır.</span><span class="sxs-lookup"><span data-stu-id="63283-189">Typically, the goal is to provide a [superposition](xref:microsoft.quantum.glossary#superposition) of outputs corresponding to inputs that are in superposition.</span></span> <span data-ttu-id="63283-190">Daha fazla bilgi için bkz. [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).</span><span class="sxs-lookup"><span data-stu-id="63283-190">For more information, see [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).</span></span>

## <a name="partial-application"></a><span data-ttu-id="63283-191">Kısmi uygulama</span><span class="sxs-lookup"><span data-stu-id="63283-191">Partial application</span></span>

<span data-ttu-id="63283-192">Tüm gerekli girişler olmadan bir [işlev](xref:microsoft.quantum.glossary#function) veya [işlem](xref:microsoft.quantum.glossary#operation) çağrılıyor.</span><span class="sxs-lookup"><span data-stu-id="63283-192">Calling a [function](xref:microsoft.quantum.glossary#function) or [operation](xref:microsoft.quantum.glossary#operation) without all the required inputs.</span></span> <span data-ttu-id="63283-193">Bu, gelecekteki bir uygulama sırasında yalnızca eksik parametrelere (alt çizgiyle belirtilir) ihtiyacı olan yeni bir [çağrılabilir](xref:microsoft.quantum.glossary#callable) döndürüyor.</span><span class="sxs-lookup"><span data-stu-id="63283-193">This returns a new [callable](xref:microsoft.quantum.glossary#callable) that only needs the missing parameters (indicated by an underscore) to be supplied during a future application.</span></span> <span data-ttu-id="63283-194">Örneğin, işlevi verildiğinde `MyFunc(x : int, y : int) : int {return x + y;}` onu kısmen yeni bir işleve uygulayabilirsiniz `let NewFunc = MyFunc(_, 3)` .</span><span class="sxs-lookup"><span data-stu-id="63283-194">For example, given the function `MyFunc(x : int, y : int) : int {return x + y;}` you can partially apply it to a new function `let NewFunc = MyFunc(_, 3)`.</span></span> <span data-ttu-id="63283-195">Daha sonra yeni işlevi, `NewFunc(2)` *5*değerini döndüren eksik parametre ile daha sonra çağırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="63283-195">You can then call the new function at a later time with the missing parameter `NewFunc(2)` which returns the value *5*.</span></span>  <span data-ttu-id="63283-196">Daha fazla bilgi için bkz. [kısmi uygulama](xref:microsoft.quantum.guide.operationsfunctions#partial-application).</span><span class="sxs-lookup"><span data-stu-id="63283-196">For more information, see [Partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application).</span></span>

## <a name="pauli-operators"></a><span data-ttu-id="63283-197">Pauli işleçleri</span><span class="sxs-lookup"><span data-stu-id="63283-197">Pauli operators</span></span>

<span data-ttu-id="63283-198">`X` `Y` Ve hisse işlemleri olarak bilinen üç 2 x 2 Unitary matrisi kümesi `Z` .</span><span class="sxs-lookup"><span data-stu-id="63283-198">A set of three 2 x 2 unitary matrices known as the `X`, `Y` and `Z` quantum operations.</span></span> <span data-ttu-id="63283-199">$I kimlik matrisi $ genellikle küme içinde de bulunur.</span><span class="sxs-lookup"><span data-stu-id="63283-199">The identity matrix, $I$, is often included in the set as well.</span></span>  <span data-ttu-id="63283-200">$I = \begin{ bmatrix } 1 & 0 \\ \\ 0 & 1 \end{ bmatrix } $, $X = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } $, $Y = \begin{ bmatrix } 0 &-ı \\ \\ i & 0 \end{ bmatrix } $, $Z = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } $.</span><span class="sxs-lookup"><span data-stu-id="63283-200">$I = \begin{bmatrix} 1 & 0 \\\\ 0 & 1 \end{bmatrix}$, $X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}$, $Y = \begin{bmatrix} 0 & -i \\\\ i & 0 \end{bmatrix}$, $Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}$.</span></span>   <span data-ttu-id="63283-201">Daha fazla bilgi için bkz. [tek qubit işlemleri](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span><span class="sxs-lookup"><span data-stu-id="63283-201">For more information, see [Single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>

## <a name="quantum-circuit-diagram"></a><span data-ttu-id="63283-202">Hisse devre diyagramı</span><span class="sxs-lookup"><span data-stu-id="63283-202">Quantum circuit diagram</span></span>

<span data-ttu-id="63283-203">Basit hisse programları için [işlem](xref:microsoft.quantum.glossary#operation) (veya [kapı](xref:microsoft.quantum.glossary#gate)) dizisini grafik olarak temsil eden bir Yöntem (örneğin,</span><span class="sxs-lookup"><span data-stu-id="63283-203">A method to graphically represent the sequence of [operations](xref:microsoft.quantum.glossary#operation) (or [gates](xref:microsoft.quantum.glossary#gate)) for simple quantum programs, for example</span></span> 

![Örnek devre diyagramı](~/media/qpe.png)<span data-ttu-id="63283-205">.</span><span class="sxs-lookup"><span data-stu-id="63283-205">.</span></span> 

<span data-ttu-id="63283-206">Daha fazla bilgi için bkz. [hisse devreleri](xref:microsoft.quantum.concepts.circuits).</span><span class="sxs-lookup"><span data-stu-id="63283-206">For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits).</span></span>

## <a name="quantum-libraries"></a><span data-ttu-id="63283-207">Hisse kitaplıkları</span><span class="sxs-lookup"><span data-stu-id="63283-207">Quantum libraries</span></span>

<span data-ttu-id="63283-208">Q # programları oluşturmak için [işlem](xref:microsoft.quantum.glossary#operation), [işlev](xref:microsoft.quantum.glossary#function) ve [Kullanıcı tanımlı türlerin](xref:microsoft.quantum.glossary#user-defined-type) koleksiyonları.</span><span class="sxs-lookup"><span data-stu-id="63283-208">Collections of [operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function) and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type) for creating Q# programs.</span></span> <span data-ttu-id="63283-209">[Standart kitaplık](xref:microsoft.quantum.libraries.standard.intro) varsayılan olarak yüklenir.</span><span class="sxs-lookup"><span data-stu-id="63283-209">The [Standard library](xref:microsoft.quantum.libraries.standard.intro) is installed by default.</span></span> <span data-ttu-id="63283-210">Kullanılabilen diğer kitaplıklar, [Kyatry kitaplığı](xref:microsoft.quantum.chemistry.concepts.intro), [Numerics kitaplığı](xref:microsoft.quantum.numerics.intro) ve [makine öğrenme kitaplığıdır](xref:microsoft.quantum.machine-learning.concepts.intro).</span><span class="sxs-lookup"><span data-stu-id="63283-210">Other libraries available are the [Chemistry library](xref:microsoft.quantum.chemistry.concepts.intro), the [Numerics library](xref:microsoft.quantum.numerics.intro) and the [Machine learning library](xref:microsoft.quantum.machine-learning.concepts.intro).</span></span>

## <a name="quantum-state"></a><span data-ttu-id="63283-211">Hisse durumu</span><span class="sxs-lookup"><span data-stu-id="63283-211">Quantum state</span></span>

<span data-ttu-id="63283-212">Yalıtılmış bir hisse sisteminin, [Ölçü](xref:microsoft.quantum.glossary#measurement) olasılıkların ayıklanabileceği kesin durumu.</span><span class="sxs-lookup"><span data-stu-id="63283-212">The precise state of an isolated quantum system, from which [measurement](xref:microsoft.quantum.glossary#measurement) probabilities can be extracted.</span></span> <span data-ttu-id="63283-213">Hisse benzeticisinde, hisse Benzetici, bu bilgileri kullanarak qubits 'in işlemlere nasıl yanıt verdiğini taklit ediyor.</span><span class="sxs-lookup"><span data-stu-id="63283-213">In quantum computing, the quantum simulator uses this information to simulate how qubits respond to operations.</span></span> <span data-ttu-id="63283-214">Daha fazla bilgi için bkz. [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="63283-214">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="qubit"></a><span data-ttu-id="63283-215">Qubit</span><span class="sxs-lookup"><span data-stu-id="63283-215">Qubit</span></span>

<span data-ttu-id="63283-216">Klasik bilgi işlem içindeki bir *bite* benzer temel bir hisse bilgisi birimi.</span><span class="sxs-lookup"><span data-stu-id="63283-216">A basic unit of quantum information, analogous to a *bit* in classical computing.</span></span> <span data-ttu-id="63283-217">Daha fazla bilgi için bkz. [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="63283-217">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="repeat-until-success"></a><span data-ttu-id="63283-218">Yineleme-Until-başarılı</span><span class="sxs-lookup"><span data-stu-id="63283-218">Repeat-until-success</span></span>

<span data-ttu-id="63283-219">Bilsel olarak başarılı olan bir hisse algoritması.</span><span class="sxs-lookup"><span data-stu-id="63283-219">A quantum algorithm that probabilistically succeeds.</span></span> <span data-ttu-id="63283-220">Hata sonrasında, yordam başarılı olana kadar yeniden dener (veya sınıra ulaşılmış olur).</span><span class="sxs-lookup"><span data-stu-id="63283-220">Upon failure, the routine will retry until successful (or a limit has been reached).</span></span> <span data-ttu-id="63283-221">Daha fazla bilgi için bkz. [başarılı olana kadar Yinele (ru)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)</span><span class="sxs-lookup"><span data-stu-id="63283-221">For more information, see [Repeat Until Success (RUS)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)</span></span>

## <a name="standard-libraries"></a><span data-ttu-id="63283-222">Standart kitaplıklar</span><span class="sxs-lookup"><span data-stu-id="63283-222">Standard libraries</span></span>

<span data-ttu-id="63283-223">Yükleme sırasında Q # derleyicisi ile birlikte yüklenen [işlemler](xref:microsoft.quantum.glossary#operation), [işlevler](xref:microsoft.quantum.glossary#function) ve [Kullanıcı tanımlı türler](xref:microsoft.quantum.glossary#user-defined-type) .</span><span class="sxs-lookup"><span data-stu-id="63283-223">[Operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function) and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type) that are installed along with the Q# compiler during installation.</span></span> <span data-ttu-id="63283-224">Standart kitaplık uygulamasının hedef makinelere göre belirsiz olması.</span><span class="sxs-lookup"><span data-stu-id="63283-224">The standard library implementation is agnostic with respect to target machines.</span></span> <span data-ttu-id="63283-225">Daha fazla bilgi için bkz. [Standart kitaplıklar](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="63283-225">For more information, see [Standard libraries](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="superposition"></a><span data-ttu-id="63283-226">Süper konum</span><span class="sxs-lookup"><span data-stu-id="63283-226">Superposition</span></span>

<span data-ttu-id="63283-227">Bu, bir [qubit](xref:microsoft.quantum.glossary#qubit) 'in, ölçülene kadar, $ \ket{0 } $ ve $ \ket{1 } $ olmak [measured](xref:microsoft.quantum.glossary#measurement)üzere iki durumun doğrusal bir birleşimi olduğunu gösteren kavram.</span><span class="sxs-lookup"><span data-stu-id="63283-227">The concept in quantum computing that a [qubit](xref:microsoft.quantum.glossary#qubit) is a linear combination of two states, $\ket{0}$ and $\ket{1}$, until it is [measured](xref:microsoft.quantum.glossary#measurement).</span></span>  <span data-ttu-id="63283-228">Daha fazla bilgi için bkz. [hisse kullanımı anlama](xref:microsoft.quantum.overview.understanding).</span><span class="sxs-lookup"><span data-stu-id="63283-228">For more information, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding).</span></span>

## <a name="target-machine"></a><span data-ttu-id="63283-229">Hedef makine</span><span class="sxs-lookup"><span data-stu-id="63283-229">Target machine</span></span>

<span data-ttu-id="63283-230">Soyut bir hisse programını donanım veya benzetim doğrultusunda alçalt bir derleme hedefi.</span><span class="sxs-lookup"><span data-stu-id="63283-230">A compilation target that lowers an abstract quantum program towards hardware or simulation.</span></span> <span data-ttu-id="63283-231">Bu genellikle, geçit değiştirme, hata düzeltme için kodlama, geometrik düzen ve diğerleri gibi birçok amaç için yeniden yazma işlemlerini içerir.</span><span class="sxs-lookup"><span data-stu-id="63283-231">This typically include re-writes for many purposes including gate replacement, encoding for error correction, geometric layout and others.</span></span> <span data-ttu-id="63283-232">Daha fazla bilgi için bkz. [hisse simülatörleri ve ana bilgisayar uygulamaları](xref:microsoft.quantum.machines).</span><span class="sxs-lookup"><span data-stu-id="63283-232">For more information, see [Quantum simulators and host applications](xref:microsoft.quantum.machines).</span></span>

## <a name="teleportation"></a><span data-ttu-id="63283-233">Işınlanma</span><span class="sxs-lookup"><span data-stu-id="63283-233">Teleportation</span></span>

<span data-ttu-id="63283-234">[Entanglement](xref:microsoft.quantum.glossary#entanglement) ve [ölçüm](xref:microsoft.quantum.glossary#measurement)kullanarak, qubit fiziksel olarak hareket ettirmeden, bir veya daha fazla bir yerde, bir [qubit](xref:microsoft.quantum.glossary#qubit) 'e veri veya [hisse durumu](xref:microsoft.quantum.glossary#quantum-state)oluşturma yöntemi.</span><span class="sxs-lookup"><span data-stu-id="63283-234">A method for regenerating data, or the [quantum state](xref:microsoft.quantum.glossary#quantum-state), of one [qubit](xref:microsoft.quantum.glossary#qubit) from one place to another without physically moving the qubit, using [entanglement](xref:microsoft.quantum.glossary#entanglement) and [measurement](xref:microsoft.quantum.glossary#measurement).</span></span>  <span data-ttu-id="63283-235">Daha fazla bilgi için bkz [. hisse başında hisse ve ilgili](xref:microsoft.quantum.concepts.circuits) küta [.](xref:microsoft.quantum.overview.katas)</span><span class="sxs-lookup"><span data-stu-id="63283-235">For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits) and the respective kata at [Quantum Katas](xref:microsoft.quantum.overview.katas).</span></span>

## <a name="tuple"></a><span data-ttu-id="63283-236">Le</span><span class="sxs-lookup"><span data-stu-id="63283-236">Tuple</span></span>

<span data-ttu-id="63283-237">Tek bir değer görevi gören virgülle ayrılmış değerler koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="63283-237">A collection of comma-separated values that acts as a single value.</span></span> <span data-ttu-id="63283-238">Tanımlama grubu *türü* , içerdiği değer türleri tarafından tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="63283-238">The *type* of a tuple is defined by the types of values it contains.</span></span> <span data-ttu-id="63283-239">Q # içinde, tanımlama grupları [sabittir](xref:microsoft.quantum.glossary#immutable) ve iç içe olabilir, diziler içerebilir veya bir dizide kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="63283-239">In Q#, tuples are [immutable](xref:microsoft.quantum.glossary#immutable) and can be nested, contain arrays, or used in an array.</span></span> <span data-ttu-id="63283-240">Daha fazla bilgi için bkz. [demet türleri](xref:microsoft.quantum.guide.types#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="63283-240">For more information, see [Tuple types](xref:microsoft.quantum.guide.types#tuple-types).</span></span>

## <a name="unitary-operator"></a><span data-ttu-id="63283-241">Unitary işleci</span><span class="sxs-lookup"><span data-stu-id="63283-241">Unitary operator</span></span>

<span data-ttu-id="63283-242">Ters, [adjoint](xref:microsoft.quantum.glossary#adjoint)değerine eşit olan bir işleç, yani $uu ^ {\dağılım } = \ID $ .</span><span class="sxs-lookup"><span data-stu-id="63283-242">An operator whose inverse is equal to its [adjoint](xref:microsoft.quantum.glossary#adjoint), i.e., $UU^{\dagger} = \id$.</span></span>

## <a name="user-defined-type"></a><span data-ttu-id="63283-243">Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="63283-243">User-defined type</span></span>

<span data-ttu-id="63283-244">Tek bir birim olarak başvurulabilen yerleşik veya önceden tanımlanmış türlerin bir koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="63283-244">A collection of built-in or previously defined types that may be referred to as a single unit.</span></span> <span data-ttu-id="63283-245">Daha fazla bilgi için bkz. [Kullanıcı tanımlı türler](xref:microsoft.quantum.guide.types#user-defined-types).</span><span class="sxs-lookup"><span data-stu-id="63283-245">For more information, see [User-defined types](xref:microsoft.quantum.guide.types#user-defined-types).</span></span>