---
title: Simulador de Ataque no Office 365
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
description: Como administrador global do Office 365, você pode usar o simulador de ataques para executar cenários de ataque realistas em sua organização. Isso pode ajudá-lo a identificar e encontrar usuários vulneráveis antes que um ataque real atinja sua empresa.
ms.openlocfilehash: 93a2601322fd33024c1310e1df69ad1dea2f07b7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083653"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="39a85-104">Simulador de Ataque no Office 365</span><span class="sxs-lookup"><span data-stu-id="39a85-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="39a85-105">**Resumo** Se você for um administrador global do Office 365 ou um administrador de segurança e sua organização tiver o Office 365 Advanced Threat Protection Plan 2, que inclui os [recursos de investigação e resposta contra ameaças](office-365-ti.md), você poderá usar o simulador de ataques para executar cenários de ataque realísticos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="39a85-105">**Summary** If you are an Office 365 global administrator or a security administrator and your organization has Office 365 Advanced Threat Protection Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="39a85-106">Isso pode ajudá-lo a identificar e encontrar usuários vulneráveis antes que um ataque real afete o resultado final.</span><span class="sxs-lookup"><span data-stu-id="39a85-106">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="39a85-107">Leia este artigo para saber mais.</span><span class="sxs-lookup"><span data-stu-id="39a85-107">Read this article to learn more.</span></span>

## <a name="the-attacks"></a><span data-ttu-id="39a85-108">Os ataques</span><span class="sxs-lookup"><span data-stu-id="39a85-108">The Attacks</span></span>

<span data-ttu-id="39a85-109">Três tipos de simulação de ataque estão disponíveis atualmente:</span><span class="sxs-lookup"><span data-stu-id="39a85-109">Three kinds of attack simulations are currently available:</span></span>

