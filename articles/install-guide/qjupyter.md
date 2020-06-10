---
title: Q# Jupyter Notebooks ile geliştirme
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b80d95a160b5f46c1132d3428ba32ad6dcd5656e
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630343"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="5477f-102">Q# Jupyter Notebooks ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="5477f-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="5477f-103">Q # Jupyıter not defterlerinde Q # işlemleri geliştirmek için QDK 'yi yükler.</span><span class="sxs-lookup"><span data-stu-id="5477f-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="5477f-104">Jupi Not defterleri yönergeler, notlar ve diğer içeriklerden sonra yerinde kod yürütmeye olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="5477f-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="5477f-105">Bu ortam, yerleşik açıklamalar veya hisse kullanımı etkileşimli öğreticilerle Q # kodu yazmak için idealdir.</span><span class="sxs-lookup"><span data-stu-id="5477f-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="5477f-106">Kendi Q# not defterlerinizi oluşturmaya başlamak için gerekenler aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="5477f-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="5477f-107">IQ# (ay-kü-şarp okunur) öncelikli olarak Jupyter ve Python tarafından .NET Core SDK için kullanılan ve Q# işlemlerinin derlenmesine ve benzetiminin yapılmasına yönelik temel işlevselliği sağlayan bir uzantıdır.</span><span class="sxs-lookup"><span data-stu-id="5477f-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="5477f-108">Q # Jupileter not defterlerinde yalnızca Q # kodunu çalıştırabilir ve işlemler harici konak programlarından (ör. Python veya C# dosyaları) çağrılamaz.</span><span class="sxs-lookup"><span data-stu-id="5477f-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="5477f-109">Amacınız, bir dış klasik ana bilgisayar programını hisse ile çevreliyorsanız, bu ortam uygun değildir.</span><span class="sxs-lookup"><span data-stu-id="5477f-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="5477f-110">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="5477f-110">Prerequisites</span></span>

    - <span data-ttu-id="5477f-111">[Python](https://www.python.org/downloads/) 3,6 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="5477f-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="5477f-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="5477f-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="5477f-113">.NET Core SDK 3,1</span><span class="sxs-lookup"><span data-stu-id="5477f-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="5477f-114">`iqsharp` paketini yükleyin</span><span class="sxs-lookup"><span data-stu-id="5477f-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="5477f-115">Adım sırasında bir hata alırsanız `dotnet iqsharp install` , yeni bir Terminal penceresi açın ve yeniden deneyin.</span><span class="sxs-lookup"><span data-stu-id="5477f-115">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="5477f-116">Bu hala işe yaramazsa, yüklü `dotnet-iqsharp` Aracı (Windows 'da `dotnet-iqsharp.exe` ) bulup çalıştırmayı deneyin:</span><span class="sxs-lookup"><span data-stu-id="5477f-116">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="5477f-117">`/path/to/dotnet-iqsharp`dosya sisteminizdeki aracın mutlak yolu ile değiştirilmelidir `dotnet-iqsharp` .</span><span class="sxs-lookup"><span data-stu-id="5477f-117">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="5477f-118">Genellikle bu, `.dotnet/tools` Kullanıcı profili klasörünüzde olacaktır.</span><span class="sxs-lookup"><span data-stu-id="5477f-118">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>

1. <span data-ttu-id="5477f-119">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="5477f-119">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="5477f-120">Not defteri sunucusunu başlatmak için aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="5477f-120">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="5477f-121">Jupyter Notebook açmak için komut satırı tarafından belirtilen URL 'YI kopyalayıp tarayıcınıza yapıştırın.</span><span class="sxs-lookup"><span data-stu-id="5477f-121">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="5477f-122">Bir Q # çekirdeğiyle Jupyter Notebook oluşturun ve ilk not defteri hücresine aşağıdaki kodu ekleyin:</span><span class="sxs-lookup"><span data-stu-id="5477f-122">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="5477f-123">Not defterinin şu hücresini çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="5477f-123">Run this cell of the notebook:</span></span>

        ![Q # kodlu Jupyter Notebook hücresi](~/media/install-guide-jupyter.png)

        <span data-ttu-id="5477f-125">Hücrenin çıktısında `SayHello` görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="5477f-125">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="5477f-126">Jupyter Notebook 'de çalışırken, Q # kodu derlenir ve Not defteri bulduğu işlem (ler) in adını verir.</span><span class="sxs-lookup"><span data-stu-id="5477f-126">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="5477f-127">Yeni bir hücrede, komutunu kullanarak yeni oluşturduğunuz işlemi (simülatör içinde) yürütün `%simulate` :</span><span class="sxs-lookup"><span data-stu-id="5477f-127">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![% Benzetim Magic ile Jupyter Notebook hücresi](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="5477f-129">İade ettiğiniz işlemin sonucuyla birlikte ekranda yazdırılmış iletiyi görmeniz gerekir (burada, `()` işlem yalnızca bir tür döndürdüğünden, boş tanımlama alanı görüyoruz `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="5477f-129">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5477f-130">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="5477f-130">Next steps</span></span>

<span data-ttu-id="5477f-131">Artık, Q # jupi Not defterleri için QDK yükleolduğunuza göre, doğrudan Jupyter Notebook ortamı içinde Q # kodunuzu yazarak [ilk hisse programınızı](xref:microsoft.quantum.quickstarts.qrng) yazabilir ve çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5477f-131">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="5477f-132">Q # Jupyter Not defterleri ile yapabileceklerinize ilişkin daha fazla örnek için lütfen şu adresten göz atabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="5477f-132">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="5477f-133">[Q # ve Jupyter Notebook girişi](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="5477f-133">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="5477f-134">Bu ortamda Q # kullanmayı gösteren bir Q # Jupyter Notebook bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="5477f-134">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="5477f-135">Hisse uyumlu öğreticilerin açık kaynaklı bir koleksiyonu olan [hisse katas](xref:microsoft.quantum.overview.katas), Q # jupi Not defterleri biçimindeki programlama alıştırmaları kümesi.</span><span class="sxs-lookup"><span data-stu-id="5477f-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="5477f-136">[Hisse katas öğretici Not defterleri](https://github.com/microsoft/QuantumKatas#tutorial-topics) iyi bir başlangıç noktasıdır.</span><span class="sxs-lookup"><span data-stu-id="5477f-136">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="5477f-137">Hisse katas, size aynı anda hisse bilgi işlem ve Q # programlama öğelerini öğretme amacıyla tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="5477f-137">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="5477f-138">Bunlar, Q # jupi Not defterleri ile oluşturabileceğiniz içerik türü için harika bir örnektir.</span><span class="sxs-lookup"><span data-stu-id="5477f-138">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
