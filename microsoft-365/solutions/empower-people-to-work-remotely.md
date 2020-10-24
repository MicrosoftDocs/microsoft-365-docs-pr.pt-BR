---
title: Capacite funcionários remotos com o Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-overview
- M365initiative-coredeploy
ms.custom: ''
description: Configure a infraestrutura de segurança e serviços que permita aos seus funcionários trabalharem remotamente em qualquer lugar e a qualquer momento.
ms.openlocfilehash: 60467f0ed3cf7aa75481cb3bb49f954c32bf2e7d
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681391"
---
# <a name="empower-remote-workers-with-microsoft-365"></a>Capacite funcionários remotos com o Microsoft 365

Sua empresa talvez precise habilitar seus funcionários a ter acesso seguro às informações, ferramentas e recursos da organização, no local e na nuvem de sua organização, a partir de suas casas. Permitir que os funcionários trabalhem fora do escritório é importante para várias organizações para:

- Economizar espaço no escritório.
- Contratar e reter funcionários que não estão dispostos a ser realocados.
- Reduza o deslocamento dos funcionários, deixando-os com mais tempo para serem produtivos e para atividades de redução de estresse fora do trabalho.

O Microsoft 365 tem os recursos para permitir que seus funcionários trabalhem remotamente.

![Capacite funcionários remotos com o Microsoft 365](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

Assista a esse vídeo para obter uma visão geral do processo de implantação.
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

Esta solução fornece esses recursos essenciais.

- Conectado

  De qualquer lugar do mundo e a qualquer momento, os funcionários remotos podem acessar: 

  - Serviços e dados baseados em nuvem na sua assinatura do Microsoft 365. 

  - Recursos da organização, como os oferecidos por centros de dados de aplicativos locais.

- Seguro

  Os logins são protegidos com autenticação multifator (MFA) e os recursos de segurança internos do Microsoft 365 e do Windows 10 protegem contra malwares, ataques maliciosos e perda de dados.

- Gerenciado

  Os dispositivos dos seus trabalhadores remotos podem ser gerenciados na nuvem com configurações de segurança, aplicativos permitidos e exigir conformidade com a integridade do sistema.

- Colaborativo e produtivo

  Seus funcionários remotos podem ser tão produtivos quanto locais, de uma maneira altamente colaborativa com:

  - Reuniões on-line e sessões de bate-papo com o Teams. 

  - Áreas de trabalho compartilhadas para armazenamento de arquivos baseados em nuvem com acessibilidade global e colaboração em tempo real com o SharePoint e o OneDrive.

  - Tarefas e fluxos de trabalho compartilhados para dividir o trabalho e realizar as tarefas. 

Para uma experiência perfeita de entrada, suas contas de usuário dos Serviços de domínio do Active Directory (AD DS) locais devem ser sincronizadas com o Azure Active Directory (Azure AD). Para proteger os dispositivos com Windows 10, eles devem ser registrados no Intune. Veja a seguir uma visão geral da infraestrutura.

![A infraestrutura básica para funcionários remotos com o Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

Para habilitar as funcionalidades do Microsoft 365 para seus trabalhadores remotos, utilize esses recursos do Microsoft 365.

| Capcidade ou recurso | Descrição | Licenças |
|:-------|:-----|:-------|
| MFA imposta com padrões de segurança   | Proteja-se contra os dispositivos e identidades comprometidos exigindo uma segunda forma de autenticação para as entradas. O padrão de segurança exige MFA para todas as contas de usuário.   | Microsoft 365 E3 ou E5 |
| MFA imposta com Acesso Condicional| Exija MFA com base nas propriedades da entrada com políticas de Acesso Condicional.    | Microsoft 365 E3 ou E5 | 
| MFA imposta com Acesso Condicional baseado em risco   | Exija a MFA com base no risco do logon do usuário com a Proteção Avançada contra Ameaças do Azure. | Microsoft 365 E5 ou E3 com as licenças do Azure AD Premium P2 | 
| Redefinição de Senha por autoatendimento (SSPR)    | Permita que os usuários redefinam ou desbloqueiem suas contas ou senhas.  | Microsoft 365 E3 ou E5 |
| Proxy do Aplicativo Azure AD    | Forneça acesso remoto seguro para aplicativos baseados na web hospedados em servidores da intranet.   | Exige uma assinatura paga do Azure paga |
| VPN de Ponto a Site do Azure   | Criar uma conexão segura do dispositivo de um trabalhador remoto para sua intranet por meio de uma rede virtual do Azure.   | Exige uma assinatura paga do Azure paga |
| Área de Trabalho Virtual do Windows   | Suporte a funcionários remotos que só podem usar seus dispositivos pessoais e não gerenciados com as áreas de trabalho virtuais que estão sendo executadas no Azure. | Exige uma assinatura paga do Azure paga |
| Serviços de Área de Trabalho Remota (RDS) | Permitir que os funcionários se conectem a computadores baseados no Windows na intranet. | Microsoft 365 E3 ou E5 | 
| Gateway dos Serviços de Área de Trabalho Remota   | Criptografe comunicações e impeça que os hosts RDS sejam expostos diretamente à Internet. | Exige licenças separadas do Windows Server |
| Microsoft Intune | Gerenciar dispositivos e aplicativos.   | Microsoft 365 E3 ou E5 | 
| Gerenciador de Configurações | Gerenciar instalações, atualizações e configurações de software em seus dispositivos | Exige licenças separadas do Configuration Manager |
| Análise de Área de Trabalho | Determine a prontidão de atualização dos seus clientes Windows.   | Exige licenças separadas do Configuration Manager |
| Windows Autopilot | Configure e configure novamente os novos dispositivos com Windows 10 para uso produtivo.   | Microsoft 365 E3 ou E5 |
| Microsoft Teams, Exchange Online, SharePoint Online e OneDrive, Microsoft 365 Apps, Microsoft Power Platform e Yammer | Criar, comunicar e colaborar. | Microsoft 365 E3 ou E5 |
||||

Para critérios de segurança e conformidade, confira [Implantar segurança e conformidade para funcionários remotos](empower-people-to-work-remotely-security-compliance.md).

<a name="poster"></a> Para obter um resumo de 2 páginas dessa solução, consulte o pôster [Capacitar trabalhadores remotos](../downloads/empower-remote-workers.pdf).

[![Pôster Capacitar trabalhadores remotos](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../downloads/empower-remote-workers.pdf)

Também é possível descarregar este pôster no formato [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pdf) e imprimi-lo em papel tamanho carta, legal, ou tabloide (11 x 17).

Use essas etapas para proteger e otimizar o acesso aos servidores e serviços em nuvem da sua organização e maximizar a produtividade do seu trabalhador remoto.

1. [Aumentar a segurança de entrada com a MFA](empower-people-to-work-remotely-secure-sign-in.md)
2. [Fornecer acesso remoto a aplicativos e serviços e aplicativos locais](empower-people-to-work-remotely-remote-access.md)
3. [Implantar serviços de segurança e conformidade](empower-people-to-work-remotely-security-compliance.md)
4. [Implantar o gerenciamento de pontos de extremidade em seus dispositivos, PCs e outros pontos de extremidade](empower-people-to-work-remotely-manage-endpoints.md)
5. [Implantar aplicativos e serviços de produtividade de trabalhador remoto](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [Treinar os funcionários remotos e responder a questões sobre o uso](empower-people-to-work-remotely-train-monitor-usage.md)

[![Os passos para capacitar os trabalhadores remotos com o Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)

Para obter as informações mais recentes da Microsoft sobre o suporte de trabalhadores remotos, consulte o site [Habilitando o trabalho híbrido com o Microsoft Teams](https://resources.techcommunity.microsoft.com/enabling-hybrid-work/).
