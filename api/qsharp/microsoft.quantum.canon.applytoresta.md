---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: ApplyToRestA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 99a18e835115491cc3451a4e3b44a6ff70e9dc6c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729090"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="94569-102">ApplyToRestA işlemi</span><span class="sxs-lookup"><span data-stu-id="94569-102">ApplyToRestA operation</span></span>

<span data-ttu-id="94569-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="94569-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="94569-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="94569-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="94569-105">Bir işlemi, bir dizinin ilk öğesi hariç tümüne uygular.</span><span class="sxs-lookup"><span data-stu-id="94569-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="94569-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="94569-106">Description</span></span>

<span data-ttu-id="94569-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="94569-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="94569-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="94569-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="94569-109">Op: 'T [] => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="94569-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="94569-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="94569-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="94569-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="94569-111">targets : 'T[]</span></span>

<span data-ttu-id="94569-112">Birincisi, ancak ilki uygulanacak bir dizi hedefi `op` .</span><span class="sxs-lookup"><span data-stu-id="94569-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="94569-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="94569-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="94569-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="94569-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="94569-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="94569-115">'T</span></span>

<span data-ttu-id="94569-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="94569-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="94569-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="94569-117">See Also</span></span>

- [<span data-ttu-id="94569-118">Microsoft. hisse. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="94569-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="94569-119">Microsoft. hisse. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="94569-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="94569-120">Microsoft. hisse. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="94569-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)