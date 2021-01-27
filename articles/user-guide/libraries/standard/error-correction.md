---
title: Standart kitaplıklarda hata düzeltme Q#
description: Q#Qubits 'in durumunu korurken programlarınızda hata düzeltme kodlarını nasıl kullanacağınızı öğrenin.
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: fc8e46aa22cb2575de42cfc3d4f57c43e5d3f7b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857203"
---
# <a name="error-correction"></a>Hata Düzeltme #

## <a name="introduction"></a>Giriş ##

Klasik bilgi işlem 'da, bir bit hataları hatalara karşı korumak istiyorsa, veri bitini tekrarlayarak bu bit, *mantıksal bir bite* göre temsil etmek için genellikle yeterli olur.
Örneğin, 0 {0} durumundaki bir bit kodlama olduğunu göstermek için 0 etiketinin üzerindeki bir satırı kullandığımızda $ \ üst çizgi = $0, veri biti 0 ' ın kodlaması olmalıdır.
Aynı şekilde $ \üst çizgi = $111 olmasına izin vermemiz durumunda {1} , bir bit Çevirme hatası ile korunan basit bir yineleme kodu sunuyoruz.
Diğer bir deyişle, üç bitten herhangi biri çevrildeyse, büyük bir oy alarak mantıksal bit durumunu kurtarabiliriz.
Klasik hata düzeltmesi, bu belirli örnekte çok daha zengin bir konudur ( [Lint 'in kodlama teorisine giriş](https://www.springer.com/us/book/9783540641339)önerisi önerilir), yukarıdaki yineleme kodu, hisse bilgilerini koruyan olası bir sorunu işaret eder.
Yani, [hiçbir](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) bireysel bilgi bitini ölçyoruz ve yukarıdaki benzerleme vurguladı ile klasik kod ile büyük bir oy alıp aldığımızda, korumaya çalışmamız gereken kesin bilgileri kaybettiğimiz anlamına gelir.

Hisse birimi ayarında, ölçümün sorunlu olduğunu görüyoruz. Yukarıdaki kodlamayı yine de uygulayabiliriz.
Bu, hisse vaya hata düzeltmesini nasıl genelleştirmemiz gerektiğini görmek için yararlıdır.
Bu nedenle, Let $ \ket{\üst çizgi {0} } = \ket {000} = \ket {0} \otimes {0} \tus\otimes {0} \tus$, ve Let $ \ket{\üst çizgi {1} } = \ket {111} $.
Daha sonra, bu, tüm girişler için yineleme kodumuzu tanımladık; Örneğin, $ \ket{\overline{+}} = (\ket{\üst çizgi {0} } + \ket{\üst çizgi {1} })/\sqrt {2} = (\tus+ {000} \ket {111} )/\sqrt {2} $.
Özellikle, bir bit çevirme hatasına $X _1 $, orta qubit üzerinde çalışır, her iki dalda da gereken düzeltme tam olarak $X _1 $: $ $ \begin{hizalaması} X_1 \ket{\overline{+}} & = \frac {1} {\sqrt {2} } \left (X_1 {000} \tus+ X_1 \ket {111} \ right) \\ \\ & = \frac {1} {\sqrt {2} } \left ( {010} \tus+ {101} \tus\right).
\end{hizalaması} $ $

Bu durumun, korumaya çalışmamız gereken çok durumu ölçmeden nasıl belirleyebileceklerini öğrenmek için, her farklı bit çevirme hatasının mantıksal durumlarımızla ne kadar olduğunu belirlemek yararlı olur:

| Hata $E $ | $E \ket{\üst çizgi {0} } $ | $E \ket{\üst çizgi {1} } $ |
| --- | --- | --- |
| $ \ cıvabitti $ | $ \ ayraç {000} $ | $ \ ayraç {111} $ |
| $X _0 $ | $ \ ayraç {100} $ | $ \ ayraç {011} $ |
| $X _1 $ | $ \ ayraç {010} $ | $ \ ayraç {101} $ |
| $X _2 $ | $ \ ayraç {001} $ | $ \ ayraç {110} $ |

Kodyaptığımız durumu korumak için, üç hatayı birbirleriyle ve $ \boldone $ kimliğiyle $ \ket{\üst çizgi {0} } $ ve $ \ket{\üst çizgi} $ arasında ayrım yapmadan ayırt edebilmemiz gerekiyor {1} .
Örneğin, $Z _0 $ değerini ölçyoruz, hiçbir hata durumunda $ \ket{\üst çizgi {0} } $ ve $ \ket{\üst çizgi} $ için farklı bir sonuç elde ediyoruz ve {1} Bu nedenle kodlanmış durumu daraldık.
Diğer taraftan, her bir hesaplama tabanlı durumda $Z _0 Z_1 $, ilk iki bitin eşlik düzeyini ölçmeye göz önünde bulundurun.
Pauli işlecinin her ölçüsünün, ölçülen durumun hangi eigenvalue 'a karşılık geldiğini denetlediğini, yukarıdaki tabloda $ \ket{\psı} $ ' ın her bir durumu için, yukarıdaki tabloda yer alan her durum $ \ma{\psi} $ ' ın, $ \pm\ket{\psı} $ olup olmadığını görmek için $Z _0 Z_1 \ket
{000} {000} {111} {111} Bu ölçünün her iki kodlanmış duruma de aynı şeyi gerçekleştirmemiz için, $Z _0 Z_1 \tus= \ket $ ve bu $Z _0 Z_1 \ket = \ket $ olduğunu unutmayın.
Diğer taraftan, $Z _0 Z_1 {100} \tus=-\ket {100} $ ve $Z _0 Z_1 \tus= {011} -\ket {011} $, bu nedenle $Z _0 Z_1 $ ölçmesi sonucu oluşan hata oluştuğunda yararlı bilgileri ortaya çıkarır.

Bunu vurgulamak için yukarıdaki tabloyu yineliyoruz, ancak her satırda $Z _0 Z_1 $ ve $Z _1 Z_2 $ ölçüm sonuçlarını eklersiniz.
Her ölçümün sonucunu, Q# `Result` `Zero` sırasıyla, ve değerlerine karşılık gelen $ + $ veya $-$ gibi gözlemlenen eigenvalue işaretine göre gösterir `One` .

| Hata $E $ | $E \ket{\üst çizgi {0} } $ | $E \ket{\üst çizgi {1} } $ | Sonuç olarak $Z _0 Z_1 $ | $Z _1 Z_2 $ sonucu |
| --- | --- | --- | --- | --- |
| $ \ cıvabitti $ | $ \ ayraç {000} $ | $ \ ayraç {111} $ | $+$ | $+$ |
| $X _0 $ | $ \ ayraç {100} $ | $ \ ayraç {011} $ | $-$ | $+$ |
| $X _1 $ | $ \ ayraç {010} $ | $ \ ayraç {101} $ | $-$ | $-$ |
| $X _2 $ | $ \ ayraç {001} $ | $ \ ayraç {110} $ | $+$ | $-$ |

Bu nedenle, iki ölçümün sonuçları, hangi bit çevirme hatasının oluştuğunu benzersiz olarak belirler, ancak hangi durumu kodladığımızda bilgi vermeksizin.
Bu sonuçlara bir *sendromu* çağrısı yaptık ve bir sendromu 'yi *Kurtarma* olarak neden olan hataya geri eşleme sürecine başvurduk.
Özellikle, kurtarma işlemi, oluşan sendromu girişi olarak geçen bir *Klasik* çıkarım prosedürü ve oluşmuş olabilecek hataların nasıl düzeltileceğiyle ilgili bir hata döndürür.

> [!NOTE]
> Yukarıdaki bit çevirme kodu yalnızca tek bit çevirme hatalarına karşı doğru olabilir; diğer bir deyişle, `X` tek bir qubit üzerinde işlem gören bir işlemdir.
> Birden `X` fazla qubit 'e uygulamak, şu kurtarma sonrasında $ \ket{\üst çizgi {0} } $ değerini $ \ket{\üst çizgi {1} } $ olarak eşleştirir.
> Benzer şekilde, bir aşama çevirme işleminin uygulanması `Z` $ \ket{\üst çizgi {1} } $ $-\ket{\üst çizgi} $ olarak eşlenir {1} ve bu nedenle $ \ket{\overline{+}} $ ile $ \ket{\üst çizgi} $ arasında eşleme olur {-} .
> Genellikle, daha fazla hata sayısını işlemek ve $Z $ hata ve $X $ hatası işlemek için kodlar oluşturulabilir.

Ölçümleri, tüm kod durumlarında aynı şekilde davranan hisse hata düzeltmesine ilişkin ölçümleri anlayabiliriz *.*
Q#Canon, sabitleyici kodlardan kodlama ve kod çözme hakkında bir çerçeve sağlar ve bir hata durumundan nasıl kurtardığını tanımlar.
Bu bölümde, bu Framework 'ü ve uygulamayı birkaç basit hisse hata düzeltme koduna anladık.

> [!TIP]
> Sabitleyici formalroni'ya tam giriş, bu bölümün kapsamının dışındadır.
> [Gottesman 2009](https://arxiv.org/abs/0904.2557)' ye daha fazla bilgi edinmek isteyen okuyucular hakkında bilgi veririz.

## <a name="representing-error-correcting-codes-in-no-locq"></a>İçindeki hata düzeltme kodlarını temsil etme Q# ##

Canon, hata düzeltme kodları belirtmeye yardımcı olmak için Q# birkaç farklı Kullanıcı tanımlı tür sağlar:

- <xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister>`= Qubit[]`: Bir qubits kaydının bir hata düzeltme kodunun kod bloğu olarak yorumlanması gerektiğini gösterir.
- <xref:Microsoft.Quantum.ErrorCorrection.Syndrome>`= Result[]`: Bir ölçüm sonuçları dizisinin, bir kod bloğunda ölçülen sendromu olarak yorumlanması gerektiğini gösterir.
- <xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn>`= (Syndrome -> Pauli[])`: Bir eşitleniyor işlevinin  , bir sendromu yorumlamak ve uygulanması gereken bir düzeltme döndürmesi için kullanılması gerektiğini belirtir.
- <xref:Microsoft.Quantum.ErrorCorrection.EncodeOp>`= ((Qubit[], Qubit[]) => LogicalRegister)`: Bir işlemin bir hata düzeltme kodunun kod bloğunu oluşturmak için, verileri yeni Andalla qubits ile birlikte temsil eden bir işlem olduğunu gösterir.
- <xref:Microsoft.Quantum.ErrorCorrection.DecodeOp>`= (LogicalRegister => (Qubit[], Qubit[]))`: Bir işlemin kod bloğunu, verileri veri qubits 'e düzeltmede hata kodu bloğunu ve sendromu bilgilerini temsil etmek için kullanılan anetla qubits 'i temsil ettiğini belirtir.
- <xref:Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp>`= (LogicalRegister => Syndrome)`: Kod tarafından korunan durumu etkilemeden, bir kod bloğunun sendromu bilgilerini ayıklamak için kullanılması gereken bir işlemi gösterir.

Son olarak, Canon <xref:Microsoft.Quantum.ErrorCorrection.QECC> bir hisse hata düzeltme kodu tanımlamak için gereken diğer türleri toplamak üzere tür sağlar. Her bir sabitleyici hisse ıcı kodu ile ilişkili kod uzunluğu $n $, mantıksal qubit sayısı $k $, ve en düşük uzaklık $d $, genellikle ⟦ $n $, $k $, $d $ ⟧ gösteriminde kolay bir şekilde gruplanırlar. Örneğin, <xref:Microsoft.Quantum.ErrorCorrection.BitFlipCode> işlevi ⟦ 3, 1, 1 ⟧ bit çevirme kodunu tanımlar:

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

`QECC`Türün bir kurtarma işlevi içermediğinden *emin* olun.
Bu, kodun kendi tanımını değiştirmeden hataları düzeltmek için kullanılan kurtarma işlevini değiştirememize olanak sağlar; Bu özellik, karakter seçme ölçümlerinden geri bildirim kurtarma tarafından kabul edilen modele dahil edildiğinde özellikle kullanışlıdır.

Bir kod bu şekilde tanımlandıktan sonra, <xref:Microsoft.Quantum.ErrorCorrection.Recover> hataları kurtarmak için işlemi kullanabiliriz:

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

Bu, [bit çevirme kod örneğinde](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code)daha ayrıntılı bir şekilde araştırıyoruz.

Bit çevirme kodundan başlayarak, Q# Canon, [beş qubit kusursuz kodun](https://arxiv.org/abs/quant-ph/9602019)uygulamalarıyla ve her ikisi de rastgele bir tek qubit hatayı düzeltebilen [yedi-qubit kod](https://arxiv.org/abs/quant-ph/9705052)uygulamalarıyla birlikte sağlanır.
