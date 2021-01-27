---
uid: Microsoft.Quantum.Logical.Conditioned
title: Koşullu işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817296"
---
# <a name="conditioned-function"></a><span data-ttu-id="e1b16-102">Koşullu işlev</span><span class="sxs-lookup"><span data-stu-id="e1b16-102">Conditioned function</span></span>

<span data-ttu-id="e1b16-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e1b16-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e1b16-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e1b16-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e1b16-105">Boole koşulunun değerine bağlı olarak iki değerden birini döndürür.</span><span class="sxs-lookup"><span data-stu-id="e1b16-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="e1b16-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e1b16-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="e1b16-107">koşul: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e1b16-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e1b16-108">Hangi girişin döndürüleceğini denetlemek için kullanılan bir koşul.</span><span class="sxs-lookup"><span data-stu-id="e1b16-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="e1b16-109">IfTrue: 'T</span><span class="sxs-lookup"><span data-stu-id="e1b16-109">ifTrue : 'T</span></span>

<span data-ttu-id="e1b16-110">Olduğunda döndürülecek değer `condition` `true` .</span><span class="sxs-lookup"><span data-stu-id="e1b16-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="e1b16-111">IfFalse: 'T</span><span class="sxs-lookup"><span data-stu-id="e1b16-111">ifFalse : 'T</span></span>

<span data-ttu-id="e1b16-112">Olduğunda döndürülecek değer `condition` `false` .</span><span class="sxs-lookup"><span data-stu-id="e1b16-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="e1b16-113">Çıkış: 'T</span><span class="sxs-lookup"><span data-stu-id="e1b16-113">Output : 'T</span></span>

<span data-ttu-id="e1b16-114">`ifTrue` ise `condition` `true` ve `ifFalse` Aksi durumda.</span><span class="sxs-lookup"><span data-stu-id="e1b16-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e1b16-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="e1b16-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e1b16-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="e1b16-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="e1b16-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e1b16-117">Remarks</span></span>

<span data-ttu-id="e1b16-118">İşlecin aksine `?|` , bu işlev kısa devre değildir, her iki giriş de tam olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="e1b16-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="e1b16-119">En fazla kısa devre davranýþý, şunlar eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="e1b16-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```