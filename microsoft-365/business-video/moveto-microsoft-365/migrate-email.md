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
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="8a809-103">Migrar email e calendário comercial do Google Workspace</span><span class="sxs-lookup"><span data-stu-id="8a809-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="8a809-104">Você pode usar uma migração de administrador para o Exchange Online a partir do Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="8a809-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="8a809-105">Você pode migrar o email de uma só vez ou em estágios.</span><span class="sxs-lookup"><span data-stu-id="8a809-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="8a809-106">As etapas a seguir mostram como migrar os dados de email de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="8a809-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="8a809-107">Para obter mais informações, consulte [Executar uma migração do G Suite.](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration)</span><span class="sxs-lookup"><span data-stu-id="8a809-107">For more information, see [Perform a G Suite migration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="8a809-108">O processo de migração leva várias etapas e pode levar de várias horas a alguns dias, dependendo da quantidade de dados que você está migrando.</span><span class="sxs-lookup"><span data-stu-id="8a809-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="8a809-109">Experimente!</span><span class="sxs-lookup"><span data-stu-id="8a809-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="8a809-110">Criar uma conta de serviço do Google</span><span class="sxs-lookup"><span data-stu-id="8a809-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="8a809-111">Usando um navegador Chrome, entre no console de administração do Google Workspace [admin.google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="8a809-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="8a809-112">Em uma nova guia ou janela, navegue até a página [Contas de](https://console.developers.google.com/iam-admin/serviceaccounts) Serviço.</span><span class="sxs-lookup"><span data-stu-id="8a809-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="8a809-113">Selecione **Criar projeto**, nome do projeto e escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="8a809-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="8a809-114">Selecione **Criar conta de serviço,** insira um nome, escolha **Criar** e, em **seguida, Feito.**</span><span class="sxs-lookup"><span data-stu-id="8a809-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="8a809-115">Abra o menu **Ações,** selecione **Editar** e anote a ID exclusiva.</span><span class="sxs-lookup"><span data-stu-id="8a809-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="8a809-116">Você precisará dessa ID mais tarde no processo.</span><span class="sxs-lookup"><span data-stu-id="8a809-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="8a809-117">Abra a **seção Mostrar delegação em todo o** domínio.</span><span class="sxs-lookup"><span data-stu-id="8a809-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="8a809-118">Selecione **Habilitar Delegação em todo** o domínio do G Suite, insira um nome de produto para a tela de consentimento e escolha **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="8a809-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="8a809-119">O nome do produto não é usado pelo processo de migração, mas é necessário para salvar na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="8a809-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="8a809-120">Abra o menu **Ações** novamente e selecione **a tecla Criar.**</span><span class="sxs-lookup"><span data-stu-id="8a809-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="8a809-121">Choose **JSON**, then **Create**.</span><span class="sxs-lookup"><span data-stu-id="8a809-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="8a809-122">A chave privada é salva na pasta de download em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8a809-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="8a809-123">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="8a809-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="8a809-124">Habilitar o uso da API para o projeto</span><span class="sxs-lookup"><span data-stu-id="8a809-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="8a809-125">Navegue até a [página de APIs.](https://console.developers.google.com/apis/library)</span><span class="sxs-lookup"><span data-stu-id="8a809-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="8a809-126">Na barra de pesquisa, insira a **API do Gmail.**</span><span class="sxs-lookup"><span data-stu-id="8a809-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="8a809-127">Selecione-a e escolha **Habilitar.**</span><span class="sxs-lookup"><span data-stu-id="8a809-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="8a809-128">Repita esse processo para a API de Calendário do Google e a API de Contatos.</span><span class="sxs-lookup"><span data-stu-id="8a809-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="8a809-129">Conceder acesso à conta de serviço</span><span class="sxs-lookup"><span data-stu-id="8a809-129">Grant access to the service account</span></span>

1. <span data-ttu-id="8a809-130">Retorne ao Console de administração do Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="8a809-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="8a809-131">Selecione **Segurança,** role para baixo e abra os controles **de API.**</span><span class="sxs-lookup"><span data-stu-id="8a809-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="8a809-132">Role para baixo e selecione **Gerenciar Delegação em todo o Domínio.**</span><span class="sxs-lookup"><span data-stu-id="8a809-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="8a809-133">Selecione **Adicionar novo** e insira a ID do Cliente que você anotou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8a809-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="8a809-134">Em seguida, insira os escopos OAuth das APIs do Google.</span><span class="sxs-lookup"><span data-stu-id="8a809-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="8a809-135">Eles estão disponíveis [no](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) aka.ms/GoogleWorkspaceMigration etapa 5 e são:</span><span class="sxs-lookup"><span data-stu-id="8a809-135">These are available at [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="8a809-136">Escolha **Autorizar**.</span><span class="sxs-lookup"><span data-stu-id="8a809-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="8a809-137">Criar um sub-domínio para o email que vai para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8a809-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="8a809-138">Retorne ao **console de administração do Google Workspace.**</span><span class="sxs-lookup"><span data-stu-id="8a809-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="8a809-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span><span class="sxs-lookup"><span data-stu-id="8a809-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="8a809-140">Insira um alias de domínio como `m365.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="8a809-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="8a809-141">Em **seguida, selecione Continuar e verifique a propriedade do domínio.**</span><span class="sxs-lookup"><span data-stu-id="8a809-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="8a809-142">A verificação de domínio geralmente leva apenas alguns minutos, mas pode levar até 48 horas.</span><span class="sxs-lookup"><span data-stu-id="8a809-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="8a809-143">Vá para o [Centro de administração do Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="8a809-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="8a809-144">In the **Microsoft 365 admin center**, in the left nav, select Show **all**, **Settings**, **Domains,** and then **Add domain**.</span><span class="sxs-lookup"><span data-stu-id="8a809-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="8a809-145">Insira o subdomínio que você criou anteriormente e selecione **Usar este domínio.**</span><span class="sxs-lookup"><span data-stu-id="8a809-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="8a809-146">Para conectar o domínio, selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="8a809-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="8a809-147">Role para baixo e anote os registros MX, CNAME e registros TXT.</span><span class="sxs-lookup"><span data-stu-id="8a809-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="8a809-148">Retorne ao **Console de administração do Google.**</span><span class="sxs-lookup"><span data-stu-id="8a809-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="8a809-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, Manage **domain**.</span><span class="sxs-lookup"><span data-stu-id="8a809-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="8a809-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span><span class="sxs-lookup"><span data-stu-id="8a809-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="8a809-151">Abra o menu suspenso de tipo de registro e selecione **MX**, insira ou copie e colar as informações de registro MX que você anotou anteriormente e escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8a809-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="8a809-152">Repita o processo para o registro CNAME e o registro TXT.</span><span class="sxs-lookup"><span data-stu-id="8a809-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="8a809-153">Pode levar algum tempo para que essas alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="8a809-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="8a809-154">Volte para onde você saiu no Centro **de administração do Microsoft 365** e selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="8a809-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="8a809-155">Seu domínio agora está definido.</span><span class="sxs-lookup"><span data-stu-id="8a809-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="8a809-156">Criar aliases de email no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8a809-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="8a809-157">Antes que a migração possa começar, você precisa criar aliases de email para seus usuários com o novo subdomínio.</span><span class="sxs-lookup"><span data-stu-id="8a809-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="8a809-158">Para iniciar a próxima etapa, no assistente **Adicionar Domínios** no centro de administração do Microsoft 365, selecione **Ir para Usuários ativos.**</span><span class="sxs-lookup"><span data-stu-id="8a809-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="8a809-159">Selecione um usuário e, em seguida, **Gerencie nome de usuário e email.**</span><span class="sxs-lookup"><span data-stu-id="8a809-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="8a809-160">No **menu suspenso Domínios,** selecione o subdomínio que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8a809-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="8a809-161">Insira um nome de usuário, **selecione Adicionar,** **Salvar alterações** e feche a janela.</span><span class="sxs-lookup"><span data-stu-id="8a809-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="8a809-162">Repita esse processo para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="8a809-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="8a809-163">Iniciar o processo de migração</span><span class="sxs-lookup"><span data-stu-id="8a809-163">Start the migration process</span></span>

<span data-ttu-id="8a809-164">Depois de terminar, você estará pronto para migrar.</span><span class="sxs-lookup"><span data-stu-id="8a809-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="8a809-165">In the left nav of the **Microsoft 365 admin center,** scroll down to **Admin centers**,and select **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="8a809-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="8a809-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose G **Suite migration**, and then **Next**.</span><span class="sxs-lookup"><span data-stu-id="8a809-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="8a809-167">Crie um arquivo CSV com uma lista das caixas de correio que você deseja migrar.</span><span class="sxs-lookup"><span data-stu-id="8a809-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="8a809-168">Certifique-se de que o arquivo segue este formato:</span><span class="sxs-lookup"><span data-stu-id="8a809-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="8a809-169">Para obter [detalhes, consulte aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span><span class="sxs-lookup"><span data-stu-id="8a809-169">For details see [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="8a809-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span><span class="sxs-lookup"><span data-stu-id="8a809-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="8a809-171">Verifique o endereço de email do administrador que você deseja usar para teste.</span><span class="sxs-lookup"><span data-stu-id="8a809-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="8a809-172">Selecione **Escolher Arquivo,** navegue até o arquivo JSON que você criou anteriormente (geralmente na pasta Downloads do seu computador), escolha-o, selecione **Abrir** e, em **seguida, Próximo**.</span><span class="sxs-lookup"><span data-stu-id="8a809-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="8a809-173">Insira um nome no campo Novo nome **do lote de migração.**</span><span class="sxs-lookup"><span data-stu-id="8a809-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="8a809-174">Insira o subdomínio que você criou no campo Domínio de entrega **de** destino, selecione **Próximo** e, em **seguida, Novo**.</span><span class="sxs-lookup"><span data-stu-id="8a809-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="8a809-175">Depois que as informações são salvas, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a809-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="8a809-176">Agora você pode exibir o status da sua migração.</span><span class="sxs-lookup"><span data-stu-id="8a809-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="8a809-177">Após algum tempo, dependendo de quantos usuários você está migrando, selecione **Atualizar.**</span><span class="sxs-lookup"><span data-stu-id="8a809-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="8a809-178">Depois que o status for alterado para **Sincronizado,** selecione Concluir este lote de **migração** e **Sim.**</span><span class="sxs-lookup"><span data-stu-id="8a809-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="8a809-179">Depois que o processo for concluído, seu status mudará para **Concluído.**</span><span class="sxs-lookup"><span data-stu-id="8a809-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="8a809-180">Se quiser, você pode selecionar **Exibir detalhes** para obter mais informações sobre a migração.</span><span class="sxs-lookup"><span data-stu-id="8a809-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="8a809-181">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="8a809-181">Select **Close**.</span></span> 
1. <span data-ttu-id="8a809-182">Abra o Outlook para verificar se todos os emails do Google Workspace foram migrados com êxito.</span><span class="sxs-lookup"><span data-stu-id="8a809-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="8a809-183">Você também pode repetir isso para itens de calendário e contatos.</span><span class="sxs-lookup"><span data-stu-id="8a809-183">You can repeat this for calendar items and contacts as well.</span></span>