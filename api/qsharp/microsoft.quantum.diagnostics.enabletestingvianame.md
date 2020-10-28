---
uid: Microsoft.Quantum.Diagnostics.EnableTestingViaName
title: EnableTestingViaName Kullanıcı tanımlı tür
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EnableTestingViaName
qsharp.summary: Compiler-recognized attribute via which an alternative name can be defined that may be used when loading a type or callable for testing purposes.
ms.openlocfilehash: ee4f32a5af4243ad85994c2edd006737a5131931
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727277"
---
# <a name="enabletestingvianame-user-defined-type"></a><span data-ttu-id="62d5c-102">EnableTestingViaName Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="62d5c-102">EnableTestingViaName user defined type</span></span>

<span data-ttu-id="62d5c-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="62d5c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="62d5c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="62d5c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="62d5c-105">Bir tür yüklenirken veya test amaçlı olarak çağrılabilir şekilde kullanılabilecek alternatif bir adın tanımlanabilmesi için, derleyici tarafından tanınan öznitelik.</span><span class="sxs-lookup"><span data-stu-id="62d5c-105">Compiler-recognized attribute via which an alternative name can be defined that may be used when loading a type or callable for testing purposes.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype EnableTestingViaName = (String);
```

