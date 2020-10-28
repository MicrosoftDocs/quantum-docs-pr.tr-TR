---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: a3e8791321b4f2ca1885dffeb92c7b13e5491a32
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727325"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="25430-102">AssertOperationsEqualReferenced işlemi</span><span class="sxs-lookup"><span data-stu-id="25430-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="25430-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="25430-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="25430-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25430-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25430-105">İki işlem söz konusu olduğunda, tüm giriş durumları için aynı hareket ettikleri onaylar.</span><span class="sxs-lookup"><span data-stu-id="25430-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="25430-106">Bu onaylama işlemi, iki entanlı kasada bir qubit durum onaylamanın bir listesini azaltmak için Choi – Jamiołkowski isomorphism kullanılarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="25430-106">This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers.</span></span>
<span data-ttu-id="25430-107">Bu nedenle, bu işlem yalnızca sınanan her bir işlem için tek bir çağrıya gerek duyar, ancak ayrılacak sayıda qubit için iki kez gerekir.</span><span class="sxs-lookup"><span data-stu-id="25430-107">Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated.</span></span>
<span data-ttu-id="25430-108">Bu onaylama, örneğin, bir işlemin en iyi duruma getirilmiş bir sürümünün Naïve uygulamasına benzer bir şekilde davranması veya bir dizi hisse kullanım dışı girişleri üzerinde davranan bir işlemin bilinen durumları kabul ettiği bir işlem olduğundan emin olmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="25430-108">This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.</span></span>

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="25430-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="25430-109">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="25430-110">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="25430-110">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="25430-111">Her bir işleme geçirilecek qubit sayısı.</span><span class="sxs-lookup"><span data-stu-id="25430-111">Number of qubits to pass to each operation.</span></span>


### <a name="actual--qubit--unit"></a><span data-ttu-id="25430-112">gerçek: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="25430-112">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="25430-113">Test edilecek işlem.</span><span class="sxs-lookup"><span data-stu-id="25430-113">Operation to be tested.</span></span>


### <a name="expected--qubit--unit-adj"></a><span data-ttu-id="25430-114">beklenen: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="25430-114">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="25430-115">Test edilen işlem için beklenen davranışı tanımlayan işlem.</span><span class="sxs-lookup"><span data-stu-id="25430-115">Operation defining the expected behavior for the operation under test.</span></span>



## <a name="output--unit"></a><span data-ttu-id="25430-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="25430-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="25430-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="25430-117">Remarks</span></span>

<span data-ttu-id="25430-118">Bu işlem, yalnızca hedef kayıt üzerinde ters işlem yapılabilmesi için beklenen davranışı modelleyen işlemin adjointable olmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="25430-118">This operation requires that the operation modeling the expected behavior is adjointable, so that the inverse can be performed on the target register alone.</span></span>
<span data-ttu-id="25430-119">Tek bir tane, bu gereksinimi veren bir yeniden çevir işlemi belirtebilir, ancak devrik işlem, isteğe bağlı olarak rastgele bir işlem için genel olarak gerçekçi değildir ve bu nedenle bir seçenek olarak burada bulunmaz.</span><span class="sxs-lookup"><span data-stu-id="25430-119">Formally, one can specify a transpose operation, which relaxes this requirement, but the transpose operation is not in general physically realizable for arbitrary quantum operations and thus is not included here as an option.</span></span>