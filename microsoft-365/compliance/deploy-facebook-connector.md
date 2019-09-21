---
title: Implantar um conector para arquivar dados do Facebook no Office 365
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
description: Os administradores podem configurar um conector nativo para importar e arquivar páginas de negócios do Facebook no Office 365. Depois que esses dados são importados para o Office 365, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar a governança dos dados de Facebook da sua organização.
ms.openlocfilehash: 1f5b0f241616cc95e79e80d054a8782f97c5887b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37070741"
---
# <a name="deploy-a-connector-to-archive-facebook-data-in-office-365"></a>Implantar um conector para arquivar dados do Facebook no Office 365

Este artigo contém o processo passo a passo para implantar um conector que usa o serviço de importação do Office 365 para importar dados de páginas de negócios do Facebook para o Office 365. Para obter uma visão geral de alto nível desse processo e uma lista de pré-requisitos necessários para implantar um conector do Facebook, consulte [usar um conector de exemplo para arquivar dados do Facebook no Office 365 (versão prévia)](archive-facebook-data-with-sample-connector.md). 

## <a name="step-1-download-the-package"></a>Etapa 1: baixar o pacote

Baixe o pacote pré-criado da seção liberar no repositório do GitHub em <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>. Na versão mais recente, baixe o arquivo zip chamado **SampleConnector. zip**. Você carrega este arquivo zip no Azure na etapa 4.

## <a name="step-2-create-an-app-in-azure-active-directory"></a>Etapa 2: criar um aplicativo no Azure Active Directory

1. Vá para <https://portal.azure.com> e entre usando as credenciais de uma conta de administrador global do Office 365.

    ![Criar aplicativo no AAD](media/FBCimage1.png)

2. No painel de navegação esquerdo, clique em **Azure Active Directory**.

    ![](media/FBCimage2.png)

3. No painel de navegação esquerdo, clique em **registros de aplicativo (visualização)** e clique em **novo registro**.

    ![](media/FBCimage3.png)

4. Registre o aplicativo. Em URI de redirecionamento, selecione Web na lista suspensa tipo de aplicativo <https://portal.azure.com> e digite na caixa para o URI.

   ![](media/FBCimage4.png)

5. Copie a ID de **aplicativo (cliente)** e a ID de **diretório (locatário)** e salve-as em um arquivo de texto ou outro local seguro. Você usa essas IDs em etapas posteriores.

   ![](media/FBCimage5.png)

6. Vá até **certificados & segredos para o novo aplicativo.**

   ![](media/FBCimage6.png)

7. Clique em **novo segredo do cliente**

   ![](media/FBCimage7.png)

8. Criar um novo segredo. Na caixa Descrição, digite o segredo e, em seguida, escolha um período de expiração. 

    ![](media/FBCimage8.png)

9. Copie o valor do segredo e salve-o em um arquivo de texto ou outro local de armazenamento. Este é o segredo do aplicativo AAD que você usa nas etapas posteriores.

   ![](media/FBCimage9.png)

