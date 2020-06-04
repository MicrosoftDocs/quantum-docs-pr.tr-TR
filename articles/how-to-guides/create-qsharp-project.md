---
title: 'Hisse geliştirme seti (QDK) ile bir Q # projesi oluşturma hakkında bilgi edinin'
description: 'Seçtiğiniz geliştirme ortamında QDK ve Q # ile hisse geliştirme için bir proje başlatın'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 8019b32a3290e2d45124ebb1eb75395f6cb758db
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327535"
---
# <a name="create-a-q-project-in-your-development-environment"></a>Geliştirme ortamınızda bir Q # projesi oluşturma

QDK ile bir Q # projesi oluşturmayı öğrenin.

Bir Q # projesi, hisse cinsi içeren Q # dosyalarını ve hisse programını çalıştırmak için bir ana bilgisayar programını içerir. Ana bilgisayar programını C# gibi .NET dillerinde veya Python 'da yazabilirsiniz. Ayrıca, IQ # çekirdeğini kullanarak Q # kodunu bir Jupyter Notebook de çalıştırabilirsiniz.

Aşağıdaki bölümlerde geliştirme ortamınızı ve dilinizi seçin:

* [Python](#create-a-python-project)
* [Q# Jupyter Notebook’ları](#create-a-q-jupyter-notebook-project)
* [Visual Studio ile C#](#create-a-c-project-on-windows-using-visual-studio)
* [VS Code C#](#create-a-c-project-using-vs-code)
* [Komut satırı ile C#](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>Python projesi oluşturma

1. Ön koşullar

     * [Python Için hisse geliştirme seti 'ni](xref:microsoft.quantum.install.python) yükler

1. Projeniz için bir klasör oluşturun ve bu klasöre gidin

1. Adlı bir Q # dosyası oluşturun `Operation.qs` ve buna q # kodunuzu ekleyin. Örnek:

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

1. Q # işleminizi çağırmak için çağrılan bir Python ana bilgisayar dosyası oluşturun `host.py` . Örnek:

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

## <a name="create-a-q-jupyter-notebook-project"></a>Bir Q # Jupyter Notebook projesi oluşturma

1. Ön koşullar

    * [Jupyıter Not defterleri Için hisse geliştirme setini](xref:microsoft.quantum.install.jupyter) yükler

1. Not defteri sunucusunu başlatmak için aşağıdaki komutu çalıştırın:

    ```bash
    jupyter notebook
    ```

1. Komut satırında gösterilen URL'ye gidin. Örneğin: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]

1. Tarayıcıda bir Jupyıter sayfası görüntülenir. **Dosyalar** sekmesinde, bir **New**  >  q # çekirdeğiyle Jupyter Notebook oluşturmak için yeni**Q #** öğesini seçin. İlk not defteri hücresine aşağıdaki kodu ekleyin:

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. **Cell**  >  Not defterini çalıştırmak için hücre**çalıştırma hücrelerini** seçin. `SayHello`kısa süre önce hücre çıktısında görünür:

    ![Q # kodlu Jupyter Notebook hücresi](~/media/install-guide-jupyter.png)

    Jupyter not defterlerinde çalışırken, Q # kodu derlenir ve Not defteri bulduğu işlem (ler) in adını verir.

1. Yeni bir hücrede `%simulate` magic kullanarak yeni oluşturduğunuz işlemin kuantum bilgisayarda yürütmesinin benzetimini yapın:

    ![% Benzetim Magic ile Jupyter Notebook hücresi](~/media/install-guide-jupyter-simulate.png)

    Ekrana yazdırılmış bir iletiyle birlikte çağırdığınız işlemin sonucuna da (bu örnekte boş) görüyor olmalısınız.

Artık, hisse geliştirme işlemlerinizi sürdürmek için diğer Q # işlemleri ekleyebilirsiniz.

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>Visual Studio 'Yu kullanarak Windows üzerinde C# projesi oluşturma

1. Ön koşullar

    * [Visual Studio Için hisse geliştirme seti uzantısını](xref:microsoft.quantum.install.cs) yükler

1. Yeni bir Q# uygulaması oluşturun

    * **Dosya**  ->  **Yeni**  ->  **Proje** 'ye git
    * Arama kutusuna `Q#` yazın
    * **Q# Uygulaması**’nı seçin
    * **İleri** Seç
    * Uygulamanız için bir ad ve konum seçin
    * **Oluştur** ' u seçin

1. Projeyi inceleyin

    İki dosya oluşturulur: C# konak uygulaması olan `Driver.cs` ve konsola bir ileti yazdıran basit işlemi tanımlayan Q# programı `Operation.qs`.

1. Uygulamayı çalıştırma

    * Hata **ayıklama**  ->  **olmadan Başlat** ' ı seçin
    * Bir konsol penceresinde yazdırılmış `Hello quantum world!` metni görmeniz gerekir.

Artık Visual Studio 'Yu kullanarak hisse geliştirmeye devam edebilirsiniz

> [!NOTE]
> * Bir Visual Studio çözümünde birden fazla projeniz varsa, çözümde yer alan tüm projelerin çözüm ile aynı klasörde veya bunun bir alt klasöründe olması gerekir.  

## <a name="create-a-c-project-using-vs-code"></a>VS Code kullanarak bir C# projesi oluşturma

1. Ön koşullar

    * [Vs Code Için hisse geliştirme seti uzantısını](xref:microsoft.quantum.install.cs) yükler

1. Yeni bir proje oluşturun:

    * **Görünüm**  ->  **komut paleti** 'ne git
    * **Q #: yeni proje oluştur** ' u seçin
    * **Tek başına konsol uygulamasını** seçin
    * Dosya sisteminde uygulamayı oluşturmak istediğiniz konuma gidin
    * Proje oluşturulduktan sonra **Yeni proje aç...** düğmesine tıklayın

1. Uygulamayı çalıştırın:

    * **Terminal**  ->  **yeni Terminal** 'e git
    * Girmesini`dotnet run`
    * Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`

Artık Visual Studio Code kullanarak hisse geliştirmeye devam edebilirsiniz.

> [!NOTE]
> * Birden fazla kök klasörü olan çalışma alanları şu anda Visual Studio Code uzantısı tarafından desteklenmemektedir. Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>Komut satırı aracını kullanarak bir C# projesi oluşturma `dotnet`

1. Ön koşullar

    * [Komut satırı Için hisse geliştirme setini](xref:microsoft.quantum.install.standalone) yükler

1. Yeni uygulama oluşturma

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. Yeni uygulama dizinine gidin

    ```bash
    cd <project name>
    ```

    Uygulamanın proje dosyaları ile birlikte iki dosyanın oluşturulur: bir Q# dosyası (`Operation.qs`) ve bir C# konak dosyası (`Driver.cs`).

1. Uygulamayı çalıştırma

    ```dotnetcli
    dotnet run
    ```

    Şu çıktıyı görmeniz gerekir: `Hello quantum world!`

Artık, komut satırı araçlarını kullanarak hisse geliştirmeye devam edersiniz.

## <a name="next-steps"></a>Sonraki adımlar

Tercih ettiğiniz ortamda bir proje oluşturduğunuza göre, artık hisse geliştirme ortamınıza devam edebilirsiniz.
