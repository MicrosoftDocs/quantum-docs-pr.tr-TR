---
title: 'Q # Jupyıter Not defterleri ile geliştirme'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b7276f9b273f601f30e4938018398353b6a9102d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831078"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Q # Jupyıter Not defterleri ile geliştirme

Q # Jupyıter not defterlerinde Q # işlemleri geliştirmek için QDK 'yi yükler.

Jupi Not defterleri yönergeler, notlar ve diğer içeriklerden sonra yerinde kod yürütmeye olanak sağlar. Bu ortam, yerleşik açıklamalar veya hisse kullanımı etkileşimli öğreticilerle Q # kodu yazmak için idealdir. Kendi Q# not defterlerinizi oluşturmaya başlamak için gerekenler aşağıda verilmiştir.

IQ# (ay-kü-şarp okunur) öncelikli olarak Jupyter ve Python tarafından .NET Core SDK için kullanılan ve Q# işlemlerinin derlenmesine ve benzetiminin yapılmasına yönelik temel işlevselliği sağlayan bir uzantıdır.

> [!NOTE]
> * Q # Jupileter not defterlerinde yalnızca Q # kodunu çalıştırabilir ve işlemler harici konak programlarından (ör. Python veya C# dosyalar) çağrılamaz. Amacınız, bir dış klasik ana bilgisayar programını hisse ile çevreliyorsanız, bu ortam uygun değildir.

1. Önkoşullar

    - [Python](https://www.python.org/downloads/) 3.6 veya üzeri
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


    - Yeni bir hücrede, az önce oluşturduğunuz işlemi (simülatör içinde) `%simulate` komutunu kullanarak yürütün:

        ![%simulate magic içeren Jupyter not defteri hücresi](~/media/install-guide-jupyter-simulate.png)

        İade ettiğiniz işlemin sonucuyla birlikte ekranda yazdırılmış iletiyi görmeniz gerekir (burada, işlem yalnızca bir `Unit` türü döndürdüğünden `()` boş tanımlama alanı görüyoruz.

## <a name="whats-next"></a>Sırada ne var?

Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.write-program) yazıp çalıştırabilirsiniz.
