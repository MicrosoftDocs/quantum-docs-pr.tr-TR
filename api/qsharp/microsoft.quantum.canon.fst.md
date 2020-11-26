---
uid: Microsoft.Quantum.Canon.Fst
title: FST işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 634f11881a054df7fe79d889832ea6bd80a7394f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206944"
---
# <a name="fst-function"></a><span data-ttu-id="0d6ef-102">FST işlevi</span><span class="sxs-lookup"><span data-stu-id="0d6ef-102">Fst function</span></span>

<span data-ttu-id="0d6ef-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0d6ef-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0d6ef-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0d6ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0d6ef-105">Bir çift verildiğinde, ilk öğesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="0d6ef-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="0d6ef-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="0d6ef-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="0d6ef-107">Çift: ('T, ' U)</span><span class="sxs-lookup"><span data-stu-id="0d6ef-107">pair : ('T,'U)</span></span>

<span data-ttu-id="0d6ef-108">İki öğe içeren bir tanımlama grubu.</span><span class="sxs-lookup"><span data-stu-id="0d6ef-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="0d6ef-109">Çıkış: 'T</span><span class="sxs-lookup"><span data-stu-id="0d6ef-109">Output : 'T</span></span>

<span data-ttu-id="0d6ef-110">İlk öğesi `pair` .</span><span class="sxs-lookup"><span data-stu-id="0d6ef-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0d6ef-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="0d6ef-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0d6ef-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="0d6ef-112">'T</span></span>

<span data-ttu-id="0d6ef-113">Çiftin ilk üyesinin türü.</span><span class="sxs-lookup"><span data-stu-id="0d6ef-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="0d6ef-114">' U</span><span class="sxs-lookup"><span data-stu-id="0d6ef-114">'U</span></span>

<span data-ttu-id="0d6ef-115">Çiftin ikinci üyesinin türü.</span><span class="sxs-lookup"><span data-stu-id="0d6ef-115">The type of the pair's second member.</span></span>