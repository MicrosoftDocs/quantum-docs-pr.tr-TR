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
ms.openlocfilehash: 20da0e1765a242c172cc595f03d7791a0e8b8d2d
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867530"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a><span data-ttu-id="33252-103">Hisse geliştirme paketine katkıda bulunan örnekler</span><span class="sxs-lookup"><span data-stu-id="33252-103">Contributing Samples to the Quantum Development Kit</span></span>

<span data-ttu-id="33252-104">[Örnek deposuna](https://github.com/Microsoft/Quantum)kod katkıda bulunmak istiyorsanız, hisse geliştirme topluluğunun daha iyi bir yerde olmasını istediğiniz için teşekkürler!</span><span class="sxs-lookup"><span data-stu-id="33252-104">If you're interested in contributing code to the [samples repository](https://github.com/Microsoft/Quantum), thank you for making the quantum development community a better place!</span></span>

## <a name="the-quantum-development-kit-samples-repository"></a><span data-ttu-id="33252-105">Hisse geliştirme seti örnekleri deposu</span><span class="sxs-lookup"><span data-stu-id="33252-105">The Quantum Development Kit Samples Repository</span></span>

<span data-ttu-id="33252-106">Katkılarınızı mümkün olduğunca hızlı bir şekilde hazırlamanıza yardımcı olmak için, örnek deposunun nasıl düzenlendiği hakkında hızlı bir bakış yapmanız yararlı olur:</span><span class="sxs-lookup"><span data-stu-id="33252-106">To help you prepare your contribution to help out as much as possible, it's helpful to take a quick look at how the samples repository is laid out:</span></span>

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

<span data-ttu-id="33252-107">Diğer bir deyişle, [Microsoft/hisse deposundaki](https://github.com/microsoft/Quantum) örnekler, veya gibi farklı klasörlere konu alanı tarafından ayrılır `algorithms/` `arithmetic/` `characterization/` .</span><span class="sxs-lookup"><span data-stu-id="33252-107">That is, the samples in the [microsoft/Quantum repository](https://github.com/microsoft/Quantum) are broken down by subject area into different folders such as `algorithms/`, `arithmetic/`, or `characterization/`.</span></span>
<span data-ttu-id="33252-108">Her bir konu alanının klasörü içinde her örnek, bir kullanıcının bu örneği araştırmasını ve kullanması gereken her şeyi toplayan tek bir klasörden oluşur.</span><span class="sxs-lookup"><span data-stu-id="33252-108">Within the folder for each subject area, each sample consists of a single folder that collects everything a user will need to explore and make use of that sample.</span></span>

## <a name="how-samples-are-structured"></a><span data-ttu-id="33252-109">Örnekler nasıl yapılandırılır?</span><span class="sxs-lookup"><span data-stu-id="33252-109">How Samples are Structured</span></span>

<span data-ttu-id="33252-110">Her bir klasörü oluşturan dosyalara bakarak [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) örneğe bakalım.</span><span class="sxs-lookup"><span data-stu-id="33252-110">Looking at the files that make up each folder, let's dive into the [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) sample.</span></span>

| <span data-ttu-id="33252-111">Dosya</span><span class="sxs-lookup"><span data-stu-id="33252-111">File</span></span>              | <span data-ttu-id="33252-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="33252-112">Description</span></span>                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | <span data-ttu-id="33252-113">Q#.NET Core SDK örneği oluşturmak için kullanılan proje</span><span class="sxs-lookup"><span data-stu-id="33252-113">Q# project used to build the sample with the .NET Core SDK</span></span> |
| `Game.qs`         | <span data-ttu-id="33252-114">Q#örnek için işlemler ve işlevler</span><span class="sxs-lookup"><span data-stu-id="33252-114">Q# operations and functions for the sample</span></span>                 |
| `Host.cs`         | <span data-ttu-id="33252-115">Örneği çalıştırmak için kullanılan C# ana bilgisayar programı</span><span class="sxs-lookup"><span data-stu-id="33252-115">C# host program used to run the sample</span></span>                     |
| `host.py`         | <span data-ttu-id="33252-116">Örneği çalıştırmak için kullanılan Python konak programı</span><span class="sxs-lookup"><span data-stu-id="33252-116">Python host program used to run the sample</span></span>                 |
| `README.md`       | <span data-ttu-id="33252-117">Örneğin ne yaptığını ve nasıl kullanılacağını gösteren belgeler</span><span class="sxs-lookup"><span data-stu-id="33252-117">Documentation on what the sample does and how to use it</span></span>    |

<span data-ttu-id="33252-118">Örneklerin hepsi aynı dosya kümesine sahip olmaz (örn. bazı örnekler yalnızca C# olabilir, diğerleri de bir Python konağına sahip olmayabilir veya bazı örnekler, iş için yardımcı veri dosyalarının çalışmasını gerektirebilir).</span><span class="sxs-lookup"><span data-stu-id="33252-118">Not all samples will have the exact same set of files (e.g.: some samples may be C#-only, others may not have a Python host, or some samples may require auxillary data files to work).</span></span>

## <a name="anatomy-of-a-helpful-readme-file"></a><span data-ttu-id="33252-119">Faydalı bir BENIOKU dosyasının anatomumu</span><span class="sxs-lookup"><span data-stu-id="33252-119">Anatomy of a Helpful README File</span></span>

<span data-ttu-id="33252-120">Özellikle önemli bir dosya, ancak `README.md` Bu dosya, kullanıcılarınızla çalışmaya başlamak için gereken şeydir.</span><span class="sxs-lookup"><span data-stu-id="33252-120">One especially important file, though, is the `README.md` file, as that's what users need to get started with your sample!</span></span>

<span data-ttu-id="33252-121">Her birinin `README.md` katkılarınızı bulmasına docs.Microsoft.com/Samples yardımcı olan bazı meta verilerle başlaması gerekir.</span><span class="sxs-lookup"><span data-stu-id="33252-121">Each `README.md` should start with some metadata that helps docs.microsoft.com/samples find your contribution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="33252-122">Chsh-Game örneğinin nasıl oluşturulduğunu görün</span><span class="sxs-lookup"><span data-stu-id="33252-122">See how the chsh-game sample is rendered</span></span>](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

<span data-ttu-id="33252-123">Bu meta veriler, örneklerinizin [YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) hangi dilleri kapsadığını (genellikle, bu, `qsharp` `csharp` , ve `python` ) ve örneklerinizin hangi ürünleri kapsadığını (genellikle, yalnızca) gösteren bir YAML üst bilgisi olarak sağlanır `qdk` .</span><span class="sxs-lookup"><span data-stu-id="33252-123">This metadata is provided as a [YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) that indicates what languages your sample covers (typically, this will be `qsharp`, `csharp`, and `python`), and what products your sample covers (typically, just `qdk`).</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> <span data-ttu-id="33252-124">`page_type: sample`Örneklerinizin docs.Microsoft.com/Samples adresinde görünmesi için üstbilgideki anahtar gereklidir.</span><span class="sxs-lookup"><span data-stu-id="33252-124">The `page_type: sample` key in the header is required for your sample to appear at docs.microsoft.com/samples.</span></span>
> <span data-ttu-id="33252-125">Benzer şekilde, `product` ve `language` anahtarları, kullanıcıların örneğinizi bulmasına ve çalıştırmasına yardımcı olmak için önemlidir.</span><span class="sxs-lookup"><span data-stu-id="33252-125">Similarly, the `product` and `language` keys are critical for helping users to find and run your sample.</span></span>

<span data-ttu-id="33252-126">Bundan sonra, yeni örneklerinizin ne yaptığını belirten kısa bir giriş sağlamak yararlı olur:</span><span class="sxs-lookup"><span data-stu-id="33252-126">After that, it's helpful to give a short intro that says what your new sample does:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

<span data-ttu-id="33252-127">Ayrıca, örneklerinizin kullanıcıları bu uygulamayı çalıştırmanın ne kadar olduğunu da anlarlar (ör. kullanıcıları yalnızca hisse alım geliştirme paketine ihtiyaç duyar veya node.js gibi ek yazılımlara gerek duyuyor musunuz?):</span><span class="sxs-lookup"><span data-stu-id="33252-127">Users of your sample will also appreciate knowing what they need to run it (e.g.: do users just need the Quantum Development Kit itself, or do they need additional software such as node.js?):</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

<span data-ttu-id="33252-128">Her türlü yerde, kullanıcılara örneğinizi nasıl çalıştıracağınızı söyleyebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="33252-128">With all that in place, you can tell users how to run your sample:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

<span data-ttu-id="33252-129">Son olarak, kullanıcılara örnekteki her bir dosyanın ne yaptığını ve daha fazla bilgi için nereye gidebileceklerini söylemek yararlı olur:</span><span class="sxs-lookup"><span data-stu-id="33252-129">Finally, it's helpful to tell users what each file in your sample does, and where they can go for more information:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> <span data-ttu-id="33252-130">Örneğiniz docs.microsoft.com/samples adresinde işlendiğinde farklı bir URL 'de göründüğünden, burada mutlak URL 'Leri kullandığınızdan emin olun!</span><span class="sxs-lookup"><span data-stu-id="33252-130">Make sure to use absolute URLs here, since your sample will appear at a different URL when rendered at docs.microsoft.com/samples!</span></span>
