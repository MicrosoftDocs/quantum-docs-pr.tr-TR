---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: e034f0a24d5c2f0465ebd1914b28cb8c695d978c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730578"
---
# <a name="reflectaboutinteger-operation"></a><span data-ttu-id="9d502-102">ReflectAboutInteger işlemi</span><span class="sxs-lookup"><span data-stu-id="9d502-102">ReflectAboutInteger operation</span></span>

<span data-ttu-id="9d502-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9d502-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9d502-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9d502-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9d502-105">Belirli bir klasik tamsayı hakkında hisse bir kayıt yansıtır.</span><span class="sxs-lookup"><span data-stu-id="9d502-105">Reflects a quantum register about a given classical integer.</span></span>

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="9d502-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="9d502-106">Description</span></span>

<span data-ttu-id="9d502-107">Başlangıçta $ \ sum_i \ alpha_i \ket{i} $ durumunda bir hisse kayıt verildi her $ \ket{i} $, bir tamsayıyı temsil eden temel bir durumdur $i $, belirli bir tamsayı $ \ket{j} $, $ $ \ sum_i (-1) ^ {\ delta_ {ij}} \ alpha_i \ket{i} $ $ gibi kaydın durumunu yansıtır.</span><span class="sxs-lookup"><span data-stu-id="9d502-107">Given a quantum register initially in the state $\sum_i \alpha_i \ket{i}$, where each $\ket{i}$ is a basis state representing an integer $i$, reflects the state of the register about the basis state for a given integer $\ket{j}$, $$ \sum_i (-1)^{ \delta_{ij} } \alpha_i \ket{i} $$</span></span>

## <a name="input"></a><span data-ttu-id="9d502-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="9d502-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="9d502-109">Dizin: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9d502-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9d502-110">Klasik tamsayı dizin oluşturma ile ilgili temel durumu oluşturur.</span><span class="sxs-lookup"><span data-stu-id="9d502-110">The classical integer indexing the basis state about which to reflect.</span></span>


### <a name="reg--littleendian"></a><span data-ttu-id="9d502-111">reg: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9d502-111">reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="9d502-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d502-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9d502-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9d502-113">Remarks</span></span>

<span data-ttu-id="9d502-114">Bu işlem, ek yardımcı qubits 'in açıkça ayrılması gerekmeden yerinde uygulanır.</span><span class="sxs-lookup"><span data-stu-id="9d502-114">This operation is implemented in-place, without explicit allocation of additional auxiliary qubits.</span></span>