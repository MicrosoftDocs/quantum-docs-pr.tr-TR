---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: _ExtractLogicalQubitFromSteaneCode işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: 273692efa629cb8cc20069ef500c4e0902fbc3ff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201351"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a>_ExtractLogicalQubitFromSteaneCode işlemi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Syndrome ölçümü ve ekleme 'nin tersi.

$X $-ve $Z $-sabitleyiciler, kodlama devresinin belirli bir seçimi nedeniyle eşit olarak değerlendirilmez.
Bu asymmetry, farklı bir sendromu ayıklama yordamına yol açar.
Bir diğeri doğrudan kod durumunda Multi-qubitpauli işlecini ölçerek sendromu 'yi ölçebilir, ancak bu amaç için mantıksal qubit tek bir qubit 'e döndürülür, bu da daha fazla beğenilmesi gerekmeden sendromu ölçümlerinin yapılabileceği bir şekilde.

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a>Giriş

### <a name="code--logicalregister"></a>kod: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)





## <a name="output--qubitintint"></a>Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))

$X $-Syndrome ve $Z $-Syndrome için mantıksal qubit ve tamsayı çifti.
Tek bir $X $-veya $Z $-hatanın ölçülen Syndrome neden olacağı bir kod qubit dizinini temsil ederler.

## <a name="remarks"></a>Açıklamalar

`internal`Birim testleri doğrudan bu işleme bağlı olduğundan, bu işlemin olarak işaretlenmediğini unutmayın. Gelecekteki bir geliştirme olarak, birim testlerinin yalnızca genel olarak yalnızca ortak callaba 'ya göre yeniden düzenlenmiş olması gerekir.

> [!WARNING]
> Bu yordam, Steane 'nin 7 qubit kodu için belirli bir kodlama devresine göre tasarlanmıştır; kodlama devresi değiştirilirse, sendromu sonucunun farklı şekilde yorumlanması gerekebilir.