---
title: Habilitar o suplemento de Mensagem de Relatório
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
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
ms.openlocfilehash: 94dbe7d9dcd5cf3dc8bd5874550880d813f879f5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42086291"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="2c841-103">Habilitar o suplemento de Mensagem de Relatório</span><span class="sxs-lookup"><span data-stu-id="2c841-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="2c841-104">O suplemento de mensagem de relatório para o Outlook e o Outlook na Web não é exatamente o mesmo que o [filtro de lixo eletrônico do Outlook](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), embora ambos possam ser usados para marcar email como lixo eletrônico, não lixo eletrônico ou uma tentativa de phishing.</span><span class="sxs-lookup"><span data-stu-id="2c841-104">The Report Message add-in for Outlook and Outlook on the web is not exactly the same thing as the [Outlook Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), although both can be used to mark email as junk, not junk, or a phishing attempt.</span></span> <span data-ttu-id="2c841-105">A diferença é, o suplemento de mensagem de relatório para o Outlook e o Outlook na Web notifica a Microsoft sobre emails não classificados, enquanto o filtro de lixo eletrônico do Outlook é usado para organizar mensagens de email na caixa de correio de um usuário.</span><span class="sxs-lookup"><span data-stu-id="2c841-105">The difference is, the Report Message add-in for Outlook and Outlook on the web notifies Microsoft about misclassified email, whereas the Outlook Junk Email Filter is used to organize email messages in a user's mailbox.</span></span>

## <a name="overview"></a><span data-ttu-id="2c841-106">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="2c841-106">Overview</span></span>

