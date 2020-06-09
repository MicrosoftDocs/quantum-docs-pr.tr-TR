---
title: Hisse geliştirme setini güncelleştirme (QDK)
description: 'Q # projelerinizi ve Microsoft Quantum Development Kit güncel sürüme nasıl güncelleşbileceğinizi açıklar.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 89db1a671767b0cc083a251918bbeeed2b39b883
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578190"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="17a3e-103">Microsoft Quantum Development Kit güncelleştirme (QDK)</span><span class="sxs-lookup"><span data-stu-id="17a3e-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="17a3e-104">Microsoft Quantum Development Kit (QDK) ' i en son sürüme güncelleştirmeyi öğrenin.</span><span class="sxs-lookup"><span data-stu-id="17a3e-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="17a3e-105">Bu makalede, zaten QDK 'nin yüklü olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="17a3e-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="17a3e-106">Uygulamasını ilk kez yüklüyorsanız, lütfen [yükleme kılavuzuna](xref:microsoft.quantum.install)bakın.</span><span class="sxs-lookup"><span data-stu-id="17a3e-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="17a3e-107">En son QDK sürümüyle güncel tutmanız önerilir.</span><span class="sxs-lookup"><span data-stu-id="17a3e-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="17a3e-108">En son QDK sürümüne yükseltmek için bu güncelleştirme kılavuzunu izleyin.</span><span class="sxs-lookup"><span data-stu-id="17a3e-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="17a3e-109">İşlem iki bölümden oluşur:</span><span class="sxs-lookup"><span data-stu-id="17a3e-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="17a3e-110">Kodunuzu güncelleştirilmiş herhangi bir sözdizimi ile hizalamak için mevcut Q # dosyalarınız ve projelerinizi güncelleştirme.</span><span class="sxs-lookup"><span data-stu-id="17a3e-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="17a3e-111">Seçtiğiniz geliştirme ortamınız için QDK 'yi güncelleştirme.</span><span class="sxs-lookup"><span data-stu-id="17a3e-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-q-projects"></a><span data-ttu-id="17a3e-112">Q # projeleri güncelleştiriliyor</span><span class="sxs-lookup"><span data-stu-id="17a3e-112">Updating Q# Projects</span></span> 

