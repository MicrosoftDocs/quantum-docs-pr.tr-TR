---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: 045f00a720e9f4d2e6993c66ace44a81e192ff30
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853472"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="33555-102">AssertOperationsEqualReferenced işlemi</span><span class="sxs-lookup"><span data-stu-id="33555-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="33555-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="33555-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="33555-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="33555-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="33555-105">İki işlem söz konusu olduğunda, tüm giriş durumları için aynı hareket ettikleri onaylar.</span><span class="sxs-lookup"><span data-stu-id="33555-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="33555-106">Bu onaylama işlemi, iki entanlı kasada bir qubit durum onaylamanın bir listesini azaltmak için Choi – Jamiołkowski isomorphism kullanılarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="33555-106">This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers.</span></span>
<span data-ttu-id="33555-107">Bu nedenle, bu işlem yalnızca sınanan her bir işlem için tek bir çağrıya gerek duyar, ancak ayrılacak sayıda qubit için iki kez gerekir.</span><span class="sxs-lookup"><span data-stu-id="33555-107">Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated.</span></span>
<span data-ttu-id="33555-108">Bu onaylama, örneğin, bir işlemin en iyi duruma getirilmiş bir sürümünün Naïve uygulamasına benzer bir şekilde davranması veya bir dizi hisse kullanım dışı girişleri üzerinde davranan bir işlemin bilinen durumları kabul ettiği bir işlem olduğundan emin olmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="33555-108">This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.</span></span>

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="33555-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="33555-109">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="33555-110">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="33555-110">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="33555-111">Her bir işleme geçirilecek qubit sayısı.</span><span class="sxs-lookup"><span data-stu-id="33555-111">Number of qubits to pass to each operation.</span></span>


### <a name="actual--qubit--unit"></a><span data-ttu-id="33555-112">gerçek: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33555-112">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="33555-113">Test edilecek işlem.</span><span class="sxs-lookup"><span data-stu-id="33555-113">Operation to be tested.</span></span>


### <a name="expected--qubit--unit--is-adj"></a><span data-ttu-id="33555-114">beklenen: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="33555-114">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="33555-115">Test edilen işlem için beklenen davranışı tanımlayan işlem.</span><span class="sxs-lookup"><span data-stu-id="33555-115">Operation defining the expected behavior for the operation under test.</span></span>



## <a name="output--unit"></a><span data-ttu-id="33555-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33555-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="33555-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="33555-117">Remarks</span></span>

<span data-ttu-id="33555-118">Bu işlem, yalnızca hedef kayıt üzerinde ters işlem yapılabilmesi için beklenen davranışı modelleyen işlemin adjointable olmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="33555-118">This operation requires that the operation modeling the expected behavior is adjointable, so that the inverse can be performed on the target register alone.</span></span>
<span data-ttu-id="33555-119">Tek bir tane, bu gereksinimi veren bir yeniden çevir işlemi belirtebilir, ancak devrik işlem, isteğe bağlı olarak rastgele bir işlem için genel olarak gerçekçi değildir ve bu nedenle bir seçenek olarak burada bulunmaz.</span><span class="sxs-lookup"><span data-stu-id="33555-119">Formally, one can specify a transpose operation, which relaxes this requirement, but the transpose operation is not in general physically realizable for arbitrary quantum operations and thus is not included here as an option.</span></span>