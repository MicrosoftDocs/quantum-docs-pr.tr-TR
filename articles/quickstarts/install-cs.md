---
title: Q# ve .NET ile geliştirme
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 2b0b16bdd9fccc3b668036e6df2b20e11b32f8b6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274157"
---
# <a name="develop-with-q-and-net"></a>Q# ve .NET ile geliştirme

Q# dili, C# ve F# gibi .NET dilleri ile birlikte uyumlu olacak şekilde tasarlanmıştır.
Bu kılavuzda, Q# dilinin bir .NET dilinde yazılmış konak programıyla nasıl kullanılacağını göstereceğiz.

## <a name="prerequisites"></a>Ön koşullar

- [Q# komut satırı projeleriyle birlikte kullanmak için](xref:microsoft.quantum.install.standalone) Quantum geliştirme setini yükleyin.

## <a name="creating-a-q-library-and-a-net-host"></a>Q# kitaplığı ve .NET konağı oluşturma

İlk adım, Q# kitaplığınız ve Q# kitaplığınızda tanımlanan işlemlere ve işlevlere çağrı yapacak .NET konağı için projeleri oluşturmaktır.

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Yeni bir Q# kitaplığı oluşturun
  - **Dosya** -> **Yeni** -> **Proje**’ye gidin
  - Arama kutusuna "Q#" yazın
  - **Q# Kitaplığı**’nı seçin
  - **İleri**’yi seçin
  - Kitaplığınız için bir ad ve konum seçin
  - "Projeyi ve çözümü aynı dizine yerleştir" seçeneğinin **işaretlenmemiş** olduğundan emin olun
  - **Oluştur**’u seçin
- Yeni bir C# veya F# konak programı oluşturun
  - **Dosya** → **Yeni** → **Proje**’ye gidin
  - C# veya F# için "Konsol Uygulaması (.NET Core")" seçeneğini belirleyin
  - **İleri**’yi seçin
  - *Çözüm* altında "çözüme ekle"yi seçin
  - Konak programınız için bir ad seçin
  - **Oluştur**’u seçin

### <a name="visual-studio-code-or-command-line"></a>[Visual Studio Code veya Komut Satırı](#tab/tabid-cmdline)

- Yeni bir Q# kitaplığı oluşturun

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- Yeni bir C# veya F# konsol projesi oluşturun

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Q# kitaplığınızı konak programınızdaki bir başvuru olarak ekleyin

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- [İsteğe Bağlı] Her iki proje için bir çözüm oluşturun

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a>.NET'ten Q# diline çağrı yapma

Projelerinizi yukarıdaki yönergeleri izleyerek ayarladıktan sonra, .NET konsol uygulamanızdan Q# diline çağrı yapabilirsiniz.
Q# derleyicisi, her Q# işlemi ve işlevi için kuantum programlarınızı bir simülatörde çalıştırmanızı sağlayan .NET sınıfları oluşturur.

Örneğin, [.NET birlikte çalışabilirlik örneği](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet), aşağıdaki Q# işlemi örneğini içerir:

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

Bu işlemi bir kuantum simülatöründe .NET'ten çağırmak için, Q# derleyicisi tarafından oluşturulan `RunAlgorithm` .NET sınıfının `Run` metodunu kullanabilirsiniz:

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a>Sonraki adımlar

Artık hem Q# komut satırı programları hem de .NET ile birlikte çalışabilirlik için Quantum geliştirme setini ayarladığınıza göre, [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.
