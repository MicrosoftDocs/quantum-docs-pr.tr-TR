---
title: Dirac gösterimi
description: Hisse durumlarını göstermek ve hisse alma işlemlerinin benzetimini yapmak için Dirac gösterimini kullanma hakkında bilgi edinin.
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
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
ms.openlocfilehash: f9dddfa25e9fd1e3d8aaf92b2e3b17c96ed8b72a
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269515"
---
# <a name="dirac-notation"></a><span data-ttu-id="e22d1-103">Dirac gösterimi</span><span class="sxs-lookup"><span data-stu-id="e22d1-103">Dirac Notation</span></span>

<span data-ttu-id="e22d1-104">Sütun vektör gösterimi doğrusal Alton içinde ikizde olduğunda, genellikle birden çok qubit ile ilgilenirken, daha fazla bilgi almak için daha fazla.</span><span class="sxs-lookup"><span data-stu-id="e22d1-104">While column vector notation is ubiquitous in linear algebra, it is often cumbersome in quantum computing especially when dealing with multiple qubits.</span></span>  <span data-ttu-id="e22d1-105">Örneğin, $ \psı 'yi bir vektör olarak tanımladığımızda, $ $ \psı $ 'nin bir satır veya bir sütun vektörü olup olmadığı açıkça net bir şekilde görünmez.</span><span class="sxs-lookup"><span data-stu-id="e22d1-105">For example, when we define $\psi$ to be a vector it is not explicitly clear whether $\psi$ is a row or a column vector.</span></span>  <span data-ttu-id="e22d1-106">Bu nedenle, $ \phi $ ve $ \psı $ vektörse, $ $ \fi $ ve $ \psı şekilleri bağlamda belirsiz olabileceğinden, $ \phi \psı çiftse eşit değildir $ .</span><span class="sxs-lookup"><span data-stu-id="e22d1-106">Thus if $\phi$ and $\psi$ are vectors then it is equally unclear if $\phi \psi$ is even defined because the shapes of $\phi$ and $\psi$ may be unclear in the context.</span></span>  <span data-ttu-id="e22d1-107">Vektörlerin şekilleriyle ilgili belirsizliğin ötesinde, daha önce sunulan doğrusal cebirsel gösterimini kullanan basit vektörleri ifade etmek çok daha kısacası olabilir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-107">Beyond the ambiguity about the shapes of vectors, expressing even simple vectors using the linear algebraic notation introduced earlier can be very cumbersome.</span></span> <span data-ttu-id="e22d1-108">Örneğin, $ her bir qubitin $0 değerini aldığı $n-qubit durumunu anlatmak istiyorsanız, $ durumu</span><span class="sxs-lookup"><span data-stu-id="e22d1-108">For example, if we wish to describe an $n$-qubit state where each qubit takes the value $0$ then we would formally express the state as</span></span> 

<span data-ttu-id="e22d1-109">$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cnoktalar \otimes \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="e22d1-109">$$\begin{bmatrix}1 \\\\  0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\  0 \end{bmatrix}.</span></span> $$  

<span data-ttu-id="e22d1-110">Vektör, katlanarak büyük bir alanda bulunduğundan ve bu gösterim, önceki gösterim kullanılarak verilen durumun en iyi açıklaması olduğundan, bu Tensor ürününü değerlendiren bir kurs pratik değildir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-110">Of course evaluating this tensor product is impractical because the vector lies in an exponentially large space and so this notation is in fact the best description of the state that can be given using the previous notation.</span></span>  

<span data-ttu-id="e22d1-111">[*Dirac gösterimi*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) bu sorunları, yeni bir dil sunarak hisse alanı tam ihtiyaçlarını karşılayacak şekilde çözer.</span><span class="sxs-lookup"><span data-stu-id="e22d1-111">[*Dirac notation*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) solves these issues by presenting a new language to fit the precise needs of quantum mechanics.</span></span>  <span data-ttu-id="e22d1-112">Bu nedenle, okuyucunun bu bölümdeki örnekleri, hisse durumlarının nasıl tanımlandığına ilişkin bir grup olarak bu bölümde yer alan örnekleri görüntüleyemeyeceğini, ancak okuyucuyu, Express hisse fikirlerini öz için kullanılabilecek öneriler olarak görüntülemesini öneririz.</span><span class="sxs-lookup"><span data-stu-id="e22d1-112">For this reason, we recommend the reader not view the examples in this section as a rigid prescription of how to describe quantum states, but rather encourage the reader to view these as suggestions that can be used to concisely express quantum ideas.</span></span>

