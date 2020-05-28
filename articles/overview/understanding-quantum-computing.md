---
title: Kuantum bilişimini anlama
description: Kuantum bilgisayarlar nedir ve kuantum mekaniği ilkelerini nasıl kullanır?
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.understanding
ms.openlocfilehash: 65fa85a80021124444fd352f9492d03cbefcb859
ms.sourcegitcommit: a03d79ca3f0774161a9f86a15528d36e1291acce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83433019"
---
# <a name="understanding-quantum-computing"></a>Kuantum bilişimini anlama

Kuantum bilişimi, bilgileri işlemek için kuantum mekaniği ilkelerini kullanır. Bu nedenle, kuantum bilişimi klasik bilişimden farklı bir yaklaşım gerektirir.  Bu farkın bir örneği, kuantum bilgisayarlarda kullanılan işlemcidir.  Klasik bilgisayarlar tanıdık silikon bazlı çipler kullanırken, kuantum bilgisayarlar atom, iyon, foton ve elektron gibi kuantum malzemelerini kullanır.  

Kuantum malzemesi, kuantum mekaniği kanunlarına göre davranır ve olasılık hesaplama, süper konum ve dolaşıklık gibi kavramlardan yararlanır. Bu kavramlar, karmaşık sorunları çözmek için kuantum bilişiminin gücünden yararlanan kuantum algoritmalarının temelini sağlar. Bu makalede, kuantum bilişiminin temel aldığı önemli kuantum mekaniği kavramlarından bazıları açıklanmaktadır.

## <a name="a-birds-eye-view-of-quantum-mechanics"></a>Kuantum mekaniğinin kuşbakışı görünümü

Kuantum teorisi olarak da bilinen kuantum mekaniği, atomik ve atom altı düzeylerdeki parçacıkların incelendiği bir fizik dalıdır. Ancak, kesin gözüyle baktığınız birçok mekanik kanunu kuantum düzeyinde geçerli olmaz. Süper konum, kuantum ölçümü ve dolaşıklık, kuantum bilişiminin merkezinde yer alan üç olaydır.  

### <a name="superposition-vs-binary-computing"></a>Süper konum ve ikili bilişim karşılaştırması

Oturma odanızda egzersiz yaptığınızı düşünün. Tamamen solunuza ve ardından tamamen sağınıza dönün. Şimdi aynı anda hem solunuza hem de sağınıza dönün. Bunu yapamazsınız (en azından kendinizi ikiye bölmeden).  Elbette aynı anda bu iki durumda bulunamazsınız, yani aynı anda hem sola hem de sağa bakamazsınız.

Ancak bir kuantum parçacığıysanız, belirli bir *sola bakma* olasılığınız VE belirli bir *sağa bakma* olasılığınız vardır. Bunun nedeni **süper konum** (**uyumluluk** olarak da bilinir) olarak bilinen bir olaydır.

Elektron gibi bir kuantum parçacığının kendi "sola bakma veya sağa bakma" özellikleri vardır. Örneğin, yukarı veya aşağı olarak adlandırılan **spin** veya klasik ikili bilişime daha yakın hale getirmek için 1 veya 0 diyelim. Bir kuantum parçacığı süper konum durumunda olduğunda, 1 ile 0 arasındaki sonsuz sayıda durumun doğrusal bir bileşimi olur, ancak gerçekten bakana kadar hangisi olacağını bilemezsiniz. Bu da **kuantum ölçümü** adlı bir sonraki olayımızı beraberinde getiriyor.

### <a name="quantum-measurement"></a>Kuantum ölçümü

Şimdi arkadaşınızın evinize geldiğini ve siz egzersiz yaparken resminizi çekmek istediğini düşünün. Büyük olasılıkla, tamamen sola ve tamamen sağa dönmenizin arasındaki halinizi gösteren bulanık bir resim çekmiş olur.

Ancak bir kuantum parçacığıysanız, ilginç bir şey olur. Resim çekilirken nerede olursanız olun, sizi her zaman ya tamamen sola ya da tamamen sağa dönmüş olarak gösterir, arada göstermez.

Bunun nedeni, kuantum parçacığını gözlemleme veya ölçme eyleminin süper konum durumunu **çöktürmesi** (**uyumsuzluk** olarak da bilinir) ve parçacığın 1 veya 0 değerindeki klasik ikili durumlarından birini almasıdır.

Bu ikili durum bizim için yararlıdır, çünkü bilişimde 1’ler ve 0’larla çok sayıda şey yapabilirsiniz. Ancak bir kuantum parçacığı ölçülüp çöktükten sonra, sonsuza dek bu durumda kalır (tıpkı resminiz gibi) ve her zaman 1 veya 0 olur. Ancak daha sonra göreceğiniz gibi, kuantum bilişiminde parçacığın kuantum hesaplamalarında yeniden kullanılabilmesi için parçacığı bir süper konum durumuna “sıfırlayabilen” işlemler vardır.

