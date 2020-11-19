---
title: Planejando seu projeto piloto do Microsoft 365 defender
description: Planeje seu projeto piloto do Microsoft 365 defender com os participantes para gerenciar as expectativas e garantir o resultado bem-sucedido.
keywords: Piloto de proteção contra ameaças da Microsoft, plano piloto de proteção contra ameaças da Microsoft, avaliar a proteção contra ameaças da Microsoft em produção, projeto piloto de proteção contra ameaças da Microsoft, segurança na CyberSource, ameaça persistente avançada, segurança corporativa, dispositivos, dispositivo, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, caça avançada
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
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 649f3e777a330e1b60faf4f3513a470b51e56a80
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356974"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>Planejando seu projeto piloto do Microsoft 365 defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

|![Planejamento](../../media/phase-diagrams/1-planning.png)<br/>Planejamento|[![Preparar](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)<br/>[Preparação](prepare-mtpeval.md) | [![Simular ameaças](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)<br/>[Simular ameaças](mtp-pilot-simulate.md) | [![Fechar e resumir](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)<br/>[Fechar e resumir](mtp-pilot-close.md)|
|--|--|--|--|
|*Você está aqui!*| | | |

Você está atualmente na fase de planejamento.

Para garantir que seu projeto piloto seja um sucesso, é essencial planejar com detalhes e obter aprovações de seus participantes no início. Os elementos de planejamento incluem o escopo de identificação, casos de uso, requisitos e critérios de sucesso.

Este guia descreve como planejar o projeto piloto. 

>[!IMPORTANT]
>Para obter resultados ideais, siga as instruções do piloto o mais próximo possível.


## <a name="scope"></a>Escopo

O escopo do piloto determinará como o teste será amplo, com base no seu ambiente e nos métodos de teste aceitáveis. Estes são alguns exemplos de escopos a serem considerados:
- Ambiente de desenvolvimento ou teste, que inclui pontos de extremidade, servidores, controladores de domínio.
- Ambiente de produção com o Microsoft 365, Azure, serviços do Active Directory, pontos de extremidade e servidores

>[!NOTE]
>Se você ainda não tem as licenças completas, pode obter licenças de avaliação para [avaliar o Microsoft 365 defender](https://aka.ms/mtp-trial-lab) – planejar, preparar, configurar, configurar e executar o projeto piloto. Suas partes interessadas desempenharão uma grande função para ajudar a facilitar o processo de início ao fim.

Os tipos de sistemas operacionais a serem avaliados também devem ser definidos com base na composição organizacional. Isso pode incluir o seguinte: [pontos de extremidade Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [servidores Linux](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [pontos de extremidade do windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).

## <a name="use-cases"></a>Casos de uso

Os casos de uso representam instruções sobre como a ferramenta que está sendo testada deve ser consumida por seus usuários pretendidos. Eles podem ser formulados como histórias de usuários do ponto de vista de uma pessoa específica, como um analista do SOC. Por exemplo:
- Como analista da SOC, preciso exibir, correlacionar, avaliar e gerenciar alertas e eventos em dispositivos, usuários e caixas de correio em minha rede. [Gerenciamento de incidentes]
- Como analista do SOC, eu preciso ter a ferramenta e o processo para investigar e responder automaticamente a eventos mal-intencionados em minha rede. [Infravermelho automático]
- Como analista do SOC, eu preciso pesquisar dados do meu ambiente para encontrar ameaças conhecidas e potenciais e atividades suspeitas. [Caça avançada]

Tenha em mente que esses casos de uso devem ser criados dentro dos parâmetros do escopo definido. Se, por exemplo, o escopo de teste não incluir uma avaliação de ferramentas como o Microsoft Cloud app Security, os casos que dependem dele como uma fonte de dados não devem ser criados.

## <a name="requirements"></a>Requisitos

Na lista de casos de uso, você pode começar a criar requisitos. Os requisitos incluem recursos que uma ferramenta deve ter para satisfazer os casos de uso. Esses requisitos podem ser divididos em categorias como configuração e manutenção, suporte para integrações e requisitos específicos de recursos, como a capacidade de busca e a capacidade de criar alertas personalizados.

## <a name="test-plan"></a>Plano de teste

Dependendo dos requisitos, diferentes métodos de teste podem ser apropriados. Por exemplo, se o requisito é avaliar a eficácia da correção automatizada, o plano de teste precisa incluir etapas para gerar o (s) comportamento (es) que acionaria uma ação de correção automatizada no Microsoft 365 defender. Se o requisito for detectar um determinado comportamento ou ataque, o teste poderá envolver mais etapas. O ponto é ter um plano para fazer um teste com precisão em relação aos seus requisitos.

## <a name="success-criteria"></a>Critérios de sucesso

O critério de sucesso é, basicamente, a barra definida para medir o que você está testando. Se você estiver testando o Microsoft 365 defender (ou qualquer outra tecnologia para esse assunto) em relação a outras ferramentas ou por si só, deve haver alguns critérios quantificáveis para determinar o valor que a ferramenta fornece. Com base no escopo, nos requisitos e no plano de testes, o critério de sucesso determinará como o teste será pontuado. Isso deve ser inferior a uma passagem ou falhar e mais de uma pontuação ponderada com base nas suas necessidades. Por exemplo, para ter êxito, uma ferramenta pode precisar de uma pontuação acima de 80% em determinadas áreas críticas que você identificar.

## <a name="scorecard"></a>Scorecard

Uma maneira de reunir todos os elementos de seu plano pode ser criar um scorecard. Veja um exemplo de Scorecard abaixo:

| Caso de uso | Requisitos | Requisitos de configuração | Plano de teste | Resultado esperado | Status do teste | Pontuação | Observações |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|Gerenciamento de incidentes|-Microsoft 365 defender  </br></br>– Microsoft defender para identidade </br></br>– Microsoft defender para ponto de extremidade </br></br>– Segurança do aplicativo do Microsoft Cloud (opcional)|Consulte os [pré-requisitos](https://aka.ms/mtp-trial-lab) para preparação, configuração e configuração para obter detalhes |[Simular ameaças](mtp-pilot-simulate.md) <br></br>[Investigue o incidente](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |Os investigadores podem entender o escopo e o impacto do incidente e gerenciar o incidente||||
|AutoIR|-Microsoft 365 defender </br></br>– Microsoft defender para identidade </br></br>– Microsoft defender para ponto de extremidade |Consulte os [pré-requisitos](https://aka.ms/mtp-trial-lab) para preparação, configuração e configuração para obter detalhes <br>Habilitar AutoIR  |[Simular ameaças](mtp-pilot-simulate.md) <br></br>[Investigação automatizada](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#automated-investigation-and-remediation) |Alertas e incidentes são corrigidos automaticamente pelo Microsoft 365 defender||||
|Busca avançada|-Microsoft 365 defender </br></br>– Microsoft defender para ponto de extremidade </br></br>– Microsoft defender para Office 365 |Consulte os [pré-requisitos](https://aka.ms/mtp-trial-lab) para preparação, configuração e configuração para obter detalhes|[Cenário de busca avançada](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#advanced-hunting-scenario) |Os investigadores podem localizar dados por meio de busca avançada, dinamização para entidades impactadas e criação de detecções personalizadas||||



## <a name="next-step"></a>Próxima etapa
|![Fase de preparação](../../media/mtp/prep.png) <br>[Fase de preparação](prepare-mtpeval.md) | Prepare seu ambiente piloto do Microsoft 365 defender
|:-------|:-----|
