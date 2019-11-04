---
title: Numerics kitaplığı yükleme ve doğrulama | Microsoft Docs
description: Numerics kitaplığı yükleme ve doğrulama
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 8369a6f342ee8e6f56b69bd1f2ce3df40e4093aa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184636"
---
# <a name="numerics-library-installation-and-validation"></a>Numerics kitaplığı yükleme ve doğrulama

Hisse geliştirme seti, [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet paketiyle Numerics işlevselliği için destek sağlar.

**Visual Studio > = 2019:** Visual Studio 2019 veya sonraki bir sürümünü kullanıyorsanız, NuGet Paket Yöneticisi 'Ni kullanarak Numerics paketini ekleyebilirsiniz.
Bunu yapmak için "NuGet Paketlerini Yönet..." seçeneğini belirleyin. Visual Studio 'daki "proje" menü öğesinden.

Araştır sekmesinden "Microsoft. hisse. Numerics" paket adını arayın

> [!NOTE]
> "Ön sürümü dahil et" i seçtiğinizden emin olun

Bu, karşıdan yüklenebilecek paketleri listeler.
"Microsoft. hisse. Numerics" üzerine gelindiğinde, sürüm numarasının sağında aşağı işaret eden bir ok görünür.
Numerics paketini yüklemek için oka tıklayın.

Daha ayrıntılı bilgi için bkz. [Paket Yöneticisi Kullanıcı Arabirimi Kılavuzu](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Alternatif olarak, komut satırı arabirimi aracılığıyla, sayılıcs kitaplığını projenize eklemek için Package Manager konsolunu kullanabilirsiniz.

![](~/media/vs2017-nuget-console-menu.png)

Paket Yöneticisi konsolundan aşağıdakileri çalıştırın:

```
Install-Package Microsoft.Quantum.Numerics
```

Daha ayrıntılı bilgi için bkz. [Paket Yöneticisi konsol Kılavuzu](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Komut satırı veya Visual Studio Code:** Komut satırını kendi başına veya Visual Studio Code içinden kullanarak projenize NuGet paket başvurusunu eklemek için `dotnet` komutunu kullanabilirsiniz:

```bash
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a>Yüklemenizin doğrulanması

Hisse geliştirme seti 'nin geri kalanı gibi, Numerics kitaplığı mümkün olduğunca hızlı başlamanıza yardımcı olan örneklerle birlikte gelir.
Bu örnekleri kullanarak yüklemenizi test etmek için, [ana örnek depoyu](https://github.com/Microsoft/Quantum) kopyalayın ve ardından örneklerden birini çalıştırın.

[`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/Numerics/CustomModAdd) örneğini çalıştırmak için:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics/CustomModAdd
dotnet run
```