---
Başlık: hisse bilgi işlem Için qubit bilgi: hisse kullanımı hakkında bilgi edinin.
Yazar: miktar Tumwriter uid: Microsoft. hisse. Concepts. qubit MS. Author: v-bendörtms. Date: 12/11/2017 MS. Topic: Makale No-loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---
# <a name="the-qubit"></a>Qubit

Aynı bitler, klasik bilgi işlem 'daki temel bir nesne olduğu gibi, [*qubits*](https://en.wikipedia.org/wiki/Qubit) (hisse bitleri) ise hisse bilgi işlem ortamında temel bilgilerin temel nesnesidir.  Bu yazışmaları anlamak için en basit örneğe göz atalım: tek bir qubit.

## <a name="representing-a-qubit"></a>Qubit 'i temsil etme

Bit veya ikili basamak, 0 veya 1 değerinde bir değere sahip olabilir; $ $ $ $ bir qubit, bu değerden ya da $ 0 $ ve 1 ' in hisse bir değeri olabilir $ $ .

Tek bir qubit 'in durumu, birim norm 'in iki boyutlu bir sütun vektörü tarafından açıklanabilir, diğer bir deyişle, girişlerinin büyüklüğü 1 ' e kadar olmalıdır $ $ . Hisse durumu vektörü olarak adlandırılan bu vektör, tek bir bit, bir ikili değişkenin durumunu anlatmak için gereken tüm bilgileri elinde tutan tek bir bit olmak üzere, bir-qubit hisse sistemini anlatmak için gereken tüm bilgileri tutar.

Norm 1 olan gerçek veya karmaşık sayıların iki boyutlu bir sütun vektörü, $ $ bir qubit tarafından tutulan olası bir hisse TI durumunu temsil eder. Bu nedenle, $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ bir qubit durumunu temsil eder $ \alpha $ ve $ \beta $ $ | \alpha | ^ 2 + | \beta | ^ 2 = 1 $ ' i karşılayan karmaşık sayılardır.   Qubits 'i temsil eden geçerli hisse alma durumu vektörlerine örnek olarak şunlar verilebilir

$$\begin{bmatrix}1 \\\\ 0 \end{bmatrix} , \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} , \begin{bmatrix} \frac { 1 } { \sqrt { 2 } } \\\\ \frac { 1 } { \sqrt { 2 } } \end{bmatrix} , \begin{bmatrix} \frac { 1 } { \sqrt { 2 } } \\\\ \frac { -1 2 } { \sqrt { } } \end{bmatrix} \text { ve } \begin{bmatrix} \frac { 1 } { \sqrt { 2 } } \\\\ \frac { ı } { \sqrt { 2 } } \end{bmatrix} .      $$

Hisse durum vektörleri $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ ve $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ özel bir rol alır. Bu iki vektör, qubit durumunu açıklayan vektör alanı için bir temel oluşturur. Bu, tüm hisse devlet vektörünün bu temel vektörin toplamı olarak yazılabileceği anlamına gelir. Özellikle vektör $ \begin{bmatrix} x y, \\\\ \end{bmatrix} $ $ x \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} + y \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ olarak yazılabilir. Bu vektörin herhangi bir dönüşü qubit için tam olarak geçerli olsa da, bunu *Hesaplama temelinde*çağırarak bunu tercih ettik.

Bu iki hisse bitini, klasik bitin iki durumuna ( $ 0 ve 1) karşılık gelecek şekilde sunuyoruz $ $ $ . Standart kural şunları seçdir

$$0 \equiv \begin{bmatrix} 1 \\\\  0 \end{bmatrix} , \qquad 1 \equiv \begin{bmatrix} 0 \\\\  1 \end{bmatrix} ,$$

zıt seçim eşit olarak da yapılabilir. Bu nedenle, sınırsız sayıda olası tek qubit hisse kaybı vektörü dışında, yalnızca iki klasik bit durumuna karşılık gelir; diğer tüm hisse ama durumları değildir.

## <a name="measuring-a-qubit"></a>Qubit ölçme

Bir qubit 'i nasıl temsil ettiğini öğrendiğimiz için, [*ölçüm*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics)kavramını tartışarak bu durumların neleri temsil ettiğini öğrenmek için bazı ıntutik kazanıyoruz. Bir ölçü, bir qubit 'de "bakıma" göz atan fikrine karşılık gelir ve bu, hisse ışından iki klasik durumdan biri olan $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ veya $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ ' i hemen daraltır. Hisse durumu vektörü tarafından verilen bir qubit $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ ölçüldüğünde, sonucu $ 0, $ olasılık $ | \alpha | ^ 2 $ ve sonuç $ 1, $ olasılık $ | \beta | ^ 2 $ ile elde ediyoruz.   Sonuç $ 0 $ ' da, qubit 'in yeni durumu $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ ; Sonuç 1 ' de $ $ durum $ \begin{bmatrix} 0 1 ' \\\\ dir \end{bmatrix} $ . Bu olasılıkların $ $ , $ | \alpha | ^ 2 + | \beta | ^ 2 = 1 $ normalleştirme koşulu nedeniyle 1 ' e kadar toplam olduğunu unutmayın.

