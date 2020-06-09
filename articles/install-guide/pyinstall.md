---
title: 'Q # ve Python ile geliştirme'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: f18d005012dc1c52aab456f1c7b194d182cab786
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578173"
---
# <a name="develop-with-q-and-python"></a>Q # ve Python ile geliştirme

Q # işlemlerini çağırmak için Python konak programları geliştirmek üzere QDK 'yi yükler.

1. Ön koşullar

    - [Python](https://www.python.org/downloads/) 3,6 veya üzeri
    - [PIP](https://pip.pypa.io/en/stable/installing) Python paket yöneticisi
    - [.NET Core SDK 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. `qsharp`Q # ve Python arasında birlikte çalışabilirliğine izin veren bir Python paketi olan paketini yükler.

    ```
    pip install qsharp
    ```

1. Q # işlemlerini derlemek ve yürütmek için temel işlevselliği sağlayan Jupileter ve Python tarafından kullanılan bir çekirdek olan IQ # öğesini yükler.

    ```dotnetcli
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

        ```
        python hello_world.py
        ```

    - Çıktıyı doğrulayın. Programınız aşağıdaki satırları çıkarmalıdır:

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * Ayrıca, Python Jupyıter not defterlerini, klasik Python programını yazmak ve hücrelerden Q # işlemlerini çağırmak için de kullanabilirsiniz. Python kodu yalnızca normal bir Python programıdır.

## <a name="next-steps"></a>Sonraki adımlar

Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.
