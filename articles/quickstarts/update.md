---
title: Quantum geliştirme setini (QDK) güncelleştirme
description: Q# projelerinizi ve Microsoft Quantum geliştirme setinizi güncel sürüme nasıl güncelleştirebileceğinizi açıklar.
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 8d39716c4d4c96ad87862b4b185895aab66cd210
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274145"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum geliştirme setini (QDK) güncelleştirme

Microsoft Quantum geliştirme setini (QDK) en son sürüme güncelleştirmeyi öğrenin.

Bu makalede QDK’yi zaten yüklemiş olduğunuz varsayılır. İlk kez yüklüyorsanız lütfen [yükleme kılavuzuna](xref:microsoft.quantum.install) başvurun.

QDK’yi en son sürümde güncel tutmanız önerilir. En son QDK sürümüne yükseltmek için bu güncelleştirme kılavuzunu izleyin. İşlem iki bölümden oluşur:
1. Kodunuzu güncelleştirilmiş herhangi bir söz dizimi ile uyumlu hale getirmek için mevcut Q# dosyalarınızı ve projelerinizi güncelleştirme.
2. Seçili geliştirme ortamınız için QDK'nin kendisini güncelleştirme.

## <a name="updating-q-projects"></a>Q# Projelerini Güncelleştirme 

Q# işlemlerini barındırmak için C# veya Python kullanmanızdan bağımsız olarak Q# projelerinizi güncelleştirmek için bu yönergeleri izleyin.

