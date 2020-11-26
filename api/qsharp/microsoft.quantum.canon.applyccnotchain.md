---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: ApplyCCNOTChain işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: 275f31ea636d15eb0d78e5148e8af6b58d22729d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209664"
---
# <a name="applyccnotchain-operation"></a><span data-ttu-id="473c1-102">ApplyCCNOTChain işlemi</span><span class="sxs-lookup"><span data-stu-id="473c1-102">ApplyCCNOTChain operation</span></span>

<span data-ttu-id="473c1-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="473c1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="473c1-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="473c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="473c1-105">, Yazmaçların bir sonraki qubit ' i üzerinde işlem gören iki qubit kayıt 'nin karşılık gelen bitleri üzerinde denetlenen CCNOT kapıları basamaklandırmasını uygular.</span><span class="sxs-lookup"><span data-stu-id="473c1-105">Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers.</span></span>
<span data-ttu-id="473c1-106">Her iki kasada de 0 konumundaki qubits 'lerden başlayarak, CCNOT hedef yazmacın 1. konumunda ve ardından hedef kayıttaki qubits 'e, vb. konumdaki qubitlere göre kontrol edilir ve hedef kasada bir eylemle biter `Length(nQubits)-1` .</span><span class="sxs-lookup"><span data-stu-id="473c1-106">Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.</span></span>

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="473c1-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="473c1-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="473c1-108">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="473c1-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="473c1-109">Qubit yazmaç, yalnızca denetimler için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="473c1-109">Qubit register, only used for controls.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="473c1-110">hedefler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="473c1-110">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="473c1-111">Qubit yazmaç, denetimler ve hedef olarak kullanılır.</span><span class="sxs-lookup"><span data-stu-id="473c1-111">Qubit register, used for controls and as target.</span></span>



## <a name="output--unit"></a><span data-ttu-id="473c1-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="473c1-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="473c1-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="473c1-113">Remarks</span></span>

<span data-ttu-id="473c1-114">Hedef qubit kayıt, diğer kayıt özelliğinden daha fazla bir qubit olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="473c1-114">The target qubit register must have one qubit more than the other register.</span></span>