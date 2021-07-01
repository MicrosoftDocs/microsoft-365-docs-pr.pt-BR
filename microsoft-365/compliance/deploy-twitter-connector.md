---
title: Implantar um conector para arquivar dados do Twitter
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
ROBOTS: NOINDEX, NOFOLLOW
description: Os administradores podem configurar um conector nativo para importar e arquivar dados do Twitter para Microsoft 365. Depois que esses dados são importados para Microsoft 365, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar a governança dos dados do Twitter da sua organização.
ms.openlocfilehash: 0a0ebb18cb39b7dd7416f2d03dcb5b4d21332c9b
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227050"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a>Implantar um conector para arquivar dados do Twitter

Este artigo contém o processo passo a passo para implantar um conector que usa o serviço Office 365 Import para importar dados da conta do Twitter da sua organização para Microsoft 365. Para uma visão geral de alto nível desse processo e uma lista de pré-requisitos necessários para implantar um conector do Twitter, consulte Configurar um conector para arquivar dados [do Twitter. ](archive-twitter-data-with-sample-connector.md)

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Etapa 1: Criar um aplicativo no Azure Active Directory

1. Acesse e <https://portal.azure.com> entre usando as credenciais de uma conta de administrador global.

   ![Entrar no Azure](../media/TCimage01.png)

2. No painel de navegação esquerdo, clique em **Azure Active Directory**.

   ![Vá para Azure Active Directory](../media/TCimage02.png)

3. No painel de navegação esquerdo, clique em **Registros de aplicativo (Visualização)** e clique em **Novo registro**.

   ![Criar um novo registro de aplicativo](../media/TCimage03.png)

