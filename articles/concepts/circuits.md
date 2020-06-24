---
title: Hisse devreleri
description: Hisse bağlantı diyagramlarında basit ve karmaşık hisse işlemlerini görsel olarak nasıl temsil ettiğini öğrenin.
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 59c32928ddc9252009ad101a3cf3ac33f4968e28
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269618"
---
# <a name="quantum-circuits"></a>Hisse devreleri
Bir süre için Unitary dönüştürme $ \ metin { cnot} _ {01 } (H \otimes 1) $ değerini göz önünde bulundurun.
Bu ağ geçidi sırası, en yüksek düzeyde bir entangled bit durumu oluşturduğundan, hisse bilgi işlem için temel öneme sahiptir:

$ $ \mathrm{CNOT}_{01 } (H \otimes 1) \ket{00 } = \frac{1 } {\sqrt{2 } } \left (\ket{00 } + \ket{11 } \ right), $ $

Bu ya da daha fazla karmaşıklığa sahip işlemler, hisse uygun bir şekilde bir hisse alım *Diyagramı*olarak adlandırılan görselleştirme için basit bir yöntem olduğundan harika bir sorun olması gerekir.
Bu en yüksek düzeyde değerlendirme için devre diyagramı şu şekilde hazırlanıyor:

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![En yüksek düzeyde bir entaninal iki-qubit durumu için devre diyagramı](~/media/1.svg)

## <a name="quantum-circuit-diagram-conventions"></a>Hisse devre diyagramı kuralları
Hisse için bu görsel dil, bir hisse devresini ifade eden kuralları anladıktan sonra eşdeğer matrisinin yazılmasından daha kolay digestible olabilir.
Aşağıda bu kuralları gözden geçiririz.

Devre diyagramında, her katı çizgi bir qubit veya daha fazla genel olarak bir qubit kaydı gösterir.
Kurala göre, üst çizgi qubit kayıt $0 ' dir $ ve geri kalan değerler sırayla etiketlenir. Yukarıdaki örnek bağlantı hattı iki qubit üzerinde (veya bir qubitden oluşan equivalently iki kayıt) üzerinde işlem görecek şekilde gösterilmiştir.
Bir veya daha fazla qubit kayıt üzerinde işlem gören kapıları kutu olarak gösterilir.
Örneğin, simge

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Tek qubit kayıt üzerinde işlem gören Hadamard işlemi sembolü](~/media/2.svg)

, tek qubit kayıt üzerinde işlem gören bir [Hadamard](xref:microsoft.quantum.intrinsic.h) işlemidir.

Hisse kapıları, ilk olarak qubits 'e uygulanan kapıda en sol geçit ile kronolojik sırada sıralanır.
Diğer bir deyişle, kapıların hisse durumunu tutan şekilde fotoğrafını yaparsanız, kablolar diyagramdaki her bir kapıdan, soldan sağa doğru hisse ma durumunu getirir.
Yani 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Soldan sağa uygulanan hisse kapıları diyagramı](~/media/3.svg)

Unitary matrisi $CBA $ .
Matris çarpıtına ters kural: en sağdaki matris önce uygulanır. Ancak, bu arada en sol kapı, en sol kapı için uygulanır.
Bu fark, her zaman karışıklığa yol açabilir, bu nedenle doğrusal cebirsel gösterimi ve hisse senedi devre şemaları arasında önemli bir farklılık olduğunu fark etmek önemlidir.

## <a name="inputs-and-outputs-of-quantum-circuits"></a>Hisse devreleri giriş ve çıkışları
Verilen tüm önceki örneklerde, hisse kapıdan alınan kabloların sayısı kadar hisse kapıda aynı sayıda kablo (qubit) girişi gerekiyordu.
Bu ilk olarak, hisse devrelerin genel olarak girdilerden daha fazla veya daha az çıkış sahibi olabileceği makul görünebilir.
Ancak tüm hisse işlemleri, ölçümü Kaydet, Unitary ve bu nedenle ters çevrilebilir olduğundan bu olanaksızdır.
Girişlerle aynı sayıda çıkışı yoksa, geri alınamaz ve bu nedenle bir çelişki olan Unitary değildir.
Bu nedenle, bir devre diyagramında çizilen her kutu, tam olarak onunla aynı sayıda kabloda yer almalıdır.

Multi-qubit devre şemaları, tek qubit olanlara benzer kuralları izler.
Bir açıklığa kavuşturan örnek olarak, $ $ (H S X) $ olarak $B iki-qubit Unitary işlemi tanımlayabilir \otimes ve devre equivalently şu şekilde ifade edebilirsiniz

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![İki-qubit Unitary işleminin devre diyagramı](~/media/4.svg)

