---
title: Visão geral da integração do Microsoft Cloud App Security
ms.reviewer: ''
description: O Microsoft Defender para Ponto de Extremidade se integra ao Cloud App Security encaminhando todas as atividades de rede de aplicativos na nuvem.
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
ms.openlocfilehash: 5a5a81bde283a9eba4d5db77ed7e4c0b7567abc9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844725"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a>Microsoft Cloud App Security visão geral do Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Cloud App Security (Cloud App Security) é uma solução abrangente que dá visibilidade aos aplicativos e serviços de nuvem, permitindo controlar e limitar o acesso a aplicativos de nuvem, ao mesmo tempo em que aplica os requisitos de conformidade aos dados armazenados na nuvem. Para obter mais informações, [consulte Cloud App Security](/cloud-app-security/what-is-cloud-app-security).

>[!NOTE]
>Esse recurso está disponível com uma licença E5 para Enterprise Mobility + Security [em](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) dispositivos que executam Windows 10 versão 1809 ou posterior.

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a>Microsoft Defender para Endpoint e Cloud App Security integração 

Cloud App Security descoberta depende de logs de tráfego na nuvem que estão sendo encaminhados para ele a partir de servidores proxy e firewall corporativos. O Microsoft Defender for Endpoint se integra ao Cloud App Security coletando e encaminhando todas as atividades de rede de aplicativos de nuvem, fornecendo visibilidade incomparável ao uso do aplicativo na nuvem. A funcionalidade de monitoramento é interna no dispositivo, fornecendo cobertura completa da atividade de rede.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


A integração fornece as seguintes melhorias principais para a descoberta Cloud App Security existente: 

- Disponível em todos os lugares – como a atividade de rede é coletada diretamente do ponto de extremidade, ela está disponível onde quer que o dispositivo esteja, na rede corporativa ou fora, pois não depende mais do tráfego roteado pelo firewall corporativo ou servidores proxy. 

- Funciona fora da caixa, nenhuma configuração necessária - Encaminhar logs de tráfego de nuvem para Cloud App Security requer configuração de servidor proxy e firewall. Com o Defender para Endpoint e Cloud App Security integração, não há nenhuma configuração necessária. Basta a opção Central de Segurança do Microsoft Defender configurações e você pode ir. 

- Contexto do dispositivo - Os logs de tráfego de nuvem não têm contexto de dispositivo. A atividade de rede do Defender for Endpoint é relatada com o contexto do dispositivo (qual dispositivo acessou o aplicativo de nuvem), para que você possa entender exatamente onde (dispositivo) a atividade de rede ocorreu, além de quem (usuário) a realizou. 

Para obter mais informações sobre descoberta na nuvem, consulte [Trabalhando com aplicativos descobertos.](/cloud-app-security/discovered-apps)

## <a name="related-topic"></a>Tópicos relacionados

- [Configurar a integração do Microsoft Cloud App Security](microsoft-cloud-app-security-config.md)
