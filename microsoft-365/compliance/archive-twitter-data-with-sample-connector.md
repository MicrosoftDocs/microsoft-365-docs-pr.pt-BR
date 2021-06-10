---
title: Configurar um conector para arquivar dados do Twitter
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
description: Saiba como os administradores podem configurar e usar um conector nativo para importar dados do Twitter para Microsoft 365.
ms.openlocfilehash: 277af8ea7367936c4c9528a8ca50ccd678745bf6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922253"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a>Configurar um conector para arquivar dados do Twitter (visualização)

Use um conector no centro de conformidade Microsoft 365 para importar e arquivar dados do Twitter para Microsoft 365. Depois de configurar e configurar o conector, ele se conecta à conta do Twitter da sua organização (agendada), converte o conteúdo de um item em um formato de mensagem de email e importa esses itens para uma caixa de correio em Microsoft 365.

Depois que os dados do Twitter são importados, você pode aplicar Microsoft 365 recursos de conformidade, como Retenção de Litígio, Pesquisa de Conteúdo, Arquivamento In-Place In-Place, Auditoria e Microsoft 365 de retenção aos dados do Twitter. Por exemplo, quando uma caixa de correio é colocada em Retenção de Litígio ou atribuída a uma política de retenção, os dados do Twitter são preservados. Você pode pesquisar dados de terceiros usando a Pesquisa de Conteúdo ou associar a caixa de correio onde os dados do Twitter são armazenados com um custodiante em um Advanced eDiscovery caso. Usar um conector para importar e arquivar dados do Twitter no Microsoft 365 pode ajudar sua organização a permanecer em conformidade com políticas governamentais e regulatórias.

Depois que os dados do Twitter são importados, você pode aplicar Microsoft 365 recursos de conformidade, como Retenção de Litígio, Pesquisa de Conteúdo, Arquivamento In-Place In-Place, Auditoria, Conformidade de comunicação e políticas de retenção Microsoft 365 aos dados armazenados na caixa de correio. Por exemplo, você pode pesquisar dados do Twitter usando a Pesquisa de Conteúdo ou associar a caixa de correio onde os dados são armazenados com um custodiante em um Advanced eDiscovery caso. Usar um conector para importar e arquivar dados do Twitter no Microsoft 365 pode ajudar sua organização a permanecer em conformidade com políticas governamentais e regulatórias.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar um conector

Conclua os seguintes pré-requisitos antes de configurar e configurar um conector no centro de conformidade Microsoft 365 para importar e arquivar dados da conta do Twitter da sua organização.

- Você precisa de uma conta do Twitter para sua organização; você precisa entrar nessa conta ao configurar o conector.

