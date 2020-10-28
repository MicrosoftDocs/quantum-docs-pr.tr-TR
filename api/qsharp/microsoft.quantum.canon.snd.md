---
uid: Microsoft.Quantum.Canon.Snd
title: SND işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c05053b45d24c3398526d1269b90bb40d1e0ef27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728393"
---
# <a name="snd-function"></a><span data-ttu-id="c030c-102">SND işlevi</span><span class="sxs-lookup"><span data-stu-id="c030c-102">Snd function</span></span>

<span data-ttu-id="c030c-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c030c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c030c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c030c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c030c-105">Bir çift verildiğinde, ikinci öğesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="c030c-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="c030c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c030c-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="c030c-107">Çift: ('T, ' U)</span><span class="sxs-lookup"><span data-stu-id="c030c-107">pair : ('T,'U)</span></span>

<span data-ttu-id="c030c-108">İki öğe içeren bir tanımlama grubu.</span><span class="sxs-lookup"><span data-stu-id="c030c-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="c030c-109">Çıkış: ' U</span><span class="sxs-lookup"><span data-stu-id="c030c-109">Output : 'U</span></span>

<span data-ttu-id="c030c-110">İkinci öğesi `pair` .</span><span class="sxs-lookup"><span data-stu-id="c030c-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c030c-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="c030c-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c030c-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="c030c-112">'T</span></span>

<span data-ttu-id="c030c-113">Çiftin ilk üyesinin türü.</span><span class="sxs-lookup"><span data-stu-id="c030c-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="c030c-114">' U</span><span class="sxs-lookup"><span data-stu-id="c030c-114">'U</span></span>

<span data-ttu-id="c030c-115">Çiftin ikinci üyesinin türü.</span><span class="sxs-lookup"><span data-stu-id="c030c-115">The type of the pair's second member.</span></span>