---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 9b17bac9d95baf5a542604892c64130bf35d7f69
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202439"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="c1868-102">AssertOperationsEqualInPlace işlemi</span><span class="sxs-lookup"><span data-stu-id="c1868-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="c1868-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c1868-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c1868-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c1868-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c1868-105">İki işlem söz konusu olduğunda, tüm giriş durumları için aynı hareket ettikleri onaylar.</span><span class="sxs-lookup"><span data-stu-id="c1868-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="c1868-106">Bu onaylama, formun tüm durumlarında işlem eylemi $V _0 \otimes... V_ {n-1} $, $V _k $ durumlardan biri $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ ve $ \ket{i} $ (Pauli Y işlecinin 1 eigenstate)</span><span class="sxs-lookup"><span data-stu-id="c1868-106">This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).</span></span>

<span data-ttu-id="c1868-107">Bu onaylama $n $ qubits kullanır ve karşılaştırılmakta olan işlemlere yönelik birden çok çağrı gerektirir.</span><span class="sxs-lookup"><span data-stu-id="c1868-107">This assertion uses $n$ qubits and requires multiple calls of the operations being compared.</span></span>

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="c1868-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="c1868-108">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="c1868-109">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c1868-109">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c1868-110">İşlemler `givenU` ve üzerinde çalışan qubits $n $ sayısı `expectedU` .</span><span class="sxs-lookup"><span data-stu-id="c1868-110">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="c1868-111">givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c1868-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c1868-112">$N $ qubits üzerinde işlem denetlenecek.</span><span class="sxs-lookup"><span data-stu-id="c1868-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="c1868-113">expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="c1868-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c1868-114">İle Karşılaştırılacak $n $ qubit üzerinde başvuru işlemi `givenU` .</span><span class="sxs-lookup"><span data-stu-id="c1868-114">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c1868-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c1868-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="c1868-116">Başvurular</span><span class="sxs-lookup"><span data-stu-id="c1868-116">References</span></span>

<span data-ttu-id="c1868-117">$ \Ket {0} $, $ \ket {1} $, $ \ket{+} $ ve $ \ket{i} $ durumlarının temeli [ *i. L. Chuang, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001)bölümünde açıklanan Chuang-Nielsen temelidir.</span><span class="sxs-lookup"><span data-stu-id="c1868-117">The basis of states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ is the Chuang-Nielsen basis, described in [ *I. L. Chuang, M. A. Nielsen* ](https://arxiv.org/abs/quant-ph/9610001).</span></span>

## <a name="see-also"></a><span data-ttu-id="c1868-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c1868-118">See Also</span></span>

- [<span data-ttu-id="c1868-119">Microsoft. hisse. Diagnostics. AssertOperationsEqualReferenced</span><span class="sxs-lookup"><span data-stu-id="c1868-119">Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)