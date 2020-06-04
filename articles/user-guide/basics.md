---
title: 'S # temel kavramları'
description: 'Soru-cevap için temel kavramlar #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: e77b52d1a6eb7e2f62ab12dedd75d00ac8fec4be
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327331"
---
# <a name="q-basics"></a>S # temel kavramları

Bu bölümde, Q # ' ın temel yapı taşlarına kısa bir giriş sunuyoruz.

Ne olduğunu ve ne olduğuna ilişkin genel bir bakış için, hisse geliştirme setinin temel bir bileşeni olarak hangi noktada olduğunu ve [ne olduğunu](xref:microsoft.quantum.overview.q-sharp)öğrenmek için soru-cevap ' a bakabilirsiniz. 

## <a name="what-is-a-quantum-program"></a>Hisse bir program nedir?

Teknik açıdan, bir hisse bir program, çağrıldığında belirli işlemleri bir hisse sisteminde gerçekleştirirken belirli bir klasik alt yordamlar kümesi olarak görülebilir.
Bu görünümün önemli bir sonucu, Q # dilinde yazılmış bir programın, qubits 'i doğrudan modelleyebilmesini, ancak klasik bir denetim bilgisayarının bu qubits ile nasıl etkileşime gireceğini açıklar.
Tasarıma göre, soru-cevap, bu nedenle hisse veya diğer hisse ve diğer özellikleri doğrudan tanımlamaz.
Örneğin, hisse bilgi Işlem kavramları kılavuzunda $ \ket{+} = \left (\ket {0} + \ket {1} \ right)/\sqrt $ durumunu göz önünde bulundurun {2} . [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro)
Bu durumu Q # ' da hazırlamak için, qubits 'in $ \ket $ durumunda başlatıldığı olguları {0} ve $ \ket{+} = H\ket {0} $ olduğunu, burada $H $, [ `H` Operation] (] (XREF: Microsoft. hisse. Intrinsic. H) tarafından uygulanan Hadamard dönüşümünden kullanırız:

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0⟩.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0⟩ = |+⟩, as we wanted.
}
```

## <a name="quantum-states-in-q"></a>Soru-cevap durumu #

Daha da, yukarıdaki programın yazılmasında, Q # içindeki duruma açıkça başvurmuyoruz, ancak durumun programımız tarafından nasıl *dönüştürüldüğünü* açıklıyoruz.
Bu, makineye bağlı farklı yorumlamalar olabilecek her bir hedef makinede bile her bir hisse alım durumunun büyük bir yerde *olduğu* konusunda tamamen belirsiz bir durumdur. 

Bir Q # programı bir qubit 'in durumuna introspect bir özelliğine sahip değildir.
Bunun yerine, bir program [`Measure`](xref:microsoft.quantum.intrinsic.measure) qubit 'ten bilgi almak için gibi işlemleri çağırabilir ve [`X`](xref:microsoft.quantum.intrinsic.x) [`H`](xref:microsoft.quantum.intrinsic.h) bir qubit durumu üzerinde işlem yapmak için ve gibi işlemleri çağırabilir.
Bu *işlemlerin gerçekten ne* olduğunu yalnızca belirli bir Q # programını çalıştırmak için kullandığımız hedef makine tarafından somut hale getirilir.
Örneğin, programı [tam durum benzeticimizde](xref:microsoft.quantum.machines.full-state-simulator)çalıştırırsanız simülatör, sanal hisse sisteme karşılık gelen matematiksel işlemleri yapar.
Ancak geleceğe bakıyorum, hedef makine gerçek bir hisse bilgisayar olduğunda, Q # ' da bu gibi işlemleri çağırmak, hisse bilgisayarını *Gerçek* hisse sisteminde ilgili *gerçek* işlemleri gerçekleştirmeye yönlendirir (örneğin, tam olarak süreli lazer pulu).

Bir Q # programı, Express hisse hesaplamasına yeni ve daha üst düzey işlemler oluşturmak için bu işlemleri bir hedef makine tarafından tanımlanan şekilde yeniden birleştirir.
Bu şekilde, Q #, temel alınan hisse ve hibrit, klasik algoritmaların yanı sıra bir hedef makine ya da simülatör yapısına göre genel de olacak şekilde ifade yapmayı kolaylaştırır.

## <a name="q-operations-and-functions"></a>S # işlem ve işlevleri

Bir Q # programı, *işlemlerden*, *işlevlerden*ve Kullanıcı tanımlı türlerden oluşur. 

İşlemler, hisse sistemleri dönüştürmelerini ve en temel yapı bloğu olan Q # programlarını anlatmak için kullanılır. Q # içinde tanımlanan her işlem, diğer birkaç işlemi çağırabilir.

İşlemlere karşılık işlevler, yalnızca *belirleyici* klasik davranışı betimleyen ve klasik değerleri hesaplama konusunda herhangi bir etkiye sahip olmayan işlevler için kullanılır. Örneğin, bir programın sonunda qubits 'lerimizi ölçmek istiyoruz ve ölçüm sonuçlarını bir diziye ekleyin.
Bu durumda, `Measure` hedef makinenin (gerçek veya sanal) qubit üzerinde bir ölçüm gerçekleştirmesini bildiren bir *işlemdir* ve döndürülen sonuçların bir diziye eklenmesi, bu işlemler *işlevleri*tarafından işlenir.

Birlikte, işlemler ve işlevler *callables*olarak adlandırılır ve temel yapısı ve davranışları [Q # sayfasındaki işlemler ve işlevlerde](xref:microsoft.quantum.guide.operationsfunctions) tanıtılmıştır.


## <a name="q-syntax-overview"></a>S # sözdizimine genel bakış

Bir dilin sözdizimi, sözdizimi doğru bir program oluşturan farklı sembol birleşimlerini tanımlar.
Q # içinde, söz dizimi öğelerini üç farklı grupta sınıflandırabilir: türler, ifadeler ve deyimler.

### <a name="types"></a>Türler
S #, türlerin dikkatli kullanımı derleyicinin derleme zamanında Q # programları hakkında güçlü garantiler sağlamasına yardımcı olabilir.
Standart ve hisse özel yerleşik temel türlerin yanı sıra (örn.,, `Int` `Bool` `Qubit` ve `Result` ), Q # Kullanıcı tanımlı türler için destek sağlar.
Tüm Q # ve temel türler, dizi ve demet türlerindeki ayrıntıların yanı sıra, bir Q # dosyası içinde yeni türlerin tanımlanması ile birlikte Q # sayfasındaki [türler](xref:microsoft.quantum.guide.types) üzerinde açıklanmıştır.

### <a name="expressions"></a>İfadeler
Programlama dilindeki bir ifade, programlama dilinin belirli bir değeri yorumlaması ve değerlendiren bir veya daha fazla sabitler, değişkenler, işleçler ve işlevlerin bir birleşimidir.
Çoğu durumda, bir dildeki her tür için, bu türdeki ifadeler, bu türdeki bir değere göre *değişmez* değer ya da semboller olabilir.
Örneğin, `5` bir değişmez değerdir `Int` (Bu nedenle türünde bir ifade `Int` ) ve sembol `count` tamsayı değerine bağlıysa, `5` `count` Ayrıca bir tamsayı ifadesi de olur.

Ayrıca, bir ifade belirli işleçlerle birleştirilmiş diğer ifadelerden oluşabilir.
Bu nedenle `Int` , olduğunu değerlendiren bir ifadenin başka bir `5` örneği `2+3` .

Q # içindeki türlerin olası ifadeleri ve bunları oluşturmak için kullanılabilecek uyumlu işleçler, [q # sayfasındaki tür ifadelerinde](xref:microsoft.quantum.guide.expressions) ayrıntılıdır. 

### <a name="statements"></a>Deyimler 
Bir ifade, gerçekleştirilecek eylemi belirten bir zorunlu programlama dilinin sözdizimsel birimidir. Bu deyimlerdeki ifadelerle karşıtlık ifadesi, sonuçları döndürmez ve yalnızca yan etkileri için yürütülür, ancak ifadeler her zaman bir sonuç döndürür ve genellikle yan etkileri yoktur.
Bu ayrım genellikle, ifadesi içinde gözlemlenmiştir: bir ifade değerlendirilir, ancak bir deyim yürütülür.

Q # içindeki bir deyimin çok temel bir örneği bir ifadeye sembol atamaktır:
```qsharp
let count = 5;
```

`for`Yineleme destekleyen ve bir *Ekstre bloğunu*içeren deyimde biraz daha ilginç bir örnektir.
Varsayalım ki, `qubits` bir qubits kaydına (Teknik olarak tür dizisi) bağladır `Qubit[]` `Qubit` . Ardından
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
, kayıt sırasında her bir qubit üzerinde yinelenen bir ifadedir ve `H` her birinde işlem gerçekleştirilir. Bunun de `H(qubit);` bir ifade olduğunu unutmayın.

Aslında, türünde herhangi bir çağrı ifadesi `Unit` (herhangi bir bilgi döndürmeyen bu callables) bir deyim olarak kullanılabilir.
Bu, `Unit` deyimin amacı örtülü hisse durumu ' nu değiştirecek olduğundan, bu işlem öncelikli olarak döndürülen qubits 'teki işlemleri çağırırken kullanılır.
İfade değerlendirme deyimleri, sonlandırma noktalı virgül gerektirir.

Bir Q # programının neredeyse her yönü, using deyimleri kullanılarak oluşturulmuştur, bu nedenle bunlarla ilgili tüm bilgileri kapsayamaz.
Ancak, kendi sözlü yapısı ve biçimlendirmesi, q # [dosya yapısı](xref:microsoft.quantum.guide.filestructure) sayfasında, soru-cevap atama ve q [# içindeki değişkenlerde](xref:microsoft.quantum.guide.variables)kapsam ve `for` [q # içindeki denetim akışı](xref:microsoft.quantum.guide.controlflow)gibi denetim akışı döngülerinde açıklanmıştır.

## <a name="next-steps"></a>Sonraki adımlar
Bu kılavuzun geri kalanında, işlem, işlev ve türlerin temel yapı taşları aracılığıyla karmaşık hisse programları oluşturmak için Q # ' ı nasıl kullanacağınızı göstereceğiz.

Başlamak için, [Q # Içinde türler](xref:microsoft.quantum.guide.types)hakkında öğrenmeye başlayabilirsiniz.

Soru-cevap hakkında daha fazla bilgi edinmek istiyorsanız, soru-cevap ' ı [neden ihtiyacım var?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)' i inceleyin.
