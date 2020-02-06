---
title: Microsoft Quantum Development Kit güncelleştirme hakkında bilgi edinin (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: f19285ae0e008b3460d06430a236f098d716e268
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036330"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum Development Kit güncelleştirme (QDK)

Microsoft Quantum Development Kit (QDK) ' i en son sürüme güncelleştirmeyi öğrenin.

Bu makalede, zaten QDK 'nin yüklü olduğu varsayılır. Uygulamasını ilk kez yüklüyorsanız, lütfen [yükleme kılavuzuna](xref:microsoft.quantum.install)bakın.

En son QDK sürümüyle güncel tutmanız önerilir. En son QDK sürümüne yükseltmek için bu güncelleştirme kılavuzunu izleyin. İşlem iki bölümden oluşur:
1. kodunuzu güncelleştirilmiş herhangi bir sözdizimi ile hizalamak için mevcut Q # dosyalarınızı ve projelerinizi güncelleştirme
2. seçtiğiniz geliştirme ortamınız için QDK 'yi güncelleştirme 

## <a name="updating-q-projects"></a>Q # projeleri güncelleştiriliyor 

Ya da Python 'u kullanarak C# q # işlemlerini barındırmanıza bakılmaksızın, q # projelerinizi güncelleştirmek için bu yönergeleri izleyin.

1. İlk olarak, [.NET Core SDK 3,1](https://dotnet.microsoft.com/download)' nin en son sürümüne sahip olup olmadığınızı kontrol edin. Komut isteminde aşağıdaki komutu çalıştırın:

    ```dotnetcli
    dotnet --version
    ```

    Çıkışın `3.1.100` veya daha yüksek olduğunu doğrulayın. Aksi takdirde, [en son sürümü](https://dotnet.microsoft.com/download) yükleyip yeniden denetleyin. Ardından, kuruluma (Visual Studio, Visual Studio Code veya doğrudan komut satırı) bağlı olarak aşağıdaki yönergeleri izleyin.

### <a name="update-q-projects-in-visual-studio"></a>Visual Studio 'da Q # projelerini güncelleştirme
 
1. Visual Studio 2019 ' nin en son sürümüne güncelleştirin, yönergeler için [buraya](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) bakın
2. Çözümünüzü Visual Studio 'da açın
3. Menüden **oluştur** -> **Çözümü Temizle** ' yi seçin
4. . Csproj dosyalarınızın her birinde, hedef çerçeveyi `netcoreapp3.0` (veya bir kitaplık projesi ise `netstandard2.1`) olarak güncelleştirin.
    Diğer bir deyişle, formun satırlarını düzenleyin:

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    [Burada](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)hedef çerçeveleri belirterek daha fazla ayrıntı bulabilirsiniz.
5. Çözümünüzdeki tüm dosyaları kaydedin ve kapatın
6. **Araçlar** -> **komut satırı** -> seçin **Geliştirici komut istemi**
7. Çözümdeki her proje için aşağıdaki komutu çalıştırın:

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Projeleriniz başka Microsoft. hisse paketleri (ör. Microsoft. hisse. Numerics) kullanıyorsa, bu komutu da çalıştırabilirsiniz.
8. Komut istemi ' ni kapatın ve **derleme** -> **Oluştur çözüm** ' u seçin (çözümü yeniden derle *seçeneğini seçmeyin)*

Artık [Visual Studio QDK uzantınızı güncelleştirmeye](#update-visual-studio-qdk-extension)devam edebilirsiniz.


### <a name="update-q-projects-in-visual-studio-code"></a>Visual Studio Code Q # projelerini güncelleştirme

1. Visual Studio Code, güncelleştirmek için projeyi içeren klasörü açın
2. **Terminal** -> **yeni Terminal** ' i seçin
3. Komut satırını kullanarak güncelleştirme yönergelerini izleyin (doğrudan aşağıda)

### <a name="update-q-projects-using-the-command-line"></a>Komut satırını kullanarak Q # projelerini güncelleştirme

1. Proje dosyanızı içeren klasöre gidin
2. Şu komutu çalıştırın:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. . Csproj dosyalarınızın her birinde, hedef çerçeveyi `netcoreapp3.0` (veya bir kitaplık projesi ise `netstandard2.1`) olarak güncelleştirin.
    Diğer bir deyişle, formun satırlarını düzenleyin:

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    [Burada](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)hedef çerçeveleri belirterek daha fazla ayrıntı bulabilirsiniz.
4. Şu komutu çalıştırın:

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    Projeniz başka Microsoft. hisse paketleri (ör. Microsoft. hisse. Numerics) kullanıyorsa, bu komutu da çalıştırabilirsiniz.
5. Tüm dosyaları kaydedin ve kapatın.
6. Her proje bağımlılığı için 1-4 tekrarlayın, ardından ana projenizi içeren klasöre dönün ve çalıştırın:

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

1. `iqsharp` çekirdeğini güncelleştirme 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. `iqsharp` sürümünü doğrulama

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Aşağıdaki çıktıyı görmeniz gerekir:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    `iqsharp` sürümünüz daha yüksekse endişelenmeyin, [en son sürümle](xref:microsoft.quantum.relnotes)eşleşmelidir.

3. `qsharp` paketini güncelleştirme

    ```bash
    pip install qsharp --upgrade
    ```

4. `qsharp` sürümünü doğrulama

    ```bash
    pip show qsharp
    ```

    Aşağıdaki çıktıyı görmeniz gerekir:

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. `.qs` dosyalarınızın konumundan aşağıdaki komutu çalıştırın

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. Artık, var olan hisse programlarınızı çalıştırmak için güncelleştirilmiş QDK sürümünü kullanabilirsiniz.

### <a name="update-iq-for-jupyter-notebooks"></a>Jupyıter Not defterleri için güncelleştirme IQ #

1. `iqsharp` çekirdeğini güncelleştirme

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. `iqsharp` sürümünü doğrulama

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Çıktın aşağıdakine benzer olması gerekir:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    `iqsharp` sürümünüz daha yüksekse endişelenmeyin, [en son sürümle](xref:microsoft.quantum.relnotes)eşleşmelidir.

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

   - **Görünüm** -> **Komut Paleti**’ne gidin
   - **S # seçin: proje şablonlarını Install**
   - Birkaç saniye sonra, "proje şablonlarının başarıyla yüklendiğini" onaylayan bir açılan pencere almalısınız

### <a name="c-using-the-dotnet-command-line-tool"></a>C#`dotnet` komut satırı aracını kullanarak

1. .NET için hisse projesi şablonlarını güncelleştirme

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>Sırada ne var?

Artık, tercih ettiğiniz ortamınızda hisse geliştirme setini güncelleştirmiş olduğunuza göre, hisse ve programlarınızı geliştirmeye ve çalıştırmaya devam edebilirsiniz. Henüz bir program yazmadıysanız, [ilk hisse al programınızı](xref:microsoft.quantum.write-program)kullanmaya başlamanızı sağlayabilirsiniz.
