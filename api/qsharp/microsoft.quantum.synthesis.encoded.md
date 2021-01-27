---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Kodlanan işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855491"
---
# <a name="encoded-function"></a><span data-ttu-id="5fb10-102">Kodlanan işlev</span><span class="sxs-lookup"><span data-stu-id="5fb10-102">Encoded function</span></span>

<span data-ttu-id="5fb10-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="5fb10-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="5fb10-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5fb10-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5fb10-105">Kodlarken Truth tablosunu kodla {1,-1}</span><span class="sxs-lookup"><span data-stu-id="5fb10-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="5fb10-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="5fb10-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="5fb10-107">Tablo: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="5fb10-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="5fb10-108">Gerçeği değeri dizi olarak Truth tablosu</span><span class="sxs-lookup"><span data-stu-id="5fb10-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="5fb10-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5fb10-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5fb10-110">Tam sayı dizisi olarak Truth tablosu {1,-1}</span><span class="sxs-lookup"><span data-stu-id="5fb10-110">Truth table as array of {1,-1} integers</span></span>

## <a name="example"></a><span data-ttu-id="5fb10-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="5fb10-111">Example</span></span>

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```