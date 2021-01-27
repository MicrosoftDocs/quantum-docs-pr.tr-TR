---
Başlık: birden çok qubits açıklaması: iki veya daha fazla qubit üzerinde işlem gerçekleştirmeyi öğrenin.
Yazar: bradben uid: Microsoft. hisse. Concepts. Multiple-qubitleri MS. Author: v-bendörtms. Date: 12/11/2017 MS. Topic: kavramsal No-loc:
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

# <a name="multiple-qubits"></a>Birden çok qubit

Tek-qubit kapıları, belirli bir zamanda birden fazla durumda olma yeteneği gibi bazı sayaç sezgisel özelliklere sahip olsa da, bir hisse başında bir bilgisayar tek qubit kapıları olsaydı, bir Hesaplayıcı yalnızca klasik bir süper bilgisayara izin vermekle birlikte, hesaplama gücüne sahip bir cihazımız olur.
Yalnızca Lem bilgi işlemin doğru gücü, qubits sayısını artırdığımız için yalnızca daha açık hale gelir.
Bu güç, parça devlet vektörlerine ait vektör alanı boyutu, qubit sayısıyla üstel olarak artmıştır.
Yani, tek bir qubit, bir 50-qubit hisse hesaplamasının benzetimini yapan, mevcut süper bilgisayarların sınırlarını eşit bir şekilde iletebileceği anlamına gelir.
Hesaplama boyutunu yalnızca bir ek qubit ile artırmak, durumu depolamak için gereken belleği *iki katına çıkarır* ve hesaplama süresini kabaca *ikiye katlanır* .
Hesaplama gücü 'nin bu hızlı katmasının nedeni nispeten az sayıda qubit olan bir hisse bilgisayarının, bazı hesaplama görevleri için yarın ve daha fazla en güçlü süper bilgisayarı daha fazla artırabileceğini tahmin edebilirsiniz.

Hisse madevlet vektörlerine neden üstel büyümemiz gerekir?  Bu bölümde, tek qubit durumlarından çok qubit durumları oluşturmak için kullanılan kuralların yanı sıra, bir evrensel çok değerli-qubit bilgisayar oluşturmak için bir geçit kümesine dahil etmemiz gereken geçit işlemlerini tartışmaktır.
Bu araçların, kodda yaygın olarak kullanılan kapı kümelerini anlaması Q# ve ayrıca, entanglement veya girişim oluşturma ile klasik bilgi işlem ile daha güçlü bir işleme

## <a name="representing-two-qubits"></a>Iki qubit 'i temsil etme
Bir-ve iki-qubit durumu arasındaki temel fark, iki-qubit durumlarının iki boyut yerine dört boyutlu olması gerektiğidir.
Bunun nedeni, iki-qubit durumlarının hesaplama temelinin, tek qubit durumlarının tencursor ürünleri tarafından oluşturulmuş olmasından kaynaklanır.  Örneğin, \begin{align}
00 \equiv \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} , \qquad 01 \equiv \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \\\\ 0 \end{bmatrix} ,\\\\
10 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix} 0 \\\\ 0 \\\\ 1 \\\\ 0 \end{bmatrix} , \qquad 11 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \begin{bmatrix} 0 \\\\ 0 \\\\ 0 \\\\ 1 \end{bmatrix} .
\end{align}

$ $ Bu oluşturma kullanılarak, n qubits 'in hisse boyutunun, 2 ^ n boyutlu bir birim vektörü ile temsil edildiği kolayca görüyordu $ $ .  Vektör

$$
\begin{bmatrix}\alpha _{ 00 } 01 \\\\ 10 \alpha_ { } \\\\ \alpha _{ 11 } \\\\ \alpha_ { }  \end{bmatrix}
$$

$ | \alpha _{ 00 } | ^ 2 | + \alpha_ { 01 } | ^ 2 + | \alpha _{ 10 } | ^ 2 | + \alpha_ { 11 } | ^ 2 = 1 $ ise iki qubit üzerinde bir hisse durumu temsil eder. Tek qubit 'de olduğu gibi, birden çok qubit için hisse durum vektörü, sistemin davranışını anlatmak için gereken tüm bilgileri tutar.

Bir diğeri durumunda iki ayrı qubit verildiyse, $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ $ \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ buna karşılık gelen iki-qubit durumu    

$$
\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} 
=\begin{bmatrix} \alpha \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\  \delta \end{bmatrix} \end{bmatrix}
= \begin{bmatrix} \alpha\gamma \\\\  \alpha\delta \\\\  \beta\gamma \\\\  \beta\delta \end{bmatrix}, $$

