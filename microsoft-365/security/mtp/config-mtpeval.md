---
title: Configurar os pilares de proteção contra ameaças da Microsoft para o laboratório de avaliação ou ambiente piloto
description: Configure os pilares de proteção contra ameaças da Microsoft, como o Office 365 ATP, o Azure ATP, o Microsoft Cloud app Security e o Microsoft defender ATP para seu laboratório de avaliação ou ambiente piloto.
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
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 79e141ad85eecab827e0caa98fe022f88335c671
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48368144"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="708af-104">Configurar os pilares de proteção contra ameaças da Microsoft para seu laboratório de avaliação ou ambiente piloto</span><span class="sxs-lookup"><span data-stu-id="708af-104">Configure Microsoft Threat Protection pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="708af-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="708af-105">**Applies to:**</span></span>
- <span data-ttu-id="708af-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="708af-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="708af-107">A criação de um laboratório de avaliação de proteção contra ameaças da Microsoft ou ambiente piloto e sua implantação é um processo de três fases:</span><span class="sxs-lookup"><span data-stu-id="708af-107">Creating a Microsoft Threat Protection trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Preparar o laboratório de avaliação de proteção contra ameaças da Microsoft ou o ambiente piloto" />
      <br/><span data-ttu-id="708af-109">Fase 1: preparar </a></span><span class="sxs-lookup"><span data-stu-id="708af-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="Configurar o laboratório de avaliação de proteção contra ameaças da Microsoft ou o ambiente piloto" />
      <br/><span data-ttu-id="708af-111">Fase 2: configuração </a></span><span class="sxs-lookup"><span data-stu-id="708af-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Configurar cada pilar de proteção contra ameaças da Microsoft para o laboratório de avaliação de proteção contra ameaças da Microsoft ou o ambiente piloto e pontos de extremidade integrados" />
      <br/><span data-ttu-id="708af-113">Fase 3: configurar o & integrado </a></span><span class="sxs-lookup"><span data-stu-id="708af-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>
  </tr>
</table>

<span data-ttu-id="708af-114">Você está atualmente na fase de configuração.</span><span class="sxs-lookup"><span data-stu-id="708af-114">You're currently in the configuration phase.</span></span>


<span data-ttu-id="708af-115">A preparação é fundamental para qualquer implantação bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="708af-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="708af-116">Neste artigo, você será orientado nos pontos que precisará considerar ao se preparar para implantar o Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="708af-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="708af-117">Pilares de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="708af-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="708af-118">A proteção contra ameaças da Microsoft consiste em quatro pilares.</span><span class="sxs-lookup"><span data-stu-id="708af-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="708af-119">Embora um pilar já possa fornecer um valor para a segurança da sua organização de rede, a habilitação dos quatro pilares de proteção contra ameaças da Microsoft dará à sua organização o mais valor.</span><span class="sxs-lookup"><span data-stu-id="708af-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![<span data-ttu-id="708af-120">Imagem of_Microsoft solução de proteção contra ameaças para usuários, proteção avançada contra ameaças do Azure, para pontos de extremidade proteção avançada contra ameaças do Microsoft defender, para aplicativos de nuvem, segurança do aplicativo do Microsoft Cloud e para dados, proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="708af-120">Image of_Microsoft Threat Protection solution for users, Azure Advanced Threat Protection, for endpoints Microsoft Defender Advanced Threat Protection, for cloud apps, Microsoft Cloud App Security, and for data, Office 365 Advanced Threat Protection</span></span>  ](../../media/mtp-eval-31.png)