Ölçümün özellikleri, hisse maeyalet vektörünün genel işaretinin ilgisiz olduğunu da ifade demektir. Bir vektörü $ \alpha \right \alpha $ negatifi, ok ve ok-ile eşdeğerdir $ \beta \right \beta $ . $0 $ ve $ 1 $ ölçmesinin olasılığı koşulların büyüklüğüne bağlı olduğundan, bu tür işaretleri eklemek, olasılıkların koşullarını değiştirmez. Bu tür aşamalar genellikle [ `` *genel aşamalar*' '](https://en.wikipedia.org/wiki/Phase_factor) olarak adlandırılır ve daha fazla genel olarak $ { \phi } $ yalnızca $ \pm 1 yerine $ e-t biçiminde olabilir.

Ölçümün son önemli özelliği, tüm hisse maeyalet vektörlerine zarar vermeyedir. $ \begin{bmatrix} Klasik durum 0 ' a karşılık gelen 1 0 ' da bir qubit ile başladığımızda \\\\ \end{bmatrix} $ $ $ , bu durumun ölçülmesi her zaman 0 sonucunu verir $ $ ve hisse durumu değişmeden bırakır. Bu anlamda, yalnızca klasik bitleri ( $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ veya 0 1 olan qubit $ \begin{bmatrix} \\\\ ) varsa \end{bmatrix} $ ölçüm sisteme zarar vermez. Bu, klasik verileri çoğaltabilmemiz ve bir hisse bir bilgisayar üzerinde yalnızca klasik bir bilgisayarda olabileceği gibi işleyebilmemiz anlamına gelir. Ancak, bilgileri bir kerede her iki durumda da depolamak için, uygun şekilde ne kadar iyi bir şekilde veri depolama alanı ve diğer Robs hisse [bilgisayarları da sayısının fark gözetmeden](https://en.wikipedia.org/wiki/No-cloning_theorem)

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a>Bloch Sphere kullanarak qubit ve dönüşümleri görselleştirme

Qubits $ $ , [*Bloch Sphere*](https://en.wikipedia.org/wiki/Bloch_sphere) temsili kullanılarak 3 D içinde de görünebilir.  Bloch Sphere, tek qubit hisse durumunu (iki boyutlu bir karmaşık vektör) üç boyutlu gerçek değerli bir vektör olarak açıklamanın bir yolunu sağlar.  Bu, tek qubit durumları görselleştirmemize ve bu nedenle çok qubit durumlarını anlamak için çok değerli olabilecek bir düşüngeli hale getirmemizi sağladığından önemlidir.  Bloch Sphere şu şekilde görselleştirilebilir:

<!--- ![](.\media\bloch.svg) { genişliği = %50} --->
![Bloch küre](~/media/concepts_bloch.png)

Bu diyagramdaki oklar, hisse devlet vektörünün işaret ettiği yönü gösterir ve okun her dönüştürmesi, Kardinal eksenlerden biri ile ilgili bir döndürme olarak düşünülebilir.
Bir hisse atısyonın sırası olarak bir hisse atımı hesaplamayı düşünürken, algoritmaları tasarlamak ve anlatmak için bu ıntuun kullanılması zor bir araçtır. Q# Bu sorunu, bu tür döndürmeler hakkında bir dil sunarak konuma almayı azaltır.

## <a name="single-qubit-operations"></a>Tek qubit Işlemler

Hisse bilgisayarları, hisse devlet vektörünün herhangi bir dönüşüyle öykünebileceği evrensel bir hisse kapısı kümesi uygulayarak verileri işler.
Bu evrenlik kavramı, giriş bitlerinin her dönüştürmesi sonlu uzunlukta bir bağlantı kullanılarak gerçekleştirilürse, bir kapı kümesi 'nin evrensel olarak kabul edildiği geleneksel (ör. klasik) bilgi işlem için evrenlik kavramına yol açabilir.
Hisse bilgi işlem ortamında, bir qubit üzerinde gerçekleştirmesine izin verilen geçerli dönüşümler, Unitary dönüştürmeleri ve ölçümdür.
*Majoint işlemi* ya da karmaşık eşleniği devrik, hisse kullanımı için önemli öneme sahiptir çünkü hisse dönüştürmelerinin tersine çevirmek için gereklidir.
Q# Bu işlemi, programcı 'nın birçok durumda bir yandan kod eklemek zorunda kalmasından tasarruf eden el ile geçit dizilerini otomatik olarak derlemeye yönelik yöntemler sunarak yansıtır. Buna bir örnek aşağıda verilmiştir:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Adj { // Auto-generate the adjoint of the operation
    H(qubit);
}
```

Bu, önemsiz bir örnek olsa da ( < XREF: Microsoft. hisse. Intrinsic. h > işlemi Self-adjoint olarak), bunun daha karmaşık qubit işlemleri için nasıl değerli olduğunu görebilirsiniz.
Daha fazla bilgi için bkz. [işlemler ve işlevler](xref:microsoft.quantum.guide.operationsfunctions).

Klasik bir bilgisayarda bir bit ile bir bit arasında eşleme yapan yalnızca dört işlev vardır. Buna karşılık, bir hisse bilgisayar üzerinde tek bir qubit üzerinde sonsuz sayıda Unitary dönüştürmesi vardır. Bu [*nedenle, kapıların adı verilen*](https://en.wikipedia.org/wiki/Quantum_logic_gate)sınırlı bir temel hisse işlem kümesi, hisse kullanımı için izin verilen sonsuz dizi dönüştürmelerinin tam olarak çoğaltılmasını sağlayabilir. Bu, klasik bilgi işlemin aksine, bir hisse bilgisayarın her olası hisse programını sınırlı sayıda kapı kullanarak tam olarak uygulaması olanaksız hale gelir. Bu nedenle, hisse bilgisayarları, klasik bilgisayarların aynı anlamda evrensel olamaz. Sonuç olarak, bir ağ geçidi kümesinin hisse kullanımı için *evrensel* olduğunu söylediğimiz zaman, klasik bilgi işlem ile karşılaştığımız için biraz daha zayıf bir şeydir.
Üniverbir bilgisayar için, bir hisse bilgisayarının yalnızca sonlu bir uzunluk kapısı sırası kullanılarak sınırlı bir hata içindeki her Unitary matrisini *yaklaşık olarak yaklaşık olarak yaklaşık olarak yaklaşık olarak yaklaşık* olarak
Diğer bir deyişle, herhangi bir Unitary dönüştürmesi bu kümeden bir kapı ürünü olarak yaklaşık olarak yazılmışsa, bir ağ geçidi kümesi evrensel bir kapı kümesidir. Herhangi bir önceden tanımlanmış hata varsa, $ { } ağ geçidi kümesinden G_ 1, g_ { 2 } , \lnoktalarla G_N var $ olan kapıları

$$
G_N G_ { N-1 } \cdots G_2 G_1 \yaklaşık U. $$

Matris çarpma kuralı, bu dizideki ilk kapı işleminin sağdan sola çarpılacağı $ G_N, $ gerçekten de hisse senedi durumu vektörüne uygulanan son bir şeydir. Daha basit bir şekilde, bu tür bir kapı kümesi, her hata toleransı için evrensel olduğunu biliyoruz: her bir hata toleransı için $ > $ $ G_1, \lnoktalar G_N, $ $ G_N \lnoktalar G_1 ve U arasındaki uzaklığın $ $ $ en fazla $ \epsilon $ olduğunu varsayalım. İdeal $ $ olarak, \epsilon 'nin bu uzaklığına ulaşmak için gereken N değeri, $ $ Poly-logaritmayı $ 1/\ Epsilon ile ölçeklendirmelidir $ .

Bu tür bir Evrensel kapı kümesi uygulamada nasıl görünür?  Tek-qubit kapıları için en basit bu tür Evrensel kapı kümesi yalnızca iki ağ geçidiyle oluşur: Hadamard Gate $ H $ ve so adlı $ T $ -Kapısı ( $ \ PI/8 kapısı olarak da bilinir $ ):

$$
H = \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix} , \qquad T = \begin{bmatrix} 1 & 0 \\\\ 0 & e ^ { i \ Pi/4 } \end{bmatrix} .
$$

Ancak, hisse matı hata düzeltmesiyle ilgili pratik nedenlerden dolayı, $ H ve T kullanılarak oluşturulabilecek bir daha büyük bir kapı kümesini düşünmek daha kolay olabilir $ $ $ . Hisse geçitlerini iki kategoride sınıflandırabiliriz: Clienfford Gates ve $ T $ -Gate.
Bu alt bölüm, çok sayıda hisse hata düzeltme şeması için yararlıdır; bu nedenle, hata tolerantly uygulamak için işlem ve qubit olarak çok az kaynak gerektirir. Bu, hata toleransı gerektirmeyen Clienfford geçitleri oldukça maliyetlidir. [İçinde Q# Varsayılan olarak dahil edilen ](xref:microsoft.quantum.libraries.standard.prelude), tek qubit clienfford kapıları standart kümesi,

$$
H = \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix} , \qquad S = \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix} = T ^ 2, \qquad X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} = HT ^ 4h,$$

$$
Y = \begin{bmatrix} 0 & -ı \\\\ ı & 0 \end{bmatrix} = T ^ 2ht ^ 4 HT ^ 6, \qquad Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} = T ^ 4.
$$

Burada $ X $ , $ Y $ ve Z işlemleri $ $ özellikle sık kullanılır ve oluşturan Wolfgang Pauli sonrasında [*Pauli işleçleri*](https://en.wikipedia.org/wiki/Pauli_matrices) olarak adlandırılır.
Clienfford Gate ( $ T $ -Gate) ile birlikte, bu işlemler tek bir qubit üzerinde her türlü Unitary dönüştürmesi ile birleştirilebilir.

Bu işlemler hakkında daha fazla bilgi için, Bloch Sphere gösterimleri ve Q# uygulamaları için bkz. [iç Işlemler ve işlevler](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions).

Bu temel öğelerden Unitary dönüştürmelerinin nasıl derlenebilir bir örnek olarak, yukarıdaki Bloo son 'da bulunan üç dönüşüm, $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \mapsto HZH \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ olan geçit dizisine karşılık gelir.

Önceki en popüler temel noktaları, yığının mantıksal düzeyinde (mantıksal düzeyin hisse algoritması düzeyi olarak düşünün) tanımlamak için en popüler temel noktaları oluştursa da, bir işlev açıklaması düzeyine daha yakın işlemler gibi, algoritmik düzeyinde daha az temel işlemleri düşünmek çok uygundur. Neyse ki, üst düzey Q# birimlere uygulama için kullanılabilir yöntemler de vardır. Bu, üst düzey algoritmaların, her şeyin Clienfford ve $ T-Gates 'e açık bir şekilde çıkarılması gerekmeden uygulanmasına izin verir $ .

En basit bu ilkel değer tek qubit Dönüştür. Üç adet tek qubit döndürme genellikle kabul edilir: $ R_x $ , $ R_y $ ve $ R_z $ . $Örneğin, döndürme R_x (\teta) eylemini görselleştirmek için, $ Örneğin, Bloch Sphere 'in x ekseninin yönü boyunca sağ Thumb 'ı işaret $ ettikten $ sonra vektörü, $ \ teta/2 $ radyanıyla birlikte döndürerek. 2. bu kafa karıştırıcı, $ $ Dikli vektörler $ $ Bloch Sphere üzerinde çizildiklerinde 180 ^ \circ, ancak aslında $ yalnızca 90 ^ \circ $ derece, geometrik olarak. Karşılık gelen Unitary matrisleri şunlardır:

\begin{align* } 
 & R_z (\teta) = e ^ { -i\teta z/2 } = \begin{bmatrix} e ^ { -i \ teta/2 } & 0 \\\\ 0 & e ^ { i \ teta/2 } \end{bmatrix} , \\\\ 
 & R_x (\teta) = e ^ { -i\teta x/2 } = HR_z (\teta) H = \begin{bmatrix} \ cos (\ teta/2) & -i\sin (\ teta/2) \\\\ -i\sin (\ teta/2) & \cos (\ teta/2) \end{bmatrix} , \\\\ 
 & R_y (\teta) = e ^ { -i\teta y/2 } = SHR_z (\teta) HS ^ \dagger = \begin{bmatrix} \cos (\ teta/2)-\sin (\ teta/2) \sin (\ teta/2) & \\\\ & \cos (\ teta/2) \end{bmatrix} . \end { Hizala*}

Üç boyutta de rastgele bir döndürme gerçekleştirmek için üç döndürmeler birlikte birleştirilebileceği gibi, blok Sphere gösteriminden herhangi bir Unitary matrisinin üç döndürmeler sırası olarak yazılabileceğini de görebilirsiniz. Özellikle, her Unitary matrisi için $ ( $ Örneğin, $ \alpha \beta \gamma \delta $ $ u = e ^ { i \alpha } R_x ( \beta ) R_z () \gamma R_x () \delta $ . $Bu nedenle, R_z (\teta) $ ve $ H $ aynı zamanda bir Evrensel kapı kümesi oluşturur, çünkü $ \teta $ herhangi bir değer alabilir. Bu nedenle ve hisse uygun bir şekilde, bu tür sürekli kapıların, bu nedenle hisse için, özellikle de hisse algoritması tasarım düzeyinde, bu tür sürekli kapılarda önemli olması için Hataya dayanıklı donanım uygulamalarına ulaşmak için, sonunda bu döndürmeleri yakın olan ayrık geçit dizileri olarak derlenir.