Bu işlem, $ \otimes $ vektörin Tensor ürünü (veya Kronecker ürünü) olarak adlandırılır. İki adet tek qubit durumunun her zaman bir iki-qubit durumu oluşturmak için her zaman götürebileceğine, iki-qubit hisse senedi durumlarının iki adet tek qubit eyaletinin tencursor ürünü olarak yazılamayacağını unutmayın.
Örneğin, bir durum yoktur $ \psi = \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ ve bu nedenle, $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ Tensor ürünü durum olur     

$$\psi\otimes\phi = \begin{bmatrix} 1/ \sqrt { 2 } \\\\ 0 \\\\ 0 \\\\ 1/ \sqrt { 2 } \end{bmatrix} .$$ 

Bu tür bir iki-qubit durumu, tek qubit durumlarının tencursor ürünü olarak yazılamaz, "entangled State" olarak adlandırılır; iki qubit, [*bağımsız olarak kabul edilir.*](https://en.wikipedia.org/wiki/Quantum_entanglement)  Gevşekle, hisse Eyaleti tek qubit durumları için bir Tensor ürünü olarak düşünülmediği için, durumun tuttuğu bilgiler tek tek qubits 'e göre sınırlandırmaz.  Bunun yerine, bilgiler, iki durum arasındaki eş ilişkilerdeki yerel olmayan bir şekilde depolanır.  Bu bilgilerin yer aldığı, klasik bilgi işlem üzerinden hisse bilgi işlem özelliklerinin büyük ayrım özelliklerinden biridir ve [hisse maporsyon](https://github.com/microsoft/Quantum/tree/main/samples/getting-started/teleportation) ve hisse ansız [hata düzeltmesi](xref:microsoft.quantum.libraries.error-correction)dahil olmak üzere bir dizi hisse protokolde gereklidir.

## <a name="measuring-two-qubit-states"></a>Two-Qubit durumlarını ölçme ##
İki-qubit durumu ölçme, tek qubit ölçümlerine çok benzer. Durumu ölçme

$$
    \begin{bmatrix}
        \alpha_{ 00 } 01 \\\\ \alpha_ { }\\\\ 
        \alpha_{ 10 } 11 \\\\ \alpha_ {}
    \end{bmatrix}
$$

, olasılık 01 ^ 2, 1 olasılık 1 $ $ ^ 2 $ | \alpha _{ } | $ $ $ ve 11 olasılık 11 ^ 2 ile 10. $ | \alpha_ { } | $ $ $ $ | \alpha _{ } | $ $ $ $ | \alpha_ { } | $ $ \alpha _{ 00 } , \alpha_ { 01 } , \alpha _{ 10 } $ ve $ 11 değişkenleri bu bağlantıyı açık hale getirmek için kasıtlı olarak adlandırılmıştı \alpha_ { } $ . Ölçüden sonra, sonuç 00 ise, $ $ iki-qubit sisteminin hisse TI durumu daraltıldı ve şu anda

$$
    oluşturun \equiv
    \begin{bmatrix}
        1 \\\\ 
        0 \\\\ 
        0 \\\\ 
        0 \end{bmatrix} .
$$

İki-qubit hisse durumunun yalnızca bir qubitinin ölçülmesi de mümkündür. Yalnızca bir alt sisteme daraltılacağından, her bir qubits 'in yalnızca bir kısmını ölçecek şekilde, ölçümün etkileri çok daha farklı bir durumdur.  Diğer bir deyişle, bu gibi durumlarda yalnızca bir qubit yalnızca bir qubit, alt sistemlerden yalnızca birini daraltır ancak bunların tümünü kullanmaz.  

Bunu görmek için, ilk olarak $ iki qubit üzerinde Hadamard Transform H 'nin $ "0" durumuna ayarlandığı, şu durumun ilk qubit 'i ölçmesini düşünün: $$
H ^ { \otimes 2 } \left ( \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \right ) = \frac { 1 } { 2 } \begin{bmatrix} 1 & 1 1, & & \\\\ 1 & -1 & 1 & -1 \\\\ 1 1- & & 1 & -1 1- \\\\ & 1 & -1 & 1 1 \end{bmatrix} \begin{bmatrix} \\\\ 0 \\\\ 0 0 1 2 1 1 1 1 \\\\ \end{bmatrix} = \frac { } { } \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \mapsto \begin{cases} \text { sonuç } = 0 1 & \frac { } { \sqrt { } } \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \\\\ \text { } = & \frac { } { \sqrt { 2 } } \begin{bmatrix} 0 \\\\ 0 \\\\ \\\\ \end{bmatrix} \\\\ \end{cases}  
$$
Her iki sonuç da %50 oranında meydana gelen bir olasılıktır.  Her ikisi için %50 olasılık elde edilen sonuç, ilk bir değer olan $ 0 $ ' ın $ $ ilk qubit üzerinde 1 ' i takas altında sabit olduğu gerçeden bağımsız olarak atanabilir.

Birinci veya ikinci qubit ölçmeye yönelik matematik kuralı basittir.  $ $ $ K ^ { \rm TH } $ Hesaplama tabanlı vektörün e_k izin vermemiz ve $ $ tüm $ e_k kümesi olduğundan, bu, $ söz konusu k 'nin söz konusu $ $ k değeri için 1 değerini alır $ $ .  Örneğin, ilk qubit ' i ölçmeye ilgileniyorsanız, $ S $ $ e_1 \equiv 10 $ ve $ e_3 \equiv 11 ' $ den oluşur.  Benzer şekilde, ikinci qubit $ S $ $ ile ilgileniyorsanız e_2 \equiv 01 $ ve $ e_3 \equiv 11 $ ' den oluşur.  Ardından, seçilen qubit ' i $ $ durum vektörü için 1 olarak ölçmeye olasılığı $\psi$

$$
P ( \text { sonuç } = 1) = \sum _ { e_k \text { set } S } \psi ^ \dagger e_k e_k ^ \dagger \psi .
$$

> [!NOTE]
> Bu belgede, hesaplama temelini etiketlemek için küçük endian biçimini kullanıyoruz. Little endian biçiminde, önce en az önemli bitler gelir. Örneğin, küçük endian biçimindeki dört sayı, bit 001 dizesi tarafından temsil edilir.

Her qubit ölçümü yalnızca $ 0 $ veya $ 1 $ ' i sağlayabileceğinizden, 0 ölçmesinin olasılığı yalnızca $ $ $ 1-P ( \text { sonuç } = 1) olur $ .  Bu nedenle 1 ölçmesinin olasılığı için yalnızca açık olarak bir formül sağlıyoruz $ $ .

Bu tür bir ölçümün durumunda olduğu eylem matematiksel olarak ifade edilebilir

$$
\psi\mapsto \frac{\sum _ { e_k \text { set } S } e_k e_k ^ \dagger \psi } { \sqrt { P ( \text { sonuç } = 1) } } .
$$

Ölçüm olasılığı sıfır olduğunda, dikkatli olan okuyucu ne olacağı hakkında endişelenmeye başlayabilir.  Bu durumda, sonuçta elde edilen durum teknik olarak tanımsız olsa da, olasılık sıfır olduğundan bu tür bir durumla uğraşmak zorunda kaldık!


$ \psi $ Yukarıda verilen ve ilk qubit 'i ölçmeye ilgilendiğimiz bir Tekdüzen durum vektörü olması halinde 

$$
P ( \text { ilk qubit 1 ölçümü } = ) = ( \psi ^ \dagger e_1) (e_1 ^ \dagger \psi ) + ( \psi ^ \dagger e_3) (e_3 ^ \dagger \psi ) = | e_1 ^ \dagger \psi | ^ 2 + | e_3 ^ ^ 2 \dagger \psi | .
$$

Bunun yalnızca, 10. sonuçların ölçülmesi beklenen iki olasılıkların toplamı olduğunu $ $ ve 11 ' in $ $ ölçüldüğü tüm qubits olduğunu unutmayın.
Örneğimiz için, bu değerlendirme

$$
\frac{1 } { 4 } \left | \begin{bmatrix} 0 & 0 & 1 & 0 \end{bmatrix} \begin{bmatrix} 1 \\\\ 1 \\\\ 1 \\\\ 1 \end{bmatrix} \right | ^ 2 + \frac { 1 } { 4 } \left | \begin{bmatrix} 0 & 0 & 0 & 1 \end{bmatrix} \begin{bmatrix} 1 \\\\ 1 \\\\ 1 \\\\ 1 \end{bmatrix} \right | ^ 2 = \frac { 1 } { 2 } .
$$

ıntuetdiğimiz anlamı bize söylerken, olasılık olması gerekir.  Benzer şekilde, durum şöyle yazılabilir

$$
\frac{\frac{e_1 } { 2 } + \frac { e_3 } { 2 } } { \sqrt { \frac { 1 } { 2 } } } = \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 0 \\\\ 0 \\\\ 1 \\\\ 1\end{bmatrix}
$$

ıntuize uygun olarak tekrar.

## <a name="two-qubit-operations"></a>Two-Qubit Işlemler
Tek qubit durumunda olduğu gibi, herhangi bir Unitary dönüştürmesi qubits üzerinde geçerli bir işlemdir. Genel olarak, n qubit üzerindeki bir Unitary dönüştürmesi $ $ $ $ $ , 2 ^ n 2 ^ n boyutundaki bir matris u \times $ $ $ ve $ u ^ { -1 } = u ^ \dagger $ gibi,% n boyutundaki vektörlerde çalışır.
Örneğin, CNOT (denetlenen) geçidi, yaygın olarak kullanılan iki-qubit kapısı ve aşağıdaki Unitary matrisi tarafından temsil edilir:

$$
\operatorname{CNOT } = \begin{bmatrix} 1 \ 0 \ 0 \ 0  \\\\  0 \ 1 \ 0 \ 0 \\\\  0 \ 0 \ 0 \ 1 0 \ 0 \ \\\\  1 \ 0 \end{bmatrix}
$$

Ayrıca, her iki qubit üzerinde tek qubit kapıları uygulayarak iki-qubit geçitleri de oluşturabilirsiniz. Örneğin, kapıları uygulıyoruz 

$$
\begin{bmatrix}
a \ b \\\\ c \ d \end{bmatrix}
$$

ve

$$\begin{bmatrix}
e \ f \\\\ g \ h \end{bmatrix}
$$

ilk ve ikinci qubits 'e sırasıyla, bu, Tensor ürünü tarafından verilen iki-qubit Unitary 'i uygulamaya eşdeğerdir: $$\begin{bmatrix}
a \ b \\\\ c \ d \end{bmatrix}
\otimes 
\begin{bmatrix}
e \ f \\\\ g \ h \end{bmatrix}=
    \begin{bmatrix}
    AE \ AF \ olmalıdır \ BF \\\\
    AG \ Ah \ bg \ BH \\\\
    CE \ CF \ de \ df \\\\
    CG \/\ DG \ DH \end{bmatrix} .$$
Bu nedenle, bilinen bir tek qubit kapıları 'ın Tensor ürününü alarak iki qubit kapıları form oluşturarız. İki-qubit kapıya örnek olarak $ h \otimes h $ , $ x \otimes \boldone $ ve $ x Z verilebilir \otimes $ .

İki adet tek qubit kapısı, tenslı ürününü alarak iki qubit ağ geçidi tanımlalarken, listesiyse 'nin doğru olmadığını unutmayın. Her iki-qubit kapıları tek qubit kapıları 'ın Tensor ürünü olarak yazılabilir.  Bu tür bir ağ geçidi, bir *entrini* geçidi olarak adlandırılır. Bir entrini kapısı örneği, CNOT Kapısı ' dir.

Denetlenen bir kapı arkasındaki ıntuun, rastgele kapıların genelleştirilemez.  Genel olarak denetlenen bir geçit, belirli bir qubit 1 değilse kimlik (yani, hiçbir eylemde yok) olarak davranan bir kapıdır $ $ .  X $ $ $ \Lambda \_ (U) ile x etiketli qubit üzerinde bu durumda denetlenen bir Unitary olduğunu belirledik $ .  Bir örnek olarak $ \Lambda , _0 (u) e \_ { 1 } \otimes { \psi } = e \_ { 1 } \otimes U { \psi } $ ve $ \Lambda \_ 0 (u) e 0 e 0 \_ { } \otimes { \psi } = \_ { } \otimes { \psi } $ , burada $ e \_ 0 $ ve $ e 1, \_ $ $ 0 $ ve 1 değerlerine karşılık gelen tek bir qubit için hesaplama tabanlı vektörlerdir $ $ .  Örneğin, aşağıdaki kontrollü-Z geçidini göz önünde bulundurun ve $ $ bunu şöyle ifade edebilirsiniz $$
\Lambda\_0 (Z) = \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{bmatrix} = ( \boldone \otimes h) \operatorname { cnot } ( \boldone \otimes h).
$$

Denetimli birimlere verimli bir şekilde derleme, önemli bir zorluktur.  Bunu yapmanın en kolay yolu, temel kapıların denetlenen sürümlerinin bir veritabanının ayarlanmasını ve orijinal Unitary işlemindeki tüm temel kapıları denetimli karşılığına göre değiştirmeyi gerektirir.  Bu çoğunlukla, aynı etkiyi elde etmek için yalnızca birkaç kapıya denetimli sürümlerle değiştirmek üzere kullanılabilir.  Bu nedenle, en iyi duruma getirilmiş bir sürüm tanındığı takdirde, iskemizdeki kullanıcının Unitary 'ın denetimli bir sürümünü tanımlamasına veya bağlanmasına izin veren Naïve yöntemini gerçekleştirme olanağı sunuyoruz.

Kapılar, klasik bilgiler kullanılarak da denetlenebilir.  Sınıf denetimli olmayan bir not kapısı, örneğin, yalnızca sıradan olmayan bir kapıdır, ancak yalnızca klasik bir bit, bir $ $ hisse bitge karşı 1 ise geçerlidir.  Bu anlamda, sınıf tarafından denetlenen bir geçit, kapıdaki hisse amayan bir bildirim yalnızca kodun bir dalında uygulanırsa bir if bildirisi olarak düşünülebilir.


Tek qubit durumunda olduğu gibi, $ 4 \times 4 $ unitöğeli bir matrisin, bu kümeden rastgele duyarlığa kadar olan bir kapı ürünüyle ilgili olması halinde, iki-qubit kapısı kümesi Universal olur.
Bir Evrensel kapı kümesi örneği, Hadamard kapısı, T kapısı ve CNOT kapısı. Bu kapıların ürünlerini alarak, iki qubit üzerinde her türlü Unitary matrisini yaklaşık olarak kullanabiliriz.

## <a name="many-qubit-systems"></a>Many-Qubit sistemleri
Daha küçük sistemlerden birçok qubit hisse durumu oluşturmak için iki-qubit durumunda araştırılan aynı desenleri izliyoruz.  Bu tür durumlar, daha küçük durumlardan oluşan tencursor ürünleri kullanılarak oluşturulmuştur.  Örneğin, 1011001 bit dizesini $ $ bir hisse bilgisayar bilgisayarında kodlamayı göz önünde bulundurun.  Bunu şöyle kodlayabiliriz

$$
1011001 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} .
$$

