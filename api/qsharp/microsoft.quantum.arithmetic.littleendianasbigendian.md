---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: c89288e1eb421fd5abd8fcd5d9c12049aa47ac89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843085"
---
# <a name="littleendianasbigendian-function"></a><span data-ttu-id="980dc-102">LittleEndianAsBigEndian işlevi</span><span class="sxs-lookup"><span data-stu-id="980dc-102">LittleEndianAsBigEndian function</span></span>

<span data-ttu-id="980dc-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="980dc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="980dc-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="980dc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="980dc-105">Qubit `LittleEndian` sıralamasını tersine çevirerek qubit kaydını bir `BigEndian` qubit kaydına dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="980dc-105">Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function LittleEndianAsBigEndian (input : Microsoft.Quantum.Arithmetic.LittleEndian) : Microsoft.Quantum.Arithmetic.BigEndian
```


## <a name="input"></a><span data-ttu-id="980dc-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="980dc-106">Input</span></span>

### <a name="input--littleendian"></a><span data-ttu-id="980dc-107">Giriş: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="980dc-107">input : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="980dc-108">Qubit kayıt `LittleEndian` biçiminde.</span><span class="sxs-lookup"><span data-stu-id="980dc-108">Qubit register in `LittleEndian` format.</span></span>



## <a name="output--bigendian"></a><span data-ttu-id="980dc-109">Çıkış: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="980dc-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="980dc-110">Qubit kayıt `BigEndian` biçiminde.</span><span class="sxs-lookup"><span data-stu-id="980dc-110">Qubit register in `BigEndian` format.</span></span>