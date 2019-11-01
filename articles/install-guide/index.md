---
title: Microsoft Quantum Development Kit (QDK) yüklemeyi öğrenin
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 3ec53934436b47908fd4d794a98933010f6059a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035298"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="7247d-102">Microsoft Quantum Development Kit (QDK) yükleme</span><span class="sxs-lookup"><span data-stu-id="7247d-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="7247d-103">Kuantum programlamaya başlayabilmek için Microsoft Quantum Development Kit (QDK) yükleme hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="7247d-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="7247d-104">QDK aşağıdakilerden oluşur:</span><span class="sxs-lookup"><span data-stu-id="7247d-104">The QDK consists of:</span></span>

- <span data-ttu-id="7247d-105">Q# programlama dili</span><span class="sxs-lookup"><span data-stu-id="7247d-105">the Q# programming language</span></span>
- <span data-ttu-id="7247d-106">Q# dilinde karmaşık işlevleri özetleyen bir kitaplık kümesi</span><span class="sxs-lookup"><span data-stu-id="7247d-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="7247d-107">Q# dilinde yazılmış kuantum işlemleri çalıştıran bir konak uygulama (Python veya bir .NET dilinde yazılmış)</span><span class="sxs-lookup"><span data-stu-id="7247d-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="7247d-108">geliştirmenizi kolaylaştıracak araçlar</span><span class="sxs-lookup"><span data-stu-id="7247d-108">tools to facilitate your development</span></span>

<span data-ttu-id="7247d-109">Seçtiğiniz geliştirme ortamına bağlı olarak, farklı yükleme adımları vardır.</span><span class="sxs-lookup"><span data-stu-id="7247d-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="7247d-110">Ortamınızı aşağıdaki bölümlerden seçin.</span><span class="sxs-lookup"><span data-stu-id="7247d-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="7247d-111">Python ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="7247d-111">Develop with Python</span></span>