Hisse kapıları tamamen aynı şekilde çalışır.  Örneğin, $ X $ geçidini ilk qubit 'e uygulamak ve sonra ikinci ve üçüncü qugeler arasında bir cnot gerçekleştirmek istiyorsanız bu dönüşümü şu şekilde ifade eteceğiz

\begin{align}
&(X \otimes \operatorname { cnot } _ { 12 } \otimes \boldone \otimes \boldone \otimes \boldone \otimes \boldone ) \begin{bmatrix} 0 \\\\ 1 1 0 0 1 0 \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1\end{bmatrix}\\\\
&\qquad\qquad\equiv 0011001. \end{align}

Birçok qubit sisteminde, genellikle hisse bilgisayarı için geçici bellek işlevi sunan qubit ve serbest bırakma gereksinimi vardır.  Böyle bir qubit, anyala olarak adlandırılır.  Varsayılan olarak, qubit durumunun $ ayırma sonrasında e_0 için başlatıldığını varsaytık $ .  Yeniden $ ayırmayı yapmadan önce e_0 tekrar döndürüldüğünü varsaytık $ .  Bu varsayım, bir anyalı qubit, serbest bırakıldığında başka bir qubit yazmaç ile birlikte eşit hale gelirse, ayırmayı kaldırma işlemi anakla 'ya zarar verir.  Bu nedenle, bu tür qubits 'in yayınlanmadan önce ilk durumuna döndürüldüğünü varsaydık.

