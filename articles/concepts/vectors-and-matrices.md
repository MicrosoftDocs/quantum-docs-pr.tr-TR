---
<span data-ttu-id="945e8-101">Başlık: hisse bilgi işlem açıklamasında vektörler ve matrisler: vektörlerin ve matrislerle nasıl çalışacağınızı öğrenin.</span><span class="sxs-lookup"><span data-stu-id="945e8-101">title: Vectors and matrices in quantum computing description: Learn the basics of how to work with vectors and matrices.</span></span>
<span data-ttu-id="945e8-102">Yazar: Histumwriter uid: Microsoft. hisse. Concepts. vektörms. Author: v-benköşeli MS. Date: 12/11/2017 MS. Topic: article No-loc:</span><span class="sxs-lookup"><span data-stu-id="945e8-102">author: QuantumWriter uid: microsoft.quantum.concepts.vectors ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="945e8-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="945e8-103">"Q#"</span></span>
- <span data-ttu-id="945e8-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="945e8-104">"$$v"</span></span>
- <span data-ttu-id="945e8-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="945e8-105">"$$"</span></span>
- <span data-ttu-id="945e8-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="945e8-106">"$$"</span></span>
- <span data-ttu-id="945e8-107">"$"</span><span class="sxs-lookup"><span data-stu-id="945e8-107">"$"</span></span>
- <span data-ttu-id="945e8-108">"$"</span><span class="sxs-lookup"><span data-stu-id="945e8-108">"$"</span></span>
- <span data-ttu-id="945e8-109">"$"</span><span class="sxs-lookup"><span data-stu-id="945e8-109">"$"</span></span>
- <span data-ttu-id="945e8-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="945e8-110">"$$"</span></span>
- <span data-ttu-id="945e8-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="945e8-111">"\cdots"</span></span>
- <span data-ttu-id="945e8-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="945e8-112">"bmatrix"</span></span>
- <span data-ttu-id="945e8-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="945e8-113">"\ddots"</span></span>
- <span data-ttu-id="945e8-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="945e8-114">"\equiv"</span></span>
- <span data-ttu-id="945e8-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="945e8-115">"\sum"</span></span>
- <span data-ttu-id="945e8-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="945e8-116">"\begin"</span></span>
- <span data-ttu-id="945e8-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="945e8-117">"\end"</span></span>
- <span data-ttu-id="945e8-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="945e8-118">"\sqrt"</span></span>
- <span data-ttu-id="945e8-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="945e8-119">"\otimes"</span></span>
- <span data-ttu-id="945e8-120">"{"</span><span class="sxs-lookup"><span data-stu-id="945e8-120">"{"</span></span>
- <span data-ttu-id="945e8-121">"}"</span><span class="sxs-lookup"><span data-stu-id="945e8-121">"}"</span></span>
- <span data-ttu-id="945e8-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="945e8-122">"\text"</span></span>
- <span data-ttu-id="945e8-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="945e8-123">"\phi"</span></span>
- <span data-ttu-id="945e8-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="945e8-124">"\kappa"</span></span>
- <span data-ttu-id="945e8-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="945e8-125">"\psi"</span></span>
- <span data-ttu-id="945e8-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="945e8-126">"\alpha"</span></span>
- <span data-ttu-id="945e8-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="945e8-127">"\beta"</span></span>
- <span data-ttu-id="945e8-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="945e8-128">"\gamma"</span></span>
- <span data-ttu-id="945e8-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="945e8-129">"\delta"</span></span>
- <span data-ttu-id="945e8-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="945e8-130">"\omega"</span></span>
- <span data-ttu-id="945e8-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="945e8-131">"\bra"</span></span>
- <span data-ttu-id="945e8-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="945e8-132">"\ket"</span></span>
- <span data-ttu-id="945e8-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="945e8-133">"\boldone"</span></span>
- <span data-ttu-id="945e8-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="945e8-134">"\\\\"</span></span>
- <span data-ttu-id="945e8-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="945e8-135">"\\"</span></span>
- <span data-ttu-id="945e8-136">"="</span><span class="sxs-lookup"><span data-stu-id="945e8-136">"="</span></span>
- <span data-ttu-id="945e8-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="945e8-137">"\frac"</span></span>
- <span data-ttu-id="945e8-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="945e8-138">"\text"</span></span>
- <span data-ttu-id="945e8-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="945e8-139">"\mapsto"</span></span>
- <span data-ttu-id="945e8-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="945e8-140">"\dagger"</span></span>
- <span data-ttu-id="945e8-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="945e8-141">"\to"</span></span>
- <span data-ttu-id="945e8-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="945e8-142">"\begin{cases}"</span></span>
- <span data-ttu-id="945e8-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="945e8-143">"\end{cases}"</span></span>
- <span data-ttu-id="945e8-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="945e8-144">"\operatorname"</span></span>
- <span data-ttu-id="945e8-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="945e8-145">"\braket"</span></span>
- <span data-ttu-id="945e8-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="945e8-146">"\id"</span></span>
- <span data-ttu-id="945e8-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="945e8-147">"\expect"</span></span>
- <span data-ttu-id="945e8-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="945e8-148">"\defeq"</span></span>
- <span data-ttu-id="945e8-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="945e8-149">"\variance"</span></span>
- <span data-ttu-id="945e8-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="945e8-150">"\dd"</span></span>
- <span data-ttu-id="945e8-151">"&"</span><span class="sxs-lookup"><span data-stu-id="945e8-151">"&"</span></span>
- <span data-ttu-id="945e8-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="945e8-152">"\begin{align}"</span></span>
- <span data-ttu-id="945e8-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="945e8-153">"\end{align}"</span></span>
- <span data-ttu-id="945e8-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="945e8-154">"\Lambda"</span></span>
- <span data-ttu-id="945e8-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="945e8-155">"\lambda"</span></span>
- <span data-ttu-id="945e8-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="945e8-156">"\Omega"</span></span>
- <span data-ttu-id="945e8-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="945e8-157">"\mathrm"</span></span>
- <span data-ttu-id="945e8-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="945e8-158">"\left"</span></span>
- <span data-ttu-id="945e8-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="945e8-159">"\right"</span></span>
- <span data-ttu-id="945e8-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="945e8-160">"\qquad"</span></span>
- <span data-ttu-id="945e8-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="945e8-161">"\times"</span></span>
- <span data-ttu-id="945e8-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="945e8-162">"\big"</span></span>
- <span data-ttu-id="945e8-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="945e8-163">"\langle"</span></span>
- <span data-ttu-id="945e8-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="945e8-164">"\rangle"</span></span>
- <span data-ttu-id="945e8-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="945e8-165">"\bigg"</span></span>
- <span data-ttu-id="945e8-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="945e8-166">"\Big"</span></span>
- <span data-ttu-id="945e8-167">"|"</span><span class="sxs-lookup"><span data-stu-id="945e8-167">"|"</span></span>
- <span data-ttu-id="945e8-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="945e8-168">"\mathbb"</span></span>
- <span data-ttu-id="945e8-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="945e8-169">"\vec"</span></span>
- <span data-ttu-id="945e8-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="945e8-170">"\in"</span></span>
- <span data-ttu-id="945e8-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="945e8-171">"\texttt"</span></span>
- <span data-ttu-id="945e8-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="945e8-172">"\ne"</span></span>
- <span data-ttu-id="945e8-173">"<"</span><span class="sxs-lookup"><span data-stu-id="945e8-173">"<"</span></span>
- <span data-ttu-id="945e8-174">">"</span><span class="sxs-lookup"><span data-stu-id="945e8-174">">"</span></span>
- <span data-ttu-id="945e8-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="945e8-175">"\leq"</span></span>
- <span data-ttu-id="945e8-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="945e8-176">"\geq"</span></span>
- <span data-ttu-id="945e8-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="945e8-177">"~~"</span></span>
- <span data-ttu-id="945e8-178">"~"</span><span class="sxs-lookup"><span data-stu-id="945e8-178">"~"</span></span>
- <span data-ttu-id="945e8-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="945e8-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="945e8-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="945e8-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="945e8-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="945e8-181">"\_"</span></span>

