---
title: Quantum geliştirme setini (QDK) güncelleştirme
description: Q# projelerinizi ve Microsoft Quantum geliştirme setinizi güncel sürüme nasıl güncelleştirebileceğinizi açıklar.
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 69b83997773896583258a4996a61b6f334edf407
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871408"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="1dcb6-103">Microsoft Quantum geliştirme setini (QDK) güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="1dcb6-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="1dcb6-104">Microsoft Quantum geliştirme setini (QDK) en son sürüme güncelleştirmeyi öğrenin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="1dcb6-105">Bu makalede QDK’yi zaten yüklemiş olduğunuz varsayılır.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="1dcb6-106">İlk kez yüklüyorsanız lütfen [yükleme kılavuzuna](xref:microsoft.quantum.install) başvurun.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="1dcb6-107">QDK’yi en son sürümde güncel tutmanız önerilir.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="1dcb6-108">En son QDK sürümüne yükseltmek için bu güncelleştirme kılavuzunu izleyin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="1dcb6-109">İşlem iki bölümden oluşur:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="1dcb6-110">Kodunuzu güncelleştirilmiş herhangi bir söz dizimi ile uyumlu hale getirmek için mevcut Q# dosyalarınızı ve projelerinizi güncelleştirme.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="1dcb6-111">Seçili geliştirme ortamınız için QDK'nin kendisini güncelleştirme.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-q-projects"></a><span data-ttu-id="1dcb6-112">Q# Projelerini Güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="1dcb6-112">Updating Q# Projects</span></span> 

<span data-ttu-id="1dcb6-113">Q# işlemlerini barındırmak için C# veya Python kullanmanızdan bağımsız olarak Q# projelerinizi güncelleştirmek için bu yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="1dcb6-114">İlk olarak, [.NET Core SDK 3.1](https://dotnet.microsoft.com/download)’in en son sürümüne sahip olup olmadığınızı kontrol edin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="1dcb6-115">Komut isteminde aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="1dcb6-116">Çıkışın `3.1.100` veya daha yüksek olduğunu doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="1dcb6-117">Aksi takdirde [en son sürümü](https://dotnet.microsoft.com/download) yükleyip yeniden denetleyin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="1dcb6-118">Ardından, kurulumunuza (Visual Studio, Visual Studio Code veya doğrudan komut satırı) bağlı olarak aşağıdaki yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="1dcb6-119">Visual Studio'daki Q# projelerini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="1dcb6-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="1dcb6-120">Visual Studio 2019’un en son sürümüne güncelleştirme hakkında yönergeler için [buraya](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) bakın.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="1dcb6-121">Çözümünüzü Visual Studio’da açın.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="1dcb6-122">Menüden **Derleme** -> **Çözümü Temizle**'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="1dcb6-123">.csproj dosyalarınızın her birinde, hedef Framework’ü `netcoreapp3.1` (veya bir kitaplık projesi ise `netstandard2.1`) olarak güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="1dcb6-124">Diğer bir deyişle, formun satırlarını düzenleyin:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="1dcb6-125">Hedef Framework’leri belirtme hakkında daha fazla ayrıntıyı [burada](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="1dcb6-126">.csproj dosyalarının her birinde, aşağıdaki satırda gösterildiği gibi SDK’yı `Microsoft.Quantum.Sdk` olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="1dcb6-127">Lütfen sürüm numarasının mevcut en son sürüme ait olduğuna ve bunu [sürüm notlarını](https://docs.microsoft.com/quantum/relnotes/) inceleyerek belirleyebileceğinize dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    ```

