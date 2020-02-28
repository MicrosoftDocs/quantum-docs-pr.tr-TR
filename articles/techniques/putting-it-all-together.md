---
title: 'S # teknik-tümünü bir araya getirme'
description: 'Hisse anını gösteren temel bir Q # programını gözden geçir.'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 6c988f77ef6e433945dbf21dfb41204c74bdda3e
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906840"
---
# <a name="putting-it-all-together-teleportation"></a>Hepsini birlikte yerleştirme: Teleporsyon #
Şimdi, [hisse devrelerin](xref:microsoft.quantum.concepts.circuits)içinde tanımlanan teleporsyon devresi örneğine dönelim. Şimdiye kadar öğrendiğimiz kavramları göstermek için bunu kullanacağız. Aşağıda, teorik ve Q # içindeki kod uygulamasına yönelik bir adım adım yol açan bir işlem için aşağıda verilmiştir. 

## <a name="quantum-teleportation-theory"></a>Hisse ve Teleporsyon: teorisi
Hisse atısyon, bir konumdaki qubitden başka bir konumdaki qubit 'e ('__ileti__' olarak adlandırılıyoruz) bilinmeyen bir hisse durumu göndermeye yönelik bir tekniktir (sırasıyla ' buraya ' ve '__burada__ __',__ bu qubits 'e başvuracağız). Dirac gösterimini kullanarak __iletinizi__ bir vektör olarak temsil edebilirsiniz: 

$ $ \ket{\psı} = \harfler \ ayraç{0} + \beta\ayraç{1} $ $

$ \Alpha $ ve $ \beta $ değerlerini bildiğimiz için, __iletinin__ qubit durumu bizim için bilinmiyor şeklindedir.

### <a name="step-1-create-an-entangled-state"></a>1\. Adım: bir entangled durumu oluşturma
__Burada__ __qubit için__ihtiyacımız olan __iletiyi__ , bu adreste qubit ile zenginbir şekilde göndermek için. Bu, bir Hadamard kapısı ve ardından bir CNOT kapısı uygulanarak elde edilir. Bu kapı işlemlerinin arkasındaki matematik bölümüne bakalım.

__Burada__ qubits ile başlayacağız ve $ \demet{0}$ __durumunda olacak.__ Bu qubits 'i doğruladıktan sonra, bu durum şu durumlardır:

$ $ \ket{\phi ^ +} = \frac{1}{\sqrt{2}} (\ayraç{00} + \ket{11}) $ $

### <a name="step-2-send-the-message"></a>2\. Adım: iletiyi gönderin
__İletiyi__ göndermek için öncelikle __ileti__ qubit ve __burada__ giriş olarak bir cnot kapısı uyguladık (Bu örnekte, __ileti__ qubit ve hedef qubit __, bu__ örnekte bu durumda). Bu giriş durumu yazılabilir:

$ $ \ket{\psi}\ket{\phi ^ +} = (\harfler \ ayraç{0} + \beta\ayraç{1}) (\frac{1}{\sqrt{2}} (\demet{00} + \tus{11})) $ $

Bu, şu şekilde genişletilir:

$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\harflerden}{\sqrt{2}} \tus{000} + \frac{\harflerden} {\sqrt{2}} \tus{011} + \frac{\beta}{\sqrt{2}} \tus{100} + \frac{\beta}{\sqrt{2}} \tus{111} $ $

Bir anımsatıcı olarak, CNOT kapısı, denetim qubit 1 olduğunda hedef qubit 'i çevirir. Örneğin, $ \ket{000}$ girişi, ilk qubit (denetim) 0 olduğunda hiçbir değişikliğe neden olmaz. Ancak, ilk qubitin 1 olduğu, örneğin $ \ket{100}$ girişi gibi bir durum alın. Bu örnekte çıktı, ikinci qubit (hedef) CNOT kapısı tarafından çevrilmiş olarak $ \ket{110}$ şeklindedir.

Şimdi, CNOT kapısı yukarıdaki girişte işlem yaptıktan sonra Çıktımızı göz atalım. Sonuç:

$ $ \frac{\harflerden}{\sqrt{2}} \tus{000} + \frac{\harflerden}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \tus{110} + \frac{\beta}{\sqrt{2}} \tus{101} $ $

__İletiyi__ göndermek için bir sonraki adım, __ileti__ qubit 'e bir Hadamard Gate (her bir terimin ilk qubıdır) uygulamaktır. 

Anımsatıcı olarak Hadamard kapısı şunları yapar:

Girdi | Çıktı
---------------------------| ---------------------------------------------------------------
$ \demet{0}$  | $ \frac{1}{\sqrt{2}} (\ayraç{0} + \ket{1}) $
$ \demet{1}$  | $ \frac{1}{\sqrt{2}} (\ayraç{0}-\demet{1}) $

