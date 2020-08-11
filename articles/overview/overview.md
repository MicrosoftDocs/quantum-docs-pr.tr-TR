---
title: Kuantum bilişimine giriş
description: Kuantum bilişiminin ne olduğunu, kuantum bilgisayarların neler yapabildiğini ve kuantum bilişimini nasıl öğrenebileceğinizi öğrenin.
author: bradben
ms.author: bradben
ms.date: 05/05/2020
ms.topic: overview
uid: microsoft.quantum.overview.introduction
no-loc:
- Q#
- $$v
ms.openlocfilehash: 59cb595ac207d6e84358fc6ba742e0e0019c76f9
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867003"
---
# <a name="introduction-to-quantum-computing-and-the-quantum-development-kit"></a>Kuantum bilişimine ve Quantum geliştirme setine giriş

Microsoft Quantum geliştirme seti (QDK), geliştiricilerin kuantum algoritmalarını öğrenmesine ve kuantum programları yazmasına yardımcı olmak için tasarlanmış bir açık kaynak araçlar kümesidir. Kuantum bilişimi gezegenimizin çevre, tarım, sağlık, enerji, iklim, malzeme bilimi ve daha henüz karşılaşmadığımız alanlardaki en zorlu sorunlarından bazılarını çözme umudu verir.  

Bu sorunlardan bazıları söz konusu olduğunda, en güçlü bilgisayarlarımız bile zorluklarla karşılaşır. Kuantum teknolojisi bilişim dünyasını daha yeni etkilemeye başlıyor olsa da, çok kapsamlı olabilir ve bilişim hakkında düşünme şeklimizi değiştirebilir.

## <a name="what-is-quantum-computing"></a>Kuantum bilişimi nedir?

Modern kullanımda kuantum sözcüğü, genellikle atomik veya atom altı parçacıkların özelliklerine başvuran herhangi bir fiziksel özelliğin olası en küçük ayrı birimi anlamına gelir. Kuantum bilgisayarlar, işlem birimleri olarak gerçek kuantum parçacıklarını, yapay atomları veya kuantum parçacıklarının toplu özelliklerini kullanır ve büyük, karmaşık ve pahalı cihazlardır.

Kuantum bilgisayarlar, kuantum fiziğinin benzersiz davranışından faydalanıp bunu bilişime uygulayarak, geleneksel programlama yöntemlerine yeni kavramlar sunar ve süper konum, dolaşıklık ve kuantum girişimi gibi kuantum fiziği davranışlarını kullanır.

## <a name="what-can-a-quantum-computer-do"></a>Bir kuantum bilgisayar ne yapabilir?

Kuantum bilgisayar, her işlemi daha hızlı yapabilecek bir süper bilgisayar değildir, ancak kuantum bilgisayarların son derece başarılı olduğu birkaç alan vardır.

