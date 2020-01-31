---
title: 'Q # + ile geliştirinC#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 1fd829c684502092bb7491b0f46b5f690320c941
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831027"
---
# <a name="develop-with-q--c"></a>Q # + ile geliştirinC#

Q # işlemlerini çağırmak için konak C# programları geliştirmek üzere QDK 'yi yükler.

S #, .NET dilleri ile birlikte çalışmak için geliştirilmiştir--özellikle C#. Bu eşleştirmede farklı geliştirme ortamları içinde çalışabilirsiniz:

- [Q # + C# Visual Studio 'Yu (Windows) kullanma](#VS)
- [Q # + C# Visual Studio Code (Windows, Linux ve Mac) kullanma](#VSC)
- [`dotnet` komut satırı C# aracını kullanarak Q # +](#command)

## Visual Studio 'Yu kullanarak Q C# # + ile geliştirme<a name="VS"></a>

Visual Studio, Q # programları geliştirmek için zengin bir ortam sunar. Q # Visual Studio uzantısı, Q # dosyaları ve projeleri için şablonlar ve sözdizimi vurgulaması, kod tamamlama ve IntelliSense desteği içerir.


1. Önkoşullar

    - .NET Core platformlar arası geliştirme iş yükü etkin olan [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3

1. Q# Visual Studio uzantısını yükleyin

    - [Visual Studio uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) indirme ve yükleme

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

## Visual Studio Code kullanarak Q # + C# ile geliştirin<a name="VSC"></a>

Visual Studio Code (VS Code) Windows, Linux ve Mac 'te Q # programları geliştirmek için zengin bir ortam sunar.  Q # VS Code uzantısı, Q # sözdizimi vurgulama, kod tamamlama ve Q # kod parçacıkları için destek içerir.

1. Önkoşullar

   - [VS Code](https://code.visualstudio.com/download)
   - [.NET Core SDK 3,1 veya üzeri](https://www.microsoft.com/net/download)

1. Kuantum VS Code uzantısını yükleme

    - [VS Code uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) yükleyin

1. Kuantum proje şablonlarını yükleyin:

   - **Görünüm** -> **Komut Paleti**’ne gidin
   - **S # seçin: proje şablonlarını Install**

    Quantum Development Kit yüklenmiştir ve kendi uygulama ve kitaplıklarınızda kullanılmaya hazırdır.

1. `Hello World` uygulaması oluşturarak yüklemeyi doğrulayın

    - Yeni bir proje oluşturun:

        - **Görünüm** -> **Komut Paleti**’ne gidin
        - **Q #: yeni proje oluştur** ' u seçin
        - **Tek başına konsol uygulamasını** seçin
        - Dosya sisteminde uygulamayı oluşturmak istediğiniz konuma gidin
        - Proje oluşturulduktan sonra **Yeni proje aç...** düğmesine tıklayın

    - VS Code için C# uzantınız yoksa bir açılır pencere görüntülenir. Uzantıyı yükler. 

    - Uygulamayı çalıştırın:

        - **Terminal** -> **yeni Terminal** 'a git
        - `dotnet run` girin
        - Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`


> [!NOTE]
> * Birden fazla kök klasörü olan çalışma alanları şu anda Visual Studio Code uzantısı tarafından desteklenmemektedir. Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.

## `dotnet` komut satırı aracını kullanarak C# Q # + ile geliştirme<a name="command"></a>

Kuşkusuz yalnızca .NET Core SDK'sını ve QDK proje şablonlarını yükleyerek Q# programlarını komut satırından da oluşturup çalıştırabilirsiniz. 

1. Önkoşullar

    - [.NET Core SDK 3,1 veya üzeri](https://www.microsoft.com/net/download)

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
