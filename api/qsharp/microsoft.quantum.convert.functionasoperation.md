---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 10703818242cf6b3853f08a45bfb9094f397f6c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224386"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="f3d75-102">FunctionAsOperation işlevi</span><span class="sxs-lookup"><span data-stu-id="f3d75-102">FunctionAsOperation function</span></span>

<span data-ttu-id="f3d75-103">Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="f3d75-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="f3d75-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f3d75-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f3d75-105">İşlevleri işlemlere dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="f3d75-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="f3d75-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="f3d75-106">Description</span></span>

<span data-ttu-id="f3d75-107">Bir işlev verildiğinde, bu işlevi çağıran ve başka hiçbir şey yapan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="f3d75-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="f3d75-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="f3d75-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="f3d75-109">FN: ' Input-> ' çıkışı</span><span class="sxs-lookup"><span data-stu-id="f3d75-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="f3d75-110">Bir işleme dönüştürülecek bir işlev.</span><span class="sxs-lookup"><span data-stu-id="f3d75-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="f3d75-111">Çıkış: ' Input => ' çıkışı</span><span class="sxs-lookup"><span data-stu-id="f3d75-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="f3d75-112">Bir işlem `op` `op(input)` , tümü için ile özdeş `fn(input)` `input` .</span><span class="sxs-lookup"><span data-stu-id="f3d75-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f3d75-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="f3d75-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="f3d75-114">' Giriş</span><span class="sxs-lookup"><span data-stu-id="f3d75-114">'Input</span></span>

<span data-ttu-id="f3d75-115">Dönüştürülecek işlevin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="f3d75-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="f3d75-116">' Çıkış</span><span class="sxs-lookup"><span data-stu-id="f3d75-116">'Output</span></span>

<span data-ttu-id="f3d75-117">Dönüştürülecek işlevin çıkış türü.</span><span class="sxs-lookup"><span data-stu-id="f3d75-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="f3d75-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f3d75-118">Remarks</span></span>

<span data-ttu-id="f3d75-119">Bu, genellikle bir işlemi giriş olarak bekleyen işlevlere veya işlemlere geçirmek için kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="f3d75-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>