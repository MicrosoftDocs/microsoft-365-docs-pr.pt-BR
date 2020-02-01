---
title: Implantar um conector para arquivar dados de páginas de negócios do Facebook
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
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Os administradores podem configurar um conector nativo para importar e arquivar páginas de negócios do Facebook para o Microsoft 365. Depois que esses dados são importados para a Microsoft 365, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar a governança dos dados de Facebook da sua organização.
ms.openlocfilehash: 22810b377abf3ed30c53bab2cd27b970a5dcd62f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595296"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a>Implantar um conector para arquivar dados de páginas de negócios do Facebook

Este artigo contém o processo passo a passo para implantar um conector que usa o serviço de importação 365 da Microsoft para importar dados de páginas de negócios do Facebook para o Microsoft 365. Para obter uma visão geral de alto nível desse processo e uma lista de pré-requisitos necessários para implantar um conector do Facebook, consulte [configurar um conector para arquivar dados do Facebook](archive-facebook-data-with-sample-connector.md). 

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Etapa 1: criar um aplicativo no Azure Active Directory

1. Vá para <https://portal.azure.com> e entre usando as credenciais de uma conta de administrador global do Office 365.

    ![Criar aplicativo no AAD](media/FBCimage1.png)

2. No painel de navegação esquerdo, clique em **Azure Active Directory**.

    ![Clique em Azure Active Directory](media/FBCimage2.png)

3. No painel de navegação esquerdo, clique em **registros de aplicativo (visualização)** e clique em **novo registro**.

    ![Clique em * * registros de aplicativo (visualização) * * e, em seguida, clique em * * novo registro * *](media/FBCimage3.png)

4. Registre o aplicativo. Em URI de redirecionamento, selecione Web na lista suspensa tipo de aplicativo <https://portal.azure.com> e digite na caixa para o URI.

   ![Registrar o aplicativo](media/FBCimage4.png)

5. Copie a ID de **aplicativo (cliente)** e a ID de **diretório (locatário)** e salve-as em um arquivo de texto ou outro local seguro. Você usa essas IDs em etapas posteriores.

   ![Copie a ID do aplicativo e a ID de diretório e salve-as](media/FBCimage5.png)

6. Vá até **certificados & segredos para o novo aplicativo.**

   ![Vá até certificados & segredos para o novo aplicativo](media/FBCimage6.png)

7. Clique em **novo segredo do cliente**

   ![Clique em novo segredo do cliente](media/FBCimage7.png)

8. Criar um novo segredo. Na caixa Descrição, digite o segredo e, em seguida, escolha um período de expiração. 

    ![Digite o segredo e, em seguida, escolha um período de expiração](media/FBCimage8.png)

