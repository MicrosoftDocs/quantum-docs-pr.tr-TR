---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: 4d451c4e8e002f86c892b394f58ea2d7e9dd6a48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842987"
---
# <a name="reflectaboutinteger-operation"></a><span data-ttu-id="6f720-102">ReflectAboutInteger işlemi</span><span class="sxs-lookup"><span data-stu-id="6f720-102">ReflectAboutInteger operation</span></span>

<span data-ttu-id="6f720-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6f720-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6f720-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f720-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f720-105">Belirli bir klasik tamsayı hakkında hisse bir kayıt yansıtır.</span><span class="sxs-lookup"><span data-stu-id="6f720-105">Reflects a quantum register about a given classical integer.</span></span>

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="6f720-106">Description</span><span class="sxs-lookup"><span data-stu-id="6f720-106">Description</span></span>

<span data-ttu-id="6f720-107">Başlangıçta $ \ sum_i \ alpha_i \ket{i} $ durumunda bir hisse kayıt verildi her $ \ket{i} $, bir tamsayıyı temsil eden temel bir durumdur $i $, belirli bir tamsayı $ \ket{j} $, $ $ \ sum_i (-1) ^ {\ delta_ {ij}} \ alpha_i \ket{i} $ $ gibi kaydın durumunu yansıtır.</span><span class="sxs-lookup"><span data-stu-id="6f720-107">Given a quantum register initially in the state $\sum_i \alpha_i \ket{i}$, where each $\ket{i}$ is a basis state representing an integer $i$, reflects the state of the register about the basis state for a given integer $\ket{j}$, $$ \sum_i (-1)^{ \delta_{ij} } \alpha_i \ket{i} $$</span></span>

## <a name="input"></a><span data-ttu-id="6f720-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="6f720-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="6f720-109">Dizin: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6f720-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6f720-110">Klasik tamsayı dizin oluşturma ile ilgili temel durumu oluşturur.</span><span class="sxs-lookup"><span data-stu-id="6f720-110">The classical integer indexing the basis state about which to reflect.</span></span>


### <a name="reg--littleendian"></a><span data-ttu-id="6f720-111">reg: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6f720-111">reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="6f720-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6f720-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6f720-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6f720-113">Remarks</span></span>

<span data-ttu-id="6f720-114">Bu işlem, ek yardımcı qubits 'in açıkça ayrılması gerekmeden yerinde uygulanır.</span><span class="sxs-lookup"><span data-stu-id="6f720-114">This operation is implemented in-place, without explicit allocation of additional auxiliary qubits.</span></span>