---

# <a name="vectors-and-matrices"></a><span data-ttu-id="945e8-182">Vektörler ve matrisler</span><span class="sxs-lookup"><span data-stu-id="945e8-182">Vectors and Matrices</span></span>

<span data-ttu-id="945e8-183">Vektör ve matrislerle ilgili bazı benzerlik, hisse bilgi işlem anlamak için önemlidir.</span><span class="sxs-lookup"><span data-stu-id="945e8-183">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="945e8-184">Aşağıdaki kısa bir giriş sağlıyoruz ve ilgilendiğiniz okuyucular *, mg, G. (1993) gibi doğrusal algela 'da standart bir başvuruyu okumak için önerilir. Doğrusal algeköşeli giriş (Vol. 3). Kaynak listesi, MA: kaynak Lesley-Cambridge Press* veya [Doğrusal algedeniz](http://joshua.smcvt.edu/linearalgebra/)gibi bir çevrimiçi başvuru.</span><span class="sxs-lookup"><span data-stu-id="945e8-184">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="945e8-185">Boyutun (veya boyutunun) bir sütun vektörü (veya basitçe [*vektör*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ , $ bir $ $ $ $ sütun olarak düzenlenmiş n karmaşık sayıların (v_1, v_2, \lnoktalar, V_n) bir koleksiyonudur $ :</span><span class="sxs-lookup"><span data-stu-id="945e8-185">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="945e8-186">$$v =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="945e8-186">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="945e8-187">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-187">v_1\\\\</span></span>
<span data-ttu-id="945e8-188">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-188">v_2\\\\</span></span>
<span data-ttu-id="945e8-189">\ sanal noktalar\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-189">\vdots\\\\</span></span>
<span data-ttu-id="945e8-190">v_n \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="945e8-190">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="945e8-191">Vektör v 'nin norm $ $ $ \sqrt { \sum \_ i i & m | \_ | } $ ı %2 olarak tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="945e8-191">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="945e8-192">Bir Vector öğesinin normu 1 ise birim norm (ya da bir [*birim vektörü*](https://en.wikipedia.org/wiki/Unit_vector)olarak adlandırılır) olduğu söylenir $ $ .</span><span class="sxs-lookup"><span data-stu-id="945e8-192">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="945e8-193">[*Vektör v 'nin adeki*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ , $ $ v ^ olarak gösterilir \dagger $ ve $ \* $ karmaşık eşleniği gösterir,</span><span class="sxs-lookup"><span data-stu-id="945e8-193">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="945e8-194">$$\begin{bmatrix}v_1 \\\\ \vnoktalar \\\\ V_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ \* & \cdots & V_n ^ \*\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="945e8-194">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="945e8-195">İki vektörün birlikte çarpılabilmesinin en yaygın yolu, bir nokta ürünü olarak da bilinen [*iç üründür*](https://en.wikipedia.org/wiki/Inner_product_space).</span><span class="sxs-lookup"><span data-stu-id="945e8-195">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="945e8-196">İç ürün, bir vektörün başka bir vektör için projeksiyonu sağlar ve diğer daha basit vektörler toplamı olarak bir Vector öğesinin nasıl ifade alınacağını açıklamak açısından değerlidir.</span><span class="sxs-lookup"><span data-stu-id="945e8-196">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="945e8-197">$U ve v arasındaki iç $ ürün $ $ , belirtilen $ \left \langle u, v \right \rangle $ olarak tanımlanır</span><span class="sxs-lookup"><span data-stu-id="945e8-197">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

$$
<span data-ttu-id="945e8-198">\langleu, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n.</span><span class="sxs-lookup"><span data-stu-id="945e8-198">\langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="945e8-199">Bu gösterim Ayrıca bir vektör v 'nin norm $ $ $ \sqrt { \langle ' i v, v \rangle } $ olarak yazılmasına izin verir.</span><span class="sxs-lookup"><span data-stu-id="945e8-199">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="945e8-200">$ $ Girişleri c ile çarpıldığı yeni bir vektör oluşturmak için, bir vektörü c sayısıyla çarpıyoruz $ $ .</span><span class="sxs-lookup"><span data-stu-id="945e8-200">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="945e8-201">Ayrıca, $ $ $ $ girdileri $ u ve v girişlerinin toplamı olan yeni bir vektör oluşturmak için iki $ $ vektör u ve v $ de ekleyebiliriz.</span><span class="sxs-lookup"><span data-stu-id="945e8-201">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="945e8-202">Bu işlemler aşağıda gösterilmiştir:</span><span class="sxs-lookup"><span data-stu-id="945e8-202">These operations are depicted below:</span></span>

