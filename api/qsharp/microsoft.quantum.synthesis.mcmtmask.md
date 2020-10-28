---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 0d3ca12d55fa4b5e8332d50939954de29e39b715
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734074"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="7e1f9-102">MCMTMask Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="7e1f9-102">MCMTMask user defined type</span></span>

<span data-ttu-id="7e1f9-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="7e1f9-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="7e1f9-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7e1f9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7e1f9-105">Birden çok kontrollü birden çok hedef Toffoli geçidini temsil eden bir tür.</span><span class="sxs-lookup"><span data-stu-id="7e1f9-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="7e1f9-106">İlk tamsayı, denetim hatları için bir bit maskesidir.</span><span class="sxs-lookup"><span data-stu-id="7e1f9-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="7e1f9-107">Ayarlanan bit dizinleri denetim satırı dizinlerine karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="7e1f9-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="7e1f9-108">İkinci tamsayı, hedef satırlar için bir bit maskesidir.</span><span class="sxs-lookup"><span data-stu-id="7e1f9-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="7e1f9-109">Ayarlanan bit dizinleri hedef satırı dizinlerine karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="7e1f9-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="7e1f9-110">Her iki tamsayının bit dizinlerinin ayrık olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="7e1f9-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="7e1f9-111">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="7e1f9-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="7e1f9-112">ControlMask: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7e1f9-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="7e1f9-113">TargetMask: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7e1f9-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

