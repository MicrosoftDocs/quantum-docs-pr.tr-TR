---
title: Hisse bilgi işlem ortamında qubit
description: Hisse bilgi işlem ortamında temel bilgi birimi olan qubits hakkında bilgi edinin.
author: QuantumWriter
uid: microsoft.quantum.concepts.qubit
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 770b739d95f5c1512234f6f7d2ca4544f1d80e64
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907537"
---
# <a name="the-qubit"></a>Qubit

Aynı bitler, klasik bilgi işlem 'daki temel bir nesne olduğu gibi, [*qubits*](https://en.wikipedia.org/wiki/Qubit) (hisse bitleri) ise hisse bilgi işlem ortamında temel bilgilerin temel nesnesidir.  Bu yazışmaları anlamak için en basit örneğe göz atalım: tek bir qubit.

## <a name="representing-a-qubit"></a>Qubit 'i temsil etme

Bit veya ikili basamak, $0 $ ya da $1 $ değerine sahip olabilir, bir qubit, bu değerden ya da $0 $ ve $1 $ ' in hisse bir değeri olabilir.

Tek bir qubit 'in durumu, birim norm 'in iki boyutlu bir sütun vektörü tarafından açıklanabilir, diğer bir deyişle, girişlerinin büyüklüğü $1 $ olarak toplamı olmalıdır. Hisse durumu vektörü olarak adlandırılan bu vektör, tek bir bit, bir ikili değişkenin durumunu anlatmak için gereken tüm bilgileri elinde tutan tek bir bit olmak üzere, bir-qubit hisse sistemini anlatmak için gereken tüm bilgileri tutar.

Norm $1 $ ile gerçek veya karmaşık sayıların herhangi bir iki boyutlu sütun vektörü, bir qubit tarafından tutulan olası bir hisse TI durumunu temsil eder. Bu nedenle $ \begin{bmatrix} \Alpha \\\\ \beta \end{bmatrix} $, $ \Alpha $ ve $ \beta $, $ | \Alpha | ^ 2 + | \beta | ^ 2 = $1 olarak bulunan karmaşık sayılardır bir qubit durumu temsil eder. Qubits 'i temsil eden geçerli hisse alma durumu vektörlerine örnek olarak şunlar verilebilir

$ $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\ \frac{1}{\sqrt{2}} \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\ \frac{-1}{\sqrt{2}} \end{bmatrix}, \Text{and} \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\ \frac{i}{\sqrt{2}} \end{bmatrix}. $ $

Hisse durum vektörleri $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ ve $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ özel bir rol alın. Bu iki vektör, qubit durumunu açıklayan vektör alanı için bir temel oluşturur. Bu, tüm hisse devlet vektörünün bu temel vektörin toplamı olarak yazılabileceği anlamına gelir. Özellikle, vektör $ \begin{bmatrix} x \\\\ y \end{bmatrix} $, $x \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} + y \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ olarak yazılabilir. Bu vektörin herhangi bir dönüşü qubit için tam olarak geçerli olsa da, bunu *Hesaplama temelinde*çağırarak bunu tercih ettik.

Bu iki hisse sağımız, klasik bitin iki durumuna karşılık gelmelidir, yani $0 $ ve $1 $. Standart kural şunları seçdir

$ $0 \ EQUIV \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qdörtlü 1 \equıv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}, $ $

zıt seçim eşit olarak da yapılabilir. Bu nedenle, sınırsız sayıda olası tek qubit hisse kaybı vektörü dışında, yalnızca iki klasik bit durumuna karşılık gelir; diğer tüm hisse ama durumları değildir.

## <a name="measuring-a-qubit"></a>Qubit ölçme

Bir qubit 'i nasıl temsil ettiğini öğrendiğimiz için, [*ölçüm*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics)kavramını tartışarak bu durumların neleri temsil ettiğini öğrenmek için bazı ıntutik kazanıyoruz. Bir ölçü, bir qubit 'de "bakıma" gibi, her iki klasik durumdan biri olan $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ veya $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $. Hisse durumu vektörü $ \begin{bmatrix} \Alpha \\\\ \beta \end{bmatrix} $ tarafından verilen bir qubit ölçüldüğünde, $0 $ sonucunu olasılık $ | \Alpha | ^ 2 $ ve sonuç $1 $ ile olasılık $ | \beta | ^ 2 $ ile elde ediyoruz. Sonuç $0 $, qubit 'in yeni durumu $ \begin{bmatrix} 1 \\\\ 0 \ End{bmatrix} $; şeklindedir. Sonuç $1 $ durumu $ \begin{bmatrix} 0 \\\\ 1 \ End{bmatrix} $ şeklindedir. Bu olasılıkların, $ | \Alpha | ^ 2 + | \beta | ^ 2 = $1 normalleştirme koşulu nedeniyle $1 $ ' e kadar olduğunu unutmayın.

