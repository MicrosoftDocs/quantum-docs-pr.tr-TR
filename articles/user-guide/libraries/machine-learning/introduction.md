---
title: Kuantum makine öğrenimi kitaplığı
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.introduction
ms.openlocfilehash: 4c42612fee3a58e15368677bb2c77a70c5680f45
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276170"
---
# <a name="introduction-to-quantum-machine-learning"></a>Hisse Machine Learning giriş

## <a name="framework-and-goals"></a>Çerçeve ve hedefler

Hisse ve bilgi işleme, klasik makine öğrenimi sınıflandırıcılarının güçlü bir alternatifidir, özellikle de özellik sayısına kısa bir değer olan hisse ve sınıf çıkarma işlemi için, daha önce hisse kaynağı oluşturma ve sınıf çıkarımı için hisse ölçümü oluşturma.
Devre merkezli hisse ayırıcı, veri kodlamasını hızlı bir şekilde birleştiren ve veri örneklerinin sınıf etiketlerini çıkarması için ölçüm tarafından izlenen görece basit bir hisse atım çözümüdür.
Amaç, konu devrelerinin klasik şekilde ve depolama alanının yanı sıra son derece büyük özellik alanları için de devre parametrelerinin karma hisse/klasik eğitimine sahip olmasını sağlamaktır.

## <a name="classifier-architecture"></a>Sınıflandırıcı mimarisi

Sınıflandırma, \{ belirli veri örneklerinin $ y_1, y_2, \lnoktalar, y_d $ sınıf etiketlerini çıkarmaktır \} . "Eğitim veri kümesi", \{ önceden atanmış bilinen etiketlerle $ \mathcal{D} = (x, y)} $ örnekleri koleksiyonudur. Burada $x $ bir veri örneğidir ve $y $ "eğitim etiketi" adı verilen bilinen etikettir.
Geleneksel yöntemlere benzer şekilde, hisse sınıflandırması üç adımdan oluşur:
- veri kodlama
- sınıflandırıcı durumunun hazırlanması
- ölçüm, ölçümün dayalı doğası nedeniyle, bu üç adım birden çok kez tekrarlanmış olmalıdır. Ölçüm, doğrusal olmayan etkinleştirmenin hisse eşdeğeri olarak görüntülenebilir.
Hem kodlama hem de sınıflandırıcı durumunun bilgi işlem miktarı *hisse*kullanım yoluyla yapılır. Kodlama devresi genellikle veri odaklı ve parametre-ücretsiz olsa da, sınıflandırıcı devresi uygun bir öğrenme parametreleri kümesi içerir. 

Önerilen çözümde, sınıflandırıcı devresi tek qubit döndürmeler ve iki qubit kontrollü döndürmeler oluşur. Burada öğrenme parametreleri, döndürme açıtlardır. Döndürme ve denetlenen döndürme kapıları, hisse alma işlemi için *evrensel* olarak bilinir. Bu, tüm Unitary ağırlığı, söz konusu kapıları oluşan uzun bir devreye göre parçalanabileceği anlamına gelir.

![Multilayer Perceptron vs. devre merkezli sınıflandırıcı](~/media/DLvsQCC.png)

Temel yapıyı daha iyi anlamak için bu modeli çok katmanlı bir Perceptron karşılaştırabiliriz. Perceptron $p (y | x, \teta) $, doğrusal olmayan etkinleştirme işlevlerini (neurlanlar) bağlayan doğrusal işlevleri belirten ağırlıklar $ \teta $ parametrized. Bu parametreler modeli oluşturmak için eğitilmiş olabilir. Çıkış katmanında, SOFTMAX gibi doğrusal olmayan etkinleştirme işlevlerini kullanarak bir sınıfa ait bir örnek olasılığını alabilirler. Devre merkezli sınıflandırıcıda, tahmine Tor, model devresinin tek qubit ve iki-qubit denetimli döndürmeler için döndürme açılarının parametrized. Benzer bir biçimde, bu parametreler, gradyan algoritması algoritmasının karma hisse/klasik bir sürümü ile eğitilir. Çıktıyı hesaplamak için, doğrusal olmayan etkinleştirme işlevleri kullanmak yerine, bu sınıfın olasılığı, denetlenen döndürmeler sonrasında belirli bir qubit üzerinden yinelenen ölçümleri okuyarak elde edilir. Bir hisse anındaki klasik verileri kodlamak için, durum hazırlığı için denetlenebilir bir kodlama devresi kullanıyoruz.

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
