---
title: Q# teknikleri - Hepsini bir araya getirmek
description: 'Kuantum ışınlama gösteren temel bir Q # programı ile yürüyün.'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030574"
---
# <a name="putting-it-all-together-teleportation"></a>Hepsini Bir Araya Getirmek: Işınlama #
[Kuantum Devreleri'nde](xref:microsoft.quantum.concepts.circuits)tanımlanan ışınlama devresi örneğine dönelim. Bunu şimdiye kadar öğrendiğimiz kavramları göstermek için kullanacağız. Kuantum ışınlanmasının açıklaması, teoriye aşina olmayanlar için aşağıda ve ardından Q#'daki kod uygulamasının bir gözden geçirilmesi sağlanmıştır. 

## <a name="quantum-teleportation-theory"></a>Kuantum Işınlama: Teori
Kuantum ışınlama bilinmeyen bir kuantum durumu göndermek için bir tekniktir (biz bir yerde bir qubit olarak bakın __'mesaj__') başka bir yerde bir qubit (biz bu qubits için '__burada__' ve '__orada__'sırasıyla) olarak bakın. __Mesajımızı__ Dirac gösterimini kullanarak bir vektör olarak temsil edebiliriz: 

$$ \ket{\psi} = \alfa\ket{0} +{1} \beta\ket $$

Biz __message__ $\alpha$ ve $\beta$ değerlerini bilmediğimiz için qubit'in durumu bizim için bilinmemektedir.

### <a name="step-1-create-an-entangled-state"></a>Adım 1: Karışık bir durum oluşturma
Burada __qubit__ orada __qubit__ile dolaşmış olması için gereken __mesajı__ göndermek için . Bu bir Hadamard kapısı uygulanarak elde edilir, ardından bir CNOT kapısı. Bu geçit işlemlerinin arkasındaki matematiğe bakalım.

Biz __burada__ qubits ile başlayacak ve __orada__ hem{0}$\ket $ devlet. Bu qubits dolaşmış sonra, onlar devlet vardır:

$$ \ket{\phi^+} ={1}\frac{2}{\sqrt{00} }(\ket + \ket{11}) $$

### <a name="step-2-send-the-message"></a>Adım 2: İletiyi gönderme
__Mesajı__ göndermek için önce __qubit iletisi__ ile bir CNOT kapısı ve __burada__ giriş olarak qubit __(mesaj__ qubit kontrol olmak ve __burada__ qubit hedef qubit olmak, bu durumda) uygulayın. Bu giriş durumu yazılabilir:

{0} $$ \ket{\psi}\ket{\phi^+} = (\alfa\ket +{1}\beta\ket{1})(\frac {\sqrt{2}}(\ket{00} + \ket{11})) $$

Bu genişletir:

$$ \ket\\psi}\ket{\phi^+}{2}= \frac{\alpha}\\sqrt{000} }\ket }\ket \{2}\frac\\ket}\ket}\ket }\ket + \frac{\beta}\ket{011} {2}{100} \ \\sqrt}\ket\ \sqrt }\sqrt }\sqrt }\sqrt }\\ket}\sqrt{2}{111} }\ket\\ket}\ket}\ket}\ket}\ket}\ket}\ket}\ket}\ket}\ket\ket}\\ket$$$\sqrt

Bir hatırlatma olarak, CNOT kapısı, kontrol qubit1 olduğunda hedef qubit çevirir. Örneğin, $\ket{000}$ girişi ilk qubit (denetim) 0 olduğundan hiçbir değişiklikle sonuçlanmaz. Ancak, ilk qubit 1 olduğu bir durumda almak - örneğin{100}$\ket $ bir giriş. Bu durumda, ikinci qubit{110}(hedef) CNOT kapısı tarafından döndürülür gibi çıktı $\ket $ olduğunu.

CNOT kapısı yukarıdaki girdimize göre hareket ettikten sonra çıktımızı şimdi düşünelim. Sonuç şudur:

$${2}\frac{\alpha}\\sqrt{000} }\ket \ \frac{\alpha}\\sqrt{2}}\ket }\ket{011} \ \frac{\beta}\sqrt}\ket{2}{110} +{2}\ket{101} }\ket}\ket $$

__İleti__ göndermek için bir sonraki adım __mesaj__ qubit (her terimin ilk qubit) bir Hadamard kapısı uygulamaktır. 

Bir hatırlatma olarak, Hadamard kapısı aşağıdakileri yapar:

