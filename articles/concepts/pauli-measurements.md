---
<span data-ttu-id="922ca-101">Başlık: Pauli ölçümleri açıklaması: tek ve Multi-qubit Pauli ölçüm işlemleriyle nasıl çalışacağınızı öğrenin.</span><span class="sxs-lookup"><span data-stu-id="922ca-101">title: Pauli Measurements description: Learn how to work with single- and multi-qubit Pauli measurement operations.</span></span>
<span data-ttu-id="922ca-102">Yazar: bradben uid: Microsoft. hisse. Concepts. Pauli MS. Author: v-benköşeli MS. Date: 12/11/2017 MS. Topic: Makale No-loc:</span><span class="sxs-lookup"><span data-stu-id="922ca-102">author: bradben uid: microsoft.quantum.concepts.pauli ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="922ca-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="922ca-103">"Q#"</span></span>
- <span data-ttu-id="922ca-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="922ca-104">"$$v"</span></span>
- <span data-ttu-id="922ca-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="922ca-105">"$$"</span></span>
- <span data-ttu-id="922ca-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="922ca-106">"$$"</span></span>
- <span data-ttu-id="922ca-107">"$"</span><span class="sxs-lookup"><span data-stu-id="922ca-107">"$"</span></span>
- <span data-ttu-id="922ca-108">"$"</span><span class="sxs-lookup"><span data-stu-id="922ca-108">"$"</span></span>
- <span data-ttu-id="922ca-109">"$"</span><span class="sxs-lookup"><span data-stu-id="922ca-109">"$"</span></span>
- <span data-ttu-id="922ca-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="922ca-110">"$$"</span></span>
- <span data-ttu-id="922ca-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="922ca-111">"\cdots"</span></span>
- <span data-ttu-id="922ca-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="922ca-112">"bmatrix"</span></span>
- <span data-ttu-id="922ca-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="922ca-113">"\ddots"</span></span>
- <span data-ttu-id="922ca-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="922ca-114">"\equiv"</span></span>
- <span data-ttu-id="922ca-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="922ca-115">"\sum"</span></span>
- <span data-ttu-id="922ca-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="922ca-116">"\begin"</span></span>
- <span data-ttu-id="922ca-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="922ca-117">"\end"</span></span>
- <span data-ttu-id="922ca-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="922ca-118">"\sqrt"</span></span>
- <span data-ttu-id="922ca-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="922ca-119">"\otimes"</span></span>
- <span data-ttu-id="922ca-120">"{"</span><span class="sxs-lookup"><span data-stu-id="922ca-120">"{"</span></span>
- <span data-ttu-id="922ca-121">"}"</span><span class="sxs-lookup"><span data-stu-id="922ca-121">"}"</span></span>
- <span data-ttu-id="922ca-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="922ca-122">"\text"</span></span>
- <span data-ttu-id="922ca-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="922ca-123">"\phi"</span></span>
- <span data-ttu-id="922ca-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="922ca-124">"\kappa"</span></span>
- <span data-ttu-id="922ca-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="922ca-125">"\psi"</span></span>
- <span data-ttu-id="922ca-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="922ca-126">"\alpha"</span></span>
- <span data-ttu-id="922ca-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="922ca-127">"\beta"</span></span>
- <span data-ttu-id="922ca-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="922ca-128">"\gamma"</span></span>
- <span data-ttu-id="922ca-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="922ca-129">"\delta"</span></span>
- <span data-ttu-id="922ca-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="922ca-130">"\omega"</span></span>
- <span data-ttu-id="922ca-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="922ca-131">"\bra"</span></span>
- <span data-ttu-id="922ca-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="922ca-132">"\ket"</span></span>
- <span data-ttu-id="922ca-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="922ca-133">"\boldone"</span></span>
- <span data-ttu-id="922ca-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="922ca-134">"\\\\"</span></span>
- <span data-ttu-id="922ca-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="922ca-135">"\\"</span></span>
- <span data-ttu-id="922ca-136">"="</span><span class="sxs-lookup"><span data-stu-id="922ca-136">"="</span></span>
- <span data-ttu-id="922ca-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="922ca-137">"\frac"</span></span>
- <span data-ttu-id="922ca-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="922ca-138">"\text"</span></span>
- <span data-ttu-id="922ca-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="922ca-139">"\mapsto"</span></span>
- <span data-ttu-id="922ca-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="922ca-140">"\dagger"</span></span>
- <span data-ttu-id="922ca-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="922ca-141">"\to"</span></span>
- <span data-ttu-id="922ca-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="922ca-142">"\begin{cases}"</span></span>
- <span data-ttu-id="922ca-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="922ca-143">"\end{cases}"</span></span>
- <span data-ttu-id="922ca-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="922ca-144">"\operatorname"</span></span>
- <span data-ttu-id="922ca-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="922ca-145">"\braket"</span></span>
- <span data-ttu-id="922ca-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="922ca-146">"\id"</span></span>
- <span data-ttu-id="922ca-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="922ca-147">"\expect"</span></span>
- <span data-ttu-id="922ca-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="922ca-148">"\defeq"</span></span>
- <span data-ttu-id="922ca-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="922ca-149">"\variance"</span></span>
- <span data-ttu-id="922ca-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="922ca-150">"\dd"</span></span>
- <span data-ttu-id="922ca-151">"&"</span><span class="sxs-lookup"><span data-stu-id="922ca-151">"&"</span></span>
- <span data-ttu-id="922ca-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="922ca-152">"\begin{align}"</span></span>
- <span data-ttu-id="922ca-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="922ca-153">"\end{align}"</span></span>
- <span data-ttu-id="922ca-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="922ca-154">"\Lambda"</span></span>
- <span data-ttu-id="922ca-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="922ca-155">"\lambda"</span></span>
- <span data-ttu-id="922ca-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="922ca-156">"\Omega"</span></span>
- <span data-ttu-id="922ca-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="922ca-157">"\mathrm"</span></span>
- <span data-ttu-id="922ca-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="922ca-158">"\left"</span></span>
- <span data-ttu-id="922ca-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="922ca-159">"\right"</span></span>
- <span data-ttu-id="922ca-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="922ca-160">"\qquad"</span></span>
- <span data-ttu-id="922ca-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="922ca-161">"\times"</span></span>
- <span data-ttu-id="922ca-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="922ca-162">"\big"</span></span>
- <span data-ttu-id="922ca-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="922ca-163">"\langle"</span></span>
- <span data-ttu-id="922ca-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="922ca-164">"\rangle"</span></span>
- <span data-ttu-id="922ca-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="922ca-165">"\bigg"</span></span>
- <span data-ttu-id="922ca-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="922ca-166">"\Big"</span></span>
- <span data-ttu-id="922ca-167">"|"</span><span class="sxs-lookup"><span data-stu-id="922ca-167">"|"</span></span>
- <span data-ttu-id="922ca-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="922ca-168">"\mathbb"</span></span>
- <span data-ttu-id="922ca-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="922ca-169">"\vec"</span></span>
- <span data-ttu-id="922ca-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="922ca-170">"\in"</span></span>
- <span data-ttu-id="922ca-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="922ca-171">"\texttt"</span></span>
- <span data-ttu-id="922ca-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="922ca-172">"\ne"</span></span>
- <span data-ttu-id="922ca-173">"<"</span><span class="sxs-lookup"><span data-stu-id="922ca-173">"<"</span></span>
- <span data-ttu-id="922ca-174">">"</span><span class="sxs-lookup"><span data-stu-id="922ca-174">">"</span></span>
- <span data-ttu-id="922ca-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="922ca-175">"\leq"</span></span>
- <span data-ttu-id="922ca-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="922ca-176">"\geq"</span></span>
- <span data-ttu-id="922ca-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="922ca-177">"~~"</span></span>
- <span data-ttu-id="922ca-178">"~"</span><span class="sxs-lookup"><span data-stu-id="922ca-178">"~"</span></span>
- <span data-ttu-id="922ca-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="922ca-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="922ca-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="922ca-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="922ca-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="922ca-181">"\_"</span></span>

