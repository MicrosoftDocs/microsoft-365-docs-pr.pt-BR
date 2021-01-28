---
title: Habilitar o relatório de phishing add-in
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Saiba como habilitar o complemento Phishing de Relatório para o Outlook e o Outlook na Web, para usuários individuais ou para toda a organização.
ms.openlocfilehash: 6d86fdc710539bc3c74eb94f8931ca48a0c992c1
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029133"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="f6c71-103">Habilite o suplemento Relatório de Phishing</span><span class="sxs-lookup"><span data-stu-id="f6c71-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="f6c71-104">Se você for um administrador em uma organização do Microsoft 365 com caixas de correio do Exchange Online, recomendamos usar o portal Envios no Centro de Conformidade e Segurança & Segurança.</span><span class="sxs-lookup"><span data-stu-id="f6c71-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f6c71-105">Para obter mais informações, consulte Usar o Envio de Administrador para [enviar spam, phishing, URLs e arquivos suspeitos para a Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f6c71-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="f6c71-106">Os complementos De Relatório de Mensagem e Phishing para Outlook e Outlook na Web (anteriormente conhecido como Outlook Web App) permitem que as pessoas reportem facilmente falsos positivos (emails válidos marcados como ruins) ou falsos negativos (emails ruins permitidos) para a Microsoft e suas afiliadas para análise.</span><span class="sxs-lookup"><span data-stu-id="f6c71-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="f6c71-107">A Microsoft usa esses envios para melhorar a eficácia das tecnologias de proteção de email.</span><span class="sxs-lookup"><span data-stu-id="f6c71-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="f6c71-108">Por exemplo, suponha que as pessoas estão relatando muitas mensagens usando o complemento Phishing de Relatório.</span><span class="sxs-lookup"><span data-stu-id="f6c71-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="f6c71-109">Essas informações são fornecidas no Painel [de Segurança e](security-dashboard.md) em outros relatórios.</span><span class="sxs-lookup"><span data-stu-id="f6c71-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="f6c71-110">A equipe de segurança da sua organização pode usar essas informações como uma indicação de que as políticas anti-phishing talvez precisem ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="f6c71-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="f6c71-111">Você pode instalar o complemento Mensagem de Relatório ou Phishing de Relatório.</span><span class="sxs-lookup"><span data-stu-id="f6c71-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="f6c71-112">Se você quiser que os usuários reportem mensagens de spam e phishing, implante o complemento Mensagem de Relatório em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f6c71-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="f6c71-113">Para obter mais informações, [consulte Habilitar o complemento Mensagem de Relatório.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="f6c71-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="f6c71-114">O complemento De Relatório de Phishing oferece a opção de relatar apenas mensagens de phishing.</span><span class="sxs-lookup"><span data-stu-id="f6c71-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="f6c71-115">Os administradores podem habilitar o complemento Phishing de Relatório para a organização, e usuários individuais podem instalá-lo por conta própria.</span><span class="sxs-lookup"><span data-stu-id="f6c71-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="f6c71-116">Se você for um usuário individual, poderá habilitar o complemento [Phishing de Relatório para si mesmo.](#get-the-report-phishing-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="f6c71-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="f6c71-117">Se você for um administrador global ou um administrador do Exchange Online e o Exchange estiver configurado para usar a autenticação OAuth, você poderá habilitar o complemento Phishing de Relatório para [sua organização.](#get-and-enable-the-report-phishing-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="f6c71-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="f6c71-118">O relatório de Add-In phishing agora está disponível por meio [da Implantação Centralizada.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="f6c71-118">The Report Phishing Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f6c71-119">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="f6c71-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f6c71-120">O complemento De Phishing de Relatório funciona com a maioria das assinaturas do Microsoft 365 e os seguintes produtos:</span><span class="sxs-lookup"><span data-stu-id="f6c71-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="f6c71-121">Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="f6c71-121">Outlook on the web</span></span>
  - <span data-ttu-id="f6c71-122">Outlook 2013 SP1 ou posterior</span><span class="sxs-lookup"><span data-stu-id="f6c71-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="f6c71-123">Outlook 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="f6c71-123">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="f6c71-124">Outlook incluído nos aplicativos do Microsoft 365 para Empresas</span><span class="sxs-lookup"><span data-stu-id="f6c71-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="f6c71-125">O complemento De Phishing de Relatório não está disponível para caixas de correio em organizações locais do Exchange.</span><span class="sxs-lookup"><span data-stu-id="f6c71-125">The Report Phishing add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="f6c71-126">Você pode configurar mensagens relatadas para serem copiadas ou redirecionadas para uma caixa de correio que você especificar.</span><span class="sxs-lookup"><span data-stu-id="f6c71-126">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="f6c71-127">Para obter mais informações, consulte [Políticas de envios de usuário.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f6c71-127">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="f6c71-128">Seu navegador da Web existente deve funcionar com o complemento Phishing de Relatório.</span><span class="sxs-lookup"><span data-stu-id="f6c71-128">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="f6c71-129">Porém, se você perceber que o complemento não está disponível ou não está funcionando conforme o esperado, tente outro navegador.</span><span class="sxs-lookup"><span data-stu-id="f6c71-129">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="f6c71-130">Para as instalações organizacionais, a organização precisa ser configurada para usar a autenticação OAuth.</span><span class="sxs-lookup"><span data-stu-id="f6c71-130">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="f6c71-131">Para obter mais informações, [consulte Determinar se a Implantação Centralizada de complementos funciona para sua organização.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="f6c71-131">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="f6c71-132">Os administradores precisam ser membros do grupo de funções Administradores globais.</span><span class="sxs-lookup"><span data-stu-id="f6c71-132">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="f6c71-133">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f6c71-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="f6c71-134">Obter o add-in de Phishing de relatório por si mesmo</span><span class="sxs-lookup"><span data-stu-id="f6c71-134">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="f6c71-135">Vá para o Microsoft AppSource em <https://appsource.microsoft.com/marketplace/apps> e pesquise o complemento Phishing de relatório.</span><span class="sxs-lookup"><span data-stu-id="f6c71-135">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="f6c71-136">Clique **EM OBTER AGORA.**</span><span class="sxs-lookup"><span data-stu-id="f6c71-136">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="f6c71-137">Na caixa de diálogo exibida, revise os termos de uso e a política de privacidade e clique em **Continuar.**</span><span class="sxs-lookup"><span data-stu-id="f6c71-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="f6c71-138">Entre usando sua conta comercial ou de estudante (para uso comercial) ou sua conta da Microsoft (para uso pessoal).</span><span class="sxs-lookup"><span data-stu-id="f6c71-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="f6c71-139">Depois que o complemento for instalado e habilitado, você verá os seguintes ícones:</span><span class="sxs-lookup"><span data-stu-id="f6c71-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="f6c71-140">No Outlook, o ícone tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="f6c71-140">In Outlook, the icon looks like this:</span></span>

  ![Ícone de relatório de add-in de phishing para Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="f6c71-142">No Outlook na Web, o ícone tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="f6c71-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Ícone de complemento de phishing de relatório do Outlook na Web](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="f6c71-144">Obter e habilitar o add-in de Phishing de Relatório para sua organização</span><span class="sxs-lookup"><span data-stu-id="f6c71-144">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="f6c71-145">Pode levar até 12 horas para que o complemento apareça em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f6c71-145">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="f6c71-146">No Centro de administração do Microsoft 365, vá para a página Configurações de  \> **Add-ins** em , Se você não vir a Página de Complementos, vá para o link Configurações Integradas de <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>  Aplicativos, na parte superior da página **Aplicativos integrados.** \>  \>  </span><span class="sxs-lookup"><span data-stu-id="f6c71-146">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="f6c71-147">Selecione **Implantar o add-in** na parte superior da página e, em seguida, **selecione Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f6c71-147">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Página de serviços e complementos no centro de administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="f6c71-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="f6c71-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="f6c71-150">Na próxima página, clique **em Escolher na Loja.**</span><span class="sxs-lookup"><span data-stu-id="f6c71-150">On the next page, click **Choose from the Store**.</span></span>

   ![Implantar uma nova página de complemento](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="f6c71-152">Na página Selecionar **add-in** exibida,  clique na caixa Pesquisar, insira  **Phishing** de Relatório e clique no ícone ![ ](../../media/search-icon.png) Pesquisar.</span><span class="sxs-lookup"><span data-stu-id="f6c71-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="f6c71-153">Na lista de resultados, encontre **Phishing de Relatório** e clique em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="f6c71-153">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="f6c71-154">Na caixa de diálogo exibida, revise as informações de licenciamento e privacidade e clique em **Continuar.**</span><span class="sxs-lookup"><span data-stu-id="f6c71-154">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="f6c71-155">Na página **Configurar o complemento** exibida, de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="f6c71-155">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f6c71-156">**Usuários atribuídos:** selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f6c71-156">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="f6c71-157">**Todos** (padrão)</span><span class="sxs-lookup"><span data-stu-id="f6c71-157">**Everyone** (default)</span></span>
     - <span data-ttu-id="f6c71-158">**Usuários/grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="f6c71-158">**Specific users / groups**</span></span>
     - <span data-ttu-id="f6c71-159">**Somente eu**</span><span class="sxs-lookup"><span data-stu-id="f6c71-159">**Just me**</span></span>

   - <span data-ttu-id="f6c71-160">**Método de** implantação: selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f6c71-160">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="f6c71-161">**Corrigido (padrão)**: o complemento é implantado automaticamente para os usuários especificados e não pode removê-lo.</span><span class="sxs-lookup"><span data-stu-id="f6c71-161">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="f6c71-162">**Disponível:** os usuários podem instalar o add-in em **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="f6c71-162">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="f6c71-163">**Opcional**: o complemento é implantado automaticamente para os usuários especificados, mas eles podem optar por removê-lo.</span><span class="sxs-lookup"><span data-stu-id="f6c71-163">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="f6c71-164">Quando terminar, clique em **Implantar.**</span><span class="sxs-lookup"><span data-stu-id="f6c71-164">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="f6c71-165">Na página **Implantar Phishing** de Relatório exibida, você verá um relatório de progresso seguido de uma confirmação de que o complemento foi implantado.</span><span class="sxs-lookup"><span data-stu-id="f6c71-165">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="f6c71-166">Depois de ler as informações, clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="f6c71-166">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="f6c71-167">Na página **Anunciar o complemento** que aparece, revise as informações e clique em **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="f6c71-167">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="f6c71-168">Saiba como usar o complemento Phishing de Relatório</span><span class="sxs-lookup"><span data-stu-id="f6c71-168">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="f6c71-169">As pessoas que têm o complemento atribuído a elas verão os seguintes ícones:</span><span class="sxs-lookup"><span data-stu-id="f6c71-169">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="f6c71-170">No Outlook, o ícone tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="f6c71-170">In Outlook, the icon looks like this:</span></span>

  ![Ícone de relatório de add-in de phishing para Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="f6c71-172">No Outlook na Web, o ícone tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="f6c71-172">In Outlook on the web, the icon looks like this:</span></span>

  ![Ícone do Aplicativo de Phishing do Outlook na Web](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="f6c71-174">Revisar ou editar configurações para o add-in de Phishing de Relatório</span><span class="sxs-lookup"><span data-stu-id="f6c71-174">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="f6c71-175">No Centro de administração do Microsoft 365, vá para a página Configurações de  \> **Add-ins** em , Se você não vir a Página de Complementos, vá para o link Configurações Integradas de <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>  Aplicativos, na parte superior da página **Aplicativos integrados.** \>  \>  </span><span class="sxs-lookup"><span data-stu-id="f6c71-175">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="f6c71-176">Encontre e selecione o **add-in De Phishing** de Relatório.</span><span class="sxs-lookup"><span data-stu-id="f6c71-176">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="f6c71-177">No flyout **Editar Relatório de Phishing** que aparece, revise e edite as configurações conforme apropriado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="f6c71-177">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="f6c71-178">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f6c71-178">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="f6c71-179">Exibir e revisar mensagens relatadas</span><span class="sxs-lookup"><span data-stu-id="f6c71-179">View and review reported messages</span></span>

<span data-ttu-id="f6c71-180">Para revisar as mensagens que os usuários relatam à Microsoft, você tem estas opções:</span><span class="sxs-lookup"><span data-stu-id="f6c71-180">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="f6c71-181">Use o portal de Envios de Administrador.</span><span class="sxs-lookup"><span data-stu-id="f6c71-181">Use the Admin Submissions portal.</span></span> <span data-ttu-id="f6c71-182">Para obter mais informações, [consulte Exibir envios de usuário para a Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="f6c71-182">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="f6c71-183">Crie uma regra de fluxo de emails (também conhecida como regra de transporte) para enviar cópias das mensagens relatadas.</span><span class="sxs-lookup"><span data-stu-id="f6c71-183">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="f6c71-184">Para obter instruções, [confira Usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="f6c71-184">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>