<span data-ttu-id="945e8-203">$$\mathrm{} ~ U ise=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="945e8-203">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="945e8-204">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-204">u_1\\\\</span></span>
<span data-ttu-id="945e8-205">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-205">u_2\\\\</span></span>
<span data-ttu-id="945e8-206">\ sanal noktalar\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-206">\vdots\\\\</span></span>
<span data-ttu-id="945e8-207">u_n \end{bmatrix} ~ \mathrm { ve}~</span><span class="sxs-lookup"><span data-stu-id="945e8-207">u_n \end{bmatrix}~\mathrm{and}~</span></span>
<span data-ttu-id="945e8-208">Yönetim =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="945e8-208">v =\begin{bmatrix}</span></span>
    <span data-ttu-id="945e8-209">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-209">v_1\\\\</span></span>
    <span data-ttu-id="945e8-210">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-210">v_2\\\\</span></span>
    <span data-ttu-id="945e8-211">\ sanal noktalar\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-211">\vdots\\\\</span></span>
    <span data-ttu-id="945e8-212">V_n \end{bmatrix} , ~ \mathrm { ardından}~</span><span class="sxs-lookup"><span data-stu-id="945e8-212">v_n \end{bmatrix},~\mathrm{then}~</span></span>
<span data-ttu-id="945e8-213">Au + BV =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="945e8-213">au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="945e8-214">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-214">au_1+bv_1\\\\</span></span>
<span data-ttu-id="945e8-215">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-215">au_2+bv_2\\\\</span></span>
<span data-ttu-id="945e8-216">\ sanal noktalar\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-216">\vdots\\\\</span></span>
<span data-ttu-id="945e8-217">au_n + bv_n \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="945e8-217">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="945e8-218">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) n boyutundaki bir $ matris \times $ , $ $ $ $ $ aşağıda gösterildiği gibi, k satırı ve n $ sütunları halinde düzenlenmiş bir MN karmaşık sayı koleksiyonudur:</span><span class="sxs-lookup"><span data-stu-id="945e8-218">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="945e8-219">$$M =</span><span class="sxs-lookup"><span data-stu-id="945e8-219">$$M =</span></span> 
\begin{bmatrix}
<span data-ttu-id="945e8-220">M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1n}\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-220">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
<span data-ttu-id="945e8-221">M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-221">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="945e8-222">M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { MN}\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-222">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\</span></span>
<span data-ttu-id="945e8-223">\end{bmatrix}.$$</span><span class="sxs-lookup"><span data-stu-id="945e8-223">\end{bmatrix}.$$</span></span>

