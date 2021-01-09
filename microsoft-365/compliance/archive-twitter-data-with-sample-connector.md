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
description: Saiba como os administradores podem configurar e usar um conector nativo para importar dados do Twitter para o Microsoft 365.
ms.openlocfilehash: 5b35259985664ac47b9d1f6265c8ca4282a4cd31
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790059"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a>Configurar um conector para arquivar dados do Twitter (visualização)

Use um conector no centro de conformidade do Microsoft 365 para importar e arquivar dados do Twitter para o Microsoft 365. Depois de configurar o conector, ele se conecta à conta do Twitter da sua organização (de forma agendada), converte o conteúdo de um item em um formato de mensagem de email e importa esses itens para uma caixa de correio no Microsoft 365.

Depois que os dados do Twitter são importados, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Pesquisa de Conteúdo, Arquivamento do In-Place, Auditoria e políticas de retenção do Microsoft 365 aos dados do Twitter. Por exemplo, quando uma caixa de correio é colocada em Retenção de Litígio ou atribuída a uma política de retenção, os dados do Twitter são preservados. Você pode pesquisar dados de terceiros usando a Pesquisa de Conteúdo ou associar a caixa de correio onde os dados do Twitter estão armazenados com um custodiante em um caso de Descoberta Eletrônico Avançada. Usar um conector para importar e arquivar dados do Twitter no Microsoft 365 pode ajudar sua organização a manter a conformidade com políticas governamentais e regulatórias.

Depois que os dados do Twitter são importados, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Pesquisa de Conteúdo, Arquivamento do In-Place, Auditoria, Conformidade de Comunicação e políticas de retenção do Microsoft 365 aos dados armazenados na caixa de correio. Por exemplo, você pode pesquisar dados do Twitter usando a Pesquisa de Conteúdo ou associar a caixa de correio onde os dados estão armazenados com um custodiante em um caso de Descoberta Eletrônico Avançada. Usar um conector para importar e arquivar dados do Twitter no Microsoft 365 pode ajudar sua organização a manter a conformidade com políticas governamentais e regulatórias.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar um conector

Conclua os seguintes pré-requisitos antes de configurar e configurar um conector no centro de conformidade do Microsoft 365 para importar e arquivar dados da conta do Twitter da sua organização.

- Você precisa de uma conta do Twitter para sua organização; você precisa entrar nessa conta ao configurar o conector.

