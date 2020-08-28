---
title: Ek Q# kitaplıkları kullanma
description: Hisse ve uygulamalarınıza ek kitaplıklar ekleme hakkında bilgi edinin Q# .
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: 39bf7dc52f4670a6e4536efc437d001c96f9584a
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992148"
---
# <a name="using-additional-no-locq-libraries"></a>Ek Q# kitaplıkları kullanma

Hisse geliştirme seti, projelerinize eklenebilen _NuGet paketleri_ aracılığıyla alana özgü ek işlevler sağlar Q# .

| Q# Kitaplığı  | NuGet paketi | Notlar |
|---------|---------|--------|
| [Q# Standart Kitaplık](xref:microsoft.quantum.libraries.standard.intro) | [**Microsoft. hisse. Standart**](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | Varsayılan olarak eklendi |
| [Kuantum kimyası kitaplığı](xref:microsoft.quantum.chemistry.concepts.intro) | [**Microsoft.Quantum.Chemistry**](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [Kuantum sayısal kitaplığı](xref:microsoft.quantum.numerics.intro) | [**Microsoft. hisse. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [Kuantum makine öğrenimi kitaplığı](xref:microsoft.quantum.libraries.machine-learning.intro) | [**Microsoft.Quantum.MachineLearning**](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

Bir hisse geliştirme setini tercih ettiğiniz ortam ve ana bilgisayar diliyle kullanılmak üzere yükledikten sonra, Q# başka bir yükleme yapmadan kitaplıkları ayrı ayrı projelere kolayca ekleyebilirsiniz.

> [!NOTE]
> Bazı Q# Kitaplıklar Q# , programlarınızda birlikte çalışan veya ana bilgisayar uygulamalarınızla tümleştirilen ek araçlarla iyi çalışabilir.
> Örneğin, [Kimya kitaplığı yükleme yönergeleri](xref:microsoft.quantum.chemistry.concepts.installation) , [ **Microsoft. hisse. kimya** paketinin](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) nwchem hesaplama Kimya platformuyla birlikte nasıl kullanılacağını ve `qdk-chem` hisse atıkmistry verileriyle çalışmak için komut satırı araçlarının nasıl yükleneceğini açıklamaktadır.

## <a name="no-locq-applications-or-net-interopability"></a>[Q# uygulamalar veya .NET karşılıklı kullanılabilirliği](#tab/tabid-csproj)

**Komut istemi veya Visual Studio Code:** Komut istemi 'ni kendi başına veya Visual Studio Code içinden kullanarak `dotnet` projenize bir NuGet paket başvurusu eklemek için komutunu kullanabilirsiniz.
Örneğin, [**Microsoft. hisse. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) paketini eklemek için aşağıdaki komutu çalıştırın:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

**Visual Studio:** Visual Studio 2019 veya sonraki bir sürümü kullanıyorsanız, Q# NuGet Paket Yöneticisi 'ni kullanarak ek paketler ekleyebilirsiniz.
Bir paket yüklemek için: 
1. Visual Studio 'da açık bir proje ile, **Proje** menüsünden **NuGet Paketlerini Yönet...** öğesini seçin.

2. **Araştır**' a tıklayın, **ön sürümü dahil et** ' i seçin ve "Microsoft. hisse. Numerics" paket adını arayın. Bu, karşıdan yüklenebilecek paketleri listeler.

3. **Microsoft. hisse. Numerics** ' ın üzerine gelin ve sayı, sayı eklemek için sürüm numarasının sağ tarafındaki aşağı açılan oka tıklayın.

Daha ayrıntılı bilgi için bkz. [Paket Yöneticisi Kullanıcı Arabirimi Kılavuzu](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Alternatif olarak, komut satırı arabirimi aracılığıyla, sayılıcs kitaplığını projenize eklemek için Package Manager konsolunu kullanabilirsiniz.

![Paket Yöneticisi konsolunu komut isteminden kullanma](~/media/vs2017-nuget-console-menu.png)

Paket Yöneticisi konsolundan aşağıdakileri çalıştırın:

```
Install-Package Microsoft.Quantum.Numerics
```

Daha ayrıntılı bilgi için bkz. [Paket Yöneticisi konsol Kılavuzu](https://docs.microsoft.com/nuget/tools/package-manager-console).

## <a name="ino-locq-notebooks"></a>[I Q# Not defterleri](#tab/tabid-notebook)

Q# [ `%package` MAGIC komutunu](xref:microsoft.quantum.iqsharp.magic-ref.package)kullanarak bir ı not defterinde kullanılabilecek ek paketleri kullanılabilir hale getirebilirsiniz.
Örneğin, bir I not defterinde kullanmak üzere [**Microsoft. hisse. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) paketini eklemek için Q# bir not defteri hücresinde aşağıdaki komutu çalıştırın:

```
%package Microsoft.Quantum.Numerics
```

Bu komutun ardından, paket Not Defteri içindeki herhangi bir hücre için kullanılabilir.
Paketi Q# geçerli çalışma alanındaki koddan kullanılabilir hale getirmek için, paketinizi ekledikten sonra çalışma alanını yeniden yükleyin:

```
%workspace reload
```

## <a name="python-interoperability"></a>[Python birlikte çalışabilirliği](#tab/tabid-python)


Yöntemini kullanarak, Python ana bilgisayarında kullanılabilecek ek paketleri kullanılabilir hale getirebilirsiniz [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages) .
Örneğin, bir I not defterinde kullanmak üzere [**Microsoft. hisse. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) paketini eklemek Için Q# aşağıdaki python kodunu çalıştırın:

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

Bu komutun ardından paket kullanılarak derlenen tüm kodlar için kullanılabilir hale getirilir Q# `qsharp.compile` .
Paketi Q# geçerli çalışma alanındaki koddan kullanılabilir hale getirmek için, paketinizi ekledikten sonra çalışma alanını yeniden yükleyin:

```python
qsharp.reload()
```

***
