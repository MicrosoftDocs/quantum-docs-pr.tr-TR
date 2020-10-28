---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: RequiresCapability Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 63b1952d402f1bcb81a8f9d0afc3cdf7aa7e5ed8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733866"
---
# <a name="requirescapability-user-defined-type"></a>RequiresCapability Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. hedefleme](xref:Microsoft.Quantum.Targeting)

Leyebilir [](https://nuget.org/packages/)


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