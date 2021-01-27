---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: cf4f8c97bf38b3a64eb952d0a502bc21c29c579c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833833"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="5a729-102">FunctionAsOperation işlevi</span><span class="sxs-lookup"><span data-stu-id="5a729-102">FunctionAsOperation function</span></span>

<span data-ttu-id="5a729-103">Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="5a729-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="5a729-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5a729-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5a729-105">İşlevleri işlemlere dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="5a729-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="5a729-106">Description</span><span class="sxs-lookup"><span data-stu-id="5a729-106">Description</span></span>

<span data-ttu-id="5a729-107">Bir işlev verildiğinde, bu işlevi çağıran ve başka hiçbir şey yapan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="5a729-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="5a729-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="5a729-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="5a729-109">FN: ' Input-> ' çıkışı</span><span class="sxs-lookup"><span data-stu-id="5a729-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="5a729-110">Bir işleme dönüştürülecek bir işlev.</span><span class="sxs-lookup"><span data-stu-id="5a729-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="5a729-111">Çıkış: ' Input => ' çıkışı</span><span class="sxs-lookup"><span data-stu-id="5a729-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="5a729-112">Bir işlem `op` `op(input)` , tümü için ile özdeş `fn(input)` `input` .</span><span class="sxs-lookup"><span data-stu-id="5a729-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5a729-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="5a729-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="5a729-114">' Giriş</span><span class="sxs-lookup"><span data-stu-id="5a729-114">'Input</span></span>

<span data-ttu-id="5a729-115">Dönüştürülecek işlevin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="5a729-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="5a729-116">' Çıkış</span><span class="sxs-lookup"><span data-stu-id="5a729-116">'Output</span></span>

<span data-ttu-id="5a729-117">Dönüştürülecek işlevin çıkış türü.</span><span class="sxs-lookup"><span data-stu-id="5a729-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a729-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5a729-118">Remarks</span></span>

<span data-ttu-id="5a729-119">Bu, genellikle bir işlemi giriş olarak bekleyen işlevlere veya işlemlere geçirmek için kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="5a729-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>