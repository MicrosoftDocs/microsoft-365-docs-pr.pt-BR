---
title: Habilitar o suplemento de Mensagem de Relatório
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Saiba como habilitar o complemento Mensagem de Relatório para o Outlook e o Outlook na Web, para usuários individuais ou para toda a organização.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1f8cffaa6346ec7f426da3c862014ed85a9a367
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029227"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="55d11-103">Habilitar o suplemento de Mensagem de Relatório</span><span class="sxs-lookup"><span data-stu-id="55d11-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="55d11-104">Se você for um administrador em uma organização do Microsoft 365 com caixas de correio do Exchange Online, recomendamos usar o portal Envios no Centro de Conformidade e Segurança & Segurança.</span><span class="sxs-lookup"><span data-stu-id="55d11-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="55d11-105">Para obter mais informações, consulte Usar o Envio de Administrador [para enviar spam, phishing, URLs e arquivos suspeitos para a Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="55d11-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="55d11-106">Os complementos De Relatório de Mensagens e Phishing do Outlook e do Outlook na Web (anteriormente conhecido como Outlook Web App) permitem que as pessoas reportem facilmente falsos positivos (emails bons marcados como ruins) ou falsos negativos (emails ruins permitidos) para a Microsoft e suas afiliadas para análise.</span><span class="sxs-lookup"><span data-stu-id="55d11-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="55d11-107">A Microsoft usa esses envios para melhorar a eficácia das tecnologias de proteção de email.</span><span class="sxs-lookup"><span data-stu-id="55d11-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="55d11-108">Por exemplo, se as pessoas estão relatando muitas mensagens que foram sinalizadas como lixo eletrônico como Não é Lixo Eletrônico usando o complemento Mensagem de Relatório, a equipe de segurança da sua organização pode precisar ajustar as políticas [anti-spam.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="55d11-108">For example, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="55d11-109">Você pode instalar o complemento Mensagem de Relatório ou Phishing de Relatório.</span><span class="sxs-lookup"><span data-stu-id="55d11-109">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="55d11-110">Se você quiser que seus usuários reportem apenas mensagens de phishing, implante o complemento De relatório de phishing em sua organização.</span><span class="sxs-lookup"><span data-stu-id="55d11-110">If you want your users to report only phishing messages, deploy the Report Phishing add-in in your organization.</span></span> <span data-ttu-id="55d11-111">Para obter mais informações, [consulte Habilitar o complemento Phishing de Relatório.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="55d11-111">For more information, see [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="55d11-112">O complemento Mensagem de Relatório oferece a opção de relatar mensagens de spam e phishing.</span><span class="sxs-lookup"><span data-stu-id="55d11-112">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="55d11-113">Os administradores podem habilitar o complemento Mensagem de Relatório para a organização, e usuários individuais podem instalá-lo por conta própria.</span><span class="sxs-lookup"><span data-stu-id="55d11-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="55d11-114">Se você for um usuário individual, poderá habilitar o complemento Mensagem [de Relatório para si mesmo.](#get-the-report-message-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="55d11-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="55d11-115">Se você for um administrador global ou um administrador do Exchange Online e o Exchange estiver configurado para usar a autenticação OAuth, você poderá habilitar o complemento Mensagem de Relatório para [sua organização.](#get-and-enable-the-report-message-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="55d11-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="55d11-116">A mensagem de Add-In relatório agora está disponível por meio [da Implantação Centralizada.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="55d11-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="55d11-117">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="55d11-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="55d11-118">O complemento Mensagem de Relatório funciona com a maioria das assinaturas do Microsoft 365 e os seguintes produtos:</span><span class="sxs-lookup"><span data-stu-id="55d11-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="55d11-119">Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="55d11-119">Outlook on the web</span></span>
  - <span data-ttu-id="55d11-120">Outlook 2013 SP1 ou posterior</span><span class="sxs-lookup"><span data-stu-id="55d11-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="55d11-121">Outlook 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="55d11-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="55d11-122">Outlook incluído nos aplicativos do Microsoft 365 para Empresas</span><span class="sxs-lookup"><span data-stu-id="55d11-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="55d11-123">O complemento Mensagem de Relatório não está disponível para caixas de correio em organizações locais do Exchange.</span><span class="sxs-lookup"><span data-stu-id="55d11-123">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="55d11-124">Você pode configurar mensagens relatadas para serem copiadas ou redirecionadas para uma caixa de correio que você especificar.</span><span class="sxs-lookup"><span data-stu-id="55d11-124">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="55d11-125">Para obter mais informações, consulte [Políticas de envios de usuário.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="55d11-125">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="55d11-126">Seu navegador da Web existente deve funcionar com o complemento Mensagem de Relatório.</span><span class="sxs-lookup"><span data-stu-id="55d11-126">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="55d11-127">Porém, se você perceber que o complemento não está disponível ou não está funcionando conforme o esperado, tente outro navegador.</span><span class="sxs-lookup"><span data-stu-id="55d11-127">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="55d11-128">Para as instalações organizacionais, a organização precisa ser configurada para usar a autenticação OAuth.</span><span class="sxs-lookup"><span data-stu-id="55d11-128">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="55d11-129">Para obter mais informações, [consulte Determinar se a Implantação Centralizada de complementos funciona para sua organização.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="55d11-129">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="55d11-130">Os administradores precisam ser membros do grupo de funções Administradores globais.</span><span class="sxs-lookup"><span data-stu-id="55d11-130">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="55d11-131">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="55d11-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="55d11-132">Obter o complemento Mensagem de Relatório para você mesmo</span><span class="sxs-lookup"><span data-stu-id="55d11-132">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="55d11-133">Vá para o Microsoft AppSource em e procure o complemento <https://appsource.microsoft.com/marketplace/apps> Mensagem de Relatório.</span><span class="sxs-lookup"><span data-stu-id="55d11-133">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="55d11-134">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="55d11-134">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="55d11-135">Clique **em OBTER AGORA.**</span><span class="sxs-lookup"><span data-stu-id="55d11-135">Click **GET IT NOW**.</span></span>

   ![Mensagem de Relatório - Obter Agora](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="55d11-137">Na caixa de diálogo exibida, revise os termos de uso e a política de privacidade e clique em **Continuar.**</span><span class="sxs-lookup"><span data-stu-id="55d11-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="55d11-138">Entre usando sua conta comercial ou de estudante (para uso comercial) ou sua conta da Microsoft (para uso pessoal).</span><span class="sxs-lookup"><span data-stu-id="55d11-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="55d11-139">Depois que o complemento for instalado e habilitado, você verá os seguintes ícones:</span><span class="sxs-lookup"><span data-stu-id="55d11-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="55d11-140">No Outlook, o ícone tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="55d11-140">In Outlook, the icon looks like this:</span></span>

  ![Ícone de add-in de Mensagem de Relatório para Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="55d11-142">No Outlook na Web, o ícone tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="55d11-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Ícone de add-in Mensagem de Relatório do Outlook na Web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="55d11-144">Para saber como usar o complemento, confira Usar o [complemento Mensagem de Relatório.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="55d11-144">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="55d11-145">Obter e habilitar o complemento Mensagem de Relatório para sua organização</span><span class="sxs-lookup"><span data-stu-id="55d11-145">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="55d11-146">Pode levar até 12 horas para que o complemento apareça em sua organização.</span><span class="sxs-lookup"><span data-stu-id="55d11-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="55d11-147">No Centro de administração do Microsoft 365, vá para a página Configurações de  \> **Add-ins** em , Se você não vir a Página de Complementos, vá para o link Configurações Integradas de <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>  Aplicativos, na parte superior da página **Aplicativos integrados.** \>  \>  </span><span class="sxs-lookup"><span data-stu-id="55d11-147">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="55d11-148">Selecione **Implantar o add-in** na parte superior da página e, em seguida, **selecione Próximo**.</span><span class="sxs-lookup"><span data-stu-id="55d11-148">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Página de serviços e complementos no centro de administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="55d11-150">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="55d11-150">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="55d11-151">Na próxima página, clique **em Escolher na Loja.**</span><span class="sxs-lookup"><span data-stu-id="55d11-151">On the next page, click **Choose from the Store**.</span></span>

   ![Implantar uma nova página de complemento](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="55d11-153">Na página Selecionar **add-in** exibida,  clique na caixa Pesquisar, insira  **Mensagem** de Relatório e clique no ícone ![ ](../../media/search-icon.png) Pesquisar.</span><span class="sxs-lookup"><span data-stu-id="55d11-153">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="55d11-154">Na lista de resultados, encontre a **Mensagem de Relatório** e clique em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="55d11-154">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Selecionar resultados de pesquisa de add-in](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="55d11-156">Na caixa de diálogo exibida, revise as informações de licenciamento e privacidade e clique em **Continuar.**</span><span class="sxs-lookup"><span data-stu-id="55d11-156">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="55d11-157">Na página **Configurar o complemento** exibida, de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="55d11-157">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="55d11-158">**Usuários atribuídos:** selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="55d11-158">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="55d11-159">**Todos** (padrão)</span><span class="sxs-lookup"><span data-stu-id="55d11-159">**Everyone** (default)</span></span>
     - <span data-ttu-id="55d11-160">**Usuários/grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="55d11-160">**Specific users / groups**</span></span>
     - <span data-ttu-id="55d11-161">**Somente eu**</span><span class="sxs-lookup"><span data-stu-id="55d11-161">**Just me**</span></span>

   - <span data-ttu-id="55d11-162">**Método de** implantação: selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="55d11-162">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="55d11-163">**Corrigido (padrão)**: o complemento é implantado automaticamente para os usuários especificados e não pode removê-lo.</span><span class="sxs-lookup"><span data-stu-id="55d11-163">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="55d11-164">**Disponível:** os usuários podem instalar o add-in em **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="55d11-164">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="55d11-165">**Opcional**: o complemento é implantado automaticamente para os usuários especificados, mas eles podem optar por removê-lo.</span><span class="sxs-lookup"><span data-stu-id="55d11-165">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Configurar página de add-in](../../media/configure-add-in.png)

   <span data-ttu-id="55d11-167">Quando terminar, clique em **Implantar.**</span><span class="sxs-lookup"><span data-stu-id="55d11-167">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="55d11-168">Na página **Implantar Mensagem de** Relatório exibida, você verá um relatório de progresso seguido de uma confirmação de que o complemento foi implantado.</span><span class="sxs-lookup"><span data-stu-id="55d11-168">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="55d11-169">Depois de ler as informações, clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="55d11-169">After you read the information, click **Next**.</span></span>

   ![Página Implantar Mensagem de Relatório](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="55d11-171">Na página **Anunciar o complemento** que aparece, revise as informações e clique em **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="55d11-171">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Anunciar página de add-in](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="55d11-173">Saiba como usar o complemento Mensagem de Relatório</span><span class="sxs-lookup"><span data-stu-id="55d11-173">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="55d11-174">As pessoas que têm o complemento atribuído a elas verão os seguintes ícones:</span><span class="sxs-lookup"><span data-stu-id="55d11-174">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="55d11-175">No Outlook, o ícone tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="55d11-175">In Outlook, the icon looks like this:</span></span>

  ![Ícone de Relatório de Add-in de Mensagem para Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="55d11-177">No Outlook na Web, o ícone tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="55d11-177">In Outlook on the web, the icon looks like this:</span></span>

  ![Ícone de Aplicativo de Mensagem de Relatório do Outlook na Web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="55d11-179">Quando você notificar os usuários sobre o complemento Mensagem de Relatório, inclua um link para [Usar o complemento Mensagem de Relatório.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="55d11-179">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="55d11-180">Revisar ou editar configurações para o complemento Mensagem de Relatório</span><span class="sxs-lookup"><span data-stu-id="55d11-180">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="55d11-181">No Centro de administração do Microsoft 365, vá para a página Configurações de  \> **Add-ins** em , Se você não vir a Página de Complementos, vá para o link Configurações Integradas de <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>  Aplicativos, na parte superior da página **Aplicativos integrados.** \>  \>  </span><span class="sxs-lookup"><span data-stu-id="55d11-181">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Página Serviços e Add-Ins no novo Centro de Administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="55d11-183">Encontre e selecione o **complemento Mensagem** de Relatório.</span><span class="sxs-lookup"><span data-stu-id="55d11-183">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="55d11-184">No menu **desdolado** Editar Mensagem de Relatório exibido, revise e edite as configurações conforme apropriado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="55d11-184">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="55d11-185">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="55d11-185">When you're finished, click **Save**.</span></span>

   ![Configurações para o complemento Mensagem de Relatório](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="55d11-187">Exibir e revisar mensagens relatadas</span><span class="sxs-lookup"><span data-stu-id="55d11-187">View and review reported messages</span></span>

<span data-ttu-id="55d11-188">Para revisar as mensagens que os usuários relatam à Microsoft, você tem estas opções:</span><span class="sxs-lookup"><span data-stu-id="55d11-188">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="55d11-189">Use o portal de Envios de Administrador.</span><span class="sxs-lookup"><span data-stu-id="55d11-189">Use the Admin Submissions portal.</span></span> <span data-ttu-id="55d11-190">Para obter mais informações, [consulte Exibir envios de usuário para a Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="55d11-190">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="55d11-191">Crie uma regra de fluxo de emails (também conhecida como regra de transporte) para enviar cópias das mensagens relatadas.</span><span class="sxs-lookup"><span data-stu-id="55d11-191">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="55d11-192">Para obter instruções, [confira Usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="55d11-192">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
