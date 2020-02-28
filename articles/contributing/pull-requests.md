---
title: Çekme istekleri açılıyor
description: Microsoft Quantum Development Kit kod veya belge katkıda bulunmak için hazırsanız GitHub çekme isteği göndermeyi öğrenin.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: a4373a65688893c95e0475356c8f6fca0912f8c5
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907469"
---
# <a name="opening-pull-requests"></a>Çekme İsteklerini Açma #

Hisse geliştirme kiti için tüm belgeler, GitHub 'da barındırılan birkaç depo kullanılarak git sürüm denetim sistemi kullanılarak yönetilir.
Git ve GitHub 'ın birlikte kullanılması, hisse geliştirme setinde büyük ölçüde işbirliği yapmayı kolaylaştırır.
Özellikle, bu deponun tamamen bağımsız bir kopyasını oluşturmak için herhangi bir git deposu kopyalanabilir veya eklenebilir.
Bu, araçlarla ve tercih ettiğiniz bir hızda katkılarınız üzerinde çalışmanıza olanak sağlar.

Hazırsanız, GitHub 'ın _çekme isteği_ işlevselliğini kullanarak katkılarımıza katkılarınızı dahil etmek için bize bir istek gönderebilirsiniz.
Her çekme isteğinin sayfasında katkılarınızı oluşturan tüm değişikliklerin ayrıntıları, katkılarınız üzerinde bir açıklama listesi ve topluluğun diğer üyelerinin geri bildirim ve öneri sağlamak için kullanabileceği bir gözden geçirme araçları bulunur.

> [!NOTE]
> Git ile ilgili bir tam öğretici bu kılavuzun kapsamı dışındadır, ancak öğrenme git hakkında daha fazla kaynak için aşağıdaki bağlantıları önerebiliriz:
>
> - [Git hakkında bilgi edinin](https://www.atlassian.com/git): atlasme 'Den bir git öğreticileri kümesi.
> - [Visual Studio Code sürüm denetimi](https://code.visualstudio.com/docs/editor/versioncontrol): GIT için guı olarak Visual Studio Code kullanma kılavuzu.
> - [GitHub Öğrenme Laboratuvarı](https://lab.github.com/): git, GitHub ve ilgili teknolojileri kullanmaya yönelik çevrimiçi kurslar kümesi.
> - [Git görselleştirme](https://git-school.github.io/visualizing-git/): git komutlarının bir deponun durumunu nasıl değiştirmelerini görselleştirmede etkileşimli bir araç.
> - [Git Ile sürüm denetimi (EPQSıS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): bilimsel bilgi işlem doğrultusunda bir git öğreticisi.
> - [Git dallandırmayı öğrenin](https://learngitbranching.js.org/): yeni git özellikleri hakkında bilgi edinmek için etkileşimli bir dallanma kümesi ve yeniden temellendirme bulmaca vs.

## <a name="what-is-a-pull-request"></a>Çekme Isteği nedir? ##

Yukarıdakileri söylediğinizde, bir çekme isteğinin ne **olduğunu**söylemek için birkaç dakika sürer.
Git ile çalışırken tüm değişiklikler, bu değişikliklerin, bu değişikliklerden önce deponun durumuyla nasıl ilişkili olduğunu betimleyen _işlemeler_ olarak gösterilir.
Genellikle yürütmelerin, önceki işlemelerden oklarla daireler olarak çizildiğini gösteren diyagramlar çizeceğiz.

`feature`adlı _dalda_ bir katkı başladığınızı varsayalım.
Bundan sonra **Microsoft/hisse** 'ın çatalınız şuna benzeyebilir:

![GitHub 'da çalışma dalı](~/media/git-workflow-step0.png)

Değişikliklerinizi yerel deponuzda yaparsanız, yukarı akış meydana gelen değişikliklere göre yakalamak için başka bir depodan yaptığınız değişiklikleri sizinkilerle _çekebilirsiniz_ .

![Yukarı akış deposundan değişiklikleri çekme ve birleştirme](~/media/git-workflow-step1.png)

Çekme istekleri aynı şekilde çalışır, ancak ters: bir çekme isteği açtığınızda, yukarı akış deposunun katkılarınızı çekmesini isteyebilirsiniz.

![Değişikliklerinizi özgün depoya geri çekmek istiyor](~/media/git-workflow-step2.png)

Depolarımızdan birine bir çekme isteği açtığınızda, GitHub, topluluklardaki başkalarının değişikliklerinizin bir özetini görmesini, bunlara yorum yapmasını ve daha da iyi bir katkı sunmanın yanı sıra yardımcı olma önerileri yapmasını sağlar.

![GitHub 'da çekme isteğinin ekran görüntüsü](~/media/pull-request-header.png)

Bu işlemi kullanmak, katkılarını geliştirmek ve hisse programlama topluluğu için yüksek kaliteli bir ürünü sürdürmek amacıyla GitHub işlevlerini kullanmamıza yardımcı olur.

## <a name="how-to-make-a-pull-request"></a>Çekme Isteği oluşturma ##

Çekme isteği oluşturmak için iki ana yol vardır.
Yalnızca tek bir dosyayı etkileyen küçük değişiklikler için GitHub Web arabirimi, çekme isteğini tamamen çevrimiçi hale getirmek için kullanılabilir.
Daha karmaşık katkılar için, öncelikle bir çekme isteğine hazırlanmak üzere yerel bilgisayarınızı kullanmak daha kolay olur.

<!--
### Using the Web Interface ###

**TODO**

### Command-Line and GitHub Flow ###

Most of the time, it's easier to prepare a pull request on your own computer; that makes it easier to work incrementally, and to test your changes.
If you haven't already done so, the first step is to _fork_ the repository that you'd like to contribute to.
Forking makes a complete clone of the original repository, but under your GitHub account instead of under [Microsoft](http://github.com/Microsoft/) or [MicrosoftDocs](http://github.com/MicrosoftDocs/).
This way, you can edit your personal fork to your heart's content before making a pull request for your work.

**TODO: pick up here**

## Code Review and Etiquette ##

**TODO: PR ettiquette, reviews, etc.**

-->

## <a name="next-steps"></a>Sonraki adımlar ##

GIT geliştirme seti topluluğu 'na yardımcı olmak için git kullanma hakkında Tebrikler!
Kodun nasıl katkıda bulunduğu hakkında daha fazla bilgi edinmek için lütfen aşağıdaki kılavuzla devam edin.

> [!div class="nextstepaction"]
> [Kod katkıda bulunma hakkında bilgi edinin](xref:microsoft.quantum.contributing.code)
