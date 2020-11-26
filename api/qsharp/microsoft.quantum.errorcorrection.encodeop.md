---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: EncodeOp Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: 18d6df6037b1fe66a171acea1936fcb9ba1b27e5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200909"
---
# <a name="encodeop-user-defined-type"></a><span data-ttu-id="18a13-102">EncodeOp Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="18a13-102">EncodeOp user defined type</span></span>

<span data-ttu-id="18a13-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="18a13-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="18a13-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="18a13-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="18a13-105">Bir fiziksel kaydı, sunulan karalama qubits 'i kullanarak mantıksal bir kayda kodlayan bir işlemi temsil eder.</span><span class="sxs-lookup"><span data-stu-id="18a13-105">Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.</span></span>

<span data-ttu-id="18a13-106">İlk bağımsız değişken, kodlanacak fiziksel kayıt olarak alınır ve ikinci bağımsız değişken kullanılacak olan karalama kaydı olarak alınır.</span><span class="sxs-lookup"><span data-stu-id="18a13-106">The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.</span></span>

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```