9. Copie o valor do segredo e salve-o em um arquivo de texto ou outro local de armazenamento. Este é o segredo do aplicativo AAD que você usa nas etapas posteriores.

   ![Copie o valor do segredo e salve-o](media/FBCimage9.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Etapa 2: implantar o serviço Web do conector do GitHub em sua conta do Azure

1. Vá para [este site do GitHub](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) e clique em **implantar no Azure**.

    ![Clique em implantar no Azure](media/FBCGithubApp.png)

2. Depois de clicar em **implantar no Azure**, você será redirecionado para um portal do Azure com uma página de modelo Personalizada. Preencha os detalhes **básico** e **configurações** e clique em **compra**.

    - **Assinatura:** Selecione sua assinatura do Azure para a qual você deseja implantar o serviço Web do conector de páginas de negócios do Facebook.
    
    - **Grupo de recursos:** Escolha ou crie um novo grupo de recursos. Um grupo de recursos é um contêiner que armazena recursos relacionados a uma solução do Azure.

    - **Local:** Escolha um local.

    - **Nome do aplicativo Web:** Forneça um nome exclusivo para o aplicativo Web do conector. O nome do ésimo deve ter entre 3 e 18 caracteres de comprimento. Esse nome é usado para criar a URL do serviço de aplicativo do Azure; por exemplo, se você fornecer o nome do aplicativo Web do **fbconnector** , a URL do serviço de aplicativo do Azure será **fbconnector.azurewebsites.net**.
    
    - **tenantid:** A ID de locatário da sua organização do Microsoft 365 que você copiou após criar o aplicativo do Facebook Connector no Azure Active Directory na etapa 1.
    
   - **APISecretKey:** Você pode digitar qualquer valor como o segredo. Isso é usado para acessar o aplicativo Web do conector na etapa 5.
   
     ![Clique em criar uma conta de armazenamento de recurso e tipo](media/FBCimage12.png)

3. Após a implantação ter êxito, a página será semelhante à captura de tela a seguir:

     ![Clique em armazenamento e em conta de armazenamento](media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a>Etapa 3: registrar o aplicativo do Facebook

1. Vá para <https://developers.facebook.com>, faça logon usando as credenciais da conta das páginas de negócios de Facebook da sua organização e clique em **Adicionar novo aplicativo**.

   ![Adicionar um novo aplicativo para a página de negócios do Facebook](media/FBCimage25.png)

2. Crie uma nova ID de aplicativo.

   ![Criar uma nova ID de aplicativo](media/FBCimage26.png)

3. No painel de navegação esquerdo, clique em **Adicionar produtos** e, em seguida, clique em **Configurar** no bloco de **logon do Facebook** .

   ![Clique em Adicionar produtos](media/FBCimage27.png)

4. Na página integrar login do Facebook, clique em **Web**.

   ![Clique em Web na página integrar logon do Facebook](media/FBCimage28.png)

5. Adicione a URL do serviço de aplicativo do Azure; por exemplo `https://fbconnector.azurewebsites.net`.

   ![Adicionar a URL do serviço de aplicativo do Azure](media/FBCimage29.png)

6. Preencha a seção QuickStart da configuração de login do Facebook.

   ![Concluir a seção QuickStart](media/FBCimage30.png)

7. No painel de navegação esquerdo em **logon do Facebook**, clique em **configurações**e adicione o URI de redirecionamento OAuth na caixa **URIs de redirecionamento OAuth válidos** . Use o formato ** \<connectorserviceuri>/views/facebookoauth**, onde o valor de connectorserviceuri é a URL do serviço de aplicativo do Azure para sua organização; por exemplo, `https://fbconnector.azurewebsites.net`.

   ![Adicione o URI de redirecionamento OAuth à caixa URIs de redirecionamento OAuth válidos](media/FBCimage31.png)

8. No painel de navegação esquerdo, clique em **Adicionar produtos** e, em seguida, clique em **WebHooks.** No menu suspenso da **página** , clique em **página**. 

   ![Clique em Adicionar produtos e em * * WebHooks](media/FBCimage32.png)

9. Adicione URL de retorno de chamada de WebHooks e adicione um token de verificação. O formato da URL de retorno de chamada, use o formato ** <connectorserviceuri>/API/FbPageWebhook**, em que o valor de connectorserviceuri é a URL do serviço de aplicativo do Azure para sua organização; por exemplo `https://fbconnector.azurewebsites.net`. 

    O token de verificação deve ser semelhante a uma senha forte. Copie o token de verificação para um arquivo de texto ou outro local de armazenamento.

        ![Add the verify token](media/FBCimage33.png)

10. Teste e assine o ponto de extremidade do feed.

    ![Testar e inscrever-se no ponto de extremidade](media/FBCimage34.png)

11. Adicione uma URL de privacidade, ícone de aplicativo e uso comercial. Além disso, copie a ID do aplicativo e o segredo do aplicativo para um arquivo de texto ou outro local de armazenamento.

    ![Adicionar uma URL de privacidade, ícone de aplicativo e uso comercial](media/FBCimage35.png)

12. Tornar o aplicativo público.

    ![Tornar o aplicativo público](media/FBCimage36.png)

13. Adicionar usuário à função de administrador ou de testador.

    ![Adicionar usuário à função de administrador ou de testador](media/FBCimage37.png)

14. Adicione a permissão de **acesso ao conteúdo público da página** .

    ![Adicionar a permissão de acesso ao conteúdo público da página](media/FBCimage38.png)

15. Permissão Adicionar gerenciar páginas.

    ![Permissão Adicionar gerenciar páginas](media/FBCimage39.png)

16. Obtenha o aplicativo revisado pelo Facebook.

    ![Obter o aplicativo revisado pelo Facebook](media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a>Etapa 4: configurar o aplicativo Web do conector

1. Vá para https://\<AzureAppResourceName>. azurewebsites.net (onde AzureAppResourceName é o nome do seu recurso do aplicativo do Azure que você nomeou na etapa 4) por exemplo, se o nome for **fbconnector**, vá para `https://fbconnector.azurewebsites.net`. A home page do aplicativo se parecerá com a captura de tela a seguir:

   ![Vá para o aplicativo Web do conector](media/FBCimage41.png)

2. Clique em **Configurar** para exibir uma página de entrada.
 
   ![Clique em configurar para exibir uma página de entrada](media/FBCimage42.png)

3. Na caixa ID do locatário, digite ou cole sua ID de locatário (que você obteve na etapa 2). Na caixa senha, digite ou cole o APISecretKey (que você obteve na etapa 2) e clique em **definir definições de configuração** para exibir a página detalhes da configuração.

    ![Entre usando sua ID de locatário e senha e vá para a página de detalhes de configuração](media/FBCimage43.png)

4. Insira as seguintes definições de configuração 

   - **ID do aplicativo do Facebook:** A ID de aplicativo para o aplicativo do Facebook obtido na etapa 3.
   
   - **Segredo do aplicativo do Facebook:** O segredo do aplicativo para o aplicativo do Facebook obtido na etapa 3.
   
   - **Token de verificação de WebHooks do Facebook:** O token de verificação que você criou na etapa 3.
   
   - **ID do aplicativo AAD:** A ID de aplicativo do aplicativo do Azure Active Directory que você criou na etapa 1.
   
   - **Segredo do aplicativo AAD:** O valor para o segredo APISecretKey que você criou na etapa 1.

5. Clique em **salvar** para salvar as configurações do conector.

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a>Etapa 5: configurar um conector do Facebook no centro de conformidade do Microsoft 365

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **conectores de dados** no painel de navegação esquerdo.

2. Na página **conectores de dados (visualização)** , em **páginas de negócios do Facebook**, clique em **Exibir**.

3. Na página **páginas de negócios do Facebook** , clique em **Adicionar conector**.

4. Na página **termos de serviço** , clique em **aceitar**.

5.  Na página **Adicionar credenciais para seu aplicativo do conector** , digite as informações a seguir e clique em **validar conexão**.

    ![Inserir credenciais de aplicativo do conector](media/TCimage38.png)

    - Na caixa **nome** , digite um nome para o conector, como página de **notícias do Facebook**.
    
    - Na caixa **URL da conexão** , digite ou cole a URL do serviço de aplicativo do Azure; por exemplo `https://fbconnector.azurewebsites.net`.
    
    - Na caixa **senha** , digite ou cole o valor do APISecretKey que você adicionou na etapa 2.
    
    - Na caixa **ID do aplicativo do Azure** , digite ou cole o valor da ID do aplicativo (cliente) também chamado de ID do aplicativo AAD que você criou na etapa 1.
 
6. Depois que a conexão for validada com êxito, clique em **Avançar**.

7. Na página **autorizar o Microsoft 365 a importar dados** , digite ou cole o APISecretKey novamente e clique em **fazer logon no aplicativo Web**.

8. Na página **Configurar aplicativo do Facebook Connector** , clique em **logon com Facebook** e faça logon usando as credenciais da conta para as páginas de negócios de Facebook da sua organização. Certifique-se de que a conta do Facebook na qual você está conectado tenha a função de administrador para as páginas de negócios de Facebook da sua organização.

   ![Faça logon com o Facebook](media/FBCimage50.png)

9. É exibida uma lista das páginas de negócios gerenciadas pela conta do Facebook que você fez logon. Selecione a página para arquivar e clique em **Avançar**.

    ![Selecione a página de negócios da organização que você deseja arquivar](media/FBCimage52.png)

10. Clique em **continuar** para sair da configuração do aplicativo de serviço do conector.

11. Na página **definir filtros** , você pode aplicar um filtro para importar inicialmente os itens que tenham uma determinada idade. Selecione uma idade e clique em **Avançar**.

12. Na página **escolher local de armazenamento** , digite o endereço de email da caixa de correio do Microsoft 365 para o qual os itens do Facebook serão importados e clique em **Avançar**.

13. Em **fornecer consentimento do administrador**, clique em **fornecer consentimento** e siga as etapas. Você deve ser um administrador global para fornecer consentimento para o serviço de importação do Office 365 para acessar dados em sua organização.

14. Clique em **Avançar** para revisar as configurações do conector e clique em **concluir** para concluir a configuração do conector.

15. No centro de conformidade, vá para a página **conectores de dados** e clique na guia **conectores** para ver o andamento do processo de importação.
