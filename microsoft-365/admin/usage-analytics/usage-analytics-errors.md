---
title: Solucionando problemas de análise de uso do Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Saiba como solucionar problemas com o aplicativo de modelo de análise de uso do Microsoft 365.
ms.openlocfilehash: 7164aa246a79a8d8c5aa50d995b53b6221003c01
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212144"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="1c6f3-103">Solucionando problemas de análise de uso do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1c6f3-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="1c6f3-104">Explore a seguinte lista de mensagens de erro para obter ajuda com os problemas mais comuns com a análise de uso do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="1c6f3-105">Não somo capazes de processar seu pedido.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-105">We are unable to process your request.</span></span> <span data-ttu-id="1c6f3-106">Você deve primeiro inscrever-se nesses dados do centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1c6f3-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="1c6f3-107">**Código de erro:** 422</span><span class="sxs-lookup"><span data-stu-id="1c6f3-107">**Error Code :** 422</span></span> 
  
 <span data-ttu-id="1c6f3-108">**Onde você verá esta mensagem:** No Power BI quando você estiver se conectando ao aplicativo de modelo de análise de uso do Microsoft 365 ou ao chamar diretamente as APIs de relatórios da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="1c6f3-109">**Causa:** Antes de poder se conectar ao aplicativo, você precisa inscrever-se nos dados do centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-109">**Cause:** Before you can connect to the app you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="1c6f3-110">Se esta etapa não for executada primeiro, você não poderá se conectar ao aplicativo de modelo, mesmo que forneça sua ID de locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant id.</span></span> 
  
 <span data-ttu-id="1c6f3-111">**Para corrigir esse erro:** Para inscrever-se nos dados, acesse o \> **Centro** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Administração e localize</a> o bloco de análise de uso do Microsoft 365 na página principal do painel.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="1c6f3-112">Selecione o **botão introdução** **e,** em seguida, no painel **relatórios** que é aberto, ative a configuração **disponibilizar dados para análise de uso do Microsoft 365 para Power bi** .</span><span class="sxs-lookup"><span data-stu-id="1c6f3-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="1c6f3-113">Estamos processando seus dados</span><span class="sxs-lookup"><span data-stu-id="1c6f3-113">We are processing your data</span></span>

 <span data-ttu-id="1c6f3-114">**Onde você verá esta mensagem:** No bloco de **análise de uso do microsoft 365** , no painel de **uso** do centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="1c6f3-115">**Causa:** Quando você [optar por ver dados no aplicativo de modelo](enable-usage-analytics.md) do centro de administração do Microsoft 365, o sistema Microsoft 365 começará a gerar dados de uso históricos para sua organização.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="1c6f3-116">Dependendo do tamanho do seu locatário, este passo pode levar entre 2 e 48 horas.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="1c6f3-117">**Para corrigir isso:** Seja paciente, mas se a mensagem não mudar para **seus dados estiver pronta** após 3 dias, [entre em contato com o suporte da Microsoft 365 para empresas](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="1c6f3-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="1c6f3-118">Não podemos processar seu pedido neste momento.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="1c6f3-119">Ainda estamos preparando os dados para sua organização</span><span class="sxs-lookup"><span data-stu-id="1c6f3-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="1c6f3-120">**Código de erro:** 423</span><span class="sxs-lookup"><span data-stu-id="1c6f3-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="1c6f3-121">**Onde você verá esta mensagem:** No Power BI quando você estiver se conectando ao aplicativo de modelo de análise de uso do Microsoft 365 ou ao chamar diretamente as APIs de relatórios da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-121">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="1c6f3-122">**Causa:** Quando você [optar por ver dados no aplicativo de modelo](enable-usage-analytics.md) a partir do centro de administração, o sistema Microsoft 365 começa a gerar dados de uso históricos para sua organização.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="1c6f3-123">Dependendo do tamanho do seu locatário, este passo pode levar entre 2 e 48 horas.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-123">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="1c6f3-124">**Para corrigir isso:** Seja paciente, mas se a mensagem não mudar para **seus dados estiver pronta** até 3 dias desde o início, [entre em contato com o suporte da Microsoft 365 para empresas](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="1c6f3-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="1c6f3-125">O ID do locatário que você forneceu não está no formato correto</span><span class="sxs-lookup"><span data-stu-id="1c6f3-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="1c6f3-126">**Código de erro:** 400</span><span class="sxs-lookup"><span data-stu-id="1c6f3-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="1c6f3-127">**Onde você verá esta mensagem:** No Power BI quando você estiver se conectando ao aplicativo de modelo de análise de uso do Microsoft 365 ou ao chamar diretamente as APIs de relatórios da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-127">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="1c6f3-p107">**Causa:** A ID do locatário é um guid e tem que estar no formato xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Se você inserir qualquer outra sequência na caixa de entrada do locatário, você receberá esse erro.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-p107">**Cause:** The tenant id is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. If you enter any other string in the tenant input box you will get this error.</span></span> 
  
 <span data-ttu-id="1c6f3-130">**Para corrigir esse erro:** Vá para \> o centro de administração de **relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">uso</a> e localize o bloco de análise de uso do Microsoft 365 na página de painel principal.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="1c6f3-131">A ID do locatário está listada no bloco.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-131">The tenant id is listed on the tile.</span></span> <span data-ttu-id="1c6f3-132">Você pode copiá-lo daqui e colá-lo na caixa de diálogo para se conectar ao aplicativo de modelo.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="1c6f3-133">A ID do locatário fornecida não é reconhecida pelo nosso sistema</span><span class="sxs-lookup"><span data-stu-id="1c6f3-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="1c6f3-134">**Código de erro:** 404</span><span class="sxs-lookup"><span data-stu-id="1c6f3-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="1c6f3-135">**Onde você verá esta mensagem:** No Power BI quando você estiver se conectando ao aplicativo de modelo de análise de uso do Microsoft 365 ou ao chamar diretamente as APIs de relatórios da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="1c6f3-136">**Causa:** A ID do locatário fornecida não é válida ou não existe.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-136">**Cause:** The tenant id you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="1c6f3-137">**Para corrigir esse erro:** Vá para \> o centro de administração de **relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">uso</a> e localize o bloco de análise de uso do Microsoft 365 na página de painel principal.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="1c6f3-138">A ID do locatário está listada no bloco.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-138">The tenant id is listed on the tile.</span></span> <span data-ttu-id="1c6f3-139">Você pode copiá-lo daqui e colá-lo na caixa de diálogo para se conectar ao aplicativo de modelo.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="1c6f3-140">Reinsira suas credenciais para fazer login no Power BI novamente</span><span class="sxs-lookup"><span data-stu-id="1c6f3-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="1c6f3-141">Código de erro: 302</span><span class="sxs-lookup"><span data-stu-id="1c6f3-141">Error Code: 302</span></span>
  
 <span data-ttu-id="1c6f3-142">**Onde você verá esta mensagem:** No Power BI quando você estiver se conectando ao aplicativo de modelo de análise de uso do Microsoft 365 ou ao chamar diretamente as APIs de relatórios da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="1c6f3-143">**Causa:** O código de autorização falhou e pode exigir que você insira suas credenciais novamente.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="1c6f3-144">**Para corrigir este erro:** Saia do Power BI e inicie a sessão novamente.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="1c6f3-145">Você não tem a autorização certa para acessar esses dados.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="1c6f3-146">Para poder obter acesso aos dados deste serviço, você precisa ser um administrador global ou qualquer um dos administradores do produto</span><span class="sxs-lookup"><span data-stu-id="1c6f3-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="1c6f3-147">**Código de erro:** 403</span><span class="sxs-lookup"><span data-stu-id="1c6f3-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="1c6f3-148">**Onde você verá esta mensagem:** No Power BI quando você estiver se conectando ao aplicativo de modelo de análise de uso do Microsoft 365 ou ao chamar diretamente as APIs de relatórios da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="1c6f3-149">**Causa:** O código de autorização falhou porque o usuário que tentou se conectar ao aplicativo de modelo não tem o nível certo de autorização para acessar esses dados.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="1c6f3-150">**Para corrigir esse erro:** Forneça as credenciais de um usuário que seja um **administrador global**, **administrador do Exchange**, **administrador do Skype for Business**, administrador **do SharePoint**, **leitor global** ou **leitor de relatórios** para se conectar ao aplicativo de modelo.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="1c6f3-151">Consulte [sobre funções de administrador](../add-users/about-admin-roles.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="1c6f3-152">Falha na atualização</span><span class="sxs-lookup"><span data-stu-id="1c6f3-152">Refresh failed</span></span>

 <span data-ttu-id="1c6f3-153">**Onde você verá esta mensagem:** Email do Power BI ou status com falha no histórico de atualização.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="1c6f3-154">**Causa:** Às vezes, as credenciais do usuário que se conectou ao aplicativo de modelo são redefinidas e não são atualizadas nas configurações de conexão do aplicativo de modelo que fazem com que o usuário veja erros de falha na atualização.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="1c6f3-155">**Para corrigir esse erro:** No Power BI, encontre o conjunto de um correspondente ao aplicativo de modelo de análise de uso do Microsoft 365, selecione **agendar atualização** e forneça suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="1c6f3-156">Se isso não funcionar, limpe o cache e recrie o aplicativo de modelo.</span><span class="sxs-lookup"><span data-stu-id="1c6f3-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
