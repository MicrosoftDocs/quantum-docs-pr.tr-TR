---
uid: Microsoft.Quantum.Math.PlusA
title: PlusA işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 14e9bfdbe4b70b4730e5bfc64a0ee81ab3cecaaf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842710"
---
# <a name="plusa-function"></a><span data-ttu-id="5f49d-102">PlusA işlevi</span><span class="sxs-lookup"><span data-stu-id="5f49d-102">PlusA function</span></span>

<span data-ttu-id="5f49d-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5f49d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5f49d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5f49d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5f49d-105">İki girişin toplamını (birleştirme) döndürür.</span><span class="sxs-lookup"><span data-stu-id="5f49d-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="5f49d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="5f49d-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="5f49d-107">a: ' element []</span><span class="sxs-lookup"><span data-stu-id="5f49d-107">a : 'Element[]</span></span>

<span data-ttu-id="5f49d-108">Toplanacak ilk giriş $a $.</span><span class="sxs-lookup"><span data-stu-id="5f49d-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="5f49d-109">b: ' öğe []</span><span class="sxs-lookup"><span data-stu-id="5f49d-109">b : 'Element[]</span></span>

<span data-ttu-id="5f49d-110">Toplanacak ikinci giriş $b $.</span><span class="sxs-lookup"><span data-stu-id="5f49d-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="5f49d-111">Output: ' element []</span><span class="sxs-lookup"><span data-stu-id="5f49d-111">Output : 'Element[]</span></span>

<span data-ttu-id="5f49d-112">Toplam $a + b $.</span><span class="sxs-lookup"><span data-stu-id="5f49d-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5f49d-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="5f49d-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="5f49d-114">' Öğesi</span><span class="sxs-lookup"><span data-stu-id="5f49d-114">'Element</span></span>

<span data-ttu-id="5f49d-115">İki giriş dizilerinin her birinde bulunan her öğenin türü.</span><span class="sxs-lookup"><span data-stu-id="5f49d-115">The type of each element in each of the two input arrays.</span></span>