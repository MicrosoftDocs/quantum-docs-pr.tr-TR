---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: Hazırlık Esingliqubitişdentity işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 12a650568aa5682e8fb6498808d188b154527acb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733722"
---
# <a name="preparesinglequbitidentity-operation"></a>Hazırlık Esingliqubitişdentity işlemi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Leyebilir [](https://nuget.org/packages/)


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