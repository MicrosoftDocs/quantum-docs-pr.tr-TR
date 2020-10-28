---
uid: Microsoft.Quantum.Math.PlusA
title: PlusA işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 0c6fdcf7c59dc5d89bf83e285339046b5ad5a57e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725886"
---
# <a name="plusa-function"></a><span data-ttu-id="30d51-102">PlusA işlevi</span><span class="sxs-lookup"><span data-stu-id="30d51-102">PlusA function</span></span>

<span data-ttu-id="30d51-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="30d51-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="30d51-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="30d51-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="30d51-105">İki girişin toplamını (birleştirme) döndürür.</span><span class="sxs-lookup"><span data-stu-id="30d51-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="30d51-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="30d51-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="30d51-107">a: ' element []</span><span class="sxs-lookup"><span data-stu-id="30d51-107">a : 'Element[]</span></span>

<span data-ttu-id="30d51-108">Toplanacak ilk giriş $a $.</span><span class="sxs-lookup"><span data-stu-id="30d51-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="30d51-109">b: ' öğe []</span><span class="sxs-lookup"><span data-stu-id="30d51-109">b : 'Element[]</span></span>

<span data-ttu-id="30d51-110">Toplanacak ikinci giriş $b $.</span><span class="sxs-lookup"><span data-stu-id="30d51-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="30d51-111">Output: ' element []</span><span class="sxs-lookup"><span data-stu-id="30d51-111">Output : 'Element[]</span></span>

<span data-ttu-id="30d51-112">Toplam $a + b $.</span><span class="sxs-lookup"><span data-stu-id="30d51-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="30d51-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="30d51-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="30d51-114">' Öğesi</span><span class="sxs-lookup"><span data-stu-id="30d51-114">'Element</span></span>

<span data-ttu-id="30d51-115">İki giriş dizilerinin her birinde bulunan her öğenin türü.</span><span class="sxs-lookup"><span data-stu-id="30d51-115">The type of each element in each of the two input arrays.</span></span>