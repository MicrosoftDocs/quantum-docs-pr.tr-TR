---
title: Q# Programlama Dili
description: Kuantum program geliştirme için Q# diline giriş.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: b62e6866fc3609d95c26a5eab2a6eac325dfe330
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907384"
---
# <a name="the-q-programming-language"></a><span data-ttu-id="ba097-103">Q# Programlama Dili</span><span class="sxs-lookup"><span data-stu-id="ba097-103">The Q# Programming Language</span></span>

## <a name="introduction"></a><span data-ttu-id="ba097-104">Giriş</span><span class="sxs-lookup"><span data-stu-id="ba097-104">Introduction</span></span>

<span data-ttu-id="ba097-105">Kuantum bilgisayarını GPU’lar, FPGA’lar ve diğer yardımcı işlemciler için kullanılanlara benzer şekilde bir ortak işlemci olarak işleme almak, kuantum bilişimi için doğal bir modeldir.</span><span class="sxs-lookup"><span data-stu-id="ba097-105">A natural model for quantum computation is to treat the quantum computer as a coprocessor, similar to that used for GPUs, FPGAs, and other adjunct processors.</span></span>
<span data-ttu-id="ba097-106">Birincil kontrol mantığı, klasik bir "konak" bilgisayar üzerinde klasik kod çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="ba097-106">The primary control logic runs classical code on a classical "host" computer.</span></span>
<span data-ttu-id="ba097-107">Uygun ve gerekli olduğunda, konak programı yardımcı işlemci üzerinde çalışan bir alt yordamı çağırabilir.</span><span class="sxs-lookup"><span data-stu-id="ba097-107">When appropriate and necessary, the host program can invoke a subroutine that runs on the adjunct processor.</span></span>
<span data-ttu-id="ba097-108">Alt yordam tamamlandığında, konak programı alt yordamın sonuçlarına erişim elde eder.</span><span class="sxs-lookup"><span data-stu-id="ba097-108">When the subroutine completes, the host program gets access to the subroutine's results.</span></span>

<span data-ttu-id="ba097-109">Q# (Q-sharp), kuantum algoritmalarını ifade etmek için kullanılan, etki alanına özel bir programlama dilidir.</span><span class="sxs-lookup"><span data-stu-id="ba097-109">Q# (Q-sharp) is a domain-specific programming language used for expressing quantum algorithms.</span></span>
<span data-ttu-id="ba097-110">Klasik bir konak program ve bilgisayarın kontrolü altında bir yardımcı kuantum işlemcisi üzerinde yürütülen alt yordamlar yazmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="ba097-110">It is to be used for writing subroutines that execute on an adjunct quantum processor, under the control of a classical host program and computer.</span></span>
<span data-ttu-id="ba097-111">Kuantum işlemcileri yaygın olarak kullanılabilir hale gelene kadar Q# alt yordamları bir simülatör üzerinde yürütülür.</span><span class="sxs-lookup"><span data-stu-id="ba097-111">Until quantum processors are widely available, Q# subroutines execute on a simulator.</span></span>

<span data-ttu-id="ba097-112">Q# yeni ve yapılandırılmış türler oluşturmaya yönelik iki yol (diziler ve demetler) ile birlikte küçük bir temel tür kümesi sağlar.</span><span class="sxs-lookup"><span data-stu-id="ba097-112">Q# provides a small set of primitive types, along with two ways (arrays and tuples) for creating new, structured types.</span></span>
<span data-ttu-id="ba097-113">Döngüler ve if/then deyimleriyle program yazmaya yönelik temel bir yordamsal modeli destekler.</span><span class="sxs-lookup"><span data-stu-id="ba097-113">It supports a basic procedural model for writing programs, with loops and if/then statements.</span></span>
<span data-ttu-id="ba097-114">Q# içindeki üst düzey yapılar kullanıcı tanımlı türler, işlemler ve işlevlerdir.</span><span class="sxs-lookup"><span data-stu-id="ba097-114">The top-level constructs in Q# are user defined types, operations, and functions.</span></span>

