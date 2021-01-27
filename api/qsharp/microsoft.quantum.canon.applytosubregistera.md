---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterA
title: ApplyToSubregisterA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 7a5ae78edcda363f21cadaaed5cb273d35cb60cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841222"
---
# <a name="applytosubregistera-operation"></a><span data-ttu-id="0c7f0-102">ApplyToSubregisterA işlemi</span><span class="sxs-lookup"><span data-stu-id="0c7f0-102">ApplyToSubregisterA operation</span></span>

<span data-ttu-id="0c7f0-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0c7f0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0c7f0-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0c7f0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0c7f0-105">Bir kaydın alt kaydına bir işlem uygular, bu, dizinlerinin bir dizisi tarafından belirtilen qubits ile.</span><span class="sxs-lookup"><span data-stu-id="0c7f0-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="0c7f0-106">Değiştirici, `A` işlemin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="0c7f0-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[], target : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="0c7f0-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="0c7f0-107">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="0c7f0-108">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="0c7f0-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="0c7f0-109">Alt kayda uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="0c7f0-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="0c7f0-110">ıdxs: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0c7f0-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0c7f0-111">İşlemin hangi qubits uygulanacağını gösteren dizin dizisi.</span><span class="sxs-lookup"><span data-stu-id="0c7f0-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="0c7f0-112">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0c7f0-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0c7f0-113">İşlemin işlem gördüğü kayıt.</span><span class="sxs-lookup"><span data-stu-id="0c7f0-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0c7f0-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0c7f0-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="0c7f0-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0c7f0-115">See Also</span></span>

- [<span data-ttu-id="0c7f0-116">Microsoft. hisse. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="0c7f0-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)