---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: 444d42e2440b30b3bdf50d55a399568bed063222
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727283"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="15706-102">DumpOperation işlemi</span><span class="sxs-lookup"><span data-stu-id="15706-102">DumpOperation operation</span></span>

<span data-ttu-id="15706-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="15706-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="15706-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="15706-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="15706-105">Bir işlem verildiğinde, geçerli yürütme hedefi tarafından kullanılabilir hale getirilen işlem hakkındaki tanılamayı görüntüler.</span><span class="sxs-lookup"><span data-stu-id="15706-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="15706-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="15706-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="15706-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="15706-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="15706-108">Verilen işlemin işlem gördüğü qubit sayısı.</span><span class="sxs-lookup"><span data-stu-id="15706-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit-adj"></a><span data-ttu-id="15706-109">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama</span><span class="sxs-lookup"><span data-stu-id="15706-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="15706-110">Tanılanmakta olan işlem.</span><span class="sxs-lookup"><span data-stu-id="15706-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="15706-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15706-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="15706-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="15706-112">Remarks</span></span>

<span data-ttu-id="15706-113">Bu işlemin çağrılması, Q # içinden herhangi bir observable etkiye sahip değildir.</span><span class="sxs-lookup"><span data-stu-id="15706-113">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="15706-114">Varsa, görüntülenen tam Tanılamalar geçerli yürütme hedefi ve düzenleyici ortamına bağımlıdır.</span><span class="sxs-lookup"><span data-stu-id="15706-114">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="15706-115">Örneğin, tam durum hisse benzeticisinde kullanıldığında, göstermek için kullanılan bir Unitary matrisi `op` görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="15706-115">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="15706-116">Simülatörleri üzerinde çalıştırıldığında, bir genel aşama belirsizliğin (örneğin, tam durum simülatörü), döndürülen temsiller genel bir aşamaya kadar farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="15706-116">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="15706-117">Benzer şekilde, satır ve sütun matris temsilinin sıralaması, bu işlemi destekleyen her simülatör tarafından kullanılan kurallara göre farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="15706-117">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>