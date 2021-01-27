---
title: Q#Standart kitaplıklarda tanılama
description: Q#Standart kitaplıklarda bulunan ve hisse ve hataların hatalarını yakalamak için kullanılan tanılama işlevleri ve işlemleri hakkında bilgi edinin.
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: d13122187a24893d297cfdbb3ad4db03eb22ded0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858691"
---
# <a name="diagnostics"></a>Tanılama #

Klasik geliştirmede olduğu gibi, hisse ve hata programlarındaki hataları ve hataları tanılamanıza de bilmek önemlidir.
Q#Standart kitaplıklar, bölümünde açıklandığı gibi hisse programlarının doğruluğunu sağlamak için çeşitli yollar sağlar <xref:microsoft.quantum.guide.testingdebugging> .
Büyük ölçüde konuşuyor, bu destek, hedef makineye ana bilgisayar programına veya geliştiriciye ek tanılama bilgileri sağlamasını belirten işlev ve işlemler biçiminde gelir veya işlev ya da işlem çağrısıyla ifade edilen koşulların ve varyantların doğruluğunu zorunlu kılar.

## <a name="machine-diagnostics"></a>Makine tanılama ##

Klasik değerler hakkında tanılama, <xref:Microsoft.Quantum.Intrinsic.Message> bir iletiyi makineye bağlı bir şekilde günlüğe kaydetmek için işlevi kullanılarak elde edilebilir.
Varsayılan olarak, bu dizeyi konsola yazar.
Enterpolasyonlu dizeler ile birlikte kullanıldığında, <xref:Microsoft.Quantum.Intrinsic.Message> Klasik değerler hakkında tanılama bilgilerini rapor etmelerini kolaylaştırır:

```qsharp
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message` imza içerir `(String -> Unit)` ve bir hata ayıklama günlüğü iletisinin yayılamıyor olduğunu temsil eder Q# .

