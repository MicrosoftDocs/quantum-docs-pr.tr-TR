---
title: Microsoft Quantum Development Kit (QDK) yüklemeyi öğrenin
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 2a098d89f13278d7137bf182a184a74afb9393be
ms.sourcegitcommit: 2ca4755d1a63431e3cb2d2918a10ad477ec2e368
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73462877"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="b92d7-102">Microsoft Quantum Development Kit (QDK) yükleme</span><span class="sxs-lookup"><span data-stu-id="b92d7-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="b92d7-103">Kuantum programlamaya başlayabilmek için Microsoft Quantum Development Kit (QDK) yükleme hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="b92d7-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="b92d7-104">QDK aşağıdakilerden oluşur:</span><span class="sxs-lookup"><span data-stu-id="b92d7-104">The QDK consists of:</span></span>

- <span data-ttu-id="b92d7-105">Q# programlama dili</span><span class="sxs-lookup"><span data-stu-id="b92d7-105">the Q# programming language</span></span>
- <span data-ttu-id="b92d7-106">Q# dilinde karmaşık işlevleri özetleyen bir kitaplık kümesi</span><span class="sxs-lookup"><span data-stu-id="b92d7-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="b92d7-107">Q# dilinde yazılmış kuantum işlemleri çalıştıran bir konak uygulama (Python veya bir .NET dilinde yazılmış)</span><span class="sxs-lookup"><span data-stu-id="b92d7-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="b92d7-108">geliştirmenizi kolaylaştıracak araçlar</span><span class="sxs-lookup"><span data-stu-id="b92d7-108">tools to facilitate your development</span></span>

<span data-ttu-id="b92d7-109">Seçtiğiniz geliştirme ortamına bağlı olarak, farklı yükleme adımları vardır.</span><span class="sxs-lookup"><span data-stu-id="b92d7-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="b92d7-110">Ortamınızı aşağıdaki bölümlerden seçin.</span><span class="sxs-lookup"><span data-stu-id="b92d7-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="b92d7-111">Python ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="b92d7-111">Develop with Python</span></span>

<span data-ttu-id="b92d7-112">Python için qsharp paketi, Python’da Q# işlemleri ve işlevlerinin simülasyonunu yapmayı kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="b92d7-112">The qsharp package for Python makes it easy to simulate Q# operations and functions from within Python.</span></span> <span data-ttu-id="b92d7-113">IQ# (ay-kü-şarp okunur) öncelikli olarak Jupyter ve Python tarafından kullanılan ve Q# işlemlerinin derlenmesine ve benzetiminin yapılmasına yönelik temel işlevselliği sağlayan bir uzantıdır.</span><span class="sxs-lookup"><span data-stu-id="b92d7-113">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python that provides the core functionality for compiling and simulating Q# operations.</span></span>

