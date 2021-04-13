---
title: Solucionar problemas no Microsoft Defender para Ponto de Extremidade no Android
description: Solucionar problemas do Microsoft Defender para Ponto de Extremidade no Android
keywords: microsoft, defender, atp, mde, android, cloud, connectivity, communication
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1a19582073565a958aab444541381f5772b6f4f1
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687598"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a>Solução de problemas no Microsoft Defender para Ponto de Extremidade no Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Ao fazer a integração de um dispositivo, você pode ver problemas de entrada após a instalação do aplicativo.

Durante a integração, você pode encontrar problemas de entrada após a instalação do aplicativo em seu dispositivo.

Este artigo fornece soluções para ajudar a resolver os problemas de login.  

## <a name="sign-in-failed---unexpected-error"></a>Falha ao entrar - erro inesperado
**Falha ao entrar:** *Erro inesperado, tente mais tarde*

![Imagem de erro de falha de login Erro inesperado](images/f9c3bad127d636c1f150d79814f35d4c.png)

**Mensagem:**

Erro inesperado, tente mais tarde

**Causa:**

Você tem uma versão mais antiga do aplicativo "Microsoft Authenticator" instalada em seu dispositivo.

**Solução:**

Instalar a versão mais recente e o [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) na Google Play Store e tentar novamente

## <a name="sign-in-failed---invalid-license"></a>Falha ao entrar - licença inválida

**Falha ao entrar:** *Licença inválida, entre em contato com o administrador*

![Falha na imagem de entrar, entre em contato com o administrador](images/920e433f440fa1d3d298e6a2a43d4811.png)

**Mensagem:** *Licença inválida, entre em contato com o administrador*

**Causa:**

Você não tem a licença do Microsoft 365 atribuída ou sua organização não tem uma licença para a assinatura do Microsoft 365 Enterprise.

**Solução:**

Entre em contato com o administrador para obter ajuda.

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a>Páginas de phishing não são bloqueadas em alguns dispositivos OEM

**Aplica-se a:** Somente OEMs específicos

-   **Xiaomi**

Phishing e ameaças na Web prejudiciais detectadas pelo Defender para Ponto de Extremidade para Android não são bloqueadas em alguns dispositivos Xiaomi. A funcionalidade a seguir não funciona nesses dispositivos.

![Imagem do site relatada não segura](images/0c04975c74746a5cdb085e1d9386e713.png)


**Causa:**

Os dispositivos Xiaomi incluem um novo modelo de permissão. Isso impede que o Defender para Ponto de Extremidade para Android ex displaye janelas pop-up enquanto ele é executado em segundo plano.

Permissão de dispositivos Xiaomi: "Exibir janelas pop-up durante a execução em segundo plano".

![Imagem da configuração pop-up](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

**Solução:**

Habilita a permissão necessária em dispositivos Xiaomi.

- Exibir janelas pop-up durante a execução em segundo plano.
