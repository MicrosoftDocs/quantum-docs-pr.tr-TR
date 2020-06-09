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
# <a name="develop-with-q-and-python"></a><span data-ttu-id="b59dc-102">Q # ve Python ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="b59dc-102">Develop with Q# and Python</span></span>

<span data-ttu-id="b59dc-103">Q # işlemlerini çağırmak için Python konak programları geliştirmek üzere QDK 'yi yükler.</span><span class="sxs-lookup"><span data-stu-id="b59dc-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="b59dc-104">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="b59dc-104">Pre-requisites</span></span>

    - <span data-ttu-id="b59dc-105">[Python](https://www.python.org/downloads/) 3,6 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="b59dc-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="b59dc-106">[PIP](https://pip.pypa.io/en/stable/installing) Python paket yöneticisi</span><span class="sxs-lookup"><span data-stu-id="b59dc-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="b59dc-107">.NET Core SDK 3,1</span><span class="sxs-lookup"><span data-stu-id="b59dc-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="b59dc-108">`qsharp`Q # ve Python arasında birlikte çalışabilirliğine izin veren bir Python paketi olan paketini yükler.</span><span class="sxs-lookup"><span data-stu-id="b59dc-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="b59dc-109">Q # işlemlerini derlemek ve yürütmek için temel işlevselliği sağlayan Jupileter ve Python tarafından kullanılan bir çekirdek olan IQ # öğesini yükler.</span><span class="sxs-lookup"><span data-stu-id="b59dc-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. <span data-ttu-id="b59dc-110">Herhangi bir IDE 'de soru-cevap özelliğini kullanarak soru-cevap için Visual Studio Code (VS Code) IDE kullanmanız önerilir.</span><span class="sxs-lookup"><span data-stu-id="b59dc-110">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="b59dc-111">Visual Studio Code ve QDK Visual Studio Code uzantısını kullanarak daha zengin işlevselliğe erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b59dc-111">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="b59dc-112">[Vs Code](https://code.visualstudio.com/download) (Windows, Linux ve Mac) 'i yükler</span><span class="sxs-lookup"><span data-stu-id="b59dc-112">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="b59dc-113">[Vs Code Için QDK uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)yükler.</span><span class="sxs-lookup"><span data-stu-id="b59dc-113">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="b59dc-114">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="b59dc-114">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b59dc-115">`Operation.qs` adlı bir dosya oluşturup dosyaya aşağıdaki kodu ekleyerek küçük bir Q# işlemi oluşturun:</span><span class="sxs-lookup"><span data-stu-id="b59dc-115">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="b59dc-116">Q# `SayHello()` işlemini çağırmak için `hello_world.py` adlı bir Python programı oluşturun:</span><span class="sxs-lookup"><span data-stu-id="b59dc-116">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="b59dc-117">Programı çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="b59dc-117">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="b59dc-118">Çıktıyı doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="b59dc-118">Verify the output.</span></span> <span data-ttu-id="b59dc-119">Programınız aşağıdaki satırları çıkarmalıdır:</span><span class="sxs-lookup"><span data-stu-id="b59dc-119">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="b59dc-120">Ayrıca, Python Jupyıter not defterlerini, klasik Python programını yazmak ve hücrelerden Q # işlemlerini çağırmak için de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b59dc-120">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="b59dc-121">Python kodu yalnızca normal bir Python programıdır.</span><span class="sxs-lookup"><span data-stu-id="b59dc-121">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b59dc-122">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="b59dc-122">Next steps</span></span>

<span data-ttu-id="b59dc-123">Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b59dc-123">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
