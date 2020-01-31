---
title: 'Q # + ile geliştirinC#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 1fd829c684502092bb7491b0f46b5f690320c941
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831027"
---
# <a name="develop-with-q--c"></a><span data-ttu-id="9fbf6-102">Q # + ile geliştirinC#</span><span class="sxs-lookup"><span data-stu-id="9fbf6-102">Develop with Q# + C#</span></span>

<span data-ttu-id="9fbf6-103">Q # işlemlerini çağırmak için konak C# programları geliştirmek üzere QDK 'yi yükler.</span><span class="sxs-lookup"><span data-stu-id="9fbf6-103">Install the QDK to develop C# host programs to call Q# operations.</span></span>

<span data-ttu-id="9fbf6-104">S #, .NET dilleri ile birlikte çalışmak için geliştirilmiştir--özellikle C#.</span><span class="sxs-lookup"><span data-stu-id="9fbf6-104">Q# is built to play well with .NET languages--specifically C#.</span></span> <span data-ttu-id="9fbf6-105">Bu eşleştirmede farklı geliştirme ortamları içinde çalışabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="9fbf6-105">You can work with this pairing inside different development environments:</span></span>

- [<span data-ttu-id="9fbf6-106">Q # + C# Visual Studio 'Yu (Windows) kullanma</span><span class="sxs-lookup"><span data-stu-id="9fbf6-106">Q# + C# using Visual Studio (Windows)</span></span>](#VS)
- [<span data-ttu-id="9fbf6-107">Q # + C# Visual Studio Code (Windows, Linux ve Mac) kullanma</span><span class="sxs-lookup"><span data-stu-id="9fbf6-107">Q# + C# using Visual Studio Code (Windows, Linux and Mac)</span></span>](#VSC)
- [<span data-ttu-id="9fbf6-108">`dotnet` komut satırı C# aracını kullanarak Q # +</span><span class="sxs-lookup"><span data-stu-id="9fbf6-108">Q# + C# using the `dotnet` command-line tool</span></span>](#command)

## <span data-ttu-id="9fbf6-109">Visual Studio 'Yu kullanarak Q C# # + ile geliştirme<a name="VS"></a></span><span class="sxs-lookup"><span data-stu-id="9fbf6-109">Develop with Q# + C# using Visual Studio <a name="VS"></a></span></span>

<span data-ttu-id="9fbf6-110">Visual Studio, Q # programları geliştirmek için zengin bir ortam sunar.</span><span class="sxs-lookup"><span data-stu-id="9fbf6-110">Visual Studio offers a rich environment for developing Q# programs.</span></span> <span data-ttu-id="9fbf6-111">Q # Visual Studio uzantısı, Q # dosyaları ve projeleri için şablonlar ve sözdizimi vurgulaması, kod tamamlama ve IntelliSense desteği içerir.</span><span class="sxs-lookup"><span data-stu-id="9fbf6-111">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting, code completion and IntelliSense support.</span></span>


1. <span data-ttu-id="9fbf6-112">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="9fbf6-112">Pre-requisites</span></span>

    - <span data-ttu-id="9fbf6-113">.NET Core platformlar arası geliştirme iş yükü etkin olan [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3</span><span class="sxs-lookup"><span data-stu-id="9fbf6-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="9fbf6-114">Q# Visual Studio uzantısını yükleyin</span><span class="sxs-lookup"><span data-stu-id="9fbf6-114">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="9fbf6-115">[Visual Studio uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) indirme ve yükleme</span><span class="sxs-lookup"><span data-stu-id="9fbf6-115">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>

1. <span data-ttu-id="9fbf6-116">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="9fbf6-116">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="9fbf6-117">Yeni bir Q# uygulaması oluşturun</span><span class="sxs-lookup"><span data-stu-id="9fbf6-117">Create a new Q# application</span></span>

        - <span data-ttu-id="9fbf6-118">**Dosya** -> **Yeni** -> **Proje**’ye gidin</span><span class="sxs-lookup"><span data-stu-id="9fbf6-118">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="9fbf6-119">Arama kutusuna `Q#` yazın</span><span class="sxs-lookup"><span data-stu-id="9fbf6-119">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="9fbf6-120">**Q# Uygulaması**’nı seçin</span><span class="sxs-lookup"><span data-stu-id="9fbf6-120">Select **Q# Application**</span></span>
        - <span data-ttu-id="9fbf6-121">**İleri**’yi seçin</span><span class="sxs-lookup"><span data-stu-id="9fbf6-121">Select **Next**</span></span>
        - <span data-ttu-id="9fbf6-122">Uygulamanız için bir ad ve konum seçin</span><span class="sxs-lookup"><span data-stu-id="9fbf6-122">Choose a name and location for your application</span></span>
        - <span data-ttu-id="9fbf6-123">**Oluştur**’u seçin</span><span class="sxs-lookup"><span data-stu-id="9fbf6-123">Select **Create**</span></span>

    - <span data-ttu-id="9fbf6-124">Projeyi inceleyin</span><span class="sxs-lookup"><span data-stu-id="9fbf6-124">Inspect the project</span></span>

        <span data-ttu-id="9fbf6-125">İki dosya oluşturulur: C# konak uygulaması olan `Driver.cs` ve konsola bir ileti yazdıran basit işlemi tanımlayan Q# programı `Operation.qs`.</span><span class="sxs-lookup"><span data-stu-id="9fbf6-125">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="9fbf6-126">Uygulamayı çalıştırma</span><span class="sxs-lookup"><span data-stu-id="9fbf6-126">Run the application</span></span>

        - <span data-ttu-id="9fbf6-127">**Hata Ayıklama** -> **Hata Ayıklamadan Başlat**’ı seçin</span><span class="sxs-lookup"><span data-stu-id="9fbf6-127">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="9fbf6-128">Bir konsol penceresinde yazdırılmış `Hello quantum world!` metni görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="9fbf6-128">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="9fbf6-129">Bir Visual Studio çözümünde birden fazla projeniz varsa, çözümde yer alan tüm projelerin çözüm ile aynı klasörde veya bunun bir alt klasöründe olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="9fbf6-129">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <span data-ttu-id="9fbf6-130">Visual Studio Code kullanarak Q # + C# ile geliştirin<a name="VSC"></a></span><span class="sxs-lookup"><span data-stu-id="9fbf6-130">Develop with Q# + C# using Visual Studio Code <a name="VSC"></a></span></span>

<span data-ttu-id="9fbf6-131">Visual Studio Code (VS Code) Windows, Linux ve Mac 'te Q # programları geliştirmek için zengin bir ortam sunar.</span><span class="sxs-lookup"><span data-stu-id="9fbf6-131">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs on Windows, Linux and Mac.</span></span>  <span data-ttu-id="9fbf6-132">Q # VS Code uzantısı, Q # sözdizimi vurgulama, kod tamamlama ve Q # kod parçacıkları için destek içerir.</span><span class="sxs-lookup"><span data-stu-id="9fbf6-132">The Q# VS Code extension includes support for Q# syntax highlighting, code completion, and Q# code snippets.</span></span>

1. <span data-ttu-id="9fbf6-133">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="9fbf6-133">Pre-requisites</span></span>

   - [<span data-ttu-id="9fbf6-134">VS Code</span><span class="sxs-lookup"><span data-stu-id="9fbf6-134">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="9fbf6-135">.NET Core SDK 3,1 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="9fbf6-135">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="9fbf6-136">Kuantum VS Code uzantısını yükleme</span><span class="sxs-lookup"><span data-stu-id="9fbf6-136">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="9fbf6-137">[VS Code uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) yükleyin</span><span class="sxs-lookup"><span data-stu-id="9fbf6-137">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="9fbf6-138">Kuantum proje şablonlarını yükleyin:</span><span class="sxs-lookup"><span data-stu-id="9fbf6-138">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="9fbf6-139">**Görünüm** -> **Komut Paleti**’ne gidin</span><span class="sxs-lookup"><span data-stu-id="9fbf6-139">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="9fbf6-140">**S # seçin: proje şablonlarını Install**</span><span class="sxs-lookup"><span data-stu-id="9fbf6-140">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="9fbf6-141">Quantum Development Kit yüklenmiştir ve kendi uygulama ve kitaplıklarınızda kullanılmaya hazırdır.</span><span class="sxs-lookup"><span data-stu-id="9fbf6-141">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="9fbf6-142">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="9fbf6-142">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="9fbf6-143">Yeni bir proje oluşturun:</span><span class="sxs-lookup"><span data-stu-id="9fbf6-143">Create a new project:</span></span>

        - <span data-ttu-id="9fbf6-144">**Görünüm** -> **Komut Paleti**’ne gidin</span><span class="sxs-lookup"><span data-stu-id="9fbf6-144">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="9fbf6-145">**Q #: yeni proje oluştur** ' u seçin</span><span class="sxs-lookup"><span data-stu-id="9fbf6-145">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="9fbf6-146">**Tek başına konsol uygulamasını** seçin</span><span class="sxs-lookup"><span data-stu-id="9fbf6-146">Select **Standalone console application**</span></span>
        - <span data-ttu-id="9fbf6-147">Dosya sisteminde uygulamayı oluşturmak istediğiniz konuma gidin</span><span class="sxs-lookup"><span data-stu-id="9fbf6-147">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="9fbf6-148">Proje oluşturulduktan sonra **Yeni proje aç...** düğmesine tıklayın</span><span class="sxs-lookup"><span data-stu-id="9fbf6-148">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="9fbf6-149">VS Code için C# uzantınız yoksa bir açılır pencere görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="9fbf6-149">If you don't already have the C# extension for VS Code installed, a pop-up will appear.</span></span> <span data-ttu-id="9fbf6-150">Uzantıyı yükler.</span><span class="sxs-lookup"><span data-stu-id="9fbf6-150">Install the extension.</span></span> 

    - <span data-ttu-id="9fbf6-151">Uygulamayı çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="9fbf6-151">Run the application:</span></span>

        - <span data-ttu-id="9fbf6-152">**Terminal** -> **yeni Terminal** 'a git</span><span class="sxs-lookup"><span data-stu-id="9fbf6-152">Go to **Terminal** -> **New Terminal**</span></span>
        - <span data-ttu-id="9fbf6-153">`dotnet run` girin</span><span class="sxs-lookup"><span data-stu-id="9fbf6-153">Enter `dotnet run`</span></span>
        - <span data-ttu-id="9fbf6-154">Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="9fbf6-154">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="9fbf6-155">Birden fazla kök klasörü olan çalışma alanları şu anda Visual Studio Code uzantısı tarafından desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="9fbf6-155">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="9fbf6-156">Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.</span><span class="sxs-lookup"><span data-stu-id="9fbf6-156">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <span data-ttu-id="9fbf6-157">`dotnet` komut satırı aracını kullanarak C# Q # + ile geliştirme<a name="command"></a></span><span class="sxs-lookup"><span data-stu-id="9fbf6-157">Develop with Q# + C# using the `dotnet` command-line tool <a name="command"></a></span></span>

<span data-ttu-id="9fbf6-158">Kuşkusuz yalnızca .NET Core SDK'sını ve QDK proje şablonlarını yükleyerek Q# programlarını komut satırından da oluşturup çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9fbf6-158">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="9fbf6-159">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="9fbf6-159">Pre-requisites</span></span>

    - [<span data-ttu-id="9fbf6-160">.NET Core SDK 3,1 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="9fbf6-160">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="9fbf6-161">.NET için Kuantum proje şablonlarını yükleme</span><span class="sxs-lookup"><span data-stu-id="9fbf6-161">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="9fbf6-162">Quantum Development Kit yüklenmiştir ve kendi uygulama ve kitaplıklarınızda kullanılmaya hazırdır.</span><span class="sxs-lookup"><span data-stu-id="9fbf6-162">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="9fbf6-163">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="9fbf6-163">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="9fbf6-164">Yeni uygulama oluşturma</span><span class="sxs-lookup"><span data-stu-id="9fbf6-164">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="9fbf6-165">Yeni uygulama dizinine gidin</span><span class="sxs-lookup"><span data-stu-id="9fbf6-165">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="9fbf6-166">Uygulamanın proje dosyaları ile birlikte iki dosyanın oluşturulur: bir Q# dosyası (`Operation.qs`) ve bir C# konak dosyası (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="9fbf6-166">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="9fbf6-167">Uygulamayı çalıştırma</span><span class="sxs-lookup"><span data-stu-id="9fbf6-167">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="9fbf6-168">Şu çıktıyı görmeniz gerekir: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="9fbf6-168">You should see the following output: `Hello quantum world!`</span></span>

    
## <a name="whats-next"></a><span data-ttu-id="9fbf6-169">Sırada ne var?</span><span class="sxs-lookup"><span data-stu-id="9fbf6-169">What's next?</span></span>

<span data-ttu-id="9fbf6-170">Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.write-program) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9fbf6-170">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