<span data-ttu-id="e22d1-113">Dirac gösteriminde iki tür vektör vardır: bir arada bir *örgü* veya iç ürün oluşturduklarında, adlandırılmış *bir vektör vektörü* ve *demet* vektörü.</span><span class="sxs-lookup"><span data-stu-id="e22d1-113">There are two types of vectors in Dirac notation: the *bra* vector and the *ket* vector, so named because when put together they form a *braket* or inner product.</span></span>  <span data-ttu-id="e22d1-114">$ \Psı $ bir sütun vektörü ise, $ \ket { } { \ CDOT $ ' ın bir } birim sütunu vektörü olduğunu (yani, bir *demet* vektörü olduğunu) $ \Ket \ PSI $ olarak Dirac gösterimine yazarız.</span><span class="sxs-lookup"><span data-stu-id="e22d1-114">If $\psi$ is a column vector then we can write it in Dirac notation as $\ket{\psi}$, where the $\ket{\cdot}$ denotes that it is a unit column vector, i.e., a *ket* vector.</span></span>  <span data-ttu-id="e22d1-115">Benzer şekilde, satır vektörü $ \psi ^ \dağılım, $ $ \bra { \ PSI $ olarak ifade edilir } .</span><span class="sxs-lookup"><span data-stu-id="e22d1-115">Similarly, the row vector $\psi^\dagger$ is expressed as $\bra{\psi}$.</span></span> <span data-ttu-id="e22d1-116">Diğer bir deyişle, $ \ PSI ^ \gesger, $ $ \ PSI öğesinin devrik öğesine giriş tabanlı karmaşık Birleşik bir uygulama uygulanarak elde edilir $ .</span><span class="sxs-lookup"><span data-stu-id="e22d1-116">In other words, $\psi^\dagger$ is obtained by applying entry-wise complex conjugation to the elements of the transpose of $\psi$.</span></span> <span data-ttu-id="e22d1-117">Köşeli ayraç gösterimi doğrudan $ { \bratus\psı | \psı } $ 'ın $ , Açıklama $1 ile olan vector $ \psı 'in iç ürünüdür $ .</span><span class="sxs-lookup"><span data-stu-id="e22d1-117">The bra-ket notation directly implies that $\braket{\psi|\psi}$ is the inner product of vector $\psi$ with itself, which is by definition $1$.</span></span>  

<span data-ttu-id="e22d1-118">Daha genel olarak, $ \psı $ ve $ \phi, $ hisse devlet vektörleridir. bu durum, $ \ket \ PSI $ değerini $ \ket \ Fi $ olarak hesaplama olasılığının $ \ ' $ { | } { } { } | \braket { \ Fi \ | PSI } | ^ 2 $ olduğunu belirten $ \bratus\phi \ PSI $ şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-118">More generally, if $\psi$ and $\phi$ are quantum state vectors their inner product is $\braket{\phi|\psi}$ which implies that the probability of measuring the state $\ket{\psi}$ to be $\ket{\phi}$ is $|\braket{\phi|\psi}|^2$.</span></span>  

<span data-ttu-id="e22d1-119">Aşağıdaki kural, sıfır ve bir (tek qubit hesaplama tabanlı durumlar) değerlerini kodlayan hisse durumlarının tanımlanmasında kullanılır:</span><span class="sxs-lookup"><span data-stu-id="e22d1-119">The following convention is used to describe the quantum states that encode the values of zero and one (the single-qubit computational basis states):</span></span>

<span data-ttu-id="e22d1-120">$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } , \qquad \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } = \ket{1 } .</span><span class="sxs-lookup"><span data-stu-id="e22d1-120">$$ \begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \ket{0},\qquad \begin{bmatrix} 0 \\\\  1 \end{bmatrix} = \ket{1}.</span></span>
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a><span data-ttu-id="e22d1-121">Örnek: Dirac gösterimi ile Hadamard işlemini temsil etme</span><span class="sxs-lookup"><span data-stu-id="e22d1-121">Example: representing the Hadamard operation with Dirac notation</span></span>

<span data-ttu-id="e22d1-122">Aşağıdaki gösterim genellikle, Hadamard kapısını $ \ket{0 } $ ve $ \ket{1 $ ' a uygulamanın } ( $ Bloch Sphere ' de $ + x ve $-x yönlerine karşılık gelen birim vektörlerine karşılık gelen durumları) belirlemek için kullanılır $ :</span><span class="sxs-lookup"><span data-stu-id="e22d1-122">The following notation is often used to describe the states that result from applying the Hadamard gate to $\ket{0}$ and $\ket{1}$ (which correspond to the unit vectors in the $+x$ and $-x$ directions on the Bloch sphere):</span></span>

<span data-ttu-id="e22d1-123">$ $ \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ 1 \end{ bmatrix } = H \ket {0 } = \ket { +}, \qquad \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ -1 \end{ bmatrix } = H \ket {1 } = { \tus-}.</span><span class="sxs-lookup"><span data-stu-id="e22d1-123">$$ \frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=H\ket{0} = \ket{+},\qquad \frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  -1 \end{bmatrix} =H\ket{1} = \ket{-} .</span></span>
$$

<span data-ttu-id="e22d1-124">Bu durumlar Ayrıca, $ \ket{0 } $ ve $ \ket{1 $ toplamı olarak Dirac gösterimi kullanılarak da Genişletilebilir } :</span><span class="sxs-lookup"><span data-stu-id="e22d1-124">These states can also be expanded using Dirac notation as sums of $\ket{0}$ and $\ket{1}$:</span></span>

<span data-ttu-id="e22d1-125">$ $ \ket { +} = \frac{1 } {\sqrt{2 } } (\ket{0 } + \ket{1 } ), \qquad { \tus-} = \frac{1 } {\sqrt{2 } } (\ket{0 } -\ket{1 } ).</span><span class="sxs-lookup"><span data-stu-id="e22d1-125">$$ \ket{+} = \frac{1}{\sqrt{2}}(\ket{0} + \ket{1}),\qquad \ket{-} = \frac{1}{\sqrt{2}}(\ket{0} - \ket{1}).</span></span>
$$

### <a name="computational-basis-vectors"></a><span data-ttu-id="e22d1-126">Hesaplama tabanlı vektörler</span><span class="sxs-lookup"><span data-stu-id="e22d1-126">Computational basis vectors</span></span>
<span data-ttu-id="e22d1-127">Bu durum, bu durumların neden genellikle *Hesaplama tabanlı*olarak çağrıldığını gösterir: her hisse maç durumu her zaman hesaplama tabanlı vektörlerin toplamı olarak ifade edilebilir ve bu tür toplamların adı, Dirac gösterimi kullanılarak kolayca ifade edilir</span><span class="sxs-lookup"><span data-stu-id="e22d1-127">This demonstrates why these states are often called a *computational basis*: every quantum state can always be expressed as sums of computational basis vectors and such sums are easily expressed using Dirac notation.</span></span>  <span data-ttu-id="e22d1-128">Aynı zamanda, $ \ket { +} $ ve $ { \tus-} $ durumları için de aynı zamanda hisse Adaları için de bir temel oluşturacak şekilde dönüştürüme de geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-128">The converse is also true in that the states $\ket{+}$ and $\ket{-}$ also form a basis for quantum states.</span></span>  <span data-ttu-id="e22d1-129">Bunu şu şekilde görebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="e22d1-129">You can see this from the fact that</span></span>

