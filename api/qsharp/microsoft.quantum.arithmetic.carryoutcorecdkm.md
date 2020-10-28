---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: Carrzı Corecdkm işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 6a292e66f6d9911d2a9075f6397f4f5ba97ec64d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731639"
---
# <a name="carryoutcorecdkm-operation"></a><span data-ttu-id="7c5fc-102">Carrzı Corecdkm işlemi</span><span class="sxs-lookup"><span data-stu-id="7c5fc-102">CarryOutCoreCDKM operation</span></span>

<span data-ttu-id="7c5fc-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7c5fc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7c5fc-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7c5fc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7c5fc-105">En yukarıdaki ApplyOuterCDKMAdder işlemiyle birlikte kullanılan Rippmacarryaddercdkm içindeki temel işlem, yani Ripplicarryaddercdkm 'nin iç işlemini elde etmek için bu işlemle birlikte kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7c5fc-105">The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM.</span></span> <span data-ttu-id="7c5fc-106">Bu işlem, alma qubit ' i hesaplar ve girişin bir bölümünde bir kapı yok dizisi uygular `ys` .</span><span class="sxs-lookup"><span data-stu-id="7c5fc-106">This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.</span></span>

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="7c5fc-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="7c5fc-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="7c5fc-108">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7c5fc-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7c5fc-109">İlk qubit kayıt.</span><span class="sxs-lookup"><span data-stu-id="7c5fc-109">First qubit register.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="7c5fc-110">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7c5fc-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7c5fc-111">İkinci qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="7c5fc-111">Second qubit register.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="7c5fc-112">anyalanla: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7c5fc-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7c5fc-113">Bu işleme, Ripptacarryaddercdkm içinde kullanılan anella qubit.</span><span class="sxs-lookup"><span data-stu-id="7c5fc-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="7c5fc-114">taşır: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7c5fc-114">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7c5fc-115">Ripptacarryaddercdkm işleminde qubit ' i çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="7c5fc-115">Carry out qubit in the RippleCarryAdderCDKM operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c5fc-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c5fc-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="7c5fc-117">Referanslar</span><span class="sxs-lookup"><span data-stu-id="7c5fc-117">References</span></span>

- <span data-ttu-id="7c5fc-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutın, David Petrie Moulton: "yeni bir 2004 hisse</span><span class="sxs-lookup"><span data-stu-id="7c5fc-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1