---
title: Configurar a integração com o Microsoft Cloud App Security
ms.reviewer: ''
description: Saiba como ativar as configurações para habilitar a integração do Microsoft Defender for Endpoint com o Microsoft Cloud App Security.
keywords: nuvem, aplicativo, segurança, configurações, integração, descoberta, relatório
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ddf32b26191826ab6ecbad6b9d047ac7bbb6276a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054478"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>Configurar o Microsoft Cloud App Security no Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Para se beneficiar dos sinais de descoberta de aplicativos de nuvem do Microsoft Defender para Endpoint, a ligue a integração com o Microsoft Cloud App Security.

>[!NOTE]
>Esse recurso estará disponível com uma licença E5 para [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) em dispositivos que executam o Windows 10, versão 1709 (Com build do sistema operacional 16299.1085 com [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, versão 1803 (build 17134.704 do sistema operacional com [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, versão 1809 (build 17763.379 do sistema operacional com [KB4489899](https://support.microsoft.com/help/4489899)) ou versões posteriores do Windows 10.

> Consulte [Integração do Microsoft Defender para Ponto](https://docs.microsoft.com/cloud-app-security/mde-integration) de Extremidade com o Microsoft Cloud App Security para integração detalhada do Microsoft Defender para Ponto de Extremidade com o Microsoft Cloud App Security. 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>Habilitar o Microsoft Cloud App Security no Microsoft Defender para Ponto de Extremidade

1. No painel de navegação, selecione **Configuração de preferências**  >  **Recursos avançados**.
2. Selecione **Microsoft Cloud App Security** e alterne a alternância para **On**.
3. Clique **em Salvar preferências**.

Depois de ativado, o Microsoft Defender para Ponto de Extremidade começará imediatamente a encaminhar sinais de descoberta para o Cloud App Security.

## <a name="view-the-data-collected"></a>Exibir os dados coletados

Para exibir e acessar dados do Microsoft Defender para Endpoint no Microsoft Cloud Apps Security, consulte [Investigar dispositivos em Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).


Para obter mais informações sobre descoberta na nuvem, consulte [Trabalhando com aplicativos descobertos.](https://docs.microsoft.com/cloud-app-security/discovered-apps)

Se você estiver interessado em tentar o Microsoft Cloud App Security, consulte [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).

## <a name="related-topic"></a>Tópicos relacionados
- [Integração com o Microsoft Cloud App Security](microsoft-cloud-app-security-integration.md)
