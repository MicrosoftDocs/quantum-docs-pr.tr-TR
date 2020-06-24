---
title: Microsoft hisse sayılıcs kitaplığı-yükleme ve doğrulama
description: Microsoft hisse biçimi kitaplığı 'nı Visual Studio 2019 veya sonraki yüklemenize eklemeyi öğrenin.
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 60ee91a552fad5becf8eda437406b6e0dfba0eb4
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276131"
---
# <a name="numerics-library-installation-and-validation"></a>Numerics kitaplığı yükleme ve doğrulama

Hisse geliştirme seti, NuGet paketiyle Numerics işlevselliği için destek sağlar [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) .

**Visual Studio >= 2019:** Visual Studio 2019 veya sonraki bir sürümünü kullanıyorsanız, NuGet Paket Yöneticisi 'Ni kullanarak Numerics paketini ekleyebilirsiniz.
Bunu yapmak için "NuGet Paketlerini Yönet..." seçeneğini belirleyin. Visual Studio 'daki "proje" menü öğesinden.

Araştır sekmesinden "Microsoft. hisse. Numerics" paket adını arayın

> [!NOTE]
> "Ön sürümü dahil et" i seçtiğinizden emin olun

Bu, karşıdan yüklenebilecek paketleri listeler.
"Microsoft. hisse. Numerics" üzerine gelindiğinde, sürüm numarasının sağında aşağı işaret eden bir ok görünür.
Numerics paketini yüklemek için oka tıklayın.

Daha ayrıntılı bilgi için bkz. [Paket Yöneticisi Kullanıcı Arabirimi Kılavuzu](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Alternatif olarak, komut satırı arabirimi aracılığıyla, sayılıcs kitaplığını projenize eklemek için Package Manager konsolunu kullanabilirsiniz.

![Paket Yöneticisi konsolunu komut satırından kullanma](~/media/vs2017-nuget-console-menu.png)

Paket Yöneticisi konsolundan aşağıdakileri çalıştırın:

```
Install-Package Microsoft.Quantum.Numerics
```

Daha ayrıntılı bilgi için bkz. [Paket Yöneticisi konsol Kılavuzu](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Komut satırı veya Visual Studio Code:** Komut satırını kendi başına veya Visual Studio Code içinden kullanarak `dotnet` projenize NuGet paket başvurusu eklemek için komutunu kullanabilirsiniz:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a>Yüklemenizin doğrulanması

Hisse geliştirme seti 'nin geri kalanı gibi, Numerics kitaplığı mümkün olduğunca hızlı başlamanıza yardımcı olan örneklerle birlikte gelir.
Bu örnekleri kullanarak yüklemenizi test etmek için, [ana örnek depoyu](https://github.com/Microsoft/Quantum) kopyalayın ve ardından örneklerden birini çalıştırın.

Örneği çalıştırmak için [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) :

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
