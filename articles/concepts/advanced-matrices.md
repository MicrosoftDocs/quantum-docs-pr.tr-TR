---
<span data-ttu-id="c3f23-101">Başlık: Gelişmiş matris kavramları açıklaması: hisse algoritmalarından bahseve benzetimini yapmak için kullanılan temel araçlar olan eigenvektörler, eigenvalues ve matris üsleri hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="c3f23-101">title: Advanced matrix concepts description: Learn about eigenvectors, eigenvalues, and matrix exponentials, the fundamental tools used to describe and simulate quantum algorithms.</span></span>
<span data-ttu-id="c3f23-102">Yazar: Histumwriter uid: Microsoft. hisse. Concepts. Matrix-Gelişmiş MS. Author: v-benköşeli MS. Date: 12/11/2017 MS. Topic: article No-loc:</span><span class="sxs-lookup"><span data-stu-id="c3f23-102">author: QuantumWriter uid: microsoft.quantum.concepts.matrix-advanced ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="c3f23-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="c3f23-103">"Q#"</span></span>
- <span data-ttu-id="c3f23-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="c3f23-104">"$$v"</span></span>
- <span data-ttu-id="c3f23-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="c3f23-105">"$$"</span></span>
- <span data-ttu-id="c3f23-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="c3f23-106">"$$"</span></span>
- <span data-ttu-id="c3f23-107">"$"</span><span class="sxs-lookup"><span data-stu-id="c3f23-107">"$"</span></span>
- <span data-ttu-id="c3f23-108">"$"</span><span class="sxs-lookup"><span data-stu-id="c3f23-108">"$"</span></span>
- <span data-ttu-id="c3f23-109">"$"</span><span class="sxs-lookup"><span data-stu-id="c3f23-109">"$"</span></span>
- <span data-ttu-id="c3f23-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="c3f23-110">"$$"</span></span>
- <span data-ttu-id="c3f23-111">"$$$"</span><span class="sxs-lookup"><span data-stu-id="c3f23-111">"$$$"</span></span>
- <span data-ttu-id="c3f23-112">"$$$"</span><span class="sxs-lookup"><span data-stu-id="c3f23-112">"$$$"</span></span>
- <span data-ttu-id="c3f23-113">"$$$"</span><span class="sxs-lookup"><span data-stu-id="c3f23-113">"$$$"</span></span>
- <span data-ttu-id="c3f23-114">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="c3f23-114">"\cdots"</span></span>
- <span data-ttu-id="c3f23-115">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="c3f23-115">"bmatrix"</span></span>
- <span data-ttu-id="c3f23-116">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="c3f23-116">"\ddots"</span></span>
- <span data-ttu-id="c3f23-117">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="c3f23-117">"\equiv"</span></span>
- <span data-ttu-id="c3f23-118">"\sum"</span><span class="sxs-lookup"><span data-stu-id="c3f23-118">"\sum"</span></span>
- <span data-ttu-id="c3f23-119">"\begin"</span><span class="sxs-lookup"><span data-stu-id="c3f23-119">"\begin"</span></span>
- <span data-ttu-id="c3f23-120">"\end"</span><span class="sxs-lookup"><span data-stu-id="c3f23-120">"\end"</span></span>
- <span data-ttu-id="c3f23-121">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="c3f23-121">"\sqrt"</span></span>
- <span data-ttu-id="c3f23-122">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="c3f23-122">"\otimes"</span></span>
- <span data-ttu-id="c3f23-123">"{"</span><span class="sxs-lookup"><span data-stu-id="c3f23-123">"{"</span></span>
- <span data-ttu-id="c3f23-124">"}"</span><span class="sxs-lookup"><span data-stu-id="c3f23-124">"}"</span></span>
- <span data-ttu-id="c3f23-125">"\text"</span><span class="sxs-lookup"><span data-stu-id="c3f23-125">"\text"</span></span>
- <span data-ttu-id="c3f23-126">"\phi"</span><span class="sxs-lookup"><span data-stu-id="c3f23-126">"\phi"</span></span>
- <span data-ttu-id="c3f23-127">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="c3f23-127">"\kappa"</span></span>
- <span data-ttu-id="c3f23-128">"\psi"</span><span class="sxs-lookup"><span data-stu-id="c3f23-128">"\psi"</span></span>
- <span data-ttu-id="c3f23-129">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="c3f23-129">"\alpha"</span></span>
- <span data-ttu-id="c3f23-130">"\beta"</span><span class="sxs-lookup"><span data-stu-id="c3f23-130">"\beta"</span></span>
- <span data-ttu-id="c3f23-131">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="c3f23-131">"\gamma"</span></span>
- <span data-ttu-id="c3f23-132">"\delta"</span><span class="sxs-lookup"><span data-stu-id="c3f23-132">"\delta"</span></span>
- <span data-ttu-id="c3f23-133">"\omega"</span><span class="sxs-lookup"><span data-stu-id="c3f23-133">"\omega"</span></span>
- <span data-ttu-id="c3f23-134">"\bra"</span><span class="sxs-lookup"><span data-stu-id="c3f23-134">"\bra"</span></span>
- <span data-ttu-id="c3f23-135">"\ket"</span><span class="sxs-lookup"><span data-stu-id="c3f23-135">"\ket"</span></span>
- <span data-ttu-id="c3f23-136">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="c3f23-136">"\boldone"</span></span>
- <span data-ttu-id="c3f23-137">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="c3f23-137">"\\\\"</span></span>
- <span data-ttu-id="c3f23-138">"\\"</span><span class="sxs-lookup"><span data-stu-id="c3f23-138">"\\"</span></span>
- <span data-ttu-id="c3f23-139">"="</span><span class="sxs-lookup"><span data-stu-id="c3f23-139">"="</span></span>
- <span data-ttu-id="c3f23-140">"\frac"</span><span class="sxs-lookup"><span data-stu-id="c3f23-140">"\frac"</span></span>
- <span data-ttu-id="c3f23-141">"\text"</span><span class="sxs-lookup"><span data-stu-id="c3f23-141">"\text"</span></span>
- <span data-ttu-id="c3f23-142">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="c3f23-142">"\mapsto"</span></span>
- <span data-ttu-id="c3f23-143">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="c3f23-143">"\dagger"</span></span>
- <span data-ttu-id="c3f23-144">"\to"</span><span class="sxs-lookup"><span data-stu-id="c3f23-144">"\to"</span></span>
- <span data-ttu-id="c3f23-145">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="c3f23-145">"\begin{cases}"</span></span>
- <span data-ttu-id="c3f23-146">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="c3f23-146">"\end{cases}"</span></span>
- <span data-ttu-id="c3f23-147">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="c3f23-147">"\operatorname"</span></span>
- <span data-ttu-id="c3f23-148">"\braket"</span><span class="sxs-lookup"><span data-stu-id="c3f23-148">"\braket"</span></span>
- <span data-ttu-id="c3f23-149">"\id"</span><span class="sxs-lookup"><span data-stu-id="c3f23-149">"\id"</span></span>
- <span data-ttu-id="c3f23-150">"\expect"</span><span class="sxs-lookup"><span data-stu-id="c3f23-150">"\expect"</span></span>
- <span data-ttu-id="c3f23-151">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="c3f23-151">"\defeq"</span></span>
- <span data-ttu-id="c3f23-152">"\variance"</span><span class="sxs-lookup"><span data-stu-id="c3f23-152">"\variance"</span></span>
- <span data-ttu-id="c3f23-153">"\dd"</span><span class="sxs-lookup"><span data-stu-id="c3f23-153">"\dd"</span></span>
- <span data-ttu-id="c3f23-154">"&"</span><span class="sxs-lookup"><span data-stu-id="c3f23-154">"&"</span></span>
- <span data-ttu-id="c3f23-155">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="c3f23-155">"\begin{align}"</span></span>
- <span data-ttu-id="c3f23-156">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="c3f23-156">"\end{align}"</span></span>
- <span data-ttu-id="c3f23-157">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="c3f23-157">"\Lambda"</span></span>
- <span data-ttu-id="c3f23-158">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="c3f23-158">"\lambda"</span></span>
- <span data-ttu-id="c3f23-159">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="c3f23-159">"\Omega"</span></span>
- <span data-ttu-id="c3f23-160">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="c3f23-160">"\mathrm"</span></span>
- <span data-ttu-id="c3f23-161">"\left"</span><span class="sxs-lookup"><span data-stu-id="c3f23-161">"\left"</span></span>
- <span data-ttu-id="c3f23-162">"\right"</span><span class="sxs-lookup"><span data-stu-id="c3f23-162">"\right"</span></span>
- <span data-ttu-id="c3f23-163">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="c3f23-163">"\qquad"</span></span>
- <span data-ttu-id="c3f23-164">"\times"</span><span class="sxs-lookup"><span data-stu-id="c3f23-164">"\times"</span></span>
- <span data-ttu-id="c3f23-165">"\big"</span><span class="sxs-lookup"><span data-stu-id="c3f23-165">"\big"</span></span>
- <span data-ttu-id="c3f23-166">"\langle"</span><span class="sxs-lookup"><span data-stu-id="c3f23-166">"\langle"</span></span>
- <span data-ttu-id="c3f23-167">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="c3f23-167">"\rangle"</span></span>
- <span data-ttu-id="c3f23-168">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="c3f23-168">"\bigg"</span></span>
- <span data-ttu-id="c3f23-169">"\Big"</span><span class="sxs-lookup"><span data-stu-id="c3f23-169">"\Big"</span></span>
- <span data-ttu-id="c3f23-170">"|"</span><span class="sxs-lookup"><span data-stu-id="c3f23-170">"|"</span></span>
- <span data-ttu-id="c3f23-171">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="c3f23-171">"\mathbb"</span></span>
- <span data-ttu-id="c3f23-172">"\vec"</span><span class="sxs-lookup"><span data-stu-id="c3f23-172">"\vec"</span></span>
- <span data-ttu-id="c3f23-173">"\in"</span><span class="sxs-lookup"><span data-stu-id="c3f23-173">"\in"</span></span>
- <span data-ttu-id="c3f23-174">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="c3f23-174">"\texttt"</span></span>
- <span data-ttu-id="c3f23-175">"\ne"</span><span class="sxs-lookup"><span data-stu-id="c3f23-175">"\ne"</span></span>
- <span data-ttu-id="c3f23-176">"<"</span><span class="sxs-lookup"><span data-stu-id="c3f23-176">"<"</span></span>
- <span data-ttu-id="c3f23-177">">"</span><span class="sxs-lookup"><span data-stu-id="c3f23-177">">"</span></span>
- <span data-ttu-id="c3f23-178">"\leq"</span><span class="sxs-lookup"><span data-stu-id="c3f23-178">"\leq"</span></span>
- <span data-ttu-id="c3f23-179">"\geq"</span><span class="sxs-lookup"><span data-stu-id="c3f23-179">"\geq"</span></span>
- <span data-ttu-id="c3f23-180">"~~"</span><span class="sxs-lookup"><span data-stu-id="c3f23-180">"~~"</span></span>
- <span data-ttu-id="c3f23-181">"~"</span><span class="sxs-lookup"><span data-stu-id="c3f23-181">"~"</span></span>
- <span data-ttu-id="c3f23-182">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="c3f23-182">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="c3f23-183">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="c3f23-183">"\end{bmatrix}"</span></span>
- <span data-ttu-id="c3f23-184">"\_"</span><span class="sxs-lookup"><span data-stu-id="c3f23-184">"\_"</span></span>

