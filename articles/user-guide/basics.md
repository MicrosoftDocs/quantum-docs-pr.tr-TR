---
title: 'S # temel kavramları'
description: 'Soru-cevap için temel kavramlar #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: 45e6f2f33dafc2aec177091d3cfa94aca14fbf0a
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415379"
---
# <a name="q-basics"></a>S # temel kavramları

Bu makalede, Q # temel yapı taşlarına kısa bir giriş sunulmaktadır.

Her ne tür bir genel bakış için, hisse geliştirme seti 'nin temel bir bileşeni olarak hangi noktada uyduğunu öğrenmek için bkz. [soru-cevap nedir?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Hisse bir program nedir?

Teknik açıdan, hisse, çağrıldığında, belirli işlemleri bir hisse sisteminde gerçekleştirirken belirli bir klasik alt yordam kümesidir.
Bu görünümün önemli bir sonucu, bir Q # programının qubits 'i doğrudan modelleyemediğini, ancak bunun yerine, belirli bir şekilde denetlenen bilgisayarın bu qubits ile nasıl etkileşime gireceğini açıklar.
Tasarıma göre, soru-cevap ' ı doğrudan hisse veya diğer özellikleri tanımlamaz.
Örneğin, hisse bilgi Işlem kavramları kılavuzunda $ \ket{+} = \left (\ket {0} + \ket {1} \ right)/\sqrt $ durumunu göz önünde bulundurun {2} . [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro)
Bu durumu Q # ' da hazırlamak için, qubits 'in $ \ket $ durumunda başlatıldığı olgularla başlayın {0} ve bu $ \ket{+} = H\ket {0} $, burada $H $, [ `H` Işlem](xref:microsoft.quantum.intrinsic.h)tarafından uygulanan [Hadamard Transform](xref:microsoft.quantum.glossary#hadamard)şeklindedir. Bir qubit başlatmak ve dönüştürmek için temel Q # kodu, daha sonra şöyle görünür:

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
Başlatma veya *ayırma*hakkında daha fazla bilgi için bkz. [qubits ile çalışma](xref:microsoft.quantum.guide.qubits).

## <a name="quantum-states-in-q"></a>Soru-cevap durumu #

Daha önemlisi, önceki program, Q # içindeki duruma açıkça başvurmaz ancak programımızın durumu nasıl *dönüştürdüğünü* açıklamaz.
Bu yaklaşımda, her bir hedef makinede bile, makineye bağlı farklı yorumlamalar olabilecek, her bir bir hisse amadığına ilişkin olarak ne *kadar büyük bir işlem olduğu* hakkında tamamen belirsiz bir durum söz konusu olabilir. 

Bir Q # programı bir qubit durumuna introspect.
Bunun yerine, bir program [`Measure`](xref:microsoft.quantum.intrinsic.measure) qubit 'ten bilgi almak için gibi işlemleri çağırabilir ve [`X`](xref:microsoft.quantum.intrinsic.x) [`H`](xref:microsoft.quantum.intrinsic.h) bir qubit durumu üzerinde işlem yapmak için ve gibi işlemleri çağırabilir.
Bu *işlemlerin gerçekten ne* olduğu, yalnızca belirli Q # programını çalıştırmak için kullanılan hedef makine tarafından somut hale getirilir.
Örneğin, programı [tam durum benzeticimizde](xref:microsoft.quantum.machines.full-state-simulator)çalıştırırsanız simülatör, sanal hisse sisteme karşılık gelen matematiksel işlemleri gerçekleştirir.
Ancak geleceğe bağlı olarak, hedef makine gerçek bir hisse bilgisayar olduğunda, Q # içinde bu gibi işlemleri çağırmak, hisse bilgisayarını *Gerçek* hisse sisteminde ilgili *gerçek* işlemleri gerçekleştirmek üzere yönlendirir, örneğin, tam olarak süreli lazer darbeleri.

Bir Q # programı, Express hisse hesaplamasına yeni ve daha üst düzey işlemler oluşturmak için bu işlemleri bir hedef makine tarafından tanımlanan şekilde yeniden birleştirir.
Bu şekilde, Q #, temel alınan hisse ve hibrit, klasik algoritmaların yanı sıra bir hedef makine ya da simülatör yapısına göre genel de olacak şekilde ifade yapmayı kolaylaştırır.

## <a name="q-operations-and-functions"></a>S # işlem ve işlevleri

Bir Q # programı, *işlemler*, *işlevler*ve Kullanıcı tanımlı türler içerir. 

İşlemler, hisse sistemleri dönüştürmelerini ve en temel yapı bloğu olan Q # programlarını anlatmak için kullanılır. Q # içinde tanımlanan her işlem, diğer birkaç işlemi çağırabilir.

İşlemlere karşılık işlevler, yalnızca *belirleyici* klasik davranışı betimleyen ve klasik değerleri hesaplama konusunda herhangi bir etkiye sahip olmayan işlevler için kullanılır. Örneğin, bir programın sonundaki qubits 'i ölçmek istediğinizi ve ölçüm sonuçlarının bir diziye ekleneceğini varsayın.
Bu durumda, `Measure` hedef makinenin (gerçek veya sanal) qubit üzerinde bir ölçü gerçekleştirmesini sağlayan bir *işlemdir* . Aynı zamanda *işlevler* , döndürülen sonuçları bir diziye eklemek için klasik işlemi işler.

