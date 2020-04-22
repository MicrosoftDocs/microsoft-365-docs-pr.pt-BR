---
title: Simulador de ataque em ATP
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
description: Como administrador global, você pode usar o simulador de ataques para executar cenários de ataque realísticos em sua organização. Isso pode ajudá-lo a identificar e encontrar usuários vulneráveis antes que um ataque real atinja sua empresa.
ms.openlocfilehash: cac09ed48a46531ea2246f9c3ef798649dc73196
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638567"
---
# <a name="attack-simulator-in-atp"></a><span data-ttu-id="6089f-104">Simulador de ataque em ATP</span><span class="sxs-lookup"><span data-stu-id="6089f-104">Attack Simulator in ATP</span></span>

<span data-ttu-id="6089f-105">**Resumo** Se você for um administrador global ou um administrador de segurança e sua organização tiver o Office 365 Advanced Threat Protection Plan 2, que inclui os [recursos de investigação e resposta contra ameaças](office-365-ti.md), você poderá usar o simulador de ataques para executar cenários de ataque realísticos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6089f-105">**Summary** If you are a global administrator or a security administrator and your organization has Office 365 Advanced Threat Protection Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="6089f-106">Isso pode ajudar você a identificar e a encontrar usuários vulneráveis, antes que um ataque real afete o resultado.</span><span class="sxs-lookup"><span data-stu-id="6089f-106">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="6089f-107">Leia este artigo para saber mais.</span><span class="sxs-lookup"><span data-stu-id="6089f-107">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6089f-108">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="6089f-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6089f-109">Para abrir o centro de conformidade & segurança, vá <https://protection.office.com/>para.</span><span class="sxs-lookup"><span data-stu-id="6089f-109">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="6089f-110">O simulador de ataque está disponível no **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="6089f-110">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span>

  ![Gerenciamento de ameaças-simulador de ataques](../../media/ThreatMgmt-AttackSimulator.png)

