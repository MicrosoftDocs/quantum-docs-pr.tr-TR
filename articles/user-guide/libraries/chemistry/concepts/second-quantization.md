---
title: İkinci Quantitleştirme
description: Hisse programlama aşamasında elektronik yapıların modellenmesi için Ikinci bir Quantileştirme yaklaşımı hakkında bilgi edinin.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6becd348f7b3957cb60b16bbd5a28228527e1d4c
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835817"
---
# <a name="second-quantization"></a>İkinci Quantitleştirme

İkinci quantileştirme, farklı bir lens aracılığıyla elektronik yapı sorununa bakar.
$N _e $ elektriklerinin her birini belirli bir duruma (veya Orbe) atamak yerine, ikinci bir ölçü her ikisi de izler ve bunların her birinde mevcut bir elektron olup olmadığını ve aynı zamanda ilgili dalga işlevinin simetri özelliklerinin otomatik olarak olmasını sağlar.
Bu önemlidir çünkü, giriş durumunu simetrik hale getirme (fermıons için gereklidir) ve ayrıca ikinci bir satışın bu tür modellerin küçük hisse malarca bilgisayarlar kullanılarak simülasyonu yapmasına izin verdiği için, bu, hisse ansız deneme modellerinin belirtilmesini sağlar.

İkinci bir ölçü işleme örneği olarak, $ \ psi_0 \cnoktalara \ psi_ {N-1} $ öğesinin bir dizi uzamsal Orbitals olduğunu varsayalım.
Bu Orbitals, sistemi kabul edilen sonlu bir küme içinde mümkün olduğunca doğru şekilde temsil edecek şekilde seçilir.
Bu tür yörüntünlerde yaygın bir örnek, Hydrogen atom için bir egensiz oluşturan atomik orbitünlerdir.
Elektriler iki döngü durumuna sahip olduğundan, bu tür uzamsal orbiye her biri için iki elektriklarca bulunabilir.
Yani, geçerli temel durumlar $ \ psi_ {0 biçiminde olur. \upok}, \lnoktalar, \ psi_ {N-1, \upoks}, \ psi_ {0, \downarrow}, \lnoktalar, \ psi_ {N-1, \downarrow} $ burada $ \upok $ ve $ \downok $, serbestlik derecesindeki iki eigenstates belirten etiketlerdir.
$ \Sigma \in \uparrow için $ (j, \sigma) $ öğesinin bu Birleşik dizinine \{ , \downarrow \} $, hem uzamsal hem de bir serbestlik derecesi de depoladığından, bir döndürme-orblik olarak adlandırılır.
Kimya kitaplığında, döndürme-Orbitals bir `SpinOrbital` veri yapısında depolanır ve aşağıdaki gibi oluşturulur.

```csharp
    // First, we load the namespace containing spin-orbital objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // First, we assign an orbital index, say `5`. Note that we use 0-indexing,
    // so this is the 6th orbital.
    var orbitalIdx = 5;

    // Second, we assign a spin index, say `Spin.u` for spin up or `Spin.d` for spin down.
    var spin = Spin.d;

    // the spin-orbital (5, ↓) is then
    var spinOrbital = new SpinOrbital(orbitalIdx, spin);

    // A tuple `(int, Spin)` is also implicitly recognized as a spin-orbital.
    (int, Spin) tuple = (orbitalIdx, spin);

    // We explicitly specify the type of `spinOrbital1` to demonstrate
    // the implicit cast to `SpinOrbital`.
    SpinOrbital spinOrbital1 = tuple;
```

Bu, her bir dizin artık bir $ (j, \sigma) $ numaralandırması olduğu için, dalga işlevinin hem dönüş hem de uzamsal kısmının her ikisinin de $ \ psi_ {0} \cnoktalar \ psi_ {2N-1} $ olarak olduğunu düşündük anlamına gelir.
Olası bir numaralandırma $g (j, \sigma) = j + N\sigma ' $.
Başka bir olası numaralandırma $h (j, \sigma) = 2 * j + \sigma $.
Hisse dili Mistry kitaplığı bu kuralları kullanabilir ve bu tür bir kodlamada bulunan döndürme-Orbitals aşağıdaki gibi oluşturulabilir.

