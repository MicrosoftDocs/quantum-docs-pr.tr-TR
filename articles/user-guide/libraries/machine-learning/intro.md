---
title: Kuantum makine öğrenimi kitaplığı
description: Makine öğrenimi 'nin hisse sistemlerinde nasıl kullanıldığını öğrenin
author: alexeib2
ms.author: alexeib
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9f7f892fb2b76432942c86163497c22f0c73d51f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833796"
---
# <a name="introduction-to-quantum-machine-learning"></a>Hisse Machine Learning giriş

## <a name="framework-and-goals"></a>Çerçeve ve hedefler

Hisse ve bilgi işleme, klasik makine öğrenimi sınıflandırıcılarında güçlü bir alternatiftir. Özellikle, işlem kaynağı olarak, ve sınıf çıkarımı için hisse ölçümü kullanarak, özellik sayısına kısa bir değer olan, ortalama kayıt verilerini kodlayabileceğimizi sağlar.
Devre merkezli hisse ayırıcı, veri kodlamasını hızlı bir şekilde birleştiren ve veri örneklerinin sınıf etiketlerini çıkarması için ölçüm tarafından izlenen görece basit bir hisse atım çözümüdür.
Amaç, konu devrelerinin klasik şekilde ve depolama alanının yanı sıra son derece büyük özellik alanları için de devre parametrelerinin karma hisse/klasik eğitimine sahip olmasını sağlamaktır.

## <a name="classifier-architecture"></a>Sınıflandırıcı mimarisi

Sınıflandırma, \{ belirli veri örneklerinin $ y_1, y_2, \lnoktalar, y_d $ sınıf etiketlerini çıkarmaktır \} . "Eğitim veri kümesi", \{ önceden atanmış bilinen etiketlerle $ \mathcal{D} = (x, y)} $ örnekleri koleksiyonudur. Burada $x $ bir veri örneğidir ve $y $ "eğitim etiketi" adı verilen bilinen etikettir.
Geleneksel yöntemlere benzer şekilde, hisse sınıflandırması üç adımdan oluşur:
- veri kodlama
- sınıflandırıcı durumunun hazırlanması
- ölçüm, ölçümün dayalı doğası nedeniyle, bu üç adım birden çok kez tekrarlanmış olmalıdır. Hem kodlama hem de sınıflandırıcı durumunun bilgi işlem miktarı *hisse*kullanım yoluyla yapılır. Kodlama devresi genellikle veri odaklı ve parametre-ücretsiz olsa da, sınıflandırıcı devresi uygun bir öğrenme parametreleri kümesi içerir. 

Önerilen çözümde, sınıflandırıcı devresi tek qubit döndürmeler ve iki qubit kontrollü döndürmeler oluşur. Burada öğrenme parametreleri, döndürme açıtlardır. Döndürme ve denetlenen döndürme kapıları, hisse alma işlemi için *evrensel* olarak bilinir. Bu, tüm Unitary ağırlığı, söz konusu kapıları oluşan uzun bir devreye göre parçalanabileceği anlamına gelir.

Önerilen sürümde, yalnızca tek bir sıklık tahmini tarafından izlenen yalnızca bir devre desteklenir.
Bu nedenle çözüm, düşük dereceli bir polinom çekirdeği olan destek vektör makinesi 'nin bir hisse andır.

![Multilayer Perceptron vs. devre merkezli sınıflandırıcı](~/media/DLvsQCC.png)

Basit bir hisse sınıflandırıcı tasarımı, geleneksel destek vektör makinesi (SVM) çözümüyle karşılaştırılabilir. SVM 'nin büyük/küçük bir bir çekirdek biçimi olan $ \sum \ alpha_j k (x_j, x) $k $ gibi bir veri $x örneği için çıkarım, belirli bir çekirdek işlevidir.

Buna karşılık, hisse bir sınıflandırıcı $p tahmine ici kullanır (y │ x, U (\teta)) = 〈 U (\teta) x | D | U (\teta) x 〉 $. Bu, ruıt ile benzerdir ancak teknik olarak oldukça farklıdır. Bu nedenle, basit bir genlik kodlaması kullanıldığında, $p (y │ x, U (\teta)) $, $x $ ' ın yükseltilmiş tudes biçiminde bir ikinci dereceden formdur, ancak bu formun katmaları artık bağımsız olarak öğrenilmemelidir; Bunlar, genellikle, "$" vekt$x örünün boyutundan büyük ölçüde daha az öğrendiği $ \teta $ parametrelerine sahip olan devre $U (\teta) $ öğesinin matris öğelerinden toplanır. Özgün özelliklerde $p polinom derecesi (y │ x, U (\teta)) $, $x $ $l $ kopyaları üzerinde hisse bir ürün kodlaması kullanılarak $2 ^ l $ değerine artırılabilir.

Mimarimiz görece basit devreleri araştırır. bu nedenle, tüm aralıklarda veri özellikleri arasındaki tüm bağıntıları yakalamak için *hızlı* bir şekilde olmalıdır. Aşağıdaki şekilde, en faydalı hızlı bir şekilde, devtoze devre bileşeni örneği gösterilmektedir. Bu geometriye sahip bir devre yalnızca $3 n + 1 $ kapısından oluşuyor olsa da, hesapladığı Unitary ağırlığı, $2 ^ n $ özellikleri arasında önemli bir çapraz konuşmayı sağlar.