Girdi | Çıktı
---------------------------| ---------------------------------------------------------------
$\ket{0}$  | $\frac{1}{\sqrt{2}}(\ket{0} {1}+ \ket )$
$\ket{1}$  | $\frac{1}{\sqrt{2}}(\ket{0} {1}- \ket )$

Yukarıdaki çıktımızın her döneminin ilk qubitine Hadamard kapısını uygularsak, aşağıdaki sonucu elde etmiş oluruz:

$${2}\frac{\alpha}{\sqrt }(\frac{1}{\sqrt{2}{0} }(\ket } (\ket + \ket{1}))\ket{2}{1}{2}{0} {1}{11} {2}{1}{2}{0} {1}{10} {2}{1}{2}{0} {00} + \frac{\alpha}\\sqrt }(\frac {\sqrt }(\ket + \ket ))\ket + \frac{\beta}\\sqrt }(\frac {\sqrt }(\ket - \ket)\ket ){1}\ket)\ket + \frac{\beta}\\sqrt }(\frac {\sqrt }(\ket - \ket ))ket{01} $$

Her terimin iki $\frac{1}{\sqrt{2}}$ faktörü olduğunu unutmayın. Aşağıdaki sonucu vererek bunları çoğaltabiliriz:

$${2}\frac{\alpha}{0} (\ket{1}+ \ket )\ket{00} +{2}\frac{\alfa}{0} (\ket + \ket{2}\ket{0} {1}{10} {2}{0} {1}{11} )\ket ) \frac{\beta} (\ket -{1}\ket\beta} (\ket\ket )\ket{01} $$

$\frac{1}{2}$ faktörü her dönem için yaygındır, bu yüzden artık parantez dışında alabilir:

{1}{2}$$ \frac{0} \big[\alpha(\ket{1}+ \ket{00} )\ket{0} + \ket{1})\ket{11} + \ket ) \ket + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket - \ket{1})\ket )\ket{01}\big] $$

Daha sonra veren her dönem için parantez leri çoğaltabiliriz:

{1}{2}$$ \frac{000} \big[\alpha\ket +{100} \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} -{110} \beta\ket{001} + \beta\ket + \beta\ket \ \beta\ket - \beta\ket{101}\big] $$

### <a name="step-3-measure-the-result"></a>Adım 3: Sonucu ölçün

__Burada__ ve __orada__ dolaşmış olması nedeniyle, __burada__ herhangi bir ölçüm __orada__durumunu etkileyecektir. Birinci ve ikinci qubiti __(mesaj__ ve __burada)__ ölçersek, bu dolaşıklık özelliğinden dolayı hangi durumda __olduğunu__ öğrenebiliriz. 

* Eğer 00'ı ölçer ve sonuç alırsak, süperpozisyon çöker ve sadece bu sonuca uygun şartlar bırakır. Bu $\alpha\ket{000} +\beta\ket{001}$. Bu $\ket{00}(\alfa\ket{0} +\beta\ket{1})$' olarak yeniden kullanılabilir. Bu nedenle birinci ve ikinci qubit'i 00 olarak ölçersek, __there__üçüncü qubitin $(\alpha\ket{0} +\beta\ket{1})$.
* 01'i ölçer ve elde edersek, süperpozisyon çöker ve yalnızca bu sonuca uygun şartlar bırakır. Bu $\alpha\ket{011} +\beta\ket{010}$. Bu $\ket{01}(\alfa\ket{1} +\beta\ket{0})$' olarak yeniden kullanılabilir. Bu nedenle birinci ve ikinci qubit'i 01 olarak ölçersek, __there__üçüncü qubitin $(\alpha\ket{1} +\beta\ket{0})$.
* Eğer 10'u ölçer ve elde edersek, süperpozisyon çöker ve yalnızca bu sonuca uygun şartlar bırakır. Bu $\alfa\ket{100} -\beta\ket{101}$. Bu $\ket{10}(\alfa\ket{0} -\beta\ket{1})$' olarak yeniden kullanılabilir. Bu nedenle birinci ve ikinci qubit'i 10 olarak ölçersek, __there__üçüncü qubitin $(\alpha\ket{0} -\beta\ket{1})$.
* Eğer ölçer ve sonuç 11 alırsak, süperpozisyon çöker ve sadece bu sonuca uygun şartlar bırakır. Bu $\alfa\ket{111} -\beta\ket{110}$. Bu $\ket{11}(\alfa\ket{1} -\beta\ket{0})$' olarak yeniden kullanılabilir. Bu nedenle birinci ve ikinci qubit'i 11 olarak ölçersek, __there__üçüncü qubitin $(\alpha\ket{1} -\beta\ket{0})$.

