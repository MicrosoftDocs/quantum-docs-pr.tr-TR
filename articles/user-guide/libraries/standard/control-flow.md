---
title: 'Q # standart libarakları içindeki akış denetimleri'
description: 'Microsoft Q # standart kitaplığındaki Flow denetim işlemleri ve işlevleri hakkında bilgi edinin.'
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b41b3edd7a3e3ac13dbda106a869f4cba8183600
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275759"
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

Bu kalıbı yineleme ve döngüleri kullanarak ifade edebilirsiniz `for` :

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<xref:microsoft.quantum.canon.applytoeachca>Ancak, gibi dizi işleme işlevlerinde ifade edilir, <xref:microsoft.quantum.arrays.zip> ancak bu çok daha kısadır ve okunması daha kolaydır:

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

Bu bölümün geri kalanında, Canon to sıkı Express hisse programları tarafından sunulan çeşitli Flow denetim işlemlerinin ve işlevlerinin nasıl kullanılacağına dair birkaç örnek sunuyoruz.

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>Işlemler ve Işlevleri diziler ve aralıklar üzerinde uygulama ##

Canon tarafından sunulan birincil soyutlamalar yinelemeden biridir.
Örneğin, tek bir-qubit Unitary $U $ için $U \otimes U \otimes \cnoktalar \otimes U $ biçiminde bir Unitary değerini düşünün.
Soru <xref:microsoft.quantum.arrays.indexrange> -cevap olarak bunu `for` bir yazmaç üzerinde döngü olarak göstermek için kullanabiliriz:

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

Daha sonra bu yeni işlemi, `HAll(register)` $H \Otimes h \otimes \cnoktalar \otimes h $ ' a uygulamak için kullanabilirsiniz.

Bununla birlikte, özellikle daha büyük bir algoritmadaki bu çok önemlidir.
Üstelik, bu yaklaşım her bir qubit için uygulamak istediğimiz belirli bir işlem için özelleştirilmiştir.
Bu algoritmik kavramını daha açık bir şekilde ifade etmek için işlemlerin birinci sınıf olduğu gerçeğini kullanabiliriz:

```qsharp
ApplyToEachCA(H, register);
```

Burada sonek, `CA` çağrısının `ApplyToEach` kendi adjointable ve denetlenebilir olduğunu gösterir.
Bu nedenle, `U` `Adjoint` ve destekliyorsa `Controlled` , aşağıdaki satırlar eşdeğerdir:

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

Özellikle bu, ' `ApplyToEachCA` nin bir adjoint özelleştirmenin otomatik olarak oluşturulduğu işlemlerde görünebileceği anlamına gelir.
Benzer şekilde, <xref:microsoft.quantum.canon.applytoeachindex> formun desenlerini temsil etmek için yararlıdır `U(0, targets[0]); U(1, targets[1]); ...` ve kendi girişi tarafından desteklenen her bir tek bir bileşim birleşimi için sürümler sağlar.

