---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 17211c1ae1fe12fcadf34a9411f9b0cf0cdcab50
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730402"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="25f91-102">ColumnAtUnchecked işlevi</span><span class="sxs-lookup"><span data-stu-id="25f91-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="25f91-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="25f91-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="25f91-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25f91-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25f91-105">Bu işlev, matris şeklini denetlemez</span><span class="sxs-lookup"><span data-stu-id="25f91-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="25f91-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="25f91-106">Description</span></span>

<span data-ttu-id="25f91-107">Bu işlev, geçerli bir dikdörtgen şeklinin giriş matrisini zaten kontrol eden diğer çok boyutlu işlevlerde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="25f91-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="25f91-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="25f91-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="25f91-109">sütun: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="25f91-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="25f91-110">Matris: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="25f91-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="25f91-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="25f91-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="25f91-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="25f91-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="25f91-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="25f91-113">'T</span></span>