$B, bağlantı hattının $ kullanıldığı içeriğe göre 2 1-qubit kayıt yerine tek bir iki-qubit kaydı üzerinde bir eyleme sahip olarak da görüntülenebilir. Bu tür soyut devre diyagramlarından en yararlı özellik, karmaşık hisse algoritmalarının, bunları temel kapıları derlemek zorunda kalmadan yüksek düzeyde açıklanmasına izin vermesidir.
Bu, algoritmadaki her bir alt yordamların nasıl çalıştığı hakkında tüm ayrıntıları anlamak zorunda kalmadan, büyük bir hisse algoritması için veri akışı hakkında bir bilgi edinebilirsiniz.

## <a name="controlled-gates"></a>Denetlenen kapıları
Multi-qubit hisse devresini içinde yerleşik olan diğer yapı denetimdir.
Bir hisse listedir kontrollü kapı eylemi, belirtilen $ \Lambda (G) $, tek bir qubitin değerinin $G uygulamasını denetliyorsa $ , bir ürün durumu girişi $ \Lambda (G) (\Alpha \ket{0 } + \beta \ket{1 } ) { \tus\psı } = \Alpha \ket{0 } \tus\psı { } + \beta \ket{1 } G \ket { \ PSI } $ şeklinde aşağıdaki örneğe bakarak anlaşılabilirler.
Yani, denetlenen kapı $ $ \psı içeren kayda $G uygular $ ve yalnızca denetim qubit $1 değerini alırsa $ .
Genel olarak, bu tür denetimli işlemleri devre diyagramlarında

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Listedir denetimli bir ağ geçidinin devre diyagramı](~/media/5.svg)

Burada siyah daire, kapıdan denetlediğiniz ve dikey bir tel, denetim qubit $1 değerini alırken uygulanan Unitary 'ı gösterir $ .
$G = X $ ve $G = Z olduğu özel durumlar için, $ kapıların denetlenen sürümünü (denetlenen-X kapısıdır [$CNOT $ kapısı](xref:microsoft.quantum.intrinsic.cnot)olduğunu unutmayın) aşağıdaki gösterimi tanıtıldık:

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Denetlenen kapıların özel durumları için devre diyagramı](~/media/6.svg)

Q #, bir işlemin denetlenen sürümünü otomatik olarak oluşturmak için yöntemler sağlar. Bu işlem, programcının bu işlemleri ele almak zorunda kalmadan kaydeder. Buna bir örnek aşağıda verilmiştir:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a>Ölçüm işleci
Devre diyagramlarında görselleştirilecek kalan işlem ölçümdür.
Ölçüm bir qubit kaydı alır, bunu ölçer ve sonucu klasik bilgiler olarak verir.
Ölçüm bir işlem, ölçüm simgesiyle gösterilir ve her zaman bir qubit yazmaç girişi (katı bir satırla gösterilir) ve klasik bilgiler verir (bir Double satırıyla gösterilir).
Özellikle, bu tür bir alt devre şöyle görünür:

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Ölçüm işlemini temsil eden sembol](~/media/7.svg)

Q # Bu amaçla bir [Ölçü işleci](xref:microsoft.quantum.intrinsic.measure) uygular.
Daha fazla bilgi için [ölçümlerle ilgili bölüme](xref:microsoft.quantum.libraries.standard.prelude#measurements) bakın.

Benzer şekilde, subdevı

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Denetlenen bir işlemi temsil eden devre diyagramı](~/media/8.svg)

$G, $ Klasik denetim bit $1 değeri olan ' de uygulandığı şekilde, sınıf denetimli bir geçit sağlar $ .

## <a name="teleportation-circuit-diagram"></a>Teleporsyon devre diyagramı
Hisse teleporsyon, bu bileşenleri göstermek için büyük olasılıkla en iyi hisse algoritmadır.
Karşılık gelen [hisse küçon](xref:microsoft.quantum.overview.katas) ile uygulamalı teleporsyon, verileri bir hisse bir bilgisayar içinde (veya hatta bir hisse ağı içindeki uzak hisse bilgisayarları arasında), entanglement ve ölçüm kullanımıyla birlikte taşımaya yönelik bir yöntemdir.
Her ne kadar, bu, bir derece bitden diğerine, bir qubit 'in değerinin ne olduğunu bilmeksizin, belirli bir qubit içindeki değeri bir ile diğerine söylemeden, gerçekten de bir hisse cısına geçiş yeteneğine sahiptir!
Bu, protokol için hisse uzayı yasaları uyarınca çalışması için gereklidir.
Hisse ve teleporsyon devresi aşağıda verilmiştir; Ayrıca, hisse öğesinin nasıl okunacağını göstermek için devresinin açıklamalı bir sürümünü sunuyoruz.

<!--- ![](.\media\tp2.svg){ width=50% } --->
![Hisse ve teleporsyon devresi](~/media/tp2.svg)
