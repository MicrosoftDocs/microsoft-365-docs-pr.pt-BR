---
title: Habilitar o suplemento de Mensagem de Relatório
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Saiba como habilitar o suplemento de mensagem de relatório para o Outlook e o Outlook na Web, para usuários individuais ou para toda a organização.
ms.openlocfilehash: c160e928c9a46dd4dc360c5e61d70ca401430378
ms.sourcegitcommit: a86787b62cec95a392ff2b933f5dc44334ceb7e9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2020
ms.locfileid: "43061717"
---
# <a name="enable-the-report-message-add-in-in-office-365"></a><span data-ttu-id="11add-103">Habilitar o suplemento de mensagem de relatório no Office 365</span><span class="sxs-lookup"><span data-stu-id="11add-103">Enable the Report Message add-in in Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="11add-104">Se você for um administrador em uma organização do Office 365 com caixas de correio do Exchange Online, recomendamos que você use o portal de envios no centro de conformidade & segurança do Office 365.</span><span class="sxs-lookup"><span data-stu-id="11add-104">If you're an admin in an Office 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="11add-105">Para obter mais informações, consulte [usar o envio do administrador para enviar spam, phishing, URLs e arquivos suspeitos à Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="11add-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="11add-106">O suplemento de mensagem de relatório para o Outlook e o Outlook na Web (anteriormente conhecido como Outlook Web App) permite que as pessoas relatem facilmente falsos positivos (emails satisfatórios marcados como defeituosos) ou falsos negativos (emails inválidos permitidos) para a Microsoft e seus afiliados para análise.</span><span class="sxs-lookup"><span data-stu-id="11add-106">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="11add-107">A Microsoft usa esses envios para melhorar a eficácia das tecnologias de proteção de email.</span><span class="sxs-lookup"><span data-stu-id="11add-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span>