1. <span data-ttu-id="b92d7-114">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="b92d7-114">Pre-requisites</span></span>

    - <span data-ttu-id="b92d7-115">[Python](https://www.python.org/downloads/) 3.6 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="b92d7-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="b92d7-116">[PIP](https://pip.pypa.io/en/stable/installing) Python paket yöneticisi</span><span class="sxs-lookup"><span data-stu-id="b92d7-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="b92d7-117">.NET Core SDK 3.0 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="b92d7-117">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="b92d7-118">`iqsharp` paketini yükleyin</span><span class="sxs-lookup"><span data-stu-id="b92d7-118">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="b92d7-119">`qsharp` paketini yükleyin</span><span class="sxs-lookup"><span data-stu-id="b92d7-119">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="b92d7-120">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="b92d7-120">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b92d7-121">`Operation.qs` adlı bir dosya oluşturup dosyaya aşağıdaki kodu ekleyerek küçük bir Q# işlemi oluşturun:</span><span class="sxs-lookup"><span data-stu-id="b92d7-121">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - <span data-ttu-id="b92d7-122">Q# `SayHello()` işlemini çağırmak için `hello_world.py` adlı bir Python programı oluşturun:</span><span class="sxs-lookup"><span data-stu-id="b92d7-122">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="b92d7-123">Programı çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="b92d7-123">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="b92d7-124">Çıktıyı doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="b92d7-124">Verify the output.</span></span> <span data-ttu-id="b92d7-125">Programınız aşağıdaki satırları çıkarmalıdır:</span><span class="sxs-lookup"><span data-stu-id="b92d7-125">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="b92d7-126">Jupyter not defterleri ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="b92d7-126">Develop with Jupyter notebooks</span></span>

<span data-ttu-id="b92d7-127">Akademik ortamlarda, bilimsel laboratuvarlarda ve İnternet'te işbirliğine dayalı programlamada tercih edilen Jupyter Notebooks şimdi Q# kodu da dahil olmak üzere yerinde kod yürütme, ayrıca yönergeler, notlar ve başka içerik sağlar.</span><span class="sxs-lookup"><span data-stu-id="b92d7-127">A favorite of academic settings, scientific labs, and online-based collaborative programming, Jupyter Notebooks offer in-place code execution—now including Q# code—along with instructions, notes, and other content.</span></span>  <span data-ttu-id="b92d7-128">Kendi Q# not defterlerinizi oluşturmaya başlamak için gerekenler aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="b92d7-128">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="b92d7-129">IQ# (ay-kü-şarp okunur) öncelikli olarak Jupyter ve Python tarafından .NET Core SDK için kullanılan ve Q# işlemlerinin derlenmesine ve benzetiminin yapılmasına yönelik temel işlevselliği sağlayan bir uzantıdır.</span><span class="sxs-lookup"><span data-stu-id="b92d7-129">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>


1. <span data-ttu-id="b92d7-130">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="b92d7-130">Pre-requisites</span></span>

    - <span data-ttu-id="b92d7-131">[Python](https://www.python.org/downloads/) 3.6 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="b92d7-131">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="b92d7-132">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="b92d7-132">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="b92d7-133">.NET Core SDK 3.0 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="b92d7-133">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="b92d7-134">`iqsharp` paketini yükleyin</span><span class="sxs-lookup"><span data-stu-id="b92d7-134">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="b92d7-135">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="b92d7-135">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b92d7-136">Not defteri sunucusunu başlatmak için aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="b92d7-136">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="b92d7-137">Komut satırında gösterilen URL'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="b92d7-137">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="b92d7-138">Örneğin: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="b92d7-138">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="b92d7-139">Bir Q# çekirdeği ile Jupyter not defteri oluşturun ve aşağıdaki kodu birinci not defteri hücresine ekleyin:</span><span class="sxs-lookup"><span data-stu-id="b92d7-139">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="b92d7-140">Not defterinin şu hücresini çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="b92d7-140">Run this cell of the notebook:</span></span>

        ![Q# kodu içeren Jupyter not defteri hücresi](~/media/install-guide-jupyter.png)

        <span data-ttu-id="b92d7-142">Hücrenin çıktısında `SayHello` görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="b92d7-142">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="b92d7-143">Jupyter not defterlerinde çalışırken Q# kodu derlenir ve not defteri bulduğu işlemlerin adını çıkarır.</span><span class="sxs-lookup"><span data-stu-id="b92d7-143">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="b92d7-144">Yeni bir hücrede `%simulate` magic kullanarak yeni oluşturduğunuz işlemin kuantum bilgisayarda yürütmesinin benzetimini yapın:</span><span class="sxs-lookup"><span data-stu-id="b92d7-144">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

        ![%simulate magic içeren Jupyter not defteri hücresi](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="b92d7-146">Ekrana yazdırılmış bir iletiyle birlikte çağırdığınız işlemin sonucuna da (bu örnekte boş) görüyor olmalısınız.</span><span class="sxs-lookup"><span data-stu-id="b92d7-146">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>


## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="b92d7-147">Visual Studio kullanarak Windows üzerinde C# ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="b92d7-147">Develop with C# on Windows, using Visual Studio</span></span>

<span data-ttu-id="b92d7-148">Visual Studio Q# programları geliştirmek için zengin bir ortam sunar; geliştiricilere uygulamalarını oluştururken yol gösteren kod tamamlama ve söz dizimi vurgulama gibi harika özellikler sağlar.</span><span class="sxs-lookup"><span data-stu-id="b92d7-148">Visual Studio offers a rich environment for developing Q# programs, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="b92d7-149">Q# Visual Studio uzantısı hem Q# dosyaları ve projeleri için şablonlar hem de söz dizimi vurgulama özelliği ve IntelliSense desteği içerir.</span><span class="sxs-lookup"><span data-stu-id="b92d7-149">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting and IntelliSense support.</span></span>


1. <span data-ttu-id="b92d7-150">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="b92d7-150">Pre-requisites</span></span>

    - <span data-ttu-id="b92d7-151">.NET Core platformlar arası geliştirme iş yükü etkin olan [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3</span><span class="sxs-lookup"><span data-stu-id="b92d7-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="b92d7-152">Q# Visual Studio uzantısını yükleyin</span><span class="sxs-lookup"><span data-stu-id="b92d7-152">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="b92d7-153">[Visual Studio uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) indirin</span><span class="sxs-lookup"><span data-stu-id="b92d7-153">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="b92d7-154">Uzantıyı Visual Studio'ya ekleyin</span><span class="sxs-lookup"><span data-stu-id="b92d7-154">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="b92d7-155">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="b92d7-155">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b92d7-156">Yeni bir Q# uygulaması oluşturun</span><span class="sxs-lookup"><span data-stu-id="b92d7-156">Create a new Q# application</span></span>

        - <span data-ttu-id="b92d7-157">**Dosya** -> **Yeni** -> **Proje**’ye gidin</span><span class="sxs-lookup"><span data-stu-id="b92d7-157">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="b92d7-158">Arama kutusuna `Q#` yazın</span><span class="sxs-lookup"><span data-stu-id="b92d7-158">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="b92d7-159">**Q# Uygulaması**’nı seçin</span><span class="sxs-lookup"><span data-stu-id="b92d7-159">Select **Q# Application**</span></span>
        - <span data-ttu-id="b92d7-160">**İleri**’yi seçin</span><span class="sxs-lookup"><span data-stu-id="b92d7-160">Select **Next**</span></span>
        - <span data-ttu-id="b92d7-161">Uygulamanız için bir ad ve konum seçin</span><span class="sxs-lookup"><span data-stu-id="b92d7-161">Choose a name and location for your application</span></span>
        - <span data-ttu-id="b92d7-162">**Oluştur**’u seçin</span><span class="sxs-lookup"><span data-stu-id="b92d7-162">Select **Create**</span></span>

    - <span data-ttu-id="b92d7-163">Projeyi inceleyin</span><span class="sxs-lookup"><span data-stu-id="b92d7-163">Inspect the project</span></span>

        <span data-ttu-id="b92d7-164">İki dosya oluşturulur: C# konak uygulaması olan `Driver.cs` ve konsola bir ileti yazdıran basit işlemi tanımlayan Q# programı `Operation.qs`.</span><span class="sxs-lookup"><span data-stu-id="b92d7-164">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="b92d7-165">Uygulamayı çalıştırma</span><span class="sxs-lookup"><span data-stu-id="b92d7-165">Run the application</span></span>

        - <span data-ttu-id="b92d7-166">**Hata Ayıklama** -> **Hata Ayıklamadan Başlat**’ı seçin</span><span class="sxs-lookup"><span data-stu-id="b92d7-166">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="b92d7-167">Bir konsol penceresinde yazdırılmış `Hello quantum world!` metni görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="b92d7-167">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="b92d7-168">Bir Visual Studio çözümünde birden fazla projeniz varsa, çözümde yer alan tüm projelerin çözüm ile aynı klasörde veya bunun bir alt klasöründe olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="b92d7-168">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-visual-studio-code"></a><span data-ttu-id="b92d7-169">Visual Studio Code kullanarak C# ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="b92d7-169">Develop with C#, using Visual Studio Code</span></span>

<span data-ttu-id="b92d7-170">Visual Studio Code (VS Code) Windows, Linux ve Mac gibi çeşitli bilgisayar ortamlarında Q# programları geliştirmek için zengin bir ortam sunar; geliştiricilere uygulamalarını oluştururken yol gösteren kod tamamlama ve söz dizimi vurgulama gibi harika özellikler sağlar.</span><span class="sxs-lookup"><span data-stu-id="b92d7-170">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs across many multiple computer environments, including Windows, Linux and Mac, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="b92d7-171">Q# VS Code uzantısı söz dizimi vurgulama özelliği ve Q# kod parçacıkları içerir.</span><span class="sxs-lookup"><span data-stu-id="b92d7-171">The Q# VS Code extension contains syntax highlighting, and Q# code snippets.</span></span>

1. <span data-ttu-id="b92d7-172">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="b92d7-172">Pre-requisites</span></span>

   - [<span data-ttu-id="b92d7-173">VS Code</span><span class="sxs-lookup"><span data-stu-id="b92d7-173">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="b92d7-174">.NET Core SDK 3.0 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="b92d7-174">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="b92d7-175">Kuantum VS Code uzantısını yükleme</span><span class="sxs-lookup"><span data-stu-id="b92d7-175">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="b92d7-176">[VS Code uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) yükleyin</span><span class="sxs-lookup"><span data-stu-id="b92d7-176">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="b92d7-177">Kuantum proje şablonlarını yükleyin:</span><span class="sxs-lookup"><span data-stu-id="b92d7-177">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="b92d7-178">**Görünüm** -> **Komut Paleti**’ne gidin</span><span class="sxs-lookup"><span data-stu-id="b92d7-178">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="b92d7-179">**Q#: Proje şablonlarını yükle**’yi seçin</span><span class="sxs-lookup"><span data-stu-id="b92d7-179">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="b92d7-180">Quantum Development Kit yüklenmiştir ve kendi uygulama ve kitaplıklarınızda kullanılmaya hazırdır.</span><span class="sxs-lookup"><span data-stu-id="b92d7-180">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="b92d7-181">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="b92d7-181">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b92d7-182">Yeni bir proje oluşturun:</span><span class="sxs-lookup"><span data-stu-id="b92d7-182">Create a new project:</span></span>

        - <span data-ttu-id="b92d7-183">**Görünüm** -> **Komut Paleti**’ne gidin</span><span class="sxs-lookup"><span data-stu-id="b92d7-183">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="b92d7-184">**Q#: Yeni Proje Oluştur**’u seçin</span><span class="sxs-lookup"><span data-stu-id="b92d7-184">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="b92d7-185">Dosya sisteminde uygulamayı oluşturmak istediğiniz konuma gidin</span><span class="sxs-lookup"><span data-stu-id="b92d7-185">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="b92d7-186">Proje oluşturulduktan sonra **Yeni proje aç...** düğmesine tıklayın</span><span class="sxs-lookup"><span data-stu-id="b92d7-186">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="b92d7-187">Uygulamayı çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="b92d7-187">Run the application:</span></span>

        - <span data-ttu-id="b92d7-188">**Hata Ayıklama** -> **Hata Ayıklamadan Başlat**’a gidin</span><span class="sxs-lookup"><span data-stu-id="b92d7-188">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="b92d7-189">Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="b92d7-189">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="b92d7-190">Birden fazla kök klasörü olan çalışma alanları şu anda Visual Studio Code uzantısı tarafından desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="b92d7-190">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="b92d7-191">Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.</span><span class="sxs-lookup"><span data-stu-id="b92d7-191">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="b92d7-192">`dotnet` komut satırı aracını kullanarak C# ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="b92d7-192">Develop with C#, using the `dotnet` command-line tool</span></span>

<span data-ttu-id="b92d7-193">Kuşkusuz yalnızca .NET Core SDK'sını ve QDK proje şablonlarını yükleyerek Q# programlarını komut satırından da oluşturup çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b92d7-193">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="b92d7-194">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="b92d7-194">Pre-requisites</span></span>

    - [<span data-ttu-id="b92d7-195">.NET Core SDK 3.0 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="b92d7-195">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="b92d7-196">.NET için Kuantum proje şablonlarını yükleme</span><span class="sxs-lookup"><span data-stu-id="b92d7-196">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="b92d7-197">Quantum Development Kit yüklenmiştir ve kendi uygulama ve kitaplıklarınızda kullanılmaya hazırdır.</span><span class="sxs-lookup"><span data-stu-id="b92d7-197">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="b92d7-198">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="b92d7-198">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b92d7-199">Yeni uygulama oluşturma</span><span class="sxs-lookup"><span data-stu-id="b92d7-199">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="b92d7-200">Yeni uygulama dizinine gidin</span><span class="sxs-lookup"><span data-stu-id="b92d7-200">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="b92d7-201">Uygulamanın proje dosyaları ile birlikte iki dosyanın oluşturulur: bir Q# dosyası (`Operation.qs`) ve bir C# konak dosyası (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="b92d7-201">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="b92d7-202">Uygulamayı çalıştırma</span><span class="sxs-lookup"><span data-stu-id="b92d7-202">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="b92d7-203">Şu çıktıyı görmeniz gerekir: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="b92d7-203">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="b92d7-204">Sırada ne var?</span><span class="sxs-lookup"><span data-stu-id="b92d7-204">What's next?</span></span>

<span data-ttu-id="b92d7-205">Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.write-program) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b92d7-205">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
