---
title: Yazılım yığını | Microsoft Docs
description: Yazılım yığını
author: QuantumWriter
uid: microsoft.quantum.concepts.software-stack
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f97dfacf6cde5fa92e1f368efaae36554a5c944d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184738"
---
# <a name="software-stack-for-quantum-computing"></a>Hisse bilgi işlem için yazılım yığını
Normal olarak, bir bilgisayarı, uygulamayı çalıştıran tek bir cihaz hakkında düşündük, ancak modern bilgi işlem ortamları çok daha karmaşık ve gelişmiş. İle etkileşimde bulunduğumuz uygulama, genellikle uygulamanın donanım düzeyine kadar yürütülmesini sağlayan birden çok yazılım katmanına göre bekletildiğinde. Bu yazılım katmanları, tüm bilgi işlem sisteminin temeldeki karmaşıklığından bir uygulama çözümünün geliştirilmesini soyutlamak için gereklidir. Bir geliştiricinin basit bir smartphone uygulaması yazarken veri yolu, önbellek mimarileri, iletişim protokolleri ve daha fazlasını düşünmesi gerekiyorsa, görev çok daha karmaşık hale gelir.  *Yazılım yığınının* kavramı, bu sorunları gidermek için klasik bilgi işlem 'da geliştirilmiştir.  Klasik kavramdan ödünç alınan bir yazılım yığını, Ayrıca, Q # ile hisse satışınızın arkasındaki vizyonın önemli bir parçasıdır.

## <a name="conventional-stack"></a>Geleneksel yığın
Yazılım yığınının arkasındaki önemli fikir özyinelemedir.  Bu, cihazın alt seviyelerinin ayrıntılarını geliştiriciden uzağa soyutlamak için birkaç iç içe arabirimler katmanından oluşur.  Örneğin, yaygın olarak kullanılan bir yazılım yığını, Windows Server üzerinde çalışan Internet Information Services (bir Web Server) üzerinde çalışan SQL Server (ilişkisel veritabanı yönetim sistemi) üzerinde çalışan ASP.NET (bir programlama dili) çalıştırmayı içerir (bir işletim sistemi), bilgisayar donanımını sürücüler.  Yazılım bir hiyerarşi olarak inceleyerek, bu yazılımın altındaki tüm yazılımların alt düzey ayrıntılarını anlamak zorunda kalmadan, ASP.NET 'e yazılım yazabilir.

## <a name="quantum-stack"></a>Hisse yığını

Bilgi işlem ortamında yazılım yığını farklı değildir ve uygulamada geleneksel yığınlardan daha düşük bir düzeyde çalışır.  Hisse yığını nasıl görünür?  Hisse bilgisayar geleneksel (genellikle klasik olarak adlandırılır) bilgisayarlar için bir değiştirme değildir.  Aslında, hisse bilgisayarları, hesaplama sorunlarını çözmek için klasik bilgisayarlarla birlikte neredeyse tamamen çalışır.  Bunun için, kırılganlığına of hisse verisi nedeniyle bu oluşur.  Bu durumda, gözlemlenecek bilgilere neredeyse tamamen zarar verseniz bile bu, en fazla bilgi.  Bu nedenle, fiziksel ortamlarındaki boş olan etkileşimlerin bilgi ve hesaplama istenmeden zarar vermemesi için hisse gerekmediğini göz önünde bulundurmanız gerekir. Bu nedenle, Q # için doğal bir hedef, hisse maların bir listesini (ağ geçitleri veya ağ geçidi işlemleri olarak adlandırılır) kabul eden bir hata düzeltilmiş hisse bilgisayarı (genellikle *hataya dayanıklı* bir hisse bilgisayar) olarak adlandırılır ve bu yönergeleri hisse adına uygular içinde depolanan veriler.  Bir hisse algoritması veya programdaki qubits ve geçit işlemlerinin sayısı yeterince küçükse, hata düzeltmesinin kesinlikle gerekli olamayacağını unutmayın.  Ancak, qubits ve ağ geçidi işlemlerinin sayısı arttıkça, daha büyük bir gereklilik olacaktır, bu nedenle yazılım yığınımızın ve Q # 'ları, hata düzeltmesini ve etkili bir şekilde idare etmek ve ölçeklenebilir, hataya dayanıklı hisse bilgi işlem işlemlerini etkinleştirmek için mimarilerimizi sağlar.

### <a name="error-correction"></a>Hata Düzeltme
Hata düzeltmesi hızlı ve güvenilir bir klasik bilgisayarın, hisse hesaplamada bulunan hataları düzeltmek için, hisse ve güvenilir bir klasik bilgisayarın, bu hataların bulunduğu sorunları giderecek şekilde çalışmasını gerektirir.  Pratikte, alan-programlanabilir kapı dizileri (FPGAs) veya hızlı Cryogenic işlemciler gibi bileşenler, bu hataların doğal olarak bir arada birikdikleri sayıdan daha hızlı belirlenmesi ve düzeltilmesi için gerekli olabilir.  Sonuç olarak, bir hisse bilgisayarı, çok çeşitli çok sayıda sıcaklıklar üzerinde çalışan birkaç farklı hesaplama cihazlarından oluşan karma bir makinedir.  Bu nedenle, bir hisse anın uygulanmasını sağlamak için gereken çok sayıda donanım ve yazılım (klasik ve hisse) katmanı olduğu için, bir yazılım yığınının merceği aracılığıyla bir hisse bilgisayarı programlamayı düşünmek çok daha yararlıdır. bir hisse bilgisayarında algoritma.

