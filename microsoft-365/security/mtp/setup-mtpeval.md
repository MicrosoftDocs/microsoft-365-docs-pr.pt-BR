---
title: Configurar o laboratório de avaliação de proteção contra ameaças da Microsoft ou o ambiente piloto
description: Acessar o centro de segurança do Microsoft 365 e configurar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft
keywords: Configuração de avaliação do Microsoft Threat Protection, configuração do piloto do Microsoft Threat Protection, experimente proteção contra ameaças da Microsoft, configuração do laboratório de avaliação de proteção contra ameaças da Microsoft
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
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 53ff0842e73e275bf4a8fa8b18c1d08ad70a64ec
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418128"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="4340b-104">Configurar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="4340b-104">Set up your Microsoft Threat Protection trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4340b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4340b-105">**Applies to:**</span></span>
- <span data-ttu-id="4340b-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="4340b-106">Microsoft Threat Protection</span></span> 


<span data-ttu-id="4340b-107">A criação de um laboratório de avaliação de proteção contra ameaças da Microsoft ou ambiente piloto e sua implantação é um processo de três fases:</span><span class="sxs-lookup"><span data-stu-id="4340b-107">Creating a Microsoft Threat Protection trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Preparar o laboratório de avaliação da proteção contra ameaças da Microsoft ou o ambiente piloto" />
      <br/><span data-ttu-id="4340b-109">Fase 1: preparar </a></span><span class="sxs-lookup"><span data-stu-id="4340b-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="Configurar o laboratório de avaliação de proteção contra ameaças da Microsoft ou o ambiente piloto" />
      <br/><span data-ttu-id="4340b-111">Fase 2: configuração </a></span><span class="sxs-lookup"><span data-stu-id="4340b-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab or pilot environment and onboard your endpoints" title="
Configure cada pilar de proteção contra ameaças da Microsoft para o laboratório de avaliação de proteção contra ameaças da Microsoft ou para o ambiente piloto e a integração dos pontos de extremidade" />
      <br/><span data-ttu-id="4340b-113">Fase 3: configurar o & integrado </a></span><span class="sxs-lookup"><span data-stu-id="4340b-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="4340b-114">Você está atualmente na fase de configuração.</span><span class="sxs-lookup"><span data-stu-id="4340b-114">You're currently in the set up phase.</span></span> <span data-ttu-id="4340b-115">Execute as etapas iniciais para acessar o centro de segurança do Microsoft 365 e configure seu laboratório de avaliação ou ambiente piloto.</span><span class="sxs-lookup"><span data-stu-id="4340b-115">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="4340b-116">Inscreva-se para uma assinatura do Office 365 ou do Azure Active Directory para gerar um locatário *. onmicrosoft.com* que você pode usar para se inscrever na sua licença do Microsoft 365 e5.</span><span class="sxs-lookup"><span data-stu-id="4340b-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="4340b-117">Se você já tiver uma assinatura existente do Office 365 ou do Azure Active Directory, poderá ignorar as etapas de avaliação do Office 365 E5 ou de criação do locatário piloto.</span><span class="sxs-lookup"><span data-stu-id="4340b-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="4340b-118">Nesta fase, você será orientado a:</span><span class="sxs-lookup"><span data-stu-id="4340b-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="4340b-119">Criar um locatário de avaliação do Office 365 e5</span><span class="sxs-lookup"><span data-stu-id="4340b-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="4340b-120">Habilitar a assinatura de avaliação do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4340b-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="4340b-121">Criar um locatário de avaliação do Office 365 e5</span><span class="sxs-lookup"><span data-stu-id="4340b-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="4340b-122">Se você já tiver uma assinatura existente do Office 365 ou do Azure Active Directory, poderá ignorar as etapas de criação do locatário de avaliação do Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="4340b-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="4340b-123">Vá para o [portal de produto do Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) e selecione **avaliação gratuita**.</span><span class="sxs-lookup"><span data-stu-id="4340b-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Página de avaliação gratuita de imagem of_Office 365 e5](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="4340b-125">Conclua o registro de avaliação inserindo seu endereço de email (pessoal ou corporativo).</span><span class="sxs-lookup"><span data-stu-id="4340b-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="4340b-126">Clique em **configurar conta**.</span><span class="sxs-lookup"><span data-stu-id="4340b-126">Click **Set up account**.</span></span>

   ![Página de configuração de registro de avaliação 365 E5 de imagem of_Office](../../media/mtp-eval-10.png)

3. <span data-ttu-id="4340b-128">Preencha seu nome, sobrenome, número de telefone comercial, nome da empresa, tamanho da empresa e país ou região.</span><span class="sxs-lookup"><span data-stu-id="4340b-128">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Imagem of_Office 365 E5 página de configuração de registro de avaliação para solicitar o nome, telefone e detalhes da empresa](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="4340b-130">O país ou a região definida aqui determina a região do Data Center em que o Office 365 será hospedado.</span><span class="sxs-lookup"><span data-stu-id="4340b-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="4340b-131">Escolha sua preferência de verificação: por meio de uma mensagem de texto ou chamada.</span><span class="sxs-lookup"><span data-stu-id="4340b-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="4340b-132">Clique em **enviar código de verificação**.</span><span class="sxs-lookup"><span data-stu-id="4340b-132">Click **Send Verification Code**.</span></span> 

   ![Imagem of_Office 365 E5 página de configuração de registro de avaliação solicitando preferência de verificação](../../media/mtp-eval-12.png)

5. <span data-ttu-id="4340b-134">Defina o nome de domínio personalizado para o seu locatário e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4340b-134">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Imagem of_Office 365 E5 página de configuração de registro de avaliação, onde você pode configurar seu nome de domínio personalizado](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="4340b-136">Configure a primeira identidade, que será um administrador global para o locatário.</span><span class="sxs-lookup"><span data-stu-id="4340b-136">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="4340b-137">Insira o **nome** e a **senha**.</span><span class="sxs-lookup"><span data-stu-id="4340b-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="4340b-138">Clique em **inscrever-se**.</span><span class="sxs-lookup"><span data-stu-id="4340b-138">Click **Sign up**.</span></span>

   ![Imagem of_Office 365 E5 página de configuração de registro de avaliação, onde você pode definir sua identidade comercial](../../media/mtp-eval-14.png)

7. <span data-ttu-id="4340b-140">Clique em **ir para configuração** para concluir o provisionamento do locatário de avaliação do Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="4340b-140">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Imagem da página de configuração do registro de avaliação do Office 365 E5 solicitando o clique no botão configuração do Go](../../media/mtp-eval-15.png)

