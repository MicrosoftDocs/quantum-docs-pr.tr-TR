---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: Lesssıme Lexographic işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 360088e31a47a7bb114bc0527edf600cd78740f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726041"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="da8cd-102">Lesssıme Lexographic işlevi</span><span class="sxs-lookup"><span data-stu-id="da8cd-102">LessThanLexographic function</span></span>

<span data-ttu-id="da8cd-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="da8cd-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="da8cd-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="da8cd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="da8cd-105">Uygulamak için kullanılır `LexographicComparison` .</span><span class="sxs-lookup"><span data-stu-id="da8cd-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="da8cd-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="da8cd-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="da8cd-107">Karşılaştırma: ('T, 'T)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="da8cd-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="da8cd-108">Sol: 'T []</span><span class="sxs-lookup"><span data-stu-id="da8cd-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="da8cd-109">Sağ: 'T []</span><span class="sxs-lookup"><span data-stu-id="da8cd-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="da8cd-110">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="da8cd-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="da8cd-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="da8cd-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="da8cd-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="da8cd-112">'T</span></span>

