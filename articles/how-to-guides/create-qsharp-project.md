---
title: 'Hisse geliştirme seti (QDK) ile bir Q # projesi oluşturma hakkında bilgi edinin'
description: 'Seçtiğiniz geliştirme ortamında QDK ve Q # ile hisse geliştirme için bir proje başlatın'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 8af8e3288aab731520ede984d5f89644de292385
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578220"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="98c59-103">Geliştirme ortamınızda bir Q # projesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="98c59-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="98c59-104">QDK ile bir Q # projesi oluşturmayı öğrenin.</span><span class="sxs-lookup"><span data-stu-id="98c59-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="98c59-105">Bir Q # projesi, hisse cinsi içeren Q # dosyalarını ve hisse programını çalıştırmak için bir ana bilgisayar programını içerir.</span><span class="sxs-lookup"><span data-stu-id="98c59-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="98c59-106">Ana bilgisayar programını C# gibi .NET dillerinde veya Python 'da yazabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="98c59-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="98c59-107">Ayrıca, IQ # çekirdeğini kullanarak Q # kodunu bir Jupyter Notebook de çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="98c59-107">You can also run Q# code in a Jupyter Notebook using the IQ# kernel.</span></span>

<span data-ttu-id="98c59-108">Aşağıdaki bölümlerde geliştirme ortamınızı ve dilinizi seçin:</span><span class="sxs-lookup"><span data-stu-id="98c59-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="98c59-109">Python</span><span class="sxs-lookup"><span data-stu-id="98c59-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="98c59-110">Q# Jupyter Notebook’ları</span><span class="sxs-lookup"><span data-stu-id="98c59-110">Q# Jupyter Notebooks</span></span>](#create-a-q-jupyter-notebook-project)
* [<span data-ttu-id="98c59-111">Visual Studio ile C#</span><span class="sxs-lookup"><span data-stu-id="98c59-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="98c59-112">VS Code C#</span><span class="sxs-lookup"><span data-stu-id="98c59-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="98c59-113">Komut satırı ile C#</span><span class="sxs-lookup"><span data-stu-id="98c59-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="98c59-114">Python projesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="98c59-114">Create a Python project</span></span>

1. <span data-ttu-id="98c59-115">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="98c59-115">Pre-requisites</span></span>

     * <span data-ttu-id="98c59-116">[Python Için hisse geliştirme seti 'ni](xref:microsoft.quantum.install.python) yükler</span><span class="sxs-lookup"><span data-stu-id="98c59-116">Install the [Quantum Development Kit for Python](xref:microsoft.quantum.install.python)</span></span>

1. <span data-ttu-id="98c59-117">Projeniz için bir klasör oluşturun ve bu klasöre gidin</span><span class="sxs-lookup"><span data-stu-id="98c59-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="98c59-118">Adlı bir Q # dosyası oluşturun `Operation.qs` ve buna q # kodunuzu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="98c59-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="98c59-119">Örnek:</span><span class="sxs-lookup"><span data-stu-id="98c59-119">For example:</span></span>

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. <span data-ttu-id="98c59-120">Q # işleminizi çağırmak için çağrılan bir Python ana bilgisayar dosyası oluşturun `host.py` .</span><span class="sxs-lookup"><span data-stu-id="98c59-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="98c59-121">Örnek:</span><span class="sxs-lookup"><span data-stu-id="98c59-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="98c59-122">Programı çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="98c59-122">Run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="98c59-123">Çıktıyı doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="98c59-123">Verify the output.</span></span> <span data-ttu-id="98c59-124">Programınız aşağıdaki satırları çıkarmalıdır:</span><span class="sxs-lookup"><span data-stu-id="98c59-124">Your program should output the following lines:</span></span>

    ```
    Hello from quantum world!
    0
    ```

<span data-ttu-id="98c59-125">Artık hisse programınızı geliştirmeye devam edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="98c59-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-q-jupyter-notebook-project"></a><span data-ttu-id="98c59-126">Bir Q # Jupyter Notebook projesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="98c59-126">Create a Q# Jupyter Notebook project</span></span>

1. <span data-ttu-id="98c59-127">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="98c59-127">Pre-requisites</span></span>

    * <span data-ttu-id="98c59-128">[Jupyıter Not defterleri Için hisse geliştirme setini](xref:microsoft.quantum.install.jupyter) yükler</span><span class="sxs-lookup"><span data-stu-id="98c59-128">Install the [Quantum Development Kit for Jupyter Notebooks](xref:microsoft.quantum.install.jupyter)</span></span>

1. <span data-ttu-id="98c59-129">Not defteri sunucusunu başlatmak için aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="98c59-129">Run the following command to start the notebook server:</span></span>

    ```
    jupyter notebook
    ```

1. <span data-ttu-id="98c59-130">Komut satırında gösterilen URL'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="98c59-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="98c59-131">Örneğin: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span><span class="sxs-lookup"><span data-stu-id="98c59-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="98c59-132">Tarayıcıda bir Jupyıter sayfası görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="98c59-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="98c59-133">**Dosyalar** sekmesinde, bir **New**  >  q # çekirdeğiyle Jupyter Notebook oluşturmak için yeni**Q #** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="98c59-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter Notebook with a Q# kernel.</span></span> <span data-ttu-id="98c59-134">İlk not defteri hücresine aşağıdaki kodu ekleyin:</span><span class="sxs-lookup"><span data-stu-id="98c59-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="98c59-135">**Cell**  >  Not defterini çalıştırmak için hücre**çalıştırma hücrelerini** seçin.</span><span class="sxs-lookup"><span data-stu-id="98c59-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="98c59-136">`SayHello`kısa süre önce hücre çıktısında görünür:</span><span class="sxs-lookup"><span data-stu-id="98c59-136">`SayHello` will soon appear in the cell output:</span></span>

    ![Q # kodlu Jupyter Notebook hücresi](~/media/install-guide-jupyter.png)

    <span data-ttu-id="98c59-138">Jupyter not defterlerinde çalışırken, Q # kodu derlenir ve Not defteri bulduğu işlem (ler) in adını verir.</span><span class="sxs-lookup"><span data-stu-id="98c59-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="98c59-139">Yeni bir hücrede `%simulate` magic kullanarak yeni oluşturduğunuz işlemin kuantum bilgisayarda yürütmesinin benzetimini yapın:</span><span class="sxs-lookup"><span data-stu-id="98c59-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![% Benzetim Magic ile Jupyter Notebook hücresi](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="98c59-141">Ekrana yazdırılmış bir iletiyle birlikte çağırdığınız işlemin sonucuna da (bu örnekte boş) görüyor olmalısınız.</span><span class="sxs-lookup"><span data-stu-id="98c59-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="98c59-142">Artık, hisse geliştirme işlemlerinizi sürdürmek için diğer Q # işlemleri ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="98c59-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="98c59-143">Visual Studio 'Yu kullanarak Windows üzerinde C# projesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="98c59-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="98c59-144">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="98c59-144">Pre-requisites</span></span>

    * <span data-ttu-id="98c59-145">[Visual Studio Için hisse geliştirme seti uzantısını](xref:microsoft.quantum.install.cs) yükler</span><span class="sxs-lookup"><span data-stu-id="98c59-145">Install the [Quantum Development Kit extension for Visual Studio](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="98c59-146">Yeni bir Q# uygulaması oluşturun</span><span class="sxs-lookup"><span data-stu-id="98c59-146">Create a new Q# application</span></span>

    * <span data-ttu-id="98c59-147">**Dosya**  ->  **Yeni**  ->  **Proje** 'ye git</span><span class="sxs-lookup"><span data-stu-id="98c59-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="98c59-148">Arama kutusuna `Q#` yazın</span><span class="sxs-lookup"><span data-stu-id="98c59-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="98c59-149">**Q# Uygulaması**’nı seçin</span><span class="sxs-lookup"><span data-stu-id="98c59-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="98c59-150">**İleri** Seç</span><span class="sxs-lookup"><span data-stu-id="98c59-150">Select **Next**</span></span>
    * <span data-ttu-id="98c59-151">Uygulamanız için bir ad ve konum seçin</span><span class="sxs-lookup"><span data-stu-id="98c59-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="98c59-152">**Oluştur** ' u seçin</span><span class="sxs-lookup"><span data-stu-id="98c59-152">Select **Create**</span></span>

1. <span data-ttu-id="98c59-153">Projeyi inceleyin</span><span class="sxs-lookup"><span data-stu-id="98c59-153">Inspect the project</span></span>

    <span data-ttu-id="98c59-154">İki dosya oluşturulur: C# konak uygulaması olan `Driver.cs` ve konsola bir ileti yazdıran basit işlemi tanımlayan Q# programı `Operation.qs`.</span><span class="sxs-lookup"><span data-stu-id="98c59-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="98c59-155">Uygulamayı çalıştırma</span><span class="sxs-lookup"><span data-stu-id="98c59-155">Run the application</span></span>

    * <span data-ttu-id="98c59-156">Hata **ayıklama**  ->  **olmadan Başlat** ' ı seçin</span><span class="sxs-lookup"><span data-stu-id="98c59-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="98c59-157">Bir konsol penceresinde yazdırılmış `Hello quantum world!` metni görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="98c59-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="98c59-158">Artık Visual Studio 'Yu kullanarak hisse geliştirmeye devam edebilirsiniz</span><span class="sxs-lookup"><span data-stu-id="98c59-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="98c59-159">Bir Visual Studio çözümünde birden fazla projeniz varsa, çözümde yer alan tüm projelerin çözüm ile aynı klasörde veya bunun bir alt klasöründe olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="98c59-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="98c59-160">VS Code kullanarak bir C# projesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="98c59-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="98c59-161">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="98c59-161">Pre-requisites</span></span>

    * <span data-ttu-id="98c59-162">[Vs Code Için hisse geliştirme seti uzantısını](xref:microsoft.quantum.install.cs) yükler</span><span class="sxs-lookup"><span data-stu-id="98c59-162">Install the [Quantum Development Kit extension for VS Code](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="98c59-163">Yeni bir proje oluşturun:</span><span class="sxs-lookup"><span data-stu-id="98c59-163">Create a new project:</span></span>

    * <span data-ttu-id="98c59-164">**Görünüm**  ->  **komut paleti** 'ne git</span><span class="sxs-lookup"><span data-stu-id="98c59-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="98c59-165">**Q #: yeni proje oluştur** ' u seçin</span><span class="sxs-lookup"><span data-stu-id="98c59-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="98c59-166">**Tek başına konsol uygulamasını** seçin</span><span class="sxs-lookup"><span data-stu-id="98c59-166">Select **Standalone console application**</span></span>
    * <span data-ttu-id="98c59-167">Dosya sisteminde uygulamayı oluşturmak istediğiniz konuma gidin</span><span class="sxs-lookup"><span data-stu-id="98c59-167">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="98c59-168">Proje oluşturulduktan sonra **Yeni proje aç...** düğmesine tıklayın</span><span class="sxs-lookup"><span data-stu-id="98c59-168">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="98c59-169">Uygulamayı çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="98c59-169">Run the application:</span></span>

    * <span data-ttu-id="98c59-170">**Terminal**  ->  **yeni Terminal** 'e git</span><span class="sxs-lookup"><span data-stu-id="98c59-170">Go to **Terminal** -> **New Terminal**</span></span>
    * <span data-ttu-id="98c59-171">Girmesini`dotnet run`</span><span class="sxs-lookup"><span data-stu-id="98c59-171">Enter `dotnet run`</span></span>
    * <span data-ttu-id="98c59-172">Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="98c59-172">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="98c59-173">Artık Visual Studio Code kullanarak hisse geliştirmeye devam edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="98c59-173">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="98c59-174">Birden fazla kök klasörü olan çalışma alanları şu anda Visual Studio Code uzantısı tarafından desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="98c59-174">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="98c59-175">Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.</span><span class="sxs-lookup"><span data-stu-id="98c59-175">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="98c59-176">Komut satırı aracını kullanarak bir C# projesi oluşturma `dotnet`</span><span class="sxs-lookup"><span data-stu-id="98c59-176">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="98c59-177">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="98c59-177">Pre-requisites</span></span>

    * <span data-ttu-id="98c59-178">[Komut satırı Için hisse geliştirme setini](xref:microsoft.quantum.install.standalone) yükler</span><span class="sxs-lookup"><span data-stu-id="98c59-178">Install the [Quantum Development Kit for the command line](xref:microsoft.quantum.install.standalone)</span></span>

1. <span data-ttu-id="98c59-179">Yeni uygulama oluşturma</span><span class="sxs-lookup"><span data-stu-id="98c59-179">Create a new application</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="98c59-180">Yeni uygulama dizinine gidin</span><span class="sxs-lookup"><span data-stu-id="98c59-180">Navigate to the new application directory</span></span>

    ```
    cd <project name>
    ```

    <span data-ttu-id="98c59-181">Uygulamanın proje dosyaları ile birlikte iki dosyanın oluşturulur: bir Q# dosyası (`Operation.qs`) ve bir C# konak dosyası (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="98c59-181">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="98c59-182">Uygulamayı çalıştırma</span><span class="sxs-lookup"><span data-stu-id="98c59-182">Run the application</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="98c59-183">Şu çıktıyı görmeniz gerekir: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="98c59-183">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="98c59-184">Artık, komut satırı araçlarını kullanarak hisse geliştirmeye devam edersiniz.</span><span class="sxs-lookup"><span data-stu-id="98c59-184">You now continue your quantum development, using command line tools.</span></span>

## <a name="next-steps"></a><span data-ttu-id="98c59-185">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="98c59-185">Next steps</span></span>

<span data-ttu-id="98c59-186">Tercih ettiğiniz ortamda bir proje oluşturduğunuza göre, artık hisse geliştirme ortamınıza devam edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="98c59-186">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>