Son olarak, iki qubit hisse bilgisayarı için evrensel hisse bilgi işlem düzeyine ulaşmak üzere, geçit kümesine yeni kapılar eklenmesi gerektiğinden, Multi-qubit durumunda yeni bir kapı tanıtılmalıdır.  Herhangi bir $ $ $ $ genel Unitary dönüştürmesi bir dizi iki qubit dönüşte parçalanabileceğinden birçok qubit üzerinde bir Evrensel kapı kümesi H, T ve cnot.  Daha sonra, iki-qubit durumu için geliştirilmiş olan teorik 'ten yararlanabilir ve çok sayıda qubit olduğunda bunu burada tekrar kullanabilirsiniz.

Şimdiye kadar kullanmakta olduğumuz doğrusal cebirsel gösterimi, çok qubit durumlarını anlatmak için kesinlikle kullanılabilir, ancak durumların boyutunu arttık.  Bir uzunluk 7 bit dizesinin ortaya çıkan sütun vektörü, örneğin, $ $ daha önce çok daha önce açıklanan gösterimi kullanarak ifade 128 boyutludur.  Bu nedenle, daha sonra bu yüksek boyutlu vektörleri öz konusunda bize izin veren hisse alım durumunda daha sonra genel bir gösterim sunuyoruz.
