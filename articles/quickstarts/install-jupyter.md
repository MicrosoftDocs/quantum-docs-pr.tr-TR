---
title: Q# Jupyter Not Defterleri ile geliştirme
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274158"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="4f43a-102">Q# Jupyter Not Defterleri ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="4f43a-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="4f43a-103">Q# Jupyter Not Defterlerinde Q# işlemleri geliştirmek için QDK'yi yükleyin.</span><span class="sxs-lookup"><span data-stu-id="4f43a-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="4f43a-104">Jupyter Not Defterleri yönergeler, notlar ve diğer içeriklerin yanı sıra yerinde kod yürütmeye olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="4f43a-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="4f43a-105">Bu ortam, ekli açıklamalar veya kuantum bilişimi etkileşimli öğreticileri ile Q# kodu yazmak için idealdir.</span><span class="sxs-lookup"><span data-stu-id="4f43a-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="4f43a-106">Kendi Q# not defterlerinizi oluşturmaya başlamak için gerekenler aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="4f43a-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="4f43a-107">IQ# (ay-kü-şarp okunur) öncelikli olarak Jupyter ve Python tarafından .NET Core SDK için kullanılan ve Q# işlemlerinin derlenmesine ve benzetiminin yapılmasına yönelik temel işlevselliği sağlayan bir uzantıdır.</span><span class="sxs-lookup"><span data-stu-id="4f43a-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="4f43a-108">Q# Jupyter Not Defterlerinde yalnızca Q# kodu çalıştırılabilir ve işlemler dış konak programlarından (ör. Python veya C# dosyaları) çağrılamaz.</span><span class="sxs-lookup"><span data-stu-id="4f43a-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="4f43a-109">Amacınız bir dış klasik konak programını kuantum programı ile birleştirmekse, bu ortam uygun değildir.</span><span class="sxs-lookup"><span data-stu-id="4f43a-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="4f43a-110">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="4f43a-110">Prerequisites</span></span>

    - <span data-ttu-id="4f43a-111">[Python](https://www.python.org/downloads/) 3.6 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="4f43a-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="4f43a-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="4f43a-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="4f43a-113">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="4f43a-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="4f43a-114">`iqsharp` paketini yükleyin</span><span class="sxs-lookup"><span data-stu-id="4f43a-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="4f43a-115">`dotnet iqsharp install` adımında bir hata alırsanız yeni bir terminal penceresi açın ve yeniden deneyin.</span><span class="sxs-lookup"><span data-stu-id="4f43a-115">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="4f43a-116">Bu adım da işe yaramazsa yüklü olan `dotnet-iqsharp` aracını (Windows’da `dotnet-iqsharp.exe`) bulup çalıştırmayı deneyin:</span><span class="sxs-lookup"><span data-stu-id="4f43a-116">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="4f43a-117">`/path/to/dotnet-iqsharp`, dosya sisteminizdeki `dotnet-iqsharp` aracının mutlak yolu ile değiştirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="4f43a-117">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="4f43a-118">Genellikle bu, kullanıcı profili klasörünüzdeki `.dotnet/tools` altında bulunur.</span><span class="sxs-lookup"><span data-stu-id="4f43a-118">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>

1. <span data-ttu-id="4f43a-119">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="4f43a-119">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4f43a-120">Not defteri sunucusunu başlatmak için aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="4f43a-120">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="4f43a-121">Jupyter Not Defterini açmak için komut satırı tarafından sağlanan URL’yi kopyalayıp tarayıcınıza yapıştırın.</span><span class="sxs-lookup"><span data-stu-id="4f43a-121">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="4f43a-122">Bir Q# çekirdeği ile Jupyter Not Defteri oluşturun ve aşağıdaki kodu birinci not defteri hücresine ekleyin:</span><span class="sxs-lookup"><span data-stu-id="4f43a-122">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="4f43a-123">Not defterinin şu hücresini çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="4f43a-123">Run this cell of the notebook:</span></span>

        ![Q# kodu içeren Jupyter Not Defteri hücresi](~/media/install-guide-jupyter.png)

        <span data-ttu-id="4f43a-125">Hücrenin çıktısında `SayHello` görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="4f43a-125">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="4f43a-126">Jupyter Not Defterinde çalışırken Q# kodu derlenir ve not defteri bulduğu işlemlerin adını çıkarır.</span><span class="sxs-lookup"><span data-stu-id="4f43a-126">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="4f43a-127">Yeni bir hücrede, az önce oluşturduğunuz işlemi `%simulate` komutunu kullanarak yürütün (simülatör içinde):</span><span class="sxs-lookup"><span data-stu-id="4f43a-127">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![%simulate magic içeren Jupyter Not Defteri hücresi](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="4f43a-129">Ekrana yazdırılmış iletiyle birlikte çağırdığınız işlemin sonucuna da görüyor olmalısınız (burada, işlemimiz yalnızca `Unit` türü döndürdüğünden boş `()` demetini görüyoruz).</span><span class="sxs-lookup"><span data-stu-id="4f43a-129">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4f43a-130">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="4f43a-130">Next steps</span></span>

<span data-ttu-id="4f43a-131">Artık Q# Jupyter Not Defterleri için QDK’yi yüklediğinize göre, Q# kodunuzu doğrudan Jupyter Notebook ortamı içinde yazarak [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4f43a-131">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="4f43a-132">Q# Jupyter Not Defterleri ile yapabileceklerinize ilişkin daha fazla örnek için lütfen şuraya göz atın:</span><span class="sxs-lookup"><span data-stu-id="4f43a-132">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="4f43a-133">[Q# ve Jupyter Notebook’a giriş](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="4f43a-133">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="4f43a-134">Burada, bu ortamda Q# kullanmayı gösteren bir Q# Jupyter Not Defteri bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="4f43a-134">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="4f43a-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), kendi hızınızda ilerleyebileceğiniz öğreticilerden ve Q# Jupyter Not Defterleri biçimindeki programlama alıştırmaları dizilerinden oluşan bir açık kaynak koleksiyondur.</span><span class="sxs-lookup"><span data-stu-id="4f43a-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="4f43a-136">[Quantum Katas öğretici not defterleri](https://github.com/microsoft/QuantumKatas#tutorial-topics) iyi bir başlangıç noktasıdır.</span><span class="sxs-lookup"><span data-stu-id="4f43a-136">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="4f43a-137">Quantum Katas, size aynı anda hem kuantum bilişiminin hem de Q# programlamanın öğelerini öğretmeyi amaçlar.</span><span class="sxs-lookup"><span data-stu-id="4f43a-137">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="4f43a-138">Bu öğreticiler, Q# Jupyter Not Defterleri ile oluşturabileceğiniz içerik türüne dair harika bir örnektir.</span><span class="sxs-lookup"><span data-stu-id="4f43a-138">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
