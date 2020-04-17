---
title: Kuantum bilişimi nedir?
description: Kuantum bilişimi özellikleri, algoritmaları ve donanımı ile Microsoft Quantum Geliştirme Seti’ne (QDK) bir giriş.
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.what
ms.openlocfilehash: 668df50882272bfa56541f178e2f4d5fb35efcf5
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906789"
---
# <a name="what-is-quantum-computing"></a>Kuantum bilişimi nedir?

Bazı problemler o kadar zor, o kadar inanılmaz büyüktür ki, dünyadaki tüm süper bilgisayarlar problem üzerinde çalıştırılsa bile problemin çözülmesine evrenin ömrü yetmez.

Kuantum bilgisayarlar gezegenimizin çevre, tarım, sağlık, enerji, iklim, malzeme bilimi ve daha henüz hayal bile etmediğimiz alanlardaki en zorlu sorunlarından bazılarını çözme umudu verir. Kuantum bilgisayarların etkisi çok kapsamlı olacak ve 1947'de günümüzün dijital ekonomisinin yolunu açan transistörün keşfi kadar büyük bir etki yaratacaktır.

Kuantum bilişimi, kuantum fiziğinin benzersiz davranışından yararlanarak yeni ve güçlü bir bilişim modeli sağlar. Kuantum fiziği teorisi maddenin kuantum düzeyinde birden çok klasik durumun üst konumunda olabildiğini varsayar. Söz konusu birçok durum da dalga havuzundaki dalgalar gibi birbirine karışabilir.  Maddenin ölçüm sonrasındaki durumu, klasik durumlardan birine "daraltılır". 

Sonrasında aynı ölçümün yinelenmesi aynı klasik sonucu verecektir.  Parçacıklar fiziksel olarak birbirlerinden uzak olsa dahi her birinin kuantum durumu diğerlerinden ayrı bir şekilde tanımlanamadığı bir etkileşim durumu oluştuğunda kuantum dolanıklığı meydana gelir.  

Kuantum bilişimi bilgileri maddenin kuantum durumları halinde depolar ve bu bilgileri temel alarak işlem yapan kuantum işlemlerini gerçekleştirmek için süper konum ve dolanıklık özelliklerini kullanır. Bu sayede kuantum girişiminden yararlanır ve bunu programlamayı öğrenir.

Kuantum bilişimi göz korkutucu gelebilir ama doğru kaynaklarla kuantum uygulamaları derlemeye bugün başlayabilirsiniz.

## <a name="the-qubit"></a>Kubit

Kuantum bilişimi, kuantum davranışını yansıtan bilişim kavramlarını tanımlar.  Kuantum bilişimi, kubit kavramıyla başlar.  Kuantum bilişiminde kuantum biti yani **kubit**, klasik bit gibi kuantum bilgileri birimidir. Klasik bitler 0 veya 1 gibi tek bir ikili değeri barındırırken, kubitin durumu aynı anda 0 ve 1 değerlerine sahip olan **süper konum** olabilir.  

Kubiti ölçme işlemi, kubitin durumunu değiştirir. Ölçüm yapıldığında kubit, süper konumdan klasik durumlardan birine geçer.  

Birden çok kubit de **dolaşık hale getirilebilir**. Dolaşık bir kubitin ölçümünü yaptığınızda, diğerinin durumuna ilişkin bilginiz de güncelleştirilir.

## <a name="quantum-algorithms"></a>Kuantum algoritmaları

Kuantum algoritmaları, klasik algoritmaları hızlandırmak üzere kuantumun doğasından ve davranışlarından yararlanacak ve fiziksel sistemlerin modellemesinde tamamen yeni yollar sağlayacak şekilde tasarlanmıştır.  Bu algoritmalar, kubitlerin bilgi kodlama yöntemiyle süper konumdaki birden fazla dolanık kubitin üzerinde paralel işlem gerçekleştirme özelliğinden faydalanır.  

Klasik bilgisayarlar bilgileri bitler halinde kodlar ve her bit 0 veya 1 olmak üzere iki olası değer kodlayabilir.  Bir kubit aynı anda 0 ve 1 olmak üzere iki değer kodlar.  İki klasik bit 4 olası değerden birini (00, 01, 10, 11) kodlayabilirken iki kubit 4 durumun süper konumunu aynı anda kodlayabilir ancak ölçüm sırasında bu değerlerden yalnızca bir tanesi elde edilebilir. Dört kubit, 16 değerin süper konumunu aynı anda kodlayabilir ve değer sayısı bu şekilde katlanarak artabilir.  100 kubit, günümüzün en büyük bilgisayar sistemlerinde bulunandan daha fazla bilgi kodlayabilir.  

Ayrıca birden çok dolaşık kubit uyumlu davrandığında, birden çok seçeneği aynı anda işleyebilir. Dolanık kubitler en hızlı kuantum dışı sistemlerin harcayacağından çok daha kısa sürede bilgileri işleyebilir.

