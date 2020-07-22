---
<span data-ttu-id="14e58-101">Başlık: hisse Oracles açıklaması: ile nasıl çalışacağınızı ve başka bir algoritmaya girdi olarak kullanılan hisse Oracles, kara Box işlemlerini nasıl tanımlayacağınızı öğrenin.</span><span class="sxs-lookup"><span data-stu-id="14e58-101">title: Quantum oracles description: Learn how to work with and define quantum oracles, black box operations that are used as input to another algorithm.</span></span>
<span data-ttu-id="14e58-102">Yazar: cgranade uid: Microsoft. hisse. Concepts. Oracles MS. Author: Christopher.Granade@microsoft.com MS. Date: 07/11/2018 MS. Topic: article No-loc:</span><span class="sxs-lookup"><span data-stu-id="14e58-102">author: cgranade uid: microsoft.quantum.concepts.oracles ms.author: Christopher.Granade@microsoft.com ms.date: 07/11/2018 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="14e58-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="14e58-103">"$$"</span></span>
- <span data-ttu-id="14e58-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="14e58-104">"$$"</span></span>
- <span data-ttu-id="14e58-105">"$"</span><span class="sxs-lookup"><span data-stu-id="14e58-105">"$"</span></span>
- <span data-ttu-id="14e58-106">"$"</span><span class="sxs-lookup"><span data-stu-id="14e58-106">"$"</span></span>
- <span data-ttu-id="14e58-107">"$"</span><span class="sxs-lookup"><span data-stu-id="14e58-107">"$"</span></span>
- <span data-ttu-id="14e58-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="14e58-108">"$$"</span></span>
- <span data-ttu-id="14e58-109">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="14e58-109">"\cdots"</span></span>
- <span data-ttu-id="14e58-110">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="14e58-110">"bmatrix"</span></span>
- <span data-ttu-id="14e58-111">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="14e58-111">"\ddots"</span></span>
- <span data-ttu-id="14e58-112">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="14e58-112">"\equiv"</span></span>
- <span data-ttu-id="14e58-113">"\sum"</span><span class="sxs-lookup"><span data-stu-id="14e58-113">"\sum"</span></span>
- <span data-ttu-id="14e58-114">"\begin"</span><span class="sxs-lookup"><span data-stu-id="14e58-114">"\begin"</span></span>
- <span data-ttu-id="14e58-115">"\end"</span><span class="sxs-lookup"><span data-stu-id="14e58-115">"\end"</span></span>
- <span data-ttu-id="14e58-116">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="14e58-116">"\sqrt"</span></span>
- <span data-ttu-id="14e58-117">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="14e58-117">"\otimes"</span></span>
- <span data-ttu-id="14e58-118">"{"</span><span class="sxs-lookup"><span data-stu-id="14e58-118">"{"</span></span>
- <span data-ttu-id="14e58-119">"}"</span><span class="sxs-lookup"><span data-stu-id="14e58-119">"}"</span></span>
- <span data-ttu-id="14e58-120">"\text"</span><span class="sxs-lookup"><span data-stu-id="14e58-120">"\text"</span></span>
- <span data-ttu-id="14e58-121">"\phi"</span><span class="sxs-lookup"><span data-stu-id="14e58-121">"\phi"</span></span>
- <span data-ttu-id="14e58-122">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="14e58-122">"\kappa"</span></span>
- <span data-ttu-id="14e58-123">"\psi"</span><span class="sxs-lookup"><span data-stu-id="14e58-123">"\psi"</span></span>
- <span data-ttu-id="14e58-124">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="14e58-124">"\alpha"</span></span>
- <span data-ttu-id="14e58-125">"\beta"</span><span class="sxs-lookup"><span data-stu-id="14e58-125">"\beta"</span></span>
- <span data-ttu-id="14e58-126">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="14e58-126">"\gamma"</span></span>
- <span data-ttu-id="14e58-127">"\delta"</span><span class="sxs-lookup"><span data-stu-id="14e58-127">"\delta"</span></span>
- <span data-ttu-id="14e58-128">"\omega"</span><span class="sxs-lookup"><span data-stu-id="14e58-128">"\omega"</span></span>
- <span data-ttu-id="14e58-129">"\bra"</span><span class="sxs-lookup"><span data-stu-id="14e58-129">"\bra"</span></span>
- <span data-ttu-id="14e58-130">"\ket"</span><span class="sxs-lookup"><span data-stu-id="14e58-130">"\ket"</span></span>
- <span data-ttu-id="14e58-131">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="14e58-131">"\boldone"</span></span>
- <span data-ttu-id="14e58-132">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="14e58-132">"\\\\"</span></span>
- <span data-ttu-id="14e58-133">"\\"</span><span class="sxs-lookup"><span data-stu-id="14e58-133">"\\"</span></span>
- <span data-ttu-id="14e58-134">"="</span><span class="sxs-lookup"><span data-stu-id="14e58-134">"="</span></span>
- <span data-ttu-id="14e58-135">"\frac"</span><span class="sxs-lookup"><span data-stu-id="14e58-135">"\frac"</span></span>
- <span data-ttu-id="14e58-136">"\text"</span><span class="sxs-lookup"><span data-stu-id="14e58-136">"\text"</span></span>
- <span data-ttu-id="14e58-137">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="14e58-137">"\mapsto"</span></span>
- <span data-ttu-id="14e58-138">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="14e58-138">"\dagger"</span></span>
- <span data-ttu-id="14e58-139">"\to"</span><span class="sxs-lookup"><span data-stu-id="14e58-139">"\to"</span></span>
- <span data-ttu-id="14e58-140">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="14e58-140">"\begin{cases}"</span></span>
- <span data-ttu-id="14e58-141">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="14e58-141">"\end{cases}"</span></span>
- <span data-ttu-id="14e58-142">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="14e58-142">"\operatorname"</span></span>
- <span data-ttu-id="14e58-143">"\braket"</span><span class="sxs-lookup"><span data-stu-id="14e58-143">"\braket"</span></span>
- <span data-ttu-id="14e58-144">"\id"</span><span class="sxs-lookup"><span data-stu-id="14e58-144">"\id"</span></span>
- <span data-ttu-id="14e58-145">"\expect"</span><span class="sxs-lookup"><span data-stu-id="14e58-145">"\expect"</span></span>
- <span data-ttu-id="14e58-146">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="14e58-146">"\defeq"</span></span>
- <span data-ttu-id="14e58-147">"\variance"</span><span class="sxs-lookup"><span data-stu-id="14e58-147">"\variance"</span></span>
- <span data-ttu-id="14e58-148">"\dd"</span><span class="sxs-lookup"><span data-stu-id="14e58-148">"\dd"</span></span>
- <span data-ttu-id="14e58-149">"&"</span><span class="sxs-lookup"><span data-stu-id="14e58-149">"&"</span></span>
- <span data-ttu-id="14e58-150">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="14e58-150">"\begin{align}"</span></span>
- <span data-ttu-id="14e58-151">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="14e58-151">"\end{align}"</span></span>
- <span data-ttu-id="14e58-152">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="14e58-152">"\Lambda"</span></span>
- <span data-ttu-id="14e58-153">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="14e58-153">"\lambda"</span></span>
- <span data-ttu-id="14e58-154">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="14e58-154">"\Omega"</span></span>
- <span data-ttu-id="14e58-155">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="14e58-155">"\mathrm"</span></span>
- <span data-ttu-id="14e58-156">"\left"</span><span class="sxs-lookup"><span data-stu-id="14e58-156">"\left"</span></span>
- <span data-ttu-id="14e58-157">"\right"</span><span class="sxs-lookup"><span data-stu-id="14e58-157">"\right"</span></span>
- <span data-ttu-id="14e58-158">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="14e58-158">"\qquad"</span></span>
- <span data-ttu-id="14e58-159">"\times"</span><span class="sxs-lookup"><span data-stu-id="14e58-159">"\times"</span></span>
- <span data-ttu-id="14e58-160">"\big"</span><span class="sxs-lookup"><span data-stu-id="14e58-160">"\big"</span></span>
- <span data-ttu-id="14e58-161">"\langle"</span><span class="sxs-lookup"><span data-stu-id="14e58-161">"\langle"</span></span>
- <span data-ttu-id="14e58-162">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="14e58-162">"\rangle"</span></span>
- <span data-ttu-id="14e58-163">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="14e58-163">"\bigg"</span></span>
- <span data-ttu-id="14e58-164">"\Big"</span><span class="sxs-lookup"><span data-stu-id="14e58-164">"\Big"</span></span>
- <span data-ttu-id="14e58-165">"|"</span><span class="sxs-lookup"><span data-stu-id="14e58-165">"|"</span></span>
- <span data-ttu-id="14e58-166">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="14e58-166">"\mathbb"</span></span>
- <span data-ttu-id="14e58-167">"\vec"</span><span class="sxs-lookup"><span data-stu-id="14e58-167">"\vec"</span></span>
- <span data-ttu-id="14e58-168">"\in"</span><span class="sxs-lookup"><span data-stu-id="14e58-168">"\in"</span></span>
- <span data-ttu-id="14e58-169">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="14e58-169">"\texttt"</span></span>
- <span data-ttu-id="14e58-170">"\ne"</span><span class="sxs-lookup"><span data-stu-id="14e58-170">"\ne"</span></span>
- <span data-ttu-id="14e58-171">"<"</span><span class="sxs-lookup"><span data-stu-id="14e58-171">"<"</span></span>
- <span data-ttu-id="14e58-172">">"</span><span class="sxs-lookup"><span data-stu-id="14e58-172">">"</span></span>
- <span data-ttu-id="14e58-173">"\leq"</span><span class="sxs-lookup"><span data-stu-id="14e58-173">"\leq"</span></span>
- <span data-ttu-id="14e58-174">"\geq"</span><span class="sxs-lookup"><span data-stu-id="14e58-174">"\geq"</span></span>
- <span data-ttu-id="14e58-175">"~~"</span><span class="sxs-lookup"><span data-stu-id="14e58-175">"~~"</span></span>
- <span data-ttu-id="14e58-176">"~"</span><span class="sxs-lookup"><span data-stu-id="14e58-176">"~"</span></span>
- <span data-ttu-id="14e58-177">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="14e58-177">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="14e58-178">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="14e58-178">"\end{bmatrix}"</span></span>
- <span data-ttu-id="14e58-179">"\_"</span><span class="sxs-lookup"><span data-stu-id="14e58-179">"\_"</span></span>

