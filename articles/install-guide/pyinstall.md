---
title: 'Q # + Python ile geliştirme'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1e40c2dddeaf4fad41693c976493f10fffffa139
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831010"
---
# <a name="develop-with-q--python"></a>Q # + Python ile geliştirme

Q # işlemlerini çağırmak için Python konak programları geliştirmek üzere QDK 'yi yükler.

1. Önkoşullar

    - [Python](https://www.python.org/downloads/) 3.6 veya üzeri
    - [PIP](https://pip.pypa.io/en/stable/installing) Python paket yöneticisi
    - [.NET Core SDK 3,1 veya üzeri](https://www.microsoft.com/net/download)


1. Q # ve Python arasında birlikte çalışabilirliğine izin veren bir Python paketi olan `qsharp` paketini yükler.

    ```bash
    pip install qsharp
    ```

1. Q # işlemlerini derlemek ve yürütmek için temel işlevselliği sağlayan Jupileter ve Python tarafından kullanılan bir çekirdek `iqsharp`yükler.

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. Herhangi bir IDE 'de soru-cevap özelliğini kullanarak soru-cevap için Visual Studio Code (VS Code) IDE kullanmanız önerilir. Visual Studio Code ve QDK Visual Studio Code uzantısını kullanarak daha zengin işlevselliğe erişebilirsiniz.

    - [Vs Code](https://code.visualstudio.com/download) (Windows, Linux ve Mac) 'i yükler
    - [Vs Code Için QDK uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)yükler.

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

        ```bash
        python hello_world.py
        ```

    - Çıktıyı doğrulayın. Programınız aşağıdaki satırları çıkarmalıdır:

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * Ayrıca, Python Jupyıter not defterlerini, klasik Python programını yazmak ve hücrelerden Q # işlemlerini çağırmak için de kullanabilirsiniz. Python kodu yalnızca normal bir Python programıdır.

## <a name="whats-next"></a>Sırada ne var?

Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.write-program) yazıp çalıştırabilirsiniz.