```csharp
    // Let us use the spin orbital created in the previous snippet.
   var spinOrbital = new SpinOrbital(5, Spin.d);

   // Let us set the total number of orbitals to be say, `7`.
   var nOrbitals = 7;

    // This converts a spin-orbital index to a unique integer, in this case `12`,
    // using the formula `g(j,σ)`.
    var integerIndexHalfUp = spinOrbital.ToInt(IndexConvention.HalfUp);

    // This converts a spin-orbital index to a unique integer, in this case `11`,
    // using the formula `h(j,σ)`.
    var integerIndexUpDown = spinOrbital.ToInt(IndexConvention.UpDown);

    // The default conversion uses the formula `h(j,σ)`, in this case `11`.
    var integerIndexDefault = spinOrbital.ToInt();
```

Fermıonic sistemleri için Pauli dışlama ilkesi, aynı anda herhangi bir döndürme/zaman için birden fazla elektron 'in bulunmasını engeller.
Yani, $ \ psi_1 $ as \begin{Equation} \ psi_1 \ettarrow \begin{Cases} \tus& _1 için iki yasal durumu yazabildiğimiz anlamına gelir. {0} $ \ psi_1 $ boş değilse,} \\\
{1}\tus_1 & \Text{If $ \ psi_1 $ dolu.} \end{Cases} \end{Equation} bu kodlama, farklı bir ücret bit olarak elektronik meslek depolayabileceği anlamına gelir.

$2N $ $ $ $ $ $ $ $ $ $ $ $ $ $ $/bit
Örnek olarak, $N = $2 sonra durum $ $ \ayraç \ ayraç \ ayraç \ ayraç {0} {1} {1} {0} , $ $

döndürme Orbitals $1 $ ve $2 $, kalan boş ile birlikte yer alar.
Benzer şekilde, $ $ \ ayraç {0} \ EQUIV \ ayraç \ {0} _ {0} cnoktalar \ ayraç {0} _{N-1}, $ $

, elektriksiz değildir ve ' vakum State ' olarak bilinir.

İkinci bir sağlığa yönelik güzel bir yan etkisi, artık hisse durumunun simetriyi açıkça takip etmemiz gerekmez.
Bunun nedeni, yaptığımız gibi, bir döndürme/atma 'un elektronik mesleklerini oluşturan ve yok eden operatörlerin commutation kuralları aracılığıyla bunun yerine durumunun kendisini temsil eder.

## <a name="fermionic-operators"></a>Fermıonic işleçleri

İkinci Satışlara dayalı vektörlere uygulanan iki temel operatör, oluşturma ve Ayla ilgili işleçler olarak bilinir.
Bu işleçler, belirli bir konuma elektriler ekler veya yok eder.
Bunlar sırasıyla $a ^ \ dagger_j $ ve $a _j $ olarak gösterilir.

Örneğin, \begin{hizalaması} a ^ \ dagger_1 {0} \tus_1 = \tus_1 {1} , \dörtlü a ^ \ dagger_1 \ayraç {1} _1 = 0, \dörtlü A_1 \demet {0} _1 = 0, \dörtlü A_1 \tus_1 {1} = {0} \tus_1.
\end{hizalaması} burada $a ^ \ dagger_1 {1} \tus_1 = 0 $ ve $a _1 \ ayraç {0} _1 $ değerini, sıfır vektörü $ \ ayraç {0}
Bu tür işleçler hermitian veya Unitary değildir.
Türü kullanarak genel oluşturma ve annun işleçlerini temsil ediyoruz <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> .
Örneğin, tek bir oluşturma işleci, takip olarak temsil edilir.

```csharp
    // We load the namespace containing ladder operator objects.
    using Microsoft.Quantum.Chemistry.LadderOperators;

    // Let us use the spin orbital created in the previous snippet.
    var spinOrbitalInteger = new SpinOrbital(5, Spin.d).ToInt();

    // We specify either a creation or annihilation operator using 
    // the enumerable type `RaisingLowering.u` or `RaisingLowering.d`
    // respectively;
    var creationEnum = RaisingLowering.u;

    // The type representing a creation operator is then initialized 
    // as follows. Here, we index these operators with integers.
    // Hence we initialize the generic ladder operator with an
    // integer index type.
    var ladderOperator0 = new LadderOperator<int>(creationEnum, spinOrbitalInteger);

    // An alternate constructor for a LadderOperator instead uses
    // a tuple.
    var ladderOperator1 = new LadderOperator<int>((creationEnum, spinOrbitalInteger));
```

