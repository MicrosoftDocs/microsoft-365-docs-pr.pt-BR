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
ms.custom:
- seo-marvel-apr2020
description: Saiba como usar o simulador de ataques para executar ataques simulados de phishing e senha em sua organização do plano 2 do Microsoft 365 E5 ou ATP.
ms.openlocfilehash: e2c6859291e4a25e56dd8dd20a8ecc5962310680
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035853"
---
# <a name="attack-simulator-in-atp"></a><span data-ttu-id="b1cd4-103">Simulador de ataque em ATP</span><span class="sxs-lookup"><span data-stu-id="b1cd4-103">Attack Simulator in ATP</span></span>

<span data-ttu-id="b1cd4-104">**Resumo** Se você for um administrador global ou um administrador de segurança e sua organização tiver o Office 365 Advanced Threat Protection Plan 2, que inclui os [recursos de investigação e resposta contra ameaças](office-365-ti.md), você poderá usar o simulador de ataques para executar cenários de ataque realísticos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-104">**Summary** If you are a global administrator or a security administrator and your organization has Office 365 Advanced Threat Protection Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="b1cd4-105">Isso pode ajudar você a identificar e a encontrar usuários vulneráveis, antes que um ataque real afete o resultado.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-105">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="b1cd4-106">Leia este artigo para saber mais.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-106">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b1cd4-107">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="b1cd4-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b1cd4-108">Para abrir o Centro de Conformidade e Segurança, acesse <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-108">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="b1cd4-109">O simulador de ataque está disponível no **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-109">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span>

  ![Gerenciamento de ameaças-simulador de ataques](../../media/ThreatMgmt-AttackSimulator.png)