### <a name="step-4-interpret-the-result"></a>Adım 4: Sonucu yorumlama

Bir hatırlatma olarak, göndermek istediğimiz orijinal __mesaj:__

$$ \ket{\psi} = \alfa\ket{0} +{1} \beta\ket $$

Biz bu duruma __orada__ qubit almak gerekir, böylece alınan devlet amaçlanan biridir. 

* Biz ölçülen ve 00 bir sonucu var, sonra üçüncü qubit, __orada__, devlet{0} $(\alpha\ket +\beta\ket{1})$. Amaçlanan __ileti__bu olduğundan, değişiklik gerekmez.
* Biz ölçülen ve 01 bir sonucu var, sonra üçüncü qubit, __orada__, devlet{1} $(\alpha\ket +\beta\ket{0})$. Bu amaçlanan __ileti__farklıdır, ancak NOT kapısı uygulamak bize istenen durumu verir{0} $(\alpha\ket +\beta\ket{1})$.
* Biz ölçülen ve 10 bir sonucu var, o zaman üçüncü qubit, __orada__,{0} devlet $(\alpha\ket -\beta\ket{1})$. Bu amaçlanan __ileti__farklıdır, ancak Z kapısı uygulamak bize istenen durumu verir{0} $(\alpha\ket +\beta\ket{1})$.
* Biz ölçülen ve 11 bir sonucu var, sonra üçüncü qubit, __orada__, devlet{1} $(\alpha\ket -\beta\ket{0})$. Bu amaçlanan __ileti__farklıdır, ancak bir Not kapısı z kapısı takip uygulayarak bize istenen{0} durum $(\alpha\ket +\beta\ket{1})$verir.

Özetlemek gerekirse, ölçersek ve ilk qubit 1 ise, Z kapısı uygulanır. Ölçersek ve ikinci qubit 1 ise, NOT kapısı uygulanır.

### <a name="summary"></a>Özet
Aşağıda gösterilen ışınlanma uygulayan bir metin kitabı kuantum devresi. Soldan sağa hareket görebilirsiniz:
- Adım 1: __Burada__ ve __orada__ bir Hadamard kapısı ve CNOT kapısı uygulayarak entangling.
- Adım 2: __İletiyi__ CNOT kapısı ve Hadamard kapısı kullanarak gönderme.
- Adım 3: Birinci ve ikinci qubits, __mesaj__ ve __burada__bir ölçüm alarak .
- Adım 4: Adım 3'teki ölçüm sonucuna bağlı olarak NOT kapısı veya Z kapısı uygulamak.

!['Teleport(msg : Qubit, orada : Qubit) : Birim'](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>Kuantum Işınlama: Kod

Kuantum ışınlanması için devremiz var:

!['Teleport(msg : Qubit, orada : Qubit) : Birim'](~/media/teleportation.svg)

Artık bu kuantum devresindeki her adımı Q#'a çevirebiliriz.

### <a name="step-0-definition"></a>Adım 0: Tanım
Işınlanma gerçekleştirirken, göndermek istediğimiz __mesajı__ ve nereye göndermek istediğimizi bilmemiz gerekir (__orada).__ Bu nedenle, bağımsız değişken olarak iki qubit verilen yeni bir Teleport `msg` `there`işlemi tanımlayarak başlar ve:

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

Biz de bir `here` `using` blok ile elde qubit ayırmanız gerekir:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>Adım 1: Karışık bir durum oluşturma
Daha sonra `here` ve `there` @"microsoft.quantum.intrinsic.h" işlemleri @"microsoft.quantum.intrinsic.cnot" kullanarak arasında dolaşmış çifti oluşturabilirsiniz:

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>Adım 2: İletiyi gönderme
Daha sonra bir sonraki $\operatorname{CNOT}$ ve $H$ kapılarını kullanarak mesajımızı qubit'imizi hareket ettirici oluruz:

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>Adım 3 & 4: Sonucu ölçme ve yorumlama
Son olarak, @"microsoft.quantum.intrinsic.m" ölçümleri gerçekleştirmek ve istenilen durumu elde etmek için gerekli `if` geçit işlemlerini gerçekleştirmek için kullanırız, ifadelerde belirtildiği gibi:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a>Adım 5: Qubit kaydını yeniden başlatma

Her Q# operasyonunun sonunda qubitlerin $\ket{0}$ durumunda olmasını istiyoruz. Tüm qubitleri sıfır durumuna yeniden başlatmak için kullanabiliriz @"microsoft.quantum.intrinsic.reset" ve bu işlemimizi bitirir.

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


