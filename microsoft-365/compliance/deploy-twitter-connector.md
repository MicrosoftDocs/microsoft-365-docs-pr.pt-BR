---
title: Implantar um conector para arquivar dados do Twitter
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Os administradores podem configurar um conector nativo para importar e arquivar dados do Twitter para o Office 365. Depois que esses dados são importados para o Office 365, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar a governança dos dados do Twitter da sua organização.
ms.openlocfilehash: 87faad6546d70b1e3893e2f5737af189ebb5f77b
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806144"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a>Implantar um conector para arquivar dados do Twitter

Este artigo contém o processo passo a passo para implantar um conector que usa o serviço de importação do Office 365 para importar dados da conta do Twitter da sua organização para o Office 365. Para obter uma visão geral de alto nível desse processo e uma lista de pré-requisitos necessários para implantar um conector do Twitter, consulte [usar um conector de exemplo para arquivar dados do Twitter no Office 365 (versão prévia)](archive-twitter-data-with-sample-connector.md). 

## <a name="step-1-download-the-package"></a>Etapa 1: baixar o pacote

Baixe o pacote pré-criado da seção liberar no repositório do GitHub em [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases). Na versão mais recente, baixe o arquivo zip chamado **SampleConnector. zip**. Você carrega este arquivo zip no Azure na etapa 4.

## <a name="step-2-create-an-app-in-azure-active-directory"></a>Etapa 2: criar um aplicativo no Azure Active Directory

1. Vá para <https://portal.azure.com> e entre usando as credenciais de uma conta de administrador global do Office 365.

   ![Entrar no Azure](media/TCimage01.png)

2. No painel de navegação esquerdo, clique em **Azure Active Directory**.

   ![Vá para o Azure Active Directory](media/TCimage02.png)

3. No painel de navegação esquerdo, clique em **registros de aplicativo (visualização)** e clique em **novo registro**.

   ![Criar um novo registro de aplicativo](media/TCimage03.png)

