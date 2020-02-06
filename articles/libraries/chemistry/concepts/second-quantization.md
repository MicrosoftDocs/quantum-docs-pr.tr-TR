---
title: İkinci Quantileştirme | Microsoft Docs
description: İkinci Quantileştirme kavramsal belgeleri
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
ms.openlocfilehash: 4b7b5a6be6d0c1f3520128609e6b9fa83e5460d5
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036432"
---
# <a name="second-quantization"></a>İkinci Quantitleştirme

İkinci quantileştirme, farklı bir lens aracılığıyla elektronik yapı sorununa bakar.
$N _e $ elektriklerinin her birini belirli bir duruma (veya Orbe) atamak yerine, ikinci bir ölçü her ikisi de izler ve her birinde bulunan bir elektron olup olmadığını ve aynı zamanda otomatik olarak karşılık gelen Wave işlevi.
Bu önemli bir durumdur çünkü, giriş durumunu simetrik hale getirme (fermıons için gereklidir) ve ayrıca ikinci bir satışın bu tür modellerin küçük hisse kullanımı ile simülasyonu yapmasına izin verdiği için, tchemistry modellerinin belirtilmesiyle bilgisayarlar.

İkinci bir ölçü işleme örneği olarak, $ \ psi_0 \cnoktalara \ psi_ {N-1} $ öğesinin bir dizi uzamsal Orbitals olduğunu varsayalım.
Bu Orbitals, sistemi kabul edilen sonlu bir küme içinde mümkün olduğunca doğru şekilde temsil edecek şekilde seçilir.
Bu tür yörüntünlerde yaygın bir örnek, Hydrogen atom için bir egensiz oluşturan atomik orbitünlerdir.
Elektriler iki döngü durumuna sahip olduğundan, bu tür uzamsal orbiye her biri için iki elektriklarca bulunabilir.
Yani, geçerli temel durumlar $ \ psi_ {0 biçiminde olur. \upok}, \lnoktalar, \ psi_ {N-1, \upoks}, \ psi_ {0, \downarrow}, \lnoktalar, \ psi_ {N-1, \downarrow} $ burada $ \upok $ ve $ \downok $, döndürme derecesindeki iki eigenstates belirten etiketlerdir serbestlik.
$ \Sigma \in \{\upok için $ (j, \sigma) $ öğesinin bu Birleşik dizininde, \downok\}$, hem uzamsal hem de döngü derecesi olarak depolandığı için bir döndürme-orblik olarak adlandırılır.
Kimya kitaplığında, döndürme-Orbitals `SpinOrbital` veri yapısında depolanır ve aşağıdaki gibi oluşturulur.

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

Bu, her bir indisin bir $ (j, \sigma) $ numaralandırması olduğu için, yalnızca Wave işlevinin döndürme ve uzamsal bölümünün temelini $ \ psi_{0} \cnoktalar \ psi_ {2N-1} $ olarak düşünebileceğimizi gösterir.
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
Yani, $ \ psi_1 $ as \begin{Equation} \ psi_1 \ettarrow \begin{Cases} \tus{0}_1 & \Text{If $ \ psi_1 $ boş değilse,} \\\
\ket{1}_1 & \Text{If $ \ psi_1 $ dolu.} \end{Cases} \end{Equation} bu kodlama, farklı bir ücret bit olarak elektronik meslek depolayabileceği anlamına gelir.

$2N $ $ $ $ $ $ $ $ $ $ $ $ $ $ $/bit
Örnek olarak, $N = $2 sonra durum $ $ \ayraç{0} \tus{1} \demet{1} \demet{0}, $ $

döndürme Orbitals $1 $ ve $2 $, kalan boş ile birlikte yer alar.
Benzer şekilde, $ $ \demet{0} \equıv \tus{0} _{0} \cnoktalar \demet{0}_ {N-1}, $ $

, elektriksiz değildir ve ' vakum State ' olarak bilinir.

