---
uid: Microsoft.Quantum.Canon.Delay
title: Gecikme işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: c8ba128e44a9b217ec196e39ff1df639ef276784
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840649"
---
# <a name="delay-operation"></a><span data-ttu-id="714ba-102">Gecikme işlemi</span><span class="sxs-lookup"><span data-stu-id="714ba-102">Delay operation</span></span>

<span data-ttu-id="714ba-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="714ba-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="714ba-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="714ba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="714ba-105">Bir gecikmeyle belirli bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="714ba-105">Applies a given operation with a delay.</span></span>

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a><span data-ttu-id="714ba-106">Description</span><span class="sxs-lookup"><span data-stu-id="714ba-106">Description</span></span>

<span data-ttu-id="714ba-107">Bir işlem ve bu işlem için bir giriş verildiğinde, ek bir giriş sağlandıktan sonra işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="714ba-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="714ba-108">Özellikle, ifade `Delay(op, arg, _)` çağrıldığında için geçerli olan bir işlemdir `op` `arg` .</span><span class="sxs-lookup"><span data-stu-id="714ba-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="714ba-109">İfade `Delay(op,arg,_)` , uygulamasını gecikmeye izin verir `op` .</span><span class="sxs-lookup"><span data-stu-id="714ba-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="714ba-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="714ba-110">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="714ba-111">Op: 'T => ' U</span><span class="sxs-lookup"><span data-stu-id="714ba-111">op : 'T => 'U</span></span> 

<span data-ttu-id="714ba-112">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="714ba-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="714ba-113">bağımsız değişken: 'T</span><span class="sxs-lookup"><span data-stu-id="714ba-113">arg : 'T</span></span>

<span data-ttu-id="714ba-114">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="714ba-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="714ba-115">Aux: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="714ba-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="714ba-116">Kısmi uygulama kullanarak işlemin uygulamasını geciktirmek için kullanılan bağımsız değişken.</span><span class="sxs-lookup"><span data-stu-id="714ba-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--u"></a><span data-ttu-id="714ba-117">Çıkış: ' U</span><span class="sxs-lookup"><span data-stu-id="714ba-117">Output : 'U</span></span>



## <a name="type-parameters"></a><span data-ttu-id="714ba-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="714ba-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="714ba-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="714ba-119">'T</span></span>

<span data-ttu-id="714ba-120">Gecikecek işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="714ba-120">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="714ba-121">' U</span><span class="sxs-lookup"><span data-stu-id="714ba-121">'U</span></span>

<span data-ttu-id="714ba-122">Gecikecek işlemin dönüş türü.</span><span class="sxs-lookup"><span data-stu-id="714ba-122">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="714ba-123">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="714ba-123">See Also</span></span>

- [<span data-ttu-id="714ba-124">Microsoft. hisse. Canon. DelayC</span><span class="sxs-lookup"><span data-stu-id="714ba-124">Microsoft.Quantum.Canon.DelayC</span></span>](xref:Microsoft.Quantum.Canon.DelayC)
- [<span data-ttu-id="714ba-125">Microsoft. hisse. Canon. DelayA</span><span class="sxs-lookup"><span data-stu-id="714ba-125">Microsoft.Quantum.Canon.DelayA</span></span>](xref:Microsoft.Quantum.Canon.DelayA)
- [<span data-ttu-id="714ba-126">Microsoft. hisse. Canon. DelayCA</span><span class="sxs-lookup"><span data-stu-id="714ba-126">Microsoft.Quantum.Canon.DelayCA</span></span>](xref:Microsoft.Quantum.Canon.DelayCA)
- [<span data-ttu-id="714ba-127">Microsoft. hisse. Canon. Gecikmeli</span><span class="sxs-lookup"><span data-stu-id="714ba-127">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)