Bu kuantum özniteliklerini kullanmak, uzun yıllardır devam eden kuantum algoritması araştırmalarının hedeflerinden biri olmuştur ve problemlerin klasik yöntemlere kıyasla çok daha kısa bir sürede çözülmesini sağlayacak birçok yenilikçi teknik mevcuttur.  

En ünlü kuantum algoritmalarından biri çarpanlara ayırmaya yönelik _Shor algoritmasıdır_. Bu algoritma klasik olarak aşırı zor olan çok büyük sayıların iki asal sayıya kadar çarpanlarına ayrılması problemini geleneksel kriptografiyi sarsacak kadar hızlı çözer.

Daha yapıcı taraftan bakarsak, süper konum, dolanıklık ve kubitlerin **klonlanmama** özelliği (kubitlerin saptanmadan kopyalanamaması) sayesinde güvenli kriptografik anahtar dağıtımı algoritmaları hazırlamak mümkün olmuştur.

_Grover algoritması_, yapılandırılmamış verilerde arama yapmak için kuadratik hızlandırma sağlayan bir kuantum algoritma tekniğidir.

## <a name="quantum-hardware"></a>Kuantum donanımı

Klasik bilgisayarlarda bitler silikon devrelerdeki voltaj düzeylerine karşılık gelir. Kuantum bilişimi donanımı, kubitlerin birçok farklı fiziksel uygulamasıyla gerçekleştirilebilir: iyon kapanı, süper iletken, nötr atomlar, elektron döngüsü, ışığın polarizasyonu, topolojik kubitler. Kuantum donanım yeni gelişen bir teknolojidir. Kubitler doğaları gereği kırılgandır ve ortamlarıyla etkileşime geçtikçe tutarlılıkları azalır. Sistemde ölçeklenebilirlikle dengeleyici doğruluk gerekir. Ölçek (yani kubit sayısı) ne kadar büyükse hata oranı da o kadar yüksektir.

Microsoft topolojik kubitlere dayalı bir kuantum bilgisayar geliştirmektedir. Topolojik kubitin içinde bulunduğu ortamdaki değişikliklerden daha az etkileneceğine, dolayısıyla dış hata düzeltme derecesinin azalacağına inanıyoruz. Topolojik kubitler daha yüksek kararlılık ve ortam gürültüsüne daha fazla dayanıklılık gösterir; diğer bir deyişle daha uzun süre ölçeklenebilir ve güvenilirliği sürdürebilir.

## <a name="quantum-computing--a-full-hardware-and-software-stack"></a>Kuantum bilişimi - tam kapsamlı donanım ve yazılım yığını

Microsoft'un kuantum programı, gerçek kuantum etkisi sunmak için sistemin her bir bileşenini ölçeklendirmeye odaklandığından benzersiz bir deneyim sunmaktadır. Bu kapsamlı yaklaşım şunları içerir:

* Güvenilir, ölçeklenebilir ve hataya dayanıklı topolojik kubitler kullanarak bir quantum bilgisayar oluşturma, 
* Düşük güç tüketimine ve ısı dağılımına sahip benzersiz bir kriyojenik kontrol düzlemi oluşturma, 
* Kuantum bilgisayarı programlamak ve sistemi uygun ölçekte yönetmek için tam kapsamlı bir yazılım yığını geliştirme.

Kuantum programlama ve algoritma geliştirme işlemlerini daha erişilebilir hale getirmek için açık kaynak Quantum Development Kit (QDK) kullanıma sunulmuştur. Üst düzey bilgisayar dilimiz Q# kuantum programlamanın zorluklarına çözüm getirir.  Q#, algoritma ve uygulama geliştirmeye yönelik üst düzey kuantum odaklı programlama dili olarak tasarlanmıştır. Q# derleyicisi, kuantum algoritmasının bir kuantum bilgisayarın temel işlemlerine kadar derlenmesine olanak tanıyan bir yazılım yığınıyla tümleştirilmiştir.  Klasik bir bilgisayarda belirli bir ölçeğe (kubit sayısı) kadar kuantum bilişiminin benzetimi yapılabilir. Benzetimi kullanarak, yarın kuantum donanımı üzerinde çalıştırılacak kuantum programlarını bugün yazmaya başlayabilirsiniz.  Ayrıca kuantum programlamaya bugün başlamanızı kolaylaştırmak için Q# ile birlikte örnekler, kitaplıklar ve öğrenme alıştırmaları da sunuyoruz. 

## <a name="next-steps"></a>Sonraki adımlar

* [Kuantum bilgisayarlar ne yapabilir?](xref:microsoft.quantum.overview.computers)
* [Microsoft Quantum Development Kit'i kullanmaya başlama](xref:microsoft.quantum.welcome)
* [Kuantum bilişimi kavramları](xref:microsoft.quantum.concepts.intro) hakkındaki diğer makaleleri okuyun
