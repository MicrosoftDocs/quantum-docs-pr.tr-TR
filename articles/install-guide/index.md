---
title: Microsoft Quantum Development Kit (QDK) yüklemeyi öğrenin
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 3ec53934436b47908fd4d794a98933010f6059a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035298"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum Development Kit (QDK) yükleme

Kuantum programlamaya başlayabilmek için Microsoft Quantum Development Kit (QDK) yükleme hakkında bilgi edinin. QDK aşağıdakilerden oluşur:

- Q# programlama dili
- Q# dilinde karmaşık işlevleri özetleyen bir kitaplık kümesi
- Q# dilinde yazılmış kuantum işlemleri çalıştıran bir konak uygulama (Python veya bir .NET dilinde yazılmış)
- geliştirmenizi kolaylaştıracak araçlar

Seçtiğiniz geliştirme ortamına bağlı olarak, farklı yükleme adımları vardır. Ortamınızı aşağıdaki bölümlerden seçin.

## <a name="develop-with-python"></a>Python ile geliştirme

1. Ön koşullar

    - [Python](https://www.python.org/downloads/) 3.6 veya üzeri
    - [PIP](https://pip.pypa.io/en/stable/installing) Python paket yöneticisi
    - [.NET Core SDK 2.1 veya üzeri](https://www.microsoft.com/net/download)

1. `iqsharp` paketini yükleyin

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. `qsharp` paketini yükleyin

    ```bash
    pip install qsharp
    ```

1. `Hello World` uygulaması oluşturarak yüklemeyi doğrulayın

    - `Operation.qs` adlı bir dosya oluşturup dosyaya aşağıdaki kodu ekleyerek küçük bir Q# işlemi oluşturun:

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - Q# `SayHello()` işlemini çağırmak için `hello_world.py` adlı bir Python programı oluşturun:

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - Programı çalıştırın:

        ```bash
        python hello_world.py
        ```

    - Çıktıyı doğrulayın. Programınız aşağıdaki satırları çıkarmalıdır:

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a>Jupyter not defterleri ile geliştirme

1. Ön koşullar

    - [Python](https://www.python.org/downloads/) 3.6 veya üzeri
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 2.1 veya üzeri](https://www.microsoft.com/net/download)

1. `iqsharp` paketini yükleyin

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. `Hello World` uygulaması oluşturarak yüklemeyi doğrulayın

    - Not defteri sunucusunu başlatmak için aşağıdaki komutu çalıştırın:

        ```bash
        jupyter notebook
        ```

    - Komut satırında gösterilen URL'ye gidin. Örneğin: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

    - Bir Q# çekirdeği ile Jupyter not defteri oluşturun ve aşağıdaki kodu birinci not defteri hücresine ekleyin:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Not defterinin şu hücresini çalıştırın:

        ![Jupyter not defteri hücresi](~/media/install-guide-jupyter.png)

        Hücrenin çıktısında `SayHello` görmeniz gerekir. Jupyter not defterlerinde çalışırken Q# kodu derlenir ve not defteri bulduğu işlemlerin adını çıkarır.

## <a name="develop-with-c-on-windows-using-visual-studio"></a>Visual Studio kullanarak Windows üzerinde C# ile geliştirme

1. Ön koşullar

    - .NET Core platformlar arası geliştirme iş yükü etkin olan [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3

1. Q# Visual Studio uzantısını yükleyin

    - [Visual Studio uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) indirin
    - Uzantıyı Visual Studio'ya ekleyin

1. `Hello World` uygulaması oluşturarak yüklemeyi doğrulayın

    - Yeni bir Q# uygulaması oluşturun

        - **Dosya** -> **Yeni** -> **Proje**’ye gidin
        - Arama kutusuna `Q#` yazın
        - **Q# Uygulaması**’nı seçin
        - **İleri**’yi seçin
        - Uygulamanız için bir ad ve konum seçin
        - **Oluştur**’u seçin

    - Projeyi inceleyin

        İki dosya oluşturulur: C# konak uygulaması olan `Driver.cs` ve konsola bir ileti yazdıran basit işlemi tanımlayan Q# programı `Operation.qs`.

    - Uygulamayı çalıştırma

        - **Hata Ayıklama** -> **Hata Ayıklamadan Başlat**’ı seçin
        - Bir konsol penceresinde yazdırılmış `Hello quantum world!` metni görmeniz gerekir.

> [!NOTE]
> * Bir Visual Studio çözümünde birden fazla projeniz varsa, çözümde yer alan tüm projelerin çözüm ile aynı klasörde veya bunun bir alt klasöründe olması gerekir.  

## <a name="develop-with-c-using-vs-code"></a>VS Code kullanarak C# ile geliştirme

1. Ön koşullar

   - [VS Code](https://code.visualstudio.com/download)
   - [.NET Core SDK 2.1 veya üzeri](https://www.microsoft.com/net/download)

1. Kuantum VS Code uzantısını yükleme

    - [VS Code uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) yükleyin

1. Kuantum proje şablonlarını yükleyin:

   - **Görünüm** -> **Komut Paleti**’ne gidin
   - **Q#: Proje şablonlarını yükle**’yi seçin

    Quantum Development Kit yüklenmiştir ve kendi uygulama ve kitaplıklarınızda kullanılmaya hazırdır.

1. `Hello World` uygulaması oluşturarak yüklemeyi doğrulayın

    - Yeni bir proje oluşturun:

        - **Görünüm** -> **Komut Paleti**’ne gidin
        - **Q#: Yeni Proje Oluştur**’u seçin
        - Dosya sisteminde uygulamayı oluşturmak istediğiniz konuma gidin
        - Proje oluşturulduktan sonra **Yeni proje aç...** düğmesine tıklayın

    - Uygulamayı çalıştırın:

        - **Hata Ayıklama** -> **Hata Ayıklamadan Başlat**’a gidin
        - Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`

> [!NOTE]
> * > * Birden fazla kök klasörü olan çalışma alanları şu anda Visual Studio Code uzantısı tarafından desteklenmemektedir. Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a>`dotnet` komut satırı aracını kullanarak C# ile geliştirme

1. Ön koşullar

    - [.NET Core SDK 2.1 veya üzeri](https://www.microsoft.com/net/download)

1. .NET için Kuantum proje şablonlarını yükleme

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    Quantum Development Kit yüklenmiştir ve kendi uygulama ve kitaplıklarınızda kullanılmaya hazırdır.

1. `Hello World` uygulaması oluşturarak yüklemeyi doğrulayın

    - Yeni uygulama oluşturma

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - Yeni uygulama dizinine gidin

       ```bash
       cd runSayHello
       ```

    Uygulamanın proje dosyaları ile birlikte iki dosyanın oluşturulur: bir Q# dosyası (`Operation.qs`) ve bir C# konak dosyası (`Driver.cs`).

    - Uygulamayı çalıştırma

        ```bash
        dotnet run
        ```

        Şu çıktıyı görmeniz gerekir: `Hello quantum world!`

## <a name="whats-next"></a>Sırada ne var?

Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.write-program) yazıp çalıştırabilirsiniz.