4. Registre o aplicativo. Em **URI de redirecionamento (opcional),** selecione **Web** na lista suspenso tipo de aplicativo e digite a caixa `https://portal.azure.com` para o URI.

   ![Digite https://portal.azure.com para o URI de redirecionamento](../media/TCimage04.png)

5. Copie a **ID do Aplicativo (cliente)** e a ID de Diretório **(locatário)** e salve-os em um arquivo de texto ou em outro local seguro. Use essas IDs em etapas posteriores.

    ![Copiar e salvar a ID do Aplicativo e a ID do Diretório](../media/TCimage05.png)

6. Vá para **Certificados & segredos do** novo aplicativo e em **Segredos do** cliente clique em Novo segredo **do cliente.**

   ![Criar um novo segredo do cliente](../media/TCimage06.png)

7. Crie um novo segredo. Na caixa descrição, digite o segredo e escolha um período de expiração.

   ![Digite o segredo e escolha o período de expiração](../media/TCimage08.png)

8. Copie o valor do segredo e salve-o em um arquivo de texto ou em outro local de armazenamento. Este é o segredo do aplicativo AAD que você usa nas etapas posteriores.

   ![Copiar e salvar o segredo](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Etapa 2: Implantar o serviço Web do conector GitHub sua conta do Azure

1. Vá para [este GitHub site e](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) clique em Implantar no **Azure**.

    ![Vá para a home page do Azure](../media/FBCimage11.png)

2. Depois de clicar **em Implantar no Azure,** você será redirecionado para um portal do Azure com uma página de modelo personalizada. Preencha os **detalhes básicos** **e Configurações** e clique em **Comprar**.

   ![Clique em Criar um recurso e digite conta de armazenamento](../media/FBCimage12.png)

    - **Assinatura:** Selecione sua assinatura do Azure para a que você deseja implantar o serviço Web do Conector do Twitter.

    - **Grupo de recursos:** Escolha ou crie um novo grupo de recursos. Um grupo de recursos é um contêiner que contém recursos relacionados para uma solução do Azure.

    - **Local:** Escolha um local.

    - **Nome do aplicativo Web:** Forneça um nome exclusivo para o aplicativo Web do conector. O nome deve ter entre 3 e 18 caracteres de comprimento. Esse nome é usado para criar a URL do serviço de aplicativo do Azure; por exemplo, se você fornecer o nome do aplicativo Web do **twitterconnector,** a URL do serviço de aplicativo do Azure **será** twitterconnector.azurewebsites.net .

    - **tenantId:** A ID de locatário da sua Microsoft 365 que você copiou após criar o aplicativo conector do Facebook no Azure Active Directory na Etapa 1.

   - **APISecretKey:** Você pode digitar qualquer valor como o segredo. Isso é usado para acessar o aplicativo Web do conector na Etapa 5.

3. Depois que a implantação for bem-sucedida, a página será semelhante à seguinte captura de tela:

    ![Clique Armazenamento e clique em Armazenamento conta](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a>Etapa 3: Criar o aplicativo twitter

1. Vá para , faça logoff usando as credenciais da conta de desenvolvedor da sua organização e clique https://developer.twitter.com em **Aplicativos**.

   ![Vá para https://developer.twitter.com e faça logoff](../media/TCimage25-5.png)
2. Clique **em Criar um aplicativo**.

   ![Vá para a página Aplicativos para criar um aplicativo](../media/TCimage26.png)

3. Em **Detalhes do aplicativo,** adicione informações sobre o aplicativo.

   ![Insira informações sobre o aplicativo](../media/TCimage27.png)

4. No painel de desenvolvedores do Twitter, selecione o aplicativo que você acabou de criar e clique em **Detalhes.**

   ![Copiar e salvar a ID do Aplicativo](../media/TCimage28.png)

5. Na guia **Chaves e tokens,** em Chaves da API do Consumidor, copie a Chave da **API** e a chave secreta da API e salve-as em um arquivo de texto ou em outro local de armazenamento. Em **seguida, clique** em Criar para gerar um token de acesso e acessar o segredo do token e copiá-los para um arquivo de texto ou outro local de armazenamento.

   ![Copiar e salvar na chave secreta da API](../media/TCimage29.png)

   Em **seguida, clique** em Criar para gerar um token de acesso e um segredo de token de acesso e copie-os para um arquivo de texto ou outro local de armazenamento.

6. Clique na **guia Permissões** e configure as permissões conforme mostrado na captura de tela a seguir:

   ![Configurar as permissões](../media/TCimage30.png)

7. Depois de salvar as configurações de permissão, clique na guia Detalhes **do** aplicativo e clique em Editar > **Editar detalhes**.

   ![Editar os detalhes do aplicativo](../media/TCimage31.png)

8. Faça as seguintes tarefas:

   - Marque a caixa de seleção para permitir que o aplicativo conector entre no Twitter.

   - Adicione o Uri de redirecionamento OAuth usando o seguinte formato: **\<connectorserviceuri> /Views/TwitterOAuth**, onde o valor *de connectorserviceuri* é a URL de serviço de aplicativo do Azure para sua organização; por exemplo, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth .

    ![Permitir que o aplicativo conector entre no Twitter e adicione Uri de redirecionamento OAuth](../media/TCimage32.png)

O aplicativo de desenvolvedor do Twitter agora está pronto para uso.

## <a name="step-4-configure-the-connector-web-app"></a>Etapa 4: Configurar o aplicativo Web do conector

1. Vá para https:// \<AzureAppResourceName> .azurewebsites.net (onde **AzureAppResourceName** é o nome do seu recurso de aplicativo do Azure nomeado na Etapa 4). Por exemplo, se o nome for **twitterconnector,** vá para https://twitterconnector.azurewebsites.net . A home page do aplicativo se parece com a seguinte captura de tela:

   ![Vá para a página de recursos do aplicativo do Azure](../media/FBCimage41.png)

2. Clique **em Configurar** para exibir uma página de login.

   ![Clique em Configurar para exibir a página de login](../media/FBCimage42.png)

3. Na caixa ID do locatário, digite ou colar sua ID de locatário (obtida na Etapa 2). Na caixa senha, digite ou colar a APISecretKey (obtida na Etapa 2) e clique em Definir Configuração **Configurações** para exibir a página de detalhes de configuração.

   ![Entrar usando a ID do locatário e a chave secreta da API](../media/TCimage35.png)

4. Insira as seguintes configurações

   - **Chave da Api do Twitter:** A chave da API para o aplicativo Twitter que você criou na Etapa 3.

   - **Chave Secreta da Api do Twitter:** A chave secreta da API para o aplicativo Twitter que você criou na Etapa 3.

   - **Token de Acesso para Twitter:** O token de acesso que você criou na Etapa 3.

   - **Segredo do Token de Acesso ao Twitter:** O segredo do token de acesso que você criou na Etapa 3.

   - **ID do aplicativo AAD:** A ID do aplicativo para o Azure Active Directory que você criou na Etapa 1

   - **Segredo do aplicativo AAD:** O valor do segredo APISecretKey criado na Etapa 1.

5. Clique **em Salvar** para salvar as configurações do conector.

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>Etapa 5: Configurar um conector do Twitter no Centro de conformidade do Microsoft 365

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **Conectores de dados** na nav esquerda.

2. Na página **Conectores de dados** em **Twitter,** clique em **Exibir**.

3. Na página **Twitter,** clique em **Adicionar conector**.

4. Na página **Termos de serviço,** clique em **Aceitar**.

5. Na página **Adicionar credenciais para seu** aplicativo do conector, insira as informações a seguir e clique em **Validar conexão**.

   ![Inserir credenciais de aplicativo de conector](../media/TCimage38.png)

    - Na caixa **Nome,** digite um nome para o conector, como Ajuda **do Twitter para manipular**.

    - Na caixa **URL do Conector,** digite ou colar a URL do serviço de aplicativo do Azure; por exemplo `https://twitterconnector.azurewebsites.net` .

    - Na caixa **Senha,** digite ou colar o valor da APISecretKey que você criou na Etapa 2.

    - Na caixa ID do Aplicativo **do Azure,** digite ou colar o valor da ID do Aplicativo do Azure (também chamada de *ID* do cliente ) obtida na Etapa 1.

6. Depois que a conexão for validada com êxito, clique em **Next**.

7. Na página **Autorizar Microsoft 365 importar** dados, digite ou colar a APISecretKey novamente e clique em **Logon do aplicativo Web**.

8. Clique **em Logon com o Twitter**.

9. Na página de login do Twitter, entre usando as credenciais da conta do Twitter da sua organização.

   ![Entrar na conta do Twitter](../media/TCimage42.png)

   Depois de entrar, a página do Twitter exibirá a seguinte mensagem, "Trabalho do Conector do Twitter Configurada com êxito".

10. Clique **em Continuar** para concluir a configuração do conector do Twitter.

11. Na página **Definir filtros,** você pode aplicar um filtro para importar inicialmente itens que têm uma determinada idade. Selecione uma idade e clique em **Próximo**.

12. Na página **Escolher local de armazenamento,** digite o endereço de email Microsoft 365 caixa de correio para a qual os itens do Twitter serão importados e clique em **Próximo**.

13. Clique **em Próximo** para revisar as configurações do conector e clique em **Concluir** para concluir a configuração do conector.

14. No centro de conformidade, vá até a página **Conectores de** dados e clique na guia **Conectores** para ver o andamento do processo de importação.
