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
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum Development Kit güncelleştirme (QDK)

Microsoft Quantum Development Kit (QDK) ' i en son sürüme güncelleştirmeyi öğrenin.

Bu makalede, zaten QDK 'nin yüklü olduğu varsayılır. Uygulamasını ilk kez yüklüyorsanız, lütfen [yükleme kılavuzuna](xref:microsoft.quantum.install)bakın.

En son QDK sürümüyle güncel tutmanız önerilir. En son QDK sürümüne yükseltmek için bu güncelleştirme kılavuzunu izleyin. İşlem iki bölümden oluşur:
1. Kodunuzu güncelleştirilmiş herhangi bir sözdizimi ile hizalamak için mevcut Q # dosyalarınız ve projelerinizi güncelleştirme.
2. Seçtiğiniz geliştirme ortamınız için QDK 'yi güncelleştirme.

## <a name="updating-q-projects"></a>Q # projeleri güncelleştiriliyor 

Q # işlemlerini barındırmak için C# veya Python kullanıp kullanmayacağınızı bağımsız olarak, Q # projelerinizi güncelleştirmek için bu yönergeleri izleyin.

1. İlk olarak, [.NET Core SDK 3,1](https://dotnet.microsoft.com/download)' nin en son sürümüne sahip olup olmadığınızı kontrol edin. Komut isteminde aşağıdaki komutu çalıştırın:

    ```dotnetcli
    dotnet --version
    ```

    Çıkışın `3.1.100` veya daha yüksek olduğunu doğrulayın. Aksi takdirde, [en son sürümü](https://dotnet.microsoft.com/download) yükleyip yeniden denetleyin. Ardından, kuruluma (Visual Studio, Visual Studio Code veya doğrudan komut satırı) bağlı olarak aşağıdaki yönergeleri izleyin.

### <a name="update-q-projects-in-visual-studio"></a>Visual Studio 'da Q # projelerini güncelleştirme
 
1. Visual Studio 2019 ' nin en son sürümüne güncelleştirin, yönergeler için [buraya](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) bakın.
2. Çözümünüzü Visual Studio 'da açın.
3. Menüden, **Build**  ->  **temiz çözüm**oluştur ' u seçin.
4. . Csproj dosyalarınızın her birinde hedef Framework 'ü `netcoreapp3.1` (veya `netstandard2.1` bir kitaplık projesi ise) olarak güncelleştirin.
    Diğer bir deyişle, formun satırlarını düzenleyin:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    [Burada](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)hedef çerçeveleri belirterek daha fazla ayrıntı bulabilirsiniz.

5. . Csproj dosyalarının her birinde, `Microsoft.Quantum.Sdk` aşağıdaki satırda gösterildiği gıbı SDK 'yı olarak ayarlayın. Sürüm numarasının en son kullanılabilir olduğunu ve [sürüm notlarını](https://docs.microsoft.com/quantum/relnotes/)inceleyerek belirleyebileceğini lütfen unutmayın.

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. Çözümünüzdeki tüm dosyaları kaydedin ve kapatın.

7. **Araçlar**  ->  **komut satırı**  ->  **Geliştirici komut istemi**seçin. Alternatif olarak, Visual Studio 'da paket yönetim konsolunu kullanabilirsiniz.

8. Çözümdeki her proje için, bu paketi **kaldırmak** için aşağıdaki komutu çalıştırın:

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Projeleriniz başka Microsoft. hisse veya Microsoft. Azure. hisse paketleri (ör. Microsoft. hisse. Numerics) kullanıyorsa, kullanılan sürümü güncelleştirmek için bunlar için **Ekle** komutunu çalıştırın.

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. Komut istemi ' ni kapatın ve **derleme**  ->  **Oluştur çözüm** ' ü *not* seçin (çözümü yeniden derle seçeneğini seçmeyin).

Artık [Visual Studio QDK uzantınızı güncelleştirmeye](#update-visual-studio-qdk-extension)devam edebilirsiniz.


### <a name="update-q-projects-in-visual-studio-code"></a>Visual Studio Code Q # projelerini güncelleştirme

1. Visual Studio Code, güncelleştirmek için projeyi içeren klasörü açın.
2. **Terminal**  ->  **yeni Terminal**' i seçin.
3. Komut satırını kullanarak güncelleştirme yönergelerini izleyin (doğrudan aşağıda verilmiştir).

### <a name="update-q-projects-using-the-command-line"></a>Komut satırını kullanarak Q # projelerini güncelleştirme

1. Ana proje dosyanızı içeren klasöre gidin.

2. Şu komutu çalıştırın:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Geçerli QDK sürümünü saptayın. Bunu bulmak için [sürüm notlarını](https://docs.microsoft.com/quantum/relnotes/)gözden geçirebilirsiniz. Sürüm, şuna benzer bir biçimde olacaktır `0.11.2006.207` .

4. Her bir `.csproj` dosya için aşağıdaki adımları izleyin:

    - Hedef çerçeveyi `netcoreapp3.1` (veya `netstandard2.1` bir kitaplık projesi ise) olarak güncelleştirin. Diğer bir deyişle, formun satırlarını düzenleyin:

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        [Burada](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)hedef çerçeveleri belirterek daha fazla ayrıntı bulabilirsiniz.

    - Proje tanımındaki SDK başvurusunu değiştirin. Sürüm numarasının **Adım 3**' te belirlenen değere karşılık geldiğinden emin olun.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - Varsa `Microsoft.Quantum.Development.Kit` , aşağıdaki girişte belirtilecektir pakete olan başvuruyu kaldırın:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - Tüm Microsoft hisse paketlerinin sürümünü, QDK 'nin en son yayınlanan sürümüne ( **Adım 3**' te belirlenir) güncelleştirin. Bu paketler aşağıdaki desenlerle adlandırılır:

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        Paketlere yapılan başvurular aşağıdaki biçimdedir:

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

Q # projeleriniz artık güncelleştirilerek, QDK 'yi güncelleştirmek için aşağıdaki yönergeleri izleyin.

## <a name="updating-the-qdk"></a>QDK 'yi güncelleştirme

QDK 'yi güncelleştirme işlemi, geliştirme diliniz ve ortamınıza bağlı olarak değişir.
Aşağıda geliştirme ortamınızı seçin.

* [Python: IQ # uzantısını güncelleştirme](#update-iq-for-python)
* [Jupyter Not defterleri: IQ # uzantısını güncelleştirme](#update-iq-for-jupyter-notebooks)
* [Visual Studio: QDK uzantısını güncelleştirme](#update-visual-studio-qdk-extension)
* [VS Code: QDK uzantısını güncelleştirme](#update-vs-code-qdk-extension)
* [Komut satırı ve C#: proje şablonlarını güncelleştirme](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>Python için IQ # güncelleştirme

1. Çekirdeği güncelleştirme `iqsharp` 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Sürümü doğrulama `iqsharp`

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Aşağıdaki çıktıyı görmeniz gerekir:

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Sürümünüz daha büyükse endişelenmeyin `iqsharp` , [en son sürümle](xref:microsoft.quantum.relnotes)eşleşmelidir.

3. Paketi güncelleştirme `qsharp`

    ```
    pip install qsharp --upgrade
    ```

4. Sürümü doğrulama `qsharp`

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

5. Dosyalarınızın konumundan aşağıdaki komutu çalıştırın `.qs`

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

6. Artık, var olan hisse programlarınızı çalıştırmak için güncelleştirilmiş QDK sürümünü kullanabilirsiniz.

### <a name="update-iq-for-jupyter-notebooks"></a>Jupyıter Not defterleri için güncelleştirme IQ #

1. Çekirdeği güncelleştirme `iqsharp`

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Sürümü doğrulama `iqsharp`

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Çıktın aşağıdakine benzer olması gerekir:

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Sürümünüz daha büyükse endişelenmeyin `iqsharp` , [en son sürümle](xref:microsoft.quantum.relnotes)eşleşmelidir.

3. Jupyter Notebook bir hücreden aşağıdaki komutu çalıştırın:

    ```
    %workspace reload
    ```

4. Artık var olan bir Jupyter Not defterini açabilir ve güncelleştirilmiş QDK ile çalıştırabilirsiniz.

### <a name="update-visual-studio-qdk-extension"></a>Visual Studio QDK uzantısını güncelleştir

1. Q # Visual Studio uzantısını güncelleştirme

    - Visual Studio, [hisse Için Visual Studio uzantısına](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) yönelik güncelleştirmeleri kabul etmenizi ister
    - Güncelleştirmeyi kabul et

    > [!NOTE]
    > Proje şablonları, uzantısıyla güncellenir. Güncelleştirilmiş şablonlar yalnızca yeni oluşturulan projeler için geçerlidir. Uzantı güncelleniyorsa, mevcut projelerinizin kodu güncellenmez.

### <a name="update-vs-code-qdk-extension"></a>VS Code QDK uzantısını güncelleştir

1. Hisse VS Code uzantısını güncelleştirme

    - VS Code yeniden Başlat
    - **Uzantılar** sekmesine gidin
    - Visual Studio Code uzantısı **için Microsoft Quantum Development Kit** seçin
    - Uzantıyı yeniden yükleme

2. Hisse projesi şablonlarını güncelleştirin:

   - **Görünüm**  ->  **komut paleti** 'ne git
   - **S # seçin: proje şablonlarını Install**
   - Birkaç saniye sonra, "proje şablonlarının başarıyla yüklendiğini" onaylayan bir açılan pencere almalısınız

### <a name="c-using-the-dotnet-command-line-tool"></a>C#, `dotnet` komut satırı aracını kullanarak

1. .NET için hisse projesi şablonlarını güncelleştirme

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
