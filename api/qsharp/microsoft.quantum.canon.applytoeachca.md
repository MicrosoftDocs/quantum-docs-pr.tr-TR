---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: ApplyToEachCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: b24fbb8c7a1a55c0a7750c5d096a61f4824dadfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729293"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="5320a-102">ApplyToEachCA işlemi</span><span class="sxs-lookup"><span data-stu-id="5320a-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="5320a-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5320a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5320a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5320a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5320a-105">Bir kayıttaki her öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="5320a-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="5320a-106">Değiştirici, `CA` tek qubit işleminin denetlenebilir ve adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="5320a-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="5320a-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="5320a-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj--ctl"></a><span data-ttu-id="5320a-108">singleElementOperation: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="5320a-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5320a-109">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="5320a-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="5320a-110">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="5320a-110">register : 'T[]</span></span>

<span data-ttu-id="5320a-111">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="5320a-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5320a-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5320a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5320a-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="5320a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5320a-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="5320a-114">'T</span></span>

<span data-ttu-id="5320a-115">İşlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="5320a-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="5320a-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5320a-116">See Also</span></span>

- [<span data-ttu-id="5320a-117">Microsoft. hisse. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="5320a-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)