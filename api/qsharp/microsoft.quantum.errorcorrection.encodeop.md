---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: EncodeOp Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: c9959f1afbd44df974c06b79f73eccd090b17985
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826186"
---
# <a name="encodeop-user-defined-type"></a><span data-ttu-id="b30bf-102">EncodeOp Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="b30bf-102">EncodeOp user defined type</span></span>

<span data-ttu-id="b30bf-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="b30bf-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="b30bf-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b30bf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b30bf-105">Bir fiziksel kaydı, sunulan karalama qubits 'i kullanarak mantıksal bir kayda kodlayan bir işlemi temsil eder.</span><span class="sxs-lookup"><span data-stu-id="b30bf-105">Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.</span></span>

<span data-ttu-id="b30bf-106">İlk bağımsız değişken, kodlanacak fiziksel kayıt olarak alınır ve ikinci bağımsız değişken kullanılacak olan karalama kaydı olarak alınır.</span><span class="sxs-lookup"><span data-stu-id="b30bf-106">The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.</span></span>

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```

