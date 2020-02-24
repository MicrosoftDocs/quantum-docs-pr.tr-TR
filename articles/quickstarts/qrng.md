---
title: Kuantum Rastgele Sayı Oluşturucusu Oluşturma
description: Kuantum rastgele sayı oluşturucusu tasarlayarak süper konum gibi temel kuantum kavramlarını gösteren bir Q# projesi oluşturun.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: d1ad2c1153814e2fa19a38307b2c668c77eae4e3
ms.sourcegitcommit: b7e205aaa7fa1ca9f0daa163e46154945f4bc965
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/18/2020
ms.locfileid: "77441068"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>Hızlı Başlangıç: Q# ile Kuantum Rastgele Sayı Oluşturucusu Oluşturma Tasarlama
Kuantum rastgele sayı oluşturucusu, Q# dilinde yazılmış kuantum algoritmalarına örnek olarak gösterilebilir. Bu algoritma, kuantum mekaniklerinin özelliklerinden faydalanarak rastgele bir sayı üretir. 

## <a name="prerequisites"></a>Ön koşullar

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Q# projesi oluşturma](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>Q# işlemi yazma

### <a name="q-operation-code"></a>Q# işlem kodu

1. Operation.qs dosyasının içeriğini aşağıdaki kodla değiştirin:

 :::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-14":::

[Kuantum Bilişimi nedir?](xref:microsoft.quantum.overview.what) makalesinde de belirttiğimiz gibi kubit, süper konumda olabilen bir kuantum bilgi birimidir. Bir kubit ölçüldüğünde yalnızca 0 veya 1 olabilir. Ancak yürütme sırasında kubitin durumu bir ölçümle 0 veya 1 değerini elde etme olasılığını temsil eder. Olasılığa dayalı olan bu durum, süper konum olarak adlandırılır. Bu olasılığı kullanarak rastgele sayı oluşturabiliriz.

Q# işlemimizde yerel bir Q# veri türü olan `Qubit` veri türünü kullanacağız. `Qubit` ayırmak için `using` deyimi kullanmamız gerekir. Ayrılan kubit her zaman `Zero` durumunda olur. 

`H` işlemini kullanarak, `Qubit` öğemizi süper konuma alabiliriz. Kubiti ölçmek ve değerini okumak için `M` iç işlemi kullanılır.

`Qubit` öğemizi üst konuma alıp ölçtüğümüzde elde ettiğimiz sonuç, kod her çağrıldığında farklı bir değer verecektir. 

`Qubit` serbest bırakıldığında açıkça `Zero` durumuna geri alınmalıdır, aksi halde simülatörde çalışma zamanı hatası oluşur. Bunu yapmanın kolay yollarından biri `Reset` çağırmaktır.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Bloch küresi ile kodu görselleştirme

Bloch küresinde kuzey kutbu klasik **0** değerini, güney kutbu ise klasik **1** değerini temsil eder. Süper konum, küredeki bir nokta ile gösterilebilir (ok simgesi kullanılır). Okun ucu kutba ne kadar yakın olursa kubitin ölçüm sonrasında o kutba atanmış olan klasik değeri alma ihtimali o kadar yüksek olur. Örneğin aşağıda kırmızı ok ile gösterilen kubit durumunun ölçüldüğünde **0** değerini verme olasılığı yüksektir.

<img src="~/media/qrng-Bloch.png" width="175">

Kodun gerçekleştirdiği işlemleri görselleştirmek için şu gösterimi kullanabiliriz:

* İlk olarak **0** durumunda başlatılan bir kubitle başlıyoruz ve **0** ile **1** olasılıklarının aynı olduğu bir süper konum oluşturmak için buna `H` uyguluyoruz.

<img src="~/media/qrng-H.png" width="450">

* Ardından kubiti ölçüp çıktıyı kaydediyoruz:

<img src="~/media/qrng-meas.png" width="450">

Ölçümün sonucu tamamen rastgele olduğundan rastgele bir bit elde ettik. Bu işlemi birkaç kere çağırarak farklı tamsayılar oluşturabiliriz. Örneğin üç rastgele bit elde etmek için işlemi üç kez çağırarak rastgele 3 bitlik sayılar (0 ile 7 arasında rastgele bir sayı) oluşturabiliriz.

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a>Konak program kullanarak eksiksiz bir rastgele sayı oluşturucu oluşturma

Artık rastgele bitler oluşturan bir Q# işlemimiz olduğuna göre, bu işlemi kullanarak konak programla eksiksiz bir kuantum rastgele sayı oluşturucu oluşturabiliriz.

 ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Visual Studio Code veya Komut Satırı ile Python](#tab/tabid-python)
 
 Yeni Q# programınızı Python'dan çalıştırmak için aşağıdaki kodu `host.py` olarak kaydedin:
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 Ardından Python konak programınızı komut satırından çalıştırabilirsiniz:
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[Visual Studio Code veya Komut Satırı ile C#](#tab/tabid-csharp)
 
 Yeni Q# programınızı C# dilinden çalıştırmak için `Driver.cs` dosyasını aşağıdaki C# kodunu içerecek şekilde değiştirin:
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 Ardından C# konak programınızı komut satırından çalıştırabilirsiniz:
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019"></a>[Visual Studio 2019 ile C#](#tab/tabid-vs2019)

 Yeni Q# programınızı Visual Studio'da C# dilinde çalıştırmak için `Driver.cs` dosyasını aşağıdaki C# kodunu içerecek şekilde değiştirin:

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 Ardından F5 tuşuna bastığınızda program yürütülmeye başlayacak ve rastgele oluşturulan sayılar içeren yeni bir pencere açılacaktır: 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***