1. <span data-ttu-id="7247d-112">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="7247d-112">Pre-requisites</span></span>

    - <span data-ttu-id="7247d-113">[Python](https://www.python.org/downloads/) 3.6 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="7247d-113">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="7247d-114">[PIP](https://pip.pypa.io/en/stable/installing) Python paket yöneticisi</span><span class="sxs-lookup"><span data-stu-id="7247d-114">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="7247d-115">.NET Core SDK 2.1 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="7247d-115">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="7247d-116">`iqsharp` paketini yükleyin</span><span class="sxs-lookup"><span data-stu-id="7247d-116">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="7247d-117">`qsharp` paketini yükleyin</span><span class="sxs-lookup"><span data-stu-id="7247d-117">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="7247d-118">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="7247d-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="7247d-119">`Operation.qs` adlı bir dosya oluşturup dosyaya aşağıdaki kodu ekleyerek küçük bir Q# işlemi oluşturun:</span><span class="sxs-lookup"><span data-stu-id="7247d-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

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

    - <span data-ttu-id="7247d-120">Q# `SayHello()` işlemini çağırmak için `hello_world.py` adlı bir Python programı oluşturun:</span><span class="sxs-lookup"><span data-stu-id="7247d-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="7247d-121">Programı çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="7247d-121">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="7247d-122">Çıktıyı doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="7247d-122">Verify the output.</span></span> <span data-ttu-id="7247d-123">Programınız aşağıdaki satırları çıkarmalıdır:</span><span class="sxs-lookup"><span data-stu-id="7247d-123">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="7247d-124">Jupyter not defterleri ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="7247d-124">Develop with Jupyter notebooks</span></span>

1. <span data-ttu-id="7247d-125">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="7247d-125">Pre-requisites</span></span>

    - <span data-ttu-id="7247d-126">[Python](https://www.python.org/downloads/) 3.6 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="7247d-126">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="7247d-127">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="7247d-127">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="7247d-128">.NET Core SDK 2.1 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="7247d-128">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="7247d-129">`iqsharp` paketini yükleyin</span><span class="sxs-lookup"><span data-stu-id="7247d-129">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="7247d-130">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="7247d-130">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="7247d-131">Not defteri sunucusunu başlatmak için aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="7247d-131">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="7247d-132">Komut satırında gösterilen URL'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="7247d-132">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="7247d-133">Örneğin: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="7247d-133">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="7247d-134">Bir Q# çekirdeği ile Jupyter not defteri oluşturun ve aşağıdaki kodu birinci not defteri hücresine ekleyin:</span><span class="sxs-lookup"><span data-stu-id="7247d-134">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="7247d-135">Not defterinin şu hücresini çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="7247d-135">Run this cell of the notebook:</span></span>

        ![Jupyter not defteri hücresi](~/media/install-guide-jupyter.png)

        <span data-ttu-id="7247d-137">Hücrenin çıktısında `SayHello` görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="7247d-137">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="7247d-138">Jupyter not defterlerinde çalışırken Q# kodu derlenir ve not defteri bulduğu işlemlerin adını çıkarır.</span><span class="sxs-lookup"><span data-stu-id="7247d-138">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="7247d-139">Visual Studio kullanarak Windows üzerinde C# ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="7247d-139">Develop with C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="7247d-140">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="7247d-140">Pre-requisites</span></span>

    - <span data-ttu-id="7247d-141">.NET Core platformlar arası geliştirme iş yükü etkin olan [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3</span><span class="sxs-lookup"><span data-stu-id="7247d-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="7247d-142">Q# Visual Studio uzantısını yükleyin</span><span class="sxs-lookup"><span data-stu-id="7247d-142">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="7247d-143">[Visual Studio uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) indirin</span><span class="sxs-lookup"><span data-stu-id="7247d-143">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="7247d-144">Uzantıyı Visual Studio'ya ekleyin</span><span class="sxs-lookup"><span data-stu-id="7247d-144">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="7247d-145">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="7247d-145">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="7247d-146">Yeni bir Q# uygulaması oluşturun</span><span class="sxs-lookup"><span data-stu-id="7247d-146">Create a new Q# application</span></span>

        - <span data-ttu-id="7247d-147">**Dosya** -> **Yeni** -> **Proje**’ye gidin</span><span class="sxs-lookup"><span data-stu-id="7247d-147">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="7247d-148">Arama kutusuna `Q#` yazın</span><span class="sxs-lookup"><span data-stu-id="7247d-148">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="7247d-149">**Q# Uygulaması**’nı seçin</span><span class="sxs-lookup"><span data-stu-id="7247d-149">Select **Q# Application**</span></span>
        - <span data-ttu-id="7247d-150">**İleri**’yi seçin</span><span class="sxs-lookup"><span data-stu-id="7247d-150">Select **Next**</span></span>
        - <span data-ttu-id="7247d-151">Uygulamanız için bir ad ve konum seçin</span><span class="sxs-lookup"><span data-stu-id="7247d-151">Choose a name and location for your application</span></span>
        - <span data-ttu-id="7247d-152">**Oluştur**’u seçin</span><span class="sxs-lookup"><span data-stu-id="7247d-152">Select **Create**</span></span>

    - <span data-ttu-id="7247d-153">Projeyi inceleyin</span><span class="sxs-lookup"><span data-stu-id="7247d-153">Inspect the project</span></span>

        <span data-ttu-id="7247d-154">İki dosya oluşturulur: C# konak uygulaması olan `Driver.cs` ve konsola bir ileti yazdıran basit işlemi tanımlayan Q# programı `Operation.qs`.</span><span class="sxs-lookup"><span data-stu-id="7247d-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="7247d-155">Uygulamayı çalıştırma</span><span class="sxs-lookup"><span data-stu-id="7247d-155">Run the application</span></span>

        - <span data-ttu-id="7247d-156">**Hata Ayıklama** -> **Hata Ayıklamadan Başlat**’ı seçin</span><span class="sxs-lookup"><span data-stu-id="7247d-156">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="7247d-157">Bir konsol penceresinde yazdırılmış `Hello quantum world!` metni görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="7247d-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="7247d-158">Bir Visual Studio çözümünde birden fazla projeniz varsa, çözümde yer alan tüm projelerin çözüm ile aynı klasörde veya bunun bir alt klasöründe olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="7247d-158">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-vs-code"></a><span data-ttu-id="7247d-159">VS Code kullanarak C# ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="7247d-159">Develop with C#, using VS Code</span></span>

1. <span data-ttu-id="7247d-160">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="7247d-160">Pre-requisites</span></span>

   - [<span data-ttu-id="7247d-161">VS Code</span><span class="sxs-lookup"><span data-stu-id="7247d-161">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="7247d-162">.NET Core SDK 2.1 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="7247d-162">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="7247d-163">Kuantum VS Code uzantısını yükleme</span><span class="sxs-lookup"><span data-stu-id="7247d-163">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="7247d-164">[VS Code uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) yükleyin</span><span class="sxs-lookup"><span data-stu-id="7247d-164">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="7247d-165">Kuantum proje şablonlarını yükleyin:</span><span class="sxs-lookup"><span data-stu-id="7247d-165">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="7247d-166">**Görünüm** -> **Komut Paleti**’ne gidin</span><span class="sxs-lookup"><span data-stu-id="7247d-166">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="7247d-167">**Q#: Proje şablonlarını yükle**’yi seçin</span><span class="sxs-lookup"><span data-stu-id="7247d-167">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="7247d-168">Quantum Development Kit yüklenmiştir ve kendi uygulama ve kitaplıklarınızda kullanılmaya hazırdır.</span><span class="sxs-lookup"><span data-stu-id="7247d-168">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="7247d-169">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="7247d-169">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="7247d-170">Yeni bir proje oluşturun:</span><span class="sxs-lookup"><span data-stu-id="7247d-170">Create a new project:</span></span>

        - <span data-ttu-id="7247d-171">**Görünüm** -> **Komut Paleti**’ne gidin</span><span class="sxs-lookup"><span data-stu-id="7247d-171">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="7247d-172">**Q#: Yeni Proje Oluştur**’u seçin</span><span class="sxs-lookup"><span data-stu-id="7247d-172">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="7247d-173">Dosya sisteminde uygulamayı oluşturmak istediğiniz konuma gidin</span><span class="sxs-lookup"><span data-stu-id="7247d-173">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="7247d-174">Proje oluşturulduktan sonra **Yeni proje aç...** düğmesine tıklayın</span><span class="sxs-lookup"><span data-stu-id="7247d-174">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="7247d-175">Uygulamayı çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="7247d-175">Run the application:</span></span>

        - <span data-ttu-id="7247d-176">**Hata Ayıklama** -> **Hata Ayıklamadan Başlat**’a gidin</span><span class="sxs-lookup"><span data-stu-id="7247d-176">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="7247d-177">Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="7247d-177">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="7247d-178">Birden fazla kök klasörü olan çalışma alanları şu anda Visual Studio Code uzantısı tarafından desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="7247d-178">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="7247d-179">Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.</span><span class="sxs-lookup"><span data-stu-id="7247d-179">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="7247d-180">`dotnet` komut satırı aracını kullanarak C# ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="7247d-180">Develop with C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="7247d-181">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="7247d-181">Pre-requisites</span></span>

    - [<span data-ttu-id="7247d-182">.NET Core SDK 2.1 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="7247d-182">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="7247d-183">.NET için Kuantum proje şablonlarını yükleme</span><span class="sxs-lookup"><span data-stu-id="7247d-183">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="7247d-184">Quantum Development Kit yüklenmiştir ve kendi uygulama ve kitaplıklarınızda kullanılmaya hazırdır.</span><span class="sxs-lookup"><span data-stu-id="7247d-184">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="7247d-185">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="7247d-185">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="7247d-186">Yeni uygulama oluşturma</span><span class="sxs-lookup"><span data-stu-id="7247d-186">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="7247d-187">Yeni uygulama dizinine gidin</span><span class="sxs-lookup"><span data-stu-id="7247d-187">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="7247d-188">Uygulamanın proje dosyaları ile birlikte iki dosyanın oluşturulur: bir Q# dosyası (`Operation.qs`) ve bir C# konak dosyası (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="7247d-188">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="7247d-189">Uygulamayı çalıştırma</span><span class="sxs-lookup"><span data-stu-id="7247d-189">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="7247d-190">Şu çıktıyı görmeniz gerekir: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="7247d-190">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="7247d-191">Sırada ne var?</span><span class="sxs-lookup"><span data-stu-id="7247d-191">What's next?</span></span>

<span data-ttu-id="7247d-192">Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.write-program) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7247d-192">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