<span data-ttu-id="e22d1-130">$ $ \ket{0 } = \frac{1 } {\sqrt{2 } } (\ket { +} + \ket { -}), \qquad \ket{1 } = \frac{1 } {\sqrt{2 } } (\demet { +}-\ demet { -}).</span><span class="sxs-lookup"><span data-stu-id="e22d1-130">$$ \ket{0} = \frac{1}{\sqrt{2}}(\ket{+} + \ket{-}),\qquad \ket{1} = \frac{1}{\sqrt{2}}(\ket{+} - \ket{-}).</span></span>
$$

<span data-ttu-id="e22d1-131">Dirac gösterimine örnek olarak, } $0 ve $1 arasındaki iç ürün olan braket $ \braketi| 1 $ öğesini düşünün $ $ .</span><span class="sxs-lookup"><span data-stu-id="e22d1-131">As an example of Dirac notation, consider the braket $\braket{0 | 1}$, which is the inner product between $0$ and $1$.</span></span>  <span data-ttu-id="e22d1-132">Bu, şöyle yazılabilir</span><span class="sxs-lookup"><span data-stu-id="e22d1-132">It can be written as</span></span> 

<span data-ttu-id="e22d1-133">$ $ \braket{0 | 1 } = \begin{ bmatrix } 1 & 0 \end{ bmatrix } \begin{ bmatrix } 0 \\\\ 1 \end{bmatrix} = 0. $ $</span><span class="sxs-lookup"><span data-stu-id="e22d1-133">$$\braket{0 | 1}=\begin{bmatrix} 1 & 0 \end{bmatrix}\begin{bmatrix}0\\\\ 1\end{bmatrix}=0.$$</span></span>

<span data-ttu-id="e22d1-134">Bu, $ \ket{0 } $ ve $ \ket{1 } $ 'ın diksel vektörler olduğunu, yani $ \braket{0 | 1 } = \braket{1 | 0 } = 0 $ olduğunu söyler.</span><span class="sxs-lookup"><span data-stu-id="e22d1-134">This says that $\ket{0}$ and $\ket{1}$ are orthogonal vectors, meaning that $\braket{0 | 1} = \braket{1 | 0} =0$.</span></span>  <span data-ttu-id="e22d1-135">Ayrıca, tanım $ \braket{0 | 0 } = \braket{1 | 1 } = 1 $ , bu da iki hesaplama tabanlı vektörde *orthonormal*çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-135">Also by definition $\braket{0 | 0} = \braket{1 | 1}=1$, which means that the two computational basis vectors can also be called *orthonormal*.</span></span>
<span data-ttu-id="e22d1-136">Bu orthonormal özellikleri aşağıdaki örnekte yararlı olacaktır.</span><span class="sxs-lookup"><span data-stu-id="e22d1-136">These orthonormal properties will be useful in the following example.</span></span> <span data-ttu-id="e22d1-137">Bir State $ \ket { \psı } = {\frac{3 } {5 } } \ket{1 } + {\frac{4 } {5 } } \ket{0 } $ olduğunda, $ \braket{1 | 0 } = 0 $ ölçmenin olasılığı $1 $</span><span class="sxs-lookup"><span data-stu-id="e22d1-137">If we have a state $\ket{\psi} = {\frac{3}{5}} \ket{1} + {\frac{4}{5}} \ket{0}$ then because $\braket{1 | 0} =0$ the probability of measuring $1$  is</span></span>  

<span data-ttu-id="e22d1-138">$ $ \ Big | \braket{1 | \psı } \ Big | ^ 2 = \left | \frac{3 } {5 } \braket{1 | 1 } + \frac{4 } {5 } \braket{1 | 0 } \ Right | ^ 2 = \frac{9 } {25 } . $ $</span><span class="sxs-lookup"><span data-stu-id="e22d1-138">$$\big|\braket{1 | \psi}\big|^2= \left|\frac{3}{5}\braket{1 | 1} +\frac{4}{5}\braket{1 | 0}\right|^2=\frac{9}{25}.$$</span></span> 

### <a name="tensor-product-notation"></a><span data-ttu-id="e22d1-139">Tensor ürün gösterimi</span><span class="sxs-lookup"><span data-stu-id="e22d1-139">Tensor product notation</span></span>
<span data-ttu-id="e22d1-140">Dirac gösterimi Ayrıca, içindeki örtük bir Tensor ürün yapısını da içerir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-140">Dirac notation also includes an implicit tensor product structure within it.</span></span>  <span data-ttu-id="e22d1-141">Bu, hisse alma sırasında iki ilişkili hisse al kaydı tarafından tanımlanan eyalet vektörünün, iki durumlu vektörün tencursor ürünleri olduğundan önemlidir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-141">This is important because in quantum computing, the state vector described by two uncorrelated quantum registers is the tensor products of the two state vectors.</span></span>  <span data-ttu-id="e22d1-142">Bir hisse veya daha fazla öneme sahip olmak isterseniz, öz, Tensor ürün yapısını açıklayan veya önem taşıyan bir hesaplama açıklanmıştır.</span><span class="sxs-lookup"><span data-stu-id="e22d1-142">Concisely describing the tensor product structure, or lack thereof, is vital if you want to explain a quantum computation.</span></span>  <span data-ttu-id="e22d1-143">Tensor ürün yapısı, $ her iki hisse madevlet vektörü $ \phi $ ve $ \psi $ \ket \ PSI $ { } \ket \ { Fi } $, bazen açıkça $ \ket \ { PSI } \otimes \ket $ olarak yazılmış, { } ancak vektörlerin arasında $ \osüreler yazmak $ için $</span><span class="sxs-lookup"><span data-stu-id="e22d1-143">The tensor product structure implies that we can write $\psi \otimes \phi$ for any two quantum state vectors $\phi$ and $\psi$ as $\ket{\psi} \ket{\phi}$, sometimes explicitly written as $\ket{\psi} \otimes \ket{\phi}$, however by convention writing $\otimes$ in between the vectors is unnecessary.</span></span>  <span data-ttu-id="e22d1-144">Örneğin, sıfır duruma göre başlatılan iki qubits ile durum şu şekilde verilir</span><span class="sxs-lookup"><span data-stu-id="e22d1-144">For example, the state with two qubits initialized to the zero state is given by</span></span>

