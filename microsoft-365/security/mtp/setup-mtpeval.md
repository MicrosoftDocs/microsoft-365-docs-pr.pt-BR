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
ms.openlocfilehash: 50557b0824999f0220af4d12b906b0274db4471e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049610"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="b1a17-104">Configurar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b1a17-104">Set up your Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="b1a17-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b1a17-105">**Applies to:**</span></span>
- <span data-ttu-id="b1a17-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b1a17-106">Microsoft Threat Protection</span></span> 


<span data-ttu-id="b1a17-107">Criar um ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft e implantá-lo é um processo de três fases:</span><span class="sxs-lookup"><span data-stu-id="b1a17-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Prepare seu laboratório de avaliação de proteção contra ameaças da Microsoft" />
      <br/><span data-ttu-id="b1a17-109">Fase 1: preparar</a></span><span class="sxs-lookup"><span data-stu-id="b1a17-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Configurar o laboratório de avaliação de proteção contra ameaças da Microsoft" />
      <br/><span data-ttu-id="b1a17-111">Fase 2: configuração</a></span><span class="sxs-lookup"><span data-stu-id="b1a17-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Configure cada pilar de proteção contra ameaças da Microsoft para seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft e integração dos seus pontos de extremidade" />
      <br/><span data-ttu-id="b1a17-113">Fase 3: configurar o & integrado</a></span><span class="sxs-lookup"><span data-stu-id="b1a17-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="b1a17-114">Você está atualmente na fase de configuração.</span><span class="sxs-lookup"><span data-stu-id="b1a17-114">You are currently in the set up phase.</span></span> <span data-ttu-id="b1a17-115">Execute as etapas iniciais para acessar o centro de segurança do Microsoft 365 e configure seu ambiente de laboratório de avaliação.</span><span class="sxs-lookup"><span data-stu-id="b1a17-115">Take the initial steps to access Microsoft 365 Security Center then setup your trial lab environment.</span></span>

<span data-ttu-id="b1a17-116">Inscreva-se para uma assinatura do Office 365 ou do Azure Active Directory para gerar um locatário *. onmicrosoft.com* que você pode usar para se inscrever na sua licença do Microsoft 365 e5.</span><span class="sxs-lookup"><span data-stu-id="b1a17-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="b1a17-117">Se você já tiver uma assinatura existente do Office 365 ou do Azure Active Directory, poderá ignorar as etapas de criação do locatário de avaliação do Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="b1a17-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

