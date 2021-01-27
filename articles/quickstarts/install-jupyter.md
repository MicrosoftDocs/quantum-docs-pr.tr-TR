---
title: Q# Jupyter Not Defterleri ile geliştirme
description: Jupyter Not Defterleri kullanarak Q# uygulaması oluşturmayı öğrenin.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.jupyter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4cef9b7252a2199b2ea995c4cf819a3582d9ca8f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844287"
---
# <a name="develop-with-no-locq-jupyter-notebooks"></a><span data-ttu-id="badac-103">Q# Jupyter Not Defterleri ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="badac-103">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="badac-104">Q# Jupyter Not Defterlerinde Q# işlemleri geliştirmek için QDK'yi yükleyin.</span><span class="sxs-lookup"><span data-stu-id="badac-104">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="badac-105">Jupyter Not Defterleri yönergeler, notlar ve diğer içeriklerin yanı sıra yerinde kod çalıştırmaya olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="badac-105">Jupyter Notebooks allow running code in-place alongside instructions, notes, and other content.</span></span> <span data-ttu-id="badac-106">Bu ortam, ekli açıklamalar veya kuantum bilişimi etkileşimli öğreticileri ile Q# kodu yazmak için idealdir.</span><span class="sxs-lookup"><span data-stu-id="badac-106">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="badac-107">Kendi Q# not defterlerinizi oluşturmaya başlamak için gerekenler aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="badac-107">Here's what you need to do to start creating your own Q# notebooks.</span></span>

## <a name="install-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="badac-108">IQ# Jupyter çekirdeğini yükleme</span><span class="sxs-lookup"><span data-stu-id="badac-108">Install the IQ# Jupyter kernel</span></span>