<span data-ttu-id="e22d1-145">$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \\ \\ 0 \end{ bmatrix } = \begin{1 0 \end{ bmatrix } \\ \\ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } \otimes \ket{0 } = \ket{0 } \ket{0 } .</span><span class="sxs-lookup"><span data-stu-id="e22d1-145">$$ \begin{bmatrix} 1 \\\\  0 \\\\  0 \\\\  0 \end{bmatrix}= \begin{bmatrix} 1 \\\\  0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \ket{0} \otimes \ket{0}= \ket{0} \ket{0}.</span></span>
$$

<span data-ttu-id="e22d1-146">Benzer şekilde, tam sayı için $ \ket{p } $ durum $p, $ tam sayı $p bir ikili gösterimde kodlayan bir hisse durumu temsil eder $ .</span><span class="sxs-lookup"><span data-stu-id="e22d1-146">Similarly,  the state $\ket{p}$ for integer $p$ represents a quantum state that encodes in binary representation the integer $p$.</span></span>  <span data-ttu-id="e22d1-147">Örneğin, $5 sayısını $ işaretsiz bir ikili kodlama kullanarak ifade etmek istiyoruz.</span><span class="sxs-lookup"><span data-stu-id="e22d1-147">For example, if we wish to express the number $5$ using an unsigned binary encoding we could equally express it as</span></span>

<span data-ttu-id="e22d1-148">$ $ \ket{1 } \ket{0 } \ket{1 } = \ket{101 } = \ket{5 } .</span><span class="sxs-lookup"><span data-stu-id="e22d1-148">$$ \ket{1}\ket{0}\ket{1} = \ket{101} = \ket{5}.</span></span>
$$

<span data-ttu-id="e22d1-149">Bu gösterimde $ \ket{0 } $ bir tek qubit duruma başvurmalıdır, ancak bunun yerine $0 ikili kodlamasını depolayan bir *qubit kaydı* vardır $ .</span><span class="sxs-lookup"><span data-stu-id="e22d1-149">Within this notation $\ket{0}$ need not refer to a single-qubit state but rather a *qubit register* storing a binary encoding of $0$.</span></span>  <span data-ttu-id="e22d1-150">Bu iki gösterimdeki farklar genellikle bağlamdan net değildir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-150">The differences between these two notations is usually clear from the context.</span></span>  <span data-ttu-id="e22d1-151">Bu kural, aşağıdaki yollarla yazılıyolabilen ilk örneği basitleştirmek için yararlıdır:</span><span class="sxs-lookup"><span data-stu-id="e22d1-151">This convention is useful for simplifying the first example which can be written in any of the following ways:</span></span>

<span data-ttu-id="e22d1-152">$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cnoktalar \otimes \begin { bmatrix } 1 \\ \\ 0 \ End{ bmatrix } = \ket{0 } \otimes \cnoktalar \otimes \ket{0 } = | 0 \cdots 0 \rangle = \ket{0 } ^ {\otimes n } = \ket{0 } .</span><span class="sxs-lookup"><span data-stu-id="e22d1-152">$$ \begin{bmatrix}1 \\\\  0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\  0 \end{bmatrix} = \ket{0} \otimes \cdots \otimes \ket{0}= |0\cdots 0\rangle = \ket{0}^{\otimes n} = \ket{0}.</span></span>
$$

### <a name="example-describing-superposition-with-dirac-notation"></a><span data-ttu-id="e22d1-153">Örnek: Dirac gösterimi ile süper konumu açıklama</span><span class="sxs-lookup"><span data-stu-id="e22d1-153">Example: Describing superposition with Dirac notation</span></span>
<span data-ttu-id="e22d1-154">Bir hisse düzeyini anlatmak için Dirac gösterimini nasıl kullanabileceğinizi gösteren başka bir örnek olarak, her bir olası bit dizesi için eşit bir süper konum olan hisse bir durum yazmak için aşağıdaki eşdeğer yöntemleri göz önünde bulundurun $n$</span><span class="sxs-lookup"><span data-stu-id="e22d1-154">As another example of how you can use Dirac notation to describe a quantum state, consider the following equivalent ways of writing a quantum state that is an equal superposition over every possible bit string of length $n$</span></span>

<span data-ttu-id="e22d1-155">$ $ H ^ {\otimes n } \ket{0 } = \frac{1 } {2 ^ {n/2 } } \ sum_ {j = 0 } ^ {2 ^ n-1 } \ket{j } = { \tus+} ^ {\otimes n } .</span><span class="sxs-lookup"><span data-stu-id="e22d1-155">$$ H^{\otimes n} \ket{0} = \frac{1}{2^{n/2}} \sum_{j=0}^{2^n-1} \ket{j} = \ket{+}^{\otimes n}.</span></span>
$$

