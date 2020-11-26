---
uid: Microsoft.Quantum.Canon.DelayC
title: DelayC işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayC
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 7a11c3990802ff36856a90de927b38d2ede8bd9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216498"
---
# <a name="delayc-operation"></a><span data-ttu-id="0bfe0-102">DelayC işlemi</span><span class="sxs-lookup"><span data-stu-id="0bfe0-102">DelayC operation</span></span>

<span data-ttu-id="0bfe0-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0bfe0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0bfe0-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0bfe0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0bfe0-105">Bir gecikmeyle belirli bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="0bfe0-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayC<'T> (op : ('T => Unit is Ctl), arg : 'T, aux : Unit) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="0bfe0-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0bfe0-106">Description</span></span>

<span data-ttu-id="0bfe0-107">Bir işlem ve bu işlem için bir giriş verildiğinde, ek bir giriş sağlandıktan sonra işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="0bfe0-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="0bfe0-108">Özellikle, ifade `Delay(op, arg, _)` çağrıldığında için geçerli olan bir işlemdir `op` `arg` .</span><span class="sxs-lookup"><span data-stu-id="0bfe0-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="0bfe0-109">İfade `Delay(op,arg,_)` , uygulamasını gecikmeye izin verir `op` .</span><span class="sxs-lookup"><span data-stu-id="0bfe0-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="0bfe0-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="0bfe0-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="0bfe0-111">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="0bfe0-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="0bfe0-112">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="0bfe0-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="0bfe0-113">bağımsız değişken: 'T</span><span class="sxs-lookup"><span data-stu-id="0bfe0-113">arg : 'T</span></span>

<span data-ttu-id="0bfe0-114">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="0bfe0-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="0bfe0-115">Aux: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0bfe0-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="0bfe0-116">Kısmi uygulama kullanarak işlemin uygulamasını geciktirmek için kullanılan bağımsız değişken.</span><span class="sxs-lookup"><span data-stu-id="0bfe0-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0bfe0-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0bfe0-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0bfe0-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="0bfe0-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0bfe0-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="0bfe0-119">'T</span></span>

<span data-ttu-id="0bfe0-120">Gecikecek işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="0bfe0-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="0bfe0-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0bfe0-121">See Also</span></span>

- [<span data-ttu-id="0bfe0-122">Microsoft. hisse. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="0bfe0-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="0bfe0-123">Microsoft. hisse. Canon. Gecikmeli</span><span class="sxs-lookup"><span data-stu-id="0bfe0-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)