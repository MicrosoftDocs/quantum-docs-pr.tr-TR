---
title: Q# komut satırı uygulamaları ile geliştirme
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 15015d1673f47faf5a13dde516f834916b4319d6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884277"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="b631b-102">Q# komut satırı uygulamaları ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="b631b-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="b631b-103">Q# programları, C#, F# veya Python gibi bir konak dilinde sürücü olmadan kendi başına çalıştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="b631b-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b631b-104">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="b631b-104">Prerequisites</span></span>

- [<span data-ttu-id="b631b-105">.NET Core SDK 3.1 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="b631b-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="b631b-106">Yükleme</span><span class="sxs-lookup"><span data-stu-id="b631b-106">Installation</span></span>

<span data-ttu-id="b631b-107">Q# komut satırı uygulamalarını herhangi bir IDE'de derleyebilseniz de, Q# uygulamalarınız için Visual Studio Code (VS Code) veya Visual Studio IDE kullanmanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="b631b-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="b631b-108">Bu ortamlarda geliştirme yapmak, QDK uzantısının uyarı, söz dizimi vurgulama, proje şablonları gibi zengin işlevlerini içerir.</span><span class="sxs-lookup"><span data-stu-id="b631b-108">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="b631b-109">VS Code'u yapılandırmak için:</span><span class="sxs-lookup"><span data-stu-id="b631b-109">To configure VS Code:</span></span>

1. <span data-ttu-id="b631b-110">[VS Code](https://code.visualstudio.com/download)’u (Windows, Linux ve Mac) indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="b631b-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="b631b-111">[VS Code için Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)’yi yükleyin.</span><span class="sxs-lookup"><span data-stu-id="b631b-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="b631b-112">Visual Studio'yu yapılandırmak için:</span><span class="sxs-lookup"><span data-stu-id="b631b-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="b631b-113">.NET Core platformlar arası geliştirme iş yükü etkin olan [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 veya üzerini indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="b631b-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="b631b-114">[Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)’yi indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="b631b-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="b631b-115">Başka bir ortam için QDK'yi yüklemek üzere komut satırına şunu girin:</span><span class="sxs-lookup"><span data-stu-id="b631b-115">To install the QDK for another environment, enter in the command line:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a><span data-ttu-id="b631b-116">Q# ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="b631b-116">Develop with Q#</span></span>

<span data-ttu-id="b631b-117">Ortamınıza karşılık gelen sekmedeki yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="b631b-117">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="b631b-118">VS Code</span><span class="sxs-lookup"><span data-stu-id="b631b-118">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="b631b-119">Q# proje şablonlarını yükleyin:</span><span class="sxs-lookup"><span data-stu-id="b631b-119">Install the Q# project templates:</span></span>

1. <span data-ttu-id="b631b-120">VS Code’u açın.</span><span class="sxs-lookup"><span data-stu-id="b631b-120">Open VS Code.</span></span>
2. <span data-ttu-id="b631b-121">**Görünüm** -> **Komut Paleti**’ne tıklayın.</span><span class="sxs-lookup"><span data-stu-id="b631b-121">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="b631b-122">**Q#: Proje şablonlarını yükleyin**.</span><span class="sxs-lookup"><span data-stu-id="b631b-122">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="b631b-123">**Proje şablonları başarıyla yüklendi** iletisi görüntülendiğinde, QDK kendi uygulama ve kitaplıklarınızla birlikte kullanıma hazırdır.</span><span class="sxs-lookup"><span data-stu-id="b631b-123">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="b631b-124">Yeni bir proje oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="b631b-124">To create a new project:</span></span>

1. <span data-ttu-id="b631b-125">**Görünüm** -> **Komut Paleti**’ne tıklayın ve **Q#: Yeni Proje Oluştur**’u seçin.</span><span class="sxs-lookup"><span data-stu-id="b631b-125">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="b631b-126">**Bağımsız konsol uygulaması**’na tıklayın.</span><span class="sxs-lookup"><span data-stu-id="b631b-126">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="b631b-127">Projenin kaydedileceği konuma gidin ve **Proje Oluştur**’a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="b631b-127">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="b631b-128">Proje başarıyla oluşturulduğunda, sağ alt kısımdaki **Yeni proje aç...** seçeneğine tıklayın.</span><span class="sxs-lookup"><span data-stu-id="b631b-128">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="b631b-129">Projeyi inceleyin.</span><span class="sxs-lookup"><span data-stu-id="b631b-129">Inspect the project.</span></span> <span data-ttu-id="b631b-130">Konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q# programı olan `Program.qs` adlı kaynak dosyayı görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="b631b-130">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="b631b-131">Uygulamayı çalıştırmak için:</span><span class="sxs-lookup"><span data-stu-id="b631b-131">To run the application:</span></span>
1. <span data-ttu-id="b631b-132">**Terminal** -> **Yeni Terminal**’e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="b631b-132">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="b631b-133">Terminal isteminde `dotnet run` girin.</span><span class="sxs-lookup"><span data-stu-id="b631b-133">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="b631b-134">Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="b631b-134">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="b631b-135">Birden fazla kök klasörü olan çalışma alanları şu anda VS Code Q# uzantısı tarafından desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="b631b-135">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="b631b-136">Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.</span><span class="sxs-lookup"><span data-stu-id="b631b-136">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="b631b-137">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b631b-137">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="b631b-138">Bir Q# `Hello World` uygulaması oluşturarak Visual Studio yüklemenizi doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="b631b-138">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="b631b-139">Yeni bir Q# uygulaması oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="b631b-139">To create a new Q# application:</span></span>
1. <span data-ttu-id="b631b-140">Visual Studio’yu açın ve **Dosya** -> **Yeni** -> **Proje**’ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="b631b-140">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="b631b-141">Arama kutusuna `Q#` yazın, **Q# Uygulaması**’nı seçin ve **İleri**’ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="b631b-141">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="b631b-142">Uygulamanız için bir ad ve konum girip **Oluştur**'a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="b631b-142">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="b631b-143">Projeyi inceleyin.</span><span class="sxs-lookup"><span data-stu-id="b631b-143">Inspect the project.</span></span> <span data-ttu-id="b631b-144">Konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q# programı olan `Program.qs` adlı kaynak dosyayı görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="b631b-144">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="b631b-145">Uygulamayı çalıştırmak için:</span><span class="sxs-lookup"><span data-stu-id="b631b-145">To run the application:</span></span>
1. <span data-ttu-id="b631b-146">**Hata Ayıklama** -> **Hata Ayıklamadan Başlat**’ı seçin.</span><span class="sxs-lookup"><span data-stu-id="b631b-146">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="b631b-147">Bir konsol penceresinde yazdırılmış `Hello quantum world!` metni görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="b631b-147">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="b631b-148">Bir Visual Studio çözümünde birden fazla projeniz varsa, çözümde yer alan tüm projelerin çözüm ile aynı klasörde veya bunun alt klasörlerinin birinde olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="b631b-148">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-line"></a>[<span data-ttu-id="b631b-149">Komut satırı içeren diğer düzenleyiciler</span><span class="sxs-lookup"><span data-stu-id="b631b-149">Other editors with the command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="b631b-150">Bir Q# `Hello World` uygulaması oluşturarak yüklemenizi doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="b631b-150">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="b631b-151">Yeni bir uygulama oluşturun:</span><span class="sxs-lookup"><span data-stu-id="b631b-151">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

2. <span data-ttu-id="b631b-152">Uygulama dizinine gidin:</span><span class="sxs-lookup"><span data-stu-id="b631b-152">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="b631b-153">Bu dizin artık, konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q# programı olan `Program.qs` adlı dosyayı içermelidir.</span><span class="sxs-lookup"><span data-stu-id="b631b-153">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="b631b-154">Bu şablonda bir metin düzenleyiciyle değişiklik yapabilir ve kendi kuantum uygulamalarınızla bu şablonun üzerine yazabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b631b-154">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

3. <span data-ttu-id="b631b-155">Programı çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="b631b-155">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

4. <span data-ttu-id="b631b-156">Şu metnin yazdırıldığını görmeniz gerekir: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="b631b-156">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="b631b-157">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="b631b-157">Next steps</span></span>

<span data-ttu-id="b631b-158">Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b631b-158">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
