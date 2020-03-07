---
title: Aplicativos na área de trabalho gerenciada da Microsoft
description: ''
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: adb6423d5c014b5f02fc272f9653abebc14cf543
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557569"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Aplicativos na área de trabalho gerenciada da Microsoft

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Aplicativos geralmente

A Microsoft inclui certos aplicativos-chave, juntamente com a licença do Microsoft 365 E3 ou E5 necessária para participar da área de trabalho gerenciada da Microsoft. No entanto, mesmo que forneçamos esses aplicativos, você ainda tem determinadas responsabilidades e ações para concluir.

Você também pode implantar aplicativos adicionais não-Microsoft nos seus usuários finais para autoatendimento por meio do portal da empresa ou uma instalação de segundo plano necessária, tudo usando o pipeline de implantação do Microsoft Intune. Se você tiver o conhecimento, poderá migrar os aplicativos que precisa sozinho; Como alternativa, os fornecedores MCS (serviços de consultoria da Microsoft) ou não da Microsoft ficarão satisfeitos para ajudá-lo com um projeto de pacote e migração. Para obter mais informações sobre como trabalhar com MCS, confira [trabalhar com serviços de consultoria da Microsoft](apps-MCS.md).


## <a name="apps-provided-by-microsoft"></a>Aplicativos fornecidos pela Microsoft

Incluído na sua licença de área de trabalho gerenciada da Microsoft são versões de 64 bits dos aplicativos no Office 365 ProPlus Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business e OneNote). As versões de clique para executar do Microsoft Project e do Visio *não* estão incluídas por padrão, mas você pode solicitar que sejam adicionadas. Para obter mais informações sobre esses aplicativos, consulte [instalar o Microsoft Project ou o Microsoft Visio em dispositivos de área de trabalho gerenciada da Microsoft](../get-started/project-visio.md).

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>O que a Microsoft faz para dar suporte aos aplicativos que fornecemos

A Microsoft fornecerá serviço completo para a implantação, atualização e suporte para os aplicativos incluídos do Office 365 ProPlus. As versões de clique para executar do Microsoft Project e do Visio *não* são incluídas por padrão, mas a área de trabalho gerenciada da Microsoft fornecerá grupos de implantação que permitem ao administrador de ti gerenciar licenças e implantar esses aplicativos de forma adequada para sua organização. A Microsoft dará suporte aos usuários finais desses aplicativos por meio dos canais de suporte do Microsoft Managed desktop.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>O que você precisa fazer para dar suporte aos aplicativos que fornecemos

Ainda há algumas coisas que você precisa fazer com estes aplicativos:

- **Atribuir licenças** – você é responsável por obter e atribuir as licenças apropriadas aos usuários finais do Office 365 ProPlus.
- **Adicionar usuários a grupos de segurança** -se você estiver usando o Microsoft Project ou o Visio, seu administrador de ti deverá adicionar esses usuários aos grupos de implantação apropriados. Os administradores de ti também são responsáveis por recuperar licenças desses usuários, caso eles saiam da empresa.
- **Implantar os complementos do office 365** -se você precisar de qualquer complemento para qualquer um dos aplicativos do Office 365 ProPlus, implante-os centralmente como qualquer outro aplicativo do Windows 32. 

## <a name="apps-you-provide"></a>Aplicativos que você fornece

Obviamente, você provavelmente tem vários outros aplicativos necessários para suas operações de negócios. Eles só podem ser implantados em dispositivos de área de trabalho gerenciada da Microsoft usando o pipeline de implantação do Microsoft Intune. Se o aplicativo precisar dele, você pode fazer com que ele seja empacotado por um fornecedor (que pode ser um fornecedor que não seja da Microsoft ou o Microsoft Consulting Services (MCS)) ou, se você tiver os meios, você pode empacotá-los por conta própria. Você adiciona esses pacotes ao portal de área de trabalho gerenciada da Microsoft e os atribui aos grupos do Azure Active Directory para acionar a implantação. 

Se, no momento, você implantar seus aplicativos usando o Microsoft Endpoint Configuration Manager, o Microsoft Managed desktop pode fornecer uma consulta para avaliar seus aplicativos e descobrir quais estão prontos para migrar para o Microsoft Intune e quais deles podem exigir alguns Just.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Preparando seus próprios aplicativos para inclusão na área de trabalho gerenciada da Microsoft
Revise seus aplicativos, verificação:

- Nenhum dos aplicativos é proibido ou tem comportamento restrito, conforme descrito nos [requisitos do aplicativo da área de trabalho gerenciada da Microsoft](https://aka.ms/app-req).
- Os aplicativos devem estar prontos para gerenciamento pelo Microsoft Intune. Para saber mais sobre isso, confira [implantação de aplicativo do Windows 10 usando o Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) e [adicione aplicativos ao Microsoft Intune](https://docs.microsoft.com/intune/apps-add).
- Outros requisitos de pré-embalagem, como fornecer chaves de licença, contrato com os termos de licença e definições de configuração de servidor.

### <a name="decide-how-to-package-apps"></a>Decidir como empacotar aplicativos

Alguns fornecedores de software independentes podem exigir que seus aplicativos sejam empacotados antes de serem implantados centralmente. "Empacotar" significa que o instalador do aplicativo é configurado com configurações como chaves de licença, locais de servidor remoto ou atalhos de área de trabalho para que o aplicativo possa ser instalado em segundo plano.

Há três opções para obter seus aplicativos empacotados: 


- Você mesmo pode empacotar aplicativos
- Você pode trabalhar com um fornecedor que não seja da Microsoft
- Você pode entrar com a MCS para empacotar seus aplicativos. Trabalhe com seu representante de conta da Microsoft. Para obter mais detalhes, consulte [Working with Microsoft Consulting Services](apps-MCS.md).







## <a name="deploying-apps"></a>Implantando aplicativos

Seja qual for o método que você usa para obter aplicativos, uma vez concluído, você está pronto para seguir as etapas em [implantar aplicativos em dispositivos de área de trabalho gerenciada da Microsoft](../get-started/deploy-apps.md).