Yukarıdaki çıktımızın her bir teriminin ilk qubit ' i için Hadamard geçidini uygulıyoruz, aşağıdaki sonucu elde ediyoruz:

$ $ \frac{\harflerden}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\demet{0} + \tus{1})) \ayraç{00} + \frac{\harflerden}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\tus{0} + \tus{1})) \tus{11} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\demet{0}-\ayraç{1})) \ayraç{10} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\demet{0}-\demet{1})) \tus{01} $ $

Her dönemde $2 \frac{1}{\sqrt{2}} $ faktörlerinin olduğunu unutmayın. Aşağıdaki sonucu vererek bunları çarpıyoruz:

$ $ \frac{\harflerden}{2}(\demet{0} + \ ayraç{1}) \ayraç{00} + \frac{\harflerden}{2}(\demet{0} + \tus{1}) \tus{11} + \frac{\beta}{2}(\demet{0}-\ayraç{1}) \ayraç{10} + \frac{\beta}{2}(\demet{0}-\ayraç{1}) \ayraç{01} $ $

$ \Frac{1}{2}$ faktörü her bir terim için ortaktır, bu sayede artık köşeli ayracın dışına götürebiliriz:

$ $ \frac{1}{2}\big [\Alpha (\demet{0} + \ket{1}) \ayraç{00} + \alfa (\ayraç{0} + \ayraç{1}) \ayraç{11} + \beta (\demet{0}-\ayraç{1}) \demet{10} + \beta (\demet{0}{1}{01}

Böylece, her dönem için köşeli ayraçları derecelebiliriz:

$ $ \frac{1}{2}\Büyük [\harfler \ ayraç{000} + \ harfler \ ayraç{100} + \ harfler \ ayraç{011} + \ harfler \ ayraç{111} + \beta\ayraç{010}-\beta\demet{110} + \beta\ayraç{001}-\beta\demet{101}\big] $ $

### <a name="step-3-measure-the-result"></a>3\. Adım: sonucu ölçme

__Burada__ __olduğu gibi__ , __burada__ bulunan her türlü ölçüm bu __durumun durumunu etkiler.__ Birinci ve ikinci qubit ' i (__ileti__ ve __burada__) ölçyoruz, bu entanglement özelliği nedeniyle __hangi durumda olduğunu__ öğreniyoruz. 

* Bir sonucu ölçyoruz ve elde ediyorsanız, üst konum daraltılır ve bu sonuçla yalnızca koşulların tutarlılığını bırakır. Bu, $ \ harfler \ ayraç{000} + \beta\ayraç{001}$. Bu, yeniden düzenlenmiş to $ \ket{00}(\harflerden \ayraç{0} + \beta\ayraç{1}) $. Bu nedenle, birinci ve ikinci qubit 'i 00 olarak ölçyoruz, burada üçüncü qubit, __burada__$ (\harflerden \demet{0} + \beta\tus{1}) $ olduğunu biliyoruz.
* Bir sonucu ölçyoruz ve elde ediyorsanız, üst konum daraltılır ve yalnızca bu sonuçla tutarlı şartlar bırakılır. Bu, $ \ harfler \ ayraç{011} + \beta\ayraç{010}$. Bu, yeniden düzenlenmiş to $ \ket{01}(\harflerden \ayraç{1} + \beta\ayraç{0}) $. Bu nedenle, birinci ve ikinci qubit 'i 01 olarak ölçyoruz, burada üçüncü qubit, __burada__$ (\harflerden \demet{1} + \beta\tus{0}) $ olduğunu biliyoruz.
* Bir sonuç 10 ' u ölçyoruz ve elde etmemiz durumunda, üst konum daraltılır ve bu sonuçla yalnızca koşulların tutarlılığını bırakır. Bu, $ \ harfler \ ayraç{100}-\beta\ayraç{101}$. Bu, yeniden düzenlenmiş to $ \ket{10}(\harflerden \ayraç{0}-\beta\ayraç{1}) $ olur. Bu nedenle, birinci ve ikinci qubit ' i 10 olarak ölçyoruz, burada üçüncü qubit, __burada__$ (\harflerden \demet{0}-\beta\demet{1}) $ olduğunu biliyoruz.
* Bir sonuç 11 ' i ölçyoruz ve elde ediyorsanız, üst konum daraltılır ve yalnızca bu sonuçla tutarlı şartlar bırakılır. Bu, $ \ harfler \ ayraç{111}-\beta\ayraç{110}$. Bu, yeniden düzenlenmiş to $ \ket{11}(\harflerden \ayraç{1}-\beta\ayraç{0}) $ olur. Bu nedenle, birinci ve ikinci qubit 'i 11 olarak ölçyoruz, burada üçüncü qubit, __burada__$ (\harflerden \demet{1}-\beta\demet{0}) $ olduğunu biliyoruz.

### <a name="step-4-interpret-the-result"></a>4\. Adım: sonucu yorumlama

Anımsatıcı olarak, daha önce gönderilmek üzere sunduğumuz özgün __ileti__ :

$ $ \ket{\psı} = \harfler \ ayraç{0} + \beta\ayraç{1} $ $

Alınan durumun amaçlanan durum olması için bu duruma __kadar quge almamız__ gerekir. 

* 00 değerini ölçtüğünüz ve elde ettiğimiz takdirde, üçüncü qubit __, $__ (\harflerden \demet{0} + \beta\demet{1}) $ durumunda olur. Bu istenen __ileti__olduğundan, hiçbir değişiklik yapılması gerekmez.
* 01 değerini ölçtüğünüz ve sonucu elde etmemiz durumunda üçüncü qubit __, $__ (\harflerden \demet{1} + \beta\demet{0}) $ şeklindedir. Bu, amaçlanan __iletiden__farklıdır, ancak Not kapısı uygulandığında istenen durum $ (\harfler \ ayraç{0} + \beta\ayraç{1}) $ sunulmaktadır.
* 10 ' un bir sonucu ölçtüğünüz ve elde etmemiz durumunda, üçüncü qubit __, $__ (\harflerden \demet{0}-\beta\demet{1}) $ şeklindedir. Bu, hedeflenen __iletiden__farklıdır, ancak Z kapısı uygulandığında istenen durum $ (\harflerden \ayraç{0} + \beta\ayraç{1}) $ sunulmaktadır.
* 11 değerini ölçtüğünüz ve sonucu elde ediyorsanız, üçüncü qubit __, $__ (\harflerden \demet{1}-\beta\demet{0}) $ durumunda olur. Bu, hedeflenen __iletiden__farklıdır, ancak bir Z kapısı ve ardından bir Z kapısı, istenen durum $ (\harflerden \ayraç{0} + \beta\ayraç{1}) $ değerini verir.

Özetlemek gerekirse, ölçyoruz ve ilk qubit 1 ise, Z kapısı uygulanır. Ölçyoruz ve ikinci qubit 1 ise, NOT kapısı uygulanır.

### <a name="summary"></a>Özet
Aşağıda gösterildiği gibi, teleporsyon uygulayan bir metin kitabı hisse devresi verilmiştir. Soldan sağa doğru hareket etmek için şunları görebilirsiniz:
- 1\. Adım: bir Hadamard kapısı __ve__ cnot kapısı uygulayarak __burada__ bir göz atın.
- 2\. Adım: bir CNOT kapısı ve Hadamard kapısı kullanarak __Ileti__ gönderme.
- 3\. Adım: birinci ve ikinci qubit, __ileti__ ve __burada__ölçüm alma.
- 4\. Adım: 3. adımdaki ölçümün sonucuna bağlı olarak NOT kapısı veya Z kapısı uygulama.

![' Teleport (MSG: qubit, burada: qubit): Unit '](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>Hisse ve Teleporsyon: kod

Hisse için bağlantı hattı için devreniz:

![' Teleport (MSG: qubit, burada: qubit): Unit '](~/media/teleportation.svg)

Artık bu hisse içindeki adımların her birini Q # olarak çevirebiliriz.

### <a name="step-0-definition"></a>Adım 0: tanım
Teleporsyon gerçekleştirdiğimiz zaman, göndermek istediğimiz __iletiyi__ ve nereye__gönderileceğini (burada__) öğrenmemiz gerekir. Bu nedenle, `msg` ve `there`bağımsız değişken olarak iki qubit verilen yeni bir teleport işlemi tanımlayarak başlayacağız:

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

Ayrıca, bir `using` bloğuyla elde ettiğimiz bir qubit `here` de ayırmanız gerekir:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>1\. Adım: bir entangled durumu oluşturma
Daha sonra, @"microsoft.quantum.intrinsic.h" ve @"microsoft.quantum.intrinsic.cnot" işlemlerini kullanarak `here` ve `there` arasında entangled çiftini oluşturarız:

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>2\. Adım: iletiyi gönderin
Daha sonra, ileti qubit bitini taşımak için sonraki $ \operatorname{CNOT} $ ve $H $ kapıları kullanın:

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>3\. adım & 4: sonucu ölçme ve yorumlama
Son olarak, ölçümleri gerçekleştirmek ve `if` deyimleriyle gösterildiği gibi istenen durumu almak için gerekli olan geçit işlemlerini gerçekleştirmek üzere @"microsoft.quantum.intrinsic.m" kullanırız:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

Bu, teleporsyon operatörünüzün tanımını tamamlar, bu nedenle `here`serbest bırakabilir, gövdeyi sonlandırabilmeniz ve işlemi sonlandırabiliriz.

```qsharp
    }
}
```
