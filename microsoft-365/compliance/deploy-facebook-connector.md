---
title: Implantar um conector para arquivar dados de páginas do Facebook Business
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
description: Os administradores podem configurar um conector nativo para importar e arquivar páginas do Facebook Business para Microsoft 365. Depois que esses dados são importados para Microsoft 365, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar a governança dos dados do Facebook da sua organização.
ms.openlocfilehash: b771c50eb5c2eb5f99269f1f399d27043ebee6bb
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619947"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a>Implantar um conector para arquivar dados de páginas do Facebook Business

Este artigo contém o processo passo a passo para implantar um conector que usa o serviço Office 365 Import para importar dados de páginas do Facebook Business para Microsoft 365. Para uma visão geral de alto nível desse processo e uma lista de pré-requisitos necessários para implantar um conector do Facebook, consulte Configurar um conector para arquivar dados [do Facebook.](archive-facebook-data-with-sample-connector.md)

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Etapa 1: Criar um aplicativo no Azure Active Directory

1. Acesse e <https://portal.azure.com> entre usando as credenciais de uma conta de administrador global.

    ![Criar aplicativo no AAD](../media/FBCimage1.png)

2. No painel de navegação esquerdo, clique em **Azure Active Directory**.

    ![Clique Azure Active Directory](../media/FBCimage2.png)

3. No painel de navegação esquerdo, clique em **Registros de aplicativo (Visualização)** e clique em **Novo registro**.

    ![Clique em **Registros de aplicativo (Visualização)** e clique em **Novo registro**](../media/FBCimage3.png)

4. Registre o aplicativo. Em URI de redirecionamento, selecione Web na lista suspenso tipo de aplicativo e digite a <https://portal.azure.com> caixa para o URI.

   ![Registrar o aplicativo](../media/FBCimage4.png)

5. Copie a **ID do Aplicativo (cliente)** e a ID de Diretório **(locatário)** e salve-os em um arquivo de texto ou em outro local seguro. Use essas IDs em etapas posteriores.

   ![Copie a ID do Aplicativo e a ID do Diretório e salve-as](../media/FBCimage5.png)

6. Vá para **Certificados & segredos do novo aplicativo.**

   ![Vá para Certificados & segredos do novo aplicativo](../media/FBCimage6.png)

7. Clique **em Novo segredo do cliente**

   ![Clique em Novo segredo do cliente](../media/FBCimage7.png)

8. Crie um novo segredo. Na caixa descrição, digite o segredo e escolha um período de expiração.

    ![Digite o segredo e escolha um período de expiração](../media/FBCimage8.png)