İkinci bir sağlığa yönelik güzel bir yan etkisi, artık hisse durumunun simetriyi açıkça takip etmemiz gerekmez.
Bunun nedeni, yaptığımız gibi, bir döndürme/atma 'un elektronik mesleklerini oluşturan ve yok eden operatörlerin commutation kuralları aracılığıyla bunun yerine durumunun kendisini temsil eder.

## <a name="fermionic-operators"></a>Fermıonic işleçleri

İkinci Satışlara dayalı vektörlere uygulanan iki temel operatör, oluşturma ve Ayla ilgili işleçler olarak bilinir.
Bu işleçler, belirli bir konuma elektriler ekler veya yok eder.
Bunlar sırasıyla $a ^ \ dagger_j $ ve $a _j $ olarak gösterilir.

Örneğin, \begin{hizalaması} a ^ \ dagger_1 \ayraç{0}_1 = \ket{1}_1, \dörtlü a ^ \ dagger_1 \ayraç{1}_1 = 0, \dörtlü a_1 \ayraç{0}_1 = 0, \dörtlü A_1 \ayraç{1}_1 = \tus{0}_1.
\end{hizalaması} burada $a ^ \ dagger_1 \tus{1}_1 = 0 $ ve $a _1 \ ayraç{0}_1 $ değerini, sıfır vektörü $ \ ' a değil + _1 $ olduğunu unutmayın.{0}
Bu tür işleçler hermitian veya Unitary değildir.
<xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> türünü kullanarak genel oluşturma ve annihilasyon işleçlerini temsil ediyoruz.
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

Bu tür işleçleri de kullanarak Express $ $ \ket{0} \tus{1} \tus{1} \demet{0} = a ^ \ dagger_1 a ^ \ dagger_2 \tus{0}^ {\otimes 4} olabilir.
$ $ Bu işleç dizisi, yukarıda göz önünde bulundurulduğuna benzer bir kod kullanılarak C# Hamiltonian simülasyon kitaplığı içinde oluşturulur:
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

