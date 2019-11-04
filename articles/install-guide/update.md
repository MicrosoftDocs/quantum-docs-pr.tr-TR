---
title: Microsoft Quantum Development Kit güncelleştirme hakkında bilgi edinin (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185860"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="c84e5-102">Microsoft Quantum Development Kit güncelleştirme (QDK)</span><span class="sxs-lookup"><span data-stu-id="c84e5-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="c84e5-103">Microsoft Quantum Development Kit (QDK) ' i en son sürüme güncelleştirmeyi öğrenin.</span><span class="sxs-lookup"><span data-stu-id="c84e5-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="c84e5-104">Bu makalede, zaten QDK 'nin yüklü olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="c84e5-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="c84e5-105">Uygulamasını ilk kez yüklüyorsanız, lütfen [yükleme kılavuzuna](xref:microsoft.quantum.install)bakın.</span><span class="sxs-lookup"><span data-stu-id="c84e5-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="c84e5-106">Güncelleştirme adımları geliştirme ortamınıza bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="c84e5-106">The update steps depend on your development environment.</span></span> <span data-ttu-id="c84e5-107">Aşağıdaki bölümlerde ortamınızı seçin.</span><span class="sxs-lookup"><span data-stu-id="c84e5-107">Choose your environment from the following sections.</span></span>

## <a name="python"></a><span data-ttu-id="c84e5-108">Python</span><span class="sxs-lookup"><span data-stu-id="c84e5-108">Python</span></span>

1. <span data-ttu-id="c84e5-109">`iqsharp` çekirdeğini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="c84e5-109">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="c84e5-110">`iqsharp` sürümünü doğrulama</span><span class="sxs-lookup"><span data-stu-id="c84e5-110">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="c84e5-111">Aşağıdaki çıktıyı görmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="c84e5-111">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="c84e5-112">`qsharp` paketini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="c84e5-112">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="c84e5-113">`qsharp` sürümünü doğrulama</span><span class="sxs-lookup"><span data-stu-id="c84e5-113">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="c84e5-114">Aşağıdaki çıktıyı görmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="c84e5-114">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="c84e5-115">Artık, var olan hisse programlarınızı çalıştırmak için güncelleştirilmiş QDK sürümünü kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c84e5-115">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="jupyter-notebooks"></a><span data-ttu-id="c84e5-116">Jupyter notebooks</span><span class="sxs-lookup"><span data-stu-id="c84e5-116">Jupyter notebooks</span></span>

1. <span data-ttu-id="c84e5-117">`iqsharp` çekirdeğini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="c84e5-117">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="c84e5-118">`iqsharp` sürümünü doğrulama</span><span class="sxs-lookup"><span data-stu-id="c84e5-118">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="c84e5-119">Aşağıdaki çıktıyı görmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="c84e5-119">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="c84e5-120">Artık var olan bir Jupyter Not defterini açabilir ve güncelleştirilmiş QDK ile çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c84e5-120">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="c-on-windows-using-visual-studio"></a><span data-ttu-id="c84e5-121">C#Windows 'da, Visual Studio 'Yu kullanarak</span><span class="sxs-lookup"><span data-stu-id="c84e5-121">C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="c84e5-122">Q # Visual Studio uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="c84e5-122">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="c84e5-123">Visual Studio, [hisse Için Visual Studio uzantısına](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) yönelik güncelleştirmeleri kabul etmenizi ister</span><span class="sxs-lookup"><span data-stu-id="c84e5-123">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="c84e5-124">Güncelleştirmeyi kabul et</span><span class="sxs-lookup"><span data-stu-id="c84e5-124">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="c84e5-125">Proje şablonları, uzantısıyla güncellenir.</span><span class="sxs-lookup"><span data-stu-id="c84e5-125">The project templates are updated with the extension.</span></span> <span data-ttu-id="c84e5-126">Güncelleştirilmiş şablonlar yalnızca yeni oluşturulan projeler için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="c84e5-126">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="c84e5-127">Uzantı güncelleniyorsa, mevcut projelerinizin kodu güncellenmez.</span><span class="sxs-lookup"><span data-stu-id="c84e5-127">The code for your existing projects is not updated when the extension is updated.</span></span>

1. <span data-ttu-id="c84e5-128">QDK paketlerini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="c84e5-128">Update the QDK packages</span></span>

    - <span data-ttu-id="c84e5-129">Mevcut bir uygulamayı aç</span><span class="sxs-lookup"><span data-stu-id="c84e5-129">Open an existing application</span></span>
    - <span data-ttu-id="c84e5-130">Çözüm Gezgini **bağımlılıkları** seçin</span><span class="sxs-lookup"><span data-stu-id="c84e5-130">Select **Dependencies** in the Solution Explorer</span></span>
    - <span data-ttu-id="c84e5-131">**NuGet Paketlerini Yönet** ' i seçin</span><span class="sxs-lookup"><span data-stu-id="c84e5-131">Select **Manage NuGet Packages**</span></span>
    - <span data-ttu-id="c84e5-132">**Microsoft. hisse** paketlerini en son sürüme güncelleştirin</span><span class="sxs-lookup"><span data-stu-id="c84e5-132">Update the **Microsoft.Quantum** packages to the latest version</span></span>

1. <span data-ttu-id="c84e5-133">Artık uygulamanızı en son QDK ile çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c84e5-133">You can now run your application with the latest QDK.</span></span>

## <a name="c-using-vs-code"></a><span data-ttu-id="c84e5-134">C#VS Code kullanarak</span><span class="sxs-lookup"><span data-stu-id="c84e5-134">C#, using VS Code</span></span>

1. <span data-ttu-id="c84e5-135">Hisse VS Code uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="c84e5-135">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="c84e5-136">VS Code yeniden Başlat</span><span class="sxs-lookup"><span data-stu-id="c84e5-136">Restart VS Code</span></span>
    - <span data-ttu-id="c84e5-137">**Uzantılar** sekmesine gidin</span><span class="sxs-lookup"><span data-stu-id="c84e5-137">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="c84e5-138">Visual Studio Code uzantısı **için Microsoft Quantum Development Kit** seçin</span><span class="sxs-lookup"><span data-stu-id="c84e5-138">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="c84e5-139">Uzantıyı yeniden yükleme</span><span class="sxs-lookup"><span data-stu-id="c84e5-139">Reload the extension</span></span>

1. <span data-ttu-id="c84e5-140">Hisse projesi şablonlarını güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="c84e5-140">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="c84e5-141">**Görüntüleme** -> **komut paleti** 'ne git</span><span class="sxs-lookup"><span data-stu-id="c84e5-141">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="c84e5-142">**S # seçin: proje şablonlarını Install**</span><span class="sxs-lookup"><span data-stu-id="c84e5-142">Select **Q#: Install project templates**</span></span>

1. <span data-ttu-id="c84e5-143">Mevcut bir uygulamayı VS Code açın</span><span class="sxs-lookup"><span data-stu-id="c84e5-143">Open an existing application in VS Code</span></span>

   - <span data-ttu-id="c84e5-144">Yeni Paket sürümlerini eklemek için. csproj dosyasını düzenleyin</span><span class="sxs-lookup"><span data-stu-id="c84e5-144">Edit the .csproj file to add the new package versions</span></span>

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    <span data-ttu-id="c84e5-145">Diğer `Microsoft.Quantum` paketlerini kullanıyorsanız, bunları da güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="c84e5-145">If you use other `Microsoft.Quantum` packages, update these too.</span></span>

1. <span data-ttu-id="c84e5-146">Artık uygulamanızı güncelleştirilmiş QDK ile çalıştırabilirsiniz</span><span class="sxs-lookup"><span data-stu-id="c84e5-146">You can now run your application with the updated QDK</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="c84e5-147">C#`dotnet` komut satırı aracını kullanarak</span><span class="sxs-lookup"><span data-stu-id="c84e5-147">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="c84e5-148">.NET için hisse projesi şablonlarını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="c84e5-148">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="c84e5-149">Mevcut bir uygulamayı güncelleştirme ve çalıştırma</span><span class="sxs-lookup"><span data-stu-id="c84e5-149">Update and run an existing application</span></span>

    - <span data-ttu-id="c84e5-150">Uygulamanızdaki QDK paket sürümlerini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="c84e5-150">Update the QDK package versions in your application</span></span>

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        <span data-ttu-id="c84e5-151">Uygulamanız başka bir `Microsoft.Quantum` paketi kullanıyorsa, bunları da güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="c84e5-151">If your application uses any other `Microsoft.Quantum` packages, update these too.</span></span>

    - <span data-ttu-id="c84e5-152">Uygulamayı çalıştırma</span><span class="sxs-lookup"><span data-stu-id="c84e5-152">Run the application</span></span>

        ```bash
        dotnet run
        ```

    - <span data-ttu-id="c84e5-153">Uygulamanız yeni paket sürümleriyle çalışacak</span><span class="sxs-lookup"><span data-stu-id="c84e5-153">Your application will run with the new package versions</span></span>

## <a name="whats-next"></a><span data-ttu-id="c84e5-154">Sırada ne var?</span><span class="sxs-lookup"><span data-stu-id="c84e5-154">What's next?</span></span>

<span data-ttu-id="c84e5-155">Artık, tercih ettiğiniz ortamınızda hisse geliştirme setini güncelleştirmiş olduğunuza göre, hisse ve programlarınızı geliştirmeye ve çalıştırmaya devam edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c84e5-155">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="c84e5-156">Henüz bir program yazmadıysanız, [ilk hisse al programınızı](xref:microsoft.quantum.write-program)kullanmaya başlamanızı sağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c84e5-156">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
