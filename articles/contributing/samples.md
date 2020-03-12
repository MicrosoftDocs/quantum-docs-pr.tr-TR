---
title: Microsoft QDK 'ye katkıda bulunan örnekler
description: Örnek kodun Microsoft Quantum Development Kit nasıl katkıda bulunabileceğinizi öğrenin (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
ms.openlocfilehash: 3bd0de04a448c74eea6c3e8e3a15dcbb19f9d705
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024160"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a><span data-ttu-id="6b993-103">Hisse geliştirme paketine katkıda bulunan örnekler</span><span class="sxs-lookup"><span data-stu-id="6b993-103">Contributing Samples to the Quantum Development Kit</span></span>

<span data-ttu-id="6b993-104">[Örnek deposuna](https://github.com/Microsoft/Quantum)kod katkıda bulunmak istiyorsanız, hisse geliştirme topluluğunun daha iyi bir yerde olmasını istediğiniz için teşekkürler!</span><span class="sxs-lookup"><span data-stu-id="6b993-104">If you're interested in contributing code to the [samples repository](https://github.com/Microsoft/Quantum), thank you for making the quantum development community a better place!</span></span>

## <a name="the-quantum-development-kit-samples-repository"></a><span data-ttu-id="6b993-105">Hisse geliştirme seti örnekleri deposu</span><span class="sxs-lookup"><span data-stu-id="6b993-105">The Quantum Development Kit Samples Repository</span></span>

<span data-ttu-id="6b993-106">Katkılarınızı mümkün olduğunca hızlı bir şekilde hazırlamanıza yardımcı olmak için, örnek deposunun nasıl düzenlendiği hakkında hızlı bir bakış yapmanız yararlı olur:</span><span class="sxs-lookup"><span data-stu-id="6b993-106">To help you prepare your contribution to help out as much as possible, it's helpful to take a quick look at how the samples repository is laid out:</span></span>

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

<span data-ttu-id="6b993-107">Diğer bir deyişle, [Microsoft/hisse deposundaki](https://github.com/microsoft/Quantum) örnekler, `algorithms/`, `arithmetic/`veya `characterization/`gibi farklı klasörlere konu alanı tarafından ayrılır.</span><span class="sxs-lookup"><span data-stu-id="6b993-107">That is, the samples in the [microsoft/Quantum repository](https://github.com/microsoft/Quantum) are broken down by subject area into different folders such as `algorithms/`, `arithmetic/`, or `characterization/`.</span></span>
<span data-ttu-id="6b993-108">Her bir konu alanının klasörü içinde her örnek, bir kullanıcının bu örneği araştırmasını ve kullanması gereken her şeyi toplayan tek bir klasörden oluşur.</span><span class="sxs-lookup"><span data-stu-id="6b993-108">Within the folder for each subject area, each sample consists of a single folder that collects everything a user will need to explore and make use of that sample.</span></span>

## <a name="how-samples-are-structured"></a><span data-ttu-id="6b993-109">Örnekler nasıl yapılandırılır?</span><span class="sxs-lookup"><span data-stu-id="6b993-109">How Samples are Structured</span></span>

<span data-ttu-id="6b993-110">Her bir klasörü oluşturan dosyalara bakarak [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) örneğine göz atalım.</span><span class="sxs-lookup"><span data-stu-id="6b993-110">Looking at the files that make up each folder, let's dive into the [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) sample.</span></span>

| <span data-ttu-id="6b993-111">Dosya</span><span class="sxs-lookup"><span data-stu-id="6b993-111">File</span></span>              | <span data-ttu-id="6b993-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6b993-112">Description</span></span>                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | <span data-ttu-id="6b993-113">.NET Core SDK örneği oluşturmak için kullanılan Q # projesi</span><span class="sxs-lookup"><span data-stu-id="6b993-113">Q# project used to build the sample with the .NET Core SDK</span></span> |
| `Game.qs`         | <span data-ttu-id="6b993-114">Q # işlem ve örnek için işlevler</span><span class="sxs-lookup"><span data-stu-id="6b993-114">Q# operations and functions for the sample</span></span>                 |
| `Host.cs`         | <span data-ttu-id="6b993-115">C#örneği çalıştırmak için kullanılan ana bilgisayar programı</span><span class="sxs-lookup"><span data-stu-id="6b993-115">C# host program used to run the sample</span></span>                     |
| `host.py`         | <span data-ttu-id="6b993-116">Örneği çalıştırmak için kullanılan Python konak programı</span><span class="sxs-lookup"><span data-stu-id="6b993-116">Python host program used to run the sample</span></span>                 |
| `README.md`       | <span data-ttu-id="6b993-117">Örneğin ne yaptığını ve nasıl kullanılacağını gösteren belgeler</span><span class="sxs-lookup"><span data-stu-id="6b993-117">Documentation on what the sample does and how to use it</span></span>    |

<span data-ttu-id="6b993-118">Örneklerin hepsi aynı dosya kümesine sahip olmaz (örneğin, bazı örnekler C#salt olabilir, diğerlerinin bir Python ana bilgisayarı olmayabilir veya bazı örnekler, çalışma verileri dosyalarının çalışmasını gerektirebilir).</span><span class="sxs-lookup"><span data-stu-id="6b993-118">Not all samples will have the exact same set of files (e.g.: some samples may be C#-only, others may not have a Python host, or some samples may require auxillary data files to work).</span></span>

## <a name="anatomy-of-a-helpful-readme-file"></a><span data-ttu-id="6b993-119">Faydalı bir BENIOKU dosyasının anatomumu</span><span class="sxs-lookup"><span data-stu-id="6b993-119">Anatomy of a Helpful README File</span></span>

<span data-ttu-id="6b993-120">Yalnızca önemli bir dosya olan `README.md` dosyası, kullanıcıların örneğinizi kullanmaya başlamak için ihtiyaç duyduğu bir dosyadır!</span><span class="sxs-lookup"><span data-stu-id="6b993-120">One especially important file, though, is the `README.md` file, as that's what users need to get started with your sample!</span></span>

<span data-ttu-id="6b993-121">Her `README.md` katkılarınızı bulmaya docs.microsoft.com/samples yardımcı olan bazı meta verilerle başlamalıdır.</span><span class="sxs-lookup"><span data-stu-id="6b993-121">Each `README.md` should start with some metadata that helps docs.microsoft.com/samples find your contribution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6b993-122">Chsh-Game örneğinin nasıl oluşturulduğunu görün</span><span class="sxs-lookup"><span data-stu-id="6b993-122">See how the chsh-game sample is rendered</span></span>](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

<span data-ttu-id="6b993-123">Bu meta veriler, örneklerinizin hangi dilleri kapsadığını belirten bir [YAML üst bilgisi](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) olarak sağlanır (genellikle bu `qsharp`, `csharp`ve `python`) ve örneklerinizin hangi ürünleri kapsadığını (genellikle, yalnızca `qdk`) gösterir.</span><span class="sxs-lookup"><span data-stu-id="6b993-123">This metadata is provided as a [YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) that indicates what languages your sample covers (typically, this will be `qsharp`, `csharp`, and `python`), and what products your sample covers (typically, just `qdk`).</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> <span data-ttu-id="6b993-124">Docs.microsoft.com/samples adresinde görünmesi için üstbilgideki `page_type: sample` anahtarı gereklidir.</span><span class="sxs-lookup"><span data-stu-id="6b993-124">The `page_type: sample` key in the header is required for your sample to appear at docs.microsoft.com/samples.</span></span>
> <span data-ttu-id="6b993-125">Benzer şekilde, `product` ve `language` anahtarları, kullanıcıların örneğinizi bulmasına ve çalıştırmasına yardımcı olmak için önemlidir.</span><span class="sxs-lookup"><span data-stu-id="6b993-125">Similarly, the `product` and `language` keys are critical for helping users to find and run your sample.</span></span>

<span data-ttu-id="6b993-126">Bundan sonra, yeni örneklerinizin ne yaptığını belirten kısa bir giriş sağlamak yararlı olur:</span><span class="sxs-lookup"><span data-stu-id="6b993-126">After that, it's helpful to give a short intro that says what your new sample does:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

<span data-ttu-id="6b993-127">Ayrıca, örneklerinizin kullanıcıları bu uygulamayı çalıştırmak için gerekenleri de daha da bilir (ör. kullanıcıları yalnızca hisse alım geliştirme paketine ihtiyaç duyar veya Node. js gibi ek yazılımlara gerek duyuyor musunuz?):</span><span class="sxs-lookup"><span data-stu-id="6b993-127">Users of your sample will also appreciate knowing what they need to run it (e.g.: do users just need the Quantum Development Kit itself, or do they need additional software such as node.js?):</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

<span data-ttu-id="6b993-128">Her türlü yerde, kullanıcılara örneğinizi nasıl çalıştıracağınızı söyleyebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="6b993-128">With all that in place, you can tell users how to run your sample:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

<span data-ttu-id="6b993-129">Son olarak, kullanıcılara örnekteki her bir dosyanın ne yaptığını ve daha fazla bilgi için nereye gidebileceklerini söylemek yararlı olur:</span><span class="sxs-lookup"><span data-stu-id="6b993-129">Finally, it's helpful to tell users what each file in your sample does, and where they can go for more information:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> <span data-ttu-id="6b993-130">Örneğiniz docs.microsoft.com/samples adresinde işlendiğinde farklı bir URL 'de göründüğünden, burada mutlak URL 'Leri kullandığınızdan emin olun!</span><span class="sxs-lookup"><span data-stu-id="6b993-130">Make sure to use absolute URLs here, since your sample will appear at a different URL when rendered at docs.microsoft.com/samples!</span></span>