<span data-ttu-id="11add-108">Por exemplo, suponha que as pessoas estejam relatando muitas mensagens como phishing.</span><span class="sxs-lookup"><span data-stu-id="11add-108">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="11add-109">Essas informações são superfícies no [painel de segurança](security-dashboard.md) e em outros relatórios.</span><span class="sxs-lookup"><span data-stu-id="11add-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="11add-110">A equipe de segurança da sua organização pode usar essas informações como indicação de que as políticas anti-phishing podem precisar ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="11add-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="11add-111">Ou, se as pessoas estiverem relatando muitas mensagens que foram sinalizadas como lixo eletrônico como não sendo lixo eletrônico usando o suplemento de mensagem de relatório, a equipe de segurança da sua organização poderá precisar ajustar [políticas antispam](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="11add-111">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="11add-112">Além disso, se sua organização estiver usando o [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) ou o [plano 2](office-365-ti.md), o suplemento de mensagem de relatório fornecerá a equipe de segurança da sua organização com informações úteis que podem ser usadas para analisar e atualizar as políticas de segurança.</span><span class="sxs-lookup"><span data-stu-id="11add-112">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="11add-113">Os administradores podem habilitar o suplemento de mensagem de relatório para a organização, e os usuários individuais podem instalá-lo para si mesmos.</span><span class="sxs-lookup"><span data-stu-id="11add-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="11add-114">Se você for um usuário individual, é possível [habilitar o relatório de suplemento de mensagens para você](#get-the-report-message-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="11add-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="11add-115">Se você for um administrador global do Office 365 ou um administrador do Exchange Online e o Exchange estiver configurado para usar a autenticação OAuth, você poderá [habilitar o suplemento de mensagem de relatório para sua organização](#get-and-enable-the-report-message-add-in-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="11add-115">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="11add-116">O suplemento de mensagem de relatório agora está disponível por meio da [implantação centralizada](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="11add-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="11add-117">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="11add-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="11add-118">O suplemento de mensagem de relatório funciona com a maioria das assinaturas do Office 365 e os seguintes produtos:</span><span class="sxs-lookup"><span data-stu-id="11add-118">The Report Message add-in works with most Office 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="11add-119">Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="11add-119">Outlook on the web</span></span>
  - <span data-ttu-id="11add-120">Outlook 2013 SP1 ou posterior</span><span class="sxs-lookup"><span data-stu-id="11add-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="11add-121">Outlook 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="11add-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="11add-122">Outlook incluído no Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="11add-122">Outlook included with Office 365 ProPlus</span></span>

- <span data-ttu-id="11add-123">O suplemento de mensagem de relatório atualmente não está disponível para:</span><span class="sxs-lookup"><span data-stu-id="11add-123">The Report Message add-in is currently not available for:</span></span>

  - <span data-ttu-id="11add-124">Caixas de correio em organizações do Exchange local</span><span class="sxs-lookup"><span data-stu-id="11add-124">Mailboxes in on-premises Exchange organizations</span></span>
  - <span data-ttu-id="11add-125">Assinaturas GCC, GCC alta ou DoD</span><span class="sxs-lookup"><span data-stu-id="11add-125">GCC, GCC HIGH, or DoD subscriptions</span></span>

- <span data-ttu-id="11add-126">O navegador da Web existente deverá funcionar com o suplemento de mensagem de relatório.</span><span class="sxs-lookup"><span data-stu-id="11add-126">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="11add-127">Mas, se você notar que o suplemento não está disponível ou não está funcionando conforme o esperado, tente um navegador diferente.</span><span class="sxs-lookup"><span data-stu-id="11add-127">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="11add-128">Para instalações organizacionais, a organização precisa ser configurada para usar a autenticação OAuth.</span><span class="sxs-lookup"><span data-stu-id="11add-128">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="11add-129">Confira mais informações em [determinar se a implantação centralizada de suplementos funciona para sua organização](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="11add-129">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="11add-130">Os administradores precisam ser membros do grupo de funções administradores globais.</span><span class="sxs-lookup"><span data-stu-id="11add-130">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="11add-131">Para obter mais informações, consulte [permissões no centro de conformidade & segurança do Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="11add-131">For more information, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="11add-132">Obter o suplemento de mensagem de relatório para você mesmo</span><span class="sxs-lookup"><span data-stu-id="11add-132">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="11add-133">Vá para o Microsoft AppSource em <https://appsource.microsoft.com/marketplace/apps> e procure o suplemento de mensagem de relatório.</span><span class="sxs-lookup"><span data-stu-id="11add-133">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="11add-134">Para ir diretamente para o suplemento de mensagem de relatório, acesse <https://appsource.microsoft.com/product/office/wa104381180>.</span><span class="sxs-lookup"><span data-stu-id="11add-134">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="11add-135">Clique em **obter agora**.</span><span class="sxs-lookup"><span data-stu-id="11add-135">Click **GET IT NOW**.</span></span>

   ![Mensagem de relatório-obter agora](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="11add-137">Na caixa de diálogo exibida, revise os termos de uso e política de privacidade e clique em **continuar**.</span><span class="sxs-lookup"><span data-stu-id="11add-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="11add-138">Entre no Office 365 usando sua conta corporativa ou de estudante (para uso comercial) ou sua conta da Microsoft (para uso pessoal).</span><span class="sxs-lookup"><span data-stu-id="11add-138">Sign in to Office 365 using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="11add-139">Depois que o suplemento estiver instalado e habilitado, você verá os seguintes ícones:</span><span class="sxs-lookup"><span data-stu-id="11add-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="11add-140">No Outlook, o ícone tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="11add-140">In Outlook, the icon looks like this:</span></span>

  ![Ícone de suplemento de mensagem de relatório para Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="11add-142">No Outlook na Web, o ícone tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="11add-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Ícone de suplemento da mensagem de relatório da Web do Outlook](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="11add-144">Para saber como usar o suplemento, confira [usar o suplemento de mensagem de relatório](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="11add-144">To learn how to use the add-in, see [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="11add-145">Obter e habilitar o suplemento de mensagem de relatório para sua organização</span><span class="sxs-lookup"><span data-stu-id="11add-145">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="11add-146">Pode levar até 12 horas para que o suplemento apareça em sua organização.</span><span class="sxs-lookup"><span data-stu-id="11add-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="11add-147">No centro de administração do Microsoft 365, vá para a página <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> **Serviços & suplementos** e clique em **implantar suplemento**.</span><span class="sxs-lookup"><span data-stu-id="11add-147">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>, and then click **Deploy Add-In**.</span></span>

   ![Página serviços e suplementos no centro de administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="11add-149">No submenu **implantar um novo suplemento** que aparece, revise as informações e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="11add-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="11add-150">Na próxima página, clique em **escolher na loja**.</span><span class="sxs-lookup"><span data-stu-id="11add-150">On the next page, click **Choose from the Store**.</span></span>

   ![Implantar uma nova página de suplemento](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="11add-152">Na página **selecionar suplemento** que aparece, clique na caixa de **pesquisa** , insira uma mensagem de **relatório**e clique em ícone](../../media/search-icon.png)de pesquisa de **pesquisa** ![.</span><span class="sxs-lookup"><span data-stu-id="11add-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="11add-153">Na lista de resultados, encontre **mensagem de relatório** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="11add-153">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Selecionar resultados de pesquisa de suplemento](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="11add-155">Na caixa de diálogo exibida, revise as informações de licenciamento e privacidade e clique em **continuar**.</span><span class="sxs-lookup"><span data-stu-id="11add-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="11add-156">Na página **Configurar Suplemento** exibida, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="11add-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="11add-157">**Usuários atribuídos**: selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="11add-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="11add-158">**Todos** (padrão)</span><span class="sxs-lookup"><span data-stu-id="11add-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="11add-159">**Usuários/grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="11add-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="11add-160">**Só eu**</span><span class="sxs-lookup"><span data-stu-id="11add-160">**Just me**</span></span>

   - <span data-ttu-id="11add-161">**Método de implantação**: selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="11add-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="11add-162">**Fixo (padrão)**: o suplemento é implantado automaticamente para os usuários especificados, e eles não podem removê-lo.</span><span class="sxs-lookup"><span data-stu-id="11add-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="11add-163">**Disponível**: os usuários podem instalar o suplemento em **casa** \> **Get de suplementos** \> do **administrador**.</span><span class="sxs-lookup"><span data-stu-id="11add-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="11add-164">**Opcional**: o suplemento é implantado automaticamente para os usuários especificados, mas eles podem optar por removê-lo.</span><span class="sxs-lookup"><span data-stu-id="11add-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Configurar página de suplemento](../../media/configure-add-in.png)

   <span data-ttu-id="11add-166">Quando tiver concluído, clique em **implantar**.</span><span class="sxs-lookup"><span data-stu-id="11add-166">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="11add-167">Na página **implantar mensagem de relatório** que aparece, você verá um relatório de progresso seguido de uma confirmação de que o suplemento foi implantado.</span><span class="sxs-lookup"><span data-stu-id="11add-167">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="11add-168">Depois de ler as informações, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="11add-168">After you read the information, click **Next**.</span></span>

   ![Página implantar mensagem de relatório](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="11add-170">Na página **anunciar suplemento** que aparece, revise as informações e, em seguida, clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="11add-170">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Anunciar página de suplemento](../../media/announce-add-in-page.png)

### <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="11add-172">Saiba como usar o suplemento de mensagem de relatório</span><span class="sxs-lookup"><span data-stu-id="11add-172">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="11add-173">Pessoas que têm o suplemento atribuído a eles verão os seguintes ícones:</span><span class="sxs-lookup"><span data-stu-id="11add-173">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="11add-174">No Outlook, o ícone tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="11add-174">In Outlook, the icon looks like this:</span></span>

  ![Ícone de suplemento de mensagem de relatório para Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="11add-176">No Outlook na Web, o ícone tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="11add-176">In Outlook on the web, the icon looks like this:</span></span>

  ![Ícone de suplemento da mensagem de relatório da Web do Outlook](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="11add-178">Ao notificar os usuários sobre o suplemento de mensagens de relatório, inclua um link para [usar o suplemento de mensagem de relatório](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="11add-178">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

### <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="11add-179">Revise ou edite as configurações do suplemento de mensagem de relatório</span><span class="sxs-lookup"><span data-stu-id="11add-179">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="11add-180">No centro de administração do Microsoft 365, acesse a página de **suplementos de &** de <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>serviços em.</span><span class="sxs-lookup"><span data-stu-id="11add-180">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![Página serviços e suplementos no novo centro de administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="11add-182">Localize e selecione o suplemento de **mensagem de relatório** .</span><span class="sxs-lookup"><span data-stu-id="11add-182">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="11add-183">No submenu **Editar mensagem de relatório** que aparece, revise e edite as configurações conforme apropriado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="11add-183">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="11add-184">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="11add-184">When you're finished, click **Save**.</span></span>

   ![Configurações para o suplemento de mensagem de relatório](../../media/EditReportMessageAddIn.png)
