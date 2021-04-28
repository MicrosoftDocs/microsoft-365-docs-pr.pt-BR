---
title: Relatar falsos positivos e falsos negativos no Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Saiba como relatar falsos positivos e falsos negativos no Outlook e habilitar os complementos Mensagem de Relatório e Relatório de Phishing.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38f940a98581c5678eef0c57c95f6349cdb41de8
ms.sourcegitcommit: ddb1bf56bcba4f03c803f79492e8cd0dc41a3d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "52065129"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="32aa7-103">Relatar falsos positivos e falsos negativos no Outlook</span><span class="sxs-lookup"><span data-stu-id="32aa7-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="32aa7-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="32aa7-104">**Applies to**</span></span>
- [<span data-ttu-id="32aa7-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="32aa7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="32aa7-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="32aa7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="32aa7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="32aa7-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="32aa7-108">Se você for um administrador em uma organização do Microsoft 365 com caixas de correio do Exchange Online, recomendamos usar o portal Envios no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="32aa7-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="32aa7-109">Para obter mais informações, [consulte Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="32aa7-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="32aa7-110">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou caixas de correio locais usando autenticação moderna híbrida, você pode enviar falsos positivos (emails bons marcados como spam) e falsos negativos (email e phishing não permitidos) para a Proteção do Exchange Online (EOP).</span><span class="sxs-lookup"><span data-stu-id="32aa7-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email marked as spam) and false negatives (bad email and phish allowed) to Exchange Online Protection (EOP).</span></span>

## <a name="things-to-remember-before-you-use-the-report-message-feature"></a><span data-ttu-id="32aa7-111">Coisas para lembrar antes de usar o recurso Relatar Mensagem</span><span class="sxs-lookup"><span data-stu-id="32aa7-111">Things to remember before you use the Report Message feature</span></span>

- <span data-ttu-id="32aa7-112">Para a melhor experiência de envio do usuário, use o complemento Mensagem de Relatório ou o complemento Relatar Phishing.</span><span class="sxs-lookup"><span data-stu-id="32aa7-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="32aa7-113">Observe que esse complemento funciona para o Outlook em todas as plataformas— na Web, iOS, Android e Área de Trabalho.</span><span class="sxs-lookup"><span data-stu-id="32aa7-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="32aa7-114">Se você for um administrador em uma organização com caixas de correio do Exchange Online, use o portal Envios no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="32aa7-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="32aa7-115">Para obter mais informações, [consulte Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="32aa7-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="32aa7-116">Você pode configurar para enviar mensagens diretamente para a Microsoft, uma caixa de correio especificada ou ambas.</span><span class="sxs-lookup"><span data-stu-id="32aa7-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="32aa7-117">Para obter mais informações, consulte [Políticas de envios de usuário](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="32aa7-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="32aa7-118">Para obter mais informações sobre o relatório de mensagens para a Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="32aa7-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="32aa7-119">Usar o recurso Mensagem de Relatório</span><span class="sxs-lookup"><span data-stu-id="32aa7-119">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="32aa7-120">Relatar mensagens de lixo eletrônico e phishing</span><span class="sxs-lookup"><span data-stu-id="32aa7-120">Report junk and phishing messages</span></span>

<span data-ttu-id="32aa7-121">Para mensagens na Caixa de Entrada ou em qualquer outra pasta de email, exceto Lixo Eletrônico, use o seguinte método para relatar mensagens de spam e phishing:</span><span class="sxs-lookup"><span data-stu-id="32aa7-121">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="32aa7-122">Clique nas **releições** Mais ações no canto superior direito  da mensagem selecionada, clique em Relatar mensagem no menu suspenso e selecione **Lixo** Eletrônico ou **Phishing**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-122">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>
  
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="32aa7-123">![Mensagem de Relatório - Mais ações](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="32aa7-123">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="32aa7-124">![Mensagem de Relatório - Lixo Eletrônico e Phishing](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="32aa7-124">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="32aa7-125">As mensagens selecionadas serão enviadas à Microsoft para análise e:</span><span class="sxs-lookup"><span data-stu-id="32aa7-125">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="32aa7-126">Movido para a pasta Lixo Eletrônico se tiver sido relatado como spam.</span><span class="sxs-lookup"><span data-stu-id="32aa7-126">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="32aa7-127">Excluído se tiver sido relatado como phishing.</span><span class="sxs-lookup"><span data-stu-id="32aa7-127">Deleted if it was reported as phishing.</span></span>
   
### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="32aa7-128">Relatar mensagens que não são lixo eletrônico</span><span class="sxs-lookup"><span data-stu-id="32aa7-128">Report messages that are not junk</span></span>

1. <span data-ttu-id="32aa7-129">Clique nas **releições** Mais ações no canto superior direito  da mensagem selecionada, clique em Relatar mensagem no menu suspenso e clique em **Não Lixo Eletrônico.**</span><span class="sxs-lookup"><span data-stu-id="32aa7-129">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="32aa7-130">![Mensagem de Relatório - Mais ações](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="32aa7-130">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="32aa7-131">![Mensagem de relatório - Não lixo eletrônico](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="32aa7-131">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="32aa7-132">A mensagem selecionada será enviada à Microsoft para análise e movida para a Caixa de Entrada ou qualquer outra pasta especificada.</span><span class="sxs-lookup"><span data-stu-id="32aa7-132">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="enable-the-report-message-and-report-phishing-add-ins"></a><span data-ttu-id="32aa7-133">Habilitar os complementos Mensagem de Relatório e Relatório de Phishing</span><span class="sxs-lookup"><span data-stu-id="32aa7-133">Enable the Report Message and Report Phishing add-ins</span></span>

<span data-ttu-id="32aa7-134">Os complementos de Mensagem de Relatório e Relatório de Phishing para Outlook e Outlook na Web (anteriormente conhecido como Outlook Web App) permitem que as pessoas reportem facilmente falsos positivos (bons emails marcados como ruins) ou falsos negativos (email ruim permitido) para a Microsoft e suas afiliadas para análise.</span><span class="sxs-lookup"><span data-stu-id="32aa7-134">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="32aa7-135">A Microsoft usa esses envios para melhorar a eficácia das tecnologias de proteção de email.</span><span class="sxs-lookup"><span data-stu-id="32aa7-135">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="32aa7-136">Por exemplo, suponha que as pessoas estão relatando muitas mensagens usando o add-in De Phishing de relatório.</span><span class="sxs-lookup"><span data-stu-id="32aa7-136">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="32aa7-137">Essas informações são publicadas no Painel de Segurança e em outros relatórios.</span><span class="sxs-lookup"><span data-stu-id="32aa7-137">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="32aa7-138">A equipe de segurança da sua organização pode usar essas informações como uma indicação de que as políticas anti-phishing podem precisar ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="32aa7-138">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="32aa7-139">Você pode instalar o add-in Report Message ou Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="32aa7-139">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="32aa7-140">Se você quiser que seus usuários reportem mensagens de spam e phishing, implante o complemento Mensagem de Relatório em sua organização.</span><span class="sxs-lookup"><span data-stu-id="32aa7-140">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="32aa7-141">Para obter mais informações, consulte Enable the Report Message add-in.</span><span class="sxs-lookup"><span data-stu-id="32aa7-141">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="32aa7-142">O complemento Mensagem de Relatório oferece a opção de relatar mensagens de spam e phishing.</span><span class="sxs-lookup"><span data-stu-id="32aa7-142">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="32aa7-143">Os administradores podem habilitar o complemento Mensagem de Relatório para a organização, e usuários individuais podem instalá-lo por conta própria.</span><span class="sxs-lookup"><span data-stu-id="32aa7-143">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="32aa7-144">O add-in Relatório phishing fornece a opção de relatar apenas mensagens de phishing.</span><span class="sxs-lookup"><span data-stu-id="32aa7-144">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="32aa7-145">Os administradores podem habilitar o complemento Relatar Phishing para a organização, e usuários individuais podem instalá-lo por conta própria.</span><span class="sxs-lookup"><span data-stu-id="32aa7-145">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="32aa7-146">Se você for um usuário individual, poderá habilitar os dois complementos para si mesmo.</span><span class="sxs-lookup"><span data-stu-id="32aa7-146">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="32aa7-147">f você é um administrador global ou um administrador do Exchange Online, e o Exchange está configurado para usar a autenticação OAuth, você pode habilitar o complemento Mensagem de Relatório e o complemento De Relatório phishing para sua organização.</span><span class="sxs-lookup"><span data-stu-id="32aa7-147">f you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="32aa7-148">Os dois complementos agora estão disponíveis por meio da [Implantação Centralizada.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="32aa7-148">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="32aa7-149">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="32aa7-149">What do you need to know before you begin?</span></span>

- <span data-ttu-id="32aa7-150">O complemento Mensagem de Relatório e o add-in De Phishing de Relatório funcionam com a maioria das assinaturas do Microsoft 365 e os seguintes produtos:</span><span class="sxs-lookup"><span data-stu-id="32aa7-150">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="32aa7-151">Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="32aa7-151">Outlook on the web</span></span>
  - <span data-ttu-id="32aa7-152">Outlook 2013 SP1 ou posterior</span><span class="sxs-lookup"><span data-stu-id="32aa7-152">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="32aa7-153">Outlook 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="32aa7-153">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="32aa7-154">Outlook incluído nos aplicativos do Microsoft 365 para Empresas</span><span class="sxs-lookup"><span data-stu-id="32aa7-154">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="32aa7-155">Aplicativo do Outlook para iOS e Android</span><span class="sxs-lookup"><span data-stu-id="32aa7-155">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="32aa7-156">Ambos os complementos não estão disponíveis para caixas de correio compartilhadas ou caixas de correio em organizações locais do Exchange.</span><span class="sxs-lookup"><span data-stu-id="32aa7-156">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="32aa7-157">O navegador da Web existente deve trabalhar com os complementos De Relatório Mensagem e Phishing de Relatório. Mas, se você observar que o complemento não está disponível ou não está funcionando conforme o esperado, tente um navegador diferente.</span><span class="sxs-lookup"><span data-stu-id="32aa7-157">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="32aa7-158">Para as instalações organizacionais, a organização precisa ser configurada para usar a autenticação OAuth.</span><span class="sxs-lookup"><span data-stu-id="32aa7-158">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="32aa7-159">Para obter mais informações, [consulte Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="32aa7-159">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="32aa7-160">Os administradores precisam ser membros do grupo de função Administradores Globais.</span><span class="sxs-lookup"><span data-stu-id="32aa7-160">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="32aa7-161">Para saber mais, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="32aa7-161">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="32aa7-162">Obter o complemento Mensagem de Relatório</span><span class="sxs-lookup"><span data-stu-id="32aa7-162">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="32aa7-163">Obter o complemento para você mesmo</span><span class="sxs-lookup"><span data-stu-id="32aa7-163">Get the add-in for yourself</span></span>

1. <span data-ttu-id="32aa7-164">Vá para o Microsoft AppSource em <https://appsource.microsoft.com/marketplace/apps> e pesquise o complemento Mensagem de Relatório.</span><span class="sxs-lookup"><span data-stu-id="32aa7-164">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="32aa7-165">Para ir diretamente para o add-in Mensagem de Relatório, vá para <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="32aa7-165">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="32aa7-166">Clique **em OBTER AGORA**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-166">Click **GET IT NOW**.</span></span>

   ![Mensagem de relatório - Obter agora](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="32aa7-168">Na caixa de diálogo exibida, revise os termos de uso e política de privacidade e clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-168">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="32aa7-169">Entre usando sua conta comercial ou de estudante (para uso comercial) ou sua conta da Microsoft (para uso pessoal).</span><span class="sxs-lookup"><span data-stu-id="32aa7-169">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="32aa7-170">Depois que o add-in for instalado e habilitado, você verá os seguintes ícones:</span><span class="sxs-lookup"><span data-stu-id="32aa7-170">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="32aa7-171">No Outlook, o ícone tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="32aa7-171">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="32aa7-172">![Ícone de add-in de mensagem de relatório para o Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="32aa7-172">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="32aa7-173">No Outlook na Web, o ícone tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="32aa7-173">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="32aa7-174">![Ícone do add-in de mensagem de relatório do Outlook na Web](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="32aa7-174">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="32aa7-175">Obter o complemento para sua organização</span><span class="sxs-lookup"><span data-stu-id="32aa7-175">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="32aa7-176">Pode levar até 12 horas para que o complemento apareça em sua organização.</span><span class="sxs-lookup"><span data-stu-id="32aa7-176">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="32aa7-177">No Centro de administração do Microsoft 365, vá para a página Ir para a página **Configurações** de \> **Complementos** em <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="32aa7-177">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="32aa7-178">Se você não vir a Página do **Add-in,** vá para o link **Configurações** Os complementos integrados de aplicativos estão na parte superior da página \>  \>  **Aplicativos integrados.**</span><span class="sxs-lookup"><span data-stu-id="32aa7-178">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="32aa7-179">Selecione **Implantar o Add-in** na parte superior da página e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-179">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Página serviços e complementos no centro de administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="32aa7-181">No **sub-sub-projeto** que aparece, revise as informações e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-181">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="32aa7-182">Na próxima página, clique **em Escolher na Loja**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-182">On the next page, click **Choose from the Store**.</span></span>

   ![Implantar uma nova página de complemento](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="32aa7-184">Na página **Selecionar o add-in** que  aparece, clique na caixa Pesquisar, insira **Mensagem** de Relatório e clique em **Pesquisar** ![ ícone de ](../../media/search-icon.png) Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="32aa7-184">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="32aa7-185">Na lista de resultados, encontre **Mensagem de Relatório** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-185">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Selecionar resultados de pesquisa de complemento](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="32aa7-187">Na caixa de diálogo exibida, revise as informações de licenciamento e privacidade e clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-187">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="32aa7-188">Na página **Configurar o complemento** que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="32aa7-188">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="32aa7-189">**Usuários atribuídos**: Selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="32aa7-189">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="32aa7-190">**Todos** (padrão)</span><span class="sxs-lookup"><span data-stu-id="32aa7-190">**Everyone** (default)</span></span>
     - <span data-ttu-id="32aa7-191">**Usuários/grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="32aa7-191">**Specific users / groups**</span></span>
     - <span data-ttu-id="32aa7-192">**Só eu**</span><span class="sxs-lookup"><span data-stu-id="32aa7-192">**Just me**</span></span>

   - <span data-ttu-id="32aa7-193">**Método de implantação**: selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="32aa7-193">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="32aa7-194">**Fixo (Padrão)**: o complemento é implantado automaticamente para os usuários especificados e eles não podem removê-lo.</span><span class="sxs-lookup"><span data-stu-id="32aa7-194">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="32aa7-195">**Disponível**: os usuários podem instalar o add-in em **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-195">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="32aa7-196">**Opcional**: o complemento é implantado automaticamente para os usuários especificados, mas eles podem optar por removê-lo.</span><span class="sxs-lookup"><span data-stu-id="32aa7-196">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Configurar página de add-in](../../media/configure-add-in.png)

   <span data-ttu-id="32aa7-198">Quando terminar, clique em **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-198">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="32aa7-199">Na página **Implantar Mensagem** de Relatório exibida, você verá um relatório de progresso seguido de uma confirmação de que o complemento foi implantado.</span><span class="sxs-lookup"><span data-stu-id="32aa7-199">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="32aa7-200">Depois de ler as informações, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-200">After you read the information, click **Next**.</span></span>

   ![Página Implantar Mensagem de Relatório](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="32aa7-202">Na página **Anunciar o** complemento que aparece, revise as informações e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-202">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Anunciar página de complementos](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="32aa7-204">Revisar ou editar configurações do complemento Mensagem de Relatório</span><span class="sxs-lookup"><span data-stu-id="32aa7-204">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="32aa7-205">No Centro de administração do Microsoft 365, vá para a página Ir para a página **Configurações** de \> **Complementos** em <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="32aa7-205">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="32aa7-206">Se você não vir a Página do **Add-in,** vá para o link **Configurações** Os complementos integrados de aplicativos estão na parte superior da página \>  \>  **Aplicativos integrados.**</span><span class="sxs-lookup"><span data-stu-id="32aa7-206">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Página Serviços e Add-Ins no novo Centro de Administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="32aa7-208">Encontre e selecione o complemento **Mensagem** de Relatório.</span><span class="sxs-lookup"><span data-stu-id="32aa7-208">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="32aa7-209">No flyout **Editar Relatório Mensagem** que aparece, revise e edite as configurações conforme apropriado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="32aa7-209">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="32aa7-210">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-210">When you're finished, click **Save**.</span></span>

   ![Configurações do complemento Mensagem de Relatório](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="32aa7-212">Obter o complemento Phishing de Relatório</span><span class="sxs-lookup"><span data-stu-id="32aa7-212">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="32aa7-213">Obter o complemento para você mesmo</span><span class="sxs-lookup"><span data-stu-id="32aa7-213">Get the add-in for yourself</span></span>

1. <span data-ttu-id="32aa7-214">Vá para o Microsoft AppSource em <https://appsource.microsoft.com/marketplace/apps> e pesquise o add-in De Phishing de relatório.</span><span class="sxs-lookup"><span data-stu-id="32aa7-214">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="32aa7-215">Clique **em OBTER AGORA**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-215">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="32aa7-216">Na caixa de diálogo exibida, revise os termos de uso e política de privacidade e clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-216">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="32aa7-217">Entre usando sua conta comercial ou de estudante (para uso comercial) ou sua conta da Microsoft (para uso pessoal).</span><span class="sxs-lookup"><span data-stu-id="32aa7-217">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="32aa7-218">Depois que o add-in for instalado e habilitado, você verá os seguintes ícones:</span><span class="sxs-lookup"><span data-stu-id="32aa7-218">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="32aa7-219">No Outlook, o ícone tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="32aa7-219">In Outlook, the icon looks like this:</span></span>

  ![Relatar ícone do add-in phishing para o Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="32aa7-221">No Outlook na Web, o ícone tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="32aa7-221">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="32aa7-222">![Ícone do add-in phishing do Outlook na Web](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="32aa7-222">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="32aa7-223">Obter o complemento para sua organização</span><span class="sxs-lookup"><span data-stu-id="32aa7-223">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="32aa7-224">Pode levar até 12 horas para que o complemento apareça em sua organização.</span><span class="sxs-lookup"><span data-stu-id="32aa7-224">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="32aa7-225">No Centro de administração do Microsoft 365, vá para a página Ir para a página **Configurações** de \> **Complementos** em <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="32aa7-225">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="32aa7-226">Se você não vir a Página do **Add-in,** vá para o link **Configurações** Os complementos integrados de aplicativos estão na parte superior da página \>  \>  **Aplicativos integrados.**</span><span class="sxs-lookup"><span data-stu-id="32aa7-226">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="32aa7-227">Selecione **Implantar o Add-in** na parte superior da página e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-227">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Página serviços e complementos no centro de administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="32aa7-229">No **sub-sub-projeto** que aparece, revise as informações e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-229">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="32aa7-230">Na próxima página, clique **em Escolher na Loja**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-230">On the next page, click **Choose from the Store**.</span></span>

   ![Implantar uma nova página de complemento](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="32aa7-232">Na página **Selecionar o add-in** que  aparece, clique na caixa Pesquisar, digite **Relatar Phishing** e clique em **Pesquisar** ícone ![ de ](../../media/search-icon.png) Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="32aa7-232">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="32aa7-233">Na lista de resultados, encontre **Relatar Phishing** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-233">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="32aa7-234">Na caixa de diálogo exibida, revise as informações de licenciamento e privacidade e clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-234">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="32aa7-235">Na página **Configurar o complemento** que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="32aa7-235">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="32aa7-236">**Usuários atribuídos**: Selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="32aa7-236">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="32aa7-237">**Todos** (padrão)</span><span class="sxs-lookup"><span data-stu-id="32aa7-237">**Everyone** (default)</span></span>
     - <span data-ttu-id="32aa7-238">**Usuários/grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="32aa7-238">**Specific users / groups**</span></span>
     - <span data-ttu-id="32aa7-239">**Só eu**</span><span class="sxs-lookup"><span data-stu-id="32aa7-239">**Just me**</span></span>

   - <span data-ttu-id="32aa7-240">**Método de implantação**: selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="32aa7-240">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="32aa7-241">**Fixo (Padrão)**: o complemento é implantado automaticamente para os usuários especificados e eles não podem removê-lo.</span><span class="sxs-lookup"><span data-stu-id="32aa7-241">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="32aa7-242">**Disponível**: os usuários podem instalar o add-in em **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-242">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="32aa7-243">**Opcional**: o complemento é implantado automaticamente para os usuários especificados, mas eles podem optar por removê-lo.</span><span class="sxs-lookup"><span data-stu-id="32aa7-243">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="32aa7-244">Quando terminar, clique em **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-244">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="32aa7-245">Na página **Implantar Phishing** de Relatório que aparece, você verá um relatório de progresso seguido de uma confirmação de que o complemento foi implantado.</span><span class="sxs-lookup"><span data-stu-id="32aa7-245">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="32aa7-246">Depois de ler as informações, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-246">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="32aa7-247">Na página **Anunciar o** complemento que aparece, revise as informações e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-247">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="32aa7-248">Revisar ou editar configurações do add-in Relatar Phishing</span><span class="sxs-lookup"><span data-stu-id="32aa7-248">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="32aa7-249">No Centro de administração do Microsoft 365, vá para a página Ir para a página **Configurações** de \> **Complementos** em <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="32aa7-249">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="32aa7-250">Se você não vir a Página do **Add-in,** vá para o link **Configurações** Os complementos integrados de aplicativos estão na parte superior da página \>  \>  **Aplicativos integrados.**</span><span class="sxs-lookup"><span data-stu-id="32aa7-250">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="32aa7-251">Encontre e selecione o **complemento Relatar Phishing.**</span><span class="sxs-lookup"><span data-stu-id="32aa7-251">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="32aa7-252">No flyout **Editar Relatório phishing** que aparece, revise e edite as configurações conforme apropriado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="32aa7-252">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="32aa7-253">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="32aa7-253">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="32aa7-254">Exibir e revisar mensagens relatadas</span><span class="sxs-lookup"><span data-stu-id="32aa7-254">View and review reported messages</span></span>

<span data-ttu-id="32aa7-255">Para revisar as mensagens relatadas pelos usuários à Microsoft, você tem estas opções:</span><span class="sxs-lookup"><span data-stu-id="32aa7-255">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="32aa7-256">Use o portal Envios de Administrador.</span><span class="sxs-lookup"><span data-stu-id="32aa7-256">Use the Admin Submissions portal.</span></span> <span data-ttu-id="32aa7-257">Para obter mais informações, consulte [Exibir envios de usuários para a Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="32aa7-257">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="32aa7-258">Crie uma regra de fluxo de emails (também conhecida como regra de transporte) para enviar cópias de mensagens relatadas.</span><span class="sxs-lookup"><span data-stu-id="32aa7-258">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="32aa7-259">Para obter instruções, [consulte Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="32aa7-259">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>