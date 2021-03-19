---
title: Comece com a Extensão de Conformidade da Microsoft (visualização)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Prepare-se e implante a Extensão de Conformidade da Microsoft.
ms.openlocfilehash: c6f56c65de6428374d912545db38337d34720c94
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838344"
---
# <a name="get-started-with-microsoft-compliance-extension-preview"></a><span data-ttu-id="80af1-103">Começar a usar a Extensão de Conformidade da Microsoft (prévia)</span><span class="sxs-lookup"><span data-stu-id="80af1-103">Get started with Microsoft Compliance Extension (preview)</span></span>

<span data-ttu-id="80af1-104">Use estes procedimentos para implementar a Extensão de Conformidade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="80af1-104">Use these procedures to roll out the Microsoft Compliance Extension.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="80af1-105">Antes de você começar</span><span class="sxs-lookup"><span data-stu-id="80af1-105">Before you begin</span></span>

<span data-ttu-id="80af1-106">Para usar a Extensão de Conformidade da Microsoft, o dispositivo deve estar integrado no ponto de extremidade da DLP.</span><span class="sxs-lookup"><span data-stu-id="80af1-106">To use Microsoft Compliance Extension, the device must be onboarded into endpoint DLP.</span></span> <span data-ttu-id="80af1-107">Para usar a extensão de conformidade da Microsoft, o dispositivo deve estar integrado no ponto de extremidade da DLP.</span><span class="sxs-lookup"><span data-stu-id="80af1-107">Review these articles if you are new to DLP or endpoint DLP</span></span>

