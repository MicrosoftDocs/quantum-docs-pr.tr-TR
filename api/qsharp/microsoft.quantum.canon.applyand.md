---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: Applyve işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 39ffb9c598b6345c0d63c0c0d9705d84e101cc47
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845183"
---
# <a name="applyand-operation"></a>Applyve işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Yalnızca her iki denetim qubit de 1 durumundaysa, adjoint işlemini gerçekleştirmek için ölçüm kullanarak, belirli bir hedef qubit 'i tersine çevirir.

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

`target`Ve yalnızca her iki denetim 1 ise, ancak 0 durumunda olduğunu varsaymaktadır `target` .  İşlem T-Count 4, T-Depth 2 ' dir ve yardımcı qubit gerektirmez ve bu nedenle, 0 olarak bilindiğinde CCNOT işlemi tercih edilebilir `target` .  Bu işlemin adekçi, ölçüm tabanlıdır ve T kapısı gerektirmez.

Bu işlemin denetlenen uygulaması, hiçbir yardımcı qubit, kapı gerektirmez `2^c` `Rz` ve bu işlem için en iyi duruma getirilmemiştir; burada `c` işlemin iki denetimi de dahil olmak üzere genel denetim qugeler sayısıdır `ApplyAnd` .  Adjoint kontrollü uygulama, `2^c - 1` `Rz` kapıları (adjoint olmayan işlemin boyutunun iki katı kadar bir açıda), yardımcı qubit olmadan ve derinlemesine en iyi duruma getirilmemelidir.

## <a name="input"></a>Giriş

### <a name="control1--qubit"></a>Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

İlk denetim qubit


### <a name="control2--qubit"></a>Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

İkinci denetim qubit


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Hedef yardımcı qubit; 0 durumunda olmalıdır



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Başvurular

- Cody Jones: "hata toleranslı Toffoli kapısı için önemli kurulumlarını", fiziksel. Rev. A 87, 022328, 2013 [Arxıv: 1212.5069](https://arxiv.org/abs/1212.5069) DOI: 10.1103/PhysRevA. 87.022328
- Craig Gidney: "hisse alma maliyetini durdurma", hisse 2, sayfa 74, 2018 [Arxıv: 1709.06648](https://arxiv.org/abs/1709.06648) DOI: 10.1103/PhysRevA. 85.044302
- Mathias Soeken: "hisse senedi Oracle devreleri ve Noel ağacı", [Blog makalesi 19 aralık 2019](https://msoeken.github.io/blog_qac.html) (Note: birden çok kontrollü oluşturma açıklanır)