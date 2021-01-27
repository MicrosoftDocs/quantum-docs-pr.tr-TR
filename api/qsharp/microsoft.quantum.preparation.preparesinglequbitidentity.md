---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: Hazırlık Esingliqubitişdentity işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: c6c9b5724354d6ee034dd8b6733901ebdd8072d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856864"
---
# <a name="preparesinglequbitidentity-operation"></a>Hazırlık Esingliqubitişdentity işlemi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Yüksek ölçüde karışık durumda bir qubit hazırlar.

$/Boldo/$2 durumunda verilen qubit $ $ \begin{hizalaması} \Omega (\rho) \mathrel{: =} \frac {1} {4} \ sum_ {\mu \{ \0 ' ı uygulayarak verilen qubit 'i hazırlar 1, 2, 3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\leger}, \end{hizalaması} $ $; $ \sigma \_ i $, $i $ TH Pauli işleci, ve $ \rho $, karışık bir durumu temsil eden bir yoğunluk operatöründür.

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a>Giriş

### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Durumu yukarıda açıklanan şekilde depolarized bir qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Bu işlemi bir duruma uygulamanın sonucunu açıklayan karışık durum $ \ cıvadone/$2, bu işlemde yapılan rastgele seçimler üzerinde bir beklentideğeri örtülü olarak tanımlar.
Bu nedenle, tek bir uygulama için, bu işlem saf durumları saf durumlara eşler, ancak beklentide anlatıldığı gibi davranır.
Özellikle, bu işlem, bir kanalın olmayan bileşenlerini ölçmek için işlem *turuntografda* kullanılabilir.