- [<span data-ttu-id="39a85-110">Coleta de credenciais do spear-phishing Attack</span><span class="sxs-lookup"><span data-stu-id="39a85-110">Credential harvest spear-phishing attack</span></span>](#credential-harvest-spear-phishing-attack)

- [<span data-ttu-id="39a85-111">Anexo de Spear-ataque de phishing</span><span class="sxs-lookup"><span data-stu-id="39a85-111">Attachment spear-phishing attack</span></span>](#attachment-spear-phishing-attack)

- [<span data-ttu-id="39a85-112">Ataque de irrigação de senha</span><span class="sxs-lookup"><span data-stu-id="39a85-112">Password-spray attack</span></span>](#password-spray-attack)

- [<span data-ttu-id="39a85-113">Ataque de senha de força bruta</span><span class="sxs-lookup"><span data-stu-id="39a85-113">Brute-force password attack</span></span>](#brute-force-password-attack)

<span data-ttu-id="39a85-114">Para que um ataque seja iniciado com êxito, certifique-se de que a conta que você está usando para executar ataques simulados esteja usando a autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="39a85-114">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="39a85-115">Além disso, você deve ser um administrador global do Office 365 ou um administrador de segurança.</span><span class="sxs-lookup"><span data-stu-id="39a85-115">In addition, you must be an Office 365 global administrator or a security administrator.</span></span> <span data-ttu-id="39a85-116">(Para saber mais sobre funções e permissões, confira [permissões no centro de conformidade & segurança do Office 365](permissions-in-the-security-and-compliance-center.md).)</span><span class="sxs-lookup"><span data-stu-id="39a85-116">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

<span data-ttu-id="39a85-117">Para acessar o simulador de conformidade, &amp; no centro de conformidade de segurança, escolha **simulador de ataque**de **Gerenciamento** \> de ameaças.</span><span class="sxs-lookup"><span data-stu-id="39a85-117">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="39a85-118">Antes de começar...</span><span class="sxs-lookup"><span data-stu-id="39a85-118">Before you begin...</span></span>

<span data-ttu-id="39a85-119">Verifique se você e sua organização atendem aos seguintes requisitos para o simulador de ataques:</span><span class="sxs-lookup"><span data-stu-id="39a85-119">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>

- <span data-ttu-id="39a85-120">O email da sua organização está hospedado no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="39a85-120">Your organization's email is hosted in Exchange Online.</span></span> <span data-ttu-id="39a85-121">(O simulador de ataque não está disponível para os servidores de email locais.)</span><span class="sxs-lookup"><span data-stu-id="39a85-121">(Attack Simulator is not available for on-premises email servers.)</span></span>

- <span data-ttu-id="39a85-122">Você é um administrador global do Office 365 ou administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="39a85-122">You are an Office 365 global administrator or security administrator</span></span>

- <span data-ttu-id="39a85-123">Campanhas de phishing coletam e processam eventos por um período de 30 dias, dados de campanha históricos estarão disponíveis por até 90 dias após a campanha ser iniciada.</span><span class="sxs-lookup"><span data-stu-id="39a85-123">Phishing campaigns will collect and process events for a period of 30 days, historical campaign data will be available for up to 90 days after the campaign is launched.</span></span>

- <span data-ttu-id="39a85-124">A [autenticação multifator/acesso condicional](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) está ativada, por pelo menos a conta de administrador global do Office 365 e os administradores de segurança que usarão o simulador de ataques.</span><span class="sxs-lookup"><span data-stu-id="39a85-124">[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) is turned on, for at least the Office 365 global administrator account and security administrators who will be using Attack Simulator.</span></span> <span data-ttu-id="39a85-125">(Idealmente, a autenticação multifator/acesso condicional está ativada para todos os usuários da sua organização.)</span><span class="sxs-lookup"><span data-stu-id="39a85-125">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>

- <span data-ttu-id="39a85-126">Sua organização tem o [plano de proteção avançada contra ameaças do Office 365](office-365-atp.md), com o simulador &amp; de ataques visível no centro de conformidade de segurança (vá para o \> **simulador de ataques**de **Gerenciamento de ameaças** )</span><span class="sxs-lookup"><span data-stu-id="39a85-126">Your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-atp.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span>

    ![Gerenciamento de ameaças-simulador de ataques](../../media/ThreatMgmt-AttackSimulator.png)

## <a name="credential-harvest-spear-phishing-attack"></a><span data-ttu-id="39a85-128">Coleta de credenciais do spear-phishing Attack</span><span class="sxs-lookup"><span data-stu-id="39a85-128">Credential harvest spear-phishing attack</span></span>

<span data-ttu-id="39a85-129">Phishing é um termo genérico para um amplo conjunto de ataques de classe como um ataque de estilo de engenharia social.</span><span class="sxs-lookup"><span data-stu-id="39a85-129">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack.</span></span> <span data-ttu-id="39a85-130">Esse ataque está voltado para o spear phishing, um ataque mais direcionado para um grupo específico de pessoas ou uma organização.</span><span class="sxs-lookup"><span data-stu-id="39a85-130">This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization.</span></span> <span data-ttu-id="39a85-131">Normalmente, um ataque personalizado com algum reconhecimento executado e usando um nome de exibição que irá gerar confiança no destinatário, como uma mensagem de email que parece ser proveniente de um executivo dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="39a85-131">Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>

<span data-ttu-id="39a85-132">Esse ataque se concentra em permitir que você manipule quem a mensagem parece ter originado alterando o nome de exibição e o endereço de origem.</span><span class="sxs-lookup"><span data-stu-id="39a85-132">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address.</span></span> <span data-ttu-id="39a85-133">Quando os ataques de spear-phishing forem bem-sucedidos, cyberattackers obter acesso às credenciais dos usuários.</span><span class="sxs-lookup"><span data-stu-id="39a85-133">When spear-phishing attacks are successful, cyberattackers gain access to users' credentials.</span></span>

### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="39a85-134">Para simular um ataque de spear-phishing</span><span class="sxs-lookup"><span data-stu-id="39a85-134">To simulate a spear-phishing attack</span></span>

![Redigir corpo de email](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

<span data-ttu-id="39a85-136">Você pode criar o editor de HTML avançado diretamente no próprio campo de **corpo de email** ou trabalhar com o código-fonte HTML.</span><span class="sxs-lookup"><span data-stu-id="39a85-136">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>

1. <span data-ttu-id="39a85-137">No [centro de &amp; conformidade de segurança](https://protection.office.com), escolha \> **simulador de ataque**de **Gerenciamento de ameaças** .</span><span class="sxs-lookup"><span data-stu-id="39a85-137">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="39a85-138">Especifique um nome de campanha significativo para o ataque ou selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="39a85-138">Specify a meaningful campaign name for the attack or select a template.</span></span>

   ![Página de início de phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

3. <span data-ttu-id="39a85-140">Especifique os destinatários de destino.</span><span class="sxs-lookup"><span data-stu-id="39a85-140">Specify the target recipients.</span></span> <span data-ttu-id="39a85-141">Podem ser indivíduos ou grupos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="39a85-141">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="39a85-142">Cada destinatário de destino deve ter uma caixa de correio do Exchange Online para que o ataque seja bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="39a85-142">Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>

   ![Seleção de destinatário](../../media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)

4. <span data-ttu-id="39a85-144">Configure os detalhes de email de phishing.</span><span class="sxs-lookup"><span data-stu-id="39a85-144">Configure the Phishing email details.</span></span>

   ![Configurar detalhes de email](../../media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)

   <span data-ttu-id="39a85-146">A formatação HTML pode ser complexa ou básica quanto às necessidades de sua campanha.</span><span class="sxs-lookup"><span data-stu-id="39a85-146">The HTML formatting can be as complex or basic as your campaign needs.</span></span> <span data-ttu-id="39a85-147">Como o formato de email é HTML, você pode inserir imagens e texto para aprimorar o believability.</span><span class="sxs-lookup"><span data-stu-id="39a85-147">As the email format is HTML, you can insert images and text to enhance believability.</span></span> <span data-ttu-id="39a85-148">Você tem controle sobre qual será a aparência da mensagem recebida no cliente de recebimento de email.</span><span class="sxs-lookup"><span data-stu-id="39a85-148">You have control on what the received message will look like in the receiving email client.</span></span>

5. <span data-ttu-id="39a85-149">Especifique o texto para o campo **de (nome)** .</span><span class="sxs-lookup"><span data-stu-id="39a85-149">Specify text for the **From (Name)** field.</span></span> <span data-ttu-id="39a85-150">Este é o campo que mostra o **nome de exibição** no cliente de recebimento de email.</span><span class="sxs-lookup"><span data-stu-id="39a85-150">This is the field that shows in the **Display Name** in the receiving email client.</span></span>

6. <span data-ttu-id="39a85-151">Especifique o texto ou o campo **de** .</span><span class="sxs-lookup"><span data-stu-id="39a85-151">Specify text or the **From** field.</span></span> <span data-ttu-id="39a85-152">Este é o campo que aparece como o endereço de email do remetente no cliente de recebimento de email.</span><span class="sxs-lookup"><span data-stu-id="39a85-152">This is the field that shows as the email address of the sender in the receiving email client.</span></span>

   <span data-ttu-id="39a85-153">Você pode inserir um namespace de email existente dentro da sua organização (isso fará com que o endereço de email seja realmente resolvido no cliente de recebimento, facilitando um modelo de confiança muito alto) ou você pode inserir um endereço de email externo.</span><span class="sxs-lookup"><span data-stu-id="39a85-153">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address.</span></span> <span data-ttu-id="39a85-154">O endereço de email que você especificar não precisa realmente existir, mas ele precisa seguir o formato de um endereço SMTP válido, como `user@domainname.extension`.</span><span class="sxs-lookup"><span data-stu-id="39a85-154">The email address that you specify does not have to actually exist, but it does need to follow the format of a valid SMTP address, such as `user@domainname.extension`.</span></span>

7. <span data-ttu-id="39a85-155">Usando o seletor suspenso, selecione uma URL de servidor de logon de phishing que reflita o tipo de conteúdo que você terá dentro de seu ataque.</span><span class="sxs-lookup"><span data-stu-id="39a85-155">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack.</span></span> <span data-ttu-id="39a85-156">Várias URLs com temas são fornecidas para você escolher, como entrega de documentos, técnica, folha de pagamento, etc. Isso é efetivamente a URL para a qual os usuários direcionados são solicitados a clicar.</span><span class="sxs-lookup"><span data-stu-id="39a85-156">Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>

8. <span data-ttu-id="39a85-157">Especifique uma URL da página de aterrissagem personalizada.</span><span class="sxs-lookup"><span data-stu-id="39a85-157">Specify a custom landing page URL.</span></span> <span data-ttu-id="39a85-158">O uso dessa forma redirecionará os usuários para uma URL que você especificar no final de um ataque bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="39a85-158">Using this will redirect users to a URL you specify at the end of a successful attack.</span></span> <span data-ttu-id="39a85-159">Se você tiver treinamento de conscientização interna, por exemplo, você pode especificar isso aqui.</span><span class="sxs-lookup"><span data-stu-id="39a85-159">If you have internal awareness training, for example, you can specify that here.</span></span>

9. <span data-ttu-id="39a85-160">Especifique o texto do campo **assunto** .</span><span class="sxs-lookup"><span data-stu-id="39a85-160">Specify text for the **Subject** field.</span></span> <span data-ttu-id="39a85-161">Este é o campo que aparece como o **nome da entidade** no cliente de recebimento de email.</span><span class="sxs-lookup"><span data-stu-id="39a85-161">This is the field that shows as the **Subject Name** in the receiving email client.</span></span>

10. <span data-ttu-id="39a85-162">Redija o **corpo do email** que o destino receberá.</span><span class="sxs-lookup"><span data-stu-id="39a85-162">Compose the **Email body** that the target will receive.</span></span>

    <span data-ttu-id="39a85-163">`${username}`Insere o nome do destino no corpo do email.</span><span class="sxs-lookup"><span data-stu-id="39a85-163">`${username}` inserts the targets name into the Email body.</span></span>

    <span data-ttu-id="39a85-164">`${loginserverurl}`Insere a URL que os usuários de destino devem clicar</span><span class="sxs-lookup"><span data-stu-id="39a85-164">`${loginserverurl}` inserts the URL we want target users to click</span></span>

11. <span data-ttu-id="39a85-165">Escolha **Avançar e** **concluir** para iniciar o ataque.</span><span class="sxs-lookup"><span data-stu-id="39a85-165">Choose **Next,** then **Finish** to launch the attack.</span></span> <span data-ttu-id="39a85-166">A mensagem de email de spear phishing é entregue às caixas de correio dos destinatários de destino.</span><span class="sxs-lookup"><span data-stu-id="39a85-166">The spear phishing email message is delivered to your target recipients' mailboxes.</span></span>

## <a name="attachment-spear-phishing-attack"></a><span data-ttu-id="39a85-167">Anexo de Spear-ataque de phishing</span><span class="sxs-lookup"><span data-stu-id="39a85-167">Attachment spear-phishing attack</span></span>

<span data-ttu-id="39a85-168">Phishing é um termo genérico para um amplo conjunto de ataques de classe como um ataque de estilo de engenharia social.</span><span class="sxs-lookup"><span data-stu-id="39a85-168">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack.</span></span> <span data-ttu-id="39a85-169">Esse ataque está voltado ao anexo de spear phishing, um ataque mais direcionado para um grupo específico de pessoas ou uma organização.</span><span class="sxs-lookup"><span data-stu-id="39a85-169">This attack is focused on attachment spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization.</span></span> <span data-ttu-id="39a85-170">Normalmente, um ataque personalizado com algum reconhecimento executado e usando um nome de exibição que irá gerar confiança no destinatário, como uma mensagem de email que parece ser proveniente de um executivo dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="39a85-170">Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>

<span data-ttu-id="39a85-171">Esse ataque se concentra em permitir que você manipule quem a mensagem parece ter originado alterando o nome de exibição e o endereço de origem, mas desta vez, em vez de oferecer uma URL para tentar e atrair o usuário final para clicar, oferecemos um anexo que estamos tentando obter usuário final para abrir o.</span><span class="sxs-lookup"><span data-stu-id="39a85-171">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address, but this time as opposed to offering a URL to try and lure the end user to click, we offer an attachment that we are trying to get the end user to open.</span></span> 

### <a name="to-simulate-a-attachment-spear-phishing-attack"></a><span data-ttu-id="39a85-172">Para simular um ataque de spear-phishing de anexo</span><span class="sxs-lookup"><span data-stu-id="39a85-172">To simulate a Attachment spear-phishing attack</span></span>

1. <span data-ttu-id="39a85-173">Siga as etapas acima, tendo esse horário em que você clicou em **ataque de anexo** na página de aterrissagem.</span><span class="sxs-lookup"><span data-stu-id="39a85-173">Follow the steps from above, having this time clicked on **Attachment Attack** on the landing page.</span></span>

2. <span data-ttu-id="39a85-174">À medida que você avança no assistente, você vê duas opções para configurar.</span><span class="sxs-lookup"><span data-stu-id="39a85-174">As you progress through the wizard, you see two options to configure.</span></span> <span data-ttu-id="39a85-175">O **tipo de anexo**, damos suporte a dois tipos de anexo, **. docx** ou **. pdf**.</span><span class="sxs-lookup"><span data-stu-id="39a85-175">The **Attachment Type**, we support two attachment types, **.docx** or **.pdf**.</span></span> <span data-ttu-id="39a85-176">O **nome do anexo**, use este campo para criar um nome de anexo significativo para a campanha.</span><span class="sxs-lookup"><span data-stu-id="39a85-176">The **Attachment Name**, use this field to create a meaningful attachment name for the campaign.</span></span>

## <a name="password-spray-attack"></a><span data-ttu-id="39a85-177">Ataque de irrigação de senha</span><span class="sxs-lookup"><span data-stu-id="39a85-177">Password-spray attack</span></span>

<span data-ttu-id="39a85-178">Um ataque de irrigação de senha em uma organização é geralmente usado após um ator incorreto ter adquirido com êxito uma lista de usuários válidos do locatário.</span><span class="sxs-lookup"><span data-stu-id="39a85-178">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant.</span></span> <span data-ttu-id="39a85-179">O ator ruim sabe sobre senhas comuns que as pessoas utilizam.</span><span class="sxs-lookup"><span data-stu-id="39a85-179">The bad actor knows about common passwords that people use.</span></span> <span data-ttu-id="39a85-180">Esse é um ataque amplamente usado, pois é um ataque barato que é executado e é mais difícil de detectar abordagens de força bruta.</span><span class="sxs-lookup"><span data-stu-id="39a85-180">This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>

<span data-ttu-id="39a85-181">Esse ataque se concentra em permitir que você especifique uma senha comum para uma grande base de destino de usuários.</span><span class="sxs-lookup"><span data-stu-id="39a85-181">This attack focuses on letting you specify a common password against a large target base of users.</span></span>

<span data-ttu-id="39a85-182">**Observação importante** a execução do ataque de irrigação de senha contra contas de usuário finais que já têm autenticação multifator resultará em uma tentativa malsucedida para essas contas no relatório.</span><span class="sxs-lookup"><span data-stu-id="39a85-182">**Important Note** running the password spray attack against end user accounts that already have multi-factor authentication, will result in a unsuccessful attempt for those accounts in the reporting.</span></span> <span data-ttu-id="39a85-183">Isso se deve ao fato de a autenticação multifator ser uma das principais mechanims para ajudar a proteger contra ataques de irrigação de senha, portanto, é esperado.</span><span class="sxs-lookup"><span data-stu-id="39a85-183">This is due to multi-factor authentication being one of the primary mechanims to help protect against password spray attacks, so is expected.</span></span>

### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="39a85-184">Para simular um ataque de irrigação de senha</span><span class="sxs-lookup"><span data-stu-id="39a85-184">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="39a85-185">No [centro de &amp; conformidade de segurança](https://protection.office.com), escolha \> **simulador de ataque**de **Gerenciamento de ameaças** .</span><span class="sxs-lookup"><span data-stu-id="39a85-185">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="39a85-186">Especifique um nome de campanha significativo para o ataque.</span><span class="sxs-lookup"><span data-stu-id="39a85-186">Specify a meaningful campaign name for the attack.</span></span>

3. <span data-ttu-id="39a85-187">Especifique os destinatários de destino.</span><span class="sxs-lookup"><span data-stu-id="39a85-187">Specify the target recipients.</span></span> <span data-ttu-id="39a85-188">Podem ser indivíduos ou grupos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="39a85-188">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="39a85-189">Um destinatário direcionado deve ter uma caixa de correio do Exchange Online para que o ataque seja bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="39a85-189">A targeted recipient must have an Exchange Online mailbox in order for the attack to be successful.</span></span>

4. <span data-ttu-id="39a85-190">Especifique uma senha a ser usada para o ataque.</span><span class="sxs-lookup"><span data-stu-id="39a85-190">Specify a password to use for the attack.</span></span> <span data-ttu-id="39a85-191">Por exemplo, uma senha comum e relevante que você pode tentar `Summer2019`é.</span><span class="sxs-lookup"><span data-stu-id="39a85-191">For example, one common, relevant password you could try is `Summer2019`.</span></span> <span data-ttu-id="39a85-192">Outro pode ser `Fall2019`ou `Password1`.</span><span class="sxs-lookup"><span data-stu-id="39a85-192">Another might be `Fall2019`, or `Password1`.</span></span>

5. <span data-ttu-id="39a85-193">Escolha **concluir** para iniciar o ataque.</span><span class="sxs-lookup"><span data-stu-id="39a85-193">Choose **Finish** to launch the attack.</span></span>

## <a name="brute-force-password-attack"></a><span data-ttu-id="39a85-194">Ataque de senha de força bruta</span><span class="sxs-lookup"><span data-stu-id="39a85-194">Brute-force password attack</span></span>

<span data-ttu-id="39a85-195">Um ataque de senha de força bruta em relação a uma organização é geralmente usado após um ator incorreto ter adquirido com êxito uma lista de usuários principais do locatário.</span><span class="sxs-lookup"><span data-stu-id="39a85-195">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant.</span></span> <span data-ttu-id="39a85-196">Esse ataque se concentra em tentar um conjunto de senhas em uma única conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="39a85-196">This attack focuses on trying a set of passwords on a single user's account.</span></span>

<span data-ttu-id="39a85-197">**Observação importante** a execução de ataques de senha de força bruta contra contas de usuário finais que já têm autenticação multifator resultará em uma tentativa malsucedida para essas contas no relatório.</span><span class="sxs-lookup"><span data-stu-id="39a85-197">**Important Note** running the brute-force password attacks against end user accounts that already have multi-factor authentication, will result in a unsuccessful attempt for those accounts in the reporting.</span></span> <span data-ttu-id="39a85-198">Isso se deve ao fato de a autenticação multifator ser uma das principais mechanims para ajudar a proteger contra ataques de senha de força bruta, portanto, é esperado.</span><span class="sxs-lookup"><span data-stu-id="39a85-198">This is due to multi-factor authentication being one of the primary mechanims to help protect against brute-force password attacks, so is expected.</span></span>

### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="39a85-199">Para simular um ataque de senha de força bruta</span><span class="sxs-lookup"><span data-stu-id="39a85-199">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="39a85-200">No [centro de &amp; conformidade de segurança](https://protection.office.com), escolha \> **simulador de ataque**de **Gerenciamento de ameaças** .</span><span class="sxs-lookup"><span data-stu-id="39a85-200">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="39a85-201">Especifique um nome de campanha significativo para o ataque.</span><span class="sxs-lookup"><span data-stu-id="39a85-201">Specify a meaningful campaign name for the attack.</span></span>

3. <span data-ttu-id="39a85-202">Especifique o destinatário de destino.</span><span class="sxs-lookup"><span data-stu-id="39a85-202">Specify the target recipient.</span></span> <span data-ttu-id="39a85-203">Um destinatário direcionado deve ter uma caixa de correio do Exchange Online para que o ataque seja bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="39a85-203">A targeted recipient must have an Exchange Online mailbox in order for the attack to be successful.</span></span>

4. <span data-ttu-id="39a85-204">Especifique um conjunto de senhas a ser usado para o ataque.</span><span class="sxs-lookup"><span data-stu-id="39a85-204">Specify a set of passwords to use for the attack.</span></span> <span data-ttu-id="39a85-205">Para fazer isso, você pode usar um arquivo de texto (. txt) para sua lista de senhas.</span><span class="sxs-lookup"><span data-stu-id="39a85-205">To do this, you can use a text (.txt) file for your list of passwords.</span></span> <span data-ttu-id="39a85-206">O arquivo de texto não pode exceder 10 MB em tamanho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="39a85-206">The text file cannot exceed 10 MB in file size.</span></span> <span data-ttu-id="39a85-207">Use uma senha por linha e certifique-se de incluir um retorno de disco rígido após a última senha em sua lista.</span><span class="sxs-lookup"><span data-stu-id="39a85-207">Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>

5. <span data-ttu-id="39a85-208">Escolha **concluir** para iniciar o ataque.</span><span class="sxs-lookup"><span data-stu-id="39a85-208">Choose **Finish** to launch the attack.</span></span>



<span data-ttu-id="39a85-209">Visite o [mapa do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para ver o que está em desenvolvimento, o que está saindo e o que já foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="39a85-209">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>

## <a name="see-also"></a><span data-ttu-id="39a85-210">Confira também</span><span class="sxs-lookup"><span data-stu-id="39a85-210">See also</span></span>

[<span data-ttu-id="39a85-211">Descrição do Serviço da Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="39a85-211">Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[<span data-ttu-id="39a85-212">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="39a85-212">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
