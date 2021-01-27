---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: RequiresCapability Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 5e0db49d6f73398ac36003eb0f44e3a6520b7f1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855146"
---
# <a name="requirescapability-user-defined-type"></a><span data-ttu-id="203a4-102">RequiresCapability Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="203a4-102">RequiresCapability user defined type</span></span>

<span data-ttu-id="203a4-103">Ad alanı: [Microsoft. hisse. hedefleme](xref:Microsoft.Quantum.Targeting)</span><span class="sxs-lookup"><span data-stu-id="203a4-103">Namespace: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span></span>

<span data-ttu-id="203a4-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="203a4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="203a4-105">Derleyici tarafından tanınan öznitelik, gereken çalışma zamanı yetenekleri ile çağrılabilir olarak işaretlemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="203a4-105">Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a><span data-ttu-id="203a4-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="203a4-106">Named Items</span></span>

### <a name="level--string"></a><span data-ttu-id="203a4-107">Düzey: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="203a4-107">Level : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="203a4-108">Çağrılabilir için gereken çalışma zamanı yetenek düzeyinin adı.</span><span class="sxs-lookup"><span data-stu-id="203a4-108">The name of the runtime capability level required by the callable.</span></span>
### <a name="reason--string"></a><span data-ttu-id="203a4-109">Neden: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="203a4-109">Reason : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="203a4-110">Çağrılabilir özelliğinin bu çalışma zamanı özelliğini neden gerektirdiğini bir açıklama.</span><span class="sxs-lookup"><span data-stu-id="203a4-110">A description of why the callable requires this runtime capability.</span></span>

## <a name="remarks"></a><span data-ttu-id="203a4-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="203a4-111">Remarks</span></span>

<span data-ttu-id="203a4-112">Çağrılabilir üzerinde bu özniteliğin bir örneği zaten mevcut değilse, bu öznitelik derleyici tarafından otomatik olarak eklenir.</span><span class="sxs-lookup"><span data-stu-id="203a4-112">This attribute is automatically added to callables by the compiler, unless an instance of this attribute already exists on the callable.</span></span> <span data-ttu-id="203a4-113">Derleyicinin gerekli özelliği doğru bir şekilde çıkarmadığından nadir durumlar dışında kullanılmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="203a4-113">It should not be used except in rare cases where the compiler does not infer the required capability correctly.</span></span>

<span data-ttu-id="203a4-114">Aşağıda, yetenek düzeyi adlarının, artırma özelliklerinin veya azalan kısıtlamaların sırası olarak listesi verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="203a4-114">Below is the list of capability level names, in order of increasing capabilities or decreasing restrictions:</span></span>

## `"BasicQuantumFunctionality"`

<span data-ttu-id="203a4-115">Ölçüm sonuçları eşitlik için karşılaştırılamaz.</span><span class="sxs-lookup"><span data-stu-id="203a4-115">Measurement results cannot be compared for equality.</span></span>

## `"BasicMeasurementFeedback"`

<span data-ttu-id="203a4-116">Ölçüm sonuçları yalnızca işlemlerdeki IF deyimi koşullu ifadelerinde eşitlik için karşılaştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="203a4-116">Measurement results can be compared for equality only in if-statement conditional expressions in operations.</span></span> <span data-ttu-id="203a4-117">Bir sonuca bağlı bir if-deyimi bloğu, blok dışında belirtilen kesilebilir değişkenler için set deyimleri içeremez ya da Return deyimleri olamaz.</span><span class="sxs-lookup"><span data-stu-id="203a4-117">The block of an if-statement that depends on a result cannot contain set statements for mutable variables declared outside the block, or return statements.</span></span>

## `"FullComputation"`

<span data-ttu-id="203a4-118">Çalışma zamanı kısıtlaması yok.</span><span class="sxs-lookup"><span data-stu-id="203a4-118">No runtime restrictions.</span></span> <span data-ttu-id="203a4-119">Herhangi bir Q # programı yürütülebilir.</span><span class="sxs-lookup"><span data-stu-id="203a4-119">Any Q# program can be executed.</span></span>