> [!TIP]
> `ApplyToEach`tür parametreli, dışında bir girişi olan işlemlerle kullanılabilmesi için `Qubit` .
> Örneğin, `codeBlocks` kurtarılması gereken bir değer dizisi olduğunu varsayalım <xref:microsoft.quantum.errorcorrection.logicalregister> .
> Ardından `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` , `code` `recoveryFn` her bloğa bağımsız olarak hata düzeltme kodu ve kurtarma işlevi uygular.
> Bu, klasik girişler için bile geçerlidir: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` $ \pı/$2 yaklaşık $X $, ardından $Y $ hakkında $Pi/$3 dönüşü uygular.

Q # Canon, işlevsel programlamaya tanıdık olan klasik numaralandırma desenleri için de destek sağlar.
Örneğin, bir <xref:microsoft.quantum.arrays.fold> \_ \_ \_ liste üzerinde bir işlevi azaltmak için $f (f (f (s {\Text{Initial}}, x 0), \noktalar) $ düzenini uygular.
Bu model toplamları, ürünleri, Minima, MAXIMA ve diğer benzeri işlevleri uygulamak için kullanılabilir:

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

Benzer şekilde, ve gibi işlevler, <xref:microsoft.quantum.arrays.mapped> <xref:microsoft.quantum.arrays.mappedbyindex> Q # içinde fonksiyonel programlama kavramlarını ifade etmek için de kullanılabilir.

## <a name="composing-operations-and-functions"></a>Işlemleri ve Işlevleri oluşturma ##

Canon tarafından sunulan denetim akışı yapıları ve işlevleri, çeşitli işlemleri veya işlevleri tek bir çağrılabilir hale getirilebilmeme yararlı olacaktır.
Örneğin, ^ {\abger} $ $UVU deseninin son derece ortak olduğu için, Canon <xref:microsoft.quantum.canon.applywith> Bu model için bir soyutlama olarak işlem sağlar.
Bu soyutlama Ayrıca, `Controlled` sıranın üzerinde `U(qubit); V(qubit); Adjoint U(qubit);` işlem yapması gerekmiyorsa, devrelere daha etkili bir şekilde uyum sağlar `U` .
Bunu görmek için, $c (U) $ 'nin Unitary temsil `Controlled U([control], target)` ettiği ve $c (V) $ ile aynı şekilde tanımlanmasına izin verin.
Daha sonra, rastgele bir durum $ \ket{\psı} $, \begin{hizalaması} c (U) c (V) c (U) ^ \hanger \ demet {1} \otimes \ket{\psı} & = \ket {1} ^ {\abger} \ket{\psı}) \\ \\ & = (\cıvadone \otimes u) (c (V)) (\cıvadone \otimes u ^ \gesger) {1}
tanımı tarafından \end{hizalaması} `Controlled` .
Diğer taraftan, \begin{hizalaması} c (U) c (V) c (U) ^ \dağılım \demet {0} \otimes \ket{\psı} & = \ket {0} \otimes \ket{\psı} \\ \\ & = \KET {0} \otimes (uu ^ \gesger \ket{\psı}) \\ \\ & = (\cıvadone \Otimes u) (c (V)) (\cıvado \otimes u ^ \dağılım) \demet {0} \otimes
* End{hizalaması} bu şekilde, tüm giriş durumları için bu şekilde $U $ devre dışı bırakabilirsiniz.
Diğer bir deyişle, $c (UVU ^ \dağılım) = U c (V) U ^ \dağılım $.
Denetim işlemleri genel olarak pahalı olabildiğinden, gibi denetimli varyantlar kullanılması `WithC` ve `WithCA` uygulanması gereken denetim dütlerini azaltmaya yardımcı olabilir.

> [!NOTE]
> Düzenleme out $U $ ' ın başka bir sonucu, functor 'un nasıl uygulanacağını de bilmelidir `Controlled` `U` .
> `ApplyWithCA`Bu nedenle, beklenenden daha zayıf bir imzaya sahip olabilir:
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

Benzer şekilde, sırayla <xref:microsoft.quantum.canon.bound> başka işlemler uygulayan işlemleri üretir.
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
Bu benzerleme vurguladı, diğer Unitary işleçleri gibi her türlü Unitary işlecinin, belirli bir Unitary işleci olarak davranacak şekilde yönergeler sunan klasik alt yordamlar için belirli bir arama dizisi oluşturma gibi, Unitary işleçlerinin yalnızca çağırma işlemlerinin yan etkilerine karşılık geldiği tanıma göre kesin hale getirilir.
Bu görünüm altında, `Bound` tam olarak matris ürününün temsili, bu, ' `Bound([A, B])(target)` `A(target); B(target);` de $ba $ ' a karşılık gelen çağrı sırası olan öğesine denk gelir.

Daha karmaşık bir örnek, [Trour – Suzuki genişletmesi](https://arxiv.org/abs/math-ph/0506007v1).
[Veri yapılarının](xref:microsoft.quantum.libraries.data-structures)Dynamical Oluşturucu temsili bölümünde açıklandığı gibi, Trour – Suzuki genişletmesi, matris üslerini ifade etmenin özellikle faydalı bir yolunu sağlar.
Örneğin, genişletmenin en düşük sırasıyla uygulanması $A $ ve $B $ $A = A ^ \dağılım $ ve $B = B ^ \dağılım $ gibi tüm işleçler için bunu verir. \begin{hizalaması} \tag{★} \label{EQ: Trour-Suzuki-0} \exp (i [A + B] t) = \ lim_ {n\to\infty} \left (\exp (ı/n) \exp (ı B t/n) \right) ^ n.
\end{hizalaması} birlikte, bu durum $A + B $ altında $A $ ve $B $ tek başına kapsamında gelişen bir durumu yaklaşık olarak geliştirdiğini söyler.
$A $ altında `A : (Double, Qubit[]) => Unit` $e ^ {i t A} $ uygulanan bir işlem tarafından temsil ediyorsanız,, arama dizilerini yeniden düzenleme açısından Trour – Suzuki genişletmesi gösterimi net hale gelir.
Her ne `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` kadar, ve gibi bir işlem verildiğinde `A = U(0, _, _)` `B = U(1, _, _)` , `U` form dizileri oluşturarak $t $ zaman içindeki integrali temsil eden yeni bir işlem tanımlayabiliriz

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

Bu noktada artık, *her şey için*ücretlendirilir – Suzuki genişletmesi olmadan bir sorun olabilir.
Genişleme, $ \eqref{EQ: Trour-Suzuki-0} $ tarafından bir çok özel yineleme düzeniyle rekabet altına alınmıştır.
Bu yineleme deseninin uygulanma ölçütü <xref:microsoft.quantum.canon.decomposeintotimestepsca> :

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

' Nin imzası `DecomposeIntoTimeStepsCA` , her biri diziler tarafından desteklenen koleksiyonlar tarafından ya da içindeki işlem öğelerinin, ilk öğeleri uzunluklarını belirten değerler olan tanımlama grupları ile temsil edildiği, Q # içinde ortak bir model izler `Int` .

## <a name="putting-it-together-controlling-operations"></a>Birlikte yerleştirme: Işlemleri denetleme ##

Son olarak, Canon, `Controlled` koşullu işlem işlemlerine ek yollar sunarak, functor 'da oluşturulur.
Özellikle de daha fazla hisse aritmetiğinde, hesaplama tabanlı durumlarda $ \ket{0\cnoktalar 0} $ dışındaki durum işlemleri için yaygın olarak kullanılır.
Yukarıda tanıtılan denetim işlemlerini ve işlevleri kullanarak, tek bir bildirimde daha fazla genel hisse koşulumuz olabilir.
<xref:microsoft.quantum.canon.controlledonbitstring>Bunu nasıl yapacağım (San türü parametreler), daha sonra parçaları bir tane olacak şekilde böleceğiz.
Yapmanız gereken ilk şey, denetimi rastgele hesaplama esasına göre uygulamaya yönelik ağır bir kaldırma işlemi için gerçekten bir işlem tanımlamaktır.
Bununla birlikte, bu işlemi doğrudan çağırmayacağız. bu nedenle, `_` başka bir yapının başka bir yerde bir uygulama olduğunu göstermek için adın başına ekliyoruz.

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

Sağladığımız `Bool` işleme uygulamak istediğimiz uygulamayı belirtmek için kullandığımız, dizi olarak temsil edilen bir bit dizesi sunuyoruz `oracle` .
Bu işlem doğrudan uygulamayı doğrudan yaptığından, burada olarak temsil edilen denetimi ve hedef kayıtları da ele almanız gerekir `Qubit[]` .

Daha sonra, $ \ket{\vec{s}} $/$ \vec{s} $ bir bit dizesi için hesaplama tabanlı durum $ \ket{\vec{s}} = \ket{s \_ 0 s \_ 1/nokta s \_ {n-1}} $ ' ın kontrol ettiğine ilişkin bilgi
Özellikle, $ \ket{\vec{s}} = X ^ {s \_ 0} \Otimes x ^ {s \_ 1} \otimes \cnoktalar \Otimes x ^ {s \_ {n-1}} \ket{0\cnoktalar 0} $.
Bu $X ^ {\abger} = X $ bu yana $ \ket{0\noktalar 0} = X ^ {s \_ 0} \Otimes x ^ {s \_ 1} \otimes \cnoktalar \Otimes x ^ {s \_ {n-1}} \ket{\vec{s}} $ anlamına gelir.
Bu nedenle, $P = X ^ {s \_ 0} \Otimes x ^ {s \_ 1} \otimes \cnoktalar \Otimes x ^ {s \_ {n-1}} $, uygulayabilir `Controlled oracle` ve $ \vec{s} $ dizinine geri dönüşüm uygulayabiliriz.
Bu oluşturma işlemi tam `ApplyWith` olarak, Yeni işlediğimiz gövdesini buna göre yazdık:

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

Burada, ' nin <xref:microsoft.quantum.canon.applypaulifrombitstring> ile kullanım için kısmen uygulanması $P $ ' i uygulamak için kullandık `ApplyWith` .
Ancak, *Denetim* kaydını istenen formumuza dönüştürmemiz gerektiğini unutmayın. bu nedenle, hedefte iç işlemi kısmen uygulayacağız `(Controlled oracle)` . *target*
Bu, `ApplyWith` tam olarak istediğiniz gibi, denetim yazmacını $P $ ile birlikte bırakır.

Bu noktada yapılabiliriz, ancak yeni operasyonumuzın, functor uygulama gibi "uygun değil" olarak karşılanmıyor `Controlled` .
Bu nedenle, Oracle 'ın denetlenmesi ve yeni bir işlem döndürmesi için geçen bir işlev yazarak yeni denetim akışı kavramımız tanımlamayı tamamlayacağız.
Bu şekilde, yeni işlevimiz, `Controlled` Q # ve Canon 'yi kullanarak güçlü yeni denetim akışı yapılarını kolayca tanımlayabiliriz.

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