Ölçümün özellikleri, hisse maeyalet vektörünün genel işaretinin ilgisiz olduğunu da ifade demektir. Bir vektörü negatifi, $ \Alpha \sağtarrow-\Alpha $ ve $ \beta \ tam Tarrow-\beta $ ile eşdeğerdir. $0 $ ve $1 $ ölçmesinin olasılığı koşulların büyüklüğüne bağlı olduğundan, bu tür bir işaret eklemek, olasılıkların koşullarını değiştirmez. Bu tür aşamalar genellikle [ *küresel aşamalar*' '``](https://en.wikipedia.org/wiki/Phase_factor) olarak adlandırılır ve daha genel olarak yalnızca $ \pm $1 yerine ^ {ı \phi} $ $e biçimde olabilir.

Ölçümün son önemli özelliği, tüm hisse maeyalet vektörlerine zarar vermeyedir. Klasik durum $0 $ ' e karşılık gelen $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ durumunda bir qubit ile başladığımızda, bu durumun ölçülmesi her zaman $0 $ sonucunu verir ve hisse durumu değişmeden bırakır. Bu anlamda, yalnızca klasik bitlerin (örneğin, $ \begin{bmatrix}1 \\\\ 0 \end{bmatrix} $ veya $ \begin{bmatrix}0 \\\\ 1 \end{bmatrix} $) sahip olduğu gibi, ölçüm sisteme zarar vermez. Bu, klasik verileri çoğaltabilmemiz ve bir hisse bir bilgisayar üzerinde yalnızca klasik bir bilgisayarda olabileceği gibi işleyebilmemiz anlamına gelir. Ancak, bilgileri bir kerede her iki durumda da depolamak için, uygun şekilde ne kadar iyi bir şekilde veri depolama alanı ve diğer Robs hisse [bilgisayarları da sayısının fark gözetmeden](https://en.wikipedia.org/wiki/No-cloning_theorem)

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a>Bloch Sphere kullanarak qubit ve dönüşümleri görselleştirme

Qubits, [*Bloch Sphere*](https://en.wikipedia.org/wiki/Bloch_sphere) temsili kullanılarak $3 $ D içinde de görünebilir.  Bloch Sphere, tek qubit hisse durumunu (iki boyutlu bir karmaşık vektör) üç boyutlu gerçek değerli bir vektör olarak açıklamanın bir yolunu sağlar.  Bu, tek qubit durumları görselleştirmemize ve bu nedenle çok qubit durumlarını anlamak için çok değerli olabilecek bir düşüngeli hale getirmemizi sağladığından önemlidir.  Bloch Sphere şu şekilde görselleştirilebilir:

<!--- ![](.\media\bloch.svg){ width=50% } --->
![Bloch Sphere](~/media/concepts_bloch.png)

Bu diyagramdaki oklar, hisse devlet vektörünün işaret ettiği yönü gösterir ve okun her dönüştürmesi, Kardinal eksenlerden biri ile ilgili bir döndürme olarak düşünülebilir.
Bir hisse atısyonın sırası olarak bir hisse atımı hesaplamayı düşünürken, algoritmaları tasarlamak ve anlatmak için bu ıntuun kullanılması zor bir araçtır. Q # bu tür döndürmeler hakkında bir dil sağlayarak bu sorunu konuma almayı azaltır.

## <a name="single-qubit-operations"></a>Tek qubit Işlemler

Hisse bilgisayarları, hisse devlet vektörünün herhangi bir dönüşüyle öykünebileceği evrensel bir hisse kapısı kümesi uygulayarak verileri işler.
Bu evrenlik kavramı, giriş bitlerinin her dönüştürmesi sonlu uzunlukta bir bağlantı kullanılarak gerçekleştirilürse, bir kapı kümesi 'nin evrensel olarak kabul edildiği geleneksel (ör. klasik) bilgi işlem için evrenlik kavramına yol açabilir.
Hisse bilgi işlem ortamında, bir qubit üzerinde gerçekleştirmesine izin verilen geçerli dönüşümler, Unitary dönüştürmeleri ve ölçümdür.
*Majoint işlemi* ya da karmaşık eşleniği devrik, hisse kullanımı için önemli öneme sahiptir çünkü hisse dönüştürmelerinin tersine çevirmek için gereklidir.
Q # bu işlemi, programcı 'nın birçok durumda bir yandan kodu kabul etmek zorunda kalmasından tasarruf eden el ile geçit dizilerini otomatik olarak derlemeye yönelik yöntemler sunarak yansıtır. Buna bir örnek aşağıda verilmiştir:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Adj { // Auto-generate the adjoint of the operation
    H(qubit);
}
```

Bu, önemsiz bir <xref:microsoft.quantum.intrinsic.h> örnek olsa da, daha karmaşık qubit işlemleri için bunun çok değerli hale geldiğini görebilirsiniz.
Daha fazla bilgi için bkz. [işlemler ve işlevler](xref:microsoft.quantum.techniques.opsandfunctions).

Klasik bir bilgisayarda bir bit ile bir bit arasında eşleme yapan yalnızca dört işlev vardır. Buna karşılık, bir hisse bilgisayar üzerinde tek bir qubit üzerinde sonsuz sayıda Unitary dönüştürmesi vardır. Bu [*nedenle, kapıların adı verilen*](https://en.wikipedia.org/wiki/Quantum_logic_gate)sınırlı bir temel hisse işlem kümesi, hisse kullanımı için izin verilen sonsuz dizi dönüştürmelerinin tam olarak çoğaltılmasını sağlayabilir. Bu, klasik bilgi işlemin aksine, bir hisse bilgisayarın her olası hisse programını sınırlı sayıda kapı kullanarak tam olarak uygulaması olanaksız hale gelir. Bu nedenle, hisse bilgisayarları, klasik bilgisayarların aynı anlamda evrensel olamaz. Sonuç olarak, bir ağ geçidi kümesinin hisse kullanımı için *evrensel* olduğunu söylediğimiz zaman, klasik bilgi işlem ile karşılaştığımız için biraz daha zayıf bir şeydir.
Üniverbir bilgisayar için, bir hisse bilgisayarının yalnızca sonlu bir uzunluk kapısı sırası kullanılarak sınırlı bir hata içindeki her Unitary matrisini *yaklaşık olarak yaklaşık olarak yaklaşık olarak yaklaşık olarak yaklaşık* olarak
Diğer bir deyişle, herhangi bir Unitary dönüştürmesi bu kümeden bir kapı ürünü olarak yaklaşık olarak yazılmışsa, bir ağ geçidi kümesi evrensel bir kapı kümesidir. Önceden tanımlanmış herhangi bir hata için, ağ geçidi kümesinden $G _{1}, G_{2}, \lnoktalar, G_N $ gibi mevcut kapıları var

$ $ G_N G_ {N-1} \cnoktalar G_2 G_1 \yaklaşık U. $ $

Matris çarpma kuralı, bu dizideki ilk kapı işleminin sağdan sola çarpılacağı, $G _N $, gerçekten de hisse senedi durumu vektörüne uygulanan en son bir şeydir. Daha da benzer bir şekilde, bu tür bir kapı kümesi, her hata toleransı $ \epsilon > 0 $ varsa, $G _N \lnoktalar G_1 $ ve $U $ arasındaki uzaklığın en fazla $ \epsilon $ olduğunu belirten $G _1, \lnoktalarla G_N $. İdeal olarak $ \epsilon $ ' in bu uzaklığına ulaşmak için gereken $N $ değeri, $1/\ Epsilon $ ile Poly-logaritmayı büyük ölçüde ölçeklendirmelidir.

Bu tür bir Evrensel kapı kümesi uygulamada nasıl görünür?  Tek-qubit kapıları için en basit bu tür Evrensel kapı kümesi yalnızca iki ağ geçidiyle oluşur: Hadamard Gate $H $ ve so-çağrılan $T $-Gate ($ \ Pi/8 $ kapısı olarak da bilinir):

$ $ H = \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 &-1 \end{bmatrix}, \qquad T = \begin{bmatrix} 1 & 0 \\\\ 0 & e ^ {ı \ Pi/4} \end{bmatrix}.
$$

Ancak, hisse matı hata düzeltmesiyle ilgili pratik nedenlerden dolayı daha büyük bir kapı kümesini düşünmek daha kolay olabilir, yani $H $ ve $T $ kullanılarak oluşturulabilir.
Hisse geçitlerini iki kategoride sınıflandırabiliriz: Clifford Gates ve $T $-Gate.
Bu alt bölüm, çok sayıda hisse hata düzeltme şeması için yararlıdır, çünkü bu nedenle, hata tolerantly uygulamak için çok az sayıda kaynak gerektirir; Bu, Clienfford Gates gibi işlem ve qubit olmayan hata toleransı gerektiren oldukça maliyetlidir. [Q # içinde varsayılan olarak dahil edilen](xref:microsoft.quantum.libraries.standard.prelude)tek qubit Clienfford kapıları standart kümesi, şunları içerir

$ $ H = \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 &-1 \end{bmatrix}, \qdörtlü S = \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix} = T ^ 2, \qdörtlü X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} = HT ^ 4H, $ $

$ $ Y = \begin{bmatrix} 0 &-i \\\\ ı & 0 \end{bmatrix} = T ^ 2HT ^ 4 HT ^ 6, \qquad Z = \begin{bmatrix}1 & 0\\\\ 0 &-1 \end{bmatrix} = T ^ 4.
$$

Burada $X $, $Y $ ve $Z $ işlemleri özellikle sık kullanılır ve Creator Wolfgang Pauli sonrasında [*Pauli işleçleri*](https://en.wikipedia.org/wiki/Pauli_matrices) olarak adlandırılır.
Clienfford Kapısı ($T $-Gate) ile birlikte, bu işlemler, tek bir qubit üzerinde her bir Unitary dönüştürmesi üzerinde bulunabilir.

Bu işlemler hakkında daha fazla bilgi için, Bloch Sphere temsilleri ve Q # uygulamaları için bkz. [Iç işlemler ve işlevler](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions).

Unitary dönüştürmelerinin bu temel öğelerden nasıl derlenebilir bir örnek olarak, yukarıdaki Bloch son 'da bulunan üç dönüşüm, $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \mapsto HZH \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $.

Önceki, yığının mantıksal düzeyindeki işlemleri tanımlamak için en popüler temel noktaları oluştursa da (mantıksal düzeyi hisse algoritması düzeyi olarak düşünün), algoritmik 'de daha az temel işlem düşünmek için kullanışlıdır bir işlev açıklaması düzeyine yaklaşarak, örneğin, işlem düzeyi. Neyse ki, Q # Ayrıca üst düzey birimlere uygulama için kullanılabilir yöntemlere sahiptir. Bu, üst düzey algoritmaların, her şeyin Clienfford ve $T $-Gates ' e kadar açık bir şekilde çıkarılması gerekmeden uygulanmasına olanak tanır.

En basit bu ilkel değer tek qubit Dönüştür. Üç adet tek qubit döndürmeler genellikle kabul edilir: $R _x $, $R _y $ ve $R _Z $. Örneğin, $R _x (\teta) $ döndürme eylemini görselleştirmek için, örneğin, sağ Thumb 'ı Bloch Sphere 'in $x $ ekseninin yönü boyunca gösterme ve vektörü $ \ teta/2 $ radyanlarının bir açısı ile döndürme. Bu kafa karıştırıcı $2 $, şişenin şişine bağlı olarak, k180 ^ \circ $ olduğunu bulmadan, ancak gerçekten de geometrik olarak $90 ^ \circ Karşılık gelen Unitary matrisleri şunlardır:

\begin{align *} & R_z (\teta) = e ^ {-i\teta z/2} = \begin{bmatrix} e ^ {-i \ teta/2} & 0\\\\ 0 & e ^ {ı \ teta/2} \end{bmatrix}, \\\\ & R_x (\teta) = e ^ {-i\teta x/2} = HR_z (\teta) H = \begin{bmatrix} \cos (\ teta/2) &-ı\sin (\ teta/2)\\\\-i\sin (\ teta/2) & \cos (\ teta/2) \end{bmatrix}, \\\\ & R_y (\teta) = e ^ {-I\teta y/2} = SHR_z (\teta) HS ^ \hanger = \begin{bmatrix} \cos (\ teta/2) &-\sin (\ teta/2)\\\\ \sin (\ teta/2) & \cos (\ teta/2) \end{bmatrix}. \end{align*}

Üç boyutta de rastgele bir döndürme gerçekleştirmek için üç döndürmeler birlikte birleştirilebileceği gibi, blok Sphere gösteriminden herhangi bir Unitary matrisinin üç döndürmeler sırası olarak yazılabileceğini de görebilirsiniz. Özellikle, her unitöğeli matris için $U $ \Alpha, \beta, \gama, \delta $ gibi $U = e ^ {i\alpha} R_x (\beta) R_z (\gama) R_x (\delta) $ vardır. Bu nedenle, $R _z (\teta) $ ve $H $, farklı bir küme olmamasına rağmen, $ \teta $ herhangi bir değer götürebileceğinden, bir Evrensel kapı kümesi de oluşturur. Bu nedenle ve hisse uygun bir şekilde, bu tür sürekli kapıların, bu nedenle hisse için, özellikle de hisse algoritması tasarım düzeyinde, bu tür sürekli kapılarda önemli olması için Hataya dayanıklı donanım uygulamalarına ulaşmak için, sonunda bu döndürmeleri yakın olan ayrık geçit dizileri olarak derlenir.
