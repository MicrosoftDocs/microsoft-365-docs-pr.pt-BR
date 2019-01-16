---
title: Microsoft Desktop gerenciados funções e responsabilidades
description: Este tópico descreve as funções e responsabilidades fornecidas pela Microsoft para Microsoft Desktop gerenciados.
keywords: Serviço Microsoft Managed Desktop, 365 da Microsoft, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 96131f7577e0e655067c70bffdd75163ba790adf
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
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
Suporte ao usuário final | A Microsoft fornecerá suporte ao usuário final para Office, Windows e dispositivos pacote de produtos para todos os usuários registrados por meio do app obter ajuda que é pré-instalado em todos os dispositivos de área de trabalho do Microsoft gerenciados. 
Suporte de serviço do Microsoft Desktop gerenciados | Microsoft oferecerá suporte ao cliente IT departamentos por meio de uma equipe de operações de área de trabalho gerenciado Microsoft. Essa equipe será solução de problemas técnicos de suporte, alterar solicitações e gerenciamento de incidentes para o ambiente do cliente Microsoft Desktop gerenciados. Para obter mais informações, consulte [Administração de suporte para o Microsoft Desktop gerenciados](../working-with-managed-desktop/admin-support.md).
Monitoramento de segurança | Microsoft monitorará dispositivos do cliente Microsoft Desktop gerenciados usando o Windows Defender ATP. Se uma ameaça for detectada pelo Microsoft Managed Desktop segurança operações Center (SOC), Microsoft notificará o cliente, isolar o dispositivo e corrigir o problema remotamente. Para obter mais informações, consulte [Security](../service-description/security.md).
Atualizar o monitoramento e gerenciamento | Microsoft monitorará ativamente os dispositivos do cliente Microsoft Desktop gerenciados para garantir que as atualizações mais recentes de qualidade e recurso estão instaladas para o Microsoft Windows e o Microsoft Office. Para obter mais informações, consulte [como as atualizações são manipuladas](../service-description/updates.md).
Agrupamento de dispositivo e de usuário | Equipe de operações do Microsoft Desktop gerenciados será criar e gerenciar o dispositivo necessário e grupos de usuários como parte das operações de TI. Não deve haver alterações feitas a esses grupos sem a aprovação da equipe de operações do Microsoft Desktop gerenciados.

## <a name="your-roles-and-responsibilities"></a>Funções e responsabilidades

Abaixo é um conjunto adicional de funções comuns e responsabilidades que não são fornecidas pela Microsoft, mas são necessários para uma implantação bem-sucedida. Ele não é completo, mas é aplicável para a maioria das organizações. Há alguns itens abaixo que a Microsoft e o cliente compartilhem responsibilties. 

Função ou responsabilidade | Descrição
--- | ---
Gerenciamento de alterações | Microsoft notificará clientes, com antecedência, quando as alterações que precisam ser feitas para seu ambiente de área de trabalho do Microsoft gerenciados. O cliente é necessário ter seu próprio gerenciamento de alteração processar e tiver um contato estabelecido com a equipe de operações de área de trabalho gerenciada da Microsoft. O cliente também é necessário ter recursos para revisar e aprovar essas alterações. Para obter mais informações, consulte [as operações e monitoramento](../service-description/operations-and-monitoring.md).  
O gerenciamento de identidades | O cliente é responsável por criar contas de usuário, como atribuir usuários a grupos e mantendo os metadados atualizados. 
Gerenciamento e a configuração do office 365 | Microsoft é responsável por garantir a aplicativos do Office são implantados para usuários finais e os aplicativos são mantidos atualizados. <br><br> O cliente é responsável pelo gerenciamento de serviços do Office 365 e políticas, incluindo o Exchange Online responsabilidades de administração:<br>-Administração email<br>-Configuração mailbox e regra<br>-Exchange gerenciamento local<br><br>O cliente também é responsável por ferramentas de colaboração, administração do SharePoint server, gerenciamento de domínio, as políticas de segurança e as informações definidas no portal de administração do Office 365. 
Suporte ao usuário final | O cliente é responsável por fornecer suporte a usuários finais: <br>-Na infraestrutura do site: todos os conectividade de rede e internet, VPN infraestrutura e configuração do cliente, equipamento de sala de conferência locais, impressoras, servidor proxy e configuração, firewalls.<br><br>-Recursos de nuvem toda a empresa: email, SharePoint, os serviços de colaboração e outra infraestrutura de nuvem que se refere à pegada de tecnologia de toda a empresa.<br><br>-Linha de negócios e quaisquer outros aplicativos específicos de empresa.
Aplicativos | Microsoft fornecerá orientações sobre a implantação de aplicativos aprovados usando Intune mediante solicitação.<br><br>O cliente é responsável por:<br>-Fornecendo uma lista de aplicativos para sua organização (fora do Office 365 apps)<br>-Gerenciamento de licenças app<br>– Tendo o tipo de à direita e a quantidade de licenças<br>-Atribuição app<br>– Atribuir aplicativos a grupos de usuários do Azure AD.<br>-Atualizações app<br>– Monitoramento, empacotamento e implantação de atualizações de segurança e recurso app<br>-Aplicativo de usuário testando (UAT)<br>-Fornecendo um pacote implantável adequado<br><br>Para obter mais informações, consulte [Apps](../get-ready/apps.md)
Monitoramento de segurança e de resposta | O cliente é responsável pela investigação e resolução de incidentes para dispositivos não - Microsoft Managed Desktop e para garantir que a equipe de operações de área de trabalho gerenciada do Microsoft é informada de quaisquer problemas que possam afetar o serviço.
Suporte de operações | O cliente é responsável por fornecer uma lista de contatos do cliente preferencial e especialistas no assunto. Microsoft precisa essas caso haja um incidente de operacionais não - Microsoft Managed Desktop. <br><br>O cliente também é responsável pela investigação e resolução de incidentes para dispositivos não - Microsoft Managed Desktop e serviços e garantir que a equipe de operações de área de trabalho gerenciada do Microsoft sempre é informada.
Infraestrutura de rede, incluindo VPN | O cliente é responsável pela instalação, configuração e gerenciamento (incluindo a solução de problemas e depuração) de todas as infraestrutura de rede e serviços, incluindo a conectividade com a internet, rede controles, a configuração de proxy e remotos infraestrutura de conectividade.<br><br>Se um proxy estiver configurado (em hardware ou software), há uma coleção de URLs que devem ser permitidas pelo proxy. O cliente é responsável por qualquer conflitos ou incompatibilidades devido aos vários proxies de solução de problemas.<br><br>Para obter mais informações, consulte [Configuração do Proxy](../get-ready/network.md).
Impressão | O cliente é responsável por instalar, manter e administrar impressoras e filas de impressão. Nuvem impressão é uma solução recomendada, mas não é necessária. 




