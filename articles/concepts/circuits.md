---
Başlık: hisse devreleri açıklaması: hisse bağlantı diyagramlarında basit ve karmaşık hisse operasyonlarını görsel olarak nasıl temsil ettiğini öğrenin.
Yazar: Histumwriter uid: Microsoft. hisse. Concepts. devreler MS. Author: v-benköşeli MS. Date: 12/11/2017 MS. Topic: article No-loc:
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

# <a name="quantum-circuits"></a>Hisse devreleri
Bir süre boyunca Unitary dönüştürme $ \text { cnot } _ { 01 } (H \otimes 1) $ göz önünde bulundurun.
Bu ağ geçidi sırası, en yüksek düzeyde bir entangled bit durumu oluşturduğundan, hisse bilgi işlem için temel öneme sahiptir:

$$\mathrm{Cnot } _ { 01 } (H \otimes 1) \ket { 00 } = \frac { 1 } { \sqrt { 2 } } \left ( \ket { 00 }  +  \ket { 11 } \right ),$$

Bu ya da daha fazla karmaşıklığa sahip işlemler, hisse uygun bir şekilde bir hisse alım *Diyagramı* olarak adlandırılan görselleştirme için basit bir yöntem olduğundan harika bir sorun olması gerekir.
Bu en yüksek düzeyde değerlendirme için devre diyagramı şu şekilde hazırlanıyor:

<!--- ![](.\media\1.svg) --->
<!--Bunu kolayca ortalamak için bir yol bulamıyor... Muhtemelen gerekli bir uzantı:-->
![En yüksek düzeyde bir entaninal iki-qubit durumu için devre diyagramı](~/media/1.svg)

## <a name="quantum-circuit-diagram-conventions"></a>Hisse devre diyagramı kuralları
Hisse için bu görsel dil, bir hisse devresini ifade eden kuralları anladıktan sonra eşdeğer matrisinin yazılmasından daha kolay digestible olabilir.
Aşağıda bu kuralları gözden geçiririz.

Devre diyagramında, her katı çizgi bir qubit veya daha fazla genel olarak bir qubit kaydı gösterir.
Kurala göre, üst çizgi, en fazla 0 kayıt $ olur $ ve geri kalan değerler sırayla etiketlenir. Yukarıdaki örnek bağlantı hattı iki qubit üzerinde (veya bir qubitden oluşan equivalently iki kayıt) üzerinde işlem görecek şekilde gösterilmiştir.
Bir veya daha fazla qubit kayıt üzerinde işlem gören kapıları kutu olarak gösterilir.
Örneğin, simge

<!--- ![](.\media\2.svg) --->
<!--Bunu kolayca ortalamak için bir yol bulamıyor... Muhtemelen gerekli bir uzantı:-->
![Tek qubit kayıt üzerinde işlem gören Hadamard işlemi sembolü](~/media/2.svg)

, tek qubit kayıt üzerinde işlem gören bir [Hadamard](xref:Microsoft.Quantum.Intrinsic.H) işlemidir.

Hisse kapıları, ilk olarak qubits 'e uygulanan kapıda en sol geçit ile kronolojik sırada sıralanır.
Diğer bir deyişle, kapıların hisse durumunu tutan şekilde fotoğrafını yaparsanız, kablolar diyagramdaki her bir kapıdan, soldan sağa doğru hisse ma durumunu getirir.
Yani 

<!--- ![](.\media\3.svg) --->
<!--Bunu kolayca ortalamak için bir yol bulamıyor... Muhtemelen gerekli bir uzantı:-->
![Soldan sağa uygulanan hisse kapıları diyagramı](~/media/3.svg)

, Unitary matris $ cba olur $ .
Matris çarpıtına ters kural: en sağdaki matris önce uygulanır. Ancak, bu arada en sol kapı, en sol kapı için uygulanır.
Bu fark, her zaman karışıklığa yol açabilir, bu nedenle doğrusal cebirsel gösterimi ve hisse senedi devre şemaları arasında önemli bir farklılık olduğunu fark etmek önemlidir.

## <a name="inputs-and-outputs-of-quantum-circuits"></a>Hisse devreleri giriş ve çıkışları
Verilen tüm önceki örneklerde, hisse kapıdan alınan kabloların sayısı kadar hisse kapıda aynı sayıda kablo (qubit) girişi gerekiyordu.
Bu ilk olarak, hisse devrelerin genel olarak girdilerden daha fazla veya daha az çıkış sahibi olabileceği makul görünebilir.
Ancak tüm hisse işlemleri, ölçümü Kaydet, Unitary ve bu nedenle ters çevrilebilir olduğundan bu olanaksızdır.
Girişlerle aynı sayıda çıkışı yoksa, geri alınamaz ve bu nedenle bir çelişki olan Unitary değildir.
Bu nedenle, bir devre diyagramında çizilen her kutu, tam olarak onunla aynı sayıda kabloda yer almalıdır.

Multi-qubit devre şemaları, tek qubit olanlara benzer kuralları izler.
Bir açıklığa kavuşturan örnek olarak, iki-qubit unitöğeli bir işlemi $ B $ $ (H S \otimes X) olarak tanımlayabilir $ ve devre equivalently şu şekilde ifade edebilirsiniz

<!--- ![](.\media\4.svg) --->
<!--Bunu kolayca ortalamak için bir yol bulamıyor... Muhtemelen gerekli bir uzantı:-->
![İki-qubit Unitary işleminin devre diyagramı](~/media/4.svg)

