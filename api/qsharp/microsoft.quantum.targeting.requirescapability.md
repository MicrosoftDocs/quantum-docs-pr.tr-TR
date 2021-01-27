---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: RequiresCapability Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 5e0db49d6f73398ac36003eb0f44e3a6520b7f1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855146"
---
# <a name="requirescapability-user-defined-type"></a>RequiresCapability Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. hedefleme](xref:Microsoft.Quantum.Targeting)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Derleyici tarafından tanınan öznitelik, gereken çalışma zamanı yetenekleri ile çağrılabilir olarak işaretlemek için kullanılır.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="level--string"></a>Düzey: [dize](xref:microsoft.quantum.lang-ref.string)

Çağrılabilir için gereken çalışma zamanı yetenek düzeyinin adı.
### <a name="reason--string"></a>Neden: [dize](xref:microsoft.quantum.lang-ref.string)

Çağrılabilir özelliğinin bu çalışma zamanı özelliğini neden gerektirdiğini bir açıklama.

## <a name="remarks"></a>Açıklamalar

Çağrılabilir üzerinde bu özniteliğin bir örneği zaten mevcut değilse, bu öznitelik derleyici tarafından otomatik olarak eklenir. Derleyicinin gerekli özelliği doğru bir şekilde çıkarmadığından nadir durumlar dışında kullanılmamalıdır.

Aşağıda, yetenek düzeyi adlarının, artırma özelliklerinin veya azalan kısıtlamaların sırası olarak listesi verilmiştir:

## `"BasicQuantumFunctionality"`

Ölçüm sonuçları eşitlik için karşılaştırılamaz.

## `"BasicMeasurementFeedback"`

Ölçüm sonuçları yalnızca işlemlerdeki IF deyimi koşullu ifadelerinde eşitlik için karşılaştırılabilir. Bir sonuca bağlı bir if-deyimi bloğu, blok dışında belirtilen kesilebilir değişkenler için set deyimleri içeremez ya da Return deyimleri olamaz.

## `"FullComputation"`

Çalışma zamanı kısıtlaması yok. Herhangi bir Q # programı yürütülebilir.