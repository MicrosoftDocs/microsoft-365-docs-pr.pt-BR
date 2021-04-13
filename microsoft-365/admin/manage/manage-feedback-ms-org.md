---
title: Gerenciar comentários da Microsoft para sua organização
f1.keywords:
- NOCSH
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Gerencie comentários que os usuários podem enviar para a Microsoft sobre produtos da Microsoft.
ms.openlocfilehash: 490081ace32203d015ee8cf3561ccf0ae978bace
ms.sourcegitcommit: dcc6bfd228ca9070975ce9eb14574e084f9ed92c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51657002"
---
# <a name="manage-microsoft-feedback-for-your-organization"></a>Gerenciar comentários da Microsoft para sua organização

Como administrador de uma organização do Microsoft 365, agora há várias políticas para ajudá-lo a gerenciar a coleção de comentários e a experiência de envolvimento do cliente de seus usuários ao usar aplicativos do Microsoft 365. Você pode criar e usar grupos de diretórios existentes do Azure Active em sua organização para cada uma dessas políticas. Com essas polícias, você pode controlar como diferentes departamentos em sua organização podem enviar comentários para a Microsoft. A Microsoft revisa todos os comentários enviados pelos clientes e usa esses comentários para melhorar o produto. Manter as experiências de comentários **ativas** permite que você veja o que seus usuários estão dizendo sobre os produtos da Microsoft que estão usando. Os comentários que coletamos de seus usuários estarão disponíveis em breve no Centro de administração do Microsoft 365.

Para saber mais sobre os tipos de comentários e como a Microsoft usa comentários do usuário, consulte Saiba mais sobre os [comentários da Microsoft para sua organização.](../misc/feedback-user-control.md)

A tabela a seguir representa quais aplicativos e serviços estão conectados atualmente às políticas de feedback mostradas na tabela de políticas de feedback abaixo. Consulte abaixo a tabela para ver exemplos de captura de tela.

|**Aplicativos & Serviços**|**Comentários no produto** <br> |**Pesquisas no produto** <br> |**Coleção Metadata** <br> |**Envolvimento do cliente** <br> |
|:-----|:-----|:-----|:-----|:-----|
|**Access**|Sim|Sim|Sim|Sim|
|**Excel**|Sim|Sim|Sim|Sim|
|**Office.com**|Em breve|Em breve|Em breve|Em breve|
|**OneNote**|Sim|Sim|Sim|Sim|
|**OneDrive**|[Algumas configurações atualmente gerenciadas por outros controles.](/onedrive/disable-contact-support-send-feedback)||||
|**Outlook**|Em breve|Em breve|Em breve|Em breve|
|**PowerPoint**|Sim|Sim|Sim|Sim|
|**Project**|Em breve|Em breve|Em breve|Em breve|
|**Publicador**|Sim|Sim|Sim|Sim|
|**SharePoint**|[Algumas configurações atualmente gerenciadas por outros controles.](/powershell/module/sharepoint-online/set-spotenant)||||
|**Teams**|[Algumas configurações atualmente gerenciadas por outros controles.](/microsoftteams/manage-feedback-policies-in-teams)||||
|**Word**|Sim|Sim|Sim|Sim|
|**Visio**|Sim|Sim|Sim|Sim|
|**Yammer**|Sim|Sim|Sim|Sim|

[Consulte aqui alguns exemplos de pesquisas no produto e comentários.](https://docs.microsoft.com/microsoft-365/admin/misc/feedback-user-control?view=o365-worldwide#in-product-surveys)

**Coleção Metadata**

:::image type="content" source="../../media/feedback-metadata2.png" alt-text="Captura de tela: página comentários mostrando exemplo de metadados":::

**Envolvimento do cliente**

:::image type="content" source="../../media/feedback-in-product-customer-engagement.png" alt-text="Captura de tela: Exemplo de pergunta de pesquisa do cliente no produto":::

## <a name="before-you-begin"></a>Antes de começar

Seus dispositivos devem estar em um número mínimo de com build para usar essas políticas. Consulte a tabela abaixo para saber mais.

|**Build #**|**Win32**|**iOS**|**Android**|**Mac**|**Web**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Comentários no produto|Pelo menos 16.0.13328|Pelo menos 2,42|Pelo menos 16.0.13328|Pelo menos 16,42|Disponível publicamente|
|Pesquisas no produto|Pelo menos 16.0.13328|Pelo menos 2,42|Pelo menos 16.0.13426|Pelo menos 16,42|Lançamento pendente|
|Coleção Metadata|Pelo menos 16.0.13328|Pelo menos 2,42|Pelo menos 16.0.13328|Pelo menos 16,42|Disponível publicamente|
|Envolvimento do cliente|Pelo menos 16.0.13328|Pelo menos 2,42|Pelo menos 16.0.13426|Pelo menos 16,42|Lançamento pendente|

## <a name="specific-policies-you-can-configure"></a>Políticas específicas que você pode configurar

### <a name="feedback-policies"></a>Políticas de feedback

|**Nome da política**|**Estado padrão**|**Resumo do controle**|
|:-----|:-----|:-----|
|Permitir que os usuários enviem comentários para a Microsoft|Habilitado|Controla pontos de entrada de comentários entre aplicativos|
|Permitir que os usuários recebam e respondam a pesquisas no produto da Microsoft|Habilitado|Prompts de pesquisa de controles dentro do produto|
|Permitir que os usuários incluam capturas de tela e anexos quando enviarem comentários à Microsoft|Desabilitado|Determina quais metadados o usuário pode decidir enviar com comentários/pesquisas|
|Permitir que a Microsoft acompanhe os comentários enviados pelos usuários|Desabilitado|Determina se o usuário pode compartilhar informações de contato com comentários/pesquisas|
|Permitir que os usuários incluam arquivos de log e exemplos de conteúdo quando os comentários são enviados à Microsoft|Desabilitado|Determina metadados que o usuário pode decidir enviar com comentários/pesquisas|

## <a name="configure-policies"></a>Configurar políticas

1. Acesse e [https://config.office.com](https://config.office.com) faça logon como usuário com permissões globais de administrador.
1. Selecione **Personalização e** Gerenciamento **de Política.**
1. Selecione **Criar**.
1. Insira **o nome e** a **descrição**.
1. Escolha os grupos de diretórios do Azure Active que você deseja configurar.
1. Pesquise **comentários** e **pesquisas.**
1. Para cada política listada, de definir o valor que você deseja.

Para obter mais informações, consulte [Visão geral do serviço de política de nuvem do Office.](/deployoffice/overview-office-cloud-policy-service)

Essas configurações de política também estarão disponíveis se você usar a Política de Grupo. Para usar essas configurações de política, baixe pelo menos a versão 5146.1000 dos arquivos de Modelo Administrativo [(ADMX/ADML),](https://www.microsoft.com/download/details.aspx?id=49030)lançada em 22 de março de 2021.

Você pode encontrar essas configurações de política em Configuração do Usuário -> Políticas -> Modelos Administrativos -> Microsoft Office 2016 -> Privacy -> Trust Center.

> [!NOTE]
> Leva algumas horas para os aplicativos cliente atualizarem.