![5 qubit üzerinde hızlı bir şekilde hisse atıştırın (iki döngüsel katman ile).](~/media/5-qubit-qccc.png)

Yukarıdaki örnekteki devre 6 tek qubit kapıları $ (G_1, \lnoktalar, G_5; G_ {16} ) $ ve 10 2-qubits kapıları $ (G_6, \lnoktalar, g_ {15} ) $. Her bir geçit öğrendiğimiz bir parametreyle tanımlanmış olduğu varsayıldığında, 16 öğrendiğimiz parametrelere sahip olduğumuz ve 5-qubit tepk alanının boyutu 32 olur. Bu tür devre geometrisi, her türlü $-qubit kaydına kolayca genelleştirilerek, $n $ tek olduğunda, $2 ^ n $ boyutlu özellik alanı için $3 n + 1 $ parametreli bir $n.

## <a name="classifier-training-as-a-supervised-learning-task"></a>Denetimli bir öğrenme görevi olarak sınıflandırıcı eğitimi

Bir sınıflandırıcı modelinin eğitimi, işlem parametrelerinin en iyi değerlerini bulmayı içerir, bu nedenle eğitim örnekleri genelinde doğru eğitim etiketlerini erteleme olasılığını en üst düzeye çıkarır.
Burada, yalnızca iki düzey sınıflandırmayla kendimize sorun yaptık, yani $d = $2 ve yalnızca $y _1, y_2 $ gibi etiketlere sahip iki sınıf vardır.

> [!NOTE]
> Yöntemlerimizi rastgele sayıda sınıfa Genelleştirmenin bir yolu, qudits ile qubit, yani $d $ tabanlı durumlarıyla ve iki yönlü ölçümü ile $d $ yönlü ölçümle aynı şekilde.

### <a name="likelihood-as-the-training-goal"></a>Eğitim hedefi olma olasılığı

Öğrenime hisse için $U (\teta) $, $ \teta $ parametrelerinin bir vektörü olduğu ve $M $ ile son ölçümü belirten, doğru etiket çıkarımını ortalama olasılığı olan $ $ \begin{hizalaması} \mathcal{L} (\teta) = \frac {1} {| \mathcal{D} |} \left (\ sum_ {(x, y_1) \In\mathcal{D}} P (M = y_1 | U (\teta) x) + \ sum_ {(x, y_2) \in\mathcal{D}} P (M = y_2 | U (\teta) x) \right) \end{hizalaması} $ $ burada $P (M = y | z) $, $y $ ' in hisse durum $z $ ' i ölçmesi olasılığının bir olasılığıdır.
Burada, $ \mathcal{L} (\teta) $ olasılığının $ \teta $ ' da düzgün olduğunu ve herhangi bir $ \ theta_j $ ' deki türevi, olasılık işlevinin kendisi için kullanılan aynı hisse protokolde olan temelde hesaplanarak hesaplanır. Bu, gradyan tarafından $ \mathcal{L} (\teta) $ için optimize etmenizi sağlar.

### <a name="classifier-bias-and-training-score"></a>Sınıflandırıcı sapması ve eğitim puanı

$ \Teta $ içindeki parametrelerin bazı ara (veya son) değerleri verildiğinde, çıkarımı *yapmak için tek* bir gerçek değer saptamız gerekir $b $. Etiket çıkarımı kuralı aşağıdaki gibi çalışmaktadır: 
- Bir örnek $x $ etiketi, $y $ IF ve yalnızca $P (d = y_2) olarak atanır. U (\teta) x) + b > $0,5 (RULE1) (Aksi takdirde, $y _1 $) etiketi atanır

Açıkça $b $, anlamlı olması için $ (-0,5, + 0,5) $ aralığında olmalıdır.

RULE1 başına $x $ için gösterilen etiket aslında $y $ öğesinden farklıysa, \mathcal{D} $ içindeki *bir eğitim* durumu $ (x, y), sapma $b $ olarak kabul edilir. Hatalı sınıflandırmaların genel sayısı, $b $ sapması verilen sınıflandırıcının *eğitim puanı* olur. *En iyi* sınıflandırıcı sapması $b $ eğitim Puanını en aza indirir. Önceden hesaplanan olasılık tahminlerinin $ \{ P (M = y_2 | olduğunu görmek kolaydır | U (\teta) x) | (x, *) \in\mathcal{D} \} $, en iyi sınıflandırıcı farkı, en fazla $ \ Log_2 (| \mathcal{D} |) yaparak $ (-0,5, + 0,5) $ aralığında ikili arama tarafından bulunabilir. $ adımları.

### <a name="reference"></a>Başvuru

Bu bilgiler, kodla yürütmeye başlamak için yeterli olmalıdır. Ancak, bu model hakkında daha fazla bilgi edinmek istiyorsanız lütfen orijinal teklifi okuyun: [ *' devre merkezli hisse ıcılar ', Maria Schuld, Alex Bocharov, Kronysta svore ve Nathan Wiebe*](https://arxiv.org/abs/1804.00633)

Sonraki adımlarda göreceğiniz kod örneğine ek olarak, [Bu öğreticide](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/QuantumClassification) hisse sınıflandırması 'nı keşfetmeye de başlayabilirsiniz 