---

# <a name="pauli-measurements"></a><span data-ttu-id="922ca-182">Pauli ölçümleri</span><span class="sxs-lookup"><span data-stu-id="922ca-182">Pauli Measurements</span></span>

<span data-ttu-id="922ca-183">Önceki tartışmalarda hesaplama tabanlı ölçümlere odaklandık.</span><span class="sxs-lookup"><span data-stu-id="922ca-183">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="922ca-184">Aslında, notational perspektifinden, işlem tabanlı ölçümlerde hızlı bir şekilde ifade etmek için uygun olan, hisse kullanımı açısından oluşan diğer yaygın ölçümler vardır.</span><span class="sxs-lookup"><span data-stu-id="922ca-184">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="922ca-185">İle çalışırken Q# , çalıştırdığınız en yaygın ölçüm türü, diğer tabanlarda ölçümleri dahil etmek üzere hesaplama tabanlı ölçümleri *Pauli measurements* genelleştirmesi ve farklı qugeler arasında eşlik olması olasıdır.</span><span class="sxs-lookup"><span data-stu-id="922ca-185">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements* , which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="922ca-186">Bu gibi durumlarda, bir Pauli işlecinin, genel olarak $ x, Y, z $ veya $ z \otimes z, x \otimes x, x \otimes Y $ , vb. gibi bir operatör ölçmesi konusunda tartışmak yaygındır.</span><span class="sxs-lookup"><span data-stu-id="922ca-186">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
<span data-ttu-id="922ca-187">> ' De Q# , Multi-qubit Pauli işleçleri genellikle türündeki diziler tarafından temsil edilir `Pauli[]` .</span><span class="sxs-lookup"><span data-stu-id="922ca-187">> In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
<span data-ttu-id="922ca-188">> Örneğin, $ X Z Y 'yi göstermek için \otimes \otimes $ dizisini kullanabilirsiniz `[PauliX, PauliZ, PauliY]` .</span><span class="sxs-lookup"><span data-stu-id="922ca-188">> For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="922ca-189">Pauli işleçleri açısından ölçüm ele alınması, özellikle de hisse hata düzeltmesinin alt alanında ortaktır.</span><span class="sxs-lookup"><span data-stu-id="922ca-189">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="922ca-190">İçinde Q# , benzer bir kuralı izliyoruz; artık ölçümlerin bu alternatif görünümünü açıkladık.</span><span class="sxs-lookup"><span data-stu-id="922ca-190">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="922ca-191">Pauli ölçüsünün nasıl düşündüğünün ayrıntılarına geçmeden önce, hisse bir bilgisayar içinde tek bir qubit 'in ne ölçmeye yönelik olduğunu düşünmek yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="922ca-191">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="922ca-192">Bir $ n $ -qubit hisse anımız olduğunu düşünün; ardından, bir qubit, $ $ durumun içinde yer aldığı 2 ^ n olasılıkların yarısını ölçmelidir.</span><span class="sxs-lookup"><span data-stu-id="922ca-192">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="922ca-193">Diğer bir deyişle, ölçüm, hisse durumunu iki yarım boşluktan birine göre projeler.</span><span class="sxs-lookup"><span data-stu-id="922ca-193">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="922ca-194">Bu ıntut 'i yansıtmak için ölçüm hakkında düşündüğünüzden bahsede genelleştireceğiz.</span><span class="sxs-lookup"><span data-stu-id="922ca-194">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="922ca-195">Bu alt boşlukların öz belirlemek için, bunları açıklamak için bir dile ihtiyacımız var.</span><span class="sxs-lookup"><span data-stu-id="922ca-195">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="922ca-196">İki alt boşluğu tanımlamanın bir yolu, kural tarafından \pm 1 olacak şekilde yalnızca iki benzersiz eigenvalues içeren bir matrisi belirtmektir $ $ .</span><span class="sxs-lookup"><span data-stu-id="922ca-196">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="922ca-197">Alt boşlukları bu şekilde açıklayan basit bir örnek için Z 'yi düşünün $ $ :</span><span class="sxs-lookup"><span data-stu-id="922ca-197">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

