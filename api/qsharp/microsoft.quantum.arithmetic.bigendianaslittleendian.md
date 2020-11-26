---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 5f5d7dc6e08a13fbdc45f9d11c93c29cfcf90bf8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223638"
---
# <a name="bigendianaslittleendian-function"></a><span data-ttu-id="ce4ac-102">BigEndianAsLittleEndian işlevi</span><span class="sxs-lookup"><span data-stu-id="ce4ac-102">BigEndianAsLittleEndian function</span></span>

<span data-ttu-id="ce4ac-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ce4ac-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ce4ac-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ce4ac-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ce4ac-105">Qubit `BigEndian` sıralamasını tersine çevirerek qubit kaydını bir `LittleEndian` qubit kaydına dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="ce4ac-105">Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a><span data-ttu-id="ce4ac-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ce4ac-106">Input</span></span>

### <a name="input--bigendian"></a><span data-ttu-id="ce4ac-107">Giriş: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="ce4ac-107">input : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="ce4ac-108">Qubit kayıt `BigEndian` biçiminde.</span><span class="sxs-lookup"><span data-stu-id="ce4ac-108">Qubit register in `BigEndian` format.</span></span>



## <a name="output--littleendian"></a><span data-ttu-id="ce4ac-109">Çıkış: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ce4ac-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ce4ac-110">Qubit kayıt `LittleEndian` biçiminde.</span><span class="sxs-lookup"><span data-stu-id="ce4ac-110">Qubit register in `LittleEndian` format.</span></span>