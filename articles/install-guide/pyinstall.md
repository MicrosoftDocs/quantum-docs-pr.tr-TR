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
# <a name="develop-with-q--python"></a><span data-ttu-id="5d499-102">Q # + Python ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="5d499-102">Develop with Q# + Python</span></span>

<span data-ttu-id="5d499-103">Q # işlemlerini çağırmak için Python konak programları geliştirmek üzere QDK 'yi yükler.</span><span class="sxs-lookup"><span data-stu-id="5d499-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="5d499-104">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="5d499-104">Pre-requisites</span></span>

    - <span data-ttu-id="5d499-105">[Python](https://www.python.org/downloads/) 3.6 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="5d499-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="5d499-106">[PIP](https://pip.pypa.io/en/stable/installing) Python paket yöneticisi</span><span class="sxs-lookup"><span data-stu-id="5d499-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="5d499-107">.NET Core SDK 3,1 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="5d499-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)


1. <span data-ttu-id="5d499-108">Q # ve Python arasında birlikte çalışabilirliğine izin veren bir Python paketi olan `qsharp` paketini yükler.</span><span class="sxs-lookup"><span data-stu-id="5d499-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="5d499-109">Q # işlemlerini derlemek ve yürütmek için temel işlevselliği sağlayan Jupileter ve Python tarafından kullanılan bir çekirdek `iqsharp`yükler.</span><span class="sxs-lookup"><span data-stu-id="5d499-109">Install `iqsharp`, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. <span data-ttu-id="5d499-110">Herhangi bir IDE 'de soru-cevap özelliğini kullanarak soru-cevap için Visual Studio Code (VS Code) IDE kullanmanız önerilir.</span><span class="sxs-lookup"><span data-stu-id="5d499-110">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="5d499-111">Visual Studio Code ve QDK Visual Studio Code uzantısını kullanarak daha zengin işlevselliğe erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5d499-111">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="5d499-112">[Vs Code](https://code.visualstudio.com/download) (Windows, Linux ve Mac) 'i yükler</span><span class="sxs-lookup"><span data-stu-id="5d499-112">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="5d499-113">[Vs Code Için QDK uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)yükler.</span><span class="sxs-lookup"><span data-stu-id="5d499-113">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="5d499-114">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="5d499-114">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="5d499-115">`Operation.qs` adlı bir dosya oluşturup dosyaya aşağıdaki kodu ekleyerek küçük bir Q# işlemi oluşturun:</span><span class="sxs-lookup"><span data-stu-id="5d499-115">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="5d499-116">Q# `SayHello()` işlemini çağırmak için `hello_world.py` adlı bir Python programı oluşturun:</span><span class="sxs-lookup"><span data-stu-id="5d499-116">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="5d499-117">Programı çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="5d499-117">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="5d499-118">Çıktıyı doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="5d499-118">Verify the output.</span></span> <span data-ttu-id="5d499-119">Programınız aşağıdaki satırları çıkarmalıdır:</span><span class="sxs-lookup"><span data-stu-id="5d499-119">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * <span data-ttu-id="5d499-120">Ayrıca, Python Jupyıter not defterlerini, klasik Python programını yazmak ve hücrelerden Q # işlemlerini çağırmak için de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5d499-120">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="5d499-121">Python kodu yalnızca normal bir Python programıdır.</span><span class="sxs-lookup"><span data-stu-id="5d499-121">The Python code is just a normal Python program.</span></span>

## <a name="whats-next"></a><span data-ttu-id="5d499-122">Sırada ne var?</span><span class="sxs-lookup"><span data-stu-id="5d499-122">What's next?</span></span>

<span data-ttu-id="5d499-123">Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.write-program) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5d499-123">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
