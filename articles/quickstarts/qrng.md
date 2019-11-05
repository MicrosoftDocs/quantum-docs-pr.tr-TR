---
title: Kuantum Rastgele Sayı Oluşturucusu Oluşturma
description: Kuantum rastgele sayı oluşturucusu tasarlayarak süper konum gibi temel kuantum kavramlarını gösteren bir Q# projesi oluşturun.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: a7c077eda3e46430cbe6598cb899adb460451f75
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443928"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>Hızlı Başlangıç: Q# ile Kuantum Rastgele Sayı Oluşturucusu Oluşturma Tasarlama
Kuantum rastgele sayı oluşturucusu, Q# dilinde yazılmış kuantum algoritmalarına örnek olarak gösterilebilir. Bu algoritma, kuantum mekaniklerinin özelliklerinden faydalanarak rastgele bir sayı üretir. 

## <a name="prerequisites"></a>Ön koşullar

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Q# projesi oluşturma](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>Q# işlemi yazma

### <a name="q-operation-code"></a>Q# işlem kodu

1. Operation.qs dosyasının içeriğini aşağıdaki kodla değiştirin:

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(q = Qubit())  { // Allocate a qubit.
                H(q);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(q);     // Measure the qubit value.
                Reset(q);
                return r;
            }
        }
    }
    ```

[Kuantum Bilişimi nedir?](xref:microsoft.quantum.overview.what) makalesinde de belirttiğimiz gibi kubit, süper konumda olabilen bir kuantum bilgi birimidir. Bir kubit ölçüldüğünde yalnızca 0 veya 1 olabilir. Ancak yürütme sırasında kubitin durumu bir ölçümle 0 veya 1 değerini elde etme olasılığını temsil eder. Olasılığa dayalı olan bu durum, süper konum olarak adlandırılır. Bu olasılığı kullanarak rastgele sayı oluşturabiliriz.

Q# işlemimizde yerel bir Q# veri türü olan `Qubit` veri türünü kullanacağız. `Qubit` ayırmak için `using` deyimi kullanmamız gerekir. Ayrılan kubit her zaman `Zero` durumunda olur. 

`H` işlemini kullanarak, `Qubit` öğemizi süper konuma alabiliriz. Kubiti ölçmek ve değerini okumak için `M` iç işlemi kullanılır.

`Qubit` öğemizi üst konuma alıp ölçtüğümüzde elde ettiğimiz sonuç, kod her çağrıldığında farklı bir değer verecektir. 

`Qubit` serbest bırakıldığında açıkça `Zero` durumuna geri alınmalıdır, aksi halde simülatörde çalışma zamanı hatası oluşur. Bunu yapmanın kolay yollarından biri `Reset` çağırmaktır.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Bloch küresi ile kodu görselleştirme

Bloch küresinde kuzey kutbu klasik **0** değerini, güney kutbu ise klasik **1** değerini temsil eder. Süper konum, küredeki bir nokta ile gösterilebilir (ok simgesi kullanılır). Okun ucu kutba ne kadar akın olursa kubitin ölçüm sonrasında o kutba atanmış olan klasik değeri alma ihtimali o kadar yüksek olur. Örneğin aşağıda kırmızı ok ile gösterilen kubit durumunun ölçüldüğünde **0** değerini verme olasılığı yüksektir.

<img src="./Bloch.svg" width="175">

Kodun gerçekleştirdiği işlemleri görselleştirmek için şu gösterimi kullanabiliriz:

* İlk olarak **0** durumunda başlatılan bir kubitle başlıyoruz ve **0** ile **1** olasılıklarının aynı olduğu bir süper konum oluşturmak için buna `H` uyguluyoruz.

<img src="./H.svg" width="450">

* Ardından kubiti ölçüp çıktıyı kaydediyoruz:

<img src="./Measurement2.svg" width="450">

Ölçümün sonucu tamamen rastgele olduğundan rastgele bir bit elde ettik. Bu işlevi birkaç kere çağırarak farklı tamsayılar oluşturabiliriz. Örneğin üç rastgele bit elde etmek için işlevi üç kez çağırarak rastgele 3 bitlik sayılar (0 ile 7 arasında rastgele bir sayı) oluşturabiliriz.
