---
title: Microsoft Quantum Development Kit güncelleştirme hakkında bilgi edinin (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185860"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum Development Kit güncelleştirme (QDK)

Microsoft Quantum Development Kit (QDK) ' i en son sürüme güncelleştirmeyi öğrenin.

Bu makalede, zaten QDK 'nin yüklü olduğu varsayılır. Uygulamasını ilk kez yüklüyorsanız, lütfen [yükleme kılavuzuna](xref:microsoft.quantum.install)bakın.

Güncelleştirme adımları geliştirme ortamınıza bağlıdır. Aşağıdaki bölümlerde ortamınızı seçin.

## <a name="python"></a>Python

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
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
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
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. Artık, var olan hisse programlarınızı çalıştırmak için güncelleştirilmiş QDK sürümünü kullanabilirsiniz.

## <a name="jupyter-notebooks"></a>Jupyter notebooks

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
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. Artık var olan bir Jupyter Not defterini açabilir ve güncelleştirilmiş QDK ile çalıştırabilirsiniz.

## <a name="c-on-windows-using-visual-studio"></a>C#Windows 'da, Visual Studio 'Yu kullanarak

1. Q # Visual Studio uzantısını güncelleştirme

    - Visual Studio, [hisse Için Visual Studio uzantısına](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) yönelik güncelleştirmeleri kabul etmenizi ister
    - Güncelleştirmeyi kabul et

    > [!NOTE]
    > Proje şablonları, uzantısıyla güncellenir. Güncelleştirilmiş şablonlar yalnızca yeni oluşturulan projeler için geçerlidir. Uzantı güncelleniyorsa, mevcut projelerinizin kodu güncellenmez.

1. QDK paketlerini güncelleştirme

    - Mevcut bir uygulamayı aç
    - Çözüm Gezgini **bağımlılıkları** seçin
    - **NuGet Paketlerini Yönet** ' i seçin
    - **Microsoft. hisse** paketlerini en son sürüme güncelleştirin

1. Artık uygulamanızı en son QDK ile çalıştırabilirsiniz.

## <a name="c-using-vs-code"></a>C#VS Code kullanarak

1. Hisse VS Code uzantısını güncelleştirme

    - VS Code yeniden Başlat
    - **Uzantılar** sekmesine gidin
    - Visual Studio Code uzantısı **için Microsoft Quantum Development Kit** seçin
    - Uzantıyı yeniden yükleme

1. Hisse projesi şablonlarını güncelleştirin:

   - **Görüntüleme** -> **komut paleti** 'ne git
   - **S # seçin: proje şablonlarını Install**

1. Mevcut bir uygulamayı VS Code açın

   - Yeni Paket sürümlerini eklemek için. csproj dosyasını düzenleyin

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    Diğer `Microsoft.Quantum` paketlerini kullanıyorsanız, bunları da güncelleştirin.

1. Artık uygulamanızı güncelleştirilmiş QDK ile çalıştırabilirsiniz

## <a name="c-using-the-dotnet-command-line-tool"></a>C#`dotnet` komut satırı aracını kullanarak

1. .NET için hisse projesi şablonlarını güncelleştirme

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. Mevcut bir uygulamayı güncelleştirme ve çalıştırma

    - Uygulamanızdaki QDK paket sürümlerini güncelleştirme

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        Uygulamanız başka bir `Microsoft.Quantum` paketi kullanıyorsa, bunları da güncelleştirin.

    - Uygulamayı çalıştırma

        ```bash
        dotnet run
        ```

    - Uygulamanız yeni paket sürümleriyle çalışacak

## <a name="whats-next"></a>Sırada ne var?

Artık, tercih ettiğiniz ortamınızda hisse geliştirme setini güncelleştirmiş olduğunuza göre, hisse ve programlarınızı geliştirmeye ve çalıştırmaya devam edebilirsiniz. Henüz bir program yazmadıysanız, [ilk hisse al programınızı](xref:microsoft.quantum.write-program)kullanmaya başlamanızı sağlayabilirsiniz.
