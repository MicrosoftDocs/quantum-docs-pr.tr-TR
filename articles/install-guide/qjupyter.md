---
title: 'Q # Jupyıter Not defterleri ile geliştirme'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b7276f9b273f601f30e4938018398353b6a9102d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831078"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="22e52-102">Q # Jupyıter Not defterleri ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="22e52-102">Develop with Q# Jupyter notebooks</span></span>

<span data-ttu-id="22e52-103">Q # Jupyıter not defterlerinde Q # işlemleri geliştirmek için QDK 'yi yükler.</span><span class="sxs-lookup"><span data-stu-id="22e52-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="22e52-104">Jupi Not defterleri yönergeler, notlar ve diğer içeriklerden sonra yerinde kod yürütmeye olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="22e52-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="22e52-105">Bu ortam, yerleşik açıklamalar veya hisse kullanımı etkileşimli öğreticilerle Q # kodu yazmak için idealdir.</span><span class="sxs-lookup"><span data-stu-id="22e52-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="22e52-106">Kendi Q# not defterlerinizi oluşturmaya başlamak için gerekenler aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="22e52-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="22e52-107">IQ# (ay-kü-şarp okunur) öncelikli olarak Jupyter ve Python tarafından .NET Core SDK için kullanılan ve Q# işlemlerinin derlenmesine ve benzetiminin yapılmasına yönelik temel işlevselliği sağlayan bir uzantıdır.</span><span class="sxs-lookup"><span data-stu-id="22e52-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="22e52-108">Q # Jupileter not defterlerinde yalnızca Q # kodunu çalıştırabilir ve işlemler harici konak programlarından (ör. Python veya C# dosyalar) çağrılamaz.</span><span class="sxs-lookup"><span data-stu-id="22e52-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="22e52-109">Amacınız, bir dış klasik ana bilgisayar programını hisse ile çevreliyorsanız, bu ortam uygun değildir.</span><span class="sxs-lookup"><span data-stu-id="22e52-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="22e52-110">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="22e52-110">Pre-requisites</span></span>

    - <span data-ttu-id="22e52-111">[Python](https://www.python.org/downloads/) 3.6 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="22e52-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="22e52-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="22e52-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="22e52-113">.NET Core SDK 3,1 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="22e52-113">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="22e52-114">`iqsharp` paketini yükleyin</span><span class="sxs-lookup"><span data-stu-id="22e52-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="22e52-115">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="22e52-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="22e52-116">Not defteri sunucusunu başlatmak için aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="22e52-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="22e52-117">Jupyter Not defterini açmak için komut satırı tarafından belirtilen URL 'YI kopyalayıp tarayıcınıza yapıştırın.</span><span class="sxs-lookup"><span data-stu-id="22e52-117">To open the Jupyter notebook copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="22e52-118">Bir Q# çekirdeği ile Jupyter not defteri oluşturun ve aşağıdaki kodu birinci not defteri hücresine ekleyin:</span><span class="sxs-lookup"><span data-stu-id="22e52-118">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="22e52-119">Not defterinin şu hücresini çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="22e52-119">Run this cell of the notebook:</span></span>

        ![Q# kodu içeren Jupyter not defteri hücresi](~/media/install-guide-jupyter.png)

        <span data-ttu-id="22e52-121">Hücrenin çıktısında `SayHello` görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="22e52-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="22e52-122">Jupyter not defterlerinde çalışırken Q# kodu derlenir ve not defteri bulduğu işlemlerin adını çıkarır.</span><span class="sxs-lookup"><span data-stu-id="22e52-122">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="22e52-123">Yeni bir hücrede, az önce oluşturduğunuz işlemi (simülatör içinde) `%simulate` komutunu kullanarak yürütün:</span><span class="sxs-lookup"><span data-stu-id="22e52-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![%simulate magic içeren Jupyter not defteri hücresi](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="22e52-125">İade ettiğiniz işlemin sonucuyla birlikte ekranda yazdırılmış iletiyi görmeniz gerekir (burada, işlem yalnızca bir `Unit` türü döndürdüğünden `()` boş tanımlama alanı görüyoruz.</span><span class="sxs-lookup"><span data-stu-id="22e52-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="whats-next"></a><span data-ttu-id="22e52-126">Sırada ne var?</span><span class="sxs-lookup"><span data-stu-id="22e52-126">What's next?</span></span>

<span data-ttu-id="22e52-127">Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.write-program) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="22e52-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
