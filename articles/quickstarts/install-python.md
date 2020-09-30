---
title: Q# ve Python ile geliştirme
description: Python kullanarak Q# uygulaması oluşturmayı öğrenin.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
no-loc:
- Q#
- $$v
ms.openlocfilehash: f6a2a7d1888cfe458fa3989a27d71fcdeed0f01f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834168"
---
# <a name="develop-with-no-locq-and-python"></a><span data-ttu-id="8c20a-103">Q# ve Python ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="8c20a-103">Develop with Q# and Python</span></span>

<span data-ttu-id="8c20a-104">Q# işlemlerini çağırmak için Python konak programları geliştirmek üzere QDK'yi yükleyin.</span><span class="sxs-lookup"><span data-stu-id="8c20a-104">Install the QDK to develop Python host programs to call Q# operations.</span></span>

## <a name="install-the-qsharp-python-package"></a><span data-ttu-id="8c20a-105">`qsharp` Python paketini yükleme</span><span class="sxs-lookup"><span data-stu-id="8c20a-105">Install the `qsharp` Python package</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="8c20a-106">Conda kullanarak yükleme (önerilir)</span><span class="sxs-lookup"><span data-stu-id="8c20a-106">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="8c20a-107">[Miniconda](https://docs.conda.io/en/latest/miniconda.html) veya [Anaconda](https://www.anaconda.com/products/individual#Downloads)'yı yükleyin.</span><span class="sxs-lookup"><span data-stu-id="8c20a-107">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="8c20a-108">**Not:** 64 bit yüklemesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="8c20a-108">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="8c20a-109">Anaconda İstemini açın.</span><span class="sxs-lookup"><span data-stu-id="8c20a-109">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="8c20a-110">Ya da PowerShell veya pwsh kullanmayı tercih ediyorsanız: Bir kabuğu açın, `conda init powershell` komutunu çalıştırın, ardından kabuğu kapatıp yeniden açın.</span><span class="sxs-lookup"><span data-stu-id="8c20a-110">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="8c20a-111">Şu komutları çalıştırarak gerekli paketlerle (Jupyter Notebook ve IQ# dahil) `qsharp-env` adlı yeni bir Conda ortamı oluşturup etkinleştirin:</span><span class="sxs-lookup"><span data-stu-id="8c20a-111">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="8c20a-112">Yüklemenizi doğrulamak için aynı terminalden `python -c "import qsharp"` komutunu çalıştırın ve yerel paket önbelleğinizi tüm gerekli QDK bileşenleriyle doldurun.</span><span class="sxs-lookup"><span data-stu-id="8c20a-112">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="8c20a-113">.NET CLI ve PIP kullanarak yükleme (gelişmiş)</span><span class="sxs-lookup"><span data-stu-id="8c20a-113">Install using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="8c20a-114">Ön koşullar:</span><span class="sxs-lookup"><span data-stu-id="8c20a-114">Prerequisites:</span></span>

    - <span data-ttu-id="8c20a-115">[Python](https://www.python.org/downloads/) 3.6 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="8c20a-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="8c20a-116">[PIP](https://pip.pypa.io/en/stable/installing) Python paket yöneticisi</span><span class="sxs-lookup"><span data-stu-id="8c20a-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="8c20a-117">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="8c20a-117">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="8c20a-118">Q# ile Python arasında birlikte çalışmayı sağlayan bir Python paketi olan `qsharp` paketini yükleyin.</span><span class="sxs-lookup"><span data-stu-id="8c20a-118">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="8c20a-119">Jupyter ile Python tarafından kullanılan, Q# işlemlerinin derlenmesine ve çalıştırılmasına yönelik temel işlevselliği sağlayan IQ# çekirdeğini yükleyin.</span><span class="sxs-lookup"><span data-stu-id="8c20a-119">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and running Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="8c20a-120">`dotnet iqsharp install` adımında bir hata alırsanız yeni bir terminal penceresi açın ve yeniden deneyin.</span><span class="sxs-lookup"><span data-stu-id="8c20a-120">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="8c20a-121">Bu adım da işe yaramazsa yüklü olan `dotnet-iqsharp` aracını (Windows’da `dotnet-iqsharp.exe`) bulup çalıştırmayı deneyin:</span><span class="sxs-lookup"><span data-stu-id="8c20a-121">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="8c20a-122">`/path/to/dotnet-iqsharp`, dosya sisteminizdeki `dotnet-iqsharp` aracının mutlak yolu ile değiştirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="8c20a-122">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="8c20a-123">Genellikle bu, kullanıcı profili klasörünüzdeki `.dotnet/tools` altında bulunur.</span><span class="sxs-lookup"><span data-stu-id="8c20a-123">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="8c20a-124">İşte bu kadar!</span><span class="sxs-lookup"><span data-stu-id="8c20a-124">That's it!</span></span> <span data-ttu-id="8c20a-125">Artık Jupyter için hem `qsharp` Python paketine hem de IQ# çekirdeğine sahipsiniz. Bu paket Python’dan Q# işlemlerini derleyip çalıştırmak için gereken temel işlevselliği sağlar ve Q# Jupyter Not Defterlerini kullanmanıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="8c20a-125">You now have both the `qsharp` Python package and the IQ# kernel for Jupyter, which provide the core functionality for compiling and running Q# operations from Python and allows you to use Q# Jupyter Notebooks.</span></span>

## <a name="choose-your-ide"></a><span data-ttu-id="8c20a-126">IDE’nizi seçin</span><span class="sxs-lookup"><span data-stu-id="8c20a-126">Choose your IDE</span></span>

<span data-ttu-id="8c20a-127">Q# dilini Python ile herhangi bir IDE'de kullanabiliyor olsanız da, Q# + Python uygulamalarınız için Visual Studio Code (VS Code) IDE kullanmanız önerilir.</span><span class="sxs-lookup"><span data-stu-id="8c20a-127">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="8c20a-128">QDK Visual Studio Code uzantısı ile uyarılar, söz dizimi vurgulama, proje şablonları gibi daha zengin işlevlere erişim elde edersiniz.</span><span class="sxs-lookup"><span data-stu-id="8c20a-128">With the QDK Visual Studio Code extension you gain access to richer functionality such as warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="8c20a-129">VS Code kullanmak istiyorsanız:</span><span class="sxs-lookup"><span data-stu-id="8c20a-129">If you would like to use VS Code:</span></span>

- <span data-ttu-id="8c20a-130">[VS Code](https://code.visualstudio.com/download)’u (Windows, Linux ve Mac) yükleyin.</span><span class="sxs-lookup"><span data-stu-id="8c20a-130">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
- <span data-ttu-id="8c20a-131">[VS Code için QDK uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) yükleyin.</span><span class="sxs-lookup"><span data-stu-id="8c20a-131">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="8c20a-132">Farklı bir düzenleyici kullanmak istiyorsanız, yukarıdaki yönergelerle gerekli hazırlıkları yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8c20a-132">If you would like to use a different editor, the instructions above have you all set.</span></span>

## <a name="write-your-first-no-locq-program"></a><span data-ttu-id="8c20a-133">İlk Q# programınızı yazma</span><span class="sxs-lookup"><span data-stu-id="8c20a-133">Write your first Q# program</span></span>

<span data-ttu-id="8c20a-134">Şimdi basit bir Q# programı yazıp çalıştırarak `qsharp` Python paketi yüklemenizi doğrulamaya hazırsınız.</span><span class="sxs-lookup"><span data-stu-id="8c20a-134">Now you are ready to verify your `qsharp` Python package installation by writing and running a simple Q# program.</span></span>

1. <span data-ttu-id="8c20a-135">`Operation.qs` adlı bir dosya oluşturup dosyaya aşağıdaki kodu ekleyerek küçük bir Q# işlemi oluşturun:</span><span class="sxs-lookup"><span data-stu-id="8c20a-135">Create a minimal Q# operation by creating a file called `Operation.qs` and adding the following code to it:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. <span data-ttu-id="8c20a-136">`Operation.qs` ile aynı klasörde, Q# `SampleQuantumRandomNumberGenerator()` işleminin simülasyonunu oluşturmak için `host.py` adlı bir Python programı oluşturun:</span><span class="sxs-lookup"><span data-stu-id="8c20a-136">In the same folder as `Operation.qs`, create a Python program called `host.py` to simulate the Q# `SampleQuantumRandomNumberGenerator()` operation:</span></span>

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    print(SampleQuantumRandomNumberGenerator.simulate())
    ```

1. <span data-ttu-id="8c20a-137">Yükleme sırasında oluşturduğunuz ortamdan (yani `qsharp` yüklediğiniz Conda veya Python ortamı) şu programı çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="8c20a-137">From the environment you created during installation (i.e., the conda or Python environment where you installed `qsharp`), run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="8c20a-138">Çağırdığınız işlemin sonucunu görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="8c20a-138">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="8c20a-139">Bu durumda, işleminiz rastgele bir sonuç oluşturduğundan ekranda `0` veya `1` yazdırılmış olduğunu görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="8c20a-139">In this case, because your operation generates a random result, you will see either `0` or `1` printed on the screen.</span></span> <span data-ttu-id="8c20a-140">Programı tekrar tekrar çalıştırırsanız her sonucu yaklaşık olarak yarı sürede görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="8c20a-140">If you run the program repeatedly, you should see each result approximately half the time.</span></span>

> [!NOTE]
> * <span data-ttu-id="8c20a-141">Python kodu yalnızca normal bir Python programıdır.</span><span class="sxs-lookup"><span data-stu-id="8c20a-141">The Python code is just a normal Python program.</span></span> <span data-ttu-id="8c20a-142">Python programını yazmak ve Q# işlemlerini çağırmak için Python tabanlı Jupyter Not Defterleri dahil olmak üzere herhangi bir Python ortamını kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8c20a-142">You can use any Python environment, including Python-based Jupyter Notebooks, to write the Python program and call Q# operations.</span></span> <span data-ttu-id="8c20a-143">Python programı, Python kodunun kendisi ile aynı klasörde bulunan tüm .qs dosyalarından Q# işlemlerini içeri aktarabilir.</span><span class="sxs-lookup"><span data-stu-id="8c20a-143">The Python program can import Q# operations from any .qs files located in the same folder as the Python code itself.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8c20a-144">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="8c20a-144">Next steps</span></span>

<span data-ttu-id="8c20a-145">Quantum geliştirme setini tercih ettiğiniz ortamda test ettiğinize göre, [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırmak için bu öğreticiyi izleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8c20a-145">Now that you have tested the Quantum Development Kit in your preferred environment, you can follow this tutorial to write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
