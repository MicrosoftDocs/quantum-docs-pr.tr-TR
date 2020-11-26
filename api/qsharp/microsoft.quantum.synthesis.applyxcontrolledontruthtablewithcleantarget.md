---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: Applyxcontroltadontruthtablewithcleantarget işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 904ff7e2e7e81ee966846af120e9427f4e92301c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203272"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a><span data-ttu-id="1fc82-102">Applyxcontroltadontruthtablewithcleantarget işlemi</span><span class="sxs-lookup"><span data-stu-id="1fc82-102">ApplyXControlledOnTruthTableWithCleanTarget operation</span></span>

<span data-ttu-id="1fc82-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="1fc82-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="1fc82-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1fc82-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1fc82-105">@"microsoft.quantum.intrinsic.x" `target` `func` İçindeki klasik atama için Boolean işlevi true olarak değerlendirilirse, işlemini üzerine uygular `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="1fc82-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="1fc82-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="1fc82-106">Description</span></span>

<span data-ttu-id="1fc82-107">Bu işlem @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" , hedef qubitin $ \ket $ durumunda olduğu bilinen özel durumunu uygular {0} .</span><span class="sxs-lookup"><span data-stu-id="1fc82-107">This operation implements a special case of @"microsoft.quantum.synthesis.applyxcontrolledontruthtable", in which the target qubit is known to be in the $\ket{0}$ state.</span></span>

<span data-ttu-id="1fc82-108">Uygulama ve kapıları kullanımını sağlar @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="1fc82-108">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>  <span data-ttu-id="1fc82-109">Adjoint işleminin uygulanması en iyi duruma getirilmiştir ve ölçüm tabanlı kaldırma işlemini kullanır.</span><span class="sxs-lookup"><span data-stu-id="1fc82-109">The implementation of the adjoint operation is optimized and uses measurement-based uncomputation.</span></span>

## <a name="input"></a><span data-ttu-id="1fc82-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="1fc82-110">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="1fc82-111">Func: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1fc82-111">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1fc82-112">Büyük tamsayı olarak temsil edilen Boolean Truth tablosu</span><span class="sxs-lookup"><span data-stu-id="1fc82-112">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="1fc82-113">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1fc82-113">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1fc82-114">Denetim qubits 'i kaydetme</span><span class="sxs-lookup"><span data-stu-id="1fc82-114">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="1fc82-115">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1fc82-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1fc82-116">Hedef qubit ($ \ket {0} $ durumunda olmalıdır)</span><span class="sxs-lookup"><span data-stu-id="1fc82-116">Target qubit (must be in $\ket{0}$ state)</span></span>



## <a name="output--unit"></a><span data-ttu-id="1fc82-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1fc82-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="1fc82-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1fc82-118">See Also</span></span>

- [<span data-ttu-id="1fc82-119">Microsoft. hisse. Sensıs. Applyxcontroltadontruthtable</span><span class="sxs-lookup"><span data-stu-id="1fc82-119">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)