---
title: 'Q # komut satırı uygulamalarıyla geliştirme'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e829862521951c50cb42eebf261c803071a95275
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426430"
---
# <a name="develop-with-q-command-line-applications"></a>Q # komut satırı uygulamalarıyla geliştirme

Q # programları, C#, F # veya Python gibi bir ana bilgisayar dilinde bir sürücü olmadan kendi başına çalıştırılabilir.

## <a name="pre-requisites"></a>Ön koşullar

- [.NET Core SDK 3,1 veya üzeri](https://www.microsoft.com/net/download)

## <a name="installation"></a>Yükleme

Herhangi bir IDE 'de Q # komut satırı uygulamaları derleyebilir, ancak Q # uygulamalarınız için Visual Studio Code (VS Code) veya Visual Studio IDE kullanmanızı öneririz. Bu araçların geliştirilmesi, zengin işlevselliğe erişim sağlar.

VS Code yapılandırmak için:

1. [Vs Code](https://code.visualstudio.com/download) indirin ve yükleyin (Windows, Linux ve Mac).
2. [Vs Code Için Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)'yi yükler.

Visual Studio 'Yu yapılandırmak için:

1. .NET Core platformlar arası geliştirme iş yükü etkinken [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16,3 veya üstünü indirip yükleyin.
2. [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)'yi indirip yükleyin.


## <a name="develop-with-q-using-vs-code"></a>VS Code kullanarak Q # ile geliştirme

Q # proje şablonlarını yükler:

1. VS Code açın.
2. **Görünüm**  ->  **komut paleti**' ne tıklayın.
3. **Q #: proje şablonlarını yükler**' i seçin.

**Proje şablonları başarıyla yüklendiğinde** , QDK kendi uygulama ve kitaplıklarınızla birlikte kullanıma yönelik olarak kullanılabilir.

Yeni bir proje oluşturmak için:

1. Komut **paletini görüntüle**' ye tıklayın  ->  **Command Palette** ve **Q #: yeni proje oluştur**' u seçin.
2. **Tek başına konsol uygulaması**' na tıklayın.
3. Projeyi kaydetmek için konuma gidin ve **proje oluştur**' a tıklayın.
4. Proje başarıyla oluşturulduğunda, sağ alt köşedeki **Yeni proje... aç** ' a tıklayın.
        
Projeyi inceleyin. `Program.qs`Konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q # programı olan adlı bir kaynak dosyası görmeniz gerekir.

Uygulamayı çalıştırmak için:
1. **Terminal**  ->  **yeni Terminal**' e tıklayın.
2. Terminal isteminde, girin `dotnet run` .
3. Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`


> [!NOTE]
> Birden çok kök klasörü olan çalışma alanları şu anda VS Code Q # uzantısı tarafından desteklenmemektedir. Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.

## <a name="develop-with-q-using-visual-studio"></a>Visual Studio kullanarak Q # ile geliştirme

Bir Q # uygulaması oluşturarak Visual Studio yüklemenizi doğrulayın `Hello World` .

Yeni bir Q # uygulaması oluşturmak için:
1. Visual Studio 'yu açın ve **Dosya**  ->  **Yeni**  ->  **Proje**' ye tıklayın.
2. `Q#`Arama kutusuna yazın, **Q # uygulaması** ' nı seçin ve **İleri**' ye tıklayın.
3. Uygulamanız için bir ad ve konum girin ve **Oluştur**' a tıklayın.


Projeyi inceleyin. `Program.qs`Konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q # programı olan adlı bir kaynak dosyası görmeniz gerekir.

Uygulamayı çalıştırmak için:
1. Hata **Debug**  ->  **ayıklamadan Başlat**' ı seçin.
2. Bir konsol penceresinde yazdırılmış `Hello quantum world!` metni görmeniz gerekir.

> [!NOTE]
> Bir Visual Studio çözümü içinde birden çok projeniz varsa, Çözümdeki tüm projelerin çözümle aynı klasörde veya alt klasörlerinden birinde olması gerekir.  


## <a name="next-steps"></a>Sonraki adımlar

Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.
