---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9485c6549ed4e1a6fb3abdfa3f85ba35579d8b0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729305"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="a7adb-102">ApplyToEachA işlemi</span><span class="sxs-lookup"><span data-stu-id="a7adb-102">ApplyToEachA operation</span></span>

<span data-ttu-id="a7adb-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a7adb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a7adb-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a7adb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a7adb-105">Bir kayıttaki her öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="a7adb-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="a7adb-106">Değiştirici, `A` tek qubit işleminin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="a7adb-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a7adb-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="a7adb-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj"></a><span data-ttu-id="a7adb-108">singleElementOperation: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="a7adb-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="a7adb-109">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="a7adb-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="a7adb-110">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="a7adb-110">register : 'T[]</span></span>

<span data-ttu-id="a7adb-111">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="a7adb-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a7adb-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a7adb-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a7adb-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="a7adb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a7adb-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="a7adb-114">'T</span></span>

<span data-ttu-id="a7adb-115">İşlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="a7adb-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7adb-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a7adb-116">See Also</span></span>

- [<span data-ttu-id="a7adb-117">Microsoft. hisse. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="a7adb-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)