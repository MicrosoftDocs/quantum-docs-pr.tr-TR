---
title: Q# Temel bilgileri
description: Temel kavramları Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: b3bc0841eabeac5d3968776f9dab3a02b1a1eef9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691636"
---
# <a name="no-locq-basics"></a>Q# Temel bilgileri

Bu makalede, uygulamasının temel yapı taşları hakkında kısa bir giriş sunulmaktadır Q# .

Ne olduğuna ve ne tür bir genel bakış, Q# hisse geliştirme setinin temel bir bileşeni olarak sığıyorsa, bkz. [nedir Q# ?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Hisse bir program nedir?

Teknik açıdan, hisse, çağrıldığında, belirli işlemleri bir hisse sisteminde gerçekleştirirken belirli bir klasik alt yordam kümesidir.
Bu görünümün önemli bir sonucu Q# , bir programın yalnızca qubits 'i doğrudan modelleyemediğini, ancak bunun yerine, belirli bir şekilde denetlenen bilgisayarın bu qubits ile nasıl etkileşime gireceğini açıklar.
Tasarıma göre, Q# doğrudan hisse tlar veya diğer hisse kutları özelliklerini tanımlamaz.
Örneğin, hisse bilgi Işlem kavramları kılavuzunda $ \ket{+} = \left (\ket {0} + \ket {1} \ right)/\sqrt $ durumunu göz önünde bulundurun {2} . [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro)
Bu durumu içinde hazırlamak için Q# , qubits 'in $ \ket $ durumunda başlatıldığı olgularla başlayın {0} ve bu $ \ket{+} = H\ket {0} $, burada $H $, [ `H` Işlem](xref:Microsoft.Quantum.Intrinsic.H)tarafından uygulanan [Hadamard Transform](xref:microsoft.quantum.glossary#hadamard)şeklindedir. Q#Bir qubit başlatmak ve dönüştürmek için temel kod, ardından şöyle görünür:

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
Başlatma veya *ayırma* hakkında daha fazla bilgi için bkz. [qubits ile çalışma](xref:microsoft.quantum.guide.qubits).

## <a name="quantum-states-in-no-locq"></a>Hisse ve ABD Q#

Daha önemlisi, önceki program içindeki duruma açıkça başvurmaz Q# ancak programımızın durumu nasıl *dönüştürdüğünü* açıklamaz.
Bu yaklaşımda, her bir hedef makinede bile, makineye bağlı farklı yorumlamalar olabilecek, her bir bir hisse amadığına ilişkin olarak ne *kadar büyük bir işlem olduğu* hakkında tamamen belirsiz bir durum söz konusu olabilir. 

Bir Q# Program, qubit 'in durumuna introspect.
Bunun yerine, bir program [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) qubit 'ten bilgi almak için gibi işlemleri çağırabilir ve [`X`](xref:Microsoft.Quantum.Intrinsic.X) [`H`](xref:Microsoft.Quantum.Intrinsic.H) bir qubit durumu üzerinde işlem yapmak için ve gibi işlemleri çağırabilir.
Bu *işlemler aslında yalnızca* belirli bir programı çalıştırmak için kullanılan hedef makine tarafından somut hale getirilir Q# .
Örneğin, programı [tam durum benzeticimizde](xref:microsoft.quantum.machines.full-state-simulator)çalıştırırsanız simülatör, sanal hisse sisteme karşılık gelen matematiksel işlemleri gerçekleştirir.
Ancak geleceğe bağlı olarak, hedef makine gerçek bir hisse bilgisayar olduğunda, bu tür işlemleri çağırmak, Q# hisse bilgisayarını *Gerçek* hisse sisteminde ilgili *Gerçek* işlemleri gerçekleştirmeye yönlendirir, örneğin, tam olarak zaman aşımına uğradı.

Q#Program, bu işlemleri bir hedef makine tarafından tanımlandığı şekilde yeniden birleştirir. Express, hızlı bir şekilde yeni ve yüksek düzey işlemler oluşturur.
Bu şekilde, Q# temel alınan hisse ve hibrit-klasik algoritmaların yanı sıra bir hedef makine ya da simülatör yapısına göre genel de olan mantıksal ve karma hisse

## <a name="no-locq-operations-and-functions"></a>Q# işlemler ve işlevler

Bir Q# Program, *işlemler* , *işlevler* ve Kullanıcı tanımlı türler içerir. 

İşlemler, hisse sistemleri ve en temel yapı blobunun dönüştürmelerini anlatmak için kullanılır Q# . İçinde tanımlanan her işlem, Q# diğer birkaç işlemi çağırabilir.

