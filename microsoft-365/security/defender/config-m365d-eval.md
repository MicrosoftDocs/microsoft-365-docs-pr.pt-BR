---
title: Configurar Microsoft 365 Defender pilares para o laboratório de avaliação ou o ambiente piloto
description: Configure Microsoft 365 Defender pilares, como o Microsoft Defender para Office 365, o Microsoft Defender para Identidade, Microsoft Cloud App Security e o Microsoft Defender para Ponto de Extremidade, para seu laboratório de avaliação ou ambiente piloto.
keywords: configurar Microsoft 365 Defender avaliação, Microsoft 365 Defender configuração de avaliação, configurar Microsoft 365 Defender projeto piloto, configurar Microsoft 365 Defender pilares, Microsoft 365 Defender pilares
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e50210f02d14be33c357517515d456318aac4bb6
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229774"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="1c262-104">Configurar Microsoft 365 Defender pilares para seu laboratório de avaliação ou ambiente piloto</span><span class="sxs-lookup"><span data-stu-id="1c262-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1c262-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1c262-105">**Applies to:**</span></span>
- <span data-ttu-id="1c262-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c262-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="1c262-107">Criar um Microsoft 365 Defender ou ambiente piloto de avaliação e implantá-lo é um processo de três fases:</span><span class="sxs-lookup"><span data-stu-id="1c262-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="1c262-108">[![Fase 1: Preparar](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="1c262-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="1c262-109">Fase 1: Preparar</span><span class="sxs-lookup"><span data-stu-id="1c262-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |<span data-ttu-id="1c262-110">[![Fase 2: Configurar](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span><span class="sxs-lookup"><span data-stu-id="1c262-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span></span><br/>[<span data-ttu-id="1c262-111">Fase 2: Configurar</span><span class="sxs-lookup"><span data-stu-id="1c262-111">Phase 2: Set up</span></span>](setup-m365deval.md) |![Fase 3: Integrar](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="1c262-113">Fase 3: Integrar</span><span class="sxs-lookup"><span data-stu-id="1c262-113">Phase 3: Onboard</span></span> | <span data-ttu-id="1c262-114">[![Voltar ao piloto](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="1c262-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="1c262-115">Voltar ao playbook piloto</span><span class="sxs-lookup"><span data-stu-id="1c262-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="1c262-116">*Você está aqui!*</span><span class="sxs-lookup"><span data-stu-id="1c262-116">*You are here!*</span></span> | |

<span data-ttu-id="1c262-117">No momento, você está na fase de configuração.</span><span class="sxs-lookup"><span data-stu-id="1c262-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="1c262-118">A preparação é fundamental para qualquer implantação bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="1c262-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="1c262-119">Neste artigo, você será orientado sobre os pontos que você precisará considerar ao se preparar para implantar o Microsoft Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="1c262-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>

## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="1c262-120">Microsoft 365 Defender pilares</span><span class="sxs-lookup"><span data-stu-id="1c262-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="1c262-121">Microsoft 365 Defender consiste em quatro pilares.</span><span class="sxs-lookup"><span data-stu-id="1c262-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="1c262-122">Embora um pilar já possa fornecer valor para a segurança da sua organização de rede, a habilitação dos quatro Microsoft 365 Defender pilares dará mais valor à sua organização.</span><span class="sxs-lookup"><span data-stu-id="1c262-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Solução do Image of_Microsoft 365 Defender para usuários, Microsoft Defender para Identidade, para pontos de extremidade Microsoft Defender para Ponto de Extremidade, para aplicativos de nuvem, Microsoft Cloud App Security e para dados, Microsoft Defender para Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="1c262-124">Esta seção o orientará a configurar:</span><span class="sxs-lookup"><span data-stu-id="1c262-124">This section will guide you to configure:</span></span>

- <span data-ttu-id="1c262-125">Obter o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1c262-125">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="1c262-126">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="1c262-126">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="1c262-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1c262-127">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="1c262-128">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="1c262-128">Microsoft Defender for Endpoint</span></span>

## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="1c262-129">Configurar o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1c262-129">Configure Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="1c262-130">Ignore esta etapa se você já habilitar o Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c262-130">Skip this step if you've already enabled Defender for Office 365.</span></span>

<span data-ttu-id="1c262-131">Há um Módulo do PowerShell chamado *Office 365 OrCA (Advanced Threat Protection Recommended Configuration Analyzer)* que ajuda a determinar algumas dessas configurações.</span><span class="sxs-lookup"><span data-stu-id="1c262-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="1c262-132">Quando executado como administrador em seu locatário, get-ORCAReport ajudará a gerar uma avaliação das configurações anti-spam, anti-phish e outras configurações de higienização de mensagens.</span><span class="sxs-lookup"><span data-stu-id="1c262-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="1c262-133">Você pode baixar esse módulo de https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="1c262-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span>

1. <span data-ttu-id="1c262-134">Navegue [até Office 365 Política de gerenciamento de ameaças](https://protection.office.com/homepage)& Centro de  >    >  **Conformidade.**</span><span class="sxs-lookup"><span data-stu-id="1c262-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Página of_Office de política de gerenciamento de ameaças do Centro de Conformidade & Segurança 365](../../media/mtp-eval-32.png)

2. <span data-ttu-id="1c262-136">Clique **em Anti-phishing,** selecione **Criar** e preencher o nome e a descrição da política.</span><span class="sxs-lookup"><span data-stu-id="1c262-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="1c262-137">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="1c262-137">Click **Next**.</span></span>

   ![Imagem of_Office página de política anti-phishing do Centro de Conformidade e Segurança & do 365 365 onde você pode nomear sua política](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="1c262-139">Edite sua política anti-phishing avançada no Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c262-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="1c262-140">Alterar **o Limite Avançado de Phishing** para **2 - Agressivo**.</span><span class="sxs-lookup"><span data-stu-id="1c262-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="1c262-141">Clique no **menu suspenso Adicionar uma** condição e selecione seu domínio(s) como domínio de destinatário.</span><span class="sxs-lookup"><span data-stu-id="1c262-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="1c262-142">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="1c262-142">Click **Next**.</span></span>

   ![Página of_Office política anti-phishing do Centro de Conformidade e Segurança do 365 36 & 5 onde você pode adicionar uma condição para seu aplicativo](../../media/mtp-eval-34.png)

4. <span data-ttu-id="1c262-144">Revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="1c262-144">Review your settings.</span></span> <span data-ttu-id="1c262-145">Clique **em Criar essa política** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="1c262-145">Click **Create this policy** to confirm.</span></span>

   ![Image of_Office 365 Security & Página de política anti-phishing do Centro de Conformidade onde você pode revisar suas configurações e clicar no botão criar essa política](../../media/mtp-eval-35.png)

5. <span data-ttu-id="1c262-147">Selecione **Cofre Anexos** e selecione a opção Ativar ATP para **SharePoint, OneDrive e Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="1c262-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Página of_Office Centro de Conformidade e Segurança do 365 36 & 5 onde você pode ativar a ATP para SharePoint, OneDrive e Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="1c262-149">Clique no ícone + para criar uma nova política de anexo seguro, aplique-a como domínio de destinatário aos seus domínios.</span><span class="sxs-lookup"><span data-stu-id="1c262-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="1c262-150">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1c262-150">Click **Save**.</span></span>

   ![Página of_Office Centro de Conformidade e Segurança & do 365 365 onde você pode criar uma nova política de anexo seguro](../../media/mtp-eval-37.png)

7. <span data-ttu-id="1c262-152">Em seguida, selecione a **política Cofre Links** e clique no ícone de lápis para editar a política padrão.</span><span class="sxs-lookup"><span data-stu-id="1c262-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="1c262-153">Certifique-se de que **a opção Não rastrear quando os** usuários clicarem em links seguros não estiver selecionada, enquanto o restante das opções estiver selecionado.</span><span class="sxs-lookup"><span data-stu-id="1c262-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="1c262-154">Consulte [Cofre Configurações de Links](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="1c262-154">See [Safe Links settings](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) for details.</span></span> <span data-ttu-id="1c262-155">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1c262-155">Click **Save**.</span></span>

   ![Imagem of_Office página do Centro de Conformidade e Segurança & do 365 365 que mostra que a opção Não rastrear quando os usuários clicam em segurança não está selecionada](../../media/mtp-eval-38.png)

9. <span data-ttu-id="1c262-157">Em seguida, selecione **a política Anti-malware,** selecione o padrão e escolha o ícone de lápis.</span><span class="sxs-lookup"><span data-stu-id="1c262-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="1c262-158">Clique **Configurações** e selecione **Sim e use o** texto de notificação padrão para habilitar a Resposta de Detecção **de Malware.**</span><span class="sxs-lookup"><span data-stu-id="1c262-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="1c262-159">Ativar o **Filtro de Tipos de Anexo** Comum.</span><span class="sxs-lookup"><span data-stu-id="1c262-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="1c262-160">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1c262-160">Click **Save**.</span></span>

    ![Página of_Office Centro de Conformidade e Segurança do 365 36 & 5 que mostra que a resposta de detecção de malware está ativeda com a notificação padrão e o filtro de tipos de anexo comum está ligado](../../media/mtp-eval-39.png)

11. <span data-ttu-id="1c262-162">Navegue [até Office 365 pesquisa de log](https://protection.office.com/homepage)de Auditoria de Pesquisa do Centro de Conformidade & Segurança e a ativar a  >    >   Auditoria.</span><span class="sxs-lookup"><span data-stu-id="1c262-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Página of_Office Centro de Conformidade e Segurança & do 365 365 onde você pode ativar a pesquisa de log de auditoria](../../media/mtp-eval-40.png)

12. <span data-ttu-id="1c262-164">Integre o Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="1c262-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="1c262-165">Navegue [até Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat management Explorer e selecione Microsoft Defender for  >    >   **Endpoint Configurações** no canto superior direito da tela.</span><span class="sxs-lookup"><span data-stu-id="1c262-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="1c262-166">Na caixa de diálogo Conexão do Defender para Ponto de Extremidade, a Conexão **para o Microsoft Defender para Ponto de Extremidade**.</span><span class="sxs-lookup"><span data-stu-id="1c262-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Página of_Office Centro de Conformidade e Segurança & do 365 365 onde você pode ativar a conexão do Microsoft Defender para Ponto de Extremidade](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="1c262-168">Configurar o Microsoft Defender para Identidade</span><span class="sxs-lookup"><span data-stu-id="1c262-168">Configure Microsoft Defender for Identity</span></span>

> [!NOTE]
> <span data-ttu-id="1c262-169">Ignore esta etapa se você já habilitar o Microsoft Defender para Identidade</span><span class="sxs-lookup"><span data-stu-id="1c262-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="1c262-170">Navegue [até Microsoft 365 Centro](https://security.microsoft.com/info) de Segurança > selecione Mais **Recursos** do Microsoft Defender  >  **para Identidade**.</span><span class="sxs-lookup"><span data-stu-id="1c262-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Página of_Microsoft Centro de Segurança do 365 em que há uma opção para abrir o Microsoft Defender para Identidade](../../media/mtp-eval-42.png)

2. <span data-ttu-id="1c262-172">Clique **em Criar** para iniciar o assistente do Microsoft Defender para Identidade.</span><span class="sxs-lookup"><span data-stu-id="1c262-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span>

   ![Página do assistente of_Microsoft Defender para Identidade onde você deve clicar em Criar botão Criar](../../media/mtp-eval-43.png)

3. <span data-ttu-id="1c262-174">Escolha **Fornecer um nome de usuário e uma senha para se conectar à sua floresta do Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="1c262-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>

   ![Página de of_Microsoft de boas-vindas do Defender para Identidade](../../media/mtp-eval-44.png)

4. <span data-ttu-id="1c262-176">Insira suas credenciais locais do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1c262-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="1c262-177">Pode ser qualquer conta de usuário que tenha acesso de leitura ao Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1c262-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Página de of_Microsoft do Defender para Diretório de Identidade onde você deve colocar suas credenciais](../../media/mtp-eval-45.png)

5. <span data-ttu-id="1c262-179">Em seguida, **escolha Baixar a Instalação do Sensor** e transferir o arquivo para o controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="1c262-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Imagem of_Microsoft página Defender para Identidade onde você pode selecionar Baixar Instalação do Sensor](../../media/mtp-eval-46.png)

6. <span data-ttu-id="1c262-181">Execute a Instalação do Microsoft Defender para Sensor de Identidade e comece a seguir o assistente.</span><span class="sxs-lookup"><span data-stu-id="1c262-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Imagem of_Microsoft página Defender para Identidade onde você deve clicar ao lado para seguir o assistente do sensor do Microsoft Defender for Identity](../../media/mtp-eval-47.png)

7. <span data-ttu-id="1c262-183">Clique **em Próximo** no tipo de implantação do sensor.</span><span class="sxs-lookup"><span data-stu-id="1c262-183">Click **Next** at the sensor deployment type.</span></span>

   ![Imagem of_Microsoft página Defender para Identidade onde você deve clicar ao lado para ir para a próxima página](../../media/mtp-eval-48.png)

8. <span data-ttu-id="1c262-185">Copie a chave de acesso porque você precisa insiá-la em seguida no Assistente.</span><span class="sxs-lookup"><span data-stu-id="1c262-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Página of_the sensores de imagem onde você deve copiar a chave de acesso que você precisa inserir na próxima página assistente de instalação do sensor de identidade do Microsoft Defender for Identity](../../media/mtp-eval-49.png)

9. <span data-ttu-id="1c262-187">Copie a chave de acesso para o Assistente e clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="1c262-187">Copy the access key into the Wizard and click **Install**.</span></span>

   ![Página of_Microsoft assistente do sensor defender para identidade onde você deve fornecer a chave de acesso e clicar no botão instalar](../../media/mtp-eval-50.png)

10. <span data-ttu-id="1c262-189">Parabéns, você configurou com êxito o Microsoft Defender para Identidade no controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="1c262-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Conclusão of_Microsoft instalação do assistente do sensor defender for Identity onde você deve clicar no botão concluir](../../media/mtp-eval-51.png)

11. <span data-ttu-id="1c262-191">Na seção [Configurações](https://go.microsoft.com/fwlink/?linkid=2040449) do Microsoft Defender para Identidade, selecione \*\*Microsoft Defender para Ponto de Extremidade \*\*e, em seguida, acione a alternância.</span><span class="sxs-lookup"><span data-stu-id="1c262-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="1c262-192">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1c262-192">Click **Save**.</span></span>

    ![Página of_the configurações de identidade do Microsoft Defender para a qual você deve ativar a alternância do Microsoft Defender para o Ponto de Extremidade](../../media/mtp-eval-52.png)

## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="1c262-194">Configurar Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1c262-194">Configure Microsoft Cloud App Security</span></span>

> [!NOTE]
> <span data-ttu-id="1c262-195">Ignore esta etapa se você já tiver habilitado Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="1c262-195">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span>

1. <span data-ttu-id="1c262-196">Navegue [até Microsoft 365 Central](https://security.microsoft.com/info)de Segurança Mais Recursos  >    >  **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="1c262-196">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Página of_Microsoft Centro de Segurança do 365 onde você pode ver o cartão do Microsoft Cloud App e deve clicar no botão abrir](../../media/mtp-eval-53.png)

2. <span data-ttu-id="1c262-198">No prompt de informações para integrar o Microsoft Defender para Identidade, selecione **Habilitar a integração de dados do Microsoft Defender para Identidade.**</span><span class="sxs-lookup"><span data-stu-id="1c262-198">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>

   ![Prompt of_the informações de imagem para integrar o Microsoft Defender for Identity onde você deve selecionar o link Habilitar o Microsoft Defender para Identidade de integração de dados](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="1c262-200">Se você não vir esse prompt, pode significar que a integração de dados do Microsoft Defender for Identity já foi habilitada.</span><span class="sxs-lookup"><span data-stu-id="1c262-200">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="1c262-201">No entanto, se você não tiver certeza, entre em contato com o administrador de TI para confirmar.</span><span class="sxs-lookup"><span data-stu-id="1c262-201">However, if you are not sure, contact your IT Administrator to confirm.</span></span>

3. <span data-ttu-id="1c262-202">Vá para **Configurações**, adque a alternância de integração do **Microsoft Defender for Identity** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1c262-202">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span>

   ![Página of_the configurações de imagem em que você deve ativar a alternância de integração do Microsoft Defender for Identity e clique em salvar](../../media/mtp-eval-55.png)

   > [!NOTE]
   > <span data-ttu-id="1c262-204">Para novas instâncias do Microsoft Defender para Identidade, essa alternância de integração é automaticamente ativado.</span><span class="sxs-lookup"><span data-stu-id="1c262-204">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="1c262-205">Confirme se a integração com o Microsoft Defender for Identity foi habilitada antes de prosseguir para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="1c262-205">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>

4. <span data-ttu-id="1c262-206">Nas configurações de descoberta na nuvem, selecione **Integração do Microsoft Defender para Ponto de Extremidade** e habilita a integração.</span><span class="sxs-lookup"><span data-stu-id="1c262-206">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="1c262-207">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1c262-207">Click **Save**.</span></span>

   ![Imagem of_the página do Microsoft Defender para Ponto de Extremidade onde a caixa de seleção bloquear aplicativos não selecionados em Integração do Microsoft Defender para Ponto de Extremidade está selecionada.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="1c262-210">Em Configurações de descoberta na nuvem, selecione **Enriquecimento de usuário** e, em seguida, habilita a integração com Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1c262-210">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Seção Imagem de enriquecimento do usuário em que os identificadores de usuário descobertos com Azure Active Directory nomes de usuário estão selecionados](../../media/mtp-eval-57.png)

## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="1c262-212">Configurar o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="1c262-212">Configure Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="1c262-213">Ignore esta etapa se você já habilitar o Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="1c262-213">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="1c262-214">Navegue [até Microsoft 365 Central de Segurança](https://security.microsoft.com/info)Mais Recursos  >    >  **Central de Segurança do Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="1c262-214">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="1c262-215">Clique em **Abrir**. </span><span class="sxs-lookup"><span data-stu-id="1c262-215">Click **Open**.</span></span>

   ![Opção of_Microsoft Centro de Segurança do Defender na página Microsoft 365 Central de Segurança](../../media/mtp-eval-58.png)

2. <span data-ttu-id="1c262-217">Siga o assistente do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="1c262-217">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="1c262-218">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="1c262-218">Click **Next**.</span></span>

   ![Página do assistente de of_the Central de Segurança do Microsoft Defender de boas-vindas](../../media/mtp-eval-59.png)

3. <span data-ttu-id="1c262-220">Escolha com base em seu local de armazenamento de dados preferencial, política de retenção de dados, tamanho da organização e aceitação para recursos de visualização.</span><span class="sxs-lookup"><span data-stu-id="1c262-220">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Página of_the imagem para selecionar o país de armazenamento de dados, a política de retenção e o tamanho da organização.](../../media/mtp-eval-60.png)

   > [!NOTE]
   > <span data-ttu-id="1c262-223">Você não pode alterar algumas das configurações, como o local de armazenamento de dados, posteriormente.</span><span class="sxs-lookup"><span data-stu-id="1c262-223">You cannot change some of the settings, like data storage location, afterwards.</span></span>

   <span data-ttu-id="1c262-224">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="1c262-224">Click **Next**.</span></span>

4. <span data-ttu-id="1c262-225">Clique **em Continuar** e ele provisiona seu locatário do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="1c262-225">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Imagem of_the página solicitando que você clique no botão continuar para criar sua instância de nuvem](../../media/mtp-eval-61.png)

5. <span data-ttu-id="1c262-227">A integração de seus pontos de extremidade por meio de Políticas de Grupo, Microsoft Endpoint Manager ou executando um script local para o Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="1c262-227">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="1c262-228">Para simplificar, este guia usa o script local.</span><span class="sxs-lookup"><span data-stu-id="1c262-228">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="1c262-229">Clique **em Baixar pacote** e copie o script de integração para seus pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="1c262-229">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Imagem of_page solicitando que você clique no botão Baixar pacote para copiar o script de integração para seu ponto de extremidade ou pontos de extremidade](../../media/mtp-eval-62.png)

7. <span data-ttu-id="1c262-231">No ponto de extremidade, execute o script de integração como Administrador e escolha Y.</span><span class="sxs-lookup"><span data-stu-id="1c262-231">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>

   ![Linha of_the de comando de imagem onde você executar o script de integração e escolher Y para prosseguir](../../media/mtp-eval-63.png)

8. <span data-ttu-id="1c262-233">Parabéns, você integra seu primeiro ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="1c262-233">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Image of_the commandline em que você tem a confirmação de que você integra seu primeiro ponto de extremidade.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="1c262-236">Copie o teste de detecção do assistente do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="1c262-236">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Imagem of_the executar uma etapa de teste de detecção em que você deve clicar em Copiar para copiar o script de teste de detecção que você deve colar no prompt de comando](../../media/mtp-eval-65.png)

10. <span data-ttu-id="1c262-238">Copie o script do PowerShell para um prompt de comando elevado e execute-o.</span><span class="sxs-lookup"><span data-stu-id="1c262-238">Copy the PowerShell script to an elevated command prompt and run it.</span></span>

    ![Prompt of_command imagem em que você deve copiar o script do PowerShell para um prompt de comando elevado e execute-o](../../media/mtp-eval-66.png)

11. <span data-ttu-id="1c262-240">Selecione **Iniciar usando o Microsoft Defender para Ponto de** Extremidade no Assistente.</span><span class="sxs-lookup"><span data-stu-id="1c262-240">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Prompt de of_the de confirmação do assistente em que você deve clicar em Iniciar usando o Microsoft Defender para Ponto de Extremidade](../../media/mtp-eval-67.png)

12. <span data-ttu-id="1c262-242">Visite o [Central de Segurança do Microsoft Defender](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="1c262-242">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="1c262-243">Vá para **Configurações** e selecione **Recursos avançados**.</span><span class="sxs-lookup"><span data-stu-id="1c262-243">Go to **Settings** and then select **Advanced features**.</span></span>

    ![Menu of_Microsoft Centro de Segurança do Defender Configurações em que você deve selecionar recursos avançados](../../media/mtp-eval-68.png)

13. <span data-ttu-id="1c262-245">Ativar a integração com **o Microsoft Defender para Identidade.**</span><span class="sxs-lookup"><span data-stu-id="1c262-245">Turn on the integration with **Microsoft Defender for Identity**.</span></span>

    ![Recursos avançados do Centro de Segurança do Defender of_Microsoft imagem, alternância de opção do Microsoft Defender for Identity que você precisa ativar](../../media/mtp-eval-69.png)

14. <span data-ttu-id="1c262-247">Ativar a integração com **o Office 365 Threat Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="1c262-247">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Recursos avançados do Centro de Segurança do Defender of_Microsoft imagem, Office 365 opção de Inteligência contra Ameaças que você precisa ativar](../../media/mtp-eval-70.png)

15. <span data-ttu-id="1c262-249">Ativar a integração com **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="1c262-249">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Recursos avançados do Centro de Segurança do Defender of_Microsoft imagem, Microsoft Cloud App Security opção de alternância que você precisa ativar](../../media/mtp-eval-71.png)

16. <span data-ttu-id="1c262-251">Role para baixo e **clique em Salvar preferências** para confirmar as novas integrações.</span><span class="sxs-lookup"><span data-stu-id="1c262-251">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Botão de of_Save de preferências de imagem que você precisa clicar](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="1c262-253">Iniciar o serviço Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c262-253">Start the Microsoft 365 Defender service</span></span>

> [!NOTE]
> <span data-ttu-id="1c262-254">A partir de 1º de junho de 2020, a Microsoft habilita automaticamente Microsoft 365 Defender recursos para todos os locatários qualificados.</span><span class="sxs-lookup"><span data-stu-id="1c262-254">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="1c262-255">Consulte este [artigo do Microsoft Tech Community sobre qualificação de licença para](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="1c262-255">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span>

<span data-ttu-id="1c262-256">Vá para [Microsoft 365 Central de Segurança.](https://security.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="1c262-256">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="1c262-257">Navegue **até Configurações** e selecione **Microsoft 365 Defender**.</span><span class="sxs-lookup"><span data-stu-id="1c262-257">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![Imagem of_Microsoft captura de tela de opção do Defender 365 Microsoft 365 página Configurações Central de Segurança](../../media/mtp-eval-72b.png)

<span data-ttu-id="1c262-259">Para obter uma orientação mais abrangente, consulte [Ativar Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="1c262-259">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

<span data-ttu-id="1c262-260">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="1c262-260">Congratulations!</span></span> <span data-ttu-id="1c262-261">Você acabou de criar seu laboratório de avaliação Microsoft 365 Defender ou ambiente piloto!</span><span class="sxs-lookup"><span data-stu-id="1c262-261">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="1c262-262">Agora você pode se familiarizar com a interface Microsoft 365 Defender usuário!</span><span class="sxs-lookup"><span data-stu-id="1c262-262">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="1c262-263">Veja o que você pode aprender com o guia interativo Microsoft 365 Defender a seguir e saiba como usar cada painel para suas tarefas de operação de segurança diárias.</span><span class="sxs-lookup"><span data-stu-id="1c262-263">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>

[<span data-ttu-id="1c262-264">Conferir o guia interativo</span><span class="sxs-lookup"><span data-stu-id="1c262-264">Check out the interactive guide</span></span>](https://aka.ms/MTP-Interactive-Guide)

<span data-ttu-id="1c262-265">Em seguida, você pode simular um ataque e ver como os recursos entre produtos detectam, criam alertas e respondem automaticamente a um ataque sem arquivo em um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="1c262-265">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="1c262-266">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="1c262-266">Next step</span></span>

- <span data-ttu-id="1c262-267">[Gerar um alerta de teste](generate-test-alert.md) - Execute uma simulação de ataque em seu laboratório de Microsoft 365 Defender de avaliação.</span><span class="sxs-lookup"><span data-stu-id="1c262-267">[Generate a test alert](generate-test-alert.md) - Run an attack simulation in your Microsoft 365 Defender trial lab.</span></span>
