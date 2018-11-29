---
title: Microsoft Desktop gerenciados funções e responsabilidades
description: Este tópico descreve as funções e responsabilidades fornecidas pela Microsoft para Microsoft Desktop gerenciados.
keywords: Serviço Microsoft Managed Desktop, 365 da Microsoft, documentação
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 923cde6353e4ff5122317f2c053fef244ee7e1b6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865320"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft Desktop gerenciados funções e responsabilidades


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Quando sua organização está inscrito no Microsoft Desktop gerenciados, o que Microsoft faz para você? E quais são as responsabilidades da sua organização?

## <a name="microsofts-roles-and-responsibilities"></a>Funções e responsabilidades da Microsoft

Abaixo estão alguns principais funções e responsabilidades que serão fornecidas a você pela Microsoft.

Função ou responsabilidade | Descrição
--- | ---
Gerenciamento de diretiva MDM | Microsoft aplicar políticas MDM conforme as práticas recomendadas e considere solicitações alterações na diretiva. Também podemos fará alterações ao seu locatário conforme prescrito [políticas de dispositivo](../service-description/device-policies.md).
Implantação de aplicativo | Microsoft implantará aplicativos aprovados para os dispositivos do cliente Microsoft Desktop gerenciados usando Intune. Para obter mais informações, consulte [Apps](../get-ready/apps.md). 
Suporte ao usuário final | A Microsoft fornecerá suporte ao usuário final para Office, Windows e dispositivos pacote de produtos para todos os usuários registrados. 
Suporte de serviço do Microsoft Desktop gerenciados | Microsoft oferecerá suporte ao cliente IT departamentos por meio de uma equipe de operações de área de trabalho gerenciado Microsoft. Essa equipe será solução de problemas técnicos de suporte, alterar solicitações e gerenciamento de incidentes para o ambiente do cliente Microsoft Desktop gerenciados. Para obter mais informações, consulte [obter suporte](../service-description/support.md).
Monitoramento de segurança | Microsoft monitorará dispositivos do cliente Microsoft Desktop gerenciados usando o Windows Defender ATP. Se uma ameaça for detectada pelo Microsoft Managed Desktop segurança operações Center (SOC), Microsoft notificará o cliente, isolar o dispositivo e corrigir o problema remotamente. Para obter mais informações, consulte [Security](../service-description/security.md).
Atualizar o monitoramento e gerenciamento | Microsoft monitorará ativamente os dispositivos do cliente Microsoft Desktop gerenciados para garantir que as atualizações mais recentes de qualidade, recurso e definição estão instaladas para o Microsoft Windows e o Microsoft Office. Para obter mais informações, consulte [como as atualizações são manipuladas](../service-description/updates.md).
Aquisição de dispositivo | Microsoft enviados ordenados dispositivos Microsoft Desktop gerenciado para os usuários finais ou o ponto de distribuição de IT de sua escolha. Para obter mais informações, consulte [dispositivos](../get-started/devices.md).

## <a name="your-roles-and-responsibilities"></a>Funções e responsabilidades

Abaixo é um conjunto adicional de funções comuns que não são fornecidas pela Microsoft, mas são necessários para uma implantação bem-sucedida. Ele não é completo, mas é típico para a maioria das organizações. 

