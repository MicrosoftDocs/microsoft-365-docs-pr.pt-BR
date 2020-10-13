---
title: Proteção contra Ameaças da Microsoft
description: A proteção contra ameaças da Microsoft é uma solução de proteção de ameaças coordenada projetada para proteger dispositivos, identidades, dados e aplicativos
keywords: Introdução à proteção contra ameaças da Microsoft, segurança da CyberSource, ameaça persistente avançada, segurança corporativa, dispositivos, dispositivo, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, busca avançada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: c98ce94bfa327b3e09cc1042717571de325a244e
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429666"
---
# <a name="microsoft-threat-protection"></a>Proteção contra Ameaças da Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft



A proteção contra ameaças da Microsoft é um pacote de defesa de negócios unificado de pré e pós-violação que coordena nativamente a detecção, prevenção, investigação e resposta entre pontos de extremidade, identidades, email e aplicativos para oferecer proteção integrada contra ataques sofisticados.

Com a solução integrada de proteção contra ameaças da Microsoft, os profissionais de segurança podem unir os sinais de ameaça de que cada um desses produtos recebe e determinam o escopo completo e o impacto da ameaça; como ele entrou no ambiente, o que ele é afetado e como ele está afetando a organização no momento. A proteção contra ameaças da Microsoft realiza ações automáticas para impedir ou interromper o ataque e a AutoCorreção de caixas de correio, pontos de extremidade e identidades de usuários afetados.  


<center><h2>Serviços de proteção contra ameaças da Microsoft</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Proteção avançada contra ameaças do Microsoft defender</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Proteção avançada contra ameaças do Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Proteção avançada contra ameaças do Azure</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Segurança do aplicativo do Microsoft Cloud</b></a></center></td>
</tr>
</table>
<br>


>[!TIP]
>Confira este [guia interativo de proteção contra ameaças da Microsoft](https://aka.ms/MTP-Interactive-Guide).


O pacote de Proteção contra Ameaças da Microsoft protege: 
- **Pontos de extremidade com Microsoft defender ATP** -Microsoft defender ATP é uma plataforma de ponto de extremidade unificado para proteção preventiva, detecção de pós-violação, investigação automatizada e resposta. 
- O **email e a colaboração com o office 365 ATP** -Office 365 ATP salvaguarda sua organização contra ameaças mal-intencionadas causadas por mensagens de email, links (URLs) e ferramentas de colaboração. 
- **Identidades com o Azure ATP e o Azure ad Identity Protection** -o Azure ATP usa sinais do Active Directory para identificar, detectar e investigar ameaças avançadas, identidades comprometidas e ações mal-intencionadas intencionais direcionadas para sua organização. 
- **Aplicativos com o Microsoft Cloud app** Security-Microsoft Cloud app Security é uma solução completa de SaaS que traz visibilidade profunda, controles de dados fortes e proteção avançada contra ameaças para seus aplicativos de nuvem. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

A camada exclusiva de produtos cruzados do Microsoft Threat Protection aumenta os componentes individuais do pacote para:
- Ajudar a proteger contra ataques e coordenar respostas defensivas no pacote por meio de compartilhamento de sinal e ações automatizadas
- Narrar a história completa do ataque entre alertas de produtos, comportamentos e contexto para equipes de segurança unindo dados sobre alertas, eventos suspeitos e ativos impactados em ' incidentes '
- Automatizar a resposta para comprometer ao acionar a auto-recuperação de ativos impactados por meio da correção automatizada
- Permitir que as equipes de segurança realizem uma busca detalhada e eficaz de ameaças nos dados do Office e do ponto de extremidade

![Imagem da página de visão geral do incidente](../../media/overview-incident.png) <br>
Incidente entre produtos (visão geral)

![Imagem da fila de alertas](../../media/incident-list.png)<br>
Todos os alertas relacionados nos produtos do pacote que foram correlacionados em um único incidente (modo de exibição de alertas)

![Imagem da fila de incidentes](../../media/advanced-hunting.png)<br>
Busca baseada em consulta na parte superior dos dados brutos de email e ponto de extremidade


Os recursos entre produtos do Microsoft Threat Protection incluem: 
- **Painel único de interauto-produtos do modo de** visualização central todas as informações para detecções, ativos impactados, ações automatizadas e evidências relacionadas em uma única fila e um único painel no [Security.Microsoft.com](https://security.microsoft.com). 
- **Fila de incidentes combinados** – para ajudar os profissionais de segurança a se concentrar no que é crítico, garantindo o escopo completo do ataque, os ativos afetados e as ações de correção automatizada são agrupados e colocados em tempo hábil. 
- **Resposta automática para ameaças** -as informações críticas de ameaças são compartilhadas em tempo real entre os produtos de proteção contra ameaças da Microsoft para ajudar a interromper o andamento de um ataque. Por exemplo, se um arquivo mal-intencionado é detectado em um ponto de extremidade protegido pelo Microsoft defender ATP, ele instruirá o Office 365 ATP a examinar e remover o arquivo de todas as mensagens de email. O arquivo será bloqueado em vista pelo pacote de segurança do Microsoft 365 inteiro.
- **Auto-recuperação de dispositivos comprometidos, identidades de usuário e caixas de correio** -a proteção contra ameaças da Microsoft usa ações automáticas e guias estratégicos para corrigir os ativos impactados de volta a um estado seguro. A proteção contra ameaças da Microsoft aproveita os recursos de correção automática dos produtos do pacote para garantir que todos os ativos afetados relacionados a um incidente sejam corrigidos automaticamente quando possível.
- **Busca de ameaças entre produtos** -as equipes de segurança podem aproveitar o conhecimento organizacional exclusivo para procurar sinais de comprometimento criando suas próprias consultas personalizadas sobre os dados brutos coletados pelos vários produtos de proteção. A proteção contra ameaças da Microsoft fornece acesso baseado em consulta para 30 dias de sinais brutos históricos e dados de alerta em todos os dados do Endpoint e do Office 365 ATP. 


## <a name="get-started"></a>Introdução
Os requisitos de licenciamento de proteção contra ameaças da Microsoft devem ser atendidos para que você possa habilitar o serviço no centro de segurança do Microsoft 365 em [Security.Microsoft.com](https://security.microsoft.com). Para obter mais informações, leia:
- [Requisitos de licenciamento](prerequisites.md#licensing-requirements)
- [Habilitar a Proteção contra Ameaças da Microsoft](mtp-enable.md)
