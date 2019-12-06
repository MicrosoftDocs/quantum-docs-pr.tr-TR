---
title: 'Hisse geliştirme seti (QDK) ile bir Q # projesi oluşturma hakkında bilgi edinin'
description: 'Seçtiğiniz geliştirme ortamında QDK ve Q # ile hisse geliştirme için bir proje başlatın'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 10b1048501c2de055f5711fc0fdbc4bac76e8f77
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864415"
---
# <a name="create-a-q-project-in-your-development-environment"></a>Geliştirme ortamınızda bir Q # projesi oluşturma

QDK ile bir Q # projesi oluşturmayı öğrenin.

Bir Q # projesi, hisse cinsi içeren Q # dosyalarını ve hisse programını çalıştırmak için bir ana bilgisayar programını içerir. Ana bilgisayar programını C#, gibi .NET dillerinde veya Python 'da yazabilirsiniz. Ayrıca, IQ # çekirdeğini kullanarak bir Jupyter not defterinde Q # kodu çalıştırabilirsiniz.

Aşağıdaki bölümlerde geliştirme ortamınızı ve dilinizi seçin:

* [Python](#create-a-python-project)
* [Jupyter Not Defterleri](#create-a-jupyter-notebook-project)
* [C#Visual Studio ile](#create-a-c-project-on-windows-using-visual-studio)
* [C#VS Code ile](#create-a-c-project-using-vs-code)
* [C#komut satırı ile](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>Python projesi oluşturma

1. Önkoşullar

     * [Python Için hisse geliştirme seti](xref:microsoft.quantum.install#develop-with-python)

1. Projeniz için bir klasör oluşturun ve bu klasöre gidin

1. `Operation.qs`adlı bir Q # dosyası oluşturun ve buna Q # kodunuzu ekleyin. Örnek:

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. Q # işleminizi çağırmak için `host.py` adlı bir Python ana bilgisayar dosyası oluşturun. Örnek:

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. Programı çalıştırın:

    ```bash
    python host.py
    ```

1. Çıktıyı doğrulayın. Programınız aşağıdaki satırları çıkarmalıdır:

    ```bash
    Hello from quantum world!
    0
    ```

Artık hisse programınızı geliştirmeye devam edebilirsiniz.

## <a name="create-a-jupyter-notebook-project"></a>Jupyter Notebook projesi oluşturma

1. Önkoşullar

    * [Jupyıter Not defterleri Için hisse geliştirme seti](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)

1. Not defteri sunucusunu başlatmak için aşağıdaki komutu çalıştırın:

    ```bash
    jupyter notebook
    ```

1. Komut satırında gösterilen URL'ye gidin. Örneğin: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

1. Tarayıcıda bir Jupyıter sayfası görüntülenir. **Dosyalar** sekmesinde, q # çekirdeğine sahip bir Jupyter Not defteri oluşturmak için **Yeni** > **q #** ' ı seçin. İlk not defteri hücresine aşağıdaki kodu ekleyin:

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. Not **defteri 'ni çalıştırmak** için **hücre** > seçin. `SayHello` kısa bir süre sonra hücre çıktısında görüntülenir:

    ![Q# kodu içeren Jupyter not defteri hücresi](~/media/install-guide-jupyter.png)

    Jupyter not defterlerinde çalışırken, Q # kodu derlenir ve Not defteri bulduğu işlem (ler) in adını verir.

1. Yeni bir hücrede `%simulate` magic kullanarak yeni oluşturduğunuz işlemin kuantum bilgisayarda yürütmesinin benzetimini yapın:

    ![%simulate magic içeren Jupyter not defteri hücresi](~/media/install-guide-jupyter-simulate.png)

    Ekrana yazdırılmış bir iletiyle birlikte çağırdığınız işlemin sonucuna da (bu örnekte boş) görüyor olmalısınız.

Artık, hisse geliştirme işlemlerinizi sürdürmek için diğer Q # işlemleri ekleyebilirsiniz.

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>Visual Studio C# 'Yu kullanarak Windows üzerinde bir proje oluşturma

1. Önkoşullar

    * [Visual Studio Için hisse geliştirme seti](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)

1. Yeni bir Q# uygulaması oluşturun

    * **Dosya** -> **Yeni** -> **Proje**’ye gidin
    * Arama kutusuna `Q#` yazın
    * **Q# Uygulaması**’nı seçin
    * **İleri**’yi seçin
    * Uygulamanız için bir ad ve konum seçin
    * **Oluştur**’u seçin

1. Projeyi inceleyin

    İki dosya oluşturulur: C# konak uygulaması olan `Driver.cs` ve konsola bir ileti yazdıran basit işlemi tanımlayan Q# programı `Operation.qs`.

1. Uygulamayı çalıştırma

    * **Hata Ayıklama** -> **Hata Ayıklamadan Başlat**’ı seçin
    * Bir konsol penceresinde yazdırılmış `Hello quantum world!` metni görmeniz gerekir.

Artık Visual Studio 'Yu kullanarak hisse geliştirmeye devam edebilirsiniz

> [!NOTE]
> * Bir Visual Studio çözümünde birden fazla projeniz varsa, çözümde yer alan tüm projelerin çözüm ile aynı klasörde veya bunun bir alt klasöründe olması gerekir.  

## <a name="create-a-c-project-using-vs-code"></a>VS Code kullanarak C# proje oluşturma

1. Önkoşullar

    * [Vs Code Için hisse geliştirme seti](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code)

1. Yeni bir proje oluşturun:

    * **Görünüm** -> **Komut Paleti**’ne gidin
    * **Q #: yeni proje oluştur** ' u seçin
    * **Tek başına konsol uygulamasını** seçin
    * Dosya sisteminde uygulamayı oluşturmak istediğiniz konuma gidin
    * Proje oluşturulduktan sonra **Yeni proje aç...** düğmesine tıklayın

1. Uygulamayı çalıştırın:

    * **Terminal** -> **yeni Terminal** 'a git
    * `dotnet run` girin
    * Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`

Artık Visual Studio Code kullanarak hisse geliştirmeye devam edebilirsiniz.

> [!NOTE]
> * Birden fazla kök klasörü olan çalışma alanları şu anda Visual Studio Code uzantısı tarafından desteklenmemektedir. Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>`dotnet` komut C# satırı aracını kullanarak bir proje oluşturun

1. Önkoşullar

    * [Komut satırı Için hisse geliştirme seti](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool)

1. Yeni uygulama oluşturma

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. Yeni uygulama dizinine gidin

    ```bash
    cd <project name>
    ```

    Uygulamanın proje dosyaları ile birlikte iki dosyanın oluşturulur: bir Q# dosyası (`Operation.qs`) ve bir C# konak dosyası (`Driver.cs`).

1. Uygulamayı çalıştırma

    ```bash
    dotnet run
    ```

    Şu çıktıyı görmeniz gerekir: `Hello quantum world!`

Artık, komut satırı araçlarını kullanarak hisse geliştirmeye devam edersiniz.

## <a name="whats-next"></a>Sırada ne var?

Tercih ettiğiniz ortamda bir proje oluşturduğunuza göre, artık hisse geliştirme ortamınıza devam edebilirsiniz.