<span data-ttu-id="708af-121">Esta seção orientará você a configurar:</span><span class="sxs-lookup"><span data-stu-id="708af-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="708af-122">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="708af-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="708af-123">Proteção Avançada contra Ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="708af-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="708af-124">Segurança no aplicativo na nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="708af-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="708af-125">Proteção avançada contra ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="708af-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="708af-126">Configurar a proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="708af-126">Configure Office 365 Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="708af-127">Pule esta etapa se já tiver habilitado a proteção avançada contra ameaças do Office 365.</span><span class="sxs-lookup"><span data-stu-id="708af-127">Skip this step if you've already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="708af-128">Há um módulo do PowerShell chamado *Office 365 Advanced Threat Protection Configuration Analyzer (orca)* que ajuda a determinar algumas dessas configurações.</span><span class="sxs-lookup"><span data-stu-id="708af-128">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="708af-129">Ao executar como um administrador em seu locatário, o Get-ORCAReport ajudará a gerar uma avaliação das configurações de higiene de antispam, anti-phishing e outras mensagens.</span><span class="sxs-lookup"><span data-stu-id="708af-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="708af-130">Você pode baixar este módulo no https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="708af-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="708af-131">Navegue até a política de gerenciamento de ameaças [do centro de conformidade & segurança do Office 365](https://protection.office.com/homepage)  >  **Threat management**  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="708af-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Página da política de gerenciamento de ameaças do centro de conformidade & of_Office de imagem 365](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="708af-133">Clique em **anti-phishing ATP**, selecione **criar** e preencha o nome e a descrição da política.</span><span class="sxs-lookup"><span data-stu-id="708af-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="708af-134">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="708af-134">Click **Next**.</span></span>

   ![Imagem of_Office 365 segurança & centro de conformidade página política de anti-phishing onde você pode nomear sua política](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="708af-136">Edite a política de anti-phishing avançada da ATP.</span><span class="sxs-lookup"><span data-stu-id="708af-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="708af-137">Altere o **limite de phishing avançado** para **2-agressivo**.</span><span class="sxs-lookup"><span data-stu-id="708af-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="708af-138">Clique no menu suspenso **Adicionar uma condição** e selecione seu (s) domínio (s) como domínio do destinatário.</span><span class="sxs-lookup"><span data-stu-id="708af-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="708af-139">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="708af-139">Click **Next**.</span></span>

   ![Imagem of_Office 365 segurança & centro de conformidade página política de anti-phishing onde você pode adicionar uma condição para seu aplicativo](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="708af-141">Revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="708af-141">Review your settings.</span></span> <span data-ttu-id="708af-142">Clique em **criar esta política** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="708af-142">Click **Create this policy** to confirm.</span></span> 

   ![Imagem of_Office 365 segurança & centro de conformidade página política de anti-phishing onde você pode revisar suas configurações e clicar no botão criar esta política](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="708af-144">Selecione **anexos seguros de ATP** e selecione a opção **Ativar ATP para SharePoint, onedrive e Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="708af-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Imagem of_Office 365 segurança & centro de conformidade onde você pode ativar a ATP para SharePoint, OneDrive e Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="708af-146">Clique no ícone + para criar uma nova política de anexo seguro, aplique-a como domínio de destinatário aos seus domínios.</span><span class="sxs-lookup"><span data-stu-id="708af-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="708af-147">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="708af-147">Click **Save**.</span></span>

   ![Imagem of_Office 365 segurança & centro de conformidade onde você pode criar um novo criar uma nova política de anexo seguro](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="708af-149">Em seguida, selecione a política de **links seguros de ATP** e clique no ícone de lápis para editar a política padrão.</span><span class="sxs-lookup"><span data-stu-id="708af-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="708af-150">Certifique-se de que a opção **não rastrear quando os usuários clicarem em links seguros** não esteja selecionada, enquanto o restante das opções estiver selecionado.</span><span class="sxs-lookup"><span data-stu-id="708af-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="708af-151">Confira [configurações de links seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="708af-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="708af-152">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="708af-152">Click **Save**.</span></span> 

   ![Imagem of_Office 365 segurança & centro de conformidade que mostra que a opção não controla quando os usuários clicam em seguro não está selecionado](../../media/mtp-eval-38.png)

9. <span data-ttu-id="708af-154">Em seguida, selecione a política **anti-malware** , selecione o padrão e escolha o ícone de lápis.</span><span class="sxs-lookup"><span data-stu-id="708af-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="708af-155">Clique em **configurações** e selecione **Sim e use o texto de notificação padrão** para habilitar a **resposta de detecção de malware**.</span><span class="sxs-lookup"><span data-stu-id="708af-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="708af-156">Ativar o **filtro de tipos de anexo comuns** .</span><span class="sxs-lookup"><span data-stu-id="708af-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="708af-157">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="708af-157">Click **Save**.</span></span>

    ![Image of_Office 365 Security & centro de conformidade a página que mostra que a resposta de detecção de malware está ativada com a notificação padrão e o filtro de tipos de anexo comuns está ativado](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="708af-159">Navegue até [Office 365 Security & centro de conformidade](https://protection.office.com/homepage)  >  **pesquisa**  >  **log de auditoria** pesquisa e ative a auditoria.</span><span class="sxs-lookup"><span data-stu-id="708af-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Imagem of_Office 365 segurança & centro de conformidade onde você pode ativar a pesquisa de log de auditoria](../../media/mtp-eval-40.png)

12. <span data-ttu-id="708af-161">Integrar o Office 365 ATP com o Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="708af-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="708af-162">Navegue até [Office 365 Security & centro de conformidade](https://protection.office.com/homepage)de  >  **Gerenciamento de ameaças**do centro  >  **Explorer** de conformidade e selecione **configurações do WDATP** no canto superior direito da tela.</span><span class="sxs-lookup"><span data-stu-id="708af-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="708af-163">Na caixa de diálogo conexão ATP do Microsoft defender, ative **conectar ao Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="708af-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>

    ![Imagem of_Office 365 segurança & centro de conformidade onde você pode ativar a conexão ATP do Windows Defender](../../media/mtp-eval-41.png)

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="708af-165">Configurar a proteção avançada contra ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="708af-165">Configure Azure Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="708af-166">Pule esta etapa se já tiver habilitado a proteção avançada contra ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="708af-166">Skip this step if you've already enabled Azure Advanced Threat Protection</span></span>

1. <span data-ttu-id="708af-167">Navegue até a [central de segurança do Microsoft 365](https://security.microsoft.com/info) > selecione **mais recursos**  >  **proteção avançada contra ameaças do Azure**.</span><span class="sxs-lookup"><span data-stu-id="708af-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>

   ![Imagem of_Microsoft 365 página da central de segurança onde há uma opção para abrir a proteção avançada contra ameaças do Azure](../../media/mtp-eval-42.png)

2. <span data-ttu-id="708af-169">Clique em **criar** para iniciar o assistente de proteção avançada contra ameaças do Azure.</span><span class="sxs-lookup"><span data-stu-id="708af-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 

   ![Imagem of_Azure página do assistente de proteção avançada contra ameaças onde você deve clicar em criar botão](../../media/mtp-eval-43.png)

3. <span data-ttu-id="708af-171">Escolha **fornecer um nome de usuário e senha para se conectar à sua floresta do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="708af-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Página de boas-vindas de proteção avançada contra ameaças de imagem of_Azure](../../media/mtp-eval-44.png)

4. <span data-ttu-id="708af-173">Insira suas credenciais locais do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="708af-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="708af-174">Pode ser qualquer conta de usuário que tenha acesso de leitura ao Active Directory.</span><span class="sxs-lookup"><span data-stu-id="708af-174">This can be any user account that has read access to Active Directory.</span></span>

   ![Imagem of_Azure página serviços de diretório avançado de proteção contra ameaças onde você deve colocar suas credenciais](../../media/mtp-eval-45.png)

5. <span data-ttu-id="708af-176">Em seguida, escolha **baixar a configuração do sensor** e transferir o arquivo para o controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="708af-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Imagem of_Azure página proteção avançada contra ameaças, onde você pode selecionar a configuração do sensor de download](../../media/mtp-eval-46.png)

6. <span data-ttu-id="708af-178">Execute a configuração do sensor ATP do Azure e comece seguindo o assistente.</span><span class="sxs-lookup"><span data-stu-id="708af-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>

   ![Página de of_Azure proteção avançada contra ameaças, onde você deve clicar em avançar para seguir o assistente do sensor ATP do Azure](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="708af-180">Clique em **Avançar** no tipo de implantação do sensor.</span><span class="sxs-lookup"><span data-stu-id="708af-180">Click **Next** at the sensor deployment type.</span></span>

   ![Imagem of_Azure página proteção avançada contra ameaças onde você deve clicar em avançar para ir para a próxima página](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="708af-182">Copie a chave de acesso porque você precisa inseri-la próxima no assistente.</span><span class="sxs-lookup"><span data-stu-id="708af-182">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Página de sensores de of_the de imagem onde você deve copiar a tecla de acesso que precisa inserir na próxima página do assistente de instalação do sensor ATP do Azure](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="708af-184">Copie a chave de acesso no assistente e clique em **instalar**.</span><span class="sxs-lookup"><span data-stu-id="708af-184">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Imagem of_Azure proteção avançada contra ameaças à página Assistente do sensor ATP do Azure onde você deve fornecer a tecla de acesso e clique no botão instalar](../../media/mtp-eval-50.png)

10. <span data-ttu-id="708af-186">Parabéns, você configurou com êxito a proteção avançada contra ameaças do Azure no seu controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="708af-186">Congratulations, you've successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>

    ![Imagem of_Azure proteção avançada contra ameaças para a conclusão da instalação do assistente do sensor ATP no qual você deve clicar no botão concluir](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="708af-188">Na seção Configurações de [ATP do Azure Azure](https://go.microsoft.com/fwlink/?linkid=2040449) , selecione **Windows Defender ATP**e ative o botão de alternância.</span><span class="sxs-lookup"><span data-stu-id="708af-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn on the toggle.</span></span> <span data-ttu-id="708af-189">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="708af-189">Click **Save**.</span></span> 

    ![Imagem of_the página de configurações de ATP do Azure Azure onde você deve ativar a opção de ativar o Windows Defender ATP](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="708af-191">O Windows Defender ATP foi remarcado como Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="708af-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="708af-192">As alterações de remarcação em todos os nossos portais estão sendo distribuídas para consistência.</span><span class="sxs-lookup"><span data-stu-id="708af-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="708af-193">Configurar o Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="708af-193">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="708af-194">Pule esta etapa se você já tiver habilitado o Microsoft Cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="708af-194">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="708af-195">Navegue até [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **mais recursos**  >  **Microsoft Cloud app Security**.</span><span class="sxs-lookup"><span data-stu-id="708af-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Imagem of_Microsoft 365 página da central de segurança onde você pode ver o Microsoft Cloud app Card e deve clicar no botão abrir](../../media/mtp-eval-53.png)

2. <span data-ttu-id="708af-197">No prompt de informações para integrar o Azure ATP, selecione **habilitar a integração de dados ATP do Azure**.</span><span class="sxs-lookup"><span data-stu-id="708af-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span>
  
   ![Imagem of_the solicitação de informações para integrar o Azure ATP onde você deve selecionar o link habilitar a integração de dados ATP do Azure](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="708af-199">Se você não vir esse prompt, pode significar que sua integração de dados ATP do Azure já foi habilitada.</span><span class="sxs-lookup"><span data-stu-id="708af-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="708af-200">No entanto, se você não tiver certeza, entre em contato com seu administrador de ti para confirmar.</span><span class="sxs-lookup"><span data-stu-id="708af-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="708af-201">Vá para **configurações**, ative a opção de ativação da **integração do Azure ATP** e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="708af-201">Go to **Settings**, turn on the **Azure ATP integration** toggle, then click **Save**.</span></span> 

   ![Página de configurações de of_the de imagem, onde você deve ativar a integração do Azure ATP e, em seguida, clique em salvar](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="708af-203">Para novas instâncias ATP do Azure, esta integração alternada é automaticamente ativada.</span><span class="sxs-lookup"><span data-stu-id="708af-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="708af-204">Confirme se a sua integração do Azure ATP foi habilitada antes de prosseguir para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="708af-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="708af-205">Nas configurações de descoberta de nuvem, selecione **integração do Microsoft defender ATP**e habilite a integração.</span><span class="sxs-lookup"><span data-stu-id="708af-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="708af-206">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="708af-206">Click **Save**.</span></span>

   ![Imagem of_the página do Microsoft defender ATP onde a caixa de seleção bloquear aplicativos não aprovados em integração ATP do Microsoft defender está selecionada.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="708af-209">Em configurações de descoberta de nuvem, selecione o **enriquecimento do usuário**e habilite a integração com o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="708af-209">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Imagem da seção de enriquecimento do usuário em que a caixa de seleção enriquecimento de identificadores de usuário descobertos com o Azure Active Directory está marcada](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="708af-211">Configurar a proteção avançada contra ameaças do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="708af-211">Configure Microsoft Defender Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="708af-212">Pule esta etapa se você já tiver habilitado a proteção avançada contra ameaças do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="708af-212">Skip this step if you've already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="708af-213">Navegue até a central de [segurança da Microsoft 365](https://security.microsoft.com/info)  >  **mais recursos**  >  **central de segurança do Microsoft defender**.</span><span class="sxs-lookup"><span data-stu-id="708af-213">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="708af-214">Clique em **Abrir**. </span><span class="sxs-lookup"><span data-stu-id="708af-214">Click **Open**.</span></span>

   ![Opção da central de segurança de imagem of_Microsoft defender na página centro de segurança do Microsoft 365](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="708af-216">Siga o assistente de proteção avançada contra ameaças do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="708af-216">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="708af-217">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="708af-217">Click **Next**.</span></span> 

   ![Imagem of_the página do assistente de boas-vindas do Microsoft defender Security Center](../../media/mtp-eval-59.png)

3. <span data-ttu-id="708af-219">Escolha com base em seu local de armazenamento de dados preferido, política de retenção de dados, tamanho da organização e consentimento para recursos de visualização.</span><span class="sxs-lookup"><span data-stu-id="708af-219">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Imagem of_the página para selecionar o país de armazenamento de dados, a política de retenção e o tamanho da organização.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="708af-222">Você não pode alterar algumas das configurações, como o local de armazenamento de dados, posteriormente.</span><span class="sxs-lookup"><span data-stu-id="708af-222">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="708af-223">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="708af-223">Click **Next**.</span></span> 

4. <span data-ttu-id="708af-224">Clique em **continuar** e ele provisionrá o locatário do Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="708af-224">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>

   ![Página de of_the de imagem solicitando que você clique no botão continuar para criar sua instância de nuvem](../../media/mtp-eval-61.png)

5. <span data-ttu-id="708af-226">Integração dos pontos de extremidade por meio de políticas de grupo, Microsoft Endpoint Manager ou executando um script local para o Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="708af-226">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="708af-227">Para simplificar, este guia usa o script local.</span><span class="sxs-lookup"><span data-stu-id="708af-227">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="708af-228">Clique em **baixar pacote** e copie o script de integração para seus pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="708af-228">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Imagem of_page solicitando que você clique no botão baixar pacote para copiar o script de integração para o ponto de extremidade ou pontos de extremidade](../../media/mtp-eval-62.png)

7. <span data-ttu-id="708af-230">No ponto de extremidade, execute o script de integração como administrador e escolha Y.</span><span class="sxs-lookup"><span data-stu-id="708af-230">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Imagem of_the linha de comando onde você executa o script de integração e escolhe Y para continuar](../../media/mtp-eval-63.png)

8. <span data-ttu-id="708af-232">Parabéns, você entrou no primeiro ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="708af-232">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Imagem of_the linha de comando, onde você obtém a confirmação de que você tenha integrado seu primeiro ponto de extremidade.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="708af-235">Copie-cole o teste de detecção do assistente do Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="708af-235">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>

   ![Imagem of_the executar uma etapa de teste de detecção onde você deve clicar em copiar para copiar o script de teste de detecção que deve ser colado no prompt de comando](../../media/mtp-eval-65.png)

10. <span data-ttu-id="708af-237">Copie o script do PowerShell para um prompt de comando com privilégios elevados e execute-o.</span><span class="sxs-lookup"><span data-stu-id="708af-237">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Imagem of_command prompt onde você deve copiar o script do PowerShell para um prompt de comando elevado e executá-lo](../../media/mtp-eval-66.png)

11. <span data-ttu-id="708af-239">Selecione **começar a usar o Microsoft defender ATP** no assistente.</span><span class="sxs-lookup"><span data-stu-id="708af-239">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>

    ![A imagem of_the prompt de confirmação do assistente onde você deve clicar em Iniciar usando o Microsoft defender ATP](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="708af-241">Visite a [central de segurança do Microsoft defender](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="708af-241">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="708af-242">Vá até **configurações** e selecione **recursos avançados**.</span><span class="sxs-lookup"><span data-stu-id="708af-242">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Imagem do menu configurações da central de segurança do of_Microsoft defender onde você deve selecionar recursos avançados](../../media/mtp-eval-68.png)

13. <span data-ttu-id="708af-244">Ative a integração com a **proteção avançada contra ameaças do Azure**.</span><span class="sxs-lookup"><span data-stu-id="708af-244">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  

    ![Image of_Microsoft defender recursos avançados do centro de segurança, opção de proteção avançada contra ameaças do Azure para habilitar](../../media/mtp-eval-69.png)

14. <span data-ttu-id="708af-246">Ative a integração com a **inteligência contra ameaças do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="708af-246">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Image of_Microsoft defender central de segurança recursos avançados, opção de inteligência de ameaças do Office 365-você precisa ativar](../../media/mtp-eval-70.png)

15. <span data-ttu-id="708af-248">Ative a integração com **o Microsoft Cloud app Security**.</span><span class="sxs-lookup"><span data-stu-id="708af-248">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Image of_Microsoft defender recursos avançados do centro de segurança, opções de segurança do aplicativo Microsoft Cloud que você precisa ativar](../../media/mtp-eval-71.png)

16. <span data-ttu-id="708af-250">Role para baixo e clique em **salvar preferências** para confirmar as novas integrações.</span><span class="sxs-lookup"><span data-stu-id="708af-250">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Botão de preferências de of_Save de imagem que você precisa clicar](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-threat-protection-service"></a><span data-ttu-id="708af-252">Iniciar o serviço da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="708af-252">Start the Microsoft Threat Protection service</span></span>

>[!NOTE]
><span data-ttu-id="708af-253">A partir de 1º de junho de 2020, a Microsoft habilita automaticamente os recursos de proteção contra ameaças da Microsoft para todos os locatários qualificados.</span><span class="sxs-lookup"><span data-stu-id="708af-253">Starting June 1, 2020, Microsoft automatically enables Microsoft Threat Protection features for all eligible tenants.</span></span> <span data-ttu-id="708af-254">Confira este [artigo da comunidade técnica da Microsoft sobre a qualificação de licença](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="708af-254">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="708af-255">Vá para a [central de segurança do Microsoft 365](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="708af-255">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="708af-256">Navegue até **configurações** e selecione **proteção contra ameaças da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="708af-256">Navigate to **Settings** and then select **Microsoft Threat Protection**.</span></span>

![<span data-ttu-id="708af-257">Captura de tela da opção de proteção contra ameaças de imagem of_Microsoft da página de configurações da central de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="708af-257">Image of_Microsoft Threat Protection option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="708af-258">Para obter uma orientação mais abrangente, consulte [ativar a proteção contra ameaças da Microsoft](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="708af-258">For a more comprehensive guidance, see [Turn on Microsoft Threat Protection](mtp-enable.md).</span></span> 

<span data-ttu-id="708af-259">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="708af-259">Congratulations!</span></span> <span data-ttu-id="708af-260">Você acabou de criar o laboratório de avaliação de proteção contra ameaças da Microsoft ou o ambiente piloto!</span><span class="sxs-lookup"><span data-stu-id="708af-260">You've just created your Microsoft Threat Protection trial lab or pilot environment!</span></span> <span data-ttu-id="708af-261">Agora você pode se familiarizar com a interface de usuário da proteção contra ameaças da Microsoft!</span><span class="sxs-lookup"><span data-stu-id="708af-261">Now you can familiarize yourself with the Microsoft Threat Protection user interface!</span></span> <span data-ttu-id="708af-262">Veja o que você pode aprender no seguinte guia interativo de proteção contra ameaças da Microsoft e saiba como usar cada painel para suas tarefas de operação de segurança diárias.</span><span class="sxs-lookup"><span data-stu-id="708af-262">See what you can learn from the following Microsoft Threat Protection interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="708af-263">Em seguida, você pode simular um ataque e ver como os recursos de produtos cruzam detectar, criar alertas e responder automaticamente a um ataque sem arquivo em um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="708af-263">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="708af-264">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="708af-264">Next step</span></span>
|<span data-ttu-id="708af-265">![Fase de simulação de ataque](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="708af-265">![Attack simulation phase](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="708af-266">Fase de simulação de ataque</span><span class="sxs-lookup"><span data-stu-id="708af-266">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="708af-267">Execute a simulação de ataque para seu ambiente piloto de proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="708af-267">Run the attack simulation for your Microsoft Threat Protection pilot environment.</span></span>
|:-------|:-----|
