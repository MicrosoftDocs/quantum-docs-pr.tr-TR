---
<span data-ttu-id="db939-101">Başlık: Gelişmiş matris kavramları açıklaması: hisse algoritmalarından bahseve benzetimini yapmak için kullanılan temel araçlar olan eigenvektörler, eigenvalues ve matris üsleri hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="db939-101">title: Advanced matrix concepts description: Learn about eigenvectors, eigenvalues, and matrix exponentials, the fundamental tools used to describe and simulate quantum algorithms.</span></span>
<span data-ttu-id="db939-102">Yazar: Histumwriter uid: Microsoft. hisse. Concepts. Matrix-Gelişmiş MS. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 MS. Topic: article No-loc:</span><span class="sxs-lookup"><span data-stu-id="db939-102">author: QuantumWriter uid: microsoft.quantum.concepts.matrix-advanced ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="db939-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="db939-103">"$$"</span></span>
- <span data-ttu-id="db939-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="db939-104">"$$"</span></span>
- <span data-ttu-id="db939-105">"$"</span><span class="sxs-lookup"><span data-stu-id="db939-105">"$"</span></span>
- <span data-ttu-id="db939-106">"$"</span><span class="sxs-lookup"><span data-stu-id="db939-106">"$"</span></span>
- <span data-ttu-id="db939-107">"$"</span><span class="sxs-lookup"><span data-stu-id="db939-107">"$"</span></span>
- <span data-ttu-id="db939-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="db939-108">"$$"</span></span>
- <span data-ttu-id="db939-109">"$$$"</span><span class="sxs-lookup"><span data-stu-id="db939-109">"$$$"</span></span>
- <span data-ttu-id="db939-110">"$$$"</span><span class="sxs-lookup"><span data-stu-id="db939-110">"$$$"</span></span>
- <span data-ttu-id="db939-111">"$$$"</span><span class="sxs-lookup"><span data-stu-id="db939-111">"$$$"</span></span>
- <span data-ttu-id="db939-112">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="db939-112">"\cdots"</span></span>
- <span data-ttu-id="db939-113">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="db939-113">"bmatrix"</span></span>
- <span data-ttu-id="db939-114">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="db939-114">"\ddots"</span></span>
- <span data-ttu-id="db939-115">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="db939-115">"\equiv"</span></span>
- <span data-ttu-id="db939-116">"\sum"</span><span class="sxs-lookup"><span data-stu-id="db939-116">"\sum"</span></span>
- <span data-ttu-id="db939-117">"\begin"</span><span class="sxs-lookup"><span data-stu-id="db939-117">"\begin"</span></span>
- <span data-ttu-id="db939-118">"\end"</span><span class="sxs-lookup"><span data-stu-id="db939-118">"\end"</span></span>
- <span data-ttu-id="db939-119">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="db939-119">"\sqrt"</span></span>
- <span data-ttu-id="db939-120">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="db939-120">"\otimes"</span></span>
- <span data-ttu-id="db939-121">"{"</span><span class="sxs-lookup"><span data-stu-id="db939-121">"{"</span></span>
- <span data-ttu-id="db939-122">"}"</span><span class="sxs-lookup"><span data-stu-id="db939-122">"}"</span></span>
- <span data-ttu-id="db939-123">"\text"</span><span class="sxs-lookup"><span data-stu-id="db939-123">"\text"</span></span>
- <span data-ttu-id="db939-124">"\phi"</span><span class="sxs-lookup"><span data-stu-id="db939-124">"\phi"</span></span>
- <span data-ttu-id="db939-125">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="db939-125">"\kappa"</span></span>
- <span data-ttu-id="db939-126">"\psi"</span><span class="sxs-lookup"><span data-stu-id="db939-126">"\psi"</span></span>
- <span data-ttu-id="db939-127">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="db939-127">"\alpha"</span></span>
- <span data-ttu-id="db939-128">"\beta"</span><span class="sxs-lookup"><span data-stu-id="db939-128">"\beta"</span></span>
- <span data-ttu-id="db939-129">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="db939-129">"\gamma"</span></span>
- <span data-ttu-id="db939-130">"\delta"</span><span class="sxs-lookup"><span data-stu-id="db939-130">"\delta"</span></span>
- <span data-ttu-id="db939-131">"\omega"</span><span class="sxs-lookup"><span data-stu-id="db939-131">"\omega"</span></span>
- <span data-ttu-id="db939-132">"\bra"</span><span class="sxs-lookup"><span data-stu-id="db939-132">"\bra"</span></span>
- <span data-ttu-id="db939-133">"\ket"</span><span class="sxs-lookup"><span data-stu-id="db939-133">"\ket"</span></span>
- <span data-ttu-id="db939-134">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="db939-134">"\boldone"</span></span>
- <span data-ttu-id="db939-135">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="db939-135">"\\\\"</span></span>
- <span data-ttu-id="db939-136">"\\"</span><span class="sxs-lookup"><span data-stu-id="db939-136">"\\"</span></span>
- <span data-ttu-id="db939-137">"="</span><span class="sxs-lookup"><span data-stu-id="db939-137">"="</span></span>
- <span data-ttu-id="db939-138">"\frac"</span><span class="sxs-lookup"><span data-stu-id="db939-138">"\frac"</span></span>
- <span data-ttu-id="db939-139">"\text"</span><span class="sxs-lookup"><span data-stu-id="db939-139">"\text"</span></span>
- <span data-ttu-id="db939-140">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="db939-140">"\mapsto"</span></span>
- <span data-ttu-id="db939-141">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="db939-141">"\dagger"</span></span>
- <span data-ttu-id="db939-142">"\to"</span><span class="sxs-lookup"><span data-stu-id="db939-142">"\to"</span></span>
- <span data-ttu-id="db939-143">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="db939-143">"\begin{cases}"</span></span>
- <span data-ttu-id="db939-144">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="db939-144">"\end{cases}"</span></span>
- <span data-ttu-id="db939-145">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="db939-145">"\operatorname"</span></span>
- <span data-ttu-id="db939-146">"\braket"</span><span class="sxs-lookup"><span data-stu-id="db939-146">"\braket"</span></span>
- <span data-ttu-id="db939-147">"\id"</span><span class="sxs-lookup"><span data-stu-id="db939-147">"\id"</span></span>
- <span data-ttu-id="db939-148">"\expect"</span><span class="sxs-lookup"><span data-stu-id="db939-148">"\expect"</span></span>
- <span data-ttu-id="db939-149">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="db939-149">"\defeq"</span></span>
- <span data-ttu-id="db939-150">"\variance"</span><span class="sxs-lookup"><span data-stu-id="db939-150">"\variance"</span></span>
- <span data-ttu-id="db939-151">"\dd"</span><span class="sxs-lookup"><span data-stu-id="db939-151">"\dd"</span></span>
- <span data-ttu-id="db939-152">"&"</span><span class="sxs-lookup"><span data-stu-id="db939-152">"&"</span></span>
- <span data-ttu-id="db939-153">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="db939-153">"\begin{align}"</span></span>
- <span data-ttu-id="db939-154">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="db939-154">"\end{align}"</span></span>
- <span data-ttu-id="db939-155">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="db939-155">"\Lambda"</span></span>
- <span data-ttu-id="db939-156">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="db939-156">"\lambda"</span></span>
- <span data-ttu-id="db939-157">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="db939-157">"\Omega"</span></span>
- <span data-ttu-id="db939-158">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="db939-158">"\mathrm"</span></span>
- <span data-ttu-id="db939-159">"\left"</span><span class="sxs-lookup"><span data-stu-id="db939-159">"\left"</span></span>
- <span data-ttu-id="db939-160">"\right"</span><span class="sxs-lookup"><span data-stu-id="db939-160">"\right"</span></span>
- <span data-ttu-id="db939-161">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="db939-161">"\qquad"</span></span>
- <span data-ttu-id="db939-162">"\times"</span><span class="sxs-lookup"><span data-stu-id="db939-162">"\times"</span></span>
- <span data-ttu-id="db939-163">"\big"</span><span class="sxs-lookup"><span data-stu-id="db939-163">"\big"</span></span>
- <span data-ttu-id="db939-164">"\langle"</span><span class="sxs-lookup"><span data-stu-id="db939-164">"\langle"</span></span>
- <span data-ttu-id="db939-165">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="db939-165">"\rangle"</span></span>
- <span data-ttu-id="db939-166">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="db939-166">"\bigg"</span></span>
- <span data-ttu-id="db939-167">"\Big"</span><span class="sxs-lookup"><span data-stu-id="db939-167">"\Big"</span></span>
- <span data-ttu-id="db939-168">"|"</span><span class="sxs-lookup"><span data-stu-id="db939-168">"|"</span></span>
- <span data-ttu-id="db939-169">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="db939-169">"\mathbb"</span></span>
- <span data-ttu-id="db939-170">"\vec"</span><span class="sxs-lookup"><span data-stu-id="db939-170">"\vec"</span></span>
- <span data-ttu-id="db939-171">"\in"</span><span class="sxs-lookup"><span data-stu-id="db939-171">"\in"</span></span>
- <span data-ttu-id="db939-172">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="db939-172">"\texttt"</span></span>
- <span data-ttu-id="db939-173">"\ne"</span><span class="sxs-lookup"><span data-stu-id="db939-173">"\ne"</span></span>
- <span data-ttu-id="db939-174">"<"</span><span class="sxs-lookup"><span data-stu-id="db939-174">"<"</span></span>
- <span data-ttu-id="db939-175">">"</span><span class="sxs-lookup"><span data-stu-id="db939-175">">"</span></span>
- <span data-ttu-id="db939-176">"\leq"</span><span class="sxs-lookup"><span data-stu-id="db939-176">"\leq"</span></span>
- <span data-ttu-id="db939-177">"\geq"</span><span class="sxs-lookup"><span data-stu-id="db939-177">"\geq"</span></span>
- <span data-ttu-id="db939-178">"~~"</span><span class="sxs-lookup"><span data-stu-id="db939-178">"~~"</span></span>
- <span data-ttu-id="db939-179">"~"</span><span class="sxs-lookup"><span data-stu-id="db939-179">"~"</span></span>
- <span data-ttu-id="db939-180">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="db939-180">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="db939-181">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="db939-181">"\end{bmatrix}"</span></span>
- <span data-ttu-id="db939-182">"\_"</span><span class="sxs-lookup"><span data-stu-id="db939-182">"\_"</span></span>

