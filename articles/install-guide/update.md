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
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum Development Kit güncelleştirme (QDK)

Microsoft Quantum Development Kit (QDK) ' i en son sürüme güncelleştirmeyi öğrenin.

Bu makalede, zaten QDK 'nin yüklü olduğu varsayılır. Uygulamasını ilk kez yüklüyorsanız, lütfen [yükleme kılavuzuna](xref:microsoft.quantum.install)bakın.


## <a name="updating-q-projects"></a>Q # projeleri güncelleştiriliyor 

1. İlk olarak, [.NET Core SDK 3,0](https://dotnet.microsoft.com/download) ' nin en son sürümünü yükleyip komut isteminde aşağıdaki komutu çalıştırın:
```bash
dotnet --version
```
 Çıktının 3.0.100 veya üzeri olduğunu doğrulayın ve ardından kuruluma bağlı olarak aşağıdaki yönergeleri izleyin.

### <a name="in-visual-studio"></a>Visual Studio’da
 
 1. Visual Studio 2019 ' nin en son sürümüne güncelleştirin, yönergeler için [buraya](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) bakın
 2. Çözümünüzü Visual Studio 'da açın
 3. Menüden oluştur > Çözümü Temizle ' yi seçin 
 4. . Csproj dosyalarınızın her birinde [hedef Framework 'ü](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) netcoreapp 3.0 'a (veya bir kitaplık projesi ise Netstandard 2.1) güncelleştirin
 5. Çözümünüzdeki tüm dosyaları kaydedin ve kapatın
 6. Araçlar > komut satırı > seçin Geliştirici Komut İstemi
 7. Çözümdeki her proje için aşağıdaki komutu çalıştırın:
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
Projeleriniz diğer Microsoft. hisse paketlerini kullanıyorsa, bunlar için komutunu çalıştırın. 
 8. Komut istemi ' ni kapatın ve derleme > Oluştur çözüm ' u *seçin (* yeniden oluşturma işlemi ilk başarısız olacak şekilde çözümü yeniden oluşturma ' yı seçmeyin)

### <a name="in-visual-studio-code"></a>Visual Studio Code

1. Visual Studio Code, güncelleştirmek için projeyi içeren klasörü açın
1. Terminal > yeni Terminal ' i seçin
1. Komut satırını kullanarak güncelleştirme yönergelerini izleyin

### <a name="using-the-command-line"></a>Komut satırını kullanma

1. Proje dosyanızı içeren klasöre gidin
2. Şu komutu çalıştırın:
```bash
dotnet clean [project_name].csproj
```

3. . Csproj dosyalarınızın her birinde [hedef Framework 'ü](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) netcoreapp 3.0 'a (veya bir kitaplık projesi ise Netstandard 2.1) güncelleştirin
4. Şu komutu çalıştırın:
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
projeniz başka bir Microsoft. hisse paketleri kullanıyorsa, bu komutu da çalıştırın.

5. Tüm dosyaları Kaydet ve Kapat
6. Her proje bağımlılığı için 1-4 tekrarlayın, ardından ana projenizi içeren klasöre dönün ve çalıştırın:
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a>Python için IQ # güncelleştirme

1. `iqsharp` çekirdeğini güncelleştirme

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. `iqsharp` sürümünü doğrulama

    ```bash
    dotnet iqsharp --version
    ```

    Aşağıdaki çıktıyı görmeniz gerekir:

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. `qsharp` paketini güncelleştirme

    ```bash
    pip install qsharp --upgrade
    ```

1. `qsharp` sürümünü doğrulama

    ```bash
    pip show qsharp
    ```

    Aşağıdaki çıktıyı görmeniz gerekir:

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. `.qs` dosyalarınızın konumundan aşağıdaki komutu çalıştırın
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. Artık, var olan hisse programlarınızı çalıştırmak için güncelleştirilmiş QDK sürümünü kullanabilirsiniz.

## <a name="update-iq-for-jupyter-notebooks"></a>Jupyıter Not defterleri için güncelleştirme IQ #

1. `iqsharp` çekirdeğini güncelleştirme

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. `iqsharp` sürümünü doğrulama

    ```bash
    dotnet iqsharp --version
    ```

    Aşağıdaki çıktıyı görmeniz gerekir:

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. Jupyter Notebook bir hücreden aşağıdaki komutu çalıştırın:
    ```
    %workspace reload
    ```

1. Artık var olan bir Jupyter Not defterini açabilir ve güncelleştirilmiş QDK ile çalıştırabilirsiniz.

## <a name="update-visual-studio-qdk-extension"></a>Visual Studio QDK uzantısını güncelleştir

1. Q # Visual Studio uzantısını güncelleştirme

    - Visual Studio, [hisse Için Visual Studio uzantısına](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) yönelik güncelleştirmeleri kabul etmenizi ister
    - Güncelleştirmeyi kabul et

    > [!NOTE]
    > Proje şablonları, uzantısıyla güncellenir. Güncelleştirilmiş şablonlar yalnızca yeni oluşturulan projeler için geçerlidir. Uzantı güncelleniyorsa, mevcut projelerinizin kodu güncellenmez.

## <a name="update-vs-code-qdk-extension"></a>VS Code QDK uzantısını güncelleştir

1. Hisse VS Code uzantısını güncelleştirme

    - VS Code yeniden Başlat
    - **Uzantılar** sekmesine gidin
    - Visual Studio Code uzantısı **için Microsoft Quantum Development Kit** seçin
    - Uzantıyı yeniden yükleme

1. Hisse projesi şablonlarını güncelleştirin:

   - **Görünüm** -> **Komut Paleti**’ne gidin
   - **S # seçin: proje şablonlarını Install**

## <a name="c-using-the-dotnet-command-line-tool"></a>C#`dotnet` komut satırı aracını kullanarak

1. .NET için hisse projesi şablonlarını güncelleştirme

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>Sırada ne var?

Artık, tercih ettiğiniz ortamınızda hisse geliştirme setini güncelleştirmiş olduğunuza göre, hisse ve programlarınızı geliştirmeye ve çalıştırmaya devam edebilirsiniz. Henüz bir program yazmadıysanız, [ilk hisse al programınızı](xref:microsoft.quantum.write-program)kullanmaya başlamanızı sağlayabilirsiniz.
