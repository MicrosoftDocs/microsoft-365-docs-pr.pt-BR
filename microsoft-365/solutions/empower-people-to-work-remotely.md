---
title: Capacite funcionários remotos com o Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: Configure a infraestrutura de segurança e serviços que permita aos seus funcionários trabalharem remotamente em qualquer lugar e a qualquer momento.
ms.openlocfilehash: 763c8e745eb54897c1df88ecb5a9064987ed5a13
ms.sourcegitcommit: 9195c83c725a7e6ed395ce0253304da54e2195f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "44560454"
---
# <a name="empower-remote-workers-with-microsoft-365"></a>Capacite funcionários remotos com o Microsoft 365

Sua empresa talvez precise habilitar seus funcionários a ter acesso seguro às informações, ferramentas e recursos da organização, no local e na nuvem de sua organização, a partir de suas casas. Permitir que os funcionários trabalhem fora do escritório sem obstáculos e com segurança é importante para várias organizações para:

- Economizar espaço no escritório.
- Contratar e reter funcionários que não estão dispostos a ser realocados.
- Reduza o deslocamento dos funcionários, deixando-os com mais tempo para serem produtivos e para atividades de redução de estresse fora do trabalho.

O trabalho remoto, também conhecido como teletrabalho, pode abranger um espectro que inclui:

- Funcionários que estão ocasionalmente fora do escritório para conferências ou reuniões com clientes.
- Alguns funcionários que trabalham remotamente em tempo integral.
- Uma organização totalmente remota na qual não há nenhum escritório e todos os funcionários são remotos.

Em qualquer lugar do mundo e a qualquer momento, os funcionários remotos devem poder acessar:

- Recursos da organização, como os oferecidos por centros de dados de aplicativos locais.
- Serviços e dados em nuvem na sua assinatura do Microsoft 365, como Teams, Exchange Online, SharePoint e OneDrive.

Para uma experiência de entrada perfeita, as contas de usuários dos Serviços de Domínio do Active Directory (AD DS) devem ser sincronizados com o Azure Active Directory (Azure AD). Para proteger os dispositivos com Windows 10, eles devem ser registrados no Intune. Veja a seguir uma visão geral da infraestrutura.

![A infraestrutura básica para funcionários remotos com o Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)


Para dar suporte a funcionários remotos, por exemplo, em resposta à crise COVID-19, uma combinação de recursos no Microsoft 365 permite aos funcionários remotos colaborar de forma ativa, como por exemplo:

- Reuniões online e sessões de chat.
- Espaços de trabalho compartilhados para armazenamento de arquivos na nuvem com acessibilidade global e colaboração em tempo real.
- Tarefas e fluxos de trabalho compartilhados para dividir o trabalho e realizar as tarefas.

Para segurança forte, o Microsoft 365 inclui:

- Requisitos de autenticação imposta, detecção e resposta a entradas de alto risco e bloqueio de aplicativos selecionados e dispositivos que não estejam em conformidade.
- Conexões criptografadas e ativos digitais na nuvem.
- Permissões para definir quem pode fazer o que com os arquivos.
- Recursos de segurança abrangentes para proteger dispositivos Windows 10.

Para atender a esses critérios para funcionários remotos, use as seguintes capacidades e recursos do Microsoft 365.

| Capcidade ou recurso | Descrição | Licenças |
|:-------|:-----|:-------|
| MFA imposta com padrões de segurança   | Proteja-se contra os dispositivos e identidades comprometidos exigindo uma segunda forma de autenticação para as entradas. O padrão de segurança exige MFA para todas as contas de usuário.   | Microsoft 365 E3 e e5 |
| MFA imposta com Acesso Condicional| Exija MFA com base nas propriedades da entrada com políticas de Acesso Condicional.    | Microsoft 365 E3 e e5 | 
| MFA imposta com Acesso Condicional baseado em risco   | Exija a MFA com base no risco do logon do usuário com a Proteção Avançada contra Ameaças do Azure. | Microsoft 365 E5 ou E3 com as licenças do Azure AD Premium P2 | 
| Redefinição de Senha por autoatendimento (SSPR)    | Permita que os usuários redefinam ou desbloqueiem suas contas ou senhas.  | Microsoft 365 E3 e e5 |
| Proxy do Aplicativo Azure AD    | Forneça acesso remoto seguro para aplicativos baseados na web hospedados em servidores da intranet.   | Exige uma assinatura paga do Azure paga |
| VPN de Ponto a Site do Azure   | Criar uma conexão segura do dispositivo de um trabalhador remoto para sua intranet por meio de uma rede virtual do Azure.   | Exige uma assinatura paga do Azure paga |
| Área de Trabalho Virtual do Windows   | Suporte a funcionários remotos que só podem usar seus dispositivos pessoais e não gerenciados com as áreas de trabalho virtuais que estão sendo executadas no Azure. | Exige uma assinatura paga do Azure paga |
| Serviços de Área de Trabalho Remota (RDS) | Permitir que os funcionários se conectem a computadores baseados no Windows na intranet. | Microsoft 365 E3 e e5 | 
| Gateway dos Serviços de Área de Trabalho Remota   | Criptografe comunicações e impeça que os hosts RDS sejam expostos diretamente à Internet. | Exige licenças separadas do Windows Server |
| Microsoft Intune | Gerenciar dispositivos e aplicativos.   | Microsoft 365 E3 e e5 | 
| Gerenciador de Configurações | Gerenciar instalações, atualizações e configurações de software em seus dispositivos | Exige licenças separadas do Configuration Manager |
| Análise de Área de Trabalho | Determine a prontidão de atualização dos seus clientes Windows.   | Exige licenças separadas do Configuration Manager |
| Windows Autopilot | Configure e configure novamente os novos dispositivos com Windows 10 para uso produtivo.   | Microsoft 365 E3 e e5 |
| Microsoft Teams, Exchange Online, SharePoint Online e OneDrive, Microsoft 365 Apps, Microsoft Power Platform, Yammer, Power Apps | Criar, comunicar e colaborar. | Microsoft 365 E3 e e5 |
||||

Use estas etapas para proteger e otimizar o acesso aos servidores, dados e serviços na nuvem da sua organização e habilitar a produtividade máxima do trabalho.

1. [Aumentar a segurança de entrada com a MFA](empower-people-to-work-remotely-secure-sign-in.md)
2. [Fornecer acesso remoto a aplicativos e serviços e aplicativos locais](empower-people-to-work-remotely-remote-access.md)
3. [Implantar o gerenciamento de pontos de extremidade em seus dispositivos, PCs e outros pontos de extremidade](empower-people-to-work-remotely-manage-endpoints.md)
4. [Implantar aplicativos e serviços de produtividade de trabalhador remoto](empower-people-to-work-remotely-teams-productivity-apps.md)
5. [Criar locais de comunicação](empower-people-to-work-remotely-communication-venues.md)
6. [Treinar os funcionários remotos e responder a questões sobre o uso](empower-people-to-work-remotely-train-monitor-usage.md)

![As etapas para capacitar funcionários remotos com o Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

Para obter as informações mais recentes da Microsoft sobre como oferecer suporte a funcionários remotos, confira [Habilitação do site de comunidade técnica de trabalho remoto](https://resources.techcommunity.microsoft.com/enabling-remote-work/).
