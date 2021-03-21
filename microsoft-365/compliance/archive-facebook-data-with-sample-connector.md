---
title: Configurar um conector para arquivar dados do Facebook
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Saiba como configurar & um conector no centro de conformidade do Microsoft 365 para importar & dados de arquivo morto de páginas do Facebook Business para o Microsoft 365.
ms.openlocfilehash: 616466a3af83c1558184526aa463f68c10ef9e70
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921731"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a>Configurar um conector para arquivar dados do Facebook (visualização)

Use um conector no centro de conformidade do Microsoft 365 para importar e arquivar dados de páginas do Facebook Business para o Microsoft 365. Depois de configurar e configurar o conector, ele se conecta à página do Facebook Business (agendada), converte o conteúdo de itens do Facebook em um formato de mensagem de email e importa esses itens para uma caixa de correio no Microsoft 365.

Depois que os dados do Facebook são importados, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Pesquisa de Conteúdo, Arquivamento In-Place In-Place, Auditoria, Conformidade de Comunicação e políticas de retenção do Microsoft 365 aos dados do Facebook. Por exemplo, quando uma caixa de correio é colocada em Retenção de Litígio ou atribuída a uma política de retenção, os dados do Facebook são preservados. Você pode pesquisar dados de terceiros usando a Pesquisa de Conteúdo ou associar a caixa de correio onde os dados do Facebook são armazenados com um custodiante em um caso de Descoberta Avançada. O uso de um conector para importar e arquivar dados do Facebook no Microsoft 365 pode ajudar sua organização a se manter em conformidade com políticas governamentais e regulatórias.

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Pré-requisitos para configurar um conector para páginas do Facebook Business

Conclua os seguintes pré-requisitos antes de configurar e configurar um conector no centro de conformidade do Microsoft 365 para importar e arquivar dados das páginas do Facebook Business da sua organização. 

- Você precisa de uma conta do Facebook para as páginas comerciais da sua organização (você precisa entrar nessa conta ao configurar o conector). Atualmente, você só pode arquivar dados de páginas do Facebook Business; você não pode arquivar dados de perfis individuais do Facebook.

