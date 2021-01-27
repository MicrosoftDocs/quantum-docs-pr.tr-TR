---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: cde188806506c586c4c77a7f9b2b43ad0e10ef1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829271"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="053fc-102">DumpOperation işlemi</span><span class="sxs-lookup"><span data-stu-id="053fc-102">DumpOperation operation</span></span>

<span data-ttu-id="053fc-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="053fc-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="053fc-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="053fc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="053fc-105">Bir işlem verildiğinde, geçerli yürütme hedefi tarafından kullanılabilir hale getirilen işlem hakkındaki tanılamayı görüntüler.</span><span class="sxs-lookup"><span data-stu-id="053fc-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="053fc-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="053fc-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="053fc-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="053fc-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="053fc-108">Verilen işlemin işlem gördüğü qubit sayısı.</span><span class="sxs-lookup"><span data-stu-id="053fc-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="053fc-109">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="053fc-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="053fc-110">Tanılanmakta olan işlem.</span><span class="sxs-lookup"><span data-stu-id="053fc-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="053fc-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="053fc-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="053fc-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="053fc-112">Example</span></span>

<span data-ttu-id="053fc-113">Hisse Benzetici hedefi üzerinde çalıştırıldığında, aşağıdaki kod parçacığı $ $ \begin{aligned} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \end{Matrix}\right) \end{aligned} matrisini çıktı.</span><span class="sxs-lookup"><span data-stu-id="053fc-113">When run on the quantum simulator target, the following snippet will output the matrix $$ \begin{aligned} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \end{matrix}\right) \end{aligned}.</span></span>
$$

```qsharp
operation DumpCnot() : Unit {
    DumpOperation(2, ApplyToFirstTwoQubitsCA(CNOT, _));
}
```

## <a name="remarks"></a><span data-ttu-id="053fc-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="053fc-114">Remarks</span></span>

<span data-ttu-id="053fc-115">Bu işlemin çağrılması, Q # içinden herhangi bir observable etkiye sahip değildir.</span><span class="sxs-lookup"><span data-stu-id="053fc-115">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="053fc-116">Varsa, görüntülenen tam Tanılamalar geçerli yürütme hedefi ve düzenleyici ortamına bağımlıdır.</span><span class="sxs-lookup"><span data-stu-id="053fc-116">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="053fc-117">Örneğin, tam durum hisse benzeticisinde kullanıldığında, göstermek için kullanılan bir Unitary matrisi `op` görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="053fc-117">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="053fc-118">Simülatörleri üzerinde çalıştırıldığında, bir genel aşama belirsizliğin (örneğin, tam durum simülatörü), döndürülen temsiller genel bir aşamaya kadar farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="053fc-118">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="053fc-119">Benzer şekilde, satır ve sütun matris temsilinin sıralaması, bu işlemi destekleyen her simülatör tarafından kullanılan kurallara göre farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="053fc-119">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>