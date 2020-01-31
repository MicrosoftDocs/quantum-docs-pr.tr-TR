---
title: 'Q # programa genel bakış-Q # teknikleri | Microsoft Docs'
description: 'Q # programa genel bakış-Q # Teknik'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.file-structure
ms.openlocfilehash: e8f52e6b0d4382331665a8e845ef19a3a1beabf9
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820836"
---
# <a name="q-program-overview"></a>Q# programına genel bakış

S #, hisse kullanımı için ölçeklenebilir, çok faktörlü, etki alanına özgü bir programlama dilidir. S #, yönergelerin hisse makineleri üzerinde nasıl yürütüleceğini açıklayan bir hisse dili programlama dilidir. Simülatörleri 'ten gerçek hisse donanımına kadar hedeflenebilir makineler. S # ölçeklenebilir: birkaç qubit üzerinde çalışan teleport gibi basit tanıtım programları yazmak için kullanılabilir, ancak aynı zamanda milyonlarca qubit ile büyük makineler gerektirecek karmaşık molecules benzetimleri gibi büyük ve karmaşık programları yazmayı destekler. Büyük fiziksel makineler hala gelecekte olsa da, soru-cevap olarak bir programcının karmaşık hisse algoritmaları kullanmasına izin verir. Daha fazla nedir, Q # hata ayıklama, profil oluşturma, kaynak tahmini ve belirli özel amaçlı benzetimler gibi çeşitli görevleri ölçeklenebilir bir şekilde destekler. 

Teknik açıdan, bir hisse bir program, çağrıldığında, yan etkileri olarak hisse devreleri oluşturmak için belirli bir klasik işlevler kümesi olarak görülebilir. Bu görünümün önemli bir sonucu, Q # dilinde yazılmış bir programın, qubits 'i doğrudan modelleyebilmesini, ancak klasik bir denetim bilgisayarının bu qubits ile nasıl etkileşime gireceğini açıklar.
Tasarıma göre, Q #, bu nedenle hisse ya da hisse MACS 'nin diğer özelliklerini doğrudan tanımlamaz, ancak bunun yerine dilde tanımlanan çeşitli alt yordamların eylemiyle dolaylı olarak yapılır.
Örneğin, [hisse bilgi Işlem kavramları](xref:microsoft.quantum.concepts.intro) Kılavuzu 'nda açıklanan $ \ket{+} = \left (\ket{0} + \tus{1}\right)/\sqrt{2}$ durumunu göz önünde bulundurun.
Bu durumu Q # ' da hazırlamak için, qubits 'in $ \ket{0}$ durumunda başlatıldığı ve bu $ \ket{+} = H\gre{0}$, burada $H $ 'nin Hadamard dönüşümünden oluşan olguları kullanıyoruz:

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0〉.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0〉 = |+〉, as we wanted.
}
```
## <a name="q-tranformations-of-quantum-states"></a>S. hisse amaçları için soru-cevap durumları

Daha da, yukarıdaki programın yazılmasında, Q # içindeki duruma açıkça başvurmuyoruz, ancak durumun programımız tarafından nasıl *dönüştürüldüğünü* açıklıyoruz.
Bu nedenle, bir grafik gölgelendirici programının her bir köşenin dönüştürmelerinin açıklamasını nasıl birikdiğinden benzer şekilde, Q # ' daki bir hisse
Bu, makineye bağlı farklı yorumlamalar olabilecek her bir hedef makinede bile her bir hisse alım durumunun büyük bir yerde *olduğu* konusunda tamamen belirsiz bir durumdur. 

Bir Q # programının perspektifinden, qubit, hedef makinenin iç yapısına tamamen opak bir başvurudur.
Bir Q # programı, bir qubit durumunun durumunu, bir hedef makine üzerinde temsilini introspect, hatta programın kullanabildiği diğer tüm qubit gibi aynı qubit olup olmadığını da bilme özelliğine sahip değildir.
Bunun yerine, bir program qubit 'ten bilgi edinmek için `Measure` gibi işlemleri çağırabilir ve bir qubit durumuna işlem yapmak için `X` ve `H` gibi çağrı işlemleri gerçekleştirebilir.
Bu işlemlerin dil içinde hiç iç tanımı yoktur ve yalnızca belirli bir Q # programını çalıştırmak için kullanılan hedef makine tarafından somut hale getirilir.
Bir Q # programı, Express hisse hesaplamasına yeni ve daha üst düzey işlemler oluşturmak için bu işlemleri bir hedef makine tarafından tanımlanan şekilde yeniden birleştirir.
Bu şekilde, Q #, temel alınan hisse ve hibrit-klasik algoritmaların yanı sıra bir hedef makine ya da simülatör yapısına göre genel de olacak şekilde ifade yapmayı kolaylaştırır.

## <a name="q-operations-and-functions"></a>S # işlem ve işlevleri

Bir Q # programı, bir veya daha fazla *işlemden*, bir veya daha fazla *işlevden*ve Kullanıcı tanımlı türlerden oluşur. İşlemler, bir hisse anın durumunun dönüşümlerini betimleyen ve en temel yapı bloğu olan Q # programlarıdır. Her bir işlem, bir hedef makine tarafından uygulanan yerleşik *iç* işlemler de dahil olmak üzere herhangi bir sayıda işlemi çağırabilir.
Derlendiğinde, her işlem hedef makinelere sağlanlenebilecek bir .NET sınıf türü olarak temsil edilir.

İşlemlere karşılık işlevler, tamamen klasik davranışı betimleyen ve klasik çıkış değerlerini hesaplama konusunda herhangi bir etkiye sahip olmayan işlevler için kullanılır. S #, türü kesin belirlenmiş bir dildir ve yerleşik temel türler kümesi ve Kullanıcı tanımlı türler için destek ile birlikte gelir. 

Bu kılavuzun geri kalanında, farklı dil kavramlarının ve yapıların nasıl kullanıldığını, karmaşık hisse programlarını işlem, işlev ve tür temel yapı taşları aracılığıyla belirlememize yardımcı olacak şekilde kullanacağız. 

## <a name="structure-of-q-source-files"></a>Q # kaynak dosyalarının yapısı

En düşük düzeyde, bir Q # kaynak dosyası, kaynak dosyadaki tanımları içeren bir .NET ad alanını belirten bir *ad alanı bildiriminden*oluşur.
Diğer Q # kaynak dosyalarından ve kitaplıklarından olan tanımlar `open` ifadesiyle eklenebilir.
Örneğin, temel kapıları tanımlayan işlemlerin çoğu <xref:microsoft.quantum.intrinsic> ad alanında tanımlanır.
Bunu kodumuza uygun hale getirmek için, her bir dosyanın en üstünde yer alan ad alanını `open`.

```qsharp
namespace Example {
    open Microsoft.Quantum.Intrinsic;

    // ...
}
```

Bir ad alanı içinde her Q # kaynak dosyası *işlemler*, *işlevler*ve *Kullanıcı tanımlı türlerin*herhangi bir birleşimini tanımlayabilir.
Bu bölümün geri kalanında, her birini sırayla anlayacağız ve yararlı hisse programları için uygulamada nasıl kullanılabilecekleri hakkında örnekler sunacağız.