<span data-ttu-id="17a3e-113">Q # işlemlerini barındırmak için C# veya Python kullanıp kullanmayacağınızı bağımsız olarak, Q # projelerinizi güncelleştirmek için bu yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="17a3e-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="17a3e-114">İlk olarak, [.NET Core SDK 3,1](https://dotnet.microsoft.com/download)' nin en son sürümüne sahip olup olmadığınızı kontrol edin.</span><span class="sxs-lookup"><span data-stu-id="17a3e-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="17a3e-115">Komut isteminde aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="17a3e-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="17a3e-116">Çıkışın `3.1.100` veya daha yüksek olduğunu doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="17a3e-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="17a3e-117">Aksi takdirde, [en son sürümü](https://dotnet.microsoft.com/download) yükleyip yeniden denetleyin.</span><span class="sxs-lookup"><span data-stu-id="17a3e-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="17a3e-118">Ardından, kuruluma (Visual Studio, Visual Studio Code veya doğrudan komut satırı) bağlı olarak aşağıdaki yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="17a3e-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="17a3e-119">Visual Studio 'da Q # projelerini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="17a3e-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="17a3e-120">Visual Studio 2019 ' nin en son sürümüne güncelleştirin, yönergeler için [buraya](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) bakın.</span><span class="sxs-lookup"><span data-stu-id="17a3e-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="17a3e-121">Çözümünüzü Visual Studio 'da açın.</span><span class="sxs-lookup"><span data-stu-id="17a3e-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="17a3e-122">Menüden, **Build**  ->  **temiz çözüm**oluştur ' u seçin.</span><span class="sxs-lookup"><span data-stu-id="17a3e-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="17a3e-123">. Csproj dosyalarınızın her birinde hedef Framework 'ü `netcoreapp3.1` (veya `netstandard2.1` bir kitaplık projesi ise) olarak güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="17a3e-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="17a3e-124">Diğer bir deyişle, formun satırlarını düzenleyin:</span><span class="sxs-lookup"><span data-stu-id="17a3e-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="17a3e-125">[Burada](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)hedef çerçeveleri belirterek daha fazla ayrıntı bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="17a3e-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="17a3e-126">. Csproj dosyalarının her birinde, `Microsoft.Quantum.Sdk` aşağıdaki satırda gösterildiği gıbı SDK 'yı olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="17a3e-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="17a3e-127">Sürüm numarasının en son kullanılabilir olduğunu ve [sürüm notlarını](https://docs.microsoft.com/quantum/relnotes/)inceleyerek belirleyebileceğini lütfen unutmayın.</span><span class="sxs-lookup"><span data-stu-id="17a3e-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. <span data-ttu-id="17a3e-128">Çözümünüzdeki tüm dosyaları kaydedin ve kapatın.</span><span class="sxs-lookup"><span data-stu-id="17a3e-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="17a3e-129">**Araçlar**  ->  **komut satırı**  ->  **Geliştirici komut istemi**seçin.</span><span class="sxs-lookup"><span data-stu-id="17a3e-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="17a3e-130">Alternatif olarak, Visual Studio 'da paket yönetim konsolunu kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="17a3e-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="17a3e-131">Çözümdeki her proje için, bu paketi **kaldırmak** için aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="17a3e-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="17a3e-132">Projeleriniz başka Microsoft. hisse veya Microsoft. Azure. hisse paketleri (ör. Microsoft. hisse. Numerics) kullanıyorsa, kullanılan sürümü güncelleştirmek için bunlar için **Ekle** komutunu çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="17a3e-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="17a3e-133">Komut istemi ' ni kapatın ve **derleme**  ->  **Oluştur çözüm** ' ü *not* seçin (çözümü yeniden derle seçeneğini seçmeyin).</span><span class="sxs-lookup"><span data-stu-id="17a3e-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="17a3e-134">Artık [Visual Studio QDK uzantınızı güncelleştirmeye](#update-visual-studio-qdk-extension)devam edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="17a3e-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="17a3e-135">Visual Studio Code Q # projelerini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="17a3e-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="17a3e-136">Visual Studio Code, güncelleştirmek için projeyi içeren klasörü açın.</span><span class="sxs-lookup"><span data-stu-id="17a3e-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="17a3e-137">**Terminal**  ->  **yeni Terminal**' i seçin.</span><span class="sxs-lookup"><span data-stu-id="17a3e-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="17a3e-138">Komut satırını kullanarak güncelleştirme yönergelerini izleyin (doğrudan aşağıda verilmiştir).</span><span class="sxs-lookup"><span data-stu-id="17a3e-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="17a3e-139">Komut satırını kullanarak Q # projelerini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="17a3e-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="17a3e-140">Ana proje dosyanızı içeren klasöre gidin.</span><span class="sxs-lookup"><span data-stu-id="17a3e-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="17a3e-141">Şu komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="17a3e-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="17a3e-142">Geçerli QDK sürümünü saptayın.</span><span class="sxs-lookup"><span data-stu-id="17a3e-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="17a3e-143">Bunu bulmak için [sürüm notlarını](https://docs.microsoft.com/quantum/relnotes/)gözden geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="17a3e-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="17a3e-144">Sürüm, şuna benzer bir biçimde olacaktır `0.11.2006.207` .</span><span class="sxs-lookup"><span data-stu-id="17a3e-144">The version will be in a format similar to `0.11.2006.207`.</span></span>