$$
\begin{align}
  <span data-ttu-id="922ca-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="922ca-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="922ca-199">Pauli- $ Z matrisinin köşegen öğelerini okuyarak $ , $ Z 'nin $ $ \ket { } $ $ \ket { } $ karşılık gelen eigenvalues $ \pm 1 ile $ iki eigenvektörün olduğunu, 0 ve 1 olduğunu görebiliriz.</span><span class="sxs-lookup"><span data-stu-id="922ca-199">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="922ca-200">Bu nedenle, qubit ' i ölçyoruz ve `Zero` (0 durumuna karşılık gelir $ \ket { } $ ), qubitin durumunun $ $ Z işlecinin + 1 eigenstate olduğunu biliyoruz $ $ .</span><span class="sxs-lookup"><span data-stu-id="922ca-200">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="922ca-201">Benzer şekilde, elde etmemiz durumunda `One` , qubitimizin durumunun $ Z-1 $ eigenstate olduğunu biliyoruz $ $ . Bu işlem, Pauli ölçümlerinin dilinde "ölçüm Pauli $ Z" olarak adlandırılır $ ve hesaplama tabanlı ölçüm gerçekleştirmeyle tamamen eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="922ca-201">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$. This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="922ca-202">$ \times $ Z 'nin Unitary dönüştürmesi olan 2 2 matrisi $ $ de bu ölçütleri karşılar.</span><span class="sxs-lookup"><span data-stu-id="922ca-202">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="922ca-203">Diğer bir deyişle, $ bir = u ^ \dagger Z u matrisi, a 'nın $ $ $ $ \pm 1 eigenvektörlerinde bir ölçünün iki sonucunu tanımlayan bir matris vermek için başka bir Unitary matrisi $ de kullanabiliriz.</span><span class="sxs-lookup"><span data-stu-id="922ca-203">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="922ca-204">Pauli ölçülerinin gösterimi, $ X, Y, Z $ ölçümlerini bir qubitden bilgi elde etmek için yaptığı eşdeğer ölçümler olarak tanımlayarak bu Unitary denklik 'e başvurur.</span><span class="sxs-lookup"><span data-stu-id="922ca-204">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="922ca-205">Bu ölçümler, kolaylık sağlamak için aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="922ca-205">These measurements are given below for convenience.</span></span>


<span data-ttu-id="922ca-206">|Pauli ölçüm  | Unitary dönüşümü  |</span><span class="sxs-lookup"><span data-stu-id="922ca-206">|Pauli Measurement  |Unitary transformation  |</span></span>
|-------------------|------------------------|
<span data-ttu-id="922ca-207">|$ $ Z |               $\boldone$             |</span><span class="sxs-lookup"><span data-stu-id="922ca-207">| $Z$               | $\boldone$             |</span></span>
<span data-ttu-id="922ca-208">|$ $ X | $H               $                    |</span><span class="sxs-lookup"><span data-stu-id="922ca-208">| $X$               | $H$                    |</span></span>
<span data-ttu-id="922ca-209">|$ $ Y | $HS ^               {\dagger}$         |</span><span class="sxs-lookup"><span data-stu-id="922ca-209">| $Y$               | $HS^{\dagger}$         |</span></span>

