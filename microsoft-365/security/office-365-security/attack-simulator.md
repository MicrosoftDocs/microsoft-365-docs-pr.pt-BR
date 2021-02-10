---
title: Simulador de Ataque no Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o Simulador de Ataque para executar ataques simulados de phishing e senha em suas organizações do Microsoft 365 E5 ou Microsoft Defender for Office 365 Plano 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 824ee04e2fcf0757a7eb32b48246bf1a1c638926
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175878"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="45051-103">Simulador de Ataque no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="45051-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="45051-104">**Aplica-se ao** [Microsoft Defender para Office 365 plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)</span><span class="sxs-lookup"><span data-stu-id="45051-104">**Applies to** [Microsoft Defender for Office 365 plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)</span></span>

<span data-ttu-id="45051-105">Se sua organização tiver o Microsoft Defender para Office 365 Plano 2, que inclui recursos de Investigação e Resposta contra [Ameaças,](office-365-ti.md)você poderá usar o Simulador de Ataques no Centro de Conformidade e Segurança & para executar cenários de ataque realistas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="45051-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="45051-106">Esses ataques simulados podem ajudá-lo a identificar e encontrar usuários vulneráveis antes que um ataque real a impacte seu resultado final.</span><span class="sxs-lookup"><span data-stu-id="45051-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="45051-107">Leia este artigo para saber mais.</span><span class="sxs-lookup"><span data-stu-id="45051-107">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="45051-108">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="45051-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="45051-109">Para abrir o Centro de Conformidade e Segurança, acesse <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="45051-109">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="45051-110">Simulador de ataque está disponível no **Simulador de** \> **ataques de gerenciamento de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="45051-110">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="45051-111">Vá diretamente para o simulador de ataques, <https://protection.office.com/attacksimulator> abra.</span><span class="sxs-lookup"><span data-stu-id="45051-111">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="45051-112">Para saber mais sobre a disponibilidade do Simulador de Ataque em diferentes assinaturas do Microsoft 365, confira a descrição do serviço do [Microsoft Defender para Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="45051-112">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="45051-113">Você precisa ser membro dos grupos de função Gerenciamento da Organização **ou** **Administrador de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="45051-113">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="45051-114">Para obter mais informações sobre grupos de funções no Centro de Conformidade e Segurança, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="45051-114">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="45051-115">Sua conta precisa ser configurada para autenticação multifatória (MFA) para criar e gerenciar campanhas no Simulador de Ataques.</span><span class="sxs-lookup"><span data-stu-id="45051-115">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="45051-116">Para obter instruções, [consulte Configurar a autenticação multifa factor.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)</span><span class="sxs-lookup"><span data-stu-id="45051-116">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="45051-117">As campanhas de phishing coletarão e processarão eventos por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="45051-117">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="45051-118">Os dados históricos da campanha estarão disponíveis por até 90 dias após o lançamento da campanha.</span><span class="sxs-lookup"><span data-stu-id="45051-118">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="45051-119">Os dados relacionados à simulação de ataque e treinamento são armazenados com outros dados do cliente para os serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="45051-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="45051-120">Para saber mais, confira [locais de dados do Microsoft 365.](/microsoft-365/enterprise/o365-data-locations)</span><span class="sxs-lookup"><span data-stu-id="45051-120">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

- <span data-ttu-id="45051-121">Não há cmdlets do PowerShell correspondentes para o Simulador de Ataque.</span><span class="sxs-lookup"><span data-stu-id="45051-121">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="45051-122">Campanhas de phishing em banda</span><span class="sxs-lookup"><span data-stu-id="45051-122">Spear phishing campaigns</span></span>

