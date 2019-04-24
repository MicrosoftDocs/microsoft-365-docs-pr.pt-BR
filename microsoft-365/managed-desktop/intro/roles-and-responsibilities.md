---
title: Funções e responsabilidades de área de trabalho gerenciada da Microsoft
description: Este tópico descreve as funções e responsabilidades fornecidas pela Microsoft para a área de trabalho gerenciada da Microsoft.
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 161be07907754cdd7a0cd88dd3342d4b5e3c72e4
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283554"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Funções e responsabilidades de área de trabalho gerenciada da Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Quando a sua organização é registrada na área de trabalho gerenciada da Microsoft, o que a Microsoft faz para você? E quais são as responsabilidades da sua organização?

## <a name="microsofts-roles-and-responsibilities"></a>Funções e responsabilidades da Microsoft

Veja abaixo algumas das principais funções e responsabilidades que serão fornecidas pela Microsoft.

Função ou responsabilidade | Descrição
--- | ---
Gerenciamento de política MDM | A Microsoft aplicará as políticas MDM de acordo com as práticas recomendadas e considerará as solicitações de alterações na política. Também alteraremos o locatário conforme prescrito nas [políticas de dispositivos](../service-description/device-policies.md).
Suporte ao usuário final | A Microsoft fornecerá suporte ao usuário final para dispositivos, Windows e pacote de produtos do Office para todos os usuários registrados através do aplicativo Get Help pré-instalado em todos os dispositivos de área de trabalho gerenciada da Microsoft. 
Suporte do serviço de desktop gerenciado da Microsoft | A Microsoft fornecerá suporte aos departamentos de ti do cliente por meio de uma equipe de operações do Microsoft Managed desktop. Esta equipe oferecerá suporte técnico para solução de problemas, solicitações de alteração e gerenciamento de incidentes para o ambiente de área de trabalho gerenciada da Microsoft do cliente. Para obter mais informações, consulte [Administração de suporte para a área de trabalho gerenciada da Microsoft](../working-with-managed-desktop/admin-support.md).
Monitoramento de segurança | A Microsoft monitorará dispositivos de área de trabalho gerenciada da Microsoft do cliente usando o Windows Defender ATP. Se uma ameaça for detectada pelo centro de operações de segurança de área de trabalho gerenciada da Microsoft (SOC), a Microsoft notificará o cliente, isolando o dispositivo e corrigirá o problema remotamente. Para obter mais informações, consulte [segurança](../service-description/security.md).
Monitoramento e gerenciamento de atualização | A Microsoft monitorará ativamente os dispositivos de área de trabalho gerenciada da Microsoft para garantir que as atualizações de recursos e qualidade mais recentes estejam instaladas para o Microsoft Windows e o Microsoft Office. Para obter mais informações, consulte [como as atualizações são tratadas](../service-description/updates.md).
Agrupamento de usuários e dispositivos | A equipe de operações de área de trabalho gerenciada da Microsoft criará e gerenciará grupos de usuários e dispositivos necessários como parte das operações de ti. Nenhuma alteração de associação ou configuração é permitida nesses grupos. A alteração desses grupos pode levar à configuração inesperada de dispositivos e à perda de funcionalidade. Para qualquer problema ou dúvida em torno desses grupos, os administradores de ti podem entrar em contato com as operações de área de trabalho gerenciada da Microsoft. Para obter mais informações, consulte [Administração de suporte para a área de trabalho gerenciada da Microsoft](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Suas funções e responsabilidades

Veja a seguir um conjunto adicional de funções e responsabilidades comuns que não são fornecidas pela Microsoft, mas são necessárias para uma implantação bem-sucedida. Não é exaustiva, mas se aplica à maioria das organizações. Há alguns itens abaixo que a Microsoft e o cliente compartilham responsibilties. 

Função ou responsabilidade | Descrição
--- | ---
Gerenciamento de alterações | A Microsoft notificará os clientes, antecipadamente, quando as alterações precisarem ser feitas no ambiente de área de trabalho gerenciada da Microsoft. O cliente precisa ter seu próprio processo de gerenciamento de alterações e ter um contato estabelecido com a equipe de operações de área de trabalho gerenciada da Microsoft. O cliente também precisa ter recursos para revisar e aprovar essas alterações. Para obter mais informações, consulte [operações e monitoramento](../service-description/operations-and-monitoring.md).  
O gerenciamento de identidades | O cliente é responsável por criar contas de usuário, atribuindo usuários a grupos e mantendo metadados atualizados. 
Configuração e gerenciamento do Office 365 | A Microsoft é responsável por garantir que os aplicativos do Office sejam implantados para os usuários finais, e esses aplicativos são atualizados. <br><br> O cliente é responsável pelo gerenciamento de políticas e serviços do Office 365, incluindo responsabilidades de administração do Exchange Online:<br>– Administração de email<br>– Configuração de regra e caixa de correio<br>-Gerenciamento local do Exchange<br><br>O cliente também é responsável por ferramentas de colaboração, administração do SharePoint Server, gerenciamento de domínio, políticas de segurança e de informações definidas no portal de administração do Office 365. 
Suporte ao usuário final | O cliente é responsável por fornecer suporte ao usuário final para: <br>-Na infraestrutura de site: toda a conectividade de rede e Internet, a infraestrutura de VPN e a configuração do cliente, equipamento de sala de conferência local, impressoras, servidor proxy e configuração, firewalls.<br><br>-Recursos de nuvem em toda a empresa: email, SharePoint, serviços de colaboração e outras infraestruturas de nuvem que se relacionam com o espaço tecnológico de toda a empresa.<br><br>-Linha de negócios e outros aplicativos específicos da empresa.
Aplicativos | A Microsoft fornecerá orientações de implantação para aplicativos aprovados usando o Intune, quando solicitado.<br><br>O cliente é responsável por:<br>– Fornecendo uma lista de aplicativos para sua organização (fora dos aplicativos do Office 365)<br>– Gerenciamento de licenças de aplicativos<br>– Ter o tipo e a quantidade de licenças corretos<br>– Atribuição de aplicativo<br>– Atribuindo aplicativos a grupos de usuários do Azure AD<br>– Atualizações de aplicativos<br>– Monitorar, empacotar e implantar recursos de aplicativos e atualizações de segurança<br>– Teste de aplicativo do usuário (UAT)<br>– Fornecendo um pacote implantável adequado<br><br>Para obter mais informações, consulte [aplicativos](../get-ready/apps.md)
Monitoramento e resposta de segurança | O cliente é responsável por investigar e resolver incidentes de dispositivos de área de trabalho gerenciados que não são da Microsoft e garantir que a equipe de operações de área de trabalho gerenciada da Microsoft seja informada sobre qualquer problema que possa impactar o serviço.
Suporte a operações | O cliente é responsável por fornecer uma lista de contatos de clientes preferenciais e especialistas no assunto. A Microsoft precisa desses casos caso haja um incidente operacional de área de trabalho gerenciada que não seja da Microsoft. <br><br>O cliente também é responsável por investigar e resolver incidentes de dispositivos e serviços de área de trabalho gerenciados que não são da Microsoft e garantir que a equipe de operações de área de trabalho gerenciada da Microsoft seja sempre informada.
Infraestrutura de rede, incluindo VPN | O cliente é responsável pela configuração, configuração e gerenciamento (incluindo solução de problemas e depuração) de todos os serviços e infraestrutura relacionados à rede, incluindo conectividade com a Internet, controles de rede, configuração de proxy e remota infraestrutura de conectividade.<br><br>Se um proxy estiver configurado (em hardware ou software), haverá uma coleção de URLs que deve ser permitida pelo proxy. O cliente é responsável por solucionar conflitos ou incompatibilidades devido a vários proxies. Você pode adicionar proxies de rede específicos à sua organização usando as configurações que podem ser definidas. Para obter mais informações, consulte [configurações](../working-with-managed-desktop/config-setting-ref.md#proxy)configuradas.<br><br>Para obter mais informações, consulte [configuração de proxy](../get-ready/network.md).
Impressão | O cliente é responsável por instalar, manter e administrar impressoras e filas de impressão. A impressão em nuvem é uma solução recomendada, mas não é necessária. 




