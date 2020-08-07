---
title: Klasik verileri yükleme
description: Microsoft Quantum Development Kit (QDK) ile bir sınıflandırıcı modeli eğitme için kendi veri kümenizi yüklemeyi öğrenin.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
no-loc:
- Q#
- $$v
ms.openlocfilehash: 26ba7411c9ade1d6c4b606e8c12c10ade18fc584
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868840"
---
# <a name="load-and-classify-your-own-datasets"></a><span data-ttu-id="69dda-103">Kendi veri kümelerinizi yükleyin ve sınıflandırın</span><span class="sxs-lookup"><span data-stu-id="69dda-103">Load and classify your own datasets</span></span>

<span data-ttu-id="69dda-104">Bu kısa öğreticide, bir sınıflandırıcı modelini hisse geliştirme kiti (QDK) ile eğiten kendi veri kümenizi nasıl yükleyeceğinizi öğreneceksiniz.</span><span class="sxs-lookup"><span data-stu-id="69dda-104">In this short tutorial, we are going to learn how to load your own dataset to train a classifier model with the Quantum Development Kit (QDK).</span></span>

<span data-ttu-id="69dda-105">Verilerinizi depolamak için [JSON dosyaları](https://en.wikipedia.org/wiki/JSON) gibi standartlaştırılmış bir serileştirme biçiminin kullanımını önemle öneririz.</span><span class="sxs-lookup"><span data-stu-id="69dda-105">We highly recommend the use of a standardized serialization format such as [JSON files](https://en.wikipedia.org/wiki/JSON) to store your data.</span></span>
<span data-ttu-id="69dda-106">Bu tür biçimler, Python ve .NET ekosistemi gibi farklı çerçeveler ile yüksek uyumluluk sunar.</span><span class="sxs-lookup"><span data-stu-id="69dda-106">Such formats offer high compatibility with different frameworks like Python and the .NET ecosystem.</span></span>
<span data-ttu-id="69dda-107">Özellikle, verileri yüklemek için şablonumuzu kullanmanızı öneririz. böylece kodu doğrudan örneklerden kopyalayabilir ve yapıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="69dda-107">In particular, we recommend using our template for loading the data, so that you can copy-paste the code directly from the samples.</span></span>

## <a name="template-for-loading-your-datasets"></a><span data-ttu-id="69dda-108">Veri kümelerinizi yüklemek için şablon</span><span class="sxs-lookup"><span data-stu-id="69dda-108">Template for loading your datasets</span></span>

<span data-ttu-id="69dda-109">Her bir örneğin _i $ $x $, $x _ {I2} $ ve $x _ {i3} $ $x $N = $2 $ (x, y) $ boyutunda bir eğitim veri kümeniz olduğunu varsayalım.</span><span class="sxs-lookup"><span data-stu-id="69dda-109">Suppose we have a training dataset $(x, y)$ of size $N=2$ where each instance $x_i$ of $x$ has three features: $x_{i1}$, $x_{i2}$ and $x_{i3}$.</span></span>
<span data-ttu-id="69dda-110">Doğrulama veri kümesi aynı yapıya sahiptir.</span><span class="sxs-lookup"><span data-stu-id="69dda-110">The validation dataset has the same structure.</span></span>
<span data-ttu-id="69dda-111">Bu datsets 'ler şuna benzer bir dosya ile temsil edilebilir `data.json` :</span><span class="sxs-lookup"><span data-stu-id="69dda-111">These datsets can be represented by a `data.json` file similar to the following:</span></span>

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

### <a name="example-using-the-template"></a><span data-ttu-id="69dda-112">Şablonu kullanarak örnek</span><span class="sxs-lookup"><span data-stu-id="69dda-112">Example using the template</span></span>

<span data-ttu-id="69dda-113">Farklı kediler ve köpekler için yüksekliklerde ve ağırlıklarla küçük bir veri kümeniz olduğunu varsayalım.</span><span class="sxs-lookup"><span data-stu-id="69dda-113">Suppose we have a small dataset with the heights and weights of different cats and dogs.</span></span> <span data-ttu-id="69dda-114">Bu veri kümesi, bir modeli eğitmek için çok küçüktür, ancak bir veri kümesini yükleme işlemini göstermek için yeterli olacaktır.</span><span class="sxs-lookup"><span data-stu-id="69dda-114">This dataset is very small to train a model but will be enough to show the process of loading a dataset.</span></span>

| <span data-ttu-id="69dda-115">Yükseklik (a)</span><span class="sxs-lookup"><span data-stu-id="69dda-115">Height (m)</span></span> | <span data-ttu-id="69dda-116">Ağırlık (kg)</span><span class="sxs-lookup"><span data-stu-id="69dda-116">Weight (kg)</span></span> | <span data-ttu-id="69dda-117">Hayvan</span><span class="sxs-lookup"><span data-stu-id="69dda-117">Animal</span></span> |
|-----------|------------|--------|
| <span data-ttu-id="69dda-118">0,54</span><span class="sxs-lookup"><span data-stu-id="69dda-118">0.54</span></span>      | <span data-ttu-id="69dda-119">30</span><span class="sxs-lookup"><span data-stu-id="69dda-119">30</span></span>         | <span data-ttu-id="69dda-120">Li</span><span class="sxs-lookup"><span data-stu-id="69dda-120">Dog</span></span>    |
| <span data-ttu-id="69dda-121">0,30</span><span class="sxs-lookup"><span data-stu-id="69dda-121">0.30</span></span>      | <span data-ttu-id="69dda-122">8</span><span class="sxs-lookup"><span data-stu-id="69dda-122">8</span></span>          | <span data-ttu-id="69dda-123">Kedi</span><span class="sxs-lookup"><span data-stu-id="69dda-123">Cat</span></span>    |
| <span data-ttu-id="69dda-124">0,91</span><span class="sxs-lookup"><span data-stu-id="69dda-124">0.91</span></span>      | <span data-ttu-id="69dda-125">44</span><span class="sxs-lookup"><span data-stu-id="69dda-125">44</span></span>         | <span data-ttu-id="69dda-126">Li</span><span class="sxs-lookup"><span data-stu-id="69dda-126">Dog</span></span>    |
| <span data-ttu-id="69dda-127">0,86</span><span class="sxs-lookup"><span data-stu-id="69dda-127">0.86</span></span>      | <span data-ttu-id="69dda-128">31</span><span class="sxs-lookup"><span data-stu-id="69dda-128">31</span></span>          | <span data-ttu-id="69dda-129">Li</span><span class="sxs-lookup"><span data-stu-id="69dda-129">Dog</span></span>    |
| <span data-ttu-id="69dda-130">0,32</span><span class="sxs-lookup"><span data-stu-id="69dda-130">0.32</span></span>      | <span data-ttu-id="69dda-131">5</span><span class="sxs-lookup"><span data-stu-id="69dda-131">5</span></span>         | <span data-ttu-id="69dda-132">Kedi</span><span class="sxs-lookup"><span data-stu-id="69dda-132">Cat</span></span>    |
| <span data-ttu-id="69dda-133">0,25</span><span class="sxs-lookup"><span data-stu-id="69dda-133">0.25</span></span>      | <span data-ttu-id="69dda-134">4</span><span class="sxs-lookup"><span data-stu-id="69dda-134">4</span></span>          | <span data-ttu-id="69dda-135">Kedi</span><span class="sxs-lookup"><span data-stu-id="69dda-135">Cat</span></span>    |

<span data-ttu-id="69dda-136">İşlem şu şekilde yapılır:</span><span class="sxs-lookup"><span data-stu-id="69dda-136">The process is:</span></span>

- <span data-ttu-id="69dda-137">İlk olarak veri kümesini eğitim ve doğrulamaya ayırdık.</span><span class="sxs-lookup"><span data-stu-id="69dda-137">First we need to separate the dataset into training and validation.</span></span> <span data-ttu-id="69dda-138">Bu durumda, eğitim için ilk üç örneği ve doğrulama için geri kalan örnekleri ele alabiliriz.</span><span class="sxs-lookup"><span data-stu-id="69dda-138">In this case we can just take the first three samples for training and the rest of samples for validation.</span></span> <span data-ttu-id="69dda-139">Genel olarak, eğitim verilerinde istenmeyen verileri önlemek için rastgele eğitim ve doğrulama veri kümesini örneklemek iyi bir uygulamadır.</span><span class="sxs-lookup"><span data-stu-id="69dda-139">In general it is a good practice to sample randomly the training and validation dataset to avoid unwanted biases in the training data.</span></span>
- <span data-ttu-id="69dda-140">İkinci olarak, her sınıfa bir sayısal etiket atamamız gerekir.</span><span class="sxs-lookup"><span data-stu-id="69dda-140">Secondly, we need to assign a numeric label to each class.</span></span> <span data-ttu-id="69dda-141">Bu, şu anda QML kitaplığı 'nın yalnızca ikili sınıflandırma sorunlarını admits olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="69dda-141">Note that, for the moment, the QML library only admits binary classification problems.</span></span> <span data-ttu-id="69dda-142">Bu nedenle, 0 etiketini sınıfa `Dog` ve 1 numaralı numarayı sınıfa atayacağız `Cat` .</span><span class="sxs-lookup"><span data-stu-id="69dda-142">So we will assign the label 0 to the class `Dog` and the number 1 to the class `Cat`.</span></span>
- <span data-ttu-id="69dda-143">Son olarak, veri kümenizdeki verileri kullanarak şablonu doldurduk.</span><span class="sxs-lookup"><span data-stu-id="69dda-143">Finally, we fill the template using the data from our dataset.</span></span> <span data-ttu-id="69dda-144">Büyük veri kümeleri için, belirli bir veri kümenizdeki şablonu otomatik olarak oluşturmak üzere küçük bir betik oluşturmanız gerektiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="69dda-144">Note that for big datasets you should build a small script to automatically generate the template from your specific dataset.</span></span> <span data-ttu-id="69dda-145">Bu betik, veri kümenizin orijinal biçimine bağlı olacaktır.</span><span class="sxs-lookup"><span data-stu-id="69dda-145">This script will depend on the original format of your dataset.</span></span>

<span data-ttu-id="69dda-146">Veri kümeniz için `data.json` dosya şu şekilde olur:</span><span class="sxs-lookup"><span data-stu-id="69dda-146">For our dataset the `data.json` file is:</span></span>

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

## <a name="loading-the-data"></a><span data-ttu-id="69dda-147">Veriyi yükleme</span><span class="sxs-lookup"><span data-stu-id="69dda-147">Loading the data</span></span>

<span data-ttu-id="69dda-148">Verileriniz bir JSON dosyası olarak serileştirildikten sonra, seçtiğiniz ana bilgisayar diliyle birlikte gelen JSON kitaplıklarını kullanarak yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="69dda-148">Once you have your data serialized as a JSON file, you can load it in using JSON libraries provided with your host language of choice.</span></span>

### <a name="python"></a>[<span data-ttu-id="69dda-149">Python</span><span class="sxs-lookup"><span data-stu-id="69dda-149">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="69dda-150">Python, JSON seri hale getirilmiş verilerle çalışmaya yönelik [yerleşik `json` paketi](https://docs.python.org/3.7/library/json.html) sağlar:</span><span class="sxs-lookup"><span data-stu-id="69dda-150">Python provides the [built-in `json` package](https://docs.python.org/3.7/library/json.html) for working with JSON-serialized data:</span></span>

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[<span data-ttu-id="69dda-151">C#</span><span class="sxs-lookup"><span data-stu-id="69dda-151">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="69dda-152">.NET Core platformu, JSON seri hale getirilmiş verilerle çalışmaya yönelik [ `System.Text.Json` paketi](https://www.nuget.org/packages/System.Text.Json) sağlar:</span><span class="sxs-lookup"><span data-stu-id="69dda-152">The .NET Core platform provides the [`System.Text.Json` package](https://www.nuget.org/packages/System.Text.Json) for working with JSON-serialized data:</span></span>

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a><span data-ttu-id="69dda-153">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="69dda-153">Next steps</span></span>

<span data-ttu-id="69dda-154">Artık kendi veri kümelerinizde kendi denemeleri çalıştırmaya başlamaya hazırsınız.</span><span class="sxs-lookup"><span data-stu-id="69dda-154">Now you are ready to start running your own experiments with your own datasets.</span></span> <span data-ttu-id="69dda-155">Farklı sınıflandırıcıları ve veri kümelerini deneyin ve sonuçlarınızı paylaşan topluluğa katkıda bulunun!</span><span class="sxs-lookup"><span data-stu-id="69dda-155">Try different classifiers and dataset and contribute to the community sharing your results!</span></span>
