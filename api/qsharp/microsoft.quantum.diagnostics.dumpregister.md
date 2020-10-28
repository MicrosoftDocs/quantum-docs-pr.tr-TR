---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: a6d29dbf0525077fd804563f85f189740fdc0429
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727272"
---
# <a name="dumpregister-function"></a>DumpRegister işlevi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Leyebilir [](https://nuget.org/packages/)


Geçerli hedef makinenin belirtilen qubits ile ilişkili durumunun dökümünü yapar.

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="location--t"></a>Konum: 'T

Durumun dökümünün nerede oluşturulacağı hakkında bilgi sağlar.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Raporlanacak qubits listesi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

Yok.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen qubits durumuyla ilişkili bilgilerin bir dosya veya başka bir konumda dökümünü yapmanıza olanak sağlar.
Oluşturulan gerçek bilgiler ve semantiği `location` her bir hedef makineye özeldir. Ancak, konum () olarak boş bir tanımlama grubu sağlamak, `()` genellikle çıktıyı konsola oluşturma anlamına gelir.

Bu yöntem, hisse geliştirme seti 'nin bir parçası olarak dağıtılan yerel tam durum simülatörü için, söz konusu qubits 'in durumunu (karşılık gelen alt sistemin Wave işlevi), her bir öğenin karşılık gelen durumu ölçme olasılığının uyumlu olmasını temsil ettiği bir dosyanın yolunu içeren bir dize bekler.
Verilen qubits, başka bir qubitle ayrılarak ve durumları ayrılacaksa, yalnızca qubits 'in bir şekilde ayrılmış olduğunu bildirir.