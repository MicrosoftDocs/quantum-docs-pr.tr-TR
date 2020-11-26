---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: e7eb2dfce060b61e27deae31e3c1fc6dc3d7655c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202116"
---
# <a name="dumpmachine-function"></a>DumpMachine işlevi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Geçerli hedef makinenin durumunu döker.

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a>Giriş

### <a name="location--t"></a>Konum: 'T

Makinenin dökümünü oluşturma hakkında bilgi sağlar.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

Yok.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="remarks"></a>Açıklamalar

Bu yöntem, hedef makinenin geçerli durumu hakkındaki bilgilerin bir dosyaya veya başka bir konuma dökümünü sağlar.
Oluşturulan gerçek bilgiler ve semantiği `location` her bir hedef makineye özeldir. Ancak, bir konum () olarak boş bir tanımlama grubu sağlamak `()` ya da yalnızca `location` parametresi atlanırsa, genellikle çıktıyı konsola oluşturma anlamına gelir.

Bu yöntem, hisse geliştirme seti 'nin bir parçası olarak dağıtılan yerel tam durum simülatörü için, her bir öğenin karşılık gelen durumu ölçme olasılığının uyumlu olduğunu gösterdiği bir dosyanın yolunu içeren bir dosyanın yolunu içeren bir dize bekler.