---
title: 'Q # standart kitaplıklarında hata düzeltme'
description: "Qubits 'in durumunu korurken, Q # programlarınızda hata düzeltme kodlarını nasıl kullanacağınızı öğrenin."
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 514fe68f603b9a3a0b4607390719b08a43fe4967
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275727"
---
# <a name="error-correction"></a><span data-ttu-id="851d7-103">Hata Düzeltme</span><span class="sxs-lookup"><span data-stu-id="851d7-103">Error Correction</span></span> #

## <a name="introduction"></a><span data-ttu-id="851d7-104">Giriş</span><span class="sxs-lookup"><span data-stu-id="851d7-104">Introduction</span></span> ##

<span data-ttu-id="851d7-105">Klasik bilgi işlem 'da, bir bit hataları hatalara karşı korumak istiyorsa, veri bitini tekrarlayarak bu bit, *mantıksal bir bite* göre temsil etmek için genellikle yeterli olur.</span><span class="sxs-lookup"><span data-stu-id="851d7-105">In classical computing, if one wants to protect a bit against errors, it can often suffice to represent that bit by a *logical bit* by repeating the data bit.</span></span>
<span data-ttu-id="851d7-106">Örneğin, 0 {0} durumundaki bir bit kodlama olduğunu göstermek için 0 etiketinin üzerindeki bir satırı kullandığımızda $ \ üst çizgi = $0, veri biti 0 ' ın kodlaması olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="851d7-106">For instance, let $\overline{0} = 000$ be the encoding of the data bit 0, where we use the a line above the label 0 to indicate that it is an encoding of a bit in the 0 state.</span></span>
<span data-ttu-id="851d7-107">Aynı şekilde $ \üst çizgi = $111 olmasına izin vermemiz durumunda {1} , bir bit Çevirme hatası ile korunan basit bir yineleme kodu sunuyoruz.</span><span class="sxs-lookup"><span data-stu-id="851d7-107">If we similarly let $\overline{1} = 111$, then we have a simple repetition code that protects against any one bit flip error.</span></span>
<span data-ttu-id="851d7-108">Diğer bir deyişle, üç bitten herhangi biri çevrildeyse, büyük bir oy alarak mantıksal bit durumunu kurtarabiliriz.</span><span class="sxs-lookup"><span data-stu-id="851d7-108">That is, if any of the three bits are flipped, then we can recover the state of the logical bit by taking a majority vote.</span></span>
<span data-ttu-id="851d7-109">Klasik hata düzeltmesi, bu belirli örnekte çok daha zengin bir konudur ( [Lint 'in kodlama teorisine giriş](https://www.springer.com/us/book/9783540641339)önerisi önerilir), yukarıdaki yineleme kodu, hisse bilgilerini koruyan olası bir sorunu işaret eder.</span><span class="sxs-lookup"><span data-stu-id="851d7-109">Though classical error correction is a much richer subject that this particular example (we recommend [Lint's introduction to coding theory](https://www.springer.com/us/book/9783540641339)), the repetition code above already points to a possible problem in protecting quantum information.</span></span>
<span data-ttu-id="851d7-110">Yani, [hiçbir](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) bireysel bilgi bitini ölçyoruz ve yukarıdaki benzerleme vurguladı ile klasik kod ile büyük bir oy alıp aldığımızda, korumaya çalışmamız gereken kesin bilgileri kaybettiğimiz anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="851d7-110">Namely, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) implies that if we measure each individual qubit and take a majority vote by analogy to classical code above, then we have lost the precise information that we are trying to protect.</span></span>

<span data-ttu-id="851d7-111">Hisse birimi ayarında, ölçümün sorunlu olduğunu görüyoruz.</span><span class="sxs-lookup"><span data-stu-id="851d7-111">In the quantum setting, we will see that the measurement is problematic.</span></span> <span data-ttu-id="851d7-112">Yukarıdaki kodlamayı yine de uygulayabiliriz.</span><span class="sxs-lookup"><span data-stu-id="851d7-112">We can still implement the encoding above.</span></span>
<span data-ttu-id="851d7-113">Bu, hisse vaya hata düzeltmesini nasıl genelleştirmemiz gerektiğini görmek için yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="851d7-113">It is helpful to do so to see how we can generalize error correction to the quantum case.</span></span>
<span data-ttu-id="851d7-114">Bu nedenle, Let $ \ket{\üst çizgi {0} } = \ket {000} = \ket {0} \otimes {0} \tus\otimes {0} \tus$, ve Let $ \ket{\üst çizgi {1} } = \ket {111} $.</span><span class="sxs-lookup"><span data-stu-id="851d7-114">Thus, let $\ket{\overline{0}} = \ket{000} = \ket{0} \otimes \ket{0} \otimes \ket{0}$, and let $\ket{\overline{1}} = \ket{111}$.</span></span>
<span data-ttu-id="851d7-115">Daha sonra, bu, tüm girişler için yineleme kodumuzu tanımladık; Örneğin, $ \ket{\overline{+}} = (\ket{\üst çizgi {0} } + \ket{\üst çizgi {1} })/\sqrt {2} = (\tus+ {000} \ket {111} )/\sqrt {2} $.</span><span class="sxs-lookup"><span data-stu-id="851d7-115">Then, by linearity, we have defined our repetition code for all inputs; for instance, $\ket{\overline{+}} = (\ket{\overline{0}} + \ket{\overline{1}}) / \sqrt{2} = (\ket{000} + \ket{111}) / \sqrt{2}$.</span></span>
<span data-ttu-id="851d7-116">Özellikle, bir bit çevirme hatasına $X _1 $, orta qubit üzerinde çalışır, her iki dalda da gereken düzeltme tam olarak $X _1 $: $ $ \begin{hizalaması} X_1 \ket{\overline{+}} & = \frac {1} {\sqrt {2} } \left (X_1 {000} \tus+ X_1 \ket {111} \ right) \\ \\ & = \frac {1} {\sqrt {2} } \left ( {010} \tus+ {101} \tus\right).</span><span class="sxs-lookup"><span data-stu-id="851d7-116">In particular, letting a bit-flip error $X_1$ act on the middle qubit, we see that the correction needed in both branches is precisely $X_1$: $$ \begin{align} X_1 \ket{\overline{+}} & = \frac{1}{\sqrt{2}} \left( X_1 \ket{000} + X_1 \ket{111} \right) \\\\ & = \frac{1}{\sqrt{2}} \left( \ket{010} + \ket{101} \right).</span></span>
<span data-ttu-id="851d7-117">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="851d7-117">\end{align} $$</span></span>

<span data-ttu-id="851d7-118">Bu durumun, korumaya çalışmamız gereken çok durumu ölçmeden nasıl belirleyebileceklerini öğrenmek için, her farklı bit çevirme hatasının mantıksal durumlarımızla ne kadar olduğunu belirlemek yararlı olur:</span><span class="sxs-lookup"><span data-stu-id="851d7-118">To see how we can identify that this is the case without measuring the very state we are trying to protect, it is helpful to write down what each different bit flip error does to our logical states:</span></span>

| <span data-ttu-id="851d7-119">Hata $E $</span><span class="sxs-lookup"><span data-stu-id="851d7-119">Error $E$</span></span> | <span data-ttu-id="851d7-120">$E \ket{\üst çizgi {0} } $</span><span class="sxs-lookup"><span data-stu-id="851d7-120">$E\ket{\overline{0}}$</span></span> | <span data-ttu-id="851d7-121">$E \ket{\üst çizgi {1} } $</span><span class="sxs-lookup"><span data-stu-id="851d7-121">$E\ket{\overline{1}}$</span></span> |
| --- | --- | --- |
| <span data-ttu-id="851d7-122">$ \ cıvabitti $</span><span class="sxs-lookup"><span data-stu-id="851d7-122">$\boldone$</span></span> | <span data-ttu-id="851d7-123">$ \ ayraç {000} $</span><span class="sxs-lookup"><span data-stu-id="851d7-123">$\ket{000}$</span></span> | <span data-ttu-id="851d7-124">$ \ ayraç {111} $</span><span class="sxs-lookup"><span data-stu-id="851d7-124">$\ket{111}$</span></span> |
| <span data-ttu-id="851d7-125">$X _0 $</span><span class="sxs-lookup"><span data-stu-id="851d7-125">$X_0$</span></span> | <span data-ttu-id="851d7-126">$ \ ayraç {100} $</span><span class="sxs-lookup"><span data-stu-id="851d7-126">$\ket{100}$</span></span> | <span data-ttu-id="851d7-127">$ \ ayraç {011} $</span><span class="sxs-lookup"><span data-stu-id="851d7-127">$\ket{011}$</span></span> |
| <span data-ttu-id="851d7-128">$X _1 $</span><span class="sxs-lookup"><span data-stu-id="851d7-128">$X_1$</span></span> | <span data-ttu-id="851d7-129">$ \ ayraç {010} $</span><span class="sxs-lookup"><span data-stu-id="851d7-129">$\ket{010}$</span></span> | <span data-ttu-id="851d7-130">$ \ ayraç {101} $</span><span class="sxs-lookup"><span data-stu-id="851d7-130">$\ket{101}$</span></span> |
| <span data-ttu-id="851d7-131">$X _2 $</span><span class="sxs-lookup"><span data-stu-id="851d7-131">$X_2$</span></span> | <span data-ttu-id="851d7-132">$ \ ayraç {001} $</span><span class="sxs-lookup"><span data-stu-id="851d7-132">$\ket{001}$</span></span> | <span data-ttu-id="851d7-133">$ \ ayraç {110} $</span><span class="sxs-lookup"><span data-stu-id="851d7-133">$\ket{110}$</span></span> |

<span data-ttu-id="851d7-134">Kodyaptığımız durumu korumak için, üç hatayı birbirleriyle ve $ \boldone $ kimliğiyle $ \ket{\üst çizgi {0} } $ ve $ \ket{\üst çizgi} $ arasında ayrım yapmadan ayırt edebilmemiz gerekiyor {1} .</span><span class="sxs-lookup"><span data-stu-id="851d7-134">In order to protect the state that we're encoding, we need to be able to distinguish the three errors from each other and from the identity $\boldone$ without distinguishing between $\ket{\overline{0}}$ and $\ket{\overline{1}}$.</span></span>
<span data-ttu-id="851d7-135">Örneğin, $Z _0 $ değerini ölçyoruz, hiçbir hata durumunda $ \ket{\üst çizgi {0} } $ ve $ \ket{\üst çizgi} $ için farklı bir sonuç elde ediyoruz ve {1} Bu nedenle kodlanmış durumu daraldık.</span><span class="sxs-lookup"><span data-stu-id="851d7-135">For example, if we measure $Z_0$, we get a different result for $\ket{\overline{0}}$ and $\ket{\overline{1}}$ in the no-error case, so that collapses the encoded state.</span></span>
<span data-ttu-id="851d7-136">Diğer taraftan, her bir hesaplama tabanlı durumda $Z _0 Z_1 $, ilk iki bitin eşlik düzeyini ölçmeye göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="851d7-136">On the other hand, consider measuring $Z_0 Z_1$, the parity of the first two bits in each computational basis state.</span></span>
<span data-ttu-id="851d7-137">Pauli işlecinin her ölçüsünün, ölçülen durumun hangi eigenvalue 'a karşılık geldiğini denetlediğini, yukarıdaki tabloda $ \ket{\psı} $ ' ın her bir durumu için, yukarıdaki tabloda yer alan her durum $ \ma{\psi} $ ' ın, $ \pm\ket{\psı} $ olup olmadığını görmek için $Z _0 Z_1 \ket</span><span class="sxs-lookup"><span data-stu-id="851d7-137">Recall that each measurement of a Pauli operator checks which eigenvalue  the state being measured corresponds to, so for each state $\ket{\psi}$ in the table above, we can compute $Z_0 Z_1 \ket{\psi}$ to see if we get $\pm\ket{\psi}$.</span></span>
<span data-ttu-id="851d7-138">{000} {000} {111} {111} Bu ölçünün her iki kodlanmış duruma de aynı şeyi gerçekleştirmemiz için, $Z _0 Z_1 \tus= \ket $ ve bu $Z _0 Z_1 \ket = \ket $ olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="851d7-138">Note that $Z_0 Z_1 \ket{000} = \ket{000}$ and that $Z_0 Z_1 \ket{111} = \ket{111}$, so that we conclude that this measurement does the same thing to both encoded states.</span></span>
<span data-ttu-id="851d7-139">Diğer taraftan, $Z _0 Z_1 {100} \tus=-\ket {100} $ ve $Z _0 Z_1 \tus= {011} -\ket {011} $, bu nedenle $Z _0 Z_1 $ ölçmesi sonucu oluşan hata oluştuğunda yararlı bilgileri ortaya çıkarır.</span><span class="sxs-lookup"><span data-stu-id="851d7-139">On the other hand, $Z_0 Z_1 \ket{100} = - \ket{100}$ and $Z_0 Z_1 \ket{011} = -\ket{011}$, so the result of measuring $Z_0 Z_1$ reveals useful information about which error occurred.</span></span>

<span data-ttu-id="851d7-140">Bunu vurgulamak için yukarıdaki tabloyu yineliyoruz, ancak her satırda $Z _0 Z_1 $ ve $Z _1 Z_2 $ ölçüm sonuçlarını eklersiniz.</span><span class="sxs-lookup"><span data-stu-id="851d7-140">To emphasize this, we repeat the table above, but add the results of measuring $Z_0 Z_1$ and $Z_1 Z_2$ on each row.</span></span>
<span data-ttu-id="851d7-141">Her ölçümün sonucunu, sırasıyla Q # değerlerine karşılık gelen $ + $ veya $-$ gibi gözlemlenen eigenvalue işaretine göre gösterir `Result` `Zero` `One` .</span><span class="sxs-lookup"><span data-stu-id="851d7-141">We denote the results of each measurement by the sign of the eigenvalue that is observed, either $+$ or $-$, corresponding to the Q# `Result` values of `Zero` and `One`, respectively.</span></span>

| <span data-ttu-id="851d7-142">Hata $E $</span><span class="sxs-lookup"><span data-stu-id="851d7-142">Error $E$</span></span> | <span data-ttu-id="851d7-143">$E \ket{\üst çizgi {0} } $</span><span class="sxs-lookup"><span data-stu-id="851d7-143">$E\ket{\overline{0}}$</span></span> | <span data-ttu-id="851d7-144">$E \ket{\üst çizgi {1} } $</span><span class="sxs-lookup"><span data-stu-id="851d7-144">$E\ket{\overline{1}}$</span></span> | <span data-ttu-id="851d7-145">Sonuç olarak $Z _0 Z_1 $</span><span class="sxs-lookup"><span data-stu-id="851d7-145">Result of $Z_0 Z_1$</span></span> | <span data-ttu-id="851d7-146">$Z _1 Z_2 $ sonucu</span><span class="sxs-lookup"><span data-stu-id="851d7-146">Result of $Z_1 Z_2$</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="851d7-147">$ \ cıvabitti $</span><span class="sxs-lookup"><span data-stu-id="851d7-147">$\boldone$</span></span> | <span data-ttu-id="851d7-148">$ \ ayraç {000} $</span><span class="sxs-lookup"><span data-stu-id="851d7-148">$\ket{000}$</span></span> | <span data-ttu-id="851d7-149">$ \ ayraç {111} $</span><span class="sxs-lookup"><span data-stu-id="851d7-149">$\ket{111}$</span></span> | $+$ | $+$ |
| <span data-ttu-id="851d7-150">$X _0 $</span><span class="sxs-lookup"><span data-stu-id="851d7-150">$X_0$</span></span> | <span data-ttu-id="851d7-151">$ \ ayraç {100} $</span><span class="sxs-lookup"><span data-stu-id="851d7-151">$\ket{100}$</span></span> | <span data-ttu-id="851d7-152">$ \ ayraç {011} $</span><span class="sxs-lookup"><span data-stu-id="851d7-152">$\ket{011}$</span></span> | $-$ | $+$ |
| <span data-ttu-id="851d7-153">$X _1 $</span><span class="sxs-lookup"><span data-stu-id="851d7-153">$X_1$</span></span> | <span data-ttu-id="851d7-154">$ \ ayraç {010} $</span><span class="sxs-lookup"><span data-stu-id="851d7-154">$\ket{010}$</span></span> | <span data-ttu-id="851d7-155">$ \ ayraç {101} $</span><span class="sxs-lookup"><span data-stu-id="851d7-155">$\ket{101}$</span></span> | $-$ | $-$ |
| <span data-ttu-id="851d7-156">$X _2 $</span><span class="sxs-lookup"><span data-stu-id="851d7-156">$X_2$</span></span> | <span data-ttu-id="851d7-157">$ \ ayraç {001} $</span><span class="sxs-lookup"><span data-stu-id="851d7-157">$\ket{001}$</span></span> | <span data-ttu-id="851d7-158">$ \ ayraç {110} $</span><span class="sxs-lookup"><span data-stu-id="851d7-158">$\ket{110}$</span></span> | $+$ | $-$ |

<span data-ttu-id="851d7-159">Bu nedenle, iki ölçümün sonuçları, hangi bit çevirme hatasının oluştuğunu benzersiz olarak belirler, ancak hangi durumu kodladığımızda bilgi vermeksizin.</span><span class="sxs-lookup"><span data-stu-id="851d7-159">Thus, the results of the two measurements uniquely determines which bit-flip error occurred, but without revealing any information about which state we encoded.</span></span>
<span data-ttu-id="851d7-160">Bu sonuçlara bir *sendromu*çağrısı yaptık ve bir sendromu 'yi *Kurtarma*olarak neden olan hataya geri eşleme sürecine başvurduk.</span><span class="sxs-lookup"><span data-stu-id="851d7-160">We call these results a *syndrome*, and refer to the process of mapping a syndrome back to the error that caused it as *recovery*.</span></span>
<span data-ttu-id="851d7-161">Özellikle, kurtarma işlemi, oluşan sendromu girişi olarak geçen bir *Klasik* çıkarım prosedürü ve oluşmuş olabilecek hataların nasıl düzeltileceğiyle ilgili bir hata döndürür.</span><span class="sxs-lookup"><span data-stu-id="851d7-161">In particular, we emphasize that recovery is a *classical* inference procedure which takes as its input the syndrome which occurred, and returns a prescription for how to fix any errors that may have occurred.</span></span>

> [!NOTE]
> <span data-ttu-id="851d7-162">Yukarıdaki bit çevirme kodu yalnızca tek bit çevirme hatalarına karşı doğru olabilir; diğer bir deyişle, `X` tek bir qubit üzerinde işlem gören bir işlemdir.</span><span class="sxs-lookup"><span data-stu-id="851d7-162">The bit-flip code above can only correct against single bit-flip errors; that is, an `X` operation acting on a single qubit.</span></span>
> <span data-ttu-id="851d7-163">Birden `X` fazla qubit 'e uygulamak, şu kurtarma sonrasında $ \ket{\üst çizgi {0} } $ değerini $ \ket{\üst çizgi {1} } $ olarak eşleştirir.</span><span class="sxs-lookup"><span data-stu-id="851d7-163">Applying `X` to more than one qubit will map $\ket{\overline{0}}$ to $\ket{\overline{1}}$ following recovery.</span></span>
> <span data-ttu-id="851d7-164">Benzer şekilde, bir aşama çevirme işleminin uygulanması `Z` $ \ket{\üst çizgi {1} } $ $-\ket{\üst çizgi} $ olarak eşlenir {1} ve bu nedenle $ \ket{\overline{+}} $ ile $ \ket{\üst çizgi} $ arasında eşleme olur {-} .</span><span class="sxs-lookup"><span data-stu-id="851d7-164">Similarly, applying a phase flip operation `Z` will map $\ket{\overline{1}}$ to $-\ket{\overline{1}}$, and hence will map $\ket{\overline{+}}$ to $\ket{\overline{-}}$.</span></span>
> <span data-ttu-id="851d7-165">Genellikle, daha fazla hata sayısını işlemek ve $Z $ hata ve $X $ hatası işlemek için kodlar oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="851d7-165">More generally, codes can be created to handle larger number of errors, and to handle $Z$ errors as well as $X$ errors.</span></span>

<span data-ttu-id="851d7-166">Ölçümleri, tüm kod durumlarında aynı şekilde davranan hisse hata düzeltmesine ilişkin ölçümleri anlayabiliriz *.*</span><span class="sxs-lookup"><span data-stu-id="851d7-166">The insight that we can describe measurements in quantum error correction that act the same way on all code states, is the essence of the *stabilizer formalism*.</span></span>
<span data-ttu-id="851d7-167">Q # Canon, sabitleyici kodlardan kodlama ve kod çözme hakkında bir çerçeve sağlar ve bir hata durumundan nasıl kurtardığını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="851d7-167">The Q# canon provides a framework for describing encoding into and decoding from stabilizer codes, and for describing how one recovers from errors.</span></span>
<span data-ttu-id="851d7-168">Bu bölümde, bu Framework 'ü ve uygulamayı birkaç basit hisse hata düzeltme koduna anladık.</span><span class="sxs-lookup"><span data-stu-id="851d7-168">In this section, we describe this framework and its application to a few simple quantum error-correcting codes.</span></span>

> [!TIP]
> <span data-ttu-id="851d7-169">Sabitleyici formalroni'ya tam giriş, bu bölümün kapsamının dışındadır.</span><span class="sxs-lookup"><span data-stu-id="851d7-169">A full introduction to the stabilizer formalism is beyond the scope of this section.</span></span>
> <span data-ttu-id="851d7-170">[Gottesman 2009](https://arxiv.org/abs/0904.2557)' ye daha fazla bilgi edinmek isteyen okuyucular hakkında bilgi veririz.</span><span class="sxs-lookup"><span data-stu-id="851d7-170">We refer readers interested in learning more to [Gottesman 2009](https://arxiv.org/abs/0904.2557).</span></span>

## <a name="representing-error-correcting-codes-in-q"></a><span data-ttu-id="851d7-171">Q 'daki hata düzeltme kodlarını temsil etme #</span><span class="sxs-lookup"><span data-stu-id="851d7-171">Representing Error Correcting Codes in Q#</span></span> ##

<span data-ttu-id="851d7-172">Q # Canon, hata düzeltme kodları belirtmeye yardımcı olmak için birkaç farklı Kullanıcı tanımlı tür sağlar:</span><span class="sxs-lookup"><span data-stu-id="851d7-172">To help specify error correcting codes, the Q# canon provides several distinct user-defined types:</span></span>

- <span data-ttu-id="851d7-173"><xref:microsoft.quantum.errorcorrection.logicalregister>`= Qubit[]`: Bir qubits kaydının bir hata düzeltme kodunun kod bloğu olarak yorumlanması gerektiğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="851d7-173"><xref:microsoft.quantum.errorcorrection.logicalregister> `= Qubit[]`: Denotes that a register of qubits should be interpreted as the code block of an error-correcting code.</span></span>
- <span data-ttu-id="851d7-174"><xref:microsoft.quantum.errorcorrection.syndrome>`= Result[]`: Bir ölçüm sonuçları dizisinin, bir kod bloğunda ölçülen sendromu olarak yorumlanması gerektiğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="851d7-174"><xref:microsoft.quantum.errorcorrection.syndrome> `= Result[]`: Denotes that an array of measurement results should be interpreted as the syndrome measured on a code block.</span></span>
- <span data-ttu-id="851d7-175"><xref:microsoft.quantum.errorcorrection.recoveryfn>`= (Syndrome -> Pauli[])`: Bir eşitleniyor işlevinin *classical* , bir sendromu yorumlamak ve uygulanması gereken bir düzeltme döndürmesi için kullanılması gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="851d7-175"><xref:microsoft.quantum.errorcorrection.recoveryfn> `= (Syndrome -> Pauli[])`: Denotes that a *classical* function should be used to interpret a syndrome and return a correction that should be applied.</span></span>
- <span data-ttu-id="851d7-176"><xref:microsoft.quantum.errorcorrection.encodeop>`= ((Qubit[], Qubit[]) => LogicalRegister)`: Bir işlemin bir hata düzeltme kodunun kod bloğunu oluşturmak için, verileri yeni Andalla qubits ile birlikte temsil eden bir işlem olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="851d7-176"><xref:microsoft.quantum.errorcorrection.encodeop> `= ((Qubit[], Qubit[]) => LogicalRegister)`: Denotes that an operation takes qubits representing data along with fresh ancilla qubits in order to produce a code block of an error-correcting code.</span></span>
- <span data-ttu-id="851d7-177"><xref:microsoft.quantum.errorcorrection.decodeop>`= (LogicalRegister => (Qubit[], Qubit[]))`: Bir işlemin kod bloğunu, verileri veri qubits 'e düzeltmede hata kodu bloğunu ve sendromu bilgilerini temsil etmek için kullanılan anetla qubits 'i temsil ettiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="851d7-177"><xref:microsoft.quantum.errorcorrection.decodeop> `= (LogicalRegister => (Qubit[], Qubit[]))`: Denotes than an operation decomposes a code block of an error correcting code into the data qubits and the ancilla qubits used to represent syndrome information.</span></span>
- <span data-ttu-id="851d7-178"><xref:microsoft.quantum.errorcorrection.syndromemeasop>`= (LogicalRegister => Syndrome)`: Kod tarafından korunan durumu etkilemeden, bir kod bloğunun sendromu bilgilerini ayıklamak için kullanılması gereken bir işlemi gösterir.</span><span class="sxs-lookup"><span data-stu-id="851d7-178"><xref:microsoft.quantum.errorcorrection.syndromemeasop> `= (LogicalRegister => Syndrome)`: Denotes an operation that should be used to extract syndrome information from a code block, without disturbing the state protected by the code.</span></span>

<span data-ttu-id="851d7-179">Son olarak, Canon <xref:microsoft.quantum.errorcorrection.qecc> bir hisse hata düzeltme kodu tanımlamak için gereken diğer türleri toplamak üzere tür sağlar.</span><span class="sxs-lookup"><span data-stu-id="851d7-179">Finally, the canon provides the <xref:microsoft.quantum.errorcorrection.qecc> type to collect the other types required to define a quantum error-correcting code.</span></span> <span data-ttu-id="851d7-180">Her bir sabitleyici hisse ıcı kodu ile ilişkili kod uzunluğu $n $, mantıksal qubit sayısı $k $, ve en düşük uzaklık $d $, genellikle ⟦ $n $, $k $, $d $ ⟧ gösteriminde kolay bir şekilde gruplanırlar.</span><span class="sxs-lookup"><span data-stu-id="851d7-180">Associated with each stabilizer quantum code is the code length $n$, the number $k$ of logical qubits, and the minimum distance $d$, often conveniently grouped together in the notation ⟦$n$, $k$, $d$⟧.</span></span> <span data-ttu-id="851d7-181">Örneğin, <xref:microsoft.quantum.errorcorrection.bitflipcode> işlevi ⟦ 3, 1, 1 ⟧ bit çevirme kodunu tanımlar:</span><span class="sxs-lookup"><span data-stu-id="851d7-181">For example, the <xref:microsoft.quantum.errorcorrection.bitflipcode> function defines the ⟦3, 1, 1⟧ bit flip code:</span></span>

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

<span data-ttu-id="851d7-182">`QECC`Türün bir kurtarma işlevi içermediğinden *emin* olun.</span><span class="sxs-lookup"><span data-stu-id="851d7-182">Notice that the `QECC` type does *not* include a recovery function.</span></span>
<span data-ttu-id="851d7-183">Bu, kodun kendi tanımını değiştirmeden hataları düzeltmek için kullanılan kurtarma işlevini değiştirememize olanak sağlar; Bu özellik, karakter seçme ölçümlerinden geri bildirim kurtarma tarafından kabul edilen modele dahil edildiğinde özellikle kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="851d7-183">This allows us to change the recovery function that is used in correcting errors without changing the definition of the code itself; this ability is in particular useful when incorporating feedback from characterization measurements into the model assumed by recovery.</span></span>

<span data-ttu-id="851d7-184">Bir kod bu şekilde tanımlandıktan sonra, <xref:microsoft.quantum.errorcorrection.recover> hataları kurtarmak için işlemi kullanabiliriz:</span><span class="sxs-lookup"><span data-stu-id="851d7-184">Once a code is defined in this way, we can use the <xref:microsoft.quantum.errorcorrection.recover> operation to recover from errors:</span></span>

```qsharp
let code = BitFlipCode();
let fn = BitFlipRecoveryFn();
let X0 = ApplyPauli([PauliX, PauliI, PauliI], _);
using (scratch = Qubit[nScratch]) {
    let logicalRegister = encode(data, scratch);
    // Cause an error.
    X0(logicalRegister);
    Recover(code, fn, logicalRegister);
    let (decodedData, decodedScratch) = decode(logicalRegister);
    ApplyToEach(Reset, decodedScratch);
}
```

<span data-ttu-id="851d7-185">Bu, [bit çevirme kod örneğinde](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code)daha ayrıntılı bir şekilde araştırıyoruz.</span><span class="sxs-lookup"><span data-stu-id="851d7-185">We explore this in more detail in the [bit flip code sample](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code).</span></span>

<span data-ttu-id="851d7-186">Bit çevirme kodundan başlayarak, Q # Canon, [beş qubit kusursuz kodun](https://arxiv.org/abs/quant-ph/9602019)uygulamalarıyla ve her ikisi de rastgele bir tek qubit hatayı düzeltebilen [yedi-qubit kodu](https://arxiv.org/abs/quant-ph/9705052)ile sağlanır.</span><span class="sxs-lookup"><span data-stu-id="851d7-186">Aside from the bit-flip code, the Q# canon is provided with implementations of the [five-qubit perfect code](https://arxiv.org/abs/quant-ph/9602019), and the [seven-qubit code](https://arxiv.org/abs/quant-ph/9705052), both of which can correct an arbitrary single-qubit error.</span></span>