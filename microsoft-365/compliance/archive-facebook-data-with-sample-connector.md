---
title: Configurar um conector para arquivar dados do Facebook
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Configure um conector para importar dados do Facebook para o Microsoft 365, de modo que você possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção.
ms.openlocfilehash: a1a45b3558e8c5fb77fb1d04a1a38402000bbd1b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035153"
---
# <a name="set-up-a-connector-to-archive-facebook-data"></a>Configurar um conector para arquivar dados do Facebook

Use um conector no centro de conformidade da Microsoft 365 para importar e arquivar dados de páginas de negócios do Facebook para a Microsoft 365. Depois de configurar e configurar o conector, ele se conecta à página de negócios do Facebook (de acordo com o agendamento), converte o conteúdo de itens do Facebook em um formato de mensagem de email e, em seguida, importa esses itens para uma caixa de correio no Microsoft 365.

Após a importação dos dados do Facebook, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, pesquisa de conteúdo, arquivamento in-loco, auditoria, conformidade de comunicação e políticas de retenção da Microsoft 365 para os dados do Facebook. Por exemplo, quando uma caixa de correio é colocada em retenção de litígio ou atribuída a uma política de retenção, os dados do Facebook são preservados. Você pode pesquisar dados de terceiros usando a pesquisa de conteúdo ou associar a caixa de correio onde os dados do Facebook são armazenados com um funcionário em uma caixa de descoberta eletrônica avançada. O uso de um conector para importar e arquivar dados do Facebook no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Pré-requisitos para configurar um conector para páginas de negócios do Facebook

Conclua os pré-requisitos a seguir antes de configurar e configurar um conector no centro de conformidade da Microsoft 365 para importar e arquivar dados das páginas de negócios de Facebook da sua organização. 

- Você precisa de uma conta do Facebook para as páginas de negócios da sua organização (você precisa fazer logon nessa conta ao configurar o conector). Atualmente, você só pode arquivar dados de páginas de negócios do Facebook; Você não pode arquivar dados de perfis individuais do Facebook.