- <span data-ttu-id="6089f-112">Para obter mais informações sobre a disponibilidade do simulador de ataque em assinaturas diferentes da Microsoft 365, confira [Descrição do serviço de proteção avançada contra ameaças do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="6089f-112">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="6089f-113">Você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de administrador de **segurança** .</span><span class="sxs-lookup"><span data-stu-id="6089f-113">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="6089f-114">Para obter mais informações sobre grupos de função no centro de conformidade de & de segurança, consulte [permissões no centro de conformidade de & de segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6089f-114">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="6089f-115">Sua conta precisa ser configurada para a MFA (autenticação multifator) para criar e gerenciar campanhas no simulador de ataques.</span><span class="sxs-lookup"><span data-stu-id="6089f-115">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="6089f-116">Para obter instruções, consulte [Configurar a autenticação multifator](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="6089f-116">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

<span data-ttu-id="6089f-117">Para que um ataque seja iniciado com êxito, certifique-se de que a conta que você está usando para executar ataques simulados esteja usando a autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="6089f-117">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="6089f-118">Além disso, você deve ser um administrador global ou um administrador de segurança.</span><span class="sxs-lookup"><span data-stu-id="6089f-118">In addition, you must be a global administrator or a security administrator.</span></span> <span data-ttu-id="6089f-119">(Para saber mais sobre funções e permissões, consulte [permissões no centro de conformidade de & de segurança](permissions-in-the-security-and-compliance-center.md).)</span><span class="sxs-lookup"><span data-stu-id="6089f-119">(To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

- <span data-ttu-id="6089f-120">Campanhas de phishing coletam e processam eventos por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="6089f-120">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="6089f-121">Dados de campanha históricos estarão disponíveis por até 90 dias após a execução da campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-121">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="6089f-122">Não há cmdlets do PowerShell correspondentes para o simulador de ataques.</span><span class="sxs-lookup"><span data-stu-id="6089f-122">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="6089f-123">Campanhas de spear phishing</span><span class="sxs-lookup"><span data-stu-id="6089f-123">Spear phishing campaigns</span></span>

<span data-ttu-id="6089f-124">*Phishing* é um termo genérico para ataques de email que tentam roubar informações confidenciais em mensagens que parecem ser de remetentes legítimos ou confiáveis.</span><span class="sxs-lookup"><span data-stu-id="6089f-124">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="6089f-125">O *spear phishing* é um ataque de phishing direcionado que usa conteúdo muito focalizado e personalizado que é especificamente ajustado para os destinatários direcionados (normalmente, após o reconhecimento dos destinatários pelo invasor).</span><span class="sxs-lookup"><span data-stu-id="6089f-125">*Spear phishing* is a targeted phishing attack that uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="6089f-126">Você é um administrador global ou administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="6089f-126">You are a global administrator or security administrator</span></span>

<span data-ttu-id="6089f-127">No simulador de ataques, dois tipos diferentes de campanhas de phishing de Spear estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="6089f-127">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="6089f-128">A [autenticação multifator/acesso condicional](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) está ativada, por pelo menos a conta de administrador global e os administradores de segurança que usarão o simulador de ataques.</span><span class="sxs-lookup"><span data-stu-id="6089f-128">[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) is turned on, for at least the global administrator account and security administrators who will be using Attack Simulator.</span></span> <span data-ttu-id="6089f-129">(Idealmente, a autenticação multifator/acesso condicional está ativada para todos os usuários da sua organização.)</span><span class="sxs-lookup"><span data-stu-id="6089f-129">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>

  - <span data-ttu-id="6089f-130">Uma página padrão que explica isso era um teste apenas e fornece dicas para reconhecer mensagens de phishing.</span><span class="sxs-lookup"><span data-stu-id="6089f-130">A default page that explains this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![O que os usuários verão se clicarem no link phishing e inserirem suas credenciais](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="6089f-132">Uma página personalizada (URL) que você especificar.</span><span class="sxs-lookup"><span data-stu-id="6089f-132">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="6089f-133">**Spear phishing (anexo)**: o ataque tenta convencer os destinatários a abrir um anexo. docx ou. pdf na mensagem.</span><span class="sxs-lookup"><span data-stu-id="6089f-133">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="6089f-134">O anexo contém o mesmo conteúdo do link phishing padrão, mas a primeira sentença começa com "\<nome\>de exibição, você está vendo esta mensagem como uma mensagem de email recente que você abriu...".</span><span class="sxs-lookup"><span data-stu-id="6089f-134">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="6089f-135">Atualmente, as campanhas de spear phishing no simulador de ataques não expiram.</span><span class="sxs-lookup"><span data-stu-id="6089f-135">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="6089f-136">Criar uma campanha de spear phishing</span><span class="sxs-lookup"><span data-stu-id="6089f-136">Create a spear phishing campaign</span></span>

<span data-ttu-id="6089f-137">Uma parte importante de qualquer campanha de spear phishing é a aparência da mensagem de email enviada aos destinatários de destino.</span><span class="sxs-lookup"><span data-stu-id="6089f-137">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="6089f-138">Para criar e configurar a mensagem de email, você tem estas opções:</span><span class="sxs-lookup"><span data-stu-id="6089f-138">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="6089f-139">**Use um modelo de email interno**: dois modelos internos estão disponíveis: **prêmios** e atualizações de folha de **pagamento**.</span><span class="sxs-lookup"><span data-stu-id="6089f-139">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="6089f-140">Você pode personalizar ainda mais algumas, todas ou nenhuma das propriedades de email do modelo ao criar e iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-140">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="6089f-141">**Criar um modelo de email reutilizável**: depois de criar e salvar o modelo de email, você pode usá-lo novamente em futuras campanhas de spear phishing.</span><span class="sxs-lookup"><span data-stu-id="6089f-141">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="6089f-142">Você pode personalizar ainda mais algumas, todas ou nenhuma das propriedades de email do modelo ao criar e iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-142">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="6089f-143">**Criar a mensagem de email no assistente**: você pode criar a mensagem de email diretamente no assistente ao criar e iniciar a campanha de spear phishing.</span><span class="sxs-lookup"><span data-stu-id="6089f-143">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="6089f-144">Etapa 1 (opcional): criar um modelo de email personalizado</span><span class="sxs-lookup"><span data-stu-id="6089f-144">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="6089f-145">Se você for usar um dos modelos internos ou criar a mensagem de email diretamente no assistente, poderá pular esta etapa.</span><span class="sxs-lookup"><span data-stu-id="6089f-145">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="6089f-146">No centro de conformidade & segurança, vá para **Threat management** \> **simulador de ataque**de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="6089f-146">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="6089f-147">Na página **simular ataques** , nas seções **spear phishing (informações de coleta de credenciais)** ou **spear phishing (anexo)** , clique em **detalhes do ataque**.</span><span class="sxs-lookup"><span data-stu-id="6089f-147">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="6089f-148">Não importa onde você crie o modelo.</span><span class="sxs-lookup"><span data-stu-id="6089f-148">It doesn't matter where you create the template.</span></span> <span data-ttu-id="6089f-149">As opções disponíveis no modelo são as mesmas para os dois tipos de ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="6089f-149">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="6089f-150">Na página **detalhes do ataque** que é aberta, na **seção modelos de phishing** , na área **criar modelos** , clique em **novo modelo**.</span><span class="sxs-lookup"><span data-stu-id="6089f-150">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="6089f-151">O assistente para **Configurar modelo de phishing** é iniciado em um novo submenu.</span><span class="sxs-lookup"><span data-stu-id="6089f-151">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="6089f-152">Na etapa **Iniciar** , digite um nome de exibição exclusivo para o modelo e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6089f-152">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="6089f-153">Na etapa **Configurar detalhes de email** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="6089f-153">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="6089f-154">**De (nome)**: o nome de exibição que é usado para o remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="6089f-154">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="6089f-155">**De (email)**: o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="6089f-155">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="6089f-156">**URL do servidor de logon de phishing**: clique no menu suspenso e selecione uma das URLs disponíveis na lista.</span><span class="sxs-lookup"><span data-stu-id="6089f-156">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="6089f-157">Esta é a URL para a qual os usuários terão tentado clicar.</span><span class="sxs-lookup"><span data-stu-id="6089f-157">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="6089f-158">As opções são:</span><span class="sxs-lookup"><span data-stu-id="6089f-158">The choices are:</span></span>

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
     > <ul><li><span data-ttu-id="6089f-159">Todas as URLs são intencionalmente http, não HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6089f-159">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="6089f-160">Um serviço de reputação de URL pode identificar uma ou mais dessas URLs como não seguras.</span><span class="sxs-lookup"><span data-stu-id="6089f-160">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="6089f-161">Verifique a disponibilidade da URL nos navegadores da Web com suporte antes de usar a URL em uma campanha de phishing.</span><span class="sxs-lookup"><span data-stu-id="6089f-161">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li></ul>

   - <span data-ttu-id="6089f-162">**URL da página de aterrissagem personalizada**: Insira uma página de aterrissagem opcional, onde os usuários são conduzidos, caso eles cliquem no link phishing e insiram suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="6089f-162">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="6089f-163">Este link substitui a página de aterrissagem padrão.</span><span class="sxs-lookup"><span data-stu-id="6089f-163">This link replaces the default landing page.</span></span> <span data-ttu-id="6089f-164">Por exemplo, se você tiver um treinamento de conscientização interna, poderá especificar essa URL aqui.</span><span class="sxs-lookup"><span data-stu-id="6089f-164">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="6089f-165">**Categoria**: no momento, essa configuração não é usada (tudo o que você inserir será ignorado).</span><span class="sxs-lookup"><span data-stu-id="6089f-165">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="6089f-166">**Assunto**: o campo **assunto** da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="6089f-166">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="6089f-167">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6089f-167">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6089f-168">Na etapa de **redação de email** , crie o corpo da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="6089f-168">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="6089f-169">Você pode usar a guia **email** (um editor de HTML avançado) ou a guia **fonte** (código HTML bruto).</span><span class="sxs-lookup"><span data-stu-id="6089f-169">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="6089f-170">A formatação HTML pode ser simples ou complexa, pois você precisará dela.</span><span class="sxs-lookup"><span data-stu-id="6089f-170">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="6089f-171">Você pode inserir imagens e texto para aprimorar o believability da mensagem no cliente de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="6089f-171">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="6089f-172">`${username}`Insere o nome do destinatário.</span><span class="sxs-lookup"><span data-stu-id="6089f-172">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="6089f-173">`${loginserverurl}`Insere o valor de **URL do servidor de logon de phishing** da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="6089f-173">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="6089f-174">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6089f-174">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="6089f-175">Na etapa **confirmar** , clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="6089f-175">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="6089f-176">Etapa 2: criar e iniciar a campanha de spear phishing</span><span class="sxs-lookup"><span data-stu-id="6089f-176">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="6089f-177">No centro de conformidade & segurança, vá para **Threat management** \> **simulador de ataque**de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="6089f-177">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="6089f-178">Na página **simular ataques** , faça uma das seguintes seleções com base no tipo de campanha que você deseja criar:</span><span class="sxs-lookup"><span data-stu-id="6089f-178">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="6089f-179">Na seção **spear phishing (coleta de credenciais)** , clique em **Iniciar ataque** ou clique em **detalhes** \> do ataque de **lançamento**.</span><span class="sxs-lookup"><span data-stu-id="6089f-179">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="6089f-180">Na seção **spear phishing (anexo)** , clique em **Iniciar ataque** ou clique em **detalhes** \> do ataque de **lançamento**.</span><span class="sxs-lookup"><span data-stu-id="6089f-180">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="6089f-181">O assistente para **configurar ataques de phishing** é iniciado em um novo submenu.</span><span class="sxs-lookup"><span data-stu-id="6089f-181">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="6089f-182">Na etapa **Iniciar** , execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="6089f-182">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="6089f-183">Na caixa **nome** , digite um nome de exibição exclusivo para a campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-183">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="6089f-184">Não clique em **usar modelo**, porque você criará a mensagem de email mais tarde no assistente.</span><span class="sxs-lookup"><span data-stu-id="6089f-184">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="6089f-185">Clique em **usar modelo** e selecione um modelo de email interno ou personalizado.</span><span class="sxs-lookup"><span data-stu-id="6089f-185">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="6089f-186">Depois de selecionar o modelo, a caixa **nome** é preenchida automaticamente com base no modelo, mas você pode alterar o nome.</span><span class="sxs-lookup"><span data-stu-id="6089f-186">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![Página de início de phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="6089f-188">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6089f-188">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6089f-189">Na etapa **destinatários de destino** , execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="6089f-189">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="6089f-190">Clique em **Catálogo de endereços** para selecionar os destinatários (usuários ou grupos) da campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-190">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="6089f-191">Cada destinatário almejado deve ter uma caixa de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6089f-191">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="6089f-192">Se você clicar em **Filtrar** e **aplicar** sem inserir um critério de pesquisa, todos os destinatários serão retornados e adicionados à campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-192">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="6089f-193">Clique em **importar** e em importar **arquivo** para importar um valor separado por vírgula (CSV) ou um arquivo separado por linha de endereços de email.</span><span class="sxs-lookup"><span data-stu-id="6089f-193">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="6089f-194">Cada linha deve conter o endereço de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="6089f-194">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="6089f-195">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6089f-195">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6089f-196">Na etapa **Configurar detalhes de email** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="6089f-196">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="6089f-197">Se você selecionou um modelo na etapa de **início** , a maioria desses valores já está configurada, mas você pode alterá-los.</span><span class="sxs-lookup"><span data-stu-id="6089f-197">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="6089f-198">**De (nome)**: o nome de exibição que é usado para o remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="6089f-198">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="6089f-199">**De (email)**: o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="6089f-199">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="6089f-200">Você pode inserir um endereço de email verdadeiro ou falso no domínio de email da sua organização ou pode inserir um endereço de email externo real ou falso.</span><span class="sxs-lookup"><span data-stu-id="6089f-200">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="6089f-201">Um endereço de email válido de um remetente da sua organização será realmente resolvido no cliente de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="6089f-201">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="6089f-202">**URL do servidor de logon de phishing**: clique no menu suspenso e selecione uma das URLs disponíveis na lista.</span><span class="sxs-lookup"><span data-stu-id="6089f-202">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="6089f-203">Esta é a URL para a qual os usuários terão tentado clicar.</span><span class="sxs-lookup"><span data-stu-id="6089f-203">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="6089f-204">As opções são:</span><span class="sxs-lookup"><span data-stu-id="6089f-204">The choices are:</span></span>

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
     > <ul><li><span data-ttu-id="6089f-205">Todas as URLs são intencionalmente http, não HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6089f-205">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="6089f-206">Um serviço de reputação de URL pode identificar uma ou mais dessas URLs como não seguras.</span><span class="sxs-lookup"><span data-stu-id="6089f-206">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="6089f-207">Verifique a disponibilidade da URL nos navegadores da Web com suporte antes de usar a URL em uma campanha de phishing.</span><span class="sxs-lookup"><span data-stu-id="6089f-207">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li><li><span data-ttu-id="6089f-208">Você deve selecionar uma URL.</span><span class="sxs-lookup"><span data-stu-id="6089f-208">You are required to select a URL.</span></span> <span data-ttu-id="6089f-209">Para campanhas de <b>spear phishing (Attachment)</b> , você pode remover o link do corpo da mensagem na próxima etapa (caso contrário, a mensagem conterá um link <b>e</b> um anexo).</span><span class="sxs-lookup"><span data-stu-id="6089f-209">For <b>Spear Phishing (Attachment)</b> campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link <b>and</b> an attachment).</span></span></li></ul>

   - <span data-ttu-id="6089f-210">**Tipo de anexo**: essa configuração só está disponível em campanhas de **spear phishing (Attachment)** .</span><span class="sxs-lookup"><span data-stu-id="6089f-210">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="6089f-211">Clique na lista suspensa e selecione **. DOCX** ou **. PDF** na lista.</span><span class="sxs-lookup"><span data-stu-id="6089f-211">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="6089f-212">**Nome do anexo**: essa configuração só está disponível em campanhas de **spear phishing (Attachment)** .</span><span class="sxs-lookup"><span data-stu-id="6089f-212">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="6089f-213">Insira um nome de arquivo para o anexo. docx ou. pdf.</span><span class="sxs-lookup"><span data-stu-id="6089f-213">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="6089f-214">**URL da página de aterrissagem personalizada**: Insira uma página de aterrissagem opcional, onde os usuários são conduzidos, caso eles cliquem no link phishing e insiram suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="6089f-214">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="6089f-215">Este link substitui a página de aterrissagem padrão.</span><span class="sxs-lookup"><span data-stu-id="6089f-215">This link replaces the default landing page.</span></span> <span data-ttu-id="6089f-216">Por exemplo, se você tiver um treinamento de conscientização interna, poderá especificar essa URL aqui.</span><span class="sxs-lookup"><span data-stu-id="6089f-216">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="6089f-217">**Assunto**: o campo **assunto** da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="6089f-217">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="6089f-218">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6089f-218">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6089f-219">Na etapa de **redação de email** , crie o corpo da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="6089f-219">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="6089f-220">Se você selecionou um modelo na etapa **Iniciar** , o corpo da mensagem já está configurado, mas você pode personalizá-lo.</span><span class="sxs-lookup"><span data-stu-id="6089f-220">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="6089f-221">Você pode usar a guia **email** (um editor de HTML avançado) ou a guia **fonte** (código HTML bruto).</span><span class="sxs-lookup"><span data-stu-id="6089f-221">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="6089f-222">A formatação HTML pode ser simples ou complexa, pois você precisará dela.</span><span class="sxs-lookup"><span data-stu-id="6089f-222">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="6089f-223">Você pode inserir imagens e texto para aprimorar o believability da mensagem no cliente de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="6089f-223">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="6089f-224">`${username}`Insere o nome do destinatário.</span><span class="sxs-lookup"><span data-stu-id="6089f-224">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="6089f-225">`${loginserverurl}`Insere o valor de **URL do servidor de logon de phishing** .</span><span class="sxs-lookup"><span data-stu-id="6089f-225">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="6089f-226">Para campanhas de **spear phishing (Attachment)** , você deve remover o link do corpo da mensagem (caso contrário, a mensagem conterá um link **e** um anexo e os cliques de link não serão rastreados em uma campanha de anexo).</span><span class="sxs-lookup"><span data-stu-id="6089f-226">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![Redigir corpo de email](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="6089f-228">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6089f-228">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="6089f-229">Na etapa **confirmar** , clique em **concluir** para iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-229">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="6089f-230">A mensagem de phishing é entregue aos destinatários direcionados.</span><span class="sxs-lookup"><span data-stu-id="6089f-230">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="6089f-231">Campanhas de ataque por senha</span><span class="sxs-lookup"><span data-stu-id="6089f-231">Password attack campaigns</span></span>

<span data-ttu-id="6089f-232">Um *ataque de senha* tenta adivinhar senhas para contas de usuário em uma organização, normalmente após o invasor ter identificado uma ou mais contas de usuário válidas.</span><span class="sxs-lookup"><span data-stu-id="6089f-232">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="6089f-233">No simulador de ataques, dois tipos diferentes de campanhas de ataque por senha estão disponíveis para você testar a complexidade das senhas de seus usuários:</span><span class="sxs-lookup"><span data-stu-id="6089f-233">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="6089f-234">**Senha de força bruta (ataque de dicionário)**: um ataque de *força bruta* ou de *dicionário* usa um arquivo de dicionário grande de senhas em uma conta de usuário, com a esperança de que um deles funcionará (muitas senhas em uma conta).</span><span class="sxs-lookup"><span data-stu-id="6089f-234">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="6089f-235">Bloqueios de senha incorretos ajudam a evitar ataques de senha forçada.</span><span class="sxs-lookup"><span data-stu-id="6089f-235">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="6089f-236">Para o ataque de dicionário, você pode especificar uma ou várias senhas para tentar (inseridas manualmente ou em um arquivo carregado) e pode especificar um ou vários usuários.</span><span class="sxs-lookup"><span data-stu-id="6089f-236">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="6089f-237">**Ataque de irrigação de senha**: um ataque de *irrigação de senha* usa a mesma senha cuidadosamente considerada em uma lista de contas de usuário (uma senha em muitas contas).</span><span class="sxs-lookup"><span data-stu-id="6089f-237">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="6089f-238">Os ataques de irrigação de senha são mais difíceis de detectar que os ataques de senha de força bruta (a probabilidade de sucessos aumenta quando um invasor tenta uma senha em dezenas ou centenas de contas sem o risco de recorrer o bloqueio de senha incorreto do usuário).</span><span class="sxs-lookup"><span data-stu-id="6089f-238">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="6089f-239">Para o ataque de irrigação de senha, você só pode especificar uma senha para tentar, e você pode especificar um ou vários usuários.</span><span class="sxs-lookup"><span data-stu-id="6089f-239">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="6089f-240">Os ataques de senha no simulador de ataque passam solicitações de autenticação básicas de nome de usuário e senha para um ponto de extremidade, de modo que também funcionem com outros métodos de autenticação (AD FS, sincronização de hash de senha, passagem, PingFederate, etc.).</span><span class="sxs-lookup"><span data-stu-id="6089f-240">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="6089f-241">Para usuários que têm o MFA habilitado, mesmo que o ataque de senha Tente sua senha real, a tentativa sempre será registrada como uma falha (em outras palavras, os usuários da MFA nunca aparecerão na contagem de **tentativas bem-sucedidas** da campanha).</span><span class="sxs-lookup"><span data-stu-id="6089f-241">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="6089f-242">Este é o resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="6089f-242">This is the expected result.</span></span> <span data-ttu-id="6089f-243">A MFA é um método principal para ajudar a proteger contra ataques de senha.</span><span class="sxs-lookup"><span data-stu-id="6089f-243">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="6089f-244">Criar e iniciar uma campanha de ataque de senha</span><span class="sxs-lookup"><span data-stu-id="6089f-244">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="6089f-245">No centro de conformidade & segurança, vá para **Threat management** \> **simulador de ataque**de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="6089f-245">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="6089f-246">Na página **simular ataques** , faça uma das seguintes seleções com base no tipo de campanha que você deseja criar:</span><span class="sxs-lookup"><span data-stu-id="6089f-246">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="6089f-247">Na seção **senha de força bruta (ataque de dicionário)** , clique em **Iniciar ataque** ou clique em **detalhes** \> do ataque de **lançamento**.</span><span class="sxs-lookup"><span data-stu-id="6089f-247">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="6089f-248">na seção **ataque de irrigação de senha** , clique em **Iniciar ataque** ou em **detalhes** \> de **lançamento**de ataques.</span><span class="sxs-lookup"><span data-stu-id="6089f-248">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="6089f-249">O assistente **Configurar ataque de senha** é iniciado em um novo submenu.</span><span class="sxs-lookup"><span data-stu-id="6089f-249">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="6089f-250">Na etapa **Iniciar** , digite um nome de exibição exclusivo para a campanha e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6089f-250">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="6089f-251">Na etapa **usuários de destino** , execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="6089f-251">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="6089f-252">Clique em **Catálogo de endereços** para selecionar os destinatários (usuários ou grupos) da campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-252">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="6089f-253">Cada destinatário almejado deve ter uma caixa de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6089f-253">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="6089f-254">Se você clicar em **Filtrar** e **aplicar** sem inserir um critério de pesquisa, todos os destinatários serão retornados e adicionados à campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-254">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="6089f-255">Clique em **importar** e em importar **arquivo** para importar um valor separado por vírgula (CSV) ou um arquivo separado por linha de endereços de email.</span><span class="sxs-lookup"><span data-stu-id="6089f-255">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="6089f-256">Cada linha deve conter o endereço de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="6089f-256">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="6089f-257">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6089f-257">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6089f-258">Na etapa **escolher as configurações de ataque** , escolha o que fazer com base no tipo de campanha:</span><span class="sxs-lookup"><span data-stu-id="6089f-258">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="6089f-259">**Senha de força bruta (ataque de dicionário)**: execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="6089f-259">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="6089f-260">**Inserir senhas manualmente**: na caixa **pressione ENTER para adicionar uma senha** , digite uma senha e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="6089f-260">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="6089f-261">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="6089f-261">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="6089f-262">**Carregar senhas de um arquivo de dicionário**: clique em **carregar** para importar um arquivo de texto existente que contenha uma senha em cada linha e uma última linha em branco.</span><span class="sxs-lookup"><span data-stu-id="6089f-262">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="6089f-263">O arquivo de texto deve ter 10 MB ou menos de tamanho e não pode conter mais de 30000 senhas.</span><span class="sxs-lookup"><span data-stu-id="6089f-263">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="6089f-264">**Ataque de irrigação de senha**: na caixa de entrada **(s) senha a ser usada no ataque** , digite uma senha.</span><span class="sxs-lookup"><span data-stu-id="6089f-264">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="6089f-265">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6089f-265">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6089f-266">Na etapa **confirmar** , clique em **concluir** para iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-266">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="6089f-267">As senhas que você especificou são tentadas nos usuários que você especificou.</span><span class="sxs-lookup"><span data-stu-id="6089f-267">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="6089f-268">Exibir resultados da campanha</span><span class="sxs-lookup"><span data-stu-id="6089f-268">View campaign results</span></span>

<span data-ttu-id="6089f-269">Depois de iniciar uma campanha, você pode verificar o progresso e os resultados na página principal de **ataques de simulações** .</span><span class="sxs-lookup"><span data-stu-id="6089f-269">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="6089f-270">As campanhas ativas mostrarão uma barra de status, um valor de porcentagem concluído e a contagem "(usuários concluídos) de (total de usuários)".</span><span class="sxs-lookup"><span data-stu-id="6089f-270">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="6089f-271">Clicar no botão **Atualizar** atualizará o progresso de todas as campanhas ativas.</span><span class="sxs-lookup"><span data-stu-id="6089f-271">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="6089f-272">Você também pode clicar em **encerrar** para interromper uma campanha ativa.</span><span class="sxs-lookup"><span data-stu-id="6089f-272">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="6089f-273">Quando a campanha é concluída, o status é alterado para **ataque concluído**.</span><span class="sxs-lookup"><span data-stu-id="6089f-273">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="6089f-274">Você pode exibir os resultados da campanha executando uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="6089f-274">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="6089f-275">Na página principais **ataques de simular** , clique em **Exibir relatório** sob o nome da campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-275">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="6089f-276">Na página principal **simular ataques** , clique em **detalhes do ataque** na seção referente ao tipo de ataque.</span><span class="sxs-lookup"><span data-stu-id="6089f-276">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="6089f-277">Na página **detalhes do ataque** que é aberta, selecione a campanha na seção **histórico de ataques** .</span><span class="sxs-lookup"><span data-stu-id="6089f-277">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="6089f-278">Qualquer uma das ações anteriores levará você para uma página chamada **detalhes do ataque**.</span><span class="sxs-lookup"><span data-stu-id="6089f-278">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="6089f-279">As informações disponíveis nesta página para cada tipo de campanha são descritas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="6089f-279">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="6089f-280">Resultados da campanha de spear phishing (coleta de credenciais)</span><span class="sxs-lookup"><span data-stu-id="6089f-280">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="6089f-281">As informações a seguir estão disponíveis na página de **detalhes do ataque** de cada campanha:</span><span class="sxs-lookup"><span data-stu-id="6089f-281">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6089f-282">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-282">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6089f-283">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="6089f-283">**Total users targeted**</span></span>

- <span data-ttu-id="6089f-284">**Tentativas bem-sucedidas**: o número de usuários que clicaram no link **e** inseriram suas credenciais (*qualquer* nome de usuário e de senha).</span><span class="sxs-lookup"><span data-stu-id="6089f-284">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="6089f-285">**Taxa de êxito geral**: uma porcentagem calculada por **tentativas** / bem-sucedidas**total dos usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="6089f-285">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="6089f-286">**Clique mais rápido**: quanto tempo levava o primeiro usuário a clicar no link depois que você iniciou a campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-286">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="6089f-287">**Clique médio**: a soma de quanto tempo levava para todos clicar no link dividido pelo número de usuários que clicaram no link.</span><span class="sxs-lookup"><span data-stu-id="6089f-287">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="6089f-288">**Clique em taxa de êxito**: uma porcentagem calculada por (número de usuários que clicaram no link)/ **total de usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="6089f-288">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="6089f-289">**Credenciais mais rápidas**: quanto tempo levava o primeiro usuário a inserir suas credenciais após o lançamento da campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-289">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="6089f-290">**Média de credenciais**: a soma de quanto tempo levava para todos inserir suas credenciais divididas pelo número de usuários que inseriram suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="6089f-290">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="6089f-291">**Taxa de êxito da credencial**: uma porcentagem calculada por (número de usuários que inseriram suas credenciais)/ **total de usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="6089f-291">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="6089f-292">Um gráfico de barras que mostra o **link clicado** e os números **fornecidos por credencial** por dia.</span><span class="sxs-lookup"><span data-stu-id="6089f-292">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="6089f-293">Um gráfico de círculo que mostra o **link clicado**, as **credenciais fornecidas**e **nenhuma** porcentagem para a campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-293">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="6089f-294">A seção **usuários comprometidos** lista os detalhes dos usuários que clicaram no link:</span><span class="sxs-lookup"><span data-stu-id="6089f-294">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="6089f-295">O endereço de email do usuário</span><span class="sxs-lookup"><span data-stu-id="6089f-295">The user's email address</span></span>

  - <span data-ttu-id="6089f-296">A data/hora em que o link foi clicado.</span><span class="sxs-lookup"><span data-stu-id="6089f-296">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="6089f-297">O endereço IP do cliente.</span><span class="sxs-lookup"><span data-stu-id="6089f-297">The client IP address.</span></span>

  - <span data-ttu-id="6089f-298">Detalhes sobre a versão do usuário do Windows e do navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="6089f-298">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="6089f-299">Você pode clicar em **Exportar** para exportar os resultados para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="6089f-299">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="6089f-300">Resultados da campanha de spear phishing (Attachment)</span><span class="sxs-lookup"><span data-stu-id="6089f-300">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="6089f-301">As informações a seguir estão disponíveis na página de **detalhes do ataque** de cada campanha:</span><span class="sxs-lookup"><span data-stu-id="6089f-301">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6089f-302">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-302">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6089f-303">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="6089f-303">**Total users targeted**</span></span>

- <span data-ttu-id="6089f-304">**Tentativas bem-sucedidas**: o número de usuários que abriram ou baixaram e abriram o anexo (a visualização não conta).</span><span class="sxs-lookup"><span data-stu-id="6089f-304">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="6089f-305">**Taxa de êxito geral**: uma porcentagem calculada por **tentativas** / bem-sucedidas**total dos usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="6089f-305">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="6089f-306">**Tempo de abertura do anexo mais rápido**: quanto tempo levava o primeiro usuário a abrir o anexo depois que você iniciou a campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-306">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="6089f-307">**Tempo médio de abertura do anexo**: a soma de quanto tempo levava todos para abrir o anexo dividido pelo número de usuários que abriram o anexo.</span><span class="sxs-lookup"><span data-stu-id="6089f-307">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="6089f-308">**Taxa de êxito na abertura do anexo**: uma porcentagem calculada por (número de usuários que abriram o anexo)/ **total de usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="6089f-308">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="6089f-309">Senha de força bruta (ataque de dicionário) resultados da campanha</span><span class="sxs-lookup"><span data-stu-id="6089f-309">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="6089f-310">As informações a seguir estão disponíveis na página de **detalhes do ataque** de cada campanha:</span><span class="sxs-lookup"><span data-stu-id="6089f-310">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6089f-311">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-311">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6089f-312">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="6089f-312">**Total users targeted**</span></span>

- <span data-ttu-id="6089f-313">**Tentativas bem-sucedidas**: o número de usuários que foram encontrados usando uma das senhas especificadas.</span><span class="sxs-lookup"><span data-stu-id="6089f-313">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="6089f-314">**Taxa de êxito geral**: uma porcentagem calculada por **tentativas** / bem-sucedidas**total dos usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="6089f-314">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="6089f-315">A seção **usuários comprometidos** lista os endereços de email dos usuários afetados.</span><span class="sxs-lookup"><span data-stu-id="6089f-315">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="6089f-316">Você pode clicar em **Exportar** para exportar os resultados para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="6089f-316">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="6089f-317">Resultados da campanha de ataque de irrigação de senha</span><span class="sxs-lookup"><span data-stu-id="6089f-317">Password spray attack campaign results</span></span>

<span data-ttu-id="6089f-318">As informações a seguir estão disponíveis na página de **detalhes do ataque** de cada campanha:</span><span class="sxs-lookup"><span data-stu-id="6089f-318">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6089f-319">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="6089f-319">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6089f-320">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="6089f-320">**Total users targeted**</span></span>

- <span data-ttu-id="6089f-321">**Tentativas bem-sucedidas**: o número de usuários que foram encontrados usando a senha especificada.</span><span class="sxs-lookup"><span data-stu-id="6089f-321">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="6089f-322">**Taxa de êxito geral**: uma porcentagem calculada por **tentativas** / bem-sucedidas**total dos usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="6089f-322">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