1. İlk olarak, [.NET Core SDK 3.1](https://dotnet.microsoft.com/download)’in en son sürümüne sahip olup olmadığınızı kontrol edin. Komut isteminde aşağıdaki komutu çalıştırın:

    ```dotnetcli
    dotnet --version
    ```

    Çıkışın `3.1.100` veya daha yüksek olduğunu doğrulayın. Aksi takdirde [en son sürümü](https://dotnet.microsoft.com/download) yükleyip yeniden denetleyin. Ardından, kurulumunuza (Visual Studio, Visual Studio Code veya doğrudan komut satırı) bağlı olarak aşağıdaki yönergeleri izleyin.

### <a name="update-q-projects-in-visual-studio"></a>Visual Studio'daki Q# projelerini güncelleştirme
 
1. Visual Studio 2019’un en son sürümüne güncelleştirme hakkında yönergeler için [buraya](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) bakın.
2. Çözümünüzü Visual Studio’da açın.
3. Menüden **Derleme** -> **Çözümü Temizle**'yi seçin.
4. .csproj dosyalarınızın her birinde, hedef Framework’ü `netcoreapp3.1` (veya bir kitaplık projesi ise `netstandard2.1`) olarak güncelleştirin.
    Diğer bir deyişle, formun satırlarını düzenleyin:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    Hedef Framework’leri belirtme hakkında daha fazla ayrıntıyı [burada](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) bulabilirsiniz.

5. .csproj dosyalarının her birinde, aşağıdaki satırda gösterildiği gibi SDK’yı `Microsoft.Quantum.Sdk` olarak ayarlayın. Lütfen sürüm numarasının mevcut en son sürüme ait olduğuna ve bunu [sürüm notlarını](https://docs.microsoft.com/quantum/relnotes/) inceleyerek belirleyebileceğinize dikkat edin.

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. Çözümünüzdeki tüm dosyaları kaydedip kapatın.

7. **Araçlar** -> **Komut Satırı** -> **Geliştirici Komut İstemi**’ni seçin. Alternatif olarak, Visual Studio’daki paket yöneticisi konsolunu kullanabilirsiniz.

8. Çözümdeki her proje için, bu paketi kaldırmak üzere aşağıdaki **remove** komutunu çalıştırın:

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Projeleriniz başka Microsoft.Quantum veya Microsoft.Azure.Quantum paketleri (örneğin, Microsoft.Quantum.Numerics) kullanıyorsa, bunlar için **add** komutunu çalıştırarak kullanılan sürümü güncelleştirin.

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. Komut istemini kapatın ve **Derleme** ** -> Derleme Çözümü**’nü seçin (Yeniden Derleme Çözümü’nü *seçmeyin*).

Artık [Visual Studio QDK uzantınızı güncelleştirme](#update-visual-studio-qdk-extension) bölümüne atlayabilirsiniz.


### <a name="update-q-projects-in-visual-studio-code"></a>Visual Studio Code'daki Q# projelerini güncelleştirme

1. Visual Studio Code’da, güncelleştirilecek projeyi içeren klasörü açın.
2. **Terminal** -> **Yeni Terminal**’i seçin.
3. Komut satırını kullanarak güncelleştirme yönergelerini izleyin (doğrudan aşağıda verilmiştir).

### <a name="update-q-projects-using-the-command-line"></a>Komut satırını kullanarak Q# projelerini güncelleştirme

1. Ana proje dosyanızı içeren klasöre gidin.

2. Şu komutu çalıştırın:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. QDK’nin geçerli sürümünü belirleyin. Bunu bulmak için [sürüm notlarını](https://docs.microsoft.com/quantum/relnotes/) gözden geçirebilirsiniz. Sürüm, `0.11.2006.207` ile benzer bir biçimde olacaktır.

4. `.csproj` dosyalarınızın her birinde, aşağıdaki adımları izleyin:

    - Hedef Framework’ü `netcoreapp3.1` (veya bir kitaplık projesi ise `netstandard2.1`) olarak güncelleştirin. Diğer bir deyişle, formun satırlarını düzenleyin:

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        Hedef Framework’leri belirtme hakkında daha fazla ayrıntıyı [burada](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) bulabilirsiniz.

    - Proje tanımındaki SDK başvurusunu değiştirin. Sürüm numarasının **3. adımda** belirlenen değere karşılık geldiğinden emin olun.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - Varsa, aşağıdaki girdide belirtilecek olan `Microsoft.Quantum.Development.Kit` paketi başvurusunu kaldırın:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - Tüm Microsoft Quantum paketlerinin sürümünü, QDK'nin en son yayınlanan sürümüne (**3. adımda** belirlenmiştir) güncelleştirin. Bu paketler aşağıdaki desenlerle adlandırılır:

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        Paketlere yönelik başvurular aşağıdaki biçimdedir:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - Güncelleştirilen dosyayı kaydedin.

    - Aşağıdaki işlemleri gerçekleştirerek projenin bağımlılıklarını geri yükleyin:

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. Ana projenizi içeren klasöre geri gidin ve şunu çalıştırın:

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Q# projeleriniz güncelleştirildiğine göre, QDK’nin kendisini güncelleştirmek için aşağıdaki yönergeleri izleyin.

## <a name="updating-the-qdk"></a>QDK’yi güncelleştirme

QDK'yi güncelleştirme işlemi, geliştirme dilinize ve ortamınıza bağlı olarak değişir.
Aşağıda geliştirme ortamınızı seçin.

* [Python: IQ# uzantısını güncelleştirme](#update-iq-for-python)
* [Jupyter Not Defterleri: IQ# uzantısını güncelleştirme](#update-iq-for-jupyter-notebooks)
* [Visual Studio: QDK uzantısını güncelleştirme](#update-visual-studio-qdk-extension)
* [VS Code: QDK uzantısını güncelleştirme](#update-vs-code-qdk-extension)
* [Komut satırı ve C#: proje şablonlarını güncelleştirme](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>Python için IQ# uzantısını güncelleştirme

1. `iqsharp` çekirdeğini güncelleştirin 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. `iqsharp` sürümünü doğrulayın

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Aşağıdaki çıktıyı görmeniz gerekir:

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    `iqsharp` sürümünüz daha yüksekse endişelenmeyin, [en son sürüm](xref:microsoft.quantum.relnotes) ile eşleşmelidir.

3. `qsharp` paketini güncelleştirin

    ```
    pip install qsharp --upgrade
    ```

4. `qsharp` sürümünü doğrulayın

    ```
    pip show qsharp
    ```

    Aşağıdaki çıktıyı görmeniz gerekir:

    ```
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. `.qs` dosyalarınızın konumundan aşağıdaki komutu çalıştırın

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

6. Artık mevcut kuantum programlarınızı çalıştırmak için güncelleştirilmiş QDK sürümünü kullanabilirsiniz.

### <a name="update-iq-for-jupyter-notebooks"></a>Jupyter Not Defterleri için IQ# uzantısını güncelleştirme

1. `iqsharp` çekirdeğini güncelleştirin

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. `iqsharp` sürümünü doğrulayın

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Çıkışınızın aşağıdakine benzer olması gerekir:

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    `iqsharp` sürümünüz daha yüksekse endişelenmeyin, [en son sürüm](xref:microsoft.quantum.relnotes) ile eşleşmelidir.

3. Jupyter not defterinizdeki bir hücreden aşağıdaki komutu çalıştırın:

    ```
    %workspace reload
    ```

4. Artık mevcut bir Jupyter not defterini açabilir ve bunu güncelleştirilmiş QDK ile çalıştırabilirsiniz.

### <a name="update-visual-studio-qdk-extension"></a>Visual Studio QDK uzantısını güncelleştirme

1. Q# Visual Studio uzantısını güncelleştirin

    - Visual Studio [Quantum Visual Studio uzantısına](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) yönelik güncelleştirmeleri kabul etmenizi ister
    - Güncelleştirmeyi kabul edin

    > [!NOTE]
    > Proje şablonları uzantıyla birlikte güncelleştirilir. Güncelleştirilen şablonlar yalnızca yeni oluşturulan projeler için geçerlidir. Uzantı güncelleştirildiyse, mevcut projelerinizin kodu güncelleştirilmez.

### <a name="update-vs-code-qdk-extension"></a>VS Code QDK uzantısını güncelleştirme

1. Quantum VS Code uzantısını güncelleştirin

    - VS Code’u yeniden başlatın
    - **Uzantılar** sekmesine gidin
    - **Visual Studio Code için Microsoft Quantum geliştirme seti** uzantısını seçin
    - Uzantıyı yeniden yükleyin

2. Quantum proje şablonlarını güncelleştirin:

   - **Görünüm** -> **Komut Paleti**’ne gidin
   - **Q#: Proje şablonlarını yükle**’yi seçin
   - Birkaç saniye sonra, "proje şablonlarının başarıyla yüklendiğini" onaylayan bir açılır pencere görmeniz gerekir

### <a name="c-using-the-dotnet-command-line-tool"></a>`dotnet` komut satırı aracını kullanarak C#

1. .NET için Quantum proje şablonlarını güncelleştirme

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
