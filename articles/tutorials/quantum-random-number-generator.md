---
title: Kuantum Rastgele Sayı Oluşturucusu Oluşturma
description: Q#Hisse rastgele sayı Oluşturucu oluşturarak üst konum gibi temel hisse kavramları gösteren bir proje oluşturun.
author: bromeg
ms.author: megbrow
ms.date: 10/25/2019
ms.topic: tutorial
uid: microsoft.quantum.quickstarts.qrng
no-loc:
- Q#
- $$v
ms.openlocfilehash: f36db426a8f0479580117cce44a67ad3a053d5de
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856358"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a>Öğretici: Q\# dilinde Kuantum Rastgele Sayı Oluşturucusu uygulama

' De yazılı bir hisse algoritması örneği Q# , hisse rastgele sayı üreticisidir. Bu algoritma, kuantum mekaniklerinin özelliklerinden faydalanarak rastgele bir sayı üretir.

## <a name="prerequisites"></a>Ön koşullar

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Bir Q# [ Q# uygulama](xref:microsoft.quantum.install.standalone)için bir [Python ana bilgisayar programıyla](xref:microsoft.quantum.install.python)veya bir [C# ana bilgisayar programıyla](xref:microsoft.quantum.install.cs)bir proje oluşturun.

## <a name="write-a-no-locq-operation"></a>İşlem yazma Q#

### <a name="no-locq-operation-code"></a>Q# işlem kodu

1. Program.qs dosyasının içeriğini aşağıdaki kodla değiştirin:

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

[Kuantum bilişimini anlama](xref:microsoft.quantum.overview.understanding) makalemizde de belirtildiği gibi kubit, süper konumda olabilen bir kuantum bilgi birimidir. Bir kubit ölçüldüğünde yalnızca 0 veya 1 olabilir. Bununla birlikte, ölçüden önce, qubit durumu bir 0 ya da bir ölçümle bir 1 okuma olasılığını temsil eder. Olasılığa dayalı olan bu durum, süper konum olarak adlandırılır. Bu olasılığı kullanarak rastgele sayı oluşturabiliriz.

Bizim işlem sırasında, Q# `Qubit` yerel veri türüne Q# `Qubit` ayırmak için `using` deyimi kullanmamız gerekir. Ayrılan kubit her zaman `Zero` durumunda olur. 

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

Artık Q# rastgele bitler üreten bir işlem olduğuna göre, bunu bir tamamen hisse rastgele sayı Oluşturucu oluşturmak için kullanabiliriz. Bir Q# uygulamayı kullanabilir veya bir konak programı kullanabilirsiniz.



### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a>[Q# Visual Studio veya Visual Studio Code ile uygulamalar](#tab/tabid-qsharp)

Tam uygulamayı oluşturmak için Q# , aşağıdaki giriş noktasını Q# programınıza ekleyin: 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

Program, `@EntryPoint()` Proje yapılandırmasına ve komut satırı seçeneklerine bağlı olarak, bir simülatör veya kaynak Estimator üzerinde özniteliğiyle işaretlenmiş işlem veya işlevi çalıştırır.

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

Visual Studio 'da, komut dosyasını çalıştırmak için CTRL + F5 tuşlarına basmanız yeterlidir.

VS Code’da terminale aşağıdakileri yazarak Program.qs dosyasını ilk kez derleyin:

```dotnetcli
dotnet build
```

Sonraki çalıştırmalar için tekrar derlenmesi gerekmez. Çalıştırmak için aşağıdaki komutu girin ve Enter tuşuna basın:

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-prompt"></a>[Visual Studio Code veya komut istemiyle Python](#tab/tabid-python)

Yeni Q# programınızı Python 'da çalıştırmak için aşağıdaki kodu şu şekilde kaydedin `host.py` :

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

Ardından, komut isteminden Python ana bilgisayar programınızı çalıştırabilirsiniz:

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[Visual Studio Code veya Visual Studio ile C#](#tab/tabid-csharp)

Q#C# ' deki yeni programınızı çalıştırmak için `Driver.cs` Aşağıdaki c# kodunu içerecek şekilde değiştirin:

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

Ardından, komut isteminden C# ana bilgisayar programınızı çalıştırabilirsiniz (Visual Studio 'da F5 'e basmalısınız):

```bash
$ dotnet run
The random number generated is 42
```

***