Bu tür işleçleri de kullanarak Express $ $ \ket \ ayraç \ ayraç \ {0} {1} {1} {0} bir ^ \ dagger_1 a ^ \ dagger_2 \tus^ {0} {\otimes 4} olabilir.
$ $ Bu işleç dizisi, yukarıda göz önünde bulundurmanız gereken tek veya daha büyük bir barkoda benzer C# kodu kullanılarak Hamiltonian simülasyon kitaplığı içinde oluşturulur:
```csharp
    // We load the namespace containing fermion-related objects.
    using Microsoft.Quantum.Chemistry.Fermion;

    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We can convert this array of tuples to a sequence of ladder
    // operators using the `ToLadderSequence()` methods.
    var ladderSequences = indices.ToLadderSequence();

    // Sequences of ladder operators are quite general. For instance,
    // they could be bosonic operators, instead of fermionic operators.
    // We specialize them by constructing a `FermionTerm` representing 
    // a fermion creation operator on the index `2` followed by `1`.
    var fermionTerm = new FermionTerm(ladderSequences);
```

$K $ Fermıons sisteminde, ikinci bir $a {1} \ dagger_i $ oluşturma işlecinin eylemi $ $ a ^ \ dagger_i \ket{n_1, n_2, \lnoktalar, 0_i, \lnoktalar, n_k} = (-1) ^ {S_i} \ket{n_1, n_2, \lnoktalar, 1_i, \lnoktalar, n_k}, $ $ ve $ $ a ^ \ dagger_i \ket{n_1, n_2, \lnoktalar, 1_i, \lnoktalar, n_k} = 0, $ $ burada $S _i = \ sum_ {j<i} a ^ \ dagger_j a_j $ tek bir parçacık durumunda olan ve bir dizin $j < ı $ olan Fermıons sayısını ölçer.

Üçüncü bir operatör de genellikle ikinci bir satışta temsilde kullanılır.
Bu işleç sayı işleci olarak bilinir ve \begin{Equation} n_i = a ^ \ dagger_i a_i tarafından tanımlanır.
\end{Equation} Bu işleç, \begin{hizalaması} n_i {0} \tus_i &= 0 \ No.\\\
n_i \demet {1} _i &= \demet {1} _i.
\end{hizalaması} Yukarıdaki `FermionTerm` örneklere benzer, bu sayı işleci aşağıdaki gibi oluşturulur.
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have omitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

Fermıonic sistemlerinde oluşturma veya alma işleçleri kullanılırken bir alt tlek ortaya çıktı.
Geçerli hisse madık etiketlerin değişimi altında simetrik bir değer olmasını gerektirir.
Yani $ $ a ^ \ dagger_2 a ^ \ dagger_1 {0} \tus=-a ^ \ dagger_1 a ^ \ dagger_2 \tusa {0} .
$ $ Bu tür işleçler ' Anti-commute ' ve genel olarak tüm $i j $ \ Begin{hizalaması} a ^ \ dagger_i a ^ \ dagger_j =-(1-\ delta_ {i, j}) a ^ \ dagger_j a ^ \ dagger_i, \dörtlü a ^ \ dagger_i a_j = \ delta_ {i, j}-a_j a ^ \ dagger_i.
\end{hizalaması} bu nedenle, aşağıdaki iki <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> örnek inetiçele olarak kabul edilir
```csharp
    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We now construct a `LadderSequence` representing a creation operator
    // on the index 1 followed by 2, then a term with the reverse ordering.
    var laddderSeqeunce = indices.ToLadderSequence();
    var laddderSeqeunceReversed = indices.Reverse().ToLadderSequence();

    // The following Boolean is `false`.
    var equal = laddderSeqeunce == laddderSeqeunceReversed;
```

Oluşturma işleçlerini her birinin anti-commute, ikinci bir ölçü kullanan bir gösterimi kullanmanın, Fermıons 'ın yalarca siklerinin üzerinde karşılaştıkları zorlukları obviate anlamına gelir.
Bunun yerine, sınama oluşturma işleçleri tanımımızda yeniden ortaya çıktı. 

