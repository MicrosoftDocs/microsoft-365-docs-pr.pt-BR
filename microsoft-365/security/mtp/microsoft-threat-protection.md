---
title: Microsoft 365 Defender
description: O Microsoft 365 defender é uma solução de proteção de ameaças coordenada projetada para proteger dispositivos, identidades, dados e aplicativos
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
ms.openlocfilehash: 573f30dc3d8a43a337a4333dbaf05baf916857fa
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357894"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

> Quer experimentar o Microsoft 365 defender? Você pode [avaliá-lo em um ambiente de laboratório](https://aka.ms/mtp-trial-lab) ou [executar o projeto piloto em produção](https://aka.ms/m365d-pilotplaybook).
>

O Microsoft 365 defender é um pacote de defesa de negócios unificado de pré e pós-violação que coordena nativamente a detecção, prevenção, investigação e resposta entre pontos de extremidade, identidades, email e aplicativos para oferecer proteção integrada contra ataques sofisticados.

Com a solução integrada do Microsoft 365 defender, os profissionais de segurança podem unir os sinais de ameaça de que cada um desses produtos recebe e determinam o escopo completo e o impacto da ameaça; como ele entrou no ambiente, o que ele é afetado e como ele está afetando a organização no momento. O Microsoft 365 defender realiza ações automáticas para impedir ou interromper o ataque e a AutoCorreção de caixas de correio, pontos de extremidade e identidades de usuários afetados.  


<center><h2>Serviços do 365 defender da Microsoft</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft defender para ponto de extremidade</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft defender para Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Microsoft defender para identidade</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Segurança do aplicativo do Microsoft Cloud</b></a></center></td>
</tr>
</table>
<br>


>[!TIP]
>Confira este [guia interativo do Microsoft 365 defender](https://aka.ms/MTP-Interactive-Guide).


O Microsoft 365 defender Suite protege: 
- **Pontos de extremidade com Microsoft defender for Endpoint** -o Microsoft defender for Endpoint é uma plataforma de ponto de extremidade unificada para proteção preventiva, detecção de pós-violação, investigação automatizada e resposta. 
- O **email e a colaboração com o Microsoft defender para office 365** -defender para Office 365 protege sua organização contra ameaças mal-intencionadas feitas por mensagens de email, links (URLs) e ferramentas de colaboração. 
- **Identidades com o Microsoft defender for Identity e o Azure ad Identity Protection** -o Microsoft defender para identidade usa sinais do Active Directory para identificar, detectar e investigar ameaças avançadas, identidades comprometidas e ações mal-intencionadas intencionais direcionadas para sua organização. 
- **Aplicativos com o Microsoft Cloud app** Security-Microsoft Cloud app Security é uma solução completa de SaaS que traz visibilidade profunda, controles de dados fortes e proteção avançada contra ameaças para seus aplicativos de nuvem. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

A camada exclusiva de produtos cruzados do Microsoft 365 defender aumenta os componentes individuais do pacote para:
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


Os recursos entre produtos do Microsoft 365 defender incluem: 
- **Painel único de interauto-produtos do modo de** visualização central todas as informações para detecções, ativos impactados, ações automatizadas e evidências relacionadas em uma única fila e um único painel no [Security.Microsoft.com](https://security.microsoft.com). 
- **Fila de incidentes combinados** – para ajudar os profissionais de segurança a se concentrar no que é crítico, garantindo o escopo completo do ataque, os ativos afetados e as ações de correção automatizada são agrupados e colocados em tempo hábil. 
- **Resposta automática para ameaças** -as informações de ameaças críticas são compartilhadas em tempo real entre os produtos do Microsoft 365 defender para ajudar a interromper o andamento de um ataque. Por exemplo, se um arquivo mal-intencionado é detectado em um ponto de extremidade protegido pelo Microsoft defender para ponto de extremidade, ele instruirá o defender para Office 365 a examinar e remover o arquivo de todas as mensagens de email. O arquivo será bloqueado em vista pelo pacote de segurança do Microsoft 365 inteiro.
- **Auto-recuperação de dispositivos comprometidos, identidades de usuário e caixas de correio** -o Microsoft 365 defender usa as ações e os guias automáticos de alimentação de recursos para corrigir ativos impactados de volta a um estado seguro. O Microsoft 365 defender aproveita os recursos de correção automática dos produtos do pacote para garantir que todos os ativos afetados relacionados a um incidente sejam corrigidos automaticamente quando possível.
- **Busca de ameaças entre produtos** -as equipes de segurança podem aproveitar o conhecimento organizacional exclusivo para procurar sinais de comprometimento criando suas próprias consultas personalizadas sobre os dados brutos coletados pelos vários produtos de proteção. O Microsoft 365 defender fornece acesso baseado em consulta para 30 dias de sinais brutos históricos e dados de alerta no ponto de extremidade e dados do Microsoft defender para Office 365. 


## <a name="get-started"></a>Introdução
Os requisitos de licenciamento do Microsoft 365 defender devem ser atendidos para que você possa habilitar o serviço na central de segurança da Microsoft 365 em [Security.Microsoft.com](https://security.microsoft.com). Para obter mais informações, leia:
- [Requisitos de licenciamento](prerequisites.md#licensing-requirements)
- [Ativar o Microsoft 365 Defender](mtp-enable.md)
