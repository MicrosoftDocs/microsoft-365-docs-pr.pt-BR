---
title: Configurar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft
description: Acessar o centro de segurança do Microsoft 365 e configurar seu ambiente de laboratório de avaliação do Microsoft Threat Protection
keywords: Configuração de avaliação do Microsoft Threat Protection, experimente a proteção contra ameaças da Microsoft, configuração do laboratório de avaliação de proteção contra ameaças da Microsoft
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
ms.openlocfilehash: 69a883263952b7c20225659ae023399e0242606d
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650064"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="b4e20-104">Configurar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b4e20-104">Set up your Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="b4e20-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b4e20-105">**Applies to:**</span></span>
- <span data-ttu-id="b4e20-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b4e20-106">Microsoft Threat Protection</span></span> 


<span data-ttu-id="b4e20-107">Criar um ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft e implantá-lo é um processo de três fases:</span><span class="sxs-lookup"><span data-stu-id="b4e20-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Prepare seu laboratório de avaliação de proteção contra ameaças da Microsoft" />
      <br/><span data-ttu-id="b4e20-109">Fase 1: preparar </a></span><span class="sxs-lookup"><span data-stu-id="b4e20-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Configurar o laboratório de avaliação de proteção contra ameaças da Microsoft" />
      <br/><span data-ttu-id="b4e20-111">Fase 2: configuração </a></span><span class="sxs-lookup"><span data-stu-id="b4e20-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Configure cada pilar de proteção contra ameaças da Microsoft para seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft e integração dos seus pontos de extremidade" />
      <br/><span data-ttu-id="b4e20-113">Fase 3: configurar o & integrado </a></span><span class="sxs-lookup"><span data-stu-id="b4e20-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="b4e20-114">Você está atualmente na fase de configuração.</span><span class="sxs-lookup"><span data-stu-id="b4e20-114">You are currently in the set up phase.</span></span> <span data-ttu-id="b4e20-115">Execute as etapas iniciais para acessar o centro de segurança do Microsoft 365 e configure seu ambiente de laboratório de avaliação.</span><span class="sxs-lookup"><span data-stu-id="b4e20-115">Take the initial steps to access Microsoft 365 Security Center then setup your trial lab environment.</span></span>

<span data-ttu-id="b4e20-116">Inscreva-se para uma assinatura do Office 365 ou do Azure Active Directory para gerar um locatário *. onmicrosoft.com* que você pode usar para se inscrever na sua licença do Microsoft 365 e5.</span><span class="sxs-lookup"><span data-stu-id="b4e20-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="b4e20-117">Se você já tiver uma assinatura existente do Office 365 ou do Azure Active Directory, poderá ignorar as etapas de criação do locatário de avaliação do Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="b4e20-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

