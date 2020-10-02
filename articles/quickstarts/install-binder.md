---
title: Q# ve Binder ile geliştirme
description: Binder kullanarak Q# uygulaması oluşturmayı öğrenin.
author: bradben
ms.author: v-benbra
ms.date: 9/03/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.binder
no-loc:
- Q#
- $$v
ms.openlocfilehash: f993a1145dd8c01045d4cc7cfd0c98efd574ea78
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836578"
---
# <a name="develop-with-no-locq-and-binder"></a>Q# ve Binder ile geliştirme

Jupyter Not Defterlerinizi çevrimiçi olarak çalıştırıp paylaşmak için Binder’ı kullanabilirsiniz.

## <a name="use-binder-with-the-microsoft-qdk-samples"></a>Binder’ı Microsoft QDK örnekleri ile kullanma

Binder’ı Microsoft QDK örneklerini kullanacak şekilde otomatik olarak yapılandırmak için:

1. Bir tarayıcı açın ve https://aka.ms/try-qsharp uygulamasını çalıştırın.
1. **Quantum geliştirme seti örnekleri** giriş sayfasında, kendi kuantum uygulama not defterlerinizi yazmak amacıyla IQ# kullanmayı öğrenmek için **Q# not defterine** tıklayın.

![QDK giriş sayfası](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a>Binder’ı kendi not defterlerinizle ve deponuzla kullanma

GitHub deponuzda zaten not defterleri varsa Binder’ı deponuzla çalışacak şekilde yapılandırabilirsiniz:

1. Deponuzun kökünde *Dockerfile* adlı bir dosya olduğundan emin olun. Dosyada en azından aşağıdaki satırlar bulunmalıdır:

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > IQ# uygulamasının en güncel sürümünü [Sürüm Notları](xref:microsoft.quantum.relnotes)’ndan doğrulayabilirsiniz.

    Dockerfile oluşturma hakkında daha fazla bilgi için [Dockerfile başvurusuna](https://docs.docker.com/engine/reference/builder/) göz atın.

2. Tarayıcınızdan [mybinder.org](https://mybinder.org) sayfasını açın.
3. Deponuzun adını **GitHub URL**’si (örneğin *Adım/Depom*) olarak girin ve **Başlat**’a tıklayın.

![MyBinder formu](~/media/mybinder.png)
    
## <a name="next-steps"></a>Sonraki adımlar

Binder ortamınızı ayarladığınıza göre şimdi [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.