<span data-ttu-id="922ca-210">Diğer bir deyişle, bu dil kullanıldığında, "ölçüm $ Y $ ", HS 'yi uygulama $ \dagger $ ve sonra hesaplama temelinde ölçme ile eşdeğerdir; burada [`S`](xref:Microsoft.Quantum.Intrinsic.S) bazen "aşama kapısı" olarak adlandırılan ve Unitary matrisi tarafından benzetilen bir iç hisse dır</span><span class="sxs-lookup"><span data-stu-id="922ca-210">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:Microsoft.Quantum.Intrinsic.S) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

$$
\begin{align}
    <span data-ttu-id="922ca-211">S =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="922ca-211">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="922ca-212">1 & 0 \\\\ 0 & ı \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="922ca-212">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="922ca-213">Ayrıca, $ HS ^ \dagger $ ' i hisse durumu vektörüne uygulamak ve ardından Z ölçüsüne benzer ve $ $ aşağıdaki işlem ile eşdeğerdir `Measure([PauliY], [q])` :</span><span class="sxs-lookup"><span data-stu-id="922ca-213">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        Adjoint S(q);
        H(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="922ca-214">Doğru durum daha sonra hesaplama temeline geri dönüştürülmesiyle, bu işlem, her ne kadar ücretli bir vektöre uygulanacak olan miktarları, $ $ Yukarıdaki kod parçacığında otomatik olarak, blok kullanılarak gerçekleştirilir `within … apply` .</span><span class="sxs-lookup"><span data-stu-id="922ca-214">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="922ca-215">' De, sonucu Q# ---, durum---ile etkileşimde bulunmalarından ayıklanan klasik bilgiler j sıfır değeri ile belirtilir ve bu, `Result` $ \in \\ { \texttt { } \texttt { } \\ } $ sonucun $ Pauli işlecinin (-1) ^ j $ eigeninin ölçüldüğü bir değer olup olmadığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="922ca-215">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="922ca-216">Birden çok qubit ölçümleri</span><span class="sxs-lookup"><span data-stu-id="922ca-216">Multiple-qubit measurements</span></span>

<span data-ttu-id="922ca-217">Multi-qubitpauli işleçlerinin ölçümleri benzer şekilde, şöyle görüldüğü gibi tanımlanmıştır:</span><span class="sxs-lookup"><span data-stu-id="922ca-217">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

$$
<span data-ttu-id="922ca-218">Z \otimes z = \begin{bmatrix} 1 & 0 0 0 & & \\\\  0 & -1 & 0 & 0 \\\\ 0 & 0 & -1 & 0 \\\\ 0 0 0 & & & 1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="922ca-218">Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="922ca-219">Bu nedenle, iki Pauli-Z işleçlerinin Tensor ürünleri, $ $ $ + 1 $ ve $ -1 $ eigenvalues içeren iki boşluktan oluşan bir matris oluşturur.</span><span class="sxs-lookup"><span data-stu-id="922ca-219">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="922ca-220">Tek qubit durumunda olduğu gibi, her ikisi de erişilebilir vektör alanının yarısını $ + 1 $ egenine ve kalan yarı $ -1 $ eigenine ait olan bir yarı alan anlamı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="922ca-220">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="922ca-221">Genel olarak, Pauli-Z işleçleri için herhangi bir Tensor ürününün $ ve kimliğin bu ürüne de duyarlı olduğu Tensor ürünü tanımından kolayca bakmak kolaydır $ .</span><span class="sxs-lookup"><span data-stu-id="922ca-221">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="922ca-222">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="922ca-222">For example,</span></span>

$$
\begin{align}
    <span data-ttu-id="922ca-223">\otimes \boldone Z =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="922ca-223">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="922ca-224">1 &  0 &  0 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="922ca-224">1 &  0 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="922ca-225">0 &  1 &  0 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="922ca-225">0 &  1 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="922ca-226">0 &  0 & -1 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="922ca-226">0 &  0 & -1 &  0 \\\\</span></span>
        <span data-ttu-id="922ca-227">0 &  0 &  0 & -1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="922ca-227">0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="922ca-228">Daha önce olduğu gibi, bu tür Matrislerin her türlü Unitary dönüştürmesi, $ \pm 1 eigenvalues ile etiketlenmiş iki yarı boşluğu da açıklar $ .</span><span class="sxs-lookup"><span data-stu-id="922ca-228">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="922ca-229">Örneğin, $ x \otimes x = h \otimes h (z \otimes z) h, \otimes $ $ z = HXH tarafından kullanılan kimlikten h $ .</span><span class="sxs-lookup"><span data-stu-id="922ca-229">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="922ca-230">Tek qubit çalışmasına benzer şekilde, tüm iki-qubit Pauli-ölçümleri $ \dagger \otimes \id $ $ 4 \times 4 $ Unitary $ u için $ u ^ (Z) u olarak yazılabilir. Aşağıdaki tablodaki dönüşümleri numaralandırıyoruz.</span><span class="sxs-lookup"><span data-stu-id="922ca-230">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$. We enumerate the transformations in the following table.</span></span>

> [!NOTE]
<span data-ttu-id="922ca-231">>Aşağıdaki tabloda, $ \operatorname { } $ matrisi > göstermek için takas kullanıyoruz$$</span><span class="sxs-lookup"><span data-stu-id="922ca-231">> In the table below, we use $\operatorname{SWAP}$ to indicate the matrix > $$</span></span>
<span data-ttu-id="922ca-232">> \begin{align}</span><span class="sxs-lookup"><span data-stu-id="922ca-232">> \begin{align}</span></span>
<span data-ttu-id="922ca-233">>     \operatorname{TAKAS et } &=</span><span class="sxs-lookup"><span data-stu-id="922ca-233">>     \operatorname{SWAP} & =</span></span>
<span data-ttu-id="922ca-234">>     \left( \begin { matris}</span><span class="sxs-lookup"><span data-stu-id="922ca-234">>     \left(\begin{matrix}</span></span>
<span data-ttu-id="922ca-235">>         1 & 0 & 0 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="922ca-235">>         1 & 0 & 0 & 0 \\\\</span></span>
<span data-ttu-id="922ca-236">>         0 & 0 & 1 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="922ca-236">>         0 & 0 & 1 & 0 \\\\</span></span>
<span data-ttu-id="922ca-237">>         0 & 1 & 0 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="922ca-237">>         0 & 1 & 0 & 0 \\\\</span></span>
<span data-ttu-id="922ca-238">>0 & 0 & 0 & 1 > \end { matris } \right ) >     \end{align}</span><span class="sxs-lookup"><span data-stu-id="922ca-238">>         0 & 0 & 0 & 1 >     \end{matrix}\right) > \end{align}</span></span>
<span data-ttu-id="922ca-239">> $$</span><span class="sxs-lookup"><span data-stu-id="922ca-239">> $$</span></span>
<span data-ttu-id="922ca-240">> iç işlemin benzetimini yapmak için kullanılır [`SWAP`](xref:Microsoft.Quantum.Intrinsic) .</span><span class="sxs-lookup"><span data-stu-id="922ca-240">> used to simulate the intrinsic operation [`SWAP`](xref:Microsoft.Quantum.Intrinsic).</span></span>

<span data-ttu-id="922ca-241">|Pauli ölçüm     | Unitary dönüşümü  |</span><span class="sxs-lookup"><span data-stu-id="922ca-241">|Pauli Measurement     |Unitary transformation  |</span></span>
|----------------------|------------------------|
<span data-ttu-id="922ca-242">|$ \otimes \boldone Z $ | $\boldone\otimes \boldone$|</span><span class="sxs-lookup"><span data-stu-id="922ca-242">| $Z\otimes \boldone$ | $\boldone\otimes \boldone$ |</span></span>
<span data-ttu-id="922ca-243">|$ \otimes \boldone X $ | $ \otimes \boldone H $|</span><span class="sxs-lookup"><span data-stu-id="922ca-243">| $X\otimes \boldone$ | $H\otimes \boldone$ |</span></span>
<span data-ttu-id="922ca-244">|$ \otimes \boldone Y $ | $ HS \dagger \otimes \boldone ^ $|</span><span class="sxs-lookup"><span data-stu-id="922ca-244">| $Y\otimes \boldone$ | $HS^\dagger\otimes \boldone$ |</span></span>
<span data-ttu-id="922ca-245">|$\boldone \otimes Z $ | $ \operatorname { takas } $|</span><span class="sxs-lookup"><span data-stu-id="922ca-245">| $\boldone \otimes Z$ | $\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="922ca-246">|$\boldone \otimes X $ | $ (H \otimes \boldone ) \operatorname { takas } $|</span><span class="sxs-lookup"><span data-stu-id="922ca-246">| $\boldone \otimes X$ | $(H\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="922ca-247">|$\boldone \otimes Y $ | $ (HS ^ \dagger \otimes \boldone ) \operatorname { takas } $|</span><span class="sxs-lookup"><span data-stu-id="922ca-247">| $\boldone \otimes Y$ | $(HS^\dagger\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="922ca-248">|$Z \otimes Z $ | $ \operatorname { cnot } \_ { 10 } $|</span><span class="sxs-lookup"><span data-stu-id="922ca-248">| $Z\otimes Z$ | $\operatorname{CNOT}\_{10}$ |</span></span>
<span data-ttu-id="922ca-249">|$X \otimes Z $ | $ \operatorname { cnot } \_ { 10 } (H \otimes \boldone ) $|</span><span class="sxs-lookup"><span data-stu-id="922ca-249">| $X\otimes Z$ | $\operatorname{CNOT}\_{10}(H\otimes \boldone)$ |</span></span>
<span data-ttu-id="922ca-250">|$Y \otimes Z $ | $ \operatorname { cnot } \_ { 10 } (HS ^ \dagger \otimes \boldone ) $|</span><span class="sxs-lookup"><span data-stu-id="922ca-250">| $Y\otimes Z$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$ |</span></span>
<span data-ttu-id="922ca-251">|$Z \otimes X $ | $ \operatorname { cnot } \_ { 10 } ( \boldone \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="922ca-251">| $Z\otimes X$ | $\operatorname{CNOT}\_{10}(\boldone\otimes H)$ |</span></span>
<span data-ttu-id="922ca-252">|$X \otimes X $ | $ \operatorname { cnot } \_ { 10 } (h \otimes h) $|</span><span class="sxs-lookup"><span data-stu-id="922ca-252">| $X\otimes X$ | $\operatorname{CNOT}\_{10}(H\otimes H)$ |</span></span>
<span data-ttu-id="922ca-253">|$Y \otimes X $ | $ \operatorname { cnot } \_ { 10 } (HS ^ \dagger \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="922ca-253">| $Y\otimes X$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$ |</span></span>
<span data-ttu-id="922ca-254">|$Z \otimes Y $ | $ \operatorname { cnot } \_ { 10 } ( \boldone \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="922ca-254">| $Z\otimes Y$ | $\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="922ca-255">|$X \otimes Y $ | $ \operatorname { cnot } \_ { 10 } (H \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="922ca-255">| $X\otimes Y$ | $\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="922ca-256">|$Y \otimes Y $ | $ \operatorname { cnot } \_ { 10 } (HS ^ \dagger \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="922ca-256">| $Y\otimes Y$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$ |</span></span>

<span data-ttu-id="922ca-257">Burada, [`CNOT`](xref:Microsoft.Quantum.Intrinsic.CNOT) işlem aşağıdaki nedenlerden dolayı görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="922ca-257">Here, the [`CNOT`](xref:Microsoft.Quantum.Intrinsic.CNOT) operation appears for the following reason.</span></span>
<span data-ttu-id="922ca-258">Matrisi içermeyen her Pauli ölçümü, $ \boldone $ $ \otimes Yukarıdaki düşünyana bir Unitary ile z z arasında eşittir $ .</span><span class="sxs-lookup"><span data-stu-id="922ca-258">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="922ca-259">Z z 'nin eigenvalues değeri $ \otimes $ yalnızca her bir hesaplama tabanlı vektörü oluşturan qubits 'e bağlıdır ve denetlenen işlemler bu eşliği hesaplamak ve ilk bit içinde saklamak için işlem yapar.</span><span class="sxs-lookup"><span data-stu-id="922ca-259">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="922ca-260">İlk bit ölçülene kadar, elde edilen yarı alanın kimliğini kurtararak Pauli işlecinin ölçülesiyle eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="922ca-260">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="922ca-261">Tek bir ek notta: ölçü $ z z 'nin, \otimes $ $ z \otimes \mathbb { 1 } $ ve sonrasında $ 1 z \mathbb { } \otimes $ ölçmesi ile aynı olduğunu varsaymaya rağmen bu varsayım yanlış olur.</span><span class="sxs-lookup"><span data-stu-id="922ca-261">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="922ca-262">Bunun nedeni, $ z \otimes z $ 'yi $ $ $ Bu operatörlerin + 1 veya-1 $ egeni olarak ölçmesini ölçmeye yönelik bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="922ca-262">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="922ca-263">$Z \otimes \mathbb { 1 } $ ve daha sonra $ \mathbb { 1 } \otimes z $ , hisse ve $ \otimes \mathbb { } $ sonra $ \mathbb { } \otimes $ 1 z bir yarı boşluk vektörü olan hisse Dört hesaplama tabanlı vektör olduğu için, her iki ölçüm de durum, durumu çeyrek boşluk olarak azaltır ve bu nedenle tek bir hesaplama tabanlı vektöre düşürür.</span><span class="sxs-lookup"><span data-stu-id="922ca-263">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="922ca-264">Kubitler arasındaki bağıntılar</span><span class="sxs-lookup"><span data-stu-id="922ca-264">Correlations between qubits</span></span>
<span data-ttu-id="922ca-265">X x veya z z gibi Pauli matrislerini ölçmeye yönelik başka bir $ Yöntem \otimes $ $ \otimes $ de, bu ölçümlerin iki qubit arasındaki bağıntılar içinde depolanan bilgilere bakmasına olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="922ca-265">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="922ca-266">$X ölçme \otimes \id $ , ilk qubit 'de yerel olarak saklanan bilgilere bakmanızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="922ca-266">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="922ca-267">Her iki ölçüm türü de hisse bilgi işlem ortamında eşit olmakla birlikte, önceki bir deyişle hisse bilgi işlem gücünü güçlendirin.</span><span class="sxs-lookup"><span data-stu-id="922ca-267">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="922ca-268">Bu, bilgi işlem ortamında, genellikle öğrenmek istediğiniz bilgilerin herhangi bir tek qubit içinde depolanmadığını, ancak aynı anda tüm qubits 'de yerel olarak depolanmadığını ve bu nedenle yalnızca bir eklem ölçümü (örn. $ z \otimes z) üzerinden arayarak $ Bu bilgilerin bildirim haline gelmesini gösterir.</span><span class="sxs-lookup"><span data-stu-id="922ca-268">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="922ca-269">Örneğin, hata düzeltilirken, korumamıza çalıştığımız durum hakkında hiçbir şey öğrenirken bir hata oluştuğunu öğrenmek istiyoruz.</span><span class="sxs-lookup"><span data-stu-id="922ca-269">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="922ca-270">[Bit çevirme kod örneği](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) , $ z z \otimes \otimes \id $ ve $ \id \otimes z \otimes z $ < gibi ölçümleri kullanarak bunu nasıl yapakullanabileceğinizi gösteren bir örnek gösterir. --TODO: bunu, bit-çevir kod örneği on-eklenmediyse olduğunda, Samples Browser bağlantısı olarak değiştirin.</span><span class="sxs-lookup"><span data-stu-id="922ca-270">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$. <!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded.</span></span> -->

<span data-ttu-id="922ca-271">X Y Z gibi rastgele Pauli işleçleri $ \otimes \otimes \otimes \boldone $ de ölçülebilir.</span><span class="sxs-lookup"><span data-stu-id="922ca-271">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="922ca-272">Pauli işleçlerinin tüm tencursor ürünlerinin her biri yalnızca iki eigenvalues $ \ pm 1 $ ve her ikisi de tüm vektör alanlarının yarı uzayını oluşturur.</span><span class="sxs-lookup"><span data-stu-id="922ca-272">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="922ca-273">Bu nedenle, yukarıda belirtilen gereksinimlere başvurırlar.</span><span class="sxs-lookup"><span data-stu-id="922ca-273">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="922ca-274">' De Q# , bu tür ölçümler, $ $ ölçü $ (-1) ^ j 'nin egenspace 'e bir sonuç veriyor ise j döndürür $ .</span><span class="sxs-lookup"><span data-stu-id="922ca-274">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="922ca-275">İçinde yerleşik bir özellik olarak Pauli ölçümleri olması Q# yararlı olur, çünkü bu tür işleçler, $ $ işlemi bir Z ve bir Tensor ürünü olarak ifade etmek için gereken diagonalizing U geçidini açıklayan, denetimli olmayan ve temel dönüşümlerde uzun zincirler gerektirir $ $ $ \id $ .</span><span class="sxs-lookup"><span data-stu-id="922ca-275">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$.</span></span>
<span data-ttu-id="922ca-276">Önceden tanımlanmış Bu ölçülerden birini yapmak istediğinizi belirleyebilmeksizin, bir hesaplama tabanlı ölçüm için gerekli bilgileri sağlamak üzere temelinizi nasıl dönüştürebileceğinizi merak etmeniz gerekmez.</span><span class="sxs-lookup"><span data-stu-id="922ca-276">By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="922ca-277">Q# sizin için gerekli olan tüm temel dönüştürmeleri otomatik olarak işler.</span><span class="sxs-lookup"><span data-stu-id="922ca-277">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="922ca-278">Daha fazla bilgi için bkz [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) . ve [`MeasurePaulis`](xref:Microsoft.Quantum.Measurement.MeasurePaulis) işlemleri.</span><span class="sxs-lookup"><span data-stu-id="922ca-278">For more information, see the [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) and [`MeasurePaulis`](xref:Microsoft.Quantum.Measurement.MeasurePaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="922ca-279">No-Cloning theorem</span><span class="sxs-lookup"><span data-stu-id="922ca-279">The No-Cloning Theorem</span></span>

<span data-ttu-id="922ca-280">Hisse bilgileri güçlüdür.</span><span class="sxs-lookup"><span data-stu-id="922ca-280">Quantum information is powerful.</span></span>
<span data-ttu-id="922ca-281">Faktör numaraları gibi harika şeyleri en iyi bilinen klasik algoritmalardan daha hızlı bir şekilde gerçekleştirebilmemizi veya düzgün bir şekilde benzetilmesini sağlayan bağıntılı elektron sistemlerinin verimli bir şekilde benzetimini yapmanızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="922ca-281">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="922ca-282">Ancak, hisse bilgi işlem gücüyle ilgili sınırlamalar vardır.</span><span class="sxs-lookup"><span data-stu-id="922ca-282">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="922ca-283">Bu tür bir sınırlama, *hiçbir kopyalama olmayan kopya* tarafından verilir.</span><span class="sxs-lookup"><span data-stu-id="922ca-283">One such limitation is given by the *No-Cloning Theorem* .</span></span>

<span data-ttu-id="922ca-284">No-Cloning theorem olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="922ca-284">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="922ca-285">Genel hisse durumlarının bir hisse bilgisayar tarafından kopyalanmasına izin vermez.</span><span class="sxs-lookup"><span data-stu-id="922ca-285">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="922ca-286">Bunların kanıtı, genel olarak basittir.</span><span class="sxs-lookup"><span data-stu-id="922ca-286">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="922ca-287">Bu konu başlığı altında, hiçbir ek yardımcı qubit, bizim tartışmamız için çok fazla teknik olmadığı için, kapsamımızda ek bir yardımcı qubitin olmaması durumunda (yardımcı qugeler, bir hesaplama sırasında karalama alanı için kullanılır ve içinde kolayca kullanılır ve yönetilir Q# , bkz. [ödünç alınan qubit](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span><span class="sxs-lookup"><span data-stu-id="922ca-287">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="922ca-288">Bu tür bir hisse bilgisayar için kopyalama işlemi bir Unitary matrisi tarafından açıklanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="922ca-288">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="922ca-289">Klonlamamız denendiğimiz hisse TI durumunu bozduğundan ölçüme izin vermeiyoruz.</span><span class="sxs-lookup"><span data-stu-id="922ca-289">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="922ca-290">Kopyalama işleminin benzetimini yapmak için Unitary matrisinin özelliği $$</span><span class="sxs-lookup"><span data-stu-id="922ca-290">To simulate the cloning operation, we want the unitary matrix used to have the property that $$</span></span>
  <span data-ttu-id="922ca-291">U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="922ca-291">U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
$$
<span data-ttu-id="922ca-292">herhangi bir durum için $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="922ca-292">for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="922ca-293">Matris çarpın doğrili özelliği daha sonra tüm ikinci hisse $ \ket { \phi } $</span><span class="sxs-lookup"><span data-stu-id="922ca-293">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

$$
\begin{align}
    <span data-ttu-id="922ca-294">U \left [ \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ] \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="922ca-294">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="922ca-295">&= \frac{ 1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="922ca-295">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="922ca-296">+ \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\</span><span class="sxs-lookup"><span data-stu-id="922ca-296">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\</span></span>
    <span data-ttu-id="922ca-297">&= \frac{ 1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="922ca-297">& = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="922ca-298">\right) \\\\</span><span class="sxs-lookup"><span data-stu-id="922ca-298">\right) \\\\</span></span>
    <span data-ttu-id="922ca-299">&\ne \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ).</span><span class="sxs-lookup"><span data-stu-id="922ca-299">& \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
\end{align}
$$

<span data-ttu-id="922ca-300">Bu, No-Cloning ' nin arkasındaki temel ıntutiye sahiptir: bilinmeyen bir hisse lık durumunu kopyalayan tüm cihazlar, kopyalayan durumların en az birinde hata almalıdır.</span><span class="sxs-lookup"><span data-stu-id="922ca-300">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="922ca-301">Cloner 'ın giriş durumunda herhangi bir şekilde hareket ederken, bu durum yardımcı qubits 'in eklenmesi ve ölçümü aracılığıyla ihlal edilebilir, ancak bu tür etkileşimler Ayrıca sistem hakkında ölçüm istatistikleri üzerinden bilgi sızıntısına ve bu gibi durumlarda tam kopyalamayı önler.</span><span class="sxs-lookup"><span data-stu-id="922ca-301">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="922ca-302">No-Cloning daha kapsamlı bir kanıtı için, [daha fazla bilgi için](xref:microsoft.quantum.more-information)bkz..</span><span class="sxs-lookup"><span data-stu-id="922ca-302">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="922ca-303">No-Cloning theorem, hisse anından çok büyük bir şekilde kopyalanabileceğinden, hisse durumlarından daha fazla bilgi edinmek için neredeyse yoğun bir özellik veriliyorsa, bu işlem, hisse hesaplamasından oluşan nitel 'yi anlamak için önemlidir.</span><span class="sxs-lookup"><span data-stu-id="922ca-303">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="922ca-304">Aslında, Heısenberg 'nin vaunbelirsizlik ilkesini ihlal edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="922ca-304">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="922ca-305">Alternatif olarak, bir karmaşık hisse dağılımla tek bir örnek almak ve yalnızca bir örnekten bu dağıtım hakkında bilgi edinmek istediğiniz her şeyi öğrenmek için en uygun bir Cloner kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="922ca-305">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="922ca-306">Bu, bir para ve gözbaşları çevirmiş ve sonra yanıt vermeye yönelik bir arkadaşla karşılaşmanız durumunda "Ah 'nin dağıtımı $ p = 0.512643 \ Lnoktalarla Bernoulli olmalıdır $ !"</span><span class="sxs-lookup"><span data-stu-id="922ca-306">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="922ca-307">Bu tür bir ifade, bir veya daha fazla bilgi olmadan dağıtımı kodlamak için gereken pek çok bilgi sağlamadığı için sensik olmayan bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="922ca-307">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="922ca-308">Benzer şekilde, önceki bilgiler olmadan, bu tür kodların her birini bilmeksizin bir şekilde hazırlayamazmız gibi, bir hisse bilgisini kusursuz bir şekilde klonlayamıyoruz $ $ .</span><span class="sxs-lookup"><span data-stu-id="922ca-308">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="922ca-309">Bilgiler hisse bilgi işlem ortamında ücretsizdir.</span><span class="sxs-lookup"><span data-stu-id="922ca-309">Information is not free in quantum computing.</span></span>
<span data-ttu-id="922ca-310">Ölçülen her bir qubit, tek bir bilgi verir ve No-Cloning, bu, sistem hakkında elde edilen bilgiler ve üzerinde çağrılan rahatsız edici temel zorunluluğunu getirir etrafında elde etmek için kullanılabilecek bir arka kapı olmadığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="922ca-310">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
