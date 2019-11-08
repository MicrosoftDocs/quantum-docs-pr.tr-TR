---
title: Microsoft Quantum Development Kit (QDK) yüklemeyi öğrenin
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 580ac14f2e839d723884a96e9c5fd336ebcb5da0
ms.sourcegitcommit: 30fcb35986b43388ad65dfb876eb3ad8ad0533ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73799157"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum Development Kit (QDK) yükleme

Kuantum programlamaya başlayabilmek için Microsoft Quantum Development Kit (QDK) yükleme hakkında bilgi edinin. QDK aşağıdakilerden oluşur:

- Q# programlama dili
- Q# dilinde karmaşık işlevleri özetleyen bir kitaplık kümesi
- Q# dilinde yazılmış kuantum işlemleri çalıştıran bir konak uygulama (Python veya bir .NET dilinde yazılmış)
- geliştirmenizi kolaylaştıracak araçlar

Seçtiğiniz geliştirme ortamına bağlı olarak, farklı yükleme adımları vardır. Ortamınızı aşağıdaki bölümlerden seçin.

## <a name="develop-with-python"></a>Python ile geliştirme

Python için qsharp paketi, Python’da Q# işlemleri ve işlevlerinin simülasyonunu yapmayı kolaylaştırır. IQ# (ay-kü-şarp okunur) öncelikli olarak Jupyter ve Python tarafından kullanılan ve Q# işlemlerinin derlenmesine ve benzetiminin yapılmasına yönelik temel işlevselliği sağlayan bir uzantıdır.

1. Ön koşullar

    - [Python](https://www.python.org/downloads/) 3.6 veya üzeri
    - [PIP](https://pip.pypa.io/en/stable/installing) Python paket yöneticisi
    - [.NET Core SDK 3.0 veya üzeri](https://www.microsoft.com/net/download)

1. `qsharp` paketini yükleyin

    ```bash
    pip install qsharp
    ```

1. `iqsharp` paketini yükleyin

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
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

Akademik ortamlarda, bilimsel laboratuvarlarda ve İnternet'te işbirliğine dayalı programlamada tercih edilen Jupyter Notebooks şimdi Q# kodu da dahil olmak üzere yerinde kod yürütme, ayrıca yönergeler, notlar ve başka içerik sağlar.  Kendi Q# not defterlerinizi oluşturmaya başlamak için gerekenler aşağıda verilmiştir.

IQ# (ay-kü-şarp okunur) öncelikli olarak Jupyter ve Python tarafından .NET Core SDK için kullanılan ve Q# işlemlerinin derlenmesine ve benzetiminin yapılmasına yönelik temel işlevselliği sağlayan bir uzantıdır.


1. Ön koşullar

    - [Python](https://www.python.org/downloads/) 3.6 veya üzeri
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.0 veya üzeri](https://www.microsoft.com/net/download)

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

        ![Q# kodu içeren Jupyter not defteri hücresi](~/media/install-guide-jupyter.png)

        Hücrenin çıktısında `SayHello` görmeniz gerekir. Jupyter not defterlerinde çalışırken Q# kodu derlenir ve not defteri bulduğu işlemlerin adını çıkarır.


    - Yeni bir hücrede `%simulate` magic kullanarak yeni oluşturduğunuz işlemin kuantum bilgisayarda yürütmesinin benzetimini yapın:

        ![%simulate magic içeren Jupyter not defteri hücresi](~/media/install-guide-jupyter-simulate.png)

        Ekrana yazdırılmış bir iletiyle birlikte çağırdığınız işlemin sonucuna da (bu örnekte boş) görüyor olmalısınız.


## <a name="develop-with-c-on-windows-using-visual-studio"></a>Visual Studio kullanarak Windows üzerinde C# ile geliştirme

Visual Studio Q# programları geliştirmek için zengin bir ortam sunar; geliştiricilere uygulamalarını oluştururken yol gösteren kod tamamlama ve söz dizimi vurgulama gibi harika özellikler sağlar.  Q# Visual Studio uzantısı hem Q# dosyaları ve projeleri için şablonlar hem de söz dizimi vurgulama özelliği ve IntelliSense desteği içerir.


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

## <a name="develop-with-c-using-visual-studio-code"></a>Visual Studio Code kullanarak C# ile geliştirme

Visual Studio Code (VS Code) Windows, Linux ve Mac gibi çeşitli bilgisayar ortamlarında Q# programları geliştirmek için zengin bir ortam sunar; geliştiricilere uygulamalarını oluştururken yol gösteren kod tamamlama ve söz dizimi vurgulama gibi harika özellikler sağlar.  Q# VS Code uzantısı söz dizimi vurgulama özelliği ve Q# kod parçacıkları içerir.

1. Ön koşullar

   - [VS Code](https://code.visualstudio.com/download)
   - [.NET Core SDK 3.0 veya üzeri](https://www.microsoft.com/net/download)

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

Kuşkusuz yalnızca .NET Core SDK'sını ve QDK proje şablonlarını yükleyerek Q# programlarını komut satırından da oluşturup çalıştırabilirsiniz. 

1. Ön koşullar

    - [.NET Core SDK 3.0 veya üzeri](https://www.microsoft.com/net/download)

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
