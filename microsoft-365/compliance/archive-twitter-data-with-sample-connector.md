---
title: Usar um exemplo de conector para arquivar dados do Twitter no Office 365 (versão prévia)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Os administradores podem configurar um conector nativo para importar dados do Twitter para o Office 365. Isso permite que você arquive dados de fontes de dados de terceiros no Office 365 para que possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar a governança dos dados de terceiros da sua organização.
ms.openlocfilehash: 6780e3fbb53e2326994e03815403c1e5ae0d0616
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072302"
---
# <a name="use-a-sample-connector-to-archive-twitter-data-in-office-365-preview"></a>Usar um exemplo de conector para arquivar dados do Twitter no Office 365 (versão prévia)

O recurso de conector de exemplo para arquivar dados do Twitter no Office 365 está em visualização.

Use um conector de exemplo no centro de conformidade & segurança no Office 365 para importar e arquivar dados do Twitter. Depois de configurar e configurar um conector de exemplo, ele se conecta à conta do Twitter da sua organização (em uma base agendada), converte o conteúdo de um item em um formato de mensagem de email e, em seguida, importa esses itens para uma caixa de correio no Office 365.

Após a importação dos dados do Twitter, você pode aplicar recursos de conformidade do Office 365, como retenção de litígio, pesquisa de conteúdo, arquivamento in-loco, auditoria, supervisão e políticas de retenção do Office 365 para os dados armazenados na caixa de correio. Por exemplo, você pode pesquisar dados do Twitter usando a pesquisa de conteúdo ou associar a caixa de correio onde os dados são armazenados com um funcionário em uma caixa de descoberta eletrônica avançada. O uso de conectores de amostra para importar e arquivar dados do Twitter no Office 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

> [!NOTE]
> Atualmente, somente os conectores de amostra para as [páginas de negócios](archive-facebook-data-with-sample-connector.md) do Twitter e do Facebook estão disponíveis para visualização. Mais exemplos de conectores serão disponibilizados em breve.


## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a>Pré-requisitos para configurar um conector para o Twitter

Você deve concluir os pré-requisitos a seguir antes de configurar e configurar um conector de exemplo no centro de conformidade & segurança para importar e arquivar dados da conta do Twitter da sua organização. 

- Você precisa de uma conta do Twitter para sua organização; Você precisa se conectar a essa conta ao configurar o conector.

