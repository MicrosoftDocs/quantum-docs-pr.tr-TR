---
title: 'Q # standart kitaplıkları-denetim ve akış | Microsoft Docs'
description: 'Q # standart kitaplıkları-denetim ve akış'
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: ff73cef12a3b8c2a6559308dc244c7c2e865ba9f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820462"
---
# <a name="higher-order-control-flow"></a>Daha yüksek sıralı denetim akışı #

Standart kitaplığın birincil rollerinden biri, yüksek düzey algoritmik fikirlerinin [hisse programları](https://en.wikipedia.org/wiki/Quantum_programming)olarak hızlı bir şekilde yönetilmesini kolaylaştırmaktır.
Bu nedenle, Q # Canon, her biri işlevlerin ve işlemlerin kısmi uygulaması kullanılarak uygulanan çeşitli farklı akış denetim yapıları sağlar.
Bir örneğe hemen atlamak için, bir kasada "CNOT merdiveni" oluşturmak istediği durumu düşünün:

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

Bu kalıbı yineleme ve `for` döngüleri kullanarak ifade edebilirsiniz:

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<xref:microsoft.quantum.arrays.zip>gibi <xref:microsoft.quantum.canon.applytoeachca> ve dizi işleme işlevlerine ifade edilir ancak bu çok daha kısadır ve okunması daha kolaydır:

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

Bu bölümün geri kalanında, Canon to sıkı Express hisse programları tarafından sunulan çeşitli Flow denetim işlemlerinin ve işlevlerinin nasıl kullanılacağına dair birkaç örnek sunuyoruz.

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>Işlemler ve Işlevleri diziler ve aralıklar üzerinde uygulama ##

Canon tarafından sunulan birincil soyutlamalar yinelemeden biridir.
Örneğin, tek bir-qubit Unitary $U $ için $U \otimes U \otimes \cnoktalar \otimes U $ biçiminde bir Unitary değerini düşünün.
Q # ' da, bunu bir kayıt üzerinde `for` döngüsü olarak göstermek için <xref:microsoft.quantum.arrays.indexrange> kullanabiliriz:

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

Daha sonra bu yeni işlemi `HAll(register)` olarak $H \otimes/cnoktalar \otimes H $ uygulamak için kullanabilirsiniz.

Bununla birlikte, özellikle daha büyük bir algoritmadaki bu çok önemlidir.
Üstelik, bu yaklaşım her bir qubit için uygulamak istediğimiz belirli bir işlem için özelleştirilmiştir.
Bu algoritmik kavramını daha açık bir şekilde ifade etmek için işlemlerin birinci sınıf olduğu gerçeğini kullanabiliriz:

```qsharp
ApplyToEachCA(H, register);
```

Burada sonek `CA`, `ApplyToEach` çağrısının kendisinin adjointable ve denetlenebilir olduğunu gösterir.
Bu nedenle, `U` `Adjoint` ve `Controlled`destekliyorsa, aşağıdaki satırlar eşdeğerdir:

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

Özellikle, bu, `ApplyToEachCA` çağrılarının bir adjoint özelleştirmenin otomatik olarak oluşturulduğu işlemlerde görünebileceği anlamına gelir.
Benzer şekilde, <xref:microsoft.quantum.canon.applytoeachindex> form `U(0, targets[0]); U(1, targets[1]); ...`desenlerini temsil etmek için yararlıdır ve kendi girişinin desteklediği her bir tek bir bileşim birleşimi için sürümler sağlar.

> [!TIP]
> `ApplyToEach`, `Qubit`dışında giriş yapan işlemlerle kullanılabilmesi için tür parametreli parametretür.
> Örneğin, `codeBlocks` kurtarılması gereken <xref:microsoft.quantum.errorcorrection.logicalregister> değerleri dizisi olduğunu varsayalım.
> `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)`, her bloğa bağımsız olarak hata düzeltme kodu `code` ve kurtarma işlevi `recoveryFn` uygular.
> Bu, klasik girişler için bile geçerlidir: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` $ \pı/$2 $X $ hakkında $pi/$3 ' nin ardından $Y $ hakkında bir döndürme uygular.

Q # Canon, işlevsel programlamaya tanıdık olan klasik numaralandırma desenleri için de destek sağlar.
Örneğin, <xref:microsoft.quantum.arrays.fold> bir işlev üzerinde bir işlevi azaltmak için $f (f (f (s\_{\Text{Initial}}, x\_0), x\_1), \noktalar) $ düzenini uygular.
Bu model toplamları, ürünleri, Minima, MAXIMA ve diğer benzeri işlevleri uygulamak için kullanılabilir:

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

Benzer şekilde, <xref:microsoft.quantum.arrays.mapped> ve <xref:microsoft.quantum.arrays.mappedbyindex> gibi işlevler, Q # içindeki fonksiyonel programlama kavramlarını ifade etmek için de kullanılabilir.

## <a name="composing-operations-and-functions"></a>Işlemleri ve Işlevleri oluşturma ##

Canon tarafından sunulan denetim akışı yapıları ve işlevleri, çeşitli işlemleri veya işlevleri tek bir çağrılabilir hale getirilebilmeme yararlı olacaktır.
Örneğin, $UVU ^ {\abger} $ deseninin son derece ortak olması, örneğin, Canon 'nin işlemi bu düzene yönelik bir soyutlama olarak <xref:microsoft.quantum.canon.applywith> sağlar.
Bu soyutlama Ayrıca, `U(qubit); V(qubit); Adjoint U(qubit);` sıralı `Controlled` işlem yapmak için her `U`üzerinde işlem yapmasına gerek olmadığı için, devrelere daha verimli bir hale getirir.
Bunu görmek için, $c (U) $ `Controlled U([control], target)` temsil eden Unitary, aynı şekilde $c (V) $ tanımlanmasına izin verin.
Daha sonra, rastgele bir durum $ \ket{\psı} $, \begin{hizalaması} c (U) c (V) c (U) ^ \hanger \demet{1} \o{1} & Times {\abger} \ket{\psı}) \\\\ & = (\cıvado \otimes U) (c (V)) (\cıvado \otimes U ^ \hanger) \tus{1} \otimes \ket{\psı}.
`Controlled`tanımına \end{hizalaması}.
Diğer taraftan, \begin{hizalaması} c (U) c (V) c (U)% \dağılım \demet{0} \otimes \ket{\psı} & = \ket{0} \otimes \ket{\psı} \\\\ & = \tus{0} \osüreler (UU ^ \hanger \ket{\psı}) \\\\ & = (\cıvado \otimes U) (c (V)) (\cıvado \otimes U ^ \dağılım) \tus{0} \otimes \ket{\psı}.
\* End{hizalaması} bu şekilde, tüm giriş durumları için bu şekilde $U $ devre dışı bırakabilirsiniz.
Diğer bir deyişle, $c (UVU ^ \dağılım) = U c (V) U ^ \dağılım $.
Denetim işlemleri genel olarak pahalı olabildiğinden, `WithC` ve `WithCA` gibi denetimli varyantlar kullanılması gereken denetim çeşitlemesinin sayısını azaltmaya yardımcı olabilir.

> [!NOTE]
> Düzenleme out $U $ ' ın başka bir sonucu, `U``Controlled` functor 'un nasıl uygulanacağını de bilmelidir.
> `ApplyWithCA` bu nedenle, beklenenden daha zayıf bir imzaya sahip olabilir:
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

Benzer şekilde, <xref:microsoft.quantum.canon.bound> sırayla başka işlemler uygulayan işlemler üretir.
Örneğin, aşağıdakiler eşdeğerdir:

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

Yineleme desenleriyle birleştirmek, bunu özellikle yararlı hale getirir:

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a>Zaman içinde sıralı bileşim ###

Akış denetimini kısmi uygulama ve klasik işlevler açısından düşünerek yine de ilerleyebiliriz ve klasik akış denetimi açısından oldukça karmaşık bir kavram da modelleyebilir.
Bu benzerleme vurguladı, Unitary işleçlerinin, diğer Unitary işleçleri için herhangi bir ayrışmayla ilgili olarak belirli bir yapılandırma ile karşılık gelen işlem belirli Unitary işleçleri olarak davranacak yönergeleri sunan klasik alt yordamlar için çağrı dizisi.
Bu görünüm altında, `Bound` matris ürününün gösterimi kesin olduğundan, `Bound([A, B])(target)` `A(target); B(target);`eşdeğerdir, bu da $BA $ öğesine karşılık gelen arama sırasıdır.

Daha karmaşık bir örnek, [Trour – Suzuki genişletmesi](https://arxiv.org/abs/math-ph/0506007v1).
[Veri yapılarının](xref:microsoft.quantum.libraries.data-structures)Dynamical Oluşturucu temsili bölümünde açıklandığı gibi, Trour – Suzuki genişletmesi, matris üslerini ifade etmenin özellikle faydalı bir yolunu sağlar.
Örneğin, genişletmenin en düşük sırasıyla uygulanması $A $ ve $B $ $A = A ^ \dağılım $ ve $B = B ^ \dağılım $ gibi tüm işleçler için bunu verir. \begin{hizalaması} \tag{★} \label{EQ: Trour-Suzuki-0} \exp (i [A + B] t) = \ lim_ {n\to\infty} \left (\exp (ı/n) \exp (ı B t/n) \right) ^ n.
\end{hizalaması} birlikte, bu durum $A + B $ altında $A $ ve $B $ tek başına kapsamında gelişen bir durumu yaklaşık olarak geliştirdiğini söyler.
$A $ altında, ^ {i t A} $ $e uygulanan `A : (Double, Qubit[]) => Unit` bir işlem tarafından temsil ediyorsanız, arama dizilerini yeniden düzenleme açısından Trour – Suzuki genişletmesi gösterimi net hale gelir.
`U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl`, `A = U(0, _, _)` ve `B = U(1, _, _)`gibi bir işlem verildiğinde, form dizileri oluşturarak $t $ $ `U` integrali temsil eden yeni bir işlem tanımlayabiliriz

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

Bu noktada artık, *her şey için*ücretlendirilir – Suzuki genişletmesi olmadan bir sorun olabilir.
Genişleme, $ \eqref{EQ: Trour-Suzuki-0} $ tarafından bir çok özel yineleme düzeniyle rekabet altına alınmıştır.
Bu yineleme deseninin <xref:microsoft.quantum.canon.decomposeintotimestepsca>tarafından uygulanması:

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

`DecomposeIntoTimeStepsCA` imzası, s # içinde ortak bir model izler. burada, diziler tarafından desteklenen koleksiyonlar, ve içindeki işlem öğelerinin, ilk öğeleri `Int` değerlerinin uzunluğunu belirten diziler tarafından temsil edildiği bir şeydir.

## <a name="putting-it-together-controlling-operations"></a>Birlikte yerleştirme: Işlemleri denetleme ##

Son olarak, Canon, koşul hisse işlemlerine ek yollar sunarak `Controlled` functor üzerinde oluşturulur.
Özellikle de daha fazla hisse aritmetiğinde, hesaplama tabanlı durumlarda $ \ket{0\cnoktalar 0} $ dışındaki durum işlemleri için yaygın olarak kullanılır.
Yukarıda tanıtılan denetim işlemlerini ve işlevleri kullanarak, tek bir bildirimde daha fazla genel hisse koşulumuz olabilir.
<xref:microsoft.quantum.canon.controlledonbitstring> bunu nasıl yapacağım (San tür parametreleri), parçaları tek tek bölümlere ayırıyoruz.
Yapmanız gereken ilk şey, denetimi rastgele hesaplama esasına göre uygulamaya yönelik ağır bir kaldırma işlemi için gerçekten bir işlem tanımlamaktır.
Bununla birlikte, bu işlemi doğrudan çağırmayacağız. bu nedenle, başka bir yapının başka bir yerde bir uygulama olduğunu göstermek için adın başına `_` ekleyeceğiz.

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

`Bool` dizi olarak temsil edilen bir bit dizesi sunuyoruz. Bu, sağladığımız `oracle` işlem için uygulamak istediğimiz bir uygulama belirtmek için kullanıyoruz.
Bu işlem doğrudan uygulamayı gerçekten yaptığından, burada `Qubit[]`olarak temsil edilen denetimi ve hedef kayıtları da ele almanız gerekir.

Daha sonra, hesaplama tabanlı durumun ($ \ket{\vec{s}} = \ket{s\_0 s\_1 \ nokta s\_{n-1}}) denetlendiğini aklınızda kılıyoruz $ \vec{s} $ bit dizesi için $ \ket{\vec{s}} $, $ \ket{0\cnoktalara 0} $ olarak dönüştürme yapılabilir.
Özellikle, $ \ket{\vec{s}} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cnoktalar \otimes X ^ {s\_{n-1}} \ket{0\cnoktalar 0} $.
Bu $X ^ {\abger} = X $ olduğundan bu, $ \ket{0\noktalara 0} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cnoktalar \otimes X ^ {s\_{n-1}} \ket{\vec{s}} $ olduğunu gösterir.
Bu nedenle, $P = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cnoktalar \otimes X ^ {s\_{n-1}} $, `Controlled oracle`uygulayabilir ve $ \vec{s} $ dizinine geri dönüşüm uygulayabiliriz.
Bu oluşturma işlemi tam olarak `ApplyWith`, bu nedenle yeni işlediğimiz gövdesini buna göre yazıyoruz:

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

Burada $P $ uygulamak için <xref:microsoft.quantum.canon.applypaulifrombitstring> kullandınız, `ApplyWith`ile kullanım için kısmen uygulanıyor.
Bununla birlikte, *Denetim* kaydını istenen formumuza dönüştürmemiz gerektiğini unutmayın. bu nedenle, *hedefte*iç işlemi `(Controlled oracle)` kısmen uygulayacağız.
Bu, tam olarak istediğiniz gibi, denetim yazmacını $P $ ile birlikte bırakmak için `ApplyWith` bırakır.

Bu noktada yapılabiliriz, ancak yeni operasyonumuzın `Controlled` functor uygulama gibi "uygun değil" olarak karşılanmaz.
Bu nedenle, Oracle 'ın denetlenmesi ve yeni bir işlem döndürmesi için geçen bir işlev yazarak yeni denetim akışı kavramımız tanımlamayı tamamlayacağız.
Bu şekilde, yeni `Controlled`işlevimiz, soru-cevap ve Canon 'yi kullanarak güçlü yeni denetim akışı yapılarını kolayca tanımlayabiliriz.

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