---
# <a name="quantum-oracles"></a><span data-ttu-id="14e58-180">Hisse Oracles</span><span class="sxs-lookup"><span data-stu-id="14e58-180">Quantum Oracles</span></span>

<span data-ttu-id="14e58-181">Oracle $ O $ , başka bir algoritmaya girdi olarak kullanılan "kara kutu" işlemidir.</span><span class="sxs-lookup"><span data-stu-id="14e58-181">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="14e58-182">Genellikle, bu gibi işlemler, $ \\ { \\ } \to \\ { \\ } $ $ n $ bit ikili girişi alan ve bir $ d $ bit ikili çıkış üreten bir klasik işlev olan f: 0, 1 ^ n 0, 1 ^ d kullanılarak tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="14e58-182">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="14e58-183">Bunu yapmak için, belirli bir ikili giriş $ x = (X_ { 0 } , X_ { 1 } , \noktalar, X_ { n-1) } $ göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="14e58-183">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="14e58-184">Qubit durumlarını $ \ket { \vec { x } } = \ket { X_ { 0 } } \otimes \ket { X_ { 1 } } \otimes \cdots \otimes \ket { X_ { n-1 } } $ olarak etiketleyebilir.</span><span class="sxs-lookup"><span data-stu-id="14e58-184">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="14e58-185">İlk $ $ olarak o $ \ket { x } = \ket { f (x) için o 'yu tanımlamaya çalışır } $ , ancak bu, birkaç soruna neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="14e58-185">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="14e58-186">İlk olarak, $ f 'nin $ farklı bir giriş ve çıkış boyutu ( $ n \ne m) olabilir $ ; Örneğin, $ O da $ kayıttaki qubit sayısını değiştirebilir.</span><span class="sxs-lookup"><span data-stu-id="14e58-186">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="14e58-187">İkincisi, $ n m olsa = bile $ , işlev ters çevrilebilir olmayabilir: $ x y için f (x) = f (y) f (y) $ $ \ne $ , o zaman $ o \ket { x } = o y, o, o & o \ket { } $ $ \dagger \ket { x } \ne o ^ \dagger o \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="14e58-187">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="14e58-188">Bu, adeklem işlemi olarak $ ^ ' i oluşturmayacağız \dagger $ ve Oracles için tanımlanmış bir adjoint 'ın olması anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="14e58-188">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="14e58-189">Bir Oracle 'ı hesaplama tabanlı durumlar üzerinde etkile tanımlama</span><span class="sxs-lookup"><span data-stu-id="14e58-189">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="14e58-190">$Yanıtınızı tutmak için ikinci bir m qubit kaydı sunarak bu sorunlardan her ikisiyle de ilgilenebiliriz $ .</span><span class="sxs-lookup"><span data-stu-id="14e58-190">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="14e58-191">Ardından, Oracle 'ın tüm hesaplama tabanlı durumlarında etkisini tanımlayacağız: tüm $ x \in \\ { 0, 1 \\ } ^ n $ ve $ y \in \\ { 0, 1 \\ } ^ d $ ,</span><span class="sxs-lookup"><span data-stu-id="14e58-191">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

$$
\begin{align}
    <span data-ttu-id="14e58-192">O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="14e58-192">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

<span data-ttu-id="14e58-193">Şimdi de şu anda bu $ = \dagger $ nedenle, daha önceki sorunları çözeceğiz.</span><span class="sxs-lookup"><span data-stu-id="14e58-193">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
><span data-ttu-id="14e58-194">O o o 'un o & u olduğunu görmek için, b! ' nin bir $ = { \dagger } $ $ = \boldone $ $ \oplus b \ OPLUS b a ile bu yana = $ $ , b \in \[ ! olduğunu unutmayın. Üs. Hayır-LOC ({)] 0, 1 \[ ! Üs. Hayır-LOC (})] $ .</span><span class="sxs-lookup"><span data-stu-id="14e58-194"> To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
><span data-ttu-id="14e58-195">Sonuç olarak, $ O \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="14e58-195"> As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="14e58-196">Bu şekilde, her hesaplama tabanlı durum x y için Oracle bu şekilde tanımlamak, $ \ket { } \ket { } $ O zaman $ O gibi $ diğer tüm durumları nasıl davrandığını da tanımlar.</span><span class="sxs-lookup"><span data-stu-id="14e58-196">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="14e58-197">Bu $ $ , tüm hisse işlemleri gibi, üzerinde işlem yaptığı durumunda doğrusal bir şekilde olmak üzere, o kadar her şey için hemen takip eder.</span><span class="sxs-lookup"><span data-stu-id="14e58-197">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="14e58-198">Örneğin, $ h \ket { 0 } = \ket { + } $ ve $ h \ket { 1 } = \ket { - } $ tarafından tanımlanan Hadamard işlemini göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="14e58-198">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="14e58-199">H 'nin üzerinde nasıl hareket eteceğimizi öğrenmek istiyoruz, $ $ $ \ket { + } $ Bu $ h $ 'nin doğrusal olduğunu kullanabiliriz.</span><span class="sxs-lookup"><span data-stu-id="14e58-199">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

$$
\begin{align}
<span data-ttu-id="14e58-200">H \ket { + } & = \frac { 1 } { \sqrt { 2 } } sa ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + h \ket { 1 } )\\\\</span><span class="sxs-lookup"><span data-stu-id="14e58-200">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\</span></span>
           &<span data-ttu-id="14e58-201">= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .</span><span class="sxs-lookup"><span data-stu-id="14e58-201"> = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
