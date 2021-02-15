---
title: Aplicativos na Área de Trabalho Gerenciada da Microsoft
description: Explica como os aplicativos são manipulados, incluindo como empacotá-los, implantá-los e dar suporte a eles.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 20d68ec007ccda82816ad2288428016019f6d4b2
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840688"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Aplicativos na Área de Trabalho Gerenciada da Microsoft

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Aplicativos geralmente

A Microsoft inclui determinados aplicativos importantes, juntamente com a licença do Microsoft 365 E3 ou E5 necessária para participar da Área de Trabalho Gerenciada da Microsoft. No entanto, embora forneçamos esses aplicativos, você ainda tem determinadas responsabilidades e ações a concluir.

Você também pode implantar aplicativos adicionais que não são da Microsoft para seus usuários para autoatenDados por meio do Portal da Empresa ou uma instalação em segundo plano necessária, todos usando o pipeline de implantação do Microsoft Intune. Se você tiver a experiência, poderá migrar os aplicativos de que precisa. como alternativa, os Serviços de Consultoria da Microsoft (MCS) ou fornecedores que não são da Microsoft vão ficar satisfeitos em ajudá-lo com um projeto de empacotamento e migração. Para obter mais informações sobre como trabalhar com MCS, consulte [Trabalhando com serviços de consultoria da Microsoft.](apps-MCS.md)


## <a name="apps-provided-by-microsoft"></a>Aplicativos fornecidos pela Microsoft

Incluídas na sua licença da Área de Trabalho Gerenciada da Microsoft estão versões de 64 bits dos aplicativos no Microsoft 365 Apps para Empresas Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business e OneNote.) As versões Clique para Executar do Microsoft  Project e do Visio não estão incluídas por padrão, mas você pode solicitar que elas sejam adicionadas. Para obter mais informações sobre esses aplicativos, consulte Instalar o [Microsoft Project ou o Microsoft Visio em dispositivos da Área de Trabalho Gerenciada da Microsoft.](../get-started/project-visio.md)

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>O que a Microsoft faz para dar suporte aos aplicativos que fornecemos

A Microsoft fornecerá serviço completo para a implantação, atualização e suporte para os aplicativos do Microsoft 365 Apps para empresas incluídos. As versões Clique para Executar do Microsoft  Project e do Visio não estão incluídas por padrão, mas a Área de Trabalho Gerenciada da Microsoft fornecerá grupos de implantação permitindo que seu administrador de IT gerencie licenças e implante esses aplicativos adequadamente para sua organização. A Microsoft dará suporte aos usuários desses aplicativos por meio dos canais de suporte da Área de Trabalho Gerenciada da Microsoft.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>O que você precisa fazer para dar suporte aos aplicativos que fornecemos

Ainda há certas coisas que você precisa fazer com esses aplicativos:

- **Atribuir licenças** - Você é responsável por obter e atribuir as licenças apropriadas aos usuários do Microsoft 365 Apps para empresas.
- **Adicionar usuários a grupos de** segurança - Se você estiver usando o Microsoft Project ou o Visio, seu administrador de TI deverá adicionar esses usuários aos grupos de implantação apropriados. Os administradores de IT também são responsáveis por recuperar licenças desses usuários se eles saírem da empresa.
- Implantar complementos do **Microsoft 365** – se você precisar de complementos para qualquer um dos aplicativos do Microsoft 365 Apps para empresas, implante-os centralmente como qualquer outro aplicativo do Windows 32. 

## <a name="apps-you-provide"></a>Aplicativos que você fornece

Você provavelmente tem outros aplicativos necessários para suas operações de negócios. Esses aplicativos só podem ser implantados em dispositivos da Área de Trabalho Gerenciada da Microsoft usando o pipeline de implantação do Microsoft Intune. Se o aplicativo precisar dele, você poderá empacotá-los por um fornecedor (que pode ser um fornecedor que não seja da Microsoft ou o Microsoft Consulting Services (MCS)) ou, se você tiver os meios, poderá empacotá-los por conta própria. Em seguida, adicione esses pacotes ao portal da Área de Trabalho Gerenciada da Microsoft e atribua-os aos grupos do Azure Active Directory para acionar a implantação. 

Se você atualmente implantar seus aplicativos usando o Microsoft Endpoint Configuration Manager, a Área de Trabalho Gerenciada da Microsoft poderá fornecer uma consulta para avaliar seus aplicativos e descobrir quais estão prontos para migrar para o Microsoft Intune e quais podem exigir algum ajuste.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Preparando seus próprios aplicativos para inclusão na Área de Trabalho Gerenciada da Microsoft
Revise seus aplicativos, verificando:

- Nenhum dos aplicativos é proibido ou tem comportamento restrito, conforme descrito nos requisitos de aplicativo da [Área de Trabalho Gerenciada da Microsoft.](https://aka.ms/app-req)
- Os aplicativos devem estar prontos para gerenciamento pelo Microsoft Intune. Para obter mais informações sobre este tópico, consulte a implantação de aplicativos do Windows 10 usando o [Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) e adicionar aplicativos [ao Microsoft Intune.](https://docs.microsoft.com/intune/apps-add)
- Outros requisitos de pré-empacotamento, como fornecimento de chaves de licença, contrato com termos de licença e pré-configuração de conexões de servidor.

### <a name="decide-how-to-package-apps"></a>Decidir como empacotar aplicativos

Alguns editores de software independentes podem exigir que seus aplicativos sejam empacotados antes da implantação centralizada. "Empacotamento" significa que o instalador do aplicativo é configurado com configurações como chaves de licença, locais do servidor remoto ou atalhos da área de trabalho para que o aplicativo possa ser instalado em segundo plano.

Há três opções para fazer com que seus aplicativos sejam empacotados: 


- Você mesmo pode empacotar aplicativos
- Você pode trabalhar com um fornecedor que não seja da Microsoft
- Você pode se envolver com MCS para empacotar seus aplicativos. Trabalhe com seu representante de conta da Microsoft. Para obter mais informações, consulte [Trabalhando com os Serviços de Consultoria da Microsoft.](apps-MCS.md)



## <a name="deploying-apps"></a>Implantando aplicativos

Seja qual for o método usado para obter aplicativos empacotados, depois de concluído, você estará pronto para seguir as etapas em Implantar aplicativos em dispositivos da Área de Trabalho [Gerenciada da Microsoft.](../get-started/deploy-apps.md)