Ayrıca $ $ , devre dışı bırakıldığına bağlı olarak 2 1-qubit kayıtları yerine tek bir iki-qubit kayıt üzerinde bir eyleme sahip olarak B 'yi de görüntüleyebiliriz. Bu tür soyut devre diyagramlarından en yararlı özellik, karmaşık hisse algoritmalarının, bunları temel kapıları derlemek zorunda kalmadan yüksek düzeyde açıklanmasına izin vermesidir.
Bu, algoritmadaki her bir alt yordamların nasıl çalıştığı hakkında tüm ayrıntıları anlamak zorunda kalmadan, büyük bir hisse algoritması için veri akışı hakkında bir bilgi edinebilirsiniz.

## <a name="controlled-gates"></a>Denetlenen kapıları
Multi-qubit hisse devresini içinde yerleşik olan diğer yapı denetimdir.
$ \Lambda Tek bir qubitin değerinin G uygulamasını denetlediğini (g), bir hisse listedir kontrollü kapıdan oluşan eylem, $ $ $ aşağıdaki bir ürün durumu girişi $ \Lambda (g) ( \alpha \ket { 0 }  +  \beta \ket { 1 } ) \ket { \psi } = \alpha \ket { 0 } \ket { \psi }  +  \beta \ket { 1 } G \ket { \psi } $ örneğine bakarak anlaşılabilmektedir. Yani, denetlenen ağ geçidi, $ $ $ \psi $ yalnızca denetim qubit değeri 1 değerini alırsa, $ öğesini içeren kayda G uygular $ .
Genel olarak, bu tür denetimli işlemleri devre diyagramlarında

<!--- ![](.\media\5.svg) --->
<!--Bunu kolayca ortalamak için bir yol bulamıyor... Muhtemelen gerekli bir uzantı:-->
![Listedir denetimli bir ağ geçidinin devre diyagramı](~/media/5.svg)

Burada siyah daire, kapıdan denetlediğiniz ve dikey bir tel, denetim qubit 1 değerini alırken uygulanan Unitary 'ı gösterir $ $ .
$G = x $ ve $ g = Z $ 'nin denetlenen sürümünü (örneğin, denetlenen X Gate 'nin [ $ cnot $ kapısı](xref:Microsoft.Quantum.Intrinsic.CNOT)olduğunu unutmayın) gösteren özel durumlar için aşağıdaki gösterimi sunuyoruz:

<!--- ![](.\media\6.svg) --->
<!--Bunu kolayca ortalamak için bir yol bulamıyor... Muhtemelen gerekli bir uzantı:-->
![Denetlenen kapıların özel durumları için devre diyagramı](~/media/6.svg)

Q# , programcının bu işlemleri ele almak zorunda kalmadan kaydeden bir işlemin denetlenen sürümünü otomatik olarak oluşturmak için yöntemler sağlar. Buna bir örnek aşağıda verilmiştir:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a>Ölçüm işleci
Devre diyagramlarında görselleştirilecek kalan işlem ölçümdür.
Ölçüm bir qubit kaydı alır, bunu ölçer ve sonucu klasik bilgiler olarak verir.
Ölçüm bir işlem, ölçüm simgesiyle gösterilir ve her zaman bir qubit yazmaç girişi (katı bir satırla gösterilir) ve klasik bilgiler verir (bir Double satırıyla gösterilir).
Özellikle, bu tür bir alt devre şöyle görünür:

<!--- ![](.\media\7.svg) ---->
<!--Bunu kolayca ortalamak için bir yol bulamıyor... Muhtemelen gerekli bir uzantı:-->
![Ölçüm işlemini temsil eden sembol](~/media/7.svg)

Q# Bu amaçla bir [Ölçü işleci](xref:Microsoft.Quantum.Intrinsic.Measure) uygular.
Daha fazla bilgi için [ölçümlerle ilgili bölüme](xref:microsoft.quantum.libraries.standard.prelude#measurements) bakın.

Benzer şekilde, subdevı

<!--- ![](.\media\8.svg) --->
<!--Bunu kolayca ortalamak için bir yol bulamıyor... Muhtemelen gerekli bir uzantı:-->
![Denetlenen bir işlemi temsil eden devre diyagramı](~/media/8.svg)

, G tarafından denetlenen bir geçit sağlar; burada $ G, $ Klasik denetim bit değeri 1 olacak şekilde uygulanır $ $ .

## <a name="teleportation-circuit-diagram"></a>Teleporsyon devre diyagramı
Hisse teleporsyon, bu bileşenleri göstermek için büyük olasılıkla en iyi hisse algoritmadır.
Karşılık gelen [hisse küçon](xref:microsoft.quantum.overview.katas) ile uygulamalı teleporsyon, verileri bir hisse bir bilgisayar içinde (veya hatta bir hisse ağı içindeki uzak hisse bilgisayarları arasında), entanglement ve ölçüm kullanımıyla birlikte taşımaya yönelik bir yöntemdir.
Her ne kadar, bu, bir derece bitden diğerine, bir qubit 'in değerinin ne olduğunu bilmeksizin, belirli bir qubit içindeki değeri bir ile diğerine söylemeden, gerçekten de bir hisse cısına geçiş yeteneğine sahiptir!
Bu, protokol için hisse uzayı yasaları uyarınca çalışması için gereklidir.
Hisse ve teleporsyon devresi aşağıda verilmiştir; Ayrıca, hisse öğesinin nasıl okunacağını göstermek için devresinin açıklamalı bir sürümünü sunuyoruz.

<!--- ![](.\media\tp2.svg) { genişliği = %50} --->
![Hisse ve teleporsyon devresi](~/media/tp2.svg)