<span data-ttu-id="badac-109">IQ# (ay-kü-şarp olarak okunur) öncelikli olarak Jupyter ve Python tarafından .NET Core SDK için kullanılan ve Q# işlemlerinin derlenmesine ve simülasyonunun yapılmasına yönelik temel işlevselliği sağlayan bir uzantıdır.</span><span class="sxs-lookup"><span data-stu-id="badac-109">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="badac-110">Conda kullanarak yükleme (önerilir)</span><span class="sxs-lookup"><span data-stu-id="badac-110">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="badac-111">[Miniconda](https://docs.conda.io/en/latest/miniconda.html) veya [Anaconda](https://www.anaconda.com/products/individual#Downloads)'yı yükleyin.</span><span class="sxs-lookup"><span data-stu-id="badac-111">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="badac-112">**Not:** 64 bit yüklemesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="badac-112">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="badac-113">Anaconda İstemini açın.</span><span class="sxs-lookup"><span data-stu-id="badac-113">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="badac-114">Ya da PowerShell veya pwsh kullanmayı tercih ediyorsanız: Bir kabuğu açın, `conda init powershell` komutunu çalıştırın, ardından kabuğu kapatıp yeniden açın.</span><span class="sxs-lookup"><span data-stu-id="badac-114">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="badac-115">Şu komutları çalıştırarak gerekli paketlerle (Jupyter Notebook ve IQ# dahil) `qsharp-env` adlı yeni bir Conda ortamı oluşturup etkinleştirin:</span><span class="sxs-lookup"><span data-stu-id="badac-115">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="badac-116">Yüklemenizi doğrulamak için aynı terminalden `python -c "import qsharp"` komutunu çalıştırın ve yerel paket önbelleğinizi tüm gerekli QDK bileşenleriyle doldurun.</span><span class="sxs-lookup"><span data-stu-id="badac-116">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-advanced"></a>[<span data-ttu-id="badac-117">.NET CLI kullanarak yükleme (gelişmiş)</span><span class="sxs-lookup"><span data-stu-id="badac-117">Install using .NET CLI (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="badac-118">Ön koşullar:</span><span class="sxs-lookup"><span data-stu-id="badac-118">Prerequisites:</span></span>

    - <span data-ttu-id="badac-119">[Python](https://www.python.org/downloads/) 3.6 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="badac-119">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="badac-120">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="badac-120">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="badac-121">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="badac-121">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="badac-122">`Microsoft.Quantum.IQSharp` paketini yükleyin.</span><span class="sxs-lookup"><span data-stu-id="badac-122">Install the `Microsoft.Quantum.IQSharp` package.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

> [!NOTE]
> <span data-ttu-id="badac-123">`dotnet iqsharp install` adımında bir hata alırsanız yeni bir terminal penceresi açın ve yeniden deneyin.</span><span class="sxs-lookup"><span data-stu-id="badac-123">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
> <span data-ttu-id="badac-124">Bu adım da işe yaramazsa yüklü olan `dotnet-iqsharp` aracını (Windows’da `dotnet-iqsharp.exe`) bulup çalıştırmayı deneyin:</span><span class="sxs-lookup"><span data-stu-id="badac-124">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
> ```
> /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
> ```
> <span data-ttu-id="badac-125">`/path/to/dotnet-iqsharp`, dosya sisteminizdeki `dotnet-iqsharp` aracının mutlak yolu ile değiştirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="badac-125">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
> <span data-ttu-id="badac-126">Genellikle bu, kullanıcı profili klasörünüzdeki `.dotnet/tools` altında bulunur.</span><span class="sxs-lookup"><span data-stu-id="badac-126">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
<span data-ttu-id="badac-127">\*\*_</span><span class="sxs-lookup"><span data-stu-id="badac-127">\*\*_</span></span>

<span data-ttu-id="badac-128">İşte bu kadar!</span><span class="sxs-lookup"><span data-stu-id="badac-128">That's it!</span></span> <span data-ttu-id="badac-129">Artık Jupyter için IQ# çekirdeğine sahipsiniz. Bu çekirdek Q# Jupyter Not Defterlerinden Q# işlemlerini derlemek ve çalıştırmak için gereken temel işlevselliği sağlar.</span><span class="sxs-lookup"><span data-stu-id="badac-129">You now have the IQ# kernel for Jupyter, which provides the core functionality for compiling and running Q# operations from Q# Jupyter Notebooks.</span></span>

## <a name="create-your-first-no-locq-notebook"></a><span data-ttu-id="badac-130">İlk Q# not defterinizi oluşturma</span><span class="sxs-lookup"><span data-stu-id="badac-130">Create your first Q# notebook</span></span>

<span data-ttu-id="badac-131">Artık basit bir Q# işlemi yazıp çalıştırarak Q# Jupyter Notebook yüklemenizi doğrulamaya hazırsınız.</span><span class="sxs-lookup"><span data-stu-id="badac-131">Now you are ready to verify your Q# Jupyter Notebook installation by writing and running a simple Q# operation.</span></span>

1. <span data-ttu-id="badac-132">Yükleme sırasında oluşturduğunuz ortamdan (yani oluşturduğunuz Conda ortamı veya Jupyter’ı yüklediğiniz Python ortamı) Jupyter Notebook sunucusunu başlatmak için şu komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="badac-132">From the environment you created during installation (i.e., either the conda environment you created, or the Python environment where you installed Jupyter), run the following command to start the Jupyter Notebook server:</span></span>

    ```
    jupyter notebook
    ```

    - <span data-ttu-id="badac-133">Jupyter Notebook otomatik olarak tarayıcınızda açılmazsa komut satırı tarafından sağlanan URL’yi kopyalayıp tarayıcınıza yapıştırın.</span><span class="sxs-lookup"><span data-stu-id="badac-133">If the Jupyter Notebook doesn't open automatically in your browser, copy and paste the URL provided by the command line into your browser.</span></span>

1. <span data-ttu-id="badac-134">Çekirdekle bir Jupyter Notebook oluşturmak için _ *New Q# →*\* öğesini seçin Q# ve ilk not defteri hücresine aşağıdaki kodu ekleyin:</span><span class="sxs-lookup"><span data-stu-id="badac-134">Choose _ *New → Q#*\* to create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. <span data-ttu-id="badac-135">Not defterinin şu hücresini çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="badac-135">Run this cell of the notebook:</span></span>

    ![Q# kodu içeren Jupyter Notebook hücresi](~/media/install-guide-jupyter.png)

    <span data-ttu-id="badac-137">Hücrenin çıktısında `SampleQuantumRandomNumberGenerator` görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="badac-137">You should see `SampleQuantumRandomNumberGenerator` in the output of the cell.</span></span> <span data-ttu-id="badac-138">Jupyter Notebook’ta çalışırken Q# kodu derlenir ve hücre, bulduğu tüm işlemlerin adlarını çıktı olarak verir.</span><span class="sxs-lookup"><span data-stu-id="badac-138">When running in Jupyter Notebook, the Q# code is compiled, and the cell outputs the name of any operations that it finds.</span></span>

1. <span data-ttu-id="badac-139">Yeni bir hücrede, az önce oluşturduğunuz işlemi `%simulate` komutunu kullanarak (simülatör içinde) çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="badac-139">In a new cell, run the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

    ![%simulate magic içeren Jupyter Not Defteri hücresi](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="badac-141">Çağırdığınız işlemin sonucunu görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="badac-141">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="badac-142">Bu durumda, işleminiz rastgele bir sonuç oluşturduğundan ekranda `Zero` veya `One` yazdırılmış olduğunu görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="badac-142">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="badac-143">Hücreyi tekrar tekrar çalıştırırsanız her sonucu yaklaşık olarak yarı sürede görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="badac-143">If you run the cell repeatedly, you should see each result approximately half the time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="badac-144">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="badac-144">Next steps</span></span>

<span data-ttu-id="badac-145">Artık Q# Jupyter Not Defterleri için QDK’yi yüklediğinize göre, Q# kodunu doğrudan Jupyter Notebook ortamı içinde yazarak [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="badac-145">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="badac-146">Q# Jupyter Not Defterleri ile yapabileceklerinize ilişkin daha fazla örnek için lütfen şuraya göz atın:</span><span class="sxs-lookup"><span data-stu-id="badac-146">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>

- <span data-ttu-id="badac-147">[Q# ve Jupyter Notebook’a giriş](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="badac-147">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="badac-148">Burada, Jupyter ortamında Q# kullanmayla ilgili daha fazla ayrıntı sağlayan bir Q# Jupyter Not Defteri bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="badac-148">There you will find a Q# Jupyter Notebook that provides more details on how to use Q# in the Jupyter environment.</span></span>
- <span data-ttu-id="badac-149">[Quantum Kataları](xref:microsoft.quantum.overview.katas), kendi hızınızda ilerleyebileceğiniz öğreticilerden ve Q# Jupyter Not Defterleri biçimindeki programlama alıştırması setlerinden oluşan bir açık kaynak koleksiyondur.</span><span class="sxs-lookup"><span data-stu-id="badac-149">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="badac-150">[Quantum Katas öğretici not defterleri](https://github.com/microsoft/QuantumKatas#tutorial-topics) iyi bir başlangıç noktasıdır.</span><span class="sxs-lookup"><span data-stu-id="badac-150">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="badac-151">Quantum Kataları, size aynı anda hem kuantum bilişiminin hem de Q# programlamanın öğelerini öğretmeyi amaçlar.</span><span class="sxs-lookup"><span data-stu-id="badac-151">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="badac-152">Bu öğreticiler, Q# Jupyter Not Defterleri ile oluşturabileceğiniz içerik türüne dair harika bir örnektir.</span><span class="sxs-lookup"><span data-stu-id="badac-152">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
