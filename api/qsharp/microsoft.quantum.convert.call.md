---
uid: Microsoft.Quantum.Convert.Call
title: Çağrı işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 93458d08aa83ffa8b7b33de8bf51c970af291db9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850205"
---
# <a name="call-operation"></a><span data-ttu-id="ab62d-102">Çağrı işlemi</span><span class="sxs-lookup"><span data-stu-id="ab62d-102">Call operation</span></span>

<span data-ttu-id="ab62d-103">Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="ab62d-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="ab62d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ab62d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ab62d-105">Verilen bir girişi olan bir işlev çağırır.</span><span class="sxs-lookup"><span data-stu-id="ab62d-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="ab62d-106">Description</span><span class="sxs-lookup"><span data-stu-id="ab62d-106">Description</span></span>

<span data-ttu-id="ab62d-107">Bir işlev ve bu işleve bir giriş verildiğinde, işlevi çağırır ve çıktısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="ab62d-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="ab62d-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="ab62d-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="ab62d-109">FN: ' Input-> ' çıkışı</span><span class="sxs-lookup"><span data-stu-id="ab62d-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="ab62d-110">Çağrılacak işlev.</span><span class="sxs-lookup"><span data-stu-id="ab62d-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="ab62d-111">Giriş: ' giriş</span><span class="sxs-lookup"><span data-stu-id="ab62d-111">input : 'Input</span></span>

<span data-ttu-id="ab62d-112">İşleve geçirilecek giriş.</span><span class="sxs-lookup"><span data-stu-id="ab62d-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="ab62d-113">Çıkış: ' çıkış</span><span class="sxs-lookup"><span data-stu-id="ab62d-113">Output : 'Output</span></span>

<span data-ttu-id="ab62d-114">Çağırmanın sonucu `fn` .</span><span class="sxs-lookup"><span data-stu-id="ab62d-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ab62d-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ab62d-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="ab62d-116">' Giriş</span><span class="sxs-lookup"><span data-stu-id="ab62d-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="ab62d-117">' Çıkış</span><span class="sxs-lookup"><span data-stu-id="ab62d-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="ab62d-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ab62d-118">Remarks</span></span>

<span data-ttu-id="ab62d-119">Bu işlem, bir işlevin bir işlem içinde belirli bir yerde çağrılmasını zorlamak için veya bir işlemin beklendiği bir işlevi çağırmak için kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="ab62d-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>