9. Copie o valor do segredo e salve-o em um arquivo de texto ou em outro local de armazenamento. Este é o segredo do aplicativo AAD que você usa nas etapas posteriores.

   ![Copie o valor do segredo e salve-o](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Etapa 2: Implantar o serviço Web do conector GitHub sua conta do Azure

1. Vá para [este GitHub site e](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) clique em Implantar no **Azure**.

    ![Clique em Implantar no Azure](../media/FBCGithubApp.png)

2. Depois de clicar **em Implantar no Azure,** você será redirecionado para um portal do Azure com uma página de modelo personalizada. Preencha os **detalhes básicos** **e Configurações** e clique em **Comprar**.

   - **Assinatura:** Selecione sua assinatura do Azure para a que você deseja implantar o serviço Web do conector de páginas do Facebook Business.

   - **Grupo de recursos:** Escolha ou crie um novo grupo de recursos. Um grupo de recursos é um contêiner que contém recursos relacionados para uma solução do Azure.

   - **Local:** Escolha um local.

   - **Nome do aplicativo Web:** Forneça um nome exclusivo para o aplicativo Web do conector. O nome deve ter entre 3 e 18 caracteres de comprimento. Esse nome é usado para criar a URL do serviço de aplicativo do Azure; por exemplo, se você fornecer o nome do aplicativo Web **do fbconnector,** a URL do serviço de aplicativo do Azure **será** fbconnector.azurewebsites.net .

   - **tenantId:** A ID de locatário da sua Microsoft 365 que você copiou depois de criar o aplicativo conector do Facebook Azure Active Directory na Etapa 1.

   - **APISecretKey:** Você pode digitar qualquer valor como o segredo. Isso é usado para acessar o aplicativo Web do conector na Etapa 5.

     ![Clique em Criar um recurso e digite conta de armazenamento](../media/FBCimage12.png)

3. Depois que a implantação for bem-sucedida, a página será semelhante à seguinte captura de tela:

   ![Clique Armazenamento e clique em Armazenamento conta](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a>Etapa 3: Registrar o aplicativo do Facebook

1. Vá para , faça logoff usando as credenciais da conta para as páginas do Facebook Business da sua organização e clique <https://developers.facebook.com> em **Adicionar Novo Aplicativo.**

   ![Adicionar um novo aplicativo para a página de negócios do Facebook](../media/FBCimage25.png)

2. Crie uma nova ID de aplicativo.

   ![Criar uma nova ID de aplicativo](../media/FBCimage26.png)

3. No painel de navegação esquerdo, clique em **Adicionar Produtos** e clique **em Configurar** no painel Logon do **Facebook.**

   ![Clique em Adicionar Produtos](../media/FBCimage27.png)

4. Na página Integrar Logon do Facebook, clique em **Web**.

   ![Clique em Web na página Integrar Logon do Facebook](../media/FBCimage28.png)

5. Adicionar a URL do serviço de aplicativo do Azure; por exemplo `https://fbconnector.azurewebsites.net` .

   ![Adicionar a URL do serviço de aplicativo do Azure](../media/FBCimage29.png)

6. Conclua a seção Início Rápido da configuração de Logon do Facebook.

   ![Concluir a seção QuickStart](../media/FBCimage30.png)

7. No painel de navegação esquerdo em **Logon** do Facebook, clique em Configurações **e** adicione o URI de redirecionamento OAuth na caixa URIs de redirecionamento **OAuth** válidos. Use o formato **\<connectorserviceuri> /Views/FacebookOAuth**, onde o valor para connectorserviceuri é a URL de serviço de aplicativo do Azure para sua organização; por exemplo, `https://fbconnector.azurewebsites.net` .

   ![Adicionar o URI de redirecionamento OAuth à caixa URIs de redirecionamento OAuth válidos](../media/FBCimage31.png)

8. No painel de navegação esquerdo, clique em **Adicionar Produtos** e clique em **Webhooks.** No menu **pull-down** Página, clique em **Página**.

   ![Clique em Adicionar Produtos e clique em **Webhooks](../media/FBCimage32.png)

9. Adicione a URL de Retorno de Chamada de Webhooks e adicione um token de verificação. O formato da URL de retorno de chamada, use o formato **<connectorserviceuri> /api/FbPageWebhook**, onde o valor para connectorserviceuri é a URL de serviço de aplicativo do Azure para sua organização; por exemplo `https://fbconnector.azurewebsites.net` .

   O token de verificação deve ser semelhante a uma senha forte. Copie o token de verificação para um arquivo de texto ou outro local de armazenamento.

   ![Adicionar o token verify](../media/FBCimage33.png)

10. Teste e inscreva-se no ponto de extremidade para feed.

    ![Testar e inscrever-se no ponto de extremidade](../media/FBCimage34.png)

11. Adicione uma URL de privacidade, ícone de aplicativo e uso comercial. Além disso, copie a ID do aplicativo e o segredo do aplicativo para um arquivo de texto ou outro local de armazenamento.

    ![Adicionar uma URL de privacidade, ícone de aplicativo e uso comercial](../media/FBCimage35.png)

12. Tornar o aplicativo público.

    ![Tornar o aplicativo público](../media/FBCimage36.png)

13. Adicione o usuário à função de administrador ou testador.

    ![Adicionar usuário à função de administrador ou testador](../media/FBCimage37.png)

14. Adicione a **permissão Page Public Content Access.**

    ![dd a permissão Page Public Content Access](../media/FBCimage38.png)

15. Adicione a permissão Gerenciar Páginas.

    ![Adicionar permissão Gerenciar Páginas](../media/FBCimage39.png)

16. Obter o aplicativo revisado pelo Facebook.

    ![Obter o aplicativo revisado pelo Facebook](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a>Etapa 4: Configurar o aplicativo Web do conector

1. Vá para (onde AzureAppResourceName é o nome do seu recurso de aplicativo do Azure que você `https://<AzureAppResourceName>.azurewebsites.net` nomeou na Etapa 4). Por exemplo, se o nome for **fbconnector,** vá para `https://fbconnector.azurewebsites.net` . A home page do aplicativo terá a seguinte captura de tela:

   ![Vá até você conector do aplicativo Web](../media/FBCimage41.png)

2. Clique **em Configurar** para exibir uma página de login.

   ![Clique em Configurar para exibir uma página de login](../media/FBCimage42.png)

3. Na caixa ID do locatário, digite ou colar sua ID de locatário (obtida na Etapa 2). Na caixa senha, digite ou colar a APISecretKey (obtida na Etapa 2) e clique em Definir Configuração **Configurações** para exibir a página de detalhes de configuração.

    ![Entre usando sua ID de locatário e senha e vá para a página de detalhes de configuração](../media/FBCimage43.png)

4. Insira as seguintes configurações

   - **ID do aplicativo do Facebook:** A ID do aplicativo do Facebook obtida na Etapa 3.

   - **Segredo do aplicativo do Facebook:** O segredo do aplicativo do Facebook que você obteve na Etapa 3.

   - **Webhooks do Facebook verificam token:** O token de verificação criado na Etapa 3.

   - **ID do aplicativo AAD:** A ID do aplicativo para o Azure Active Directory que você criou na Etapa 1.

   - **Segredo do aplicativo AAD:** O valor do segredo APISecretKey criado na Etapa 1.

5. Clique **em Salvar** para salvar as configurações do conector.

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a>Etapa 5: Configurar um conector do Facebook no centro Microsoft 365 conformidade

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **Conectores de dados** na nav esquerda.

2. Na página **Conectores de dados** em **páginas do Facebook Business,** clique em **Exibir**.

3. Na página **Páginas comerciais do Facebook,** clique em **Adicionar conector**.

4. Na página **Termos de serviço,** clique em **Aceitar**.

5. Na página **Adicionar credenciais para seu** aplicativo do conector, insira as informações a seguir e clique em **Validar conexão**.

   ![Inserir credenciais de aplicativo de conector](../media/TCimage38.png)

   - Na caixa **Nome,** digite um nome para o conector, como a **página de notícias do Facebook.**

   - Na caixa **URL de conexão,** digite ou colar a URL do serviço de aplicativo do Azure; por exemplo `https://fbconnector.azurewebsites.net` .

   - Na caixa **Senha,** digite ou colar o valor da APISecretKey que você adicionou na Etapa 2.

   - Na caixa ID do Aplicativo **do Azure,** digite ou colar o valor da ID do Aplicativo (cliente) também chamada como ID do Aplicativo AAD que você criou na Etapa 1.

6. Depois que a conexão for validada com êxito, clique em **Next**.

7. Na página **Autorizar Microsoft 365 importar** dados, digite ou colar a APISecretKey novamente e clique em **Logon do aplicativo Web**.

8. Na página Configurar aplicativo do conector do **Facebook,** clique em **Logon** com o Facebook e faça logon usando as credenciais da conta para as páginas do Facebook Business da sua organização. Certifique-se de que a conta do Facebook à que você fez login tenha a função de administrador para as páginas do Facebook Business da sua organização.

   ![Faça logoff com o Facebook](../media/FBCimage50.png)

9. Uma lista das páginas de negócios gerenciadas pela conta do Facebook à que você fez logont é exibida. Selecione a página a ser arquivada e clique em **Próximo**.

   ![Selecione a página de negócios da organização que você deseja arquivar](../media/FBCimage52.png)

10. Clique **em Continuar** para sair da instalação do aplicativo de serviço do conector.

11. Na página **Definir filtros,** você pode aplicar um filtro para importar inicialmente itens que têm uma determinada idade. Selecione uma idade e clique em **Próximo**.

12. Na página **Escolher local de armazenamento,** digite o endereço de email Microsoft 365 caixa de correio para a qual os itens do Facebook serão importados e clique em **Próximo**.

13. Clique **em Próximo** para revisar as configurações do conector e clique em **Concluir** para concluir a configuração do conector.

14. No centro de conformidade, vá até a página **Conectores de** dados e clique na guia **Conectores** para ver o andamento do processo de importação.
