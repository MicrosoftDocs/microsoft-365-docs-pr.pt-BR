---
title: Integração usando o Microsoft Endpoint Configuration Manager
description: Saiba como integrar o Microsoft Defender para Ponto de Extremidade usando o Microsoft Endpoint Configuration Manager
keywords: integração, configuração, implantação, implantação, gerenciador de configuração de ponto de extremidade, Microsoft Defender para Ponto de Extremidade, criação de coleção, resposta de detecção de ponto de extremidade, proteção de próxima geração, redução de superfície de ataque, microsoft endpoint configuration manager
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 84273ce3e060eb86ee246a5cc6a8cae3cba743b5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934484"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="5367d-104">Integração usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5367d-104">Onboarding using Microsoft Endpoint Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5367d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5367d-105">**Applies to:**</span></span>
- [<span data-ttu-id="5367d-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5367d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5367d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5367d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5367d-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="5367d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5367d-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="5367d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="5367d-110">Este artigo faz parte do guia implantação e age como um exemplo de método de integração.</span><span class="sxs-lookup"><span data-stu-id="5367d-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="5367d-111">No tópico [Planejamento,](deployment-strategy.md) havia vários métodos fornecidos para os dispositivos de integração ao serviço.</span><span class="sxs-lookup"><span data-stu-id="5367d-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="5367d-112">Este tópico aborda a arquitetura de co-gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="5367d-112">This topic covers the co-management architecture.</span></span> 

<span data-ttu-id="5367d-113">![Imagem da arquitetura nativa da nuvem ](images/co-management-architecture.png)
 *Diagrama de arquiteturas de ambiente*</span><span class="sxs-lookup"><span data-stu-id="5367d-113">![Image of cloud-native architecture](images/co-management-architecture.png)
*Diagram of environment architectures*</span></span>


<span data-ttu-id="5367d-114">Embora o Defender para Ponto de Extremidade suporte à integração de vários pontos de extremidade e ferramentas, este artigo não os abrange.</span><span class="sxs-lookup"><span data-stu-id="5367d-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="5367d-115">Para obter informações sobre a integração geral usando outras ferramentas e métodos de implantação com suporte, consulte [Onboarding overview](onboarding.md).</span><span class="sxs-lookup"><span data-stu-id="5367d-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>



<span data-ttu-id="5367d-116">Este tópico orienta os usuários em:</span><span class="sxs-lookup"><span data-stu-id="5367d-116">This topic guides users in:</span></span>
- <span data-ttu-id="5367d-117">Etapa 1: Integrando dispositivos Windows ao serviço</span><span class="sxs-lookup"><span data-stu-id="5367d-117">Step 1: Onboarding Windows devices to the service</span></span> 
- <span data-ttu-id="5367d-118">Etapa 2: Configurando o Defender para recursos do Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5367d-118">Step 2: Configuring Defender for Endpoint capabilities</span></span>

<span data-ttu-id="5367d-119">Essas diretrizes de integração orientarão você pelas seguintes etapas básicas que você precisa seguir ao usar o Microsoft Endpoint Configuration Manager:</span><span class="sxs-lookup"><span data-stu-id="5367d-119">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Configuration Manager:</span></span>
- <span data-ttu-id="5367d-120">**Criando uma coleção no Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="5367d-120">**Creating a collection in Microsoft Endpoint Configuration Manager**</span></span>
- <span data-ttu-id="5367d-121">**Configurando o Microsoft Defender para recursos de ponto de extremidade usando o Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="5367d-121">**Configuring Microsoft Defender for Endpoint capabilities using Microsoft Endpoint Configuration Manager**</span></span>

>[!NOTE]
><span data-ttu-id="5367d-122">Somente dispositivos Windows são abordados nesta implantação de exemplo.</span><span class="sxs-lookup"><span data-stu-id="5367d-122">Only Windows devices are covered in this example deployment.</span></span> 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="5367d-123">Etapa 1: Integração de dispositivos Windows usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5367d-123">Step 1: Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>

### <a name="collection-creation"></a><span data-ttu-id="5367d-124">Criação de coleção</span><span class="sxs-lookup"><span data-stu-id="5367d-124">Collection creation</span></span>
<span data-ttu-id="5367d-125">Para a integração de dispositivos Windows 10 com o Microsoft Endpoint Configuration Manager, a implantação pode direcionar uma coleção existente ou uma nova coleção pode ser criada para testes.</span><span class="sxs-lookup"><span data-stu-id="5367d-125">To onboard Windows 10 devices with Microsoft Endpoint Configuration Manager, the deployment can target an existing collection or a new collection can be created for testing.</span></span> 

<span data-ttu-id="5367d-126">A integração usando ferramentas como política de grupo ou método manual não instala nenhum agente no sistema.</span><span class="sxs-lookup"><span data-stu-id="5367d-126">Onboarding using tools such as Group policy or manual method does not install any agent on the system.</span></span> 

<span data-ttu-id="5367d-127">No console do Microsoft Endpoint Configuration Manager, o processo de integração será configurado como parte das configurações de conformidade no console.</span><span class="sxs-lookup"><span data-stu-id="5367d-127">Within the Microsoft Endpoint Configuration Manager console the onboarding process will be configured as part of the compliance settings within the console.</span></span>

<span data-ttu-id="5367d-128">Qualquer sistema que receber essa configuração necessária manterá essa configuração enquanto o cliente do Configuration Manager continuar a receber essa política do ponto de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="5367d-128">Any system that receives this required configuration will maintain that configuration for as long as the Configuration Manager client continues to receive this policy from the management point.</span></span> 

<span data-ttu-id="5367d-129">Siga as etapas abaixo para os pontos de extremidade de integração usando o Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="5367d-129">Follow the steps below to onboard endpoints using Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="5367d-130">No console do Microsoft Endpoint Configuration Manager, navegue até **Assets and Compliance Overview Device \> \> Collections**.</span><span class="sxs-lookup"><span data-stu-id="5367d-130">In Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Device Collections**.</span></span>            

    ![Imagem do Assistente do Microsoft Endpoint Configuration Manager1](images/configmgr-device-collections.png)

2. <span data-ttu-id="5367d-132">Clique com **o botão direito do mouse em Conjunto de Dispositivos** e selecione Criar Coleção de **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="5367d-132">Right Click **Device Collection** and select **Create Device Collection**.</span></span>

    ![Imagem do Assistente do Microsoft Endpoint Configuration Manager2](images/configmgr-create-device-collection.png)

3. <span data-ttu-id="5367d-134">Forneça uma **coleção Name** and **Limiting**, em seguida, selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="5367d-134">Provide a **Name** and **Limiting Collection**, then select **Next**.</span></span>

    ![Imagem do Assistente do Microsoft Endpoint Configuration Manager3](images/configmgr-limiting-collection.png)

4. <span data-ttu-id="5367d-136">Selecione **Adicionar Regra** e escolha Regra de **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="5367d-136">Select **Add Rule** and choose **Query Rule**.</span></span>

    ![Imagem do Assistente do Microsoft Endpoint Configuration Manager4](images/configmgr-query-rule.png)

5.  <span data-ttu-id="5367d-138">Clique **em Próximo** no Assistente de Associação **Direta** e clique em **Editar instrução De consulta**.</span><span class="sxs-lookup"><span data-stu-id="5367d-138">Click **Next** on the **Direct Membership Wizard** and click on **Edit Query Statement**.</span></span>

     ![Imagem do Assistente do Microsoft Endpoint Configuration Manager5](images/configmgr-direct-membership.png)

6. <span data-ttu-id="5367d-140">Selecione **Critérios** e escolha o ícone de estrela.</span><span class="sxs-lookup"><span data-stu-id="5367d-140">Select **Criteria** and then choose the star icon.</span></span>

     ![Imagem do Assistente do Microsoft Endpoint Configuration Manager6](images/configmgr-criteria.png)

7. <span data-ttu-id="5367d-142">Mantenha o tipo de critério como valor simples **,** escolha  onde como Sistema Operacional **-** número de com build , operador maior ou igual a e **valor 14393** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5367d-142">Keep criterion type as **simple value**, choose where as **Operating System - build number**, operator as **is greater than or equal to** and value **14393** and click on **OK**.</span></span>

    ![Imagem do Assistente do Microsoft Endpoint Configuration Manager7](images/configmgr-simple-value.png)

8. <span data-ttu-id="5367d-144">Selecione **Próximo** e **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="5367d-144">Select **Next** and **Close**.</span></span>

    ![Imagem do Assistente do Microsoft Endpoint Configuration Manager8](images/configmgr-membership-rules.png)

9. <span data-ttu-id="5367d-146">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5367d-146">Select **Next**.</span></span>

    ![Imagem do Assistente do Microsoft Endpoint Configuration Manager9](images/configmgr-confirm.png)


<span data-ttu-id="5367d-148">Depois de concluir essa tarefa, agora você tem uma coleção de dispositivos com todos os pontos de extremidade do Windows 10 no ambiente.</span><span class="sxs-lookup"><span data-stu-id="5367d-148">After completing this task, you now have a device collection with all the Windows 10 endpoints in the environment.</span></span> 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="5367d-149">Etapa 2: Configurar o Microsoft Defender para recursos do Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5367d-149">Step 2: Configure Microsoft Defender for Endpoint capabilities</span></span> 
<span data-ttu-id="5367d-150">Esta seção orienta você na configuração dos seguintes recursos usando o Microsoft Endpoint Configuration Manager em dispositivos Windows:</span><span class="sxs-lookup"><span data-stu-id="5367d-150">This section guides you in configuring the following capabilities using Microsoft Endpoint Configuration Manager on Windows devices:</span></span>

- [<span data-ttu-id="5367d-151">**Detecção de ponto de extremidade e resposta**</span><span class="sxs-lookup"><span data-stu-id="5367d-151">**Endpoint detection and response**</span></span>](#endpoint-detection-and-response)
- [<span data-ttu-id="5367d-152">**Proteção de próxima geração**</span><span class="sxs-lookup"><span data-stu-id="5367d-152">**Next-generation protection**</span></span>](#next-generation-protection)
- [<span data-ttu-id="5367d-153">**Redução de superfície de ataque**</span><span class="sxs-lookup"><span data-stu-id="5367d-153">**Attack surface reduction**</span></span>](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a><span data-ttu-id="5367d-154">Detecção de ponto de extremidade e resposta</span><span class="sxs-lookup"><span data-stu-id="5367d-154">Endpoint detection and response</span></span>
#### <a name="windows-10"></a><span data-ttu-id="5367d-155">Windows 10</span><span class="sxs-lookup"><span data-stu-id="5367d-155">Windows 10</span></span>
<span data-ttu-id="5367d-156">De dentro do Centro de Segurança do Microsoft Defender, é possível baixar a política '.onboarding' que pode ser usada para criar a política no System Center Configuration Manager e implantar essa política em dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5367d-156">From within the Microsoft Defender Security Center it is possible to download the '.onboarding' policy that can be used to create the policy in System Center Configuration Manager and deploy that policy to Windows 10 devices.</span></span>

1. <span data-ttu-id="5367d-157">Em um Portal do Centro de Segurança do Microsoft Defender, selecione [Configurações e, em seguida, Integrando](https://securitycenter.windows.com/preferences2/onboarding).</span><span class="sxs-lookup"><span data-stu-id="5367d-157">From a Microsoft Defender Security Center Portal, select [Settings and then Onboarding](https://securitycenter.windows.com/preferences2/onboarding).</span></span>



2. <span data-ttu-id="5367d-158">Em Método deployment, selecione a versão suportada do **Microsoft Endpoint Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="5367d-158">Under Deployment method select the supported version of **Microsoft Endpoint Configuration Manager**.</span></span>

    ![Imagem do Assistente de integração do Microsoft Defender para Ponto de Extremidade10](images/mdatp-onboarding-wizard.png)

3. <span data-ttu-id="5367d-160">Selecione **Baixar pacote**.</span><span class="sxs-lookup"><span data-stu-id="5367d-160">Select **Download package**.</span></span>

    ![Imagem do Assistente de integração do Microsoft Defender para Ponto de Extremidade11](images/mdatp-download-package.png)

4. <span data-ttu-id="5367d-162">Salve o pacote em um local acessível.</span><span class="sxs-lookup"><span data-stu-id="5367d-162">Save the package to an accessible location.</span></span>
5. <span data-ttu-id="5367d-163">No Microsoft Endpoint Configuration Manager, navegue até: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span><span class="sxs-lookup"><span data-stu-id="5367d-163">In  Microsoft Endpoint Configuration Manager, navigate to: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span></span>

6. <span data-ttu-id="5367d-164">Clique com o botão direito do **mouse em Políticas do Microsoft Defender ATP** e selecione Criar Política do Microsoft Defender **ATP**.</span><span class="sxs-lookup"><span data-stu-id="5367d-164">Right-click **Microsoft Defender ATP Policies** and select **Create Microsoft Defender ATP Policy**.</span></span>

    ![Imagem do Assistente de Configuração do Microsoft Endpoint12](images/configmgr-create-policy.png)

7. <span data-ttu-id="5367d-166">Insira o nome e a descrição, verifique **se a integração** está selecionada e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="5367d-166">Enter the name and description, verify **Onboarding** is selected, then select **Next**.</span></span>

    ![Imagem do Assistente de Configuração do Microsoft Endpoint13](images/configmgr-policy-name.png)


8. <span data-ttu-id="5367d-168">Clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="5367d-168">Click **Browse**.</span></span>

9. <span data-ttu-id="5367d-169">Navegue até o local do arquivo baixado da etapa 4 acima.</span><span class="sxs-lookup"><span data-stu-id="5367d-169">Navigate to the location of the downloaded file from step 4 above.</span></span>

10. <span data-ttu-id="5367d-170">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5367d-170">Click **Next**.</span></span>
11. <span data-ttu-id="5367d-171">Configure o Agente com as amostras apropriadas (**Nenhum** ou **Todos os tipos de arquivo**).</span><span class="sxs-lookup"><span data-stu-id="5367d-171">Configure the Agent with the appropriate samples (**None** or **All file types**).</span></span>

    ![Imagem das configurações1](images/configmgr-config-settings.png)

12. <span data-ttu-id="5367d-173">Selecione a telemetria apropriada (**Normal** ou **Acelerada**) e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="5367d-173">Select the appropriate telemetry (**Normal** or **Expedited**) then click **Next**.</span></span>

    ![Imagem das configurações2](images/configmgr-telemetry.png)

14. <span data-ttu-id="5367d-175">Verifique a configuração e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="5367d-175">Verify the configuration, then click **Next**.</span></span>

     ![Imagem das configurações3](images/configmgr-verify-configuration.png)

15. <span data-ttu-id="5367d-177">Clique **em Fechar** quando o Assistente for concluído.</span><span class="sxs-lookup"><span data-stu-id="5367d-177">Click **Close** when the Wizard completes.</span></span>

16.  <span data-ttu-id="5367d-178">No console do Microsoft Endpoint Configuration Manager, clique com o botão direito do mouse na política Defender para Ponto de Extremidade que você acabou de criar e selecione **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="5367d-178">In the Microsoft Endpoint Configuration Manager console, right-click the Defender for Endpoint policy you just created and select **Deploy**.</span></span>

     ![Imagem das configurações4](images/configmgr-deploy.png)

17. <span data-ttu-id="5367d-180">No painel direito, selecione a coleção criada anteriormente e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5367d-180">On the right panel, select the previously created collection and click **OK**.</span></span>

    ![Imagem das configurações5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a><span data-ttu-id="5367d-182">Versões anteriores do Windows Client (Windows 7 e Windows 8.1)</span><span class="sxs-lookup"><span data-stu-id="5367d-182">Previous versions of Windows Client (Windows 7 and Windows 8.1)</span></span>
<span data-ttu-id="5367d-183">Siga as etapas a seguir para identificar a ID do Espaço de Trabalho do Defender para Ponto de Extremidade e a Chave do Espaço de Trabalho, que serão necessárias para a integração de versões anteriores do Windows.</span><span class="sxs-lookup"><span data-stu-id="5367d-183">Follow the steps below to identify the Defender for Endpoint Workspace ID and Workspace Key, that will be required for the onboarding of previous versions of Windows.</span></span>

1. <span data-ttu-id="5367d-184">Em um Portal do Centro de Segurança do Microsoft Defender, selecione **Configurações > Integração**.</span><span class="sxs-lookup"><span data-stu-id="5367d-184">From a Microsoft Defender Security Center Portal, select **Settings > Onboarding**.</span></span>

2. <span data-ttu-id="5367d-185">Em sistema operacional, **escolha Windows 7 SP1 e 8.1**.</span><span class="sxs-lookup"><span data-stu-id="5367d-185">Under operating system choose **Windows 7 SP1 and 8.1**.</span></span>

3. <span data-ttu-id="5367d-186">Copie a **ID do Espaço de** Trabalho e **a Chave do Espaço de Trabalho** e salve-as.</span><span class="sxs-lookup"><span data-stu-id="5367d-186">Copy the **Workspace ID** and **Workspace Key** and save them.</span></span> <span data-ttu-id="5367d-187">Eles serão usados posteriormente no processo.</span><span class="sxs-lookup"><span data-stu-id="5367d-187">They will be used later in the process.</span></span>

    ![Imagem da integração](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. <span data-ttu-id="5367d-189">Instale o Microsoft Monitoring Agent (MMA).</span><span class="sxs-lookup"><span data-stu-id="5367d-189">Install the Microsoft Monitoring Agent (MMA).</span></span> <br>
    <span data-ttu-id="5367d-190">Atualmente, o MMA (a partir de janeiro de 2019) tem suporte nos seguintes Sistemas Operacionais Windows:</span><span class="sxs-lookup"><span data-stu-id="5367d-190">MMA is currently (as of January 2019) supported on the following Windows Operating Systems:</span></span>

    -   <span data-ttu-id="5367d-191">SKUs de servidor: Windows Server 2008 SP1 ou Newer</span><span class="sxs-lookup"><span data-stu-id="5367d-191">Server SKUs: Windows Server 2008 SP1 or Newer</span></span>

    -   <span data-ttu-id="5367d-192">SKUs cliente: Windows 7 SP1 e posterior</span><span class="sxs-lookup"><span data-stu-id="5367d-192">Client SKUs: Windows 7 SP1 and later</span></span>

    <span data-ttu-id="5367d-193">O agente MMA precisará ser instalado em dispositivos Windows.</span><span class="sxs-lookup"><span data-stu-id="5367d-193">The MMA agent will need to be installed on Windows devices.</span></span> <span data-ttu-id="5367d-194">Para instalar o agente, alguns sistemas precisarão baixar o Update para experiência do cliente e [a telemetria](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) de diagnóstico para coletar os dados com o MMA.</span><span class="sxs-lookup"><span data-stu-id="5367d-194">To install the agent, some systems will need to download the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) in order to collect the data with MMA.</span></span> <span data-ttu-id="5367d-195">Essas versões do sistema incluem, mas podem não se limitar a:</span><span class="sxs-lookup"><span data-stu-id="5367d-195">These system versions include but may not be limited to:</span></span>

    -   <span data-ttu-id="5367d-196">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="5367d-196">Windows 8.1</span></span>

    -   <span data-ttu-id="5367d-197">Windows 7</span><span class="sxs-lookup"><span data-stu-id="5367d-197">Windows 7</span></span>

    -   <span data-ttu-id="5367d-198">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="5367d-198">Windows Server 2016</span></span>

    -   <span data-ttu-id="5367d-199">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="5367d-199">Windows Server 2012 R2</span></span>

    -   <span data-ttu-id="5367d-200">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="5367d-200">Windows Server 2008 R2</span></span>

    <span data-ttu-id="5367d-201">Especificamente, para o Windows 7 SP1, os seguintes patches devem ser instalados:</span><span class="sxs-lookup"><span data-stu-id="5367d-201">Specifically, for Windows 7 SP1, the following patches must be installed:</span></span>

    -   <span data-ttu-id="5367d-202">Instalar [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="5367d-202">Install [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>

    -   <span data-ttu-id="5367d-203">Instale o [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (ou posterior) **ou** 
         [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span><span class="sxs-lookup"><span data-stu-id="5367d-203">Install either [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) **or**
        [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span></span>
        <span data-ttu-id="5367d-204">Não instale ambos no mesmo sistema.</span><span class="sxs-lookup"><span data-stu-id="5367d-204">Do not install both on the same system.</span></span>

5. <span data-ttu-id="5367d-205">Se você estiver usando um proxy para se conectar à Internet, consulte a seção Configurar configurações de proxy.</span><span class="sxs-lookup"><span data-stu-id="5367d-205">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="5367d-206">Depois de concluído, você deverá ver pontos de extremidade integrados no portal dentro de uma hora.</span><span class="sxs-lookup"><span data-stu-id="5367d-206">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="5367d-207">Proteção de próxima geração</span><span class="sxs-lookup"><span data-stu-id="5367d-207">Next generation protection</span></span> 
<span data-ttu-id="5367d-208">O Windows Defender Antivírus é uma solução antimalware interna que oferece proteção de próxima geração para computadores desktop, computadores portáteis e servidores.</span><span class="sxs-lookup"><span data-stu-id="5367d-208">Microsoft Defender Antivirus is a built-in antimalware solution that provides next generation protection for desktops, portable computers, and servers.</span></span>

1. <span data-ttu-id="5367d-209">No console do Microsoft Endpoint Configuration Manager, navegue até **Assets and Compliance Overview \> \> Endpoint Protection \> Antimalware Polices** e escolha **Criar Política antimalware**.</span><span class="sxs-lookup"><span data-stu-id="5367d-209">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Antimalware Polices** and choose **Create Antimalware Policy**.</span></span>

    ![Imagem da política antimalware](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. <span data-ttu-id="5367d-211">Selecione **Verificações** agendadas, **Configurações** de **verificação,** ações **padrão,** proteção em tempo **real,** configurações de exclusão, **avançadas,** substituições de **ameaças,** atualizações de inteligência de segurança e serviço de proteção na nuvem e escolha **OK**. </span><span class="sxs-lookup"><span data-stu-id="5367d-211">Select **Scheduled scans**, **Scan settings**, **Default actions**, **Real-time protection**, **Exclusion settings**, **Advanced**, **Threat overrides**, **Cloud Protection Service** and **Security intelligence   updates** and choose **OK**.</span></span>

    ![Imagem do painel de proteção de próxima geração1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    <span data-ttu-id="5367d-213">Em determinados setores ou alguns clientes corporativos selecionados podem ter necessidades específicas sobre como o Antivírus é configurado.</span><span class="sxs-lookup"><span data-stu-id="5367d-213">In certain industries or some select enterprise customers might have specific needs on how Antivirus is configured.</span></span>

  
    [<span data-ttu-id="5367d-214">Verificação rápida versus verificação completa e verificação personalizada</span><span class="sxs-lookup"><span data-stu-id="5367d-214">Quick scan versus full scan and custom scan</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    <span data-ttu-id="5367d-215">Para obter mais detalhes, consulte [Estrutura de configuração do Windows Security](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span><span class="sxs-lookup"><span data-stu-id="5367d-215">For more details, see [Windows Security configuration framework](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span></span>
  
    ![Imagem do painel de proteção de próxima geração2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![Imagem do painel de proteção de próxima geração3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![Imagem do painel de proteção de próxima geração4](images/a28afc02c1940d5220b233640364970c.png)

    ![Imagem do painel de proteção de próxima geração5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![Imagem do painel de proteção de próxima geração6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![Imagem do painel de proteção de próxima geração7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![Imagem do painel de proteção de próxima geração8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![Imagem do painel de proteção de próxima geração9](images/3876ca687391bfc0ce215d221c683970.png)

3. <span data-ttu-id="5367d-224">Clique com o botão direito do mouse na política antimalware recém-criada e selecione **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="5367d-224">Right-click on the newly created antimalware policy and select **Deploy**.</span></span>

    ![Imagem do painel de proteção de próxima geração10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. <span data-ttu-id="5367d-226">Direcionar a nova política antimalware para sua coleção Windows 10 e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5367d-226">Target the new antimalware policy to your Windows 10 collection and click **OK**.</span></span>

     ![Imagem do painel de proteção de próxima geração11](images/configmgr-select-collection.png)

<span data-ttu-id="5367d-228">Depois de concluir essa tarefa, você agora configurou com êxito o Windows Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="5367d-228">After completing this task, you now have successfully configured Windows Defender Antivirus.</span></span>

### <a name="attack-surface-reduction"></a><span data-ttu-id="5367d-229">Redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="5367d-229">Attack surface reduction</span></span>
<span data-ttu-id="5367d-230">O pilar de redução de superfície de ataque do Defender para Ponto de Extremidade inclui o conjunto de recursos que está disponível em Exploit Guard.</span><span class="sxs-lookup"><span data-stu-id="5367d-230">The attack surface reduction pillar of Defender for Endpoint includes the feature set that is available under Exploit Guard.</span></span> <span data-ttu-id="5367d-231">Regras de redução de superfície de ataque (ASR), Acesso Controlado a Pastas, Proteção de Rede e Proteção contra Exploração.</span><span class="sxs-lookup"><span data-stu-id="5367d-231">Attack surface reduction (ASR) rules, Controlled Folder Access, Network Protection and Exploit Protection.</span></span> 

<span data-ttu-id="5367d-232">Todos esses recursos fornecem um modo de auditoria e um modo de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="5367d-232">All these features provide an audit mode and a block mode.</span></span> <span data-ttu-id="5367d-233">No modo de auditoria, não há impacto no usuário final.</span><span class="sxs-lookup"><span data-stu-id="5367d-233">In audit mode there is no end-user impact.</span></span> <span data-ttu-id="5367d-234">Tudo o que ele faz é coletar telemetria adicional e torná-la disponível no Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="5367d-234">All it does is collect additional telemetry and make it available in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="5367d-235">O objetivo com uma implantação é mover passo a passo os controles de segurança para o modo de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="5367d-235">The goal with a deployment is to step-by-step move security controls into block mode.</span></span>

<span data-ttu-id="5367d-236">Para definir regras ASR no modo de auditoria:</span><span class="sxs-lookup"><span data-stu-id="5367d-236">To set ASR rules in Audit mode:</span></span>

1. <span data-ttu-id="5367d-237">No console do Microsoft Endpoint Configuration Manager, navegue até **Assets and Compliance Overview \> \> Endpoint Protection Windows Defender Exploit \> Guard** e escolha **Criar Política do Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="5367d-237">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

   ![Imagem do Microsoft Endpoint Configuration Manager console0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  <span data-ttu-id="5367d-239">Selecione **Redução de Superfície de Ataque**.</span><span class="sxs-lookup"><span data-stu-id="5367d-239">Select **Attack Surface Reduction**.</span></span>
   

3. <span data-ttu-id="5367d-240">De definir regras como **Auditoria e** clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="5367d-240">Set rules to **Audit** and click **Next**.</span></span>


    ![Imagem do console do Microsoft Endpoint Configuration Manager1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. <span data-ttu-id="5367d-242">Confirme a nova política do Exploit Guard clicando em **Next**.</span><span class="sxs-lookup"><span data-stu-id="5367d-242">Confirm the new Exploit Guard policy by clicking on **Next**.</span></span>

    ![Imagem do console do Microsoft Endpoint Configuration Manager2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. <span data-ttu-id="5367d-244">Depois que a política for criada, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="5367d-244">Once the policy is created click **Close**.</span></span>

    ![Imagem do console do Microsoft Endpoint Configuration Manager3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Imagem do console do Microsoft Endpoint Manager1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  <span data-ttu-id="5367d-247">Clique com o botão direito do mouse na política recém-criada e escolha **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="5367d-247">Right-click on the newly created policy and choose **Deploy**.</span></span>
    
    ![Imagem do console do Microsoft Endpoint Configuration Manager4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="5367d-249">Destino da política para a coleção recém-criada do Windows 10 e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5367d-249">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Imagem do console do Microsoft Endpoint Configuration Manager5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="5367d-251">Depois de concluir essa tarefa, agora você configurou com êxito as regras ASR no modo de auditoria.</span><span class="sxs-lookup"><span data-stu-id="5367d-251">After completing this task, you now have successfully configured ASR rules in audit mode.</span></span>  
  
<span data-ttu-id="5367d-252">A seguir estão etapas adicionais para verificar se as regras ASR são aplicadas corretamente aos pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="5367d-252">Below are additional steps to verify whether ASR rules are correctly applied to endpoints.</span></span> <span data-ttu-id="5367d-253">(Isso pode levar alguns minutos)</span><span class="sxs-lookup"><span data-stu-id="5367d-253">(This may take few minutes)</span></span>


1. <span data-ttu-id="5367d-254">Em um navegador da Web, navegue até <https://securitycenter.windows.com> .</span><span class="sxs-lookup"><span data-stu-id="5367d-254">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

2.  <span data-ttu-id="5367d-255">Selecione **Gerenciamento de configuração** no menu esquerdo.</span><span class="sxs-lookup"><span data-stu-id="5367d-255">Select **Configuration management** from left side menu.</span></span>

3. <span data-ttu-id="5367d-256">Clique **em Ir para atacar o gerenciamento de superfície** no painel gerenciamento de superfície de ataque.</span><span class="sxs-lookup"><span data-stu-id="5367d-256">Click **Go to attack surface management** in the Attack surface management panel.</span></span> 
    
    ![Imagem do gerenciamento de superfície de ataque](images/security-center-attack-surface-mgnt-tile.png)

4. <span data-ttu-id="5367d-258">Clique **na guia** Configuração em Relatórios de regras de redução de superfície de ataque.</span><span class="sxs-lookup"><span data-stu-id="5367d-258">Click **Configuration** tab in Attack surface reduction rules reports.</span></span> <span data-ttu-id="5367d-259">Ele mostra a visão geral da configuração de regras ASR e o status das regras ASR em cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5367d-259">It shows ASR rules configuration overview and ASR rules status on each devices.</span></span>

    ![Uma captura de tela de relatórios de regras de redução de superfície de ataque1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. <span data-ttu-id="5367d-261">Clique em cada dispositivo mostra detalhes de configuração das regras ASR.</span><span class="sxs-lookup"><span data-stu-id="5367d-261">Click each device shows configuration details of ASR rules.</span></span>

    ![Uma captura de tela de relatórios de regras de redução de superfície de ataque2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

<span data-ttu-id="5367d-263">Confira [Otimizar a implantação e as detecções de regras ASR](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)   para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="5367d-263">See [Optimize ASR rule deployment and detections](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)   for more details.</span></span>  


#### <a name="set-network-protection-rules-in-audit-mode"></a><span data-ttu-id="5367d-264">Definir regras de Proteção de Rede no modo de auditoria:</span><span class="sxs-lookup"><span data-stu-id="5367d-264">Set Network Protection rules in Audit mode:</span></span>
1. <span data-ttu-id="5367d-265">No console do Microsoft Endpoint Configuration Manager, navegue até **Assets and Compliance Overview \> \> Endpoint Protection Windows Defender Exploit \> Guard** e escolha **Criar Política do Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="5367d-265">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and  Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Um Gerenciador de Configuração do System Center de captura de tela1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="5367d-267">Selecione **Proteção de rede**.</span><span class="sxs-lookup"><span data-stu-id="5367d-267">Select **Network protection**.</span></span>

3. <span data-ttu-id="5367d-268">De definir a configuração como **Auditoria** e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="5367d-268">Set the setting to **Audit** and click **Next**.</span></span> 

    ![Uma captura de tela Do System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. <span data-ttu-id="5367d-270">Confirme a nova Política do Exploit Guard clicando em **Next**.</span><span class="sxs-lookup"><span data-stu-id="5367d-270">Confirm the new Exploit Guard Policy by clicking **Next**.</span></span>
    
    ![Uma captura de tela Exploit GUard policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="5367d-272">Depois que a política for criada, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="5367d-272">Once the policy is created click on **Close**.</span></span>

    ![Uma política exploit GUard de captura de tela2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="5367d-274">Clique com o botão direito do mouse na política recém-criada e escolha **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="5367d-274">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Uma captura de tela do Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="5367d-276">Selecione a política para a coleção recém-criada do Windows 10 e escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="5367d-276">Select the policy to the newly created Windows 10 collection and choose **OK**.</span></span>

    ![Uma captura de tela do Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



<span data-ttu-id="5367d-278">Depois de concluir essa tarefa, você agora configurou com êxito a Proteção de Rede no modo de auditoria.</span><span class="sxs-lookup"><span data-stu-id="5367d-278">After completing this task, you now have successfully configured Network Protection in audit mode.</span></span>

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a><span data-ttu-id="5367d-279">Para definir regras de Acesso Controlado a Pastas no modo de auditoria:</span><span class="sxs-lookup"><span data-stu-id="5367d-279">To set Controlled Folder Access rules in Audit mode:</span></span>

1. <span data-ttu-id="5367d-280">No console do Microsoft Endpoint Configuration Manager, navegue até **Assets and Compliance Overview \> \> Endpoint Protection Windows Defender Exploit \> Guard** e escolha **Criar Política do Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="5367d-280">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Captura de tela do Microsoft Endpoint Configuration Manager3](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="5367d-282">Selecione **Acesso controlado a pastas**.</span><span class="sxs-lookup"><span data-stu-id="5367d-282">Select **Controlled folder access**.</span></span>
    
3. <span data-ttu-id="5367d-283">De definir a configuração **como Auditoria e** clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="5367d-283">Set the configuration to **Audit** and click **Next**.</span></span>

    ![Captura de tela do Microsoft Endpoint Configuration Manager4](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. <span data-ttu-id="5367d-285">Confirme a nova Política do Exploit Guard clicando em **Next**.</span><span class="sxs-lookup"><span data-stu-id="5367d-285">Confirm the new Exploit Guard Policy by clicking on **Next**.</span></span>

    ![Captura de tela do Microsoft Endpoint Configuration Manager5](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="5367d-287">Depois que a política for criada, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="5367d-287">Once the policy is created click on **Close**.</span></span>

    ![Captura de tela do Microsoft Endpoint Configuration Manager6](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="5367d-289">Clique com o botão direito do mouse na política recém-criada e escolha **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="5367d-289">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Captura de tela do Microsoft Endpoint Configuration Manager7](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  <span data-ttu-id="5367d-291">Destino da política para a coleção recém-criada do Windows 10 e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5367d-291">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Captura de tela do Microsoft Endpoint Configuration Manager8](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="5367d-293">Agora você configurou com êxito o acesso controlado a pastas no modo de auditoria.</span><span class="sxs-lookup"><span data-stu-id="5367d-293">You have now successfully configured Controlled folder access in audit mode.</span></span>

## <a name="related-topic"></a><span data-ttu-id="5367d-294">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5367d-294">Related topic</span></span>
- [<span data-ttu-id="5367d-295">Integração usando o Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="5367d-295">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
