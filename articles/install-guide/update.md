---
title: Hisse geliştirme setini güncelleştirme (QDK)
description: 'Q # projelerinizi ve Microsoft Quantum Development Kit güncel sürüme nasıl güncelleşbileceğinizi açıklar.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 53f72f1d49ae32a5a8572a1cf68a66a1d9b45e4a
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426901"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="80073-103">Microsoft Quantum Development Kit güncelleştirme (QDK)</span><span class="sxs-lookup"><span data-stu-id="80073-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="80073-104">Microsoft Quantum Development Kit (QDK) ' i en son sürüme güncelleştirmeyi öğrenin.</span><span class="sxs-lookup"><span data-stu-id="80073-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="80073-105">Bu makalede, zaten QDK 'nin yüklü olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="80073-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="80073-106">Uygulamasını ilk kez yüklüyorsanız, lütfen [yükleme kılavuzuna](xref:microsoft.quantum.install)bakın.</span><span class="sxs-lookup"><span data-stu-id="80073-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="80073-107">En son QDK sürümüyle güncel tutmanız önerilir.</span><span class="sxs-lookup"><span data-stu-id="80073-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="80073-108">En son QDK sürümüne yükseltmek için bu güncelleştirme kılavuzunu izleyin.</span><span class="sxs-lookup"><span data-stu-id="80073-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="80073-109">İşlem iki bölümden oluşur:</span><span class="sxs-lookup"><span data-stu-id="80073-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="80073-110">kodunuzu güncelleştirilmiş herhangi bir sözdizimi ile hizalamak için mevcut Q # dosyalarınızı ve projelerinizi güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="80073-110">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="80073-111">seçtiğiniz geliştirme ortamınız için QDK 'yi güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="80073-111">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="80073-112">Q # projeleri güncelleştiriliyor</span><span class="sxs-lookup"><span data-stu-id="80073-112">Updating Q# Projects</span></span> 

<span data-ttu-id="80073-113">Q # işlemlerini barındırmak için C# veya Python kullanıp kullanmayacağınızı bağımsız olarak, Q # projelerinizi güncelleştirmek için bu yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="80073-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="80073-114">İlk olarak, [.NET Core SDK 3,1](https://dotnet.microsoft.com/download)' nin en son sürümüne sahip olup olmadığınızı kontrol edin.</span><span class="sxs-lookup"><span data-stu-id="80073-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="80073-115">Komut isteminde aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="80073-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="80073-116">Çıkışın `3.1.100` veya daha yüksek olduğunu doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="80073-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="80073-117">Aksi takdirde, [en son sürümü](https://dotnet.microsoft.com/download) yükleyip yeniden denetleyin.</span><span class="sxs-lookup"><span data-stu-id="80073-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="80073-118">Ardından, kuruluma (Visual Studio, Visual Studio Code veya doğrudan komut satırı) bağlı olarak aşağıdaki yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="80073-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="80073-119">Visual Studio 'da Q # projelerini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="80073-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="80073-120">Visual Studio 2019 ' nin en son sürümüne güncelleştirin, yönergeler için [buraya](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) bakın</span><span class="sxs-lookup"><span data-stu-id="80073-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="80073-121">Çözümünüzü Visual Studio 'da açın</span><span class="sxs-lookup"><span data-stu-id="80073-121">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="80073-122">Menüden, **Build**  ->  **temiz çözüm** oluştur ' u seçin.</span><span class="sxs-lookup"><span data-stu-id="80073-122">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="80073-123">. Csproj dosyalarınızın her birinde hedef Framework 'ü `netcoreapp3.1` (veya `netstandard2.1` bir kitaplık projesi ise) olarak güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="80073-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="80073-124">Diğer bir deyişle, formun satırlarını düzenleyin:</span><span class="sxs-lookup"><span data-stu-id="80073-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="80073-125">[Burada](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)hedef çerçeveleri belirterek daha fazla ayrıntı bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="80073-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="80073-126">Çözümünüzdeki tüm dosyaları kaydedin ve kapatın</span><span class="sxs-lookup"><span data-stu-id="80073-126">Save and close all files in your solution</span></span>
6. <span data-ttu-id="80073-127">**Araçlar**  ->  **komut satırı**  ->  **Geliştirici komut istemi** seçin</span><span class="sxs-lookup"><span data-stu-id="80073-127">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="80073-128">Çözümdeki her proje için aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="80073-128">For each project in the solution, run the following command:</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="80073-129">Projeleriniz başka Microsoft. hisse paketleri (ör. Microsoft. hisse. Numerics) kullanıyorsa, bu komutu da çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="80073-129">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="80073-130">Komut istemi ' ni kapatın ve **derleme**  ->  **Oluştur çözüm** ' ü *not* seçin (çözümü yeniden derle seçeneğini seçmeyin)</span><span class="sxs-lookup"><span data-stu-id="80073-130">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution)</span></span>

