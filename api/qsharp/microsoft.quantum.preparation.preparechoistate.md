---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: Hazırlık yankı işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: cb34078c09f8c28b5b9bbda1bae6936d13ffcc78
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854394"
---
# <a name="preparechoistate-operation"></a>Hazırlık yankı işlemi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Belirli bir işlem için CHOI – Jamiołkowski durumunu verilen başvuru ve hedef Yazmaçları üzerine hazırlar.

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="op--qubit--unit"></a>Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) 

Choi – Jamiołkowski State $J (\Lambda)/2 ^ N $ olan Operation $ \Lambda $ hazırlanmaktadır; burada $N $, üzerinde işlem gören qubits sayısıdır `op` .


### <a name="reference--qubit"></a>Başvuru: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$ \Ket{00\cnoktalar 0} $ durumunda, öğesinin eylemi için bir başvuru olarak kullanılacak bir qubits kaydı `op` .


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Başlangıçta $ \ket{00\cnoktalar 0} $ durumunda olacak şekilde bir qubıts kaydı `op` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Bir hisse işleminin CHOI – Jamiłkowski State $J (\Lambda) $ $ $ \begin{hizalaması} J (\Lambda) \mathrel{: =} (\cıvaal\otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langta\cıvadone |), \end{hizalaması} $ $ burada $ | olarak tanımlanmıştır. X\rangle \! \rangle $, bir matrisin $X $ 'ın, sütun yığınlama kuralına *vektörleştirmesi* . Bu durumun klasik bir açıklamasını öğrenmek, $ \Lambda $ ' ın rastgele giriş durumlarına göre hareket etmesinin yanı sıra *hisse işleme* temelini oluşturur.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. hazırlık. hazırlık yankı Istatea](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [Microsoft. hisse. hazırlık. hazırlık yankı Istatec](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [Microsoft. hisse. hazırlık. hazırlık yankı Istateca](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)