<span data-ttu-id="e22d1-156">Burada toplamın neden $0 ' den $ $2 ^ {n-1 ' e kadar } $ $n bitler 'e geçgireceğini merak edebilirsiniz $ .</span><span class="sxs-lookup"><span data-stu-id="e22d1-156">Here you may wonder why the sum goes from $0$ to $2^{n}-1$ for $n$ bits.</span></span>  <span data-ttu-id="e22d1-157">İlk olarak, } $n bitlerin gerçekleştirebileceğine ilişkin $2 ^ {n $ farklı yapılandırma olduğunu unutmayın $ .</span><span class="sxs-lookup"><span data-stu-id="e22d1-157">First note that there are $2^{n}$ different configurations that $n$ bits can take.</span></span>  <span data-ttu-id="e22d1-158">Bu, bir bitin $2 $ değer alıp belirleyebilmesini, ancak iki bitin $4 değer alıp bu şekilde devam edebilir olduğunu belirterek görebilirsiniz $ .</span><span class="sxs-lookup"><span data-stu-id="e22d1-158">You can see this by noting that one bit can take $2$ values but two bits can take $4$ values and so forth.</span></span> <span data-ttu-id="e22d1-159">Bu, genel olarak, $2 ^ n $ farklı olası bit dizelerinin olduğu, ancak bunların hiçbirinde kodlandığı en büyük değerin $1 \cdots 1 = 2 ^ n-1 olduğu anlamına gelir $ ve bu nedenle toplamın üst sınırı budur.</span><span class="sxs-lookup"><span data-stu-id="e22d1-159">In general, this means that there are $2^n$ different possible bit strings but the largest value encoded in any of them $1\cdots 1=2^n-1$ and hence it is the upper limit for the sum.</span></span>
<span data-ttu-id="e22d1-160">Yan bir not olarak, bu { } { } } } notational kuralı genellikle her bir qubit, sıfıra başlatıldığından hesaplama tabanlı durum için ayrıldığından, bu örnekte $ \ket +} ^ {\otimes n = \ket +} $, benzerleme vurguladı ile $ \ket{0 ^ {\otimes n = \ket{0 $ kullandık.</span><span class="sxs-lookup"><span data-stu-id="e22d1-160">As a side note, in this example we did not use $\ket{+}^{\otimes n}=\ket{+}$ in analogy to $\ket{0}^{\otimes n} = \ket{0}$ because this notational convention is usually reserved for the computational basis state with every qubit initialized to zero.</span></span>  <span data-ttu-id="e22d1-161">Böyle bir kural bu durumda denenirken, hisse bilgi işlem belgelerinde işe alınamaz.</span><span class="sxs-lookup"><span data-stu-id="e22d1-161">While such a convention would be sensible in this case, it is not employed in the quantum computing literature.</span></span>

### <a name="expressing-linearity-with-dirac-notation"></a><span data-ttu-id="e22d1-162">Dirac gösterimi ile doğrity belirtme</span><span class="sxs-lookup"><span data-stu-id="e22d1-162">Expressing linearity with Dirac notation</span></span>
<span data-ttu-id="e22d1-163">Daha iyi bir Dirac gösterimi özelliği, doğrusal olduğu olgusaldır.</span><span class="sxs-lookup"><span data-stu-id="e22d1-163">Another nice feature of Dirac notation is the fact that it is linear.</span></span>  <span data-ttu-id="e22d1-164">Dört hisse alım durumu vektörü için yazmak istiyorsanız,</span><span class="sxs-lookup"><span data-stu-id="e22d1-164">If we wish to write for any four quantum state vectors,</span></span> 

<span data-ttu-id="e22d1-165">$ $ (\Alpha \ ayraç { \ psi } + \beta \ket { \fi } ) \otimes (\gama \ ayraç { \ çi } + \delta \ayraç \ { Omega } ) = \alfa \gamma \ ayraç { \ PSI \ } ayraç \ { çi } + \alfa \delta \ { } { } \gamma \ket { } { } \delta \ket { } { } [\</span><span class="sxs-lookup"><span data-stu-id="e22d1-165">$$(\alpha \ket{\psi} +\beta\ket{\phi})\otimes (\gamma \ket{\chi} + \delta \ket{\omega})= \alpha\gamma \ket{\psi}\ket{\chi} + \alpha\delta \ket{\psi}\ket{\omega}+\beta\gamma\ket{\phi}\ket{\chi}+\beta\delta\ket{\phi}\ket{\omega}.$$</span></span>

<span data-ttu-id="e22d1-166">Yani, durum vektörleri arasında tencursor ürünlerinin alınması normal çarpmaya benzer şekilde görünmesi için Dirac gösteriminde Tensor ürün gösterimini dağıtabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e22d1-166">That is to say, you can distribute the tensor product notation in Dirac notation so that taking tensor products between state vectors ends up looking just like ordinary multiplication.</span></span>

<span data-ttu-id="e22d1-167">Köşeli vektörler, demet vektörlerine benzer bir kural izler.</span><span class="sxs-lookup"><span data-stu-id="e22d1-167">Bra vectors follow a similar convention to ket vectors.</span></span>  <span data-ttu-id="e22d1-168">Örneğin, $ \bra { \ PSI } \bra { \phi } $ vektörü $ \psi ^ \gesger \otimes \phi ^ \hanger = (\psı \otimes \fi) ^ \hanger olan vector $ .</span><span class="sxs-lookup"><span data-stu-id="e22d1-168">For example, the vector $\bra{\psi}\bra{\phi}$ is equivalent to the state vector $\psi^\dagger \otimes \phi^\dagger=(\psi\otimes \phi)^\dagger$.</span></span> <span data-ttu-id="e22d1-169">Demet vektörü $ { \tus\psı $, } $ \Alpha \ket{0 } + \beta \ket{1 $ ise } Vector öğesinin köşeli vektör sürümü $ \bra { \ PSI } = \tus\psı { } ^ \gger = (\bra{0 } \Alpha ^ \* + \bra{1 } \beta ^ \*) $ şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-169">If the ket vector $\ket{\psi}$ is $\alpha \ket{0} + \beta \ket{1}$ then the bra vector version of the vector is $\bra{\psi}=\ket{\psi}^\dagger = (\bra{0}\alpha^\* +\bra{1}\beta^\*)$.</span></span>

<span data-ttu-id="e22d1-170">Örnek olarak, $ { \tus\psı } = \frac{3 } {5 } \ket{1 } + \frac{4 {5 \ket{0 } $ durumunun } } $ \ket { +} $ veya $ \tus-} $ olduğunu ölçmek için bir hisse öğesi kullanarak { $</span><span class="sxs-lookup"><span data-stu-id="e22d1-170">As an example, imagine that we wish to calculate the probability of measuring the state $\ket{\psi} = \frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}$ using a quantum program for measuring states to be either $\ket{+}$ or $\ket{-}$.</span></span> <span data-ttu-id="e22d1-171">Daha sonra, cihazın durumun $ \ket-} $ olduğunu belirten bir olasılık {</span><span class="sxs-lookup"><span data-stu-id="e22d1-171">Then the probability that the device would output that the state is $\ket{-}$ is</span></span> 

<span data-ttu-id="e22d1-172">$ $ | { \bratus-| \psı } | ^ 2 = \left | \frac{1 } {\sqrt{2 } } (\bra{0 } -\bra{1 } ) (\frac{3 } {5 } \ket{1 } + \frac{4 } {5 } \ket{0 } ) \ doğru | ^ 2 = \left | -\frac{3 } {5 \sqrt {2 } } + \frac{4 } {5 \sqrt {2 } } \ Right | ^ 2 = \frac{1 } {50 } . $ $</span><span class="sxs-lookup"><span data-stu-id="e22d1-172">$$|\braket{- | \psi}|^2= \left|\frac{1}{\sqrt{2}}(\bra{0} - \bra{1})(\frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}) \right|^2=\left|-\frac{3}{5\sqrt{2}} + \frac{4}{5\sqrt{2}}\right|^2=\frac{1}{50}.$$</span></span>

<span data-ttu-id="e22d1-173">Negatif işaretin olasılık hesaplamasında görünmesi, hisse alma 'nın klasik bilgi işlem üzerinden daha fazla avantaj elde eden mekanizmalardan biridir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-173">The fact that the negative sign appears in the calculation of the probability is a manifestation of quantum interference, which is one of the mechanisms by which quantum computing gains advantages over classical computing.</span></span>

## <a name="ketbra-or-outer-product"></a><span data-ttu-id="e22d1-174">ketya veya dış ürün</span><span class="sxs-lookup"><span data-stu-id="e22d1-174">ketbra or outer product</span></span>
<span data-ttu-id="e22d1-175">Dirac gösterimi ile tartışmak için en son öğe, *ketya* veya dış üründür.</span><span class="sxs-lookup"><span data-stu-id="e22d1-175">The final item worth discussing in Dirac notation is the *ketbra* or outer product.</span></span>  <span data-ttu-id="e22d1-176">Dış ürün, $ { \tus\psı \bra \phi $ olarak Dirac gösterimler içinde temsil edilir } { } ve bazen Bras ve kets, brakets olarak ters sırada gerçekleştiğinden, bazı durumlarda ketbras olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="e22d1-176">The outer product is represented within Dirac notations as $\ket{\psi} \bra{\phi}$, and sometimes called ketbras because the bras and kets occur in the opposite order as brakets.</span></span>  <span data-ttu-id="e22d1-177">Dış ürün, t\ket { \ PSI } \bra { \phi } = \psı \ Fi ^ \linger $ $ \psi $ ve $ \fi $ olarak matris çarpma aracılığıyla tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="e22d1-177">The outer product is defined via matrix multiplication as $\ket{\psi} \bra{\phi} = \psi \phi^\dagger$ for quantum state vectors $\psi$ and $\phi$.</span></span>  <span data-ttu-id="e22d1-178">Bu gösterimi en basit ve en sık kullanılan örnek,</span><span class="sxs-lookup"><span data-stu-id="e22d1-178">The simplest, and arguably most common example of this notation, is</span></span>

<span data-ttu-id="e22d1-179">$ $ \ket{0 } \bra{0 } = \begin{ bmatrix } 1 \\\\ 0 \end{ bmatrix } \begin{ bmatrix } 1&0 \end{ bmatrix } = \begin{ bmatrix } 1 &0 \\\\ 0 &0 \end{bmatrix} \ qquad \ket{1 } \bra{1 } = \begin{ bmatrix } 0 \\\\ 1 \end{ bmatrix } \begin{} 0 bmatrix&1 \end{ bmatrix } = \begin{ bmatrix } 0 &0 \\\\ 0 &1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="e22d1-179">$$ \ket{0} \bra{0} = \begin{bmatrix}1\\\\ 0 \end{bmatrix}\begin{bmatrix}1&0 \end{bmatrix}= \begin{bmatrix}1 &0\\\\ 0 &0\end{bmatrix} \qquad \ket{1} \bra{1} = \begin{bmatrix}0\\\\ 1 \end{bmatrix}\begin{bmatrix}0&1 \end{bmatrix}= \begin{bmatrix}0 &0\\\\ 0 &1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="e22d1-180">Ketbras, her zaman sabit bir değere bir hisse durumu yansıdığından Projektör olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="e22d1-180">Ketbras are often called projectors because they project a quantum state onto a fixed value.</span></span>  <span data-ttu-id="e22d1-181">Bu işlemler Unitary olmadığından (ve bir vektör 'nin norm de korumadığından), bir hisse bilgisayarının bir projektörün bir projektörü kesin bir şekilde uygulayamaması halinde gelmelidir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-181">Since these operations are not unitary (and do not even preserve the norm of a vector), it should come as no surprise that a quantum computer cannot deterministically apply a projector.</span></span>  <span data-ttu-id="e22d1-182">Ancak, bir hisse başında ölçüm durumundaki eylemi açıklayan güzel bir iş vardır.</span><span class="sxs-lookup"><span data-stu-id="e22d1-182">However projectors do a beautiful job of describing the action that measurement has on a quantum state.</span></span>  <span data-ttu-id="e22d1-183">Örneğin, $ \ket \ PSI $ değerini $0 olarak ölçyoruz, { } $ Bu durumda durum deneyimlerinin bir sonucu olarak ortaya çıkan dönüşümdür</span><span class="sxs-lookup"><span data-stu-id="e22d1-183">For example, if we measure a state $\ket{\psi}$ to be $0$ then the resulting transformation that the state experiences as a result of the measurement is</span></span>

  <span data-ttu-id="e22d1-184">$ $ \ demet { \ PSI } \sağtarrow \frac { (\ket{0 } \bra{0 } ) \demet { \ PSI } } {| \braket{0 | \psı } |} = \ket{0 } , $ $</span><span class="sxs-lookup"><span data-stu-id="e22d1-184">$$\ket{\psi} \rightarrow \frac{(\ket{0} \bra{0})\ket{\psi}}{|\braket{0 | \psi}|}= \ket{0},$$</span></span>

<span data-ttu-id="e22d1-185">Bunlardan biri, durumu ölçmenizi ve $ \ket{0 $ olacak şekilde bulmayı bekler } .</span><span class="sxs-lookup"><span data-stu-id="e22d1-185">as one expects if you were to measure the state and find it to be $\ket{0}$.</span></span>  <span data-ttu-id="e22d1-186">Yeniden yinelemek için, bu tür projektörler bir hisse bir bilgisayardaki bir duruma göre belirlenebilir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-186">To reiterate, such projectors cannot be applied on a state in a quantum computer deterministically.</span></span>  <span data-ttu-id="e22d1-187">Bunun yerine, } bazı sabit olasılığa sahip $ \ket{0 $ sonucu ile en iyi şekilde rastgele uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-187">Instead, they can at best be applied randomly with the result $\ket{0}$ appearing with some fixed probability.</span></span>  <span data-ttu-id="e22d1-188">Bu tür bir ölçünün başarılı olma olasılığı, devlet projektörün beklentisi değeri olarak yazılabilir</span><span class="sxs-lookup"><span data-stu-id="e22d1-188">The probability of such a measurement succeeding can be written as the expectation value of the quantum projector in the state</span></span>

<span data-ttu-id="e22d1-189">$ $ \bra { \ PSI } (\ket{0 } \bra{0 } ) \ayraç { \ PSI } = | \bratus\psi { | 0 } | ^ 2, $ $</span><span class="sxs-lookup"><span data-stu-id="e22d1-189">$$ \bra{\psi} (\ket{0} \bra{0})\ket{\psi} = |\braket{\psi | 0}|^2, $$</span></span>

<span data-ttu-id="e22d1-190">Bu, projektörlerin ölçüm sürecini ifade etmenin yeni bir yolunu sunışını gösterir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-190">which illustrates that projectors simply give a new way of expressing the measurement process.</span></span>

<span data-ttu-id="e22d1-191">Bunun yerine, Multi-qubit durumunun $1 olması için ilk qubit 'in ölçülmesini düşünmemiz durumunda, $ Bu işlemi projektör ve Dirac gösterimini kullanarak kolayca de açıklayabilir:</span><span class="sxs-lookup"><span data-stu-id="e22d1-191">If instead we consider measuring the first qubit of a multi-qubit state to be $1$ then we can also describe this process conveniently using projectors and Dirac notation:</span></span>

<span data-ttu-id="e22d1-192">$ $ P (\Text{First qubit = 1 } ) = \bra { \ PSI } \left (\ket{1 } \bra{1 } \otimes \cıvabitti ^ {\otimes n-1 } \ right) { \tus\psi } .</span><span class="sxs-lookup"><span data-stu-id="e22d1-192">$$ P(\text{first qubit = 1})= \bra{\psi}\left(\ket{1}\bra{1}\otimes \boldone^{\otimes n-1}\right) \ket{\psi}.</span></span>
$$

<span data-ttu-id="e22d1-193">Burada kimlik matrisi, şu şekilde Dirac gösteriminde kolayca yazılabilir</span><span class="sxs-lookup"><span data-stu-id="e22d1-193">Here the identity matrix can be conveniently written in Dirac notation as</span></span>

<span data-ttu-id="e22d1-194">$ $ \ cıvadone = \ket{0 } \bra{0 } + \ket{1 } \bra{1 } = \begin{ bmatrix } 1&0 \\\\ 0&1 \ End{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="e22d1-194">$$ \boldone = \ket{0} \bra{0}+\ket{1} \bra{1}= \begin{bmatrix}1&0\\\\ 0&1 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="e22d1-195">İki-qubit olduğu durumlarda, projektörün şu şekilde genişletilebileceği</span><span class="sxs-lookup"><span data-stu-id="e22d1-195">For the case where there are two-qubits the projector can be expanded as</span></span> 

<span data-ttu-id="e22d1-196">$ $ \ket{1 } \bra{1 } \otimes \ID = \ket{1 } \bra{1 } \otimes (\ket{0 } \bra{0 } + \ket{1 } \bra{1 } ) = \ket{10 } \bra{10 } + \ket{11 } \bra{11 } .</span><span class="sxs-lookup"><span data-stu-id="e22d1-196">$$ \ket{1} \bra{1} \otimes \id = \ket{1}\bra{1} \otimes (\ket{0} \bra{0}+\ket{1} \bra{1})= \ket{10}\bra{10} + \ket{11}\bra{11}.</span></span>
$$

<span data-ttu-id="e22d1-197">Daha sonra bunun, sütun vektörü gösterimi kullanılarak multiqubit durumları için ölçüm likelihoods hakkındaki tartışmaya tutarlı olduğunu görebiliriz:</span><span class="sxs-lookup"><span data-stu-id="e22d1-197">We can then see that this is consistent with the discussion about measurement likelihoods for multiqubit states using column-vector notation:</span></span>

<span data-ttu-id="e22d1-198">$ $ P (\Text{First qubit = 1 } ) = \psi ^ \dağılım (e e \_ {10} \_ {10 ^ \dağılım } + e e \_ {11} \_ {11 } ^ \dağılım) \psı = | e \_ {10 } ^ \ dağılım \ PSI | ^ 2 + | e \_ {11 } ^ \dağılım \psı | ^ 2, $ $</span><span class="sxs-lookup"><span data-stu-id="e22d1-198">$$ P(\text{first qubit = 1})= \psi^\dagger (e\_{10}e\_{10}^\dagger + e\_{11}e\_{11}^\dagger)\psi = |e\_{10}^\dagger \psi|^2 + |e\_{11}^\dagger \psi|^2, $$</span></span>

<span data-ttu-id="e22d1-199">Multi-qubit ölçüm tartışmayla eşleşir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-199">which matches the multi-qubit measurement discussion.</span></span>  <span data-ttu-id="e22d1-200">Ancak, bu sonucun Multi-qubit örneğine genelleştirmeye yönelik Genelleştirme, sütun vektörü gösteriminden daha basit olan Dirac gösterimi kullanılarak hızlı bir şekilde daha basittir ve önceki işleme tamamen eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-200">The generalization of this result to the multi-qubit case, however, is slightly more straightforward to express using Dirac notation than column-vector notation, and is entirely equivalent to the previous treatment.</span></span>

## <a name="density-operators"></a><span data-ttu-id="e22d1-201">Yoğunluk işleçleri</span><span class="sxs-lookup"><span data-stu-id="e22d1-201">Density operators</span></span>

<span data-ttu-id="e22d1-202">Dirac gösterimini kullanarak hızlı bir şekilde başka bir yararlı operatör de *durum işleci*olarak da bilinen bir *yoğunluk işleçtir*.</span><span class="sxs-lookup"><span data-stu-id="e22d1-202">Another useful operator to express using Dirac notation is a *density operator*, sometimes also known as a *state operator*.</span></span>
<span data-ttu-id="e22d1-203">Hisse bir ABD devleti için bir yoğunluk işleci $ \rho = { \tus\psı } \bra { \ PSI $ biçimini alır } .</span><span class="sxs-lookup"><span data-stu-id="e22d1-203">A density operator for a quantum state vector takes the form $\rho = \ket{\psi} \bra{\psi}$.</span></span>
<span data-ttu-id="e22d1-204">Durumu bir açıklama yerine matris olarak temsil eden bu kavram, genellikle yararlı olur, çünkü olasılık hesaplamalarını temsil etmek için kullanışlı bir yöntem sunar ve ayrıca bir birinin aynı formalronizde aynı şekilde hem istatistiksel olmayan belirsizlik hem de aynı şekilde, aynı şekilde, aynı şekilde, hem istatistiksel unilkliği hem de</span><span class="sxs-lookup"><span data-stu-id="e22d1-204">This concept of representing the state as a matrix, rather than a vector, is often convenient because it gives a convenient way of representing probability calculations, and also allows one to describe both statistical uncertainty as well as quantum uncertainty within the same formalism.</span></span>
<span data-ttu-id="e22d1-205">Vektörlerden farklı olarak genel hisse alım işleçleri, bazı hisse bilgi işlem alanlarında ve alanın temel bilgilerini anlamak için gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-205">General quantum state operators, rather than vectors, are ubiquitous in some areas of quantum computing but are not necessary to understand the basics of the field.</span></span>
<span data-ttu-id="e22d1-206">İlgilendiğiniz okuyucu için, [daha fazla bilgi için](xref:microsoft.quantum.more-information)' de sunulan başvuru defterlerinden birini okumanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="e22d1-206">For the interested reader, we recommend reading one of the reference books provided in [For more information](xref:microsoft.quantum.more-information).</span></span>

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a><span data-ttu-id="e22d1-207">S # ağ geçidi dizileri hisse durumlarıyla eşdeğer</span><span class="sxs-lookup"><span data-stu-id="e22d1-207">Q# gate sequences equivalent to quantum states</span></span>
<span data-ttu-id="e22d1-208">Aylık gösterimi ve Q # programlama dili hakkında en son bir nokta: Bu belgenin onkümesinde, hisse Eyaleti 'nin hisse bilgi işlem ortamında temel nesne olduğunu belirttik.</span><span class="sxs-lookup"><span data-stu-id="e22d1-208">A final point worth raising about quantum notation and the Q# programming language: at the onset of this document we mentioned that the quantum state is the fundamental object of information in quantum computing.</span></span>  <span data-ttu-id="e22d1-209">Daha sonra, soru-cevap durumu kavramı olmadığı için soru-cevap olarak gelebilir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-209">It may then come as a surprise that in Q# there is no notion of a quantum state.</span></span>  <span data-ttu-id="e22d1-210">Bunun yerine, tüm durumlar yalnızca bunları hazırlamak için kullanılan işlemler tarafından açıklanmıştır.</span><span class="sxs-lookup"><span data-stu-id="e22d1-210">Instead, all states are described only by the operations used to prepare them.</span></span>  <span data-ttu-id="e22d1-211">Önceki örnek bunun mükemmel bir çizimidir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-211">The previous example is an excellent illustration of this.</span></span>  <span data-ttu-id="e22d1-212">Bir kayıttaki her hisse bit dizesinde Tekdüzen üst konumunu ifade etmek yerine, sonucu $H ^ {\otimes n } \ket{0 $ olarak temsil edebiliriz } .</span><span class="sxs-lookup"><span data-stu-id="e22d1-212">Rather than expressing a uniform superposition over every quantum bit string in a register, we can represent the result as $H^{\otimes n} \ket{0}$.</span></span>  <span data-ttu-id="e22d1-213">Bu durumun katlanarak daha kısa olan bu açıklaması yalnızca, bununla ilgili olarak neden olabilecek avantaja sahip olmakla kalmaz, Ayrıca öz, algoritmayı uygulamak için yazılım yığınında yayılması gereken işlemleri tanımlar.</span><span class="sxs-lookup"><span data-stu-id="e22d1-213">This exponentially shorter description of the state not only has the advantage that we can classically reason about it, but it also concisely defines the operations needed to be propagated through the software stack to implement the algorithm.</span></span>  <span data-ttu-id="e22d1-214">Bu nedenle, Q #, hisse durumlarından değil, kapı dizilerini göstermek için tasarlanmıştır; Ancak, teorik düzeyinde iki perspektif eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="e22d1-214">For this reason, Q# is designed to emit gate sequences rather than quantum states; however, at a theoretical level the two perspectives are equivalent.</span></span>
