---
title: 'Q # standart kitaplıkları-hata düzeltme | Microsoft Docs'
description: 'Q # standart kitaplıkları-hata düzeltme'
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: e1b78cf94ae0a043ad275d4cb06b230eafd7fc85
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74863206"
---
# <a name="error-correction"></a>Hata Düzeltme #

## <a name="introduction"></a>Tanıtım ##

Klasik bilgi işlem 'da, bir bit hataları hatalara karşı korumak istiyorsa, veri bitini tekrarlayarak bu bit, *mantıksal bir bite* göre temsil etmek için genellikle yeterli olur.
Örneğin, 0 durumundaki bir bit kodlama olduğunu göstermek için 0 etiketinin üzerindeki bir satırı kullandığımızda $ \üstünü{0} = $0, veri biti 0 kodlaması olmalıdır.
Aynı şekilde $ \üst çizgi{1} = $111 olmasına izin verdiğimiz takdirde, herhangi bir bit çevirme hatasına karşı koruyan basit bir yineleme kodu sunuyoruz.
Diğer bir deyişle, üç bitten herhangi biri çevrildeyse, büyük bir oy alarak mantıksal bit durumunu kurtarabiliriz.
Klasik hata düzeltmesi, bu belirli örnekte çok daha zengin bir konudur ( [Lint 'in kodlama teorisine giriş](https://www.springer.com/us/book/9783540641339)önerisi önerilir), yukarıdaki yineleme kodu, hisse bilgilerini koruyan olası bir sorunu işaret eder.
Yani, [hiçbir](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) bireysel bilgi bitini ölçyoruz ve yukarıdaki benzerleme vurguladı ile klasik kod ile büyük bir oy alıp aldığımızda, korumaya çalışmamız gereken kesin bilgileri kaybettiğimiz anlamına gelir.

Hisse birimi ayarında, ölçümün sorunlu olduğunu görüyoruz. Yukarıdaki kodlamayı yine de uygulayabiliriz.
Bu, hisse vaya hata düzeltmesini nasıl genelleştirmemiz gerektiğini görmek için yararlıdır.
Bu nedenle, $ \ket{\üst çizgi{0}} = \demet{000} = \ayraç{0} \otimes \demet{0} \otimes \tus{0}$, ve Let $ \ket{\üst çizgi{1}} = \tus{111}$.
Daha sonra, bu, tüm girişler için yineleme kodumuzu tanımladık; Örneğin, $ \ket{\overline{+}} = (\ket{\üst{0}} + \ket{\üst çizgi{1}})/\sqrt{2} = (\tus{000} + \tus{111})/\sqrt{2}$.
Özellikle, bir bit Çevirme hatası $X _1 $ 'ın ortadaki qubit üzerinde işlem yapmasına izin vermek için her iki dalda de gerekli düzeltmenin tam olarak $X _1 $: $ $ \begin{hizalaması} X_1 \ket{\overline{+}} & = \frac{1}{\sqrt{2}} \left (X_1 \tus{000} + X_1 \tus{111} \right) \\\\ & = \frac{1}{\sqrt{2}} \left (\tus{010} + \tus{101} \ right).
\end{hizalaması} $ $

Bu durumun, korumaya çalışmamız gereken çok durumu ölçmeden nasıl belirleyebileceklerini öğrenmek için, her farklı bit çevirme hatasının mantıksal durumlarımızla ne kadar olduğunu belirlemek yararlı olur:

| Hata $E $ | $E \ket{\üst çizgi{0}} $ | $E \ket{\üst çizgi{1}} $ |
| --- | --- | --- |
| $ \ cıvabitti $ | $ \demet{000}$ | $ \demet{111}$ |
| $X _0 $ | $ \demet{100}$ | $ \demet{011}$ |
| $X _1 $ | $ \demet{010}$ | $ \demet{101}$ |
| $X _2 $ | $ \demet{001}$ | $ \demet{110}$ |

Koddığımız durumu korumak için, {\ket{\üst{0}} $ ve $ \ket{\üst çizgi{1}} $ arasında ayrım yapmadan üç hatayı birbirleriyle ve $ \cıvadone $ kimliğiyle ayırt edebilmemiz gerekir.
Örneğin, $Z _0 $ değerini ölçyoruz, hiçbir hata durumunda $ \ket{\üst çizgi{0}} $ ve $ \ket{\üst çizgi{1}} $ için farklı bir sonuç elde ediyoruz ve bu nedenle kodlanmış durumu daraldık.
Diğer taraftan, her bir hesaplama tabanlı durumda $Z _0 Z_1 $, ilk iki bitin eşlik düzeyini ölçmeye göz önünde bulundurun.
Pauli işlecinin her ölçüsünün, ölçülen durumun hangi eigenvalue 'a karşılık geldiğini denetlediğini, yukarıdaki tabloda $ \ket{\psı} $ ' ın her bir durumu için, yukarıdaki tabloda yer alan her durum $ \ma{\psi} $ ' ın, $ \pm\ket{\psı} $ olup olmadığını görmek için $Z _0 Z_1 \ket
Bu ölçümün her iki kodlanmış duruma de aynı şeyi gerçekleştirmemiz için $Z _0 Z_1 \ayraç{000} = \demet{000}$ $Z Z_1 _0{111} \tus{111}= \tus $ olduğunu unutmayın.
Diğer taraftan, $Z _0 Z_1 \ayraç{100} =-\tus{100}$ ve $Z _0 Z_1 \ayraç{011} =-\tus{011}$, bu nedenle $Z _0 Z_1 $ ölçmesi sonucu oluşan hata oluştuğunda yararlı bilgileri ortaya çıkarır.

Bunu vurgulamak için yukarıdaki tabloyu yineliyoruz, ancak her satırda $Z _0 Z_1 $ ve $Z _1 Z_2 $ ölçüm sonuçlarını eklersiniz.
Her ölçümün sonucunu, sırasıyla, `Zero` ve `One`'nin Q # `Result` değerlerine karşılık gelen $ + $ veya $-$ şeklinde gözlemlenen eigenvalue değerinin işaretine göre gösterir.

| Hata $E $ | $E \ket{\üst çizgi{0}} $ | $E \ket{\üst çizgi{1}} $ | Sonuç olarak $Z _0 Z_1 $ | $Z _1 Z_2 $ sonucu |
| --- | --- | --- | --- | --- |
| $ \ cıvabitti $ | $ \demet{000}$ | $ \demet{111}$ | $+$ | $+$ |
| $X _0 $ | $ \demet{100}$ | $ \demet{011}$ | $-$ | $+$ |
| $X _1 $ | $ \demet{010}$ | $ \demet{101}$ | $-$ | $-$ |
| $X _2 $ | $ \demet{001}$ | $ \demet{110}$ | $+$ | $-$ |

Bu nedenle, iki ölçümün sonuçları, hangi bit çevirme hatasının oluştuğunu benzersiz olarak belirler, ancak hangi durumu kodladığımızda bilgi vermeksizin.
Bu sonuçlara bir *sendromu*çağrısı yaptık ve bir sendromu 'yi *Kurtarma*olarak neden olan hataya geri eşleme sürecine başvurduk.
Özellikle, kurtarma işlemi, oluşan sendromu girişi olarak geçen bir *Klasik* çıkarım prosedürü ve oluşmuş olabilecek hataların nasıl düzeltileceğiyle ilgili bir hata döndürür.

> [!NOTE]
> Yukarıdaki bit çevirme kodu yalnızca tek bit çevirme hatalarına karşı doğru olabilir; diğer bir deyişle, tek bir qubit üzerinde işlem gören `X` bir işlemdir.
> Birden fazla qubit 'e `X` uygulamak, $ \ket{\üst çizgi{0}} $ öğesini $ \ket{\üst çizgi{1}} $ ile Şu kurtarma için eşleştirir.
> Benzer şekilde, bir aşama çevirme işleminin uygulanması `Z` $ \ket{\üst çizgi{1}} $ $-\ket{\üst çizgi{1}} $ olarak eşlenir ve bu nedenle $ \ket{\overline{+}} $ ile $ \ket{\üst çizgi{-}} $ arasında eşleme olur.
> Genellikle, daha fazla hata sayısını işlemek ve $Z $ hata ve $X $ hatası işlemek için kodlar oluşturulabilir.

Ölçümleri, tüm kod durumlarında aynı şekilde davranan hisse hata düzeltmesine ilişkin ölçümleri anlayabiliriz *.*
Q # Canon, sabitleyici kodlardan kodlama ve kod çözme hakkında bir çerçeve sağlar ve bir hata durumundan nasıl kurtardığını tanımlar.
Bu bölümde, bu Framework 'ü ve uygulamayı birkaç basit hisse hata düzeltme koduna anladık.

> [!TIP]
> Sabitleyici formalroni'ya tam giriş, bu bölümün kapsamının dışındadır.
> [Gottesman 2009](https://arxiv.org/abs/0904.2557)' ye daha fazla bilgi edinmek isteyen okuyucular hakkında bilgi veririz.

## <a name="representing-error-correcting-codes-in-q"></a>Q 'daki hata düzeltme kodlarını temsil etme # ##

Q # Canon, hata düzeltme kodları belirtmeye yardımcı olmak için birkaç farklı Kullanıcı tanımlı tür sağlar:

- <xref:microsoft.quantum.errorcorrection.logicalregister> `= Qubit[]`: bir qubits kaydının bir hata düzeltme kodunun kod bloğu olarak yorumlanması gerektiğini gösterir.
- <xref:microsoft.quantum.errorcorrection.syndrome> `= Result[]`: bir ölçüm sonuçları dizisinin, bir kod bloğunda ölçülen sendromu olarak yorumlanması gerektiğini gösterir.
- <xref:microsoft.quantum.errorcorrection.recoveryfn> `= (Syndrome -> Pauli[])`: bir *Klasik* işlevin, bir sendromu yorumlamak için kullanılması gerektiğini ve uygulanması gereken bir düzeltme döndürmesi gerektiğini belirtir.
- <xref:microsoft.quantum.errorcorrection.encodeop> `= ((Qubit[], Qubit[]) => LogicalRegister)`: bir işlemin bir hata düzeltme kodunun kod bloğunu oluşturmak için yeni Andalla qubits ile birlikte verileri temsil eden qubits aldığını gösterir.
- <xref:microsoft.quantum.errorcorrection.decodeop> `= (LogicalRegister => (Qubit[], Qubit[]))`: bir işlemin kod bloğunu, verileri veri qubits 'e düzeltme hatası ve sendromu bilgilerini temsil etmek için kullanılan anetla qubits.
- <xref:microsoft.quantum.errorcorrection.syndromemeasop> `= (LogicalRegister => Syndrome)`: kod tarafından korunan durumu etkilemeden bir kod bloğundan sendromu bilgilerini ayıklamak için kullanılması gereken bir işlemi gösterir.

Son olarak, Canon, bir hisse hata düzeltme kodu tanımlamak için gereken diğer türleri toplamak üzere <xref:microsoft.quantum.errorcorrection.qecc> türünü sağlar. Her bir sabitleyici hisse ıcı kodu ile ilişkili kod uzunluğu $n $, mantıksal qubit sayısı $k $, ve en düşük uzaklık $d $, genellikle ⟦ $n $, $k $, $d $ ⟧ gösteriminde kolay bir şekilde gruplanırlar. Örneğin, <xref:microsoft.quantum.errorcorrection.bitflipcode> işlevi ⟦ 3, 1, 1 ⟧ bit çevirme kodunu tanımlar:

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

`QECC` türünün bir kurtarma *işlevi içermediğinden emin* olun.
Bu, kodun kendi tanımını değiştirmeden hataları düzeltmek için kullanılan kurtarma işlevini değiştirememize olanak sağlar; Bu özellik, karakter seçme ölçümlerinden geri bildirim kurtarma tarafından kabul edilen modele dahil edildiğinde özellikle kullanışlıdır.

Bir kod bu şekilde tanımlandıktan sonra, hatalardan kurtulmak için <xref:microsoft.quantum.errorcorrection.recover> işlemini kullanabiliriz:

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

Bu, [bit çevirme kod örneğinde](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code)daha ayrıntılı bir şekilde araştırıyoruz.

Bit çevirme kodundan başlayarak, Q # Canon, [beş qubit kusursuz kodun](https://arxiv.org/abs/quant-ph/9602019)uygulamalarıyla ve her ikisi de rastgele bir tek qubit hatayı düzeltebilen [yedi-qubit kodu](https://arxiv.org/abs/quant-ph/9705052)ile sağlanır.
