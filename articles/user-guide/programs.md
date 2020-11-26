---
title: Soru-cevap
description: 'Soru-cevap programlarına hızlı giriş #'
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234320"
---
# <a name="q-quantum-programming-language"></a>Q # hisse programlama dili

Q # programlama dili hakkında bilmeniz gereken her şey, [q # dil kılavuzunda](xref:microsoft.quantum.qsharp.index)ayrıntılı olarak açıklanmıştır. Diğer her şey gibi, [dil tasarım sürecimiz](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) açık kaynak ve hoş geldiniz katkılarımız olur.
Q # ' dan sonra kuruluş ve mosyon hakkında daha fazla arka plan için bkz. [neden soru-cevap veriyoruz?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).  
S # hızlı bir genel bakış Için hisse geliştirme setinin (QDK) bir parçası olarak gönderilir, [QDK nedir?](xref:microsoft.quantum.overview.q-sharp)konusuna bakın. 

## <a name="what-is-a-quantum-program"></a>Hisse bir program nedir?

Bir hisse bir program, çağrıldığında bir hisse sistemi ile etkileşimde bulunarak bir hesaplama gerçekleştirirken, belirli bir klasik alt yordamlar kümesi olarak görülebilir; Q # dilinde yazılmış bir program hisse durumunu doğrudan modellemez, bunun yerine bir klasik denetim bilgisayarının qubits ile nasıl etkileşime gireceğini açıklar.
Bu, makineye bağlı farklı yorumlamalar olabilecek her bir hedef makinede bile her bir hisse alım durumunun büyük bir yerde *olduğu* konusunda tamamen belirsiz bir durumdur. 

Bunun önemli bir sonucu olarak, Q # ' ın bir qubit ya da başka bir hisse ve diğer özellikleri için introspect, bir Q # programının fiziksel bir bilgisayar üzerinde fiziksel olarak yürütülüp yürütülmemesini güvence altına alma yeteneği yoktur.
Bunun yerine, bir program, [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) bir qubit 'den klasik bilgileri ayıklamak gibi işlemleri çağırabilir.

Ayrıldıktan sonra, *callables* olarak da adlandırılan işlemlere ve işlevlere qubit iletilebilir. Bazı anlamda, bir Q # programının bir qubit ile yapamalarıdır. Bir qubit durumu üzerinde herhangi bir doğrudan eylem, ve gibi *iç* callables tarafından tanımlanır, [`X`](xref:Microsoft.Quantum.Intrinsic.X) [`H`](xref:Microsoft.Quantum.Intrinsic.H) ancak uygulamaları Q # içinde tanımlanmamıştır ancak hedef makine tarafından tanımlanır. Bu *işlemlerin gerçekten ne* olduğunu yalnızca belirli bir Q # programını çalıştırmak için kullandığımız hedef makine tarafından somut hale getirilir.

Örneğin, programı [tam durum benzeticimizde](xref:microsoft.quantum.machines.full-state-simulator)çalıştırırsanız simülatör, sanal hisse sisteme karşılık gelen matematiksel işlemleri gerçekleştirir.
Ancak geleceğe bakıyorum, hedef makine gerçek bir hisse bilgisayar olduğunda, Q # ' da bu gibi işlemleri çağırmak, hisse bilgisayarını *Gerçek* hisse sisteminde ilgili *gerçek* işlemleri gerçekleştirmeye yönlendirir (örneğin, tam olarak süreli lazer pulu).

Bir Q # programı, Express hisse hesaplamasına yeni ve daha üst düzey işlemler oluşturmak için bu işlemleri bir hedef makine tarafından tanımlanan şekilde yeniden birleştirir.
Bu şekilde, Q #, temel alınan hisse ve hibrit, klasik algoritmaların yanı sıra bir hedef makine ya da simülatör yapısına göre genel de olacak şekilde ifade yapmayı kolaylaştırır.

Basit bir örnek aşağıdaki programdır ve $ \ket $ durumunda bir qubit ayırır {0} , ardından buna bir Hadamard işlemi uygular `H` ve sonucu `PauliZ` temelde ölçer.

```qsharp
@EntryPoint()
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

[Hisse kamız](https://github.com/microsoft/QuantumKatas#introduction) , genel hisse alma işlemleri ve qubits 'in nasıl kullanılacağı gibi [hisse bilgi işlem kavramları](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) hakkında iyi bir giriş sağlar. Ayrıca, [Iç işlemlerde ve işlevlerde](xref:microsoft.quantum.libraries.standard.prelude)daha fazla örnek bulunabilir.



