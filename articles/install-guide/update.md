---
title: Microsoft Quantum Development Kit güncelleştirme hakkında bilgi edinin (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463288"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="5c6b8-102">Microsoft Quantum Development Kit güncelleştirme (QDK)</span><span class="sxs-lookup"><span data-stu-id="5c6b8-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="5c6b8-103">Microsoft Quantum Development Kit (QDK) ' i en son sürüme güncelleştirmeyi öğrenin.</span><span class="sxs-lookup"><span data-stu-id="5c6b8-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="5c6b8-104">Bu makalede, zaten QDK 'nin yüklü olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="5c6b8-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="5c6b8-105">Uygulamasını ilk kez yüklüyorsanız, lütfen [yükleme kılavuzuna](xref:microsoft.quantum.install)bakın.</span><span class="sxs-lookup"><span data-stu-id="5c6b8-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>


## <a name="updating-q-projects"></a><span data-ttu-id="5c6b8-106">Q # projeleri güncelleştiriliyor</span><span class="sxs-lookup"><span data-stu-id="5c6b8-106">Updating Q# Projects</span></span> 

1. <span data-ttu-id="5c6b8-107">İlk olarak, [.NET Core SDK 3,0](https://dotnet.microsoft.com/download) ' nin en son sürümünü yükleyip komut isteminde aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="5c6b8-107">First, install the latest version of the [.NET Core SDK 3.0](https://dotnet.microsoft.com/download) and run the following command in the command prompt:</span></span>
```bash
dotnet --version
```
 <span data-ttu-id="5c6b8-108">Çıktının 3.0.100 veya üzeri olduğunu doğrulayın ve ardından kuruluma bağlı olarak aşağıdaki yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="5c6b8-108">Verify the output is 3.0.100 or higher, then follow the instructions below depending on your setup.</span></span>

### <a name="in-visual-studio"></a><span data-ttu-id="5c6b8-109">Visual Studio’da</span><span class="sxs-lookup"><span data-stu-id="5c6b8-109">In Visual Studio</span></span>
 
 1. <span data-ttu-id="5c6b8-110">Visual Studio 2019 ' nin en son sürümüne güncelleştirin, yönergeler için [buraya](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) bakın</span><span class="sxs-lookup"><span data-stu-id="5c6b8-110">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
 2. <span data-ttu-id="5c6b8-111">Çözümünüzü Visual Studio 'da açın</span><span class="sxs-lookup"><span data-stu-id="5c6b8-111">Open your solution in Visual Studio</span></span>
 3. <span data-ttu-id="5c6b8-112">Menüden oluştur > Çözümü Temizle ' yi seçin</span><span class="sxs-lookup"><span data-stu-id="5c6b8-112">From the menu, select Build > Clean Solution</span></span> 
 4. <span data-ttu-id="5c6b8-113">. Csproj dosyalarınızın her birinde [hedef Framework 'ü](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) netcoreapp 3.0 'a (veya bir kitaplık projesi ise Netstandard 2.1) güncelleştirin</span><span class="sxs-lookup"><span data-stu-id="5c6b8-113">[Update the target framework](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
 5. <span data-ttu-id="5c6b8-114">Çözümünüzdeki tüm dosyaları kaydedin ve kapatın</span><span class="sxs-lookup"><span data-stu-id="5c6b8-114">Save and close all files in your solution</span></span>
 6. <span data-ttu-id="5c6b8-115">Araçlar > komut satırı > seçin Geliştirici Komut İstemi</span><span class="sxs-lookup"><span data-stu-id="5c6b8-115">Select Tools > Command Line > Developer Command Prompt</span></span>
 7. <span data-ttu-id="5c6b8-116">Çözümdeki her proje için aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="5c6b8-116">For each project in the solution, run the following command:</span></span>
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
<span data-ttu-id="5c6b8-117">Projeleriniz diğer Microsoft. hisse paketlerini kullanıyorsa, bunlar için komutunu çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="5c6b8-117">If your projects use any other Microsoft.Quantum packages, run the command for these too.</span></span> 
 8. <span data-ttu-id="5c6b8-118">Komut istemi ' ni kapatın ve derleme > Oluştur çözüm ' u *seçin (* yeniden oluşturma işlemi ilk başarısız olacak şekilde çözümü yeniden oluşturma ' yı seçmeyin)</span><span class="sxs-lookup"><span data-stu-id="5c6b8-118">Close the command prompt and select Build > Build Solution (do *not* select Rebuild Solution, as rebuilding will initially fail)</span></span>

### <a name="in-visual-studio-code"></a><span data-ttu-id="5c6b8-119">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5c6b8-119">In Visual Studio Code</span></span>

1. <span data-ttu-id="5c6b8-120">Visual Studio Code, güncelleştirmek için projeyi içeren klasörü açın</span><span class="sxs-lookup"><span data-stu-id="5c6b8-120">In Visual Studio Code, open the folder containing the project to update</span></span>
1. <span data-ttu-id="5c6b8-121">Terminal > yeni Terminal ' i seçin</span><span class="sxs-lookup"><span data-stu-id="5c6b8-121">Select Terminal > New Terminal</span></span>
1. <span data-ttu-id="5c6b8-122">Komut satırını kullanarak güncelleştirme yönergelerini izleyin</span><span class="sxs-lookup"><span data-stu-id="5c6b8-122">Follow the instructions for updating using the command line</span></span>

### <a name="using-the-command-line"></a><span data-ttu-id="5c6b8-123">Komut satırını kullanma</span><span class="sxs-lookup"><span data-stu-id="5c6b8-123">Using the command line</span></span>

1. <span data-ttu-id="5c6b8-124">Proje dosyanızı içeren klasöre gidin</span><span class="sxs-lookup"><span data-stu-id="5c6b8-124">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="5c6b8-125">Şu komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="5c6b8-125">Run the following command:</span></span>
```bash
dotnet clean [project_name].csproj
```

3. <span data-ttu-id="5c6b8-126">. Csproj dosyalarınızın her birinde [hedef Framework 'ü](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) netcoreapp 3.0 'a (veya bir kitaplık projesi ise Netstandard 2.1) güncelleştirin</span><span class="sxs-lookup"><span data-stu-id="5c6b8-126">[Update the target framework](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
4. <span data-ttu-id="5c6b8-127">Şu komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="5c6b8-127">Run the following command:</span></span>
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
<span data-ttu-id="5c6b8-128">projeniz başka bir Microsoft. hisse paketleri kullanıyorsa, bu komutu da çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="5c6b8-128">if your project uses any other Microsoft.Quantum packages, run the command for these too.</span></span>

5. <span data-ttu-id="5c6b8-129">Tüm dosyaları Kaydet ve Kapat</span><span class="sxs-lookup"><span data-stu-id="5c6b8-129">Save and close all files</span></span>
6. <span data-ttu-id="5c6b8-130">Her proje bağımlılığı için 1-4 tekrarlayın, ardından ana projenizi içeren klasöre dönün ve çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="5c6b8-130">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a><span data-ttu-id="5c6b8-131">Python için IQ # güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="5c6b8-131">Update IQ# for Python</span></span>

1. <span data-ttu-id="5c6b8-132">`iqsharp` çekirdeğini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="5c6b8-132">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="5c6b8-133">`iqsharp` sürümünü doğrulama</span><span class="sxs-lookup"><span data-stu-id="5c6b8-133">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="5c6b8-134">Aşağıdaki çıktıyı görmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="5c6b8-134">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. <span data-ttu-id="5c6b8-135">`qsharp` paketini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="5c6b8-135">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="5c6b8-136">`qsharp` sürümünü doğrulama</span><span class="sxs-lookup"><span data-stu-id="5c6b8-136">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="5c6b8-137">Aşağıdaki çıktıyı görmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="5c6b8-137">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. <span data-ttu-id="5c6b8-138">`.qs` dosyalarınızın konumundan aşağıdaki komutu çalıştırın</span><span class="sxs-lookup"><span data-stu-id="5c6b8-138">Run the following command from the location of your `.qs` files</span></span>
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. <span data-ttu-id="5c6b8-139">Artık, var olan hisse programlarınızı çalıştırmak için güncelleştirilmiş QDK sürümünü kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5c6b8-139">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="5c6b8-140">Jupyıter Not defterleri için güncelleştirme IQ #</span><span class="sxs-lookup"><span data-stu-id="5c6b8-140">Update IQ# for Jupyter notebooks</span></span>

1. <span data-ttu-id="5c6b8-141">`iqsharp` çekirdeğini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="5c6b8-141">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="5c6b8-142">`iqsharp` sürümünü doğrulama</span><span class="sxs-lookup"><span data-stu-id="5c6b8-142">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="5c6b8-143">Aşağıdaki çıktıyı görmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="5c6b8-143">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. <span data-ttu-id="5c6b8-144">Jupyter Notebook bir hücreden aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="5c6b8-144">Run the following command from a cell in your Jupyter Notebook:</span></span>
    ```
    %workspace reload
    ```

1. <span data-ttu-id="5c6b8-145">Artık var olan bir Jupyter Not defterini açabilir ve güncelleştirilmiş QDK ile çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5c6b8-145">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="5c6b8-146">Visual Studio QDK uzantısını güncelleştir</span><span class="sxs-lookup"><span data-stu-id="5c6b8-146">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="5c6b8-147">Q # Visual Studio uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="5c6b8-147">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="5c6b8-148">Visual Studio, [hisse Için Visual Studio uzantısına](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) yönelik güncelleştirmeleri kabul etmenizi ister</span><span class="sxs-lookup"><span data-stu-id="5c6b8-148">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="5c6b8-149">Güncelleştirmeyi kabul et</span><span class="sxs-lookup"><span data-stu-id="5c6b8-149">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="5c6b8-150">Proje şablonları, uzantısıyla güncellenir.</span><span class="sxs-lookup"><span data-stu-id="5c6b8-150">The project templates are updated with the extension.</span></span> <span data-ttu-id="5c6b8-151">Güncelleştirilmiş şablonlar yalnızca yeni oluşturulan projeler için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="5c6b8-151">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="5c6b8-152">Uzantı güncelleniyorsa, mevcut projelerinizin kodu güncellenmez.</span><span class="sxs-lookup"><span data-stu-id="5c6b8-152">The code for your existing projects is not updated when the extension is updated.</span></span>

## <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="5c6b8-153">VS Code QDK uzantısını güncelleştir</span><span class="sxs-lookup"><span data-stu-id="5c6b8-153">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="5c6b8-154">Hisse VS Code uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="5c6b8-154">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="5c6b8-155">VS Code yeniden Başlat</span><span class="sxs-lookup"><span data-stu-id="5c6b8-155">Restart VS Code</span></span>
    - <span data-ttu-id="5c6b8-156">**Uzantılar** sekmesine gidin</span><span class="sxs-lookup"><span data-stu-id="5c6b8-156">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="5c6b8-157">Visual Studio Code uzantısı **için Microsoft Quantum Development Kit** seçin</span><span class="sxs-lookup"><span data-stu-id="5c6b8-157">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="5c6b8-158">Uzantıyı yeniden yükleme</span><span class="sxs-lookup"><span data-stu-id="5c6b8-158">Reload the extension</span></span>

1. <span data-ttu-id="5c6b8-159">Hisse projesi şablonlarını güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="5c6b8-159">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="5c6b8-160">**Görünüm** -> **Komut Paleti**’ne gidin</span><span class="sxs-lookup"><span data-stu-id="5c6b8-160">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="5c6b8-161">**S # seçin: proje şablonlarını Install**</span><span class="sxs-lookup"><span data-stu-id="5c6b8-161">Select **Q#: Install project templates**</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="5c6b8-162">C#`dotnet` komut satırı aracını kullanarak</span><span class="sxs-lookup"><span data-stu-id="5c6b8-162">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="5c6b8-163">.NET için hisse projesi şablonlarını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="5c6b8-163">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="5c6b8-164">Sırada ne var?</span><span class="sxs-lookup"><span data-stu-id="5c6b8-164">What's next?</span></span>

<span data-ttu-id="5c6b8-165">Artık, tercih ettiğiniz ortamınızda hisse geliştirme setini güncelleştirmiş olduğunuza göre, hisse ve programlarınızı geliştirmeye ve çalıştırmaya devam edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5c6b8-165">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="5c6b8-166">Henüz bir program yazmadıysanız, [ilk hisse al programınızı](xref:microsoft.quantum.write-program)kullanmaya başlamanızı sağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5c6b8-166">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
