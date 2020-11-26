---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: _ExtractLogicalQubitFromSteaneCode işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: 273692efa629cb8cc20069ef500c4e0902fbc3ff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201351"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a><span data-ttu-id="a1a39-102">_ExtractLogicalQubitFromSteaneCode işlemi</span><span class="sxs-lookup"><span data-stu-id="a1a39-102">_ExtractLogicalQubitFromSteaneCode operation</span></span>

<span data-ttu-id="a1a39-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="a1a39-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="a1a39-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a1a39-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a1a39-105">Syndrome ölçümü ve ekleme 'nin tersi.</span><span class="sxs-lookup"><span data-stu-id="a1a39-105">Syndrome measurement and the inverse of embedding.</span></span>

<span data-ttu-id="a1a39-106">$X $-ve $Z $-sabitleyiciler, kodlama devresinin belirli bir seçimi nedeniyle eşit olarak değerlendirilmez.</span><span class="sxs-lookup"><span data-stu-id="a1a39-106">$X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit.</span></span>
<span data-ttu-id="a1a39-107">Bu asymmetry, farklı bir sendromu ayıklama yordamına yol açar.</span><span class="sxs-lookup"><span data-stu-id="a1a39-107">This asymmetry leads to a different syndrome extraction routine.</span></span>
<span data-ttu-id="a1a39-108">Bir diğeri doğrudan kod durumunda Multi-qubitpauli işlecini ölçerek sendromu 'yi ölçebilir, ancak bu amaç için mantıksal qubit tek bir qubit 'e döndürülür, bu da daha fazla beğenilmesi gerekmeden sendromu ölçümlerinin yapılabileceği bir şekilde.</span><span class="sxs-lookup"><span data-stu-id="a1a39-108">One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.</span></span>

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a><span data-ttu-id="a1a39-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="a1a39-109">Input</span></span>

### <a name="code--logicalregister"></a><span data-ttu-id="a1a39-110">kod: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="a1a39-110">code : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>





## <a name="output--qubitintint"></a><span data-ttu-id="a1a39-111">Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="a1a39-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="a1a39-112">$X $-Syndrome ve $Z $-Syndrome için mantıksal qubit ve tamsayı çifti.</span><span class="sxs-lookup"><span data-stu-id="a1a39-112">The logical qubit and a pair of integers for $X$-syndrome and $Z$-syndrome.</span></span>
<span data-ttu-id="a1a39-113">Tek bir $X $-veya $Z $-hatanın ölçülen Syndrome neden olacağı bir kod qubit dizinini temsil ederler.</span><span class="sxs-lookup"><span data-stu-id="a1a39-113">They represent the index of the code qubit on which a single $X$- or $Z$-error would have caused the measured syndrome.</span></span>

## <a name="remarks"></a><span data-ttu-id="a1a39-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a1a39-114">Remarks</span></span>

<span data-ttu-id="a1a39-115">`internal`Birim testleri doğrudan bu işleme bağlı olduğundan, bu işlemin olarak işaretlenmediğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="a1a39-115">Note that this operation is not marked as `internal`, as unit tests directly depend on this operation.</span></span> <span data-ttu-id="a1a39-116">Gelecekteki bir geliştirme olarak, birim testlerinin yalnızca genel olarak yalnızca ortak callaba 'ya göre yeniden düzenlenmiş olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="a1a39-116">As a future improvement, unit tests should be refactored to depend only on public callables directly.</span></span>

> [!WARNING]
> <span data-ttu-id="a1a39-117">Bu yordam, Steane 'nin 7 qubit kodu için belirli bir kodlama devresine göre tasarlanmıştır; kodlama devresi değiştirilirse, sendromu sonucunun farklı şekilde yorumlanması gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="a1a39-117">This routine is tailored to a particular encoding circuit for Steane's 7 qubit code; if the encoding circuit is modified then the syndrome outcome might have to be interpreted differently.</span></span>