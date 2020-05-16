---
title: 'Q # Jupyıter Not defterleri ile geliştirme'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 38db14ccc5f2406043ff4baee3f562385cdf47a8
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426389"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Q # Jupyıter Not defterleri ile geliştirme

Q # Jupyıter not defterlerinde Q # işlemleri geliştirmek için QDK 'yi yükler.

Jupi Not defterleri yönergeler, notlar ve diğer içeriklerden sonra yerinde kod yürütmeye olanak sağlar. Bu ortam, yerleşik açıklamalar veya hisse kullanımı etkileşimli öğreticilerle Q # kodu yazmak için idealdir. Kendi Q# not defterlerinizi oluşturmaya başlamak için gerekenler aşağıda verilmiştir.

IQ# (ay-kü-şarp okunur) öncelikli olarak Jupyter ve Python tarafından .NET Core SDK için kullanılan ve Q# işlemlerinin derlenmesine ve benzetiminin yapılmasına yönelik temel işlevselliği sağlayan bir uzantıdır.

> [!NOTE]
> * Q # Jupileter not defterlerinde yalnızca Q # kodunu çalıştırabilir ve işlemler harici konak programlarından (ör. Python veya C# dosyaları) çağrılamaz. Amacınız, bir dış klasik ana bilgisayar programını hisse ile çevreliyorsanız, bu ortam uygun değildir.

1. Ön koşullar

    - [Python](https://www.python.org/downloads/) 3,6 veya üzeri
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3,1 veya üzeri](https://www.microsoft.com/net/download)

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

    - Jupyter Not defterini açmak için komut satırı tarafından belirtilen URL 'YI kopyalayıp tarayıcınıza yapıştırın.

    - Bir Q# çekirdeği ile Jupyter not defteri oluşturun ve aşağıdaki kodu birinci not defteri hücresine ekleyin:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Not defterinin şu hücresini çalıştırın:

        ![Q# kodu içeren Jupyter not defteri hücresi](~/media/install-guide-jupyter.png)

        Hücrenin çıktısında `SayHello` görmeniz gerekir. Jupyter not defterlerinde çalışırken Q# kodu derlenir ve not defteri bulduğu işlemlerin adını çıkarır.


    - Yeni bir hücrede, komutunu kullanarak yeni oluşturduğunuz işlemi (simülatör içinde) yürütün `%simulate` :

        ![%simulate magic içeren Jupyter not defteri hücresi](~/media/install-guide-jupyter-simulate.png)

        İade ettiğiniz işlemin sonucuyla birlikte ekranda yazdırılmış iletiyi görmeniz gerekir (burada, `()` işlem yalnızca bir tür döndürdüğünden, boş tanımlama alanı görüyoruz `Unit` ).

## <a name="next-steps"></a>Sonraki adımlar

Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.
