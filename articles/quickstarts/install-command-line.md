---
title: 'Bir IDE içinde :::no-loc(Q#)::: uygulamaları ile geliştirme'
description: 'Komut isteminden çalışan bir :::no-loc(Q#)::: uygulaması oluşturmayı öğrenin.'
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: a6823888dcbe8cf79f0045d2615fe8b889dcc7c3
ms.sourcegitcommit: a13c7c86fd52a05cbf129b8dd713d6586ca1cc2c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2020
ms.locfileid: "93376431"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a><span data-ttu-id="db78a-103">Bir IDE içinde :::no-loc(Q#)::: uygulamaları ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="db78a-103">Develop with :::no-loc(Q#)::: applications in an IDE</span></span>

<span data-ttu-id="db78a-104">:::no-loc(Q#)::: programları C#, F# veya Python gibi bir konak dilinde sürücü olmadan kendi başına çalışabilir.</span><span class="sxs-lookup"><span data-stu-id="db78a-104">:::no-loc(Q#)::: programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span> <span data-ttu-id="db78a-105">Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces veya herhangi bir düzenleyici/IDE ile :::no-loc(Q#)::: uygulamaları geliştirebilir ve uygulamaları .NET konsolundan çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="db78a-105">You can develop :::no-loc(Q#)::: applications in Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces, or with any editor/IDE and run applications from the .NET console.</span></span> 

## <a name="prerequisites-for-all-environments"></a><span data-ttu-id="db78a-106">Tüm ortamlar için önkoşullar</span><span class="sxs-lookup"><span data-stu-id="db78a-106">Prerequisites for all environments</span></span>

- [<span data-ttu-id="db78a-107">.NET Core SDK 3.1 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="db78a-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="db78a-108">Yükleme</span><span class="sxs-lookup"><span data-stu-id="db78a-108">Installation</span></span>

<span data-ttu-id="db78a-109">:::no-loc(Q#)::: uygulamalarını herhangi bir IDE'de derleyebilseniz de, :::no-loc(Q#)::: uygulamalarınızı yerel olarak geliştirmek için Visual Studio Code (VS Code) veya Visual Studio IDE kullanmanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="db78a-109">While you can build :::no-loc(Q#)::: applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your :::no-loc(Q#)::: applications locally.</span></span> <span data-ttu-id="db78a-110">Web tarayıcısı aracılığıyla bulutta geliştirmek için Visual Studio Codespaces’ı öneririz.</span><span class="sxs-lookup"><span data-stu-id="db78a-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="db78a-111">Bu ortamlarda geliştirme yapılırken QDK uzantısının uyarı, söz dizimi vurgulama, proje şablonları gibi zengin işlevlerinden yararlanılır.</span><span class="sxs-lookup"><span data-stu-id="db78a-111">Developing in these environments leverages the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

### <a name="to-configure-for-vs-code"></a><span data-ttu-id="db78a-112">VS Code için yapılandırmak üzere:</span><span class="sxs-lookup"><span data-stu-id="db78a-112">To configure for VS Code:</span></span>

1. <span data-ttu-id="db78a-113">[VS Code](https://code.visualstudio.com/download)’u (Windows, Linux ve Mac) indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="db78a-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="db78a-114">[VS Code için Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)’yi yükleyin.</span><span class="sxs-lookup"><span data-stu-id="db78a-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

### <a name="to-configure-for-visual-studio"></a><span data-ttu-id="db78a-115">Visual Studio için yapılandırmak üzere:</span><span class="sxs-lookup"><span data-stu-id="db78a-115">To configure for Visual Studio:</span></span>

1. <span data-ttu-id="db78a-116">.NET Core platformlar arası geliştirme iş yükü etkin olan [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 veya üzerini indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="db78a-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="db78a-117">[Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)’yi indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="db78a-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

### <a name="to-configure-for-another-environment"></a><span data-ttu-id="db78a-118">Başka bir ortam için yapılandırmak üzere:</span><span class="sxs-lookup"><span data-stu-id="db78a-118">To configure for another environment:</span></span> 

1. <span data-ttu-id="db78a-119">Komut isteminde aşağıdakini girin</span><span class="sxs-lookup"><span data-stu-id="db78a-119">Enter the following at the command prompt</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a><span data-ttu-id="db78a-120">Visual Studio Codespaces için yapılandırmak üzere:</span><span class="sxs-lookup"><span data-stu-id="db78a-120">To configure for Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="db78a-121">[Azure hesabı](https://azure.microsoft.com/free/) oluşturun.</span><span class="sxs-lookup"><span data-stu-id="db78a-121">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="db78a-122">Codespaces ortamı oluşturun.</span><span class="sxs-lookup"><span data-stu-id="db78a-122">Create a Codespaces environment.</span></span> <span data-ttu-id="db78a-123">Lütfen [hızlı başlangıç kılavuzunu](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser) izleyin.</span><span class="sxs-lookup"><span data-stu-id="db78a-123">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="db78a-124">Kod alanını oluştururken QDK'ye özgü ayarları yüklemek için "Git Deposu" alanına `microsoft/Quantum` girmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="db78a-124">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="db78a-125">Artık yeni ortamınızı başlatabilir ve [VS Codespaces Bulut IDE’si](https://online.visualstudio.com/environments) aracılığıyla tarayıcıda geliştirme yapmaya başlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="db78a-125">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="db78a-126">Alternatif olarak, yerel VS Code yüklemenizi kullanmanız ve Codespaces’ı [uzak ortam](https://docs.microsoft.com/visualstudio/online/how-to/vscode) olarak kullanmanız da mümkündür.</span><span class="sxs-lookup"><span data-stu-id="db78a-126">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>

## <a name="develop-with-no-locq"></a><span data-ttu-id="db78a-127">:::no-loc(Q#)::: ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="db78a-127">Develop with :::no-loc(Q#):::</span></span>

<span data-ttu-id="db78a-128">Geliştirme ortamınıza karşılık gelen sekmedeki yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="db78a-128">Follow the instructions on the tab corresponding to your development environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="db78a-129">VS Code</span><span class="sxs-lookup"><span data-stu-id="db78a-129">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="db78a-130">Yeni bir proje oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="db78a-130">To create a new project:</span></span>

1. <span data-ttu-id="db78a-131">**Görünüm** -> **Komut Paleti** ’ne tıklayın ve **:::no-loc(Q#):::: Yeni Proje Oluştur** ’u seçin.</span><span class="sxs-lookup"><span data-stu-id="db78a-131">Click **View** -> **Command Palette** and select **:::no-loc(Q#):::: Create New Project**.</span></span>
2. <span data-ttu-id="db78a-132">**Bağımsız konsol uygulaması** ’na tıklayın.</span><span class="sxs-lookup"><span data-stu-id="db78a-132">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="db78a-133">Projenin kaydedileceği konuma gidin ve **Proje Oluştur** ’a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="db78a-133">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="db78a-134">Proje başarıyla oluşturulduğunda, sağ alt kısımdaki **Yeni proje aç...** seçeneğine tıklayın.</span><span class="sxs-lookup"><span data-stu-id="db78a-134">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="db78a-135">Projeyi inceleyin.</span><span class="sxs-lookup"><span data-stu-id="db78a-135">Inspect the project.</span></span> <span data-ttu-id="db78a-136">Konsola ileti yazdırmak için basit bir işlem tanımlayan bir :::no-loc(Q#)::: programı olan `Program.qs` adlı kaynak dosyayı görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="db78a-136">You should see a source file named `Program.qs`, which is a :::no-loc(Q#)::: program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="db78a-137">Uygulamayı çalıştırmak için:</span><span class="sxs-lookup"><span data-stu-id="db78a-137">To run the application:</span></span>

1. <span data-ttu-id="db78a-138">**Terminal** -> **Yeni Terminal** ’e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="db78a-138">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="db78a-139">Terminal isteminde `dotnet run` girin.</span><span class="sxs-lookup"><span data-stu-id="db78a-139">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="db78a-140">Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="db78a-140">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="db78a-141">Birden fazla kök klasörü içeren çalışma alanları şu anda VS Code :::no-loc(Q#)::: uzantısı tarafından desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="db78a-141">Workspaces with multiple root folders are not currently supported by the VS Code :::no-loc(Q#)::: extension.</span></span> <span data-ttu-id="db78a-142">Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.</span><span class="sxs-lookup"><span data-stu-id="db78a-142">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="db78a-143">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="db78a-143">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="db78a-144">Bir :::no-loc(Q#)::: `Hello World` uygulaması oluşturarak Visual Studio yüklemenizi doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="db78a-144">Verify your Visual Studio installation by creating a :::no-loc(Q#)::: `Hello World` application.</span></span>

<span data-ttu-id="db78a-145">Yeni bir :::no-loc(Q#)::: uygulaması oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="db78a-145">To create a new :::no-loc(Q#)::: application:</span></span>

1. <span data-ttu-id="db78a-146">Visual Studio’yu açın ve **Dosya** -> **Yeni** -> **Proje** ’ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="db78a-146">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="db78a-147">Arama kutusuna `:::no-loc(Q#):::` yazın, **:::no-loc(Q#)::: Uygulaması** ’nı seçin ve **İleri** ’ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="db78a-147">Type `:::no-loc(Q#):::` in the search box, select **:::no-loc(Q#)::: Application** and click **Next**.</span></span>
3. <span data-ttu-id="db78a-148">Uygulamanız için bir ad ve konum girip **Oluştur** 'a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="db78a-148">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="db78a-149">Projeyi inceleyin.</span><span class="sxs-lookup"><span data-stu-id="db78a-149">Inspect the project.</span></span> <span data-ttu-id="db78a-150">Konsola ileti yazdırmak için basit bir işlem tanımlayan bir :::no-loc(Q#)::: programı olan `Program.qs` adlı kaynak dosyayı görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="db78a-150">You should see a source file named `Program.qs`, which is a :::no-loc(Q#)::: program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="db78a-151">Uygulamayı çalıştırmak için:</span><span class="sxs-lookup"><span data-stu-id="db78a-151">To run the application:</span></span>

1. <span data-ttu-id="db78a-152">**Hata Ayıklama** -> **Hata Ayıklamadan Başlat** ’ı seçin.</span><span class="sxs-lookup"><span data-stu-id="db78a-152">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="db78a-153">Bir konsol penceresinde yazdırılmış `Hello quantum world!` metni görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="db78a-153">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="db78a-154">Bir Visual Studio çözümünde birden fazla projeniz varsa, çözümde yer alan tüm projelerin çözüm ile aynı klasörde veya bunun alt klasörlerinin birinde olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="db78a-154">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="db78a-155">Komut istemi içeren diğer düzenleyiciler</span><span class="sxs-lookup"><span data-stu-id="db78a-155">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="db78a-156">Bir :::no-loc(Q#)::: `Hello World` uygulaması oluşturarak yüklemenizi doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="db78a-156">Verify your installation by creating a :::no-loc(Q#)::: `Hello World` application.</span></span>

1. <span data-ttu-id="db78a-157">Yeni bir uygulama oluşturun:</span><span class="sxs-lookup"><span data-stu-id="db78a-157">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang :::no-loc(Q#)::: -o runSayHello
    ```

1. <span data-ttu-id="db78a-158">Uygulama dizinine gidin:</span><span class="sxs-lookup"><span data-stu-id="db78a-158">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="db78a-159">Bu dizin şimdi, konsola ileti yazdırmak için basit bir işlem tanımlayan bir :::no-loc(Q#)::: programı olan `Program.qs` adlı dosyayı içermelidir.</span><span class="sxs-lookup"><span data-stu-id="db78a-159">This directory should now contain a file `Program.qs`, which is a :::no-loc(Q#)::: program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="db78a-160">Bu şablonda bir metin düzenleyiciyle değişiklik yapabilir ve kendi kuantum uygulamalarınızla bu şablonun üzerine yazabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="db78a-160">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="db78a-161">Programı çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="db78a-161">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="db78a-162">Şu metnin yazdırıldığını görmeniz gerekir: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="db78a-162">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="db78a-163">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="db78a-163">Next steps</span></span>

<span data-ttu-id="db78a-164">Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="db78a-164">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
