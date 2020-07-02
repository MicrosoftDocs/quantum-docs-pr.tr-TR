---
title: Q# komut satırı uygulamaları ile geliştirme
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274195"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="dabeb-102">Q# komut satırı uygulamaları ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="dabeb-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="dabeb-103">Q# programları, C#, F# veya Python gibi bir konak dilinde sürücü olmadan kendi başına çalıştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="dabeb-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dabeb-104">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="dabeb-104">Prerequisites</span></span>

- [<span data-ttu-id="dabeb-105">.NET Core SDK 3.1 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="dabeb-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="dabeb-106">Yükleme</span><span class="sxs-lookup"><span data-stu-id="dabeb-106">Installation</span></span>

<span data-ttu-id="dabeb-107">Q# komut satırı uygulamalarını herhangi bir IDE'de derleyebilseniz de, Q# uygulamalarınız için Visual Studio Code (VS Code) veya Visual Studio IDE kullanmanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="dabeb-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="dabeb-108">Bu araçlarda geliştirme yapılması, zengin işlevselliğe erişim sağlar.</span><span class="sxs-lookup"><span data-stu-id="dabeb-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="dabeb-109">VS Code'u yapılandırmak için:</span><span class="sxs-lookup"><span data-stu-id="dabeb-109">To configure VS Code:</span></span>

1. <span data-ttu-id="dabeb-110">[VS Code](https://code.visualstudio.com/download)’u (Windows, Linux ve Mac) indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="dabeb-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="dabeb-111">[VS Code için Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)’yi yükleyin.</span><span class="sxs-lookup"><span data-stu-id="dabeb-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="dabeb-112">Visual Studio'yu yapılandırmak için:</span><span class="sxs-lookup"><span data-stu-id="dabeb-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="dabeb-113">.NET Core platformlar arası geliştirme iş yükü etkin olan [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 veya üzerini indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="dabeb-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="dabeb-114">[Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)’yi indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="dabeb-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="dabeb-115">VS Code kullanarak Q# ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="dabeb-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="dabeb-116">Q# proje şablonlarını yükleyin:</span><span class="sxs-lookup"><span data-stu-id="dabeb-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="dabeb-117">VS Code’u açın.</span><span class="sxs-lookup"><span data-stu-id="dabeb-117">Open VS Code.</span></span>
2. <span data-ttu-id="dabeb-118">**Görünüm** -> **Komut Paleti**’ne tıklayın.</span><span class="sxs-lookup"><span data-stu-id="dabeb-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="dabeb-119">**Q#: Proje şablonlarını yükleyin**.</span><span class="sxs-lookup"><span data-stu-id="dabeb-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="dabeb-120">**Proje şablonları başarıyla yüklendi** iletisi görüntülendiğinde, QDK kendi uygulama ve kitaplıklarınızla birlikte kullanıma hazırdır.</span><span class="sxs-lookup"><span data-stu-id="dabeb-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="dabeb-121">Yeni bir proje oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="dabeb-121">To create a new project:</span></span>

1. <span data-ttu-id="dabeb-122">**Görünüm** -> **Komut Paleti**’ne tıklayın ve **Q#: Yeni Proje Oluştur**’u seçin.</span><span class="sxs-lookup"><span data-stu-id="dabeb-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="dabeb-123">**Bağımsız konsol uygulaması**’na tıklayın.</span><span class="sxs-lookup"><span data-stu-id="dabeb-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="dabeb-124">Projenin kaydedileceği konuma gidin ve **Proje Oluştur**’a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="dabeb-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="dabeb-125">Proje başarıyla oluşturulduğunda, sağ alt kısımdaki **Yeni proje aç...** seçeneğine tıklayın.</span><span class="sxs-lookup"><span data-stu-id="dabeb-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="dabeb-126">Projeyi inceleyin.</span><span class="sxs-lookup"><span data-stu-id="dabeb-126">Inspect the project.</span></span> <span data-ttu-id="dabeb-127">Konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q# programı olan `Program.qs` adlı kaynak dosyayı görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="dabeb-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="dabeb-128">Uygulamayı çalıştırmak için:</span><span class="sxs-lookup"><span data-stu-id="dabeb-128">To run the application:</span></span>
1. <span data-ttu-id="dabeb-129">**Terminal** -> **Yeni Terminal**’e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="dabeb-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="dabeb-130">Terminal isteminde `dotnet run` girin.</span><span class="sxs-lookup"><span data-stu-id="dabeb-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="dabeb-131">Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="dabeb-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="dabeb-132">Birden fazla kök klasörü olan çalışma alanları şu anda VS Code Q# uzantısı tarafından desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="dabeb-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="dabeb-133">Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.</span><span class="sxs-lookup"><span data-stu-id="dabeb-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="dabeb-134">Visual Studio kullanarak Q# ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="dabeb-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="dabeb-135">Bir Q# `Hello World` uygulaması oluşturarak Visual Studio yüklemenizi doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="dabeb-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="dabeb-136">Yeni bir Q# uygulaması oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="dabeb-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="dabeb-137">Visual Studio’yu açın ve **Dosya** -> **Yeni** -> **Proje**’ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="dabeb-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="dabeb-138">Arama kutusuna `Q#` yazın, **Q# Uygulaması**’nı seçin ve **İleri**’ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="dabeb-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="dabeb-139">Uygulamanız için bir ad ve konum girip **Oluştur**'a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="dabeb-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="dabeb-140">Projeyi inceleyin.</span><span class="sxs-lookup"><span data-stu-id="dabeb-140">Inspect the project.</span></span> <span data-ttu-id="dabeb-141">Konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q# programı olan `Program.qs` adlı kaynak dosyayı görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="dabeb-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="dabeb-142">Uygulamayı çalıştırmak için:</span><span class="sxs-lookup"><span data-stu-id="dabeb-142">To run the application:</span></span>
1. <span data-ttu-id="dabeb-143">**Hata Ayıklama** -> **Hata Ayıklamadan Başlat**’ı seçin.</span><span class="sxs-lookup"><span data-stu-id="dabeb-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="dabeb-144">Bir konsol penceresinde yazdırılmış `Hello quantum world!` metni görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="dabeb-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="dabeb-145">Bir Visual Studio çözümünde birden fazla projeniz varsa, çözümde yer alan tüm projelerin çözüm ile aynı klasörde veya bunun alt klasörlerinin birinde olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="dabeb-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="dabeb-146">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="dabeb-146">Next steps</span></span>

<span data-ttu-id="dabeb-147">Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="dabeb-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