4. Registre o aplicativo. Em **URI de redirecionamento (opcional)**, selecione **Web** na lista suspensa tipo de aplicativo `https://portal.azure.com` e digite a caixa para o URI.

   ![Tipo https://portal.azure.com para o URI de redirecionamento ](media/TCimage04.png)

5. Copie a ID de **aplicativo (cliente)** e a ID de **diretório (locatário)** e salve-as em um arquivo de texto ou outro local seguro. Você usa essas IDs em etapas posteriores.

    ![Copie e salve a ID do aplicativo e a ID de diretório](media/TCimage05.png)

6. Vá até **certificados & segredos para o novo aplicativo** e, em **segredos do cliente** , clique em **novo segredo do cliente**.

   ![Criar um novo segredo do cliente](media/TCimage06.png)

7. Criar um novo segredo. Na caixa Descrição, digite o segredo e, em seguida, escolha um período de expiração. 

   ![Digite o segredo e escolha o período de expiração](media/TCimage08.png)

8. Copie o valor do segredo e salve-o em um arquivo de texto ou outro local de armazenamento. Este é o segredo do aplicativo AAD que você usa nas etapas posteriores.

   ![Copie e salve o segredo](media/TCimage09.png)

9. Vá para **manifesto** e copie o identifieruris agora (que também é chamado de URI do aplicativo AAD) como realçado na captura de tela a seguir. Copie o URI do aplicativo AAD para um arquivo de texto ou outro local de armazenamento. Você pode usá-lo na etapa 6.

    ![Copie e salve o URI do aplicativo AAD](media/TCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a>Etapa 3: criar uma conta de armazenamento do Azure

1.  Vá para a home page do Azure para sua organização.

    ![GI para a página inicial do Azure](media/TCimage11.png)

2. Clique em **criar um recurso** e digite a **conta de armazenamento** na caixa de pesquisa.

   ![Criar um recurso da conta de armazenamento](media/TCimage12.png)

3. Clique em **armazenamento**e, em seguida, clique em **conta de armazenamento**.

   ![Clique em armazenamento e em conta de armazenamento](media/TCimage13.png)

4. Na página **criar conta de armazenamento** , na caixa assinatura, selecione **pagar como você** ou **avaliação gratuita** , dependendo do tipo de assinatura do Azure que você tem. 

   ![Selecionar um tipo de conta de armazenamento](media/TCimage14.png)

5. Selecione ou crie um grupo de recursos.

   ![Selecionar ou criar um grupo de recursos](media/TCimage15.png)

6. Digite um nome para a conta de armazenamento.

   ![Nomear a conta de armazenamento](media/TCimage16.png)

7. Revise e clique em **criar** para criar a conta de armazenamento.

   ![Revisar configurações e criar conta de armazenamento](media/TCimage17.png)

8. Após alguns momentos, clique em **Atualizar** e clique em **ir para recurso** para navegar até a conta de armazenamento.

   ![Vá para a conta de armazenamento que você acabou de criar](media/TCimage18.png)

9. Clique em **teclas de acesso** no painel de navegação esquerdo.

   ![Clique em teclas de acesso](media/TCimage19.png)

10. Copie uma **cadeia de caracteres de conexão** e salve-a em um arquivo de texto ou outro local de armazenamento. Você usa isso ao criar um recurso do aplicativo Web na etapa 4.

    ![Copiar uma cadeia de conexão](media/TCimage20.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a>Etapa 4: criar um novo recurso do aplicativo Web no Azure

1. Na **Home** Page do portal do Azure, clique em **criar um recurso \> para \> todos os aplicativos Web**. Na página **Web App** , clique em **criar**.

   ![Criar recurso do aplicativo Web no Azure](media/TCimage21.png)

2. Preencha os detalhes (conforme mostrado abaixo) e, em seguida, crie o aplicativo Web. O nome inserido na caixa nome do **aplicativo** é usado para criar a URL do serviço de aplicativo do Azure; por exemplo, twitterconnector.azurewebsites.net.

   ![Nome do tipo para o recurso do aplicativo Web; por exemplo twitterconnector.azurewebsites.net ](media/TCimage22.png)

3. Vá para o recurso aplicativo Web recém-criado e clique em **configurações do aplicativo** no painel de navegação esquerdo. Em **configurações do aplicativo**, clique em **Adicionar nova configuração** e adicione as três configurações a seguir. Use os valores (que você copiou para o arquivo de texto das etapas anteriores): 

    - **APISecretKey** – você pode digitar qualquer valor como o segredo. Isso é usado para acessar o aplicativo Web do conector na etapa 7.

    - **StorageAccountConnectionString** – o URI da cadeia de caracteres de conexão que você copiou após a criação da conta de armazenamento do Azure na etapa 3.

    - **tenantid** – a ID do locatário de sua organização do Office 365 que você copiou depois de criar o aplicativo do conector do Twitter no Azure Active Directory na etapa 2.

    ![Adicionar configurações de aplicativo](media/TCimage23.png)

4. Em **configurações gerais**, clique **em** ao lado de **sempre ligado**. Clique em **salvar** na parte superior da página para salvar as configurações do aplicativo.

   ![Ativar o recurso do aplicativo Web e salvá-lo](media/TCimage24.png)

5. A etapa final é carregar o código-fonte do aplicativo conector para o Azure que você baixou na etapa 1. Em um navegador da Web, vá para<AzureAppResourceName>https://. SCM.azurewebsites.net/ZipDeployUi. Por exemplo, se o nome do seu recurso de aplicativo do Azure (que você nomeou na etapa 2 nesta seção) for **twitterconnector**, vá para https://twitterconnector.scm.azurewebsites.net/ZipDeployUi.

6. Arraste e solte o SampleConnector. zip (que você baixou na etapa 1) para esta página. Após o carregamento dos arquivos e a implantação ter êxito, a página será semelhante à captura de tela a seguir:

   ![Arraste e solte o arquivo SampleConnector. zip nesta página](media/TCimage25.png)

## <a name="step-5-create-the-twitter-app"></a>Etapa 5: criar o aplicativo Twitter

1. Vá para https://developer.twitter.com, faça logon usando as credenciais da conta de desenvolvedor da sua organização e clique em **aplicativos**.

   ![Ir para https://developer.twitter.com e fazer logon](media/TCimage25-5.png)
2. Clique em **criar um aplicativo**.
   
   ![Ir para a página aplicativos para criar um aplicativo](media/TCimage26.png)

3. Em **detalhes do aplicativo**, adicione informações sobre o aplicativo.

   ![Inserir informações sobre o aplicativo](media/TCimage27.png)

4. No painel de desenvolvedor do Twitter, selecione o aplicativo que você acabou de criar e copie a ID do aplicativo que é exibida e salve-a em um arquivo de texto ou outro local de armazenamento. Em seguida, clique em **detalhes**.
   
   ![Copiar e salvar a ID do aplicativo](media/TCimage28.png)

5. Na guia **chaves e tokens** , em **chaves da API do consumidor** , copie a chave secreta da API e salve-a em um arquivo de texto ou outro local de armazenamento. Em seguida, clique em **criar** para gerar um token de acesso e um segredo de token de acesso e copie-os para um arquivo de texto ou outro local de armazenamento.
   
   ![Copiar e salvar a chave secreta da API](media/TCimage29.png)

   Em seguida, clique em **criar** para gerar um token de acesso e um segredo de token de acesso e copie-os para um arquivo de texto ou outro local de armazenamento.

6. Clique na guia **permissões** e configure as permissões conforme mostrado na captura de tela a seguir:

   ![Configurar permissões](media/TCimage30.png)

7. Após salvar as configurações de permissão, clique na guia **detalhes do aplicativo** e, em seguida, clique em **Editar > editar detalhes**.

   ![Editar os detalhes do aplicativo](media/TCimage31.png)

8. Execute as seguintes tarefas:

   - Marque a caixa de seleção para permitir que o aplicativo conector entre no Twitter.
   
   - Adicione o URI de redirecionamento OAuth usando o seguinte formato: ** \<connectorserviceuri>/views/twitteroauth**, onde o valor de *connectorserviceuri* é a URL do serviço de aplicativo do Azure para sua organização; por exemplo, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.

    ![Permitir que o aplicativo conector entre no Twitter e adicione o URI de redirecionamento OAuth](media/TCimage32.png)

O aplicativo de desenvolvedor do Twitter agora está pronto para uso.

## <a name="step-6-configure-the-connector-web-app"></a>Etapa 6: configurar o aplicativo Web do conector 

1. Vá para https://\<AzureAppResourceName>. azurewebsites.net (onde **AzureAppResourceName** é o nome do seu recurso do aplicativo do Azure que você nomeou na etapa 4). Por exemplo, se o nome for **twitterconnector**, vá para https://twitterconnector.azurewebsites.net. A home page do aplicativo é semelhante à captura de tela a seguir:

   ![Ir para a página de recursos do aplicativo do Azure](media/FBCimage41.png)

2. Clique em **Configurar** para exibir uma página de entrada.

   ![Clique em configurar para exibir a página de entrada](media/FBCimage42.png)

3. Na caixa ID do locatário, digite ou cole sua ID de locatário (que você obteve na etapa 2). Na caixa senha, digite ou cole o APISecretKey (que você obteve na etapa 2) e clique em **definir definições de configuração** para exibir a página **detalhes da configuração** .

   ![Entrar usando a ID do locatário e a chave secreta da API](media/TCimage35.png)

4. Em **detalhes da configuração**, insira as seguintes definições de configuração 

   - **Chave de API do Twitter** – a ID de aplicativo do aplicativo Twitter que você criou na etapa 5.
   - **Chave secreta da API do Twitter** – a chave secreta da API do aplicativo Twitter que você criou na etapa 5.
   - **Token de acesso do Twitter** – o token de acesso que você criou na etapa 5.
   - **Segredo do token de acesso do Twitter** – o segredo do token de acesso que você criou na etapa 5.
   - **ID do aplicativo AAD** – a ID do aplicativo para o aplicativo do Azure Active Directory que você criou na etapa 2
   - **Segredo do aplicativo AAD** – o valor para o segredo APISecretKey que você criou na etapa 4.
   - **URI do aplicativo AAD** – o URI do aplicativo AAD obtido na etapa 2; por exemplo, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.
   - **Chave de instrumentação do App insights** – deixe esta caixa em branco.

5. Clique em **salvar** para salvar as configurações do conector.

## <a name="step-7-set-up-a-custom-connector-in-the-security-and-compliance-center"></a>Etapa 7: configurar um conector personalizado no centro de conformidade e segurança

1.  Vá para <https://protection.office.com> e, em seguida, clique em **importação \> \> de governança de informações arquivar dados de terceiros**.

    ![Ir para arquivo morto de página de dados de terceiros no centro de conformidade e segurança](media/TCimage36.png)

2. Clique em **Adicionar um conector** e, em seguida, clique em **Twitter**.

   ![Clique em Adicionar um conector para adicionar um conector do Twitter](media/TCimage37.png)

3. Na página **Adicionar aplicativo do conector** , digite as informações a seguir e clique em **validar conector**.

    - Na primeira caixa, digite um nome para o conector, como **Twitter**.
    - Na segunda caixa, digite ou cole o valor do APISecretKey que você adicionou na etapa 4.
    - Na terceira caixa, digite ou cole a URL do serviço de aplicativo do Azure; por exemplo, **https://twitterconnector.azurewebsites.net**.

   Depois que o conector for validado com êxito, clique em **Avançar**.

   ![Inserir configurações de aplicativo do conector](media/TCimage38.png)

4. Clique em **login com o aplicativo do conector**.

   ![Fazer logon no aplicativo do conector](media/TCimage39.png)

5. Digite ou cole o APISecretKey novamente e, em seguida, clique em **login to Connector Service**.

   ![Chave secreta da API de tipo para fazer logon no serviço do conector](media/TCimage40.png)

6. Clique em **continuar com o Twitter**.

7. Na página de entrada do Twitter, entre usando as credenciais da conta da conta do Twitter da sua organização.

   ![Entrar na conta do Twitter](media/TCimage42.png)

   Depois que você entrar, a página do Twitter exibirá a seguinte mensagem, "trabalho do conector do Twitter configurado com êxito".

8. Clique em **concluir** para concluir a configuração do conector do Twitter.

9. Na página **definir filtros** , você pode aplicar um filtro para importar (e arquivar) itens que são uma determinada idade. Clique em **Avançar**.

   ![Configurar filtro para importar itens de uma determinada idade](media/TCimage44.png)

10. Na página **definir conta de armazenamento** , digite o endereço de email de uma caixa de correio do Office 365 para a qual os itens do Twitter serão importados.

    ![Especificar uma caixa de correio do Office 365 para importar itens do Twitter para](media/TCimage45.png)

11. Revise suas configurações e clique em **concluir** para concluir a configuração do conector no centro de conformidade do & de segurança.

    ![Revise as configurações e clique em concluir](media/TCimage46.png)

    ![Tela mostrando que a configuração do conector está concluída](media/TCimage47.png)

12. Vá para a página **arquivar dados** de terceiros para ver o andamento do processo de importação.

    ![Novo conector exibido no centro de conformidade e segurança](media/TCimage48.png)
