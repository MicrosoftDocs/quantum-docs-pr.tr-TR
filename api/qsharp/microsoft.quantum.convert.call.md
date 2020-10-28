---
uid: Microsoft.Quantum.Convert.Call
title: Çağrı işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 8630f846b4b9823ce1c1dfd61dc8ca81e468517d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727571"
---
# <a name="call-operation"></a><span data-ttu-id="0bdd6-102">Çağrı işlemi</span><span class="sxs-lookup"><span data-stu-id="0bdd6-102">Call operation</span></span>

<span data-ttu-id="0bdd6-103">Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="0bdd6-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="0bdd6-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0bdd6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0bdd6-105">Verilen bir girişi olan bir işlev çağırır.</span><span class="sxs-lookup"><span data-stu-id="0bdd6-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="0bdd6-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0bdd6-106">Description</span></span>

<span data-ttu-id="0bdd6-107">Bir işlev ve bu işleve bir giriş verildiğinde, işlevi çağırır ve çıktısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="0bdd6-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="0bdd6-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="0bdd6-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="0bdd6-109">FN: ' Input-> ' çıkışı</span><span class="sxs-lookup"><span data-stu-id="0bdd6-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="0bdd6-110">Çağrılacak işlev.</span><span class="sxs-lookup"><span data-stu-id="0bdd6-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="0bdd6-111">Giriş: ' giriş</span><span class="sxs-lookup"><span data-stu-id="0bdd6-111">input : 'Input</span></span>

<span data-ttu-id="0bdd6-112">İşleve geçirilecek giriş.</span><span class="sxs-lookup"><span data-stu-id="0bdd6-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="0bdd6-113">Çıkış: ' çıkış</span><span class="sxs-lookup"><span data-stu-id="0bdd6-113">Output : 'Output</span></span>

<span data-ttu-id="0bdd6-114">Çağırmanın sonucu `fn` .</span><span class="sxs-lookup"><span data-stu-id="0bdd6-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0bdd6-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="0bdd6-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="0bdd6-116">' Giriş</span><span class="sxs-lookup"><span data-stu-id="0bdd6-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="0bdd6-117">' Çıkış</span><span class="sxs-lookup"><span data-stu-id="0bdd6-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="0bdd6-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0bdd6-118">Remarks</span></span>

<span data-ttu-id="0bdd6-119">Bu işlem, bir işlevin bir işlem içinde belirli bir yerde çağrılmasını zorlamak için veya bir işlemin beklendiği bir işlevi çağırmak için kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="0bdd6-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>