Função ou reponsibility | Descrição
--- | ---
Gerenciamento de alterações | Microsoft Desktop gerenciados notificará clientes, com antecedência, quando as alterações que precisam ser feitas para seu ambiente de área de trabalho gerenciada do Microsoft. Os clientes precisam ter seu próprio processo de gerenciamento de alterações e são necessários para um contato com a Microsoft Desktop gerenciados. O cliente é necessária para têm recursos para revisar e aprovar essas alterações. Para obter mais informações, consulte [as operações e monitoramento](../service-description/operations-and-monitoring.md).  
O gerenciamento de identidades | Criar contas de usuário, como atribuir usuários a grupos e mantendo os metadados atualizados. 
Gerenciamento e a configuração do office 365 | Administração do Exchange Oonline, incluindo:<br>-Administração email<br>-Configuração mailbox e regra<br>-Exchange gerenciamento local<br><br>Ferramentas de colaboração, administração do SharePoint server, gerenciamento de domínio, as políticas de segurança e as informações definidas no portal de administração do Office 365 (Microsoft Desktop gerenciados garantirá aplicativos do Office são implantados em dispositivos do usuário final e mantenha-se atualizado). 
Suporte ao usuário final | O cliente fornecerá o suporte de usuário final para: <br>-Na infraestrutura do site: todos os conectividade de rede e internet, VPN infraestrutura e configuração do cliente, equipamento de sala de conferência locais, impressoras, servidor proxy e configuração, firewalls.<br><br>-Recursos de nuvem toda a empresa: email, SharePoint, os serviços de colaboração e outra infraestrutura de nuvem que se refere à pegada de tecnologia de toda a empresa.<br><br>---Aplicativos de LOB: software personalizado, software de terceiros 3rd, software de ERP (planejamento) de recursos da empresa, ferramentas de design e qualquer coisa não especificado neste documento.
Agrupamento de dispositivo e de usuário | Equipe de operações do Microsoft Desktop gerenciados será criar e gerenciar o dispositivo necessário e grupos de usuários como parte das operações de TI. O cliente não fará alterações para esses agrupamentos sem primeiro entrando em contato com as operações de TI através de canais com suporte. Todos os detectados alterações serão desfeitas.
Aplicativos | Os clientes fornecerão uma lista de aplicativos que queiram usar em suas organizações (além dos aplicativos incluídos com licença da Microsoft 365). Os clientes também oferecem um pacote implantável (Appx ou MSI)<br>O cliente é responsável por:<br>-Gerenciamento de licenças app – tendo o tipo de à direita e a quantidade de licenças<br>-Atribuição app – apps atribuindo a grupos de usuários do Azure AD.<br>-Atualizações app – monitoramento, empacotamento e implantação de atualizações de segurança e o recurso de aplicativo<br>-Aplicativo de usuário testando (UAT)<br><br>Para obter mais informações, consulte [Apps](../get-ready/apps.md)
Monitoramento de segurança e de resposta | Se um incidente de segurança for detectado que está fora do escopo das operações de área de trabalho gerenciada da Microsoft, podemos exigirá uma lista de contatos de cliente preferencial, dependendo da gravidade do problema.<br><br>O cliente é responsável pela investigação e resolução de incidentes para dispositivos não - Microsoft Managed Desktop e para garantir que a equipe de operações de área de trabalho gerenciada do Microsoft é informada de quaisquer problemas que possam afetar o serviço.
Suporte de operações | Operações de área de trabalho do Microsoft gerenciados precisa de uma lista de contatos do cliente preferencial e especialistas no assunto. Precisamos essas caso haja um incidente de operacionais não - Microsoft Managed Desktop. <br><br>O cliente é responsável pela investigação e resolução de incidentes para dispositivos não - Microsoft Managed Desktop e serviços e garantir que a equipe de operações de área de trabalho gerenciada do Microsoft sempre é informada.
Infraestrutura de rede, incluindo VPN | Instalação, configuração e gerenciamento (incluindo a solução de problemas e depuração) da infra-estrutura de todas as relacionadas a rede e serviços, incluindo a conectividade com a internet, rede controles, a configuração de proxy e a infra-estrutura de conectividade remota.<br><br>Por padrão, o Microsoft Desktop gerenciados não especifique ou exigem um proxy. No entanto, se houver algum configurado (em hardware ou software), é uma coleção de URLs que devem ser permitidas pelo proxy. O cliente é responsável por qualquer conflitos ou incompatibilidades devido aos vários proxies de solução de problemas.<br><br>Para obter mais informações, consulte [Configuração do Proxy](../get-ready/network.md).
Impressão | Instalar, manter e administrar impressoras e filas de impressão. Nuvem impressão é uma solução recomendada, mas não é necessária. 
Dispositivos móveis | Dispositivos e Acessórios não fornecidos pelo Microsoft Desktop gerenciados. Gerenciados a equipe de operações de área de trabalho do Microsoft suporta apenas o dispositivo Microsoft Desktop gerenciados, estação de encaixe e Acessórios incluídos.




