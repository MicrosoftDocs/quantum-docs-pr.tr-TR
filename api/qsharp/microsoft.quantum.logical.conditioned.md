---
uid: Microsoft.Quantum.Logical.Conditioned
title: Koşullu işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: 8aabe8b018129ddee3b934c207d0a62e59fb6f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731295"
---
# <a name="conditioned-function"></a><span data-ttu-id="f5bdf-102">Koşullu işlev</span><span class="sxs-lookup"><span data-stu-id="f5bdf-102">Conditioned function</span></span>

<span data-ttu-id="f5bdf-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f5bdf-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f5bdf-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f5bdf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f5bdf-105">Boole koşulunun değerine bağlı olarak iki değerden birini döndürür.</span><span class="sxs-lookup"><span data-stu-id="f5bdf-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="f5bdf-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f5bdf-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="f5bdf-107">koşul: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f5bdf-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f5bdf-108">Hangi girişin döndürüleceğini denetlemek için kullanılan bir koşul.</span><span class="sxs-lookup"><span data-stu-id="f5bdf-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="f5bdf-109">IfTrue: 'T</span><span class="sxs-lookup"><span data-stu-id="f5bdf-109">ifTrue : 'T</span></span>

<span data-ttu-id="f5bdf-110">Olduğunda döndürülecek değer `condition` `true` .</span><span class="sxs-lookup"><span data-stu-id="f5bdf-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="f5bdf-111">IfFalse: 'T</span><span class="sxs-lookup"><span data-stu-id="f5bdf-111">ifFalse : 'T</span></span>

<span data-ttu-id="f5bdf-112">Olduğunda döndürülecek değer `condition` `false` .</span><span class="sxs-lookup"><span data-stu-id="f5bdf-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="f5bdf-113">Çıkış: 'T</span><span class="sxs-lookup"><span data-stu-id="f5bdf-113">Output : 'T</span></span>

<span data-ttu-id="f5bdf-114">`ifTrue` ise `condition` `true` ve `ifFalse` Aksi durumda.</span><span class="sxs-lookup"><span data-stu-id="f5bdf-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f5bdf-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="f5bdf-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f5bdf-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="f5bdf-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="f5bdf-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f5bdf-117">Remarks</span></span>

<span data-ttu-id="f5bdf-118">İşlecin aksine `?|` , bu işlev kısa devre değildir, her iki giriş de tam olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="f5bdf-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="f5bdf-119">En fazla kısa devre davranýþý, şunlar eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="f5bdf-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```