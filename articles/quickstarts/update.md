---
title: Quantum geliştirme setini (QDK) güncelleştirme
description: Q# projelerinizi ve Microsoft Quantum geliştirme setinizi güncel sürüme nasıl güncelleştirebileceğinizi açıklar.
author: bradben
ms.author: v-benbra
ms.date: 5/30/2020
ms.topic: quickstart
uid: microsoft.quantum.update
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1b5def3226bd073c878f8573aaddd757d733ec48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858054"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum geliştirme setini (QDK) güncelleştirme

Microsoft Quantum geliştirme setini (QDK) en son sürüme güncelleştirmeyi öğrenin.

Bu makalede QDK’yi zaten yüklemiş olduğunuz varsayılır. İlk kez yüklüyorsanız lütfen [yükleme kılavuzuna](xref:microsoft.quantum.install) başvurun.

QDK’yi en son sürümde güncel tutmanız önerilir. En son QDK sürümüne yükseltmek için bu güncelleştirme kılavuzunu izleyin. İşlem iki bölümden oluşur:
1. Kodunuzu güncelleştirilmiş herhangi bir söz dizimi ile uyumlu hale getirmek için mevcut Q# dosyalarınızı ve projelerinizi güncelleştirme.
2. Seçili geliştirme ortamınız için QDK'nin kendisini güncelleştirme.

## <a name="updating-no-locq-projects"></a>Q# Projelerini Güncelleştirme 

Q# işlemlerini barındırmak için C# veya Python kullanmanızdan bağımsız olarak Q# projelerinizi güncelleştirmek için bu yönergeleri izleyin.