---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="db939-183">Gelişmiş matris kavramları</span><span class="sxs-lookup"><span data-stu-id="db939-183">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="db939-184">Artık, bir dizi algoritmalarınızı anlatmak ve uygulamak için ihtiyaç duyduğumuz temel bir araç kümesini oluşturan [*Eigenvalues, Eigenvektörler*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) ve [*üs ve üslerin*](https://en.wikipedia.org/wiki/Matrix_exponential) sağlığımızı genişlettik.</span><span class="sxs-lookup"><span data-stu-id="db939-184">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="db939-185">Eigenvalues ve Eigenvektör'ler</span><span class="sxs-lookup"><span data-stu-id="db939-185">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="db939-186">$ $ Bir kare matris ve $ v $ 'nin tüm sıfır olmayan vektör (yani, tüm girdileri 0 ' a eşit olan vektör) olmayan bir vektör $ $ olmasına izin verin.</span><span class="sxs-lookup"><span data-stu-id="db939-186">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="db939-187">C 'nin $ $ bir sayı ise, f CV ise M 'nin [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) olduğunu varsayalım $ $ $ = $ $ $ .</span><span class="sxs-lookup"><span data-stu-id="db939-187">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="db939-188">$C $ 'nin eigenvector v öğesine karşılık gelen [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) olduğunu varsayalım $ $ .</span><span class="sxs-lookup"><span data-stu-id="db939-188">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="db939-189">Genel olarak bir matris $ $ , bir vektörü başka bir vektöre dönüştürebilir, ancak bir sayı ile Çarpılmakta olduğu sürece değişmeden bırakıldığı için bir eigenvector özeldir.</span><span class="sxs-lookup"><span data-stu-id="db939-189">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="db939-190">$V $ , eigenvalue c ile bir eigenvector ise $ $ , $ av $ 'nin $ $ aynı eigenvalue ile aynı zamanda bir eigenvector (sıfır olmayan a için) olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="db939-190">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="db939-191">Örneğin, kimlik matrisi için her vektör $ v, $ eigenvalue 1 içeren bir eigenvector değeridir $ $ .</span><span class="sxs-lookup"><span data-stu-id="db939-191">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="db939-192">Diğer bir örnek olarak, [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ $ köşegen üzerinde yalnızca sıfır olmayan girdilerin bulunduğu diyagonal bir matrisi göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="db939-192">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

$$
\begin{bmatrix}
<span data-ttu-id="db939-193">d_1 0 0 0 & & \\\\ & d_2 & 0 \\\\ 0 & 0 & D_3 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="db939-193">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="db939-194">Vektörler</span><span class="sxs-lookup"><span data-stu-id="db939-194">The vectors</span></span>

$$<span data-ttu-id="db939-195">\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} , \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} ve \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="db939-195">\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="db939-196">Bu matrisin eigenvalues $ D_1 $ , $ d_2 $ ve $ D_3 $ sırasıyla.</span><span class="sxs-lookup"><span data-stu-id="db939-196">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="db939-197">$D_1 $ , $ d_2 $ ve $ D_3 $ birbirinden farklı sayısa, bu vektörler (ve bunların katları) d matrisinin yalnızca emoji vektörleridir $ $ . Genel olarak, çapraz matris için, eigenvalues ve eigenvektörleri okumak kolaydır.</span><span class="sxs-lookup"><span data-stu-id="db939-197">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$. In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="db939-198">Eigenvalues, köşegen üzerinde görünen tüm numaralardır ve ilgili eigenvektörlerini 1 ' e eşit olan birim vektörleridir $ $ ve kalan girişler 0 ' a eşittir $ $ .</span><span class="sxs-lookup"><span data-stu-id="db939-198">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="db939-199">Yukarıdaki örnekte, D 'nin egenvektörler 'in $ $ $ 3 $ boyutlu vektörler için temel olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="db939-199">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="db939-200">Bu, herhangi bir Vector öğesinin doğrusal bir birleşimi olarak yazılabilmesini sağlayan bir vektör kümesidir.</span><span class="sxs-lookup"><span data-stu-id="db939-200">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="db939-201">Daha açık, $ v_1 $ , $ v_2 $ ve $ v_3 $ bir vektör $ v $ $ = $ 'nin, v_1 $ $ , $ a_2 $ ve $ v_2 $ bazı sayılar için v A_1 a_3 + v_3 A_1 + a_2 a_3 olarak yazılabilmesini sağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="db939-201">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="db939-202">Bir hermitian matrisinin (kendi kendine adjoint olarak da bilinir), kendi karmaşık eşleniği için eşit olan karmaşık bir kare matrisi olduğunu anımsayın, ancak Unitary matrisi ters, adjoint veya karmaşık eşleniği devrik değerine eşit olan karmaşık bir kare matrisi olur.</span><span class="sxs-lookup"><span data-stu-id="db939-202">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate transpose, while a unitary matrix is a complex square matrix whose inverse is equal to its adjoint or complex conjugate transpose.</span></span>
<span data-ttu-id="db939-203">Yalnızca hisse hesaplamasından kaynaklanan tek matrisler olan hermitian ve Unitary matrisleri için, şunları göz atmak gereken [*Spectral teoreminin*](https://en.wikipedia.org/wiki/Spectral_theorem)olarak bilinen genel bir sonuç vardır: herhangi bir hermitian veya Unitary 3 $ $ $ $ $ = \dagger $ $ $ . Ayrıca, D 'nin çapraz girdileri $ $ M 'nin eigenvalues değeri olacaktır $ $ .</span><span class="sxs-lookup"><span data-stu-id="db939-203">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$. Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="db939-204">Bir diyagonal matris D 'nin eigenvalues ve eigenvektörlerini nasıl hesapladığımimizi zaten $ biliyoruz $ . Bu işlemi kullanarak, $ v 'nin $ $ $ eigenvalue c, yani DV CV ile D 'nin bir egenvector olduğunu, $ $ yani $ = $ $ U ^ \dagger v 'nin $ $ $ eigenvalue c ile M 'nin eigenvector $ $ olduğunu biliyoruz.</span><span class="sxs-lookup"><span data-stu-id="db939-204">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$. Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="db939-205">Bunun nedeni</span><span class="sxs-lookup"><span data-stu-id="db939-205">This is because</span></span>

$$<span data-ttu-id="db939-206">M (U ^ \dagger v) = u ^ \dagger d U (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger ) v = u ^ d \dagger v = c u ^ \dagger v.$$</span><span class="sxs-lookup"><span data-stu-id="db939-206">M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="db939-207">Matris üs öğeleri</span><span class="sxs-lookup"><span data-stu-id="db939-207">Matrix Exponentials</span></span>
<span data-ttu-id="db939-208">Bir [*matris üstel*](https://en.wikipedia.org/wiki/Matrix_exponential) , üstel işlevine tam benzerleme vurguladı de tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="db939-208">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="db939-209">Bir matrisin a 'nın matris üsleri, $ $ şöyle ifade edilebilir</span><span class="sxs-lookup"><span data-stu-id="db939-209">The matrix exponential of a matrix $A$ can be expressed as</span></span>

$$
<span data-ttu-id="db939-210">e ^ a = \boldone + a + \frac { ^ 2 } { 2! } + \frac { Bir ^ 3 } { 3!}+\cdots</span><span class="sxs-lookup"><span data-stu-id="db939-210">e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots</span></span>
$$

<span data-ttu-id="db939-211">Bu önemli bir öneme sahip olduğundan, hisse ve saat evriminin $ { } $ B hermitian matrisi için e ^ IB biçiminde $ bir Unitary matrisi tarafından açıklandığından bu önemlidir $ .  Bu nedenle, matris üsleri gerçekleştirmek, hisse alma işlemlerinin temel bir parçasıdır ve bu da bu işlemleri tanımlamak için soru-cevap yordamları sunar.</span><span class="sxs-lookup"><span data-stu-id="db939-211">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.  For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="db939-212">Klasik bir bilgisayarda matris üstel değerini hesaplamak için uygulamada birçok yol vardır ve genel olarak bu tür üslü bir üstel olarak yaklaşık olarak, perıl ile bir üstel olarak kullanılır.</span><span class="sxs-lookup"><span data-stu-id="db939-212">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="db939-213">Bkz [*. Cleve Moldova ve Charles Van kredisi. "Bir matrisin üstel boyutunu hesaplamak için nineon yedi yol." SıHAR incelemesi 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) , ilgili zorluk hakkında daha fazla bilgi için bkz..</span><span class="sxs-lookup"><span data-stu-id="db939-213">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="db939-214">Bir matrisin üstel değerini nasıl hesapladığınızı anlamanın en kolay yolu, bu matrisin eigenvalues ve eigenvektörlerinden oluşur.</span><span class="sxs-lookup"><span data-stu-id="db939-214">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="db939-215">Özellikle, yukarıda açıklanan Spectral, her hermitian veya Unitary matrisinin $ bir $ unitöğeli matris $ U $ ve $ $ $ = u ^ \dagger D u gibi $ diyagonal bir matris olduğunu söylüyor.  UnitID özellikleri nedeniyle, bir $ ^ 2 = u ^ \dagger d ^ 2 u $ ve benzer şekilde herhangi bir Power $ p $ $ a ^ p = u ^ \dagger d ^ p u olabilir $ .  Bunu, elde ettiğimiz işleç üstel işlecinin işleç tanımına değiştirir:</span><span class="sxs-lookup"><span data-stu-id="db939-215">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

$$
<span data-ttu-id="db939-216">e ^ A = U ^ \dagger \left ( \boldone + d + \frac { d ^ 2 } { 2! } + \cdots \right ) U = u ^ \dagger \begin{bmatrix} \exp (D_ { 11 } ) & 0 & \cdots & 0 \\\\ 0 & \ exp (D_ { 22 } ) & \cdots & 0 \\\\ \vnoktalara & \vnoktalara & \ddots & \vnoktalar \\\\ 0 & 0 & \cdots & \ exp (D_ { nn } ) \end{bmatrix} U.$$</span><span class="sxs-lookup"><span data-stu-id="db939-216">e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="db939-217">Diğer bir deyişle, matrisin eigenine dönüştürmeniz halinde matris $ $ üstel değeri, matrisin eigendeğerlerinin normal üstel değerini hesaplama ile eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="db939-217">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="db939-218">Hisse bilgi işlem içindeki çok sayıda işlem matris üslerinin gerçekleştirilmesini içerir. Bu arada, işleç üstel özelliğinin gerçekleştirilmesini kolaylaştırmak için bir matrisin eigenliğine dönüştürülmesi, bu kılavuzda sık görülen ve bu kılavuzun ilerleyen bölümlerinde ele alınan Trour – Suzuki-Style hisse</span><span class="sxs-lookup"><span data-stu-id="db939-218">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="db939-219">$B $ 'nin hem Unitary hem de hermitian, yani b $ = b ^ { -1 } = B ^, \dagger $ $ b ^ 2 = \boldone $ olması başka bir yararlı özelliktir.</span><span class="sxs-lookup"><span data-stu-id="db939-219">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="db939-220">Bu kuralı, matris üstel değerinin yukarıdaki genişlemesine uygulayarak ve $ \boldone $ ve $ B $ terimlerini birlikte gruplandırarak, tüm gerçek değer $ x için kimlik olduğunu görebilir $</span><span class="sxs-lookup"><span data-stu-id="db939-220">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

$$<span data-ttu-id="db939-221">e ^ { ibx } = \boldone \cos (x) + ib\sin (x)$$</span><span class="sxs-lookup"><span data-stu-id="db939-221">e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="db939-222">taşıyan.</span><span class="sxs-lookup"><span data-stu-id="db939-222">holds.</span></span> <span data-ttu-id="db939-223">Bu işlem özellikle yararlıdır çünkü b boyutu, b 'nin $ $ $ $ hem Unitary hem de hermitian olduğu durumlarda özel durum için, b boyutu üstel olarak büyük olsa bile,</span><span class="sxs-lookup"><span data-stu-id="db939-223">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
