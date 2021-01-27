---
uid: Microsoft.Quantum.Canon.Snd
title: SND işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: 11786fa195de12a7f2e4f2edb00ac0bc1071dd5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852164"
---
# <a name="snd-function"></a><span data-ttu-id="1b049-102">SND işlevi</span><span class="sxs-lookup"><span data-stu-id="1b049-102">Snd function</span></span>

<span data-ttu-id="1b049-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1b049-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1b049-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b049-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1b049-105">Bir çift verildiğinde, ikinci öğesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="1b049-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="1b049-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1b049-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="1b049-107">Çift: ('T, ' U)</span><span class="sxs-lookup"><span data-stu-id="1b049-107">pair : ('T,'U)</span></span>

<span data-ttu-id="1b049-108">İki öğe içeren bir tanımlama grubu.</span><span class="sxs-lookup"><span data-stu-id="1b049-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="1b049-109">Çıkış: ' U</span><span class="sxs-lookup"><span data-stu-id="1b049-109">Output : 'U</span></span>

<span data-ttu-id="1b049-110">İkinci öğesi `pair` .</span><span class="sxs-lookup"><span data-stu-id="1b049-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1b049-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="1b049-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1b049-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="1b049-112">'T</span></span>

<span data-ttu-id="1b049-113">Çiftin ilk üyesinin türü.</span><span class="sxs-lookup"><span data-stu-id="1b049-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="1b049-114">' U</span><span class="sxs-lookup"><span data-stu-id="1b049-114">'U</span></span>

<span data-ttu-id="1b049-115">Çiftin ikinci üyesinin türü.</span><span class="sxs-lookup"><span data-stu-id="1b049-115">The type of the pair's second member.</span></span>