\end{align}
$$

<span data-ttu-id="14e58-202">Oracle O sitemizi tanımlama durumunda $ $ benzer şekilde, $ \ket { \psi } $ $ n + m qubits üzerinde herhangi bir durumun şu $ şekilde yazılabileceğini de kullanabilirsiniz</span><span class="sxs-lookup"><span data-stu-id="14e58-202">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

$$
\begin{align}
\ket<span data-ttu-id="14e58-203">{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ e } \alpha (x, y) \ket { x } \ket { y}</span><span class="sxs-lookup"><span data-stu-id="14e58-203">{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
\end{align}
$$

<span data-ttu-id="14e58-204">Burada $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C, } $ durumun katsayılarını temsil eder $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="14e58-204">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="14e58-205">Bu nedenle,</span><span class="sxs-lookup"><span data-stu-id="14e58-205">Thus,</span></span>

$$
\begin{align}
<span data-ttu-id="14e58-206">O o \ket { \psi } & = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\</span><span class="sxs-lookup"><span data-stu-id="14e58-206">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\</span></span>
             &<span data-ttu-id="14e58-207">= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ e } \alpha (x, y) \ket { x } \ket { y \ OPLUS f (x) } .</span><span class="sxs-lookup"><span data-stu-id="14e58-207"> = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

