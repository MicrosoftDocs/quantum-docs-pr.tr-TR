---
title: Q# nedir?
description: Microsoft tarafından kuantum bilgisayarlara uygulama geliştirmek için oluşturulan bilgisayar dili Q# hakkında bilgi edinin
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: 3fd288439c7db7f939240b4388c9cdb114b6535c
ms.sourcegitcommit: edcf15044d7bdf4f8b21fb8f6af4bde475eb13a0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73529981"
---
# <a name="what-is-q"></a>Q# nedir?

Q#, kuantum bilişimine özgü özellikleri olan bir bilgisayar dilidir.

Q# kuantum programcılarına geçit dizisi iyileştirmesi veya kuantum bilgisayar fiziksel uygulaması gibi teknik ayrıntılarla ilgilenmek zorunda kalmadan algoritmalara odaklanmanızı sağlayan bir çerçeve getirir.

Q# bilgisayar dili, kuantum bilgisayarın iç mantığı hakkında kafa yormak zorunda kalmadan algoritmalar geliştirmek için size sezgisel bir tür, işlem ve mantık ifadeleri kümesi sağlar.

## <a name="code-algorithms"></a>Kod algoritmaları

Kuantum bilgisayarların ilk dönemlerinde algoritmalar, klasik bilgi işlem devre şemalarına benzer şekilde görselleştiriliyordu.  Devre modeli Microsoft'ta kuantum bilişimi araştırmasında yıllardır yararlı olsa da, biz geliştiricilerin Q# kullanarak kuantum devrelerinin ötesine geçip kuantum algoritmaları ve uygulamaları geliştirebileceğine inanıyoruz. Q# dili, on yıllardır klasik yazılım geliştirme çalışmalarından çıkardığımız derslerden yararlanmak ve kuantum geliştiricilerini kuantum bilişimini hedefleyen üst düzey dil işlevselliğiyle güçlendirmek için oluşturulmuştur.


## <a name="how-does-q-work"></a>Q# nasıl çalışır?

Q# dilinin temel yapı taşlarından biri, aynı gerçek kubit gibi kopyalanamayan veya doğrudan erişilemeyen `Qubit` türüdür. Bunun yerine bu türü ölçebilir ve ölçümün sonucunu, iki olası değer alabilen (`Zero` ve `One`) bir Q# türü olan `Result` değişkeninde depolarız. Bunun gibi yapılar algoritmaların her zaman kuantum fiziğinin yasalarına uymasını garanti eder ve kuantum bilgisayarlarda veya simülatörlerde doğru bir şekilde çalıştırılabilir.

Q# ayrıca tüm kuantum kurallarına uyulduğundan emin olmak için bazı inceliklerle koşullular ve döngüler gibi klasik mantık özelliklerini de içerir. Örneğin, kuantum işlemlerinin yürütüldüğünden emin olmak için döngülerin yürütülme şeklini kısıtlayabilir.

Q# programları çoğunlukla C# veya Python dilinde yazılmış bir konak programıyla eşlenir ve bu da klasik kodla kuantum kodunun kullanışlı bir düzenlemesini sağlayabilir. C# ve Python gibi dillerin desteklemesinin yanı sıra, QDK IQ# Jupyter çekirdeğiyle Jupyter Notebook desteği de sağlar.

## <a name="use-q-to-learn-quantum-computing"></a>Kuantum bilişimini öğrenmek için Q# kullanma

Şimdiye kadar kuantum bilişimini öğrenmek istediğinizde, kuantum geçitleri ve ölçümlerinin sıralı dizileri biçimindeki algoritmaları anlamak için devre modelini öğrenmeniz gerekiyordu. Q# ile farklı bir yol izleyebilir, kuantum programları yazarak kuantum bilişimini öğrenebilirsiniz.

## <a name="use-q-to-design-quantum-algorithms"></a>Q# kullanarak kuantum algoritması tasarlama

Q# size artan sayıda kitaplık ve kullanıcı tanımlı tür sağlar. Bunlar gelişmiş kuantum algoritmaları oluşturmak için araçları kullanmanıza yardımcı olur. Örneğin iki kubiti, q1 ve q2'yi dolanıklaştırmanız mı gerekiyor? Kubitleri dolanıklaştırmak için gerekli geçitleri tek tek uygulamak yerine zaten yerleşik olarak sağlanan `PrepareEntangledState([q1], [q2])` işlemini kullanabilirsiniz.

## <a name="use-q-to-estimate-quantum-resources"></a>Q# kullanarak kuantum kaynaklarıyla ilgili tahminde bulunma

Quantum Development Kit (QDK) ile birlikte sunulan tam durum bilgisine sahip kuantum simülatörünü kullanarak Q# programınız için yürütme simülasyonu yapabilirsiniz.  QDK ayrıca simülatörde çalıştırılamayacak kadar büyük Q# programlarının performansıyla ilgili içgörüler sağlayan kaynak tahmin araçlarına da sahiptir.  Bu, algoritma tasarımcıları için oldukça değerlidir ve tasarımcılar bu sayede programlarını daha az kaynak kullanacak şekilde ayarlayabilir (daha az sayıda işlem çalıştıran daha az sayıda kubit kullanmak gibi) ve daha küçük ölçekli kuantum donanımlarında çalıştırabilirler.

## <a name="use-q-to-validate-hardware-performance"></a>Q# kullanarak donanım performansını doğrulama

Q# dilinin avantajı, bir programı yazıp kuantum simülatörlerinde çalıştırarak hata ayıklama gerçekleştirdikten sonra farklı kuantum bilgisayarı donanımlarında çalıştırmayı mümkün hale getirmesidir.  Q# dilinde yazılan kıyaslama programları, kuantum bilgisayarlar geliştikçe ve yeni kuantum bilgisayarlar kullanıma sunuldukça donanım performansını doğrulamak ve sonuçları karşılaştırmak için kullanılabilir.  

## <a name="next-steps"></a>Sonraki adımlar

* [Kuantum bilişimini nasıl öğrenebilirim?](xref:microsoft.quantum.overview.learn)
* [Microsoft Quantum Development Kit'i kullanmaya başlama](xref:microsoft.quantum.welcome)