- Sua organização deve ter uma assinatura válida do Azure. Se você não tiver uma assinatura do Azure existente, poderá se inscrever em uma destas opções:

    - [Inscreva-se para uma assinatura gratuita do Azure para um ano](https://azure.microsoft.com/free) 

    - [Inscreva-se para obter uma assinatura do Azure de pagamento conforme a ser acessado](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > A [assinatura gratuita do Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) incluída na assinatura do Microsoft 365 não é compatível com os conectores no centro de conformidade do & de segurança.

- Sua organização deve dar o consentimento para permitir que o serviço de importação do Office 365 acesse dados de caixa de correio em sua organização. Para concordar com essa solicitação, [acesse esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), entre com as credenciais de um administrador global e aceite a solicitação.

- O usuário que configura o conector personalizado no centro de conformidade da Microsoft 365 (na etapa 5) deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Etapa 1: criar um aplicativo no Azure Active Directory

A primeira etapa é registrar um novo aplicativo no Azure Active Directory (AAD). Este aplicativo corresponde ao recurso do aplicativo Web que você implementa na etapa 4 e etapa 5 para o conector do Facebook. 

Para obter instruções detalhadas, consulte [criar um aplicativo no Azure Active Directory](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory).

Durante a conclusão desta etapa (usando as instruções passo a passo anteriores), você salvará as informações a seguir em um arquivo de texto. Esses valores são usados nas etapas posteriores do processo de implantação.

- ID do aplicativo AAD

- Segredo do aplicativo AAD

- ID do locatário

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Etapa 2: implantar o serviço Web do conector do GitHub em sua conta do Azure

A próxima etapa é implantar o código-fonte para o aplicativo Facebook Business Pages Connector que usará a API do Facebook para se conectar à sua conta do Facebook e extrair dados para que você possa importá-lo para o Microsoft 365. O conector do Facebook que você implantar para sua organização carregará os itens de suas páginas de negócios do Facebook para o local de armazenamento do Azure criado nesta etapa. Depois de criar um conector de páginas de negócios do Facebook no centro de conformidade da Microsoft 365 (na etapa 5), o serviço de importação copiará os dados de páginas de negócios do Facebook do local de armazenamento do Azure para uma caixa de correio em sua organização do Microsoft 365. Conforme explicado anteriormente na seção [pré-requisitos](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) , você deve ter uma assinatura válida do Azure para criar uma conta de armazenamento do Azure.

Para obter instruções passo a passo, consulte [implantar o serviço Web do conector do GitHub para sua conta do Azure](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).

Nas instruções passo a passo para concluir esta etapa, você fornecerá as seguintes informações:

- APISecretKey: você cria esse segredo durante a conclusão desta etapa. É usado na etapa 5.

- Tenantid: a ID do locatário da sua organização do Microsoft 365 que você copiou depois de criar o aplicativo do Facebook Connector no Azure Active Directory na etapa 1.

Após concluir esta etapa, certifique-se de copiar a URL do serviço de aplicativo do Azure https://fbconnector.azurewebsites.net)(por exemplo,. Você precisa usar essa URL para concluir a etapa 3, etapa 4 e etapa 5.

## <a name="step-3-register-the-web-app-on-facebook"></a>Etapa 3: registrar o aplicativo Web no Facebook

A próxima etapa é criar e configurar um novo aplicativo no Facebook. O conector de páginas de negócios do Facebook que você cria na etapa 5 usa o Facebook Web App para interagir com a API do Facebook para obter dados das páginas de negócios do Facebook da sua organização.

Para obter instruções passo a passo, consulte [Register The Facebook app](deploy-facebook-connector.md#step-3-register-the-facebook-app).

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você salva as informações a seguir em um arquivo de texto. Esses valores são usados para configurar o aplicativo do Facebook Connector na etapa 4.

- ID do aplicativo do Facebook

- Segredo do aplicativo do Facebook

- Token de verificação de WebHooks do Facebook

## <a name="step-4-configure-the-facebook-connector-app"></a>Etapa 4: configurar o aplicativo do Facebook Connector

A próxima etapa é adicionar definições de configuração ao aplicativo do Facebook Connector carregado quando você criou o recurso do Azure Web App na etapa 1. Para fazer isso, vá até a home page do seu aplicativo conector e configure-a.

Para obter instruções detalhadas, consulte [Configure The Facebook Connector app](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app).

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você fornece as seguintes informações (que você copiou para um arquivo de texto depois de concluir as etapas anteriores):

- ID do aplicativo do Facebook (obtida na etapa 3)

- Segredo do aplicativo do Facebook (obtido na etapa 3)

- Token de verificação de WebHooks do Facebook (obtido na etapa 3)

- ID de aplicativo do Azure Active Directory (o ID de aplicativo do AAD obtido na etapa 1)

- Segredo de aplicativo do Azure Active Directory (o segredo do aplicativo AAD obtido na etapa 1)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>Etapa 5: configurar um conector de páginas de negócios do Facebook no centro de conformidade da Microsoft 365

A etapa final é configurar o conector no centro de conformidade da Microsoft 365 que importará dados de suas páginas de negócios do Facebook para uma caixa de correio especificada no Microsoft 365. Após concluir esta etapa, o serviço de importação do Office 365 começará a importar dados de suas páginas de negócios do Facebook para a Microsoft 365.

Para obter instruções passo a passo, consulte [etapa 5: configurar um conector do Facebook no centro de conformidade da Microsoft 365](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center). 

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você fornece as seguintes informações (que você copiou para um arquivo de texto depois de concluir as etapas).

- ID do aplicativo AAD (obtido na etapa 1)

- URL do serviço de aplicativo do Azure (obtido na etapa 1; por exemplo,https://fbconnector.azurewebsites.net)

- APISecretKey (que você criou na etapa 2)
