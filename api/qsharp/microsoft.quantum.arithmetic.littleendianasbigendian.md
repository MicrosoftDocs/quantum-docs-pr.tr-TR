---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 8c2e6150a839bb0cd4c311c821b78a080288cd22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731450"
---
# <a name="littleendianasbigendian-function"></a><span data-ttu-id="dcf1c-102">LittleEndianAsBigEndian işlevi</span><span class="sxs-lookup"><span data-stu-id="dcf1c-102">LittleEndianAsBigEndian function</span></span>

<span data-ttu-id="dcf1c-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="dcf1c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="dcf1c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dcf1c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dcf1c-105">Qubit `LittleEndian` sıralamasını tersine çevirerek qubit kaydını bir `BigEndian` qubit kaydına dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="dcf1c-105">Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function LittleEndianAsBigEndian (input : Microsoft.Quantum.Arithmetic.LittleEndian) : Microsoft.Quantum.Arithmetic.BigEndian
```


## <a name="input"></a><span data-ttu-id="dcf1c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="dcf1c-106">Input</span></span>

### <a name="input--littleendian"></a><span data-ttu-id="dcf1c-107">Giriş: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dcf1c-107">input : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="dcf1c-108">Qubit kayıt `LittleEndian` biçiminde.</span><span class="sxs-lookup"><span data-stu-id="dcf1c-108">Qubit register in `LittleEndian` format.</span></span>



## <a name="output--bigendian"></a><span data-ttu-id="dcf1c-109">Çıkış: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="dcf1c-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="dcf1c-110">Qubit kayıt `BigEndian` biçiminde.</span><span class="sxs-lookup"><span data-stu-id="dcf1c-110">Qubit register in `BigEndian` format.</span></span>