<span data-ttu-id="b4e20-118">Nesta fase, você será orientado a:</span><span class="sxs-lookup"><span data-stu-id="b4e20-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="b4e20-119">Criar um locatário de avaliação do Office 365 e5</span><span class="sxs-lookup"><span data-stu-id="b4e20-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="b4e20-120">Habilitar a assinatura de avaliação do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b4e20-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="b4e20-121">Criar um locatário de avaliação do Office 365 e5</span><span class="sxs-lookup"><span data-stu-id="b4e20-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="b4e20-122">Se você já tiver uma assinatura existente do Office 365 ou do Azure Active Directory, poderá ignorar as etapas de criação do locatário de avaliação do Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="b4e20-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="b4e20-123">Vá para o [portal de produto do Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) e selecione **avaliação gratuita**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>
<span data-ttu-id="b4e20-124">![Página de avaliação gratuita de imagem of_Office 365 e5](../../media/mtp-eval-9.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-124">![Image of_Office 365 E5 free trial page](../../media/mtp-eval-9.png)</span></span> <br>
  
2. <span data-ttu-id="b4e20-125">Conclua o registro de avaliação inserindo seu endereço de email (pessoal ou corporativo).</span><span class="sxs-lookup"><span data-stu-id="b4e20-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="b4e20-126">Clique em **configurar conta**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-126">Click **Set up account**.</span></span>
<span data-ttu-id="b4e20-127">![Página de configuração de registro de avaliação 365 E5 de imagem of_Office](../../media/mtp-eval-10.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-127">![Image of_Office 365 E5 trial registration setup page](../../media/mtp-eval-10.png)</span></span> <br> 

3. <span data-ttu-id="b4e20-128">Preencha seu nome, sobrenome, número de telefone comercial, nome da empresa, tamanho da empresa e país ou região.</span><span class="sxs-lookup"><span data-stu-id="b4e20-128">Fill in your first name, last name, business phone number, company name, company size and country or region.</span></span>  
<br>![Imagem of_Office 365 E5 página de configuração de registro de avaliação para solicitar o nome, telefone e detalhes da empresa](../../media/mtp-eval-11.png) <br>
>[!NOTE]
><span data-ttu-id="b4e20-130">O país ou a região definida aqui determina a região do Data Center em que o Office 365 será hospedado.</span><span class="sxs-lookup"><span data-stu-id="b4e20-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="b4e20-131">Escolha sua preferência de verificação: por meio de uma mensagem de texto ou chamada.</span><span class="sxs-lookup"><span data-stu-id="b4e20-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="b4e20-132">Clique em **enviar código de verificação**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-132">Click **Send Verification Code**.</span></span> 
<span data-ttu-id="b4e20-133">![Imagem of_Office 365 E5 página de configuração de registro de avaliação solicitando preferência de verificação](../../media/mtp-eval-12.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-133">![Image of_Office 365 E5 trial registration setup page asking for verification preference](../../media/mtp-eval-12.png)</span></span> <br>

5. <span data-ttu-id="b4e20-134">Defina o nome de domínio personalizado para o seu locatário e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-134">Set the custom domain name for your tenant, then click **Next**.</span></span>
<br><span data-ttu-id="b4e20-135">![Imagem of_Office 365 E5 página de configuração de registro de avaliação, onde você pode configurar seu nome de domínio personalizado](../../media/mtp-eval-13.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-135">![Image of_Office 365 E5 trial registration setup page where you can set up your custom domain name](../../media/mtp-eval-13.png)</span></span> <br>
 
6. <span data-ttu-id="b4e20-136">Configure a primeira identidade que será um administrador global do locatário.</span><span class="sxs-lookup"><span data-stu-id="b4e20-136">Set up the first identity which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="b4e20-137">Insira o **nome** e a **senha**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="b4e20-138">Clique em **inscrever-se**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-138">Click **Sign up**.</span></span>
<span data-ttu-id="b4e20-139">![Imagem of_Office 365 E5 página de configuração de registro de avaliação, onde você pode definir sua identidade comercial](../../media/mtp-eval-14.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-139">![Image of_Office 365 E5 trial registration setup page where you can set your business identity](../../media/mtp-eval-14.png)</span></span> <br>

7. <span data-ttu-id="b4e20-140">Clique em **ir para configuração** para concluir o provisionamento do locatário de avaliação do Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="b4e20-140">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>
<br><span data-ttu-id="b4e20-141">![Imagem da página de configuração do registro de avaliação do Office 365 E5 solicitando o clique no botão configuração do Go](../../media/mtp-eval-15.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-141">![Image of Office 365 E5 trial registration setup page prompting to click Go Setup button](../../media/mtp-eval-15.png)</span></span> <br>

8. <span data-ttu-id="b4e20-142">Conecte seu domínio corporativo ao locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4e20-142">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="b4e20-143">Opcion Escolha **conectar um domínio que você já possui** e digite o nome do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="b4e20-143">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="b4e20-144">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-144">Click **Next**.</span></span>
<br><span data-ttu-id="b4e20-145">![Página de configuração de imagem of_Office 365 E5 onde você deve personalizar sua entrada e email](../../media/mtp-eval-16.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-145">![Image of_Office 365 E5 Setup page where you should personalize your sign-in and email](../../media/mtp-eval-16.png)</span></span> <br>
 
9. <span data-ttu-id="b4e20-146">Será necessário adicionar um registro TXT ou MX para validar a propriedade do domínio.</span><span class="sxs-lookup"><span data-stu-id="b4e20-146">You will need to add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="b4e20-147">Depois de adicionar o registro TXT ou MX ao seu domínio, selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-147">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>
<br><span data-ttu-id="b4e20-148">![Página de imagem of_Office 365 E5 onde você deve adicionar um TXT do registro MX para verificar seu domínio](../../media/mtp-eval-17.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-148">![Image of_Office 365 E5 setup page where you should add a TXT of MX record to verify your domain](../../media/mtp-eval-17.png)</span></span> <br>
 
10. <span data-ttu-id="b4e20-149">Opcion Criar mais contas de usuário para o locatário.</span><span class="sxs-lookup"><span data-stu-id="b4e20-149">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="b4e20-150">Você pode ignorar essa etapa clicando em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-150">You can skip this step by clicking **Next**.</span></span>
<span data-ttu-id="b4e20-151">![Página de configuração de imagem of_Office 365 E5 onde você pode adicionar mais usuários](../../media/mtp-eval-18.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-151">![Image of_Office 365 E5 setup page where you can add more users](../../media/mtp-eval-18.png)</span></span> <br>
 
11. <span data-ttu-id="b4e20-152">Opcion Baixar aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="b4e20-152">[Optional] Download Office apps.</span></span> <span data-ttu-id="b4e20-153">Clique em **Avançar** para ignorar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="b4e20-153">Click **Next** to skip this step.</span></span> 
<br><span data-ttu-id="b4e20-154">![Página de imagem of_Office 365 E5 onde você pode instalar seus aplicativos do Office](../../media/mtp-eval-19.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-154">![Image of_Office 365 E5 page where you can install your Office apps](../../media/mtp-eval-19.png)</span></span> <br>

12. <span data-ttu-id="b4e20-155">Opcion Migrar mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="b4e20-155">[Optional] Migrate email messages.</span></span> <span data-ttu-id="b4e20-156">Novamente, você pode ignorar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="b4e20-156">Again, you can skip this step.</span></span>
<br><span data-ttu-id="b4e20-157">![Image of_Office 365 E5 onde você pode definir se deseja migrar mensagens de email ou não](../../media/mtp-eval-20.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-157">![Image of_Office 365 E5 where you can set whether to migrate email messages or not](../../media/mtp-eval-20.png)</span></span> <br>
 
13. <span data-ttu-id="b4e20-158">Escolha serviços online.</span><span class="sxs-lookup"><span data-stu-id="b4e20-158">Choose online services.</span></span> <span data-ttu-id="b4e20-159">Selecione **Exchange** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-159">Select **Exchange** and click **Next**.</span></span> 
<br><span data-ttu-id="b4e20-160">![Imagem of_Office 365 E5 onde você pode escolher seus serviços online](../../media/mtp-eval-21.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-160">![Image of_Office 365 E5 where you can choose your online services](../../media/mtp-eval-21.png)</span></span> <br>

14. <span data-ttu-id="b4e20-161">Adicione registros MX, CNAME e TXT ao seu domínio.</span><span class="sxs-lookup"><span data-stu-id="b4e20-161">Add MX, CNAME and TXT records to your domain.</span></span> <span data-ttu-id="b4e20-162">Quando concluído, selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-162">When completed, select **Verify**.</span></span>
<br><span data-ttu-id="b4e20-163">![Imagem of_Office 365 E5 aqui você pode adicionar seus registros DNS](../../media/mtp-eval-22.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-163">![Image of_Office 365 E5 here you can add your DNS records](../../media/mtp-eval-22.png)</span></span> <br>
 
15. <span data-ttu-id="b4e20-164">Parabéns, você concluiu o provisionamento do seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4e20-164">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>
<br><span data-ttu-id="b4e20-165">![Página de confirmação de conclusão da instalação da of_Office 365 e5](../../media/mtp-eval-23.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-165">![Image of_Office 365 E5 setup completion confirmation page](../../media/mtp-eval-23.png)</span></span> <br>

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="b4e20-166">Habilitar a assinatura de avaliação do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b4e20-166">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="b4e20-167">Inscrever-se em uma avaliação oferece 25 licenças de usuário para usar por mês.</span><span class="sxs-lookup"><span data-stu-id="b4e20-167">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="b4e20-168">Consulte [tentar ou comprar uma assinatura do M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="b4e20-168">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="b4e20-169">No [centro de administração do Microsoft 365](https://admin.microsoft.com/), clique em **cobrança** e navegue até **serviços de compra**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-169">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="b4e20-170">Selecione **Microsoft 365 E5** e clique em **Iniciar avaliação gratuita**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-170">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 
<span data-ttu-id="b4e20-171">![Imagem of_Microsoft 365 E5 iniciar página de avaliação gratuita](../../media/mtp-eval-24.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-171">![Image of_Microsoft 365 E5 Start free trial page](../../media/mtp-eval-24.png)</span></span> <br>

3. <span data-ttu-id="b4e20-172">Escolha sua preferência de verificação: por meio de uma mensagem de texto ou chamada.</span><span class="sxs-lookup"><span data-stu-id="b4e20-172">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="b4e20-173">Depois de decidir, insira o número de telefone, selecione o **texto me** ou **telefonar para mim** , dependendo da seleção.</span><span class="sxs-lookup"><span data-stu-id="b4e20-173">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>
<span data-ttu-id="b4e20-174">![Imagem of_Microsoft 365 E5 iniciar página de avaliação gratuita solicitando detalhes do contato para enviar código para provar que você não é um robô](../../media/mtp-eval-25.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-174">![Image of_Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot](../../media/mtp-eval-25.png)</span></span> <br>
 
4. <span data-ttu-id="b4e20-175">Insira o código de verificação e clique em **iniciar sua avaliação gratuita**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-175">Enter the verification code and click **Start your free trial**.</span></span> 
<br><span data-ttu-id="b4e20-176">![Imagem of_Microsoft 365 E5 iniciar página de avaliação gratuita onde você pode preencher o código de verificação o sistema enviado para provar que você não é um robô](../../media/mtp-eval-26.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-176">![Image of_Microsoft 365 E5 Start free trial page where you can fill out verification code the system sent to prove you are not a robot](../../media/mtp-eval-26.png)</span></span> <br>

5. <span data-ttu-id="b4e20-177">Clique em **tentar agora** para confirmar sua avaliação do Microsoft 365 e5.</span><span class="sxs-lookup"><span data-stu-id="b4e20-177">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>
<br><span data-ttu-id="b4e20-178">![Imagem of_Microsoft 365 E5 iniciar página de avaliação gratuita onde você deve registrar o botão experimentar agora para iniciar](../../media/mtp-eval-27.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-178">![Image of_Microsoft 365 E5 Start free trial page where you should clock the Try now button to start](../../media/mtp-eval-27.png)</span></span> <br>
 
6. <span data-ttu-id="b4e20-179">Vá para o **centro de administração do Microsoft 365**  >  **usuários**  >  **ativos**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-179">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="b4e20-180">Selecione sua conta de usuário, selecione **gerenciar licenças de produto**e troque a licença do Office 365 E5 para a **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-180">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="b4e20-181">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-181">Click **Save**.</span></span>
<span data-ttu-id="b4e20-182">![Imagem of_Microsoft 365 página de centro de administração onde você pode selecionar a licença do Microsoft 365 e5](../../media/mtp-eval-28.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-182">![Image of_Microsoft 365 Admin Center page where you can select Microsoft 365 E5 license](../../media/mtp-eval-28.png)</span></span> <br>
 
7. <span data-ttu-id="b4e20-183">Selecione a conta de administrador global novamente e, em seguida, clique em **gerenciar nome de usuário**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-183">Select the global administrator account again then click **Manage username**.</span></span>
<br><span data-ttu-id="b4e20-184">![Imagem of_Microsoft 365 página de centro de administração onde você pode selecionar Account e gerenciar username](../../media/mtp-eval-29.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-184">![Image of_Microsoft 365 Admin Center page where you can select Account and then Manage username](../../media/mtp-eval-29.png)</span></span> <br>

8. <span data-ttu-id="b4e20-185">Opcion Altere o domínio de *onmicrosoft.com* para seu próprio domínio, dependendo do que você escolheu nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="b4e20-185">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="b4e20-186">Clique em **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="b4e20-186">Click **Save changes**.</span></span>
<br><span data-ttu-id="b4e20-187">![Imagem of_Microsoft 365 página de centro de administração onde você pode alterar sua preferência de domínio](../../media/mtp-eval-30.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-187">![Image of_Microsoft 365 Admin Center page where you can change your domain preference](../../media/mtp-eval-30.png)</span></span> <br>



## <a name="next-step"></a><span data-ttu-id="b4e20-188">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="b4e20-188">Next step</span></span>
<span data-ttu-id="b4e20-189">![Fase 3: configurar o & integrado](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="b4e20-189">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="b4e20-190">Fase 3: configurar o & integrado</span><span class="sxs-lookup"><span data-stu-id="b4e20-190">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) <br><span data-ttu-id="b4e20-191">Configure cada pilar de proteção contra ameaças da Microsoft para o laboratório de avaliação de proteção contra ameaças da Microsoft e integração dos seus pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="b4e20-191">Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection evaluation lab and onboard your endpoints.</span></span>
