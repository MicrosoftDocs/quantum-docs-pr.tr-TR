---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 90e9f0c922a77fbb6d6faf8945d4f5d1c8ff33b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727560"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="d9af0-102">FunctionAsOperation işlevi</span><span class="sxs-lookup"><span data-stu-id="d9af0-102">FunctionAsOperation function</span></span>

<span data-ttu-id="d9af0-103">Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="d9af0-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="d9af0-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d9af0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d9af0-105">İşlevleri işlemlere dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="d9af0-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="d9af0-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="d9af0-106">Description</span></span>

<span data-ttu-id="d9af0-107">Bir işlev verildiğinde, bu işlevi çağıran ve başka hiçbir şey yapan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="d9af0-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="d9af0-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="d9af0-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="d9af0-109">FN: ' Input-> ' çıkışı</span><span class="sxs-lookup"><span data-stu-id="d9af0-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="d9af0-110">Bir işleme dönüştürülecek bir işlev.</span><span class="sxs-lookup"><span data-stu-id="d9af0-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="d9af0-111">Çıkış: ' Input => ' çıkışı</span><span class="sxs-lookup"><span data-stu-id="d9af0-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="d9af0-112">Bir işlem `op` `op(input)` , tümü için ile özdeş `fn(input)` `input` .</span><span class="sxs-lookup"><span data-stu-id="d9af0-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d9af0-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="d9af0-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="d9af0-114">' Giriş</span><span class="sxs-lookup"><span data-stu-id="d9af0-114">'Input</span></span>

<span data-ttu-id="d9af0-115">Dönüştürülecek işlevin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="d9af0-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="d9af0-116">' Çıkış</span><span class="sxs-lookup"><span data-stu-id="d9af0-116">'Output</span></span>

<span data-ttu-id="d9af0-117">Dönüştürülecek işlevin çıkış türü.</span><span class="sxs-lookup"><span data-stu-id="d9af0-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9af0-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d9af0-118">Remarks</span></span>

<span data-ttu-id="d9af0-119">Bu, genellikle bir işlemi giriş olarak bekleyen işlevlere veya işlemlere geçirmek için kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="d9af0-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>