<span data-ttu-id="45051-123">*Phishing* é um termo genérico para ataques de email que tentam roubar informações confidenciais em mensagens que parecem ser de senders legítimos ou confiáveis.</span><span class="sxs-lookup"><span data-stu-id="45051-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="45051-124">*O phishing* em busca de phishing é um ataque de phishing direcionado que usa conteúdo focado e personalizado especificamente adaptado aos destinatários de alvo (normalmente, após a ida e volta aos destinatários pelo invasor).</span><span class="sxs-lookup"><span data-stu-id="45051-124">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="45051-125">No Simulador de Ataques, dois tipos diferentes de campanhas de phishing de phishing estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="45051-125">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="45051-126">**Phishing de nome (coleta de credenciais)**: o ataque tenta convencer os destinatários a clicar em uma URL na mensagem.</span><span class="sxs-lookup"><span data-stu-id="45051-126">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="45051-127">Se eles clicarem no link, serão solicitados a inserir suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="45051-127">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="45051-128">Se o fizerem, eles serão levados para um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="45051-128">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="45051-129">Uma página padrão que explica que isso foi apenas um teste e fornece dicas para reconhecer mensagens de phishing.</span><span class="sxs-lookup"><span data-stu-id="45051-129">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![O que os usuários verão se clicarem no link de phishing e inserirem suas credenciais](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="45051-131">Uma página personalizada (URL) que você especificar.</span><span class="sxs-lookup"><span data-stu-id="45051-131">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="45051-132">**Phishing (anexo)**: o ataque tenta convencer os destinatários a abrir um anexo .docx ou .pdf na mensagem.</span><span class="sxs-lookup"><span data-stu-id="45051-132">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="45051-133">O anexo contém o mesmo conteúdo do link de phishing padrão, mas a primeira frase começa com " \<Display Name\> , you are seeing this message as a recent email message you opened...".</span><span class="sxs-lookup"><span data-stu-id="45051-133">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="45051-134">Atualmente, as campanhas de phishing em phishing no Simulador de Ataques não expiram.</span><span class="sxs-lookup"><span data-stu-id="45051-134">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="45051-135">Criar uma campanha de phishing em forma de phishing</span><span class="sxs-lookup"><span data-stu-id="45051-135">Create a spear phishing campaign</span></span>

