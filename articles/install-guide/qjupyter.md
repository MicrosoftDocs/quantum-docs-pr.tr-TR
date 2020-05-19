---
title: 'Q # Jupyıter Not defterleri ile geliştirme'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 3302a9bd0652b2dea86b844058bf8303ee7a4a7f
ms.sourcegitcommit: c85c1b439807ac576d3a11aadca307d57b059673
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/18/2020
ms.locfileid: "83551048"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="05e7a-102">Q # Jupyıter Not defterleri ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="05e7a-102">Develop with Q# Jupyter notebooks</span></span>

<span data-ttu-id="05e7a-103">Q # Jupyıter not defterlerinde Q # işlemleri geliştirmek için QDK 'yi yükler.</span><span class="sxs-lookup"><span data-stu-id="05e7a-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="05e7a-104">Jupi Not defterleri yönergeler, notlar ve diğer içeriklerden sonra yerinde kod yürütmeye olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="05e7a-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="05e7a-105">Bu ortam, yerleşik açıklamalar veya hisse kullanımı etkileşimli öğreticilerle Q # kodu yazmak için idealdir.</span><span class="sxs-lookup"><span data-stu-id="05e7a-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="05e7a-106">Kendi Q# not defterlerinizi oluşturmaya başlamak için gerekenler aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="05e7a-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="05e7a-107">IQ# (ay-kü-şarp okunur) öncelikli olarak Jupyter ve Python tarafından .NET Core SDK için kullanılan ve Q# işlemlerinin derlenmesine ve benzetiminin yapılmasına yönelik temel işlevselliği sağlayan bir uzantıdır.</span><span class="sxs-lookup"><span data-stu-id="05e7a-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="05e7a-108">Q # Jupileter not defterlerinde yalnızca Q # kodunu çalıştırabilir ve işlemler harici konak programlarından (ör. Python veya C# dosyaları) çağrılamaz.</span><span class="sxs-lookup"><span data-stu-id="05e7a-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="05e7a-109">Amacınız, bir dış klasik ana bilgisayar programını hisse ile çevreliyorsanız, bu ortam uygun değildir.</span><span class="sxs-lookup"><span data-stu-id="05e7a-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="05e7a-110">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="05e7a-110">Pre-requisites</span></span>

    - <span data-ttu-id="05e7a-111">[Python](https://www.python.org/downloads/) 3,6 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="05e7a-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="05e7a-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="05e7a-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="05e7a-113">.NET Core SDK 3,1</span><span class="sxs-lookup"><span data-stu-id="05e7a-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="05e7a-114">`iqsharp` paketini yükleyin</span><span class="sxs-lookup"><span data-stu-id="05e7a-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="05e7a-115">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="05e7a-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="05e7a-116">Not defteri sunucusunu başlatmak için aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="05e7a-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="05e7a-117">Jupyter Not defterini açmak için komut satırı tarafından belirtilen URL 'YI kopyalayıp tarayıcınıza yapıştırın.</span><span class="sxs-lookup"><span data-stu-id="05e7a-117">To open the Jupyter notebook copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="05e7a-118">Bir Q# çekirdeği ile Jupyter not defteri oluşturun ve aşağıdaki kodu birinci not defteri hücresine ekleyin:</span><span class="sxs-lookup"><span data-stu-id="05e7a-118">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="05e7a-119">Not defterinin şu hücresini çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="05e7a-119">Run this cell of the notebook:</span></span>

        ![Q# kodu içeren Jupyter not defteri hücresi](~/media/install-guide-jupyter.png)

        <span data-ttu-id="05e7a-121">Hücrenin çıktısında `SayHello` görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="05e7a-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="05e7a-122">Jupyter not defterlerinde çalışırken Q# kodu derlenir ve not defteri bulduğu işlemlerin adını çıkarır.</span><span class="sxs-lookup"><span data-stu-id="05e7a-122">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="05e7a-123">Yeni bir hücrede, komutunu kullanarak yeni oluşturduğunuz işlemi (simülatör içinde) yürütün `%simulate` :</span><span class="sxs-lookup"><span data-stu-id="05e7a-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![%simulate magic içeren Jupyter not defteri hücresi](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="05e7a-125">İade ettiğiniz işlemin sonucuyla birlikte ekranda yazdırılmış iletiyi görmeniz gerekir (burada, `()` işlem yalnızca bir tür döndürdüğünden, boş tanımlama alanı görüyoruz `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="05e7a-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="05e7a-126">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="05e7a-126">Next steps</span></span>

<span data-ttu-id="05e7a-127">Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="05e7a-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
