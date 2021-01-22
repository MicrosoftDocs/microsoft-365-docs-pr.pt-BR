---
title: Microsoft 365 Defender
description: O Microsoft 365 Defender é uma solução de proteção coordenada contra ameaças projetada para proteger dispositivos, identidade, dados e aplicativos
keywords: Introdução à Proteção contra Ameaças da Microsoft, segurança cibernética, ameaça persistente avançada, segurança corporativa, dispositivos, dispositivo, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, busca avançada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e80a3d094ac8f5724bbe7daf72a0ded7d30091ba
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930565"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

> Deseja experimentar o Microsoft 365 Defender? Você pode [avaliá-lo em um ambiente de laboratório](https://aka.ms/mtp-trial-lab) ou executar seu projeto piloto em [produção.](https://aka.ms/m365d-pilotplaybook)
>

O Microsoft 365 Defender é um pacote unificado de defesa empresarial pré-e pós-violação que coordena de forma nativa a detecção, prevenção, investigação e resposta entre pontos de extremidade, identidades, email e aplicativos para fornecer proteção integrada contra ataques sofisticados.

Com a solução integrada do Microsoft 365 Defender, os profissionais de segurança podem unir os sinais de ameaça que cada um desses produtos recebe e determinar o escopo completo e o impacto da ameaça; como ele entrou no ambiente, o que é afetado e como ele está afetando a organização no momento. O Microsoft 365 Defender faz uma ação automática para impedir ou parar o ataque e auto-recuperar caixas de correio afetadas, pontos de extremidade e identidades de usuário.  


<center><h2>Serviços do Microsoft 365 Defender</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender para Ponto de Extremidade</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender para Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Microsoft Defender for Identity</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Guia interativo do Microsoft 365 Defender

Neste guia interativo, você aprenderá a proteger sua organização com o Microsoft 365 Defender. Você verá como o Microsoft 365 Defender pode ajudá-lo a detectar riscos de segurança, investigar ataques à sua organização e evitar atividades prejudiciais automaticamente.

> [!VIDEO https://aka.ms/M365Defender-InteractiveGuide]



O pacote do Microsoft 365 Defender protege: 
- **Pontos de extremidade com** o Microsoft Defender para Ponto de Extremidade - o Microsoft Defender para Ponto de Extremidade é uma plataforma unificada de pontos de extremidade para proteção preventiva, detecção pós-violação, investigação automatizada e resposta. 
- Email e colaboração com o **Microsoft Defender para Office 365** - O Defender para Office 365 protege sua organização contra ameaças mal-intencionadas, colocadas por mensagens de email, links (URLs) e ferramentas de colaboração. 
- Identidades com o Microsoft Defender for Identity e o **Azure AD Identity Protection** - o Microsoft Defender for Identity usa sinais do Active Directory para identificar, detectar e investigar ameaças avançadas, identidades comprometidas e ações internas mal-intencionadas direcionadas à sua organização. 
- **Aplicativos com segurança do Microsoft Cloud App** – a segurança do Microsoft Cloud App é uma solução abrangente entre SaaS, que traz ampla visibilidade, controles de dados fortes e proteção aprimorada contra ameaças para seus aplicativos de nuvem. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

A camada exclusiva entre produtos do Microsoft 365 Defender aumenta os componentes individuais do pacote para:
- Ajudar a proteger contra ataques e coordenar respostas coordenadas em todo o pacote por meio de compartilhamento de sinal e ações automatizadas
- Narrar a história completa do ataque em alertas, comportamentos e contextos de produtos para equipes de segurança, juntando dados sobre alertas, eventos suspeitos e ativos afetados a "incidentes"
- Automatizar a resposta ao comprometimento disparando a autorreeração para ativos afetados por meio de correção automatizada
- Permitir que as equipes de segurança realizem buscas detalhadas e eficazes de ameaças nos pontos de extremidade e nos dados do Office

![Imagem da página de visão geral do incidente](../../media/overview-incident.png) <br>
Incidente entre produtos (visão geral)

![Imagem da fila de alertas](../../media/incident-list.png)<br>
Todos os alertas relacionados nos produtos do pacote correlacionados em um único incidente (exibição de alertas)

![Imagem da fila de incidentes](../../media/advanced-hunting.png)<br>
Busca baseada em consulta sobre dados brutos de email e ponto de extremidade


Os recursos entre produtos do Microsoft 365 Defender incluem: 
- **Painel único** de vidro entre produtos - Exibição central de todas as informações para detecções, ativos afetados, ações automatizadas tomadas e evidências relacionadas em uma única fila e um único painel no [security.microsoft.com](https://security.microsoft.com). 
- Fila de **incidentes combinados** - Para ajudar os profissionais de segurança a se concentrarem no que é fundamental, garantindo o escopo completo do ataque, os ativos afetados e as ações de correção automatizadas são agrupados e aparecerem em tempo hábil. 
- **Resposta automática a ameaças** - As informações críticas sobre ameaças são compartilhadas em tempo real entre os produtos do Microsoft 365 Defender para ajudar a parar a progressão de um ataque. Por exemplo, se um arquivo mal-intencionado for detectado em um ponto de extremidade protegido pelo Microsoft Defender para Ponto de Extremidade, ele instrui o Defender para Office 365 a verificar e remover o arquivo de todas as mensagens de email. O arquivo será bloqueado à vista por todo o pacote de segurança do Microsoft 365.
- Auto-recuperação para dispositivos **comprometidos,** identidades de usuário e caixas de correio - o Microsoft 365 Defender usa ações automáticas e playbooks da tecnologia AI para remediar os ativos afetados de volta para um estado seguro. O Microsoft 365 Defender aproveita os recursos de correção automática dos produtos do pacote para garantir que todos os ativos afetados relacionados a um incidente sejam automaticamente remediados sempre que possível.
- **Busca de ameaças entre** produtos - As equipes de segurança podem aproveitar seu conhecimento organizacional exclusivo para procurar sinais de comprometimento criando suas próprias consultas personalizadas sobre os dados brutos coletados pelos vários produtos de proteção. O Microsoft 365 Defender fornece acesso baseado em consulta a 30 dias de sinais brutos históricos e dados de alerta no ponto de extremidade e no Microsoft Defender para dados do Office 365. 


## <a name="get-started"></a>Introdução
Os requisitos de licenciamento do Microsoft 365 Defender devem ser atendidos antes que você possa habilitar o serviço na central de segurança do Microsoft 365 [em security.microsoft.com](https://security.microsoft.com). Para obter mais informações, leia:
- [Requisitos de licenciamento](prerequisites.md#licensing-requirements)
- [Ativar o Microsoft 365 Defender](mtp-enable.md)
