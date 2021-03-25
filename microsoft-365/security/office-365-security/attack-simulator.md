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
description: Os administradores podem aprender a usar o Simulador de Ataques para executar ataques simulados de phishing e senha em suas organizações do Microsoft 365 E5 ou do Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 637e84281b85e8c859207ae81342a3c6ab3d00be
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203003"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="bced3-103">Simulador de Ataque no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="bced3-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bced3-104">**Aplica-se ao** [Microsoft Defender para Office 365 plano 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="bced3-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="bced3-105">Se sua organização tiver o Microsoft Defender para Office 365 Plano 2, que inclui recursos de Investigação e Resposta contra [Ameaças,](office-365-ti.md)você poderá usar o Simulador de Ataques no Centro de Conformidade & Segurança para executar cenários de ataque realistas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="bced3-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="bced3-106">Esses ataques simulados podem ajudá-lo a identificar e encontrar usuários vulneráveis antes que um ataque real impacte sua linha inferior.</span><span class="sxs-lookup"><span data-stu-id="bced3-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="bced3-107">Leia este artigo para saber mais.</span><span class="sxs-lookup"><span data-stu-id="bced3-107">Read this article to learn more.</span></span>

> [!NOTE]
>
> <span data-ttu-id="bced3-108">O Simulador de Ataque, conforme descrito neste artigo,  agora é somente leitura e foi substituído pelo treinamento de simulação de ataque no nó de colaboração **email &** no centro de segurança do [Microsoft 365.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="bced3-108">Attack Simulator as described in this article is now read-only and has been replaced by **Attack simulation training** in the **Email & collaboration** node in the [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="bced3-109">Para obter mais informações, consulte [Começar a usar o treinamento de simulação de ataque](attack-simulation-training-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="bced3-109">For more information, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
>
> <span data-ttu-id="bced3-110">A capacidade de iniciar novas simulações dessa versão do Simulador de Ataque foi desabilitada.</span><span class="sxs-lookup"><span data-stu-id="bced3-110">The ability to launch new simulations from this version of Attack Simulator has been disabled.</span></span> <span data-ttu-id="bced3-111">No entanto, você ainda pode acessar relatórios por até 90 dias a partir de 24 de janeiro de 2021.</span><span class="sxs-lookup"><span data-stu-id="bced3-111">However, you can still access reports for up to 90 days from January 24, 2021.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bced3-112">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="bced3-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bced3-113">Para abrir o Centro de Conformidade e Segurança, acesse <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="bced3-113">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="bced3-114">Simulador de ataque está disponível no simulador **de ataques de gerenciamento** de \> **ameaças.**</span><span class="sxs-lookup"><span data-stu-id="bced3-114">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="bced3-115">Vá diretamente para o simulador de ataque, abra <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="bced3-115">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="bced3-116">Para obter mais informações sobre a disponibilidade do Simulador de Ataques em diferentes assinaturas do Microsoft 365, consulte [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="bced3-116">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="bced3-117">Você precisa ser membro dos grupos de função Gerenciamento da **Organização** ou **Administrador de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="bced3-117">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="bced3-118">Para obter mais informações sobre grupos de funções no Centro de Conformidade e Segurança, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="bced3-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="bced3-119">Sua conta precisa ser configurada para a autenticação multifato (MFA) para criar e gerenciar campanhas no Simulador de Ataques.</span><span class="sxs-lookup"><span data-stu-id="bced3-119">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="bced3-120">Para obter instruções, consulte [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="bced3-120">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="bced3-121">O Simulador de Ataque só funciona em caixas de correio baseadas em nuvem.</span><span class="sxs-lookup"><span data-stu-id="bced3-121">Attack Simulator only works on cloud-based mailboxes.</span></span>

- <span data-ttu-id="bced3-122">As campanhas de phishing coletarão e processarão eventos por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="bced3-122">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="bced3-123">Os dados históricos da campanha estarão disponíveis por até 90 dias após o início da campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-123">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="bced3-124">Dados relacionados à simulação de ataque e treinamento são armazenados com outros dados do cliente para serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bced3-124">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="bced3-125">Para obter mais informações, consulte Locais de dados [do Microsoft 365](../../enterprise/o365-data-locations.md).</span><span class="sxs-lookup"><span data-stu-id="bced3-125">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span>

- <span data-ttu-id="bced3-126">Não há cmdlets do PowerShell correspondentes para Simulador de Ataque.</span><span class="sxs-lookup"><span data-stu-id="bced3-126">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="bced3-127">Campanhas de phishing de lança</span><span class="sxs-lookup"><span data-stu-id="bced3-127">Spear phishing campaigns</span></span>

<span data-ttu-id="bced3-128">*Phishing* é um termo genérico para ataques de email que tentam roubar informações confidenciais em mensagens que parecem ser de senders legítimos ou confiáveis.</span><span class="sxs-lookup"><span data-stu-id="bced3-128">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="bced3-129">*Phishing de* lança é um ataque de phishing direcionado que usa conteúdo focado e personalizado especificamente personalizado para os destinatários direcionados (normalmente, após o reconhecimento nos destinatários pelo invasor).</span><span class="sxs-lookup"><span data-stu-id="bced3-129">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="bced3-130">No Simulador de Ataques, dois tipos diferentes de campanhas de phishing de lança estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="bced3-130">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="bced3-131">**Phishing de lança (coleta de credenciais)**: o ataque tenta convencer os destinatários a clicar em uma URL na mensagem.</span><span class="sxs-lookup"><span data-stu-id="bced3-131">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="bced3-132">Se eles clicarem no link, serão solicitados a inserir suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="bced3-132">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="bced3-133">Se fizerem isso, serão levados para um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="bced3-133">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="bced3-134">Uma página padrão que explica que isso foi apenas um teste e fornece dicas para reconhecer mensagens de phishing.</span><span class="sxs-lookup"><span data-stu-id="bced3-134">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![O que os usuários verão se clicarem no link de phishing e inserirem suas credenciais](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="bced3-136">Uma página personalizada (URL) que você especificar.</span><span class="sxs-lookup"><span data-stu-id="bced3-136">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="bced3-137">**Phishing de lança (anexo)**: O ataque tenta convencer os destinatários a abrir um anexo .docx ou .pdf na mensagem.</span><span class="sxs-lookup"><span data-stu-id="bced3-137">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="bced3-138">O anexo contém o mesmo conteúdo do link padrão de phishing, mas a primeira frase começa com " , você está vendo essa mensagem como uma mensagem de email recente que você \<Display Name\> abriu...".</span><span class="sxs-lookup"><span data-stu-id="bced3-138">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="bced3-139">Atualmente, as campanhas de phishing de lança no Simulador de Ataques não expiram.</span><span class="sxs-lookup"><span data-stu-id="bced3-139">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="bced3-140">Criar uma campanha de phishing de lança</span><span class="sxs-lookup"><span data-stu-id="bced3-140">Create a spear phishing campaign</span></span>

<span data-ttu-id="bced3-141">Uma parte importante de qualquer campanha de phishing de lança é a aparência da mensagem de email enviada aos destinatários direcionados.</span><span class="sxs-lookup"><span data-stu-id="bced3-141">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="bced3-142">Para criar e configurar a mensagem de email, você tem estas opções:</span><span class="sxs-lookup"><span data-stu-id="bced3-142">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="bced3-143">**Use um modelo de email integrado:** Dois modelos integrados estão disponíveis: **Oferta de** Prêmio e **Atualização de Folha de Pagamento.**</span><span class="sxs-lookup"><span data-stu-id="bced3-143">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="bced3-144">Você pode personalizar ainda mais algumas, todas ou nenhuma das propriedades de email do modelo ao criar e iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-144">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="bced3-145">**Criar um modelo de email** reutilizável : depois de criar e salvar o modelo de email, você pode usá-lo novamente em campanhas futuras de phishing de lança.</span><span class="sxs-lookup"><span data-stu-id="bced3-145">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="bced3-146">Você pode personalizar ainda mais algumas, todas ou nenhuma das propriedades de email do modelo ao criar e iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-146">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="bced3-147">**Crie a mensagem de email no assistente**: Você pode criar a mensagem de email diretamente no assistente ao criar e iniciar a campanha de phishing de lança.</span><span class="sxs-lookup"><span data-stu-id="bced3-147">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="bced3-148">Etapa 1 (Opcional): Criar um modelo de email personalizado</span><span class="sxs-lookup"><span data-stu-id="bced3-148">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="bced3-149">Se você vai usar um dos modelos integrados ou criar a mensagem de email diretamente no assistente, ignore esta etapa.</span><span class="sxs-lookup"><span data-stu-id="bced3-149">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="bced3-150">No Centro de Conformidade & segurança, vá para Simulador de ataque **de gerenciamento** \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="bced3-150">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="bced3-151">Na página **Simular ataques,** nas seções Phishing de Lança (Coleta de **Credenciais)** ou **Phishing** de Lança (Anexo), clique em **Detalhes de Ataque**.</span><span class="sxs-lookup"><span data-stu-id="bced3-151">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="bced3-152">Não importa onde você cria o modelo.</span><span class="sxs-lookup"><span data-stu-id="bced3-152">It doesn't matter where you create the template.</span></span> <span data-ttu-id="bced3-153">As opções disponíveis no modelo são as mesmas para ambos os tipos de ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="bced3-153">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="bced3-154">Na página **Detalhes de** ataque que é aberta, na seção Modelos **de Phishing,** na área **Criar Modelos,** clique em **Novo Modelo**.</span><span class="sxs-lookup"><span data-stu-id="bced3-154">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="bced3-155">O **assistente Configurar Modelo de Phishing** começa em um novo flyout.</span><span class="sxs-lookup"><span data-stu-id="bced3-155">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="bced3-156">Na etapa **Iniciar,** insira um nome de exibição exclusivo para o modelo e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="bced3-156">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="bced3-157">Na etapa **Configurar detalhes de email,** configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="bced3-157">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="bced3-158">**De (Nome)**: o nome de exibição usado para o remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="bced3-158">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="bced3-159">**De (Email)**: o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="bced3-159">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="bced3-160">**URL do Servidor de Logon de Phishing**: clique no drop-down e selecione uma das URLs disponíveis na lista.</span><span class="sxs-lookup"><span data-stu-id="bced3-160">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="bced3-161">Esta é a URL em que os usuários serão tentados a clicar.</span><span class="sxs-lookup"><span data-stu-id="bced3-161">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="bced3-162">As opções são:</span><span class="sxs-lookup"><span data-stu-id="bced3-162">The choices are:</span></span>

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
     > <span data-ttu-id="bced3-163">Um serviço de reputação de URL pode identificar uma ou mais DESSAS URLs como não seguras.</span><span class="sxs-lookup"><span data-stu-id="bced3-163">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="bced3-164">Verifique a disponibilidade da URL em seus navegadores da Web com suporte antes de usar a URL em uma campanha de phishing.</span><span class="sxs-lookup"><span data-stu-id="bced3-164">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="bced3-165">**URL da Página inicial personalizada**: insira uma página de aterrissagem opcional onde os usuários são levados se clicarem no link de phishing e inserirem suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="bced3-165">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="bced3-166">Este link substitui a página de aterrissagem padrão.</span><span class="sxs-lookup"><span data-stu-id="bced3-166">This link replaces the default landing page.</span></span> <span data-ttu-id="bced3-167">Por exemplo, se você tiver treinamento de reconhecimento interno, poderá especificar essa URL aqui.</span><span class="sxs-lookup"><span data-stu-id="bced3-167">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="bced3-168">**Categoria**: Atualmente, essa configuração não é usada (tudo o que você inserir é ignorado).</span><span class="sxs-lookup"><span data-stu-id="bced3-168">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="bced3-169">**Assunto**: O **campo Assunto** da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="bced3-169">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="bced3-170">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bced3-170">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="bced3-171">Na etapa **Escrever email,** crie o corpo da mensagem da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="bced3-171">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="bced3-172">Você pode usar a guia **Email** (um editor HTML rico) ou a guia **Origem** (código HTML bruto).</span><span class="sxs-lookup"><span data-stu-id="bced3-172">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="bced3-173">A formatação HTML pode ser tão simples ou complexa quanto você precisa.</span><span class="sxs-lookup"><span data-stu-id="bced3-173">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="bced3-174">Você pode inserir imagens e texto para melhorar a capacidade de acreditar da mensagem no cliente de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="bced3-174">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="bced3-175">`${username}` insere o nome do destinatário.</span><span class="sxs-lookup"><span data-stu-id="bced3-175">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="bced3-176">`${loginserverurl}` insere o valor de URL do Servidor de **Logon de Phishing** da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="bced3-176">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="bced3-177">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bced3-177">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="bced3-178">Na etapa **Confirmar,** clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="bced3-178">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="bced3-179">Etapa 2: Criar e iniciar a campanha de phishing de lança</span><span class="sxs-lookup"><span data-stu-id="bced3-179">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="bced3-180">No Centro de Conformidade & segurança, vá para Simulador de ataque **de gerenciamento** \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="bced3-180">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="bced3-181">Na página **Simular ataques,** faça uma das seguintes seleções com base no tipo de campanha que você deseja criar:</span><span class="sxs-lookup"><span data-stu-id="bced3-181">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="bced3-182">Na seção **Phishing de Lança (Coleta de Credenciais),** clique em **Iniciar Ataque** ou clique em **Ataque de Detalhes de** \> **Ataque.**</span><span class="sxs-lookup"><span data-stu-id="bced3-182">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="bced3-183">Na seção **Phishing de Lança (Anexo),** clique em **Iniciar Ataque** ou clique em **Ataque de Início de Detalhes de** \> **Ataque**.</span><span class="sxs-lookup"><span data-stu-id="bced3-183">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="bced3-184">O **assistente Configurar Ataques de Phishing** começa em um novo flyout.</span><span class="sxs-lookup"><span data-stu-id="bced3-184">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="bced3-185">Na etapa **Iniciar,** faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="bced3-185">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="bced3-186">Na caixa **Nome,** insira um nome de exibição exclusivo para a campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-186">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="bced3-187">Não clique em **Usar Modelo**, pois você criará a mensagem de email posteriormente no assistente.</span><span class="sxs-lookup"><span data-stu-id="bced3-187">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="bced3-188">Clique **em Usar Modelo** e selecione um modelo de email integrado ou personalizado.</span><span class="sxs-lookup"><span data-stu-id="bced3-188">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="bced3-189">Depois de selecionar o modelo, a caixa **Nome** é preenchida automaticamente com base no modelo, mas você pode alterar o nome.</span><span class="sxs-lookup"><span data-stu-id="bced3-189">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bced3-190">![Página inicial de phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="bced3-190">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="bced3-191">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bced3-191">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="bced3-192">Na etapa **Destinatários de** destino, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="bced3-192">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="bced3-193">Clique **em Livro de** Endereços para selecionar os destinatários (usuários ou grupos) da campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-193">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="bced3-194">Cada destinatário direcionado deve ter uma caixa de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bced3-194">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="bced3-195">Se você clicar **em Filtrar** **e Aplicar** sem inserir um critério de pesquisa, todos os destinatários serão retornados e adicionados à campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-195">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="bced3-196">Clique **em Importar** e **Importar** Arquivo para importar um valor separado por vírgula (CSV) ou arquivo separado por linha de endereços de email.</span><span class="sxs-lookup"><span data-stu-id="bced3-196">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="bced3-197">Cada linha deve conter o endereço de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="bced3-197">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="bced3-198">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bced3-198">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="bced3-199">Na etapa **Configurar detalhes de email,** configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="bced3-199">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="bced3-200">Se você selecionou um modelo **na** etapa Iniciar, a maioria desses valores já está configurada, mas você pode alterá-los.</span><span class="sxs-lookup"><span data-stu-id="bced3-200">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="bced3-201">**De (Nome)**: o nome de exibição usado para o remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="bced3-201">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="bced3-202">**De (Email)**: o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="bced3-202">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="bced3-203">Você pode inserir um endereço de email real ou falso do domínio de email da sua organização ou inserir um endereço de email externo real ou falso.</span><span class="sxs-lookup"><span data-stu-id="bced3-203">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="bced3-204">Um endereço de email de remetente válido da sua organização será resolvido no cliente de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="bced3-204">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="bced3-205">**URL do Servidor de Logon de Phishing**: clique no drop-down e selecione uma das URLs disponíveis na lista.</span><span class="sxs-lookup"><span data-stu-id="bced3-205">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="bced3-206">Esta é a URL em que os usuários serão tentados a clicar.</span><span class="sxs-lookup"><span data-stu-id="bced3-206">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="bced3-207">As opções são:</span><span class="sxs-lookup"><span data-stu-id="bced3-207">The choices are:</span></span>

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
     > - <span data-ttu-id="bced3-208">Todas as URLs são intencionalmente http, não https.</span><span class="sxs-lookup"><span data-stu-id="bced3-208">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="bced3-209">Um serviço de reputação de URL pode identificar uma ou mais DESSAS URLs como não seguras.</span><span class="sxs-lookup"><span data-stu-id="bced3-209">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="bced3-210">Verifique a disponibilidade da URL em seus navegadores da Web com suporte antes de usar a URL em uma campanha de phishing.</span><span class="sxs-lookup"><span data-stu-id="bced3-210">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="bced3-211">Você deve selecionar uma URL.</span><span class="sxs-lookup"><span data-stu-id="bced3-211">You are required to select a URL.</span></span> <span data-ttu-id="bced3-212">Para **campanhas de Phishing** de Lança (Anexo), você pode remover o link do corpo da mensagem na próxima etapa (caso contrário, a mensagem conterá um **link** e um anexo).</span><span class="sxs-lookup"><span data-stu-id="bced3-212">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="bced3-213">**Tipo de** anexo : essa configuração só está disponível em campanhas **de Phishing de Lança (Anexo).**</span><span class="sxs-lookup"><span data-stu-id="bced3-213">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="bced3-214">Clique na lista listada e selecione **. DOCX** ou **. PDF** da lista.</span><span class="sxs-lookup"><span data-stu-id="bced3-214">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="bced3-215">**Nome do** anexo : essa configuração só está disponível em campanhas de Phishing de Lança **(Anexo).**</span><span class="sxs-lookup"><span data-stu-id="bced3-215">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="bced3-216">Insira um nome de arquivo para o anexo .docx ou .pdf.</span><span class="sxs-lookup"><span data-stu-id="bced3-216">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="bced3-217">**URL da Página inicial personalizada**: insira uma página de aterrissagem opcional onde os usuários são levados se clicarem no link de phishing e inserirem suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="bced3-217">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="bced3-218">Este link substitui a página de aterrissagem padrão.</span><span class="sxs-lookup"><span data-stu-id="bced3-218">This link replaces the default landing page.</span></span> <span data-ttu-id="bced3-219">Por exemplo, se você tiver treinamento de reconhecimento interno, poderá especificar essa URL aqui.</span><span class="sxs-lookup"><span data-stu-id="bced3-219">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="bced3-220">**Assunto**: O **campo Assunto** da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="bced3-220">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="bced3-221">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bced3-221">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="bced3-222">Na etapa **Escrever email,** crie o corpo da mensagem da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="bced3-222">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="bced3-223">Se você selecionou um modelo na etapa **Iniciar,** o corpo da mensagem já está configurado, mas você pode personalizá-lo.</span><span class="sxs-lookup"><span data-stu-id="bced3-223">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="bced3-224">Você pode usar a guia **Email** (um editor HTML rico) ou a guia **Origem** (código HTML bruto).</span><span class="sxs-lookup"><span data-stu-id="bced3-224">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="bced3-225">A formatação HTML pode ser tão simples ou complexa quanto você precisa.</span><span class="sxs-lookup"><span data-stu-id="bced3-225">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="bced3-226">Você pode inserir imagens e texto para melhorar a capacidade de acreditar da mensagem no cliente de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="bced3-226">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="bced3-227">`${username}` insere o nome do destinatário.</span><span class="sxs-lookup"><span data-stu-id="bced3-227">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="bced3-228">`${loginserverurl}`insere o **valor de URL do Servidor de Logon de Phishing.**</span><span class="sxs-lookup"><span data-stu-id="bced3-228">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="bced3-229">Para **campanhas de Phishing** de Lança (Anexo), você deve remover o link do corpo da mensagem (caso contrário, a mensagem conterá um **link** e um anexo e os cliques de link não serão rastreados em uma campanha de anexo).</span><span class="sxs-lookup"><span data-stu-id="bced3-229">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bced3-230">![Corpo do Email de Composição](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="bced3-230">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="bced3-231">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bced3-231">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="bced3-232">Na etapa **Confirmar,** clique em **Concluir** para iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-232">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="bced3-233">A mensagem de phishing é entregue aos destinatários direcionados.</span><span class="sxs-lookup"><span data-stu-id="bced3-233">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="bced3-234">Campanhas de ataque de senha</span><span class="sxs-lookup"><span data-stu-id="bced3-234">Password attack campaigns</span></span>

<span data-ttu-id="bced3-235">Um *ataque de senha* tenta adivinhar senhas para contas de usuário em uma organização, normalmente depois que o invasor identifica uma ou mais contas de usuário válidas.</span><span class="sxs-lookup"><span data-stu-id="bced3-235">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="bced3-236">No Simulador de Ataques, dois tipos diferentes de campanhas de ataque de senha estão disponíveis para você testar a complexidade das senhas dos usuários:</span><span class="sxs-lookup"><span data-stu-id="bced3-236">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="bced3-237">**Senha de força** bruta (ataque  de  dicionário) : Um ataque de força bruta ou dicionário usa um grande arquivo de dicionário de senhas em uma conta de usuário com a esperança de que uma delas funcione (muitas senhas em uma conta).</span><span class="sxs-lookup"><span data-stu-id="bced3-237">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="bced3-238">Bloqueios de senha incorretos ajudam a impedir ataques de senha de força bruta.</span><span class="sxs-lookup"><span data-stu-id="bced3-238">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="bced3-239">Para o ataque de dicionário, você pode especificar uma ou muitas senhas a tentar (inseridas manualmente ou em um arquivo carregado) e você pode especificar um ou muitos usuários.</span><span class="sxs-lookup"><span data-stu-id="bced3-239">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="bced3-240">**Ataque de pulverização de** senha : Um ataque de *pulverização* de senha usa a mesma senha cuidadosamente considerada em uma lista de contas de usuário (uma senha em várias contas).</span><span class="sxs-lookup"><span data-stu-id="bced3-240">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="bced3-241">Os ataques de pulverização de senha são mais difíceis de detectar do que ataques de senha de força bruta (a probabilidade de sucesso aumenta quando um invasor tenta uma senha entre dezenas ou centenas de contas sem o risco de bloquear a senha incorreta do usuário).</span><span class="sxs-lookup"><span data-stu-id="bced3-241">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="bced3-242">Para o ataque de pulverização de senha, você só pode especificar uma senha a ser tentada e pode especificar um ou muitos usuários.</span><span class="sxs-lookup"><span data-stu-id="bced3-242">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="bced3-243">Os ataques de senha no Simulador de Ataque passam o nome de usuário e a senha Solicitações básicas de autenticação para um ponto de extremidade, para que eles também funcionem com outros métodos de autenticação (AD FS, sincronização de hash de senha, passagem, PingFederate, etc.).</span><span class="sxs-lookup"><span data-stu-id="bced3-243">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="bced3-244">Para usuários que têm a MFA habilitada, mesmo que o ataque de senha tente sua senha real,  a tentativa sempre se registrará como uma falha (em outras palavras, os usuários MFA nunca aparecerão na contagem de tentativas bem-sucedidas da campanha).</span><span class="sxs-lookup"><span data-stu-id="bced3-244">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="bced3-245">Esse é o resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="bced3-245">This is the expected result.</span></span> <span data-ttu-id="bced3-246">O MFA é um método principal para ajudar a proteger contra ataques de senha.</span><span class="sxs-lookup"><span data-stu-id="bced3-246">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="bced3-247">Criar e iniciar uma campanha de ataque de senha</span><span class="sxs-lookup"><span data-stu-id="bced3-247">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="bced3-248">No Centro de Conformidade & segurança, vá para Simulador de ataque **de gerenciamento** \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="bced3-248">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="bced3-249">Na página **Simular ataques,** faça uma das seguintes seleções com base no tipo de campanha que você deseja criar:</span><span class="sxs-lookup"><span data-stu-id="bced3-249">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="bced3-250">Na seção **Senha de Força Bruta (Ataque de Dicionário),** clique em Iniciar **Ataque** ou em Ataque De Início **de Detalhes** de \> **Ataque.**</span><span class="sxs-lookup"><span data-stu-id="bced3-250">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="bced3-251">na seção **Ataque de pulverização de senha,** clique em **Iniciar Ataque ou** em Ataque De Início de **Detalhes** de \> **Ataque**.</span><span class="sxs-lookup"><span data-stu-id="bced3-251">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="bced3-252">O **assistente Configurar Ataque de Senha** é iniciado em um novo sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="bced3-252">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="bced3-253">Na etapa **Iniciar,** insira um nome de exibição exclusivo para a campanha e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="bced3-253">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="bced3-254">Na etapa **Usuários de destino,** faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="bced3-254">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="bced3-255">Clique **em Livro de** Endereços para selecionar os destinatários (usuários ou grupos) da campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-255">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="bced3-256">Cada destinatário direcionado deve ter uma caixa de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bced3-256">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="bced3-257">Se você clicar **em Filtrar** **e Aplicar** sem inserir um critério de pesquisa, todos os destinatários serão retornados e adicionados à campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-257">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="bced3-258">Clique **em Importar** e **Importar** Arquivo para importar um valor separado por vírgula (CSV) ou arquivo separado por linha de endereços de email.</span><span class="sxs-lookup"><span data-stu-id="bced3-258">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="bced3-259">Cada linha deve conter o endereço de email do destinatário.</span><span class="sxs-lookup"><span data-stu-id="bced3-259">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="bced3-260">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bced3-260">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="bced3-261">Na etapa **Escolher configurações de** ataque, escolha o que fazer com base no tipo de campanha:</span><span class="sxs-lookup"><span data-stu-id="bced3-261">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="bced3-262">**Senha de Força Bruta (Ataque de Dicionário)**: Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="bced3-262">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="bced3-263">**Insira senhas manualmente**: Na caixa Pressionar **digite** para adicionar uma senha, digite uma senha e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="bced3-263">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="bced3-264">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="bced3-264">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="bced3-265">**Carregar senhas de um arquivo de** dicionário : clique em **Carregar** para importar um arquivo de texto existente que contém uma senha em cada linha e uma última linha em branco.</span><span class="sxs-lookup"><span data-stu-id="bced3-265">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="bced3-266">O arquivo de texto deve ter 10 MB ou menos de tamanho e não pode conter mais de 30.000 senhas.</span><span class="sxs-lookup"><span data-stu-id="bced3-266">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="bced3-267">**Ataque de pulverização de** senha : Em As senhas a ser **usadas na caixa de** ataque, insira uma senha.</span><span class="sxs-lookup"><span data-stu-id="bced3-267">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="bced3-268">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bced3-268">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="bced3-269">Na etapa **Confirmar,** clique em **Concluir** para iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-269">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="bced3-270">As senhas especificadas são tentadas nos usuários especificados.</span><span class="sxs-lookup"><span data-stu-id="bced3-270">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="bced3-271">Exibir resultados da campanha</span><span class="sxs-lookup"><span data-stu-id="bced3-271">View campaign results</span></span>

<span data-ttu-id="bced3-272">Depois de iniciar uma campanha, você pode verificar o progresso e os resultados na página principal **simular ataques.**</span><span class="sxs-lookup"><span data-stu-id="bced3-272">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="bced3-273">As campanhas ativas mostrarão uma barra de status, um valor percentual concluído e a contagem "(usuários concluídos) de (total de usuários)".</span><span class="sxs-lookup"><span data-stu-id="bced3-273">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="bced3-274">Clicar no botão **Atualizar** atualizará o progresso de todas as campanhas ativas.</span><span class="sxs-lookup"><span data-stu-id="bced3-274">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="bced3-275">Você também pode clicar **em Encerrar** para interromper uma campanha ativa.</span><span class="sxs-lookup"><span data-stu-id="bced3-275">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="bced3-276">Quando a campanha é concluída, o status muda para **Ataque concluído**.</span><span class="sxs-lookup"><span data-stu-id="bced3-276">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="bced3-277">Você pode exibir os resultados da campanha fazendo uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="bced3-277">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="bced3-278">Na página principal **Simular ataques,** clique em **Exibir Relatório** com o nome da campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-278">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="bced3-279">Na página principal **Simular ataques,** clique em **Detalhes de** Ataque na seção para o tipo de ataque.</span><span class="sxs-lookup"><span data-stu-id="bced3-279">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="bced3-280">Na página **Detalhes de** ataque aberta, selecione a campanha na seção **Histórico de** Ataques.</span><span class="sxs-lookup"><span data-stu-id="bced3-280">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="bced3-281">Qualquer uma das ações anteriores levará você a uma página chamada **Detalhes de ataque.**</span><span class="sxs-lookup"><span data-stu-id="bced3-281">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="bced3-282">As informações disponíveis nesta página para cada tipo de campanha são descritas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="bced3-282">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="bced3-283">Resultados da campanha Phishing de Lança (Coleta de Credenciais)</span><span class="sxs-lookup"><span data-stu-id="bced3-283">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="bced3-284">As informações a seguir estão disponíveis na página **Detalhes de** ataque para cada campanha:</span><span class="sxs-lookup"><span data-stu-id="bced3-284">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="bced3-285">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-285">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="bced3-286">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="bced3-286">**Total users targeted**</span></span>

- <span data-ttu-id="bced3-287">**Tentativas** bem-sucedidas : o número de usuários que clicaram no **link** e entraram em suas credenciais (*qualquer nome de* usuário e valor de senha).</span><span class="sxs-lookup"><span data-stu-id="bced3-287">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="bced3-288">**Taxa de Sucesso Geral**: Uma porcentagem calculada por tentativas bem-sucedidas   /  **Total de usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="bced3-288">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="bced3-289">**Clique mais** rápido: quanto tempo o primeiro usuário levou para clicar no link depois de iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-289">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="bced3-290">**Clique em** Média : a soma de quanto tempo todos demoraram para clicar no link dividido pelo número de usuários que clicaram no link.</span><span class="sxs-lookup"><span data-stu-id="bced3-290">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="bced3-291">**Clique em Taxa de** Sucesso : Uma porcentagem calculada por (número de usuários que clicaram no link) / **Total de usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="bced3-291">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="bced3-292">**Credenciais mais rápidas:** quanto tempo o primeiro usuário levou para inserir suas credenciais depois de iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-292">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="bced3-293">**Credenciais médias**: a soma de quanto tempo todos demoraram para inserir suas credenciais divididas pelo número de usuários que inseriram suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="bced3-293">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="bced3-294">**Taxa de Sucesso de** Credenciais : Uma porcentagem calculada por (número de usuários que entraram em suas credenciais) / **Total de usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="bced3-294">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="bced3-295">Um gráfico de barras que mostra **o Link clicado e** os números **fornecidos por** dia por credencial.</span><span class="sxs-lookup"><span data-stu-id="bced3-295">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="bced3-296">Um gráfico de círculo que mostra **as porcentagens Link clicou**, **Credencial fornecida** e **Nenhuma** para a campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-296">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="bced3-297">A **seção Usuários Comprometidos** lista os detalhes dos usuários que clicaram no link:</span><span class="sxs-lookup"><span data-stu-id="bced3-297">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="bced3-298">O endereço de email do usuário</span><span class="sxs-lookup"><span data-stu-id="bced3-298">The user's email address</span></span>

  - <span data-ttu-id="bced3-299">A data/hora em que eles clicaram no link.</span><span class="sxs-lookup"><span data-stu-id="bced3-299">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="bced3-300">O endereço IP do cliente.</span><span class="sxs-lookup"><span data-stu-id="bced3-300">The client IP address.</span></span>

  - <span data-ttu-id="bced3-301">Detalhes sobre a versão do usuário do Windows e do navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="bced3-301">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="bced3-302">Você pode clicar **em Exportar** para exportar os resultados para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="bced3-302">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="bced3-303">Resultados da campanha Phishing de Lança (Anexo)</span><span class="sxs-lookup"><span data-stu-id="bced3-303">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="bced3-304">As informações a seguir estão disponíveis na página **Detalhes de** ataque para cada campanha:</span><span class="sxs-lookup"><span data-stu-id="bced3-304">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="bced3-305">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-305">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="bced3-306">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="bced3-306">**Total users targeted**</span></span>

- <span data-ttu-id="bced3-307">**Tentativas** bem-sucedidas : o número de usuários que abriram ou baixaram e abriram o anexo (a visualização não conta).</span><span class="sxs-lookup"><span data-stu-id="bced3-307">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="bced3-308">**Taxa de Sucesso Geral**: Uma porcentagem calculada por tentativas bem-sucedidas   /  **Total de usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="bced3-308">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="bced3-309">**Tempo de abertura de anexo mais** rápido: quanto tempo o primeiro usuário levou para abrir o anexo depois de iniciar a campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-309">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="bced3-310">**Tempo médio de** abertura de anexo : a soma de quanto tempo todos demoraram para abrir o anexo dividido pelo número de usuários que abriram o anexo.</span><span class="sxs-lookup"><span data-stu-id="bced3-310">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="bced3-311">**Taxa de sucesso de** abertura de anexo: uma porcentagem calculada por (número de usuários que abriram o anexo) / Total de usuários **direcionados**.</span><span class="sxs-lookup"><span data-stu-id="bced3-311">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="bced3-312">Resultados da campanha Senha de Força Bruta (Ataque de Dicionário)</span><span class="sxs-lookup"><span data-stu-id="bced3-312">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="bced3-313">As informações a seguir estão disponíveis na página **Detalhes de** ataque para cada campanha:</span><span class="sxs-lookup"><span data-stu-id="bced3-313">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="bced3-314">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-314">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="bced3-315">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="bced3-315">**Total users targeted**</span></span>

- <span data-ttu-id="bced3-316">**Tentativas** bem-sucedidas : o número de usuários que foram encontrados usando uma das senhas especificadas.</span><span class="sxs-lookup"><span data-stu-id="bced3-316">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="bced3-317">**Taxa de Sucesso Geral**: Uma porcentagem calculada por tentativas bem-sucedidas   /  **Total de usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="bced3-317">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="bced3-318">A **seção Usuários Comprometidos** lista os endereços de email dos usuários afetados.</span><span class="sxs-lookup"><span data-stu-id="bced3-318">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="bced3-319">Você pode clicar **em Exportar** para exportar os resultados para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="bced3-319">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="bced3-320">Resultados da campanha de ataque de pulverização de senha</span><span class="sxs-lookup"><span data-stu-id="bced3-320">Password spray attack campaign results</span></span>

<span data-ttu-id="bced3-321">As informações a seguir estão disponíveis na página **Detalhes de** ataque para cada campanha:</span><span class="sxs-lookup"><span data-stu-id="bced3-321">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="bced3-322">A duração (data/hora de início e data/hora de término) da campanha.</span><span class="sxs-lookup"><span data-stu-id="bced3-322">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="bced3-323">**Total de usuários direcionados**</span><span class="sxs-lookup"><span data-stu-id="bced3-323">**Total users targeted**</span></span>

- <span data-ttu-id="bced3-324">**Tentativas** bem-sucedidas : o número de usuários que foram encontrados usando a senha especificada.</span><span class="sxs-lookup"><span data-stu-id="bced3-324">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="bced3-325">**Taxa de Sucesso Geral**: Uma porcentagem calculada por tentativas bem-sucedidas   /  **Total de usuários direcionados**.</span><span class="sxs-lookup"><span data-stu-id="bced3-325">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>