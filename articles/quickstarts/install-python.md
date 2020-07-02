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
# <a name="develop-with-q-and-python"></a><span data-ttu-id="653ef-102">Q# ve Python ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="653ef-102">Develop with Q# and Python</span></span>

<span data-ttu-id="653ef-103">Q# işlemlerini çağırmak için Python konak programları geliştirmek üzere QDK'yi yükleyin.</span><span class="sxs-lookup"><span data-stu-id="653ef-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="653ef-104">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="653ef-104">Prerequisites</span></span>

    - <span data-ttu-id="653ef-105">[Python](https://www.python.org/downloads/) 3.6 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="653ef-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="653ef-106">[PIP](https://pip.pypa.io/en/stable/installing) Python paket yöneticisi</span><span class="sxs-lookup"><span data-stu-id="653ef-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="653ef-107">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="653ef-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="653ef-108">Q# ile Python arasında birlikte çalışmayı sağlayan bir Python paketi olan `qsharp` paketini yükleyin.</span><span class="sxs-lookup"><span data-stu-id="653ef-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="653ef-109">Jupyter ile Python tarafından kullanılan, Q# işlemlerinin derlenmesine ve yürütülmesine yönelik temel işlevselliği sağlayan IQ# çekirdeğini yükleyin.</span><span class="sxs-lookup"><span data-stu-id="653ef-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="653ef-110">`dotnet iqsharp install` adımında bir hata alırsanız yeni bir terminal penceresi açın ve yeniden deneyin.</span><span class="sxs-lookup"><span data-stu-id="653ef-110">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="653ef-111">Bu adım da işe yaramazsa yüklü olan `dotnet-iqsharp` aracını (Windows’da `dotnet-iqsharp.exe`) bulup çalıştırmayı deneyin:</span><span class="sxs-lookup"><span data-stu-id="653ef-111">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="653ef-112">`/path/to/dotnet-iqsharp`, dosya sisteminizdeki `dotnet-iqsharp` aracının mutlak yolu ile değiştirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="653ef-112">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="653ef-113">Genellikle bu, kullanıcı profili klasörünüzdeki `.dotnet/tools` altında bulunur.</span><span class="sxs-lookup"><span data-stu-id="653ef-113">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
  
1. <span data-ttu-id="653ef-114">Q# dilini Python ile herhangi bir IDE'de kullanabiliyor olsanız da, Q# + Python uygulamalarınız için Visual Studio Code (VS Code) IDE kullanmanız önerilir.</span><span class="sxs-lookup"><span data-stu-id="653ef-114">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="653ef-115">Visual Studio Code ve QDK Visual Studio Code uzantısını kullanarak daha zengin işlevselliğe erişim elde edersiniz.</span><span class="sxs-lookup"><span data-stu-id="653ef-115">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="653ef-116">[VS Code](https://code.visualstudio.com/download)’u (Windows, Linux ve Mac) yükleyin</span><span class="sxs-lookup"><span data-stu-id="653ef-116">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="653ef-117">[VS Code için QDK uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) yükleyin.</span><span class="sxs-lookup"><span data-stu-id="653ef-117">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="653ef-118">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="653ef-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="653ef-119">`Operation.qs` adlı bir dosya oluşturup dosyaya aşağıdaki kodu ekleyerek küçük bir Q# işlemi oluşturun:</span><span class="sxs-lookup"><span data-stu-id="653ef-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="653ef-120">Q# `SayHello()` işlemini çağırmak için `hello_world.py` adlı bir Python programı oluşturun:</span><span class="sxs-lookup"><span data-stu-id="653ef-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="653ef-121">Programı çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="653ef-121">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="653ef-122">Çıktıyı doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="653ef-122">Verify the output.</span></span> <span data-ttu-id="653ef-123">Programınız aşağıdaki satırları çıkarmalıdır:</span><span class="sxs-lookup"><span data-stu-id="653ef-123">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="653ef-124">Ayrıca Python Jupyter not defterlerini, klasik Python programı yazmak ve hücrelerden Q# işlemlerini çağırmak için de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="653ef-124">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="653ef-125">Python kodu yalnızca normal bir Python programıdır.</span><span class="sxs-lookup"><span data-stu-id="653ef-125">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="653ef-126">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="653ef-126">Next steps</span></span>

<span data-ttu-id="653ef-127">Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="653ef-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