- [<span data-ttu-id="80af1-108">Saiba mais sobre a Extensão de Conformidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="80af1-108">Learn about Microsoft Compliance Extension</span></span>](dlp-chrome-learn-about.md)
- [<span data-ttu-id="80af1-109">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="80af1-109">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="80af1-110">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="80af1-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="80af1-111">Criar uma política DLP a partir de um modelo</span><span class="sxs-lookup"><span data-stu-id="80af1-111">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
- [<span data-ttu-id="80af1-112">Saiba mais sobre a prevenção contra Perda de Dados de Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="80af1-112">Learn about endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="80af1-113">Introdução à Prevenção contra perda de dados do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="80af1-113">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="80af1-114">Ferramentas e métodos de integração para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="80af1-114">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
- [<span data-ttu-id="80af1-115">Definir as configurações de proxy do dispositivo e conexão à Internet para Ponto de extremidade da DLP</span><span class="sxs-lookup"><span data-stu-id="80af1-115">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)
- [<span data-ttu-id="80af1-116">Usando a Prevenção contra perda de dados de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="80af1-116">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="80af1-117">Licenciamento SKU/assinaturas</span><span class="sxs-lookup"><span data-stu-id="80af1-117">SKU/subscriptions licensing</span></span>

<span data-ttu-id="80af1-118">Antes de começar, você deve confirmar sua [assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e quaisquer complementos.</span><span class="sxs-lookup"><span data-stu-id="80af1-118">Before you get started, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="80af1-119">Para acessar e usar a funcionalidade do Endpoint DLP, você deve ter uma dessas assinaturas ou complementos.</span><span class="sxs-lookup"><span data-stu-id="80af1-119">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="80af1-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="80af1-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="80af1-121">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="80af1-121">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="80af1-122">Conformidade do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="80af1-122">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="80af1-123">Conformidade do Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="80af1-123">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="80af1-124">Governança e Proteção de Informações do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="80af1-124">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="80af1-125">Governança e Proteção de Informações do Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="80af1-125">Microsoft 365 A5 information protection and governance</span></span>

<span data-ttu-id="80af1-126">Para obter orientações de licenciamento detalhadas, confira as [orientações de licenciamento do Microsoft 365 para segurança e conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span><span class="sxs-lookup"><span data-stu-id="80af1-126">For detailed licensing guidance, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

- <span data-ttu-id="80af1-127">Sua organização deve ser licenciada para ponto de extremidade da DLP</span><span class="sxs-lookup"><span data-stu-id="80af1-127">Your org must be licensed for Endpoint DLP</span></span>
- <span data-ttu-id="80af1-128">Seus dispositivos devem estar executando o Windows 10 x64 build 1809 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="80af1-128">Your devices must be running Windows 10 x64 build 1809 or later.</span></span>
- <span data-ttu-id="80af1-129">O dispositivo deve ter a versão do cliente Antimalware 4.18.2101.9 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="80af1-129">The device must have Antimalware Client Version is 4.18.2101.9 or later.</span></span> <span data-ttu-id="80af1-130">Verifique sua versão atual abrindo o aplicativo **Segurança do Windows**, selecione o ícone **Configurações** e selecione **Sobre**.</span><span class="sxs-lookup"><span data-stu-id="80af1-130">Check your current version by opening **Windows Security** app, select the **Settings** icon, and then select **About**.</span></span>


### <a name="permissions"></a><span data-ttu-id="80af1-131">Permissões</span><span class="sxs-lookup"><span data-stu-id="80af1-131">Permissions</span></span>

<span data-ttu-id="80af1-132">Os dados do Ponto de extremidade DLP podem ser exibidos no [Explorador de atividades](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="80af1-132">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="80af1-133">Existem sete funções que concedem permissão ao explorador de atividades, a conta que você usa para acessar os dados deve ser membro de qualquer uma delas.</span><span class="sxs-lookup"><span data-stu-id="80af1-133">There are seven roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="80af1-134">Administrador global</span><span class="sxs-lookup"><span data-stu-id="80af1-134">Global admin</span></span>
- <span data-ttu-id="80af1-135">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="80af1-135">Compliance admin</span></span>
- <span data-ttu-id="80af1-136">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="80af1-136">Security admin</span></span>
- <span data-ttu-id="80af1-137">Administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="80af1-137">Compliance data admin</span></span>
- <span data-ttu-id="80af1-138">Leitor global</span><span class="sxs-lookup"><span data-stu-id="80af1-138">Global reader</span></span>
- <span data-ttu-id="80af1-139">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="80af1-139">Security reader</span></span>
- <span data-ttu-id="80af1-140">Leitor de relatórios</span><span class="sxs-lookup"><span data-stu-id="80af1-140">Reports reader</span></span>

### <a name="overall-installation-workflow"></a><span data-ttu-id="80af1-141">Fluxo de trabalho geral de instalação</span><span class="sxs-lookup"><span data-stu-id="80af1-141">Overall installation workflow</span></span>

<span data-ttu-id="80af1-142">Implantar a Extensão de Conformidade da Microsoft é um processo de várias fases.</span><span class="sxs-lookup"><span data-stu-id="80af1-142">Deploying Microsoft Compliance Extension is a multi-phase process.</span></span> <span data-ttu-id="80af1-143">Você pode escolher instalar em uma máquina por vez ou usar o Microsoft Endpoint Manager ou a Política de Grupo para implantações em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="80af1-143">You can choose to install on one machine at a time, or use Microsoft Endpoint Manager or Group Policy for organization-wide deployments.</span></span>

1. <span data-ttu-id="80af1-144">[Prepare seus dispositivos](#prepare-your-devices).</span><span class="sxs-lookup"><span data-stu-id="80af1-144">[Prepare your devices](#prepare-your-devices).</span></span>
2. [<span data-ttu-id="80af1-145">Configuração Básica de Selfhost de Máquina Única</span><span class="sxs-lookup"><span data-stu-id="80af1-145">Basic Setup Single Machine Selfhost</span></span>](#basic-setup-single-machine-selfhost)
3. [<span data-ttu-id="80af1-146">Implantar usando o Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="80af1-146">Deploy using Microsoft Endpoint Manager</span></span>](#deploy-using-microsoft-endpoint-manager)
4. [<span data-ttu-id="80af1-147">Implantar usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="80af1-147">Deploy using Group Policy</span></span>](#deploy-using-group-policy)
5. [<span data-ttu-id="80af1-148">Teste a Extensão</span><span class="sxs-lookup"><span data-stu-id="80af1-148">Test the Extension</span></span>](#test-the-extension)
6. [<span data-ttu-id="80af1-149">Use o painel de gerenciamento de alertas para visualizar os alertas da DLP do Chrome</span><span class="sxs-lookup"><span data-stu-id="80af1-149">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)
7. <span data-ttu-id="80af1-150">[Visualização de dados da DLP do Chrome](#viewing-chrome-dlp-data-in-activity-explorer) no explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="80af1-150">[Viewing Chrome DLP data in activity explorer](#viewing-chrome-dlp-data-in-activity-explorer)</span></span> 

### <a name="prepare-infrastructure"></a><span data-ttu-id="80af1-151">Preparar a infraestrutura</span><span class="sxs-lookup"><span data-stu-id="80af1-151">Prepare infrastructure</span></span>

<span data-ttu-id="80af1-152">Se você estiver implementando a extensão de conformidade da Microsoft para todos os dispositivos Windows 10 monitorados, deverá remover o Google Chrome das listas de aplicativos e navegadores não permitidos.</span><span class="sxs-lookup"><span data-stu-id="80af1-152">If you are rolling out the Microsoft Compliance Extension to all your monitored Windows 10 devices, you should remove Google Chrome from the unallowed app and unallowed browser lists.</span></span> <span data-ttu-id="80af1-153">Para obter mais informações, confira [Navegadores não permitidos](endpoint-dlp-using.md#unallowed-browsers).</span><span class="sxs-lookup"><span data-stu-id="80af1-153">For more information, see [Unallowed browsers](endpoint-dlp-using.md#unallowed-browsers).</span></span> <span data-ttu-id="80af1-154">Se você estiver implementando apenas para alguns dispositivos, poderá deixar o Chrome no navegador não permitido ou nas listas de aplicativos não permitidos.</span><span class="sxs-lookup"><span data-stu-id="80af1-154">If you are only rolling it out to a few devices, you can leave Chrome on the unallowed browser or unallowed app lists.</span></span> <span data-ttu-id="80af1-155">A extensão de conformidade da Microsoft contornará as restrições de ambas as listas dos computadores onde está instalada.</span><span class="sxs-lookup"><span data-stu-id="80af1-155">The Microsoft Compliance Extension will bypass the restrictions of both lists for those computers where it is installed.</span></span>  

### <a name="prepare-your-devices"></a><span data-ttu-id="80af1-156">Preparar os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="80af1-156">Prepare your devices</span></span>

1. <span data-ttu-id="80af1-157">Use os procedimentos nestes tópicos para integrar seus dispositivos:</span><span class="sxs-lookup"><span data-stu-id="80af1-157">Use the procedures in these topics to onboard your devices:</span></span>
    1. [<span data-ttu-id="80af1-158">Introdução à Prevenção contra perda de dados do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="80af1-158">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
    1. [<span data-ttu-id="80af1-159">Ferramentas e métodos de integração para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="80af1-159">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
    1. [<span data-ttu-id="80af1-160">Definir as configurações de proxy do dispositivo e conexão à Internet para Ponto de extremidade da DLP</span><span class="sxs-lookup"><span data-stu-id="80af1-160">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a><span data-ttu-id="80af1-161">Configuração Básica de Selfhost de Máquina Única</span><span class="sxs-lookup"><span data-stu-id="80af1-161">Basic Setup Single Machine Selfhost</span></span>

<span data-ttu-id="80af1-162">Este e o método recomendado.</span><span class="sxs-lookup"><span data-stu-id="80af1-162">This is the recommended method.</span></span> 

1. <span data-ttu-id="80af1-163">Entre no computador Windows 10 no qual deseja instalar a extensão de conformidade da Microsoft e execute este script do PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="80af1-163">Sign in to the Windows 10 computer on which you want to install the Microsoft Compliance Extension on, and run this PowerShell script as an administrator.</span></span> 

   ```powershell
   Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
   ``` 

2.  <span data-ttu-id="80af1-164">Navegue até a [Extensão de Conformidade da Microsoft - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).</span><span class="sxs-lookup"><span data-stu-id="80af1-164">Navigate to [Microsoft Compliance Extension - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).</span></span>

3.  <span data-ttu-id="80af1-165">Instale a extensão usando as instruções na página da Chrome Web Store.</span><span class="sxs-lookup"><span data-stu-id="80af1-165">Install the extension using the instructions on the Chrome Web Store page.</span></span>

### <a name="deploy-using-microsoft-endpoint-manager"></a><span data-ttu-id="80af1-166">Implantar usando o Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="80af1-166">Deploy using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="80af1-167">Use este método de configuração para implantações em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="80af1-167">Use this setup method for organization-wide deployments.</span></span>


##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a><span data-ttu-id="80af1-168">Habilitando a Chave de Registro Exigida por meio do Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="80af1-168">Enabling Required Registry Key via Microsoft Endpoint Manager</span></span>

1.  <span data-ttu-id="80af1-169">Crie um script Windows PowerShell com o seguinte conteúdo:</span><span class="sxs-lookup"><span data-stu-id="80af1-169">Create a PowerShell script with the following contents:</span></span>

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2.  <span data-ttu-id="80af1-170">Entre no [Centro de Administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="80af1-170">Sign in to the [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com).</span></span>

3.  <span data-ttu-id="80af1-171">Navegue até **Dispositivos** > **Scripts** e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="80af1-171">Navigate to **Devices** > **Scripts** and select **Add**.</span></span>

4.  <span data-ttu-id="80af1-172">Navegue até o local do script criado quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="80af1-172">Browse to the location of the script created when prompted.</span></span>

5.  <span data-ttu-id="80af1-173">Selecione as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="80af1-173">Select the following settings:</span></span>
    1. <span data-ttu-id="80af1-174">Execute este script usando as credenciais de logon: SIM</span><span class="sxs-lookup"><span data-stu-id="80af1-174">Run this script using the logged-on credentials: YES</span></span>
    1. <span data-ttu-id="80af1-175">Aplicar verificação de assinatura de script: NÃO</span><span class="sxs-lookup"><span data-stu-id="80af1-175">Enforce script signature check: NO</span></span>
    1. <span data-ttu-id="80af1-176">Execute o script em Windows PowerShell Host de 64 bits: SIM</span><span class="sxs-lookup"><span data-stu-id="80af1-176">Run script in 64-bit PowerShell Host: YES</span></span>

6.  <span data-ttu-id="80af1-177">Selecione os grupos de dispositivos adequados e aplique a política.</span><span class="sxs-lookup"><span data-stu-id="80af1-177">Select the proper device groups and apply the policy.</span></span>

#### <a name="microsoft-endpoint-manager-force-install-steps"></a><span data-ttu-id="80af1-178">Etapas de instalação forçada do Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="80af1-178">Microsoft Endpoint Manager Force Install Steps</span></span>

<span data-ttu-id="80af1-179">Antes de adicionar a extensão de Conformidade da Microsoft à lista de Extensões de instalação forçada, é importante ingerir o Chrome ADMX.</span><span class="sxs-lookup"><span data-stu-id="80af1-179">Before adding the Microsoft Compliance Extension to the list of force-installed extensions, it is important to ingest the Chrome ADMX.</span></span> <span data-ttu-id="80af1-180">As etapas para esse processo no Microsoft Endpoint Manager são documentadas pelo Google: [Gerenciar o Navegador Chrome com o Microsoft Intune - Ajuda do Google Chrome Empresa](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).</span><span class="sxs-lookup"><span data-stu-id="80af1-180">Steps for this process in Microsoft Endpoint Manager are documented by Google: [Manage Chrome Browser with Microsoft Intune - Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).</span></span>

 <span data-ttu-id="80af1-181">Depois de ingerir o ADMX, as etapas abaixo podem ser seguidas para criar um perfil de configuração para esta extensão.</span><span class="sxs-lookup"><span data-stu-id="80af1-181">After ingesting the ADMX, the steps below can be followed to create a configuration profile for this extension.</span></span>

1.  <span data-ttu-id="80af1-182">Entre no Centro de Administração do Microsoft Endpoint Manager (https://endpoint.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="80af1-182">Sign in to the Microsoft Endpoint Manager Admin Center (https://endpoint.microsoft.com).</span></span>

2.  <span data-ttu-id="80af1-183">Navegue até Perfis de Configuração.</span><span class="sxs-lookup"><span data-stu-id="80af1-183">Navigate to Configuration Profiles.</span></span>

3.  <span data-ttu-id="80af1-184">Selecione **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="80af1-184">Select **Create Profile**.</span></span>

4.  <span data-ttu-id="80af1-185">Selecione **Windows 10** como plataforma.</span><span class="sxs-lookup"><span data-stu-id="80af1-185">Select **Windows 10** as the platform.</span></span>

5.  <span data-ttu-id="80af1-186">Selecione **Personalizar** como tipo de perfil.</span><span class="sxs-lookup"><span data-stu-id="80af1-186">Select **Custom** as profile type.</span></span>

6.  <span data-ttu-id="80af1-187">Selecione a guia **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="80af1-187">Select the **Settings** tab.</span></span>

7.  <span data-ttu-id="80af1-188">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="80af1-188">Select **Add**.</span></span>

8.  <span data-ttu-id="80af1-189">Insira as seguintes informações de política.</span><span class="sxs-lookup"><span data-stu-id="80af1-189">Enter the following policy information.</span></span>
    
    <span data-ttu-id="80af1-190">OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`</span><span class="sxs-lookup"><span data-stu-id="80af1-190">OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`</span></span><br/>
    <span data-ttu-id="80af1-191">Tipo de dados: `String`</span><span class="sxs-lookup"><span data-stu-id="80af1-191">Data type: `String`</span></span><br/>
    <span data-ttu-id="80af1-192">Valor: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`</span><span class="sxs-lookup"><span data-stu-id="80af1-192">Value: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`</span></span>

9.  <span data-ttu-id="80af1-193">Clique em criar.</span><span class="sxs-lookup"><span data-stu-id="80af1-193">Click create.</span></span>

### <a name="deploy-using-group-policy"></a><span data-ttu-id="80af1-194">Implantar usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="80af1-194">Deploy using Group Policy</span></span>

<span data-ttu-id="80af1-195">Se não quiser usar o Microsoft Endpoint Manager, você pode usar políticas de grupo para implantar a Extensão de Conformidade da Microsoft em sua organização</span><span class="sxs-lookup"><span data-stu-id="80af1-195">If you don't want to use Microsoft Endpoint Manager, you can use group policies to deploy the Microsoft Compliance Extension across your organization</span></span>

1. <span data-ttu-id="80af1-196">Seus dispositivos devem ser gerenciáveis por meio da Política de Grupo e você precisa importar todos os ADMXs do Chrome para o Armazenamento Central de Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="80af1-196">Your devices must be manageable via Group Policy, and you need to import all Chrome ADMXs into the Group Policy Central Store.</span></span> <span data-ttu-id="80af1-197">Para obter mais informações, confira [Como criar e gerenciar o Repositório Central para Modelos Administrativos de Política de Grupo no Windows](https://docs.microsoft.com/troubleshoot/windows-client/group-policy/create-and-manage-central-store).</span><span class="sxs-lookup"><span data-stu-id="80af1-197">For more information, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://docs.microsoft.com/troubleshoot/windows-client/group-policy/create-and-manage-central-store).</span></span>

2.  <span data-ttu-id="80af1-198">Crie um script do PowerShell usando este comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="80af1-198">Create a PowerShell script using this PowerShell command:</span></span>

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

3.  <span data-ttu-id="80af1-199">Abra o **Console de Gerenciamento de Política de Grupo** e navegue até sua unidade organizacional (UO).</span><span class="sxs-lookup"><span data-stu-id="80af1-199">Open the **Group Policy Management Console** and navigate to your organizational unit (OU).</span></span>

4.  <span data-ttu-id="80af1-200">Clique com o botão direito e selecione **Criar um GPO neste domínio e Vinculá-lo aqui**.</span><span class="sxs-lookup"><span data-stu-id="80af1-200">Right-click and select **Create a GPO in this domain and Link it here**.</span></span> <span data-ttu-id="80af1-201">Quando solicitado, atribua um nome descritivo a este objeto de política de grupo (GPO) e termine de criá-lo.</span><span class="sxs-lookup"><span data-stu-id="80af1-201">When prompted, assign a descriptive name to this group policy object (GPO) and finish creating it.</span></span>

5.  <span data-ttu-id="80af1-202">Clique com o botão direito no GPO e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="80af1-202">Right-click the GPO and select **Edit**.</span></span>

6.  <span data-ttu-id="80af1-203">Vá para **Configuração do Computador** > **Preferências** > **Configurações do Painel de Controle** > **Tarefas Agendadas**.</span><span class="sxs-lookup"><span data-stu-id="80af1-203">Go to **Computer Configuration** > **Preferences** > **Control Panel Settings** > **Scheduled Tasks**.</span></span>

7.  <span data-ttu-id="80af1-204">Criar uma nova tarefa imediata clicando com o botão direito e selecionando **Nova** > **Tarefa Imediata (pelo menos Windows 7)**.</span><span class="sxs-lookup"><span data-stu-id="80af1-204">Create a new immediate task by selecting right-clicking and selecting **New** > **Immediate Task (At least Windows 7)**.</span></span>

8.  <span data-ttu-id="80af1-205">Dê um nome e uma descrição à tarefa.</span><span class="sxs-lookup"><span data-stu-id="80af1-205">Give the task a name & description.</span></span>

9.  <span data-ttu-id="80af1-206">Escolha a conta correspondente para executar a tarefa imediata, por exemplo NT Authority</span><span class="sxs-lookup"><span data-stu-id="80af1-206">Choose the corresponding account to run the immediate task, for example NT Authority</span></span>

10. <span data-ttu-id="80af1-207">Selecione **Executar com privilégios mais altos**.</span><span class="sxs-lookup"><span data-stu-id="80af1-207">Select **Run with highest privileges**.</span></span>

11. <span data-ttu-id="80af1-208">Configure a política para Windows 10.</span><span class="sxs-lookup"><span data-stu-id="80af1-208">Configure the policy for Windows 10.</span></span>

12. <span data-ttu-id="80af1-209">Na guia **Ações**, selecione a ação **Iniciar um programa**.</span><span class="sxs-lookup"><span data-stu-id="80af1-209">In the **Actions** tab, select the action **Start a program**.</span></span>

13. <span data-ttu-id="80af1-210">Insira o caminho para o Programa/Script criado na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="80af1-210">Enter the path to the Program/Script created in Step 1.</span></span>

14. <span data-ttu-id="80af1-211">Selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="80af1-211">Select **Apply**.</span></span>

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a><span data-ttu-id="80af1-212">Adicionando a Extensão do Chrome à Lista ForceInstall</span><span class="sxs-lookup"><span data-stu-id="80af1-212">Adding the Chrome Extension to the ForceInstall List</span></span>

1.  <span data-ttu-id="80af1-213">No Editor de Gerenciamento de Política de Grupo, navegue até sua UO.</span><span class="sxs-lookup"><span data-stu-id="80af1-213">In the Group Policy Management Editor, navigate to your OU.</span></span>

2.  <span data-ttu-id="80af1-214">Expanda o seguinte caminho **Configuração de Computador/Usuário** > **Políticas** > **Modelos Administrativos** > **Modelos Administrativos Clássicos** > **Google** > **Google Chrome** > **Extensões**.</span><span class="sxs-lookup"><span data-stu-id="80af1-214">Expand the following path **Computer/User configuration** > **Policies** > **Administrative templates** > **Classic administrative templates** > **Google** > **Google Chrome** > **Extensions**.</span></span> <span data-ttu-id="80af1-215">Este caminho pode variar dependendo da sua configuração.</span><span class="sxs-lookup"><span data-stu-id="80af1-215">This path may vary depending on your configuration.</span></span>

3.  <span data-ttu-id="80af1-216">Selecione **Configurar a lista de extensões instaladas por força**.</span><span class="sxs-lookup"><span data-stu-id="80af1-216">Select **Configure the list of force-installed extensions**.</span></span>

4.  <span data-ttu-id="80af1-217">Clique com o botão direito do mouse e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="80af1-217">Right click and select **Edit**.</span></span>

5.  <span data-ttu-id="80af1-218">Selecione **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="80af1-218">Select **Enabled**.</span></span>

6.  <span data-ttu-id="80af1-219">Selecione **Mostrar**.</span><span class="sxs-lookup"><span data-stu-id="80af1-219">Select **Show**.</span></span>

7.  <span data-ttu-id="80af1-220">Em **valor**, adicione a seguinte entrada: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span><span class="sxs-lookup"><span data-stu-id="80af1-220">Under **Value**, add the following entry: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span></span>

8.  <span data-ttu-id="80af1-221">Selecione **OK** e, em seguida, **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="80af1-221">Select **OK** and then **Apply**.</span></span>

### <a name="test-the-extension"></a><span data-ttu-id="80af1-222">Teste a Extensão</span><span class="sxs-lookup"><span data-stu-id="80af1-222">Test the Extension</span></span>

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a><span data-ttu-id="80af1-223">Faça upload para o serviço de nuvem ou acesse por navegadores não permitidos Saída da Nuvem</span><span class="sxs-lookup"><span data-stu-id="80af1-223">Upload to cloud service, or access by unallowed browsers Cloud Egress</span></span>  

1. <span data-ttu-id="80af1-224">Crie ou obtenha um item confidencial e tente fazer upload de um arquivo para um dos domínios de serviço restritos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="80af1-224">Create or get a sensitive item and, try to upload a file to one of your organization’s restricted service domains.</span></span> <span data-ttu-id="80af1-225">Os dados confidenciais devem corresponder a um de nossos [Tipos de Informações Confidenciais](sensitive-information-type-entity-definitions.md) integrados ou a um dos tipos de informações confidenciais da sua organização.</span><span class="sxs-lookup"><span data-stu-id="80af1-225">The sensitive data must match one of our built-in [Sensitive Info Types](sensitive-information-type-entity-definitions.md), or one of your organization’s sensitive information types.</span></span> <span data-ttu-id="80af1-226">Você deve receber uma notificação do sistema DLP no dispositivo que está testando, mostrando que essa ação não é permitida quando o arquivo é aberto.</span><span class="sxs-lookup"><span data-stu-id="80af1-226">You should get a DLP toast notification on the device you are testing from that shows that this action is not allowed when the file is open.</span></span>

#### <a name="testing-other-dlp-scenarios-in-chrome"></a><span data-ttu-id="80af1-227">Testar outros cenários DLP no Chrome</span><span class="sxs-lookup"><span data-stu-id="80af1-227">Testing other DLP scenarios in Chrome</span></span> 

<span data-ttu-id="80af1-228">Agora que você removeu o Chrome da lista de navegadores/aplicativos não permitidos, pode testar os cenários abaixo para confirmar se o comportamento atende aos requisitos de sua organização:</span><span class="sxs-lookup"><span data-stu-id="80af1-228">Now that you’ve removed Chrome from the disallowed browsers/apps list, you can test the scenarios below to confirm the behavior meets your organization’s requirements:</span></span>

- <span data-ttu-id="80af1-229">Copie dados de um item confidencial para outro documento usando a Área de transferência</span><span class="sxs-lookup"><span data-stu-id="80af1-229">Copy data from a sensitive item to another document using the Clipboard</span></span>
    - <span data-ttu-id="80af1-230">Para testar, abra um arquivo que está protegido contra ações de copiar para a área de transferência no navegador Chrome e tente copiar os dados do arquivo.</span><span class="sxs-lookup"><span data-stu-id="80af1-230">To test, open a file that is protected against copy to clipboard actions in the Chrome browser and attempt to copy data from the file.</span></span>
    - <span data-ttu-id="80af1-231">Resultado esperado: uma notificação do sistema DLP mostrando que esta ação não é permitida quando o arquivo está aberto.</span><span class="sxs-lookup"><span data-stu-id="80af1-231">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="80af1-232">Imprimir documentos</span><span class="sxs-lookup"><span data-stu-id="80af1-232">Print a document</span></span>
    - <span data-ttu-id="80af1-233">Para testar, abra um arquivo que esteja protegido contra ações de impressão no navegador Chrome e tente imprimir o arquivo.</span><span class="sxs-lookup"><span data-stu-id="80af1-233">To test, open a file that is protected against print actions in the Chrome browser and attempt to print the file.</span></span>
    - <span data-ttu-id="80af1-234">Resultado esperado: uma notificação do sistema DLP mostrando que esta ação não é permitida quando o arquivo está aberto.</span><span class="sxs-lookup"><span data-stu-id="80af1-234">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="80af1-235">Copiar para Mídia Removível USB</span><span class="sxs-lookup"><span data-stu-id="80af1-235">Copy to USB Removeable Media</span></span>
    - <span data-ttu-id="80af1-236">Para testar, tente salvar o arquivo em um armazenamento de mídia removível.</span><span class="sxs-lookup"><span data-stu-id="80af1-236">To test, try to save the file to a removeable media storage.</span></span>
    - <span data-ttu-id="80af1-237">Resultado esperado: uma notificação do sistema DLP mostrando que esta ação não é permitida quando o arquivo está aberto.</span><span class="sxs-lookup"><span data-stu-id="80af1-237">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="80af1-238">Copiar para Compartilhamento de Rede</span><span class="sxs-lookup"><span data-stu-id="80af1-238">Copy to Network Share</span></span>
    - <span data-ttu-id="80af1-239">Para testar, tente salvar o arquivo em um compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="80af1-239">To test, try to save the file to a network share.</span></span>
    - <span data-ttu-id="80af1-240">Resultado esperado: uma notificação do sistema DLP mostrando que esta ação não é permitida quando o arquivo está aberto.</span><span class="sxs-lookup"><span data-stu-id="80af1-240">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>


### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a><span data-ttu-id="80af1-241">Usar o painel de gerenciamento de alertas para visualizar os alertas do Chrome DLP</span><span class="sxs-lookup"><span data-stu-id="80af1-241">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>

1. <span data-ttu-id="80af1-242">Abra a página **Prevenção contra perda de dados** no [Centro de Conformidade do Microsoft 365](https://compliance.microsoft.com) e selecione **Alertas**.</span><span class="sxs-lookup"><span data-stu-id="80af1-242">Open the **Data loss prevention** page in the [Microsoft 365 Compliance center](https://compliance.microsoft.com) and select **Alerts**.</span></span>

2. <span data-ttu-id="80af1-243">Confira os procedimentos em [Como configurar e exibir alertas para suas políticas de DLP](dlp-configure-view-alerts-policies.md) para exibir alertas das políticas de DLP do Ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="80af1-243">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a><span data-ttu-id="80af1-244">Visualização de dados do Chrome DLP no explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="80af1-244">Viewing Chrome DLP data in activity explorer</span></span>

1. <span data-ttu-id="80af1-245">Abra a [página de classificação de dados](https://compliance.microsoft.com/dataclassification?viewid=overview) para o seu domínio no Centro de conformidade do Microsoft 365 e escolha **Explorador de atividades**.</span><span class="sxs-lookup"><span data-stu-id="80af1-245">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose **Activity explorer**.</span></span>

2. <span data-ttu-id="80af1-246">Confira os procedimentos no [Comece a usar o Explorador de atividades](data-classification-activity-explorer.md) para acessar e filtrar todos os dados dos dispositivos de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="80af1-246">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="80af1-247">![filtro do explorador de atividades para dispositivos de ponto de extremidade](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="80af1-247">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

### <a name="known-issues-and-limitations"></a><span data-ttu-id="80af1-248">Limitações e problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="80af1-248">Known Issues and Limitations</span></span>

1. <span data-ttu-id="80af1-249">A imposição Arrastar e soltar para carregamento de pasta não é compatível.</span><span class="sxs-lookup"><span data-stu-id="80af1-249">Drag & Drop enforcement for folder upload is not supported.</span></span>
2. <span data-ttu-id="80af1-250">A imposição de substituição de bloqueio para saída da nuvem não é compatível.</span><span class="sxs-lookup"><span data-stu-id="80af1-250">Block Override enforcement for cloud egress is not supported.</span></span>
3. <span data-ttu-id="80af1-251">O modo anônimo não é compatível e deve ser desabilitado.</span><span class="sxs-lookup"><span data-stu-id="80af1-251">Incognito mode is not supported and must be disabled.</span></span>

## <a name="next-steps"></a><span data-ttu-id="80af1-252">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="80af1-252">Next steps</span></span>
<span data-ttu-id="80af1-253">Agora que você tem dispositivos integrados e pode exibir os dados de atividade no Explorador de atividades, você está pronto para prosseguir para a próxima etapa na qual você cria políticas DLP que protegem seus itens confidenciais.</span><span class="sxs-lookup"><span data-stu-id="80af1-253">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="80af1-254">Usando a Prevenção contra perda de dados de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="80af1-254">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="80af1-255">Confira também</span><span class="sxs-lookup"><span data-stu-id="80af1-255">See also</span></span>

- [<span data-ttu-id="80af1-256">Saiba mais sobre a Prevenção contra perda de dados do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="80af1-256">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="80af1-257">Usando a prevenção contra perda de dados do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="80af1-257">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="80af1-258">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="80af1-258">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="80af1-259">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="80af1-259">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="80af1-260">Começar a usar o Explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="80af1-260">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="80af1-261">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="80af1-261">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="80af1-262">Ferramentas e métodos de integração para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="80af1-262">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="80af1-263">Assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="80af1-263">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="80af1-264">Dispositivos associados ao Microsoft Azure AD</span><span class="sxs-lookup"><span data-stu-id="80af1-264">Azure AD joined devices</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="80af1-265">Baixar o novo Microsoft Edge baseado em Chromium</span><span class="sxs-lookup"><span data-stu-id="80af1-265">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
