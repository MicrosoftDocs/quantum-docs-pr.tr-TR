---
title: 'Ek Q # kitaplıklarını kullanma'
description: 'Hisse uygun Q # kitaplıklarını daha fazla bilgi edinin.'
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
ms.openlocfilehash: b82113b925870d07c8a28aecd50176e009826062
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86872667"
---
# <a name="using-additional-q-libraries"></a>Ek Q # kitaplıklarını kullanma

Hisse geliştirme seti, Q # projelerinize eklenebilen _NuGet paketleri_ aracılığıyla alana özgü ek işlevler sağlar.

| S # kitaplığı  | NuGet paketi | Notlar |
|---------|---------|--------|
| [Q # standart kitaplığı](xref:microsoft.quantum.libraries.standard.intro) | [**Microsoft. hisse. Standart**](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | Varsayılan olarak eklendi |
| [Kuantum kimyası kitaplığı](xref:microsoft.quantum.chemistry.concepts.intro) | [**Microsoft.Quantum.Chemistry**](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [Kuantum sayısal kitaplığı](xref:microsoft.quantum.numerics.intro) | [**Microsoft. hisse. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [Kuantum makine öğrenimi kitaplığı](xref:microsoft.quantum.libraries.machine-learning.intro) | [**Microsoft.Quantum.MachineLearning**](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

Bir hisse geliştirme setini tercih ettiğiniz ortam ve ana bilgisayar diliyle kullanılmak üzere yükledikten sonra, başka bir yükleme yapmadan tek tek Q # projelerine kitaplıkları kolayca ekleyebilirsiniz.

> [!NOTE]
> Bazı Q # kitaplıkları, Q # programlarınızda birlikte çalışan veya ana bilgisayar uygulamalarınızla tümleştirilen ek araçlarla iyi çalışabilir.
> Örneğin, [Kimya kitaplığı yükleme yönergeleri](xref:microsoft.quantum.chemistry.concepts.installation) , [ **Microsoft. hisse. kimya** paketinin](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) nwchem hesaplama Kimya platformuyla birlikte nasıl kullanılacağını ve `qdk-chem` hisse atıkmistry verileriyle çalışmak için komut satırı araçlarının nasıl yükleneceğini açıklamaktadır.

## <a name="q-command-line-applications-or-net-interopability"></a>[Q # komut satırı uygulamaları veya .NET karşılıklı kullanılabilirliği](#tab/tabid-csproj)

**Komut satırı veya Visual Studio Code:** Komut satırını kendi başına veya Visual Studio Code içinden kullanarak `dotnet` projenize bir NuGet paket başvurusu eklemek için komutunu kullanabilirsiniz.
Örneğin, [**Microsoft. hisse. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) paketini eklemek için aşağıdaki komutu çalıştırın:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

**Visual Studio:** Visual Studio 2019 veya sonraki bir sürümü kullanıyorsanız, NuGet Paket Yöneticisi 'Ni kullanarak ek Q # paketleri ekleyebilirsiniz.
Bir paket yüklemek için: 
1. Visual Studio 'da açık bir proje ile, **Proje** menüsünden **NuGet Paketlerini Yönet...** öğesini seçin.

2. **Araştır**' a tıklayın, **ön sürümü dahil et** ' i seçin ve "Microsoft. hisse. Numerics" paket adını arayın. Bu, karşıdan yüklenebilecek paketleri listeler.

3. **Microsoft. hisse. Numerics** ' ın üzerine gelin ve sayı, sayı eklemek için sürüm numarasının sağ tarafındaki aşağı açılan oka tıklayın.

Daha ayrıntılı bilgi için bkz. [Paket Yöneticisi Kullanıcı Arabirimi Kılavuzu](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Alternatif olarak, komut satırı arabirimi aracılığıyla, sayılıcs kitaplığını projenize eklemek için Package Manager konsolunu kullanabilirsiniz.

![Paket Yöneticisi konsolunu komut satırından kullanma](~/media/vs2017-nuget-console-menu.png)

Paket Yöneticisi konsolundan aşağıdakileri çalıştırın:

```
Install-Package Microsoft.Quantum.Numerics
```

Daha ayrıntılı bilgi için bkz. [Paket Yöneticisi konsol Kılavuzu](https://docs.microsoft.com/nuget/tools/package-manager-console).

## <a name="iq-notebooks"></a>[IQ # Not defterleri](#tab/tabid-notebook)

[ `%package` MAGIC komutunu](xref:microsoft.quantum.iqsharp.magic-ref.package)kullanarak bir IQ # not defterinde kullanılmak üzere ek paketleri kullanılabilir hale getirebilirsiniz.
Örneğin, bir IQ # not defterinde kullanmak üzere [**Microsoft. hisse. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) paketini eklemek için bir not defteri hücresinde aşağıdaki komutu çalıştırın:

```
%package Microsoft.Quantum.Numerics
```

Bu komutun ardından, paket Not Defteri içindeki herhangi bir hücre için kullanılabilir.
Paketi geçerli çalışma alanındaki Q # kodundan kullanılabilir hale getirmek için paketinizi ekledikten sonra çalışma alanını yeniden yükleyin:

```
%workspace reload
```

## <a name="python-interoperability"></a>[Python birlikte çalışabilirliği](#tab/tabid-python)


Yöntemini kullanarak, Python ana bilgisayarında kullanılabilecek ek paketleri kullanılabilir hale getirebilirsiniz [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) .
Örneğin, IQ # not defterinde kullanmak üzere [**Microsoft. hisse. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) paketini eklemek Için aşağıdaki python kodunu çalıştırın:

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

Bu komutun ardından paket kullanılarak derlenen her bir Q # kodu için kullanılabilir hale getirilir `qsharp.compile` .
Paketi geçerli çalışma alanındaki Q # kodundan kullanılabilir hale getirmek için paketinizi ekledikten sonra çalışma alanını yeniden yükleyin:

```python
qsharp.reload()
```

***
