---
title: Configurar os pilares do Microsoft 365 defender para o laboratório de avaliação ou o ambiente piloto
description: Configure os pilares do Microsoft 365 defender, como o Microsoft defender para Office 365, o Microsoft defender para identidade, o Microsoft Cloud app Security e o Microsoft defender para ponto de extremidade, para seu laboratório de avaliação ou ambiente piloto.
keywords: configurar a avaliação de proteção contra ameaças da Microsoft, configuração de avaliação de proteção contra ameaças da Microsoft, configurar o projeto piloto de proteção contra ameaças da Microsoft, configurar os pilares de proteção contra ameaças da Microsoft, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 240ffd7ec8d46da33c43ec2f9cb50cf59c89f11b
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131292"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="7ea84-104">Configurar os pilares do Microsoft 365 defender para seu laboratório de avaliação ou ambiente piloto</span><span class="sxs-lookup"><span data-stu-id="7ea84-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7ea84-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="7ea84-105">**Applies to:**</span></span>
- <span data-ttu-id="7ea84-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ea84-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="7ea84-107">Criar um laboratório de avaliação do Microsoft 365 defender ou um ambiente piloto e implantá-lo é um processo de três fases:</span><span class="sxs-lookup"><span data-stu-id="7ea84-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="7ea84-108">[![Fase 1: preparar](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="7ea84-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="7ea84-109">Fase 1: preparar</span><span class="sxs-lookup"><span data-stu-id="7ea84-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |<span data-ttu-id="7ea84-110">[![Fase 2: configurar](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="7ea84-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span></span><br/>[<span data-ttu-id="7ea84-111">Fase 2: configurar</span><span class="sxs-lookup"><span data-stu-id="7ea84-111">Phase 2: Set up</span></span>](setup-mtpeval.md) |![Fase 3: integração](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="7ea84-113">Fase 3: integração</span><span class="sxs-lookup"><span data-stu-id="7ea84-113">Phase 3: Onboard</span></span> | <span data-ttu-id="7ea84-114">[![Voltar ao piloto](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="7ea84-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="7ea84-115">Voltar ao manual do piloto</span><span class="sxs-lookup"><span data-stu-id="7ea84-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="7ea84-116">*Você está aqui!*</span><span class="sxs-lookup"><span data-stu-id="7ea84-116">*You are here!*</span></span> | |

<span data-ttu-id="7ea84-117">Você está atualmente na fase de configuração.</span><span class="sxs-lookup"><span data-stu-id="7ea84-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="7ea84-118">A preparação é fundamental para qualquer implantação bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="7ea84-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="7ea84-119">Neste artigo, você será orientado nos pontos que precisará considerar ao se preparar para implantar o Microsoft defender para ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="7ea84-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="7ea84-120">Pilares do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="7ea84-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="7ea84-121">O Microsoft 365 defender consiste em quatro pilares.</span><span class="sxs-lookup"><span data-stu-id="7ea84-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="7ea84-122">Embora um pilar já possa fornecer o valor para a segurança da sua organização de rede, habilitar os quatro pilares Microsoft 365 defender fornecerá à sua organização o mais valor.</span><span class="sxs-lookup"><span data-stu-id="7ea84-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Image of_Microsoft 365 defender Solution for users, Microsoft defender para identidade, para pontos de extremidade Microsoft defender for Endpoint, para aplicativos de nuvem, segurança do aplicativo do Microsoft Cloud e para dados, Microsoft defender para Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="7ea84-124">Esta seção orientará você a configurar:</span><span class="sxs-lookup"><span data-stu-id="7ea84-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="7ea84-125">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7ea84-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="7ea84-126">Microsoft Defender para Identidade</span><span class="sxs-lookup"><span data-stu-id="7ea84-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="7ea84-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7ea84-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="7ea84-128">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="7ea84-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="7ea84-129">Configurar o Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7ea84-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="7ea84-130">Pule esta etapa se você já ativou o defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ea84-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="7ea84-131">Há um módulo do PowerShell chamado *Office 365 Advanced Threat Protection Configuration Analyzer (orca)* que ajuda a determinar algumas dessas configurações.</span><span class="sxs-lookup"><span data-stu-id="7ea84-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="7ea84-132">Ao executar como um administrador em seu locatário, o Get-ORCAReport ajudará a gerar uma avaliação das configurações de higiene de antispam, anti-phishing e outras mensagens.</span><span class="sxs-lookup"><span data-stu-id="7ea84-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="7ea84-133">Você pode baixar este módulo no https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="7ea84-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="7ea84-134">Navegue até a política de gerenciamento de ameaças [do centro de conformidade & segurança do Office 365](https://protection.office.com/homepage)  >  **Threat management**  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Página da política de gerenciamento de ameaças do centro de conformidade & of_Office de imagem 365](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="7ea84-136">Clique em **anti-phishing**, selecione **criar** e preencha o nome e a descrição da política.</span><span class="sxs-lookup"><span data-stu-id="7ea84-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="7ea84-137">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-137">Click **Next**.</span></span>

   ![Imagem of_Office 365 segurança & centro de conformidade página política de anti-phishing onde você pode nomear sua política](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="7ea84-139">Edite sua política anti-phishing avançada no Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ea84-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="7ea84-140">Altere o **limite de phishing avançado** para **2-agressivo**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="7ea84-141">Clique no menu suspenso **Adicionar uma condição** e selecione seu (s) domínio (s) como domínio do destinatário.</span><span class="sxs-lookup"><span data-stu-id="7ea84-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="7ea84-142">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-142">Click **Next**.</span></span>

   ![Imagem of_Office 365 segurança & centro de conformidade página política de anti-phishing onde você pode adicionar uma condição para seu aplicativo](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="7ea84-144">Revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="7ea84-144">Review your settings.</span></span> <span data-ttu-id="7ea84-145">Clique em **criar esta política** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="7ea84-145">Click **Create this policy** to confirm.</span></span> 

   ![Imagem of_Office 365 segurança & centro de conformidade página política de anti-phishing onde você pode revisar suas configurações e clicar no botão criar esta política](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="7ea84-147">Selecione **anexos seguros** e selecione a opção **Ativar ATP para SharePoint, onedrive e Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="7ea84-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Imagem of_Office 365 segurança & centro de conformidade onde você pode ativar a ATP para SharePoint, OneDrive e Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="7ea84-149">Clique no ícone + para criar uma nova política de anexo seguro, aplique-a como domínio de destinatário aos seus domínios.</span><span class="sxs-lookup"><span data-stu-id="7ea84-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="7ea84-150">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-150">Click **Save**.</span></span>

   ![Imagem of_Office 365 segurança & centro de conformidade onde você pode criar um novo criar uma nova política de anexo seguro](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="7ea84-152">Em seguida, selecione a política de **links seguros** e clique no ícone de lápis para editar a política padrão.</span><span class="sxs-lookup"><span data-stu-id="7ea84-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="7ea84-153">Certifique-se de que a opção **não rastrear quando os usuários clicarem em links seguros** não esteja selecionada, enquanto o restante das opções estiver selecionado.</span><span class="sxs-lookup"><span data-stu-id="7ea84-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="7ea84-154">Confira [configurações de links seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="7ea84-154">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="7ea84-155">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-155">Click **Save**.</span></span> 

   ![Imagem of_Office 365 segurança & centro de conformidade que mostra que a opção não controla quando os usuários clicam em seguro não está selecionado](../../media/mtp-eval-38.png)

9. <span data-ttu-id="7ea84-157">Em seguida, selecione a política **anti-malware** , selecione o padrão e escolha o ícone de lápis.</span><span class="sxs-lookup"><span data-stu-id="7ea84-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="7ea84-158">Clique em **configurações** e selecione **Sim e use o texto de notificação padrão** para habilitar a **resposta de detecção de malware**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="7ea84-159">Ativar o **filtro de tipos de anexo comuns** .</span><span class="sxs-lookup"><span data-stu-id="7ea84-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="7ea84-160">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-160">Click **Save**.</span></span>

    ![Image of_Office 365 Security & centro de conformidade a página que mostra que a resposta de detecção de malware está ativada com a notificação padrão e o filtro de tipos de anexo comuns está ativado](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="7ea84-162">Navegue até [Office 365 Security & centro de conformidade](https://protection.office.com/homepage)  >  **pesquisa**  >  **log de auditoria** pesquisa e ative a auditoria.</span><span class="sxs-lookup"><span data-stu-id="7ea84-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Imagem of_Office 365 segurança & centro de conformidade onde você pode ativar a pesquisa de log de auditoria](../../media/mtp-eval-40.png)

12. <span data-ttu-id="7ea84-164">Integre o Microsoft defender para Office 365 com o Microsoft defender para ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="7ea84-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="7ea84-165">Navegue até [Office 365 Security & centro de conformidade](https://protection.office.com/homepage)  >  **Gerenciamento de ameaças** de central  >  **Explorer** de segurança e selecione o **Microsoft defender para configurações de ponto de extremidade** no canto superior direito da tela.</span><span class="sxs-lookup"><span data-stu-id="7ea84-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="7ea84-166">Na caixa de diálogo de conexão do defender for Endpoint, ative **conectar ao Microsoft defender para ponto de extremidade**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Imagem of_Office 365 segurança & centro de conformidade onde você pode ativar o Microsoft defender para a conexão de ponto de extremidade no](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="7ea84-168">Configurar o Microsoft defender para identidade</span><span class="sxs-lookup"><span data-stu-id="7ea84-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="7ea84-169">Pule esta etapa se você já tiver habilitado o Microsoft defender para identidade</span><span class="sxs-lookup"><span data-stu-id="7ea84-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="7ea84-170">Navegue até a [central de segurança do Microsoft 365](https://security.microsoft.com/info) > selecione **mais recursos**  >  **Microsoft defender para identidade**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Imagem of_Microsoft 365 página da central de segurança onde há uma opção para abrir o Microsoft defender para identidade](../../media/mtp-eval-42.png)

2. <span data-ttu-id="7ea84-172">Clique em **criar** para iniciar o assistente do Microsoft defender para identidade.</span><span class="sxs-lookup"><span data-stu-id="7ea84-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![Página do assistente de imagem of_Microsoft defender para identidade onde você deve clicar em criar botão](../../media/mtp-eval-43.png)

3. <span data-ttu-id="7ea84-174">Escolha **fornecer um nome de usuário e senha para se conectar à sua floresta do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Página de boas-vindas do of_Microsoft defender para identidade](../../media/mtp-eval-44.png)

4. <span data-ttu-id="7ea84-176">Insira suas credenciais locais do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7ea84-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="7ea84-177">Pode ser qualquer conta de usuário que tenha acesso de leitura ao Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7ea84-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Imagem of_Microsoft defender da página de serviços de diretório de identidade onde você deve colocar suas credenciais](../../media/mtp-eval-45.png)

5. <span data-ttu-id="7ea84-179">Em seguida, escolha **baixar a configuração do sensor** e transferir o arquivo para o controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="7ea84-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Imagem of_Microsoft defender para a página de identidade onde você pode selecionar a configuração do sensor de download](../../media/mtp-eval-46.png)

6. <span data-ttu-id="7ea84-181">Execute a instalação do sensor de identidade do Microsoft defender e comece seguindo o assistente.</span><span class="sxs-lookup"><span data-stu-id="7ea84-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Imagem of_Microsoft defender para a página de identidade onde você deve clicar em avançar para seguir o assistente do sensor de identidade do Microsoft defender](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="7ea84-183">Clique em **Avançar** no tipo de implantação do sensor.</span><span class="sxs-lookup"><span data-stu-id="7ea84-183">Click **Next** at the sensor deployment type.</span></span>

   ![Imagem of_Microsoft defender para a página de identidade onde você deve clicar em avançar para ir para a próxima página](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="7ea84-185">Copie a chave de acesso porque você precisa inseri-la próxima no assistente.</span><span class="sxs-lookup"><span data-stu-id="7ea84-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Página sensores de of_the de imagem onde você deve copiar a tecla de acesso que precisa inserir na próxima página do assistente de instalação do sensor de identidade do Microsoft defender](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="7ea84-187">Copie a chave de acesso no assistente e clique em **instalar**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Imagem of_Microsoft defender para o assistente de sensor de identidade onde você deve fornecer a chave de acesso e clique no botão instalar](../../media/mtp-eval-50.png)

10. <span data-ttu-id="7ea84-189">Parabéns, você configurou com êxito o Microsoft defender para identidade no seu controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="7ea84-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Imagem of_Microsoft defender para a conclusão da instalação do assistente do sensor de identidade onde você deve clicar no botão concluir](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="7ea84-191">Na seção configurações [de identidade do Microsoft defender](https://go.microsoft.com/fwlink/?linkid=2040449) , selecione \* \* Microsoft defender para ponto de extremidade \* \* e ative o botão de alternância.</span><span class="sxs-lookup"><span data-stu-id="7ea84-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="7ea84-192">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-192">Click **Save**.</span></span> 

    ![Imagem of_the a página de configurações do Microsoft defender para identidade onde você deve ativar a ativar/desativar o Microsoft defender para ponto de extremidade](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="7ea84-194">O Windows Defender ATP foi remarcado como Microsoft defender para ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="7ea84-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="7ea84-195">As alterações de remarcação em todos os nossos portais estão sendo distribuídas para consistência.</span><span class="sxs-lookup"><span data-stu-id="7ea84-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="7ea84-196">Configurar o Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="7ea84-196">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="7ea84-197">Pule esta etapa se você já tiver habilitado o Microsoft Cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="7ea84-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="7ea84-198">Navegue até [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **mais recursos**  >  **Microsoft Cloud app Security**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Imagem of_Microsoft 365 página da central de segurança onde você pode ver o Microsoft Cloud app Card e deve clicar no botão abrir](../../media/mtp-eval-53.png)

2. <span data-ttu-id="7ea84-200">No prompt de informações para integrar o Microsoft defender para identidade, selecione **habilitar o Microsoft defender para integração de dados de identidade**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Imagem of_the solicitação de informações para integrar o Microsoft defender para identidade onde você deve selecionar o link habilitar o Microsoft defender para identidade de dados de identidade](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="7ea84-202">Se você não vir esse prompt, pode significar que sua integração de dados do Microsoft defender para identidade já foi habilitada.</span><span class="sxs-lookup"><span data-stu-id="7ea84-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="7ea84-203">No entanto, se você não tiver certeza, entre em contato com seu administrador de ti para confirmar.</span><span class="sxs-lookup"><span data-stu-id="7ea84-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="7ea84-204">Vá para **configurações**, ative o **Microsoft defender para habilitar a integração de identidades** e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Imagem of_the de configurações onde você deve ativar o Microsoft defender para habilitar a integração de identidade e clicar em salvar](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="7ea84-206">Para novas instâncias do Microsoft defender para identidade, essa integração é ativada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7ea84-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="7ea84-207">Confirme se a integração do Microsoft defender para identidades foi habilitada antes de prosseguir para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="7ea84-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="7ea84-208">Nas configurações de descoberta de nuvem, selecione **Microsoft defender para a integração de ponto de extremidade** e habilite a integração.</span><span class="sxs-lookup"><span data-stu-id="7ea84-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="7ea84-209">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-209">Click **Save**.</span></span>

   ![Imagem of_the página do Microsoft defender para ponto de extremidade onde a caixa de seleção bloquear aplicativos não aprovados em Microsoft defender para integração de ponto de extremidade está selecionada.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="7ea84-212">Em configurações de descoberta de nuvem, selecione o **enriquecimento do usuário** e habilite a integração com o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7ea84-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Imagem da seção de enriquecimento do usuário em que a caixa de seleção enriquecimento de identificadores de usuário descobertos com o Azure Active Directory está marcada](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="7ea84-214">Configurar o Microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="7ea84-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="7ea84-215">Pule esta etapa se já tiver habilitado o Microsoft defender para ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="7ea84-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="7ea84-216">Navegue até a central de [segurança da Microsoft 365](https://security.microsoft.com/info)  >  **mais recursos**  >  **central de segurança do Microsoft defender**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="7ea84-217">Clique em **Abrir**. </span><span class="sxs-lookup"><span data-stu-id="7ea84-217">Click **Open**.</span></span>

   ![Opção da central de segurança de imagem of_Microsoft defender na página centro de segurança do Microsoft 365](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="7ea84-219">Siga o assistente do Microsoft defender para pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="7ea84-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="7ea84-220">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-220">Click **Next**.</span></span> 

   ![Imagem of_the página do assistente de boas-vindas do Microsoft defender Security Center](../../media/mtp-eval-59.png)

3. <span data-ttu-id="7ea84-222">Escolha com base em seu local de armazenamento de dados preferido, política de retenção de dados, tamanho da organização e consentimento para recursos de visualização.</span><span class="sxs-lookup"><span data-stu-id="7ea84-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Imagem of_the página para selecionar o país de armazenamento de dados, a política de retenção e o tamanho da organização.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="7ea84-225">Você não pode alterar algumas das configurações, como o local de armazenamento de dados, posteriormente.</span><span class="sxs-lookup"><span data-stu-id="7ea84-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="7ea84-226">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-226">Click **Next**.</span></span> 

4. <span data-ttu-id="7ea84-227">Clique em **continuar** para provisionar seu locatário do Microsoft defender para ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="7ea84-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Página de of_the de imagem solicitando que você clique no botão continuar para criar sua instância de nuvem](../../media/mtp-eval-61.png)

5. <span data-ttu-id="7ea84-229">Integração dos pontos de extremidade por meio de políticas de grupo, Microsoft Endpoint Manager ou executando um script local para o Microsoft defender para ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="7ea84-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="7ea84-230">Para simplificar, este guia usa o script local.</span><span class="sxs-lookup"><span data-stu-id="7ea84-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="7ea84-231">Clique em **baixar pacote** e copie o script de integração para seus pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="7ea84-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Imagem of_page solicitando que você clique no botão baixar pacote para copiar o script de integração para o ponto de extremidade ou pontos de extremidade](../../media/mtp-eval-62.png)

7. <span data-ttu-id="7ea84-233">No ponto de extremidade, execute o script de integração como administrador e escolha Y.</span><span class="sxs-lookup"><span data-stu-id="7ea84-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Imagem of_the linha de comando onde você executa o script de integração e escolhe Y para continuar](../../media/mtp-eval-63.png)

8. <span data-ttu-id="7ea84-235">Parabéns, você entrou no primeiro ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="7ea84-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Imagem of_the linha de comando, onde você obtém a confirmação de que você tenha integrado seu primeiro ponto de extremidade.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="7ea84-238">Copie-cole o teste de detecção do assistente do Microsoft defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="7ea84-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Imagem of_the executar uma etapa de teste de detecção onde você deve clicar em copiar para copiar o script de teste de detecção que deve ser colado no prompt de comando](../../media/mtp-eval-65.png)

10. <span data-ttu-id="7ea84-240">Copie o script do PowerShell para um prompt de comando com privilégios elevados e execute-o.</span><span class="sxs-lookup"><span data-stu-id="7ea84-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Imagem of_command prompt onde você deve copiar o script do PowerShell para um prompt de comando elevado e executá-lo](../../media/mtp-eval-66.png)

11. <span data-ttu-id="7ea84-242">Selecione **começar a usar o Microsoft defender para ponto de extremidade** do assistente.</span><span class="sxs-lookup"><span data-stu-id="7ea84-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![A imagem of_the prompt de confirmação do assistente onde você deve clicar em começar a usar o Microsoft defender para ponto de extremidade](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="7ea84-244">Visite a [central de segurança do Microsoft defender](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="7ea84-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="7ea84-245">Vá até **configurações** e selecione **recursos avançados**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Imagem do menu configurações da central de segurança do of_Microsoft defender onde você deve selecionar recursos avançados](../../media/mtp-eval-68.png)

13. <span data-ttu-id="7ea84-247">Ative a integração com o **Microsoft defender para identidade**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Image of_Microsoft defender recursos avançados da central de segurança, Microsoft defender para opções de identidade alternar que você precisa ativar](../../media/mtp-eval-69.png)

14. <span data-ttu-id="7ea84-249">Ative a integração com a **inteligência contra ameaças do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Image of_Microsoft defender central de segurança recursos avançados, opção de inteligência de ameaças do Office 365-você precisa ativar](../../media/mtp-eval-70.png)

15. <span data-ttu-id="7ea84-251">Ative a integração com **o Microsoft Cloud app Security**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Image of_Microsoft defender recursos avançados do centro de segurança, opções de segurança do aplicativo Microsoft Cloud que você precisa ativar](../../media/mtp-eval-71.png)

16. <span data-ttu-id="7ea84-253">Role para baixo e clique em **salvar preferências** para confirmar as novas integrações.</span><span class="sxs-lookup"><span data-stu-id="7ea84-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Botão de preferências de of_Save de imagem que você precisa clicar](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="7ea84-255">Iniciar o serviço Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ea84-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="7ea84-256">A partir de 1º de junho de 2020, a Microsoft habilita automaticamente os recursos do Microsoft 365 defender para todos os locatários qualificados.</span><span class="sxs-lookup"><span data-stu-id="7ea84-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="7ea84-257">Confira este [artigo da comunidade técnica da Microsoft sobre a qualificação de licença](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="7ea84-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="7ea84-258">Vá para a [central de segurança do Microsoft 365](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="7ea84-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="7ea84-259">Navegue até **configurações** e, em seguida, selecione **Microsoft 365 defender**.</span><span class="sxs-lookup"><span data-stu-id="7ea84-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="7ea84-260">Captura de tela de opção de imagem of_Microsoft 365 defender da página de configurações da central de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7ea84-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="7ea84-261">Para obter uma orientação mais abrangente, consulte [ativar o Microsoft 365 defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="7ea84-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](mtp-enable.md).</span></span> 

<span data-ttu-id="7ea84-262">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="7ea84-262">Congratulations!</span></span> <span data-ttu-id="7ea84-263">Você acabou de criar o laboratório de avaliação do Microsoft 365 defender ou o ambiente piloto!</span><span class="sxs-lookup"><span data-stu-id="7ea84-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="7ea84-264">Agora você pode se familiarizar com a interface do usuário do Microsoft 365 defender!</span><span class="sxs-lookup"><span data-stu-id="7ea84-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="7ea84-265">Veja o que você pode aprender no seguinte guia interativo do Microsoft 365 defender e saiba como usar cada painel para suas tarefas de operação de segurança diárias.</span><span class="sxs-lookup"><span data-stu-id="7ea84-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="7ea84-266">Em seguida, você pode simular um ataque e ver como os recursos de produtos cruzam detectar, criar alertas e responder automaticamente a um ataque sem arquivo em um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="7ea84-266">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="7ea84-267">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="7ea84-267">Next step</span></span>
|[<span data-ttu-id="7ea84-268">Fase de simulação de ataque</span><span class="sxs-lookup"><span data-stu-id="7ea84-268">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="7ea84-269">Execute a simulação de ataque para seu ambiente piloto do Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="7ea84-269">Run the attack simulation for your Microsoft 365 Defender pilot environment.</span></span>
|:-------|:-----|
