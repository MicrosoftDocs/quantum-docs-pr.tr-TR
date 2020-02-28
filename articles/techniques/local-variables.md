---
title: 'Yerel değişkenler-Q # teknikleri'
description: Soru-cevap özelliğini kullanarak yerel değişkenleri tanımlama ve bunlarla çalışma hakkında bilgi edinin.
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.local-variables
ms.openlocfilehash: cb6c662137c31a13c3dd6e9ca3f67879c469f788
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906874"
---
# <a name="local-variables"></a>Yerel değişkenler #

Q # içindeki herhangi bir türün değeri, `let` anahtar sözcüğü kullanılarak bir işlem veya işlev içinde yeniden kullanım için bir değişkene atanabilir.
Örneğin:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Bu, belirli bir Pauli işleçleri dizisini `measurementOperator`adlı bir değişkene atar.

> [!TIP]
> `let` deyiminin sağ tarafındaki ifade belirsiz olduğundan ve tür derleyicinin tarafından çıkarsandığı için yeni değişkenimizin türünü açık bir şekilde belirtmemiz gerekmediğini unutmayın. 

Q # içindeki değişkenler *sabittir*, yani bir değişken bu şekilde tanımlandığında, artık hiçbir şekilde değiştirilemez.
Bu, bir işlemin `Adjoint` türevini uygulamak için değişkenlerin yeniden düzenlenmesine yönelik klasik mantığın iyileştirilmesi dahil olmak üzere birkaç yarar iyileştirmesi sağlar.

Yukarıdaki `let` bağlama kullanılarak tanımlanan değişkenler, bir işlemin gövdesi veya bir `for` döngüsünün içeriği gibi belirli bir kapsamda yereldir.


## <a name="mutability"></a>Değişebilirliği ##

`let`ile bir değişken oluşturulmasına alternatif olarak, `mutable` anahtar sözcüğü, ilk kez `set` anahtar sözcüğü kullanılarak oluşturulduktan sonra yeniden bağlanabilen özel bir kesilebilir değişken oluşturur.

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

Tüm Q # türleri diziler de dahil olmak üzere değer semantiğini izler. Özellikle, dizi öğelerini güncelleştirmek mümkün değildir. Var olan bir diziyi değiştirmek için, içindeki F#kayıtlar için bir kopyalama ve güncelleştirme mekanizmasından çok daha fazla yararlanmak gerekir. [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays)sağlanan diziler için kitaplık araçlarını kullanarak, Dizin `i` 'nin verilen değeri aldığı ve diğer tüm girdilerin kimlik olduğu Paulis dizisini döndüren bir işlevi kolayca tanımlayabiliriz: 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

Q # deyimlerini ve ifadelerini ele alırken dizilerle nasıl çalışacağız hakkında daha fazla bilgi göndereceğiz. 

Q # içindeki değiştirici, bir tür veya değer yerine bir *sembol* için geçerli olan bir kavramdır. Özellikle, tür sisteminde bir gösterimi yoktur, örtük olarak veya açıkça ve bir bağlamanın değişebilir (`mutable` anahtar sözcüğüyle gösterildiği gibi) veya sabit (`let`tarafından belirtildiği gibi), bağlama değişkenlerinin türünü değiştirmez. Bu, özelleştirilmiş işlevler ve işlemler içindeki değiştirici yalıtmak için önemli bir yol sağlar.
Özellikle, kesilebilir değişken kullanan bir işlem için adjoint özelleştirmesi otomatik olarak üretilemez olsa da, otomatik oluşturma, değiştirici kullanan bir işlev çağıran bir işlem için sorunsuz çalışır.
Bu nedenle, daha kısa ve sıkıştır kullanan işlevleri ve işlemleri mümkün olduğunca kısa ve küçük bir hale getirmek iyi bir uygulamadır, böylece hisse programının kalanı sıradan sabit değişkenler kullanılarak yazılabilir.


## <a name="deconstruction"></a>Ayrıştırma ##

Tek bir değişken atamaya ek olarak, `let` ve `mutable` anahtar sözcükleri; diğer tüm bağlama yapısıyla aynı zamanda bir [demet türünün](xref:microsoft.quantum.language.type-model#tuple-types)içeriğinin açılmasını sağlar.
Bu formun bir ataması, bu kayıt düzeninin öğelerini *parçalara ayırmayı* kabul edilir.
Örneğin, bir Hamiltonian içindeki bir terimi bir tanımlama grubu tarafından modelliyoruz, bu terimin altında benzetim yapmanız gereken farklı verilere erişmek için oluşturmayı kullanabiliriz:

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