- Sua organização deve ter uma assinatura válida do Azure. Se você não tiver uma assinatura do Azure existente, poderá se inscrever em uma destas opções:

    - [Inscreva-se para obter uma assinatura gratuita do Azure em 1 ano](https://azure.microsoft.com/free) 

    - [Inscreva-se para obter uma assinatura do Azure de pagamento conforme a ser acessado](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > A [assinatura gratuita do Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) incluída na assinatura do Office 365 não dá suporte aos conectores de amostra no centro de conformidade de segurança &.

- Sua organização deve dar o consentimento para permitir que o serviço de importação do Office 365 acesse dados de caixa de correio em sua organização. Para concordar com essa solicitação, [acesse esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), entre com as credenciais de um administrador global do Office 365 e aceite a solicitação.

- O usuário que configura o conector personalizado no Security & Compliance (na etapa 7) deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online. Por padrão, essa função não é atribuída a nenhum grupo de função no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um novo grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a>Etapa 1: baixar o pacote de aplicativos do conector pré-criado do github

A primeira etapa é baixar o código-fonte para o aplicativo do conector de amostra do Twitter que usará uma API do Twitter para se conectar à sua conta do Twitter e extrair os dados para que você possa importá-lo para o Office 365.

1. Vá para [este site do GitHub](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases). 
2. Na versão mais recente, clique no arquivo **SampleConnector. zip** .
3. Salve o arquivo ZIP em um local no computador local. Você carrega este arquivo zip no Azure na etapa 4.

## <a name="step-2-create-an-app-in-azure-active-directory"></a>Etapa 2: criar um aplicativo no Azure Active Directory

A próxima etapa é registrar um novo aplicativo no Azure Active Directory (AAD). Este aplicativo corresponde ao recurso do aplicativo Web que você implementa na etapa 4 para o conector do Twitter. 

Para obter instruções passo a passo, consulte [etapa 2: criar um aplicativo no Azure Active Directory](deploy-twitter-connector.md#step-2-create-an-app-in-azure-active-directory).

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você salvará as informações a seguir em um arquivo de texto. Os valores para eles serão usados nas etapas posteriores do processo de implantação.

- ID do aplicativo AAD
- Segredo do aplicativo AAD
- URI do aplicativo AAD
- ID do locatário

## <a name="step-3-create-an-azure-storage-account"></a>Etapa 3: criar uma conta de armazenamento do Azure

O conector do Twitter implantado para sua organização carrega os itens do Twitter para o local de armazenamento do Azure que você cria nesta etapa. Depois de criar um conector personalizado no centro de conformidade e segurança & (na etapa 7), o serviço de importação do Office 365 copiará os dados do Twitter do local de armazenamento do Azure para uma caixa de correio no Office 365. Conforme explicado anteriormente na seção [pré-requisitos](#prerequisites-for-setting-up-a-connector-for-twitter) , você deve ter uma assinatura válida do Azure para criar uma conta de armazenamento do Azure.

Para obter instruções passo a passo, consulte [etapa 3: criar uma conta de armazenamento do Azure](deploy-twitter-connector.md#step-3-create-an-azure-storage-account).

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você salva o URI da cadeia de conexão gerado. Use esta cadeia de caracteres ao criar um recurso do aplicativo Web no Azure na etapa 4.

## <a name="step-4-create-a-web-app-resource-in-azure"></a>Etapa 4: criar um recurso do aplicativo Web no Azure

A próxima etapa é criar um recurso do aplicativo Web no Azure para o conector do Twitter. 

Para obter instruções passo a passo, consulte [etapa 4: criar um novo recurso do aplicativo Web no Azure](deploy-twitter-connector.md#step-4-create-a-new-web-app-resource-in-azure).

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você fornecerá as seguintes informações (que você copiou para um arquivo de texto depois de concluir as etapas anteriores) ao criar o recurso do aplicativo Web.

- APISecretKey – você cria esse segredo durante a conclusão desta etapa; é usado na etapa 7.
- StorageAccountConnectionString – o URI da cadeia de caracteres de conexão que você copiou após a criação da conta de armazenamento do Azure na etapa 3.
- tenantid – a ID do locatário de sua organização do Office 365 que você copiou depois de criar o aplicativo do conector do Twitter no Azure Active Directory na etapa 2.

Além disso, você carrega o arquivo SampleConnector. zip (que baixou na etapa 1) nesta etapa para implantar o código-fonte do aplicativo do conector do Twitter.

Após concluir esta etapa, certifique-se de copiar a URL do serviço de aplicativo do Azure https://twitterconnector.azurewebsites.net)(por exemplo,. É necessário usá-lo para concluir a etapa 5, etapa 6 e etapa 7).

## <a name="step-5-create-developer-app-on-twitter"></a>Etapa 5: criar um aplicativo de desenvolvedor no Twitter

A próxima etapa é criar e configurar um aplicativo de desenvolvedor no Twitter. O conector personalizado criado na etapa 7 usa o aplicativo Twitter para interagir com a API do Twitter para obter dados da conta do Twitter da sua organização.

Para obter instruções passo a passo, consulte [etapa 5: criar o aplicativo Twitter](deploy-twitter-connector.md#step-5-create-the-twitter-app).

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você salva as informações a seguir em um arquivo de texto. Os valores para eles serão usados para configurar o aplicativo do conector do Twitter na etapa 6.

- Chave de API do Twitter
- Chave secreta da API do Twitter
- Token de acesso do Twitter
- Segredo do token de acesso do Twitter

## <a name="step-6-configure-the-twitter-connector-app"></a>Etapa 6: configurar o aplicativo do conector do Twitter

A próxima etapa é adicionar configurações de configurações ao aplicativo do conector do Twitter que você carregou quando criou o recurso do Azure Web App na etapa 4. Para fazer isso, vá até a home page do seu aplicativo conector e configure-a.

Para obter instruções detalhadas, consulte [etapa 6: Configure the Connector Web App](deploy-twitter-connector.md#step-6-configure-the-connector-web-app).

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você fornecerá as seguintes informações (que você copiou para um arquivo de texto depois de concluir as etapas anteriores):

- Chave de API do Twitter (obtida na etapa 5)
- Chave secreta da API do Twitter (obtida na etapa 5)
- Token de acesso do Twitter (obtido na etapa 5)
- Segredo do token de acesso do Twitter (obtido na etapa 5)
- ID de aplicativo do Azure Active Directory (a ID de aplicativo do AAD obtida na etapa 2)
- Segredo de aplicativo do Azure Active Directory (o segredo do aplicativo AAD obtido na etapa 2)
- URI do aplicativo do Azure Active Directory (o URI do aplicativo AAD obtido na etapa 2; por exemplo,https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a>Etapa 7: configurar um conector personalizado no centro de conformidade & segurança

A etapa final é configurar o conector personalizado no centro de conformidade de & de segurança que importa dados da conta do Twitter da sua organização para uma caixa de correio especificada no Office 365. Depois de concluir com êxito esta etapa, o serviço de importação do Office 365 iniciará o processo de importação de dados do Twitter para o Office 365. 

Para obter instruções passo a passo, consulte [etapa 7: configurar um conector personalizado no centro de segurança e conformidade](deploy-twitter-connector.md#step-7-set-up-a-custom-connector-in-the-security-and-compliance-center). 

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você fornecerá as seguintes informações (que você copiou para um arquivo de texto depois de concluir as etapas).

- URL do serviço de aplicativo do Azure (obtido na etapa 4; por exemplo,https://twitterconnector.azurewebsites.net)
- APISecretKey (que você criou na etapa 4)
