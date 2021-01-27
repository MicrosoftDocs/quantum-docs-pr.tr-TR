---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 50bec0f9aca95afab83491db6b742d1f0323371f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855371"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="8da01-102">MCMTMask Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="8da01-102">MCMTMask user defined type</span></span>

<span data-ttu-id="8da01-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="8da01-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="8da01-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8da01-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8da01-105">Birden çok kontrollü birden çok hedef Toffoli geçidini temsil eden bir tür.</span><span class="sxs-lookup"><span data-stu-id="8da01-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="8da01-106">İlk tamsayı, denetim hatları için bir bit maskesidir.</span><span class="sxs-lookup"><span data-stu-id="8da01-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="8da01-107">Ayarlanan bit dizinleri denetim satırı dizinlerine karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="8da01-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="8da01-108">İkinci tamsayı, hedef satırlar için bir bit maskesidir.</span><span class="sxs-lookup"><span data-stu-id="8da01-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="8da01-109">Ayarlanan bit dizinleri hedef satırı dizinlerine karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="8da01-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="8da01-110">Her iki tamsayının bit dizinlerinin ayrık olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="8da01-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="8da01-111">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="8da01-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="8da01-112">ControlMask: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8da01-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="8da01-113">TargetMask: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8da01-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