Birlikte, işlemler ve işlevler *callables*olarak bilinir. Temel yapısı ve davranışları, [Q # ' daki işlemler ve işlevlerde](xref:microsoft.quantum.guide.operationsfunctions)tanıtılmıştır ve ayrıntılıdır.


## <a name="q-syntax-overview"></a>S # sözdizimine genel bakış

Bir dilin sözdizimi, sözdizimi doğru bir program oluşturan farklı sembol birleşimlerini tanımlar.
Q # ' da, söz dizimi öğeleri üç farklı gruba sınıflandırılır: türler, ifadeler ve deyimler.

### <a name="types"></a>Türler
S #, türlerin dikkatli kullanımı derleyicinin derleme zamanında Q # programları hakkında güçlü garantiler sağlamasına yardımcı olabilir.
Standart ve hisse özel yerleşik temel türlerin yanı sıra,,, ve,,,, `Int` `Bool` `Qubit` ve `Result` ,,

Tüm ilkel türlerin açıklamaları, dizi ve demet türlerine ilişkin ayrıntılar ve bir Q # dosyası içinde yeni türler tanımlama adımları için, bkz. [q # türleri](xref:microsoft.quantum.guide.types).

### <a name="expressions"></a>İfadeler
Programlama dilindeki bir ifade, programlama dilinin belirli bir değeri yorumlaması ve değerlendiren bir veya daha fazla sabitler, değişkenler, işleçler ve işlevlerin bir birleşimidir.
Çoğu durumda, bir dildeki her tür için, bu türdeki ifadeler, bu türdeki bir değere göre *değişmez* değer ya da semboller olabilir.
Örneğin, `5` bir değişmez değerdir `Int` (Bu nedenle türünde bir ifade `Int` ) ve sembol `count` tamsayı değerine bağlıysa, `5` `count` Ayrıca bir tamsayı ifadesi de olur.

Ayrıca, bir ifade belirli işleçlerle birleştirilmiş diğer ifadelerden oluşabilir.
Örneğin, `Int` olarak değerlendirilen başka bir ifade `5` `2+3` .

Q # içindeki ifadeler ve uyumlu işleçler hakkında daha fazla bilgi için bkz. [q # Içinde tür ifadeleri](xref:microsoft.quantum.guide.expressions). 

### <a name="statements"></a>Deyimler 
Bir ifade, gerçekleştirilecek bir eylemi ifade eden bir zorunlu programlama dilinin sözdizimsel birimidir. Bu deyimlerdeki ifadelerle karşıtlık ifadesi sonuçları döndürmez ve yalnızca yan etkileri için yürütülür. Ancak, ifadesi her zaman bir sonuç döndürür ve genellikle yan etkileri yoktur. Kısaca, Q # deyimleri yürütülür, ancak ifadeler değerlendirilir.

Q # içindeki bir ifadeye basit bir örnek, bir ifadeye sembol atanıyor:
```qsharp
let count = 5;
```

Daha ilginç bir örnek, `for` yinelemeyi destekleyen ve bir *Ekstre bloğunu*içeren deyimdir.
`qubits`Bir qubits (Teknik olarak tür `Qubit[]` veya bir tür dizisi) kaydına yönelik simgenin olduğunu varsayalım `Qubit` . Ardından
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
, kayıt sırasında her bir qubit üzerinde yinelenen bir ifadedir ve `H` her birinde işlem gerçekleştirilir. Bunun de `H(qubit);` bir ifade olduğunu unutmayın.

Türünde herhangi bir çağrı ifadesini kullanabilirsiniz `Unit` (bir `Unit` tür herhangi bir bilgi döndürmez), deyim olarak.
Bu tür bir ifade, `Unit` deyimin amacı örtülü hisse durumu değiştirmek olduğu için döndürülen qubits üzerinde işlemler çağrılırken faydalıdır.
İfade değerlendirme deyimleri, sonlandırma noktalı virgül gerektirir.

Bir Q # programının neredeyse her yönünü oluşturmak için deyimlerini kullanırsınız ve bunlarla ilgili tüm bilgileri kapsayamaz.
Kendi sözlü yapısı ve biçimlendirmesi hakkında daha fazla bilgi için bkz. [Q # dosya yapısı](xref:microsoft.quantum.guide.filestructure); sembol bağlama ataması ve kapsamı için bkz. [Q #; değişkenleri](xref:microsoft.quantum.guide.variables) ve gibi denetim akışı döngüleri için `for` bkz. [Q # Içindeki denetim akışı](xref:microsoft.quantum.guide.controlflow).

## <a name="next-steps"></a>Sonraki adımlar

[Q # Içindeki türler](xref:microsoft.quantum.guide.types)hakkında öğrenmeye başlayın.

Q # ' dan sonra kuruluş ve mosyon hakkında daha fazla arka plan için bkz. [neden soru-cevap veriyoruz?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).
