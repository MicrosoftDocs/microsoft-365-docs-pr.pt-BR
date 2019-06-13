---
title: Funções e responsabilidades de área de trabalho gerenciada da Microsoft
description: Este tópico descreve as funções e responsabilidades fornecidas pela Microsoft para a área de trabalho gerenciada da Microsoft.
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 302f6b3b993a62cdd2d934ac9acd43ad57540cd1
ms.sourcegitcommit: 498340389e1c34f49f0b2da382c23c8d5334ae47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2019
ms.locfileid: "34913052"
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
Aplicativos | Funções e responsabilidades variam um pouco para os aplicativos fornecidos como parte da área de trabalho gerenciada da Microsoft em comparação com as que você fornecer. <br><br>Para aplicativos fornecidos pela Microsoft (Office 365 ProPlus Standard Suite que inclui o Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business {ainda true ou substituído pelo Teams?} e o OneNote), a **Microsoft** oferecerá serviço completo para o implantação, atualização e suporte. **Você** deve obter e atribuir licenças para esses aplicativos, adicionar usuários a grupos de segurança e gerenciar o fim da vida útil e implantar qualquer complemento do Office 365 que você precisa.<br><br>Para aplicativos que você fornece (como seus aplicativos de linha de negócios), se você os empacota ou não é um fornecedor da Microsoft para fazer isso, **você** é responsável por estas ações: <br><br>– Identificando aplicativos necessários para grupos de usuários de destino<br>– Criando e gerenciando grupos do Azure AD para implantação de aplicativos<br>Pacotes de aplicativos para atender aos padrões de implantação do Microsoft Intune<br>-Carregando aplicativos no Microsoft Intune<br>– Testar aplicativos no ambiente de área de trabalho gerenciada da Microsoft<br>– Testando aplicativos com seus usuários finais<br>– Gerenciando e atribuindo usuários a aplicativos<br>– Identificar e implantar atualizações de aplicativos por meio do Microsoft Intune<br>– Desinstalar e remover aplicativos quando eles forem desativados<br>-Aquisição e atribuindo licenças<br>– Fornecendo suporte ao usuário final para aplicativos de linha de negócios<br>– Gerenciamento remoto das configurações do aplicativo<br><br>A **Microsoft** fornecerá ferramentas de implantação do Microsoft Intune para fornecer os aplicativos para clientes remotos.<br><br>Para obter mais informações, consulte [aplicativos](../get-ready/apps.md)
Monitoramento e resposta de segurança | O cliente é responsável por investigar e resolver incidentes de dispositivos de área de trabalho gerenciados que não são da Microsoft e garantir que a equipe de operações de área de trabalho gerenciada da Microsoft seja informada sobre qualquer problema que possa impactar o serviço.
Suporte a operações | O cliente é responsável por fornecer uma lista de contatos de clientes preferenciais e especialistas no assunto. A Microsoft precisa desses casos caso haja um incidente operacional de área de trabalho gerenciada que não seja da Microsoft. <br><br>O cliente também é responsável por investigar e resolver incidentes de dispositivos e serviços de área de trabalho gerenciados que não são da Microsoft e garantir que a equipe de operações de área de trabalho gerenciada da Microsoft seja sempre informada.
Infraestrutura de rede, incluindo VPN | O cliente é responsável pela configuração, configuração e gerenciamento (incluindo solução de problemas e depuração) de todos os serviços e infraestrutura relacionados à rede, incluindo conectividade com a Internet, controles de rede, configuração de proxy e remota infraestrutura de conectividade.<br><br>Se um proxy estiver configurado (em hardware ou software), haverá uma coleção de URLs que deve ser permitida pelo proxy. O cliente é responsável por solucionar conflitos ou incompatibilidades devido a vários proxies. Você pode adicionar proxies de rede específicos à sua organização usando as configurações que podem ser definidas. Para obter mais informações, consulte [configurações](../working-with-managed-desktop/config-setting-ref.md#proxy)configuradas.<br><br>Para obter mais informações, consulte [configuração de proxy](../get-ready/network.md).
Impressão | O cliente é responsável por instalar, manter e administrar impressoras e filas de impressão. A impressão em nuvem é uma solução recomendada, mas não é necessária. 




