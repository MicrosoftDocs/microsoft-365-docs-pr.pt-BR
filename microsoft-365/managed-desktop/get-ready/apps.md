---
title: Aplicativos na Área de Trabalho Gerenciada da Microsoft
description: Explica como os aplicativos são manipulados, incluindo como empacotar, implantar e dar suporte a eles.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: d970ac1a28c62703f648e4fbf6f66e2f825a6188
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574614"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Aplicativos na Área de Trabalho Gerenciada da Microsoft

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Aplicativos geralmente

A Microsoft inclui determinados aplicativos principais juntamente com a licença do Microsoft 365 E3 ou E5 necessária para participar da Área de Trabalho Gerenciada da Microsoft. No entanto, mesmo que forneçamos esses aplicativos, você ainda tem certas responsabilidades e ações a ser concluídas.

Você também pode implantar aplicativos adicionais que não são da Microsoft para seus usuários para autoatendê por meio do Portal da Empresa ou uma instalação em segundo plano necessária, todos usando o pipeline de implantação do Microsoft Intune. Se você tiver a experiência, poderá migrar os aplicativos de que precisa. como alternativa, o Microsoft Consulting Services (MCS) ou fornecedores que não sejam da Microsoft terão o prazer de ajudá-lo com um projeto de empacotamento e migração. Para obter mais informações sobre como trabalhar com MCS, consulte [Working with Microsoft Consulting Services](apps-MCS.md).


## <a name="apps-provided-by-microsoft"></a>Aplicativos fornecidos pela Microsoft

Incluído na licença da Área de Trabalho Gerenciada da Microsoft estão versões de 64 bits dos aplicativos no Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business e OneNote.) As versões clique para executar do Microsoft  Project e do Visio não estão incluídas por padrão, mas você pode solicitá-las para serem adicionadas. Para obter mais informações sobre esses aplicativos, consulte [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>O que a Microsoft faz para dar suporte aos aplicativos que fornecemos

A Microsoft fornecerá serviço completo para implantação, atualização e suporte para os aplicativos do Microsoft 365 incluídos para aplicativos corporativos. As versões clique para executar do Microsoft  Project e do Visio não estão incluídas por padrão, mas a Área de Trabalho Gerenciada da Microsoft fornecerá grupos de implantação permitindo que o administrador de IT gerencie licenças e implante esses aplicativos adequadamente para sua organização. A Microsoft dará suporte aos usuários desses aplicativos por meio dos canais de suporte da Área de Trabalho Gerenciada da Microsoft.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>O que você precisa fazer para dar suporte aos aplicativos que fornecemos

Ainda há certas coisas que você precisa fazer com esses aplicativos:

- **Atribuir licenças** - Você é responsável por obter e atribuir as licenças apropriadas aos usuários do Microsoft 365 Apps para empresas.
- **Adicionar usuários a** grupos de segurança - Se você estiver usando o Microsoft Project ou o Visio, o administrador de TI deverá adicionar esses usuários aos grupos de implantação apropriados. Os administradores de IT também são responsáveis por recuperar licenças desses usuários se saírem da empresa.
- Implantar complementos do Microsoft 365 - Se você precisar de complementos para qualquer um dos Aplicativos do Microsoft 365 para **aplicativos corporativos, implante-os** centralmente, como qualquer outro aplicativo do Windows 32. 

## <a name="apps-you-provide"></a>Aplicativos que você fornece

Você provavelmente tem outros aplicativos necessários para suas operações de negócios. Esses aplicativos só podem ser implantados em dispositivos da Área de Trabalho Gerenciada da Microsoft usando o pipeline de implantação do Microsoft Intune. Se o aplicativo precisar dele, você pode empacotá-los por um fornecedor (que pode ser um fornecedor que não seja a Microsoft ou o Microsoft Consulting Services (MCS)) ou se tiver os meios, você mesmo poderá empacotá-los. Em seguida, adicione esses pacotes ao portal da Área de Trabalho Gerenciada da Microsoft e atribua-os aos grupos do Azure Active Directory para disparar a implantação. 

Se você implantar seus aplicativos usando o Microsoft Endpoint Configuration Manager, a Área de Trabalho Gerenciada da Microsoft poderá fornecer uma consulta para avaliar seus aplicativos e descobrir quais estão prontos para migrar para o Microsoft Intune e quais podem exigir algum ajuste.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Preparando seus próprios aplicativos para inclusão na Área de Trabalho Gerenciada da Microsoft
Revise seus aplicativos, verificando:

- Nenhum dos aplicativos é proibido ou tem comportamento restrito, conforme descrito em Requisitos de aplicativo da [Área de Trabalho Gerenciada da Microsoft.](../service-description/mmd-app-requirements.md)
- Os aplicativos devem estar prontos para gerenciamento pelo Microsoft Intune. Para obter mais informações sobre este tópico, consulte Implantação de aplicativos do [Windows 10 usando o Microsoft Intune](/intune/apps-windows-10-app-deploy) e Adicionar [aplicativos ao Microsoft Intune](/intune/apps-add).
- Outros requisitos de pré-empacotamento, como fornecimento de chaves de licença, acordo com termos de licença e conexões de servidor de pré-configuração.

### <a name="decide-how-to-package-apps"></a>Decidir como empacotar aplicativos

Alguns editores de software independentes podem exigir que seus aplicativos sejam empacotados antes que sejam implantados centralmente. "Empacotamento" significa que o instalador do aplicativo está configurado com configurações como chaves de licença, locais de servidor remoto ou atalhos da área de trabalho para que o aplicativo possa ser instalado em segundo plano.

Há três opções para obter seus aplicativos empacotados: 


- Você pode empacotar aplicativos sozinho
- Você pode trabalhar com um fornecedor que não seja da Microsoft
- Você pode interagir com MCS para empacotar seus aplicativos. Trabalhe com seu representante de conta da Microsoft. Para obter mais informações, consulte [Working with Microsoft Consulting Services](apps-MCS.md).



## <a name="deploying-apps"></a>Implantando aplicativos

Qualquer método que você use para obter aplicativos empacotados, uma vez concluído, você estará pronto para seguir as etapas em Implantar aplicativos para dispositivos da Área de [Trabalho Gerenciada da Microsoft.](../get-started/deploy-apps.md)


## <a name="steps-to-get-ready"></a>Etapas para se preparar

1. Revise [os pré-requisitos da Área de Trabalho Gerenciada da Microsoft.](prerequisites.md)
2. Use [ferramentas de avaliação de preparação.](readiness-assessment-tool.md)
3. [Pré-requisitos para contas de convidados](guest-accounts.md)
4. [Configuração de rede na Área de Trabalho Gerenciada da Microsoft](network.md)
5. [Preparar certificados e perfis de rede da Área de Trabalho Gerenciada da Microsoft](certs-wifi-lan.md)
6. [Preparar o acesso aos recursos locais da Área de Trabalho Gerenciada da Microsoft](authentication.md)
7. [Aplicativos na Área de Trabalho Gerenciada](apps.md) da Microsoft (Este artigo)
8. [Preparar unidades mapeadas da Área de Trabalho Gerenciada da Microsoft](mapped-drives.md)
9. [Preparar recursos de impressão da Área de Trabalho Gerenciada da Microsoft](printing.md)
