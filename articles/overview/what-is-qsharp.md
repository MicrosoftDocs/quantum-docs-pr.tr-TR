---
title: Q# ve QDK nedir?
description: Microsoft tarafından kuantum bilgisayarlara uygulama geliştirmek için oluşturulan ve Microsoft Quantum Geliştirme Seti’nin temel bir bileşeni olan Q# bilgisayar dili hakkında bilgi edinin
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: a4bf21887e34ac85f75e5e0b9a033138464fd09d
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2020
ms.locfileid: "77907010"
---
# <a name="what-are-q-and-the-qdk"></a>Q# ve QDK nedir?

Q#, kuantum bilişimiyle kullanmak için özel olarak tasarlanmış özelliklere sahip bir bilgisayar dilidir.
Microsoft Quantum Geliştirme Seti’nin temel bir bileşeni olan Q#, kuantum programcılarına geçit dizisi iyileştirmesi veya kuantum bilgisayar fiziksel uygulaması gibi teknik ayrıntılarla ilgilenmek zorunda kalmadan algoritmalara odaklanmanızı sağlayan bir çerçeve getirir.

QDK, geliştiricilere kuantum programları yazmaya başlamak için ihtiyaç duydukları her şeyi sunan çeşitli araçlardan oluşur.
QDK, Q# dilinin yanı sıra şunları içerir:
* Geliştiricilerin çalışır durumda uygulamalar sunmasına ve gerçek dünyaya yönelik kuantum uygulamaları oluşturmasına olanak sağlayan *Q# kitaplıkları*
* Q# programlarının çalıştırılabileceği çeşitli *hedef makineler*. Bunlar daha büyük kuantum programları için kaynak tahminleri ve simülatörleri ile gürültüsüz bir kuantum bilgisayarı gibi davranan, tam durum bilgisine sahip bir kuantum simülatörünü içerir. İkincisi, fikirler, hata ayıklama programları ve kuantum fiziği hakkında bilgi edinmek için oldukça kullanışlıdır, ancak yalnızca nispeten daha az kubit içeren programlar için etkilidir. Gelecekte hedef makine olarak kullanılabilen kuantum bilişimi donanımları oluşturmak için sabırsızlanıyoruz.
* Visual Studio ve VS Code için uzantılar ile Python ve Jupyter Notebooks ile kullanmak için paketler gibi Q# diliyle çalışmayı mümkün olduğunca sorunsuz hale getiren *araçlar*.
* Q# dilini Python ve C# gibi klasik konak dilleriyle eşlemek için *API belgeleri*

Microsoft Quantum Geliştirme Seti’yle geliştirilen uygulamalar genellikle iki parçadan oluşur:
1. Q# kuantum bilgisayar dili kullanılarak uygulanan ve klasik konak programı tarafından çağrılan bir veya daha fazla kuantum algoritması. Bunlar aşağıdakilerden oluşur: 
    - Q# işlemleri: kuantum işlemleri içeren alt yordamlar ve 
    - Q# işlevleri: kuantum algoritması içinde kullanılan klasik alt yordamlar.
2. Python veya C# gibi klasik bir bilgisayar dilinde uygulanan, ana giriş noktası işlevi gören ve kuantum algoritmasını yürütmek istediğinde Q# işlemlerini çağıran klasik bir program.

## <a name="write-quantum-programs-not-quantum-circuits"></a>Kuantum devreleri değil kuantum programları yazın

Kuantum bilgisayarların ilk dönemlerinde algoritmalar, klasik bilgi işlem devre şemalarına benzer şekilde görselleştiriliyordu.
Devre modeli Microsoft'ta kuantum bilişimi araştırmasında yıllardır yararlı olsa da, biz geliştiricilerin Q# kullanarak kuantum devrelerinin ötesine geçip kuantum algoritmaları ve uygulamaları geliştirebileceğine inanıyoruz.
Q# dili, on yıllardır klasik yazılım geliştirme çalışmalarından çıkardığımız derslerden yararlanmak ve kuantum geliştiricilerini kuantum bilişimini hedefleyen üst düzey dil işlevselliğiyle güçlendirmek için oluşturulmuştur.

## <a name="how-does-q-work"></a>Q# nasıl çalışır?

Q# bilgisayar dili, kuantum bilgisayarın iç mantığı hakkında kafa yormak zorunda kalmadan algoritmalar geliştirmek için size sezgisel bir tür, işlem ve mantık ifadeleri kümesi sağlar.