- [Kuantum simülasyonu](xref:microsoft.quantum.overview.introduction#quantum-simulation)
- [Şifreleme](xref:microsoft.quantum.overview.introduction#cryptography-and-shors-algorithm)
- [Search](xref:microsoft.quantum.overview.introduction#search-and-grovers-algorithm)
- [İyileştirme](xref:microsoft.quantum.overview.introduction#quantum-inspired-computing-and-optimization)
- [Makine öğrenmesi](xref:microsoft.quantum.overview.introduction#quantum-machine-learning)

## <a name="quantum-simulation"></a>Kuantum simülasyonu

Kuantum bilgisayarlar hesaplama sırasında kuantum olaylarını kullandığından diğer kuantum sistemlerini modellemek için idealdir. Fotosentez, süper iletkenlik ve karmaşık moleküler oluşumlar, kuantum programlarının simülasyonunu yapabileceği kuantum mekanizmalarına örnektir.

## <a name="cryptography-and-shors-algorithm"></a>Şifreleme ve Shor algoritması

1994’te Peter Shor, ölçeklenebilir bir kuantum bilgisayarın, RSA algoritması gibi yaygın olarak kullanılan şifreleme tekniklerini çözebileceğini gösterdi. Klasik şifreleme, tamsayıyı çarpanlara ayırma veya ayrık logaritmalar gibi, kuantum bilgisayarlar kullanılarak çok daha verimli bir şekilde çözülebilecek birçok sorunun zorluk derecesine dayanır.

## <a name="search-and-grovers-algorithm"></a>Arama ve Grover algoritması

1996’da Lov Grover, yapılandırılmamış veri aramalarına yönelik çözümü önemli ölçüde hızlandırarak, aramaları klasik algoritmaların tümünden daha az adımda çalıştıran bir kuantum algoritması geliştirmiştir.

## <a name="quantum-inspired-computing-and-optimization"></a>Kuantumdan esinlenen bilişim ve iyileştirme

Kuantumdan esinlenen algoritmalar, hızı ve doğruluğu artırmak için kuantum ilkelerini kullanır ancak klasik bilgisayar sistemlerinde uygulanır. Bu yaklaşım, geliştiricilerin, henüz gelişmekte olan bir sektör olarak bilinen kuantum donanımını beklemeden yeni kuantum tekniklerinin gücünden yararlanmasını sağlar.

İyileştirme, istenen sonuç ve kısıtlamalar dikkate alındığında bir soruna en iyi çözümü bulma işlemidir. Maliyet, kalite veya üretim süresi gibi faktörlerin hepsi, sektör ve bilim dünyası tarafından yapılan kritik kararlarda etkili olur. Bugünün klasik bilgisayarlarında çalışan ve kuantumdan esinlenen iyileştirme algoritmaları şu ana dek mümkün olmayan çözümleri bulabilir. Sıkışıklığı azaltmak için trafik akışını iyileştirmenin yanı sıra uçak kapı ataması, paket teslimi ve iş planlama gibi birçok işlem gerçekleştirilebilir. Malzeme bilimindeki yenilikler sayesinde yeni enerji türleri, daha fazla kapasiteye sahip piller, daha hafif ve daha dayanıklı malzemeler geliştirilebilir.

> [!NOTE]
> Microsoft kuantumdan esinlenen bilişimin [malzeme biliminde](https://cloudblogs.microsoft.com/quantum/2020/01/21/oti-lumionics-accelerating-materials-design-microsoft-azure-quantum/), [risk yönetiminde](https://cloudblogs.microsoft.com/quantum/2019/05/22/microsoft-quantum-collaborates-with-willis-towers-watson-to-transform-risk-management-solutions/) ve [tıpta](https://blogs.microsoft.com/blog/2018/05/18/microsoft-quantum-helps-case-western-reserve-university-advance-mri-research/) nasıl kullanıldığı hakkında daha fazla bilgi edinin.

## <a name="quantum-machine-learning"></a>Kuantum makine öğrenimi

Klasik bilgisayarlardaki makine öğrenimi, bilim ve iş dünyasında devrim yapıyor. Bununla birlikte modelleri eğitmenin getirdiği yüksek hesaplama maliyeti, bu alanın geliştirilmesini ve kapsamını kısıtlıyor. Kuantum makine öğrenimi alanı, klasik bilgisayarlardan daha hızlı çalışan makine öğrenimi sağlayan kuantum yazılımı geliştirmeyi ve uygulamayı keşfeder.

Quantum geliştirme seti, hibrit kuantum/klasik makine öğrenimi denemeleri çalıştırmanıza olanak tanıyan [kuantum makine öğrenimi kitaplığı](xref:microsoft.quantum.machine-learning.concepts.intro) ile birlikte gelir. Kitaplık, örnekler ve öğreticiler içerir, denetimli sınıflandırma sorunlarını çözmek üzere yeni bir hibrit kuantum-klasik algoritması olan devre merkezli kuantum sınıflandırıcısını uygulamak için gerekli olan araçları sağlar.

## <a name="no-locq-and-the-microsoft-quantum-development-kit-qdk"></a>Q# ve Microsoft Quantum geliştirme seti (QDK)

Q#, Microsoft'un kuantum algoritmaları geliştirmeye ve çalıştırmaya yönelik açık kaynak programlama dilidir. Yerleşik tam durumlu kuantum simülatörü de dahil olmak üzere çeşitli ortamlarda çalıştırabileceğiniz kuantum uygulamaları geliştirmek için standart araçlar ve dillerle kullanabileceğiniz, Q# diline yönelik tam özellikli bir geliştirme seti olan [QDK](https://docs.microsoft.com/quantum/)’nin bir parçasıdır.

Visual Studio ve VS Code uzantılarının yanı sıra Python ve Jupyter Notebook ile birlikte kullanılmak üzere paketler vardır.

QDK, özelleştirilmiş kimya, makine öğrenimi ve sayısal kitaplıklarıyla birlikte standart bir kitaplık içerir.

Belgelerde, hızlı bir şekilde başlamanıza yardımcı olacak bir Q# dili kılavuzu, öğreticiler ve örnek kodun yanı sıra kuantum bilişimi kavramlarını daha ayrıntılı incelemenize yardımcı olacak zengin makaleler bulunur.  

## <a name="microsoft-quantum-hardware-partners"></a>Microsoft kuantum donanımı iş ortakları

Microsoft, geliştiricilere kuantum donanımına bulut erişimi sağlamak amacıyla kuantum donanımı şirketleriyle iş ortaklığı kuruyor. Geliştiriciler [Azure Quantum](https://azure.microsoft.com/services/quantum/) platformu ve Q# dilinden yararlanarak, kuantum algoritmalarını keşfedebilir ve kendi kuantum programlarını farklı türlerdeki kuantum donanımlarında çalıştırabilir.

Hem [IonQ](https://ionq.com/news/november-4-2019-microsoft-partnership) hem de [Honeywell](https://www.honeywell.com/en-us/newsroom/news/2019/11/the-future-of-quantum-computing), elektronik bir alanda kapalı tutulan iyonlardan tek tek yararlanan **kapalı iyon bazlı** işlemciler kullanır, [QCI](https://quantumcircuits.com/news-and-publications/quantum-circuits-partners-with-microsoft-on-azure-quantum) ise süper iletkenli devreler kullanır.

## <a name="next-steps"></a>Sonraki adımlar

[Kuantum bilişimine yönelik temel kavramlar](xref:microsoft.quantum.overview.understanding)
[Hızlı başlangıçlar](xref:microsoft.quantum.welcome)