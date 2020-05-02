---
title: 'Sürücü ve ana bilgisayar dili olmadan Q # programlarını yürütme'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706810"
---
# <a name="q-command-line-applications"></a><span data-ttu-id="fd9fb-102">Q # komut satırı uygulamaları</span><span class="sxs-lookup"><span data-stu-id="fd9fb-102">Q# Command Line Applications</span></span>

<span data-ttu-id="fd9fb-103">Q # programları, C#, F # veya Python gibi bir ana bilgisayar dilinde bir sürücü olmadan kendi başına çalıştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="fd9fb-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="fd9fb-104">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="fd9fb-104">Pre-requisites</span></span>

- [<span data-ttu-id="fd9fb-105">.NET Core SDK 3,1 veya üzeri</span><span class="sxs-lookup"><span data-stu-id="fd9fb-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="fd9fb-106">Yükleme</span><span class="sxs-lookup"><span data-stu-id="fd9fb-106">Installation</span></span>

<span data-ttu-id="fd9fb-107">Herhangi bir IDE 'de Q # komut satırı uygulamaları derleyebilir, ancak Q # uygulamalarınız için Visual Studio Code (VS Code) veya Visual Studio IDE kullanmanızı kesinlikle öneririz.</span><span class="sxs-lookup"><span data-stu-id="fd9fb-107">While you can build Q# command line applications in any IDE, we highly recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="fd9fb-108">VS Code veya Visual Studio ile QDK Visual Studio Code uzantısını kullanarak daha zengin işlevselliğe erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fd9fb-108">By using VS Code or Visual Studio and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

- <span data-ttu-id="fd9fb-109">[Vs Code](https://code.visualstudio.com/download) (Windows, Linux ve Mac) 'i yükler</span><span class="sxs-lookup"><span data-stu-id="fd9fb-109">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
- <span data-ttu-id="fd9fb-110">[Vs Code Için QDK uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) yükler veya</span><span class="sxs-lookup"><span data-stu-id="fd9fb-110">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) OR</span></span>
- <span data-ttu-id="fd9fb-111">.NET Core platformlar arası geliştirme iş yükü etkin olan [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3</span><span class="sxs-lookup"><span data-stu-id="fd9fb-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>
- <span data-ttu-id="fd9fb-112">[Visual Studio uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) indirme ve yükleme</span><span class="sxs-lookup"><span data-stu-id="fd9fb-112">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="fd9fb-113">VS Code kullanarak Q # ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="fd9fb-113">Develop with Q# using VS Code</span></span>

<span data-ttu-id="fd9fb-114">Kuantum proje şablonlarını yükleyin:</span><span class="sxs-lookup"><span data-stu-id="fd9fb-114">Install the Quantum project templates:</span></span>

- <span data-ttu-id="fd9fb-115">**Görünüm** -> **komut paleti** 'ne git</span><span class="sxs-lookup"><span data-stu-id="fd9fb-115">Go to **View** -> **Command Palette**</span></span>
- <span data-ttu-id="fd9fb-116">**S # seçin: proje şablonlarını Install**</span><span class="sxs-lookup"><span data-stu-id="fd9fb-116">Select **Q#: Install project templates**</span></span>

<span data-ttu-id="fd9fb-117">Quantum Development Kit yüklenmiştir ve kendi uygulama ve kitaplıklarınızda kullanılmaya hazırdır.</span><span class="sxs-lookup"><span data-stu-id="fd9fb-117">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>
- <span data-ttu-id="fd9fb-118">Yeni bir proje oluşturun:</span><span class="sxs-lookup"><span data-stu-id="fd9fb-118">Create a new project:</span></span>
  - <span data-ttu-id="fd9fb-119">**Görünüm** -> **komut paleti** 'ne git</span><span class="sxs-lookup"><span data-stu-id="fd9fb-119">Go to **View** -> **Command Palette**</span></span>
  - <span data-ttu-id="fd9fb-120">**Q #: yeni proje oluştur** ' u seçin</span><span class="sxs-lookup"><span data-stu-id="fd9fb-120">Select **Q#: Create New Project**</span></span>
  - <span data-ttu-id="fd9fb-121">**Tek başına konsol uygulamasını** seçin</span><span class="sxs-lookup"><span data-stu-id="fd9fb-121">Select **Standalone console application**</span></span>
  - <span data-ttu-id="fd9fb-122">Dosya sisteminde uygulamayı oluşturmak istediğiniz konuma gidin</span><span class="sxs-lookup"><span data-stu-id="fd9fb-122">Navigate to the location on the file system where you would like to create the application</span></span>
  - <span data-ttu-id="fd9fb-123">Proje oluşturulduktan sonra **Yeni proje aç...** düğmesine tıklayın</span><span class="sxs-lookup"><span data-stu-id="fd9fb-123">Click on the **Open new project...** button, once the project has been created</span></span>
        
- <span data-ttu-id="fd9fb-124">Projeyi inceleyin</span><span class="sxs-lookup"><span data-stu-id="fd9fb-124">Inspect the project</span></span>
  - <span data-ttu-id="fd9fb-125">Konsola ileti yazdırmak için basit bir işlem `Program.qs` tanımlayan bir Q # programı olan adlı bir dosyanın oluşturulduğunu görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="fd9fb-125">You should see that a file called `Program.qs` created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="fd9fb-126">Uygulamayı çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="fd9fb-126">Run the application:</span></span>
  - <span data-ttu-id="fd9fb-127">**Terminal** -> **yeni Terminal** 'e git</span><span class="sxs-lookup"><span data-stu-id="fd9fb-127">Go to **Terminal** -> **New Terminal**</span></span>
  - <span data-ttu-id="fd9fb-128">Girmesini`dotnet run`</span><span class="sxs-lookup"><span data-stu-id="fd9fb-128">Enter `dotnet run`</span></span>
  - <span data-ttu-id="fd9fb-129">Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="fd9fb-129">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="fd9fb-130">Birden fazla kök klasörü olan çalışma alanları şu anda Visual Studio Code uzantısı tarafından desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="fd9fb-130">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="fd9fb-131">Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.</span><span class="sxs-lookup"><span data-stu-id="fd9fb-131">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="fd9fb-132">Visual Studio kullanarak Q # ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="fd9fb-132">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="fd9fb-133">`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın</span><span class="sxs-lookup"><span data-stu-id="fd9fb-133">Verify the installation by creating a `Hello World` application</span></span>

- <span data-ttu-id="fd9fb-134">Yeni bir Q# uygulaması oluşturun</span><span class="sxs-lookup"><span data-stu-id="fd9fb-134">Create a new Q# application</span></span>
  - <span data-ttu-id="fd9fb-135">**Dosya** -> **New**yeni -> **Proje** 'ye git</span><span class="sxs-lookup"><span data-stu-id="fd9fb-135">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="fd9fb-136">Arama kutusuna `Q#` yazın</span><span class="sxs-lookup"><span data-stu-id="fd9fb-136">Type `Q#` in the search box</span></span>
  - <span data-ttu-id="fd9fb-137">**Q# Uygulaması**’nı seçin</span><span class="sxs-lookup"><span data-stu-id="fd9fb-137">Select **Q# Application**</span></span>
  - <span data-ttu-id="fd9fb-138">**İleri** Seç</span><span class="sxs-lookup"><span data-stu-id="fd9fb-138">Select **Next**</span></span>
  - <span data-ttu-id="fd9fb-139">Uygulamanız için bir ad ve konum seçin</span><span class="sxs-lookup"><span data-stu-id="fd9fb-139">Choose a name and location for your application</span></span>
  - <span data-ttu-id="fd9fb-140">**Oluştur** ' u seçin</span><span class="sxs-lookup"><span data-stu-id="fd9fb-140">Select **Create**</span></span>

- <span data-ttu-id="fd9fb-141">Projeyi inceleyin</span><span class="sxs-lookup"><span data-stu-id="fd9fb-141">Inspect the project</span></span>
  - <span data-ttu-id="fd9fb-142">Adlı `Program.qs` bir dosyanın oluşturulduğunu, yani konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q # programı olduğunu görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="fd9fb-142">You should see that a file called `Program.qs` has been created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="fd9fb-143">Uygulamayı çalıştırma</span><span class="sxs-lookup"><span data-stu-id="fd9fb-143">Run the application</span></span>
  - <span data-ttu-id="fd9fb-144">Hata ayıklama**olmadan Başlat** ' **ı seçin** -> </span><span class="sxs-lookup"><span data-stu-id="fd9fb-144">Select **Debug** -> **Start Without Debugging**</span></span>
  - <span data-ttu-id="fd9fb-145">Bir konsol penceresinde yazdırılmış `Hello quantum world!` metni görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="fd9fb-145">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="fd9fb-146">Bir Visual Studio çözümünde birden fazla projeniz varsa, çözümde yer alan tüm projelerin çözüm ile aynı klasörde veya bunun bir alt klasöründe olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="fd9fb-146">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  


## <a name="whats-next"></a><span data-ttu-id="fd9fb-147">Sırada ne var?</span><span class="sxs-lookup"><span data-stu-id="fd9fb-147">What's next?</span></span>

<span data-ttu-id="fd9fb-148">Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.write-program) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fd9fb-148">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
