---
title: Q# komut satırı uygulamaları ile geliştirme
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274195"
---
# <a name="develop-with-q-command-line-applications"></a>Q# komut satırı uygulamaları ile geliştirme

Q# programları, C#, F# veya Python gibi bir konak dilinde sürücü olmadan kendi başına çalıştırılabilir.

## <a name="prerequisites"></a>Ön koşullar

- [.NET Core SDK 3.1 veya üzeri](https://www.microsoft.com/net/download)

## <a name="installation"></a>Yükleme

Q# komut satırı uygulamalarını herhangi bir IDE'de derleyebilseniz de, Q# uygulamalarınız için Visual Studio Code (VS Code) veya Visual Studio IDE kullanmanızı öneririz. Bu araçlarda geliştirme yapılması, zengin işlevselliğe erişim sağlar.

VS Code'u yapılandırmak için:

1. [VS Code](https://code.visualstudio.com/download)’u (Windows, Linux ve Mac) indirip yükleyin.
2. [VS Code için Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)’yi yükleyin.

Visual Studio'yu yapılandırmak için:

1. .NET Core platformlar arası geliştirme iş yükü etkin olan [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 veya üzerini indirip yükleyin.
2. [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)’yi indirip yükleyin.


## <a name="develop-with-q-using-vs-code"></a>VS Code kullanarak Q# ile geliştirme

Q# proje şablonlarını yükleyin:

1. VS Code’u açın.
2. **Görünüm** -> **Komut Paleti**’ne tıklayın.
3. **Q#: Proje şablonlarını yükleyin**.

**Proje şablonları başarıyla yüklendi** iletisi görüntülendiğinde, QDK kendi uygulama ve kitaplıklarınızla birlikte kullanıma hazırdır.

Yeni bir proje oluşturmak için:

1. **Görünüm** -> **Komut Paleti**’ne tıklayın ve **Q#: Yeni Proje Oluştur**’u seçin.
2. **Bağımsız konsol uygulaması**’na tıklayın.
3. Projenin kaydedileceği konuma gidin ve **Proje Oluştur**’a tıklayın.
4. Proje başarıyla oluşturulduğunda, sağ alt kısımdaki **Yeni proje aç...** seçeneğine tıklayın.
        
Projeyi inceleyin. Konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q# programı olan `Program.qs` adlı kaynak dosyayı görmeniz gerekir.

Uygulamayı çalıştırmak için:
1. **Terminal** -> **Yeni Terminal**’e tıklayın.
2. Terminal isteminde `dotnet run` girin.
3. Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`


> [!NOTE]
> Birden fazla kök klasörü olan çalışma alanları şu anda VS Code Q# uzantısı tarafından desteklenmemektedir. Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.

## <a name="develop-with-q-using-visual-studio"></a>Visual Studio kullanarak Q# ile geliştirme

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


## <a name="next-steps"></a>Sonraki adımlar

Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.