1. İlk olarak, [.NET Core SDK 3.1](https://dotnet.microsoft.com/download)’in en son sürümüne sahip olup olmadığınızı kontrol edin. Komut isteminde aşağıdaki komutu çalıştırın:

    ```dotnetcli
    dotnet --version
    ```

    Çıkışın `3.1.100` veya daha yüksek olduğunu doğrulayın. Aksi takdirde [en son sürümü](https://dotnet.microsoft.com/download) yükleyip yeniden denetleyin. Ardından, kurulumunuza (Visual Studio, Visual Studio Code veya doğrudan komut isteminden) bağlı olarak aşağıdaki yönergeleri izleyin.

### <a name="update-no-locq-projects-in-visual-studio"></a>Visual Studio'daki Q# projelerini güncelleştirme
 
1. Visual Studio 2019’un en son sürümüne güncelleştirme hakkında yönergeler için [buraya](https://docs.microsoft.com/visualstudio/install/update-visual-studio) bakın.
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
    <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
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


### <a name="update-no-locq-projects-in-visual-studio-code"></a>Visual Studio Code'da Q# projelerini güncelleştirme

1. Visual Studio Code’da, güncelleştirilecek projeyi içeren klasörü açın.
2. **Terminal** -> **Yeni Terminal**’i seçin.
3. Komut istemini kullanarak güncelleştirme yönergelerini izleyin (hemen aşağıda verilmiştir).

### <a name="update-no-locq-projects-using-the-command-prompt"></a>Komut istemini kullanarak Q# projelerini güncelleştirme

1. Ana proje dosyanızı içeren klasöre gidin.

2. Şu komutu çalıştırın:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. QDK’nin geçerli sürümünü belirleyin. Bunu bulmak için [sürüm notlarını](https://docs.microsoft.com/quantum/relnotes/) gözden geçirebilirsiniz. Sürüm, `0.12.20072031` ile benzer bir biçimde olacaktır.

4. `.csproj` dosyalarınızın her birinde, aşağıdaki adımları izleyin:

    - Hedef Framework’ü `netcoreapp3.1` (veya bir kitaplık projesi ise `netstandard2.1`) olarak güncelleştirin. Diğer bir deyişle, formun satırlarını düzenleyin:

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        Hedef Framework’leri belirtme hakkında daha fazla ayrıntıyı [burada](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) bulabilirsiniz.

    - Proje tanımındaki SDK başvurusunu değiştirin. Sürüm numarasının **3. adımda** belirlenen değere karşılık geldiğinden emin olun.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
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
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.12.20072031" />
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

* [Python: `qsharp` paketini güncelleştirme](#update-the-qsharp-python-package)
* [Jupyter Not Defterleri: IQ# çekirdeğini güncelleştirme](#update-the-iq-jupyter-kernel)
* [Visual Studio: QDK uzantısını güncelleştirme](#update-visual-studio-qdk-extension)
* [VS Code: QDK uzantısını güncelleştirme](#update-vs-code-qdk-extension)
* [Komut satırı ve C#: proje şablonlarını güncelleştirme](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a>`qsharp` Python paketini güncelleştirme

Güncelleştirme yordamı, ilk olarak Conda veya .NET CLI ve PIP kullanarak yükleyip yüklemediğinize bağlıdır.

#### <a name="update-using-conda-recommended"></a>[Conda kullanarak güncelleştirme (önerilir)](#tab/tabid-conda)

1. `qsharp` paketini yüklediğiniz Conda ortamını etkinleştirin ve sonra güncelleştirmek için şu komutu çalıştırın:

    ```
    conda update -c quantum-engineering qsharp
    ```

1. `.qs` dosyalarınızın konumundan şu komutu çalıştırın:

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[.NET CLI ve PIP kullanarak güncelleştirme (gelişmiş)](#tab/tabid-dotnetcli)

1. `iqsharp` çekirdeğini güncelleştirin 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. `iqsharp` sürümünü doğrulayın

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Aşağıdaki çıktıyı görmeniz gerekir:

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    `iqsharp` sürümünüz daha yüksekse endişelenmeyin. Sürümünüz [en son sürüm](xref:microsoft.quantum.relnotes) ile eşleşmelidir.

1. `qsharp` paketini güncelleştirin:

    ```
    pip install qsharp --upgrade
    ```

1. `qsharp` sürümünü doğrulayın:

    ```
    pip show qsharp
    ```

    Aşağıdaki çıktıyı görmeniz gerekir:

    ```
    Name: qsharp
    Version: 0.12.2007.2031
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. `.qs` dosyalarınızın konumundan şu komutu çalıştırın:

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

Artık mevcut kuantum programlarınızı çalıştırmak için güncelleştirilmiş `qsharp` Python paketini kullanabilirsiniz.

### <a name="update-the-ino-locq-jupyter-kernel"></a>IQ# Jupyter çekirdeğini güncelleştirme

Güncelleştirme yordamı, ilk olarak Conda veya .NET CLI ve PIP kullanarak yükleyip yüklemediğinize bağlıdır.

#### <a name="update-using-conda-recommended"></a>[Conda kullanarak güncelleştirme (önerilir)](#tab/tabid-conda)

1. `qsharp` paketini yüklediğiniz Conda ortamını etkinleştirin ve sonra güncelleştirmek için şu komutu çalıştırın:

    ```
    conda update -c quantum-engineering qsharp
    ```

1. Mevcut Q# Jupyter Not Defterlerinizin her birindeki bir hücreden aşağıdaki komutu çalıştırın:

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[.NET CLI ve PIP kullanarak güncelleştirme (gelişmiş)](#tab/tabid-dotnetcli)

1. `Microsoft.Quantum.IQSharp` paketini güncelleştirin:

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. `iqsharp` sürümünü doğrulayın:

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Çıkışınızın aşağıdakine benzer olması gerekir:

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    `iqsharp` sürümünüz daha yüksekse endişelenmeyin. Sürümünüz [en son sürüm](xref:microsoft.quantum.relnotes) ile eşleşmelidir.

1. Mevcut Q# Jupyter Not Defterlerinizin her birindeki bir hücreden aşağıdaki komutu çalıştırın:

    ```
    %workspace reload
    ```

**_

Artık mevcut Q# Jupyter Not Defterlerinizi çalıştırmak için güncelleştirilmiş IQ# çekirdeğini kullanabilirsiniz.

### <a name="update-visual-studio-qdk-extension"></a>Visual Studio QDK uzantısını güncelleştirme

1. Q# Visual Studio uzantısını güncelleştirin

    - Visual Studio [Quantum Visual Studio uzantısına](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) yönelik güncelleştirmeleri kabul etmenizi ister
    - Güncelleştirmeyi kabul edin

    > [!NOTE]
    > Proje şablonları uzantıyla birlikte güncelleştirilir. Güncelleştirilen şablonlar yalnızca yeni oluşturulan projeler için geçerlidir. Uzantı güncelleştirildiyse, mevcut projelerinizin kodu güncelleştirilmez.

### <a name="update-vs-code-qdk-extension"></a>VS Code QDK uzantısını güncelleştirme

1. Quantum VS Code uzantısını güncelleştirin

    - VS Code’u yeniden başlatın
    - _ *Extensions** sekmesine gidin
    - **Visual Studio Code için Microsoft Quantum geliştirme seti** uzantısını seçin
    - Uzantıyı yeniden yükleyin

### <a name="c-using-the-dotnet-command-line-tool"></a>`dotnet` komut satırı aracını kullanarak C#

1. .NET için Quantum proje şablonlarını güncelleştirme

    Komut isteminden:

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

   Alternatif olarak komut satırı şablonlarını kullanmayı amaçlıyorsanız ve VS Code QDK uzantısı zaten yüklüyse proje şablonlarını uzantının kendisinden güncelleştirebilirsiniz:

   - [QDK uzantısını güncelleştirme](#update-vs-code-qdk-extension)
   - VS Code’da **Görünüm** -> **Komut Paleti**’ne gidin
   - **Q# seçeneğini belirleyin: Komut satırı proje şablonlarını yükle** komutunu seçin
   - Birkaç saniye sonra, "proje şablonlarının başarıyla yüklendiğini" onaylayan bir açılır pencere görmeniz gerekir
