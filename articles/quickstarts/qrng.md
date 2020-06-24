---
title: Kuantum Rastgele Sayı Oluşturucusu Oluşturma
description: Kuantum rastgele sayı oluşturucusu tasarlayarak süper konum gibi temel kuantum kavramlarını gösteren bir Q# projesi oluşturun.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 18e8975e513a87c0a67a6dbb5586cc7dab5a93fb
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630120"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a>Öğretici: Q\# dilinde Kuantum Rastgele Sayı Oluşturucusu uygulama

Kuantum rastgele sayı oluşturucusu, Q# dilinde yazılmış kuantum algoritmalarına örnek olarak gösterilebilir. Bu algoritma, kuantum mekaniklerinin özelliklerinden faydalanarak rastgele bir sayı üretir.

## <a name="prerequisites"></a>Ön koşullar

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Komut satırından Q# kullanmak](xref:microsoft.quantum.install.standalone) veya bir [Python konak programı](xref:microsoft.quantum.install.python) ya da [C# konak programı](xref:microsoft.quantum.install.cs) ile kullanmak üzere bir Q# projesi oluşturun.

## <a name="write-a-q-operation"></a>Q# işlemi yazma

### <a name="q-operation-code"></a>Q# işlem kodu

1. Program.qs dosyasının içeriğini aşağıdaki kodla değiştirin:

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

[Kuantum bilişimini anlama](xref:microsoft.quantum.overview.understanding) makalemizde de belirtildiği gibi kubit, süper konumda olabilen bir kuantum bilgi birimidir. Bir kubit ölçüldüğünde yalnızca 0 veya 1 olabilir. Ancak yürütme sırasında kubitin durumu bir ölçümle 0 veya 1 değerini elde etme olasılığını temsil eder. Olasılığa dayalı olan bu durum, süper konum olarak adlandırılır. Bu olasılığı kullanarak rastgele sayı oluşturabiliriz.

Q# işlemimizde yerel bir Q# veri türü olan `Qubit` veri türünü kullanacağız. `Qubit` ayırmak için `using` deyimi kullanmamız gerekir. Ayrılan kubit her zaman `Zero` durumunda olur. 

`H` işlemini kullanarak, `Qubit` öğemizi süper konuma alabiliriz. Kubiti ölçmek ve değerini okumak için `M` iç işlemi kullanılır.

`Qubit` öğemizi üst konuma alıp ölçtüğümüzde elde ettiğimiz sonuç, kod her çağrıldığında farklı bir değer verecektir.

`Qubit` serbest bırakıldığında yeniden açıkça `Zero` durumuna ayarlanmalıdır, aksi halde simülatörde çalışma zamanı hatası bildirilir. Bunu yapmanın kolay yollarından biri `Reset` çağırmaktır.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Bloch küresi ile kodu görselleştirme

Bloch küresinde kuzey kutbu klasik **0** değerini, güney kutbu ise klasik **1** değerini temsil eder. Süper konum, küredeki bir nokta ile gösterilebilir (ok simgesi kullanılır). Okun ucu kutba ne kadar yakın olursa kubitin ölçüm sonrasında o kutba atanmış olan klasik değeri alma ihtimali o kadar yüksek olur. Örneğin aşağıda kırmızı ok ile gösterilen kubit durumunun ölçüldüğünde **0** değerini verme olasılığı yüksektir.

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

Kodun gerçekleştirdiği işlemleri görselleştirmek için şu gösterimi kullanabiliriz:

* İlk olarak **0** durumunda başlatılan bir kubitle başlıyoruz ve **0** ile **1** olasılıklarının aynı olduğu bir süper konum oluşturmak için buna `H` uyguluyoruz.

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* Ardından kubiti ölçüp çıktıyı kaydediyoruz:

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

Ölçümün sonucu tamamen rastgele olduğundan rastgele bir bit elde ettik. Bu işlemi birkaç kere çağırarak farklı tamsayılar oluşturabiliriz. Örneğin üç rastgele bit elde etmek için işlemi üç kez çağırarak rastgele 3 bitlik sayılar (0 ile 7 arasında rastgele bir sayı) oluşturabiliriz.


## <a name="creating-a-complete-random-number-generator"></a>Eksiksiz bir rastgele sayı oluşturucu oluşturma

Artık rastgele bitler oluşturan bir Q# işlemimiz olduğuna göre, bu işlemi kullanarak eksiksiz bir kuantum rastgele sayı oluşturucu oluşturabiliriz. Q# komut satırı uygulamalarını kullanabilir veya bir konak programı kullanabiliriz.



### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[Visual Studio veya Visual Studio Code ile Q# komut satırı uygulamaları](#tab/tabid-qsharp)

Tam Q# komut satırı uygulamasını oluşturmak için Q# programınıza şu giriş noktasını ekleyin: 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

Yürütülebilir dosya, proje yapılandırmasına ve komut satırı seçeneklerine bağlı olarak simülatör veya kaynak tahmini aracında `@EntryPoint()` özniteliğiyle işaretlenmiş işlemi ya da işlevi çalıştırır.

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

Visual Studio’da betiği yürütmek için Ctrl + F5 tuşlarına basmanız yeterlidir.

VS Code’da terminale aşağıdakileri yazarak Program.qs dosyasını ilk kez derleyin:

```dotnetcli
dotnet build
```

Sonraki çalıştırmalar için tekrar derlenmesi gerekmez. Çalıştırmak için aşağıdaki komutu girin ve Enter tuşuna basın:

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Visual Studio Code veya Komut Satırı ile Python](#tab/tabid-python)

Yeni Q# programınızı Python'dan çalıştırmak için aşağıdaki kodu `host.py` olarak kaydedin:

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

Ardından Python konak programınızı komut satırından çalıştırabilirsiniz:

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[Visual Studio Code veya Visual Studio ile C#](#tab/tabid-csharp)

Yeni Q# programınızı C# dilinden çalıştırmak için `Driver.cs` dosyasını aşağıdaki C# kodunu içerecek şekilde değiştirin:

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

Ardından C# konak programınızı komut satırından çalıştırabilirsiniz (Visual Studio’da F5 tuşuna basmalısınız):

```bash
$ dotnet run
The random number generated is 42
```

***
