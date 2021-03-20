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
description: Saiba como migrar emails, contatos e calendário do Google Workspace para o Microsoft 365 para empresas.
ms.openlocfilehash: d6639032b379a2cd632b6ab6ee7e4082b1e7be0b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913617"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="1a639-103">Migrar email comercial e calendário do Google Workspace</span><span class="sxs-lookup"><span data-stu-id="1a639-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="1a639-104">Você pode usar uma migração de administrador para o Exchange Online a partir do Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="1a639-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="1a639-105">Você pode migrar o email de uma só vez ou em estágios.</span><span class="sxs-lookup"><span data-stu-id="1a639-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="1a639-106">As etapas a seguir mostram como migrar os dados de email de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="1a639-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="1a639-107">Para obter mais informações, [consulte Perform a G Suite migration](/exchange/mailbox-migration/perform-g-suite-migration).</span><span class="sxs-lookup"><span data-stu-id="1a639-107">For more information, see [Perform a G Suite migration](/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="1a639-108">O processo de migração toma várias etapas e pode levar de várias horas a alguns dias, dependendo da quantidade de dados que você está migrando.</span><span class="sxs-lookup"><span data-stu-id="1a639-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="1a639-109">Experimente!</span><span class="sxs-lookup"><span data-stu-id="1a639-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="1a639-110">Criar uma conta de serviço do Google</span><span class="sxs-lookup"><span data-stu-id="1a639-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="1a639-111">Usando um navegador Chrome, entre no console de administração do Google Workspace [em](https://admin.google.com)admin.google.com .</span><span class="sxs-lookup"><span data-stu-id="1a639-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="1a639-112">Em uma nova guia ou janela, navegue até a página [Contas de](https://console.developers.google.com/iam-admin/serviceaccounts) Serviço.</span><span class="sxs-lookup"><span data-stu-id="1a639-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="1a639-113">Selecione **Criar projeto,** nomee o projeto e escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="1a639-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="1a639-114">Selecione **Criar conta de serviço,** insira um nome, escolha **Criar** **e,** em seguida, Feito .</span><span class="sxs-lookup"><span data-stu-id="1a639-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="1a639-115">Abra o menu **Ações,** selecione **Editar** e anote a ID Exclusiva.</span><span class="sxs-lookup"><span data-stu-id="1a639-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="1a639-116">Você precisará dessa ID posteriormente no processo.</span><span class="sxs-lookup"><span data-stu-id="1a639-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="1a639-117">Abra a **seção Mostrar delegação em todo o** domínio.</span><span class="sxs-lookup"><span data-stu-id="1a639-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="1a639-118">Selecione **Habilitar delegação em todo o** domínio do G Suite, insira um nome de produto para a tela de consentimento e escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1a639-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="1a639-119">O nome do produto não é usado pelo processo de migração, mas é necessário para salvar na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1a639-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="1a639-120">Abra o menu **Ações** novamente e selecione **Criar chave**.</span><span class="sxs-lookup"><span data-stu-id="1a639-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="1a639-121">Escolha **JSON,** em **seguida, Criar**.</span><span class="sxs-lookup"><span data-stu-id="1a639-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="1a639-122">A chave privada é salva na pasta de download em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1a639-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="1a639-123">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="1a639-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="1a639-124">Habilitar o uso da API para o projeto</span><span class="sxs-lookup"><span data-stu-id="1a639-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="1a639-125">Navegue até [a página APIs](https://console.developers.google.com/apis/library).</span><span class="sxs-lookup"><span data-stu-id="1a639-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="1a639-126">Na barra de pesquisa, insira API **do Gmail**.</span><span class="sxs-lookup"><span data-stu-id="1a639-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="1a639-127">Selecione-o e escolha **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="1a639-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="1a639-128">Repita esse processo para API de Calendário do Google e API de Contatos.</span><span class="sxs-lookup"><span data-stu-id="1a639-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="1a639-129">Conceder acesso à conta de serviço</span><span class="sxs-lookup"><span data-stu-id="1a639-129">Grant access to the service account</span></span>

1. <span data-ttu-id="1a639-130">Retorne ao console de administração do Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="1a639-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="1a639-131">Selecione **Segurança,** role para baixo e abra controles **de API**.</span><span class="sxs-lookup"><span data-stu-id="1a639-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="1a639-132">Role para baixo e selecione **Gerenciar Delegação em todo o domínio.**</span><span class="sxs-lookup"><span data-stu-id="1a639-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="1a639-133">Selecione **Adicionar novo** e insira a ID do Cliente que você anotou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1a639-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="1a639-134">Em seguida, insira os escopos OAuth para APIs do Google.</span><span class="sxs-lookup"><span data-stu-id="1a639-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="1a639-135">Elas estão disponíveis [no](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) aka.ms/GoogleWorkspaceMigration etapa 5 e são:</span><span class="sxs-lookup"><span data-stu-id="1a639-135">These are available at [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="1a639-136">Escolha **Autorizar**.</span><span class="sxs-lookup"><span data-stu-id="1a639-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="1a639-137">Criar um sub-domínio para emails que vão para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1a639-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="1a639-138">Retorne ao console de administração **do Google Workspace.**</span><span class="sxs-lookup"><span data-stu-id="1a639-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="1a639-139">Selecione **Domínios,** **Gerenciar domínios**, em seguida, **Adicionar um alias de domínio**.</span><span class="sxs-lookup"><span data-stu-id="1a639-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="1a639-140">Insira um alias de domínio como `m365.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="1a639-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="1a639-141">Em seguida, **selecione Continuar e verificar a propriedade do domínio**.</span><span class="sxs-lookup"><span data-stu-id="1a639-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="1a639-142">A verificação de domínio geralmente leva apenas alguns minutos, mas pode levar até 48 horas.</span><span class="sxs-lookup"><span data-stu-id="1a639-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="1a639-143">Vá para o Centro de administração [do Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="1a639-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="1a639-144">No Centro de administração do **Microsoft 365**, na nav esquerda, selecione **Mostrar tudo** **,** Configurações, **Domínios** e, em seguida, **Adicionar domínio**.</span><span class="sxs-lookup"><span data-stu-id="1a639-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="1a639-145">Insira o subdomínio criado anteriormente e selecione **Usar este domínio**.</span><span class="sxs-lookup"><span data-stu-id="1a639-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="1a639-146">Para conectar o domínio, selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="1a639-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="1a639-147">Role para baixo e anote os registros MX, CNAME e TXT.</span><span class="sxs-lookup"><span data-stu-id="1a639-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="1a639-148">Retorne ao **console de administração do Google**.</span><span class="sxs-lookup"><span data-stu-id="1a639-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="1a639-149">Selecione **Domínios,** selecione **Gerenciar domínios,** **Verificar Detalhes** e, em seguida, Gerenciar **domínio**.</span><span class="sxs-lookup"><span data-stu-id="1a639-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="1a639-150">Na nav esquerda, escolha **DNS** e role para baixo até **Registros de recursos personalizados.**</span><span class="sxs-lookup"><span data-stu-id="1a639-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="1a639-151">Abra o menu suspenso tipo de registro e selecione **MX**, insira ou copie e copie e colar as informações de registro MX que você anotou anteriormente e escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1a639-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="1a639-152">Repita o processo para o registro CNAME e o registro TXT.</span><span class="sxs-lookup"><span data-stu-id="1a639-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="1a639-153">Pode levar algum tempo para que essas alterações entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="1a639-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="1a639-154">Volte para onde você foi deixado no Centro de administração do **Microsoft 365** e selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="1a639-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="1a639-155">Seu domínio agora está definido.</span><span class="sxs-lookup"><span data-stu-id="1a639-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="1a639-156">Criar aliases de email no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1a639-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="1a639-157">Antes que a migração possa começar, você precisa criar aliases de email para seus usuários com o novo subdomínio.</span><span class="sxs-lookup"><span data-stu-id="1a639-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="1a639-158">Para iniciar a próxima etapa, no assistente **Adicionar Domínios** no Centro de administração do Microsoft 365, selecione **Ir para Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="1a639-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="1a639-159">Selecione um usuário, em seguida, **Gerenciar nome de usuário e email**.</span><span class="sxs-lookup"><span data-stu-id="1a639-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="1a639-160">Na lista **suspenso Domínios,** selecione o subdomínio que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1a639-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="1a639-161">Insira um nome de usuário, **selecione Adicionar**, **Salvar alterações** e feche a janela.</span><span class="sxs-lookup"><span data-stu-id="1a639-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="1a639-162">Repita esse processo para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="1a639-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="1a639-163">Iniciar o processo de migração</span><span class="sxs-lookup"><span data-stu-id="1a639-163">Start the migration process</span></span>

<span data-ttu-id="1a639-164">Depois de terminar, você estará pronto para migrar.</span><span class="sxs-lookup"><span data-stu-id="1a639-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="1a639-165">No nav esquerdo do Centro de administração do **Microsoft 365,** role para baixo até **Centros** de administração e selecione **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="1a639-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="1a639-166">Em **destinatários,** escolha **migração,** selecione **Novo,** Migrar para **o Exchange Online,** escolha **Migração do G Suite** **e,** em seguida, Próximo .</span><span class="sxs-lookup"><span data-stu-id="1a639-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="1a639-167">Crie um arquivo CSV com uma lista das caixas de correio que você deseja migrar.</span><span class="sxs-lookup"><span data-stu-id="1a639-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="1a639-168">Certifique-se de que o arquivo siga este formato:</span><span class="sxs-lookup"><span data-stu-id="1a639-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="1a639-169">Para obter detalhes, [consulte aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span><span class="sxs-lookup"><span data-stu-id="1a639-169">For details see [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="1a639-170">Selecione **Escolher Arquivo**, navegue até o arquivo CSV, escolha-o, selecione **Abrir**, em **seguida, Próximo**.</span><span class="sxs-lookup"><span data-stu-id="1a639-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="1a639-171">Verifique o endereço de email do administrador que você deseja usar para teste.</span><span class="sxs-lookup"><span data-stu-id="1a639-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="1a639-172">Selecione **Escolher Arquivo**, navegue até o arquivo JSON que você criou anteriormente (geralmente na pasta Downloads em seu computador), escolha-o, selecione **Abrir**, em **seguida, Próximo**.</span><span class="sxs-lookup"><span data-stu-id="1a639-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="1a639-173">Insira um nome no campo **Novo nome do lote de migração.**</span><span class="sxs-lookup"><span data-stu-id="1a639-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="1a639-174">Insira o subdomínio que você criou no campo Domínio de **entrega de** destino, selecione **Próximo** e, em **seguida, Novo**.</span><span class="sxs-lookup"><span data-stu-id="1a639-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="1a639-175">Depois que as informações são salvas, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a639-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="1a639-176">Agora você pode exibir o status da migração.</span><span class="sxs-lookup"><span data-stu-id="1a639-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="1a639-177">Após algum tempo passar, dependendo de quantos usuários você está migrando, selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="1a639-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="1a639-178">Depois que o status for alterado para **Sincronizado,** selecione Concluir esse lote de **migração** e **Sim**.</span><span class="sxs-lookup"><span data-stu-id="1a639-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="1a639-179">Depois que o processo for concluído, seu status será alterado para **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="1a639-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="1a639-180">Se quiser, selecione **Exibir detalhes** para obter mais informações sobre a migração.</span><span class="sxs-lookup"><span data-stu-id="1a639-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="1a639-181">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="1a639-181">Select **Close**.</span></span> 
1. <span data-ttu-id="1a639-182">Abra o Outlook para verificar se todos os emails do Google Workspace foram migrados com êxito.</span><span class="sxs-lookup"><span data-stu-id="1a639-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="1a639-183">Você também pode repetir isso para itens de calendário e contatos.</span><span class="sxs-lookup"><span data-stu-id="1a639-183">You can repeat this for calendar items and contacts as well.</span></span>