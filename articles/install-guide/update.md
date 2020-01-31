---
title: Microsoft Quantum Development Kit güncelleştirme hakkında bilgi edinin (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ed2a90749bbe245dde97424fc3191682f995d85b
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819748"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="60fa0-102">Microsoft Quantum Development Kit güncelleştirme (QDK)</span><span class="sxs-lookup"><span data-stu-id="60fa0-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="60fa0-103">Microsoft Quantum Development Kit (QDK) ' i en son sürüme güncelleştirmeyi öğrenin.</span><span class="sxs-lookup"><span data-stu-id="60fa0-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="60fa0-104">Bu makalede, zaten QDK 'nin yüklü olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="60fa0-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="60fa0-105">Uygulamasını ilk kez yüklüyorsanız, lütfen [yükleme kılavuzuna](xref:microsoft.quantum.install)bakın.</span><span class="sxs-lookup"><span data-stu-id="60fa0-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="60fa0-106">En son QDK sürümüyle güncel tutmanız önerilir.</span><span class="sxs-lookup"><span data-stu-id="60fa0-106">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="60fa0-107">En son QDK sürümüne yükseltmek için bu güncelleştirme kılavuzunu izleyin.</span><span class="sxs-lookup"><span data-stu-id="60fa0-107">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="60fa0-108">İşlem iki bölümden oluşur:</span><span class="sxs-lookup"><span data-stu-id="60fa0-108">The process consists of two parts:</span></span>
1. <span data-ttu-id="60fa0-109">kodunuzu güncelleştirilmiş herhangi bir sözdizimi ile hizalamak için mevcut Q # dosyalarınızı ve projelerinizi güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="60fa0-109">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="60fa0-110">seçtiğiniz geliştirme ortamınız için QDK 'yi güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="60fa0-110">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="60fa0-111">Q # projeleri güncelleştiriliyor</span><span class="sxs-lookup"><span data-stu-id="60fa0-111">Updating Q# Projects</span></span> 

<span data-ttu-id="60fa0-112">Ya da Python 'u kullanarak C# q # işlemlerini barındırmanıza bakılmaksızın, q # projelerinizi güncelleştirmek için bu yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="60fa0-112">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="60fa0-113">İlk olarak, [.NET Core SDK 3,1](https://dotnet.microsoft.com/download)' nin en son sürümüne sahip olup olmadığınızı kontrol edin.</span><span class="sxs-lookup"><span data-stu-id="60fa0-113">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="60fa0-114">Komut isteminde aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="60fa0-114">Run the following command in the command prompt:</span></span>
    ```bash
    dotnet --version
    ```
<span data-ttu-id="60fa0-115">Çıkışın `3.1.100` veya daha yüksek olduğunu doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="60fa0-115">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="60fa0-116">Aksi takdirde, [en son sürümü](https://dotnet.microsoft.com/download) yükleyip yeniden denetleyin.</span><span class="sxs-lookup"><span data-stu-id="60fa0-116">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="60fa0-117">Ardından, kuruluma (Visual Studio, Visual Studio Code veya doğrudan komut satırı) bağlı olarak aşağıdaki yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="60fa0-117">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="60fa0-118">Visual Studio 'da Q # projelerini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="60fa0-118">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="60fa0-119">Visual Studio 2019 ' nin en son sürümüne güncelleştirin, yönergeler için [buraya](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) bakın</span><span class="sxs-lookup"><span data-stu-id="60fa0-119">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="60fa0-120">Çözümünüzü Visual Studio 'da açın</span><span class="sxs-lookup"><span data-stu-id="60fa0-120">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="60fa0-121">Menüden **oluştur** -> **Çözümü Temizle** ' yi seçin</span><span class="sxs-lookup"><span data-stu-id="60fa0-121">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="60fa0-122">. Csproj dosyalarınızın her birinde, hedef çerçeveyi `netcoreapp3.0` (veya bir kitaplık projesi ise `netstandard2.1`) olarak güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="60fa0-122">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="60fa0-123">Diğer bir deyişle, formun satırlarını düzenleyin:</span><span class="sxs-lookup"><span data-stu-id="60fa0-123">That is, edit lines of the form:</span></span>
    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```
    <span data-ttu-id="60fa0-124">[Burada](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)hedef çerçeveleri belirterek daha fazla ayrıntı bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60fa0-124">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="60fa0-125">Çözümünüzdeki tüm dosyaları kaydedin ve kapatın</span><span class="sxs-lookup"><span data-stu-id="60fa0-125">Save and close all files in your solution</span></span>
6. <span data-ttu-id="60fa0-126">**Araçlar** -> **komut satırı** -> seçin **Geliştirici komut istemi**</span><span class="sxs-lookup"><span data-stu-id="60fa0-126">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="60fa0-127">Çözümdeki her proje için aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="60fa0-127">For each project in the solution, run the following command:</span></span>
    ```bash
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```
    <span data-ttu-id="60fa0-128">Projeleriniz başka Microsoft. hisse paketleri (ör. Microsoft. hisse. Numerics) kullanıyorsa, bu komutu da çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60fa0-128">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="60fa0-129">Komut istemi ' ni kapatın ve **derleme** -> **Oluştur çözüm** ' u *seçin (* yeniden oluşturma Işlemi Ilk başarısız olacak şekilde çözümü yeniden oluşturma ' yı seçmeyin)</span><span class="sxs-lookup"><span data-stu-id="60fa0-129">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution, as rebuilding will initially fail)</span></span>

<span data-ttu-id="60fa0-130">Artık [Visual Studio QDK uzantınızı güncelleştirmeye](#update-visual-studio-qdk-extension)devam edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60fa0-130">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="60fa0-131">Visual Studio Code Q # projelerini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="60fa0-131">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="60fa0-132">Visual Studio Code, güncelleştirmek için projeyi içeren klasörü açın</span><span class="sxs-lookup"><span data-stu-id="60fa0-132">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="60fa0-133">**Terminal** -> **yeni Terminal** ' i seçin</span><span class="sxs-lookup"><span data-stu-id="60fa0-133">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="60fa0-134">Komut satırını kullanarak güncelleştirme yönergelerini izleyin (doğrudan aşağıda)</span><span class="sxs-lookup"><span data-stu-id="60fa0-134">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="60fa0-135">Komut satırını kullanarak Q # projelerini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="60fa0-135">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="60fa0-136">Proje dosyanızı içeren klasöre gidin</span><span class="sxs-lookup"><span data-stu-id="60fa0-136">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="60fa0-137">Şu komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="60fa0-137">Run the following command:</span></span>
    ```bash
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="60fa0-138">. Csproj dosyalarınızın her birinde, hedef çerçeveyi `netcoreapp3.0` (veya bir kitaplık projesi ise `netstandard2.1`) olarak güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="60fa0-138">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="60fa0-139">Diğer bir deyişle, formun satırlarını düzenleyin:</span><span class="sxs-lookup"><span data-stu-id="60fa0-139">That is, edit lines of the form:</span></span>
    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```
    <span data-ttu-id="60fa0-140">[Burada](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)hedef çerçeveleri belirterek daha fazla ayrıntı bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60fa0-140">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="60fa0-141">Şu komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="60fa0-141">Run the following command:</span></span>
    ```bash
    dotnet add package Microsoft.Quantum.Development.Kit
    ```
    <span data-ttu-id="60fa0-142">Projeniz başka Microsoft. hisse paketleri (ör. Microsoft. hisse. Numerics) kullanıyorsa, bu komutu da çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60fa0-142">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="60fa0-143">Tüm dosyaları kaydedin ve kapatın.</span><span class="sxs-lookup"><span data-stu-id="60fa0-143">Save and close all files.</span></span>
6. <span data-ttu-id="60fa0-144">Her proje bağımlılığı için 1-4 tekrarlayın, ardından ana projenizi içeren klasöre dönün ve çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="60fa0-144">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>
    ```bash
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="60fa0-145">Q # projeleriniz artık güncelleştirilerek, QDK 'yi güncelleştirmek için aşağıdaki yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="60fa0-145">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="60fa0-146">QDK 'yi güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="60fa0-146">Updating the QDK</span></span>

<span data-ttu-id="60fa0-147">QDK 'yi güncelleştirme işlemi, geliştirme diliniz ve ortamınıza bağlı olarak değişir.</span><span class="sxs-lookup"><span data-stu-id="60fa0-147">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="60fa0-148">Aşağıda geliştirme ortamınızı seçin.</span><span class="sxs-lookup"><span data-stu-id="60fa0-148">Select your development environment below.</span></span>

* [<span data-ttu-id="60fa0-149">Python: IQ # uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="60fa0-149">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="60fa0-150">Jupyter Not defterleri: IQ # uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="60fa0-150">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="60fa0-151">Visual Studio: QDK uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="60fa0-151">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="60fa0-152">VS Code: QDK uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="60fa0-152">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="60fa0-153">Komut satırı ve C#: proje şablonlarını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="60fa0-153">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="60fa0-154">Python için IQ # güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="60fa0-154">Update IQ# for Python</span></span>

1. <span data-ttu-id="60fa0-155">`iqsharp` çekirdeğini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="60fa0-155">Update the `iqsharp` kernel</span></span> 

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="60fa0-156">`iqsharp` sürümünü doğrulama</span><span class="sxs-lookup"><span data-stu-id="60fa0-156">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="60fa0-157">Aşağıdaki çıktıyı görmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="60fa0-157">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```
    <span data-ttu-id="60fa0-158">`iqsharp` sürümünüz daha yüksekse endişelenmeyin, [en son sürümle](xref:microsoft.quantum.relnotes)eşleşmelidir.</span><span class="sxs-lookup"><span data-stu-id="60fa0-158">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="60fa0-159">`qsharp` paketini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="60fa0-159">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="60fa0-160">`qsharp` sürümünü doğrulama</span><span class="sxs-lookup"><span data-stu-id="60fa0-160">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="60fa0-161">Aşağıdaki çıktıyı görmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="60fa0-161">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
5. <span data-ttu-id="60fa0-162">`.qs` dosyalarınızın konumundan aşağıdaki komutu çalıştırın</span><span class="sxs-lookup"><span data-stu-id="60fa0-162">Run the following command from the location of your `.qs` files</span></span>
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="60fa0-163">Artık, var olan hisse programlarınızı çalıştırmak için güncelleştirilmiş QDK sürümünü kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60fa0-163">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="60fa0-164">Jupyıter Not defterleri için güncelleştirme IQ #</span><span class="sxs-lookup"><span data-stu-id="60fa0-164">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="60fa0-165">`iqsharp` çekirdeğini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="60fa0-165">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="60fa0-166">`iqsharp` sürümünü doğrulama</span><span class="sxs-lookup"><span data-stu-id="60fa0-166">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="60fa0-167">Çıktın aşağıdakine benzer olması gerekir:</span><span class="sxs-lookup"><span data-stu-id="60fa0-167">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```
    <span data-ttu-id="60fa0-168">`iqsharp` sürümünüz daha yüksekse endişelenmeyin, [en son sürümle](xref:microsoft.quantum.relnotes)eşleşmelidir.</span><span class="sxs-lookup"><span data-stu-id="60fa0-168">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="60fa0-169">Jupyter Notebook bir hücreden aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="60fa0-169">Run the following command from a cell in your Jupyter Notebook:</span></span>
    ```
    %workspace reload
    ```

4. <span data-ttu-id="60fa0-170">Artık var olan bir Jupyter Not defterini açabilir ve güncelleştirilmiş QDK ile çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60fa0-170">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="60fa0-171">Visual Studio QDK uzantısını güncelleştir</span><span class="sxs-lookup"><span data-stu-id="60fa0-171">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="60fa0-172">Q # Visual Studio uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="60fa0-172">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="60fa0-173">Visual Studio, [hisse Için Visual Studio uzantısına](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) yönelik güncelleştirmeleri kabul etmenizi ister</span><span class="sxs-lookup"><span data-stu-id="60fa0-173">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="60fa0-174">Güncelleştirmeyi kabul et</span><span class="sxs-lookup"><span data-stu-id="60fa0-174">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="60fa0-175">Proje şablonları, uzantısıyla güncellenir.</span><span class="sxs-lookup"><span data-stu-id="60fa0-175">The project templates are updated with the extension.</span></span> <span data-ttu-id="60fa0-176">Güncelleştirilmiş şablonlar yalnızca yeni oluşturulan projeler için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="60fa0-176">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="60fa0-177">Uzantı güncelleniyorsa, mevcut projelerinizin kodu güncellenmez.</span><span class="sxs-lookup"><span data-stu-id="60fa0-177">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="60fa0-178">VS Code QDK uzantısını güncelleştir</span><span class="sxs-lookup"><span data-stu-id="60fa0-178">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="60fa0-179">Hisse VS Code uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="60fa0-179">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="60fa0-180">VS Code yeniden Başlat</span><span class="sxs-lookup"><span data-stu-id="60fa0-180">Restart VS Code</span></span>
    - <span data-ttu-id="60fa0-181">**Uzantılar** sekmesine gidin</span><span class="sxs-lookup"><span data-stu-id="60fa0-181">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="60fa0-182">Visual Studio Code uzantısı **için Microsoft Quantum Development Kit** seçin</span><span class="sxs-lookup"><span data-stu-id="60fa0-182">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="60fa0-183">Uzantıyı yeniden yükleme</span><span class="sxs-lookup"><span data-stu-id="60fa0-183">Reload the extension</span></span>

2. <span data-ttu-id="60fa0-184">Hisse projesi şablonlarını güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="60fa0-184">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="60fa0-185">**Görünüm** -> **Komut Paleti**’ne gidin</span><span class="sxs-lookup"><span data-stu-id="60fa0-185">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="60fa0-186">**S # seçin: proje şablonlarını Install**</span><span class="sxs-lookup"><span data-stu-id="60fa0-186">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="60fa0-187">Birkaç saniye sonra, "proje şablonlarının başarıyla yüklendiğini" onaylayan bir açılan pencere almalısınız</span><span class="sxs-lookup"><span data-stu-id="60fa0-187">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="60fa0-188">C#`dotnet` komut satırı aracını kullanarak</span><span class="sxs-lookup"><span data-stu-id="60fa0-188">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="60fa0-189">.NET için hisse projesi şablonlarını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="60fa0-189">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="60fa0-190">Sırada ne var?</span><span class="sxs-lookup"><span data-stu-id="60fa0-190">What's next?</span></span>

<span data-ttu-id="60fa0-191">Artık, tercih ettiğiniz ortamınızda hisse geliştirme setini güncelleştirmiş olduğunuza göre, hisse ve programlarınızı geliştirmeye ve çalıştırmaya devam edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60fa0-191">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="60fa0-192">Henüz bir program yazmadıysanız, [ilk hisse al programınızı](xref:microsoft.quantum.write-program)kullanmaya başlamanızı sağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="60fa0-192">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
