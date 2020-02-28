---
title: 'Q # standart kitaplıklarında tanılama'
description: 'Hisse ve hata hatalarını yakalamak için kullanılan Q # standart kitaplıklarında Tanılama işlevleri ve işlemler hakkında bilgi edinin.'
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: ba2f248327bb3db4ee895f8e65ea31c17e42b5f4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906245"
---
# <a name="diagnostics"></a>Tanılama #

Klasik geliştirmede olduğu gibi, hisse ve hata programlarındaki hataları ve hataları tanılamanıza de bilmek önemlidir.
Q # standart kitaplıkları, <xref:microsoft.quantum.techniques.testing-and-debugging>bölümünde açıklandığı gibi hisse programlarının doğruluğunu sağlamak için çeşitli yollar sunar.
Büyük ölçüde konuşuyor, bu destek, hedef makineye ana bilgisayar programına veya geliştiriciye ek tanılama bilgileri sağlamasını sağlayan işlevler ve işlemler biçiminde gelir veya koşulların ve ınvaryanların doğruluğunu zorunlu kılar işlev veya işlem çağrısı.

## <a name="machine-diagnostics"></a>Makine tanılama ##

Klasik değerler hakkında tanılama, bir iletiyi makineye bağlı bir şekilde günlüğe kaydetmek için <xref:microsoft.quantum.intrinsic.message> işlevi kullanılarak elde edilebilir.
Varsayılan olarak, bu dizeyi konsola yazar.
Enterpolasyonlu dizeler ile birlikte kullanıldığında <xref:microsoft.quantum.intrinsic.message> klasik değerler hakkında tanılama bilgilerini rapor etmelerini kolaylaştırır:

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message` imza `(String -> Unit)`, bir hata ayıklama günlüğü iletisinin yaydığını temsil eden, Q # içinden de gözlemlenemez.

<xref:microsoft.quantum.diagnostics.dumpmachine> ve <xref:microsoft.quantum.diagnostics.dumpregister> callables, hedef makinelere, geçerli olarak ayrılmış olan tüm qubits ve sırasıyla belirli bir qubit kaydı hakkında tanılama bilgileri sağlamalarına yönlendirir.
Her bir hedef makine, bir döküm yönergesine yanıt olarak hangi tanılama bilgilerinin sağlandığını farklılık gösterir.
Örneğin, [tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator) hedef makinesi, ana bilgisayar programını, bir qubits 'in bir kaydını temsil etmek için dahili olarak kullandığı durum vektörünü sağlar.
Karşılaştırmayla, [Toffoli simülatör](xref:microsoft.quantum.machines.toffoli-simulator) hedef makinesi her bir qubit için tek bir klasik bit sağlar.

 [Tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator) `DumpMachine` çıkışı hakkında daha fazla bilgi edinmek için [test ve hata ayıklama makaleimizin](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions)döküm işlevleri bölümüne göz atın.


## <a name="facts-and-assertions"></a>Olgular ve Onaylamalar ##

[Test ve hata ayıklama](xref:microsoft.quantum.techniques.testing-and-debugging)bölümünde açıklandığı gibi, sırasıyla imza `Unit -> Unit` veya `Unit => Unit`olan bir işlev veya işlem *birim testi*olarak işaretlenebilir.
Her birim testi genellikle küçük bir hisse programından ve bu programın doğruluğunu kontrol eden bir veya daha fazla koşuldan oluşur.
Bu _koşullar, giriş_olarak geçirilen bir veya daha fazla qubit 'in durumlarını kontrol eden her iki _olgu_biçiminde gelebilir.

Örneğin `EqualityFactI(1 + 1, 2, "1 + 1 != 2")`, $1 + 1 = $2 olan matematiksel olguyu temsil ederken `AssertQubit(One, qubit)`, `qubit` ölçmeye yönelik bir `One` döndüren koşulu temsil eder.
Önceki durumda, koşulun yalnızca kendi değerleri verilen değerini denetliyoruz, ikincisi de onaylaması değerlendirmek için qubit durumu hakkında bir şeyler bilmelidir.

Q # standart kitaplıkları, olguları temsil etmek için çeşitli farklı işlevler sağlar; örneğin:

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfactc>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a>Qubit durumlarını test etme ###

Pratikte, onaylamalar, gerçek makinemiz için bir simülatör kullanırken fiziksel ölçümleri ve onaylamaları yapabilmemiz gibi, tüm hisse uygun olmayan ölçümleri ve kayıt kaldırma işlemlerini [hiçbir](https://arxiv.org/abs/quant-ph/9607018)şekilde etkilemez.
Bu nedenle, donanıma dağıtım yapmadan önce tek tek işlemleri klasik Benzetici üzerinde test edebilirsiniz.
Onayların değerlendirmesine izin verilmeyen hedef makinelerde, <xref:microsoft.quantum.intrinsic.assert> çağrıları güvenle yoksayılabilir.

Daha genel olarak, <xref:microsoft.quantum.intrinsic.assert> işlemi verilen Pabdtabanında verilen qubits 'in her zaman verilen sonuca göre ölçülmesini onaylar.
Onaylama başarısız olursa, yürütme, verilen iletiyle `fail` çağırarak sona erer.
Varsayılan olarak, bu işlem uygulanmaz; Bunu destekleyebilen simülatörleri, çalışma zamanı denetimini gerçekleştiren bir uygulama sağlamalıdır.
`Assert` imza `((Pauli[], Qubit[], Result, String) -> ())`sahip.
`Assert`, çıkış türü olarak boş bir tanımlama grubu olan bir işlev olduğundan, `Assert` çağırmaktan hiçbir efekt bir Q # programı içinde observable değildir.

<xref:microsoft.quantum.intrinsic.assertprob> Operation işlevi, verilen Pabdtabanında verilen qubits 'in belirli bir tolerans dahilinde verilen olasılığa sahip olduğunu ölçmeye yönelik onaylar.
Tolerans eklenebilir (ör. `abs(expected-actual) < tol`).
Onaylama başarısız olursa, yürütme, verilen iletiyle `fail` çağırarak sona erer.
Varsayılan olarak, bu işlem uygulanmaz; Bunu destekleyebilen simülatörleri, çalışma zamanı denetimini gerçekleştiren bir uygulama sağlamalıdır.
`AssertProb` imza `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`sahip. `Double` parametrelerin ilki, sonucun istenen olasılığını ve ikinci bir toleransı sağlar.

Tek bir ölçüm için bir Benzetici tarafından kullanılan klasik bilgilerin, bir qubit 'in iç durumunu temsil etmesi için kullanılan klasik bilgilerin kopyalanmaya, bu şekilde, fiticimizi test etmek için bir ölçüm gerçekleştirmeleri gerekmez.
Özellikle, bu, gerçek donanım üzerinde mümkün olmayan, *uyumsuz* ölçümler hakkında nedenimizi olanaklı kılmaktadır.

`P : Qubit => Unit`, girişi $ \ket{0}$ durumunda olduğunda $ \ket{\psı} $ durumunun hazırlanması amaçlanan bir işlem olduğunu varsayalım.
Let $ \ket{\psı '} $ `P`tarafından hazırlanan gerçek eyalet olmalıdır.
Ardından, $ \ket{\psı} = \ket{\psı '} $ varsa ve yalnızca $ \ket{\psı} $ tarafından tanımlanan eksende $ \ket{\psı '} $ ölçmesi her zaman `Zero`döndürür.
Diğer bir deyişle, \begin{hizalaması} \ket{\psı} = \ket{\psı '} \Text{IF ve yalnızca If} \braket{\psı | \psı '} = 1.
\end{hizalaması} Prelude tanımlı temel işlemleri kullanarak, $ \ket{\psı} $, Pauli işleçlerinden birinin bir egenstate 'i olan `Zero` döndüren bir ölçümü doğrudan gerçekleştirebiliriz.


İşlem <xref:microsoft.quantum.diagnostics.assertqubit>, < \ket{\psı} = \tus{0}$ onay testini test etmek istediğimiz için özellikle yararlı bir Özet sağlar.
Bu, örneğin, serbest bir{0}şekilde hesaplandığımızda, sevk ettiğimiz zaman (örneğin,
$ \Ket{0}$ ' a karşı onaylama, ayrıca iki durum hazırlama `P` ve `Q` işlemlerinin aynı durumu hazırlanmasını ve `Q` `Adjoint`desteklediğinde de yararlı olur.
Özellikle,

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

Ancak genel olarak, Pauli işleçlerinin eigenstates ile aynı olmayan durumlar hakkında onaylara erişemeyebilirsiniz.
Örneğin, $ \ket{\psı} = (\ket{0} + e ^ {i \pi/8} \ayraç{1})/\sqrt{2}$ herhangi bir Pauli işlecinin eigenstate değil, bu şekilde, bir State $ \ket{\psı '} $ $ \ket{\psı} $ değerine eşit olduğunu benzersiz şekilde belirleyebilmek için <xref:microsoft.quantum.intrinsic.assertprob> kullanmıyoruz.
Bunun yerine, simülatımız tarafından desteklenen temel elemanlar kullanılarak doğrudan sınanabilen varsayımlar halinde $ \ket{\psı '} = \ket{\psi} $ onaylama onayını kaldırdık.
Bunu yapmak için $ \ket{\psı} = \Alpha \ket{0} + \beta \ ayraç{1}$ karmaşık sayılar için $ \Alpha = a\_r + a\_i i $ ve $ \beta $.
Bu ifadenin, her bir karmaşık sayının gerçek ve sanal bir parçanın toplamı olarak ifade edileceği şekilde, bir\_i, b\_r, b\_i\}$\_\{dört gerçek sayı olacağını unutmayın.
Ancak genel aşama nedeniyle, tek bir tek qubit durumu belirtmek için yalnızca üç gerçek numaraya ihtiyacımız olacak şekilde $a\_i = $0 ' i seçebiliriz.

Bu nedenle, beklediğimiz durumu belirlemek için birbirinden bağımsız olan üç onay belirtmemiz gerekir.
Bu, $ \Alpha $ ve $ \beta $ verilen her bir Pauli ölçümü için `Zero` gözlemleme olasılığını bularak her birini ayrı ayrı ele aldık.
$X $, $y $ ve $z $, Pauli $X $, $Y $ ve $Z $ ölçümleri için sırasıyla `Result` değer olmasına izin verir.
Ardından, hisse ölçüleri için olasılık işlevi, \begin{hizalaması} \Pr (x = \Texttt{dd} | \Alpha, \beta) & = \frac12 + a\_r b\_r + a\_ı b\_ı \\\\ \Pr (y = \Texttt{dd} | \Alpha, \beta) & = \frac12 + a\_r b\_ı-a\_ı b\_r \\\\ \Pr (z = \Texttt{sıfırlaması} | \Alpha, \beta) & = \frac12\left (1 + a\_r ^ 2 + b\_i ^ 2 \ doğru).\_\_
\end{hizalaması}

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> işlemi, bu onaylamaları, $ \Alpha $ ve $ \beta $ ' nin <xref:microsoft.quantum.math.complex>türünde değerler olarak verilen gösterimleri uygular.
Beklenen durum matematik olarak hesaplanabileceğinden bu faydalıdır.

### <a name="asserting-equality-of-quantum-operations"></a>Hisse Işlemlerinin eşitliğini ele ###

Bu nedenle, belirli durumları hazırlamaya yönelik test işlemleriyle ilgilentik.
Ancak, genellikle bir işlemin tek bir sabit giriş yerine rastgele girişler için nasıl davrandığını öğreniyoruz.
Örneğin, bir işlem `U : ((Double, Qubit[]) => () : Adjoint)`, bir Unitary işleçleri $U (t) $ ' e karşılık gelen bir işlemi uyguladığımyız ve `adjoint auto`kullanmak yerine açık bir `adjoint` bloğu sağladık.
$T $ bir evlenme süresini temsil ediyorsa, bu $U ^ \hanger (t) = U (-t) $, beklenen şekilde ilgileniyor olabilir.

Genel anlamda, iki işlemin `U` ve `V` aynı şekilde hareket etmesini sağlayan iki farklı strateji vardır.
İlk olarak, `U(target); (Adjoint V)(target);` her durumu belirli bir temelinde koruyabiliriz.
İkincisi, entangled durumunun yarısını oluşturan `U(target); (Adjoint V)(target);`, bu entanglement 'i korur.
Bu stratejiler, sırasıyla Canon Operations <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> ve <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced>tarafından uygulanır.

> [!NOTE]
> Yukarıda açıklanan başvurulan onaylama, $n $ qubits üzerindeki işlemleri $2n $ qubits 'teki bir durum ile ilişkilendiren bir matematik çerçevesi olan [CHOI – Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality)temel alınarak çalışmaktadır.
> Özellikle, $n $ qubits üzerindeki kimlik işlemi, entangled State $ \ket{\ beta_{00}} \mathrel{: =} (\tus{00} + \tus{11})/\sqrt{2}$ $n $ kopyaları tarafından temsil edilir.
> İşlem <xref:microsoft.quantum.preparation.preparechoistate>, belirli bir işlemi temsil eden bir durum hazırlarken bu isomorphism uygular.

Kabaca, bu stratejiler bir zaman alanına göre ayırt edilir: Space zorunluluğunu getirir.
Her giriş durumu için yineleme ek zaman alır, ancak başvuru olarak entanglement kullanılması ek qubit depolanmasını gerektirir.
Bir işlemin yalnızca hesaplama tabanlı durumlar üzerinde davranışını ilgilentireceğiz gibi, tersine çevrilebilir bir işlem uyguladığı durumlarda, bu kısıtlanmış giriş kümesinde <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis>.

> [!TIP]
> Giriş durumları üzerinde yineleme, <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> ve <xref:microsoft.quantum.canon.iteratethroughcartesianpower>sabit listesi işlemleri tarafından işlenir.
> Bu işlemler, iki veya daha fazla küme arasındaki Kartezyen ürünün her bir öğesine bir işlem uygulamak için daha genel bir seçenektir.

Ancak, bu iki yaklaşımlar İnceleme altındaki işlemlerin farklı özelliklerini test etmek.
Yerinde onaylama işlemi her bir işlemi birden çok kez çağırarak her giriş durumu için bir kez tüm rastgele seçimler ve ölçüm sonuçları çağrılar arasında değişebilir.
Buna karşılık, başvurulan onaylama her işlemi tam olarak bir kez çağırır. bu şekilde, işlemlerin *tek bir görüntüsündeki*eşit olduğunu kontrol eder.
Bu testlerin her ikisi de hisse programlarının doğruluğunu sağlamak için yararlıdır.


## <a name="further-reading"></a>Daha Fazla Bilgi ##

- <xref:microsoft.quantum.techniques.testing-and-debugging>
- <xref:microsoft.quantum.diagnostics>