<span data-ttu-id="945e8-224">Boyut n 'nin vektörünün $ $ yalnızca n 1 boyutlu bir matris olduğunu unutmayın $ \times $ .</span><span class="sxs-lookup"><span data-stu-id="945e8-224">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="945e8-225">Vektörlerde olduğu gibi, $ $ her girdinin c ile çarpıldığı yeni bir matrisi elde etmek için bir matrisi c sayısıyla çarpabiliriz $ $ ve girişleri iki matrisin ilgili girişlerinin toplamı olan yeni bir matris oluşturmak için aynı boyutta iki matris ekleyebiliriz.</span><span class="sxs-lookup"><span data-stu-id="945e8-225">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="945e8-226">Matris çarpma ve Tensor ürünleri</span><span class="sxs-lookup"><span data-stu-id="945e8-226">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="945e8-227">Ayrıca, $ $ $ \times $ $ $ $ \times $ $ $ $ \times Şu şekilde boyut m p $ boyutunda yeni bir matris almak için boyut m n ve n boyut n p 'nin iki matrisi de çarpmak için:</span><span class="sxs-lookup"><span data-stu-id="945e8-227">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

\begin{align}
&\begin{bmatrix}
    <span data-ttu-id="945e8-228">M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1n}\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-228">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
    <span data-ttu-id="945e8-229">M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-229">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
    \ddots\\\\
    <span data-ttu-id="945e8-230">M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { MN}</span><span class="sxs-lookup"><span data-stu-id="945e8-230">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
\end{bmatrix}
\begin{bmatrix}
<span data-ttu-id="945e8-231">N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ { 1p}\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-231">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\</span></span>
<span data-ttu-id="945e8-232">N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ { 2p}\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-232">N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="945e8-233">N_ { N1 } ~~ N_ { N2 } ~~ \cdots ~~ N_ { NP}</span><span class="sxs-lookup"><span data-stu-id="945e8-233">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
\end{bmatrix}=\begin{bmatrix}
<span data-ttu-id="945e8-234">P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1p}\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-234">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\</span></span>
<span data-ttu-id="945e8-235">P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2p}\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-235">P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="945e8-236">P_ { M1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { MP}</span><span class="sxs-lookup"><span data-stu-id="945e8-236">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
\end{bmatrix}
\end{align}

