---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: 8e7088ec3918165d7b2afb1056a8319c6fb17796
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214288"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="93947-102">BoolArrayAsPauli işlevi</span><span class="sxs-lookup"><span data-stu-id="93947-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="93947-103">Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="93947-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="93947-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="93947-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="93947-105">Bir bit dizesi verildiğinde, tek qubit Pauli işleçleri dizisi olarak temsil edilen bir multi-qubit Pauli işleci döndürür.</span><span class="sxs-lookup"><span data-stu-id="93947-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="93947-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="93947-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="93947-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="93947-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="93947-108">Burada qubits 'e uygulanacak Pauli işleci `bitsApply == bits[idx]` .</span><span class="sxs-lookup"><span data-stu-id="93947-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="93947-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="93947-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="93947-110">bit Bu değer ise Pauli uygulayın.</span><span class="sxs-lookup"><span data-stu-id="93947-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="93947-111">bit: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="93947-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="93947-112">Boolean dizisi.</span><span class="sxs-lookup"><span data-stu-id="93947-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="93947-113">Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="93947-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="93947-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="93947-114">Remarks</span></span>

<span data-ttu-id="93947-115">Boole dizisi ve hisse kayıt uzunluğu eşit olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="93947-115">The Boolean array and the quantum register must be of equal length.</span></span>