4. <span data-ttu-id="17a3e-145">Her bir `.csproj` dosya için aşağıdaki adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="17a3e-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="17a3e-146">Hedef çerçeveyi `netcoreapp3.1` (veya `netstandard2.1` bir kitaplık projesi ise) olarak güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="17a3e-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="17a3e-147">Diğer bir deyişle, formun satırlarını düzenleyin:</span><span class="sxs-lookup"><span data-stu-id="17a3e-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="17a3e-148">[Burada](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)hedef çerçeveleri belirterek daha fazla ayrıntı bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="17a3e-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="17a3e-149">Proje tanımındaki SDK başvurusunu değiştirin.</span><span class="sxs-lookup"><span data-stu-id="17a3e-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="17a3e-150">Sürüm numarasının **Adım 3**' te belirlenen değere karşılık geldiğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="17a3e-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - <span data-ttu-id="17a3e-151">Varsa `Microsoft.Quantum.Development.Kit` , aşağıdaki girişte belirtilecektir pakete olan başvuruyu kaldırın:</span><span class="sxs-lookup"><span data-stu-id="17a3e-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="17a3e-152">Tüm Microsoft hisse paketlerinin sürümünü, QDK 'nin en son yayınlanan sürümüne ( **Adım 3**' te belirlenir) güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="17a3e-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="17a3e-153">Bu paketler aşağıdaki desenlerle adlandırılır:</span><span class="sxs-lookup"><span data-stu-id="17a3e-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="17a3e-154">Paketlere yapılan başvurular aşağıdaki biçimdedir:</span><span class="sxs-lookup"><span data-stu-id="17a3e-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - <span data-ttu-id="17a3e-155">Güncelleştirilen dosyayı kaydedin.</span><span class="sxs-lookup"><span data-stu-id="17a3e-155">Save the updated file.</span></span>

    - <span data-ttu-id="17a3e-156">Aşağıdaki işlemleri gerçekleştirerek projenin bağımlılıklarını geri yükleyin:</span><span class="sxs-lookup"><span data-stu-id="17a3e-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="17a3e-157">Ana projenizi içeren klasöre geri gidin ve şunu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="17a3e-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="17a3e-158">Q # projeleriniz artık güncelleştirilerek, QDK 'yi güncelleştirmek için aşağıdaki yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="17a3e-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="17a3e-159">QDK 'yi güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="17a3e-159">Updating the QDK</span></span>

<span data-ttu-id="17a3e-160">QDK 'yi güncelleştirme işlemi, geliştirme diliniz ve ortamınıza bağlı olarak değişir.</span><span class="sxs-lookup"><span data-stu-id="17a3e-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="17a3e-161">Aşağıda geliştirme ortamınızı seçin.</span><span class="sxs-lookup"><span data-stu-id="17a3e-161">Select your development environment below.</span></span>

