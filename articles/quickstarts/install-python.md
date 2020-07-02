---
title: Q# ve Python ile geliştirme
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 6513acd5b9cdce15ce61ed2c0454f46e6a6d9bd0
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274146"
---
# <a name="develop-with-q-and-python"></a>Q# ve Python ile geliştirme

Q# işlemlerini çağırmak için Python konak programları geliştirmek üzere QDK'yi yükleyin.

1. Ön koşullar

    - [Python](https://www.python.org/downloads/) 3.6 veya üzeri
    - [PIP](https://pip.pypa.io/en/stable/installing) Python paket yöneticisi
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Q# ile Python arasında birlikte çalışmayı sağlayan bir Python paketi olan `qsharp` paketini yükleyin.

    ```
    pip install qsharp
    ```

1. Jupyter ile Python tarafından kullanılan, Q# işlemlerinin derlenmesine ve yürütülmesine yönelik temel işlevselliği sağlayan IQ# çekirdeğini yükleyin.

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
  
1. Q# dilini Python ile herhangi bir IDE'de kullanabiliyor olsanız da, Q# + Python uygulamalarınız için Visual Studio Code (VS Code) IDE kullanmanız önerilir. Visual Studio Code ve QDK Visual Studio Code uzantısını kullanarak daha zengin işlevselliğe erişim elde edersiniz.

    - [VS Code](https://code.visualstudio.com/download)’u (Windows, Linux ve Mac) yükleyin
    - [VS Code için QDK uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) yükleyin.

1. `Hello World` uygulaması oluşturarak yüklemeyi doğrulayın

    - `Operation.qs` adlı bir dosya oluşturup dosyaya aşağıdaki kodu ekleyerek küçük bir Q# işlemi oluşturun:

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - Q# `SayHello()` işlemini çağırmak için `hello_world.py` adlı bir Python programı oluşturun:

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - Programı çalıştırın:

        ```
        python hello_world.py
        ```

    - Çıktıyı doğrulayın. Programınız aşağıdaki satırları çıkarmalıdır:

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * Ayrıca Python Jupyter not defterlerini, klasik Python programı yazmak ve hücrelerden Q# işlemlerini çağırmak için de kullanabilirsiniz. Python kodu yalnızca normal bir Python programıdır.

## <a name="next-steps"></a>Sonraki adımlar

Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.
