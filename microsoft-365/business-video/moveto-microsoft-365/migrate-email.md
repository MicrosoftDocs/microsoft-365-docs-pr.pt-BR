---
title: Migrar email comercial e calendário do Google Workspace
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como migrar emails, contatos e calendário do Google Workspace para Microsoft 365 para empresas.
ms.openlocfilehash: d6639032b379a2cd632b6ab6ee7e4082b1e7be0b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913617"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>Migrar email comercial e calendário do Google Workspace

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

Você pode usar uma migração de administrador para Exchange Online do Google Workspace. Você pode migrar o email de uma só vez ou em estágios. As etapas a seguir mostram como migrar os dados de email de uma só vez. Para obter mais informações, [consulte Perform a G Suite migration](/exchange/mailbox-migration/perform-g-suite-migration).

O processo de migração toma várias etapas e pode levar de várias horas a alguns dias, dependendo da quantidade de dados que você está migrando.

## <a name="try-it"></a>Experimente!

### <a name="create-a-google-service-account"></a>Criar uma conta de serviço do Google

1. Usando um navegador Chrome, entre no console de administração do Google Workspace [em](https://admin.google.com)admin.google.com . 
1. Em uma nova guia ou janela, navegue até a página [Contas de](https://console.developers.google.com/iam-admin/serviceaccounts) Serviço. 
1. Selecione **Criar projeto,** nomee o projeto e escolha **Criar**. 
1. Selecione **Criar conta de serviço,** insira um nome, escolha **Criar** **e,** em seguida, Feito . 
1. Abra o menu **Ações,** selecione **Editar** e anote a ID Exclusiva. Você precisará dessa ID posteriormente no processo. 
1. Abra a **seção Mostrar delegação em todo o** domínio. 
1. Selecione **Habilitar delegação em todo o** domínio do G Suite, insira um nome de produto para a tela de consentimento e escolha **Salvar**. 

    > [!NOTE]
> O nome do produto não é usado pelo processo de migração, mas é necessário para salvar na caixa de diálogo.     

1. Abra o menu **Ações** novamente e selecione **Criar chave**. 
1. Escolha **JSON,** em **seguida, Criar**. 

     A chave privada é salva na pasta de download em seu dispositivo.
 
1. Selecione **Fechar**. 

### <a name="enable-api-usage-for-the-project"></a>Habilitar o uso da API para o projeto

1. Navegue até [a página APIs](https://console.developers.google.com/apis/library). 
1. Na barra de pesquisa, insira API **do Gmail**.
1. Selecione-o e escolha **Habilitar**.
1. Repita esse processo para API de Calendário do Google e API de Contatos. 

### <a name="grant-access-to-the-service-account"></a>Conceder acesso à conta de serviço

1. Retorne ao console de administração do Google Workspace. 
1. Selecione **Segurança,** role para baixo e abra controles **de API**. 
1. Role para baixo e selecione **Gerenciar Delegação em todo o domínio.**
1. Selecione **Adicionar novo** e insira a ID do Cliente que você anotou anteriormente.
1. Em seguida, insira os escopos OAuth para APIs do Google. Elas estão disponíveis [no](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) aka.ms/GoogleWorkspaceMigration etapa 5 e são:

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. Escolha **Autorizar**. 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>Criar um sub-domínio para email que Microsoft 365

1. Retorne ao console de administração **do Google Workspace.**
1. Selecione **Domínios,** **Gerenciar domínios**, em seguida, **Adicionar um alias de domínio**. 
1. Insira um alias de domínio como `m365.contoso.com` .
1. Em seguida, **selecione Continuar e verificar a propriedade do domínio**. 

    A verificação de domínio geralmente leva apenas alguns minutos, mas pode levar até 48 horas.

1. Vá para o centro [de administração Microsoft 365.](https://admin.microsoft.com)
1. No centro **Microsoft 365 de** administração , na nav esquerda, selecione **Mostrar** tudo **,** Configurações , **Domínios** e, em seguida, **Adicionar domínio**. 
1. Insira o subdomínio criado anteriormente e selecione **Usar este domínio**. 
1. Para conectar o domínio, selecione **Continuar**. 
1. Role para baixo e anote os registros MX, CNAME e TXT. 
1. Retorne ao **console de administração do Google**.
1. Selecione **Domínios,** selecione **Gerenciar domínios,** **Verificar Detalhes** e, em seguida, Gerenciar **domínio**. 
1. Na nav esquerda, escolha **DNS** e role para baixo até **Registros de recursos personalizados.** 
1. Abra o menu suspenso tipo de registro e selecione **MX**, insira ou copie e copie e colar as informações de registro MX que você anotou anteriormente e escolha **Adicionar**. 
1. Repita o processo para o registro CNAME e o registro TXT. 

    Pode levar algum tempo para que essas alterações entre em vigor.  

1. Retorne para onde você foi deixado no Microsoft 365 **de administração** e selecione **Continuar**. 

Seu domínio agora está definido.  

### <a name="create-email-aliases-in-microsoft-365"></a>Criar aliases de email em Microsoft 365

Antes que a migração possa começar, você precisa criar aliases de email para seus usuários com o novo subdomínio. 

1. Para iniciar a próxima etapa, no assistente **Adicionar Domínios** no centro de administração Microsoft 365, selecione **Ir para Usuários ativos**. 
1. Selecione um usuário, em seguida, **Gerenciar nome de usuário e email**. 
1. Na lista **suspenso Domínios,** selecione o subdomínio que você criou anteriormente. 
1. Insira um nome de usuário, **selecione Adicionar**, **Salvar alterações** e feche a janela. 

    Repita esse processo para cada usuário. 

### <a name="start-the-migration-process"></a>Iniciar o processo de migração

Depois de terminar, você estará pronto para migrar. 

1. Na nav esquerda do centro de administração **Microsoft 365,** role para baixo até **Centros** de administração e selecione **Exchange**. 
1. Em **destinatários,** escolha **migração**, selecione **Novo,** **Migrar** para Exchange Online, escolha **Migração do G Suite** **e,** em seguida, Próximo . 
1. Crie um arquivo CSV com uma lista das caixas de correio que você deseja migrar. Certifique-se de que o arquivo siga este formato: 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      Para obter detalhes, [consulte aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac). 

1. Selecione **Escolher Arquivo**, navegue até o arquivo CSV, escolha-o, selecione **Abrir**, em **seguida, Próximo**. 
1. Verifique o endereço de email do administrador que você deseja usar para teste. 
1. Selecione **Escolher Arquivo**, navegue até o arquivo JSON que você criou anteriormente (geralmente na pasta Downloads em seu computador), escolha-o, selecione **Abrir**, em **seguida, Próximo**. 
1. Insira um nome no campo **Novo nome do lote de migração.**
1. Insira o subdomínio que você criou no campo Domínio de **entrega de** destino, selecione **Próximo** e, em **seguida, Novo**. 
1. Depois que as informações são salvas, selecione **OK**. 

    Agora você pode exibir o status da migração. 

1. Após algum tempo passar, dependendo de quantos usuários você está migrando, selecione **Atualizar**. 
1. Depois que o status for alterado para **Sincronizado,** selecione Concluir esse lote de **migração** e **Sim**. 
1. Depois que o processo for concluído, seu status será alterado para **Concluído**. 
1. Se quiser, selecione **Exibir detalhes** para obter mais informações sobre a migração. 
1. Selecione **Fechar**. 
1. Abra Outlook para verificar se todos os emails do Google Workspace foram migrados com êxito.
Você também pode repetir isso para itens de calendário e contatos.