İşlemlere karşılık işlevler, yalnızca *belirleyici* klasik davranışı betimleyen ve klasik değerleri hesaplama konusunda herhangi bir etkiye sahip olmayan işlevler için kullanılır. Örneğin, bir programın sonundaki qubits 'i ölçmek istediğinizi ve ölçüm sonuçlarının bir diziye ekleneceğini varsayın.
Bu durumda, `Measure` hedef makinenin (gerçek veya sanal) qubit üzerinde bir ölçü gerçekleştirmesini sağlayan bir *işlemdir* . Aynı zamanda *işlevler* , döndürülen sonuçları bir diziye eklemek için klasik işlemi işler.

Birlikte, işlemler ve işlevler *callables* olarak bilinir. Temel yapısı ve davranışları, [Içindeki Q# Işlemler ve işlevlerde ](xref:microsoft.quantum.guide.operationsfunctions)tanıtılmıştır ve ayrıntılıdır.


## <a name="no-locq-syntax-overview"></a>Q# sözdizimine genel bakış

Bir dilin sözdizimi, sözdizimi doğru bir program oluşturan farklı sembol birleşimlerini tanımlar.
' De Q# , sözdizimi öğeleri üç farklı gruba sınıflandırılır: türler, ifadeler ve deyimler.

### <a name="types"></a>Türler
Q# , türlerin iyi şekilde kullanılması derleyicinin derleme zamanında programlar hakkında güçlü garantiler sağlamasına yardımcı olabilir Q# .
Standart ve hisse özel yerleşik temel türlerin yanı sıra,,,, ve,,, `Int` , `Bool` `Qubit` ve, `Result` Q# Kullanıcı tanımlı türler için destek sağlar.

Tüm ilkel türlerin açıklamaları, dizi ve demet türlerine ilişkin ayrıntılar ve bir dosya içinde yeni türler tanımlama adımları için Q# , bkz. [türleri Q# ](xref:microsoft.quantum.guide.types).

### <a name="expressions"></a>İfadeler
Programlama dilindeki bir ifade, programlama dilinin belirli bir değeri yorumlaması ve değerlendiren bir veya daha fazla sabitler, değişkenler, işleçler ve işlevlerin bir birleşimidir.
Çoğu durumda, bir dildeki her tür için, bu türdeki ifadeler, bu türdeki bir değere göre *değişmez* değer ya da semboller olabilir.
Örneğin, `5` bir değişmez değerdir `Int` (Bu nedenle türünde bir ifade `Int` ) ve sembol `count` tamsayı değerine bağlıysa, `5` `count` Ayrıca bir tamsayı ifadesi de olur.

Ayrıca, bir ifade belirli işleçlerle birleştirilmiş diğer ifadelerden oluşabilir.
Örneğin, `Int` olarak değerlendirilen başka bir ifade `5` `2+3` .

İçindeki ifadeler ve uyumlu işleçler hakkında daha fazla bilgi için Q# bkz. [ Q# içinde tür ifadeleri ](xref:microsoft.quantum.guide.expressions). 

### <a name="statements"></a>Deyimler 
Bir ifade, gerçekleştirilecek bir eylemi ifade eden bir zorunlu programlama dilinin sözdizimsel birimidir. Bu deyimlerdeki ifadelerle karşıtlık ifadesi sonuçları döndürmez ve yalnızca yan etkileri için çalıştırılır. Ancak, ifadesi her zaman bir sonuç döndürür ve genellikle yan etkileri yoktur. Kısaca, Q# ifadeler değerlendirildiğinde deyimler çalıştırılır.

İçindeki bir ifadeye basit bir örnek Q# , bir ifadeye sembol atanıyor:
```qsharp
let count = 5;
```

Daha ilginç bir örnek, `for` yinelemeyi destekleyen ve bir *Ekstre bloğunu* içeren deyimdir.
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

Bir programın neredeyse her yönünü oluşturmak için deyimlerini kullanırsınız Q# ve bunlarla ilgili tüm bilgileri kapsayamaz.
Kendi sözlü yapısı ve biçimlendirmesi hakkında daha fazla bilgi için bkz. [ Q# dosya yapısı](xref:microsoft.quantum.guide.filestructure); sembol bağlama ataması ve kapsamı için bkz. [içindeki Q# değişkenler ](xref:microsoft.quantum.guide.variables)ve gibi denetim akışı döngüleri için `for` , bkz. [Denetim akışı Q# ](xref:microsoft.quantum.guide.controlflow).

## <a name="next-steps"></a>Sonraki adımlar

[Içindeki Q# türler ](xref:microsoft.quantum.guide.types)hakkında öğrenmeye başlayın.

Arka plandaki temel bilgiler ve mosyon hakkında daha fazla bilgi için Q# bkz. [neden ihtiyacımız Q# var?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).
