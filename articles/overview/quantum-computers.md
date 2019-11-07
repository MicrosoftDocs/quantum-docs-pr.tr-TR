---
title: Kuantum bilgisayarlar ne yapabilir?
description: Orijinal kuantum algoritmalarından klasik bilgisayarlarda çalıştırılan kuantumdan esinlenmiş algoritmalara kadar, kuantum bilişiminin etkilerini öğrenin.
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.computers
ms.openlocfilehash: 9d8ba90a504f298f9465ebf564c43625a4d43168
ms.sourcegitcommit: edcf15044d7bdf4f8b21fb8f6af4bde475eb13a0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73529943"
---
# <a name="what-can-a-quantum-computer-do"></a>Bir kuantum bilgisayar ne yapabilir?

Kuantum bilgisayarla, klasik bilgisayarla yapamayacağımız neleri yapabiliriz?

Mevcut bilgisayarlarla bir çözüm bulmanın milyarlarca yıl sürebileceği dünyanın en zorlu problemlerinden bazılarını, bir kuantum bilgisayar günler, saatler, hatta dakikalar içinde çözebilir.

Kuantum bilişimi araştırmacıların yeni katalizörler ve malzemeler geliştirmesine, ilaçları geliştirmesine, yapay zeka alanındaki ilerlemeleri hızlandırmasına ve evrenimizin kökeni hakkındaki temel soruları yanıtlamasına olanak tanıyacaktır.

## <a name="quantum-simulation"></a>Kuantum simülasyonu

Kuantum programlarını kullanarak kuantum sistemler tasarlamak ve bu sayede birçok farklı sektörde daha fazla içgörü elde ederek yeni çözümler elde etmek mümkündür. Kuantum programları kullanılarak benzetimi yapılabilecek kuantum sistemlerine örnek olarak fotosentez, süper iletkenler ve karmaşık moleküller verilebilir.

Kuantum mekaniğinin yasalarına göre davranan mikroskobik sistemlerin benzetimini yapmak, bilgisayar açısından pahalıya gelir. Süper konumda olabilecek tüm olası durumları hesaba katmamız gerekir ve sistemin boyutu arttıkça durum sayısı katlanarak artar. Kuantum bilgisayarda sistemin tüm durumlarını modellememiz gerekmez. Bunun yerine benzetimini yapmak istediğimiz sistemin kuantum durumunu bilgisayarın kendi kubitlerine gömeriz ve belirli bir kuantum geçidi kümesiyle benzetimi çalıştırırız. Diğer bir deyişle kuantum sisteminin benzetimini yapmak için kuantum bilgisayarı kullanırız.

Kimyasal moleküller kuantum sistemleridir ve dolayısıyla bu yolla analiz edilebilir. Bu tür özel kimyasallardan biri de _nitrojenaz_ enzimidir. Özellikleri daha iyi anlaşıldığında enerji tüketimini ve mevcut gübrelerin sera gazı salınımını azaltabilir.

## <a name="cryptography"></a>Şifreleme

Kuantum bilgisayarların muhtemelen en çok bilinen uygulama alanlarından biri de şifreleme teknolojisidir. 1994 yılında Peter Shor, ölçeklenebilir bir kuantum bilgisayarın oldukça yaygın bir şekilde kullanılan bir şifreleme tekniğini kırabileceğini göstermiştir.  Klasik kriptografide büyük sayıların iki asal sayıya kadar çarpanlarına ayrılması gibi büyük sayılarla gerçekleştirilecek işlemlerin zorluğuna güvenilir.

Kuantum bilişimi bu işlemleri teorik olarak mümkün hale getirir (Shor algoritmasıyla). Bu algoritmanın uygulanması kuantum donanımının mevcut ölçeğiyle fiziksel olarak mümkün olmasa da, şifreleme ve kriptografik anahtar dağıtımına yönelik orijinal kuantum algoritmaları gibi geleceğe dayanıklı veri güvenliği için kuantuma dayanıklı algoritmalar geliştirme çalışmalarını başlatmıştır.

Microsoft'ta çalışan dünyanın bir numaralı kuantum şifreleme sonrası ve güvenlik ekibinde kuantuma dayanıklı algoritmalar geliştirilmektedir.

## <a name="optimization"></a>İyileştirme

İyileştirme, geniş çaplı bir alanda geniş bir arama işlemi gerçekleştirerek maliyetleri en aza indiren bir çözüm elde etmektir.   Kuantum bilgisayarda iyileştirme algoritmaları hızlandırılarak başka türlü mümkün olmayan çözümler elde edilebilir. Taşımacılık ve lojistik sektöründen sağlık, tanı ve malzeme bilimlerine kadar farklı uygulamalar tasarlanabilir. Bu sayede bu sektörler daha verimli hale getirilebilir.

Kuantum bilişimi ile iyileştirme sayesinde günümüzdeki taşımacılık ve lojistik sektöründe, mevcut klasik sistemlerle mümkün olmayan bir şekilde yenilik geliştirilebilir.

Trafik akışı iyileştirilerek trafik sıkışıklığı azaltılabilir.  Rota planlamanın yanı sıra uçak kapısı atama, paket teslimi ve iş planlama gibi birçok işlem gerçekleştirilebilir. Malzeme bilimindeki yenilikler sayesinde yeni enerji türleri, daha fazla kapasiteye sahip piller, daha hafif ve daha güçlü malzemeler geliştirilebilir.

## <a name="machine-learning"></a>Makine öğrenimi

Klasik bilişimde sayısal hesaplamaların büyük bölümü temelde doğrusal denklem sistemlerini çözmekten oluşur. Bu durum özellikle hesaplama maliyetinin büyük bölümünün muazzam büyüklükteki matrislerin tersini almaya harcandığı makine öğrenmesi alanında geçerlidir.

Neyse ki sistemi klasik bilgisayardan çok daha hızlı bir şekilde yaklaşık olarak çözmemize olanak sağlayan bir kuantum algoritması vardır. Bu algoritma, doğrusal denklem sistemlerinin çözülmesini gerektiren her problemde çok yüksek hız artışlarının önünü açmıştır.

Bu alanlardaki sorunlara çözüm bulmak enerji krizi, iklim değişikliği, gıda kıtlığı ve kişisel/kesin tıbbi tanı sorunlarının çözülmesine yardımcı olacaktır.

## <a name="quantum-inspired-computing"></a>Kuantumdan esinlenen bilişim

Kuantumdan esinlenen algoritmalar klasik yazılımlarla gerçekleştirilir ama hızı ve doğruluğu artırmak için kuantum ilkelerini kullanır.

Kuantumdan esinlenen algoritmalar tıbbi araştırmalara, örneğin Manyetik Rezonans Görüntüleme (MRI) taramalarının doğruluğunu geliştirme çalışmalarına uygulanmaktadır. Kuantumdan esinlenen bilişim, MRI makinelerinin yapılandırmasını belirli hastalıkları tanımlayacak şekilde iyileştirmek için kullanılmaktadır.

## <a name="next-steps"></a>Sonraki adımlar

* [Kuantum bilişimini neden öğrenmeliyim?](xref:microsoft.quantum.overview.why)
* [Microsoft Quantum Development Kit'i kullanmaya başlama](xref:microsoft.quantum.welcome)
