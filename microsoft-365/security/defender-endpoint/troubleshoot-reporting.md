---
title: Solucionar problemas com ferramentas de relatórios para o Microsoft Defender AV
description: Identificar e resolver problemas comuns ao tentar relatar o status de proteção do Microsoft Defender AV no Update Compliance
keywords: solução de problemas, erro, correção, conformidade de atualização, oms, monitor, relatório, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 50136c620450861c41513650f27bf24fc782e968
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764526"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>Solucionar problemas de relatórios do Microsoft Defender Antivírus em Conformidade de Atualização

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> Em 31 de março de 2020, o recurso de relatório do Microsoft Defender Antivírus de Conformidade de Atualização será removido. Você pode continuar a definir e revisar políticas de conformidade de segurança usando o [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), o que permite um controle mais preciso sobre recursos e atualizações de segurança.

Você pode usar o Microsoft Defender Antivírus com Conformidade de Atualização. Você verá status para licenças E3, B, F1, VL e Pro. No entanto, para licenças do E5, você precisa usar o [portal do Microsoft Defender para Ponto de Extremidade.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) Para saber mais sobre opções de licenciamento, consulte Opções de licenciamento [de produto do Windows 10.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)

Quando você usa a Conformidade de Atualização do Windows Analytics para obter relatórios sobre o status de proteção de [dispositivos](/windows/deployment/update/update-compliance-using#wdav-assessment) ou pontos de extremidade em sua rede que estão usando o Microsoft Defender Antivírus, você pode encontrar problemas ou problemas.

Normalmente, os indicadores mais comuns de um problema são:
- Você só vê um pequeno número ou subconjunto de todos os dispositivos que você estava esperando ver
- Você não vê nenhum dispositivo
- Os relatórios e informações que você vê estão desatualizados (mais antigos do que alguns dias)

Para códigos de erro comuns e IDs de evento relacionadas ao serviço Microsoft Defender Antivírus que não estão relacionados à Conformidade de Atualização, consulte Eventos do [Microsoft Defender Antivírus](troubleshoot-microsoft-defender-antivirus.md). 

Há três etapas para solucionar esses problemas:

1. Confirme se você atendeu a todos os pré-requisitos
2. Verifique sua conectividade com o serviço Windows Defender baseado em nuvem
3. Enviar logs de suporte

>[!IMPORTANT]
>Normalmente, leva 3 dias para que os dispositivos comecem a aparecer em Conformidade de Atualização.


## <a name="confirm-prerequisites"></a>Confirmar pré-requisitos

Para que os dispositivos mostrem corretamente em Conformidade de Atualização, você precisa atender a determinados pré-requisitos para o serviço de Conformidade de Atualização e para o Microsoft Defender Antivírus:

>[!div class="checklist"]
>- Os pontos de extremidade estão usando o Microsoft Defender Antivírus como o único aplicativo de proteção antivírus. [O uso de qualquer outro aplicativo antivírus](microsoft-defender-antivirus-compatibility.md) fará com que o Microsoft Defender AV se desabilite e o ponto de extremidade não será relatado em Conformidade de Atualização.
> - [A proteção entregue na nuvem está habilitada](enable-cloud-protection-microsoft-defender-antivirus.md).
> - Os pontos de extremidade podem [se conectar à nuvem do Microsoft Defender AV](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - Se o ponto de extremidade estiver executando o Windows 10 versão 1607 ou anterior, os dados de diagnóstico do Windows 10 devem ser definidos para [o nível aprimorado](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).
> - Faz três dias que todos os requisitos foram atendidos

"Você pode usar o Microsoft Defender Antivírus com Conformidade de Atualização. Você verá status para licenças E3, B, F1, VL e Pro. No entanto, para licenças do E5, você precisa usar o portal do Microsoft Defender para Ponto de Extremidade ( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) . Para saber mais sobre opções de licenciamento, consulte Opções de licenciamento de produtos do Windows 10"

Se todos os pré-requisitos acima foram atendidos, talvez seja necessário prosseguir para a próxima etapa para coletar informações de diagnóstico e enviá-la para nós.

> [!div class="nextstepaction"]
> [Coletar dados de diagnóstico para solução de problemas de conformidade de atualização](collect-diagnostic-data.md)  

## <a name="related-topics"></a>Tópicos relacionados

- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Implantar o Microsoft Defender Antivírus](deploy-manage-report-microsoft-defender-antivirus.md)