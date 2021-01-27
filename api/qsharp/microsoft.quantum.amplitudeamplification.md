---
uid: Microsoft.Quantum.AmplitudeAmplification
title: Microsoft. hisse. yükseltilmiş Tudeamplifi ad alanı
ms.date: 1/23/2021 12:00:00 AM
ms.topic: managed-reference
qsharp.kind: namespace
qsharp.name: Microsoft.Quantum.AmplitudeAmplification
qsharp.summary: This namespace contains functions and operations for performing amplitude amplification.
ms.openlocfilehash: a014f923de62c5e660c1c0fc839fbe60e80f8ba9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845840"
---
# <a name="microsoftquantumamplitudeamplification-namespace"></a>Microsoft. hisse. yükseltilmiş Tudeamplifi ad alanı

Bu ad alanı, genliğini gerçekleştirmeye yönelik işlevler ve işlemler içerir.



## <a name="description"></a>Description

Kısmi yansıtımları ile yükümlülüğü uygulayan, burada uygulanan en genel genme biçimidir.

Bu işlem AmpAmpObliviousByReflectionPhases aracılığıyla çağrılır.

Bu iki kayıt içerir: `ancillaRegister` ve `systemRegister` .

Bu `ReflectionOracle` , yalnızca yazmaç üzerinde işlem gören bu tür yansımaları için iki Oracles kabul eder `ancillaRegister` .

Bu, `ObliviousOracle` her iki kasada de birlikte çalışan bir Oracle özel için, türü bir Oracle özel bakış düzeyini kabul eder.

Giriş durumunun, `ancillaRegister` ilk yansıma işlecinin benzersiz $-$1 eigenstate olduğu varsayılır $I-2 \ ayraç {s} \ köşeli {s} $.

Bir hedef hisse cıya ilişkin yansıtıcılıkları genellikle bu durumu hesaplama tabanlı $ \ket{0\cnoktalar 0} $ ' dan hazırlayan bir Oracle erişimi varsayıldığında uygulanır.

Bu Oracles için kuralımız iki kayıt gerektirir: tek bir-qubit `flagQubit` kayıt ve Anyalakaydet kaydındaki diğer her şey için bir kayıt.

Oracle türü, `StateOracle` {1} `flagQubit` bazı gerçek genlerle kasada $ \ket $ tarafından işaretlenen hedef durumu oluşturmak için her iki kasada de birlikte yürütülür.

`ReflectionOracle`Bu bayrak durumuyla ilgili yansıma, işlem tarafından oluşturulur `TargetStateReflectionOracle` .

`ReflectionOracle`Giriş durumu hakkındaki yansıma, `ancillaRegister` stateoracle 'ı ters çeviren ve daha sonra reflectionstart () ile birlikte $ \ket{0\cnoktalar 0} $ hakkında yansıtılırken oluşturulur.

Oracle türü, `DeterministicStateOracle` `qubitState` hedef durumu yalnızca bayrak olmadan oluşturmak için kayıt defterlerine davranır.

`AmpAmpObliviousByOraclePhases` , Oracles `StateOracle` ve yansıtımları yerine kabul eden bir zorunluluvou genliği yükseltme sürümüdür `ObliviousOracle` .

Genüzliği, `ObliviousOracle` Identity operatörü olan ve hiçbir sistem qubit (boş) olmayan, yükümlülüğü uygulayan özel bir durum olduğunu unutmayın `systemRegister` .

Bu işlem ve işlemi aracılığıyla çağrılır `AmpAmByReflectionPhases` `AmpAmpByOraclePhases` .

Grover aramasının standart durumunda kısmi yansıtılılıkları için aşamalar, AmpAmpPhasesStandard işlevi tarafından sağlanır.

Örneğin, şu bağımlılıklara sahipsiniz: AmpAmpByOracle-> Ampampbyoracliaşamalar-> AmpAmpObliviousByOraclePhases-> AmpAmpObliviousByReflectionPhases.