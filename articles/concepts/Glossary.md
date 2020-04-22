---
title: Kuantum bilgi işlem sözlüğü
description: Kuantum bilgi işlemde kullanılan ortak terimler, eylemler ve nesneler sözlüğü.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: ee78515a0f47730b7d3df10da0853c5b8a7f6624
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81482221"
---
# <a name="quantum-computing-glossary"></a>Kuantum bilgi işlem sözlüğü

## <a name="adjoint"></a>Adjoint

Karmaşık eşlekap bir [işlemin transktos](xref:microsoft.quantum.glossary#operation). [Üniter](xref:microsoft.quantum.glossary#unitary-operator) bir işleç uygulayan işlemler için, bitişik işlem ters ve bir hançer sembolü ile gösterilir. Örneğin, işlem `U` birimsel işleci temsil ediyorsa `Adjoint U` $U$, sonra $U^\hançer$'ı temsil eder. Daha fazla bilgi için [Adjoint'a](xref:microsoft.quantum.language.file-structure#adjoint)bakın.

## <a name="ancilla"></a>Ancilla

Bir kuantum bilgisayarı için geçici bellek görevi sunan ve gerektiğinde ayrılan ve ayrılan bir [qubit.](xref:microsoft.quantum.glossary#qubit)  Daha fazla bilgi için [çoklu qubits'e](xref:microsoft.quantum.concepts.multiple-qubits)bakın.

## <a name="bell-state"></a>Çan durumu

İki qubitin [entangled](xref:microsoft.quantum.glossary#entanglement) dört özel kuantum [eyaletinden](xref:microsoft.quantum.glossary#quantum-state) biri. Dört durum $\ket{\beta_{ij}} = (\mathbb{I} \otimes X^iZ^j){00} (\ket +{11}\ket{2}) / \sqrt $olarak tanımlanır. Bell durumu, [EPR çifti](xref:microsoft.quantum.glossary#epr-pair)olarak da bilinir.

## <a name="bloch-sphere"></a>Bloch küresi

Üç boyutlu bir birim kürede nokta olarak tek[bir qubit](xref:microsoft.quantum.glossary#qubit) [kuantum durumunun](xref:microsoft.quantum.glossary#quantum-state) grafiksel gösterimi. Daha fazla bilgi için [Bloch Küresini kullanarak Qubits ve Transformations'ı Görselleştirme'ye](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)bakın.

## <a name="callable"></a>Callable

Q# dilinde bir [işlem](xref:microsoft.quantum.glossary#operation) veya [işlev.](xref:microsoft.quantum.glossary#function) Daha fazla bilgi için [Bkz. Operasyon ve işlev türleri.](xref:microsoft.quantum.language.type-model#operation-and-function-types)

## <a name="clifford-group"></a>Clifford grubu

[Bloch küreve](xref:microsoft.quantum.glossary#bloch-sphere) [Pauli operatörlerin](xref:microsoft.quantum.glossary#pauli-operators)etkisi permütasyon octants işgal operasyonların kümesi. Bunlar [$X$](xref:microsoft.quantum.intrinsic.x), [$Y$](xref:microsoft.quantum.intrinsic.y), [$Z$](xref:microsoft.quantum.intrinsic.z), [$H$](xref:microsoft.quantum.intrinsic.h) ve [$S$](xref:microsoft.quantum.intrinsic.s)işlemlerini kapsamaktadır.

## <a name="controlled"></a>Kontrollü

Hedef operasyon için bir veya daha fazla [qubit'i](xref:microsoft.quantum.glossary#qubit) etkinleştirici olarak alan bir kuantum [işlemi.](xref:microsoft.quantum.glossary#operation) Daha fazla bilgi için [Bkz. Denetimli.](xref:microsoft.quantum.language.type-model#controlled)

## <a name="dirac-notation"></a>Dirac Gösterimi

[Kuantum durumlarının](xref:microsoft.quantum.glossary#quantum-state)temsilini kolaylaştıran sembolik bir steno , *bra-ket* gösterimi olarak da adlandırılır.  *Sütyen* kısmı bir satır vektörü temsil eder, örneğin $\bra{A} = \begin{bmatrix} A{_1} & A{_2} \end{bmatrix}$ ve *ket* kısmı bir sütun vektörü \\ \\ temsil eder, $\ket{B} = \begin{bmatrix} B{_1} B{_1} \end{bmatrix$}. Daha fazla bilgi için [Dirac Notation'a](xref:microsoft.quantum.concepts.dirac)bakın.

## <a name="eigenvalue"></a>Eigenvalue

Belirli bir dönüşümün bir [eigenvector](xref:microsoft.quantum.glossary#eigenvector) büyüklüğünü dönüşüm uygulaması ile değiştirilir hangi faktör.  Bir kare matris $M $ ve bir eigenvector $v $ göz önüne alındığında, sonra $Mv = cv $, $c $ eigenvalue ve herhangi bir argüman karmaşık bir sayı olabilir. Daha fazla bilgi için [Gelişmiş matris kavramlarına](xref:microsoft.quantum.concepts.matrix-advanced)bakın.

## <a name="eigenvector"></a>Eigenvector

Yönü belirli bir dönüşümle değişmeyen ve büyüklüğü o vektörün [özdeğerine](xref:microsoft.quantum.glossary#eigenvalue)karşılık gelen bir faktörle değiştirilen bir vektör. Bir kare matris $M $ ve bir eigenvalue $c $ göz önüne alındığında, daha sonra $Mv = cv $, $v $ matris bir eigenvector ve herhangi bir argüman karmaşık bir sayı olabilir. Daha fazla bilgi için [Gelişmiş matris kavramlarına](xref:microsoft.quantum.concepts.matrix-advanced)bakın.

## <a name="entanglement"></a>Dolaşıklık

[Kubitler](xref:microsoft.quantum.glossary#qubit)gibi kuantum parçacıkları birbirine bağlanabilir veya *birbirine* bağlanabilir. Ölçüm sonuçları, sonsuz uzakta ayrılsalar bile ilişkilidir. Dolaşıklık bir qubit [durumunu](xref:microsoft.quantum.glossary#quantum-state) [ölçmek](xref:microsoft.quantum.glossary#measurement) için gereklidir.  Daha fazla bilgi için [Gelişmiş matris kavramlarına](xref:microsoft.quantum.concepts.matrix-advanced)bakın.

## <a name="epr-pair"></a>EPR çifti

İki [qubitin](xref:microsoft.quantum.glossary#qubit)dört spesifik maksimal dolaşık [kuantum devletlerinden](xref:microsoft.quantum.glossary#quantum-state) biri. Dört{1} durum $\ket{\beta_{ij}} = (\mathbb \otimes X^iZ^j){00} (\ket +{11}\ket{2}) / \sqrt $olarak tanımlanır. EPR çifti Bell [durumu](xref:microsoft.quantum.glossary#bell-state) olarak da bilinir

## <a name="evolution"></a>Evrim

Kuantum [durumu](xref:microsoft.quantum.glossary#quantum-state) zaman içinde nasıl değişir. Daha fazla bilgi için [Matrix üstel bölüme](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials)bakın.

## <a name="function"></a>İşlev
Q# dilinde tamamen klasik (kuantum olmayan) bir alt yordam türü. Fonksiyonlar kuantum algoritmaları içinde kullanılırken, qubitler veya çağrı [işlemleri](xref:microsoft.quantum.glossary#operation)üzerinde hareket [edemezler.](xref:microsoft.quantum.glossary#qubit) Daha fazla bilgi için [Bkz. Operasyon ve işlev türleri.](xref:microsoft.quantum.language.type-model#operation-and-function-types)

## <a name="gate"></a>Kapı

Klasik mantık kapıları kavramına dayanan bir kuantum [operasyonu](xref:microsoft.quantum.glossary#operation)için eski bir terim. [Kuantum](xref:microsoft.quantum.glossary#quantum-circuit-diagram) devresi, klasik mantık devrelerinin benzer kavramına dayanan bir kapı (veya işlem ağı) ağıdır.

## <a name="global-phase"></a>Küresel faz

İki [durum](xref:microsoft.quantum.glossary#quantum-state) karmaşık bir sayının bir katı $e^{i\phi}$'a kadar aynı olduğunda, bunların genel bir aşamaya kadar farklılık gösterirolduğu söylenir. Yerel aşamaların aksine, küresel aşamalar herhangi [bir ölçüleme](xref:microsoft.quantum.glossary#measurement)ile gözlemlenemez. Daha fazla bilgi için [Qubit'e](xref:microsoft.quantum.concepts.qubit)bakın.

## <a name="hadamard"></a>Hadamard

Hadamard operasyonu (hadamard kapısı veya dönüştürmek olarak da adlandırılır) tek bir [qubit](xref:microsoft.quantum.glossary#qubit) üzerinde hareket eder{0}ve qubit{1}başlangıçta $\ket{0}$ durumunda ise $\ket $ veya $\ket $ bir bile [superposition](xref:microsoft.quantum.glossary#superposition) koyar. Q#'da bu işlem önceden tanımlanmış [`H`](xref:microsoft.quantum.intrinsic.h) işlem tarafından uygulanır.

## <a name="immutable"></a>Sabit

Değeri değiştirilemeyen bir değişken. Q# kelimesi `let` nde değişmez bir değişken anahtar kelime kullanılarak oluşturulur. *Değiştirilebilen* değişkenleri bildirmek için, bildirmek için [değiştirilebilir](xref:microsoft.quantum.glossary#immutable) anahtar `set` sözcüğü ve değeri değiştirmek için anahtar kelimeyi kullanın. 

## <a name="measurement"></a>Ölçüm

Bir gözlemsonucu veren bir [qubitin](xref:microsoft.quantum.glossary#qubit) (veya qubit kümesinin) manipülasyonu, klasik bir bit elde etmektir. Daha fazla bilgi için [Qubit'e](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit)bakın.

## <a name="mutable"></a>Değiştirilebilir

Oluşturulduktan sonra değeri değiştirilebilecek bir değişken. Q#'da değişken bir değişken `mutable` anahtar kelime kullanılarak `set` bildirilir ve anahtar kelime kullanılarak değiştirilir. `let` Anahtar kelimeyle oluşturulan değişkenler [değişmez](xref:microsoft.quantum.glossary#immutable) ve değerleri değiştirilemez.

## <a name="namespace"></a>Ad Alanı

İlgili adlar (yani, [işlemler,](xref:microsoft.quantum.glossary#operation) [işlevler](xref:microsoft.quantum.glossary#function)ve kullanıcı [tanımlı türler)](xref:microsoft.quantum.glossary#user-defined-type)koleksiyonu için bir etiket. Örneğin, ad alanı [Microsoft.Quantum.Preparation,](xref:microsoft.quantum.preparation) standart kitaplıkta tanımlanan ve ilk durumların hazırlanmasına yardımcı olan tüm simgeleri etiketler.

## <a name="operation"></a>İşlem

Q#'daki kuantum infazının temel birimi. Kabaca C, C++ veya Python'daki bir işleve veya C# veya Java'daki statik bir yönteme eşdeğerdir. Daha fazla bilgi için [Bkz. Operasyon ve işlev türleri.](xref:microsoft.quantum.language.type-model#operation-and-function-types)

## <a name="operator-application"></a>Operatör uygulaması

Kuantum operasyonu yapıyor. Bu genellikle geçerli kuantum durum vektörü için birüniter matris uygular.

## <a name="oracle"></a>Oracle

Çalışma zamanında kuantum algoritmasına veriye bağlı bilgi sağlayan bir alt yordam. Genellikle, amaç, süperpozisyonda olan girdilere karşılık gelen çıktıların [üst pozisyonunu](xref:microsoft.quantum.glossary#superposition) sağlamaktır. Daha fazla bilgi için [Oracles'a](xref:microsoft.quantum.libraries.data-structures#oracles)bakın.

## <a name="partial-application"></a>Kısmi uygulama

Gerekli tüm girdiler olmadan bir [işlevi](xref:microsoft.quantum.glossary#function) veya [işlemi](xref:microsoft.quantum.glossary#operation) çağırma. Bu, gelecekteki bir uygulama sırasında sağlanacak eksik parametrelerin (alt puanla gösterilir) yalnızca ihtiyaç duyduğu yeni bir [çağrılabilir](xref:microsoft.quantum.glossary#callable) döndürür. Örneğin, işlevi `MyFunc(x : int, y : int) : int {return x + y;}` göz önüne alındığında kısmen yeni bir `let NewFunc = MyFunc(_, 3)`işlev için uygulayabilirsiniz. Daha sonra *5*değerini döndüren eksik parametre `NewFunc(2)` ile daha sonra yeni işlevi arayabilirsiniz.  Daha fazla bilgi için [Kısmi uygulamaya](xref:microsoft.quantum.language.expressions#partial-application)bakın.

## <a name="pauli-operators"></a>Pauli operatörleri

Üç 2 x 2 üniter matrisler olarak `X`bilinen `Y` `Z` bir dizi , ve kuantum işlemleri. Kimlik matrisi, $I$, genellikle kümede de yer alıyor.  $I = \begin{bmatrix} \\ \\ 1 & 0 0 & 1 \end{bmatrix}$, $X \\ \\ = \begin{bmatrix} 0 & 1 1 & 0 \end{bmatrix}$, $Y = \begin{bmatrix} 0 & -i \\ \\ & 0 \end{bmatrix}$, $Z = \begin{bmatrix} 1 & 0 0 \\ \\ & -1 \end{bmatrix}$.   Daha fazla bilgi için [Tek qubit işlemlerine](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)bakın.

## <a name="quantum-circuit-diagram"></a>Kuantum devre şeması

Örnek devre diyagramı ![gibi basit kuantum programları için [işlem](xref:microsoft.quantum.glossary#operation) sırasını (veya](~/media/qpe.png) [kapıları)](xref:microsoft.quantum.glossary#gate)grafikolarak temsil eden bir yöntem. Daha fazla bilgi için [Kuantum devrelerine](xref:microsoft.quantum.concepts.circuits)bakın.

## <a name="quantum-libraries"></a>Kuantum kütüphaneleri

Q# programları oluşturmak için [işlem](xref:microsoft.quantum.glossary#operation)koleksiyonları, [işlevler](xref:microsoft.quantum.glossary#function) ve [kullanıcı tanımlı türleri.](xref:microsoft.quantum.glossary#user-defined-type) [Standart kitaplık](xref:microsoft.quantum.libraries.standard.intro) varsayılan olarak yüklenir. Diğer kütüphaneler Kimya [kütüphanesi,](xref:microsoft.quantum.chemistry.concepts.intro) [Sayısal kitaplığı](xref:microsoft.quantum.numerics.intro) ve [Makine öğrenme kütüphanesidir.](xref:microsoft.quantum.machine-learning.concepts.intro)

## <a name="quantum-state"></a>Kuantum durumu

Ölçü [olasılıklarının](xref:microsoft.quantum.glossary#measurement) çıkarılabildiği izole edilmiş bir kuantum sisteminin kesin durumu. Kuantum hesaplamasında, kuantum simülatörü bu bilgiyi qubitlerin operasyonlara nasıl tepki verebildiğini simüle etmek için kullanır. Daha fazla bilgi için [Qubit'e](xref:microsoft.quantum.concepts.qubit)bakın.

## <a name="qubit"></a>Qubit

Kuantum bilgisinin temel bir birimi, klasik bilgi işlemde *biraza* benzer. Daha fazla bilgi için [Qubit'e](xref:microsoft.quantum.concepts.qubit)bakın.

## <a name="repeat-until-success"></a>Tekrar-kadar-başarı

Probabilistically başarılı bir kuantum algoritması. Başarısız olunması üzerine, yordam başarılı olana (veya bir sınıra ulaşılına) kadar yeniden dener. Daha fazla bilgi için bkz: [Başarıya Kadar Yinele (RUS)](xref:microsoft.quantum.techniques.qubits#measurements)

## <a name="standard-libraries"></a>Standart kitaplıklar

Yükleme sırasında Q# derleyicisi ile birlikte yüklenen [işlemler,](xref:microsoft.quantum.glossary#operation) [işlevler](xref:microsoft.quantum.glossary#function) ve [kullanıcı tanımlı türleri.](xref:microsoft.quantum.glossary#user-defined-type) Standart kitaplık uygulaması hedef makinelere göre agnostiktir. Daha fazla bilgi için [Standart kitaplıklar'a](xref:microsoft.quantum.libraries.standard.intro)bakın.

## <a name="superposition"></a>Süperpozisyon

Kuantum hesaplamasında bir [qubit'in](xref:microsoft.quantum.glossary#qubit) [ölçülür.](xref:microsoft.quantum.glossary#measurement)  Daha fazla bilgi için [kuantum bilgi işlem nedir](xref:microsoft.quantum.overview.what)bakın.

## <a name="target-machine"></a>Hedef makine

Donanım veya simülasyon doğru soyut bir kuantum programı düşürür bir derleme hedefi. Bu genellikle kapı değiştirme, hata düzeltme, geometrik düzen ve diğerleri için kodlama dahil olmak üzere birçok amaç için yeniden yazma içerir. Daha fazla bilgi için [Quantum simülatörleri ve ana bilgisayar uygulamalarına](xref:microsoft.quantum.machines)bakın.

## <a name="teleportation"></a>Işınlanma

Bir [qubit'in](xref:microsoft.quantum.glossary#qubit) bir yerden diğerine fiziksel olarak qubit'i hareket ettirilmeden, [dolaşıklık](xref:microsoft.quantum.glossary#entanglement) ve ölçüm kullanarak veri veya [kuantum durumunu](xref:microsoft.quantum.glossary#quantum-state)yeniden üretmek için kullanılan [bir](xref:microsoft.quantum.glossary#measurement)yöntem.  Daha fazla bilgi için [Kuantum devreleri](xref:microsoft.quantum.concepts.circuits) ve [hepsini bir araya getirin.](xref:microsoft.quantum.techniques.puttingittogether)

## <a name="tuple"></a>Tuple

Tek bir değer olarak hareket eden virgülle ayrılmış değerler topluluğu. Bir tuple *türü* içerdiği değer türleri ile tanımlanır. Q#'da, tuples [değişmezdir](xref:microsoft.quantum.glossary#immutable) ve iç içe olabilir, diziler içerebilir veya bir dizide kullanılabilir. Daha fazla bilgi için [Tuple türlerine](xref:microsoft.quantum.language.type-model#tuple-types)bakın.

## <a name="unitary-operator"></a>Üniter işleç

Tersi [adjoint'ına](xref:microsoft.quantum.glossary#adjoint)eşit olan bir işleç , yani, $UU^{\hançer} = \id$.

## <a name="user-defined-type"></a>Kullanıcı tanımlı tür

Tek bir birim olarak adlandırılabilecek yerleşik veya daha önce tanımlanmış türler topluluğu. Daha fazla bilgi için [Bkz. Kullanıcı tanımlı türleri.](xref:microsoft.quantum.language.type-model#user-defined-types)