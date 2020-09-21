---
title: Hisse makine öğrenimi kitaplığı sözlüğü
description: Hisse makine öğrenimi terimleri sözlüğü
author: alexeib2
ms.author: alexeib
ms.date: 2/27/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.training
no-loc:
- Q#
- $$v
ms.openlocfilehash: 39974af0121a5167f1965e508cd595535178548b
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833908"
---
# <a name="quantum-machine-learning-glossary"></a>Hisse Machine Learning sözlüğü

Devre merkezli bir hisse sınıflandırıcının eğitimi, çok sayıda hareketli parçaya sahip olan ve geleneksel sınıflandırıcılara yönelik eğitim olarak denemeye ve hataya göre aynı (veya biraz daha büyük) bir işlem yapılmasını gerektiren bir işlemdir. Burada, bu eğitim sürecinin ana kavramlarını ve bu malzemeleri tanımlayacağız.

## <a name="trainingtesting-schedules"></a>Eğitim/test zamanlamaları

Sınıflandırıcı eğitiminde bir *zamanlama* , bir genel eğitim veya test kümesindeki veri örneklerinin bir alt kümesini açıklar. Bir zamanlama genellikle örnek dizinlerin bir koleksiyonu olarak tanımlanır.

## <a name="parameterbias-scores"></a>Parametre/sapma puanları

Bir aday parametresi vektörü ve bir sınıflandırıcı sapması verildiğinde, *doğrulama puanı* seçilen doğrulama zamanlamalarına göre ölçülür ve zamanlamaya göre tüm örneklerde sayılan bir dizi hatalı sınıflandırmalarla ifade edilir.

## <a name="hyperparameters"></a>Ayarlama hiperparametreleri

Model eğitimi işlemi, *hiper parametreler*adlı bazı önceden ayarlanmış değerlere tabidir:

### <a name="learning-rate"></a>Öğrenme oranı

Bu, anahtar hiper parametrelerinden biridir. Geçerli stochastik gradyan tahmini 'nin parametre güncelleştirmesini ne kadar etkiler olduğunu tanımlar. Parametre güncelleştirme Delta boyutu öğrenme oranı ile orantılıdır. Daha az öğrenme oranı değerleri, daha yavaş parametre evrimine ve daha yavaş yakınsama olmasına neden olur, ancak büyük oranda büyük bir değer, Gradyan ' ın belirli bir yerel en düşük düzeyde hiç tamamlanmadığından yakınsama işlemi tamamen bozulabilir. Öğrenme oranı eğitim algoritması tarafından bir ölçüde uyarlanırken, için iyi bir başlangıç değeri seçilmesi önemlidir. Öğrenme oranı için olağan varsayılan başlangıç değeri 0,1 ' dir. Öğrenme oranının en iyi değerini seçmek, ince bir örnektir (örneğin, Goodfellow et bölümünün 4,3 bölümüne bakın., "derin öğrenme", MıT Press, 2017).

### <a name="minibatch-size"></a>Mini yığın boyutu

Tek bir Stokastik gradyanının tahmini için kaç veri örneği kullanıldığını tanımlar. Mini yığın boyutunun daha büyük değerleri genellikle daha sağlam ve daha fazla monoton 'e yol açabilir, ancak herhangi bir gradyan tahmininin maliyeti minimatch boyutuyla orantılıdır. Mini toplu iş boyutu için olağan bir varsayılan değer 10 ' dur.

### <a name="training-epochs-tolerance-gridlocks"></a>Eğitim dönemleri, tolerans, gridkilitleri

"Dönem", zamanlanan eğitim verilerinden bir bütün geçiş anlamına gelir.
Eğitim iş parçacığı başına maksimum dönemler sayısı (aşağıya bakın) Eğitim iş parçacığı, en fazla dönemler çalıştırıldığında sonlanacak (en iyi bilinen aday parametreleriyle birlikte) sona erecek şekilde tanımlanır. Ancak, bu tür bir eğitim daha önce doğrulama zamanlamasında yanlış sınıflandırma oranı seçilen bir toleransın altına düştüğünde daha önce sonlandırılır. Örneğin, yanlış sınıflandırma toleransı 0,01 (%1%) olduğunu varsayalım; 2000 örnek doğrulama kümesinde 20 ' den az sınıflandırma gördüğünüzü kabul ediyorsanız, tolerans düzeyi elde edilir. Aday modelin doğrulama puanı birkaç ardışık dönemler (Gridlock) üzerinde herhangi bir geliştirme göstermezse, eğitim iş parçacığı de zamanından önce sonlanır. Sapmanızı sonlandırmasının mantığı şu anda sabit olarak kodlanmıştır.

### <a name="measurements-count"></a>Ölçüm sayısı

Eğitim/doğrulama puanlarını ve bir hisse uygun gözlemlenenler birden fazla ölçüm gerektiren hisse miktarı ile ilgili olarak bir hisse cihazı miktarındaki Stokastik gradyanının bileşenlerini tahmin etme. Ölçüm sayısı $O (1/\ Epsilon ^ 2) $ $ \epsilon $, istenen tahmin hatası olarak ölçeklendirmelidir.
Thumb kuralı olarak, ilk ölçüm sayısı yaklaşık $1/\ mbox {toleransı} ^ 2 $ (önceki paragrafta tolerans tanımına bakın) olabilir. Gradyanın çok Erratic ve yakınsama çok zor gibi görünüyorsa, birinin ölçüm sayısını yukarı doğru gözden geçirmeniz gerekir.

### <a name="training-threads"></a>Eğitim iş parçacıkları

Sınıflandırıcı için eğitim yardımcı programı olan olasılık işlevi, genellikle kalite gereği önemli ölçüde farklı olabilecek parametre alanında çok sayıda yerel optimize eden bir convex. SGD işlemi yalnızca tek bir en uygun değere yakınlaşdığından, birden çok başlangıç parametresi vektörünü incelemek önemlidir. Machine Learning 'de yaygın olarak kullanılan uygulama, başlangıç vektörlerini rastgele başlatmaktır. Q#Eğitim API 'si, bu tür başlangıç vektörlerine yönelik rastgele bir dizi kabul eder ancak temeldeki kod bunları sırayla araştırır. Bir çok veya daha fazla paralel bilgi işlem mimarisi üzerinde Q# , çağrılar genelinde farklı parametre başlatmaları ile paralel olarak EĞITIM API 'sine birkaç çağrı gerçekleştirmeniz önerilir.

#### <a name="how-to-modify-the-hyperparameters"></a>Hiper parametreleri değiştirme

QML kitaplığında, hiper parametreleri değiştirmek için en iyi yol UDT 'nin varsayılan değerlerini geçersiz kılmasından oluşur [`TrainingOptions`](xref:microsoft.quantum.machinelearning.trainingoptions) . Bunu yapmak için, işlevi ile çağırır [`DefaultTrainingOptions`](xref:microsoft.quantum.machinelearning.defaulttrainingoptions) ve `w/` varsayılan değerleri geçersiz kılmak için işlecini uygular. Örneğin, 100.000 ölçülerini ve 0,01 öğrenme oranını kullanmak için:
 ```qsharp
let options = DefaultTrainingOptions()
w/ LearningRate <- 0.01
w/ NMeasurements <- 100000;
 ```
