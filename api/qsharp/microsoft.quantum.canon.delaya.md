---
uid: Microsoft.Quantum.Canon.DelayA
title: DelayA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 77c40633824ccd9250252804b08d7400936515dd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728754"
---
# <a name="delaya-operation"></a><span data-ttu-id="ce353-102">DelayA işlemi</span><span class="sxs-lookup"><span data-stu-id="ce353-102">DelayA operation</span></span>

<span data-ttu-id="ce353-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ce353-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ce353-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ce353-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ce353-105">Bir gecikmeyle belirli bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="ce353-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a><span data-ttu-id="ce353-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ce353-106">Description</span></span>

<span data-ttu-id="ce353-107">Bir işlem ve bu işlem için bir giriş verildiğinde, ek bir giriş sağlandıktan sonra işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="ce353-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="ce353-108">Özellikle, ifade `Delay(op, arg, _)` çağrıldığında için geçerli olan bir işlemdir `op` `arg` .</span><span class="sxs-lookup"><span data-stu-id="ce353-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="ce353-109">İfade `Delay(op,arg,_)` , uygulamasını gecikmeye izin verir `op` .</span><span class="sxs-lookup"><span data-stu-id="ce353-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="ce353-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="ce353-110">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="ce353-111">Op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="ce353-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="ce353-112">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="ce353-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="ce353-113">bağımsız değişken: 'T</span><span class="sxs-lookup"><span data-stu-id="ce353-113">arg : 'T</span></span>

<span data-ttu-id="ce353-114">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="ce353-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="ce353-115">Aux: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ce353-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="ce353-116">Kısmi uygulama kullanarak işlemin uygulamasını geciktirmek için kullanılan bağımsız değişken.</span><span class="sxs-lookup"><span data-stu-id="ce353-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ce353-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ce353-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ce353-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ce353-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ce353-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="ce353-119">'T</span></span>

<span data-ttu-id="ce353-120">Gecikecek işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="ce353-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce353-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ce353-121">See Also</span></span>

- [<span data-ttu-id="ce353-122">Microsoft. hisse. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="ce353-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="ce353-123">Microsoft. hisse. Canon. Gecikmeli</span><span class="sxs-lookup"><span data-stu-id="ce353-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)