10. Vá para **manifesto** e copie o identifieruris agora (que também é chamado de URI do aplicativo AAD) como realçado na captura de tela a seguir. Copie o URI do aplicativo AAD para um arquivo de texto ou outro local de armazenamento. Você pode usá-lo na etapa 6.

   ![](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a>Etapa 3: criar uma conta de armazenamento do Azure

1. Vá para a home page do Azure para sua organização.

    ![](media/FBCimage11.png)

2. Clique em **criar um recurso** e digite a **conta de armazenamento** na caixa de pesquisa.

    ![](media/FBCimage12.png)

3. Clique em **armazenamento**e, em seguida, clique em **conta de armazenamento**.

    ![](media/FBCimage13.png)

4. Na página **criar conta de armazenamento** , na caixa assinatura, selecione **pagar como você** ou **avaliação gratuita** , dependendo do tipo de assinatura do Azure que você tem. Em seguida, selecione ou crie um grupo de recursos.

    ![](media/FBCimage14.png)

5. Digite um nome para a conta de armazenamento.

    ![](media/FBCimage15.png)

6. Revise e clique em **criar** para criar a conta de armazenamento.

    ![](media/FBCimage16.png)

7. Após alguns momentos, clique em **Atualizar** e clique em **ir para recurso** para navegar até a conta de armazenamento.

    ![](media/FBCimage17.png)

8. Clique em **teclas de acesso** no painel de navegação esquerdo.

    ![](media/FBCimage18.png)

9. Copie uma **cadeia de caracteres de conexão** e salve-a em um arquivo de texto ou outro local de armazenamento. Você usa isso ao criar um recurso do aplicativo Web.

    ![](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a>Etapa 4: criar um novo recurso do aplicativo Web no Azure

1. Na **Home** Page do portal do Azure, clique em **criar um recurso \> para \> todos os aplicativos Web**. Na página **Web App** , clique em **criar**. 

   ![](media/FBCimage20.png)

2. Preencha os detalhes (conforme mostrado abaixo) e, em seguida, crie o aplicativo Web. Observe que o nome inserido na caixa nome do **aplicativo** é usado para criar a URL do serviço de aplicativo do Azure; por exemplo, fbconnector.azurewebsites.net.

   ![](media/FBCimage21.png)

3. Vá para o recurso aplicativo Web recém-criado, clique em **configurações do aplicativo** no painel de navegação esquerdo. Em configurações do aplicativo, clique em Adicionar nova configuração e adicione as três configurações a seguir: Use os valores (que você copiou para o arquivo de texto das etapas anteriores): 

    – **APISecretKey** – você pode digitar qualquer valor como o segredo. Isso é usado para acessar o aplicativo Web do conector na etapa 7.

    – * * StorageAccountConnectionString — o URI da cadeia de caracteres de conexão que você copiou após a criação da conta de armazenamento do Azure na etapa 3.

    – **tenantid** – a ID do locatário de sua organização do Office 365 que você copiou depois de criar o aplicativo do Facebook Connector no Azure Active Directory na etapa 2.

    ![](media/FBCimage22.png)

4. Em **configurações gerais**, clique **em** ao lado de **sempre ligado**. Clique em **salvar** na parte superior da página para salvar as configurações do aplicativo.

   ![](media/FBCimage23.png)

5. A etapa final é carregar o código-fonte do aplicativo conector para o Azure que você baixou na etapa 1. Em um navegador da Web, vá para<AzureAppResourceName>https://. SCM.azurewebsites.net/ZipDeployUi. Por exemplo, se o nome do seu recurso de aplicativo do Azure (que você nomeou na etapa 2 nesta seção) for **fbconnector**, vá para https://fbconnector.scm.azurewebsites.net/ZipDeployUi. 

6. Arraste e solte o SampleConnector. zip (que você baixou na etapa 1) para esta página. Após o carregamento dos arquivos e a implantação ter êxito, a página será semelhante à captura de tela a seguir:

   ![](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a>Etapa 5: registrar o aplicativo do Facebook

1. Vá para <https://developers.facebook.com>, faça logon usando as credenciais da conta das páginas de negócios de Facebook da sua organização e clique em **Adicionar novo aplicativo**.

   ![](media/FBCimage25.png)

2. Crie uma nova ID de aplicativo.

   ![](media/FBCimage26.png)

3. No painel de navegação esquerdo, clique em **Adicionar produtos** e, em seguida, clique em **Configurar** no bloco de **logon do Facebook** .

   ![](media/FBCimage27.png)

4. Na página integrar login do Facebook, clique em **Web**.

   ![](media/FBCimage28.png)

5. Adicione a URL do serviço de aplicativo do Azure; por exemplo https://fbconnector.azurewebsites.net.

   ![](media/FBCimage29.png)

6. Preencha a seção QuickStart da configuração de login do Facebook.

   ![](media/FBCimage30.png)

7. No painel de navegação esquerdo em **logon do Facebook**, clique em **configurações**e adicione o URI de redirecionamento OAuth na caixa **URIs de redirecionamento OAuth válidos** . Use o formato ** \<connectorserviceuri>/views/facebookoauth**, onde o valor de connectorserviceuri é a URL do serviço de aplicativo do Azure para sua organização; por exemplo, https://fbconnector.azurewebsites.net.

   ![](media/FBCimage31.png)

8. No painel de navegação esquerdo, clique em **Adicionar produtos** e, em seguida, clique em **WebHooks.** No menu suspenso da **página** , clique em **página**. 

   ![](media/FBCimage32.png)

9. Adicione URL de retorno de chamada de WebHooks e adicione um token de verificação. O formato da URL de retorno de chamada, use o formato ** <connectorserviceuri>/API/FbPageWebhook**, em que o valor de connectorserviceuri é a URL do serviço de aplicativo do Azure para sua organização; por exemplo https://fbconnector.azurewebsites.net. 

    O token de verificação deve ser semelhante a uma senha forte. Copie o token de verificação para um arquivo de texto ou outro local de armazenamento.

     ![](media/FBCimage33.png)

10. Teste e assine o ponto de extremidade do feed.

    ![](media/FBCimage34.png)

11. Adicione uma URL de privacidade, ícone de aplicativo e uso comercial. Além disso, copie a ID do aplicativo e o segredo do aplicativo para um arquivo de texto ou outro local de armazenamento.

    ![](media/FBCimage35.png)

12. Tornar o aplicativo público.

    ![](media/FBCimage36.png)

13. Adicionar usuário à função de administrador ou de testador.

    ![](media/FBCimage37.png)

14. Adicione a permissão de **acesso ao conteúdo público da página** .

    ![](media/FBCimage38.png)

15. Permissão Adicionar gerenciar páginas.

    ![](media/FBCimage39.png)

16. Obtenha o aplicativo revisado pelo Facebook.

    ![](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a>Etapa 6: configurar o aplicativo Web do conector

1. Vá para https://\<AzureAppResourceName>. azurewebsites.net (onde AzureAppResourceName é o nome do seu recurso do aplicativo do Azure que você nomeou na etapa 4) por exemplo, se o nome for **fbconnector**, vá para https://fbconnector.azurewebsites.net. A home page do aplicativo se parecerá com a captura de tela a seguir:


   ![](media/FBCimage41.png)

2. Clique em **Configurar** para exibir uma página de entrada.
 
   ![](media/FBCimage42.png)

3. Na caixa ID do locatário, digite ou cole sua ID de locatário (que você obteve na etapa 2). Na caixa senha, digite ou cole o APISecretKey (que você obteve na etapa 2) e clique em **definir definições de configuração** para exibir a página **detalhes da configuração** .

    ![](media/FBCimage43.png)


4. Em **detalhes da configuração**, insira as seguintes definições de configuração 

   – **ID do aplicativo do Facebook** – a ID do aplicativo para o aplicativo Facebook obtido na etapa 5.
   – **Segredo do aplicativo do Facebook** – o segredo do aplicativo para o aplicativo do Facebook obtido na etapa 5.
   – **Token de verificação de WebHooks do Facebook** – o token de verificação que você criou na etapa 5.
   – **ID do aplicativo AAD** – a ID do aplicativo para o aplicativo do Azure Active Directory que você criou na etapa 2.
   – **Segredo do aplicativo AAD** – o valor para o segredo APISecretKey que você criou na etapa 4.
   – **URI do aplicativo AAD** – o URI do aplicativo AAD obtido na etapa 2; por exemplo, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.
   – **Chave de instrumentação do App insights** – deixe esta caixa em branco.

5. Clique em **salvar** para salvar as configurações do conector.

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a>Etapa 7: configurar um conector personalizado no centro de conformidade & segurança

1. Vá para <https://protection.office.com> e, em seguida, clique em **arquivar importação \> \> de governança de dados dados de terceiros**.

   ![](media/FBCimage44.png)

2.  Clique em **Adicionar um conector** e, em seguida, clique em **páginas do Facebook**.

    ![](media/FBCimage46.png)

3.  Na página **Adicionar aplicativo do conector** , digite as informações a seguir e clique em **validar conector**.

    – Na primeira caixa, digite um nome para o conector, como o **Facebook**.
    – Na segunda caixa, digite ou cole o valor do APISecretKey que você adicionou na etapa 4.
    – Na terceira caixa, digite ou cole a URL do serviço de aplicativo do Azure; por exemplo **https://fbconnector.azurewebsites.net**.
 
    Depois que o conector for validado com êxito, clique em **Avançar**.
    
    ![](media/FBCimage47.png)

4.  Clique em **login com o aplicativo do conector**.

    ![](media/FBCimage45.png)

5. Digite ou cole o APISecretKey novamente e, em seguida, clique em **login to Connector Service**.

   ![](media/FBCimage48.png)


6. Clique em **login com o Facebook.**

   ![](media/FBCimage49.png)

7. Na página **fazer logon no Facebook** , faça o login usando as credenciais da conta das páginas de negócios de Facebook da sua organização. Certifique-se de que a conta do Facebook na qual você está conectado tenha a função de administrador para as páginas de negócios de Facebook da sua organização

   ![](media/FBCimage50.png)

8. Clique em **selecionar páginas** para escolher as páginas comerciais da sua organização que você deseja arquivar no Office 365.

   ![](media/FBCimage51.png)

9. É exibida uma lista das páginas de negócios gerenciadas pela conta do Facebook que você fez logon. Selecione a página para arquivar e clique em **salvar**.

    ![](media/FBCimage52.png)

10. Clique em **preparar** para sair da configuração do aplicativo de serviço do conector.

    ![](media/FBCimage53.png)

11. Na página **definir filtros** , você pode aplicar um filtro para importar (e arquivar) itens que são uma determinada idade. Clique em **Avançar**.

    ![](media/FBCimage54.png)

12. Na página **definir conta de armazenamento** , selecione a caixa de correio do Office 365 que os itens das páginas de negócios do Facebook que você selecionou anteriormente serão importados.

    ![](media/FBCimage55.png)

13. Revise suas configurações e clique em **concluir** para concluir a configuração do conector no centro de conformidade do & de segurança.

    ![](media/FBCimage56.png)

14. Vá para a página **arquivar dados** de terceiros para ver o andamento do processo de importação.

    ![](media/FBCimage58.png)