<span data-ttu-id="945e8-237">$P girişlerinin $ $ P_ { ık } = \sum _j M_ { IJ } N_ { JK } $ .</span><span class="sxs-lookup"><span data-stu-id="945e8-237">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="945e8-238">Örneğin, $ P_ 11 ' in { ilk } $ satırı N ilk sütununun iç ürünüdür $ $ $ $ . Vector öğesinin yalnızca bir matrisin özel durumu olduğundan, bu tanım matris-vektör çarpörüne genişletilir.</span><span class="sxs-lookup"><span data-stu-id="945e8-238">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$. Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="945e8-239">Dikkate aldığımız tüm matrisler, satır ve sütun sayısının eşit olduğu ve yalnızca 1 sütuna karşılık gelen vektörlerin bulunduğu kare matrisleri olacaktır $ $ .</span><span class="sxs-lookup"><span data-stu-id="945e8-239">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="945e8-240">Tek bir özel kare matrisi, [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix) $ \boldone $ Tüm köşegen öğelerini 1 ' e eşit $ $ ve kalan öğeleri 0 ' a eşit $ $ olan, belirtilen kimlik matrisi ' dir:</span><span class="sxs-lookup"><span data-stu-id="945e8-240">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

$$\boldone=\begin{bmatrix}
<span data-ttu-id="945e8-241">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-241">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="945e8-242">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-242">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="945e8-243">~~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-243">~~ \ddots\\\\</span></span>
<span data-ttu-id="945e8-244">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} .$$</span><span class="sxs-lookup"><span data-stu-id="945e8-244">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="945e8-245">Bir kare matris $ a için $ , $ $ AB B 'nin [*ters*](https://en.wikipedia.org/wiki/Invertible_matrix) bir matris olduğunu söyliyoruz $ = = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="945e8-245">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="945e8-246">Bir matrisin tersi de mevcut değildir, ancak mevcut olduğunda, $ bir ^ { -1 olduğunu gösterir } $ .</span><span class="sxs-lookup"><span data-stu-id="945e8-246">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="945e8-247">Her matris için $ $ , adjoint veya eşleniği devrik, $ $ $ $ $ { IJ } = m_ { Ji N_ } ^ \* $ bir matris N.</span><span class="sxs-lookup"><span data-stu-id="945e8-247">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="945e8-248">A 'nın adjoint $ , $ genellikle $ a ^ olarak gösterilir \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="945e8-248">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="945e8-249">$ $ [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) $ Uu ^ \dagger = u ^ \dagger u = \boldone $ veya equivalently, $ u ^ { -1 } = U ^ \dagger $ olan bir matris u olduğunu söyliyoruz.</span><span class="sxs-lookup"><span data-stu-id="945e8-249">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="945e8-250">Belki de Unitary matrislerinin en önemli özelliği, bir vektör 'nin norm düzeyini korumıdır.</span><span class="sxs-lookup"><span data-stu-id="945e8-250">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="945e8-251">Bu durum</span><span class="sxs-lookup"><span data-stu-id="945e8-251">This happens because</span></span> 

<span data-ttu-id="945e8-252">$$\langlev, v \rangle = v ^ \dagger v = v ^ \dagger u ^ { -1 } U v = v ^ \dagger u ^ \dagger u v = \langle u v, U v \rangle .$$</span><span class="sxs-lookup"><span data-stu-id="945e8-252">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="945e8-253">Bir matris $ d $ , [*hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) olarak kabul edilir $ = \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="945e8-253">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="945e8-254">Son olarak, m n ve n boyutudaki iki matrisin en büyük matris [*ürünü*](https://en.wikipedia.org/wiki/Tensor_product) (veya Kronecker ürünü), $ $ $ \times $ $ $ $ \times $ MP nq boyutunda daha büyük bir matris $ p = m \otimes $ $ \times $ ve h 'den elde edilir $ $ $ $ :</span><span class="sxs-lookup"><span data-stu-id="945e8-254">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

\begin{align}
    <span data-ttu-id="945e8-255">e \otimes N &=</span><span class="sxs-lookup"><span data-stu-id="945e8-255">M \otimes N &=</span></span>
    \begin{bmatrix}
        <span data-ttu-id="945e8-256">M_ { 11 } ~~ \cdots ~~ m_ { 1n }\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-256">M_{11} ~~ \cdots ~~ M_{1n} \\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="945e8-257">M_ { M1 } ~~ \cdots ~~ m_ { MN  }</span><span class="sxs-lookup"><span data-stu-id="945e8-257">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        <span data-ttu-id="945e8-258">N_ { 11 } ~~ \cdots ~~ N_ { 1 soru  }\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-258">N_{11}  ~~ \cdots ~~ N_{1q}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="945e8-259">{ } ~~ \cdots ~~ PQ N_ N_ P1 {}</span><span class="sxs-lookup"><span data-stu-id="945e8-259">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        <span data-ttu-id="945e8-260">M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="945e8-260">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="945e8-261">M_ { 1n } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ }  \end{bmatrix}\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-261">M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="945e8-262">M_ { M1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="945e8-262">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="945e8-263">M_ { MN } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ }  \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="945e8-263">M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="945e8-264">\end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="945e8-264">\end{bmatrix}.</span></span>
