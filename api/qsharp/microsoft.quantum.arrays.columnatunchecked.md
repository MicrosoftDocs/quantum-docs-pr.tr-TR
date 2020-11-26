---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 06fce23bbf7142ee0e0b0ed3f2c0578676f2097b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221598"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="110c7-102">ColumnAtUnchecked işlevi</span><span class="sxs-lookup"><span data-stu-id="110c7-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="110c7-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="110c7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="110c7-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="110c7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="110c7-105">Bu işlev, matris şeklini denetlemez</span><span class="sxs-lookup"><span data-stu-id="110c7-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="110c7-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="110c7-106">Description</span></span>

<span data-ttu-id="110c7-107">Bu işlev, geçerli bir dikdörtgen şeklinin giriş matrisini zaten kontrol eden diğer çok boyutlu işlevlerde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="110c7-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="110c7-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="110c7-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="110c7-109">sütun: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="110c7-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="110c7-110">Matris: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="110c7-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="110c7-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="110c7-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="110c7-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="110c7-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="110c7-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="110c7-113">'T</span></span>