## <a name="phase-oracles"></a><span data-ttu-id="14e58-208">Phase Oracles</span><span class="sxs-lookup"><span data-stu-id="14e58-208">Phase oracles</span></span>
<span data-ttu-id="14e58-209">Alternatif olarak, $ $ $ $ O 'ya giriş temelinde bir _aşama_ uygulayarak bir Oracle 'a f $ 'yi kodlayabiliriz $ . Örneğin, $ o $ gibi$$</span><span class="sxs-lookup"><span data-stu-id="14e58-209">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$. For instance, we might define $O$ such that $$</span></span>
\begin{align}
    <span data-ttu-id="14e58-210">O \ket { x } = (-1) ^ { f (x) } \ket { x } .</span><span class="sxs-lookup"><span data-stu-id="14e58-210">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
\end{align}
$$
<span data-ttu-id="14e58-211">Bir evre, başlangıçta hesaplama tabanlı bir durum x 'te bir yazmaç üzerinde hareket eder $ \ket { } $ , bu aşama genel bir aşamadır ve bu nedenle observable değildir.</span><span class="sxs-lookup"><span data-stu-id="14e58-211">If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="14e58-212">Ancak bu tür bir Oracle, bir üst konuma veya denetimli bir işleme uygulandığında çok güçlü bir kaynak olabilir.</span><span class="sxs-lookup"><span data-stu-id="14e58-212">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="14e58-213">Örneğin, $ $ tek bir-qubit işlevi için bir Oracle O_f aşaması düşünün $ $ .</span><span class="sxs-lookup"><span data-stu-id="14e58-213">For example, consider a phase oracle $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="14e58-214">Ni$$</span><span class="sxs-lookup"><span data-stu-id="14e58-214">Then, $$</span></span>
\begin{align}
    <span data-ttu-id="14e58-215">O_f\ket{+}</span><span class="sxs-lookup"><span data-stu-id="14e58-215">O_f \ket{+}</span></span>
        &<span data-ttu-id="14e58-216">=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="14e58-216"> = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="14e58-217">=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="14e58-217"> = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="14e58-218">=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="14e58-218"> = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="14e58-219">=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } .</span><span class="sxs-lookup"><span data-stu-id="14e58-219"> = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
\end{align}
$$

<span data-ttu-id="14e58-220">Daha genel olarak, Oracles görünümlerinin her ikisi de yalnızca tek bir bit yerine gerçek sayılar döndüren klasik işlevleri temsil edecek şekilde ayarlanabilir.</span><span class="sxs-lookup"><span data-stu-id="14e58-220">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="14e58-221">Oracle 'ı uygulamak için en iyi yolu seçmek, bu Oracle 'ın belirli bir algoritma içinde nasıl kullanılacağına bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="14e58-221">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="14e58-222">Örneğin, [Deutsch-Jozsa algoritması](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) , Oracle 'ın birinci şekilde uygulandığı, [Grover 'in algoritması](https://en.wikipedia.org/wiki/Grover's_algorithm) ikinci şekilde uygulanan Oracle 'ı temel alır.</span><span class="sxs-lookup"><span data-stu-id="14e58-222">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="14e58-223">Daha fazla ayrıntı için [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465)' deki tartışmayı öneririz.</span><span class="sxs-lookup"><span data-stu-id="14e58-223">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
