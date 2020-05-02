---
title: 'Sürücü ve ana bilgisayar dili olmadan Q # programlarını yürütme'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706810"
---
# <a name="q-command-line-applications"></a>Q # komut satırı uygulamaları

Q # programları, C#, F # veya Python gibi bir ana bilgisayar dilinde bir sürücü olmadan kendi başına çalıştırılabilir.

## <a name="pre-requisites"></a>Ön koşullar

- [.NET Core SDK 3,1 veya üzeri](https://www.microsoft.com/net/download)

## <a name="installation"></a>Yükleme

Herhangi bir IDE 'de Q # komut satırı uygulamaları derleyebilir, ancak Q # uygulamalarınız için Visual Studio Code (VS Code) veya Visual Studio IDE kullanmanızı kesinlikle öneririz. VS Code veya Visual Studio ile QDK Visual Studio Code uzantısını kullanarak daha zengin işlevselliğe erişebilirsiniz.

- [Vs Code](https://code.visualstudio.com/download) (Windows, Linux ve Mac) 'i yükler
- [Vs Code Için QDK uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) yükler veya
- .NET Core platformlar arası geliştirme iş yükü etkin olan [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3
- [Visual Studio uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) indirme ve yükleme


## <a name="develop-with-q-using-vs-code"></a>VS Code kullanarak Q # ile geliştirme

Kuantum proje şablonlarını yükleyin:

- **Görünüm** -> **komut paleti** 'ne git
- **S # seçin: proje şablonlarını Install**

Quantum Development Kit yüklenmiştir ve kendi uygulama ve kitaplıklarınızda kullanılmaya hazırdır.
- Yeni bir proje oluşturun:
  - **Görünüm** -> **komut paleti** 'ne git
  - **Q #: yeni proje oluştur** ' u seçin
  - **Tek başına konsol uygulamasını** seçin
  - Dosya sisteminde uygulamayı oluşturmak istediğiniz konuma gidin
  - Proje oluşturulduktan sonra **Yeni proje aç...** düğmesine tıklayın
        
- Projeyi inceleyin
  - Konsola ileti yazdırmak için basit bir işlem `Program.qs` tanımlayan bir Q # programı olan adlı bir dosyanın oluşturulduğunu görmeniz gerekir.

- Uygulamayı çalıştırın:
  - **Terminal** -> **yeni Terminal** 'e git
  - Girmesini`dotnet run`
  - Çıktı penceresinde aşağıdaki metni görürsünüz `Hello quantum world!`


> [!NOTE]
> * Birden fazla kök klasörü olan çalışma alanları şu anda Visual Studio Code uzantısı tarafından desteklenmemektedir. Bir VS Code çalışma alanında birden çok projeniz varsa, tüm projelerin aynı kök klasörde yer alması gerekir.

## <a name="develop-with-q-using-visual-studio"></a>Visual Studio kullanarak Q # ile geliştirme

`Hello World` uygulaması oluşturarak yüklemeyi doğrulayın

- Yeni bir Q# uygulaması oluşturun
  - **Dosya** -> **New**yeni -> **Proje** 'ye git
  - Arama kutusuna `Q#` yazın
  - **Q# Uygulaması**’nı seçin
  - **İleri** Seç
  - Uygulamanız için bir ad ve konum seçin
  - **Oluştur** ' u seçin

- Projeyi inceleyin
  - Adlı `Program.qs` bir dosyanın oluşturulduğunu, yani konsola ileti yazdırmak için basit bir işlem tanımlayan bir Q # programı olduğunu görmeniz gerekir.

- Uygulamayı çalıştırma
  - Hata ayıklama**olmadan Başlat** ' **ı seçin** -> 
  - Bir konsol penceresinde yazdırılmış `Hello quantum world!` metni görmeniz gerekir.

> [!NOTE]
> * Bir Visual Studio çözümünde birden fazla projeniz varsa, çözümde yer alan tüm projelerin çözüm ile aynı klasörde veya bunun bir alt klasöründe olması gerekir.  


## <a name="whats-next"></a>Sırada ne var?

Quantum Development Kit’i tercih ettiğiniz ortama yüklediğinize göre [ilk kuantum programınızı](xref:microsoft.quantum.write-program) yazıp çalıştırabilirsiniz.