<xref:Microsoft.Quantum.Diagnostics.DumpMachine>Ve <xref:Microsoft.Quantum.Diagnostics.DumpRegister> callables, hedef makinelere, geçerli olarak ayrılmış olan tüm qubits ve sırasıyla belirli bir qubit kaydı hakkında tanılama bilgileri sağlar.
Her bir hedef makine, bir döküm yönergesine yanıt olarak hangi tanılama bilgilerinin sağlandığını farklılık gösterir.
Örneğin, [tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator) hedef makinesi, ana bilgisayar programını, bir qubits 'in bir kaydını temsil etmek için dahili olarak kullandığı durum vektörünü sağlar.
Karşılaştırmayla, [Toffoli simülatör](xref:microsoft.quantum.machines.toffoli-simulator) hedef makinesi her bir qubit için tek bir klasik bit sağlar.

 [Tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator) çıkışı hakkında daha fazla bilgi edinmek için `DumpMachine` [test ve hata ayıklama Makalemizin](xref:microsoft.quantum.guide.testingdebugging#dump-functions)döküm işlevleri bölümüne göz atın.


## <a name="facts-and-assertions"></a>Olgular ve Onaylamalar ##

[Test ve hata ayıklama](xref:microsoft.quantum.guide.testingdebugging)bölümünde açıklandığı gibi, imzasına veya sırasıyla bir işlev veya işlem `Unit -> Unit` `Unit => Unit` *birim testi* olarak işaretlenebilir.
Her birim testi genellikle küçük bir hisse programından ve bu programın doğruluğunu kontrol eden bir veya daha fazla koşuldan oluşur.
Bu _koşullar, giriş_ olarak geçirilen bir veya daha fazla qubit 'in durumlarını kontrol eden her iki _olgu_ biçiminde gelebilir.

Örneğin, `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` $1 + 1 = $2 olan matematiksel olguyu temsil ederken, `AssertQubit(One, qubit)` `qubit` ölçüyle bir belirsizlik döndüren koşulu temsil eder `One` .
Önceki durumda, koşulun yalnızca kendi değerleri verilen değerini denetliyoruz, ikincisi de onaylaması değerlendirmek için qubit durumu hakkında bir şeyler bilmelidir.

Q#Standart kitaplıklar, olguları temsil etmek için çeşitli farklı işlevler sağlar; örneğin:

- <xref:Microsoft.Quantum.Diagnostics.Fact>
- <xref:Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact>
- <xref:Microsoft.Quantum.Diagnostics.NearEqualityFactC>
- <xref:Microsoft.Quantum.Diagnostics.EqualityFactI>


### <a name="testing-qubit-states"></a>Qubit durumlarını test etme ###

Pratikte, onaylamalar, gerçek makinemiz için bir simülatör kullanırken fiziksel ölçümleri ve onaylamaları yapabilmemiz gibi, tüm hisse uygun olmayan ölçümleri ve kayıt kaldırma işlemlerini [hiçbir](https://arxiv.org/abs/quant-ph/9607018)şekilde etkilemez.
Bu nedenle, donanıma dağıtım yapmadan önce tek tek işlemleri klasik Benzetici üzerinde test edebilirsiniz.
Onayların değerlendirmesine izin verilmeyen hedef makinelerde, çağrıları <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> güvenle yoksayılabilir.

Daha genel olarak, <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> işlem, verilen pabdtabanında verilen qubits 'leri ölçmeye her zaman verilen sonuca sahip olacağını onaylar.
Onaylama başarısız olursa, çalıştırma, belirtilen iletiyle çağırarak sona erer `fail` .
Varsayılan olarak, bu işlem uygulanmaz; Bunu destekleyebilen simülatörleri, çalışma zamanı denetimini gerçekleştiren bir uygulama sağlamalıdır.
`AssertMeasurement` imza içeriyor `((Pauli[], Qubit[], Result, String) -> ())` .
`AssertMeasurement`, Çıkış türü olarak boş bir tanımlama grubu olan bir işlev olduğundan, çağrılmasından hiçbir efekt `AssertMeasurement` bir program içinde observable değildir Q# .

<xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability>İşlem işlevi, verilen pabdtabanında verilen qubits 'in belirli bir tolerans dahilinde verilen olasılığa sahip olduğunu ölçmeye yönelik onaylar.
Tolerans eklenebilir (örneğin, `abs(expected-actual) < tol` ).
Onaylama başarısız olursa, çalıştırma, belirtilen iletiyle çağırarak sona erer `fail` .
Varsayılan olarak, bu işlem uygulanmaz; Bunu destekleyebilen simülatörleri, çalışma zamanı denetimini gerçekleştiren bir uygulama sağlamalıdır.
`AssertMeasurementProbability` imza içeriyor `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)` . `Double`Parametrelerin ilki, sonucun istenen olasılığını ve ikinci bir toleransı sağlar.

Tek bir ölçüm için bir Benzetici tarafından kullanılan klasik bilgilerin, bir qubit 'in iç durumunu temsil etmesi için kullanılan klasik bilgilerin kopyalanmaya, bu şekilde, fiticimizi test etmek için bir ölçüm gerçekleştirmeleri gerekmez.
Özellikle, bu, gerçek donanım üzerinde mümkün olmayan, *uyumsuz* ölçümler hakkında nedenimizi olanaklı kılmaktadır.

`P : Qubit => Unit`Girişi $ \ket $ durumunda olduğunda $ \ket{\psı} $ durumunun hazırlanması amaçlanan bir işlem olduğunu varsayalım {0} .
Let $ \ket{\psı '} $ tarafından hazırlanan gerçek eyalet olmalıdır `P` .
Ardından, $ \ket{\psı} = \ket{\psı '} $ ise ve yalnızca $ \ket{\psı} $ tarafından tanımlanan eksende $ \ket{\psı '} $ her zaman döndürülür `Zero` .
Diğer bir deyişle, \begin{hizalaması} \ket{\psı} = \ket{\psı '} \Text{IF ve yalnızca If} \braket{\psı | \psı '} = 1.
\end{hizalaması} Prelude tanımlanan temel işlemleri kullanarak, `Zero` $ \ket{\psı} $ Pauli işleçlerinden birinin eigenstate olması durumunda, döndüren bir ölçümü doğrudan gerçekleştirebiliriz.


Bu işlem, <xref:Microsoft.Quantum.Diagnostics.AssertQubit> < \ket{\psı} = \ket $ onayını test etmek istediğimiz için özellikle yararlı bir Özet sağlar {0} .
Bu, örneğin, {0} serbest bırakıldığımızda, serbest bırakmadan önce $ \ket $ ' e geri dönmek için hesaplandığımız zaman yaygındır.
$ \Ket {0} $ ' e karşı onaylama, iki durum hazırlığı `P` ve `Q` işlemlerinin her ikisinin de aynı durumu hazırlanmasını ve ne zaman `Q` desteklenmesini sağlamak için de yararlıdır `Adjoint` .
Özellikle,

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

Ancak genel olarak, Pauli işleçlerinin eigenstates ile aynı olmayan durumlar hakkında onaylara erişemeyebilirsiniz.
Örneğin, $ \ket{\psı} = (\ket {0} + e ^ {i \pi/8} \ket {1} )/\sqrt {2} $, bir Pauli işlecinin eigenstate değil; bu nedenle, <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> bir State $ \ket{\psı '} $ öğesinin $ \ket{\psı} $ değerine eşit olduğunu benzersiz şekilde tespit etmek için kullandığımyız.
Bunun yerine, simülatımız tarafından desteklenen temel elemanlar kullanılarak doğrudan sınanabilen varsayımlar halinde $ \ket{\psı '} = \ket{\psi} $ onaylama onayını kaldırdık.
Bunu yapmak için $ \ket{\psı} = \Alpha {0} \tus+ \beta \ demet $ ' i {1} karmaşık sayılar için $ \Alpha = a \_ r + a \_ i i $ ve $ \beta $ $.
Bu ifadenin, \{ \_ \_ \_ \_ \} her bir karmaşık sayının gerçek ve sanal bir parçanın toplamı olarak ifade edileceği dört gerçek sayı olan $ a r, ı, b r, b i $ değerini belirtmesini unutmayın.
Ancak genel aşama nedeniyle, \_ tek bir tek qubit durumu belirtmek için yalnızca üç gerçek numaraya ihtiyacımız olacak şekilde $a i = $0 ' i seçebiliriz.

Bu nedenle, beklediğimiz durumu belirlemek için birbirinden bağımsız olan üç onay belirtmemiz gerekir.
Bu `Zero` , $ \Alpha $ ve $ \beta $ ' ya verilen her Pauli ölçümü için gözlemleme olasılığını bularak her birini ayrı ayrı ele aldık.
`Result`Sırasıyla Pauli $X $, $Y $ ve $Z $ ölçümleri için $x $, $y $ ve $z $ değerlerinin olmasına izin verin.
Ardından, hisse ölçümlerine yönelik olasılık işlevini kullanarak \begin{hizalaması} \Pr (x = \Texttt{dd} | \Alpha, \beta) & = \frac12 + a \_ r b \_ r + a \_ ı b \_ ı \\ \\ \Pr (y = \Texttt{dd} | \alpha, \beta) & = \frac12 + a \_ r b \_ ı-a \_ ı b \_ r \\ \\ \pr (z = \texttt{dd} | \Alpha, \beta) & = \frac12\left (1 + a r ^ 2 + a i ^ 2 + b \_ \_ \_ r ^ 2 + b \_ i ^ 2 \ sağda).
\end{hizalaması}

<xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance>İşlem bu onaylamaları, $ \Alpha $ ve $ \beta $ ' ın tür değerleri olarak verilen gösterimlerine uygular <xref:Microsoft.Quantum.Math.Complex> .
Beklenen durum matematik olarak hesaplanabileceğinden bu faydalıdır.

### <a name="asserting-equality-of-quantum-operations"></a>Hisse Işlemlerinin eşitliğini ele ###

Bu nedenle, belirli durumları hazırlamaya yönelik test işlemleriyle ilgilentik.
Ancak, genellikle bir işlemin tek bir sabit giriş yerine rastgele girişler için nasıl davrandığını öğreniyoruz.
Örneğin, `U : ((Double, Qubit[]) => () : Adjoint)` bir dizi Unitary işleçlerine karşılık gelen bir işlemi uyguladığımızda $U (t) $, ve kullanmak yerine açık bir blok sağladık `adjoint` `adjoint auto` .
$T $ bir evlenme süresini temsil ediyorsa, bu $U ^ \hanger (t) = U (-t) $, beklenen şekilde ilgileniyor olabilir.

Genel anlamda, iki işlem ve aynı şekilde hareket eden onaylama yaparken izleyebilmemiz için iki farklı strateji vardır `U` `V` .
İlk olarak, `U(target); (Adjoint V)(target);` her durumu belirli bir temelinde koruyan denetliyoruz.
İkincisi, `U(target); (Adjoint V)(target);` entangled 'in yarısı üzerinde işlem yapan bu entanglement 'i korur.
Bu stratejiler, Canon işlemleri <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> ve <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> sırasıyla uygulanır.

> [!NOTE]
> Yukarıda açıklanan başvurulan onaylama, $n $ qubits üzerindeki işlemleri $2n $ qubits 'teki bir durum ile ilişkilendiren bir matematik çerçevesi olan [CHOI – Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality)temel alınarak çalışmaktadır.
> Özellikle, $n $ qubits üzerindeki kimlik işlemi, entangled State $ \ket{\ beta_ {00} } \mathrel{: =} (\ket {00} + \ demet {11} )/\sqrt $ öğesinin $n $ kopyaları tarafından temsil edilir {2} .
> Bu işlem <xref:Microsoft.Quantum.Preparation.PrepareChoiState> , belirli bir işlemi temsil eden bir durum hazırlarken bu isomorphism uygular.

Kabaca, bu stratejiler bir zaman alanına göre ayırt edilir: Space zorunluluğunu getirir.
Her giriş durumu için yineleme ek zaman alır, ancak başvuru olarak entanglement kullanılması ek qubit depolanmasını gerektirir.
Bir işlemin yalnızca hesaplama tabanlı durumlarıyla ilgili davranışını ilgilentireceğiz gibi, tersine çevrilebilir bir işlem uyguladığı durumlarda, <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis> Bu kısıtlanmış giriş kümesinde eşitliği sınar.

> [!TIP]
> Giriş durumları üzerindeki yineleme, numaralandırma işlemleri ve tarafından işlenir <xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct> <xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower> .
> Bu işlemler, iki veya daha fazla küme arasındaki Kartezyen ürünün her bir öğesine bir işlem uygulamak için daha genel bir seçenektir.

Ancak, bu iki yaklaşımlar İnceleme altındaki işlemlerin farklı özelliklerini test etmek.
Yerinde onaylama işlemi her bir işlemi birden çok kez çağırarak her giriş durumu için bir kez tüm rastgele seçimler ve ölçüm sonuçları çağrılar arasında değişebilir.
Buna karşılık, başvurulan onaylama her işlemi tam olarak bir kez çağırır. bu şekilde, işlemlerin *tek bir görüntüsündeki* eşit olduğunu kontrol eder.
Bu testlerin her ikisi de hisse programlarının doğruluğunu sağlamak için yararlıdır.


## <a name="further-reading"></a>Daha Fazla Bilgi ##

- <xref:microsoft.quantum.guide.testingdebugging>
- <xref:Microsoft.Quantum.Diagnostics>
