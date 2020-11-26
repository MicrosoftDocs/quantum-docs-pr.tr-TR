---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 3cdcd18f06bf43d109c9f5e69f319f9d33b96bfc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222754"
---
# <a name="littleendianasbigendian-function"></a><span data-ttu-id="1698a-102">LittleEndianAsBigEndian işlevi</span><span class="sxs-lookup"><span data-stu-id="1698a-102">LittleEndianAsBigEndian function</span></span>

<span data-ttu-id="1698a-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1698a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1698a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1698a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1698a-105">Qubit `LittleEndian` sıralamasını tersine çevirerek qubit kaydını bir `BigEndian` qubit kaydına dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="1698a-105">Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function LittleEndianAsBigEndian (input : Microsoft.Quantum.Arithmetic.LittleEndian) : Microsoft.Quantum.Arithmetic.BigEndian
```


## <a name="input"></a><span data-ttu-id="1698a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1698a-106">Input</span></span>

### <a name="input--littleendian"></a><span data-ttu-id="1698a-107">Giriş: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1698a-107">input : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1698a-108">Qubit kayıt `LittleEndian` biçiminde.</span><span class="sxs-lookup"><span data-stu-id="1698a-108">Qubit register in `LittleEndian` format.</span></span>



## <a name="output--bigendian"></a><span data-ttu-id="1698a-109">Çıkış: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="1698a-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="1698a-110">Qubit kayıt `BigEndian` biçiminde.</span><span class="sxs-lookup"><span data-stu-id="1698a-110">Qubit register in `BigEndian` format.</span></span>