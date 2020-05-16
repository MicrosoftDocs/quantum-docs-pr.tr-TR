---
title: 'Q # komut satırı uygulamalarıyla geliştirme'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e829862521951c50cb42eebf261c803071a95275
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426430"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="34739-102">Q # komut satırı uygulamalarıyla geliştirme</span><span class="sxs-lookup"><span data-stu-id="34739-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="34739-103">Q # programları, C#, F # veya Python gibi bir ana bilgisayar dilinde bir sürücü olmadan kendi başına çalıştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="34739-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="34739-104">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="34739-104">Pre-requisites</span></span>

- [<span data-ttu-id="34739-105">.NET Core SDK 3,1 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="34739-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="34739-106">Yükleme</span><span class="sxs-lookup"><span data-stu-id="34739-106">Installation</span></span>

<span data-ttu-id="34739-107">Herhangi bir IDE 'de Q # komut satırı uygulamaları derleyebilir, ancak Q # uygulamalarınız için Visual Studio Code (VS Code) veya Visual Studio IDE kullanmanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="34739-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="34739-108">Bu araçların geliştirilmesi, zengin işlevselliğe erişim sağlar.</span><span class="sxs-lookup"><span data-stu-id="34739-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="34739-109">VS Code yapılandırmak için:</span><span class="sxs-lookup"><span data-stu-id="34739-109">To configure VS Code:</span></span>

1. <span data-ttu-id="34739-110">[Vs Code](https://code.visualstudio.com/download) indirin ve yükleyin (Windows, Linux ve Mac).</span><span class="sxs-lookup"><span data-stu-id="34739-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="34739-111">[Vs Code Için Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)'yi yükler.</span><span class="sxs-lookup"><span data-stu-id="34739-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="34739-112">Visual Studio 'Yu yapılandırmak için:</span><span class="sxs-lookup"><span data-stu-id="34739-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="34739-113">.NET Core platformlar arası geliştirme iş yükü etkinken [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16,3 veya üstünü indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="34739-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="34739-114">[Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)'yi indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="34739-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="34739-115">VS Code kullanarak Q # ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="34739-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="34739-116">Q # proje şablonlarını yükler:</span><span class="sxs-lookup"><span data-stu-id="34739-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="34739-117">VS Code açın.</span><span class="sxs-lookup"><span data-stu-id="34739-117">Open VS Code.</span></span>
2. <span data-ttu-id="34739-118">**Görünüm**  ->  **komut paleti**' ne tıklayın.</span><span class="sxs-lookup"><span data-stu-id="34739-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="34739-119">**Q #: proje şablonlarını yükler**' i seçin.</span><span class="sxs-lookup"><span data-stu-id="34739-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="34739-120">**Proje şablonları başarıyla yüklendiğinde** , QDK kendi uygulama ve kitaplıklarınızla birlikte kullanıma yönelik olarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="34739-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="34739-121">Yeni bir proje oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="34739-121">To create a new project:</span></span>

1. <span data-ttu-id="34739-122">Komut **paletini görüntüle**' ye tıklayın  ->  **Command Palette** ve **Q #: yeni proje oluştur**' u seçin.</span><span class="sxs-lookup"><span data-stu-id="34739-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="34739-123">**Tek başına konsol uygulaması**' na tıklayın.</span><span class="sxs-lookup"><span data-stu-id="34739-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="34739-124">Projeyi kaydetmek için konuma gidin ve **proje oluştur**' a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="34739-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="34739-125">Proje başarıyla oluşturulduğunda, sağ alt köşedeki **Yeni proje... aç** ' a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="34739-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="34739-126">Projeyi inceleyin.</span><span class="sxs-lookup"><span data-stu-id="34739-126">Inspect the project.</span></span> <span data-ttu-id="34739-127">`Program.qs`Konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q # programı olan adlı bir kaynak dosyası görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="34739-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="34739-128">Uygulamayı çalıştırmak için:</span><span class="sxs-lookup"><span data-stu-id="34739-128">To run the application:</span></span>
1. <span data-ttu-id="34739-129">**Terminal**  ->  **yeni Terminal**' e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="34739-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="34739-130">Terminal isteminde, girin `dotnet run` .</span><span class="sxs-lookup"><span data-stu-id="34739-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="34739-131">Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="34739-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="34739-132">Birden çok kök klasörü olan çalışma alanları şu anda VS Code Q # uzantısı tarafından desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="34739-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="34739-133">Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.</span><span class="sxs-lookup"><span data-stu-id="34739-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="34739-134">Visual Studio kullanarak Q # ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="34739-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="34739-135">Bir Q # uygulaması oluşturarak Visual Studio yüklemenizi doğrulayın `Hello World` .</span><span class="sxs-lookup"><span data-stu-id="34739-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="34739-136">Yeni bir Q # uygulaması oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="34739-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="34739-137">Visual Studio 'yu açın ve **Dosya**  ->  **Yeni**  ->  **Proje**' ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="34739-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="34739-138">`Q#`Arama kutusuna yazın, **Q # uygulaması** ' nı seçin ve **İleri**' ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="34739-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="34739-139">Uygulamanız için bir ad ve konum girin ve **Oluştur**' a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="34739-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="34739-140">Projeyi inceleyin.</span><span class="sxs-lookup"><span data-stu-id="34739-140">Inspect the project.</span></span> <span data-ttu-id="34739-141">`Program.qs`Konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q # programı olan adlı bir kaynak dosyası görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="34739-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="34739-142">Uygulamayı çalıştırmak için:</span><span class="sxs-lookup"><span data-stu-id="34739-142">To run the application:</span></span>
1. <span data-ttu-id="34739-143">Hata **Debug**  ->  **ayıklamadan Başlat**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="34739-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="34739-144">Bir konsol penceresinde yazdırılmış `Hello quantum world!` metni görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="34739-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="34739-145">Bir Visual Studio çözümü içinde birden çok projeniz varsa, Çözümdeki tüm projelerin çözümle aynı klasörde veya alt klasörlerinden birinde olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="34739-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="34739-146">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="34739-146">Next steps</span></span>

<span data-ttu-id="34739-147">Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="34739-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
