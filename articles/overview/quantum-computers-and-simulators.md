---
title: Kuantum bilgisayarlar ve kuantum simülatörleri
description: Kuantum donanımı, kuantum simülatörleri ve kuantum işlemlerinin nasıl çalıştığı hakkında bilgi edinin.
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.simulators
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8691838b2d6c54baa40042245eee8c901a7ca965
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835018"
---
# <a name="quantum-computers-and-quantum-simulators"></a>Kuantum bilgisayarlar ve kuantum simülatörleri

Kuantum bilgisayarlar hala geliştirme süreçlerinin ilk aşamalarındadır. Donanım ve bakım pahalıdır ve çoğu sistemler üniversitelerde ve araştırma laboratuvarlarında bulunur. Ancak teknoloji gelişmektedir ve bazı sistemlere yönelik sınırlı genel erişim sunulmaktadır.

Kuantum simülatörleri, klasik bilgisayarlarda çalışan ve kubitlerin farklı işlemlere nasıl tepki vereceğini tahmin eden bir ortamda kuantum programları çalıştırıp test etmeyi mümkün hale getiren yazılım programlarıdır.

## <a name="quantum-hardware"></a>Kuantum donanımı

Bir kuantum bilgisayarın başlıca üç bölümü vardır: kubitleri barındıran bir alan, sinyalleri kubitlere aktarmaya yönelik bir yöntem ve program çalıştırıp yönergeler göndermeyi sağlayan klasik bir bilgisayar.

- Kubitler için kullanılan kuantum malzemeleri kırılgandır ve çevresel müdahalelere karşı oldukça duyarlıdır. Bazı kubit depolama yöntemlerinde, kubitleri barındıran birim, bunların uyumluluğunu en üst düzeye çıkarmak için mutlak sıfırın hemen üzerinde bir sıcaklıkta tutulur. Diğer kubit barındırma türlerinde, titreşimleri en aza indirmeye ve kubitleri kararlı hale getirmeye yardımcı olmak için bir vakum haznesi kullanılır.  
- Sinyaller; mikrodalgalar, lazer ve voltaj gibi çeşitli yöntemler kullanılarak kubitlere gönderilebilir.

Kuantum bilgisayarlar, doğru bir şekilde çalışmak üzere çok sayıda zorlukla karşılaşır. Kuantum bilgisayarlarda hata düzeltmesi önemli bir sorundur ve ölçeği artırmak (daha fazla kubit eklemek) hata oranını artırır. Bu sınırlamalar nedeniyle, bir kuantum bilgisayarın masaüstünüze gelmesi ancak uzak bir gelecekte mümkün olsa da, ticari olarak uygun laboratuvar tabanlı bir kuantum bilgisayarın kullanıma sunulması daha yakındır.

## <a name="quantum-simulators"></a>Kuantum simülatörleri

Klasik bilgisayarlarda çalışan kuantum simülatörleri, kuantum algoritmalarının bir kuantum sisteminde hesaplanmasının simülasyonunu yapmanıza olanak sağlar.  Microsoft Quantum geliştirme seti (QDK), diğer özelleştirilmiş kuantum simülatörlerinin yanı sıra tam durumlu bir vektör simülatörü içerir.

## <a name="topological-qubit"></a>Topolojik kubit

Microsoft topolojik kubitlere dayalı bir kuantum bilgisayar geliştirmektedir. Topolojik kubit, içinde bulunduğu ortamdaki değişikliklerden daha az etkilenir, dolayısıyla gerekli dış hata düzeltme derecesi azalır.

Topolojik kubitler daha yüksek kararlılık ve ortam gürültüsüne daha fazla dayanıklılık gösterir; diğer bir deyişle daha uzun süre ölçeklenebilir ve güvenilirliği sürdürebilir.

## <a name="microsoft-and-quantum-hardware-partnerships"></a>Microsoft ve kuantum donanımı iş ortaklıkları

Microsoft, kuantum bilgisayarları gelecekte geliştiricilerin erişebileceği hale getirmek için kuantum donanımı üreticileri olan IonQ, Honeywell ve QCI ile iş ortaklığı kuruyor. Geliştiriciler, Azure Quantum platformundan yararlanarak kuantum programları yazmak ve bunları uzaktan çalıştırmak için Microsoft Quantum geliştirme setini (QDK) ve Q# dilini kullanabilir.

## <a name="quantum-computations"></a>Kuantum hesaplamaları

Kuantum bilgisayarda veya kuantum simülatöründe hesaplamalar gerçekleştirmek için temel bir süreç izlenir:

- Kubitlere erişme
- Kubitleri istenen durumda başlatma
- Kubitlerin durumlarını dönüştürecek işlemleri gerçekleştirme
- Kubitlerin yeni durumlarını ölçme

Kubit başlatma ve dönüştürme işlemi, **kuantum işlemleri** (bazen kuantum geçitleri olarak adlandırılır) kullanılarak yapılır. Kuantum işlemleri, klasik bilişimdeki AND, OR, NOT ve XOR gibi mantıksal işlemlere benzer. Bir işlem, kubitin durumunu 1’den 0’a çevirmek veya bir kubit çiftini dolaşık hale getirmek gibi temel eylemlerden, süper konumlu bir kubitin iki değerden birine çökmesi olasılığını etkilemek için seri halindeki birden çok işlemi kullanmaya kadar farklılık gösterebilir.

> [!NOTE] 
> [Q# kitaplıkları](xref:microsoft.quantum.libraries), alt düzey kuantum işlemlerinin karmaşık bileşimlerini tanımlayan yerleşik işlemler sağlar. Kubitleri dönüştürmek ve daha karmaşık kullanıcı tanımlı işlemler oluşturmak için kitaplık işlemlerini kullanabilirsiniz.  

Hesaplama sonucunu ölçmek bize bir yanıt verir ancak bazı kuantum algoritmaları için her zaman doğru yanıtı vermez. Bazı kuantum algoritmalarının sonucu, kuantum işlemleri tarafından yapılandırılan olasılığa bağlı olduğundan bu hesaplamalar, bir olasılık dağılımı almak ve sonuçların doğruluğunu iyileştirmek için birden çok kez çalıştırılır.  Bir işlemin doğru bir yanıt döndürmüş olma güvencesi, kuantum doğrulama olarak bilinir ve bu, kuantum bilişimde önemli bir zorluk olarak ortaya çıkar.

## <a name="summary"></a>Özet

Kuantum bilişimin bazı kavramları klasik bilişim ile aynıdır ancak kuantum bilişim, bunların yanı sıra birkaç yenilik ekler. Aşağıda bazı önemli çıkarımlar verilmiştir:

- Kuantum donanım pahalıdır ve bu donanımla çalışılması hassasiyet gerektirir, bu nedenle programları yazmak ve test etmek için kuantum simülatörleri kullanılır.
- Hem klasik hem de kuantum bilgisayarlar, hesaplamaları hazırlamak için mantıksal işlemler (veya geçitler) kullanır.
- Kuantum hesaplamaları olasılıklar döndürür.

Kuantum donanımındaki ve tekniklerindeki gelişmeler, bu alanı hızla değiştirmektedir. Birkaç [güncel gelişme](https://phys.org/search/?search=quantum+computer&s=0) aşağıda verilmiştir.

## <a name="next-steps"></a>Sonraki adımlar

[Q# programlama dili ve QDK nedir?](xref:microsoft.quantum.overview.q-sharp)
