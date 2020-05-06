---
title: Configurar os pilares de proteção contra ameaças da Microsoft para o ambiente de laboratório de avaliação
description: Configurar os pilares de proteção contra ameaças da Microsoft, o Office 365 ATP, o Azure ATP, o Microsoft Cloud app Security e o Microsoft defender ATP para seu ambiente de laboratório de avaliação
keywords: configurar a avaliação de proteção contra ameaças da Microsoft, configuração de avaliação de proteção contra ameaças da Microsoft, configurar os pilares de proteção contra ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 68d8f06803d75c3f89cae6fa7998734fd54084ca
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049504"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-environment"></a><span data-ttu-id="4b967-104">Configurar os pilares de proteção contra ameaças da Microsoft para seu ambiente de laboratório de avaliação</span><span class="sxs-lookup"><span data-stu-id="4b967-104">Configure Microsoft Threat Protection pillars for your trial lab environment</span></span>

<span data-ttu-id="4b967-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4b967-105">**Applies to:**</span></span>
- <span data-ttu-id="4b967-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="4b967-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="4b967-107">Criar um ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft e implantá-lo é um processo de três fases:</span><span class="sxs-lookup"><span data-stu-id="4b967-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Preparar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft" />
      <br/><span data-ttu-id="4b967-109">Fase 1: preparar</a></span><span class="sxs-lookup"><span data-stu-id="4b967-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Configurar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft" />
      <br/><span data-ttu-id="4b967-111">Fase 2: configuração</a></span><span class="sxs-lookup"><span data-stu-id="4b967-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Configurar cada pilar de proteção contra ameaças da Microsoft para seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft e pontos de extremidade integrados" />
      <br/><span data-ttu-id="4b967-113">Fase 3: configurar o & integrado</a></span><span class="sxs-lookup"><span data-stu-id="4b967-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="4b967-114">No momento, você está na fase de configuração.</span><span class="sxs-lookup"><span data-stu-id="4b967-114">You are currently in the configuration phase.</span></span>


<span data-ttu-id="4b967-115">A preparação é fundamental para qualquer implantação bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="4b967-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="4b967-116">Neste artigo, você será orientado nos pontos que precisará considerar ao se preparar para implantar o Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="4b967-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="4b967-117">Pilares de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="4b967-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="4b967-118">A proteção contra ameaças da Microsoft consiste em quatro pilares.</span><span class="sxs-lookup"><span data-stu-id="4b967-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="4b967-119">Embora um pilar já possa fornecer um valor para a segurança da sua organização de rede, a habilitação dos quatro pilares de proteção contra ameaças da Microsoft dará à sua organização o mais valor.</span><span class="sxs-lookup"><span data-stu-id="4b967-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![Of_page de imagem](../../media/mtp-eval-31.png) <br>

