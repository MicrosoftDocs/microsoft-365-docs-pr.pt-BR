---
title: Executar seu projeto piloto do Microsoft 365 Defender
description: Execute seu projeto piloto do Microsoft 365 Defender em produção para determinar efetivamente os benefícios e a adoção do Microsoft 365 Defender.
keywords: Piloto da Proteção contra Ameaças da Microsoft, execute o projeto piloto da Proteção contra Ameaças da Microsoft, avalie a Proteção contra Ameaças da Microsoft em produção, projeto piloto da Proteção contra Ameaças da Microsoft, segurança cibernética, ameaças persistentes avançadas, segurança corporativa, dispositivos, dispositivos, identidade, usuários, dados, aplicativos, incidentes, investigação automatizada e correção, busca avançada
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
ms.openlocfilehash: c6c373d084c7f7cf12073c6402695af644944bad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910865"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Executar seu projeto piloto do Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender


Este guia ajuda você a executar um projeto piloto fornecendo ponteiros para garantir que você tenha um plano bem estruturado, orientando você usando o recurso de simulação de ataque e, finalmente, concluindo o piloto com as principais dicas para você refletir e documentar os resultados.

![Fases na execução de um piloto do Microsoft 365 Defender](../../media/pilotphases.png)


Executar um piloto ajuda você a determinar efetivamente o benefício de adotar o Microsoft 365 Defender. Antes de habilenciar o Microsoft 365 Defender em seu ambiente de produção e iniciar seus casos de uso, é melhor planejar a determinação das tarefas a realizar para seu projeto piloto e definir os critérios de sucesso. 


## <a name="how-to-use-this-pilot-playbook"></a>Como usar esse playbook piloto

Este guia fornece uma visão geral do Microsoft 365 Defender e instruções passo a passo sobre como configurar seu projeto piloto. 

O Microsoft 365 Defender é um pacote de defesa empresarial unificado pré e pós-violação que coordena a proteção, a detecção, a prevenção, a investigação e a resposta entre pontos de extremidade, identidades, email e aplicativos para fornecer proteção integrada contra ataques sofisticados. Ele faz isso combinando e orquestrando os seguintes recursos em uma única solução de segurança:
  - Microsoft Defender para Ponto de Extremidade, o novo nome para Proteção Avançada contra Ameaças do Microsoft Defender (pontos de extremidade)
  - Microsoft Defender para Office 365, o novo nome do Office 365 ATP (email) 
  - Microsoft Defender for Identity, o novo nome do Azure ATP (identidade) 
  - Microsoft Cloud App Security (aplicativos)

![Solução do Image of_Microsoft 365 Defender para usuários, Microsoft Defender for Identity, para pontos de extremidade Microsoft Defender para Ponto de Extremidade, para aplicativos de nuvem, Microsoft Cloud App Security e para dados, Microsoft Defender para Office 365](../../media/mtp/m365pillars.png)

Com a solução integrada do Microsoft 365 Defender, os profissionais de segurança podem unir os sinais de ameaça que o Microsoft Defender para Ponto de Extremidade, o Microsoft Defender para Office 365, o Microsoft Defender para Identidade e o Microsoft Cloud App Security recebem e determinam o escopo completo e o impacto da ameaça, como ela entrou no ambiente, o que ela é afetada e como ela está afetando a organização no momento. O Microsoft 365 Defender toma medidas automáticas para impedir ou interromper o ataque e a auto-recuperação de caixas de correio afetadas, pontos de extremidade e identidades de usuário. Consulte a [visão geral do Microsoft 365 Defender](./microsoft-threat-protection.md) para obter detalhes.



A linha do tempo de exemplo a seguir varia dependendo de ter os recursos certos em seu ambiente. Algumas detecções e fluxos de trabalho podem precisar de mais tempo de aprendizado do que as outras.

![Linha do tempo de exemplo na execução de um piloto do Microsoft 365 Defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>Para obter resultados ideais, siga as instruções piloto o mais próximo possível.


### <a name="pilot-playbook-phases"></a>Fases piloto do playbook 

Há quatro fases na execução de um piloto do Microsoft 365 Defender:

|Fase | Descrição | 
|:-------|:-----|
| [Planejamento](mtp-pilot-plan.md)<br> ~ 1 dia| Saiba o que você precisa considerar antes de executar seu projeto piloto do Microsoft 365 Defender: <br><br>- Escopo <br> - Usar casos <br>- Requisitos <br>- Plano de teste <br> - Critérios de sucesso <br> - Scorecard 
| [Preparação](mtp-evaluation.md) <br>~2 dias|  Acesse o Centro de Segurança do Microsoft 365 para configurar seu ambiente piloto do Microsoft 365 Defender. Você será guiado para:<br><br>- Identificar participantes e buscar aprovação para seu piloto <br> - Considerações sobre o ambiente <br>- Access <br>- Configuração do Azure Active Directory <br> - Ordem de configuração <br> - Inscrever-se na avaliação do Microsoft 365 E5 <br> - Configurar domínio <br>- Atribuir licenças do Microsoft 365 E5 <br> – Conclua o assistente de instalação no portal|
| [Simulação de ataque](mtp-pilot-simulate.md) <br>~2 dias| Para simular um ataque, você será orientado a:<br><br>- Verificar os requisitos do ambiente de teste <br>- Executar a simulação <br>- Investigar um incidente <br>- resolver o incidente 
| [Fechamento e resumo](mtp-pilot-close.md) <br>~ 1 dia| Quando você chegar ao final do processo, você será orientado a:<br><br>- Passar pela saída final<br>- Apresentar sua saída para seus participantes <br>- Fornecer comentários <br>- Dê as próximas etapas 

## <a name="next-step"></a>Próxima etapa
|[Fase de planejamento](mtp-pilot-plan.md) | Planejar seu projeto piloto do Microsoft 365 Defender 
|:-------|:-----|