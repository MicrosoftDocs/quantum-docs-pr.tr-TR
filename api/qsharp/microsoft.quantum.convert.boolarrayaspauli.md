---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c5ef71322dae248fc2c6b1db3adf891de7d72488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727601"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="a12c3-102">BoolArrayAsPauli işlevi</span><span class="sxs-lookup"><span data-stu-id="a12c3-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="a12c3-103">Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="a12c3-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="a12c3-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a12c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a12c3-105">Bir bit dizesi verildiğinde, tek qubit Pauli işleçleri dizisi olarak temsil edilen bir multi-qubit Pauli işleci döndürür.</span><span class="sxs-lookup"><span data-stu-id="a12c3-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="a12c3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a12c3-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="a12c3-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="a12c3-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="a12c3-108">Burada qubits 'e uygulanacak Pauli işleci `bitsApply == bits[idx]` .</span><span class="sxs-lookup"><span data-stu-id="a12c3-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="a12c3-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a12c3-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a12c3-110">bit Bu değer ise Pauli uygulayın.</span><span class="sxs-lookup"><span data-stu-id="a12c3-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="a12c3-111">bit: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="a12c3-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="a12c3-112">Boolean dizisi.</span><span class="sxs-lookup"><span data-stu-id="a12c3-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="a12c3-113">Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="a12c3-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="a12c3-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a12c3-114">Remarks</span></span>

<span data-ttu-id="a12c3-115">Boole dizisi ve hisse kayıt uzunluğu eşit olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a12c3-115">The Boolean array and the quantum register must be of equal length.</span></span>