<span data-ttu-id="ba097-115">Aşağıdaki bölümlerde ayrıntılı olarak şu konular açıklanmaktadır:</span><span class="sxs-lookup"><span data-stu-id="ba097-115">The following sections detail:</span></span>
- [<span data-ttu-id="ba097-116">Tür Modeli</span><span class="sxs-lookup"><span data-stu-id="ba097-116">The Type Model</span></span>](xref:microsoft.quantum.language.type-model)
- [<span data-ttu-id="ba097-117">İfadeler</span><span class="sxs-lookup"><span data-stu-id="ba097-117">Expressions</span></span>](xref:microsoft.quantum.language.expressions)
- [<span data-ttu-id="ba097-118">Deyimler</span><span class="sxs-lookup"><span data-stu-id="ba097-118">Statements</span></span>](xref:microsoft.quantum.language.statements)
- [<span data-ttu-id="ba097-119">Dosya Yapısı</span><span class="sxs-lookup"><span data-stu-id="ba097-119">File Structure</span></span>](xref:microsoft.quantum.language.file-structure)

## <a name="conventions"></a><span data-ttu-id="ba097-120">Kurallar</span><span class="sxs-lookup"><span data-stu-id="ba097-120">Conventions</span></span>

<span data-ttu-id="ba097-121">Tüm durumlarda genel noktalama işaretlerinin tutarlı bir şekilde kullanıldığından emin olmak için çalışıyoruz.</span><span class="sxs-lookup"><span data-stu-id="ba097-121">We are working to ensure that common punctuation marks are used consistently in all situations.</span></span>
<span data-ttu-id="ba097-122">Bu işaretler her zaman aynı anlama geldiğinden ve aynı kavram her zaman aynı şekilde temsil edildiğinden böylece Q# dilinin daha kolay öğrenilebileceğini ve okunabileceğini umuyoruz.</span><span class="sxs-lookup"><span data-stu-id="ba097-122">We expect that this will make Q# easier to learn and to read because these marks always mean the same thing, and the same concept is always represented the same way.</span></span>

<span data-ttu-id="ba097-123">Daha ayrıntılı şekilde belirtmek gerekirse:</span><span class="sxs-lookup"><span data-stu-id="ba097-123">Specifically:</span></span>

- <span data-ttu-id="ba097-124">Noktalı virgül, `;`, bir deyimi veya tek satırlık yönergeyi sonlandırmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="ba097-124">The semi-colon, `;`, is used to end a statement or single-line directive.</span></span>
  <span data-ttu-id="ba097-125">Başka bir amaçla kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="ba097-125">It is not used for any other purpose.</span></span>
- <span data-ttu-id="ba097-126">Virgül, `,`, bir dizinin öğelerini ayırmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="ba097-126">The comma, `,`, is used to separate elements of a sequence.</span></span> <span data-ttu-id="ba097-127">Demet değişmez değerleri, dizi değişmez değerleri, bağımsız değişken listeleri, demet tanımları ve tür listeleri için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="ba097-127">It is used for tuple literals, array literals, argument lists, tuple definitions, and type lists.</span></span> <span data-ttu-id="ba097-128">**Önceki sürümlerden farklı olarak, `;` artık bir dizi değişmez değeri ayırıcısı olarak desteklenmemektedir.**</span><span class="sxs-lookup"><span data-stu-id="ba097-128">**In a change from earlier versions, `;` is no longer supported as an array literal separator.**</span></span>
- <span data-ttu-id="ba097-129">İki nokta üst üste, `:`, bir tür ek açıklaması oluşturmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="ba097-129">The colon, `:`, is used to introduce a type annotation.</span></span> <span data-ttu-id="ba097-130">Birincil olarak çağrılabilir imzalarda kullanılır.</span><span class="sxs-lookup"><span data-stu-id="ba097-130">It is primarily used in callable signatures.</span></span>
  <span data-ttu-id="ba097-131">İki nokta üst üste her zaman bir tür imzası oluşturduğundan, 0,3'te oluşturulan üç koşullu işleç true ve false değerlerini ayırmak için bir dikey çubuk (`|`) kullanır. Bu nedenle Q#, C'de olduğu gibi ayırıcı olarak iki nokta üst üste yerine `cond ? tval | fval` kullanır.</span><span class="sxs-lookup"><span data-stu-id="ba097-131">Because colon always introduces a type signature, the ternary conditional operator introduced in 0.3 uses a vertical bar, `|`, to separate the true and false values; thus, Q# uses `cond ? tval | fval` instead of the colon as separator as in C.</span></span>
  
