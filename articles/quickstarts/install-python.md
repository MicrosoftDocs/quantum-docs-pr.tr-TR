---
title: Q# ve Python ile geliştirme
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 7fbbb81b1ee51bff74b287745bf4447004a0254c
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885534"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="69c6c-102">Q# ve Python ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="69c6c-102">Develop with Q# and Python</span></span>

<span data-ttu-id="69c6c-103">Q# işlemlerini çağırmak için Python konak programları geliştirmek üzere QDK'yi yükleyin.</span><span class="sxs-lookup"><span data-stu-id="69c6c-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

## <a name="install-the-qsharp-python-package"></a><span data-ttu-id="69c6c-104">`qsharp` Python paketini yükleme</span><span class="sxs-lookup"><span data-stu-id="69c6c-104">Install the `qsharp` Python package</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="69c6c-105">Conda kullanarak yükleme (önerilir)</span><span class="sxs-lookup"><span data-stu-id="69c6c-105">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="69c6c-106">[Miniconda](https://docs.conda.io/en/latest/miniconda.html) veya [Anaconda](https://www.anaconda.com/products/individual#Downloads)'yı yükleyin.</span><span class="sxs-lookup"><span data-stu-id="69c6c-106">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span>

1. <span data-ttu-id="69c6c-107">Anaconda İstemini açın.</span><span class="sxs-lookup"><span data-stu-id="69c6c-107">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="69c6c-108">Ya da PowerShell veya pwsh kullanmayı tercih ediyorsanız: Bir kabuğu açın, `conda init powershell` komutunu çalıştırın, ardından kabuğu kapatıp yeniden açın.</span><span class="sxs-lookup"><span data-stu-id="69c6c-108">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="69c6c-109">Şu komutları çalıştırarak gerekli paketlerle (Jupyter Notebook ve IQ# dahil) `qsharp-env` adlı yeni bir Conda ortamı oluşturup etkinleştirin:</span><span class="sxs-lookup"><span data-stu-id="69c6c-109">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="69c6c-110">Yüklemenizi doğrulamak için aynı terminalden `python -c "import qsharp"` komutunu çalıştırın ve yerel paket önbelleğinizi tüm gerekli QDK bileşenleriyle doldurun.</span><span class="sxs-lookup"><span data-stu-id="69c6c-110">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="69c6c-111">.NET CLI ve PIP kullanarak yükleme (gelişmiş)</span><span class="sxs-lookup"><span data-stu-id="69c6c-111">Install using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="69c6c-112">Ön koşullar:</span><span class="sxs-lookup"><span data-stu-id="69c6c-112">Prerequisites:</span></span>

    - <span data-ttu-id="69c6c-113">[Python](https://www.python.org/downloads/) 3.6 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="69c6c-113">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="69c6c-114">[PIP](https://pip.pypa.io/en/stable/installing) Python paket yöneticisi</span><span class="sxs-lookup"><span data-stu-id="69c6c-114">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="69c6c-115">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="69c6c-115">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="69c6c-116">Q# ile Python arasında birlikte çalışmayı sağlayan bir Python paketi olan `qsharp` paketini yükleyin.</span><span class="sxs-lookup"><span data-stu-id="69c6c-116">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="69c6c-117">Jupyter ile Python tarafından kullanılan, Q# işlemlerinin derlenmesine ve yürütülmesine yönelik temel işlevselliği sağlayan IQ# çekirdeğini yükleyin.</span><span class="sxs-lookup"><span data-stu-id="69c6c-117">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="69c6c-118">`dotnet iqsharp install` adımında bir hata alırsanız yeni bir terminal penceresi açın ve yeniden deneyin.</span><span class="sxs-lookup"><span data-stu-id="69c6c-118">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="69c6c-119">Bu adım da işe yaramazsa yüklü olan `dotnet-iqsharp` aracını (Windows’da `dotnet-iqsharp.exe`) bulup çalıştırmayı deneyin:</span><span class="sxs-lookup"><span data-stu-id="69c6c-119">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="69c6c-120">`/path/to/dotnet-iqsharp`, dosya sisteminizdeki `dotnet-iqsharp` aracının mutlak yolu ile değiştirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="69c6c-120">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="69c6c-121">Genellikle bu, kullanıcı profili klasörünüzdeki `.dotnet/tools` altında bulunur.</span><span class="sxs-lookup"><span data-stu-id="69c6c-121">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="69c6c-122">İşte bu kadar!</span><span class="sxs-lookup"><span data-stu-id="69c6c-122">That's it!</span></span> <span data-ttu-id="69c6c-123">Artık Jupyter için hem `qsharp` Python paketine hem de IQ# çekirdeğine sahipsiniz. Bu paket Python’dan Q# işlemlerini derlemek ve yürütmek üzere temel işlevselliği sağlar ve Q# Jupyter Not Defterlerini kullanmanıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="69c6c-123">You now have both the `qsharp` Python package and the IQ# kernel for Jupyter, which provides the core functionality for compiling and executing Q# operations from Python and allows you to use Q# Jupyter Notebooks.</span></span>

## <a name="choose-your-ide"></a><span data-ttu-id="69c6c-124">IDE’nizi seçin</span><span class="sxs-lookup"><span data-stu-id="69c6c-124">Choose your IDE</span></span>

<span data-ttu-id="69c6c-125">Q# dilini Python ile herhangi bir IDE'de kullanabiliyor olsanız da, Q# + Python uygulamalarınız için Visual Studio Code (VS Code) IDE kullanmanız önerilir.</span><span class="sxs-lookup"><span data-stu-id="69c6c-125">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="69c6c-126">QDK Visual Studio Code uzantısı ile uyarılar, söz dizimi vurgulama, proje şablonları gibi daha zengin işlevlere erişim elde edersiniz.</span><span class="sxs-lookup"><span data-stu-id="69c6c-126">With the QDK Visual Studio Code extension you gain access to richer functionality such as warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="69c6c-127">VS Code kullanmak istiyorsanız:</span><span class="sxs-lookup"><span data-stu-id="69c6c-127">If you would like to use VS Code:</span></span>

- <span data-ttu-id="69c6c-128">[VS Code](https://code.visualstudio.com/download)’u (Windows, Linux ve Mac) yükleyin.</span><span class="sxs-lookup"><span data-stu-id="69c6c-128">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
- <span data-ttu-id="69c6c-129">[VS Code için QDK uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) yükleyin.</span><span class="sxs-lookup"><span data-stu-id="69c6c-129">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="69c6c-130">Farklı bir düzenleyici kullanmak istiyorsanız, yukarıdaki yönergelerle gerekli hazırlıkları yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="69c6c-130">If you would like to use a different editor, the instructions above have you all set.</span></span>

## <a name="write-your-first-q-program"></a><span data-ttu-id="69c6c-131">İlk Q# programınızı yazma</span><span class="sxs-lookup"><span data-stu-id="69c6c-131">Write your first Q# program</span></span>

<span data-ttu-id="69c6c-132">Artık basit bir Q# programı yazarak ve yürüterek `qsharp` Python paketi yüklemenizi doğrulamaya hazırsınız.</span><span class="sxs-lookup"><span data-stu-id="69c6c-132">Now you are ready to verify your `qsharp` Python package installation by writing and executing a simple Q# program.</span></span>

1. <span data-ttu-id="69c6c-133">`Operation.qs` adlı bir dosya oluşturup dosyaya aşağıdaki kodu ekleyerek küçük bir Q# işlemi oluşturun:</span><span class="sxs-lookup"><span data-stu-id="69c6c-133">Create a minimal Q# operation by creating a file called `Operation.qs` and adding the following code to it:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. <span data-ttu-id="69c6c-134">`Operation.qs` ile aynı klasörde, Q# `SampleQuantumRandomNumberGenerator()` işleminin simülasyonunu oluşturmak için `host.py` adlı bir Python programı oluşturun:</span><span class="sxs-lookup"><span data-stu-id="69c6c-134">In the same folder as `Operation.qs`, create a Python program called `host.py` to simulate the Q# `SampleQuantumRandomNumberGenerator()` operation:</span></span>

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    SampleQuantumRandomNumberGenerator.simulate()
    ```

1. <span data-ttu-id="69c6c-135">Yükleme sırasında oluşturduğunuz ortamdan (yani `qsharp` yüklediğiniz Conda veya Python ortamı) şu programı çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="69c6c-135">From the environment you created during installation (i.e., the conda or Python environment where you installed `qsharp`), run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="69c6c-136">Çağırdığınız işlemin sonucunu görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="69c6c-136">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="69c6c-137">Bu durumda, işleminiz rastgele bir sonuç oluşturduğundan ekranda `Zero` veya `One` yazdırılmış olduğunu görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="69c6c-137">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="69c6c-138">Programı tekrar tekrar yürütürseniz, her sonucu yaklaşık olarak yarı sürede görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="69c6c-138">If you execute the program repeatedly, you should see each result approximately half the time.</span></span>

> [!NOTE]
> * <span data-ttu-id="69c6c-139">Python kodu yalnızca normal bir Python programıdır.</span><span class="sxs-lookup"><span data-stu-id="69c6c-139">The Python code is just a normal Python program.</span></span> <span data-ttu-id="69c6c-140">Python programını yazmak ve Q# işlemlerini çağırmak için Python tabanlı Jupyter Not Defterleri dahil olmak üzere herhangi bir Python ortamını kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="69c6c-140">You can use any Python environment, including Python-based Jupyter Notebooks, to write the Python program and call Q# operations.</span></span> <span data-ttu-id="69c6c-141">Python programı, Python kodunun kendisi ile aynı klasörde bulunan tüm .qs dosyalarından Q# işlemlerini içeri aktarabilir.</span><span class="sxs-lookup"><span data-stu-id="69c6c-141">The Python program can import Q# operations from any .qs files located in the same folder as the Python code itself.</span></span>

## <a name="next-steps"></a><span data-ttu-id="69c6c-142">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="69c6c-142">Next steps</span></span>

<span data-ttu-id="69c6c-143">Quantum geliştirme setini tercih ettiğiniz ortama yüklediğinize göre, [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırmak için bu öğreticiyi izleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="69c6c-143">Now that you have installed the Quantum Development Kit in your preferred environment, you can follow this tutorial to write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
