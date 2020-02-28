---
title: Hisse devreleri
description: Hisse bağlantı diyagramlarında basit ve karmaşık hisse işlemlerini görsel olarak nasıl temsil ettiğini öğrenin.
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 8ba4648f1837065d15957a01ab4ca8dd2d490a42
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77905157"
---
# <a name="quantum-circuits"></a>Hisse devreleri
Şu anda Unitary dönüştürmesi $ \Text{CNOT} _{01}(H\otimes 1) $ ' i göz önünde bulundurun.
Bu ağ geçidi sırası, en yüksek düzeyde bir entangled bit durumu oluşturduğundan, hisse bilgi işlem için temel öneme sahiptir:

$ $ \mathrm{CNOT}_{01}(H\otimes 1) \ayraç{00} = \frac{1}{\sqrt{2}} \left (\demet{00} + \ayraç{11} \right), $ $

Bu ya da daha fazla karmaşıklığa sahip işlemler, hisse uygun bir şekilde bir hisse alım *Diyagramı*olarak adlandırılan görselleştirme için basit bir yöntem olduğundan harika bir sorun olması gerekir.
Bu en yüksek düzeyde değerlendirme için devre diyagramı şu şekilde hazırlanıyor:

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
en yüksek düzeyde bir entangled bit durumu için ![devre diyagramı](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a>Hisse devre diyagramı kuralları
Hisse için bu görsel dil, bir hisse devresini ifade eden kuralları anladıktan sonra eşdeğer matrisinin yazılmasından daha kolay digestible olabilir.
Aşağıda bu kuralları gözden geçiririz.

Devre diyagramında, her katı çizgi bir qubit veya daha fazla genel olarak bir qubit kaydı gösterir.
Kurala göre, üst çizgi qubit yazmaç $0 $ ' dir ve geri kalan değerler sırayla etiketlenir. Yukarıdaki örnek bağlantı hattı iki qubit üzerinde (veya bir qubitden oluşan equivalently iki kayıt) üzerinde işlem görecek şekilde gösterilmiştir.
Bir veya daha fazla qubit kayıt üzerinde işlem gören kapıları kutu olarak gösterilir.
Örneğin, simge

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
tek qubit kayıt üzerinde işlem gören Hadamard işlemi için ![sembol](~/media/concepts_2.png)

, tek qubit kayıt üzerinde işlem gören bir [Hadamard](xref:microsoft.quantum.intrinsic.h) işlemidir.

Hisse kapıları, ilk olarak qubits 'e uygulanan kapıda en sol geçit ile kronolojik sırada sıralanır.
Diğer bir deyişle, kapıların hisse durumunu tutan şekilde fotoğrafını yaparsanız, kablolar diyagramdaki her bir kapıdan, soldan sağa doğru hisse ma durumunu getirir.
Yani 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
soldan sağa uygulanan hisse kapıların diyagramı ![](~/media/concepts_3.png)

Unitary matris $CBA $ ' dir.
Matris çarpıtına ters kural: en sağdaki matris önce uygulanır. Ancak, bu arada en sol kapı, en sol kapı için uygulanır.
Bu fark, her zaman karışıklığa yol açabilir, bu nedenle doğrusal cebirsel gösterimi ve hisse senedi devre şemaları arasında önemli bir farklılık olduğunu fark etmek önemlidir.

## <a name="inputs-and-outputs-of-quantum-circuits"></a>Hisse devreleri giriş ve çıkışları
Verilen tüm önceki örneklerde, hisse kapıdan alınan kabloların sayısı kadar hisse kapıda aynı sayıda kablo (qubit) girişi gerekiyordu.
Bu ilk olarak, hisse devrelerin genel olarak girdilerden daha fazla veya daha az çıkış sahibi olabileceği makul görünebilir.
Ancak tüm hisse işlemleri, ölçümü Kaydet, Unitary ve bu nedenle ters çevrilebilir olduğundan bu olanaksızdır.
Girişlerle aynı sayıda çıkışı yoksa, geri alınamaz ve bu nedenle bir çelişki olan Unitary değildir.
Bu nedenle, bir devre diyagramında çizilen her kutu, tam olarak onunla aynı sayıda kabloda yer almalıdır.

Multi-qubit devre şemaları, tek qubit olanlara benzer kuralları izler.
Bir açıklığa kavuşturan örnek olarak, $ (H \ saat X) $ $ $ $ (H \ saat X) $ $ $ (H \ saat X) $ olarak $B

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
iki-qubit Unitary işleminin devre diyagramı ![](~/media/concepts_4.png)

Ayrıca, devre dışı bırakıldığına bağlı olarak 2 1-qubit kayıtları yerine tek bir iki-qubit kayıt üzerinde eyleme sahip $B $ ' i de görüntüleyebiliriz. Bu tür soyut devre diyagramlarından en yararlı özellik, karmaşık hisse algoritmalarının, bunları temel kapıları derlemek zorunda kalmadan yüksek düzeyde açıklanmasına izin vermesidir.
Bu, algoritmadaki her bir alt yordamların nasıl çalıştığı hakkında tüm ayrıntıları anlamak zorunda kalmadan, büyük bir hisse algoritması için veri akışı hakkında bir bilgi edinebilirsiniz.

## <a name="controlled-gates"></a>Denetlenen kapıları
Multi-qubit hisse devresini içinde yerleşik olan diğer yapı denetimdir.
Tek bir qubit değerinin $G $ uygulamasını denetlediğini, belirtilen $ \Lambda (G) $, bir hisse listedir kontrollü kapıdan oluşan eylem. bir ürün durumu girişi $ \Lambda (G) (\Alpha \demet{0} + \ Beta \ demet{1}) \ket{\psı} = \Alpha \tus{0} \ket{\psı} + \beta \ demet{1} G\tus{\ PSI} $ örneğine bakarak anlaşılabiliyor.
Yani, denetlenen kapı $ \psı $ öğesini içeren Register 'a $G $, ancak yalnızca denetim qubit $1 $ değerini alırsa bu şekilde geçerlidir.
Genel olarak, bu tür denetimli işlemleri devre diyagramlarında

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
listedir kontrollü bir kapı ![devre diyagramı](~/media/concepts_5.png)

Burada siyah daire, kapıın kontrol edeceği hisse bitini ve bir dikey tel, denetim qubit $1 $ değerini alırken uygulanan Unitary 'ı gösterir.
$G = X $ ve $G = Z $ olan özel durumlar için, kapıların denetlenen sürümünü (denetlenen-X kapısı [$CNOT $ Gate](xref:microsoft.quantum.intrinsic.cnot)olduğunu unutmayın) anlatmak için aşağıdaki gösterimi tanıtıldık:

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
denetlenen kapıların özel durumları için devre diyagramı ![](~/media/concepts_6.png)

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
ölçüm işlemini temsil eden ![sembol](~/media/concepts_7.png)

Q # Bu amaçla bir [Ölçü işleci](xref:microsoft.quantum.intrinsic.measure) uygular.
Daha fazla bilgi için [ölçümlerle ilgili bölüme](xref:microsoft.quantum.libraries.standard.prelude#measurements) bakın.

Benzer şekilde, subdevı

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
denetlenen işlemi temsil eden ![devre diyagramı](~/media/concepts_8.png)

$G $ değerinin klasik denetim bit değeri $1 $ değerine göre uygulandığı, bir sınıf denetimli geçit sağlar.

## <a name="teleportation-circuit-diagram"></a>Teleporsyon devre diyagramı
[Hisse teleporsyon](xref:microsoft.quantum.techniques.puttingittogether) , bu bileşenleri göstermek için büyük olasılıkla en iyi hisse algoritmadır.
Hisse salarasyon, entanglement ve ölçüm kullanımı aracılığıyla bir hisse bilgisayarı içindeki verileri (ya da bir hisse ağı içindeki uzak hisse bilgisayarları arasında) taşımak için kullanılan bir yöntemdir.
Her ne kadar, bu, bir derece bitden diğerine, bir qubit 'in değerinin ne olduğunu bilmeksizin, belirli bir qubit içindeki değeri bir ile diğerine söylemeden, gerçekten de bir hisse cısına geçiş yeteneğine sahiptir!
Bu, protokol için hisse uzayı yasaları uyarınca çalışması için gereklidir.
Hisse ve teleporsyon devresi aşağıda verilmiştir; Ayrıca, hisse öğesinin nasıl okunacağını göstermek için devresinin açıklamalı bir sürümünü sunuyoruz.

<!--- ![](.\media\tp2.svg){ width=50% } --->
![hisse teleporsyon devresi](~/media/concepts_tp2.png)