<span data-ttu-id="4b967-121">Esta seção orientará você a configurar:</span><span class="sxs-lookup"><span data-stu-id="4b967-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="4b967-122">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="4b967-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="4b967-123">Proteção Avançada contra Ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="4b967-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="4b967-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4b967-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="4b967-125">Proteção avançada contra ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4b967-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="4b967-126">Configurar a proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="4b967-126">Configure Office 365 Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="4b967-127">Pule esta etapa se já tiver habilitado a proteção avançada contra ameaças do Office 365.</span><span class="sxs-lookup"><span data-stu-id="4b967-127">Skip this step if you have already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="4b967-128">Há um módulo do PowerShell chamado *Office 365 Advanced Threat Protection Configuration Analyzer (orca)* que ajuda a determinar algumas dessas configurações.</span><span class="sxs-lookup"><span data-stu-id="4b967-128">There is a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="4b967-129">Ao executar como um administrador em seu locatário, o Get-ORCAReport ajudará a gerar uma avaliação das configurações de higiene de antispam, anti-phishing e outras mensagens.</span><span class="sxs-lookup"><span data-stu-id="4b967-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="4b967-130">Você pode baixar este módulo no https://www.powershellgallery.com/packages/ORCA/.</span><span class="sxs-lookup"><span data-stu-id="4b967-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="4b967-131">Navegue até a**política**de**Gerenciamento** > de ameaças do centro > de [conformidade & segurança do Office 365](https://protection.office.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="4b967-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>
<span data-ttu-id="4b967-132">![Of_page de imagem](../../media/mtp-eval-32.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-132">![Image of_page](../../media/mtp-eval-32.png)</span></span> <br>
 
2. <span data-ttu-id="4b967-133">Clique em **anti-phishing ATP**, selecione **criar** e preencha o nome e a descrição da política.</span><span class="sxs-lookup"><span data-stu-id="4b967-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="4b967-134">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4b967-134">Click **Next**.</span></span>
<span data-ttu-id="4b967-135">![Of_page de imagem](../../media/mtp-eval-33.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-135">![Image of_page](../../media/mtp-eval-33.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="4b967-136">Edite a política de anti-phishing avançada da ATP.</span><span class="sxs-lookup"><span data-stu-id="4b967-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="4b967-137">Altere o **limite de phishing avançado** para **2-agressivo**.</span><span class="sxs-lookup"><span data-stu-id="4b967-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>
<br>

3. <span data-ttu-id="4b967-138">Clique no menu suspenso **Adicionar uma condição** e selecione seu (s) domínio (s) como domínio do destinatário.</span><span class="sxs-lookup"><span data-stu-id="4b967-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="4b967-139">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4b967-139">Click **Next**.</span></span>
<span data-ttu-id="4b967-140">![Of_page de imagem](../../media/mtp-eval-34.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-140">![Image of_page](../../media/mtp-eval-34.png)</span></span> <br>
 
4. <span data-ttu-id="4b967-141">Revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="4b967-141">Review your settings.</span></span> <span data-ttu-id="4b967-142">Clique em **criar esta política** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="4b967-142">Click **Create this policy** to confirm.</span></span> 
<span data-ttu-id="4b967-143">![Of_page de imagem](../../media/mtp-eval-35.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-143">![Image of_page](../../media/mtp-eval-35.png)</span></span> <br>
 
5. <span data-ttu-id="4b967-144">Selecione **anexos seguros de ATP** e selecione a opção **Ativar ATP para SharePoint, onedrive e Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="4b967-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>  
<span data-ttu-id="4b967-145">![Of_page de imagem](../../media/mtp-eval-36.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-145">![Image of_page](../../media/mtp-eval-36.png)</span></span> <br>

6. <span data-ttu-id="4b967-146">Clique no ícone + para criar uma nova política de anexo seguro, aplique-a como domínio de destinatário aos seus domínios.</span><span class="sxs-lookup"><span data-stu-id="4b967-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="4b967-147">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4b967-147">Click **Save**.</span></span>
<span data-ttu-id="4b967-148">![Of_page de imagem](../../media/mtp-eval-37.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-148">![Image of_page](../../media/mtp-eval-37.png)</span></span> <br>
 
7. <span data-ttu-id="4b967-149">Em seguida, selecione a política de **links seguros de ATP** e clique no ícone de lápis para editar a política padrão.</span><span class="sxs-lookup"><span data-stu-id="4b967-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="4b967-150">Certifique-se de que a opção **não rastrear quando os usuários clicarem em links seguros** não esteja selecionada, enquanto o restante das opções estiver selecionado.</span><span class="sxs-lookup"><span data-stu-id="4b967-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="4b967-151">Confira [configurações de links seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="4b967-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) for details.</span></span> <span data-ttu-id="4b967-152">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4b967-152">Click **Save**.</span></span> 
<span data-ttu-id="4b967-153">![Of_page de imagem](../../media/mtp-eval-38.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-153">![Image of_page](../../media/mtp-eval-38.png)</span></span> <br>

9. <span data-ttu-id="4b967-154">Em seguida, selecione a política **anti-malware** , selecione o padrão e escolha o ícone de lápis.</span><span class="sxs-lookup"><span data-stu-id="4b967-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="4b967-155">Clique em **configurações** e selecione **Sim e use o texto de notificação padrão** para habilitar a **resposta de detecção de malware**.</span><span class="sxs-lookup"><span data-stu-id="4b967-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="4b967-156">Ativar o **filtro de tipos de anexo comuns** .</span><span class="sxs-lookup"><span data-stu-id="4b967-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="4b967-157">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4b967-157">Click **Save**.</span></span>
<br><span data-ttu-id="4b967-158">![Of_page de imagem](../../media/mtp-eval-39.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-158">![Image of_page](../../media/mtp-eval-39.png)</span></span> <br>
  
11. <span data-ttu-id="4b967-159">Navegue até [Office 365 Security & centro](https://protection.office.com/homepage) > de conformidade**pesquisa** > **log de auditoria** pesquisa e ative a auditoria.</span><span class="sxs-lookup"><span data-stu-id="4b967-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>  
<span data-ttu-id="4b967-160">![Of_page de imagem](../../media/mtp-eval-40.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-160">![Image of_page](../../media/mtp-eval-40.png)</span></span> <br>

12. <span data-ttu-id="4b967-161">Integrar o Office 365 ATP com o Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="4b967-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="4b967-162">Navegue até [Office 365 Security & centro de conformidade](https://protection.office.com/homepage)de > **Gerenciamento** > **de** ameaças do centro de conformidade e selecione **configurações do WDATP** no canto superior direito da tela.</span><span class="sxs-lookup"><span data-stu-id="4b967-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="4b967-163">Na caixa de diálogo conexão ATP do Microsoft defender, ative **conectar ao Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="4b967-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>
<span data-ttu-id="4b967-164">![Of_page de imagem](../../media/mtp-eval-41.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-164">![Image of_page](../../media/mtp-eval-41.png)</span></span> <br>

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="4b967-165">Configurar a proteção avançada contra ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="4b967-165">Configure Azure Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="4b967-166">Pule esta etapa se você já tiver habilitado a proteção avançada contra ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="4b967-166">Skip this step if you have already enabled Azure Advanced Threat Protection</span></span>


1. <span data-ttu-id="4b967-167">Navegue até a [central de segurança do Microsoft 365](https://security.microsoft.com/info) > selecione **mais recursos** > **proteção avançada contra ameaças do Azure**.</span><span class="sxs-lookup"><span data-stu-id="4b967-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>
<span data-ttu-id="4b967-168">![Of_page de imagem](../../media/mtp-eval-42.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-168">![Image of_page](../../media/mtp-eval-42.png)</span></span> <br>

2. <span data-ttu-id="4b967-169">Clique em **criar** para iniciar o assistente de proteção avançada contra ameaças do Azure.</span><span class="sxs-lookup"><span data-stu-id="4b967-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 
<br><span data-ttu-id="4b967-170">![Of_page de imagem](../../media/mtp-eval-43.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-170">![Image of_page](../../media/mtp-eval-43.png)</span></span> <br>

3. <span data-ttu-id="4b967-171">Escolha **fornecer um nome de usuário e senha para se conectar à sua floresta do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="4b967-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  
<span data-ttu-id="4b967-172">![Of_page de imagem](../../media/mtp-eval-44.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-172">![Image of_page](../../media/mtp-eval-44.png)</span></span> <br>

4. <span data-ttu-id="4b967-173">Insira suas credenciais locais do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4b967-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="4b967-174">Pode ser qualquer conta de usuário que tenha acesso de leitura ao Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4b967-174">This can be any user account that has read access to Active Directory.</span></span>
<span data-ttu-id="4b967-175">![Of_page de imagem](../../media/mtp-eval-45.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-175">![Image of_page](../../media/mtp-eval-45.png)</span></span> <br>

5. <span data-ttu-id="4b967-176">Em seguida, escolha **baixar a configuração do sensor** e transferir o arquivo para o controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="4b967-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span> 
<span data-ttu-id="4b967-177">![Of_page de imagem](../../media/mtp-eval-46.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-177">![Image of_page](../../media/mtp-eval-46.png)</span></span> <br>

6. <span data-ttu-id="4b967-178">Execute a configuração do sensor ATP do Azure e comece seguindo o assistente.</span><span class="sxs-lookup"><span data-stu-id="4b967-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>
<br><span data-ttu-id="4b967-179">![Of_page de imagem](../../media/mtp-eval-47.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-179">![Image of_page](../../media/mtp-eval-47.png)</span></span> <br>
 
7. <span data-ttu-id="4b967-180">Clique em **Avançar** no tipo de implantação do sensor.</span><span class="sxs-lookup"><span data-stu-id="4b967-180">Click **Next** at the sensor deployment type.</span></span>
<br><span data-ttu-id="4b967-181">![Of_page de imagem](../../media/mtp-eval-48.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-181">![Image of_page](../../media/mtp-eval-48.png)</span></span> <br>
 
8. <span data-ttu-id="4b967-182">Copie a chave de acesso, pois será necessário inseri-la em seguida no assistente.</span><span class="sxs-lookup"><span data-stu-id="4b967-182">Copy the access key as you will need to enter it next in the Wizard.</span></span>
<span data-ttu-id="4b967-183">![Of_page de imagem](../../media/mtp-eval-49.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-183">![Image of_page](../../media/mtp-eval-49.png)</span></span> <br>
 
9. <span data-ttu-id="4b967-184">Copie a chave de acesso no assistente e clique em **instalar**.</span><span class="sxs-lookup"><span data-stu-id="4b967-184">Copy the access key into the Wizard and click **Install**.</span></span> 
<br><span data-ttu-id="4b967-185">![Of_page de imagem](../../media/mtp-eval-50.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-185">![Image of_page](../../media/mtp-eval-50.png)</span></span> <br>

10. <span data-ttu-id="4b967-186">Parabéns, você configurou com êxito a proteção avançada contra ameaças do Azure no seu controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="4b967-186">Congratulations, you have successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>
<span data-ttu-id="4b967-187">![Of_page de imagem](../../media/mtp-eval-51.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-187">![Image of_page](../../media/mtp-eval-51.png)</span></span> <br>
 
11. <span data-ttu-id="4b967-188">Na seção Configurações de [ATP do Azure Azure](https://go.microsoft.com/fwlink/?linkid=2040449) , selecione **Windows Defender ATP**e ative a opção de ativar.</span><span class="sxs-lookup"><span data-stu-id="4b967-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn the toggle on.</span></span> <span data-ttu-id="4b967-189">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4b967-189">Click **Save**.</span></span> 
<span data-ttu-id="4b967-190">![Of_page de imagem](../../media/mtp-eval-52.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-190">![Image of_page](../../media/mtp-eval-52.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="4b967-191">O Windows Defender ATP foi remarcado como Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="4b967-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="4b967-192">As alterações de remarcação em todos os nossos portais estão sendo distribuídas para consistência.</span><span class="sxs-lookup"><span data-stu-id="4b967-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="4b967-193">Configurar o Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="4b967-193">Configure Microsoft Cloud App Security</span></span>
>[!NOTE]
><span data-ttu-id="4b967-194">Pule esta etapa se você já tiver habilitado o Microsoft Cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="4b967-194">Skip this step if you have already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="4b967-195">Navegue até [Microsoft 365 Security Center](https://security.microsoft.com/info) > **mais recursos** > **Microsoft Cloud app Security**.</span><span class="sxs-lookup"><span data-stu-id="4b967-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>
<span data-ttu-id="4b967-196">![Of_page de imagem](../../media/mtp-eval-53.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-196">![Image of_page](../../media/mtp-eval-53.png)</span></span> <br>

2. <span data-ttu-id="4b967-197">No prompt de informações para integrar o Azure ATP, selecione **habilitar a integração de dados ATP do Azure**.</span><span class="sxs-lookup"><span data-stu-id="4b967-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span> 
<br><span data-ttu-id="4b967-198">![Of_page de imagem](../../media/mtp-eval-54.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-198">![Image of_page](../../media/mtp-eval-54.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="4b967-199">Se você não vir esse prompt, pode significar que sua integração de dados ATP do Azure já foi habilitada.</span><span class="sxs-lookup"><span data-stu-id="4b967-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="4b967-200">No entanto, se você não tiver certeza, entre em contato com seu administrador de ti para confirmar.</span><span class="sxs-lookup"><span data-stu-id="4b967-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="4b967-201">Vá para **configurações**, ative a ativação da **integração do Azure ATP** e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="4b967-201">Go to **Settings**, turn the **Azure ATP integration** toggle on, then click **Save**.</span></span> 
<span data-ttu-id="4b967-202">![Of_page de imagem](../../media/mtp-eval-55.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-202">![Image of_page](../../media/mtp-eval-55.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="4b967-203">Para novas instâncias ATP do Azure, esta integração alternada é automaticamente ativada.</span><span class="sxs-lookup"><span data-stu-id="4b967-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="4b967-204">Confirme se a sua integração do Azure ATP foi habilitada antes de prosseguir para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="4b967-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="4b967-205">Nas configurações de descoberta de nuvem, selecione **integração do Microsoft defender ATP**e habilite a integração.</span><span class="sxs-lookup"><span data-stu-id="4b967-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="4b967-206">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4b967-206">Click **Save**.</span></span>
<span data-ttu-id="4b967-207">![Of_page de imagem](../../media/mtp-eval-56.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-207">![Image of_page](../../media/mtp-eval-56.png)</span></span> <br>

5. <span data-ttu-id="4b967-208">Em configurações de descoberta de nuvem, selecione o **enriquecimento do usuário**e habilite a integração com o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4b967-208">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>
<span data-ttu-id="4b967-209">![Of_page de imagem](../../media/mtp-eval-57.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-209">![Image of_page](../../media/mtp-eval-57.png)</span></span> <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="4b967-210">Configurar a proteção avançada contra ameaças do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="4b967-210">Configure Microsoft Defender Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="4b967-211">Pule esta etapa se você já tiver habilitado a proteção avançada contra ameaças do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="4b967-211">Skip this step if you have already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="4b967-212">Navegue até a central de [segurança](https://security.microsoft.com/info) > da Microsoft 365**mais recursos** > **central de segurança do Microsoft defender**.</span><span class="sxs-lookup"><span data-stu-id="4b967-212">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="4b967-213">Clique em **Abrir**. </span><span class="sxs-lookup"><span data-stu-id="4b967-213">Click **Open**.</span></span>
<br><span data-ttu-id="4b967-214">![Of_page de imagem](../../media/mtp-eval-58.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-214">![Image of_page](../../media/mtp-eval-58.png)</span></span> <br>
 
2. <span data-ttu-id="4b967-215">Siga o assistente de proteção avançada contra ameaças do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="4b967-215">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="4b967-216">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4b967-216">Click **Next**.</span></span> 
<br><span data-ttu-id="4b967-217">![Of_page de imagem](../../media/mtp-eval-59.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-217">![Image of_page](../../media/mtp-eval-59.png)</span></span> <br>

3. <span data-ttu-id="4b967-218">Escolha com base em seu local de armazenamento de dados preferido, política de retenção de dados, tamanho da organização e consentimento para recursos de visualização.</span><span class="sxs-lookup"><span data-stu-id="4b967-218">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span> 
<br><span data-ttu-id="4b967-219">![Of_page de imagem](../../media/mtp-eval-60.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-219">![Image of_page](../../media/mtp-eval-60.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="4b967-220">Você não pode alterar algumas das configurações, como o local de armazenamento de dados, posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4b967-220">You cannot change some of the settings, like data storage location, afterwards.</span></span> 
<br>

<span data-ttu-id="4b967-221">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4b967-221">Click **Next**.</span></span> 

4. <span data-ttu-id="4b967-222">Clique em **continuar** e ele provisionrá o locatário do Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="4b967-222">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>
<br><span data-ttu-id="4b967-223">![Of_page de imagem](../../media/mtp-eval-61.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-223">![Image of_page](../../media/mtp-eval-61.png)</span></span> <br>

5. <span data-ttu-id="4b967-224">Integração dos pontos de extremidade por meio de políticas de grupo, Microsoft Endpoint Manager ou executando um script local para o Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="4b967-224">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="4b967-225">Para simplificar, este guia usa o script local.</span><span class="sxs-lookup"><span data-stu-id="4b967-225">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="4b967-226">Clique em **baixar pacote** e copie o script de integração para seus pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="4b967-226">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>  
<br><span data-ttu-id="4b967-227">![Of_page de imagem](../../media/mtp-eval-62.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-227">![Image of_page](../../media/mtp-eval-62.png)</span></span> <br>

7. <span data-ttu-id="4b967-228">No ponto de extremidade, execute o script de integração como administrador e escolha Y.</span><span class="sxs-lookup"><span data-stu-id="4b967-228">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>
<br><span data-ttu-id="4b967-229">![Of_page de imagem](../../media/mtp-eval-63.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-229">![Image of_page](../../media/mtp-eval-63.png)</span></span> <br>

8. <span data-ttu-id="4b967-230">Parabéns, você terá integrado seu primeiro ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="4b967-230">Congratulations, you have onboarded your first endpoint.</span></span>  
<br>![Of_page de imagem](../../media/mtp-eval-64.png) <br>

9. <span data-ttu-id="4b967-232">Copie-cole o teste de detecção do assistente do Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="4b967-232">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>
<br><span data-ttu-id="4b967-233">![Of_page de imagem](../../media/mtp-eval-65.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-233">![Image of_page](../../media/mtp-eval-65.png)</span></span> <br>

10. <span data-ttu-id="4b967-234">Copie o script do PowerShell para um prompt de comando com privilégios elevados e execute-o.</span><span class="sxs-lookup"><span data-stu-id="4b967-234">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 
<br><span data-ttu-id="4b967-235">![Of_page de imagem](../../media/mtp-eval-66.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-235">![Image of_page](../../media/mtp-eval-66.png)</span></span> <br>

11. <span data-ttu-id="4b967-236">Selecione **começar a usar o Microsoft defender ATP** no assistente.</span><span class="sxs-lookup"><span data-stu-id="4b967-236">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>
<br><span data-ttu-id="4b967-237">![Of_page de imagem](../../media/mtp-eval-67.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-237">![Image of_page](../../media/mtp-eval-67.png)</span></span> <br>
 
12. <span data-ttu-id="4b967-238">Visite a [central de segurança do Microsoft defender](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="4b967-238">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="4b967-239">Vá até **configurações** e selecione **recursos avançados**.</span><span class="sxs-lookup"><span data-stu-id="4b967-239">Go to **Settings** and then select **Advanced features**.</span></span> 
<br><span data-ttu-id="4b967-240">![Of_page de imagem](../../media/mtp-eval-68.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-240">![Image of_page](../../media/mtp-eval-68.png)</span></span> <br>

13. <span data-ttu-id="4b967-241">Ative a integração com a **proteção avançada contra ameaças do Azure**.</span><span class="sxs-lookup"><span data-stu-id="4b967-241">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  
<br><span data-ttu-id="4b967-242">![Of_page de imagem](../../media/mtp-eval-69.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-242">![Image of_page](../../media/mtp-eval-69.png)</span></span> <br>

14. <span data-ttu-id="4b967-243">Ative a integração com a **inteligência contra ameaças do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="4b967-243">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>
<br><span data-ttu-id="4b967-244">![Of_page de imagem](../../media/mtp-eval-70.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-244">![Image of_page](../../media/mtp-eval-70.png)</span></span> <br>

15. <span data-ttu-id="4b967-245">Ative a integração com **o Microsoft Cloud app Security**.</span><span class="sxs-lookup"><span data-stu-id="4b967-245">Turn on integration with **Microsoft Cloud App Security**.</span></span>
<br><span data-ttu-id="4b967-246">![Of_page de imagem](../../media/mtp-eval-71.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-246">![Image of_page](../../media/mtp-eval-71.png)</span></span> <br>

16. <span data-ttu-id="4b967-247">Role para baixo e clique em **salvar preferências** para confirmar as novas integrações.</span><span class="sxs-lookup"><span data-stu-id="4b967-247">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>
<br><span data-ttu-id="4b967-248">![Of_page de imagem](../../media/mtp-eval-72.png)</span><span class="sxs-lookup"><span data-stu-id="4b967-248">![Image of_page](../../media/mtp-eval-72.png)</span></span> <br>

## <a name="next-steps"></a><span data-ttu-id="4b967-249">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="4b967-249">Next steps</span></span>
<span data-ttu-id="4b967-250">[Ative a proteção contra ameaças da Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) e [gere um alerta de teste](generate-test-alert.md).</span><span class="sxs-lookup"><span data-stu-id="4b967-250">[Turn on Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) and then [generate a test alert](generate-test-alert.md).</span></span>
