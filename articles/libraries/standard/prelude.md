---
title: QDK 'deki iç işlemler ve işlevler
description: Klasik işlevler ve Unitary, döndürme ve ölçüm işlemleri dahil olmak üzere QDK 'deki iç işlemler ve işlevler hakkında bilgi edinin.
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b1c26c632f36b6c254d940a89b13638f7592ab80
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907214"
---
# <a name="the-prelude"></a>Prelude dili #

H#development Kit 'e dahil edilen Q # derleyicisi ve hedef makineler, Q # ' da hisse programları yazılırken kullanılabilecek bir dizi iç işlev ve işlem sağlar.

## <a name="intrinsic-operations-and-functions"></a>İç Işlemler ve Işlevler ##

Standart kitaplıkta tanımlanan iç işlemler kabaca birkaç kategoriden birine girer:

- <xref:microsoft.quantum.core> ad alanında toplanan, önemli klasik işlevler.
- [Clienfford ve $T $ Gates 'ten oluşan unitfıerlerini](xref:microsoft.quantum.concepts.qubit)temsil eden işlemler.
- Çeşitli işleçlerle ilgili döndürmeler temsil eden işlemler.
- Ölçümleri uygulayan işlemler.

Clienfford + $T $ Gate kümesi, hisse bilgi işlem için [evrensel](xref:microsoft.quantum.concepts.multiple-qubits) olduğundan, bu işlemler, eksik küçük bir hata içinde yaklaşık bir hisse algoritması uygulamak için yeterli olacaktır.
Q #, tek qubit Unitary ve CNOT Gate kitaplığı içinde çalışmasına izin verir. Bu kitaplık, programcının Clienfford + $T $ ayrıştırma 'yı doğrudan hızlı bir şekilde ifade ettiğinden ve tek qubit birimlere Clienfford ve $T $ Gates 'e (daha fazla bilgi için bkz. [buraya](xref:microsoft.quantum.more-information) bakın) yönelik yüksek verimli yöntemler içerdiğinden düşünmek çok daha kolay.

Mümkün olduğunda, daha önce, qubitlerdeki, hedef makinenin uygun Ayrıştırma işlemini gerçekleştirmesini sağlayan, `Controlled` türevini uygulamaya izin veren bir işlem.

Prelude 'nun bu bölümünde tanımlanan işlevlerin ve işlemlerin birçoğu @"microsoft.quantum.intrinsic" ad alanıdır. bu nedenle, çoğu Q # kaynak dosyası ilk ad alanı bildiriminden hemen sonra bir `open Microsoft.Quantum.Intrinsic;` yönergesine sahip olur.
<xref:microsoft.quantum.core> ad alanı otomatik olarak açılır, böylece <xref:microsoft.quantum.core.length> gibi işlevlerin hiç bir `open` açıklaması olmadan kullanılabilmesi için.

### <a name="common-single-qubit-unitary-operations"></a>Yaygın tek qubit Unitary Işlemleri ###

Prelude, birçok yaygın [tek qubit işlemini](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)de tanımlar.
Bu işlemlerin tümü hem `Controlled` hem de `Adjoint` funlarına izin verir.

#### <a name="pauli-operators"></a>Pauli Işleçleri ####

<xref:microsoft.quantum.intrinsic.x> işlemi Pauli $X $ işlecini uygular.
Bu, bazen `NOT` kapısı olarak da bilinir.
İmza `(Qubit => Unit is Adj + Ctl)`vardır.
Tek qubit Unitary öğesine karşılık gelir:

\begin{Equation} \begin{bmatrix} 0 & 1 \\\\% FIXME: Bu şu anda quadwhack Hack 'ı kullanıyor.
1 & 0 \ End{bmatrix} \end{Equation}

<xref:microsoft.quantum.intrinsic.y> işlemi Pauli $Y $ işlecini uygular.
İmza `(Qubit => Unit is Adj + Ctl)`vardır.
Tek qubit Unitary öğesine karşılık gelir:

\begin{Equation} \begin{bmatrix} 0 &-ı \\\\% FIXME: Bu şu anda quadwhack Hack 'ı kullanıyor.
ı & 0 \ End{bmatrix} \end{Equation}

<xref:microsoft.quantum.intrinsic.z> işlemi Pauli $Z $ işlecini uygular.
İmza `(Qubit => Unit is Adj + Ctl)`vardır.
Tek qubit Unitary öğesine karşılık gelir:

\begin{Equation} \begin{bmatrix} 1 & 0 \\\\% FIXME: Bu şu anda quadwhack Hack 'ı kullanıyor.
0 &-1 \end{bmatrix} \end{Equation}

Aşağıda [Bloch Sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) ile eşleştirilmiş olan bu dönüşümleri görtik (her durumda döndürme ekseni kırmızı vurgulanır):

![Bloch sphere üzerine eşlenmiş Pauli işlemleri](~/media/prelude_pauliBloch.png)

Aynı Pauli Gate 'in aynı qubit 'e iki kez uygulanması işlemi iptal eder (bundan böyle, daha sonra başlangıç noktasına geri dönerek, bir 2π (360 °) yüzeyi üzerinde tam bir döndürme gerçekleştirdiniz. Bu, bize aşağıdaki kimliğe getirir:

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \ cıvabitti $ $

Bu, Bloch Sphere üzerinde görselleştirmelere neden olabilir:

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>Diğer tek qubit Clienffords ####

<xref:microsoft.quantum.intrinsic.h> işlemi Hadamard geçidini uygular.
Bu, $H \ket{0} = \ket{+} \mathrel{: =} (\tus{0} + \ket{1})/\sqrt{2}$ ve $H \ket{+} = \tus{0}$ gibi hedef qubit 'in Pauli $X $ ve $Z $ eksenlerini birbirine dönüştürür.
İmza `(Qubit => Unit is Adj + Ctl)`vardır ve tek-qubit Unitary öğesine karşılık gelir:

\begin{Equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\% FIXME: Bu şu anda quadwhack Hack 'ı kullanıyor.
1 &-1 \end{bmatrix} \end{Equation}

Hadamard geçidi, $ \ket{0}$ ve $ \demet{1}$ durumlarının bir üst konumunu oluşturmak için kullanılabilmesi amacıyla özellikle önemlidir. Bloch Sphere gösteriminde, $ \ Pi $ radyan ($ 180 ^ \circ $) x ekseni etrafında $ \ket{\psı} $ öğesinin bir dönüşü olarak düşünmek en kolay yoldur. Bu, x/pi/2 $ radyanlara ($ 90 ^ \circ $) göre y ekseni etrafında (saat yönünde) bir döndürme işlemi izlemelidir:

![Hadamard işlemi Bloch sphere üzerine eşlendi](~/media/prelude_hadamardBloch.png)

<xref:microsoft.quantum.intrinsic.s> işlemi, $S $ aşama kapısını uygular.
Bu, Pauli $Z $ işleminin matris kare köküdür.
Yani, $S ^ 2 = Z $.
İmza `(Qubit => Unit is Adj + Ctl)`vardır ve tek-qubit Unitary öğesine karşılık gelir:

\begin{Equation} \begin{bmatrix} 1 & 0 \\\\% FIXME: Bu şu anda quadwhack Hack 'ı kullanıyor.
0 & ı \end{bmatrix} \end{Equation}

#### <a name="rotations"></a>Döndürmelerini ####

Yukarıdaki Pauli ve Clifford işlemlerine ek olarak, Q # Prelude, döndürmeler ifade etmenin çeşitli yollarını sunmaktadır.
[Tek qubit işlemlerinde](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)açıklandığı gibi, döndürme özelliği, hisse algoritması için kritik öneme sahiptir.

$H $ ve $T $ kapıları kullanarak herhangi bir tek qubit işlemi hızlı bir şekilde ifade edebiliyoruz; $H burada \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\\\% FIXME: Bu şu anda dörtlü geri Whack Hack 'ı kullanıyor.
0 & e ^ {i \ Pi/4} \end{bmatrix} \end{Equation} bu, <xref:microsoft.quantum.intrinsic.s> işleminin (^ 2 = S $ $T) kare köküdür.
$T $ Gate <xref:microsoft.quantum.intrinsic.t> işlemi tarafından uygulanır ve tek bir-qubit üzerinde bir Unitary işlemi olduğunu belirten imzaya `(Qubit => Unit is Adj + Ctl)`.

Bu, herhangi bir rastgele tek qubit işlemi açıklamaya yetecek olsa da, farklı hedef makineler Pauli işleçleri hakkında daha verimli temsiller olabilir. bu nedenle, Prelude 'un yarışmasını sağlamanın çeşitli yollarını içerir. Bu tür döndürmeler.
Bunların en temel değeri, belirtilen Pauli ekseninin etrafında bir döndürme uygulayan <xref:microsoft.quantum.intrinsic.r> işlemidir. \begin{Equation} R (\sigma, \fi) \mathrel{: =} \exp (-i \phi \ Sigma/2), \end{Equation}; burada $ \sigma $ bir Pauli işleci, $ \phi $ bir açı ve $ \exp $, matris üstel değerini temsil eder.
Girişin ilk iki bölümünün, Unitary işleci $R (\sigma, \fi) belirtmek için gereken klasik bağımsız değişkenleri $ \sigma $ ve $ \phi $ ' ı gösterdiği imzaya `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`.
Türü tek qubit Unitary olan bir işlem elde etmek için $ \sigma $ ve $ \phi $ öğesini kısmen uygulayabiliriz.
Örneğin, `R(PauliZ, PI() / 4, _)` `(Qubit => Unit is Adj + Ctl)`türü vardır.

> [!NOTE]
> <xref:microsoft.quantum.intrinsic.r> işlemi giriş açısını 2 ' ye böler ve-1 ile çarpar.
> $Z $ döndürmeler için bu, $ \ket{0}$ eigenstate 'in $-\phi/$2 ile döndürüldüğü ve $ \ket{1}$ eigenstate $ \phi/$2 tarafından döndürüldüğü anlamına gelir. böylece $ \ket{1}$ eigenstate $ \ket $ ' i $ \tus{0}$ eigenstate ile göreli $ \phi $ tarafından döndürülür.
>
> Özellikle bu, `T` ve `R(PauliZ, PI() / 8, _)` yalnızca ilgisiz [küresel bir aşamaya](xref:microsoft.quantum.glossary#global-phase)göre farklılık gösterir.
> Bu nedenle $T $, bazen $ \frac{\pi}{8}$-Gate olarak bilinir.
>
> Ayrıca, `PauliI` etrafında döndürmesinin yalnızca $ \phi/$2 küresel bir aşamasını uygulayacağını unutmayın. Bu tür aşamalar ilgisizdir, [kavramsal belgelerde](xref:microsoft.quantum.concepts.qubit)belirtildiği gibi, denetlenen `PauliI` döndürmeler için de uygundur.

Hisse algoritmaları dahilinde, her zaman {\phi = \pi k/2 ^ n $ for \mathbb{Z} $ ve \mathbb{N} $ içinde $n \ $ adlı bazı $k \jyadic kesirleri olarak ifade etmek yararlı olur.
<xref:microsoft.quantum.intrinsic.rfrac> işlemi, bu kuralı kullanarak belirtilen Pauli ekseninin etrafında bir döndürme uygular.
Döndürme açısının, dyadic kesri olarak yorumlanan `Int`türünde iki giriş olarak belirtildiğinden <xref:microsoft.quantum.intrinsic.r> farklıdır.
Bu nedenle `RFrac` imza `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`vardır.
Tek qubit Unitary $ \ exp (i \pı k \ Sigma/2 ^ n) $, burada $ \sigma $ ilk bağımsız değişkene karşılık gelen Pauli matrisi, $k $ ikinci bağımsız değişkendir ve $n $ üçüncü bağımsız değişkendir.
`RFrac(_,k,n,_)`, `R(_,-πk/2^n,_)`ile aynıdır; açının kesirin *negatifi* olduğunu unutmayın.

<xref:microsoft.quantum.intrinsic.rx> işlemi Pauli $X $ ekseninin etrafında bir döndürme uygular.
İmza `((Double, Qubit) => Unit is Adj + Ctl)`vardır.
`Rx(_, _)`, `R(PauliX, _, _)`ile aynıdır.

<xref:microsoft.quantum.intrinsic.ry> işlemi Pauli $Y $ ekseninin etrafında bir döndürme uygular.
İmza `((Double, Qubit) => Unit is Adj + Ctl)`vardır.
`Ry(_, _)`, `R(PauliY,_ , _)`ile aynıdır.

<xref:microsoft.quantum.intrinsic.rz> işlemi Pauli $Z $ ekseninin etrafında bir döndürme uygular.
İmza `((Double, Qubit) => Unit is Adj + Ctl)`vardır.
`Rz(_, _)`, `R(PauliZ, _, _)`ile aynıdır.

<xref:microsoft.quantum.intrinsic.r1> işlemi, $Z $ $-$1 eigenstate $ \tus{1}$ etrafında verilen miktar boyunca bir döndürme uygular.
İmza `((Double, Qubit) => Unit is Adj + Ctl)`vardır.
`R1(phi,_)`, `R(PauliZ,phi,_)` ardından `R(PauliI,-phi,_)`ile aynıdır.

<xref:microsoft.quantum.intrinsic.r1frac> işlemi, Z = 1 eigenstate etrafında verilen miktarda kesirli bir döndürme uygular.
İmza `((Int,Int, Qubit) => Unit is Adj + Ctl)`vardır.
`R1Frac(k,n,_)`, `RFrac(PauliZ,-k.n+1,_)` ardından `RFrac(PauliI,k,n+1,_)`ile aynıdır.

Bloch sphere üzerine eşlenmiş bir döndürme işlemi (Bu örnekteki Pauli $Z $ ekseni etrafında) örneği aşağıda gösterilmektedir:

![Bloch sphere üzerine eşlenen döndürme işlemi](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>Multi-Qubitoperations ####

Yukarıdaki tek qubit işlemlerine ek olarak, Prelude birçok multi-qubit işlemini de tanımlar.

İlk olarak, <xref:microsoft.quantum.intrinsic.cnot> işlemi standart denetlenen-`NOT` kapısı, \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 0 \\1 \\ 0 & End{bmatrix} gerçekleştirir.
\end{Equation}, iki bireysel qubit üzerinde $ \operatorname{CNOT} $ davranır unitarily öğesini temsil eden imzaya `((Qubit, Qubit) => Unit is Adj + Ctl)`sahiptir.
`CNOT(q1, q2)`, `(Controlled X)([q1], q2)`ile aynıdır.
`Controlled` functor, bir yazmaç üzerinde denetim için izin verdiğinden, yalnızca bir denetim isteytiğimiz olduğunu göstermek için `[q1]` dizi değişmez değeri kullanırız.

<xref:microsoft.quantum.intrinsic.ccnot> işlem, bazen Toffoli kapısı olarak da bilinen, düzgün şekilde denetlenen bir ağ geçidi gerçekleştirir.
İmza `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`vardır.
`CCNOT(q1, q2, q3)`, `(Controlled X)([q1, q2], q3)`ile aynıdır.

<xref:microsoft.quantum.intrinsic.swap> işlemi, iki qubit 'in hisse durumlarının sayısını değiştirir.
Diğer bir deyişle, Unitary matrisi \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix} uygular.
\end{Equation} `((Qubit, Qubit) => Unit is Adj + Ctl)`imza içeriyor.
`SWAP(q1,q2)`, `CNOT(q1, q2)` ardından `CNOT(q2, q1)` ve ardından `CNOT(q1, q2)`eşdeğerdir.

> [!NOTE]
> TAKAS kapısı, türü `Qubit[]`olan bir değişkenin öğelerinin yeniden düzenleme işlemiyle aynı *değil* .
> `SWAP(q1, q2)` uygulamak, `q1` ve `q2`tarafından başvurulan qubit durumunda bir değişikliğe neden olur, `let swappedRegister = [q2, q1];` yalnızca bu qubits 'e başvurduğumuz şekilde etkiler.
> Ayrıca, `(Controlled SWAP)([q0], (q1, q2))`, `SWAP` bir üçüncü qubit durumunda koşullu olmasını sağlar ve öğeleri yeniden düzenleyerek temsil eteceğiz.
> Fredkabağı kapısı olarak da bilinen denetimli-takas kapısı, tüm klasik hesaplamayı dahil etmek için yeterince güçlüdür.

Son olarak, Prelude, Multi-qubit Pauli işleçlerinin üslerini temsil eden iki işlem sağlar.
<xref:microsoft.quantum.intrinsic.exp> işlemi, Multi-qubit Unitary \begin{Equation} \operatorname{Exp} (\vec{\sigma}, \fi) \mathrel{: =} \exp\left (i \fi \ sigma_0 \otimes \ sigma_1 \otimes \cnoktalar \otimes \ sigma_n \right), \end{Equation}; burada $ \vec{\sigma} = (\ sigma_0, \ sigma_1, \noktalar, \ sigma_n) $ bir tek qubit Pauli işleçleri dizisi ve $ \phi $ bir açı.
`Exp` döndürme $ \vec{\sigma} $ öğesini, imza `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`olması gibi `Pauli` öğelerinin bir dizisi olarak temsil eder.

<xref:microsoft.quantum.intrinsic.expfrac> işlemi, yukarıda açıklanan dyadic kesir gösterimini kullanarak aynı dönüşü gerçekleştirir.
İmza `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`vardır.

> [!WARNING]
> Pauli işleçleri için tencursor ürünlerinin üs öğeleri Pauli işleçleri 'nin üsünlerinin, tencursor ürünleriyle aynı değildir.
> Yani, $e ^ {i (Z \otimes Z) \phi} \ne e ^ {i Z \ Phi} \otimes e ^ {i Z \ Phi} $.

### <a name="measurements"></a>Ölçümler ###

Ölçme sırasında, ölçülen işlecin + 1 eigenvalue değeri bir `Zero` sonucuna ve-1 eigenvalue değerini `One` sonucuna karşılık gelir.

> [!NOTE]
> Bu kural tek görünebilir, ancak bu iki avantaja sahiptir.
> İlk olarak, sonucu $ \ket{0}$ `Result` değer `Zero`temsil eder, ancak $ \ket{1}$, `One`öğesine karşılık gelir.
> İkinci olarak, bir sonuca karşılık gelen eigenvalue $ \lambda $ $r $ $ \lambda = (-1) ^ r $ olduğunu yazalım.

Ölçüm işlemleri `Adjoint` ne de `Controlled` functor 'ı destekler.

<xref:microsoft.quantum.intrinsic.measure> işlemi, belirtilen Pauli işleçleri üründe bir veya daha fazla qubits 'in Birleşik ölçüsünü gerçekleştirir.
Pauli Array ve qubit dizisi farklı uzunluklardır, işlem başarısız olur.
`Measure` imza `((Pauli[], Qubit[]) => Result)`sahip.

Bir eklem ölçüsünün her bir qubit ayrı ayrı ölçüyle aynı olmadığına unutmayın.
Örneğin, $ \ket{11} = \ayraç{1} \otimes \ayraç{1} = X\otimes X \tus{00}$ durumunu göz önünde bulundurun.
$Z _0 $ ve $Z _1 $ her biri ayrı ayrı, $r _0 = $1 ve $r _1 = $1 sonucunu elde ediyoruz.
$Z _0 Z_1 $, ancak $ \ket{11}$ değerinin pozitif olduğunu belirten _ {\textrm{Joint}} = $0 adlı tek bir $r sonuç elde ediyoruz.
Farklı, $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{Joint}}) $.
Kritik olarak, *yalnızca* bu ölçüden eşlik öğrendiğimiz için, pozitif eşlik 'nın 2 2-qubit durumları, $ \ket{00}$ ve $ \tus{11}$ arasındaki üst konumda temsil edilen tüm hisse bilgileri korunur.
Hata düzeltmesini tartıştığımız için bu özellik daha sonra temel alınacaktır.

Kolaylık sağlaması için, Prelude, qubits 'i ölçmek için iki diğer işlem de sağlar.
Birincisi, tek qubit ölçümleri gerçekleştirirken oldukça yaygın olduğundan, Prelude bu durum için bir toplu değer tanımlar.
<xref:microsoft.quantum.intrinsic.m> işlemi, Pauli $Z $ işlecini tek bir qubit üzerinde ölçer ve imza `(Qubit => Result)`içeriyor.
`M(q)` `Measure([PauliZ], [q])`eşdeğerdir.

<xref:microsoft.quantum.measurement.multim>, her bir qubit için elde edilen `Result` değerlerinin *dizisini* döndüren her bir qubit dizisinin her birinde pauli $Z $ işlecini *ayrı olarak* ölçer.
Bazı durumlarda bu, iyileştirilebilir. İmza (`Qubit[] => Result[])`.
`MultiM(qs)` eşittir:

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a>Uzantı Işlevleri ve Işlemler ##

Ayrıca, Prelude, Q # kodu içinde kullanılmak üzere .NET düzeyinde zengin bir matematik ve tür dönüştürme işlevleri tanımlar.
Örneğin, <xref:microsoft.quantum.extensions.math> ad alanı <xref:microsoft.quantum.extensions.math.sin> ve <xref:microsoft.quantum.extensions.math.log>gibi yararlı işlemleri tanımlar.
Hisse geliştirme seti tarafından sunulan uygulama klasik .NET temel sınıf kitaplığını kullanır ve bu nedenle hisse programları ve bunların klasik sürücüleri arasında ek bir iletişim gidiş gelişmesi içerebilir.
Bu, yerel simülatör için bir sorun sunmadığından, bir hedef makine olarak uzak simülatör veya gerçek donanım kullanılırken bir performans sorunu olabilir.
Yani, tek bir hedef makine, bu işlemleri söz konusu sistem için daha verimli olan sürümlerle geçersiz kılarak bu performans etkisini hafifletmeyebilir.

### <a name="math"></a>Tiğin ###

<xref:microsoft.quantum.extensions.math> ad alanı, .NET temel sınıf kitaplığının [`System.Math` sınıfından](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1)birçok yararlı işlev sağlar.
Bu işlevler, diğer tüm Q # işlevleriyle aynı şekilde kullanılabilir:

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

.NET statik yönteminin bağımsız değişkenlerinin türüne göre aşırı yüklendiği yerlerde, karşılık gelen Q # işlevine, girişinin türünü gösteren bir sonek ile açıklama eklenir:

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>Bit düzeyinde Işlemler ###

Son olarak, <xref:microsoft.quantum.extensions.bitwise> ad alanı, bit düzeyinde işleçler aracılığıyla tamsayıları işlemek için çeşitli yararlı işlevler sağlar.
Örneğin, <xref:microsoft.quantum.extensions.bitwise.parity> bir tamsayının bit düzeyinde eşlik sayısını başka bir tamsayı olarak döndürür.
