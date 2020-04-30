---
title: Configurar um conector para arquivar dados do Twitter
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
description: Os administradores podem configurar um conector nativo para importar dados do Twitter para o Microsoft 365. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar a governança dos dados de terceiros da sua organização.
ms.openlocfilehash: 5d4c1817fe9b3c47dc3cbabd0147f23057c7bc65
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943190"
---
# <a name="set-up-a-connector-to-archive-twitter-data"></a>Configurar um conector para arquivar dados do Twitter

Use um conector no centro de conformidade da Microsoft 365 para importar e arquivar dados do Twitter para o Microsoft 365. Depois de configurar e configurar o conector, ele se conecta à conta do Twitter da sua organização (em uma base agendada), converte o conteúdo de um item em um formato de mensagem de email e, em seguida, importa esses itens para uma caixa de correio no Microsoft 365.

Depois que os dados do Twitter são importados, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, pesquisa de conteúdo, arquivamento in-loco, auditoria e políticas de retenção da Microsoft 365 para os dados do Twitter. Por exemplo, quando uma caixa de correio é colocada em retenção de litígio ou atribuída a uma política de retenção, os dados do Twitter são preservados. Você pode pesquisar dados de terceiros usando a pesquisa de conteúdo ou associar a caixa de correio onde os dados do Twitter estão armazenados com um funcionário em uma caixa de descoberta eletrônica avançada. O uso de um conector para importar e arquivar dados do Twitter no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

Após a importação dos dados do Twitter, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, pesquisa de conteúdo, arquivamento in-loco, auditoria, conformidade de comunicação e políticas de retenção da Microsoft 365 para os dados armazenados na caixa de correio. Por exemplo, você pode pesquisar dados do Twitter usando a pesquisa de conteúdo ou associar a caixa de correio onde os dados são armazenados com um funcionário em uma caixa de descoberta eletrônica avançada. O uso de um conector para importar e arquivar dados do Twitter no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a>Pré-requisitos para configurar um conector para o Twitter

Conclua os pré-requisitos a seguir antes de configurar e configurar um conector no centro de conformidade da Microsoft 365 para importar e arquivar dados da conta do Twitter da sua organização.

- Você precisa de uma conta do Twitter para sua organização; Você precisa se conectar a essa conta ao configurar o conector.

