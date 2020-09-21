---
title: Microsoft QDK 'ye katkıda bulunan örnekler
description: Örnek kodun Microsoft Quantum Development Kit nasıl katkıda bulunabileceğinizi öğrenin (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
no-loc:
- Q#
- $$v
ms.openlocfilehash: ae29614cc9c8bf965ea3cb373dc17470aec21252
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759195"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a>Hisse geliştirme paketine katkıda bulunan örnekler

[Örnek deposuna](https://github.com/Microsoft/Quantum)kod katkıda bulunmak istiyorsanız, hisse geliştirme topluluğunun daha iyi bir yerde olmasını istediğiniz için teşekkürler!

## <a name="the-quantum-development-kit-samples-repository"></a>Hisse geliştirme seti örnekleri deposu

Katkılarınızı mümkün olduğunca hızlı bir şekilde hazırlamanıza yardımcı olmak için, örnek deposunun nasıl düzenlendiği hakkında hızlı bir bakış yapmanız yararlı olur:

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

Diğer bir deyişle, [Microsoft/hisse deposundaki](https://github.com/microsoft/Quantum) örnekler, veya gibi farklı klasörlere konu alanı tarafından ayrılır `algorithms/` `arithmetic/` `characterization/` .
Her bir konu alanının klasörü içinde her örnek, bir kullanıcının bu örneği araştırmasını ve kullanması gereken her şeyi toplayan tek bir klasörden oluşur.

## <a name="how-samples-are-structured"></a>Örnekler nasıl yapılandırılır?

Her bir klasörü oluşturan dosyalara bakarak [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/chsh-game) örneğe bakalım.

| Dosya              | Description                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | Q# .NET Core SDK örneği oluşturmak için kullanılan proje |
| `Game.qs`         | Q# örnek için işlemler ve işlevler                 |
| `Host.cs`         | Örneği çalıştırmak için kullanılan C# ana bilgisayar programı                     |
| `host.py`         | Örneği çalıştırmak için kullanılan Python konak programı                 |
| `README.md`       | Örneğin ne yaptığını ve nasıl kullanılacağını gösteren belgeler    |

Örneklerin hepsi aynı dosya kümesine sahip olmaz (örn. bazı örnekler yalnızca C# olabilir, diğerleri de bir Python konağına sahip olmayabilir veya bazı örnekler, iş için yardımcı veri dosyalarının çalışmasını gerektirebilir).

## <a name="anatomy-of-a-helpful-readme-file"></a>Faydalı bir BENIOKU dosyasının anatomumu

Özellikle önemli bir dosya, ancak `README.md` Bu dosya, kullanıcılarınızla çalışmaya başlamak için gereken şeydir.

Her birinin `README.md` katkılarınızı bulmasına docs.Microsoft.com/Samples yardımcı olan bazı meta verilerle başlaması gerekir.

> [!div class="nextstepaction"]
> [Chsh-Game örneğinin nasıl oluşturulduğunu görün](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

Bu meta veriler, örneklerinizin [YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) hangi dilleri kapsadığını (genellikle, bu, `qsharp` `csharp` , ve `python` ) ve örneklerinizin hangi ürünleri kapsadığını (genellikle, yalnızca) gösteren bir YAML üst bilgisi olarak sağlanır `qdk` .

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> `page_type: sample`Örneklerinizin docs.Microsoft.com/Samples adresinde görünmesi için üstbilgideki anahtar gereklidir.
> Benzer şekilde, `product` ve `language` anahtarları, kullanıcıların örneğinizi bulmasına ve çalıştırmasına yardımcı olmak için önemlidir.

Bundan sonra, yeni örneklerinizin ne yaptığını belirten kısa bir giriş sağlamak yararlı olur:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

Ayrıca, örneklerinizin kullanıcıları bu uygulamayı çalıştırmanın ne kadar olduğunu da anlarlar (ör. kullanıcıları yalnızca hisse alım geliştirme paketine ihtiyaç duyar veya node.js gibi ek yazılımlara gerek duyuyor musunuz?):

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

Her türlü yerde, kullanıcılara örneğinizi nasıl çalıştıracağınızı söyleyebilirsiniz:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

Son olarak, kullanıcılara örnekteki her bir dosyanın ne yaptığını ve daha fazla bilgi için nereye gidebileceklerini söylemek yararlı olur:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> Örneğiniz docs.microsoft.com/samples adresinde işlendiğinde farklı bir URL 'de göründüğünden, burada mutlak URL 'Leri kullandığınızdan emin olun!