<span data-ttu-id="b1a17-118">Nesta fase, você será orientado a:</span><span class="sxs-lookup"><span data-stu-id="b1a17-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="b1a17-119">Criar um locatário de avaliação do Office 365 e5</span><span class="sxs-lookup"><span data-stu-id="b1a17-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="b1a17-120">Habilitar a assinatura de avaliação do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b1a17-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="b1a17-121">Criar um locatário de avaliação do Office 365 e5</span><span class="sxs-lookup"><span data-stu-id="b1a17-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="b1a17-122">Se você já tiver uma assinatura existente do Office 365 ou do Azure Active Directory, poderá ignorar as etapas de criação do locatário de avaliação do Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="b1a17-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="b1a17-123">Vá para o [portal de produto do Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) e selecione **avaliação gratuita**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>
<span data-ttu-id="b1a17-124">![Of_page de imagem](../../media/mtp-eval-9.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-124">![Image of_page](../../media/mtp-eval-9.png)</span></span> <br>
  
2. <span data-ttu-id="b1a17-125">Conclua o registro de avaliação inserindo seu endereço de email (pessoal ou corporativo).</span><span class="sxs-lookup"><span data-stu-id="b1a17-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="b1a17-126">Clique em **configurar conta**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-126">Click **Set up account**.</span></span>
<span data-ttu-id="b1a17-127">![Of_page de imagem](../../media/mtp-eval-10.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-127">![Image of_page](../../media/mtp-eval-10.png)</span></span> <br> 

3. <span data-ttu-id="b1a17-128">Preencha seu nome, sobrenome, número de telefone comercial, nome da empresa, tamanho da empresa e país ou região.</span><span class="sxs-lookup"><span data-stu-id="b1a17-128">Fill in your first name, last name, business phone number, company name, company size and country or region.</span></span>  
<br>![Of_page de imagem](../../media/mtp-eval-11.png) <br>
>[!NOTE]
><span data-ttu-id="b1a17-130">O país ou a região definida aqui determina a região do Data Center em que o Office 365 será hospedado.</span><span class="sxs-lookup"><span data-stu-id="b1a17-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="b1a17-131">Escolha sua preferência de verificação: por meio de uma mensagem de texto ou chamada.</span><span class="sxs-lookup"><span data-stu-id="b1a17-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="b1a17-132">Clique em **enviar código de verificação**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-132">Click **Send Verification Code**.</span></span> 
<span data-ttu-id="b1a17-133">![Of_page de imagem](../../media/mtp-eval-12.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-133">![Image of_page](../../media/mtp-eval-12.png)</span></span> <br>

5. <span data-ttu-id="b1a17-134">Defina o nome de domínio personalizado para o seu locatário e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-134">Set the custom domain name for your tenant, then click **Next**.</span></span>
<br><span data-ttu-id="b1a17-135">![Of_page de imagem](../../media/mtp-eval-13.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-135">![Image of_page](../../media/mtp-eval-13.png)</span></span> <br>
 
6. <span data-ttu-id="b1a17-136">Configure a primeira identidade que será um administrador global do locatário.</span><span class="sxs-lookup"><span data-stu-id="b1a17-136">Set up the first identity which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="b1a17-137">Insira o **nome** e a **senha**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="b1a17-138">Clique em **inscrever-se**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-138">Click **Sign up**.</span></span>
<span data-ttu-id="b1a17-139">![Of_page de imagem](../../media/mtp-eval-14.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-139">![Image of_page](../../media/mtp-eval-14.png)</span></span> <br>
<span data-ttu-id="b1a17-140">c</span><span class="sxs-lookup"><span data-stu-id="b1a17-140">c</span></span>
7. <span data-ttu-id="b1a17-141">Clique em **ir para configuração** para concluir o provisionamento do locatário de avaliação do Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="b1a17-141">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>
<br><span data-ttu-id="b1a17-142">![Of_page de imagem](../../media/mtp-eval-15.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-142">![Image of_page](../../media/mtp-eval-15.png)</span></span> <br>

8. <span data-ttu-id="b1a17-143">Conecte seu domínio corporativo ao locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b1a17-143">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="b1a17-144">Opcion Escolha **conectar um domínio que você já possui** e digite o nome do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="b1a17-144">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="b1a17-145">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-145">Click **Next**.</span></span>
<br><span data-ttu-id="b1a17-146">![Of_page de imagem](../../media/mtp-eval-16.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-146">![Image of_page](../../media/mtp-eval-16.png)</span></span> <br>
 
9. <span data-ttu-id="b1a17-147">Será necessário adicionar um registro TXT ou MX para validar a propriedade do domínio.</span><span class="sxs-lookup"><span data-stu-id="b1a17-147">You will need to add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="b1a17-148">Depois de adicionar o registro TXT ou MX ao seu domínio, selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-148">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>
<br><span data-ttu-id="b1a17-149">![Of_page de imagem](../../media/mtp-eval-17.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-149">![Image of_page](../../media/mtp-eval-17.png)</span></span> <br>
 
10. <span data-ttu-id="b1a17-150">Opcion Criar mais contas de usuário para o locatário.</span><span class="sxs-lookup"><span data-stu-id="b1a17-150">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="b1a17-151">Você pode ignorar essa etapa clicando em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-151">You can skip this step by clicking **Next**.</span></span>
<span data-ttu-id="b1a17-152">![Of_page de imagem](../../media/mtp-eval-18.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-152">![Image of_page](../../media/mtp-eval-18.png)</span></span> <br>
 
11. <span data-ttu-id="b1a17-153">Opcion Baixar aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="b1a17-153">[Optional] Download Office apps.</span></span> <span data-ttu-id="b1a17-154">Clique em **Avançar** para ignorar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="b1a17-154">Click **Next** to skip this step.</span></span> 
<br><span data-ttu-id="b1a17-155">![Of_page de imagem](../../media/mtp-eval-19.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-155">![Image of_page](../../media/mtp-eval-19.png)</span></span> <br>

12. <span data-ttu-id="b1a17-156">Opcion Migrar mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="b1a17-156">[Optional] Migrate email messages.</span></span> <span data-ttu-id="b1a17-157">Novamente, você pode ignorar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="b1a17-157">Again, you can skip this step.</span></span>
<br><span data-ttu-id="b1a17-158">![Of_page de imagem](../../media/mtp-eval-20.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-158">![Image of_page](../../media/mtp-eval-20.png)</span></span> <br>
 
13. <span data-ttu-id="b1a17-159">Escolha serviços online.</span><span class="sxs-lookup"><span data-stu-id="b1a17-159">Choose online services.</span></span> <span data-ttu-id="b1a17-160">Selecione **Exchange** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-160">Select **Exchange** and click **Next**.</span></span> 
<br><span data-ttu-id="b1a17-161">![Of_page de imagem](../../media/mtp-eval-21.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-161">![Image of_page](../../media/mtp-eval-21.png)</span></span> <br>

14. <span data-ttu-id="b1a17-162">Adicione registros MX, CNAME e TXT ao seu domínio.</span><span class="sxs-lookup"><span data-stu-id="b1a17-162">Add MX, CNAME and TXT records to your domain.</span></span> <span data-ttu-id="b1a17-163">Quando concluído, selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-163">When completed, select **Verify**.</span></span>
<br><span data-ttu-id="b1a17-164">![Of_page de imagem](../../media/mtp-eval-22.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-164">![Image of_page](../../media/mtp-eval-22.png)</span></span> <br>
 
15. <span data-ttu-id="b1a17-165">Parabéns, você concluiu o provisionamento do seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b1a17-165">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>
<br><span data-ttu-id="b1a17-166">![Of_page de imagem](../../media/mtp-eval-23.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-166">![Image of_page](../../media/mtp-eval-23.png)</span></span> <br>

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="b1a17-167">Habilitar a assinatura de avaliação do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b1a17-167">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="b1a17-168">Inscrever-se em uma avaliação oferece 25 licenças de usuário para usar por mês.</span><span class="sxs-lookup"><span data-stu-id="b1a17-168">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="b1a17-169">Consulte [tentar ou comprar uma assinatura do M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="b1a17-169">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="b1a17-170">No [centro de administração do Microsoft 365](https://admin.microsoft.com/), clique em **cobrança** e navegue até **serviços de compra**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-170">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="b1a17-171">Selecione **Microsoft 365 E5** e clique em **Iniciar avaliação gratuita**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-171">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 
<span data-ttu-id="b1a17-172">![Of_page de imagem](../../media/mtp-eval-24.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-172">![Image of_page](../../media/mtp-eval-24.png)</span></span> <br>

3. <span data-ttu-id="b1a17-173">Escolha sua preferência de verificação: por meio de uma mensagem de texto ou chamada.</span><span class="sxs-lookup"><span data-stu-id="b1a17-173">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="b1a17-174">Depois de decidir, insira o número de telefone, selecione o **texto me** ou **telefonar para mim** , dependendo da seleção.</span><span class="sxs-lookup"><span data-stu-id="b1a17-174">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>
<span data-ttu-id="b1a17-175">![Of_page de imagem](../../media/mtp-eval-25.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-175">![Image of_page](../../media/mtp-eval-25.png)</span></span> <br>
 
4. <span data-ttu-id="b1a17-176">Insira o código de verificação e clique em **iniciar sua avaliação gratuita**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-176">Enter the verification code and click **Start your free trial**.</span></span> 
<br><span data-ttu-id="b1a17-177">![Of_page de imagem](../../media/mtp-eval-26.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-177">![Image of_page](../../media/mtp-eval-26.png)</span></span> <br>

5. <span data-ttu-id="b1a17-178">Clique em **tentar agora** para confirmar sua avaliação do Microsoft 365 e5.</span><span class="sxs-lookup"><span data-stu-id="b1a17-178">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>
<br><span data-ttu-id="b1a17-179">![Of_page de imagem](../../media/mtp-eval-27.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-179">![Image of_page](../../media/mtp-eval-27.png)</span></span> <br>
 
6. <span data-ttu-id="b1a17-180">Vá para o **Centro** > **Users** > de administração do Microsoft 365 usuários**ativos**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-180">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="b1a17-181">Selecione sua conta de usuário, selecione **gerenciar licenças de produto**e troque a licença do Office 365 E5 para a **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-181">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="b1a17-182">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-182">Click **Save**.</span></span>
<span data-ttu-id="b1a17-183">![Of_page de imagem](../../media/mtp-eval-28.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-183">![Image of_page](../../media/mtp-eval-28.png)</span></span> <br>
 
7. <span data-ttu-id="b1a17-184">Selecione a conta de administrador global novamente e, em seguida, clique em **gerenciar nome de usuário**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-184">Select the global administrator account again then click **Manage username**.</span></span>
<br><span data-ttu-id="b1a17-185">![Of_page de imagem](../../media/mtp-eval-29.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-185">![Image of_page](../../media/mtp-eval-29.png)</span></span> <br>

8. <span data-ttu-id="b1a17-186">Opcion Altere o domínio de *onmicrosoft.com* para seu próprio domínio, dependendo do que você escolheu nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="b1a17-186">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="b1a17-187">Clique em **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="b1a17-187">Click **Save changes**.</span></span>
<br><span data-ttu-id="b1a17-188">![Of_page de imagem](../../media/mtp-eval-30.png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-188">![Image of_page](../../media/mtp-eval-30.png)</span></span> <br>



## <a name="next-step"></a><span data-ttu-id="b1a17-189">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="b1a17-189">Next step</span></span>
<span data-ttu-id="b1a17-190">||| |:-------|:-----| config-onboard. png)</span><span class="sxs-lookup"><span data-stu-id="b1a17-190">||| |:-------|:-----|config-onboard.png)</span></span> <br><span data-ttu-id="b1a17-191">[Fase 3: configurar & integrada](config-mtpeval.md) | Configure cada pilar de proteção contra ameaças da Microsoft para seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft e integração dos seus pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="b1a17-191">[Phase 3: Configure & Onboard](config-mtpeval.md) | Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints.</span></span>
