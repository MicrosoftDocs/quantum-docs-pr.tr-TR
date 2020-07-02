---
title: Q# Jupyter Not Defterleri ile geliştirme
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274158"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Q# Jupyter Not Defterleri ile geliştirme

Q# Jupyter Not Defterlerinde Q# işlemleri geliştirmek için QDK'yi yükleyin.

Jupyter Not Defterleri yönergeler, notlar ve diğer içeriklerin yanı sıra yerinde kod yürütmeye olanak sağlar. Bu ortam, ekli açıklamalar veya kuantum bilişimi etkileşimli öğreticileri ile Q# kodu yazmak için idealdir. Kendi Q# not defterlerinizi oluşturmaya başlamak için gerekenler aşağıda verilmiştir.

IQ# (ay-kü-şarp okunur) öncelikli olarak Jupyter ve Python tarafından .NET Core SDK için kullanılan ve Q# işlemlerinin derlenmesine ve benzetiminin yapılmasına yönelik temel işlevselliği sağlayan bir uzantıdır.

> [!NOTE]
> * Q# Jupyter Not Defterlerinde yalnızca Q# kodu çalıştırılabilir ve işlemler dış konak programlarından (ör. Python veya C# dosyaları) çağrılamaz. Amacınız bir dış klasik konak programını kuantum programı ile birleştirmekse, bu ortam uygun değildir.

1. Ön koşullar

    - [Python](https://www.python.org/downloads/) 3.6 veya üzeri
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. `iqsharp` paketini yükleyin

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > `dotnet iqsharp install` adımında bir hata alırsanız yeni bir terminal penceresi açın ve yeniden deneyin.
    > Bu adım da işe yaramazsa yüklü olan `dotnet-iqsharp` aracını (Windows’da `dotnet-iqsharp.exe`) bulup çalıştırmayı deneyin:
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > `/path/to/dotnet-iqsharp`, dosya sisteminizdeki `dotnet-iqsharp` aracının mutlak yolu ile değiştirilmelidir.
    > Genellikle bu, kullanıcı profili klasörünüzdeki `.dotnet/tools` altında bulunur.

1. `Hello World` uygulaması oluşturarak yüklemeyi doğrulayın

    - Not defteri sunucusunu başlatmak için aşağıdaki komutu çalıştırın:

        ```
        jupyter notebook
        ```

    - Jupyter Not Defterini açmak için komut satırı tarafından sağlanan URL’yi kopyalayıp tarayıcınıza yapıştırın.

    - Bir Q# çekirdeği ile Jupyter Not Defteri oluşturun ve aşağıdaki kodu birinci not defteri hücresine ekleyin:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Not defterinin şu hücresini çalıştırın:

        ![Q# kodu içeren Jupyter Not Defteri hücresi](~/media/install-guide-jupyter.png)

        Hücrenin çıktısında `SayHello` görmeniz gerekir. Jupyter Not Defterinde çalışırken Q# kodu derlenir ve not defteri bulduğu işlemlerin adını çıkarır.


    - Yeni bir hücrede, az önce oluşturduğunuz işlemi `%simulate` komutunu kullanarak yürütün (simülatör içinde):

        ![%simulate magic içeren Jupyter Not Defteri hücresi](~/media/install-guide-jupyter-simulate.png)

        Ekrana yazdırılmış iletiyle birlikte çağırdığınız işlemin sonucuna da görüyor olmalısınız (burada, işlemimiz yalnızca `Unit` türü döndürdüğünden boş `()` demetini görüyoruz).

## <a name="next-steps"></a>Sonraki adımlar

Artık Q# Jupyter Not Defterleri için QDK’yi yüklediğinize göre, Q# kodunuzu doğrudan Jupyter Notebook ortamı içinde yazarak [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.

Q# Jupyter Not Defterleri ile yapabileceklerinize ilişkin daha fazla örnek için lütfen şuraya göz atın:
- [Q# ve Jupyter Notebook’a giriş](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Burada, bu ortamda Q# kullanmayı gösteren bir Q# Jupyter Not Defteri bulacaksınız.
- [Quantum Katas](xref:microsoft.quantum.overview.katas), kendi hızınızda ilerleyebileceğiniz öğreticilerden ve Q# Jupyter Not Defterleri biçimindeki programlama alıştırmaları dizilerinden oluşan bir açık kaynak koleksiyondur. [Quantum Katas öğretici not defterleri](https://github.com/microsoft/QuantumKatas#tutorial-topics) iyi bir başlangıç noktasıdır. Quantum Katas, size aynı anda hem kuantum bilişiminin hem de Q# programlamanın öğelerini öğretmeyi amaçlar. Bu öğreticiler, Q# Jupyter Not Defterleri ile oluşturabileceğiniz içerik türüne dair harika bir örnektir.
