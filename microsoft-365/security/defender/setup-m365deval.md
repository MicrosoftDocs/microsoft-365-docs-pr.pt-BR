---
title: Configurar o laboratório de avaliação do Microsoft 365 Defender ou o ambiente piloto
description: Acesse o Centro de Segurança do Microsoft 365 e, em seguida, configurar seu ambiente de laboratório de avaliação do Microsoft 365 Defender
keywords: Configuração de avaliação do Microsoft 365 Defender, configuração piloto do Microsoft 365 Defender, configuração do laboratório de avaliação do Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: ae81f6be0a83d5d0141f0f0c8c89f8f2207cc56c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935420"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="f4ded-104">Configurar seu ambiente de laboratório de avaliação do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4ded-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f4ded-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f4ded-105">**Applies to:**</span></span>
- <span data-ttu-id="f4ded-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4ded-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="f4ded-107">Criar um laboratório de avaliação do Microsoft 365 Defender ou um ambiente piloto e implantá-lo é um processo de três fases:</span><span class="sxs-lookup"><span data-stu-id="f4ded-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="f4ded-108">[![Fase 1: Preparar](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="f4ded-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="f4ded-109">Fase 1: Preparar</span><span class="sxs-lookup"><span data-stu-id="f4ded-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |![Fase 2: Configurar](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="f4ded-111">Fase 2: Configurar</span><span class="sxs-lookup"><span data-stu-id="f4ded-111">Phase 2: Set up</span></span> |<span data-ttu-id="f4ded-112">[![Fase 3: Integrar](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="f4ded-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span></span><br/>[<span data-ttu-id="f4ded-113">Fase 3: Integrar</span><span class="sxs-lookup"><span data-stu-id="f4ded-113">Phase 3: Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="f4ded-114">[![Voltar ao piloto](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="f4ded-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="f4ded-115">Voltar ao playbook piloto</span><span class="sxs-lookup"><span data-stu-id="f4ded-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="f4ded-116">*Você está aqui!*</span><span class="sxs-lookup"><span data-stu-id="f4ded-116">*You are here!*</span></span>  | | |


<span data-ttu-id="f4ded-117">No momento, você está na fase de configuração.</span><span class="sxs-lookup"><span data-stu-id="f4ded-117">You're currently in the set up phase.</span></span> <span data-ttu-id="f4ded-118">Tome as etapas iniciais para acessar o Centro de Segurança do Microsoft 365 e, em seguida, configurar seu laboratório de avaliação ou ambiente piloto.</span><span class="sxs-lookup"><span data-stu-id="f4ded-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="f4ded-119">Inscreva-se em uma assinatura do Office 365 ou do Azure Active Directory para gerar um *locatário .onmicrosoft.com* que você pode usar para se inscrever na licença do Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f4ded-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="f4ded-120">Se você já tiver uma assinatura existente do Office 365 ou do Azure Active Directory, poderá ignorar as etapas de avaliação do Office 365 E5 ou criação de locatário piloto.</span><span class="sxs-lookup"><span data-stu-id="f4ded-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="f4ded-121">Nesta fase, você será guiado para:</span><span class="sxs-lookup"><span data-stu-id="f4ded-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="f4ded-122">Criar um locatário de avaliação do Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="f4ded-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="f4ded-123">Habilitar a assinatura de avaliação do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4ded-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="f4ded-124">Criar um locatário de avaliação do Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="f4ded-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="f4ded-125">Se você já tiver uma assinatura existente do Office 365 ou do Azure Active Directory, poderá ignorar as etapas de criação de locatários de avaliação do Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f4ded-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="f4ded-126">Vá para o portal de produtos do [Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) e selecione **avaliação gratuita.**</span><span class="sxs-lookup"><span data-stu-id="f4ded-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Página de avaliação gratuita of_Office 365 E5](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="f4ded-128">Conclua o registro de avaliação inserindo seu endereço de email (pessoal ou corporativo).</span><span class="sxs-lookup"><span data-stu-id="f4ded-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="f4ded-129">Clique **em Configurar conta**.</span><span class="sxs-lookup"><span data-stu-id="f4ded-129">Click **Set up account**.</span></span>

   ![Página de configuração de registro de avaliação do Of_Office 365 E5](../../media/mtp-eval-10.png)

3. <span data-ttu-id="f4ded-131">Preencha seu nome, sobrenome, número de telefone comercial, nome da empresa, tamanho da empresa e país ou região.</span><span class="sxs-lookup"><span data-stu-id="f4ded-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Imagem of_Office página de configuração de registro de avaliação do 365 E5 solicitando o nome, telefone e detalhes da empresa](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="f4ded-133">O país ou região que você definir aqui determina a região do data center onde o Office 365 será hospedado.</span><span class="sxs-lookup"><span data-stu-id="f4ded-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="f4ded-134">Escolha sua preferência de verificação: por meio de uma mensagem de texto ou chamada.</span><span class="sxs-lookup"><span data-stu-id="f4ded-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="f4ded-135">Clique **em Enviar Código de Verificação**.</span><span class="sxs-lookup"><span data-stu-id="f4ded-135">Click **Send Verification Code**.</span></span> 

   ![Imagem of_Office página de configuração de registro de avaliação do 365 E5 solicitando preferência de verificação](../../media/mtp-eval-12.png)

5. <span data-ttu-id="f4ded-137">De definir o nome de domínio personalizado para seu locatário e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f4ded-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Imagem of_Office página de configuração de registro de avaliação do 365 E5 onde você pode configurar seu nome de domínio personalizado](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="f4ded-139">Configurar a primeira identidade, que será um Administrador Global para o locatário.</span><span class="sxs-lookup"><span data-stu-id="f4ded-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="f4ded-140">Preencha Nome **e** **Senha**.</span><span class="sxs-lookup"><span data-stu-id="f4ded-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="f4ded-141">Clique **em Inscrever-se**.</span><span class="sxs-lookup"><span data-stu-id="f4ded-141">Click **Sign up**.</span></span>

   ![Imagem of_Office página de configuração de registro de avaliação do 365 E5 onde você pode definir sua identidade comercial](../../media/mtp-eval-14.png)

7. <span data-ttu-id="f4ded-143">Clique **em Ir para a Instalação** para concluir o provisionamento do locatário de avaliação do Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f4ded-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Imagem da página de configuração de registro de avaliação do Office 365 E5 solicitando que clique em Ir botão Configurar](../../media/mtp-eval-15.png)

8. <span data-ttu-id="f4ded-145">Conecte seu domínio corporativo ao locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f4ded-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="f4ded-146">[Opcional] Escolha **Conectar um domínio que você já possui** e digite seu nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="f4ded-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="f4ded-147">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f4ded-147">Click **Next**.</span></span>

   ![Imagem of_Office página de Instalação do 365 E5 em que você deve personalizar sua assinatura e email](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="f4ded-149">Adicione um registro TXT ou MX para validar a propriedade do domínio.</span><span class="sxs-lookup"><span data-stu-id="f4ded-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="f4ded-150">Depois de adicionar o registro TXT ou MX ao seu domínio, selecione **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="f4ded-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Página of_Office de configuração do 365 E5 em que você deve adicionar um TXT de registro MX para verificar seu domínio](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="f4ded-152">[Opcional] Crie mais contas de usuário para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="f4ded-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="f4ded-153">Você pode ignorar esta etapa clicando em **Next**.</span><span class="sxs-lookup"><span data-stu-id="f4ded-153">You can skip this step by clicking **Next**.</span></span>

    ![Página of_Office de configuração do 365 E5 onde você pode adicionar mais usuários](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="f4ded-155">[Opcional] Baixe aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="f4ded-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="f4ded-156">Clique **em Próximo** para ignorar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="f4ded-156">Click **Next** to skip this step.</span></span> 

    ![Página of_Office 365 E5 em que você pode instalar seus aplicativos do Office](../../media/mtp-eval-19.png)

12. <span data-ttu-id="f4ded-158">[Opcional] Migrar mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="f4ded-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="f4ded-159">Novamente, você pode ignorar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="f4ded-159">Again, you can skip this step.</span></span>

    ![Imagem of_Office 365 E5 onde você pode definir se deve migrar mensagens de email ou não](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="f4ded-161">Escolha serviços online.</span><span class="sxs-lookup"><span data-stu-id="f4ded-161">Choose online services.</span></span> <span data-ttu-id="f4ded-162">Selecione **Exchange** e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="f4ded-162">Select **Exchange** and click **Next**.</span></span> 

    ![Imagem of_Office 365 E5 onde você pode escolher seus serviços online](../../media/mtp-eval-21.png)

14. <span data-ttu-id="f4ded-164">Adicione registros MX, CNAME e TXT ao seu domínio.</span><span class="sxs-lookup"><span data-stu-id="f4ded-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="f4ded-165">Quando concluído, selecione **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="f4ded-165">When completed, select **Verify**.</span></span>

    ![Imagem of_Office 365 E5 aqui você pode adicionar seus registros DNS](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="f4ded-167">Parabéns, você concluiu o provisionamento do locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f4ded-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Página de confirmação de conclusão da instalação of_Office 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="f4ded-169">Habilitar a assinatura de avaliação do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4ded-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="f4ded-170">Inscrever-se em uma avaliação oferece 25 licenças de usuário para usar por um mês.</span><span class="sxs-lookup"><span data-stu-id="f4ded-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="f4ded-171">Consulte [Try or Buy an M365 subscription para](../../commerce/try-or-buy-microsoft-365.md) obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="f4ded-171">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="f4ded-172">No Centro de Administração do [Microsoft 365,](https://admin.microsoft.com/)clique em **Cobrança** e navegue até **Serviços de Compra.**</span><span class="sxs-lookup"><span data-stu-id="f4ded-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="f4ded-173">Selecione **Microsoft 365 E5 e** clique em Iniciar **avaliação gratuita**.</span><span class="sxs-lookup"><span data-stu-id="f4ded-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Página de avaliação gratuita do Of_Microsoft 365 E5](../../media/mtp-eval-24.png)

3. <span data-ttu-id="f4ded-175">Escolha sua preferência de verificação: por meio de uma mensagem de texto ou chamada.</span><span class="sxs-lookup"><span data-stu-id="f4ded-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="f4ded-176">Depois de decidir, digite o número de telefone, selecione **Texto-me** ou **Chame-me** dependendo de sua seleção.</span><span class="sxs-lookup"><span data-stu-id="f4ded-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Imagem of_Microsoft 365 E5 Iniciar página de avaliação gratuita solicitando detalhes de contato para enviar código para provar que você não é um robô](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="f4ded-178">Insira o código de verificação e clique em **Iniciar sua avaliação gratuita.**</span><span class="sxs-lookup"><span data-stu-id="f4ded-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![Imagem of_Microsoft 365 E5 Iniciar página de avaliação gratuita onde você pode preencher o código de verificação enviado pelo sistema para provar que não é um robô](../../media/mtp-eval-26.png)

5. <span data-ttu-id="f4ded-180">Clique **em Tentar agora** para confirmar sua avaliação do Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f4ded-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Imagem of_Microsoft 365 E5 Iniciar página de avaliação gratuita onde você deve relógio o botão Tentar agora para iniciar](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="f4ded-182">Vá para o Centro de Administração do **Microsoft 365**  >  **Usuários**  >  **ativos.**</span><span class="sxs-lookup"><span data-stu-id="f4ded-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="f4ded-183">Selecione sua conta de usuário, selecione **Gerenciar licenças** de produto e, em seguida, troque a licença do Office 365 E5 para **o Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="f4ded-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="f4ded-184">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f4ded-184">Click **Save**.</span></span>

   ![Página of_Microsoft centro de administração do 365 em que você pode selecionar a licença do Microsoft 365 E5](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="f4ded-186">Selecione a conta de administrador global novamente e clique em Gerenciar nome **de usuário**.</span><span class="sxs-lookup"><span data-stu-id="f4ded-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![Página of_Microsoft centro de administração do 365 onde você pode selecionar Conta e gerenciar nome de usuário](../../media/mtp-eval-29.png)

8. <span data-ttu-id="f4ded-188">[Opcional] Altere o domínio *de onmicrosoft.com* para seu próprio domínio, dependendo do que você escolheu nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="f4ded-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="f4ded-189">Clique em **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="f4ded-189">Click **Save changes**.</span></span>

   ![Página of_Microsoft centro de administração do 365 onde você pode alterar sua preferência de domínio](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="f4ded-191">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="f4ded-191">Next step</span></span>
|[<span data-ttu-id="f4ded-192">Fase 3: Configurar o & Onboard</span><span class="sxs-lookup"><span data-stu-id="f4ded-192">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="f4ded-193">Configure cada pilar do Microsoft 365 Defender para seu laboratório de avaliação do Microsoft 365 Defender ou ambiente piloto e aborde seus pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="f4ded-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