Anti-commutation kurallarını kullanarak bazı örnekler, `LadderSequence` bazen eksi işaretine kadar olan fermıonic işleçleri dizisine karşılık gelir.
Örneğin, Hamiltonian $a _0 ^ \dağılım a_1 ^ \dağılım a_1 a_0 =-a_1 ^ \dağılım a_0 ^ \ dağılım A_1 a_0 $ değerini düşünün.
Bu, her için kurallı bir sıralama tanımlamamıza olanak sağlar `FermionTerm` .
Herhangi biri `FermionTerm` , aşağıdaki gibi otomatik olarak kurallı bir sıraya konur.
```csharp
    // We now construct two `FermionTerms` that are equivalent with respect to
    // anti-commutation up to a sign change.
    var fermionTerm0 = new FermionTerm(new[] { 0, 1, 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 1, 0, 1, 0 }.ToLadderSequence());

    // The following Boolean is `true`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // The change in sign is not compared above, but is an internally tracked
    // property of `FermionTerm`.
    int sign0 = fermionTerm0.Coefficient;
    var sign1 = fermionTerm1.Coefficient;

    // The following Boolean is `false`.
    var signEqual = sign0 == sign1;
```

## <a name="second-quantized-fermionic-hamiltonian"></a>İkinci Quantitik Gümıonic Hamiltonian

Büyük olasılıkla, [elektronik sistemler için](xref:microsoft.quantum.chemistry.concepts.quantummodels) ücretlerdeki Hamiltonian 'nin oluşturma ve Ayla ilgili işleçler açısından yazılabilmesini unsurprising.
Özellikle, $ \psı \_ j $, temeli oluşturan döndürme orbitleri ise

\begin{Equation} \hat{H} = \sum \_ {PQ} h \_ {PQ} a ^ \_ \hanuger p a \_ q + \frac {1} {2} \sum \_ {pqrs} h \_ {pqrs} a ^ \dağılım \_ p a ^ \_ \_ \dokger q a ra \_ s + H \_ {\Textrm NUC}, \label{EQ: totalham} \end{Equation}; burada $h \_ {\textrm NUC} $, nükleer enerji

\begin{hizalaması} h \_ {PQ} &= \int \_ {-\infty} ^ \infty \psı ^ \* \_ p (x \_ 1) \left (-\frac{\nabla ^ 2} {2} + V (x \_ 1) \right) \psı \_ q (x \_ 1) \mathrm{d} ^ 3x \_ 1, \end{hizalaması}

Burada $V (x) $, ortalama alan potansiyeli ve

\begin{hizalaması} h \_ {pqrs} &= \int \_ {-\infty} ^ \inf\ınt \_ {-\infty} ^ \infty\psı \_ p ^ \* (x \_ 1) \psı \_ q ^ \* (x \_ 2) \left (\frac {1} {| x_1-x_2 |} \right) \psı \_ r (x \_ 2) \psı \_ s (x \_ 1) \mathrm{d} ^ 3x \_ 1 \ mathrm {d} ^ 3x \_ 2. \ Label {EQ: integrals} \end{hizalaması}

$H \_ {PQ} $ terimleri yalnızca tek bir elekons içerdiğinden ve benzer $h şekilde \_ {pqrs} $ iki elektron integralleri içerdiğinden, bu koşullara tek bir elektron integralya denir.
Bu katsayıların değerlerini hesaplamak bir integral gerektirdiğinden integrallar olarak adlandırılırlar.
Tek bir elektron terimi, bireysel elektriklerin Kinetic enerji ve nuclei 'nin elektrik alanları ile etkileşimlerini anlatmaktadır.
Diğer yandan iki elektron integrallarca, elektriler arasındaki etkileşimler açıklanır.

Bu koşulların ne anlama geldiğini, her birini oluşturan oluşturma ve dumaılasyon işleçlerinden nasıl eğilebileceği.
Örneğin, $h _ {PQ} a ^ \ dagger_p a_q $, orbili$p $ ' ı döndürme ve döndürme için bir veya daha fazla $q $ arasındaki elektron çizlemeyi açıklar.
Benzer şekilde, $h _ {pqrs} a ^ \ dagger_p a ^ \ dagger_q a_r a_s $ (ayrı $p, q, r, s $), döndürme ve $r $ ' de iki elektrikten ve $s $ ve $p $ ile sona eriyor.
$R = q $ ve $p = s $ $h _ {prrp} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = h_ {prrp} n_p N_R $, iki elektriğe yakın enerji cezası sunar, ancak bir dinamik işlemini tanımlamaz.