---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="c3f23-185">Gelişmiş matris kavramları</span><span class="sxs-lookup"><span data-stu-id="c3f23-185">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="c3f23-186">Artık, bir dizi algoritmalarınızı anlatmak ve uygulamak için ihtiyaç duyduğumuz temel bir araç kümesini oluşturan [*Eigenvalues, Eigenvektörler*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) ve [*üs ve üslerin*](https://en.wikipedia.org/wiki/Matrix_exponential) sağlığımızı genişlettik.</span><span class="sxs-lookup"><span data-stu-id="c3f23-186">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="c3f23-187">Eigenvalues ve Eigenvektör'ler</span><span class="sxs-lookup"><span data-stu-id="c3f23-187">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="c3f23-188">$ $ Bir kare matris ve $ v $ 'nin tüm sıfır olmayan vektör (yani, tüm girdileri 0 ' a eşit olan vektör) olmayan bir vektör $ $ olmasına izin verin.</span><span class="sxs-lookup"><span data-stu-id="c3f23-188">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="c3f23-189">C 'nin $ $ bir sayı ise, f CV ise M 'nin [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) olduğunu varsayalım  $ $ $ = $ $ $ .</span><span class="sxs-lookup"><span data-stu-id="c3f23-189">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="c3f23-190">$C $ 'nin eigenvector v öğesine karşılık gelen [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) olduğunu varsayalım $ $ .</span><span class="sxs-lookup"><span data-stu-id="c3f23-190">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="c3f23-191">Genel olarak bir matris $ $ , bir vektörü başka bir vektöre dönüştürebilir, ancak bir sayı ile Çarpılmakta olduğu sürece değişmeden bırakıldığı için bir eigenvector özeldir.</span><span class="sxs-lookup"><span data-stu-id="c3f23-191">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="c3f23-192">$V $ , eigenvalue c ile bir eigenvector ise $ $ , $ av $ 'nin $ $ aynı eigenvalue ile aynı zamanda bir eigenvector (sıfır olmayan a için) olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="c3f23-192">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="c3f23-193">Örneğin, kimlik matrisi için her vektör $ v, $ eigenvalue 1 içeren bir eigenvector değeridir $ $ .</span><span class="sxs-lookup"><span data-stu-id="c3f23-193">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="c3f23-194">Diğer bir örnek olarak, [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ $ köşegen üzerinde yalnızca sıfır olmayan girdilerin bulunduğu diyagonal bir matrisi göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="c3f23-194">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

$$
\begin{bmatrix}
<span data-ttu-id="c3f23-195">d_1 0 0 0 & & \\\\ & d_2 & 0 \\\\ 0 & 0 & D_3 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="c3f23-195">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="c3f23-196">Vektörler</span><span class="sxs-lookup"><span data-stu-id="c3f23-196">The vectors</span></span>

<span data-ttu-id="c3f23-197">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} , \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} ve \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="c3f23-197">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="c3f23-198">Bu matrisin eigenvalues  $ D_1 $ , $ d_2 $ ve $ D_3 $ sırasıyla.</span><span class="sxs-lookup"><span data-stu-id="c3f23-198">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="c3f23-199">$D_1 $ , $ d_2 $ ve $ D_3 $ birbirinden farklı sayısa, bu vektörler (ve bunların katları) d matrisinin yalnızca emoji vektörleridir $ $ . Genel olarak, çapraz matris için, eigenvalues ve eigenvektörleri okumak kolaydır.</span><span class="sxs-lookup"><span data-stu-id="c3f23-199">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$. In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="c3f23-200">Eigenvalues, köşegen üzerinde görünen tüm numaralardır ve ilgili eigenvektörlerini 1 ' e eşit olan birim vektörleridir $ $ ve kalan girişler 0 ' a eşittir $ $ .</span><span class="sxs-lookup"><span data-stu-id="c3f23-200">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="c3f23-201">Yukarıdaki örnekte, D 'nin egenvektörler 'in $ $ $ 3 $ boyutlu vektörler için temel olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="c3f23-201">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="c3f23-202">Bu, herhangi bir Vector öğesinin doğrusal bir birleşimi olarak yazılabilmesini sağlayan bir vektör kümesidir.</span><span class="sxs-lookup"><span data-stu-id="c3f23-202">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="c3f23-203">Daha açık, $ v_1 $ , $ v_2 $ ve $ v_3 $ bir vektör $ v $ $ = $ 'nin, v_1 $ $ , $ a_2 $ ve $ v_2 $ bazı sayılar için v A_1 a_3 + v_3 A_1 + a_2 a_3 olarak yazılabilmesini sağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c3f23-203">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="c3f23-204">Bir hermitian matrisinin (kendi kendine adjoint olarak da bilinir), kendi karmaşık eşleniği için eşit olan karmaşık bir kare matrisi olduğunu anımsayın, ancak Unitary matrisi ters, adjoint veya karmaşık eşleniği devrik değerine eşit olan karmaşık bir kare matrisi olur.</span><span class="sxs-lookup"><span data-stu-id="c3f23-204">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate transpose, while a unitary matrix is a complex square matrix whose inverse is equal to its adjoint or complex conjugate transpose.</span></span>
<span data-ttu-id="c3f23-205">Yalnızca hisse hesaplamasından kaynaklanan tek matrisler olan hermitian ve Unitary matrisleri için, şunları göz atmak gereken [*Spectral teoreminin*](https://en.wikipedia.org/wiki/Spectral_theorem)olarak bilinen genel bir sonuç vardır: herhangi bir hermitian veya Unitary 3 $ $ $ $ $ = \dagger $ $ $ . Ayrıca, D 'nin çapraz girdileri $ $ M 'nin eigenvalues değeri olacaktır $ $ .</span><span class="sxs-lookup"><span data-stu-id="c3f23-205">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$. Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="c3f23-206">Bir diyagonal matris D 'nin eigenvalues ve eigenvektörlerini nasıl hesapladığımimizi zaten $ biliyoruz $ . Bu işlemi kullanarak, $ v 'nin $ $ $ eigenvalue c, yani DV CV ile D 'nin bir egenvector olduğunu, $ $ yani $ = $ $ U ^ \dagger v 'nin $ $ $ eigenvalue c ile M 'nin eigenvector $ $ olduğunu biliyoruz.</span><span class="sxs-lookup"><span data-stu-id="c3f23-206">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$. Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="c3f23-207">Bunun nedeni</span><span class="sxs-lookup"><span data-stu-id="c3f23-207">This is because</span></span>

<span data-ttu-id="c3f23-208">$$M (U ^ \dagger v) = u ^ \dagger d U (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger ) v = u ^ d \dagger v = c u ^ \dagger v.$$</span><span class="sxs-lookup"><span data-stu-id="c3f23-208">$$M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="c3f23-209">Matris üs öğeleri</span><span class="sxs-lookup"><span data-stu-id="c3f23-209">Matrix Exponentials</span></span>
<span data-ttu-id="c3f23-210">Bir [*matris üstel*](https://en.wikipedia.org/wiki/Matrix_exponential) , üstel işlevine tam benzerleme vurguladı de tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="c3f23-210">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="c3f23-211">Bir matrisin a 'nın matris üsleri, $ $ şöyle ifade edilebilir</span><span class="sxs-lookup"><span data-stu-id="c3f23-211">The matrix exponential of a matrix $A$ can be expressed as</span></span>

$$
<span data-ttu-id="c3f23-212">e ^ a = \boldone + a + \frac { ^ 2 } { 2! } + \frac { Bir ^ 3 } { 3!}+\cdots</span><span class="sxs-lookup"><span data-stu-id="c3f23-212">e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots</span></span>
$$

<span data-ttu-id="c3f23-213">Bu önemli bir öneme sahip olduğundan, hisse ve saat evriminin $ { } $ B hermitian matrisi için e ^ IB biçiminde $ bir Unitary matrisi tarafından açıklandığından bu önemlidir $ .  Bu nedenle, matris üsleri gerçekleştirmek, hisse alma işlemlerinin temel bir parçasıdır ve Q# Bu da bu işlemleri tanımlamaya yönelik iç yordamlar sunar.</span><span class="sxs-lookup"><span data-stu-id="c3f23-213">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.  For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="c3f23-214">Klasik bir bilgisayarda matris üstel değerini hesaplamak için uygulamada birçok yol vardır ve genel olarak bu tür üslü bir üstel olarak yaklaşık olarak, perıl ile bir üstel olarak kullanılır.</span><span class="sxs-lookup"><span data-stu-id="c3f23-214">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="c3f23-215">Bkz [*. Cleve Moldova ve Charles Van kredisi. "Bir matrisin üstel boyutunu hesaplamak için nineon yedi yol." SıHAR incelemesi 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) , ilgili zorluk hakkında daha fazla bilgi için bkz..</span><span class="sxs-lookup"><span data-stu-id="c3f23-215">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="c3f23-216">Bir matrisin üstel değerini nasıl hesapladığınızı anlamanın en kolay yolu, bu matrisin eigenvalues ve eigenvektörlerinden oluşur.</span><span class="sxs-lookup"><span data-stu-id="c3f23-216">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="c3f23-217">Özellikle, yukarıda açıklanan Spectral, her hermitian veya Unitary matrisinin $ bir $ unitöğeli matris $ U $ ve $ $ $ = u ^ \dagger D u gibi $ diyagonal bir matris olduğunu söylüyor.  UnitID özellikleri nedeniyle, bir $ ^ 2 = u ^ \dagger d ^ 2 u $ ve benzer şekilde herhangi bir Power $ p $ $ a ^ p = u ^ \dagger d ^ p u olabilir $ .  Bunu, elde ettiğimiz işleç üstel işlecinin işleç tanımına değiştirir:</span><span class="sxs-lookup"><span data-stu-id="c3f23-217">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

$$
<span data-ttu-id="c3f23-218">e ^ A = U ^ \dagger \left ( \boldone + d + \frac { d ^ 2 } { 2! } + \cdots \right ) U = u ^ \dagger \begin{bmatrix} \exp (D_ { 11 } ) & 0 & \cdots & 0 \\\\ 0 & \ exp (D_ { 22 } ) & \cdots & 0 \\\\ \vnoktalara & \vnoktalara & \ddots & \vnoktalar \\\\ 0 & 0 & \cdots & \ exp (D_ { nn } ) \end{bmatrix} U.$$</span><span class="sxs-lookup"><span data-stu-id="c3f23-218">e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="c3f23-219">Diğer bir deyişle, matrisin eigenine dönüştürmeniz halinde matris $ $ üstel değeri, matrisin eigendeğerlerinin normal üstel değerini hesaplama ile eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="c3f23-219">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="c3f23-220">Hisse bilgi işlem içindeki çok sayıda işlem matris üslerinin gerçekleştirilmesini içerir. Bu arada, işleç üstel özelliğinin gerçekleştirilmesini kolaylaştırmak için bir matrisin eigenliğine dönüştürülmesi, bu kılavuzda sık görülen ve bu kılavuzun ilerleyen bölümlerinde ele alınan Trour – Suzuki-Style hisse</span><span class="sxs-lookup"><span data-stu-id="c3f23-220">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="c3f23-221">$B $ 'nin hem Unitary hem de hermitian, yani b $ = b ^ { -1 } = B ^, \dagger $ $ b ^ 2 = \boldone $ olması başka bir yararlı özelliktir.</span><span class="sxs-lookup"><span data-stu-id="c3f23-221">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="c3f23-222">Bu kuralı, matris üstel değerinin yukarıdaki genişlemesine uygulayarak ve $ \boldone $ ve $ B $ terimlerini birlikte gruplandırarak, tüm gerçek değer $ x için kimlik olduğunu görebilir $</span><span class="sxs-lookup"><span data-stu-id="c3f23-222">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

<span data-ttu-id="c3f23-223">$$e ^ { ibx } = \boldone \cos (x) + ib\sin (x)$$</span><span class="sxs-lookup"><span data-stu-id="c3f23-223">$$e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="c3f23-224">taşıyan.</span><span class="sxs-lookup"><span data-stu-id="c3f23-224">holds.</span></span> <span data-ttu-id="c3f23-225">Bu işlem özellikle yararlıdır çünkü b boyutu, b 'nin $ $ $ $ hem Unitary hem de hermitian olduğu durumlarda özel durum için, b boyutu üstel olarak büyük olsa bile,</span><span class="sxs-lookup"><span data-stu-id="c3f23-225">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