### <a name="entanglement"></a>Dolaşıklık

Kuantum mekaniğinin belki de en ilginç olayı, iki veya daha fazla kuantum parçacığının birbiriyle **dolaşık** hale gelmesi olanağıdır. Parçacıklar dolaşık hale geldiğinde, herhangi bir parçacığın kuantum durumunun diğer parçacıkların kuantum durumundan bağımsız olarak açıklanamayacağı tek bir sistem oluşturur. Bu, bir parçacığa uyguladığınız her türlü işlemin diğer parçacıklarla da bağıntılı olduğu anlamına gelir.

Bu karşılıklı bağımlılığın yanı sıra, parçacıklar son derece büyük uzaklıklarda (ışık yılları kadar uzaklıkta bile) ayrılsa bile bu bağlantıyı koruyabilir. Kuantum ölçümünün etkileri dolaşık parçacıklar için de geçerli olur. Bu parçacıklardan biri ölçülüp çöktüğünde diğer parçacık da çöker. Dolaşık kubitler arasında bir bağıntı olduğundan, bir kubitin durumunu ölçmek diğer kubitin durumu hakkında bilgi sağlar. Bu özellik, kuantum bilişiminde çok faydalıdır.

### <a name="qubits-and-probability"></a>Kubitler ve olasılık

Klasik bilgisayarlar bilgileri, 1 veya 0 durumlarından birine sahip olabilen ancak asla ikisine birden sahip olamayan bitlerde depolayıp işler. Bunun kuantum bilişimindeki eşdeğeri, kuantum parçacığının durumunu temsil eden **kubittir**. Süper konum nedeniyle, kubitler 1, 0 ya da bunların arasındaki herhangi bir değer olabilir. Bir kubit, yapılandırmasına bağlı olarak, 1 veya 0 değerine çökmeye yönelik belirli bir *olasılığa* sahiptir. Kubitin iki durumdan birine çökme olasılığı, **kuantum girişimi** ile belirlenir. 

Resminizi çeken arkadaşınızı hatırladınız mı? Kamerasında *girişim* filtreleri olarak adlandırılan özel filtreler olduğunu varsayalım. *70/30* filtresini seçer ve resim çekmeye başlarsa, resimlerin %70’inde sola baktığınız, %30’unda ise sağa baktığınız görülür. Filtre, davranış olasılığını etkilemek için kameranın normal durumuna girişimde bulunmuştur.

Benzer şekilde kuantum girişimi, ölçüm sırasında belirli bir sonucun olasılığını etkilemek için bir kubitin durumunu etkiler ve bu olasılık durumu, kuantum bilişimi gücünün üstün olduğu yerdir.

Örneğin, klasik bir bilgisayardaki her bit, 1 veya 0 depolayabilir, böylece iki bit ile dört olası değer (**00**, **01**, **10** ve **11**) depolayabilirsiniz, ancak bunu tek seferde biri olacak şekilde yapabilirsiniz. Ancak süper konumda iki kubit olduğunda, her kubit 1 veya 0 ya da *her ikisi* de olabilir, yani aynı anda bu dört değeri temsil edebilirsiniz. Üç kubitle sekiz değeri temsil edebilir, dört kubitle 16 değeri temsil edebilir ve bu şekilde devam edebilirsiniz.

## <a name="summary"></a>Özet

Bu kavramlar, kuantum mekaniğinin yalnızca giriş kısımlarını oluşturuyor olsa da kuantum bilişimini öğrenme konusunda önemli temel kavramlardır.

- **Süper konum**: Kuantum parçacıklarının tüm olası durumların bir bileşimi olması olanağı.
- **Kuantum ölçümü**: Bir kuantum parçacığını süper konumda gözlemleme ve olası durumlardan birine neden olma işlemi.
- **Dolaşıklık**: Kuantum parçacıklarının ölçüm sonuçlarını birbirleriyle ilişkilendirme olanağı.
- **Kubit**: Kuantum bilişiminde temel bilgi birimi. Kubit, bir kuantum parçacığını tüm olası durumların süper konumunda temsil eder.
- **Girişim**: Bir kubitin iki durumdan birine çökme olasılığını etkilemeye yönelik süper konum nedeniyle kendine özgü davranışı.

## <a name="next-steps"></a>Sonraki Adımlar

> [!div class="nextstepaction"]
> [Kuantum bilgisayarlar ve kuantum simülatörleri](xref:microsoft.quantum.overview.simulators)
