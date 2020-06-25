# <a name="articles"></a>Makaleler

Bu dizinde, hisse geliştirme setinin belgeleri için makaleleri bulabilirsiniz. Bu dizin şunları içerir:

- **Makale dizinleri**: belgelerin her bölümü için makaleleri içerir. Bu dizinlerde aşağıdaki içerikleri bulabilirsiniz:
  
  - Her dizin, `toc.yml` dizinin içeriğini ana Içindekiler tablosunda (TOC) görüntüleyen bir dosya içerir.
  - Belgeleri içeren markın makaleleri. Bu makaleler [Microsoft docs katkıda bulunan Kılavuzu ' na](https://docs.microsoft.com/en-us/contribute/)ait yönergeleri izlemelidir.
  - Makaleler alt dizinler. Bu alt dizinler ayrıca kendi `toc.yml` dosyalarını içermelidir.

> :p Encil: `*.md` dosyaları doğrudan üst dosyada başvurmak mümkün olsa da `TOC.yml` , nesneleri sipariş etmek için yalnızca `toc.yml` kendi geçerli dizinlerinden başvurduk.

- **Ana içindekiler tablosu (TOC) `TOC.yml` dosyası**: Bu dosyada, TOC Web sitesinin bölümleri `toc.yml` her bölümün dizininin ana dosyası başvurusuyla birlikte listelenir.
- **`index.yml`** YAML, belgelerinin giriş sayfası yapılandırmasıyla birlikte.
- **`\media`**: Belgelerde kullanılan tüm görüntüleri depolamak için bir dizin. `\media\src`Görüntülerin kaynak dosyalarını depolamak için bir alt dizin içerir.
- **Lisans dosyaları**: yasal lisansları içeren dosyalar
- **Teknik dosyalar**: makrolar ve meta verileri içeren dosyalar.

## <a name="guidelines"></a>Yönergeler

Katkıda bulunanlar için bu dizinin organizasyonu hakkında bazı genel yönergeler:

- Her dizin veya alt dizin `toc.yml` , aynı düzey makalelere veya alt dizinlerinin dosyalarına başvuruda bulunulan kendi dosyasını içermelidir `toc.yml` .
- Deponun dizinlerinin organizasyonu, belge Web sitesinin içindekiler tablosunun kuruluşunda mümkün olduğunca yakın olmalıdır.
- Tüm görüntülerin, makaleler klasöründe değil ' de depolanması gerekir `articles\media` .
- Makalelerin başlıkları, TOC 'deki adlar ve meta verilerin *UID 'si* bunlar arasında olabildiğince yakın olmalıdır ve markaşağı belgesinin açıkça H1 üstbilgisini temsil eder.

## <a name="adding-images"></a>Görüntü ekleme

Görüntülerin koyu modda düzgün bir şekilde işlemesini sağlamak için saydamlıkları kullanmaktan kaçınmalısınız.
- `*.jpg`Dosyalar için dosya biçimi saydam öğeleri desteklemediğinden hiçbir şey yapmanız gerekmez.
- `*.png`Dosyalar için bir beyaz arka plan eklemeniz veya Alfa kanalının değerini 100 olarak değiştirmeniz gerekir. Bu işlemi Windows 'da yapmanın en kolay yolu, orijinal dosyanın üzerine yazarak dosyayı Paint ve kaydetme bölümünde açmaktır.
- `*.svg`Dosyalar için en düşük katmana beyaz dikdörtgen eklemeniz gerekir. Bunu Inkscape ile yapabilirsiniz:
  - `*.svg` dosyasını açın.
  - Kare Oluşturucu aracını seçin ve orijinal şeklin üzerine bir beyaz dikdörtgen çizin.
  - Koyu oka tıklayarak veya F1 tuşuna basarak "nesneleri Seç ve Dönüştür" aracını seçin.
  - Dikdörtgenin seçili olmasına karşın, "seçim için alt öğe (bitiş)" araç çubuğu öğesine tıklayın.
  - Dikdörtgeni fare veya ok tuşlarıyla ayarlayın.