\end{align}

<span data-ttu-id="945e8-265">Bu, bazı örneklerde daha iyi gösterilmiştir:</span><span class="sxs-lookup"><span data-stu-id="945e8-265">This is better demonstrated with some examples:</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="945e8-266">a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=</span><span class="sxs-lookup"><span data-stu-id="945e8-266">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} =</span></span>
    \begin{bmatrix}
        <span data-ttu-id="945e8-267">\begin{bmatrix}c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="945e8-267">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="945e8-268">\\\\[1,5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="945e8-268">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    \end{bmatrix}
    <span data-ttu-id="945e8-269">=\begin{bmatrix}c \\\\ a d \\\\ a \\\\ b c \\\\ b d \\\\ s\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="945e8-269">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="945e8-270">ve</span><span class="sxs-lookup"><span data-stu-id="945e8-270">and</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="945e8-271">a \ b \\\\ c \ d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="945e8-271">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    \otimes 
    \begin{bmatrix}
        <span data-ttu-id="945e8-272">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="945e8-272">e\ f\\\\g\ h \end{bmatrix}</span></span>
     =
    \begin{bmatrix}
    <span data-ttu-id="945e8-273">a\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="945e8-273">a\begin{bmatrix}</span></span>
    <span data-ttu-id="945e8-274">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="945e8-274">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="945e8-275">kenarı\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="945e8-275">b\begin{bmatrix}</span></span>
    <span data-ttu-id="945e8-276">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="945e8-276">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="945e8-277">\\\\[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="945e8-277">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="945e8-278">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="945e8-278">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="945e8-279">TID\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="945e8-279">d\begin{bmatrix}</span></span>
    <span data-ttu-id="945e8-280">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="945e8-280">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \end{bmatrix}
    =
    \begin{bmatrix}
    <span data-ttu-id="945e8-281">AE \ AF \ olmalıdır \ BF \\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-281">ae\ af\ be\ bf \\\\</span></span>
    <span data-ttu-id="945e8-282">AG \ Ah \ bg \ BH \\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-282">ag\ ah\ bg\ bh \\\\</span></span>
    <span data-ttu-id="945e8-283">CE \ CF \ de \ df \\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-283">ce\ cf\ de\ df \\\\</span></span>
    <span data-ttu-id="945e8-284">CG \/\ DG \ DH \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="945e8-284">cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="945e8-285">Tencursor ürünlerini çevreleyen son yararlı bir notational kuralı, herhangi bir vektör $ v $ veya matris $ d $ , $ v ^ { \otimes n } $ veya $ k ^ n için de { \otimes } $ $ n $ katlama yinelenen bir Tensor ürünü için kısa bir seçenektir.</span><span class="sxs-lookup"><span data-stu-id="945e8-285">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="945e8-286">Örnek:</span><span class="sxs-lookup"><span data-stu-id="945e8-286">For example:</span></span>

\begin{align}
<span data-ttu-id="945e8-287">&\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1- \\\\ 1 \\\\ -1 \\\\ 1 \end{bmatrix} ,\\\\</span><span class="sxs-lookup"><span data-stu-id="945e8-287">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\</span></span>
  <span data-ttu-id="945e8-288">&\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} , \qquad \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 1 & 0 & 0 & 0 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="945e8-288">&\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}  0& 1 \\\\ 1& 0    \end{bmatrix},    \qquad\begin{bmatrix}   0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
\end{align}