Q# dilinin temel yapı taşlarından biri, aynı gerçek kubit gibi kopyalanamayan veya doğrudan erişilemeyen `Qubit` türüdür.
Bunun yerine bu türü ölçebilir ve ölçümün sonucunu, iki olası değer alabilen (`Result` ve `Zero`) bir Q# türü olan `One` değişkeninde depolarız.
Bunun gibi yapılar algoritmaların her zaman kuantum fiziğinin yasalarına uymasını garanti eder ve kuantum bilgisayarlarda veya simülatörlerde doğru bir şekilde çalıştırılabilir.

Q# ayrıca tüm kuantum kurallarına uyulduğundan emin olmak için bazı inceliklerle koşullular ve döngüler gibi klasik mantık özelliklerini de içerir.
Örneğin, kuantum işlemlerinin yalnızca belirlenimci klasik alt yordamlar içerebilen işlevlerin içinde çağrılmamasını sağlamak için döngülerin yürütüldüğü yolları kısıtlama.

Q# programları çoğunlukla C# veya Python dilinde yazılmış bir konak programıyla eşlenir ve bu da klasik kodla kuantum kodunun kullanışlı bir düzenlemesini sağlayabilir.
C# ve Python gibi dillerin desteklemesinin yanı sıra, QDK IQ# Jupyter çekirdeğiyle Jupyter Notebook desteği de sağlar.

## <a name="what-can-i-use-q-for"></a>Q# dilini ne için kullanabilirim?

### <a name="use-q-to-learn-quantum-computing"></a>Kuantum bilişimini öğrenmek için Q# kullanma

Şimdiye kadar kuantum bilişimini öğrenmek istediğinizde, kuantum geçitleri ve ölçümlerinin sıralı dizileri biçimindeki algoritmaları anlamak için devre modelini öğrenmeniz gerekiyordu. Q# ile farklı bir yol izleyebilir, kuantum programları yazarak kuantum bilişimini öğrenebilirsiniz.

### <a name="use-q-to-design-quantum-algorithms"></a>Q# kullanarak kuantum algoritması tasarlama

Q# size artan sayıda kitaplık ve kullanıcı tanımlı tür sağlar. Bunlar gelişmiş kuantum algoritmaları oluşturmak için araçları kullanmanıza yardımcı olur. Örneğin iki kubiti, q1 ve q2'yi dolanıklaştırmanız mı gerekiyor? Kubitleri dolanıklaştırmak için gerekli geçitleri tek tek uygulamak yerine zaten yerleşik olarak sağlanan `PrepareEntangledState([q1], [q2])` işlemini kullanabilirsiniz.

### <a name="use-q-to-estimate-quantum-resources"></a>Q# kullanarak kuantum kaynaklarıyla ilgili tahminde bulunma

Quantum Development Kit (QDK) ile birlikte sunulan tam durum bilgisine sahip kuantum simülatörünü kullanarak Q# programınız için yürütme simülasyonu yapabilirsiniz.  QDK ayrıca simülatörde çalıştırılamayacak kadar büyük Q# programlarının performansıyla ilgili içgörüler sağlayan kaynak tahmin araçlarına da sahiptir.  Bu, algoritma tasarımcıları için oldukça değerlidir ve tasarımcılar bu sayede programlarını daha az kaynak kullanacak şekilde ayarlayabilir (daha az sayıda işlem çalıştıran daha az sayıda kubit kullanmak gibi) ve daha küçük ölçekli kuantum donanımlarında çalıştırabilirler.

### <a name="use-q-to-validate-hardware-performance"></a>Q# kullanarak donanım performansını doğrulama

Q# dilinin avantajı, bir programı yazıp kuantum simülatörlerinde çalıştırarak hata ayıklama gerçekleştirdikten sonra farklı kuantum bilgisayarı donanımlarında çalıştırmayı mümkün hale getirmesidir.  Q# dilinde yazılan kıyaslama programları, kuantum bilgisayarlar geliştikçe ve yeni kuantum bilgisayarlar kullanıma sunuldukça donanım performansını doğrulamak ve sonuçları karşılaştırmak için kullanılabilir.  

## <a name="next-steps"></a>Sonraki adımlar

* [Kuantum bilişimi hakkında nasıl bilgi edinebilirim?](xref:microsoft.quantum.overview.learn)
* [Microsoft Quantum Development Kit'i kullanmaya başlama](xref:microsoft.quantum.welcome)
