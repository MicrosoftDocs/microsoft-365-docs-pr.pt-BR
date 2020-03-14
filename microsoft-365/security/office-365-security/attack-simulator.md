---
title: Simulador de ataque no Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: Use o simulador de ataques para executar ataques simulados de phishing e senha na sua organização do Office 365 E5 ou ATP plano 2, que pode ajudá-lo a identificar usuários vulneráveis antes que um ataque real atinja sua empresa.
ms.openlocfilehash: 95b7af302a5dcc1987040c23a7dde867e2d09292
ms.sourcegitcommit: 08a4ee7765f3eba42f0c037c5c564c581e45df3e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42637334"
---
# <a name="attack-simulator-in-office-365-atp"></a><span data-ttu-id="ef15e-103">Simulador de ataque no Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="ef15e-103">Attack Simulator in Office 365 ATP</span></span>

<span data-ttu-id="ef15e-104">Simulador de ataque no Office 365 o plano de proteção avançada contra ameaças (plano ATP 2) permite que você execute as campanhas realísticas, mas phishing e de ataques de senha simuladas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ef15e-104">Attack Simulator in Office 365 Advanced Threat Protection Plan 2 (ATP Plan 2) allows you to run realistic, but simulated phishing and password attack campaigns in your organization.</span></span> <span data-ttu-id="ef15e-105">Você pode usar os resultados de campanhas para identificar e treinar usuários vulneráveis.</span><span class="sxs-lookup"><span data-stu-id="ef15e-105">You can use the results of campaigns to identify and train vulnerable users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ef15e-106">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="ef15e-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ef15e-107">Para abrir o centro de conformidade & segurança do Office 365, <https://protection.office.com/>vá para.</span><span class="sxs-lookup"><span data-stu-id="ef15e-107">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="ef15e-108">O simulador de ataque está disponível no **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-108">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span>

  ![Gerenciamento de ameaças-simulador de ataques](../../media/ThreatMgmt-AttackSimulator.png)