<span data-ttu-id="2c841-107">O suplemento de mensagem de relatório para o Outlook e o Outlook na Web (anteriormente conhecido como Outlook Web App) permite que as pessoas relatem facilmente emails mal classificados, sejam seguros ou mal-intencionados para a Microsoft e seus afiliados para análise.</span><span class="sxs-lookup"><span data-stu-id="2c841-107">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="2c841-108">A Microsoft usa esses envios para melhorar a eficácia das tecnologias de proteção de email.</span><span class="sxs-lookup"><span data-stu-id="2c841-108">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="2c841-109">Além disso, se sua organização estiver usando o [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) ou o [plano 2](office-365-ti.md), o suplemento de mensagem de relatório fornecerá a equipe de segurança da sua organização com informações úteis que podem ser usadas para analisar e atualizar as políticas de segurança.</span><span class="sxs-lookup"><span data-stu-id="2c841-109">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="2c841-110">Por exemplo, suponha que as pessoas estejam relatando muitas mensagens como phishing.</span><span class="sxs-lookup"><span data-stu-id="2c841-110">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="2c841-111">Essas informações são superfícies no [painel de segurança](security-dashboard.md) e em outros relatórios.</span><span class="sxs-lookup"><span data-stu-id="2c841-111">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="2c841-112">A equipe de segurança da sua organização pode usar essas informações como indicação de que as políticas anti-phishing podem precisar ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="2c841-112">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="2c841-113">Ou, se as pessoas estiverem relatando muitas mensagens que foram sinalizadas como lixo eletrônico como não sendo lixo eletrônico usando o suplemento de mensagem de relatório, a equipe de segurança da sua organização poderá precisar ajustar [políticas antispam](configure-the-anti-spam-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2c841-113">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span>

<span data-ttu-id="2c841-114">O suplemento de mensagem de relatório funciona com a maioria das assinaturas do Office 365 e os seguintes produtos:</span><span class="sxs-lookup"><span data-stu-id="2c841-114">The Report Message add-in works with most Office 365 subscriptions and the following products:</span></span>

 - <span data-ttu-id="2c841-115">Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="2c841-115">Outlook on the web</span></span>
 - <span data-ttu-id="2c841-116">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="2c841-116">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="2c841-117">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2c841-117">Outlook 2016</span></span>
 - <span data-ttu-id="2c841-118">Outlook 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="2c841-118">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="2c841-119">Outlook incluído no Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="2c841-119">Outlook included with Office 365 ProPlus</span></span>

<span data-ttu-id="2c841-120">O suplemento de mensagem de relatório atualmente não está disponível para:</span><span class="sxs-lookup"><span data-stu-id="2c841-120">The Report Message add-in is currently not available for:</span></span>

 - <span data-ttu-id="2c841-121">Caixas de correio em organizações do Exchange local</span><span class="sxs-lookup"><span data-stu-id="2c841-121">Mailboxes in on-premises Exchange organizations</span></span>
 - <span data-ttu-id="2c841-122">Assinaturas GCC, GCC alta ou DoD</span><span class="sxs-lookup"><span data-stu-id="2c841-122">GCC, GCC HIGH, or DoD subscriptions</span></span>

<span data-ttu-id="2c841-123">O navegador da Web existente deve ser suficiente para que o suplemento de mensagem de relatório funcione; no entanto, se você notar que o suplemento não está disponível ou não está funcionando conforme o esperado, tente um navegador diferente.</span><span class="sxs-lookup"><span data-stu-id="2c841-123">Your existing web browser should suffice for the Report Message add-in to work; however, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

<span data-ttu-id="2c841-124">Se você for um usuário individual, é possível [habilitar o relatório de suplemento de mensagens para você](#get-the-report-message-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="2c841-124">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="2c841-125">Se você for um administrador global do Office 365 ou um administrador do Exchange Online e o Exchange estiver configurado para usar a autenticação OAuth, você poderá [habilitar o suplemento de mensagem de relatório para sua organização](#get-and-enable-the-report-message-add-in-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="2c841-125">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="2c841-126">O suplemento de mensagem de relatório agora está disponível por meio da [implantação centralizada](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="2c841-126">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="2c841-127">Obter o suplemento de mensagem de relatório para você mesmo</span><span class="sxs-lookup"><span data-stu-id="2c841-127">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="2c841-128">No [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), procure o [suplemento de mensagem de relatório](https://appsource.microsoft.com/product/office/wa104381180).</span><span class="sxs-lookup"><span data-stu-id="2c841-128">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>

2. <span data-ttu-id="2c841-129">Escolha **obtê-lo agora**.</span><span class="sxs-lookup"><span data-stu-id="2c841-129">Choose **GET IT NOW**.</span></span>

   ![Mensagem de relatório-obter agora](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="2c841-131">Revise os termos de uso e política de privacidade.</span><span class="sxs-lookup"><span data-stu-id="2c841-131">Review the terms of use and privacy policy.</span></span> <span data-ttu-id="2c841-132">Em seguida, escolha **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="2c841-132">Then choose **Continue**.</span></span>

4. <span data-ttu-id="2c841-133">Entre no Office 365 usando sua conta corporativa ou de estudante (para uso comercial) ou sua conta da Microsoft (para uso pessoal).</span><span class="sxs-lookup"><span data-stu-id="2c841-133">Sign in to Office 365 using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="2c841-134">Depois que o suplemento estiver instalado e habilitado, você verá os seguintes ícones:</span><span class="sxs-lookup"><span data-stu-id="2c841-134">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="2c841-135">No Outlook, o ícone tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="2c841-135">In Outlook, the icon looks like this:</span></span>

  ![Ícone de suplemento de mensagem de relatório para Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="2c841-137">No Outlook na Web (anteriormente conhecido como Outlook Web App), o ícone tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="2c841-137">In Outlook on the web (formerly known as Outlook Web App), the icon looks like this:</span></span>

  ![Ícone de suplemento da mensagem de relatório da Web do Outlook](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

> [!TIP]
> <span data-ttu-id="2c841-139">Como próxima etapa, saiba como [usar o suplemento de mensagem de relatório](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="2c841-139">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="2c841-140">Obter e habilitar o suplemento de mensagem de relatório para sua organização</span><span class="sxs-lookup"><span data-stu-id="2c841-140">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c841-141">Você deve ser um administrador global do Office 365 ou um administrador do Exchange Online para concluir essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="2c841-141">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span> <span data-ttu-id="2c841-142">Além disso, o Exchange deve ser configurado para usar a autenticação OAuth para saber mais, consulte [Exchange Requirements (implantação centralizada de suplementos)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="2c841-142">In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

1. <span data-ttu-id="2c841-143">Vá até a [página serviços & suplementos](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c841-143">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span>

   ![Página serviços e suplementos no novo centro de administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="2c841-145">Escolha **+ implantar suplemento**.</span><span class="sxs-lookup"><span data-stu-id="2c841-145">Choose **+ Deploy Add-in**.</span></span>

   ![Escolha implantar suplemento](../../media/ServicesAddIns-ChooseDeployAddIn.png)

3. <span data-ttu-id="2c841-147">Na tela **novo suplemento** , revise as informações e, em seguida, escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2c841-147">In the **New Add-In** screen, review the information, and then choose **Next**.</span></span>

   ![Novos detalhes do suplemento](../../media/NewAddInScreen1.png)

4. <span data-ttu-id="2c841-149">Selecione **desejo adicionar um suplemento da Office Store**e, em seguida, escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2c841-149">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span>

   ![Desejo adicionar um novo suplemento](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="2c841-151">Procure por **mensagem de relatório**e, na lista de resultados, ao lado do **suplemento de mensagem de relatório**, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2c841-151">Search for **Report Message**, and in the list of results, next to the **Report Message Add-In**, choose **Add**.</span></span>

   ![Procure por mensagem de relatório e escolha Adicionar](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="2c841-153">Na tela de **mensagens de relatório** , revise as informações e, em seguida, escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2c841-153">On the **Report Message** screen, review the information, and then choose **Next**.</span></span>

   ![Detalhes da mensagem de relatório](../../media/ReportMessageAdd-InNewScreen4.png)

7. <span data-ttu-id="2c841-155">Especifique as configurações padrão do usuário para o Outlook e, em seguida, escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2c841-155">Specify the user default settings for Outlook, and  then choose **Next**.</span></span>

   ![Configurações padrão de mensagens de relatório para o Outlook](../../media/ReportMessageOptionsScreen5.png)

8. <span data-ttu-id="2c841-157">Especifique quem recebe o suplemento de mensagem de relatório e, em seguida, escolha **salvar**.</span><span class="sxs-lookup"><span data-stu-id="2c841-157">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span>

   ![Quem recebe o suplemento de mensagem de relatório](../../media/ReportMessageOptionsScreen6.png)

> [!TIP]
> <span data-ttu-id="2c841-159">Recomendamos [Configurar uma regra para obter uma cópia das mensagens de email relatadas por seus usuários](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span><span class="sxs-lookup"><span data-stu-id="2c841-159">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span></span>

<span data-ttu-id="2c841-160">Dependendo do que você selecionou quando configurou o suplemento (etapas 7-8 acima), as pessoas em sua organização terão o [suplemento de mensagem de relatório](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) disponível.</span><span class="sxs-lookup"><span data-stu-id="2c841-160">Depending on what you selected when you set up the add-in (steps 7-8 above), people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available.</span></span> <span data-ttu-id="2c841-161">As pessoas na sua organização verão os seguintes ícones:</span><span class="sxs-lookup"><span data-stu-id="2c841-161">People in your organization will see the following icons:</span></span>

- <span data-ttu-id="2c841-162">No Outlook, o ícone tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="2c841-162">In Outlook, the icon looks like this:</span></span>

  ![Ícone de suplemento de mensagem de relatório para Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="2c841-164">No Outlook na Web, o ícone tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="2c841-164">In Outlook on the web, the icon looks like this:</span></span>

  ![Ícone de suplemento da mensagem de relatório da Web do Outlook](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

> [!TIP]
> <span data-ttu-id="2c841-166">Ao notificar os usuários sobre o suplemento de mensagens de relatório, inclua um link para [usar o suplemento de mensagem de relatório](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="2c841-166">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="2c841-167">Configurar uma regra para obter uma cópia das mensagens de email relatadas por seus usuários</span><span class="sxs-lookup"><span data-stu-id="2c841-167">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c841-168">Você deve ser um administrador do Exchange Online para executar essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="2c841-168">You must be an Exchange Online Administrator to perform this task.</span></span>

<span data-ttu-id="2c841-169">Você pode configurar uma regra para obter uma cópia das mensagens de email relatadas por usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="2c841-169">You can set up a rule to get a copy of email messages reported by users in your organization.</span></span> <span data-ttu-id="2c841-170">Faça isso depois de baixar e habilitar o suplemento de mensagem de relatório para sua organização.</span><span class="sxs-lookup"><span data-stu-id="2c841-170">You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>

1. <span data-ttu-id="2c841-171">No centro de administração do Exchange, escolha **regras**de **fluxo** \> de email.</span><span class="sxs-lookup"><span data-stu-id="2c841-171">In the Exchange admin center, choose **mail flow** \> **rules**.</span></span>

2. <span data-ttu-id="2c841-172">Escolha **+** \> **criar uma nova regra**.</span><span class="sxs-lookup"><span data-stu-id="2c841-172">Choose **+** \> **Create a new rule**.</span></span>

3. <span data-ttu-id="2c841-173">Na caixa **nome** , digite um nome, como envios.</span><span class="sxs-lookup"><span data-stu-id="2c841-173">In the **Name** box, type a name, such as Submissions.</span></span>

4. <span data-ttu-id="2c841-174">Na lista **aplicar esta regra se** , escolha **o endereço do destinatário inclui..**.</span><span class="sxs-lookup"><span data-stu-id="2c841-174">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span>

5. <span data-ttu-id="2c841-175">Na tela **especificar palavras ou frases** , adicione `junk@office365.microsoft.com` e `phish@office365.microsoft.com`, em seguida, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c841-175">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span>

   ![Especificar os endereços de email de lixo eletrônico e phishing da regra](../../media/018c1833-f336-4333-a45c-f2e8b75cd698.png)

6. <span data-ttu-id="2c841-177">Na lista **faça o seguinte...** , escolha **Cco a mensagem para..**..</span><span class="sxs-lookup"><span data-stu-id="2c841-177">In the **Do the following...** list, choose **Bcc the message to...**.</span></span>

7. <span data-ttu-id="2c841-178">Adicione um administrador global, um administrador de segurança e/ou um leitor de segurança que deve receber uma cópia de cada mensagem de email que as pessoas relatam à Microsoft e, em seguida, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c841-178">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span>

   ![Adicionar um administrador global ou de segurança para receber uma cópia de cada mensagem relatada](../../media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)

8. <span data-ttu-id="2c841-180">Selecione **auditar esta regra com nível de severidade**e escolha **médio**.</span><span class="sxs-lookup"><span data-stu-id="2c841-180">Select **Audit this rule with severity level**, and choose **Medium**.</span></span>

9. <span data-ttu-id="2c841-181">Em **escolher um modo para essa regra**, escolha **impor**.</span><span class="sxs-lookup"><span data-stu-id="2c841-181">Under **Choose a mode for this rule**, choose **Enforce**.</span></span>

   ![Configurar uma regra para obter uma cópia de cada mensagem relatada](../../media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)

10. <span data-ttu-id="2c841-183">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2c841-183">Choose **Save**.</span></span>

<span data-ttu-id="2c841-184">Com essa regra em vigor, sempre que alguém em sua organização relatar uma mensagem de email usando o suplemento de mensagem de relatório, seu administrador global, administrador de segurança e/ou leitor de segurança receberá uma cópia dessa mensagem.</span><span class="sxs-lookup"><span data-stu-id="2c841-184">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message.</span></span> <span data-ttu-id="2c841-185">Essas informações podem permitir que você configure ou ajuste políticas, como as políticas de [links seguros de ATP do Office 365](atp-safe-links.md) ou suas configurações [antispam](anti-spam-protection.md) .</span><span class="sxs-lookup"><span data-stu-id="2c841-185">This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies, or your [anti-spam](anti-spam-protection.md) settings.</span></span>

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="2c841-186">Saiba como usar o suplemento de mensagem de relatório</span><span class="sxs-lookup"><span data-stu-id="2c841-186">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="2c841-187">Confira [usar o suplemento de mensagem de relatório](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="2c841-187">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="2c841-188">Revise ou edite as configurações do suplemento de mensagem de relatório</span><span class="sxs-lookup"><span data-stu-id="2c841-188">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="2c841-189">Você pode revisar e editar as configurações padrão para o suplemento de mensagem de relatório na [página de suplementos de serviços &](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span><span class="sxs-lookup"><span data-stu-id="2c841-189">You can review and edit the default settings for the Report Message add-in on the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c841-190">Você deve ser um administrador global do Office 365 ou um administrador do Exchange Online para concluir essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="2c841-190">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>

1. <span data-ttu-id="2c841-191">Vá até a [página serviços & suplementos](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c841-191">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span>

   ![Página serviços e suplementos no novo centro de administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="2c841-193">Localize e selecione o suplemento de mensagem de relatório.</span><span class="sxs-lookup"><span data-stu-id="2c841-193">Find and select the Report Message add-in.</span></span>

   ![Localizar e selecionar o suplemento de mensagem de relatório](../../media/FindReportMessageAddIn.png)

3. <span data-ttu-id="2c841-195">Na tela de mensagens de relatório, revise e edite as configurações conforme apropriado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="2c841-195">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span>

   ![Configurações para o suplemento de mensagem de relatório](../../media/EditReportMessageAddIn.png)

## <a name="related-topics"></a><span data-ttu-id="2c841-197">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2c841-197">Related topics</span></span>

[<span data-ttu-id="2c841-198">Usar o suplemento de mensagem de relatório</span><span class="sxs-lookup"><span data-stu-id="2c841-198">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

[<span data-ttu-id="2c841-199">Exibir relatórios de segurança de email no &amp; centro de conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="2c841-199">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="2c841-200">Exibir relatórios para a proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="2c841-200">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="2c841-201">Usar o Explorer no centro &amp; de conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="2c841-201">Use Explorer in the Security &amp; Compliance Center</span></span>](threat-explorer.md)
