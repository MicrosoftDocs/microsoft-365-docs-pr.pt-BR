---
title: Execute seu projeto piloto do Microsoft 365 defender
description: Execute seu projeto piloto do Microsoft 365 defender em produção para determinar efetivamente os benefícios e a adoção do Microsoft 365 defender.
keywords: Piloto de proteção contra ameaças da Microsoft, executar o piloto de proteção contra ameaças da Microsoft, avaliar a proteção contra ameaças da Microsoft em produção, projeto piloto de proteção contra ameaças da Microsoft, segurança na CyberSource, ameaça persistente avançada, segurança corporativa, dispositivos, dispositivo, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, caça avançada
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
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 50f334a055a5bd974f9ea1f39c8fa38d44be9c26
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131217"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Execute seu projeto piloto do Microsoft 365 defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Para determinar efetivamente o benefício e a adoção do Microsoft 365 defender, você pode executar um projeto piloto. Antes de habilitar o Microsoft 365 defender em seu ambiente de produção e iniciar seus casos de uso, é melhor planejar determinar as tarefas a serem realizadas para o projeto piloto e definir os critérios de sucesso. 


## <a name="how-to-use-this-pilot-playbook"></a>Como usar este guia estratégico piloto

Este guia fornece uma visão geral do Microsoft 365 defender e instruções passo a passo sobre como configurar seu projeto piloto. 

O Microsoft 365 defender é um pacote de defesa unificado do Enterprise Defense, que coordena nativamente a proteção, detecção, prevenção, investigação e resposta entre os pontos de extremidade, as identidades, os emails e os aplicativos para fornecer proteção integrada contra ataques sofisticados. Isso é feito combinando e organizando os seguintes recursos em uma única solução de segurança:
  - Microsoft defender para ponto de extremidade, o novo nome da proteção avançada contra ameaças do Microsoft defender (pontos de extremidade)
  - Microsoft defender para Office 365, o novo nome do Office 365 ATP (email) 
  - Microsoft defender para identidade, o novo nome para o Azure ATP (identidade) 
  - Microsoft Cloud app Security (aplicativos)

![Image of_Microsoft 365 defender Solution for users, Microsoft defender para identidade, para pontos de extremidade Microsoft defender for Endpoint, para aplicativos de nuvem, segurança do aplicativo do Microsoft Cloud e para dados, Microsoft defender para Office 365](../../media/mtp/m365pillars.png)

Com a solução integrada do Microsoft 365 defender, os profissionais de segurança podem unir os sinais de ameaça que o Microsoft defender para ponto de extremidade, o Microsoft defender para Office 365, o Microsoft defender para identidade e o Microsoft Cloud app Security recebem, e determinar o escopo completo e o impacto da ameaça, como ele entrou no ambiente, o que é afetado e como ele está afetando a organização. O Microsoft 365 defender realiza ações automáticas para impedir ou interromper o ataque e a AutoCorreção de caixas de correio, pontos de extremidade e identidades de usuários afetados. Consulte a [visão geral do Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) para obter detalhes.

![Fases na execução de um piloto do Microsoft 365 defender](../../media/pilotphases.png)

A linha do tempo de exemplo a seguir varia de acordo com os recursos corretos em seu ambiente. Algumas detecções e fluxos de trabalho podem precisar de mais tempo de aprendizagem do que os outros.

![Linha do tempo de amostra na execução de um piloto do Microsoft 365 defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>Para obter resultados ideais, siga as instruções do piloto o mais próximo possível.


### <a name="pilot-playbook-phases"></a>Fases do manual do piloto 

Há quatro fases na execução de um piloto do Microsoft 365 defender:

|Fase | Descrição | 
|:-------|:-----|
| [Planejamento](mtp-pilot-plan.md)<br> aproximadamente 1 dia| Saiba o que você precisa considerar antes de executar o projeto piloto do Microsoft 365 defender: <br><br>-Escopo <br> – Casos de uso <br>- Requisitos <br>– Plano de teste <br> -Critérios de êxito <br> -Scorecard 
| [Preparação](mtp-evaluation.md) <br>~ 2 dias|  Acesse o centro de segurança do Microsoft 365 para configurar seu ambiente piloto do Microsoft 365 defender. Você será orientado para:<br><br>– Identificar os participantes e a aprovação de busca para o seu piloto <br> -Considerações de ambiente <br>– Acesso <br>-Configuração do Azure Active Directory <br> -Ordem de configuração <br> -Inscrever-se no Microsoft 365 E5 Trial <br> -Configurar domínio <br>-Atribuir licenças do Microsoft 365 e5 <br> – Concluir o assistente de configuração no portal|
| [Simulação de ataque](mtp-pilot-simulate.md) <br>~ 2 dias| Para simular um ataque, você será orientado a:<br><br>– Verificar os requisitos do ambiente de teste <br>– Executar a simulação <br>– Investigue um incidente <br>-resolver o incidente 
| [Fechamento e Resumo](mtp-pilot-close.md) <br>aproximadamente 1 dia| Quando você chegar ao final do processo, será orientado para:<br><br>-Passar pela saída final<br>-Apresentar sua saída para seus participantes <br>– Fornecer comentários <br>-Siga as próximas etapas 

## <a name="next-step"></a>Próxima etapa
|[Fase de planejamento](mtp-pilot-plan.md) | Planejar seu projeto piloto do Microsoft 365 defender 
|:-------|:-----|
