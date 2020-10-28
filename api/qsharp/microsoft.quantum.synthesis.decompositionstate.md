---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: Dekompozisyontionstate Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: 0547c04828a80b4f696cc17e13c8cc57d0379f96
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733911"
---
# <a name="decompositionstate-user-defined-type"></a>Dekompozisyontionstate Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Leyebilir [](https://nuget.org/packages/)


Değişken dizinleri temel alarak ayrıştırma sırasında durum

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="perm--int"></a>İzin: [Int](xref:microsoft.quantum.lang-ref.int)[]


### <a name="lfunctions--bigintint"></a>Lfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int)) []


### <a name="rfunctions--bigintint"></a>Rfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int)) []



## <a name="description"></a>Açıklama

Durum, sol taraftaki kontrol edilen kapıların ve sağ taraftaki denetimli kapıların geçerli permütasyon ve şu anda oluşturulmuş işlevlerini barındırır.