- Sua organização deve ter uma assinatura válida do Azure. Se você não tiver uma assinatura do Azure existente, poderá se inscrever em uma destas opções:

    - [Inscreva-se para uma assinatura gratuita do Azure para um ano](https://azure.microsoft.com/free) 

    - [Inscreva-se para obter uma assinatura do Azure de pagamento conforme a ser acessado](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > A [assinatura gratuita do Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) incluída na assinatura do Microsoft 365 não é compatível com os conectores no centro de conformidade do & de segurança.

- Sua organização deve dar o consentimento para permitir que o serviço de importação do Office 365 acesse dados de caixa de correio em sua organização. Para concordar com essa solicitação, [acesse esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), entre com as credenciais de um administrador global e aceite a solicitação.

- O usuário que configura o conector do Twitter no centro de conformidade da Microsoft 365 (na etapa 5) deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Etapa 1: criar um aplicativo no Azure Active Directory

A primeira etapa é registrar um novo aplicativo no Azure Active Directory (AAD). Este aplicativo corresponde ao recurso do aplicativo Web que você implementa na etapa 2 para o conector do Twitter.

Para obter instruções detalhadas, consulte [criar um aplicativo no Azure Active Directory](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory).

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você salvará as informações a seguir em um arquivo de texto. Esses valores serão usados nas etapas posteriores do processo de implantação.

- ID do aplicativo AAD

- Segredo do aplicativo AAD

- ID do locatário

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>Etapa 2: implantar o serviço Web do conector do repositório do GitHub em sua conta do Azure

A próxima etapa é implantar o código-fonte do aplicativo do conector do Twitter que usará a API do Twitter para se conectar à sua conta do Twitter e extrair os dados para que você possa importá-lo para o Microsoft 365. O conector do Twitter implantado para sua organização carregará os itens da conta do Twitter da sua organização para o local de armazenamento do Azure criado nesta etapa. Após criar um conector do Twitter no centro de conformidade da Microsoft 365 (na etapa 5), o serviço de importação do Office 365 copiará os dados do Twitter do local de armazenamento do Azure para uma caixa de correio no Microsoft 365. Conforme explicado anteriormente na seção [pré-requisitos](#prerequisites-for-setting-up-a-connector-for-twitter) , você deve ter uma assinatura válida do Azure para criar uma conta de armazenamento do Azure.

Para implantar o código-fonte do aplicativo do conector do Twitter:

1. Vá para [este site do GitHub](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet).

2. Clique em **implantar no Azure**.

Para obter instruções passo a passo, consulte [implantar o serviço Web do conector do GitHub para sua conta do Azure](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).

Ao seguir as instruções passo a passo para concluir esta etapa, você fornece as seguintes informações

- APISecretKey: você cria esse segredo durante a conclusão desta etapa. É usado na etapa 5.

- tenantid: a ID do locatário da sua organização do Microsoft 365 que você copiou depois de criar o aplicativo Twitter no Azure Active Directory na etapa 1.

Após concluir esta etapa, certifique-se de copiar a URL do serviço de aplicativo ( `https://twitterconnector.azurewebsites.net`por exemplo,). Você precisa usar essa URL para concluir a etapa 3, etapa 4 e etapa 5.

## <a name="step-3-create-developer-app-on-twitter"></a>Etapa 3: criar um aplicativo de desenvolvedor no Twitter

A próxima etapa é criar e configurar um aplicativo de desenvolvedor no Twitter. O conector personalizado criado na etapa 7 usa o aplicativo Twitter para interagir com a API do Twitter para obter dados da conta do Twitter da sua organização.

Para obter instruções passo a passo, consulte [Create the Twitter app](deploy-twitter-connector.md#step-3-create-the-twitter-app).

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você salva as informações a seguir em um arquivo de texto. Esses valores serão usados para configurar o aplicativo do conector do Twitter na etapa 4.

- Chave de API do Twitter

- Chave secreta da API do Twitter

- Token de acesso do Twitter

- Segredo do token de acesso do Twitter

## <a name="step-4-configure-the-twitter-connector-app"></a>Etapa 4: configurar o aplicativo do conector do Twitter

A próxima etapa é adicionar configurações de configurações ao aplicativo do conector do Twitter que você implantou na etapa 2. Para fazer isso, vá até a home page do seu aplicativo conector e configure-a.

Para obter instruções detalhadas, consulte [Configure the Connector Web App](deploy-twitter-connector.md#step-4-configure-the-connector-web-app).

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você fornecerá as seguintes informações (que você copiou para um arquivo de texto depois de concluir as etapas anteriores):

- Chave de API do Twitter (obtida na etapa 3)

- Chave secreta da API do Twitter (obtida na etapa 3)

- Token de acesso do Twitter (obtido na etapa 3)

- Segredo do token de acesso do Twitter (obtido na etapa 3)

- ID de aplicativo do Azure Active Directory (o ID de aplicativo do AAD obtido na etapa 1)

- Segredo de aplicativo do Azure Active Directory (o segredo do aplicativo AAD obtido na etapa 1)

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>Etapa 5: configurar um conector do Twitter no centro de conformidade da Microsoft 365

A etapa final é configurar o conector do Twitter no centro de conformidade da Microsoft 365 que irá importar dados da conta do Twitter da sua organização para uma caixa de correio especificada no Microsoft 365. Após concluir esta etapa, o serviço de importação do Office 365 começará a importar dados da conta do Twitter da sua organização para a Microsoft 365.

Para obter instruções detalhadas, consulte [configurar um conector do Twitter no centro de conformidade do Microsoft 365](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center). 

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você fornecerá as seguintes informações (que você copiou para um arquivo de texto depois de concluir as etapas).

- URL do serviço de aplicativo do Azure (obtido na etapa 2; `https://twitterconnector.azurewebsites.net`por exemplo,)

- APISecretKey (que você criou na etapa 2)