$K $ Fermıons sisteminin ikinci bir sistem için, {$ a ^ \ dagger_i \ket{n_1, n_2, \lnoktalar, 0_i, \lnoktalar, n_k} = (-1) ^ {S_i} \ket{n_1, n_2, \lnoktalar, 1_i tarafından verilen oluşturma dagger_i $a işlecinin eylemi , \lnoktalar, n_k}, $ $ and $ $ a ^ \ dagger_i \ket{n_1, n_2, \lnoktalar, 1_i, \lnoktalar, n_k} = 0, $ $ burada $S _i = \ sum_ {j < i} a ^ \ dagger_j a_j $, tek bir parçacık durumunda olan ve bir dizin $j < ı $ olan Fermıons toplam sayısını ölçer.

Üçüncü bir operatör de genellikle ikinci bir satışta temsilde kullanılır.
Bu işleç sayı işleci olarak bilinir ve \begin{Equation} n_i = a ^ \ dagger_i a_i tarafından tanımlanır.
\end{Equation} Bu işleç, \ Begin{hizalaması} n_i \tus{0}_i & = 0 \ olmayan\\\
n_i \tus{1}_i & = \demet{1}_i.
\end{hizalaması} yukarıdaki `FermionTerm` örneklerle benzerdir, bu sayı işleci aşağıdaki gibi oluşturulur.
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
Bu, $ $ a ^ \ dagger_2 bir ^ \ dagger_1 \ayraç{0} =-a ^ \ dagger_1 bir ^ \ dagger_2 \tus{0}anlamına gelir.
$ $ Bu tür işleçler ' Anti-commute ' ve genel olarak tüm $i j $ \ Begin{hizalaması} a ^ \ dagger_i a ^ \ dagger_j =-(1-\ delta_ {i, j}) a ^ \ dagger_j a ^ \ dagger_i, \dörtlü a ^ \ dagger_i a_j = \ delta_ {i, j}-a_j a ^ \ dagger_i.
\end{hizalaması} bu nedenle, aşağıdaki iki <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> örneği inetiçele olarak kabul edilir
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

Anti-commutation kurallarını kullanarak bazı `LadderSequence` örnekleri, bazı durumlarda eksi işaretine kadar olan fermıonic işleçleri dizisine karşılık gelir.
Örneğin, Hamiltonian $a _0 ^ \dağılım a_1 ^ \dağılım a_1 a_0 =-a_1 ^ \dağılım a_0 ^ \ dağılım A_1 a_0 $ değerini düşünün.
Bu, her `FermionTerm`için kurallı bir sıralama tanımlamamıza olanak sağlar.
Her `FermionTerm` otomatik olarak aşağıdaki gibi kurallı sırayla yerleştirilir.
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
Özellikle, $ \psı\_j $, temeli oluşturan döndürme orbitleri ise

\begin{Equation} \hat{H} = \sum\_{PQ} H\_{PQ} a ^ \hanger\_p a\_q + \frac{1}{2}\sum\_{pqrs} H\_{pqrs} a ^ \gesger\_p a ^ \dağılım\_q a\_ra\_s + H\_{\textrm NUC}, \label{EQ: Totalhemi} \end{Equation}; burada $h\_{\textrm NUC} $, Nunet enerji

\begin{hizalaması} h\_{pq} & = \int\_{-\infty} ^ \ınfty \ PSI ^\*\_p (x\_1) \left (-\frac{\nabla ^ 2}{2} + V (x\_1) \ right) \psı\_q (x\_1) \mathrm{d} ^ 3x\_1, \end{hizalaması}

Burada $V (x) $, ortalama alan potansiyeli ve

\begin{hizalaması} h\_{pqrs} & = \int\_{-\infty} ^ \inf\int\_{-\infty} ^ \infty\psı\_p ^\*(x\_1) \psi\_q ^\*(x\_2) \left (\frac{1}{| x_1-x_2 |} \right) \psı\_r (x\_2) \psı\_s (x\_1) \mathrm{d} ^ 3x\_1 \ mathrm {d} ^ 3x\_2. \ Label {EQ : integrals} \end{hizalaması}

$H\_{PQ} $ terimleri yalnızca tek bir elekons ve benzer şekilde $h\_{pqrs} $ iki elektron integralları içerdiğinden, tek bir elektron integrals olarak adlandırılır.
Bu katsayıların değerlerini hesaplamak bir integral gerektirdiğinden integrallar olarak adlandırılırlar.
Tek bir elektron terimi, bireysel elektriklerin Kinetic enerji ve nuclei 'nin elektrik alanları ile etkileşimlerini anlatmaktadır.
Diğer yandan iki elektron integrallarca, elektriler arasındaki etkileşimler açıklanır.

Bu koşulların ne anlama geldiğini, her birini oluşturan oluşturma ve dumaılasyon işleçlerinden nasıl eğilebileceği.
Örneğin, $h _ {PQ} a ^ \ dagger_p a_q $, orbili$p $ ' ı döndürme ve döndürme için bir veya daha fazla $q $ arasındaki elektron çizlemeyi açıklar.
Benzer şekilde, $h _ {pqrs} a ^ \ dagger_p a ^ \ dagger_q a_r a_s $ (ayrı $p, q, r, s $), döndürme ve $r $ ' de iki elektrikten ve $s $ ve $p $ ile sona eriyor.
$R = q $ ve $p = s $ $h _ {prrp} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = h_ {prrp} n_p N_R $, iki elektriğe yakın enerji cezası sunar, ancak bir dinamik işlemini tanımlamaz.

Bu tür Hamiltonians, aslında istenen tüm `FermionTerm` örneklerinin bulunduğu bir liste olan `FermionHamiltonian` sınıfını kullanarak temsil edebilir.
Hamiltonians hermitian as Definition olduğundan, koşulların eşit olup olmadığını denetlerken hermitian simetri kullanan `HermitianFermionTerm` daha özelleştirilmiş tür kullanarak terimleri dizinliyoruz.

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
`Add`kullanarak Hamiltonian 'e terim eklerken, `fermionTerm0` gibi tüm hermitian terimlerinin hermitian eşleniği ile eşleştirilmek üzere olduğu varsayılır.
Bu nedenle, aşağıdaki kod parçacığı aynı Hamiltonian 'yi de temsil eder:
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

Anti-commutation kurallarını kullanarak Hamiltonian içindeki bazı `FermionTerm` örnekleri, bazen eksi işaretine kadar, her zaman aynı fermıonic işleçleri dizisine karşılık gelir.
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

$ $ \begin{hizalaması} H = \sum\_{PQ} h\_{PQ} a ^ \hanger\_{p} a\_{q} + \frac{1}{2}\sum\_{pqrs} H\_{pqrs} a ^ \gesger\_{p} a ^ \dağılım\_{q} a\_{s}.\_
\end{hizalaması} $ $

Bu gösterimde, en çok $N ^ 2 + N ^ 4 $ katsayılar vardır.
Ancak, bu katsayıların birçoğu aynı işlece karşılık geldiği için toplanabilir.
Örneğin, burada $p, q, r, s $ farklı dizinlerdir, şunları göstermek için anti-commutation kurallarını kullanabiliriz: $ $ a ^ \dağılım\_{p} a ^ \dağılım\_{q} a\_{r} a\_{s} =-bir ^ \dağılım\_{q} a ^ \dağılım\_{p} a\_{r} a\_{s} =-a ^ \kama ger\_{p} a ^ \dağılım\_{q} a\_{s} bir\_{r} = bir ^ \dağılım\_{q} a ^ \dağılım\_{p}\_{s} a\_{r}.
$$

Ayrıca, $H $ olduğu gibi, hermitian fermıonic işlecinin her birinde $h\_{pqrs} bir ^ \dağılım\_{p} bir ^ \dağılım\_{q}\_{r}\_{s} $, $H $ içinde de bulunan bir hermitian eşleniği vardır. Bu symmetries tarafından nitelenen terim gruplarını benzersiz şekilde indekslemek için, dizinler $ (i\_1, \cnoktalar, ı\_n, j\_1, \cnoktalar, j\_m) $ herhangi bir dizi $n + m $ fermıonic işleci $a ^ \hanger\_{i\_1} \cnoktalar a ^ \dağılım\_{i\_n} a\_{j\_1} \cnoktalar a\_{j\_m} $as :
-   ^ \Dağılım\_{i\_\cdot} $ $a tüm oluşturma işleçleri, tüm annıılasyon işleçleri $a\_{j\_\cdot} $ öğesinden önce yerleştirildi.
-   Tüm oluşturma işleci dizinleri artan düzende sıralanır; bu $i\_1 < ı\_2 < \cnoktalar < ı\_n $.
-   Tüm Ayla ilgili işleç dizinleri azalan düzende sıralanır; bu $j\_1 > j\_2 \ cnoktalar > j\_d $ olur.
-   En soldaki Dizin, en sağdaki dizinden daha küçüktür veya eşittir, bu $i\_1 \ Le j\_d $.

Bu kurallı sıralı dizin kümesini $ $ \begin{hizalaması} (i\_1, \cnoktalar, ı\_n, j\_1, \cnoktalar, j\_m) \ '\_{n, m} olarak tanımmıza izin verin.
\end{hizalaması} $ $

Bu kurallı sıralamada, fermıonic Hamiltonian, $ $ \begin{hizalaması} H = \sum\_{(p, q) \in S\_{1,1}} H '\_{PQ} \frac{a ^ \hanger\_{p} a\_{q} + bir ^ \dağılım\_{q} a\_{p}}{2}+ \ Sum\_{(p, s, r, s) \in S\_{2,2}} H '\_{pqrs} \frac{a ^ \gesger\_{p} a ^ \dağılım\_{q} a\_{r} a\_{s} + a ^ \dağılım\_{s} a ^ \ dağılım\_{r} bir\_{q} a\_{p}}{2}, \end{hizalaması} $ $, tek ve iki elektron integrals $h '\_{PQ} $ ve $h '\_{pqrs} $, sırasıyla.