8. <span data-ttu-id="4340b-142">Conecte seu domínio corporativo ao locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="4340b-142">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="4340b-143">Opcion Escolha **conectar um domínio que você já possui** e digite o nome do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="4340b-143">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="4340b-144">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4340b-144">Click **Next**.</span></span>

   ![Página de configuração de imagem of_Office 365 E5 onde você deve personalizar sua entrada e email](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="4340b-146">Adicione um registro TXT ou MX para validar a propriedade do domínio.</span><span class="sxs-lookup"><span data-stu-id="4340b-146">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="4340b-147">Depois de adicionar o registro TXT ou MX ao seu domínio, selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="4340b-147">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Página de imagem of_Office 365 E5 onde você deve adicionar um TXT do registro MX para verificar seu domínio](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="4340b-149">Opcion Criar mais contas de usuário para o locatário.</span><span class="sxs-lookup"><span data-stu-id="4340b-149">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="4340b-150">Você pode ignorar essa etapa clicando em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4340b-150">You can skip this step by clicking **Next**.</span></span>

    ![Página de configuração de imagem of_Office 365 E5 onde você pode adicionar mais usuários](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="4340b-152">Opcion Baixar aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="4340b-152">[Optional] Download Office apps.</span></span> <span data-ttu-id="4340b-153">Clique em **Avançar** para ignorar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="4340b-153">Click **Next** to skip this step.</span></span> 

    ![Página de imagem of_Office 365 E5 onde você pode instalar seus aplicativos do Office](../../media/mtp-eval-19.png)

12. <span data-ttu-id="4340b-155">Opcion Migrar mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="4340b-155">[Optional] Migrate email messages.</span></span> <span data-ttu-id="4340b-156">Novamente, você pode ignorar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="4340b-156">Again, you can skip this step.</span></span>

    ![Image of_Office 365 E5 onde você pode definir se deseja migrar mensagens de email ou não](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="4340b-158">Escolha serviços online.</span><span class="sxs-lookup"><span data-stu-id="4340b-158">Choose online services.</span></span> <span data-ttu-id="4340b-159">Selecione **Exchange** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4340b-159">Select **Exchange** and click **Next**.</span></span> 

    ![Imagem of_Office 365 E5 onde você pode escolher seus serviços online](../../media/mtp-eval-21.png)

14. <span data-ttu-id="4340b-161">Adicionar registros MX, CNAME e TXT ao seu domínio.</span><span class="sxs-lookup"><span data-stu-id="4340b-161">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="4340b-162">Quando concluído, selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="4340b-162">When completed, select **Verify**.</span></span>

    ![Imagem of_Office 365 E5 aqui você pode adicionar seus registros DNS](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="4340b-164">Parabéns, você concluiu o provisionamento do seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="4340b-164">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Página de confirmação de conclusão da instalação da of_Office 365 e5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="4340b-166">Habilitar a assinatura de avaliação do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4340b-166">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="4340b-167">Inscrever-se em uma avaliação oferece 25 licenças de usuário para usar por mês.</span><span class="sxs-lookup"><span data-stu-id="4340b-167">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="4340b-168">Consulte [tentar ou comprar uma assinatura do M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="4340b-168">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="4340b-169">No [centro de administração do Microsoft 365](https://admin.microsoft.com/), clique em **cobrança** e navegue até **serviços de compra**.</span><span class="sxs-lookup"><span data-stu-id="4340b-169">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="4340b-170">Selecione **Microsoft 365 E5** e clique em **Iniciar avaliação gratuita**.</span><span class="sxs-lookup"><span data-stu-id="4340b-170">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Imagem of_Microsoft 365 E5 iniciar página de avaliação gratuita](../../media/mtp-eval-24.png)

3. <span data-ttu-id="4340b-172">Escolha sua preferência de verificação: por meio de uma mensagem de texto ou chamada.</span><span class="sxs-lookup"><span data-stu-id="4340b-172">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="4340b-173">Depois de decidir, insira o número de telefone, selecione o **texto me** ou **telefonar para mim** , dependendo da seleção.</span><span class="sxs-lookup"><span data-stu-id="4340b-173">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Imagem of_Microsoft 365 E5 iniciar página de avaliação gratuita solicitando detalhes do contato para enviar código para provar que você não é um robô](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="4340b-175">Insira o código de verificação e clique em **iniciar sua avaliação gratuita**.</span><span class="sxs-lookup"><span data-stu-id="4340b-175">Enter the verification code and click **Start your free trial**.</span></span>

   ![Imagem of_Microsoft 365 E5 iniciar página de avaliação gratuita onde você pode preencher o código de verificação o sistema enviado para provar que você não é um robô](../../media/mtp-eval-26.png)

5. <span data-ttu-id="4340b-177">Clique em **tentar agora** para confirmar sua avaliação do Microsoft 365 e5.</span><span class="sxs-lookup"><span data-stu-id="4340b-177">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Imagem of_Microsoft 365 E5 iniciar página de avaliação gratuita onde você deve registrar o botão experimentar agora para iniciar](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="4340b-179">Vá para o **centro de administração do Microsoft 365**  >  **usuários**  >  **ativos**.</span><span class="sxs-lookup"><span data-stu-id="4340b-179">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="4340b-180">Selecione sua conta de usuário, selecione **gerenciar licenças de produto**e troque a licença do Office 365 E5 para a **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="4340b-180">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="4340b-181">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4340b-181">Click **Save**.</span></span>

   ![Imagem of_Microsoft 365 página de centro de administração onde você pode selecionar a licença do Microsoft 365 e5](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="4340b-183">Selecione a conta de administrador global novamente e, em seguida, clique em **gerenciar nome de usuário**.</span><span class="sxs-lookup"><span data-stu-id="4340b-183">Select the global administrator account again then click **Manage username**.</span></span>

   ![Imagem of_Microsoft 365 página de centro de administração onde você pode selecionar Account e gerenciar username](../../media/mtp-eval-29.png)

8. <span data-ttu-id="4340b-185">Opcion Altere o domínio de *onmicrosoft.com* para seu próprio domínio, dependendo do que você escolheu nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="4340b-185">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="4340b-186">Clique em **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="4340b-186">Click **Save changes**.</span></span>

   ![Imagem of_Microsoft 365 página de centro de administração onde você pode alterar sua preferência de domínio](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="4340b-188">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="4340b-188">Next step</span></span>
|<span data-ttu-id="4340b-189">![Fase 3: configurar o & integrado](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="4340b-189">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="4340b-190">Fase 3: configurar o & integrado</span><span class="sxs-lookup"><span data-stu-id="4340b-190">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="4340b-191">Configure cada pilar de proteção contra ameaças da Microsoft para o laboratório de avaliação de proteção contra ameaças da Microsoft ou para o ambiente piloto e integração dos pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="4340b-191">Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
