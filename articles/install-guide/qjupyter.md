---
title: Q# Jupyter Notebooks ile geliştirme
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 0c4dc856c94b0a694fb99607eda64cec4d5c221d
ms.sourcegitcommit: 328f45a0b64cb6b325fa9d3b3ddb74a6a7a97ee9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83660764"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Q# Jupyter Notebooks ile geliştirme

Q # Jupyıter not defterlerinde Q # işlemleri geliştirmek için QDK 'yi yükler.

Jupi Not defterleri yönergeler, notlar ve diğer içeriklerden sonra yerinde kod yürütmeye olanak sağlar. Bu ortam, yerleşik açıklamalar veya hisse kullanımı etkileşimli öğreticilerle Q # kodu yazmak için idealdir. Kendi Q# not defterlerinizi oluşturmaya başlamak için gerekenler aşağıda verilmiştir.

IQ# (ay-kü-şarp okunur) öncelikli olarak Jupyter ve Python tarafından .NET Core SDK için kullanılan ve Q# işlemlerinin derlenmesine ve benzetiminin yapılmasına yönelik temel işlevselliği sağlayan bir uzantıdır.

> [!NOTE]
> * Q # Jupileter not defterlerinde yalnızca Q # kodunu çalıştırabilir ve işlemler harici konak programlarından (ör. Python veya C# dosyaları) çağrılamaz. Amacınız, bir dış klasik ana bilgisayar programını hisse ile çevreliyorsanız, bu ortam uygun değildir.

1. Ön koşullar

    - [Python](https://www.python.org/downloads/) 3,6 veya üzeri
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. `iqsharp` paketini yükleyin

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. `Hello World` uygulaması oluşturarak yüklemeyi doğrulayın

    - Not defteri sunucusunu başlatmak için aşağıdaki komutu çalıştırın:

        ```bash
        jupyter notebook
        ```

    - Jupyter Notebook açmak için komut satırı tarafından belirtilen URL 'YI kopyalayıp tarayıcınıza yapıştırın.

    - Bir Q # çekirdeğiyle Jupyter Notebook oluşturun ve ilk not defteri hücresine aşağıdaki kodu ekleyin:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Not defterinin şu hücresini çalıştırın:

        ![Q # kodlu Jupyter Notebook hücresi](~/media/install-guide-jupyter.png)

        Hücrenin çıktısında `SayHello` görmeniz gerekir. Jupyter Notebook 'de çalışırken, Q # kodu derlenir ve Not defteri bulduğu işlem (ler) in adını verir.


    - Yeni bir hücrede, komutunu kullanarak yeni oluşturduğunuz işlemi (simülatör içinde) yürütün `%simulate` :

        ![% Benzetim Magic ile Jupyter Notebook hücresi](~/media/install-guide-jupyter-simulate.png)

        İade ettiğiniz işlemin sonucuyla birlikte ekranda yazdırılmış iletiyi görmeniz gerekir (burada, `()` işlem yalnızca bir tür döndürdüğünden, boş tanımlama alanı görüyoruz `Unit` ).

## <a name="next-steps"></a>Sonraki adımlar

Artık, Q # jupi Not defterleri için QDK yükleolduğunuza göre, doğrudan Jupyter Notebook ortamı içinde Q # kodunuzu yazarak [ilk hisse programınızı](xref:microsoft.quantum.quickstarts.qrng) yazabilir ve çalıştırabilirsiniz.

Q # Jupyter Not defterleri ile yapabileceklerinize ilişkin daha fazla örnek için lütfen şu adresten göz atabilirsiniz:
- [Q # ve Jupyter Notebook girişi](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Bu ortamda Q # kullanmayı gösteren bir Q # Jupyter Notebook bulacaksınız.
- Hisse uyumlu öğreticilerin açık kaynaklı bir koleksiyonu olan [hisse katas](xref:microsoft.quantum.overview.katas), Q # jupi Not defterleri biçimindeki programlama alıştırmaları kümesi. [Hisse katas öğretici Not defterleri](https://github.com/microsoft/QuantumKatas#tutorial-topics) iyi bir başlangıç noktasıdır. Hisse katas, size aynı anda hisse bilgi işlem ve Q # programlama öğelerini öğretme amacıyla tasarlanmıştır. Bunlar, Q # jupi Not defterleri ile oluşturabileceğiniz içerik türü için harika bir örnektir.
