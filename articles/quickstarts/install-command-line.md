---
title: Bir IDE içinde Q# uygulamaları ile geliştirme
description: Komut isteminden çalışan bir Q# uygulaması oluşturmayı öğrenin.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3e4f1e97477ecb0547b1586b1c7603c8a9954584
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844328"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a>Bir IDE içinde Q# uygulamaları ile geliştirme

Q# programları C#, F# veya Python gibi bir konak dilinde sürücü olmadan kendi başına çalışabilir. Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces veya herhangi bir düzenleyici/IDE ile Q# uygulamaları geliştirebilir ve uygulamaları .NET konsolundan çalıştırabilirsiniz. 

## <a name="prerequisites-for-all-environments"></a>Tüm ortamlar için önkoşullar

- [.NET Core SDK 3.1 veya üzeri](https://www.microsoft.com/net/download)

## <a name="installation"></a>Yükleme

Q# uygulamalarını herhangi bir IDE'de derleyebilseniz de, Q# uygulamalarınızı yerel olarak geliştirmek için Visual Studio Code (VS Code) veya Visual Studio IDE kullanmanızı öneririz. Web tarayıcısı aracılığıyla bulutta geliştirmek için Visual Studio Codespaces’ı öneririz. Bu ortamlarda geliştirme yapılırken QDK uzantısının uyarı, söz dizimi vurgulama, proje şablonları gibi zengin işlevlerinden yararlanılır. 

### <a name="to-configure-for-vs-code"></a>VS Code için yapılandırmak üzere:

1. [VS Code](https://code.visualstudio.com/download)’u (Windows, Linux ve Mac) indirip yükleyin.
2. [VS Code için Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)’yi yükleyin.

### <a name="to-configure-for-visual-studio"></a>Visual Studio için yapılandırmak üzere:

1. .NET Core platformlar arası geliştirme iş yükü etkin olan [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 veya üzerini indirip yükleyin.
2. [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)’yi indirip yükleyin.

### <a name="to-configure-for-another-environment"></a>Başka bir ortam için yapılandırmak üzere: 

1. Komut isteminde aşağıdakini girin

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a>Visual Studio Codespaces için yapılandırmak üzere:

1. [Azure hesabı](https://azure.microsoft.com/free/) oluşturun.
2. Codespaces ortamı oluşturun. Lütfen [hızlı başlangıç kılavuzunu](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser) izleyin. Kod alanını oluştururken QDK'ye özgü ayarları yüklemek için "Git Deposu" alanına `microsoft/Quantum` girmeniz önerilir.
3. Artık yeni ortamınızı başlatabilir ve [VS Codespaces Bulut IDE’si](https://online.visualstudio.com/environments) aracılığıyla tarayıcıda geliştirme yapmaya başlayabilirsiniz. Alternatif olarak, yerel VS Code yüklemenizi kullanmanız ve Codespaces’ı [uzak ortam](https://docs.microsoft.com/visualstudio/online/how-to/vscode) olarak kullanmanız da mümkündür.

## <a name="develop-with-no-locq"></a>Q# ile geliştirme

Geliştirme ortamınıza karşılık gelen sekmedeki yönergeleri izleyin.

### <a name="vs-code"></a>[VS Code](#tab/tabid-vscode)

Yeni bir proje oluşturmak için:

1. **Görünüm** -> **Komut Paleti**’ne tıklayın ve **Q#: Yeni Proje Oluştur**’u seçin.
2. **Bağımsız konsol uygulaması**’na tıklayın.
3. Projenin kaydedileceği konuma gidin. Proje adını girin ve **Proje Oluştur**’a tıklayın.
4. Proje başarıyla oluşturulduğunda, sağ alt kısımdaki **Yeni proje aç...** seçeneğine tıklayın.

Projeyi inceleyin. Konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q# programı olan `Program.qs` adlı kaynak dosyayı görmeniz gerekir.

Uygulamayı çalıştırmak için:

1. **Terminal** -> **Yeni Terminal**’e tıklayın.
2. Terminal isteminde `dotnet run` girin.
3. Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`

> [!NOTE]
> Birden fazla kök klasörü içeren çalışma alanları şu anda VS Code Q# uzantısı tarafından desteklenmemektedir. Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.

### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs)

Bir Q# `Hello World` uygulaması oluşturarak Visual Studio yüklemenizi doğrulayın.

Yeni bir Q# uygulaması oluşturmak için:

1. Visual Studio’yu açın ve **Dosya** -> **Yeni** -> **Proje**’ye tıklayın.
2. Arama kutusuna `Q#` yazın, **Q# Uygulaması**’nı seçin ve **İleri**’ye tıklayın.
3. Uygulamanız için bir ad ve konum girip **Oluştur**'a tıklayın.


Projeyi inceleyin. Konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q# programı olan `Program.qs` adlı kaynak dosyayı görmeniz gerekir.

Uygulamayı çalıştırmak için:

1. **Hata Ayıklama** -> **Hata Ayıklamadan Başlat**’ı seçin.
2. Bir konsol penceresinde yazdırılmış `Hello quantum world!` metni görmeniz gerekir.

> [!NOTE]
> Bir Visual Studio çözümünde birden fazla projeniz varsa, çözümde yer alan tüm projelerin çözüm ile aynı klasörde veya bunun alt klasörlerinin birinde olması gerekir.  

### <a name="other-editors-with-the-command-prompt"></a>[Komut istemi içeren diğer düzenleyiciler](#tab/tabid-cmdline)

Bir Q# `Hello World` uygulaması oluşturarak yüklemenizi doğrulayın.

1. Yeni bir uygulama oluşturun:

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. Uygulama dizinine gidin:

    ```dotnetcli
    cd runSayHello
    ```

    Bu dizin şimdi, konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q# programı olan `Program.qs` adlı dosyayı içermelidir. Bu şablonda bir metin düzenleyiciyle değişiklik yapabilir ve kendi kuantum uygulamalarınızla bu şablonun üzerine yazabilirsiniz. 

1. Programı çalıştırın:

    ```dotnetcli
    dotnet run
    ```

1. Şu metnin yazdırıldığını görmeniz gerekir: `Hello quantum world!`

***

## <a name="next-steps"></a>Sonraki adımlar

Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.
