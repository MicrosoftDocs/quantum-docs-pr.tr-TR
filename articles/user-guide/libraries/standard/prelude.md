---
title: QDK 'deki iç işlemler ve işlevler
description: Klasik işlevler ve Unitary, döndürme ve ölçüm işlemleri dahil olmak üzere QDK 'deki iç işlemler ve işlevler hakkında bilgi edinin.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.libraries.standard.prelude
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6ed5b1677a204b9425f229a3ea0855bb789f3f75
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857198"
---
# <a name="the-prelude"></a>Prelude dili #

Q#Hisse geliştirme paketine dahil edilen derleyici ve hedef makineler, ' de hisse programları yazılırken kullanılabilecek bir dizi iç işlev ve işlem sağlar Q# .

## <a name="intrinsic-operations-and-functions"></a>İç Işlemler ve Işlevler ##

Standart kitaplıkta tanımlanan iç işlemler kabaca birkaç kategoriden birine girer:

- Ad alanında toplanan, önemli klasik işlevler <xref:Microsoft.Quantum.Core> .
- [Clienfford ve $T $ Gates 'ten oluşan unitfıerlerini](xref:microsoft.quantum.concepts.qubit)temsil eden işlemler.
- Çeşitli işleçlerle ilgili döndürmeler temsil eden işlemler.
- Ölçümleri uygulayan işlemler.

Clienfford + $T $ Gate kümesi, hisse bilgi işlem için [evrensel](xref:microsoft.quantum.concepts.multiple-qubits) olduğundan, bu işlemler, eksik küçük bir hata içinde yaklaşık bir hisse algoritması uygulamak için yeterli olacaktır.
Rosalar da sunarak, Q# Programcının tek qubit Unitary ve CNOT kapısı kitaplığı içinde çalışmasına izin verir. Bu kitaplık, programcının Clienfford + $T $ ayrıştırma 'yı doğrudan hızlı bir şekilde ifade ettiğinden ve tek qubit birimlere Clienfford ve $T $ Gates 'e (daha fazla bilgi için bkz. [buraya](xref:microsoft.quantum.more-information) bakın) yönelik yüksek verimli yöntemler içerdiğinden düşünmek çok daha kolay.

Mümkün olduğu durumlarda, ilgeler üzerinde işlem yapan ve `Controlled` hedef makinenin uygun Ayrıştırma işlemini gerçekleştirmesini sağlayan, bu, ilgeler 'yi uygulamaya izin veren bir işlem.

Prelude 'nun bu bölümünde tanımlanan işlevlerin ve işlemlerin birçoğu @"microsoft.quantum.intrinsic" ad alanında, çoğu Q# kaynak dosyanın `open Microsoft.Quantum.Intrinsic;` ilk ad alanı bildiriminden hemen sonra gelen bir yönergesi olacaktır.
<xref:Microsoft.Quantum.Core>Ad alanı otomatik olarak açılır, böylece gibi işlevler <xref:Microsoft.Quantum.Core.Length> hiç bir beyan olmadan kullanılabilir `open` .

### <a name="common-single-qubit-unitary-operations"></a>Ortak Single-Qubit Unitary Işlemleri ###

Prelude, birçok yaygın [tek qubit işlemini](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)de tanımlar.
Bu işlemlerin tümü hem `Controlled` hem de `Adjoint` funlarına izin verir.

#### <a name="pauli-operators"></a>Pauli Işleçleri ####

<xref:Microsoft.Quantum.Intrinsic.X>Işlem Pauli $X $ işlecini uygular.
Bu, bazen ağ geçidi olarak da bilinir `NOT` .
İmza içeriyor `(Qubit => Unit is Adj + Ctl)` .
Tek qubit Unitary öğesine karşılık gelir:

\begin{Equation} \begin{bmatrix} 0 & 1 \\ \\ % fixme: Bu şu anda quadwhack Hack 'ı kullanıyor.
1 & 0 \ End{bmatrix} \end{Equation}

<xref:Microsoft.Quantum.Intrinsic.Y>Işlem Pauli $Y $ işlecini uygular.
İmza içeriyor `(Qubit => Unit is Adj + Ctl)` .
Tek qubit Unitary öğesine karşılık gelir:

\begin{Equation} \begin{bmatrix} 0 &-ı \\ \\ % fixme: Bu şu anda quadwhack Hack 'ı kullanıyor.
ı & 0 \ End{bmatrix} \end{Equation}

<xref:Microsoft.Quantum.Intrinsic.Z>Işlem Pauli $Z $ işlecini uygular.
İmza içeriyor `(Qubit => Unit is Adj + Ctl)` .
Tek qubit Unitary öğesine karşılık gelir:

\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % fixme: Bu şu anda quadwhack Hack 'ı kullanıyor.
0 &-1 \end{bmatrix} \end{Equation}

Aşağıda [Bloch Sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) ile eşleştirilmiş olan bu dönüşümleri görtik (her durumda döndürme ekseni kırmızı vurgulanır):

![Bloch sphere üzerine eşlenmiş Pauli işlemleri](~/media/prelude_pauliBloch.png)

Aynı Pauli Gate 'in aynı qubit 'e iki kez uygulanması işlemi iptal eder (bundan böyle, daha sonra başlangıç noktasına geri dönerek, bir 2π (360 °) yüzeyi üzerinde tam bir döndürme gerçekleştirdiniz. Bu, bize aşağıdaki kimliğe getirir:

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \ cıvabitti $ $

Bu, Bloch Sphere üzerinde görselleştirmelere neden olabilir:

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>Diğer Single-Qubit Clienffords ####

<xref:Microsoft.Quantum.Intrinsic.H>Işlem Hadamard geçidini uygular.
Bu, hedef qubit 'in Pauli $X $ ve $Z $ eksenlerinin $H {0} \tus= \ket{+} \mathrel{: =} ( {0} \tus+ \ket {1} )/\sqrt {2} $ ve $H \ket{+} = \ket {0} $ olduğunu birbirine dönüştürür.
İmzaya sahiptir `(Qubit => Unit is Adj + Ctl)` ve tek qubit Unitary öğesine karşılık gelir:

\begin{Equation} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ % fixme: Bu şu anda quadwhack Hack 'ı kullanıyor.
1 &-1 \end{bmatrix} \end{Equation}

Hadamard geçidi, $ \ket {0} $ ve $ \ket $ durumlarının bir üst konumunu oluşturmak için kullanılabilir {1} . Bloch Sphere gösteriminde, $ \ Pi $ radyan ($ 180 ^ \circ $) x ekseni etrafında $ \ket{\psı} $ öğesinin bir dönüşü olarak düşünmek en kolay yoldur. Bu, x/pi/2 $ radyanlara ($ 90 ^ \circ $) göre y ekseni etrafında (saat yönünde) bir döndürme işlemi izlemelidir:

![Hadamard işlemi Bloch sphere üzerine eşlendi](~/media/prelude_hadamardBloch.png)

<xref:Microsoft.Quantum.Intrinsic.S>İşlem, $S $ aşama kapısını uygular.
Bu, Pauli $Z $ işleminin matris kare köküdür.
Yani, $S ^ 2 = Z $.
İmzaya sahiptir `(Qubit => Unit is Adj + Ctl)` ve tek qubit Unitary öğesine karşılık gelir:

\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % fixme: Bu şu anda quadwhack Hack 'ı kullanıyor.
0 & ı \end{bmatrix} \end{Equation}

#### <a name="rotations"></a>Rotasyonlar ####

Yukarıdaki Pauli ve Clifford işlemlerine ek olarak, Q# Prelude, döndürmeler ifade etmenin çeşitli yollarını sağlar.
[Tek qubit işlemlerinde](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)açıklandığı gibi, döndürme özelliği, hisse algoritması için kritik öneme sahiptir.

$H $ ve $T $ kapıları kullanarak herhangi bir tek qubit işlemi hızlı bir şekilde ifade edebiliyoruz; $H burada \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ % fixme: Bu, şu anda dörtlü geri Whack Hack 'ı kullanıyor.
0 & e ^ {i \ Pi/4} \end{bmatrix} \end{Equation} bu, <xref:Microsoft.Quantum.Intrinsic.S> işlemin karekökünü, yani $T ^ 2 = S $ olur.
$T $ Gate, işlem tarafından uygulanır <xref:Microsoft.Quantum.Intrinsic.T> ve `(Qubit => Unit is Adj + Ctl)` tek bir-qubit üzerinde Unitary işlemi olduğunu belirten imzaya sahiptir.

Bu, herhangi bir rastgele tek qubit işlemi açıklamaya yetecek olsa da, farklı hedef makineler Pauli işleçleri hakkında daha etkili temsiller olabilir. bu nedenle, Prelude, bu tür döndürmeler için çeşitli yollar içerir.
Bunların en temel değeri, <xref:Microsoft.Quantum.Intrinsic.R> belirtilen Pauli ekseninin etrafında bir döndürme uygulayan işlemdir. \begin{Equation} R (\sigma, \fi) \mathrel{: =} \exp (-i \phi \ Sigma/2), \end{Equation}; burada $ \sigma $ bir Pauli işleci, $ \phi $ bir açı ve $ \exp $, matris üstel değerini temsil eder.
`((Pauli, Double, Qubit) => Unit is Adj + Ctl)`Girişin ilk iki bölümü, Unitary işleci $R (\sigma, \fi) $ ' i belirtmek için gereken klasik bağımsız değişkenleri $ \sigma $ ve $ \phi $ olarak temsil eden imzaya sahiptir.
Türü tek qubit Unitary olan bir işlem elde etmek için $ \sigma $ ve $ \phi $ öğesini kısmen uygulayabiliriz.
Örneğin, `R(PauliZ, PI() / 4, _)` türü vardır `(Qubit => Unit is Adj + Ctl)` .

> [!NOTE]
> <xref:Microsoft.Quantum.Intrinsic.R>İşlem giriş açısını 2 ' ye böler ve-1 ile çarpar.
> $Z $ döndürmeler için bu, $ \ket {0} $ eigenstate 'in $-\phi/$2 ile döndürüldüğü ve $ \ket $ eigenstate $ \phi/$2 tarafından döndürülerek $ \ket $ eigenstate 'in $ {1} {1} \ket $ eigenstate 'e göreli olarak $ \phi $ ile döndürüldüğü anlamına gelir {0} .
>
> Bu, özellikle de `T` `R(PauliZ, PI() / 8, _)` ilgisiz [küresel bir aşamaya](xref:microsoft.quantum.glossary#global-phase)göre farklılık gösterir.
> Bu nedenle $T $, bazen $ \frac{\pi} {8} $-Gate olarak bilinir.
>
> Ayrıca, etrafında döndürme `PauliI` , $ \phi/$2 genel aşamasını uygular. Bu tür aşamalar ilgisiz olsa da, [kavramsal belgelerde](xref:microsoft.quantum.concepts.qubit)olduğu gibi, denetlenen döndürmeler için de uygundur `PauliI` .

Hisse algoritmaları dahilinde, her zaman {\phi = \pi k/2 ^ n $ for \mathbb{Z} $ ve \mathbb{N} $ içinde $n \ $ adlı bazı $k \jyadic kesirleri olarak ifade etmek yararlı olur.
<xref:Microsoft.Quantum.Intrinsic.RFrac>İşlem, bu kuralı kullanarak belirtilen Pauli ekseninin etrafında bir döndürme uygular.
Bu, <xref:Microsoft.Quantum.Intrinsic.R> döndürme açısının, `Int` dyadic kesri olarak yorumlanan iki tür giriş olarak belirtildiğinden farklıdır.
Bu nedenle, `RFrac` imzası vardır `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` .
Tek qubit Unitary $ \ exp (i \pı k \ Sigma/2 ^ n) $, burada $ \sigma $ ilk bağımsız değişkene karşılık gelen Pauli matrisi, $k $ ikinci bağımsız değişkendir ve $n $ üçüncü bağımsız değişkendir.
`RFrac(_,k,n,_)` ile aynıdır `R(_,-πk/2^n,_)` ; açının kesirin *negatifi* olduğunu unutmayın.

<xref:Microsoft.Quantum.Intrinsic.Rx>Işlem Pauli $X $ ekseninin etrafında bir döndürme uygular.
İmza içeriyor `((Double, Qubit) => Unit is Adj + Ctl)` .
`Rx(_, _)` , ile aynıdır `R(PauliX, _, _)` .

<xref:Microsoft.Quantum.Intrinsic.Ry>Işlem Pauli $Y $ ekseninin etrafında bir döndürme uygular.
İmza içeriyor `((Double, Qubit) => Unit is Adj + Ctl)` .
`Ry(_, _)` , ile aynıdır `R(PauliY,_ , _)` .

<xref:Microsoft.Quantum.Intrinsic.Rz>Işlem Pauli $Z $ ekseninin etrafında bir döndürme uygular.
İmza içeriyor `((Double, Qubit) => Unit is Adj + Ctl)` .
`Rz(_, _)` , ile aynıdır `R(PauliZ, _, _)` .

<xref:Microsoft.Quantum.Intrinsic.R1>İşlem, {1} $Z $ $-$1 eigenstate of $ \ket $ etrafında verilen miktarda bir döndürme uygular.
İmza içeriyor `((Double, Qubit) => Unit is Adj + Ctl)` .
`R1(phi,_)` , `R(PauliZ,phi,_)` ve ile aynıdır `R(PauliI,-phi,_)` .

<xref:Microsoft.Quantum.Intrinsic.R1Frac>İşlem, Z = 1 eigenstate etrafında verilen miktarda kesirli bir döndürme uygular.
İmza içeriyor `((Int,Int, Qubit) => Unit is Adj + Ctl)` .
`R1Frac(k,n,_)` , `RFrac(PauliZ,-k.n+1,_)` ve ile aynıdır `RFrac(PauliI,k,n+1,_)` .

Bloch sphere üzerine eşlenmiş bir döndürme işlemi (Bu örnekteki Pauli $Z $ ekseni etrafında) örneği aşağıda gösterilmektedir:

![Bloch sphere üzerine eşlenen döndürme işlemi](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>Multi-Qubitoperations ####

Yukarıdaki tek qubit işlemlerine ek olarak, Prelude birçok multi-qubit işlemini de tanımlar.

İlk olarak, <xref:Microsoft.Quantum.Intrinsic.CNOT> işlem standart kontrollü bir- `NOT` kapısı, \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 & 0 \\ \\ \\ \\ & 1 & 0 & 0 & 0 &
\end{Equation} `((Qubit, Qubit) => Unit is Adj + Ctl)` , iki bireysel qubit üzerinde $ \operatorname{CNOT} $ davranır unitarily öğesini temsil eden imzaya sahip.
`CNOT(q1, q2)` , ile aynıdır `(Controlled X)([q1], q2)` .
`Controlled`Functor bir yazmaç üzerinde denetlemeye izin verdiğinden, `[q1]` yalnızca bir denetim isteytiğimiz belirten dizi değişmez değerini kullanırız.

Bu <xref:Microsoft.Quantum.Intrinsic.CCNOT> işlem, bazen Toffoli kapısı olarak da bilinen, düzenli olarak denetlenen bir kapısı gerçekleştirir.
İmza içeriyor `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` .
`CCNOT(q1, q2, q3)` , ile aynıdır `(Controlled X)([q1, q2], q3)` .

<xref:Microsoft.Quantum.Intrinsic.SWAP>İşlem iki qubit 'in hisse durumlarını değiştirir.
Diğer bir deyişle, Unitary matrisi \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 0 & \\ \\ 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix} uygular.
\end{Equation} öğesinde imza var `((Qubit, Qubit) => Unit is Adj + Ctl)` .
`SWAP(q1,q2)` , `CNOT(q1, q2)` ve sonrasında ile eşdeğerdir `CNOT(q2, q1)` `CNOT(q1, q2)` .

> [!NOTE]
> TAKAS kapısı, türünde bir değişkenin öğelerinin yeniden düzenleme işlemiyle aynı *değil* `Qubit[]` .
> Uygulama, `SWAP(q1, q2)` ve tarafından başvurulan qubits 'in durumuna bir değişikliğe neden olur `q1` `q2` , `let swappedRegister = [q2, q1];` ancak bu qubits 'e nasıl başvurduğumuz ile ilgili olarak yalnızca bunları etkiler.
> Üstelik, `(Controlled SWAP)([q0], (q1, q2))` öğeleri yeniden `SWAP` düzenleyerek temsil ettiğimiz üçüncü bir qubit durumunda koşullu olmasını sağlar.
> Fredkabağı kapısı olarak da bilinen denetimli-takas kapısı, tüm klasik hesaplamayı dahil etmek için yeterince güçlüdür.

Son olarak, Prelude, Multi-qubit Pauli işleçlerinin üslerini temsil eden iki işlem sağlar.
<xref:Microsoft.Quantum.Intrinsic.Exp>İşlem, çok-qubit Unitary \begin{Equation} \operatorname{exp} (\vec{\sigma}, \fi) \mathrel{: =} \exp\left (i \fi \ sigma_0 \otimes \ sigma_1 \otimes \cnoktalar \otimes \ sigma_n \right), \end{Equation}; burada $ \vec{\sigma} = (\ sigma_0, \ sigma_1, \noktalar, \ sigma_n) $ bir tek qubit Pauli işleçleri dizisi ve $ \phi $ bir açı.
`Exp`Döndürme, imza içeren bir öğe dizisi olarak $ \vec{\sigma} $ öğesini temsil eder `Pauli` `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` .

<xref:Microsoft.Quantum.Intrinsic.ExpFrac>İşlem, yukarıda açıklanan dyadic kesir gösterimini kullanarak aynı dönüşü gerçekleştirir.
İmza içeriyor `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` .

> [!WARNING]
> Pauli işleçleri için tencursor ürünlerinin üs öğeleri Pauli işleçleri 'nin üsünlerinin, tencursor ürünleriyle aynı değildir.
> Yani, $e ^ {i (Z \otimes Z) \phi} \ne e ^ {i Z \ Phi} \otimes e ^ {i Z \ Phi} $.

### <a name="measurements"></a>Ölçümler ###

Ölçtüğünde, ölçülen işlecin + 1 eigenvalue değeri bir sonuca karşılık gelir `Zero` ve-1 eigenvalue değeri bir sonuca karşılık gelir `One` .

> [!NOTE]
> Bu kural tek görünebilir, ancak bu iki avantaja sahiptir.
> İlk olarak, $ \ket $ sonucunu gözlemleyerek {0} değer ile temsil `Result` edilir `Zero` , gözlemleme $ \ket {1} $, öğesine karşılık gelir `One` .
> İkinci olarak, bir sonuca karşılık gelen eigenvalue $ \lambda $ $r $ $ \lambda = (-1) ^ r $ olduğunu yazalım.

Ölçüm işlemleri `Adjoint` ne ne de `Controlled` functor 'ı destekler.

<xref:Microsoft.Quantum.Intrinsic.Measure>İşlem, belirtilen Pauli işleçleri üründe bir veya daha fazla qubits 'in Birleşik ölçüsünü gerçekleştirir.
Pauli Array ve qubit dizisi farklı uzunluklardır, işlem başarısız olur.
`Measure` imza içeriyor `((Pauli[], Qubit[]) => Result)` .

Bir eklem ölçüsünün her bir qubit ayrı ayrı ölçüyle aynı olmadığına unutmayın.
Örneğin, $ \ket {11} = \ket {1} \otimes {1} \Tus= X\otimes X \ket $ durumunu göz önünde bulundurun {00} .
$Z _0 $ ve $Z _1 $ her biri ayrı ayrı, $r _0 = $1 ve $r _1 = $1 sonucunu elde ediyoruz.
$Z _0 Z_1 $, ancak $ \ket $ değerinin pozitif olduğunu belirten _ {\textrm{Joint}} = $0 adlı tek bir $r sonuç elde ediyoruz {11} .
Farklı, $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{Joint}}) $.
Kritik olarak, *yalnızca* bu ölçüden eşlik öğrendiğimiz için, pozitif eşlik için 2 2-qubit durumları, $ \ket {00} $ ve $ \tus$ arasındaki üst konumda temsil edilen tüm hisse bilgileri {11} korunur.
Hata düzeltmesini tartıştığımız için bu özellik daha sonra temel alınacaktır.

Kolaylık sağlaması için, Prelude, qubits 'i ölçmek için iki diğer işlem de sağlar.
Birincisi, tek qubit ölçümleri gerçekleştirirken oldukça yaygın olduğundan, Prelude bu durum için bir toplu değer tanımlar.
<xref:Microsoft.Quantum.Intrinsic.M>Işlem Pauli $Z $ işlecini tek bir qubit üzerinde ölçer ve imza içeriyor `(Qubit => Result)` .
`M(q)`, `Measure([PauliZ], [q])` ile eşdeğerdir.

<xref:Microsoft.Quantum.Measurement.MultiM>Pauli $Z $ işlecini her bir qubit dizisi üzerinde *ayrı olarak* ölçer ve her bir  `Result` qubit için elde edilen değer dizisini döndürür.
Bazı durumlarda bu, iyileştirilebilir. İmza ( `Qubit[] => Result[])` .
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

Ayrıca, Prelude, kod içinde kullanılmak üzere .NET düzeyinde zengin bir matematik ve tür dönüştürme işlevleri tanımlar Q# .
Örneğin, <xref:Microsoft.Quantum.Math> ad alanı ve gibi faydalı işlemleri tanımlar <xref:Microsoft.Quantum.Math.Sin> <xref:Microsoft.Quantum.Math.Log> .
Hisse geliştirme seti tarafından sunulan uygulama klasik .NET temel sınıf kitaplığını kullanır ve bu nedenle hisse programları ve bunların klasik sürücüleri arasında ek bir iletişim gidiş gelişmesi içerebilir.
Bu, yerel simülatör için bir sorun sunmadığından, bir hedef makine olarak uzak simülatör veya gerçek donanım kullanılırken bir performans sorunu olabilir.
Yani, tek bir hedef makine, bu işlemleri söz konusu sistem için daha verimli olan sürümlerle geçersiz kılarak bu performans etkisini hafifletmeyebilir.

### <a name="math"></a>Matematik ###

<xref:Microsoft.Quantum.Math>Ad alanı, .net temel sınıf kitaplığının [ `System.Math` sınıfından](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1&preserve-view=true)birçok yararlı işlev sağlar.
Bu işlevler, diğer işlevlerle aynı şekilde kullanılabilir Q# :

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

.NET statik yönteminin bağımsız değişkenlerinin türüne göre aşırı yüklendiği yerlerde, karşılık gelen Q# işlev, girişinin türünü gösteren bir sonek ile açıklanmıştır:

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>Bit düzeyinde Işlemler ###

Son olarak, <xref:Microsoft.Quantum.Bitwise> ad alanı sayıların bit düzeyinde işleçler aracılığıyla işlenmesine yönelik çeşitli yararlı işlevler sağlar.
Örneğin, <xref:Microsoft.Quantum.Bitwise.Parity> bir tamsayının bit düzeyinde eşlik sayısını başka bir tamsayı olarak döndürür.
