---
uid: Microsoft.Quantum.Canon.Snd
title: SND işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c935a2bc9e3f5ab32669feae2bfc0f2ebf57e744
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205329"
---
# <a name="snd-function"></a><span data-ttu-id="56b50-102">SND işlevi</span><span class="sxs-lookup"><span data-stu-id="56b50-102">Snd function</span></span>

<span data-ttu-id="56b50-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="56b50-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="56b50-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="56b50-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="56b50-105">Bir çift verildiğinde, ikinci öğesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="56b50-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="56b50-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="56b50-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="56b50-107">Çift: ('T, ' U)</span><span class="sxs-lookup"><span data-stu-id="56b50-107">pair : ('T,'U)</span></span>

<span data-ttu-id="56b50-108">İki öğe içeren bir tanımlama grubu.</span><span class="sxs-lookup"><span data-stu-id="56b50-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="56b50-109">Çıkış: ' U</span><span class="sxs-lookup"><span data-stu-id="56b50-109">Output : 'U</span></span>

<span data-ttu-id="56b50-110">İkinci öğesi `pair` .</span><span class="sxs-lookup"><span data-stu-id="56b50-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="56b50-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="56b50-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="56b50-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="56b50-112">'T</span></span>

<span data-ttu-id="56b50-113">Çiftin ilk üyesinin türü.</span><span class="sxs-lookup"><span data-stu-id="56b50-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="56b50-114">' U</span><span class="sxs-lookup"><span data-stu-id="56b50-114">'U</span></span>

<span data-ttu-id="56b50-115">Çiftin ikinci üyesinin türü.</span><span class="sxs-lookup"><span data-stu-id="56b50-115">The type of the pair's second member.</span></span>