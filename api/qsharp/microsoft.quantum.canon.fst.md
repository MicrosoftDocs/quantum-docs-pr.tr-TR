---
uid: Microsoft.Quantum.Canon.Fst
title: FST işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 88ff5e29de9eeefcc1e207f277c37c63cb0faade
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728706"
---
# <a name="fst-function"></a><span data-ttu-id="1cddd-102">FST işlevi</span><span class="sxs-lookup"><span data-stu-id="1cddd-102">Fst function</span></span>

<span data-ttu-id="1cddd-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1cddd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1cddd-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1cddd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1cddd-105">Bir çift verildiğinde, ilk öğesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="1cddd-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="1cddd-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1cddd-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="1cddd-107">Çift: ('T, ' U)</span><span class="sxs-lookup"><span data-stu-id="1cddd-107">pair : ('T,'U)</span></span>

<span data-ttu-id="1cddd-108">İki öğe içeren bir tanımlama grubu.</span><span class="sxs-lookup"><span data-stu-id="1cddd-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="1cddd-109">Çıkış: 'T</span><span class="sxs-lookup"><span data-stu-id="1cddd-109">Output : 'T</span></span>

<span data-ttu-id="1cddd-110">İlk öğesi `pair` .</span><span class="sxs-lookup"><span data-stu-id="1cddd-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1cddd-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="1cddd-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1cddd-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="1cddd-112">'T</span></span>

<span data-ttu-id="1cddd-113">Çiftin ilk üyesinin türü.</span><span class="sxs-lookup"><span data-stu-id="1cddd-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="1cddd-114">' U</span><span class="sxs-lookup"><span data-stu-id="1cddd-114">'U</span></span>

<span data-ttu-id="1cddd-115">Çiftin ikinci üyesinin türü.</span><span class="sxs-lookup"><span data-stu-id="1cddd-115">The type of the pair's second member.</span></span>