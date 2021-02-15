---
title: Executar seu projeto piloto do Microsoft 365 Defender
description: Execute seu projeto piloto do Microsoft 365 Defender em produção para determinar efetivamente os benefícios e a adoção do Microsoft 365 Defender.
keywords: Piloto da Proteção contra Ameaças da Microsoft, execute o projeto piloto da Proteção contra Ameaças da Microsoft, avalie a Proteção contra Ameaças da Microsoft em produção, projeto piloto da Proteção contra Ameaças da Microsoft, segurança cibernética, ameaça persistente avançada, segurança corporativa, dispositivos, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, busca avançada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 9c0635058539e464a76f1720f041c205a05fa9b2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933025"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Executar seu projeto piloto do Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender


Este guia ajuda você a executar um projeto piloto fornecendo ponteiros para garantir que você tenha um plano bem estruturado, orientando você pelo uso do recurso de simulação de ataque e, por fim, concluindo o piloto com as principais dicas para refletir e documentar os resultados.

![Fases da execução de um piloto do Microsoft 365 Defender](../../media/pilotphases.png)


Executar um piloto ajuda você a determinar efetivamente o benefício de adotar o Microsoft 365 Defender. Antes de ativar o Microsoft 365 Defender em seu ambiente de produção e iniciar seus casos de uso, é melhor planejar a determinação das tarefas a realizar para seu projeto piloto e definir os critérios de sucesso. 


## <a name="how-to-use-this-pilot-playbook"></a>Como usar este manual piloto

Este guia fornece uma visão geral do Microsoft 365 Defender e instruções passo a passo sobre como configurar seu projeto piloto. 

O Microsoft 365 Defender é um pacote unificado de defesa empresarial pré e pós-violação que coordena na verdade a proteção, a detecção, a prevenção, a investigação e a resposta entre pontos de extremidade, identidades, email e aplicativos para fornecer proteção integrada contra ataques sofisticados. Ele faz isso combinando e orquestrando os seguintes recursos em uma única solução de segurança:
  - Microsoft Defender para Ponto de Extremidade, o novo nome da Proteção Avançada contra Ameaças do Microsoft Defender (pontos de extremidade)
  - Microsoft Defender para Office 365, o novo nome do Office 365 ATP (email) 
  - Microsoft Defender for Identity, o novo nome da ATP do Azure (identidade) 
  - Microsoft Cloud App Security (aplicativos)

![Image of_Microsoft 365 Defender solution for users, Microsoft Defender for Identity, for endpoints Microsoft Defender for Endpoint, for cloud apps, Microsoft Cloud App Security, and for data, Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

Com a solução integrada do Microsoft 365 Defender, os profissionais de segurança podem unir os sinais de ameaça que o Microsoft Defender para Ponto de Extremidade, o Microsoft Defender para Office 365, o Microsoft Defender para Identidade e o Microsoft Cloud App Security recebem e determinar o escopo completo e o impacto da ameaça, como ela entrou no ambiente, o que é afetado e como ela está afetando a organização no momento. O Microsoft 365 Defender faz uma ação automática para impedir ou parar o ataque e auto-recuperar caixas de correio afetadas, pontos de extremidade e identidades de usuário. Consulte a [visão geral do Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) para obter detalhes.



A linha do tempo de exemplo a seguir varia dependendo de ter os recursos certos em seu ambiente. Algumas detecções e fluxos de trabalho podem precisar de mais tempo de aprendizagem do que os outros.

![Linha do tempo de exemplo na execução de um piloto do Microsoft 365 Defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>Para obter os melhores resultados, siga as instruções do piloto o mais próximo possível.


### <a name="pilot-playbook-phases"></a>Fases do manual piloto 

Há quatro fases na execução de um piloto do Microsoft 365 Defender:

|Fase | Descrição | 
|:-------|:-----|
| [Planejamento](mtp-pilot-plan.md)<br> ~ 1 dia| Saiba o que você precisa considerar antes de executar seu projeto piloto do Microsoft 365 Defender: <br><br>- Escopo <br> - Casos de uso <br>- Requisitos <br>- Plano de teste <br> - Critérios de sucesso <br> - Scorecard 
| [Preparação](mtp-evaluation.md) <br>~2 dias|  Acesse a Central de Segurança do Microsoft 365 para configurar seu ambiente piloto do Microsoft 365 Defender. Você será orientado a:<br><br>- Identificar os participantes e buscar a aprovação para o seu piloto <br> - Considerações sobre o ambiente <br>- Acesso <br>- Configuração do Azure Active Directory <br> - Ordem de configuração <br> - Inscreva-se na avaliação do Microsoft 365 E5 <br> - Configurar domínio <br>- Atribuir licenças do Microsoft 365 E5 <br> – Conclua o assistente de configuração no portal|
| [Simulação de ataque](mtp-pilot-simulate.md) <br>~2 dias| Para simular um ataque, você será orientado a:<br><br>- Verificar os requisitos do ambiente de teste <br>- Executar a simulação <br>- Investigar um incidente <br>- resolver o incidente 
| [Fechamento e resumo](mtp-pilot-close.md) <br>~ 1 dia| Quando chegar ao final do processo, você será orientado a:<br><br>- Passar pela saída final<br>- Apresente sua saída aos stakeholders <br>- Fornecer comentários <br>- Tomar as próximas etapas 

## <a name="next-step"></a>Próxima etapa
|[Fase de planejamento](mtp-pilot-plan.md) | Planejar seu projeto piloto do Microsoft 365 Defender 
|:-------|:-----|
