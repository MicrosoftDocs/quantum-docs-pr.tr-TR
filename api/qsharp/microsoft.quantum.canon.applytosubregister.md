---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: ApplyToSubregister işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: c9181b8962d36b20f7a9140eb7aaef11aee7faa0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729071"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="14a63-102">ApplyToSubregister işlemi</span><span class="sxs-lookup"><span data-stu-id="14a63-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="14a63-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="14a63-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="14a63-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="14a63-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="14a63-105">Bir kaydın alt kaydına bir işlem uygular, bu, dizinlerinin bir dizisi tarafından belirtilen qubits ile.</span><span class="sxs-lookup"><span data-stu-id="14a63-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="14a63-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="14a63-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="14a63-107">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14a63-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="14a63-108">Alt kayda uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="14a63-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="14a63-109">ıdxs: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="14a63-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="14a63-110">İşlemin hangi qubits uygulanacağını gösteren dizin dizisi.</span><span class="sxs-lookup"><span data-stu-id="14a63-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="14a63-111">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="14a63-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="14a63-112">İşlemin işlem gördüğü kayıt.</span><span class="sxs-lookup"><span data-stu-id="14a63-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="14a63-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14a63-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="14a63-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="14a63-114">See Also</span></span>

- [<span data-ttu-id="14a63-115">Microsoft. hisse. Canon. ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="14a63-115">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="14a63-116">Microsoft. hisse. Canon. ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="14a63-116">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="14a63-117">Microsoft. hisse. Canon. ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="14a63-117">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)