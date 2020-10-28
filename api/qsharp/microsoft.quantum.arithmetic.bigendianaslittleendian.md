---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 65074b74bcc952efc8b2a9473b2a010bdda42990
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731658"
---
# <a name="bigendianaslittleendian-function"></a><span data-ttu-id="08be5-102">BigEndianAsLittleEndian işlevi</span><span class="sxs-lookup"><span data-stu-id="08be5-102">BigEndianAsLittleEndian function</span></span>

<span data-ttu-id="08be5-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="08be5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="08be5-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="08be5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="08be5-105">Qubit `BigEndian` sıralamasını tersine çevirerek qubit kaydını bir `LittleEndian` qubit kaydına dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="08be5-105">Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a><span data-ttu-id="08be5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="08be5-106">Input</span></span>

### <a name="input--bigendian"></a><span data-ttu-id="08be5-107">Giriş: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="08be5-107">input : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="08be5-108">Qubit kayıt `BigEndian` biçiminde.</span><span class="sxs-lookup"><span data-stu-id="08be5-108">Qubit register in `BigEndian` format.</span></span>



## <a name="output--littleendian"></a><span data-ttu-id="08be5-109">Çıkış: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="08be5-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="08be5-110">Qubit kayıt `LittleEndian` biçiminde.</span><span class="sxs-lookup"><span data-stu-id="08be5-110">Qubit register in `LittleEndian` format.</span></span>