- Sua organização deve ter uma assinatura válida do Azure. Se você não tiver uma assinatura existente do Azure, inscreva-se para uma destas opções:

    - [Inscreva-se para uma assinatura gratuita de um ano do Azure](https://azure.microsoft.com/free) 

    - [Inscrever-se para uma assinatura do Azure "Pagar como Você-Pode"](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > A [assinatura gratuita do Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) incluída na assinatura do Microsoft 365 não dá suporte aos conectores no Centro de Conformidade e Segurança & Segurança.

- O conector do Twitter pode importar um total de 200.000 itens em um único dia. Se houver mais de 200.000 itens do Twitter em um dia, nenhum desses itens será importado para o Microsoft 365.

- O usuário que configura o conector do Twitter no centro de conformidade do Microsoft 365 (na Etapa 5) deve receber a função Importar Exportar Caixa de Correio no Exchange Online. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Importar Exportar Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Importar Exportar Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) as [seções](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Criar grupos de função ou Modificar grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Etapa 1: Criar um aplicativo no Azure Active Directory

A primeira etapa é registrar um novo aplicativo no Azure Active Directory (AAD). Esse aplicativo corresponde ao recurso de aplicativo Web que você implementa na Etapa 2 para o conector do Twitter.

Para obter instruções passo a passo, confira [Criar um aplicativo no Azure Active Directory.](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você salvará as informações a seguir em um arquivo de texto. Esses valores serão usados em etapas posteriores do processo de implantação.

- ID do aplicativo AAD

- Segredo do aplicativo AAD

- ID do locatário

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>Etapa 2: Implantar o serviço Web do conector do repositório do GitHub em sua conta do Azure

A próxima etapa é implantar o código-fonte para o aplicativo de conector do Twitter que usará a API do Twitter para se conectar à sua conta do Twitter e extrair dados para que você possa importá-los para o Microsoft 365. O conector do Twitter implantado para sua organização carregará os itens da conta do Twitter da sua organização para o local de armazenamento do Azure criado nesta etapa. Depois de criar um conector do Twitter no centro de conformidade do Microsoft 365 (na Etapa 5), o serviço de Importação do Microsoft 365 copiará os dados do Twitter do local de armazenamento do Azure para uma caixa de correio no Microsoft 365. Conforme explicado anteriormente na seção [Antes](#before-you-set-up-a-connector) de configurar um conector, você deve ter uma assinatura válida do Azure para criar uma conta de Armazenamento do Azure.

Para implantar o código-fonte para o aplicativo de conector do Twitter:

1. Vá para [este site do GitHub.](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)

2. Clique **em Implantar no Azure.**

Para obter instruções passo a passo, confira Implantar o serviço Web do conector do [GitHub em sua conta do Azure.](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)

Enquanto você segue as instruções passo a passo para concluir esta etapa, forneça as seguintes informações

- APISecretKey: você cria esse segredo durante a conclusão desta etapa. Ele é usado na Etapa 5.

- tenantId: a ID de locatário da sua organização do Microsoft 365 que você copiou depois de criar o aplicativo Twitter no Azure Active Directory na Etapa 1.

Depois de concluir esta etapa, copie a URL do serviço de aplicativo (por exemplo, `https://twitterconnector.azurewebsites.net` ). Você precisa usar essa URL para concluir a Etapa 3, Etapa 4 e Etapa 5).

## <a name="step-3-create-developer-app-on-twitter"></a>Etapa 3: Criar um aplicativo de desenvolvedor no Twitter

A próxima etapa é criar e configurar um aplicativo de desenvolvedor no Twitter. O conector personalizado criado na Etapa 7 usa o aplicativo Twitter para interagir com a API do Twitter para obter dados da conta do Twitter da sua organização.

Para obter instruções passo a passo, consulte [Criar o aplicativo Twitter.](deploy-twitter-connector.md#step-3-create-the-twitter-app)

Durante a conclusão desta etapa (seguindo as instruções passo a passo), salve as informações a seguir em um arquivo de texto. Esses valores serão usados para configurar o aplicativo de conector do Twitter na Etapa 4.

- Chave da API do Twitter

- Chave secreta da API do Twitter

- Token de acesso do Twitter

- Segredo do Token de Acesso do Twitter

## <a name="step-4-configure-the-twitter-connector-app"></a>Etapa 4: Configurar o aplicativo de conector do Twitter

A próxima etapa é adicionar configurações ao aplicativo de conector do Twitter implantado na Etapa 2. Você pode fazer isso indo para a home page do seu aplicativo de conector e configurá-lo.

Para obter instruções passo a passo, consulte [Configurar o aplicativo Web do conector.](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você fornecerá as seguintes informações (que você copiou para um arquivo de texto após concluir as etapas anteriores):

- Chave da API do Twitter (obtida na Etapa 3)

- Chave secreta da API do Twitter (obtida na Etapa 3)

- Token de acesso do Twitter (obtido na Etapa 3)

- Segredo do Token de Acesso do Twitter (obtido na Etapa 3)

- ID do aplicativo Azure Active Directory (a ID de aplicativo do AAD obtida na Etapa 1)

- Segredo do aplicativo Azure Active Directory (o segredo do aplicativo AAD obtido na Etapa 1)

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>Etapa 5: Configurar um conector do Twitter no centro de conformidade do Microsoft 365

A etapa final é configurar o conector do Twitter no centro de conformidade do Microsoft 365 que importa os dados da conta do Twitter da sua organização para uma caixa de correio especificada no Microsoft 365. Depois de concluir esta etapa, o serviço de Importação do Microsoft 365 começará a importar dados da conta do Twitter da sua organização para o Microsoft 365.

Para obter instruções passo a passo, confira Configurar um conector do Twitter no centro de conformidade [do Microsoft 365.](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center) 

Durante a conclusão desta etapa (seguindo as instruções passo a passo), você fornecerá as seguintes informações (que você copiou para um arquivo de texto após concluir as etapas).

- URL do serviço de aplicativo do Azure (obtida na Etapa 2; por exemplo, `https://twitterconnector.azurewebsites.net` )

- APISecretKey (que você criou na Etapa 2)
