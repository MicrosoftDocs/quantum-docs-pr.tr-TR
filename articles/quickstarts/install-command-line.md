---
title: Q# komut satırı uygulamaları ile geliştirme
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 3d70838289e72afdd0a48bbdff0bec407428d125
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871442"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="ed20c-102">Q# komut satırı uygulamaları ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="ed20c-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="ed20c-103">Q# programları, C#, F# veya Python gibi bir konak dilinde sürücü olmadan kendi başına çalıştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="ed20c-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ed20c-104">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="ed20c-104">Prerequisites</span></span>

- [<span data-ttu-id="ed20c-105">.NET Core SDK 3.1 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="ed20c-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="ed20c-106">Yükleme</span><span class="sxs-lookup"><span data-stu-id="ed20c-106">Installation</span></span>

<span data-ttu-id="ed20c-107">Q# komut satırı uygulamalarını herhangi bir IDE'de derleyebilseniz de, Q# uygulamalarınızı yerel olarak geliştirmek için Visual Studio Code (VS Code) veya Visual Studio IDE kullanmanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="ed20c-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="ed20c-108">Web tarayıcısı aracılığıyla bulutta geliştirmek için Visual Studio Codespaces’ı öneririz.</span><span class="sxs-lookup"><span data-stu-id="ed20c-108">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="ed20c-109">Bu ortamlarda geliştirme yapmak, QDK uzantısının uyarı, söz dizimi vurgulama, proje şablonları gibi zengin işlevlerini içerir.</span><span class="sxs-lookup"><span data-stu-id="ed20c-109">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

<span data-ttu-id="ed20c-110">VS Code'u yapılandırmak için:</span><span class="sxs-lookup"><span data-stu-id="ed20c-110">To configure VS Code:</span></span>

1. <span data-ttu-id="ed20c-111">[VS Code](https://code.visualstudio.com/download)’u (Windows, Linux ve Mac) indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="ed20c-111">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="ed20c-112">[VS Code için Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)’yi yükleyin.</span><span class="sxs-lookup"><span data-stu-id="ed20c-112">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="ed20c-113">Visual Studio'yu yapılandırmak için:</span><span class="sxs-lookup"><span data-stu-id="ed20c-113">To configure Visual Studio:</span></span>

1. <span data-ttu-id="ed20c-114">.NET Core platformlar arası geliştirme iş yükü etkin olan [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 veya üzerini indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="ed20c-114">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="ed20c-115">[Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)’yi indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="ed20c-115">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="ed20c-116">Visual Studio Codespaces’ı yapılandırmak için:</span><span class="sxs-lookup"><span data-stu-id="ed20c-116">To configure Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="ed20c-117">[Azure hesabı](https://azure.microsoft.com/free/) oluşturun.</span><span class="sxs-lookup"><span data-stu-id="ed20c-117">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="ed20c-118">Codespaces ortamı oluşturun.</span><span class="sxs-lookup"><span data-stu-id="ed20c-118">Create a Codespaces environment.</span></span> <span data-ttu-id="ed20c-119">Lütfen [hızlı başlangıç kılavuzunu](https://docs.microsoft.com/visualstudio/online/quickstarts/browser) izleyin.</span><span class="sxs-lookup"><span data-stu-id="ed20c-119">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/online/quickstarts/browser).</span></span> <span data-ttu-id="ed20c-120">Kod alanını oluştururken QDK'ye özgü ayarları yüklemek için "Git Deposu" alanına `microsoft/Quantum` girmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="ed20c-120">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="ed20c-121">Artık yeni ortamınızı başlatabilir ve [VS Codespaces Bulut IDE’si](https://online.visualstudio.com/environments) aracılığıyla tarayıcıda geliştirme yapmaya başlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ed20c-121">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="ed20c-122">Alternatif olarak, yerel VS Code yüklemenizi kullanmanız ve Codespaces’ı [uzak ortam](https://docs.microsoft.com/visualstudio/online/how-to/vscode) olarak kullanmanız da mümkündür.</span><span class="sxs-lookup"><span data-stu-id="ed20c-122">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>


<span data-ttu-id="ed20c-123">Başka bir ortam için QDK'yi yüklemek üzere komut satırına şunu girin:</span><span class="sxs-lookup"><span data-stu-id="ed20c-123">To install the QDK for another environment, enter in the command line:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a><span data-ttu-id="ed20c-124">Q# ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="ed20c-124">Develop with Q#</span></span>

<span data-ttu-id="ed20c-125">Ortamınıza karşılık gelen sekmedeki yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="ed20c-125">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="ed20c-126">VS Code</span><span class="sxs-lookup"><span data-stu-id="ed20c-126">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="ed20c-127">Yeni bir proje oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="ed20c-127">To create a new project:</span></span>

1. <span data-ttu-id="ed20c-128">**Görünüm** -> **Komut Paleti**’ne tıklayın ve **Q#: Yeni Proje Oluştur**’u seçin.</span><span class="sxs-lookup"><span data-stu-id="ed20c-128">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="ed20c-129">**Bağımsız konsol uygulaması**’na tıklayın.</span><span class="sxs-lookup"><span data-stu-id="ed20c-129">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="ed20c-130">Projenin kaydedileceği konuma gidin ve **Proje Oluştur**’a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="ed20c-130">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="ed20c-131">Proje başarıyla oluşturulduğunda, sağ alt kısımdaki **Yeni proje aç...** seçeneğine tıklayın.</span><span class="sxs-lookup"><span data-stu-id="ed20c-131">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="ed20c-132">Projeyi inceleyin.</span><span class="sxs-lookup"><span data-stu-id="ed20c-132">Inspect the project.</span></span> <span data-ttu-id="ed20c-133">Konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q# programı olan `Program.qs` adlı kaynak dosyayı görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="ed20c-133">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="ed20c-134">Uygulamayı çalıştırmak için:</span><span class="sxs-lookup"><span data-stu-id="ed20c-134">To run the application:</span></span>
1. <span data-ttu-id="ed20c-135">**Terminal** -> **Yeni Terminal**’e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="ed20c-135">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="ed20c-136">Terminal isteminde `dotnet run` girin.</span><span class="sxs-lookup"><span data-stu-id="ed20c-136">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="ed20c-137">Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="ed20c-137">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="ed20c-138">Birden fazla kök klasörü olan çalışma alanları şu anda VS Code Q# uzantısı tarafından desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="ed20c-138">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="ed20c-139">Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.</span><span class="sxs-lookup"><span data-stu-id="ed20c-139">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="ed20c-140">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ed20c-140">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="ed20c-141">Bir Q# `Hello World` uygulaması oluşturarak Visual Studio yüklemenizi doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="ed20c-141">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="ed20c-142">Yeni bir Q# uygulaması oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="ed20c-142">To create a new Q# application:</span></span>
1. <span data-ttu-id="ed20c-143">Visual Studio’yu açın ve **Dosya** -> **Yeni** -> **Proje**’ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="ed20c-143">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="ed20c-144">Arama kutusuna `Q#` yazın, **Q# Uygulaması**’nı seçin ve **İleri**’ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="ed20c-144">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="ed20c-145">Uygulamanız için bir ad ve konum girip **Oluştur**'a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="ed20c-145">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="ed20c-146">Projeyi inceleyin.</span><span class="sxs-lookup"><span data-stu-id="ed20c-146">Inspect the project.</span></span> <span data-ttu-id="ed20c-147">Konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q# programı olan `Program.qs` adlı kaynak dosyayı görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="ed20c-147">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="ed20c-148">Uygulamayı çalıştırmak için:</span><span class="sxs-lookup"><span data-stu-id="ed20c-148">To run the application:</span></span>
1. <span data-ttu-id="ed20c-149">**Hata Ayıklama** -> **Hata Ayıklamadan Başlat**’ı seçin.</span><span class="sxs-lookup"><span data-stu-id="ed20c-149">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="ed20c-150">Bir konsol penceresinde yazdırılmış `Hello quantum world!` metni görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="ed20c-150">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="ed20c-151">Bir Visual Studio çözümünde birden fazla projeniz varsa, çözümde yer alan tüm projelerin çözüm ile aynı klasörde veya bunun alt klasörlerinin birinde olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="ed20c-151">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-line"></a>[<span data-ttu-id="ed20c-152">Komut satırı içeren diğer düzenleyiciler</span><span class="sxs-lookup"><span data-stu-id="ed20c-152">Other editors with the command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="ed20c-153">Bir Q# `Hello World` uygulaması oluşturarak yüklemenizi doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="ed20c-153">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="ed20c-154">Proje şablonlarını yükleyin.</span><span class="sxs-lookup"><span data-stu-id="ed20c-154">Install the project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="ed20c-155">Yeni bir uygulama oluşturun:</span><span class="sxs-lookup"><span data-stu-id="ed20c-155">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="ed20c-156">Uygulama dizinine gidin:</span><span class="sxs-lookup"><span data-stu-id="ed20c-156">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="ed20c-157">Bu dizin artık, konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q# programı olan `Program.qs` adlı dosyayı içermelidir.</span><span class="sxs-lookup"><span data-stu-id="ed20c-157">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="ed20c-158">Bu şablonda bir metin düzenleyiciyle değişiklik yapabilir ve kendi kuantum uygulamalarınızla bu şablonun üzerine yazabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ed20c-158">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="ed20c-159">Programı çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="ed20c-159">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="ed20c-160">Şu metnin yazdırıldığını görmeniz gerekir: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="ed20c-160">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="ed20c-161">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="ed20c-161">Next steps</span></span>

<span data-ttu-id="ed20c-162">Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ed20c-162">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
