---
title: Q# uygulamaları ile geliştirme
description: Komut isteminden çalışan bir Q# uygulaması oluşturmayı öğrenin.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 68f530d80e5c5f40dc2bcbb185879c3cb6f93f91
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834423"
---
# <a name="develop-with-no-locq-applications"></a><span data-ttu-id="282c3-103">Q# uygulamaları ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="282c3-103">Develop with Q# applications</span></span>

<span data-ttu-id="282c3-104">Ortamınıza karşılık gelen sekmedeki yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="282c3-104">Follow the instructions at the tab corresponding to your environment.</span></span>

<span data-ttu-id="282c3-105">Q# programları C#, F# veya Python gibi bir konak dilinde sürücü olmadan kendi başına çalışabilir.</span><span class="sxs-lookup"><span data-stu-id="282c3-105">Q# programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="282c3-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="282c3-106">Prerequisites</span></span>

- [<span data-ttu-id="282c3-107">.NET Core SDK 3.1 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="282c3-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="282c3-108">Yükleme</span><span class="sxs-lookup"><span data-stu-id="282c3-108">Installation</span></span>

<span data-ttu-id="282c3-109">Q# uygulamalarını herhangi bir IDE'de derleyebilseniz de, Q# uygulamalarınızı yerel olarak geliştirmek için Visual Studio Code (VS Code) veya Visual Studio IDE kullanmanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="282c3-109">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="282c3-110">Web tarayıcısı aracılığıyla bulutta geliştirmek için Visual Studio Codespaces’ı öneririz.</span><span class="sxs-lookup"><span data-stu-id="282c3-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="282c3-111">Bu ortamlarda geliştirme yapmak, QDK uzantısının uyarı, söz dizimi vurgulama, proje şablonları gibi zengin işlevlerini içerir.</span><span class="sxs-lookup"><span data-stu-id="282c3-111">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

<span data-ttu-id="282c3-112">VS Code'u yapılandırmak için:</span><span class="sxs-lookup"><span data-stu-id="282c3-112">To configure VS Code:</span></span>

1. <span data-ttu-id="282c3-113">[VS Code](https://code.visualstudio.com/download)’u (Windows, Linux ve Mac) indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="282c3-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="282c3-114">[VS Code için Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)’yi yükleyin.</span><span class="sxs-lookup"><span data-stu-id="282c3-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="282c3-115">Visual Studio'yu yapılandırmak için:</span><span class="sxs-lookup"><span data-stu-id="282c3-115">To configure Visual Studio:</span></span>

1. <span data-ttu-id="282c3-116">.NET Core platformlar arası geliştirme iş yükü etkin olan [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 veya üzerini indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="282c3-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="282c3-117">[Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)’yi indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="282c3-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="282c3-118">Visual Studio Codespaces’ı yapılandırmak için:</span><span class="sxs-lookup"><span data-stu-id="282c3-118">To configure Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="282c3-119">[Azure hesabı](https://azure.microsoft.com/free/) oluşturun.</span><span class="sxs-lookup"><span data-stu-id="282c3-119">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="282c3-120">Codespaces ortamı oluşturun.</span><span class="sxs-lookup"><span data-stu-id="282c3-120">Create a Codespaces environment.</span></span> <span data-ttu-id="282c3-121">Lütfen [hızlı başlangıç kılavuzunu](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser) izleyin.</span><span class="sxs-lookup"><span data-stu-id="282c3-121">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="282c3-122">Kod alanını oluştururken QDK'ye özgü ayarları yüklemek için "Git Deposu" alanına `microsoft/Quantum` girmeniz önerilir.</span><span class="sxs-lookup"><span data-stu-id="282c3-122">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="282c3-123">Artık yeni ortamınızı başlatabilir ve [VS Codespaces Bulut IDE’si](https://online.visualstudio.com/environments) aracılığıyla tarayıcıda geliştirme yapmaya başlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="282c3-123">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="282c3-124">Alternatif olarak, yerel VS Code yüklemenizi kullanmanız ve Codespaces’ı [uzak ortam](https://docs.microsoft.com/visualstudio/online/how-to/vscode) olarak kullanmanız da mümkündür.</span><span class="sxs-lookup"><span data-stu-id="282c3-124">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>


<span data-ttu-id="282c3-125">Başka bir ortam için QDK’yı yüklemek üzere komut istemine şunu girin:</span><span class="sxs-lookup"><span data-stu-id="282c3-125">To install the QDK for another environment, enter the following at the command prompt:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-no-locq"></a><span data-ttu-id="282c3-126">Q# ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="282c3-126">Develop with Q#</span></span>

<span data-ttu-id="282c3-127">Ortamınıza karşılık gelen sekmedeki yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="282c3-127">Follow the instructions on the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="282c3-128">VS Code</span><span class="sxs-lookup"><span data-stu-id="282c3-128">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="282c3-129">Yeni bir proje oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="282c3-129">To create a new project:</span></span>

1. <span data-ttu-id="282c3-130">**Görünüm** -> **Komut Paleti**’ne tıklayın ve **Q#: Yeni Proje Oluştur**’u seçin.</span><span class="sxs-lookup"><span data-stu-id="282c3-130">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="282c3-131">**Bağımsız konsol uygulaması**’na tıklayın.</span><span class="sxs-lookup"><span data-stu-id="282c3-131">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="282c3-132">Projenin kaydedileceği konuma gidin ve **Proje Oluştur**’a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="282c3-132">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="282c3-133">Proje başarıyla oluşturulduğunda, sağ alt kısımdaki **Yeni proje aç...** seçeneğine tıklayın.</span><span class="sxs-lookup"><span data-stu-id="282c3-133">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="282c3-134">Projeyi inceleyin.</span><span class="sxs-lookup"><span data-stu-id="282c3-134">Inspect the project.</span></span> <span data-ttu-id="282c3-135">Konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q# programı olan `Program.qs` adlı kaynak dosyayı görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="282c3-135">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="282c3-136">Uygulamayı çalıştırmak için:</span><span class="sxs-lookup"><span data-stu-id="282c3-136">To run the application:</span></span>

1. <span data-ttu-id="282c3-137">**Terminal** -> **Yeni Terminal**’e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="282c3-137">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="282c3-138">Terminal isteminde `dotnet run` girin.</span><span class="sxs-lookup"><span data-stu-id="282c3-138">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="282c3-139">Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="282c3-139">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="282c3-140">Birden fazla kök klasörü içeren çalışma alanları şu anda VS Code Q# uzantısı tarafından desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="282c3-140">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="282c3-141">Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.</span><span class="sxs-lookup"><span data-stu-id="282c3-141">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="282c3-142">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="282c3-142">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="282c3-143">Bir Q# `Hello World` uygulaması oluşturarak Visual Studio yüklemenizi doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="282c3-143">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="282c3-144">Yeni bir Q# uygulaması oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="282c3-144">To create a new Q# application:</span></span>

1. <span data-ttu-id="282c3-145">Visual Studio’yu açın ve **Dosya** -> **Yeni** -> **Proje**’ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="282c3-145">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="282c3-146">Arama kutusuna `Q#` yazın, **Q# Uygulaması**’nı seçin ve **İleri**’ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="282c3-146">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="282c3-147">Uygulamanız için bir ad ve konum girip **Oluştur**'a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="282c3-147">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="282c3-148">Projeyi inceleyin.</span><span class="sxs-lookup"><span data-stu-id="282c3-148">Inspect the project.</span></span> <span data-ttu-id="282c3-149">Konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q# programı olan `Program.qs` adlı kaynak dosyayı görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="282c3-149">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="282c3-150">Uygulamayı çalıştırmak için:</span><span class="sxs-lookup"><span data-stu-id="282c3-150">To run the application:</span></span>

1. <span data-ttu-id="282c3-151">**Hata Ayıklama** -> **Hata Ayıklamadan Başlat**’ı seçin.</span><span class="sxs-lookup"><span data-stu-id="282c3-151">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="282c3-152">Bir konsol penceresinde yazdırılmış `Hello quantum world!` metni görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="282c3-152">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="282c3-153">Bir Visual Studio çözümünde birden fazla projeniz varsa, çözümde yer alan tüm projelerin çözüm ile aynı klasörde veya bunun alt klasörlerinin birinde olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="282c3-153">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="282c3-154">Komut istemi içeren diğer düzenleyiciler</span><span class="sxs-lookup"><span data-stu-id="282c3-154">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="282c3-155">Bir Q# `Hello World` uygulaması oluşturarak yüklemenizi doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="282c3-155">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="282c3-156">Proje şablonlarını yükleyin.</span><span class="sxs-lookup"><span data-stu-id="282c3-156">Install the project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="282c3-157">Yeni bir uygulama oluşturun:</span><span class="sxs-lookup"><span data-stu-id="282c3-157">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="282c3-158">Uygulama dizinine gidin:</span><span class="sxs-lookup"><span data-stu-id="282c3-158">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="282c3-159">Bu dizin şimdi, konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q# programı olan `Program.qs` adlı dosyayı içermelidir.</span><span class="sxs-lookup"><span data-stu-id="282c3-159">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="282c3-160">Bu şablonda bir metin düzenleyiciyle değişiklik yapabilir ve kendi kuantum uygulamalarınızla bu şablonun üzerine yazabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="282c3-160">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="282c3-161">Programı çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="282c3-161">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="282c3-162">Şu metnin yazdırıldığını görmeniz gerekir: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="282c3-162">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="282c3-163">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="282c3-163">Next steps</span></span>

<span data-ttu-id="282c3-164">Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="282c3-164">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
