---
title: Migrar email e calendário comercial do Google Workspace
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como migrar emails, contatos e calendário do Google Workspace para o Microsoft 365 para empresas.
ms.openlocfilehash: cb751b1d2f18b226021bb6f218b62f3ae426f6a4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928241"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>Migrar email e calendário comercial do Google Workspace

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

Você pode usar uma migração gerenciada pelo administrador para o Exchange Online a partir do Google Workspace. Você pode migrar o email de uma só vez ou em estágios. As etapas a seguir mostram como migrar os dados de email de uma só vez. Para obter mais informações, consulte [Executar uma migração do G Suite.](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration)

O processo de migração leva várias etapas e pode levar de várias horas a alguns dias, dependendo da quantidade de dados que você está migrando.

## <a name="try-it"></a>Experimente!

### <a name="create-a-google-service-account"></a>Criar uma conta de serviço do Google

1. Usando um navegador Chrome, entre no console de administração do Google Workspace [admin.google.com.](https://admin.google.com) 
1. Em uma nova guia ou janela, navegue até a página [Contas de](https://console.developers.google.com/iam-admin/serviceaccounts) Serviço. 
1. Selecione **Criar projeto**, nome do projeto e escolha **Criar**. 
1. Selecione **Criar conta de serviço,** insira um nome, escolha **Criar** e, em **seguida, Feito.** 
1. Abra **o** menu Ações, selecione **Editar** e anote a ID exclusiva. Você precisará dessa ID mais tarde no processo. 
1. Abra a **seção Mostrar delegação em todo o** domínio. 
1. Selecione **Habilitar Delegação em todo** o domínio do G Suite, insira um nome de produto para a tela de consentimento e escolha **Salvar.** 

    > [!NOTE]
> O nome do produto não é usado pelo processo de migração, mas é necessário para salvar na caixa de diálogo.     

1. Abra o menu **Ações** novamente e selecione **a tecla Criar.** 
1. Choose **JSON**, then **Create**. 

     A chave privada é salva na pasta de download em seu dispositivo.
 
1. Selecione **Fechar**. 

### <a name="enable-api-usage-for-the-project"></a>Habilitar o uso da API para o projeto

1. Navegue até a [página de APIs.](https://console.developers.google.com/apis/library) 
1. Na barra de pesquisa, insira a **API do Gmail.**
1. Selecione-a e escolha **Habilitar.**
1. Repita esse processo para a API de Calendário do Google e a API de Contatos. 

### <a name="grant-access-to-the-service-account"></a>Conceder acesso à conta de serviço

1. Retorne ao Console de administração do Google Workspace. 
1. Selecione **Segurança,** role para baixo e abra os controles **de API.** 
1. Role para baixo e selecione **Gerenciar Delegação em todo o Domínio.**
1. Selecione **Adicionar novo** e insira a ID do Cliente que você anotou anteriormente.
1. Em seguida, insira os escopos OAuth das APIs do Google. Eles estão disponíveis no [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) etapa 5 e são:

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. Escolha **Autorizar**. 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>Criar um sub-domínio para emails que vão para o Microsoft 365

1. Retorne ao **Console de administração do Google Workspace.**
1. Select **Domains**, **Manage domains**, then, **Add a domain alias**. 
1. Insira um alias de domínio como `m365.contoso.com` .
1. Em **seguida, selecione Continuar e verifique a propriedade do domínio.** 

    A verificação de domínio geralmente leva apenas alguns minutos, mas pode levar até 48 horas.

1. Vá para o [Centro de administração do Microsoft 365.](https://admin.microsoft.com)
1. In the **Microsoft 365 admin center**, in the left nav, select Show **all**, **Settings**, **Domains,** and then **Add domain**. 
1. Insira o subdomínio que você criou anteriormente e selecione **Usar este domínio.** 
1. Para conectar o domínio, selecione **Continuar**. 
1. Role para baixo e anote os registros MX, CNAME e registros TXT. 
1. Retorne ao **Console de administração do Google.**
1. Select **Domains**, select **Manage domains**, **Verify Details** and then, Manage **domain**. 
1. In the left nav, choose **DNS** and scroll down to **Custom resource records**. 
1. Abra o menu suspenso de tipo de registro e selecione **MX**, insira ou copie e colar as informações de registro MX que você anotou anteriormente e escolha **Adicionar**. 
1. Repita o processo para o registro CNAME e o registro TXT. 

    Pode levar algum tempo para que essas alterações entrem em vigor.  

1. Volte para onde você saiu no Centro **de administração do Microsoft 365** e selecione **Continuar**. 

Seu domínio agora está definido.  

### <a name="create-email-aliases-in-microsoft-365"></a>Criar aliases de email no Microsoft 365

Antes que a migração possa começar, você precisa criar aliases de email para seus usuários com o novo subdomínio. 

1. Para iniciar a próxima etapa, no assistente **Adicionar Domínios** no centro de administração do Microsoft 365, selecione **Ir para Usuários ativos.** 
1. Selecione um usuário e, em seguida, **Gerencie nome de usuário e email.** 
1. No **menu suspenso Domínios,** selecione o subdomínio que você criou anteriormente. 
1. Insira um nome de usuário, **selecione Adicionar,** **Salvar alterações** e feche a janela. 

    Repita esse processo para cada usuário. 

### <a name="start-the-migration-process"></a>Iniciar o processo de migração

Depois de terminar, você estará pronto para migrar. 

1. In the left nav of the **Microsoft 365 admin center,** scroll down to **Admin centers**,and select **Exchange**. 
1. Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose G **Suite migration**, and then **Next**. 
1. Crie um arquivo CSV com uma lista das caixas de correio que você deseja migrar. Certifique-se de que o arquivo segue este formato: 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      Para obter [detalhes, consulte aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac). 

1. Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**. 
1. Verifique o endereço de email do administrador que você deseja usar para teste. 
1. Selecione **Escolher Arquivo,** navegue até o arquivo JSON que você criou anteriormente (geralmente na pasta Downloads do seu computador), escolha-o, selecione **Abrir** e, em **seguida, Próximo**. 
1. Insira um nome no campo Novo nome **do lote de migração.**
1. Insira o subdomínio que você criou no campo Domínio de entrega **de** destino, selecione **Próximo** e, em **seguida, Novo**. 
1. Depois que as informações são salvas, selecione **OK**. 

    Agora você pode exibir o status da sua migração. 

1. Após algum tempo, dependendo de quantos usuários você está migrando, selecione **Atualizar.** 
1. Depois que o status for alterado para **Sincronizado,** selecione Concluir este lote de **migração** e **Sim.** 
1. Depois que o processo for concluído, seu status mudará para **Concluído.** 
1. Se quiser, você pode selecionar **Exibir detalhes** para obter mais informações sobre a migração. 
1. Selecione **Fechar**. 
1. Abra o Outlook para verificar se todos os emails do Google Workspace foram migrados com êxito.
Você também pode repetir isso para itens de calendário e contatos.