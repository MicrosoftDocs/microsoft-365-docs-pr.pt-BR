---
title: Avaliar a proteção contra ameaças da Microsoft
description: Configure seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft para experimentar como a solução de proteção de ameaças coordenada projetada para proteger dispositivos, identidade, dados e aplicativos pode ajudar sua organização
keywords: Avaliação de proteção contra ameaças da Microsoft, experimente a proteção contra ameaças da Microsoft, avaliar a proteção contra ameaças da Microsoft, laboratório de avaliação de proteção contra ameaças da Microsoft, segurança da CyberSource, ameaça persistente avançada, segurança corporativa, dispositivos, dispositivo, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, busca avançada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: f6ee8147965a29b87d84690535116f096e4c6006
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049634"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a>Criar um ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft 

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

O objetivo de criar este ambiente de laboratório de avaliação é ilustrar os recursos abrangentes, integrados e inteligentes da proteção contra ameaças da Microsoft em detecção, prevenção, investigação e resposta que você pode usar em sua organização. 

Este guia orienta as etapas para iniciar a avaliação de proteção contra ameaças da Microsoft com base nos caminhos de implantação recomendados. O objetivo é ajudá-lo a configurar os serviços integrados de proteção contra ameaças da Microsoft em um ambiente de laboratório ou como uma verificação de conceito (VDC) ao apresentar aos tomadores de decisões da solução de segurança em sua organização. Quando você terminar de executar as simulações de ataque, investigação e resposta automatizadas e estiver satisfeito com os resultados, você pode implantá-lo em seu ambiente de produção com a ajuda dos profissionais de vendas técnicos ou especialistas da Microsoft em sua organização. 

Este guia ajudará você a:
- Configurar seu servidor de laboratório e computadores
- Configurar o Active Directory com usuários e grupos
- Configurar e configurar o Azure ATP, o Office ATP, o Microsoft defender ATP e o Microsoft Cloud app Security
- Configurar políticas locais para seu servidor e computadores
- Imitar um ataque de ameaça para gerar um incidente de teste ou alerta na proteção contra ameaças da Microsoft

>[!IMPORTANT]
>Para obter resultados ideais, siga as instruções de configuração do laboratório o mais próximo possível.


## <a name="deployment-phases"></a>Fases de implantação

Há três fases na criação de um ambiente de laboratório de avaliação do Microsoft Threat Protection e sua implantação:

|Fase | Descrição | 
|:-------|:-----|
| ![Fase 1: preparar](../../media/prepare.png)<br>[Fase 1: preparar](prepare-mtpeval.md)| Saiba o que você precisa considerar ao implantar a proteção contra ameaças da Microsoft em um ambiente de laboratório de avaliação: <br><br>– Participantes e aprovação <br> -Considerações de ambiente <br>– Acesso <br>-Configuração do Azure Active Directory <br> -Ordem de configuração
|  ![Fase 2: configuração](../../media/setup.png) <br>[Fase 2: configuração](setup-mtpeval.md)|  Siga as etapas iniciais para acessar a central de segurança do Microsoft 365 para configurar seu ambiente de laboratório de avaliação do Microsoft Threat Protection. Você será orientado para:<br><br>-Inscrever-se no Microsoft 365 E5 Trial <br>  -Configurar domínio<br>-Atribuir licenças do Microsoft 365 e5<br>– Concluir o assistente de configuração no portal|
|  ![Fase 3: configurar o & integrado](../../media/config-onboard.png) <br>[Fase 3: configurar o & integrado](config-mtpeval.md) | Configure cada pilar de proteção contra ameaças e pontos de extremidade integrados da Microsoft. Você será orientado para:<br><br>– Configurar a proteção avançada contra ameaças do Office 365<br>– Configurar o Microsoft Cloud app Security<br>– Configurar a proteção avançada contra ameaças do Azure<br>– Configurar a proteção avançada contra ameaças do Microsoft defender 


## <a name="in-scope"></a>No escopo

O seguinte é o escopo deste guia de ambiente de laboratório de avaliação:
-   Configurar o Azure Active Directory
-   Configurar a proteção contra ameaças da Microsoft
    -   Inscreva-se na versão de avaliação do Microsoft 365 e5
    -   Configurar domínio
    -   Atribuir licenças do Microsoft 365 e5
    -   Concluindo o assistente de configuração no portal
-   Configurar todos os pilares de proteção contra ameaças da Microsoft com base nas práticas recomendadas
    -   Proteção Avançada contra Ameaças do Office 365
    -   Proteção Avançada contra Ameaças do Azure
    -   Microsoft Cloud App Security
    -   Proteção avançada contra ameaças do Microsoft Defender

## <a name="out-of-scope"></a>Fora do escopo

Os itens a seguir estão fora do escopo deste guia de implantação:

-   Configuração de soluções de terceiros que podem ser integradas ao Microsoft defender ATP
-   Teste de penetração no ambiente de produção

## <a name="next-step"></a>Próxima etapa
|||
|:-------|:-----|
|![Fase 1: preparar](../../media/prepare.png) <br>[Fase 1: preparar](prepare-mtpeval.md) | Preparar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft
