---
title: Funções e responsabilidades da Área de Trabalho Gerenciada da Microsoft
description: Este artigo descreve as funções e responsabilidades fornecidas pela Microsoft para a área de trabalho gerenciada da Microsoft.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8ced46ea30c7225fd3e5c8f1309ef482542e51b2
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445778"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Funções e responsabilidades da Área de Trabalho Gerenciada da Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Quando a sua organização é registrada na área de trabalho gerenciada da Microsoft, o que a Microsoft faz para você? E quais são as responsabilidades da sua organização?

## <a name="microsofts-roles-and-responsibilities"></a>Funções e responsabilidades da Microsoft

A Microsoft fornece as principais funções e responsabilidades:

Função ou responsabilidade | Descrição
--- | ---
Gerenciamento de política MDM | A Microsoft aplicará as políticas MDM de acordo com as práticas recomendadas e considerará as solicitações de alterações na política. Também alteraremos o locatário conforme prescrito nas [políticas de dispositivos](../service-description/device-policies.md).
suporte ao usuário | Fornecemos suporte ao usuário para dispositivos, Windows e para o pacote de produtos do Microsoft 365 para todos os usuários registrados por meio do aplicativo Get Help pré-instalado em todos os dispositivos de área de trabalho gerenciada da Microsoft. 
Suporte do serviço de desktop gerenciado da Microsoft | A Microsoft fornecerá suporte ao seu departamento de ti por meio de uma equipe de operações de área de trabalho gerenciada da Microsoft. Esta equipe oferecerá suporte técnico para solução de problemas, solicitações de alteração e gerenciamento de incidentes para o ambiente de área de trabalho gerenciada da Microsoft do cliente. Para obter mais informações, consulte [Administração de suporte para a área de trabalho gerenciada da Microsoft](../working-with-managed-desktop/admin-support.md).
Monitoramento de segurança | A Microsoft monitorará seus dispositivos de área de trabalho gerenciada da Microsoft usando o Microsoft defender ATP. Se o SOC (centro de operações de segurança) do Microsoft Managed desktop detectar uma ameaça, você será notificado, isolando o dispositivo e corrigirá o problema remotamente. Para obter mais informações, consulte [segurança](../service-description/security.md).
Monitoramento e gerenciamento de atualização | Monitoramos ativamente seus dispositivos de área de trabalho gerenciada da Microsoft para garantir que as atualizações de qualidade e recursos mais recentes estejam instaladas para o Microsoft Windows e o Microsoft Office. Para obter mais informações, consulte [como as atualizações são tratadas](../service-description/updates.md).
Agrupamento de usuários e dispositivos | A equipe de operações de área de trabalho gerenciada da Microsoft criará e gerenciará grupos de usuários e dispositivos necessários como parte das operações de ti. Nenhuma alteração de associação ou configuração é permitida nesses grupos. A alteração desses grupos pode levar à configuração inesperada de dispositivos e à perda de funcionalidade. Para qualquer problema ou dúvida em torno desses grupos, os administradores de ti podem entrar em contato com as operações de área de trabalho gerenciada da Microsoft. Para obter mais informações, consulte [Administração de suporte para a área de trabalho gerenciada da Microsoft](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Suas funções e responsabilidades

Esse conjunto adicional de funções e responsabilidades comuns é necessário para a implantação, mas não é fornecido pela Microsoft. Não é exaustiva, mas se aplica à maioria das organizações. Há alguns itens que você e a Microsoft compartilham responsabilidade. 

Função ou responsabilidade | Descrição
--- | ---
Gerenciamento de alterações | A Microsoft notificará os clientes, antecipadamente, quando as alterações precisarem ser feitas no ambiente de área de trabalho gerenciada da Microsoft. Para obter mais informações, consulte [Service Changes and Communication](../service-description/servicechanges.md).<br><br>Você deve ter seu próprio processo de gerenciamento de alterações e ter um contato estabelecido com a equipe de operações de área de trabalho gerenciada da Microsoft. Você também deve ter recursos para revisar e aprovar essas alterações. Para obter mais informações, consulte [operações e monitoramento](../service-description/operations-and-monitoring.md).  
O gerenciamento de identidades | Você é responsável pela criação de contas de usuário, pela atribuição de usuários a grupos e pela manutenção dos metadados. 
Microsoft 365 aplicativos para gerenciamento e configuração empresarial | A Microsoft é responsável por garantir que os aplicativos do Office sejam implantados para os usuários e que esses aplicativos sejam atualizados. <br><br> Você é responsável por gerenciar serviços e políticas do Microsoft 365, incluindo responsabilidades de administração do Exchange Online:<br>– Administração de email<br>– Configuração de regra e caixa de correio<br>-Gerenciamento local do Exchange<br><br>Você também é responsável por ferramentas de colaboração, administração do SharePoint Server, gerenciamento de domínio e políticas de segurança e de informações que são definidas no centro de administração do Microsoft 365. 
Suporte ao usuário | Você deve fornecer suporte ao usuário para: <br>-Infraestrutura no local: toda a conectividade de rede e Internet, a infraestrutura de VPN e a configuração do cliente, equipamento de sala de conferência local, impressoras, servidor proxy e configuração e firewalls.<br><br>-Recursos de nuvem em toda a empresa: email, SharePoint, serviços de colaboração e outras infraestruturas de nuvem que se relacionam com o espaço tecnológico de toda a empresa.<br><br>-Linha de negócios e outros aplicativos específicos da empresa.
Aplicativos | Funções e responsabilidades variam um pouco para os aplicativos fornecidos como parte da área de trabalho gerenciada da Microsoft versus os aplicativos que você fornece. <br><br>Para aplicativos fornecidos pela Microsoft (Microsoft 365 aplicativos para empresas que compõem Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, Teams e OneNote), a **Microsoft** oferecerá serviço completo para implantação, atualização e suporte. **Você** deve obter e atribuir licenças para esses aplicativos, adicionar usuários a grupos de segurança e gerenciar o fim da vida e implantar quaisquer Complementos necessários.<br><br>Para aplicativos que você fornece (como seus aplicativos de linha de negócios), se você os empacota ou não é um fornecedor da Microsoft para fazer isso, **você** é responsável por estas ações: <br><br>– Identificando aplicativos necessários para grupos de usuários de destino<br>– Criando e gerenciando grupos do Azure AD para implantação de aplicativos<br>Pacotes de aplicativos para atender aos padrões de implantação do Microsoft Intune<br>-Carregando aplicativos no Microsoft Intune<br>– Testar aplicativos no ambiente de área de trabalho gerenciada da Microsoft<br>– Testar aplicativos com seus usuários<br>– Gerenciando e atribuindo usuários a aplicativos<br>– Identificar e implantar atualizações de aplicativos por meio do Microsoft Intune<br>– Desinstalando e removendo aplicativos quando eles tiverem sido desativados<br>-Aquisição e atribuindo licenças<br>– Fornecer suporte ao usuário para aplicativos de linha de negócios<br>– Gerenciamento remoto das configurações do aplicativo<br><br>A **Microsoft** fornecerá ferramentas de implantação do Microsoft Intune para fornecer os aplicativos para clientes remotos.<br><br>Para obter mais informações, consulte [aplicativos](../get-ready/apps.md).
Monitoramento e resposta de segurança | Você é responsável por investigar e resolver incidentes para dispositivos que não são dispositivos de área de trabalho gerenciada pela Microsoft e garantir que a equipe de operações de área de trabalho gerenciada da Microsoft seja informada sobre qualquer problema que possa impactar o serviço.
Suporte a operações | Você deve fornecer uma lista de contatos preferidos e especialistas no assunto em sua organização. Precisamos desses casos em caso de um incidente operacional não relacionado à área de trabalho gerenciada da Microsoft. <br><br>Você também é responsável pela investigação e pela resolução de incidentes para dispositivos e serviços que não estão na área de trabalho gerenciada da Microsoft e garantem que a equipe de operações de área de trabalho gerenciada da Microsoft seja sempre informada.
Infraestrutura de rede, incluindo VPN | Você é responsável pela configuração, configuração e gerenciamento (incluindo solução de problemas e depuração) de todos os serviços e infraestruturas relacionados à rede, incluindo conectividade com a Internet, controles de rede, configuração de proxy e infraestrutura de conectividade remota.<br><br>Se um proxy estiver configurado (em hardware ou software), haverá uma coleção de URLs que deve ser permitida pelo proxy. Você é responsável por solucionar conflitos ou incompatibilidades devido a vários proxies. Você pode adicionar proxies de rede específicos à sua organização usando as configurações que podem ser definidas. Para obter mais informações, consulte [configurações configuradas](../working-with-managed-desktop/config-setting-ref.md#proxy).<br><br>Para obter mais informações, consulte [configuração de proxy](../get-ready/network.md).
Impressão | Você é responsável pela instalação, manutenção e administração de impressoras e filas de impressão. A impressão em nuvem é uma solução recomendada, mas não é necessária. 




