---
title: Klasik verileri yükleme
description: Microsoft Quantum Development Kit (QDK) ile bir sınıflandırıcı modeli eğitme için kendi veri kümenizi yüklemeyi öğrenin.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
ms.openlocfilehash: efa4a65a489446cbef48507d0b02a932da74c71c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276134"
---
# <a name="load-and-classify-your-own-datasets"></a>Kendi veri kümelerinizi yükleyin ve sınıflandırın

Bu kısa öğreticide, bir sınıflandırıcı modelini hisse geliştirme kiti (QDK) ile eğiten kendi veri kümenizi nasıl yükleyeceğinizi öğreneceksiniz.

Verilerinizi depolamak için [JSON dosyaları](https://en.wikipedia.org/wiki/JSON) gibi standartlaştırılmış bir serileştirme biçiminin kullanımını önemle öneririz.
Bu tür biçimler, Python ve .NET ekosistemi gibi farklı çerçeveler ile yüksek uyumluluk sunar.
Özellikle, verileri yüklemek için şablonumuzu kullanmanızı öneririz. böylece kodu doğrudan örneklerden kopyalayabilir ve yapıştırabilirsiniz.

## <a name="template-for-loading-your-datasets"></a>Veri kümelerinizi yüklemek için şablon

Her bir örneğin _i $ $x $, $x _ {I2} $ ve $x _ {i3} $ $x $N = $2 $ (x, y) $ boyutunda bir eğitim veri kümeniz olduğunu varsayalım.
Doğrulama veri kümesi aynı yapıya sahiptir.
Bu datsets 'ler şuna benzer bir dosya ile temsil edilebilir `data.json` :

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a>Şablonu kullanarak örnek

Farklı kediler ve köpekler için yüksekliklerde ve ağırlıklarla küçük bir veri kümeniz olduğunu varsayalım. Bu veri kümesi, bir modeli eğitmek için çok küçüktür, ancak bir veri kümesini yükleme işlemini göstermek için yeterli olacaktır.

| Yükseklik (a) | Ağırlık (kg) | Hayvan |
|-----------|------------|--------|
| 0,54      | 30         | Li    |
| 0,30      | 8          | Kedi    |
| 0,91      | 44         | Li    |
| 0,86      | 31          | Li    |
| 0,32      | 5         | Kedi    |
| 0,25      | 4          | Kedi    |

İşlem şu şekilde yapılır:

- İlk olarak veri kümesini eğitim ve doğrulamaya ayırdık. Bu durumda, eğitim için ilk üç örneği ve doğrulama için geri kalan örnekleri ele alabiliriz. Genel olarak, eğitim verilerinde istenmeyen verileri önlemek için rastgele eğitim ve doğrulama veri kümesini örneklemek iyi bir uygulamadır.
- İkinci olarak, her sınıfa bir sayısal etiket atamamız gerekir. Bu, şu anda QML kitaplığı 'nın yalnızca ikili sınıflandırma sorunlarını admits olduğunu unutmayın. Bu nedenle, 0 etiketini sınıfa `Dog` ve 1 numaralı numarayı sınıfa atayacağız `Cat` .
- Son olarak, veri kümenizdeki verileri kullanarak şablonu doldurduk. Büyük veri kümeleri için, belirli bir veri kümenizdeki şablonu otomatik olarak oluşturmak üzere küçük bir betik oluşturmanız gerektiğini unutmayın. Bu betik, veri kümenizin orijinal biçimine bağlı olacaktır.

Veri kümeniz için `data.json` dosya şu şekilde olur:

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a>Veriyi yükleme

Verileriniz bir JSON dosyası olarak serileştirildikten sonra, seçtiğiniz ana bilgisayar diliyle birlikte gelen JSON kitaplıklarını kullanarak yükleyebilirsiniz.

### <a name="python"></a>[Python](#tab/tabid-python)

Python, JSON seri hale getirilmiş verilerle çalışmaya yönelik [yerleşik `json` paketi](https://docs.python.org/3.7/library/json.html) sağlar:

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[C#](#tab/tabid-csharp)

.NET Core platformu, JSON seri hale getirilmiş verilerle çalışmaya yönelik [ `System.Text.Json` paketi](https://www.nuget.org/packages/System.Text.Json) sağlar:

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a>Sonraki adımlar

Artık kendi veri kümelerinizde kendi denemeleri çalıştırmaya başlamaya hazırsınız. Farklı sınıflandırıcıları ve veri kümelerini deneyin ve sonuçlarınızı paylaşan topluluğa katkıda bulunun!