- Sua organização deve ter uma assinatura válida do Azure. Se você não tiver uma assinatura do Azure existente, inscreva-se em uma destas opções:

    - [Inscrever-se para uma assinatura gratuita de um ano do Azure](https://azure.microsoft.com/free)

    - [Inscrever-se para uma assinatura do Azure Pay-As-Go](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > A assinatura gratuita do [Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) incluída na sua assinatura do Microsoft 365 não dá suporte aos conectores no Centro de Conformidade & Segurança.

- O conector para páginas do Facebook Business pode importar um total de 200.000 itens em um único dia. Se houver mais de 200.000 itens do Facebook Business em um dia, nenhum desses itens será importado para o Microsoft 365.

- O usuário que configura o conector personalizado no centro de conformidade do Microsoft 365 (na Etapa 5) deve receber a função de Exportação de Importação de Caixa de Correio no Exchange Online. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de  [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Etapa 1: Criar um aplicativo no Azure Active Directory

A primeira etapa é registrar um novo aplicativo no Azure Active Directory (AAD). Este aplicativo corresponde ao recurso de aplicativo Web que você implementa na Etapa 4 e Etapa 5 para o conector do Facebook. 

Para obter instruções passo a passo, consulte [Create an app in Azure Active Directory](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory).

Durante a conclusão desta etapa (usando as instruções passo a passo anteriores), você salvará as informações a seguir em um arquivo de texto. Esses valores são usados em etapas posteriores no processo de implantação.

- ID do aplicativo AAD

- Segredo do aplicativo AAD

- ID do locatário

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Etapa 2: Implantar o serviço Web do conector do GitHub em sua conta do Azure

A próxima etapa é implantar o código-fonte para o aplicativo conector de páginas do Facebook Business que usará a API do Facebook para se conectar à sua conta do Facebook e extrair dados para que você possa importá-lo para o Microsoft 365. O conector do Facebook implantado para sua organização carregará os itens de suas páginas do Facebook Business para o local de Armazenamento do Azure criado nesta etapa. Depois de criar um conector de páginas comerciais do Facebook no centro de conformidade do Microsoft 365 (na Etapa 5), o serviço Import copiará os dados de páginas comerciais do Facebook do local de Armazenamento do Azure para uma caixa de correio em sua organização do Microsoft 365. Conforme explicado anteriormente na seção [Pré-requisitos,](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) você deve ter uma assinatura válida do Azure para criar uma conta de Armazenamento do Azure.

Para obter instruções passo a passo, consulte [Deploy the connector web service from GitHub to your Azure account](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).

Nas instruções passo a passo para concluir esta etapa, você fornecerá as seguintes informações:

- APISecretKey: crie esse segredo durante a conclusão desta etapa. É usado na Etapa 5.

- TenantId: a ID de locatário da sua organização do Microsoft 365 que você copiou depois de criar o aplicativo de conector do Facebook no Azure Active Directory na Etapa 1.

Após concluir esta etapa, copie a URL do serviço de aplicativo do Azure (por exemplo, https://fbconnector.azurewebsites.net) . Você precisa usar essa URL para concluir a Etapa 3, Etapa 4 e Etapa 5).

## <a name="step-3-register-the-web-app-on-facebook"></a>Etapa 3: Registrar o aplicativo Web no Facebook

A próxima etapa é criar e configurar um novo aplicativo no Facebook. O conector de páginas comerciais do Facebook que você cria na Etapa 5 usa o aplicativo Web do Facebook para interagir com a API do Facebook para obter dados das páginas do Facebook Business da sua organização.

Para obter instruções passo a passo, consulte [Register the Facebook app](deploy-facebook-connector.md#step-3-register-the-facebook-app).

Durante a conclusão desta etapa (seguindo as instruções passo a passo), salve as informações a seguir em um arquivo de texto. Esses valores são usados para configurar o aplicativo conector do Facebook na Etapa 4.

- ID do aplicativo do Facebook

- Segredo do aplicativo do Facebook

- Webhooks do Facebook verificam token

## <a name="step-4-configure-the-facebook-connector-app"></a>Etapa 4: Configurar o aplicativo conector do Facebook

A próxima etapa é adicionar configurações ao aplicativo conector do Facebook que você carregou ao criar o recurso do aplicativo Web do Azure na Etapa 1. Você faz isso indo para a home page do aplicativo do conector e configurando-o.

Para obter instruções passo a passo, consulte [Configure the Facebook connector app](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app).

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você fornece as seguintes informações (que você copiou para um arquivo de texto após concluir as etapas anteriores):

- ID do aplicativo do Facebook (obtida na Etapa 3)

- Segredo do aplicativo do Facebook (obtido na Etapa 3)

- Webhooks do Facebook verificam token (obtido na Etapa 3)

- ID do aplicativo do Azure Active Directory (a ID do aplicativo AAD obtida na Etapa 1)

- Segredo do aplicativo do Azure Active Directory (o segredo do aplicativo AAD obtido na Etapa 1)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>Etapa 5: Configurar um conector de páginas do Facebook Business no centro de conformidade do Microsoft 365

A etapa final é configurar o conector no centro de conformidade do Microsoft 365 que importará dados de suas páginas do Facebook Business para uma caixa de correio especificada no Microsoft 365. Após concluir esta etapa, o serviço de Importação do Microsoft 365 começará a importar dados de suas páginas do Facebook Business para o Microsoft 365.

Para obter instruções passo a passo, consulte Etapa 5: Configurar um conector do Facebook no centro de [conformidade do Microsoft 365.](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center) 

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você fornece as seguintes informações (que você copiou para um arquivo de texto após concluir as etapas).

- ID do aplicativo AAD (obtida na Etapa 1)

- URL do serviço de aplicativo do Azure (obtida na Etapa 1; por exemplo, https://fbconnector.azurewebsites.net)

- APISecretKey (que você criou na Etapa 2)