Bu tür Hamiltonians `FermionHamiltonian` , temel olarak istenen tüm örnekleri içeren bir liste olan sınıfını kullanarak temsil edebilir `FermionTerm` .
Hamiltonians hermitian as tanımına göre, koşulların `HermitianFermionTerm` eşdeğer olup olmadığını denetlerken da hermitian simetri kullanan daha özelleştirilmiş tür kullanarak terimleri dizinliyoruz.

Birkaç tanım örnek oluşturmamıza izin verin.
Hamiltonian $ \hat{H} = a_0 ^ \dağılım a_1 + a_1 ^ \ dağılım a_0 $ değerini düşünün.
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the terms to be added.
    var fermionTerm0 = new FermionTerm(new[] { 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 0, 1 }.ToLadderSequence());

    // These fermion terms are not equal. The following Boolean is `false`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // However, these terms are equal under Hermitian symmetry.
    // We also take the opportunity to demonstrate equivalent constructors
    // for hermitian fermion terms
    var hermitianFermionTerm0 = new HermitianFermionTerm(fermionTerm0);
    var hermitianFermionTerm1 = new HermitianFermionTerm(new[] { 0, 1 });

    // These Hermitian fermion terms are equal. The following Boolean is `true`.
    var hermitianSequenceEqual = hermitianFermionTerm0 == hermitianFermionTerm1;

    // We add the terms to the Hamiltonian with the appropriate coefficient.
    // Note that these terms are identical.
    hamiltonian.Add(hermitianFermionTerm0, 1.0);
    hamiltonian.Add(hermitianFermionTerm1, 1.0);
```
Hamiltonian işleçleri hermitian işleçleri olan olguyu kullanarak bu oluşturmayı basitleştirebiliriz.
Kullanılarak Hamiltonian 'e terim eklenirken, gibi `Add` hermitian olmayan herhangi bir terim, `fermionTerm0` hermitian eşleniği ile eşleştirilmek üzere varsayılır.
Bu nedenle, aşağıdaki kod parçacığı aynı Hamiltonian 'yi de temsil eder:
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

Anti-commutation kurallarını kullanarak `FermionTerm` Hamiltonian içindeki bazı örnekler, bazen eksi işaretine kadar, her zaman aynı fermıonic işleçleri dizisine karşılık gelir.
Örneğin, yukarıda oluşturulan koşulların toplamı olan Hamiltonian $H = a_0 ^ \ortager a_1 ^ \ortager a_1 a_0-a_1 ^ \ortager a_0 ^ \gesger A_1 a_0 $2a_0 ^ \dağılım A_1 ^ \dağılım A_1 a_0 $ ' i düşünün.
Her zaman, bunların eşdeğer şartlar gibi kullanıcılara açık olmaz ve bu nedenle ayrıca Hamiltonian 'e ayrı olarak eklenebilir.
Alternatif olarak, birisi Hamiltonian 'de zaten var olan terimleri değiştirmek isteyebilir.
Bu durumlarda, eşdeğer terimleri aşağıdaki gibi birleştirebiliriz.
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We now create two Hermitian fermion terms that are equivalent with respect to
    // anti-commutation and Hermitian symmetry.
    var terms = new[] {
        (new[] { 0, 1, 1, 0 }, 1.0),
        (new[] { 1, 0, 1, 0 }, 1.0) }
    .Select(o => (new HermitianFermionTerm(o.Item1.ToLadderSequence()), o.Item2.ToDoubleCoeff()));

    // Now add `terms` to the Hamiltonian.
    hamiltonian.AddRange(terms);

    // There is only one unique term. `nTerms == 1` is `true`.
    var nTerms = hamiltonian.CountTerms();
```
Denk terimlerin katsayılarını birleştirerek Hamiltonian içindeki toplam terim sayısını azalttık.
Daha sonra, bu, Hamiltonian benzetimi için gereken hisse kapıları sayısını azaltır.

