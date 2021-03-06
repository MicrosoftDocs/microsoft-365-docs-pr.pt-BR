---
title: Solucionar problemas no Microsoft Defender para Ponto de Extremidade no Android
description: Solucionar problemas do Microsoft Defender para Ponto de Extremidade no Android
keywords: microsoft, defender, Microsoft Defender for Endpoint, mde, android, cloud, connectivity, communication
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
ms.openlocfilehash: 18afd4aa160ec345839d23719d1b3fcce21654ec
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246351"
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

Instale a versão mais recente e [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) da Google Play Store e tente novamente

## <a name="sign-in-failed---invalid-license"></a>Falha ao entrar - licença inválida

**Falha ao entrar:** *Licença inválida, entre em contato com o administrador*

![Falha na imagem de entrar, entre em contato com o administrador](images/920e433f440fa1d3d298e6a2a43d4811.png)

**Mensagem:** *Licença inválida, entre em contato com o administrador*

**Causa:**

Você não tem uma Microsoft 365 atribuída, ou sua organização não tem uma licença para Microsoft 365 Enterprise assinatura.

**Solução:**

Entre em contato com o administrador para obter ajuda.

## <a name="report-unsafe-site"></a>Relatar site não seguro

Sites de phishing personificam sites confiáveis com o objetivo de obter suas informações pessoais ou financeiras. Visite a [página Fornecer comentários sobre a](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) proteção de rede se quiser relatar um site que pode ser um site de phishing.

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
