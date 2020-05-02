---
title: Q# ve C# ile geliştirme
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 5bcb036b0b32e64d43f90e9a068d9dcc237890ba
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680175"
---
# <a name="using-q-with-c-and-f"></a>C\# ve F ile Q # kullanma\#

Q #, C# ve F # gibi .NET dilleri ile birlikte oynamak üzere geliştirilmiştir.
Bu kılavuzda, bir .NET dilinde yazılmış bir ana bilgisayar programıyla Q # ' ı nasıl kullanacağınızı göstereceğiz.

## <a name="prerequisites"></a>Ön koşullar

- [Q # komut satırı projeleriyle kullanılmak üzere](xref:microsoft.quantum.install.standalone)hisse geliştirme setini yükler.

## <a name="creating-a-q-library-and-a-net-host"></a>Bir Q # kitaplığı ve bir .NET Konağı oluşturma

İlk adım, Q # kitaplığınız için projeler oluşturmaktır ve Q # kitaplığınızda tanımlanan işlemler ve işlevlere çağrı yapılacak .NET ana bilgisayarı için kullanılır.

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Yeni bir Q # kitaplığı oluşturun
  - **Dosya** -> **New**yeni -> **Proje** 'ye git
  - Arama kutusuna "Q #" yazın
  - **Q # kitaplığı** Seç
  - **İleri** Seç
  - Kitaplığınız için bir ad ve konum seçin
  - "Projeyi ve çözümü aynı dizinde yerleştir" **işaretinin işaretli** olmadığından emin olun
  - **Oluştur** ' u seçin
- Yeni bir C# veya F # ana bilgisayar programı oluşturma
  - **Dosya** → **Yeni** → **projesine** git
  - C# veya F için "konsol uygulaması (.NET Core") "seçeneğini belirleyin #
  - **İleri** Seç
  - *Çözüm*altında "çözüme Ekle" yi seçin
  - Ana bilgisayar programınız için bir ad seçin
  - **Oluştur** ' u seçin

### <a name="visual-studio-code-or-command-line"></a>[Visual Studio Code veya komut satırı](#tab/tabid-cmdline)

- Yeni bir Q # kitaplığı oluşturun

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- Yeni bir C# veya F # konsol projesi oluşturma

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Q # kitaplığınızı ana bilgisayar programınızdaki bir başvuru olarak ekleyin

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- Seçim Her iki proje için bir çözüm oluşturun

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a>.NET 'ten Q # içine çağırma

Projelerinizi yukarıdaki yönergeleri izleyerek ayarladıktan sonra, .NET konsol uygulamanızdan Q # dosyasına çağrı yapabilirsiniz.
Q # derleyicisi her bir Q # işlemi ve bir Benzetici üzerinde hisse

Örneğin, [.net birlikte çalışabilirlik örneği](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) aşağıdaki bir Q # işlemi örneğini içerir:

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

Bu işlemi bir hisse Benzetici üzerinde .NET 'ten çağırmak için, Q # derleyicisi `Run` tarafından oluşturulan `RunAlgorithm` .net sınıfının yöntemini kullanabilirsiniz:

### <a name="c"></a>[, #](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="whats-next"></a>Sırada ne var?

Hem Q # komut satırı programlarında hem de .NET ile birlikte çalışabilirliğine sahip olduğunuza göre, [ilk hisse programınızı](xref:microsoft.quantum.write-program)yazabilir ve çalıştırabilirsiniz.