<span data-ttu-id="80073-131">Artık [Visual Studio QDK uzantınızı güncelleştirmeye](#update-visual-studio-qdk-extension)devam edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="80073-131">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="80073-132">Visual Studio Code Q # projelerini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="80073-132">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="80073-133">Visual Studio Code, güncelleştirmek için projeyi içeren klasörü açın</span><span class="sxs-lookup"><span data-stu-id="80073-133">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="80073-134">**Terminal**  ->  **yeni terminali** seçin</span><span class="sxs-lookup"><span data-stu-id="80073-134">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="80073-135">Komut satırını kullanarak güncelleştirme yönergelerini izleyin (doğrudan aşağıda)</span><span class="sxs-lookup"><span data-stu-id="80073-135">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="80073-136">Komut satırını kullanarak Q # projelerini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="80073-136">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="80073-137">Proje dosyanızı içeren klasöre gidin</span><span class="sxs-lookup"><span data-stu-id="80073-137">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="80073-138">Şu komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="80073-138">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="80073-139">. Csproj dosyalarınızın her birinde hedef Framework 'ü `netcoreapp3.1` (veya `netstandard2.1` bir kitaplık projesi ise) olarak güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="80073-139">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="80073-140">Diğer bir deyişle, formun satırlarını düzenleyin:</span><span class="sxs-lookup"><span data-stu-id="80073-140">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="80073-141">[Burada](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)hedef çerçeveleri belirterek daha fazla ayrıntı bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="80073-141">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="80073-142">Şu komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="80073-142">Run the following command:</span></span>

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    <span data-ttu-id="80073-143">Projeniz başka Microsoft. hisse paketleri (ör. Microsoft. hisse. Numerics) kullanıyorsa, bu komutu da çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="80073-143">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="80073-144">Tüm dosyaları kaydedin ve kapatın.</span><span class="sxs-lookup"><span data-stu-id="80073-144">Save and close all files.</span></span>
6. <span data-ttu-id="80073-145">Her proje bağımlılığı için 1-4 tekrarlayın, ardından ana projenizi içeren klasöre dönün ve çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="80073-145">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="80073-146">Q # projeleriniz artık güncelleştirilerek, QDK 'yi güncelleştirmek için aşağıdaki yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="80073-146">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="80073-147">QDK 'yi güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="80073-147">Updating the QDK</span></span>

<span data-ttu-id="80073-148">QDK 'yi güncelleştirme işlemi, geliştirme diliniz ve ortamınıza bağlı olarak değişir.</span><span class="sxs-lookup"><span data-stu-id="80073-148">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="80073-149">Aşağıda geliştirme ortamınızı seçin.</span><span class="sxs-lookup"><span data-stu-id="80073-149">Select your development environment below.</span></span>

* [<span data-ttu-id="80073-150">Python: IQ # uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="80073-150">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="80073-151">Jupyter Not defterleri: IQ # uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="80073-151">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="80073-152">Visual Studio: QDK uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="80073-152">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="80073-153">VS Code: QDK uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="80073-153">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="80073-154">Komut satırı ve C#: proje şablonlarını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="80073-154">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="80073-155">Python için IQ # güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="80073-155">Update IQ# for Python</span></span>

1. <span data-ttu-id="80073-156">Çekirdeği güncelleştirme `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="80073-156">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="80073-157">Sürümü doğrulama `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="80073-157">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="80073-158">Aşağıdaki çıktıyı görmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="80073-158">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="80073-159">Sürümünüz daha büyükse endişelenmeyin `iqsharp` , [en son sürümle](xref:microsoft.quantum.relnotes)eşleşmelidir.</span><span class="sxs-lookup"><span data-stu-id="80073-159">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="80073-160">Paketi güncelleştirme `qsharp`</span><span class="sxs-lookup"><span data-stu-id="80073-160">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="80073-161">Sürümü doğrulama `qsharp`</span><span class="sxs-lookup"><span data-stu-id="80073-161">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="80073-162">Aşağıdaki çıktıyı görmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="80073-162">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="80073-163">Dosyalarınızın konumundan aşağıdaki komutu çalıştırın `.qs`</span><span class="sxs-lookup"><span data-stu-id="80073-163">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="80073-164">Artık, var olan hisse programlarınızı çalıştırmak için güncelleştirilmiş QDK sürümünü kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="80073-164">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="80073-165">Jupyıter Not defterleri için güncelleştirme IQ #</span><span class="sxs-lookup"><span data-stu-id="80073-165">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="80073-166">Çekirdeği güncelleştirme `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="80073-166">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="80073-167">Sürümü doğrulama `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="80073-167">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="80073-168">Çıktın aşağıdakine benzer olması gerekir:</span><span class="sxs-lookup"><span data-stu-id="80073-168">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="80073-169">Sürümünüz daha büyükse endişelenmeyin `iqsharp` , [en son sürümle](xref:microsoft.quantum.relnotes)eşleşmelidir.</span><span class="sxs-lookup"><span data-stu-id="80073-169">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="80073-170">Jupyter Notebook bir hücreden aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="80073-170">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="80073-171">Artık var olan bir Jupyter Not defterini açabilir ve güncelleştirilmiş QDK ile çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="80073-171">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="80073-172">Visual Studio QDK uzantısını güncelleştir</span><span class="sxs-lookup"><span data-stu-id="80073-172">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="80073-173">Q # Visual Studio uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="80073-173">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="80073-174">Visual Studio, [hisse Için Visual Studio uzantısına](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) yönelik güncelleştirmeleri kabul etmenizi ister</span><span class="sxs-lookup"><span data-stu-id="80073-174">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="80073-175">Güncelleştirmeyi kabul et</span><span class="sxs-lookup"><span data-stu-id="80073-175">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="80073-176">Proje şablonları, uzantısıyla güncellenir.</span><span class="sxs-lookup"><span data-stu-id="80073-176">The project templates are updated with the extension.</span></span> <span data-ttu-id="80073-177">Güncelleştirilmiş şablonlar yalnızca yeni oluşturulan projeler için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="80073-177">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="80073-178">Uzantı güncelleniyorsa, mevcut projelerinizin kodu güncellenmez.</span><span class="sxs-lookup"><span data-stu-id="80073-178">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="80073-179">VS Code QDK uzantısını güncelleştir</span><span class="sxs-lookup"><span data-stu-id="80073-179">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="80073-180">Hisse VS Code uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="80073-180">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="80073-181">VS Code yeniden Başlat</span><span class="sxs-lookup"><span data-stu-id="80073-181">Restart VS Code</span></span>
    - <span data-ttu-id="80073-182">**Uzantılar** sekmesine gidin</span><span class="sxs-lookup"><span data-stu-id="80073-182">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="80073-183">Visual Studio Code uzantısı **için Microsoft Quantum Development Kit** seçin</span><span class="sxs-lookup"><span data-stu-id="80073-183">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="80073-184">Uzantıyı yeniden yükleme</span><span class="sxs-lookup"><span data-stu-id="80073-184">Reload the extension</span></span>

2. <span data-ttu-id="80073-185">Hisse projesi şablonlarını güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="80073-185">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="80073-186">**Görünüm**  ->  **komut paleti** 'ne git</span><span class="sxs-lookup"><span data-stu-id="80073-186">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="80073-187">**S # seçin: proje şablonlarını Install**</span><span class="sxs-lookup"><span data-stu-id="80073-187">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="80073-188">Birkaç saniye sonra, "proje şablonlarının başarıyla yüklendiğini" onaylayan bir açılan pencere almalısınız</span><span class="sxs-lookup"><span data-stu-id="80073-188">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="80073-189">C#, `dotnet` komut satırı aracını kullanarak</span><span class="sxs-lookup"><span data-stu-id="80073-189">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="80073-190">.NET için hisse projesi şablonlarını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="80073-190">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```