### <a name="internal-representation"></a>İç Gösterim

Tek ve iki boyutlu etkileşimleri olan bir Fermionic Hamiltonian, şu şekilde ikinci quantitik gösterimde temsil edilir

$ $ \begin{hizalaması} H = \sum \_ {PQ} h \_ {PQ} a ^ \dağılım { \_ p} a \_ {q} + \frac {1} {2} \sum \_ {pqrs} H \_ {pqrs} a ^ \gesger {p} a \_ ^ \dağılım {q \_ \_ \_ } a {r} a {s}.
\end{hizalaması} $ $

Bu gösterimde, en çok $N ^ 2 + N ^ 4 $ katsayılar vardır.
Ancak, bu katsayıların birçoğu aynı işlece karşılık geldiği için toplanabilir.
Örneğin, burada $p, q, r, s $ farklı dizinlerdir, şunları göstermek için anti-commutation kurallarını kullanabiliriz: $ $ a ^ \dağılım \_ {p} a ^ \dağılım {q} a {r} a \_ \_ \_ {s} =-a ^ \dağılım \_ {q} a ^ \dağılım \_ {p} a {r} a \_ \_ {s} =-a ^ \dağılım {p} a ^ \_ \dağılım { \_ q} a { \_ s} a \_ {r} = a ^ \hanger {q} a \_ ^ \dağılım \_ {p \_ \_ } a {s} a {r}.
$$

Ayrıca, $H $ olduğu gibi, hermitian fermıonic işlecinin her birinde $h \_ {pqrs} bir ^ \leger { \_ p}, bir ^ \dağılım {q} a {r} a { \_ \_ \_ s} $, $H $ içinde de bulunan bir hermitian eşleniği vardır. Bu symmetries tarafından nitelenen terim gruplarını benzersiz bir şekilde indekslemek için, dizinler $ (i 1) üzerinde kurallı bir sıralama tanımladık. \_ \cnoktalar, ı \_ n, j \_ 1, \cnoktalar, j \_ m) $ herhangi bir dizi $n + m $ fermıonic işleci $a ^ \hanger \_ {i \_ 1} \cnoktalar a ^ \dağılım {i \_ \_ n} a \_ {j \_ 1} \cnoktalar a \_ {j \_ m} $as aşağıda verilmiştir:
-   ^ \Hanger \_ {i \_ \cdot} $ $a tüm oluşturma işleçleri, tüm fihilatıon işleçleri \_ {j \_ \ cdot} $ $a önce yerleştirildi.
-   Tüm oluşturma işleci dizinleri artan düzende sıralanır; bu $i \_ 1< ı \_ 2< \cnoktalar < i \_ n $ olur.
-   Tüm Ayla ilgili işleç dizinleri, $j \_ 1> j \_ 2 \cnoktalarla > j e $ $) olarak azalan düzende sıralanır \_ .
-   En soldaki Dizin, en çok dizinden daha küçüktür veya eşittir, bu $i \_ 1 \ Le j \_ e $ ' dır.

Bu kurallı sıralı dizin kümesini $ $ \begin{hizalaması} (i \_ 1, \cnoktalar, ı \_ n, j \_ 1, \cnoktalar, j \_ m) \ in S \_ {n, m} olarak tanımlamamıza izin verin.
\end{hizalaması} $ $

Bu kurallı sıralamada, fermıonic Hamiltonian, $ $ \begin{hizalaması} H = \sum {(p) olarak ifade edilebilir. \_ q) \in S \_ {1,1} } H ' \_ {PQ} \frac{a ^ \hanger { \_ p} a \_ {q} + a ^ \dağılım { \_ q} a \_ {p}} {2} + \ Sum \_ {(p, q, r) s) \in s \_ {2,2} } H ' \_ {pqrs} \frac{a ^ \hanger {p} a ^ \dağılım {q} a {r} a \_ \_ \_ \_ {s} + a ^ \dağılım {s} a ^ \_ \_ \_ \_ {2} \" \_ {PQ} $ ve $h ' \_ {pqrs} $ $h, sırasıyla bir {q} a {p}}, \end{hizalaması} $ $, uygun şekilde uyarıı ve iki elektron integrals.

