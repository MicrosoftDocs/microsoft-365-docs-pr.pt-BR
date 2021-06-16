---
title: Executar seu projeto piloto Microsoft 365 Defender
description: Execute seu projeto piloto Microsoft 365 Defender em produção para determinar efetivamente os benefícios e adoção do Microsoft 365 Defender.
keywords: Microsoft 365 Piloto do Defender, execute o projeto piloto do Microsoft 365 Defender, avalie o Microsoft 365 Defender em produção, projeto piloto do Microsoft 365 Defender, segurança cibernética, ameaças persistentes avançadas, segurança corporativa, dispositivos, dispositivos, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, busca avançada
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 3219b329c53c32e02cd29acdd41a48cd93b2e8bb
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930506"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Executar seu projeto piloto Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender


Este guia ajuda você a executar um projeto piloto fornecendo ponteiros para garantir que você tenha um plano bem estruturado, orientando você usando o recurso de simulação de ataque e, finalmente, concluindo o piloto com as principais dicas para você refletir e documentar os resultados.

![Fases na execução de um piloto Microsoft 365 Defender](../../media/pilotphases.png)


Executar um piloto ajuda você a determinar efetivamente o benefício de adotar Microsoft 365 Defender. Antes de Microsoft 365 o defender em seu ambiente de produção e iniciar seus casos de uso, é melhor planejar a determinação das tarefas a realizar para seu projeto piloto e definir os critérios de sucesso. 


## <a name="how-to-use-this-pilot-playbook"></a>Como usar esse playbook piloto

Este guia fornece uma visão geral Microsoft 365 instruções passo a passo do Defender sobre como configurar seu projeto piloto. 

Microsoft 365 O Defender é um pacote de defesa empresarial unificado pré e pós-violação que coordena a proteção, a detecção, a prevenção, a investigação e a resposta entre pontos de extremidade, identidades, email e aplicativos para fornecer proteção integrada contra ataques sofisticados. Ele faz isso combinando e orquestrando os seguintes recursos em uma única solução de segurança:
  - Microsoft Defender para Ponto de Extremidade (pontos de extremidade)
  - Microsoft Defender para Office 365 (email) 
  - Microsoft Defender para Identidade (identidade) 
  - Microsoft Cloud App Security (aplicativos)

![Solução do Image of_Microsoft 365 Defender para usuários, Microsoft Defender para Identidade, para pontos de extremidade Microsoft Defender para Ponto de Extremidade, para aplicativos de nuvem, Microsoft Cloud App Security e para dados, Microsoft Defender para Office 365](../../media/mtp/m365pillars.png)

Com a solução integrada do Microsoft 365 Defender, os profissionais de segurança podem unir os sinais de ameaça que o Microsoft Defender para Ponto de Extremidade, o Microsoft Defender para Office 365, o Microsoft Defender para Identidade e o Microsoft Cloud App Security recebem e determinam o escopo completo e o impacto da ameaça, como ele entrou no ambiente, o que ele é afetado e como ele está afetando a organização no momento. Microsoft 365 O Defender toma medidas automáticas para impedir ou interromper o ataque e a auto-recuperação de caixas de correio afetadas, pontos de extremidade e identidades de usuário. Consulte o [Microsoft 365 visão geral do Defender](microsoft-365-defender.md) para obter detalhes.



A linha do tempo de exemplo a seguir varia dependendo de ter os recursos certos em seu ambiente. Algumas detecções e fluxos de trabalho podem precisar de mais tempo de aprendizado do que as outras.

![Linha do tempo de exemplo ao executar um Microsoft 365 piloto do Defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>Para obter resultados ideais, siga as instruções piloto o mais próximo possível.


### <a name="pilot-playbook-phases"></a>Fases piloto do playbook 

Há quatro fases na execução de um piloto Microsoft 365 Defender:

|Fase | Descrição | 
|:-------|:-----|
| [Planejamento](m365d-pilot-plan.md)<br> ~ 1 dia| Saiba o que você precisa considerar antes de executar seu projeto piloto Microsoft 365 Defender: <br><br>- Escopo <br> - Usar casos <br>- Requisitos <br>- Plano de teste <br> - Critérios de sucesso <br> - Scorecard 
| [Preparação](m365d-evaluation.md) <br>~2 dias|  Acesse Microsoft 365 Central de Segurança para configurar seu ambiente piloto Microsoft 365 Defender. Você será guiado para:<br><br>- Identificar participantes e buscar aprovação para seu piloto <br> - Considerações sobre o ambiente <br>- Access <br>- Azure Active Directory configuração <br> - Ordem de configuração <br> - Inscreva-se para Microsoft 365 E5 Avaliação <br> - Configurar domínio <br>- Atribuir Microsoft 365 E5 licenças <br> – Conclua o assistente de instalação no portal|
| [Simulação de ataque](m365d-pilot-simulate.md) <br>~2 dias| Para simular um ataque, você será orientado a:<br><br>- Verificar os requisitos do ambiente de teste <br>- Executar a simulação <br>- Investigar um incidente <br>- resolver o incidente 
| [Fechamento e resumo](m365d-pilot-close.md) <br>~ 1 dia| Quando você chegar ao final do processo, você será orientado a:<br><br>- Passar pela saída final<br>- Apresentar sua saída para seus participantes <br>- Fornecer comentários <br>- Dê as próximas etapas 

## <a name="next-step"></a>Próxima etapa
|[Fase de planejamento](m365d-pilot-plan.md) | Planejar seu projeto piloto do Microsoft 365 Defender 
|:-------|:-----|
