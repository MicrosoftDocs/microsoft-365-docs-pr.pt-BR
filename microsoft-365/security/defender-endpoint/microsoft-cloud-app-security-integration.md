---
title: Visão geral da integração do Microsoft Cloud App Security
ms.reviewer: ''
description: O Microsoft Defender for Endpoint se integra ao Cloud App Security encaminhando todas as atividades de rede de aplicativos na nuvem.
keywords: nuvem, aplicativo, rede, visibilidade, uso
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
ms.topic: conceptual
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: d756c738f9f61638a9e7424aa3fdf639f8f02f2a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185594"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a>Visão geral do Microsoft Cloud App Security no Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

O Microsoft Cloud App Security (Cloud App Security) é uma solução abrangente que dá visibilidade a aplicativos e serviços de nuvem, permitindo controlar e limitar o acesso a aplicativos de nuvem, ao mesmo tempo em que aplica os requisitos de conformidade aos dados armazenados na nuvem. Para obter mais informações, consulte [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).

>[!NOTE]
>Esse recurso está disponível com uma licença E5 para [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) em dispositivos que executam o Windows 10 versão 1809 ou posterior.

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a>Integração do Microsoft Defender para Endpoint e Cloud App Security 

A descoberta do Cloud App Security baseia-se nos logs de tráfego na nuvem que estão sendo encaminhados a ela a partir de servidores proxy e firewall corporativos. O Microsoft Defender for Endpoint se integra ao Cloud App Security coletando e encaminhando todas as atividades de rede de aplicativos na nuvem, fornecendo visibilidade incomparável ao uso do aplicativo na nuvem. A funcionalidade de monitoramento é interna no dispositivo, fornecendo cobertura completa da atividade de rede.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


A integração fornece as seguintes melhorias principais para a descoberta existente do Cloud App Security: 

- Disponível em todos os lugares – como a atividade de rede é coletada diretamente do ponto de extremidade, ela está disponível onde quer que o dispositivo esteja, na rede corporativa ou fora, pois não depende mais do tráfego roteado pelo firewall corporativo ou servidores proxy. 

- Funciona fora da caixa, nenhuma configuração necessária - Encaminhar logs de tráfego de nuvem para o Cloud App Security requer configuração de firewall e servidor proxy. Com a integração do Defender para Endpoint e segurança do aplicativo na nuvem, não há nenhuma configuração necessária. Basta acariá-lo nas configurações do Centro de Segurança do Microsoft Defender e você pode ir. 

- Contexto do dispositivo - Os logs de tráfego de nuvem não têm contexto de dispositivo. A atividade de rede do Defender for Endpoint é relatada com o contexto do dispositivo (qual dispositivo acessou o aplicativo de nuvem), para que você possa entender exatamente onde (dispositivo) a atividade de rede ocorreu, além de quem (usuário) a realizou. 

Para obter mais informações sobre descoberta na nuvem, consulte [Trabalhando com aplicativos descobertos.](https://docs.microsoft.com/cloud-app-security/discovered-apps)

## <a name="related-topic"></a>Tópicos relacionados

- [Configurar a integração com o Microsoft Cloud App Security](microsoft-cloud-app-security-config.md)
