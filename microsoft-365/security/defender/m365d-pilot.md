---
title: Executar seu projeto piloto do Microsoft 365 Defender
description: Execute seu projeto piloto do Microsoft 365 Defender em produção para determinar efetivamente os benefícios e a adoção do Microsoft 365 Defender.
keywords: Piloto do Microsoft 365 Defender, execute o projeto piloto do Microsoft 365 Defender, avalie o Microsoft 365 Defender em produção, projeto piloto do Microsoft 365 Defender, segurança cibernética, ameaça persistente avançada, segurança corporativa, dispositivos, dispositivos, identidade, usuários, dados, aplicativos, incidentes, investigação automatizada e correção, busca avançada
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
ms.openlocfilehash: b1616b39597a90ff8e8f7b4c92f29f75c62fea18
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934424"
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
  - Microsoft Defender para Ponto de Extremidade (pontos de extremidade)
  - Microsoft Defender para Office 365 (email) 
  - Microsoft Defender para Identidade (identidade) 
  - Microsoft Cloud App Security (aplicativos)

![Solução do Image of_Microsoft 365 Defender para usuários, Microsoft Defender for Identity, para pontos de extremidade Microsoft Defender para Ponto de Extremidade, para aplicativos de nuvem, Microsoft Cloud App Security e para dados, Microsoft Defender para Office 365](../../media/mtp/m365pillars.png)

Com a solução integrada do Microsoft 365 Defender, os profissionais de segurança podem unir os sinais de ameaça que o Microsoft Defender para Ponto de Extremidade, o Microsoft Defender para Office 365, o Microsoft Defender para Identidade e o Microsoft Cloud App Security recebem e determinam o escopo completo e o impacto da ameaça, como ela entrou no ambiente, o que ela é afetada e como ela está afetando a organização no momento. O Microsoft 365 Defender toma medidas automáticas para impedir ou interromper o ataque e a auto-recuperação de caixas de correio afetadas, pontos de extremidade e identidades de usuário. Consulte a [visão geral do Microsoft 365 Defender](microsoft-365-defender.md) para obter detalhes.



A linha do tempo de exemplo a seguir varia dependendo de ter os recursos certos em seu ambiente. Algumas detecções e fluxos de trabalho podem precisar de mais tempo de aprendizado do que as outras.

![Linha do tempo de exemplo na execução de um piloto do Microsoft 365 Defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>Para obter resultados ideais, siga as instruções piloto o mais próximo possível.


### <a name="pilot-playbook-phases"></a>Fases piloto do playbook 

Há quatro fases na execução de um piloto do Microsoft 365 Defender:

|Fase | Descrição | 
|:-------|:-----|
| [Planejamento](m365d-pilot-plan.md)<br> ~ 1 dia| Saiba o que você precisa considerar antes de executar seu projeto piloto do Microsoft 365 Defender: <br><br>- Escopo <br> - Usar casos <br>- Requisitos <br>- Plano de teste <br> - Critérios de sucesso <br> - Scorecard 
| [Preparação](m365d-evaluation.md) <br>~2 dias|  Acesse o Centro de Segurança do Microsoft 365 para configurar seu ambiente piloto do Microsoft 365 Defender. Você será guiado para:<br><br>- Identificar participantes e buscar aprovação para seu piloto <br> - Considerações sobre o ambiente <br>- Access <br>- Configuração do Azure Active Directory <br> - Ordem de configuração <br> - Inscrever-se na avaliação do Microsoft 365 E5 <br> - Configurar domínio <br>- Atribuir licenças do Microsoft 365 E5 <br> – Conclua o assistente de instalação no portal|
| [Simulação de ataque](m365d-pilot-simulate.md) <br>~2 dias| Para simular um ataque, você será orientado a:<br><br>- Verificar os requisitos do ambiente de teste <br>- Executar a simulação <br>- Investigar um incidente <br>- resolver o incidente 
| [Fechamento e resumo](m365d-pilot-close.md) <br>~ 1 dia| Quando você chegar ao final do processo, você será orientado a:<br><br>- Passar pela saída final<br>- Apresentar sua saída para seus participantes <br>- Fornecer comentários <br>- Dê as próximas etapas 

## <a name="next-step"></a>Próxima etapa
|[Fase de planejamento](m365d-pilot-plan.md) | Planejar seu projeto piloto do Microsoft 365 Defender 
|:-------|:-----|