6. <span data-ttu-id="1dcb6-128">Çözümünüzdeki tüm dosyaları kaydedip kapatın.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="1dcb6-129">**Araçlar** -> **Komut Satırı** -> **Geliştirici Komut İstemi**’ni seçin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="1dcb6-130">Alternatif olarak, Visual Studio’daki paket yöneticisi konsolunu kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="1dcb6-131">Çözümdeki her proje için, bu paketi kaldırmak üzere aşağıdaki **remove** komutunu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="1dcb6-132">Projeleriniz başka Microsoft.Quantum veya Microsoft.Azure.Quantum paketleri (örneğin, Microsoft.Quantum.Numerics) kullanıyorsa, bunlar için **add** komutunu çalıştırarak kullanılan sürümü güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="1dcb6-133">Komut istemini kapatın ve **Derleme** \*\* -> Derleme Çözümü\*\*’nü seçin (Yeniden Derleme Çözümü’nü *seçmeyin*).</span><span class="sxs-lookup"><span data-stu-id="1dcb6-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="1dcb6-134">Artık [Visual Studio QDK uzantınızı güncelleştirme](#update-visual-studio-qdk-extension) bölümüne atlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="1dcb6-135">Visual Studio Code'daki Q# projelerini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="1dcb6-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="1dcb6-136">Visual Studio Code’da, güncelleştirilecek projeyi içeren klasörü açın.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="1dcb6-137">**Terminal** -> **Yeni Terminal**’i seçin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="1dcb6-138">Komut satırını kullanarak güncelleştirme yönergelerini izleyin (doğrudan aşağıda verilmiştir).</span><span class="sxs-lookup"><span data-stu-id="1dcb6-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="1dcb6-139">Komut satırını kullanarak Q# projelerini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="1dcb6-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="1dcb6-140">Ana proje dosyanızı içeren klasöre gidin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="1dcb6-141">Şu komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="1dcb6-142">QDK’nin geçerli sürümünü belirleyin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="1dcb6-143">Bunu bulmak için [sürüm notlarını](https://docs.microsoft.com/quantum/relnotes/) gözden geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="1dcb6-144">Sürüm, `0.12.20072031` ile benzer bir biçimde olacaktır.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-144">The version will be in a format similar to `0.12.20072031`.</span></span>

4. <span data-ttu-id="1dcb6-145">`.csproj` dosyalarınızın her birinde, aşağıdaki adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="1dcb6-146">Hedef Framework’ü `netcoreapp3.1` (veya bir kitaplık projesi ise `netstandard2.1`) olarak güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="1dcb6-147">Diğer bir deyişle, formun satırlarını düzenleyin:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="1dcb6-148">Hedef Framework’leri belirtme hakkında daha fazla ayrıntıyı [burada](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="1dcb6-149">Proje tanımındaki SDK başvurusunu değiştirin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="1dcb6-150">Sürüm numarasının **3. adımda** belirlenen değere karşılık geldiğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
        ```

    - <span data-ttu-id="1dcb6-151">Varsa, aşağıdaki girdide belirtilecek olan `Microsoft.Quantum.Development.Kit` paketi başvurusunu kaldırın:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="1dcb6-152">Tüm Microsoft Quantum paketlerinin sürümünü, QDK'nin en son yayınlanan sürümüne (**3. adımda** belirlenmiştir) güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="1dcb6-153">Bu paketler aşağıdaki desenlerle adlandırılır:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="1dcb6-154">Paketlere yönelik başvurular aşağıdaki biçimdedir:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.12.20072031" />
        ```

    - <span data-ttu-id="1dcb6-155">Güncelleştirilen dosyayı kaydedin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-155">Save the updated file.</span></span>

    - <span data-ttu-id="1dcb6-156">Aşağıdaki işlemleri gerçekleştirerek projenin bağımlılıklarını geri yükleyin:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="1dcb6-157">Ana projenizi içeren klasöre geri gidin ve şunu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="1dcb6-158">Q# projeleriniz güncelleştirildiğine göre, QDK’nin kendisini güncelleştirmek için aşağıdaki yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="1dcb6-159">QDK’yi güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="1dcb6-159">Updating the QDK</span></span>

<span data-ttu-id="1dcb6-160">QDK'yi güncelleştirme işlemi, geliştirme dilinize ve ortamınıza bağlı olarak değişir.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="1dcb6-161">Aşağıda geliştirme ortamınızı seçin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-161">Select your development environment below.</span></span>

* [<span data-ttu-id="1dcb6-162">Python: `qsharp` paketini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="1dcb6-162">Python: update the `qsharp` package</span></span>](#update-the-qsharp-python-package)
* [<span data-ttu-id="1dcb6-163">Jupyter Not Defterleri: IQ# çekirdeğini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="1dcb6-163">Jupyter Notebooks: update the IQ# kernel</span></span>](#update-the-iq-jupyter-kernel)
* [<span data-ttu-id="1dcb6-164">Visual Studio: QDK uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="1dcb6-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="1dcb6-165">VS Code: QDK uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="1dcb6-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="1dcb6-166">Komut satırı ve C#: proje şablonlarını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="1dcb6-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a><span data-ttu-id="1dcb6-167">`qsharp` Python paketini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="1dcb6-167">Update the `qsharp` Python package</span></span>

<span data-ttu-id="1dcb6-168">Güncelleştirme yordamı, ilk olarak Conda veya .NET CLI ve PIP kullanarak yükleyip yüklemediğinize bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-168">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="1dcb6-169">Conda kullanarak güncelleştirme (önerilir)</span><span class="sxs-lookup"><span data-stu-id="1dcb6-169">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="1dcb6-170">`qsharp` paketini yüklediğiniz Conda ortamını etkinleştirin ve sonra güncelleştirmek için şu komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-170">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="1dcb6-171">`.qs` dosyalarınızın konumundan şu komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-171">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="1dcb6-172">.NET CLI ve PIP kullanarak güncelleştirme (gelişmiş)</span><span class="sxs-lookup"><span data-stu-id="1dcb6-172">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="1dcb6-173">`iqsharp` çekirdeğini güncelleştirin</span><span class="sxs-lookup"><span data-stu-id="1dcb6-173">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="1dcb6-174">`iqsharp` sürümünü doğrulayın</span><span class="sxs-lookup"><span data-stu-id="1dcb6-174">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="1dcb6-175">Aşağıdaki çıktıyı görmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-175">You should see the following output:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="1dcb6-176">`iqsharp` sürümünüz daha yüksekse endişelenmeyin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-176">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="1dcb6-177">Sürümünüz [en son sürüm](xref:microsoft.quantum.relnotes) ile eşleşmelidir.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-177">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="1dcb6-178">`qsharp` paketini güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-178">Update the `qsharp` package:</span></span>

    ```
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="1dcb6-179">`qsharp` sürümünü doğrulayın:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-179">Verify the `qsharp` version:</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="1dcb6-180">Aşağıdaki çıktıyı görmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-180">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.12.2007.2031
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="1dcb6-181">`.qs` dosyalarınızın konumundan şu komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-181">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

<span data-ttu-id="1dcb6-182">Artık mevcut kuantum programlarınızı çalıştırmak için güncelleştirilmiş `qsharp` Python paketini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-182">You can now use the updated `qsharp` Python package to run your existing quantum programs.</span></span>

### <a name="update-the-iq-jupyter-kernel"></a><span data-ttu-id="1dcb6-183">IQ# Jupyter çekirdeğini güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="1dcb6-183">Update the IQ# Jupyter kernel</span></span>

<span data-ttu-id="1dcb6-184">Güncelleştirme yordamı, ilk olarak Conda veya .NET CLI ve PIP kullanarak yükleyip yüklemediğinize bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-184">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="1dcb6-185">Conda kullanarak güncelleştirme (önerilir)</span><span class="sxs-lookup"><span data-stu-id="1dcb6-185">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="1dcb6-186">`qsharp` paketini yüklediğiniz Conda ortamını etkinleştirin ve sonra güncelleştirmek için şu komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-186">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="1dcb6-187">Mevcut Q# Jupyter Not Defterlerinizin her birindeki bir hücreden aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-187">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="1dcb6-188">.NET CLI ve PIP kullanarak güncelleştirme (gelişmiş)</span><span class="sxs-lookup"><span data-stu-id="1dcb6-188">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="1dcb6-189">`Microsoft.Quantum.IQSharp` paketini güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-189">Update the `Microsoft.Quantum.IQSharp` package:</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="1dcb6-190">`iqsharp` sürümünü doğrulayın:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-190">Verify the `iqsharp` version:</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="1dcb6-191">Çıkışınızın aşağıdakine benzer olması gerekir:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-191">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="1dcb6-192">`iqsharp` sürümünüz daha yüksekse endişelenmeyin.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-192">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="1dcb6-193">Sürümünüz [en son sürüm](xref:microsoft.quantum.relnotes) ile eşleşmelidir.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-193">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="1dcb6-194">Mevcut Q# Jupyter Not Defterlerinizin her birindeki bir hücreden aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-194">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

***

<span data-ttu-id="1dcb6-195">Artık mevcut Q# Jupyter Not Defterlerinizi çalıştırmak için güncelleştirilmiş IQ# çekirdeğini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-195">You can now use the updated IQ# kernel to run your existing Q# Jupyter Notebooks.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="1dcb6-196">Visual Studio QDK uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="1dcb6-196">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="1dcb6-197">Q# Visual Studio uzantısını güncelleştirin</span><span class="sxs-lookup"><span data-stu-id="1dcb6-197">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="1dcb6-198">Visual Studio [Quantum Visual Studio uzantısına](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) yönelik güncelleştirmeleri kabul etmenizi ister</span><span class="sxs-lookup"><span data-stu-id="1dcb6-198">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="1dcb6-199">Güncelleştirmeyi kabul edin</span><span class="sxs-lookup"><span data-stu-id="1dcb6-199">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="1dcb6-200">Proje şablonları uzantıyla birlikte güncelleştirilir.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-200">The project templates are updated with the extension.</span></span> <span data-ttu-id="1dcb6-201">Güncelleştirilen şablonlar yalnızca yeni oluşturulan projeler için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-201">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="1dcb6-202">Uzantı güncelleştirildiyse, mevcut projelerinizin kodu güncelleştirilmez.</span><span class="sxs-lookup"><span data-stu-id="1dcb6-202">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="1dcb6-203">VS Code QDK uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="1dcb6-203">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="1dcb6-204">Quantum VS Code uzantısını güncelleştirin</span><span class="sxs-lookup"><span data-stu-id="1dcb6-204">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="1dcb6-205">VS Code’u yeniden başlatın</span><span class="sxs-lookup"><span data-stu-id="1dcb6-205">Restart VS Code</span></span>
    - <span data-ttu-id="1dcb6-206">**Uzantılar** sekmesine gidin</span><span class="sxs-lookup"><span data-stu-id="1dcb6-206">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="1dcb6-207">**Visual Studio Code için Microsoft Quantum geliştirme seti** uzantısını seçin</span><span class="sxs-lookup"><span data-stu-id="1dcb6-207">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="1dcb6-208">Uzantıyı yeniden yükleyin</span><span class="sxs-lookup"><span data-stu-id="1dcb6-208">Reload the extension</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="1dcb6-209">`dotnet` komut satırı aracını kullanarak C#</span><span class="sxs-lookup"><span data-stu-id="1dcb6-209">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="1dcb6-210">.NET için Quantum proje şablonlarını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="1dcb6-210">Update the Quantum project templates for .NET</span></span>

    <span data-ttu-id="1dcb6-211">Komut satırından:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-211">From the command line:</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

   <span data-ttu-id="1dcb6-212">Alternatif olarak komut satırı şablonlarını kullanmayı amaçlıyorsanız ve VS Code QDK uzantısı zaten yüklüyse proje şablonlarını uzantının kendisinden güncelleştirebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="1dcb6-212">Alternatively, if you intend to use the command line templates, and already have the VS Code QDK extension installed, you can update the project templates from the extension itself:</span></span>

   - [<span data-ttu-id="1dcb6-213">QDK uzantısını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="1dcb6-213">Update the QDK extension</span></span>](#update-vs-code-qdk-extension)
   - <span data-ttu-id="1dcb6-214">VS Code’da **Görünüm** -> **Komut Paleti**’ne gidin</span><span class="sxs-lookup"><span data-stu-id="1dcb6-214">In VS Code, go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="1dcb6-215">**Q#: Komut satırı proje şablonlarını yükle** komutunu seçin</span><span class="sxs-lookup"><span data-stu-id="1dcb6-215">Select **Q#: Install command line project templates**</span></span>
   - <span data-ttu-id="1dcb6-216">Birkaç saniye sonra, "proje şablonlarının başarıyla yüklendiğini" onaylayan bir açılır pencere görmeniz gerekir</span><span class="sxs-lookup"><span data-stu-id="1dcb6-216">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>