- Sua organização deve ter uma assinatura válida do Azure. Se você não tiver uma assinatura do Azure existente, inscreva-se em uma destas opções:

    - [Inscrever-se para uma assinatura gratuita de um ano do Azure](https://azure.microsoft.com/free) 

    - [Inscrever-se para uma assinatura do Azure Pay-As-Go](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > A [assinatura Azure Active Directory de](use-your-free-azure-ad-subscription-in-office-365.md) assinatura gratuita incluída na assinatura Microsoft 365 não dá suporte aos conectores no Centro de Conformidade & Segurança.

- O conector do Twitter pode importar um total de 200.000 itens em um único dia. Se houver mais de 200.000 itens do Twitter em um dia, nenhum desses itens será importado para Microsoft 365.

- O usuário que configura o conector do Twitter no centro de conformidade do Microsoft 365 (na Etapa 5) deve receber a função De importação de importação de caixa de correio no Exchange Online. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de funções em Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Etapa 1: Criar um aplicativo no Azure Active Directory

A primeira etapa é registrar um novo aplicativo no Azure Active Directory (AAD). Este aplicativo corresponde ao recurso de aplicativo Web que você implementa na Etapa 2 para o conector do Twitter.

Para obter instruções passo a passo, consulte [Create an app in Azure Active Directory](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory).

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você salvará as informações a seguir em um arquivo de texto. Esses valores serão usados em etapas posteriores no processo de implantação.

- ID do aplicativo AAD

- Segredo do aplicativo AAD

- ID do locatário

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>Etapa 2: Implantar o serviço Web do conector GitHub repositório para sua conta do Azure

A próxima etapa é implantar o código-fonte do aplicativo conector do Twitter que usará a API do Twitter para se conectar à sua conta do Twitter e extrair dados para que você possa importá-lo para Microsoft 365. O conector do Twitter que você implantar para sua organização carregará os itens da conta do Twitter da sua organização para o local de Armazenamento do Azure criado nesta etapa. Depois de criar um conector do Twitter no centro de conformidade do Microsoft 365 (na Etapa 5), o serviço Microsoft 365 Import copiará os dados do Twitter do local de Armazenamento do Azure para uma caixa de correio no Microsoft 365. Conforme explicado anteriormente na seção [Antes](#before-you-set-up-a-connector) de configurar um conector, você deve ter uma assinatura válida do Azure para criar uma conta do Azure Armazenamento.

Para implantar o código-fonte para o aplicativo conector do Twitter:

1. Vá para [este GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet).

2. Clique **em Implantar no Azure**.

Para obter instruções passo a passo, consulte [Deploy the connector web service from GitHub to your Azure account](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).

Enquanto você segue as instruções passo a passo para concluir esta etapa, você fornece as seguintes informações

- APISecretKey: crie esse segredo durante a conclusão desta etapa. É usado na Etapa 5.

- tenantId: a ID de locatário da sua organização Microsoft 365 que você copiou após criar o aplicativo Twitter Azure Active Directory na Etapa 1.

Após concluir esta etapa, copie a URL do serviço do aplicativo (por exemplo, `https://twitterconnector.azurewebsites.net` ). Você precisa usar essa URL para concluir a Etapa 3, Etapa 4 e Etapa 5).

## <a name="step-3-create-developer-app-on-twitter"></a>Etapa 3: Criar aplicativo de desenvolvedor no Twitter

A próxima etapa é criar e configurar um aplicativo de desenvolvedor no Twitter. O conector personalizado criado na Etapa 7 usa o aplicativo Twitter para interagir com a API do Twitter para obter dados da conta do Twitter da sua organização.

Para obter instruções passo a passo, consulte [Create the Twitter app](deploy-twitter-connector.md#step-3-create-the-twitter-app).

Durante a conclusão desta etapa (seguindo as instruções passo a passo), salve as informações a seguir em um arquivo de texto. Esses valores serão usados para configurar o aplicativo conector do Twitter na Etapa 4.

- Chave da API do Twitter

- Chave secreta da API do Twitter

- Token de Acesso do Twitter

- Segredo do Token de Acesso ao Twitter

## <a name="step-4-configure-the-twitter-connector-app"></a>Etapa 4: Configurar o aplicativo conector do Twitter

A próxima etapa é adicionar configurações ao aplicativo conector do Twitter implantado na Etapa 2. Você faz isso indo para a home page do aplicativo do conector e configurando-o.

Para obter instruções passo a passo, consulte [Configure the connector web app](deploy-twitter-connector.md#step-4-configure-the-connector-web-app).

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você fornecerá as seguintes informações (que você copiou para um arquivo de texto após concluir as etapas anteriores):

- Chave da API do Twitter (obtida na Etapa 3)

- Chave Secreta da API do Twitter (obtida na Etapa 3)

- Token de Acesso do Twitter (obtido na Etapa 3)

- Segredo do Token de Acesso ao Twitter (obtido na Etapa 3)

- Azure Active Directory ID do aplicativo (a ID do aplicativo AAD obtida na Etapa 1)

- Azure Active Directory do aplicativo (o segredo do aplicativo AAD obtido na Etapa 1)

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>Etapa 5: Configurar um conector do Twitter no centro Microsoft 365 conformidade

A etapa final é configurar o conector do Twitter no centro de conformidade Microsoft 365 que importará dados da conta do Twitter da sua organização para uma caixa de correio especificada no Microsoft 365. Depois de concluir essa etapa, o serviço Microsoft 365 Import começará a importar dados da conta do Twitter da sua organização para Microsoft 365.

Para obter instruções passo a passo, consulte [Set up a Twitter connector in the Microsoft 365 compliance center](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center). 

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você fornecerá as seguintes informações (que você copiou para um arquivo de texto após concluir as etapas).

- URL do serviço de aplicativo do Azure (obtida na Etapa 2; por exemplo, `https://twitterconnector.azurewebsites.net` )

- APISecretKey (que você criou na Etapa 2)