* [<span data-ttu-id="17a3e-162">Python: IQ # uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="17a3e-162">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="17a3e-163">Jupyter Not defterleri: IQ # uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="17a3e-163">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="17a3e-164">Visual Studio: QDK uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="17a3e-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="17a3e-165">VS Code: QDK uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="17a3e-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="17a3e-166">Komut satırı ve C#: proje şablonlarını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="17a3e-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="17a3e-167">Python için IQ # güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="17a3e-167">Update IQ# for Python</span></span>

1. <span data-ttu-id="17a3e-168">Çekirdeği güncelleştirme `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="17a3e-168">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="17a3e-169">Sürümü doğrulama `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="17a3e-169">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="17a3e-170">Aşağıdaki çıktıyı görmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="17a3e-170">You should see the following output:</span></span>

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="17a3e-171">Sürümünüz daha büyükse endişelenmeyin `iqsharp` , [en son sürümle](xref:microsoft.quantum.relnotes)eşleşmelidir.</span><span class="sxs-lookup"><span data-stu-id="17a3e-171">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="17a3e-172">Paketi güncelleştirme `qsharp`</span><span class="sxs-lookup"><span data-stu-id="17a3e-172">Update the `qsharp` package</span></span>

    ```
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="17a3e-173">Sürümü doğrulama `qsharp`</span><span class="sxs-lookup"><span data-stu-id="17a3e-173">Verify the `qsharp` version</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="17a3e-174">Aşağıdaki çıktıyı görmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="17a3e-174">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="17a3e-175">Dosyalarınızın konumundan aşağıdaki komutu çalıştırın `.qs`</span><span class="sxs-lookup"><span data-stu-id="17a3e-175">Run the following command from the location of your `.qs` files</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="17a3e-176">Artık, var olan hisse programlarınızı çalıştırmak için güncelleştirilmiş QDK sürümünü kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="17a3e-176">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="17a3e-177">Jupyıter Not defterleri için güncelleştirme IQ #</span><span class="sxs-lookup"><span data-stu-id="17a3e-177">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="17a3e-178">Çekirdeği güncelleştirme `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="17a3e-178">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="17a3e-179">Sürümü doğrulama `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="17a3e-179">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="17a3e-180">Çıktın aşağıdakine benzer olması gerekir:</span><span class="sxs-lookup"><span data-stu-id="17a3e-180">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="17a3e-181">Sürümünüz daha büyükse endişelenmeyin `iqsharp` , [en son sürümle](xref:microsoft.quantum.relnotes)eşleşmelidir.</span><span class="sxs-lookup"><span data-stu-id="17a3e-181">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="17a3e-182">Jupyter Notebook bir hücreden aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="17a3e-182">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="17a3e-183">Artık var olan bir Jupyter Not defterini açabilir ve güncelleştirilmiş QDK ile çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="17a3e-183">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="17a3e-184">Visual Studio QDK uzantısını güncelleştir</span><span class="sxs-lookup"><span data-stu-id="17a3e-184">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="17a3e-185">Q # Visual Studio uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="17a3e-185">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="17a3e-186">Visual Studio, [hisse Için Visual Studio uzantısına](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) yönelik güncelleştirmeleri kabul etmenizi ister</span><span class="sxs-lookup"><span data-stu-id="17a3e-186">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="17a3e-187">Güncelleştirmeyi kabul et</span><span class="sxs-lookup"><span data-stu-id="17a3e-187">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="17a3e-188">Proje şablonları, uzantısıyla güncellenir.</span><span class="sxs-lookup"><span data-stu-id="17a3e-188">The project templates are updated with the extension.</span></span> <span data-ttu-id="17a3e-189">Güncelleştirilmiş şablonlar yalnızca yeni oluşturulan projeler için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="17a3e-189">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="17a3e-190">Uzantı güncelleniyorsa, mevcut projelerinizin kodu güncellenmez.</span><span class="sxs-lookup"><span data-stu-id="17a3e-190">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="17a3e-191">VS Code QDK uzantısını güncelleştir</span><span class="sxs-lookup"><span data-stu-id="17a3e-191">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="17a3e-192">Hisse VS Code uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="17a3e-192">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="17a3e-193">VS Code yeniden Başlat</span><span class="sxs-lookup"><span data-stu-id="17a3e-193">Restart VS Code</span></span>
    - <span data-ttu-id="17a3e-194">**Uzantılar** sekmesine gidin</span><span class="sxs-lookup"><span data-stu-id="17a3e-194">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="17a3e-195">Visual Studio Code uzantısı **için Microsoft Quantum Development Kit** seçin</span><span class="sxs-lookup"><span data-stu-id="17a3e-195">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="17a3e-196">Uzantıyı yeniden yükleme</span><span class="sxs-lookup"><span data-stu-id="17a3e-196">Reload the extension</span></span>

2. <span data-ttu-id="17a3e-197">Hisse projesi şablonlarını güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="17a3e-197">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="17a3e-198">**Görünüm**  ->  **komut paleti** 'ne git</span><span class="sxs-lookup"><span data-stu-id="17a3e-198">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="17a3e-199">**S # seçin: proje şablonlarını Install**</span><span class="sxs-lookup"><span data-stu-id="17a3e-199">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="17a3e-200">Birkaç saniye sonra, "proje şablonlarının başarıyla yüklendiğini" onaylayan bir açılan pencere almalısınız</span><span class="sxs-lookup"><span data-stu-id="17a3e-200">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="17a3e-201">C#, `dotnet` komut satırı aracını kullanarak</span><span class="sxs-lookup"><span data-stu-id="17a3e-201">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="17a3e-202">.NET için hisse projesi şablonlarını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="17a3e-202">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
