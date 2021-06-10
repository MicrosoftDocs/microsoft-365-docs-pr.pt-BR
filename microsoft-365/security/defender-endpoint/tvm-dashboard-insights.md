---
title: Insights do painel - Gerenciamento de Ameaças e Vulnerabilidades
description: O Gerenciamento de Ameaças e Vulnerabilidades painel pode ajudar os administradores de segurança e SecOps a lidar com ameaças de segurança cibernética e criar a resiliência de segurança de sua organização.
keywords: Microsoft Defender para Endpoint-tvm, Painel do Microsoft Defender para Endpoint-tvm, ameaças & Gerenciamento de Vulnerabilidades, Gerenciamento de Ameaças e Vulnerabilidades, ameaças baseadas em risco & Gerenciamento de Vulnerabilidades, configuração de segurança, Pontuação Segura da Microsoft para Dispositivos, pontuação de exposição
search.appverid: met150
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 82b6123a99eb406918708c6bf23b870ef3bc3d79
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934136"
---
# <a name="dashboard-insights---threat-and-vulnerability-management"></a>Insights do painel - Gerenciamento de Ameaças e Vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Ameaça e Gerenciamento de Vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

A ameaça e Gerenciamento de Vulnerabilidades é um componente do Defender para Ponto de Extremidade e fornece aos administradores de segurança e equipes de operações de segurança um valor exclusivo, incluindo:


- Percepções de detecção e resposta do ponto de extremidade (EDR) em tempo real correlacionados a vulnerabilidades de ponto de extremidade
- Contexto de vulnerabilidade de dispositivo inestimável durante investigações de incidentes
- Processos internos de correção por meio Microsoft Intune e Microsoft Endpoint Configuration Manager  
  
Você pode usar o recurso Gerenciamento de Ameaças e Vulnerabilidades [de](https://securitycenter.windows.com/) Central de Segurança do Microsoft Defender para:

- Exibir a pontuação de exposição e a Pontuação Segura da Microsoft para Dispositivos, juntamente com as principais recomendações de segurança, vulnerabilidade de software, atividades de correção e dispositivos expostos
- Correlacionar EDR informações com vulnerabilidades de ponto de extremidade e processá-las
- Selecione opções de correção para triagem e rastrear as tarefas de correção
- Selecione opções de exceção e acompanhe exceções ativas

> [!NOTE]
> Os dispositivos que não estão ativos nos últimos 30 dias não são fatorados nos dados que refletem a pontuação de exposição Gerenciamento de Ameaças e Vulnerabilidades da sua organização e a Pontuação Segura da Microsoft para Dispositivos.

Assista a este vídeo para uma visão geral rápida do que está no painel Gerenciamento de Ameaças e Vulnerabilidades painel.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r1nv]

## <a name="threat-and-vulnerability-management-dashboard"></a>Painel de ameaças e Gerenciamento de Vulnerabilidades de segurança

 ![Portal do Microsoft Defender para Ponto de Extremidade](images/tvm-dashboard-devices.png)

Área | Descrição
:---|:---
**Grupos de dispositivos selecionados (#/#)**   | Filtre os Gerenciamento de Ameaças e Vulnerabilidades dados que você deseja ver no painel e cartões por grupos de dispositivos. O que você selecionar no filtro se aplica a todas as Gerenciamento de Ameaças e Vulnerabilidades.
[**Pontuação de exposição**](tvm-exposure-score.md)   | Consulte o estado atual da exposição de dispositivos da sua organização a ameaças e vulnerabilidades. Vários fatores afetam a pontuação de exposição da sua organização: pontos fracos descobertos em seus dispositivos, probabilidade de que seus dispositivos sejam violados, o valor dos dispositivos para sua organização e alertas relevantes descobertos com seus dispositivos. O objetivo é reduzir a pontuação de exposição da sua organização para ser mais segura. Para reduzir a pontuação, você precisa resolver os problemas de configuração de segurança relacionados listados nas recomendações de segurança.
[**Microsoft Secure Score para dispositivos**](tvm-microsoft-secure-score-devices.md) | Consulte a postura de segurança do sistema operacional, aplicativos, rede, contas e controles de segurança da sua organização. O objetivo é resolver os problemas de configuração de segurança relacionados para aumentar sua pontuação para dispositivos. Selecionar as barras o levará à página **Recomendação de** segurança.
**Distribuição de exposição de dispositivo** | Veja quantos dispositivos são expostos com base no nível de exposição. Selecione uma seção no gráfico de  roscas para ir até a página de lista Dispositivos e exibir os nomes de dispositivo afetados, o nível de exposição, o nível de risco e outros detalhes, como domínio, plataforma do sistema operacional, seu estado de saúde, quando foi visto pela última vez e suas marcas.
**Principais recomendações de segurança** | Consulte as recomendações de segurança coladas que são organizadas e priorizadas com base na exposição de risco da sua organização e na urgência necessária. Selecione **Mostrar mais** para ver o restante das recomendações de segurança na lista. Selecione **Mostrar exceções** para a lista de recomendações que têm uma exceção.
**Principais softwares vulneráveis** | Obter visibilidade em tempo real do inventário de software da sua organização com uma lista classificada em pilha de softwares vulneráveis instalados nos dispositivos da rede e como eles impactam sua pontuação de exposição organizacional. Selecione um item para obter detalhes ou **Mostrar mais** para ver o restante da lista de softwares vulneráveis na página **Inventário de** software.
**Principais atividades de correção** | Acompanhe as atividades de correção geradas a partir das recomendações de segurança. Você pode selecionar cada item na lista para ver os detalhes na página **Correção** ou selecionar **Mostrar** mais para exibir o restante das atividades de correção e exceções ativas.
**Principais dispositivos expostos** | Exibir nomes de dispositivos expostos e seu nível de exposição. Selecione um nome de dispositivo na lista para ir até a página do dispositivo onde você pode exibir os alertas, riscos, incidentes, recomendações de segurança, software instalado e vulnerabilidades descobertas associadas aos dispositivos expostos. Selecione **Mostrar mais** para ver o restante da lista de dispositivos expostos. Na lista de dispositivos, você pode gerenciar marcas, iniciar investigações automatizadas, iniciar uma sessão de resposta ao vivo, coletar um pacote de investigação, executar a verificação antivírus, restringir a execução do aplicativo e isolar o dispositivo.

Para obter mais informações sobre os ícones usados em todo o portal, consulte [Microsoft Defender for Endpoint icons](portal-overview.md#microsoft-defender-for-endpoint-icons).


## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral Gerenciamento de Vulnerabilidades ameaça](next-gen-threat-and-vuln-mgt.md)
- [Pontuação de exposição](tvm-exposure-score.md)
- [Microsoft Secure Score para dispositivos](tvm-microsoft-secure-score-devices.md)
- [Recomendações de segurança](tvm-security-recommendation.md)
- [Inventário de software](tvm-software-inventory.md)
- [Cronograma do evento](threat-and-vuln-mgt-event-timeline.md)