### <a name="quantum-conceptual-stack"></a>Hisse kavram yığını
Bir hisse bilgi işlem ortamında düzenleme 8704143553785700723 'nin işlevsel akışını gösteren kavramsal bir yığın aşağıda gösterilmiştir:

![Yazılım yığını](~/media/concepts_stack.png)

### <a name="specification-and-algorithm"></a>Belirtim ve algoritma
Bu tür bir hisse hesaplamadığının birkaç geniş aşamasına kadar programlama vardır.  Birincisi ve arguya en zorlu aşamada, tek bir dilekün çözmeyle ilgili sorun belirlenir.  Bu durumda, sorun 8704143553785700723 numarasını iki asal sayının bir ürününe katmada olur.  Sonraki adım, bu hesaplama sorununun çözümüne yönelik bir algoritma tasarlamaya yöneliktir.  Bu durumda, faktörleri bulmak için Shor 'ın faünlü hisse düzenleme algoritması kullanılabilir.  Bu algoritma, Q # ' da ifade edilir ve ardından bir hisse miktarı dizisi, bir dizi işlem ile ilgili bir hata-ücretsiz hisse bilgisayarında çalıştırılabilen çıktıdır.  

### <a name="physical-gates"></a>Fiziksel kapıları
Bu örnekte, bir hata-ücretsiz hisse bilgisayarı sağlamak için doğası olduğunu varsayarak, sonraki adım Q # tarafından oluşturulan işlemleri alır ve bunları, fiziksel kapıların seçtiği hisse temel donanım çalıştırılabilir.  Bu işlem, bir önceki modelde açıklanan bir fiziksel qubit ana bilgisayarıyla, bu bilgileri tek bir qubit içindeki bilgileri, şirket içi fiziksel üzerinde yerel hataları yeniden düzenleyebilir Bu tür hataların algılanabilmesi ve düzeltilmesi için yeterince uzun.  Aynı şekilde, Q # kodu tarafından tanımlanan mantıksal qubits 'in birçok fiziksel qubit ile değişmesi gerekir. aynı şekilde, çıktıda açıklanan her hisse kapıda fiziksel qubit üzerinde işlem yapan bir fiziksel ağ dizisine çevrilmesi gerekir.  Bu nedenle, Q # çıkışı nadiren bilgi işlem için son hedeftir ve daha fazla soyutlama düzeyi, kodu donanımda bir şekilde yürütmek için gereklidir.

### <a name="control-computer"></a>Denetim bilgisayarı
Fiziksel ağ geçidi sırası, bu yönergeleri daha sonra doğrudan hisse bilgisayar ile arabirimlerin bulunduğu bir denetim bilgisayarına gönderen sıradan bir bilgisayara yüklenir.  Yazılım yığını içindeki bu katman genellikle [Qcodes](http://qcodes.github.io/Qcodes/)gibi deneysel denetim yazılımları tarafından işlenir.

### <a name="interface-computer"></a>Arabirim bilgisayar
Bu işlemdeki son adım, bir hızlı denetim bilgisayarına gereken kapıların ilk akışını yapan arabirim bilgisayarını içerir. Hızlı denetim bilgisayarı, gerekli kapıları qubits 'e uygulamak için gerekli olan voltages (genellikle pulu olarak adlandırılır) uygular. Bu işlem, hisse alınan hata düzeltmekle gözlemlendiği hata düzeltilirken yapılmalıdır.  Cryogenic FPGAs veya diğer Exotic Hardware 'in, bu adımları, bu adımların, bir miktar bilgisayarda görünme hızına göre belirlenen katı zaman gereksinimleri içinde gerçekleştirmesi gerekebilir.  Bu düzeydeki hedef dil genellikle [VHDL](https://en.wikipedia.org/wiki/VHDL)'dir ve bu, bir hisse algoritması açıklamasını ayrıştırmak için yığının en üst ucunda kullanılan farklı bir yol gerektirir.

### <a name="the-q-quantum-programming-language"></a>Q # hisse programlama dili
Q # amacı, geliştiricilerin çok sayıda hisse bilgi işlem platformunu ve arabirimini hedefleyen ve Kullanıcı ile hisse cihazı arasında çok sayıda yazılım kullanan bir kod yazmasına olanak tanıyan basit bir dil sağlamaktır.  Bu dil, bir yazılım yığını kavramını benimseyerek ve temel alınan hisse bilgisayar düzeylerine izin verirken, gibi bir dilde C#açığa çıkarılan, gerekli olan Q # kodundan temel işlemlere çeviri.  Bu, geliştiricinin en iyi şekilde yaptığı işe odaklanmasını sağlar: algoritmaları tasarlama ve sorunları çözme.