- <span data-ttu-id="b1cd4-111">Para obter mais informações sobre a disponibilidade do simulador de ataque em assinaturas diferentes da Microsoft 365, confira [Descrição do serviço de proteção avançada contra ameaças do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-111">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="b1cd4-112">Você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de administrador de **segurança** .</span><span class="sxs-lookup"><span data-stu-id="b1cd4-112">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="b1cd4-113">Para obter mais informações sobre grupos de funções no Centro de Conformidade e Segurança, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="b1cd4-114">Sua conta precisa ser configurada para a MFA (autenticação multifator) para criar e gerenciar campanhas no simulador de ataques.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-114">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="b1cd4-115">Para obter instruções, consulte [Configurar a autenticação multifator](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-115">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

<span data-ttu-id="b1cd4-116">Para que um ataque seja iniciado com êxito, certifique-se de que a conta que você está usando para executar ataques simulados esteja usando a autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-116">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="b1cd4-117">Além disso, você deve ser um administrador global ou um administrador de segurança.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-117">In addition, you must be a global administrator or a security administrator.</span></span> <span data-ttu-id="b1cd4-118">(Para saber mais sobre funções e permissões, consulte [permissões no centro de conformidade de & de segurança](permissions-in-the-security-and-compliance-center.md).)</span><span class="sxs-lookup"><span data-stu-id="b1cd4-118">(To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

- <span data-ttu-id="b1cd4-119">Campanhas de phishing coletam e processam eventos por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-119">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="b1cd4-120">Dados de campanha históricos estarão disponíveis por até 90 dias após a execução da campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-120">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="b1cd4-121">Não há cmdlets do PowerShell correspondentes para o simulador de ataques.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-121">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="b1cd4-122">Campanhas de spear phishing</span><span class="sxs-lookup"><span data-stu-id="b1cd4-122">Spear phishing campaigns</span></span>

<span data-ttu-id="b1cd4-123">*Phishing* é um termo genérico para ataques de email que tentam roubar informações confidenciais em mensagens que parecem ser de remetentes legítimos ou confiáveis.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="b1cd4-124">O *spear phishing* é um ataque de phishing direcionado que usa conteúdo muito focalizado e personalizado que é especificamente ajustado para os destinatários direcionados (normalmente, após o reconhecimento dos destinatários pelo invasor).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-124">*Spear phishing* is a targeted phishing attack that uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="b1cd4-125">Você é um administrador global ou administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="b1cd4-125">You are a global administrator or security administrator</span></span>

<span data-ttu-id="b1cd4-126">No simulador de ataques, dois tipos diferentes de campanhas de phishing de Spear estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-126">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="b1cd4-127">A [autenticação multifator/acesso condicional](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) está ativada, por pelo menos a conta de administrador global e os administradores de segurança que usarão o simulador de ataques.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-127">[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) is turned on, for at least the global administrator account and security administrators who will be using Attack Simulator.</span></span> <span data-ttu-id="b1cd4-128">(Idealmente, a autenticação multifator/acesso condicional está ativada para todos os usuários da sua organização.)</span><span class="sxs-lookup"><span data-stu-id="b1cd4-128">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>

  - <span data-ttu-id="b1cd4-129">Uma página padrão que explica isso era um teste apenas e fornece dicas para reconhecer mensagens de phishing.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-129">A default page that explains this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![O que os usuários verão se clicarem no link phishing e inserirem suas credenciais](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="b1cd4-131">Uma página personalizada (URL) que você especificar.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-131">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="b1cd4-132">**Spear phishing (anexo)**: o ataque tenta convencer os destinatários a abrir um anexo. docx ou. pdf na mensagem.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-132">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="b1cd4-133">O anexo contém o mesmo conteúdo do link phishing padrão, mas a primeira sentença começa com "\<nome\>de exibição, você está vendo esta mensagem como uma mensagem de email recente que você abriu...".</span><span class="sxs-lookup"><span data-stu-id="b1cd4-133">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="b1cd4-134">Atualmente, as campanhas de spear phishing no simulador de ataques não expiram.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-134">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="b1cd4-135">Criar uma campanha de spear phishing</span><span class="sxs-lookup"><span data-stu-id="b1cd4-135">Create a spear phishing campaign</span></span>

<span data-ttu-id="b1cd4-136">Uma parte importante de qualquer campanha de spear phishing é a aparência da mensagem de email enviada aos destinatários de destino.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-136">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="b1cd4-137">Para criar e configurar a mensagem de email, você tem estas opções:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-137">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="b1cd4-138">**Use um modelo de email interno**: dois modelos internos estão disponíveis: **prêmios** e atualizações de folha de **pagamento**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-138">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="b1cd4-139">Você pode personalizar ainda mais algumas, todas ou nenhuma das propriedades de email do modelo ao criar e iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-139">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="b1cd4-140">**Criar um modelo de email reutilizável**: depois de criar e salvar o modelo de email, você pode usá-lo novamente em futuras campanhas de spear phishing.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-140">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="b1cd4-141">Você pode personalizar ainda mais algumas, todas ou nenhuma das propriedades de email do modelo ao criar e iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-141">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="b1cd4-142">**Criar a mensagem de email no assistente**: você pode criar a mensagem de email diretamente no assistente ao criar e iniciar a campanha de spear phishing.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-142">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="b1cd4-143">Etapa 1 (opcional): criar um modelo de email personalizado</span><span class="sxs-lookup"><span data-stu-id="b1cd4-143">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="b1cd4-144">Se você for usar um dos modelos internos ou criar a mensagem de email diretamente no assistente, poderá pular esta etapa.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-144">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="b1cd4-145">No centro de conformidade & segurança, vá para **Threat management** \> **simulador de ataque**de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-145">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="b1cd4-146">Na página **simular ataques** , nas seções **spear phishing (informações de coleta de credenciais)** ou **spear phishing (anexo)** , clique em **detalhes do ataque**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-146">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="b1cd4-147">Não importa onde você crie o modelo.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-147">It doesn't matter where you create the template.</span></span> <span data-ttu-id="b1cd4-148">As opções disponíveis no modelo são as mesmas para os dois tipos de ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-148">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="b1cd4-149">Na página **detalhes do ataque** que é aberta, na **seção modelos de phishing** , na área **criar modelos** , clique em **novo modelo**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-149">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="b1cd4-150">O assistente para **Configurar modelo de phishing** é iniciado em um novo submenu.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-150">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="b1cd4-151">Na etapa **Iniciar** , digite um nome de exibição exclusivo para o modelo e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-151">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="b1cd4-152">Na etapa **Configurar detalhes de email** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-152">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="b1cd4-153">**De (nome)**: o nome de exibição que é usado para o remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-153">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="b1cd4-154">**De (email)**: o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-154">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="b1cd4-155">**URL do servidor de logon de phishing**: clique no menu suspenso e selecione uma das URLs disponíveis na lista.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-155">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="b1cd4-156">Esta é a URL para a qual os usuários terão tentado clicar.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-156">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="b1cd4-157">As opções são:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-157">The choices are:</span></span>

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
     > <ul><li><span data-ttu-id="b1cd4-158">Todas as URLs são intencionalmente http, não HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-158">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="b1cd4-159">Um serviço de reputação de URL pode identificar uma ou mais dessas URLs como não seguras.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-159">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="b1cd4-160">Verifique a disponibilidade da URL nos navegadores da Web com suporte antes de usar a URL em uma campanha de phishing.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-160">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li></ul>

   - <span data-ttu-id="b1cd4-161">**URL da página de aterrissagem personalizada**: Insira uma página de aterrissagem opcional, onde os usuários são conduzidos, caso eles cliquem no link phishing e insiram suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-161">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="b1cd4-162">Este link substitui a página de aterrissagem padrão.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-162">This link replaces the default landing page.</span></span> <span data-ttu-id="b1cd4-163">Por exemplo, se você tiver um treinamento de conscientização interna, poderá especificar essa URL aqui.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-163">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="b1cd4-164">**Categoria**: no momento, essa configuração não é usada (tudo o que você inserir será ignorado).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-164">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="b1cd4-165">**Assunto**: o campo **assunto** da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-165">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="b1cd4-166">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-166">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b1cd4-167">Na etapa de **redação de email** , crie o corpo da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-167">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="b1cd4-168">Você pode usar a guia **email** (um editor de HTML avançado) ou a guia **fonte** (código HTML bruto).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-168">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="b1cd4-169">A formatação HTML pode ser simples ou complexa, pois você precisará dela.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-169">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="b1cd4-170">Você pode inserir imagens e texto para aprimorar o believability da mensagem no cliente de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-170">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="b1cd4-171">`${username}`Insere o nome do destinatário.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-171">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="b1cd4-172">`${loginserverurl}`Insere o valor de **URL do servidor de logon de phishing** da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-172">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="b1cd4-173">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-173">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="b1cd4-174">Na etapa **confirmar** , clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-174">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="b1cd4-175">Etapa 2: criar e iniciar a campanha de spear phishing</span><span class="sxs-lookup"><span data-stu-id="b1cd4-175">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="b1cd4-176">No centro de conformidade & segurança, vá para **Threat management** \> **simulador de ataque**de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-176">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="b1cd4-177">Na página **simular ataques** , faça uma das seguintes seleções com base no tipo de campanha que você deseja criar:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-177">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="b1cd4-178">Na seção **spear phishing (coleta de credenciais)** , clique em **Iniciar ataque** ou clique em **detalhes** \> do ataque de **lançamento**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-178">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="b1cd4-179">Na seção **spear phishing (anexo)** , clique em **Iniciar ataque** ou clique em **detalhes** \> do ataque de **lançamento**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-179">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="b1cd4-180">O assistente para **configurar ataques de phishing** é iniciado em um novo submenu.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-180">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="b1cd4-181">Na etapa **Iniciar** , execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-181">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="b1cd4-182">Na caixa **nome** , digite um nome de exibição exclusivo para a campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-182">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="b1cd4-183">Não clique em **usar modelo**, porque você criará a mensagem de email mais tarde no assistente.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-183">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="b1cd4-184">Clique em **usar modelo** e selecione um modelo de email interno ou personalizado.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-184">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="b1cd4-185">Depois de selecionar o modelo, a caixa **nome** é preenchida automaticamente com base no modelo, mas você pode alterar o nome.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-185">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![Página de início de phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="b1cd4-187">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-187">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b1cd4-188">Na etapa **destinatários de destino** , execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-188">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="b1cd4-189">Clique em **Catálogo de endereços** para selecionar os destinatários (usuários ou grupos) da campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-189">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="b1cd4-190">Cada destinatário almejado deve ter uma caixa de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-190">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="b1cd4-191">Se você clicar em **Filtrar** e **aplicar** sem inserir um critério de pesquisa, todos os destinatários serão retornados e adicionados à campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-191">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="b1cd4-192">Clique em **importar** e em importar **arquivo** para importar um valor separado por vírgula (CSV) ou um arquivo separado por linha de endereços de email.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-192">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="b1cd4-193">Cada linha deve conter o endereço de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-193">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="b1cd4-194">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-194">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b1cd4-195">Na etapa **Configurar detalhes de email** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-195">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="b1cd4-196">Se você selecionou um modelo na etapa de **início** , a maioria desses valores já está configurada, mas você pode alterá-los.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-196">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="b1cd4-197">**De (nome)**: o nome de exibição que é usado para o remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-197">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="b1cd4-198">**De (email)**: o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-198">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="b1cd4-199">Você pode inserir um endereço de email verdadeiro ou falso no domínio de email da sua organização ou pode inserir um endereço de email externo real ou falso.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-199">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="b1cd4-200">Um endereço de email válido de um remetente da sua organização será realmente resolvido no cliente de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-200">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="b1cd4-201">**URL do servidor de logon de phishing**: clique no menu suspenso e selecione uma das URLs disponíveis na lista.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-201">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="b1cd4-202">Esta é a URL para a qual os usuários terão tentado clicar.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-202">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="b1cd4-203">As opções são:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-203">The choices are:</span></span>

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
     > <ul><li><span data-ttu-id="b1cd4-204">Todas as URLs são intencionalmente http, não HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-204">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="b1cd4-205">Um serviço de reputação de URL pode identificar uma ou mais dessas URLs como não seguras.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-205">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="b1cd4-206">Verifique a disponibilidade da URL nos navegadores da Web com suporte antes de usar a URL em uma campanha de phishing.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-206">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li><li><span data-ttu-id="b1cd4-207">Você deve selecionar uma URL.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-207">You are required to select a URL.</span></span> <span data-ttu-id="b1cd4-208">Para campanhas de <b>spear phishing (Attachment)</b> , você pode remover o link do corpo da mensagem na próxima etapa (caso contrário, a mensagem conterá um link <b>e</b> um anexo).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-208">For <b>Spear Phishing (Attachment)</b> campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link <b>and</b> an attachment).</span></span></li></ul>

   - <span data-ttu-id="b1cd4-209">**Tipo de anexo**: essa configuração só está disponível em campanhas de **spear phishing (Attachment)** .</span><span class="sxs-lookup"><span data-stu-id="b1cd4-209">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="b1cd4-210">Clique na lista suspensa e selecione **. DOCX** ou **. PDF** na lista.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-210">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="b1cd4-211">**Nome do anexo**: essa configuração só está disponível em campanhas de **spear phishing (Attachment)** .</span><span class="sxs-lookup"><span data-stu-id="b1cd4-211">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="b1cd4-212">Insira um nome de arquivo para o anexo. docx ou. pdf.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-212">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="b1cd4-213">**URL da página de aterrissagem personalizada**: Insira uma página de aterrissagem opcional, onde os usuários são conduzidos, caso eles cliquem no link phishing e insiram suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-213">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="b1cd4-214">Este link substitui a página de aterrissagem padrão.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-214">This link replaces the default landing page.</span></span> <span data-ttu-id="b1cd4-215">Por exemplo, se você tiver um treinamento de conscientização interna, poderá especificar essa URL aqui.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-215">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="b1cd4-216">**Assunto**: o campo **assunto** da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-216">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="b1cd4-217">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-217">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b1cd4-218">Na etapa de **redação de email** , crie o corpo da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-218">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="b1cd4-219">Se você selecionou um modelo na etapa **Iniciar** , o corpo da mensagem já está configurado, mas você pode personalizá-lo.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-219">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="b1cd4-220">Você pode usar a guia **email** (um editor de HTML avançado) ou a guia **fonte** (código HTML bruto).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-220">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="b1cd4-221">A formatação HTML pode ser simples ou complexa, pois você precisará dela.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-221">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="b1cd4-222">Você pode inserir imagens e texto para aprimorar o believability da mensagem no cliente de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-222">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="b1cd4-223">`${username}`Insere o nome do destinatário.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-223">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="b1cd4-224">`${loginserverurl}`Insere o valor de **URL do servidor de logon de phishing** .</span><span class="sxs-lookup"><span data-stu-id="b1cd4-224">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="b1cd4-225">Para campanhas de **spear phishing (Attachment)** , você deve remover o link do corpo da mensagem (caso contrário, a mensagem conterá um link **e** um anexo e os cliques de link não serão rastreados em uma campanha de anexo).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-225">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![Redigir corpo de email](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="b1cd4-227">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-227">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="b1cd4-228">Na etapa **confirmar** , clique em **concluir** para iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-228">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="b1cd4-229">A mensagem de phishing é entregue aos destinatários direcionados.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-229">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="b1cd4-230">Campanhas de ataque por senha</span><span class="sxs-lookup"><span data-stu-id="b1cd4-230">Password attack campaigns</span></span>

<span data-ttu-id="b1cd4-231">Um *ataque de senha* tenta adivinhar senhas para contas de usuário em uma organização, normalmente após o invasor ter identificado uma ou mais contas de usuário válidas.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-231">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="b1cd4-232">No simulador de ataques, dois tipos diferentes de campanhas de ataque por senha estão disponíveis para você testar a complexidade das senhas de seus usuários:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-232">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="b1cd4-233">**Senha de força bruta (ataque de dicionário)**: um ataque de *força bruta* ou de *dicionário* usa um arquivo de dicionário grande de senhas em uma conta de usuário, com a esperança de que um deles funcionará (muitas senhas em uma conta).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-233">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="b1cd4-234">Bloqueios de senha incorretos ajudam a evitar ataques de senha forçada.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-234">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="b1cd4-235">Para o ataque de dicionário, você pode especificar uma ou várias senhas para tentar (inseridas manualmente ou em um arquivo carregado) e pode especificar um ou vários usuários.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-235">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="b1cd4-236">**Ataque de irrigação de senha**: um ataque de *irrigação de senha* usa a mesma senha cuidadosamente considerada em uma lista de contas de usuário (uma senha em muitas contas).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-236">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="b1cd4-237">Os ataques de irrigação de senha são mais difíceis de detectar que os ataques de senha de força bruta (a probabilidade de sucessos aumenta quando um invasor tenta uma senha em dezenas ou centenas de contas sem o risco de recorrer o bloqueio de senha incorreto do usuário).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-237">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="b1cd4-238">Para o ataque de irrigação de senha, você só pode especificar uma senha para tentar, e você pode especificar um ou vários usuários.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-238">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="b1cd4-239">Os ataques de senha no simulador de ataque passam solicitações de autenticação básicas de nome de usuário e senha para um ponto de extremidade, de modo que também funcionem com outros métodos de autenticação (AD FS, sincronização de hash de senha, passagem, PingFederate, etc.).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-239">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="b1cd4-240">Para usuários que têm o MFA habilitado, mesmo que o ataque de senha Tente sua senha real, a tentativa sempre será registrada como uma falha (em outras palavras, os usuários da MFA nunca aparecerão na contagem de **tentativas bem-sucedidas** da campanha).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-240">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="b1cd4-241">Este é o resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-241">This is the expected result.</span></span> <span data-ttu-id="b1cd4-242">A MFA é um método principal para ajudar a proteger contra ataques de senha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-242">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="b1cd4-243">Criar e iniciar uma campanha de ataque de senha</span><span class="sxs-lookup"><span data-stu-id="b1cd4-243">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="b1cd4-244">No centro de conformidade & segurança, vá para **Threat management** \> **simulador de ataque**de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-244">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="b1cd4-245">Na página **simular ataques** , faça uma das seguintes seleções com base no tipo de campanha que você deseja criar:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-245">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="b1cd4-246">Na seção **senha de força bruta (ataque de dicionário)** , clique em **Iniciar ataque** ou clique em **detalhes** \> do ataque de **lançamento**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-246">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="b1cd4-247">na seção **ataque de irrigação de senha** , clique em **Iniciar ataque** ou em **detalhes** \> de **lançamento**de ataques.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-247">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="b1cd4-248">O assistente **Configurar ataque de senha** é iniciado em um novo submenu.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-248">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="b1cd4-249">Na etapa **Iniciar** , digite um nome de exibição exclusivo para a campanha e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-249">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="b1cd4-250">Na etapa **usuários de destino** , execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-250">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="b1cd4-251">Clique em **Catálogo de endereços** para selecionar os destinatários (usuários ou grupos) da campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-251">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="b1cd4-252">Cada destinatário almejado deve ter uma caixa de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-252">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="b1cd4-253">Se você clicar em **Filtrar** e **aplicar** sem inserir um critério de pesquisa, todos os destinatários serão retornados e adicionados à campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-253">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="b1cd4-254">Clique em **importar** e em importar **arquivo** para importar um valor separado por vírgula (CSV) ou um arquivo separado por linha de endereços de email.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-254">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="b1cd4-255">Cada linha deve conter o endereço de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-255">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="b1cd4-256">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-256">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b1cd4-257">Na etapa **escolher as configurações de ataque** , escolha o que fazer com base no tipo de campanha:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-257">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="b1cd4-258">**Senha de força bruta (ataque de dicionário)**: execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-258">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="b1cd4-259">**Inserir senhas manualmente**: na caixa **pressione ENTER para adicionar uma senha** , digite uma senha e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-259">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="b1cd4-260">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-260">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="b1cd4-261">**Carregar senhas de um arquivo de dicionário**: clique em **carregar** para importar um arquivo de texto existente que contenha uma senha em cada linha e uma última linha em branco.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-261">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="b1cd4-262">O arquivo de texto deve ter 10 MB ou menos de tamanho e não pode conter mais de 30000 senhas.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-262">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="b1cd4-263">**Ataque de irrigação de senha**: na caixa de entrada **(s) senha a ser usada no ataque** , digite uma senha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-263">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="b1cd4-264">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-264">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b1cd4-265">Na etapa **confirmar** , clique em **concluir** para iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-265">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="b1cd4-266">As senhas que você especificou são tentadas nos usuários que você especificou.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-266">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="b1cd4-267">Exibir resultados da campanha</span><span class="sxs-lookup"><span data-stu-id="b1cd4-267">View campaign results</span></span>

<span data-ttu-id="b1cd4-268">Depois de iniciar uma campanha, você pode verificar o progresso e os resultados na página principal de **ataques de simulações** .</span><span class="sxs-lookup"><span data-stu-id="b1cd4-268">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="b1cd4-269">As campanhas ativas mostrarão uma barra de status, um valor de porcentagem concluído e a contagem "(usuários concluídos) de (total de usuários)".</span><span class="sxs-lookup"><span data-stu-id="b1cd4-269">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="b1cd4-270">Clicar no botão **Atualizar** atualizará o progresso de todas as campanhas ativas.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-270">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="b1cd4-271">Você também pode clicar em **encerrar** para interromper uma campanha ativa.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-271">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="b1cd4-272">Quando a campanha é concluída, o status é alterado para **ataque concluído**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-272">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="b1cd4-273">Você pode exibir os resultados da campanha executando uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-273">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="b1cd4-274">Na página principais **ataques de simular** , clique em **Exibir relatório** sob o nome da campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-274">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="b1cd4-275">Na página principal **simular ataques** , clique em **detalhes do ataque** na seção referente ao tipo de ataque.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-275">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="b1cd4-276">Na página **detalhes do ataque** que é aberta, selecione a campanha na seção **histórico de ataques** .</span><span class="sxs-lookup"><span data-stu-id="b1cd4-276">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="b1cd4-277">Qualquer uma das ações anteriores levará você para uma página chamada **detalhes do ataque**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-277">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="b1cd4-278">As informações disponíveis nesta página para cada tipo de campanha são descritas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-278">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="b1cd4-279">Resultados da campanha de spear phishing (coleta de credenciais)</span><span class="sxs-lookup"><span data-stu-id="b1cd4-279">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="b1cd4-280">As informações a seguir estão disponíveis na página de **detalhes do ataque** de cada campanha:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-280">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="b1cd4-281">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-281">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="b1cd4-282">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="b1cd4-282">**Total users targeted**</span></span>

- <span data-ttu-id="b1cd4-283">**Tentativas bem-sucedidas**: o número de usuários que clicaram no link **e** inseriram suas credenciais (*qualquer* nome de usuário e de senha).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-283">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="b1cd4-284">**Taxa de êxito geral**: uma porcentagem calculada por **tentativas** / bem-sucedidas**total dos usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-284">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="b1cd4-285">**Clique mais rápido**: quanto tempo levava o primeiro usuário a clicar no link depois que você iniciou a campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-285">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="b1cd4-286">**Clique médio**: a soma de quanto tempo levava para todos clicar no link dividido pelo número de usuários que clicaram no link.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-286">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="b1cd4-287">**Clique em taxa de êxito**: uma porcentagem calculada por (número de usuários que clicaram no link)/ **total de usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-287">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="b1cd4-288">**Credenciais mais rápidas**: quanto tempo levava o primeiro usuário a inserir suas credenciais após o lançamento da campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-288">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="b1cd4-289">**Média de credenciais**: a soma de quanto tempo levava para todos inserir suas credenciais divididas pelo número de usuários que inseriram suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-289">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="b1cd4-290">**Taxa de êxito da credencial**: uma porcentagem calculada por (número de usuários que inseriram suas credenciais)/ **total de usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-290">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="b1cd4-291">Um gráfico de barras que mostra o **link clicado** e os números **fornecidos por credencial** por dia.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-291">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="b1cd4-292">Um gráfico de círculo que mostra o **link clicado**, as **credenciais fornecidas**e **nenhuma** porcentagem para a campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-292">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="b1cd4-293">A seção **usuários comprometidos** lista os detalhes dos usuários que clicaram no link:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-293">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="b1cd4-294">O endereço de email do usuário</span><span class="sxs-lookup"><span data-stu-id="b1cd4-294">The user's email address</span></span>

  - <span data-ttu-id="b1cd4-295">A data/hora em que o link foi clicado.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-295">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="b1cd4-296">O endereço IP do cliente.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-296">The client IP address.</span></span>

  - <span data-ttu-id="b1cd4-297">Detalhes sobre a versão do usuário do Windows e do navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-297">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="b1cd4-298">Você pode clicar em **Exportar** para exportar os resultados para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-298">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="b1cd4-299">Resultados da campanha de spear phishing (Attachment)</span><span class="sxs-lookup"><span data-stu-id="b1cd4-299">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="b1cd4-300">As informações a seguir estão disponíveis na página de **detalhes do ataque** de cada campanha:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-300">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="b1cd4-301">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-301">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="b1cd4-302">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="b1cd4-302">**Total users targeted**</span></span>

- <span data-ttu-id="b1cd4-303">**Tentativas bem-sucedidas**: o número de usuários que abriram ou baixaram e abriram o anexo (a visualização não conta).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-303">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="b1cd4-304">**Taxa de êxito geral**: uma porcentagem calculada por **tentativas** / bem-sucedidas**total dos usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-304">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="b1cd4-305">**Tempo de abertura do anexo mais rápido**: quanto tempo levava o primeiro usuário a abrir o anexo depois que você iniciou a campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-305">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="b1cd4-306">**Tempo médio de abertura do anexo**: a soma de quanto tempo levava todos para abrir o anexo dividido pelo número de usuários que abriram o anexo.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-306">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="b1cd4-307">**Taxa de êxito na abertura do anexo**: uma porcentagem calculada por (número de usuários que abriram o anexo)/ **total de usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-307">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="b1cd4-308">Senha de força bruta (ataque de dicionário) resultados da campanha</span><span class="sxs-lookup"><span data-stu-id="b1cd4-308">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="b1cd4-309">As informações a seguir estão disponíveis na página de **detalhes do ataque** de cada campanha:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-309">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="b1cd4-310">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-310">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="b1cd4-311">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="b1cd4-311">**Total users targeted**</span></span>

- <span data-ttu-id="b1cd4-312">**Tentativas bem-sucedidas**: o número de usuários que foram encontrados usando uma das senhas especificadas.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-312">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="b1cd4-313">**Taxa de êxito geral**: uma porcentagem calculada por **tentativas** / bem-sucedidas**total dos usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-313">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="b1cd4-314">A seção **usuários comprometidos** lista os endereços de email dos usuários afetados.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-314">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="b1cd4-315">Você pode clicar em **Exportar** para exportar os resultados para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-315">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="b1cd4-316">Resultados da campanha de ataque de irrigação de senha</span><span class="sxs-lookup"><span data-stu-id="b1cd4-316">Password spray attack campaign results</span></span>

<span data-ttu-id="b1cd4-317">As informações a seguir estão disponíveis na página de **detalhes do ataque** de cada campanha:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-317">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="b1cd4-318">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-318">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="b1cd4-319">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="b1cd4-319">**Total users targeted**</span></span>

- <span data-ttu-id="b1cd4-320">**Tentativas bem-sucedidas**: o número de usuários que foram encontrados usando a senha especificada.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-320">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="b1cd4-321">**Taxa de êxito geral**: uma porcentagem calculada por **tentativas** / bem-sucedidas**total dos usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-321">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