- <span data-ttu-id="ef15e-110">Para obter mais informações sobre a disponibilidade do simulador de ataque em assinaturas diferentes do Office 365, confira [Descrição do serviço de proteção avançada contra ameaças do office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="ef15e-110">For more information about the availability of Attack Simulator across different Office 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="ef15e-111">Você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de administrador de **segurança** .</span><span class="sxs-lookup"><span data-stu-id="ef15e-111">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="ef15e-112">Para obter mais informações sobre grupos de função no centro de conformidade & segurança, consulte [permissões no centro de conformidade & segurança do Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ef15e-112">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="ef15e-113">Sua conta precisa ser configurada para a MFA (autenticação multifator) para criar e gerenciar campanhas no simulador de ataques.</span><span class="sxs-lookup"><span data-stu-id="ef15e-113">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="ef15e-114">Para obter instruções, consulte [Configurar a autenticação multifator](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="ef15e-114">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="ef15e-115">Você só pode executar campanhas de phishing ou de ataques de senha em usuários com caixas de correio no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ef15e-115">You can only run phishing or password attack campaigns on users with mailboxes in Exchange Online.</span></span>

- <span data-ttu-id="ef15e-116">Campanhas de phishing coletam e processam eventos por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="ef15e-116">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="ef15e-117">Dados de campanha históricos estarão disponíveis por até 90 dias após a execução da campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-117">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="ef15e-118">Não há cmdlets do PowerShell correspondentes para o simulador de ataques.</span><span class="sxs-lookup"><span data-stu-id="ef15e-118">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="ef15e-119">Campanhas de spear phishing</span><span class="sxs-lookup"><span data-stu-id="ef15e-119">Spear phishing campaigns</span></span>

<span data-ttu-id="ef15e-120">*Phishing* é um termo genérico para ataques de email que tentam roubar informações confidenciais em mensagens que parecem ser de remetentes legítimos ou confiáveis.</span><span class="sxs-lookup"><span data-stu-id="ef15e-120">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="ef15e-121">O *spear phishing* é um ataque de phishing direcionado que usa conteúdo muito focalizado e personalizado que é especificamente ajustado para os destinatários direcionados (normalmente, após o reconhecimento dos destinatários pelo invasor).</span><span class="sxs-lookup"><span data-stu-id="ef15e-121">*Spear phishing* is a targeted phishing attack that uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="ef15e-122">Para obter mais informações sobre phishing e spear phishing, consulte [phishing](https://docs.microsoft.com/windows/security/threat-protection/intelligence/phishing).</span><span class="sxs-lookup"><span data-stu-id="ef15e-122">For more information about phishing and spear phishing, see [Phishing](https://docs.microsoft.com/windows/security/threat-protection/intelligence/phishing).</span></span>

<span data-ttu-id="ef15e-123">No simulador de ataques, dois tipos diferentes de campanhas de phishing de Spear estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="ef15e-123">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="ef15e-124">**Spear phishing (coleta de credenciais)**: o ataque tenta convencer os destinatários a clicar em uma URL na mensagem.</span><span class="sxs-lookup"><span data-stu-id="ef15e-124">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="ef15e-125">Se clicar no link, os usuários serão solicitados a inserir suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="ef15e-125">If they click the link, users are asked to enter their credentials.</span></span> <span data-ttu-id="ef15e-126">Se o fizerem, eles serão levados a um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="ef15e-126">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="ef15e-127">Uma página padrão que explica isso era um teste apenas e fornece dicas para reconhecer mensagens de phishing.</span><span class="sxs-lookup"><span data-stu-id="ef15e-127">A default page that explains this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![O que os usuários verão se clicarem no link phishing e inserirem suas credenciais](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="ef15e-129">Uma página personalizada (URL) que você especificar.</span><span class="sxs-lookup"><span data-stu-id="ef15e-129">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="ef15e-130">**Spear phishing (anexo)**: o ataque tenta convencer os destinatários a abrir um anexo. docx ou. pdf na mensagem.</span><span class="sxs-lookup"><span data-stu-id="ef15e-130">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="ef15e-131">O anexo contém o mesmo conteúdo do link phishing padrão, mas a primeira sentença começa com "\<nome\>de exibição, você está vendo esta mensagem como uma mensagem de email recente que você abriu...".</span><span class="sxs-lookup"><span data-stu-id="ef15e-131">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="ef15e-132">Atualmente, as campanhas de spear phishing no simulador de ataques não expiram.</span><span class="sxs-lookup"><span data-stu-id="ef15e-132">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="ef15e-133">Criar uma campanha de spear phishing</span><span class="sxs-lookup"><span data-stu-id="ef15e-133">Create a spear phishing campaign</span></span>

<span data-ttu-id="ef15e-134">Uma parte importante de qualquer campanha de spear phishing é a aparência da mensagem de email enviada aos destinatários de destino.</span><span class="sxs-lookup"><span data-stu-id="ef15e-134">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="ef15e-135">Para criar e configurar a mensagem de email, você tem estas opções:</span><span class="sxs-lookup"><span data-stu-id="ef15e-135">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="ef15e-136">**Use um modelo de email interno**: dois modelos internos estão disponíveis: **prêmios** e atualizações de folha de **pagamento**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-136">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="ef15e-137">Você pode personalizar ainda mais algumas, todas ou nenhuma das propriedades de email do modelo ao criar e iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-137">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="ef15e-138">**Criar um modelo de email reutilizável**: depois de criar e salvar o modelo de email, você pode usá-lo novamente em futuras campanhas de spear phishing.</span><span class="sxs-lookup"><span data-stu-id="ef15e-138">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="ef15e-139">Você pode personalizar ainda mais algumas, todas ou nenhuma das propriedades de email do modelo ao criar e iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-139">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="ef15e-140">**Criar a mensagem de email no assistente**: você pode criar a mensagem de email diretamente no assistente ao criar e iniciar a campanha de spear phishing.</span><span class="sxs-lookup"><span data-stu-id="ef15e-140">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="ef15e-141">Etapa 1 (opcional): criar um modelo de email personalizado</span><span class="sxs-lookup"><span data-stu-id="ef15e-141">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="ef15e-142">Se você for usar um dos modelos internos ou criar a mensagem de email diretamente no assistente, poderá pular esta etapa.</span><span class="sxs-lookup"><span data-stu-id="ef15e-142">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="ef15e-143">No centro de conformidade & segurança, vá para **Threat management** \> **simulador de ataque**de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="ef15e-143">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="ef15e-144">Na página **simular ataques** , nas seções **spear phishing (informações de coleta de credenciais)** ou **spear phishing (anexo)** , clique em **detalhes do ataque**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-144">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="ef15e-145">Não importa onde você crie o modelo.</span><span class="sxs-lookup"><span data-stu-id="ef15e-145">It doesn't matter where you create the template.</span></span> <span data-ttu-id="ef15e-146">As opções disponíveis no modelo são as mesmas para os dois tipos de ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="ef15e-146">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="ef15e-147">Na página **detalhes do ataque** que é aberta, na **seção modelos de phishing** , na área **criar modelos** , clique em **novo modelo**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-147">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="ef15e-148">O assistente para **Configurar modelo de phishing** é iniciado em um novo submenu.</span><span class="sxs-lookup"><span data-stu-id="ef15e-148">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="ef15e-149">Na etapa **Iniciar** , digite um nome de exibição exclusivo para o modelo e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-149">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="ef15e-150">Na etapa **Configurar detalhes de email** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="ef15e-150">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="ef15e-151">**De (nome)**: o nome de exibição que é usado para o remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="ef15e-151">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="ef15e-152">**De (email)**: o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="ef15e-152">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="ef15e-153">**URL do servidor de logon de phishing**: clique no menu suspenso e selecione uma das URLs disponíveis na lista.</span><span class="sxs-lookup"><span data-stu-id="ef15e-153">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="ef15e-154">Esta é a URL para a qual os usuários terão tentado clicar.</span><span class="sxs-lookup"><span data-stu-id="ef15e-154">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="ef15e-155">As opções são:</span><span class="sxs-lookup"><span data-stu-id="ef15e-155">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     > <ul><li><span data-ttu-id="ef15e-156">Todas as URLs são intencionalmente http, não HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ef15e-156">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="ef15e-157">Um serviço de reputação de URL pode identificar uma ou mais dessas URLs como não seguras.</span><span class="sxs-lookup"><span data-stu-id="ef15e-157">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="ef15e-158">Verifique a disponibilidade da URL nos navegadores da Web com suporte antes de usar a URL em uma campanha de phishing.</span><span class="sxs-lookup"><span data-stu-id="ef15e-158">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li></ul>

   - <span data-ttu-id="ef15e-159">**URL da página de aterrissagem personalizada**: Insira uma página de aterrissagem opcional, onde os usuários são conduzidos, caso eles cliquem no link phishing e insiram suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="ef15e-159">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="ef15e-160">Este link substitui a página de aterrissagem padrão.</span><span class="sxs-lookup"><span data-stu-id="ef15e-160">This link replaces the default landing page.</span></span> <span data-ttu-id="ef15e-161">Por exemplo, se você tiver um treinamento de conscientização interna, poderá especificar essa URL aqui.</span><span class="sxs-lookup"><span data-stu-id="ef15e-161">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="ef15e-162">**Categoria**: no momento, essa configuração não é usada (tudo o que você inserir será ignorado).</span><span class="sxs-lookup"><span data-stu-id="ef15e-162">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="ef15e-163">**Assunto**: o campo **assunto** da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="ef15e-163">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="ef15e-164">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-164">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="ef15e-165">Na etapa de **redação de email** , crie o corpo da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="ef15e-165">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="ef15e-166">Você pode usar a guia **email** (um editor de HTML avançado) ou a guia **fonte** (código HTML bruto).</span><span class="sxs-lookup"><span data-stu-id="ef15e-166">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="ef15e-167">A formatação HTML pode ser simples ou complexa, pois você precisará dela.</span><span class="sxs-lookup"><span data-stu-id="ef15e-167">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="ef15e-168">Você pode inserir imagens e texto para aprimorar o believability da mensagem no cliente de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="ef15e-168">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="ef15e-169">`${username}`Insere o nome do destinatário.</span><span class="sxs-lookup"><span data-stu-id="ef15e-169">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="ef15e-170">`${loginserverurl}`Insere o valor de **URL do servidor de logon de phishing** da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="ef15e-170">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="ef15e-171">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-171">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="ef15e-172">Na etapa **confirmar** , clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-172">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="ef15e-173">Etapa 2: criar e iniciar a campanha de spear phishing</span><span class="sxs-lookup"><span data-stu-id="ef15e-173">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="ef15e-174">No centro de conformidade & segurança, vá para **Threat management** \> **simulador de ataque**de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="ef15e-174">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="ef15e-175">Na página **simular ataques** , faça uma das seguintes seleções com base no tipo de campanha que você deseja criar:</span><span class="sxs-lookup"><span data-stu-id="ef15e-175">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="ef15e-176">Na seção **spear phishing (coleta de credenciais)** , clique em **Iniciar ataque** ou clique em **detalhes** \> do ataque de **lançamento**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-176">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="ef15e-177">Na seção **spear phishing (anexo)** , clique em **Iniciar ataque** ou clique em **detalhes** \> do ataque de **lançamento**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-177">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="ef15e-178">O assistente para **configurar ataques de phishing** é iniciado em um novo submenu.</span><span class="sxs-lookup"><span data-stu-id="ef15e-178">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="ef15e-179">Na etapa **Iniciar** , execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="ef15e-179">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="ef15e-180">Na caixa **nome** , digite um nome de exibição exclusivo para a campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-180">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="ef15e-181">Não clique em **usar modelo**, porque você criará a mensagem de email mais tarde no assistente.</span><span class="sxs-lookup"><span data-stu-id="ef15e-181">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="ef15e-182">Clique em **usar modelo** e selecione um modelo de email interno ou personalizado.</span><span class="sxs-lookup"><span data-stu-id="ef15e-182">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="ef15e-183">Depois de selecionar o modelo, a caixa **nome** é preenchida automaticamente com base no modelo, mas você pode alterar o nome.</span><span class="sxs-lookup"><span data-stu-id="ef15e-183">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![Página de início de phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="ef15e-185">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-185">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="ef15e-186">Na etapa **destinatários de destino** , execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="ef15e-186">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="ef15e-187">Clique em **Catálogo de endereços** para selecionar os destinatários (usuários ou grupos) da campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-187">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="ef15e-188">Cada destinatário almejado deve ter uma caixa de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ef15e-188">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="ef15e-189">Se você clicar em **Filtrar** e **aplicar** sem inserir um critério de pesquisa, todos os destinatários serão retornados e adicionados à campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-189">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="ef15e-190">Clique em **importar** e em importar **arquivo** para importar um valor separado por vírgula (CSV) ou um arquivo separado por linha de endereços de email.</span><span class="sxs-lookup"><span data-stu-id="ef15e-190">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="ef15e-191">Cada linha deve conter o endereço de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="ef15e-191">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="ef15e-192">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-192">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="ef15e-193">Na etapa **Configurar detalhes de email** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="ef15e-193">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="ef15e-194">Se você selecionou um modelo na etapa de **início** , a maioria desses valores já está configurada, mas você pode alterá-los.</span><span class="sxs-lookup"><span data-stu-id="ef15e-194">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="ef15e-195">**De (nome)**: o nome de exibição que é usado para o remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="ef15e-195">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="ef15e-196">**De (email)**: o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="ef15e-196">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="ef15e-197">Você pode inserir um endereço de email verdadeiro ou falso no domínio de email da sua organização ou pode inserir um endereço de email externo real ou falso.</span><span class="sxs-lookup"><span data-stu-id="ef15e-197">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="ef15e-198">Um endereço de email válido de um remetente da sua organização será realmente resolvido no cliente de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="ef15e-198">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="ef15e-199">**URL do servidor de logon de phishing**: clique no menu suspenso e selecione uma das URLs disponíveis na lista.</span><span class="sxs-lookup"><span data-stu-id="ef15e-199">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="ef15e-200">Esta é a URL para a qual os usuários terão tentado clicar.</span><span class="sxs-lookup"><span data-stu-id="ef15e-200">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="ef15e-201">As opções são:</span><span class="sxs-lookup"><span data-stu-id="ef15e-201">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     > <ul><li><span data-ttu-id="ef15e-202">Todas as URLs são intencionalmente http, não HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ef15e-202">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="ef15e-203">Um serviço de reputação de URL pode identificar uma ou mais dessas URLs como não seguras.</span><span class="sxs-lookup"><span data-stu-id="ef15e-203">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="ef15e-204">Verifique a disponibilidade da URL nos navegadores da Web com suporte antes de usar a URL em uma campanha de phishing.</span><span class="sxs-lookup"><span data-stu-id="ef15e-204">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li><li><span data-ttu-id="ef15e-205">Você deve selecionar uma URL.</span><span class="sxs-lookup"><span data-stu-id="ef15e-205">You are required to select a URL.</span></span> <span data-ttu-id="ef15e-206">Para campanhas de <b>spear phishing (Attachment)</b> , você pode remover o link do corpo da mensagem na próxima etapa (caso contrário, a mensagem conterá um link <b>e</b> um anexo).</span><span class="sxs-lookup"><span data-stu-id="ef15e-206">For <b>Spear Phishing (Attachment)</b> campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link <b>and</b> an attachment).</span></span></li></ul>

   - <span data-ttu-id="ef15e-207">**Tipo de anexo**: essa configuração só está disponível em campanhas de **spear phishing (Attachment)** .</span><span class="sxs-lookup"><span data-stu-id="ef15e-207">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="ef15e-208">Clique na lista suspensa e selecione **. DOCX** ou **. PDF** na lista.</span><span class="sxs-lookup"><span data-stu-id="ef15e-208">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="ef15e-209">**Nome do anexo**: essa configuração só está disponível em campanhas de **spear phishing (Attachment)** .</span><span class="sxs-lookup"><span data-stu-id="ef15e-209">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="ef15e-210">Insira um nome de arquivo para o anexo. docx ou. pdf.</span><span class="sxs-lookup"><span data-stu-id="ef15e-210">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="ef15e-211">**URL da página de aterrissagem personalizada**: Insira uma página de aterrissagem opcional, onde os usuários são conduzidos, caso eles cliquem no link phishing e insiram suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="ef15e-211">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="ef15e-212">Este link substitui a página de aterrissagem padrão.</span><span class="sxs-lookup"><span data-stu-id="ef15e-212">This link replaces the default landing page.</span></span> <span data-ttu-id="ef15e-213">Por exemplo, se você tiver um treinamento de conscientização interna, poderá especificar essa URL aqui.</span><span class="sxs-lookup"><span data-stu-id="ef15e-213">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="ef15e-214">**Assunto**: o campo **assunto** da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="ef15e-214">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="ef15e-215">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-215">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="ef15e-216">Na etapa de **redação de email** , crie o corpo da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="ef15e-216">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="ef15e-217">Se você selecionou um modelo na etapa **Iniciar** , o corpo da mensagem já está configurado, mas você pode personalizá-lo.</span><span class="sxs-lookup"><span data-stu-id="ef15e-217">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="ef15e-218">Você pode usar a guia **email** (um editor de HTML avançado) ou a guia **fonte** (código HTML bruto).</span><span class="sxs-lookup"><span data-stu-id="ef15e-218">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="ef15e-219">A formatação HTML pode ser simples ou complexa, pois você precisará dela.</span><span class="sxs-lookup"><span data-stu-id="ef15e-219">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="ef15e-220">Você pode inserir imagens e texto para aprimorar o believability da mensagem no cliente de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="ef15e-220">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="ef15e-221">`${username}`Insere o nome do destinatário.</span><span class="sxs-lookup"><span data-stu-id="ef15e-221">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="ef15e-222">`${loginserverurl}`Insere o valor de **URL do servidor de logon de phishing** .</span><span class="sxs-lookup"><span data-stu-id="ef15e-222">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="ef15e-223">Para campanhas de **spear phishing (Attachment)** , você deve remover o link do corpo da mensagem (caso contrário, a mensagem conterá um link **e** um anexo e os cliques de link não serão rastreados em uma campanha de anexo).</span><span class="sxs-lookup"><span data-stu-id="ef15e-223">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![Redigir corpo de email](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="ef15e-225">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-225">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="ef15e-226">Na etapa **confirmar** , clique em **concluir** para iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-226">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="ef15e-227">A mensagem de phishing é entregue aos destinatários direcionados.</span><span class="sxs-lookup"><span data-stu-id="ef15e-227">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="ef15e-228">Campanhas de ataque por senha</span><span class="sxs-lookup"><span data-stu-id="ef15e-228">Password attack campaigns</span></span>

<span data-ttu-id="ef15e-229">Um *ataque de senha* tenta adivinhar senhas para contas de usuário em uma organização, normalmente após o invasor ter identificado uma ou mais contas de usuário válidas.</span><span class="sxs-lookup"><span data-stu-id="ef15e-229">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="ef15e-230">No simulador de ataques, dois tipos diferentes de campanhas de ataque por senha estão disponíveis para você testar a complexidade das senhas de seus usuários:</span><span class="sxs-lookup"><span data-stu-id="ef15e-230">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="ef15e-231">**Senha de força bruta (ataque de dicionário)**: um ataque de *força bruta* ou de *dicionário* usa um arquivo de dicionário grande de senhas em uma conta de usuário, com a esperança de que um deles funcionará (muitas senhas em uma conta).</span><span class="sxs-lookup"><span data-stu-id="ef15e-231">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="ef15e-232">Bloqueios de senha incorretos ajudam a evitar ataques de senha forçada.</span><span class="sxs-lookup"><span data-stu-id="ef15e-232">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="ef15e-233">Para o ataque de dicionário, você pode especificar uma ou várias senhas para tentar (inseridas manualmente ou em um arquivo carregado) e pode especificar um ou vários usuários.</span><span class="sxs-lookup"><span data-stu-id="ef15e-233">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="ef15e-234">**Ataque de irrigação de senha**: um ataque de *irrigação de senha* usa a mesma senha cuidadosamente considerada em uma lista de contas de usuário (uma senha em muitas contas).</span><span class="sxs-lookup"><span data-stu-id="ef15e-234">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="ef15e-235">Os ataques de irrigação de senha são mais difíceis de detectar que os ataques de senha de força bruta (a probabilidade de sucessos aumenta quando um invasor tenta uma senha em dezenas ou centenas de contas sem o risco de recorrer o bloqueio de senha incorreto do usuário).</span><span class="sxs-lookup"><span data-stu-id="ef15e-235">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="ef15e-236">Para o ataque de irrigação de senha, você só pode especificar uma senha para tentar, e você pode especificar um ou vários usuários.</span><span class="sxs-lookup"><span data-stu-id="ef15e-236">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="ef15e-237">Os ataques de senha no simulador de ataque passam solicitações de autenticação básicas de nome de usuário e senha para um ponto de extremidade, de modo que também funcionem com outros métodos de autenticação (AD FS, sincronização de hash de senha, passagem, PingFederate, etc.).</span><span class="sxs-lookup"><span data-stu-id="ef15e-237">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="ef15e-238">Para usuários que têm o MFA habilitado, mesmo que o ataque de senha Tente sua senha real, a tentativa sempre será registrada como uma falha (em outras palavras, os usuários da MFA nunca aparecerão na contagem de **tentativas bem-sucedidas** da campanha).</span><span class="sxs-lookup"><span data-stu-id="ef15e-238">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="ef15e-239">Este é o resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="ef15e-239">This is the expected result.</span></span> <span data-ttu-id="ef15e-240">A MFA é um método principal para ajudar a proteger contra ataques de senha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-240">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="ef15e-241">Criar e iniciar uma campanha de ataque de senha</span><span class="sxs-lookup"><span data-stu-id="ef15e-241">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="ef15e-242">No centro de conformidade & segurança, vá para **Threat management** \> **simulador de ataque**de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="ef15e-242">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="ef15e-243">Na página **simular ataques** , faça uma das seguintes seleções com base no tipo de campanha que você deseja criar:</span><span class="sxs-lookup"><span data-stu-id="ef15e-243">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="ef15e-244">Na seção **senha de força bruta (ataque de dicionário)** , clique em **Iniciar ataque** ou clique em **detalhes** \> do ataque de **lançamento**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-244">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="ef15e-245">na seção **ataque de irrigação de senha** , clique em **Iniciar ataque** ou em **detalhes** \> de **lançamento**de ataques.</span><span class="sxs-lookup"><span data-stu-id="ef15e-245">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="ef15e-246">O assistente **Configurar ataque de senha** é iniciado em um novo submenu.</span><span class="sxs-lookup"><span data-stu-id="ef15e-246">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="ef15e-247">Na etapa **Iniciar** , digite um nome de exibição exclusivo para a campanha e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-247">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="ef15e-248">Na etapa **usuários de destino** , execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="ef15e-248">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="ef15e-249">Clique em **Catálogo de endereços** para selecionar os destinatários (usuários ou grupos) da campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-249">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="ef15e-250">Cada destinatário almejado deve ter uma caixa de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ef15e-250">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="ef15e-251">Se você clicar em **Filtrar** e **aplicar** sem inserir um critério de pesquisa, todos os destinatários serão retornados e adicionados à campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-251">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="ef15e-252">Clique em **importar** e em importar **arquivo** para importar um valor separado por vírgula (CSV) ou um arquivo separado por linha de endereços de email.</span><span class="sxs-lookup"><span data-stu-id="ef15e-252">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="ef15e-253">Cada linha deve conter o endereço de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="ef15e-253">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="ef15e-254">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-254">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="ef15e-255">Na etapa **escolher as configurações de ataque** , escolha o que fazer com base no tipo de campanha:</span><span class="sxs-lookup"><span data-stu-id="ef15e-255">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="ef15e-256">**Senha de força bruta (ataque de dicionário)**: execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="ef15e-256">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="ef15e-257">**Inserir senhas manualmente**: na caixa **pressione ENTER para adicionar uma senha** , digite uma senha e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="ef15e-257">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="ef15e-258">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="ef15e-258">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="ef15e-259">**Carregar senhas de um arquivo de dicionário**: clique em **carregar** para importar um arquivo de texto existente que contenha uma senha em cada linha e uma última linha em branco.</span><span class="sxs-lookup"><span data-stu-id="ef15e-259">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="ef15e-260">O arquivo de texto deve ter 10 MB ou menos de tamanho e não pode conter mais de 30000 senhas.</span><span class="sxs-lookup"><span data-stu-id="ef15e-260">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="ef15e-261">**Ataque de irrigação de senha**: na caixa de entrada **(s) senha a ser usada no ataque** , digite uma senha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-261">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="ef15e-262">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-262">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="ef15e-263">Na etapa **confirmar** , clique em **concluir** para iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-263">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="ef15e-264">As senhas que você especificou são tentadas nos usuários que você especificou.</span><span class="sxs-lookup"><span data-stu-id="ef15e-264">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="ef15e-265">Exibir resultados da campanha</span><span class="sxs-lookup"><span data-stu-id="ef15e-265">View campaign results</span></span>

<span data-ttu-id="ef15e-266">Depois de iniciar uma campanha, você pode verificar o progresso e os resultados na página principal de **ataques de simulações** .</span><span class="sxs-lookup"><span data-stu-id="ef15e-266">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="ef15e-267">As campanhas ativas mostrarão uma barra de status, um valor de porcentagem concluído e a contagem "(usuários concluídos) de (total de usuários)".</span><span class="sxs-lookup"><span data-stu-id="ef15e-267">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="ef15e-268">Clicar no botão **Atualizar** atualizará o progresso de todas as campanhas ativas.</span><span class="sxs-lookup"><span data-stu-id="ef15e-268">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="ef15e-269">Você também pode clicar em **encerrar** para interromper uma campanha ativa.</span><span class="sxs-lookup"><span data-stu-id="ef15e-269">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="ef15e-270">Quando a campanha é concluída, o status é alterado para **ataque concluído**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-270">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="ef15e-271">Você pode exibir os resultados da campanha executando uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="ef15e-271">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="ef15e-272">Na página principais **ataques de simular** , clique em **Exibir relatório** sob o nome da campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-272">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="ef15e-273">Na página principal **simular ataques** , clique em **detalhes do ataque** na seção referente ao tipo de ataque.</span><span class="sxs-lookup"><span data-stu-id="ef15e-273">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="ef15e-274">Na página **detalhes do ataque** que é aberta, selecione a campanha na seção **histórico de ataques** .</span><span class="sxs-lookup"><span data-stu-id="ef15e-274">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="ef15e-275">Qualquer uma das ações anteriores levará você para uma página chamada **detalhes do ataque**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-275">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="ef15e-276">As informações disponíveis nesta página para cada tipo de campanha são descritas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="ef15e-276">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="ef15e-277">Resultados da campanha de spear phishing (coleta de credenciais)</span><span class="sxs-lookup"><span data-stu-id="ef15e-277">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="ef15e-278">As informações a seguir estão disponíveis na página de **detalhes do ataque** de cada campanha:</span><span class="sxs-lookup"><span data-stu-id="ef15e-278">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="ef15e-279">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-279">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="ef15e-280">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="ef15e-280">**Total users targeted**</span></span>

- <span data-ttu-id="ef15e-281">**Tentativas bem-sucedidas**: o número de usuários que clicaram no link **e** inseriram suas credenciais (*qualquer* nome de usuário e de senha).</span><span class="sxs-lookup"><span data-stu-id="ef15e-281">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="ef15e-282">**Taxa de êxito geral**: uma porcentagem calculada por **tentativas** / bem-sucedidas**total dos usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-282">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="ef15e-283">**Clique mais rápido**: quanto tempo levava o primeiro usuário a clicar no link depois que você iniciou a campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-283">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="ef15e-284">**Clique médio**: a soma de quanto tempo levava para todos clicar no link dividido pelo número de usuários que clicaram no link.</span><span class="sxs-lookup"><span data-stu-id="ef15e-284">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="ef15e-285">**Clique em taxa de êxito**: uma porcentagem calculada por (número de usuários que clicaram no link)/ **total de usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-285">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="ef15e-286">**Credenciais mais rápidas**: quanto tempo levava o primeiro usuário a inserir suas credenciais após o lançamento da campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-286">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="ef15e-287">**Média de credenciais**: a soma de quanto tempo levava para todos inserir suas credenciais divididas pelo número de usuários que inseriram suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="ef15e-287">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="ef15e-288">**Taxa de êxito da credencial**: uma porcentagem calculada por (número de usuários que inseriram suas credenciais)/ **total de usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-288">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="ef15e-289">Um gráfico de barras que mostra o **link clicado** e os números **fornecidos por credencial** por dia.</span><span class="sxs-lookup"><span data-stu-id="ef15e-289">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="ef15e-290">Um gráfico de círculo que mostra o **link clicado**, as **credenciais fornecidas**e **nenhuma** porcentagem para a campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-290">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="ef15e-291">A seção **usuários comprometidos** lista os detalhes dos usuários que clicaram no link:</span><span class="sxs-lookup"><span data-stu-id="ef15e-291">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="ef15e-292">O endereço de email do usuário</span><span class="sxs-lookup"><span data-stu-id="ef15e-292">The user's email address</span></span>

  - <span data-ttu-id="ef15e-293">A data/hora em que o link foi clicado.</span><span class="sxs-lookup"><span data-stu-id="ef15e-293">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="ef15e-294">O endereço IP do cliente.</span><span class="sxs-lookup"><span data-stu-id="ef15e-294">The client IP address.</span></span>

  - <span data-ttu-id="ef15e-295">Detalhes sobre a versão do usuário do Windows e do navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="ef15e-295">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="ef15e-296">Você pode clicar em **Exportar** para exportar os resultados para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="ef15e-296">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="ef15e-297">Resultados da campanha de spear phishing (Attachment)</span><span class="sxs-lookup"><span data-stu-id="ef15e-297">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="ef15e-298">As informações a seguir estão disponíveis na página de **detalhes do ataque** de cada campanha:</span><span class="sxs-lookup"><span data-stu-id="ef15e-298">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="ef15e-299">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-299">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="ef15e-300">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="ef15e-300">**Total users targeted**</span></span>

- <span data-ttu-id="ef15e-301">**Tentativas bem-sucedidas**: o número de usuários que abriram ou baixaram e abriram o anexo (a visualização não conta).</span><span class="sxs-lookup"><span data-stu-id="ef15e-301">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="ef15e-302">**Taxa de êxito geral**: uma porcentagem calculada por **tentativas** / bem-sucedidas**total dos usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-302">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="ef15e-303">**Tempo de abertura do anexo mais rápido**: quanto tempo levava o primeiro usuário a abrir o anexo depois que você iniciou a campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-303">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="ef15e-304">**Tempo médio de abertura do anexo**: a soma de quanto tempo levava todos para abrir o anexo dividido pelo número de usuários que abriram o anexo.</span><span class="sxs-lookup"><span data-stu-id="ef15e-304">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="ef15e-305">**Taxa de êxito na abertura do anexo**: uma porcentagem calculada por (número de usuários que abriram o anexo)/ **total de usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-305">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="ef15e-306">Senha de força bruta (ataque de dicionário) resultados da campanha</span><span class="sxs-lookup"><span data-stu-id="ef15e-306">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="ef15e-307">As informações a seguir estão disponíveis na página de **detalhes do ataque** de cada campanha:</span><span class="sxs-lookup"><span data-stu-id="ef15e-307">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="ef15e-308">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-308">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="ef15e-309">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="ef15e-309">**Total users targeted**</span></span>

- <span data-ttu-id="ef15e-310">**Tentativas bem-sucedidas**: o número de usuários que foram encontrados usando uma das senhas especificadas.</span><span class="sxs-lookup"><span data-stu-id="ef15e-310">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="ef15e-311">**Taxa de êxito geral**: uma porcentagem calculada por **tentativas** / bem-sucedidas**total dos usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-311">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="ef15e-312">A seção **usuários comprometidos** lista os endereços de email dos usuários afetados.</span><span class="sxs-lookup"><span data-stu-id="ef15e-312">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="ef15e-313">Você pode clicar em **Exportar** para exportar os resultados para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="ef15e-313">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="ef15e-314">Resultados da campanha de ataque de irrigação de senha</span><span class="sxs-lookup"><span data-stu-id="ef15e-314">Password spray attack campaign results</span></span>

<span data-ttu-id="ef15e-315">As informações a seguir estão disponíveis na página de **detalhes do ataque** de cada campanha:</span><span class="sxs-lookup"><span data-stu-id="ef15e-315">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="ef15e-316">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="ef15e-316">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="ef15e-317">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="ef15e-317">**Total users targeted**</span></span>

- <span data-ttu-id="ef15e-318">**Tentativas bem-sucedidas**: o número de usuários que foram encontrados usando a senha especificada.</span><span class="sxs-lookup"><span data-stu-id="ef15e-318">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="ef15e-319">**Taxa de êxito geral**: uma porcentagem calculada por **tentativas** / bem-sucedidas**total dos usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="ef15e-319">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
