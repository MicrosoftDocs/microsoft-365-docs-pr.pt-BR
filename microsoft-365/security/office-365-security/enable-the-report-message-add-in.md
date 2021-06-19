---
title: Habilitar a Mensagem de Relatório ou os complementos de Phishing de Relatório
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
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
description: Saiba como habilitar a Mensagem de Relatório ou os complementos de Phishing de Relatório para Outlook e Outlook na Web, para usuários individuais ou para toda a sua organização.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c7e5136e6d1a118df2e0e91f09a79a9a63e88052
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028578"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a><span data-ttu-id="427d7-103">Habilitar a Mensagem de Relatório ou os complementos de Phishing de Relatório</span><span class="sxs-lookup"><span data-stu-id="427d7-103">Enable the Report Message or the Report Phishing add-ins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="427d7-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="427d7-104">**Applies to**</span></span>
- [<span data-ttu-id="427d7-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="427d7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="427d7-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="427d7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="427d7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="427d7-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="427d7-108">Se você for um administrador em uma organização do Microsoft 365 com caixas de correio do Exchange Online, recomendamos que você use o portal envios no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="427d7-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in Microsoft 365 Defender.</span></span> <span data-ttu-id="427d7-109">Para obter mais informações, [consulte Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="427d7-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="427d7-110">Os complementos de Mensagem de Relatório e Relatório de Phishing para Outlook e Outlook na Web (anteriormente conhecido como Outlook Web App) permitem que as pessoas reportem facilmente falsos positivos (bons emails marcados como ruins) ou falsos negativos (email ruim permitido) para a Microsoft e suas afiliadas para análise.</span><span class="sxs-lookup"><span data-stu-id="427d7-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="427d7-111">A Microsoft usa esses envios para melhorar a eficácia das tecnologias de proteção de email.</span><span class="sxs-lookup"><span data-stu-id="427d7-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="427d7-112">Por exemplo, suponha que as pessoas estão relatando muitas mensagens usando o add-in De Phishing de relatório.</span><span class="sxs-lookup"><span data-stu-id="427d7-112">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="427d7-113">Essas informações são publicadas no Painel de Segurança e em outros relatórios.</span><span class="sxs-lookup"><span data-stu-id="427d7-113">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="427d7-114">A equipe de segurança da sua organização pode usar essas informações como uma indicação de que as políticas anti-phishing podem precisar ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="427d7-114">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="427d7-115">Você pode instalar o add-in Report Message ou Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="427d7-115">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="427d7-116">Se você quiser que seus usuários reportem mensagens de spam e phishing, implante o complemento Mensagem de Relatório em sua organização.</span><span class="sxs-lookup"><span data-stu-id="427d7-116">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="427d7-117">Para obter mais informações, consulte Enable the Report Message add-in.</span><span class="sxs-lookup"><span data-stu-id="427d7-117">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="427d7-118">O complemento Mensagem de Relatório oferece a opção de relatar mensagens de spam e phishing.</span><span class="sxs-lookup"><span data-stu-id="427d7-118">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="427d7-119">Os administradores podem habilitar o complemento Mensagem de Relatório para a organização, e usuários individuais podem instalá-lo por conta própria.</span><span class="sxs-lookup"><span data-stu-id="427d7-119">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="427d7-120">O add-in Relatório phishing fornece a opção de relatar apenas mensagens de phishing.</span><span class="sxs-lookup"><span data-stu-id="427d7-120">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="427d7-121">Os administradores podem habilitar o complemento Relatar Phishing para a organização, e usuários individuais podem instalá-lo por conta própria.</span><span class="sxs-lookup"><span data-stu-id="427d7-121">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="427d7-122">Se você for um usuário individual, poderá habilitar os dois complementos para si mesmo.</span><span class="sxs-lookup"><span data-stu-id="427d7-122">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="427d7-123">Se você for um administrador global ou um administrador do Exchange Online e o Exchange estiver configurado para usar a autenticação OAuth, você poderá habilitar o complemento Mensagem de Relatório e o complemento De Relatório phishing para sua organização.</span><span class="sxs-lookup"><span data-stu-id="427d7-123">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="427d7-124">Os dois complementos agora estão disponíveis por meio da [Implantação Centralizada.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="427d7-124">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="427d7-125">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="427d7-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="427d7-126">O complemento Mensagem de Relatório e o add-in De Phishing de Relatório funcionam com a maioria das assinaturas do Microsoft 365 e os seguintes produtos:</span><span class="sxs-lookup"><span data-stu-id="427d7-126">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>
  - <span data-ttu-id="427d7-127">Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="427d7-127">Outlook on the web</span></span>
  - <span data-ttu-id="427d7-128">Outlook 2013 SP1 ou posterior</span><span class="sxs-lookup"><span data-stu-id="427d7-128">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="427d7-129">Outlook 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="427d7-129">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="427d7-130">Outlook incluído nos aplicativos do Microsoft 365 para Empresas</span><span class="sxs-lookup"><span data-stu-id="427d7-130">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="427d7-131">Aplicativo do Outlook para iOS e Android</span><span class="sxs-lookup"><span data-stu-id="427d7-131">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="427d7-132">Ambos os complementos não estão disponíveis para caixas de correio compartilhadas ou caixas de correio em organizações locais do Exchange.</span><span class="sxs-lookup"><span data-stu-id="427d7-132">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="427d7-133">O navegador da Web existente deve trabalhar com os complementos De Relatório Mensagem e Phishing de Relatório. Mas, se você observar que o complemento não está disponível ou não está funcionando conforme o esperado, tente um navegador diferente.</span><span class="sxs-lookup"><span data-stu-id="427d7-133">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="427d7-134">Para as instalações organizacionais, a organização precisa ser configurada para usar a autenticação OAuth.</span><span class="sxs-lookup"><span data-stu-id="427d7-134">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="427d7-135">Para obter mais informações, [consulte Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="427d7-135">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="427d7-136">Os administradores precisam ser membros do grupo de função Administradores Globais.</span><span class="sxs-lookup"><span data-stu-id="427d7-136">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="427d7-137">Para obter mais informações, consulte [Permissões no Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="427d7-137">For more information, see [Permissions in the Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="427d7-138">Para obter mais informações sobre como relatar uma mensagem usando o recurso Mensagem de Relatório, consulte [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="427d7-138">For more information on how to report a message using the Report Message feature, see [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="427d7-139">Não recomendamos a experiência interna de relatório no Outlook porque ela não pode usar a [política de envio do usuário.](./user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="427d7-139">We don't recommend the built-in reporting experience in Outlook because it can't use the [user submission policy](./user-submission.md).</span></span> <span data-ttu-id="427d7-140">Em vez disso, recomendamos o uso do add-in Mensagem de Relatório ou do add-in Relatar Phishing.</span><span class="sxs-lookup"><span data-stu-id="427d7-140">We recommend using the Report Message add-in or the Report Phishing add-in instead.</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="427d7-141">Obter o complemento Mensagem de Relatório</span><span class="sxs-lookup"><span data-stu-id="427d7-141">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="427d7-142">Obter o complemento para você mesmo</span><span class="sxs-lookup"><span data-stu-id="427d7-142">Get the add-in for yourself</span></span>

1. <span data-ttu-id="427d7-143">Vá para o Microsoft AppSource em <https://appsource.microsoft.com/marketplace/apps> e pesquise o complemento Mensagem de Relatório.</span><span class="sxs-lookup"><span data-stu-id="427d7-143">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="427d7-144">Para ir diretamente para o add-in Mensagem de Relatório, vá para <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="427d7-144">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="427d7-145">Clique **em OBTER AGORA**.</span><span class="sxs-lookup"><span data-stu-id="427d7-145">Click **GET IT NOW**.</span></span>

   ![Mensagem de relatório - Obter agora](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="427d7-147">Na caixa de diálogo exibida, revise os termos de uso e política de privacidade e clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="427d7-147">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="427d7-148">Entre usando sua conta comercial ou de estudante (para uso comercial) ou sua conta da Microsoft (para uso pessoal).</span><span class="sxs-lookup"><span data-stu-id="427d7-148">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="427d7-149">Depois que o add-in for instalado e habilitado, você verá os seguintes ícones:</span><span class="sxs-lookup"><span data-stu-id="427d7-149">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="427d7-150">No Outlook, o ícone tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="427d7-150">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="427d7-151">![Ícone de add-in de mensagem de relatório para o Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="427d7-151">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="427d7-152">No Outlook na Web, o ícone tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="427d7-152">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="427d7-153">![Ícone do add-in de mensagem de relatório do Outlook na Web](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="427d7-153">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="427d7-154">Obter o complemento para sua organização</span><span class="sxs-lookup"><span data-stu-id="427d7-154">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="427d7-155">Pode levar até 12 horas para que o complemento apareça em sua organização.</span><span class="sxs-lookup"><span data-stu-id="427d7-155">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="427d7-156">No Centro de administração do Microsoft 365, vá para a página **Configurações** \> **de Complementos** em <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="427d7-156">In the Microsoft 365 admin center, go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="427d7-157">Se você não vir a Página do **Add-in,** vá para o link **Configurações** Os complementos integrados de aplicativos estão na parte superior da página \>  \>  **Aplicativos integrados.**</span><span class="sxs-lookup"><span data-stu-id="427d7-157">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="427d7-158">Selecione **Implantar o Add-in** na parte superior da página e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="427d7-158">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Página serviços e complementos no centro de administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="427d7-160">No **sub-sub-projeto** que aparece, revise as informações e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="427d7-160">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="427d7-161">Na próxima página, clique **em Escolher na Loja**.</span><span class="sxs-lookup"><span data-stu-id="427d7-161">On the next page, click **Choose from the Store**.</span></span>

   ![Implantar uma nova página de complemento](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="427d7-163">Na página **Selecionar o add-in** que  aparece, clique na caixa Pesquisar, insira **Mensagem** de Relatório e clique em **Pesquisar** ![ ícone de ](../../media/search-icon.png) Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="427d7-163">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="427d7-164">Na lista de resultados, encontre **Mensagem de Relatório** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="427d7-164">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Selecionar resultados de pesquisa de complemento](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="427d7-166">Na caixa de diálogo exibida, revise as informações de licenciamento e privacidade e clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="427d7-166">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="427d7-167">Na página **Configurar o complemento** que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="427d7-167">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="427d7-168">**Usuários atribuídos**: Selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="427d7-168">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="427d7-169">**Todos** (padrão)</span><span class="sxs-lookup"><span data-stu-id="427d7-169">**Everyone** (default)</span></span>
     - <span data-ttu-id="427d7-170">**Usuários/grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="427d7-170">**Specific users / groups**</span></span>
     - <span data-ttu-id="427d7-171">**Só eu**</span><span class="sxs-lookup"><span data-stu-id="427d7-171">**Just me**</span></span>

   - <span data-ttu-id="427d7-172">**Método de implantação**: selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="427d7-172">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="427d7-173">**Fixo (Padrão)**: o complemento é implantado automaticamente para os usuários especificados e eles não podem removê-lo.</span><span class="sxs-lookup"><span data-stu-id="427d7-173">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="427d7-174">**Disponível**: os usuários podem instalar o add-in em **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="427d7-174">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="427d7-175">**Opcional**: o complemento é implantado automaticamente para os usuários especificados, mas eles podem optar por removê-lo.</span><span class="sxs-lookup"><span data-stu-id="427d7-175">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Configurar página de add-in](../../media/configure-add-in.png)

   <span data-ttu-id="427d7-177">Quando terminar, clique em **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="427d7-177">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="427d7-178">Na página **Implantar Mensagem** de Relatório exibida, você verá um relatório de progresso seguido de uma confirmação de que o complemento foi implantado.</span><span class="sxs-lookup"><span data-stu-id="427d7-178">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="427d7-179">Depois de ler as informações, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="427d7-179">After you read the information, click **Next**.</span></span>

   ![Página Implantar Mensagem de Relatório](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="427d7-181">Na página **Anunciar o** complemento que aparece, revise as informações e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="427d7-181">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Anunciar página de complementos](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="427d7-183">Revisar ou editar configurações do complemento Mensagem de Relatório</span><span class="sxs-lookup"><span data-stu-id="427d7-183">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="427d7-184">No Centro de administração do Microsoft 365, vá para a página Ir para a página **Configurações** de \> **Complementos** em <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="427d7-184">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="427d7-185">Se você não vir a Página do **Add-in,** vá para o link **Configurações** Os complementos integrados de aplicativos estão na parte superior da página \>  \>  **Aplicativos integrados.**</span><span class="sxs-lookup"><span data-stu-id="427d7-185">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Página Serviços e Add-Ins no novo Centro de Administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="427d7-187">Encontre e selecione o complemento **Mensagem** de Relatório.</span><span class="sxs-lookup"><span data-stu-id="427d7-187">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="427d7-188">No flyout **Editar Relatório Mensagem** que aparece, revise e edite as configurações conforme apropriado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="427d7-188">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="427d7-189">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="427d7-189">When you're finished, click **Save**.</span></span>

   ![Configurações do complemento Mensagem de Relatório](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="427d7-191">Obter o complemento Phishing de Relatório</span><span class="sxs-lookup"><span data-stu-id="427d7-191">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="427d7-192">Obter o complemento para você mesmo</span><span class="sxs-lookup"><span data-stu-id="427d7-192">Get the add-in for yourself</span></span>

1. <span data-ttu-id="427d7-193">Vá para o Microsoft AppSource em <https://appsource.microsoft.com/marketplace/apps> e pesquise o add-in De Phishing de relatório.</span><span class="sxs-lookup"><span data-stu-id="427d7-193">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="427d7-194">Clique **em OBTER AGORA**.</span><span class="sxs-lookup"><span data-stu-id="427d7-194">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="427d7-195">Na caixa de diálogo exibida, revise os termos de uso e política de privacidade e clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="427d7-195">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="427d7-196">Entre usando sua conta comercial ou de estudante (para uso comercial) ou sua conta da Microsoft (para uso pessoal).</span><span class="sxs-lookup"><span data-stu-id="427d7-196">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="427d7-197">Depois que o add-in for instalado e habilitado, você verá os seguintes ícones:</span><span class="sxs-lookup"><span data-stu-id="427d7-197">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="427d7-198">No Outlook, o ícone tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="427d7-198">In Outlook, the icon looks like this:</span></span>

  ![Relatar ícone do add-in phishing para o Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="427d7-200">No Outlook na Web, o ícone tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="427d7-200">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="427d7-201">![Ícone do add-in phishing do Outlook na Web](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="427d7-201">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="427d7-202">Obter o complemento para sua organização</span><span class="sxs-lookup"><span data-stu-id="427d7-202">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="427d7-203">Pode levar até 12 horas para que o complemento apareça em sua organização.</span><span class="sxs-lookup"><span data-stu-id="427d7-203">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="427d7-204">No Centro de administração do Microsoft 365, vá para a página Ir para a página **Configurações** de \> **Complementos** em <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="427d7-204">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="427d7-205">Se você não vir a Página do **Add-in,** vá para o link **Configurações** Os complementos integrados de aplicativos estão na parte superior da página \>  \>  **Aplicativos integrados.**</span><span class="sxs-lookup"><span data-stu-id="427d7-205">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="427d7-206">Selecione **Implantar o Add-in** na parte superior da página e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="427d7-206">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Página serviços e complementos no centro de administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="427d7-208">No **sub-sub-projeto** que aparece, revise as informações e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="427d7-208">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="427d7-209">Na próxima página, clique **em Escolher na Loja**.</span><span class="sxs-lookup"><span data-stu-id="427d7-209">On the next page, click **Choose from the Store**.</span></span>

   ![Implantar uma nova página de complemento](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="427d7-211">Na página **Selecionar o add-in** que  aparece, clique na caixa Pesquisar, digite **Relatar Phishing** e clique em **Pesquisar** ícone ![ de ](../../media/search-icon.png) Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="427d7-211">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="427d7-212">Na lista de resultados, encontre **Relatar Phishing** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="427d7-212">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="427d7-213">Na caixa de diálogo exibida, revise as informações de licenciamento e privacidade e clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="427d7-213">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="427d7-214">Na página **Configurar o complemento** que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="427d7-214">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="427d7-215">**Usuários atribuídos**: Selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="427d7-215">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="427d7-216">**Todos** (padrão)</span><span class="sxs-lookup"><span data-stu-id="427d7-216">**Everyone** (default)</span></span>
     - <span data-ttu-id="427d7-217">**Usuários/grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="427d7-217">**Specific users / groups**</span></span>
     - <span data-ttu-id="427d7-218">**Só eu**</span><span class="sxs-lookup"><span data-stu-id="427d7-218">**Just me**</span></span>

   - <span data-ttu-id="427d7-219">**Método de implantação**: selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="427d7-219">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="427d7-220">**Fixo (Padrão)**: o complemento é implantado automaticamente para os usuários especificados e eles não podem removê-lo.</span><span class="sxs-lookup"><span data-stu-id="427d7-220">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="427d7-221">**Disponível**: os usuários podem instalar o add-in em **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="427d7-221">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="427d7-222">**Opcional**: o complemento é implantado automaticamente para os usuários especificados, mas eles podem optar por removê-lo.</span><span class="sxs-lookup"><span data-stu-id="427d7-222">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="427d7-223">Quando terminar, clique em **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="427d7-223">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="427d7-224">Na página **Implantar Phishing** de Relatório que aparece, você verá um relatório de progresso seguido de uma confirmação de que o complemento foi implantado.</span><span class="sxs-lookup"><span data-stu-id="427d7-224">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="427d7-225">Depois de ler as informações, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="427d7-225">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="427d7-226">Na página **Anunciar o** complemento que aparece, revise as informações e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="427d7-226">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="427d7-227">Revisar ou editar configurações do add-in Relatar Phishing</span><span class="sxs-lookup"><span data-stu-id="427d7-227">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="427d7-228">No Centro de administração do Microsoft 365, vá para a página Ir para a página **Configurações** de \> **Complementos** em <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="427d7-228">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="427d7-229">Se você não vir a Página do **Add-in,** vá para o link **Configurações** Os complementos integrados de aplicativos estão na parte superior da página \>  \>  **Aplicativos integrados.**</span><span class="sxs-lookup"><span data-stu-id="427d7-229">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="427d7-230">Encontre e selecione o **complemento Relatar Phishing.**</span><span class="sxs-lookup"><span data-stu-id="427d7-230">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="427d7-231">No flyout **Editar Relatório phishing** que aparece, revise e edite as configurações conforme apropriado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="427d7-231">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="427d7-232">Ao finalizar, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="427d7-232">When you're finished, click **Save**.</span></span>