<span data-ttu-id="45051-136">Uma parte importante de qualquer campanha de phishing de phishing é a aparência da mensagem de email que é enviada aos destinatários de alvo.</span><span class="sxs-lookup"><span data-stu-id="45051-136">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="45051-137">Para criar e configurar a mensagem de email, você tem estas opções:</span><span class="sxs-lookup"><span data-stu-id="45051-137">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="45051-138">**Use um modelo de email integrado:** dois modelos integrados estão disponíveis: **Giveaway e Payroll** **Update.**</span><span class="sxs-lookup"><span data-stu-id="45051-138">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="45051-139">Você pode personalizar ainda mais algumas, todas ou nenhuma das propriedades de email do modelo ao criar e iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="45051-139">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="45051-140">**Crie um modelo de email** reutilizável: depois de criar e salvar o modelo de email, você poderá usá-lo novamente em futuras campanhas de phishing.</span><span class="sxs-lookup"><span data-stu-id="45051-140">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="45051-141">Você pode personalizar ainda mais algumas, todas ou nenhuma das propriedades de email do modelo ao criar e iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="45051-141">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="45051-142">**Crie a mensagem de email no assistente:** você pode criar a mensagem de email diretamente no assistente ao criar e iniciar a campanha de phishing.</span><span class="sxs-lookup"><span data-stu-id="45051-142">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="45051-143">Etapa 1 (opcional): criar um modelo de email personalizado</span><span class="sxs-lookup"><span data-stu-id="45051-143">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="45051-144">Se você for usar um dos modelos integrados ou criar a mensagem de email diretamente no assistente, ignore esta etapa.</span><span class="sxs-lookup"><span data-stu-id="45051-144">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="45051-145">No Centro de Conformidade & segurança, vá para o simulador de ataques **de gerenciamento** \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="45051-145">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="45051-146">Na página **Simular ataques,** nas seções Phishing de Phishing de Phishing (Credenciais **de Coleta)** ou Phishing de **Phishing (Anexo),** clique em **Detalhes do Ataque.**</span><span class="sxs-lookup"><span data-stu-id="45051-146">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="45051-147">Não importa onde você criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="45051-147">It doesn't matter where you create the template.</span></span> <span data-ttu-id="45051-148">As opções disponíveis no modelo são as mesmas para ambos os tipos de ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="45051-148">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="45051-149">Na página Detalhes **do** ataque que é aberta, na  seção Modelos de **Phishing,** na área Criar Modelos, clique em **Novo Modelo.**</span><span class="sxs-lookup"><span data-stu-id="45051-149">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="45051-150">O **assistente Configurar Modelo de Phishing** é iniciado em um novo flyout.</span><span class="sxs-lookup"><span data-stu-id="45051-150">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="45051-151">Na etapa **Iniciar,** insira um nome de exibição exclusivo para o modelo e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="45051-151">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="45051-152">Na etapa **Configurar detalhes de email,** de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="45051-152">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="45051-153">**De (Nome)**: o nome de exibição usado para o remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="45051-153">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="45051-154">**De (Email)**: o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="45051-154">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="45051-155">**URL do Servidor de Logon de Phishing:** clique no drop down e selecione uma das URLs disponíveis na lista.</span><span class="sxs-lookup"><span data-stu-id="45051-155">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="45051-156">Esta é a URL em que os usuários serão tentados a clicar.</span><span class="sxs-lookup"><span data-stu-id="45051-156">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="45051-157">As opções são:</span><span class="sxs-lookup"><span data-stu-id="45051-157">The choices are:</span></span>

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
     >
     > <span data-ttu-id="45051-158">Um serviço de reputação de URL pode identificar uma ou mais dessas URLs como não seguras.</span><span class="sxs-lookup"><span data-stu-id="45051-158">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="45051-159">Verifique a disponibilidade da URL em seus navegadores da Web com suporte antes de usar a URL em uma campanha de phishing.</span><span class="sxs-lookup"><span data-stu-id="45051-159">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="45051-160">**URL da Página de** Aterrissagem Personalizada: insira uma página inicial opcional onde os usuários serão levados se clicarem no link de phishing e inserirem suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="45051-160">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="45051-161">Esse link substitui a página de aterrissagem padrão.</span><span class="sxs-lookup"><span data-stu-id="45051-161">This link replaces the default landing page.</span></span> <span data-ttu-id="45051-162">Por exemplo, se você tiver treinamento interno de reconhecimento, poderá especificar essa URL aqui.</span><span class="sxs-lookup"><span data-stu-id="45051-162">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="45051-163">**Categoria**: Atualmente, essa configuração não é usada (qualquer coisa que você inserir será ignorada).</span><span class="sxs-lookup"><span data-stu-id="45051-163">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="45051-164">**Assunto**: o **campo Assunto** da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="45051-164">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="45051-165">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="45051-165">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="45051-166">Na etapa **Redigir email,** crie o corpo da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="45051-166">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="45051-167">Você pode usar a **guia Email** (um editor de HTML rico) ou a guia **Fonte** (código HTML bruto).</span><span class="sxs-lookup"><span data-stu-id="45051-167">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="45051-168">A formatação HTML pode ser tão simples ou complexa quanto você precisa.</span><span class="sxs-lookup"><span data-stu-id="45051-168">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="45051-169">Você pode inserir imagens e texto para melhorar a capacidade de acreditar da mensagem no cliente de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="45051-169">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="45051-170">`${username}` insere o nome do destinatário.</span><span class="sxs-lookup"><span data-stu-id="45051-170">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="45051-171">`${loginserverurl}` insere o valor da URL do Servidor de Logon de **Phishing** da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="45051-171">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="45051-172">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="45051-172">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="45051-173">Na etapa **Confirmar,** clique em **Concluir.**</span><span class="sxs-lookup"><span data-stu-id="45051-173">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="45051-174">Etapa 2: criar e iniciar a campanha de phishing de phishing</span><span class="sxs-lookup"><span data-stu-id="45051-174">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="45051-175">No Centro de Conformidade & segurança, vá para o simulador de ataques **de gerenciamento** \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="45051-175">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="45051-176">Na página **Simular ataques,** faça uma das seguintes seleções com base no tipo de campanha que você deseja criar:</span><span class="sxs-lookup"><span data-stu-id="45051-176">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="45051-177">Na seção **Phishing de Phishing (Coleta de Credenciais),** clique em **Iniciar** Ataque ou em **Ataque de Detalhes** de \> **Ataque.**</span><span class="sxs-lookup"><span data-stu-id="45051-177">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="45051-178">Na seção **Phishing de Phishing (Anexo),** clique em **Iniciar Ataque** ou em **Ataque de Detalhes** de \> **Ataque.**</span><span class="sxs-lookup"><span data-stu-id="45051-178">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="45051-179">O **assistente Configurar Ataque de Phishing** é iniciado em um novo flyout.</span><span class="sxs-lookup"><span data-stu-id="45051-179">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="45051-180">Na etapa **Iniciar,** faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="45051-180">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="45051-181">Na caixa **Nome,** insira um nome de exibição exclusivo para a campanha.</span><span class="sxs-lookup"><span data-stu-id="45051-181">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="45051-182">Não clique em **Usar Modelo,** pois você criará a mensagem de email posteriormente no assistente.</span><span class="sxs-lookup"><span data-stu-id="45051-182">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="45051-183">Clique **em Usar** Modelo e selecione um modelo de email personalizado ou integrado.</span><span class="sxs-lookup"><span data-stu-id="45051-183">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="45051-184">Depois de selecionar o modelo, a **caixa** Nome será preenchida automaticamente com base no modelo, mas você poderá alterar o nome.</span><span class="sxs-lookup"><span data-stu-id="45051-184">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="45051-185">![Página Inicial de Phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="45051-185">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="45051-186">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="45051-186">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="45051-187">Na etapa **Destinatários de** destino, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="45051-187">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="45051-188">Clique **no Livro de** Endereços para selecionar os destinatários (usuários ou grupos) da campanha.</span><span class="sxs-lookup"><span data-stu-id="45051-188">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="45051-189">Cada destinatário de alvo deve ter uma caixa de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="45051-189">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="45051-190">Se você clicar em **Filtrar** **e Aplicar** sem inserir critérios de pesquisa, todos os destinatários serão retornados e adicionados à campanha.</span><span class="sxs-lookup"><span data-stu-id="45051-190">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="45051-191">Clique **em Importar** e **Importar** Arquivo para importar um valor separado por vírgula (CSV) ou arquivo separado por linha de endereços de email.</span><span class="sxs-lookup"><span data-stu-id="45051-191">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="45051-192">Cada linha deve conter o endereço de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="45051-192">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="45051-193">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="45051-193">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="45051-194">Na etapa **Configurar detalhes de email,** de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="45051-194">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="45051-195">Se você selecionou um modelo **na** etapa Iniciar, a maioria desses valores já está configurada, mas você pode alterá-los.</span><span class="sxs-lookup"><span data-stu-id="45051-195">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="45051-196">**De (Nome)**: o nome de exibição usado para o remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="45051-196">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="45051-197">**De (Email)**: o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="45051-197">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="45051-198">Você pode inserir um endereço de email real ou falso do domínio de email da sua organização ou pode inserir um endereço de email externo real ou falso.</span><span class="sxs-lookup"><span data-stu-id="45051-198">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="45051-199">Um endereço de email válido do remetente da sua organização será, na verdade, resolvido no cliente de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="45051-199">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="45051-200">**URL do Servidor de Logon de Phishing:** clique no drop down e selecione uma das URLs disponíveis na lista.</span><span class="sxs-lookup"><span data-stu-id="45051-200">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="45051-201">Esta é a URL em que os usuários serão tentados a clicar.</span><span class="sxs-lookup"><span data-stu-id="45051-201">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="45051-202">As opções são:</span><span class="sxs-lookup"><span data-stu-id="45051-202">The choices are:</span></span>

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
     >
     > - <span data-ttu-id="45051-203">Todas as URLs são intencionalmente http, não https.</span><span class="sxs-lookup"><span data-stu-id="45051-203">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="45051-204">Um serviço de reputação de URL pode identificar uma ou mais dessas URLs como não seguras.</span><span class="sxs-lookup"><span data-stu-id="45051-204">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="45051-205">Verifique a disponibilidade da URL em seus navegadores da Web com suporte antes de usar a URL em uma campanha de phishing.</span><span class="sxs-lookup"><span data-stu-id="45051-205">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="45051-206">Você precisa selecionar uma URL.</span><span class="sxs-lookup"><span data-stu-id="45051-206">You are required to select a URL.</span></span> <span data-ttu-id="45051-207">Para **campanhas** de Phishing de Phishing (Anexo), você pode remover o link do corpo da mensagem na próxima etapa (caso contrário, a mensagem conterá um **link** e um anexo).</span><span class="sxs-lookup"><span data-stu-id="45051-207">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="45051-208">**Tipo de anexo:** essa configuração só está disponível em campanhas **de Phishing de Phishing (Anexo).**</span><span class="sxs-lookup"><span data-stu-id="45051-208">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="45051-209">Clique no drop down e selecione **. DOCX** ou **. PDF** da lista.</span><span class="sxs-lookup"><span data-stu-id="45051-209">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="45051-210">**Nome do** anexo: essa configuração só está disponível em campanhas **de Phishing de Phishing (Anexo).**</span><span class="sxs-lookup"><span data-stu-id="45051-210">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="45051-211">Insira um nome de arquivo para o anexo .docx ou .pdf.</span><span class="sxs-lookup"><span data-stu-id="45051-211">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="45051-212">**URL da Página de** Aterrissagem Personalizada: insira uma página inicial opcional onde os usuários serão levados se clicarem no link de phishing e inserirem suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="45051-212">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="45051-213">Esse link substitui a página de aterrissagem padrão.</span><span class="sxs-lookup"><span data-stu-id="45051-213">This link replaces the default landing page.</span></span> <span data-ttu-id="45051-214">Por exemplo, se você tiver treinamento interno de reconhecimento, poderá especificar essa URL aqui.</span><span class="sxs-lookup"><span data-stu-id="45051-214">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="45051-215">**Assunto**: o **campo Assunto** da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="45051-215">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="45051-216">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="45051-216">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="45051-217">Na etapa **Redigir email,** crie o corpo da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="45051-217">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="45051-218">Se você selecionou um modelo **na** etapa Iniciar, o corpo da mensagem já está configurado, mas você pode personalizá-lo.</span><span class="sxs-lookup"><span data-stu-id="45051-218">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="45051-219">Você pode usar a **guia Email** (um editor de HTML rico) ou a guia **Fonte** (código HTML bruto).</span><span class="sxs-lookup"><span data-stu-id="45051-219">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="45051-220">A formatação HTML pode ser tão simples ou complexa quanto você precisa.</span><span class="sxs-lookup"><span data-stu-id="45051-220">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="45051-221">Você pode inserir imagens e texto para melhorar a capacidade de acreditar da mensagem no cliente de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="45051-221">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="45051-222">`${username}` insere o nome do destinatário.</span><span class="sxs-lookup"><span data-stu-id="45051-222">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="45051-223">`${loginserverurl}`insere o valor da URL do Servidor de **Logon de Phishing.**</span><span class="sxs-lookup"><span data-stu-id="45051-223">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="45051-224">Para campanhas de **Phishing** de Phishing (Anexo), você deve remover o link do corpo da mensagem (caso contrário, a mensagem conterá um **link** e um anexo, e os cliques de link não serão rastreados em uma campanha de anexo).</span><span class="sxs-lookup"><span data-stu-id="45051-224">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="45051-225">![Corpo do email de composição](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="45051-225">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="45051-226">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="45051-226">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="45051-227">Na etapa **Confirmar,** clique em **Concluir** para iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="45051-227">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="45051-228">A mensagem de phishing é entregue aos destinatários de alvo.</span><span class="sxs-lookup"><span data-stu-id="45051-228">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="45051-229">Campanhas de ataque de senha</span><span class="sxs-lookup"><span data-stu-id="45051-229">Password attack campaigns</span></span>

<span data-ttu-id="45051-230">Um *ataque de senha* tenta adivinhar senhas para contas de usuário em uma organização, normalmente depois que o invasor identifica uma ou mais contas de usuário válidas.</span><span class="sxs-lookup"><span data-stu-id="45051-230">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="45051-231">No Simulador de Ataques, dois tipos diferentes de campanhas de ataque de senha estão disponíveis para você testar a complexidade das senhas dos usuários:</span><span class="sxs-lookup"><span data-stu-id="45051-231">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="45051-232">Senha de força bruta (ataque  de  **dicionário)**: um ataque de força bruta ou de dicionário usa um arquivo de dicionário grande de senhas em uma conta de usuário com a expectativa de que uma delas funcione (muitas senhas em uma conta).</span><span class="sxs-lookup"><span data-stu-id="45051-232">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="45051-233">Bloqueios de senha incorretos ajudam a impedir ataques de senha de força bruta.</span><span class="sxs-lookup"><span data-stu-id="45051-233">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="45051-234">Para o ataque de dicionário, você pode especificar uma ou várias senhas para tentar (inseridas manualmente ou em um arquivo carregado) e você pode especificar um ou vários usuários.</span><span class="sxs-lookup"><span data-stu-id="45051-234">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="45051-235">**Ataque de pulverização de** senha: um ataque de *pulverização* de senha usa a mesma senha cuidadosamente considerada em uma lista de contas de usuário (uma senha em várias contas).</span><span class="sxs-lookup"><span data-stu-id="45051-235">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="45051-236">Ataques de pulverização de senha são mais difíceis de detectar do que ataques de senha de força bruta (a probabilidade de sucesso aumenta quando um invasor tenta uma senha em dezenas ou centenas de contas sem o risco de bloquear a senha incorreta do usuário).</span><span class="sxs-lookup"><span data-stu-id="45051-236">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="45051-237">Para o ataque de pulverização de senha, você só pode especificar uma senha para tentar, e você pode especificar um ou vários usuários.</span><span class="sxs-lookup"><span data-stu-id="45051-237">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="45051-238">Os ataques de senha no Simulador de Ataque passam o nome de usuário e a senha Solicitações de autenticação básicas para um ponto de extremidade, para que também funcionem com outros métodos de autenticação (AD FS, sincronização de hash de senha, passagem, PingFederate, etc.).</span><span class="sxs-lookup"><span data-stu-id="45051-238">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="45051-239">Para os usuários que têm a MFA habilitada, mesmo que o ataque de senha tente sua senha real, a tentativa sempre se registrará como uma falha (em outras palavras, os usuários da MFA nunca aparecerão na contagem de tentativas bem-sucedidas da campanha). </span><span class="sxs-lookup"><span data-stu-id="45051-239">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="45051-240">Esse é o resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="45051-240">This is the expected result.</span></span> <span data-ttu-id="45051-241">A MFA é um método principal para ajudar a proteger contra ataques de senha.</span><span class="sxs-lookup"><span data-stu-id="45051-241">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="45051-242">Criar e iniciar uma campanha de ataque de senha</span><span class="sxs-lookup"><span data-stu-id="45051-242">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="45051-243">No Centro de Conformidade & segurança, vá para o simulador de ataques **de gerenciamento** \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="45051-243">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="45051-244">Na página **Simular ataques,** faça uma das seguintes seleções com base no tipo de campanha que você deseja criar:</span><span class="sxs-lookup"><span data-stu-id="45051-244">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="45051-245">Na seção **Senha de Força Bruta (Ataque de** Dicionário), clique em **Iniciar** Ataque ou em Ataque **de Detalhes** \> **de Ataque.**</span><span class="sxs-lookup"><span data-stu-id="45051-245">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="45051-246">na seção **Ataque de pulverização de** senha, clique em Iniciar **Ataque** ou em Ataque **de Detalhes** \> **de Ataque.**</span><span class="sxs-lookup"><span data-stu-id="45051-246">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="45051-247">O **assistente Configurar Ataque de** Senha é iniciado em um novo flyout.</span><span class="sxs-lookup"><span data-stu-id="45051-247">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="45051-248">Na etapa **Iniciar,** insira um nome de exibição exclusivo para a campanha e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="45051-248">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="45051-249">Na etapa **Usuários de** destino, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="45051-249">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="45051-250">Clique **no Livro de** Endereços para selecionar os destinatários (usuários ou grupos) da campanha.</span><span class="sxs-lookup"><span data-stu-id="45051-250">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="45051-251">Cada destinatário de alvo deve ter uma caixa de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="45051-251">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="45051-252">Se você clicar em **Filtrar** **e Aplicar** sem inserir critérios de pesquisa, todos os destinatários serão retornados e adicionados à campanha.</span><span class="sxs-lookup"><span data-stu-id="45051-252">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="45051-253">Clique **em Importar** e **Importar** Arquivo para importar um valor separado por vírgula (CSV) ou arquivo separado por linha de endereços de email.</span><span class="sxs-lookup"><span data-stu-id="45051-253">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="45051-254">Cada linha deve conter o endereço de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="45051-254">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="45051-255">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="45051-255">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="45051-256">Na etapa **Escolher configurações de ataque,** escolha o que fazer com base no tipo de campanha:</span><span class="sxs-lookup"><span data-stu-id="45051-256">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="45051-257">**Senha de Força Bruta (Ataque de Dicionário)**: faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="45051-257">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="45051-258">**Insira senhas manualmente:** pressione Enter **para adicionar uma caixa** de senha, digite uma senha e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="45051-258">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="45051-259">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="45051-259">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="45051-260">**Carregar senhas de um** arquivo  de dicionário: clique em Carregar para importar um arquivo de texto existente que contenha uma senha em cada linha e uma última linha em branco.</span><span class="sxs-lookup"><span data-stu-id="45051-260">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="45051-261">O arquivo de texto deve ter 10 MB ou menos de tamanho e não pode conter mais de 30.000 senhas.</span><span class="sxs-lookup"><span data-stu-id="45051-261">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="45051-262">**Ataque de pulverização** de senha: **nas senhas a usar na caixa de** ataque, insira uma senha.</span><span class="sxs-lookup"><span data-stu-id="45051-262">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="45051-263">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="45051-263">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="45051-264">Na etapa **Confirmar,** clique em **Concluir** para iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="45051-264">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="45051-265">As senhas especificadas são tentadas nos usuários especificados.</span><span class="sxs-lookup"><span data-stu-id="45051-265">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="45051-266">Exibir resultados da campanha</span><span class="sxs-lookup"><span data-stu-id="45051-266">View campaign results</span></span>

<span data-ttu-id="45051-267">Depois de iniciar uma campanha, você pode verificar o progresso e os resultados na página principal **simular ataques.**</span><span class="sxs-lookup"><span data-stu-id="45051-267">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="45051-268">As campanhas ativas mostrarão uma barra de status, um valor percentual concluído e a contagem "(usuários concluídos) de (usuários totais)".</span><span class="sxs-lookup"><span data-stu-id="45051-268">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="45051-269">Clicar no botão **Atualizar** atualizará o progresso de quaisquer campanhas ativas.</span><span class="sxs-lookup"><span data-stu-id="45051-269">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="45051-270">Você também pode clicar **em Encerrar** para interromper uma campanha ativa.</span><span class="sxs-lookup"><span data-stu-id="45051-270">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="45051-271">Quando a campanha é concluída, o status muda para **Ataque concluído.**</span><span class="sxs-lookup"><span data-stu-id="45051-271">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="45051-272">Você pode exibir os resultados da campanha fazendo uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="45051-272">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="45051-273">Na página principal **Simular ataques,** clique **em Exibir Relatório** com o nome da campanha.</span><span class="sxs-lookup"><span data-stu-id="45051-273">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="45051-274">Na página principal **Simular ataques,** clique em **Detalhes** do Ataque na seção para o tipo de ataque.</span><span class="sxs-lookup"><span data-stu-id="45051-274">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="45051-275">Na página **Detalhes do ataque** que é aberta, selecione a campanha na seção Histórico **de** Ataques.</span><span class="sxs-lookup"><span data-stu-id="45051-275">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="45051-276">Qualquer uma das ações anteriores levará você a uma página chamada **Detalhes do ataque.**</span><span class="sxs-lookup"><span data-stu-id="45051-276">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="45051-277">As informações disponíveis nesta página para cada tipo de campanha são descritas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="45051-277">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="45051-278">Resultados da campanha de Phishing de Phishing (Coleta de Credenciais)</span><span class="sxs-lookup"><span data-stu-id="45051-278">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="45051-279">As informações a seguir estão disponíveis na página **Detalhes do** ataque para cada campanha:</span><span class="sxs-lookup"><span data-stu-id="45051-279">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="45051-280">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="45051-280">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="45051-281">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="45051-281">**Total users targeted**</span></span>

- <span data-ttu-id="45051-282">**Tentativas** bem-sucedidas: o número de usuários que clicaram no **link** e forneceram suas credenciais (qualquer valor *de* nome de usuário e senha).</span><span class="sxs-lookup"><span data-stu-id="45051-282">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="45051-283">**Taxa de Sucesso Geral**: Uma porcentagem calculada pelas tentativas bem-sucedidas total de  /  **usuários direcionados.**</span><span class="sxs-lookup"><span data-stu-id="45051-283">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="45051-284">**Clique mais** rápido: quanto tempo o primeiro usuário levou para clicar no link depois de iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="45051-284">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="45051-285">**Clique médio**: a soma de quanto tempo todos demoraram para clicar no link dividido pelo número de usuários que clicaram no link.</span><span class="sxs-lookup"><span data-stu-id="45051-285">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="45051-286">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span><span class="sxs-lookup"><span data-stu-id="45051-286">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="45051-287">**Credenciais mais rápidas:** quanto tempo o primeiro usuário levou para inserir suas credenciais depois de iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="45051-287">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="45051-288">**Credenciais médias:** a soma do tempo que todos demoraram para inserir suas credenciais divididas pelo número de usuários que inseriram suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="45051-288">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="45051-289">**Taxa de Sucesso da** Credencial: Uma porcentagem calculada por (número de usuários que ins inseridas em suas credenciais) / **Total de usuários direcionados.**</span><span class="sxs-lookup"><span data-stu-id="45051-289">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="45051-290">Um gráfico de barras que mostra **o link clicado** e os **números fornecidos de credencial** por dia.</span><span class="sxs-lookup"><span data-stu-id="45051-290">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="45051-291">Um gráfico em círculo que mostra **as porcentagens Link clicado**, **Credencial** fornecida e Nenhuma para a campanha. </span><span class="sxs-lookup"><span data-stu-id="45051-291">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="45051-292">A **seção Usuários** Comprometidos lista os detalhes dos usuários que clicaram no link:</span><span class="sxs-lookup"><span data-stu-id="45051-292">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="45051-293">O endereço de email do usuário</span><span class="sxs-lookup"><span data-stu-id="45051-293">The user's email address</span></span>

  - <span data-ttu-id="45051-294">A data/hora em que eles clicaram no link.</span><span class="sxs-lookup"><span data-stu-id="45051-294">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="45051-295">O endereço IP do cliente.</span><span class="sxs-lookup"><span data-stu-id="45051-295">The client IP address.</span></span>

  - <span data-ttu-id="45051-296">Detalhes sobre a versão do usuário do Windows e do navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="45051-296">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="45051-297">Você pode clicar **em Exportar** para exportar os resultados para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="45051-297">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="45051-298">Resultados da campanha de Phishing de Phishing (Anexo)</span><span class="sxs-lookup"><span data-stu-id="45051-298">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="45051-299">As informações a seguir estão disponíveis na página **Detalhes do** ataque para cada campanha:</span><span class="sxs-lookup"><span data-stu-id="45051-299">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="45051-300">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="45051-300">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="45051-301">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="45051-301">**Total users targeted**</span></span>

- <span data-ttu-id="45051-302">**Tentativas** bem-sucedidas: o número de usuários que abriram ou baixaram e abriram o anexo (a visualização não conta).</span><span class="sxs-lookup"><span data-stu-id="45051-302">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="45051-303">**Taxa de Sucesso Geral**: Uma porcentagem calculada pelas tentativas bem-sucedidas total de  /  **usuários direcionados.**</span><span class="sxs-lookup"><span data-stu-id="45051-303">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="45051-304">**Tempo de abertura do anexo mais** rápido: quanto tempo o primeiro usuário levou para abrir o anexo depois que você iniciou a campanha.</span><span class="sxs-lookup"><span data-stu-id="45051-304">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="45051-305">**Tempo médio de abertura do anexo:** a soma de quanto tempo todos demoraram para abrir o anexo dividido pelo número de usuários que abriram o anexo.</span><span class="sxs-lookup"><span data-stu-id="45051-305">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="45051-306">**Taxa de sucesso de abertura de** anexos: Uma porcentagem calculada por (número de usuários que abriram o anexo) / Total de usuários **direcionados.**</span><span class="sxs-lookup"><span data-stu-id="45051-306">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="45051-307">Resultados da campanha senha de força bruta (ataque de dicionário)</span><span class="sxs-lookup"><span data-stu-id="45051-307">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="45051-308">As informações a seguir estão disponíveis na página **Detalhes do** ataque para cada campanha:</span><span class="sxs-lookup"><span data-stu-id="45051-308">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="45051-309">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="45051-309">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="45051-310">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="45051-310">**Total users targeted**</span></span>

- <span data-ttu-id="45051-311">**Tentativas** bem-sucedidas: o número de usuários que foram encontrados usando uma das senhas especificadas.</span><span class="sxs-lookup"><span data-stu-id="45051-311">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="45051-312">**Taxa de Sucesso Geral**: Uma porcentagem calculada pelas tentativas bem-sucedidas total de  /  **usuários direcionados.**</span><span class="sxs-lookup"><span data-stu-id="45051-312">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="45051-313">A **seção Usuários Comprometidos** lista os endereços de email dos usuários afetados.</span><span class="sxs-lookup"><span data-stu-id="45051-313">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="45051-314">Você pode clicar **em Exportar** para exportar os resultados para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="45051-314">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="45051-315">Resultados da campanha de ataque de pulverização de senha</span><span class="sxs-lookup"><span data-stu-id="45051-315">Password spray attack campaign results</span></span>

<span data-ttu-id="45051-316">As informações a seguir estão disponíveis na página **Detalhes do** ataque para cada campanha:</span><span class="sxs-lookup"><span data-stu-id="45051-316">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="45051-317">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="45051-317">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="45051-318">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="45051-318">**Total users targeted**</span></span>

- <span data-ttu-id="45051-319">**Tentativas** bem-sucedidas: o número de usuários que foram encontrados usando a senha especificada.</span><span class="sxs-lookup"><span data-stu-id="45051-319">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="45051-320">**Taxa de Sucesso Geral**: Uma porcentagem calculada pelas tentativas bem-sucedidas total de  /  **usuários direcionados.**</span><span class="sxs-lookup"><span data-stu-id="45051-320">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
