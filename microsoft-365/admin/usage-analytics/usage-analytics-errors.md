---
title: Solução de problemas Microsoft 365 análise de uso
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Saiba como solucionar problemas com o aplicativo de modelo de análise de uso Microsoft 365 uso.
ms.openlocfilehash: 74ee32ae015421a2352474daefa0eaa0a53fbbc9
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293730"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="05097-103">Solução de problemas Microsoft 365 análise de uso</span><span class="sxs-lookup"><span data-stu-id="05097-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="05097-104">Explore a lista a seguir de mensagens de erro para obter ajuda com os problemas mais comuns com Microsoft 365 análise de uso.</span><span class="sxs-lookup"><span data-stu-id="05097-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="05097-105">Não somo capazes de processar seu pedido.</span><span class="sxs-lookup"><span data-stu-id="05097-105">We are unable to process your request.</span></span> <span data-ttu-id="05097-106">Você precisa primeiro se inscrever para esses dados do centro de administração Microsoft 365 local</span><span class="sxs-lookup"><span data-stu-id="05097-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="05097-107">**Código de Erro:** 422</span><span class="sxs-lookup"><span data-stu-id="05097-107">**Error Code:** 422</span></span> 
  
 <span data-ttu-id="05097-108">**Onde você verá esta mensagem:** Em Power BI quando você estiver se conectando ao aplicativo de modelo de Análise de Uso Microsoft 365 ou ao chamar diretamente as APIs Microsoft 365 Reporting.</span><span class="sxs-lookup"><span data-stu-id="05097-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="05097-109">**Causa:** Antes de se conectar ao aplicativo, você precisa assinar os dados do Microsoft 365 de administração.</span><span class="sxs-lookup"><span data-stu-id="05097-109">**Cause:** Before you can connect to the app, you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="05097-110">Se essa etapa não for feita primeiro, você não poderá se conectar ao aplicativo de modelo, mesmo que forneça sua ID Microsoft 365 locatário.</span><span class="sxs-lookup"><span data-stu-id="05097-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant ID.</span></span> 
  
 <span data-ttu-id="05097-111">**Para corrigir esse erro:** Para assinar os dados, vá para o centro de administração Relatórios Uso e localize o Microsoft 365 de análise de uso \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> na página principal do painel.</span><span class="sxs-lookup"><span data-stu-id="05097-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="05097-112">Selecione o botão **Iniciar** e, em seguida, no  painel Relatórios que é aberto, a opção Disponibilizar dados para Microsoft 365 análise de uso para Power BI configuração e **Salvar**. </span><span class="sxs-lookup"><span data-stu-id="05097-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="05097-113">Estamos processando seus dados</span><span class="sxs-lookup"><span data-stu-id="05097-113">We are processing your data</span></span>

 <span data-ttu-id="05097-114">**Onde você verá esta mensagem:** No Microsoft 365 **de análise** de uso no painel **Uso** no Microsoft 365 de administração.</span><span class="sxs-lookup"><span data-stu-id="05097-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="05097-115">**Causa:** Quando você [opta por](enable-usage-analytics.md) ver dados no aplicativo de modelo do centro de administração Microsoft 365, o sistema Microsoft 365 começa a gerar dados de uso histórico para sua organização.</span><span class="sxs-lookup"><span data-stu-id="05097-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="05097-116">Dependendo do tamanho do seu locatário, este passo pode levar entre 2 e 48 horas.</span><span class="sxs-lookup"><span data-stu-id="05097-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="05097-117">**Para corrigir isso:** Seja paciente, mas se a mensagem não mudar para **Seus dados** estão prontos após 3 dias, entre em contato Microsoft 365 suporte [para empresas.](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="05097-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../../business-video/get-help-support.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="05097-p105">Não podemos processar seu pedido neste momento. Ainda estamos preparando os dados para sua organização</span><span class="sxs-lookup"><span data-stu-id="05097-p105">We are unable to process your request at this time. We are still preparing the data for your organization</span></span>

 <span data-ttu-id="05097-120">**Código de erro:** 423</span><span class="sxs-lookup"><span data-stu-id="05097-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="05097-121">**Onde você verá esta mensagem:** Em Power BI, quando você estiver se conectando ao aplicativo de modelo de Análise de Uso Microsoft 365 ou ao chamar diretamente as APIs Microsoft 365 Reporting.</span><span class="sxs-lookup"><span data-stu-id="05097-121">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="05097-122">**Causa:** Quando você [opta por ver](enable-usage-analytics.md) dados no aplicativo de modelo do centro de administração, o sistema Microsoft 365 começa a gerar dados de uso histórico para sua organização.</span><span class="sxs-lookup"><span data-stu-id="05097-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="05097-123">Dependendo do tamanho do locatário, essa etapa pode levar entre duas horas e 48 horas.</span><span class="sxs-lookup"><span data-stu-id="05097-123">Depending on the size of your tenant, this step could take anywhere between two hours to 48 hours.</span></span> 
  
 <span data-ttu-id="05097-124">**Para corrigir isso:** Basta ter paciência, mas se a  mensagem não mudar para Seus dados estão prontos até 3 dias desde o início, entre em contato Microsoft 365 [suporte para empresas.](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="05097-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../../business-video/get-help-support.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="05097-125">O ID do locatário que você forneceu não está no formato correto</span><span class="sxs-lookup"><span data-stu-id="05097-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="05097-126">**Código de erro:** 400</span><span class="sxs-lookup"><span data-stu-id="05097-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="05097-127">**Onde você verá esta mensagem:** Em Power BI, quando você estiver se conectando ao aplicativo de modelo de Análise de Uso Microsoft 365 ou ao chamar diretamente as APIs Microsoft 365 Reporting.</span><span class="sxs-lookup"><span data-stu-id="05097-127">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="05097-128">**Causa:** A ID do locatário é um guid e deve estar no formato xxxxxxxx-xxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span><span class="sxs-lookup"><span data-stu-id="05097-128">**Cause:** The tenant ID is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="05097-129">Se você inserir qualquer outra cadeia de caracteres na caixa de entrada do locatário, receberá esse erro.</span><span class="sxs-lookup"><span data-stu-id="05097-129">If you enter any other string in the tenant input box, you will get this error.</span></span> 
  
 <span data-ttu-id="05097-130">**Para corrigir esse erro:** Vá para o centro de administração Relatórios Uso e localize o Microsoft 365 de análise de \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> uso na página principal do painel.</span><span class="sxs-lookup"><span data-stu-id="05097-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="05097-131">A ID do locatário está listada no azulejo.</span><span class="sxs-lookup"><span data-stu-id="05097-131">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="05097-132">Você pode copiá-lo daqui e colar na caixa de diálogo para se conectar ao aplicativo de modelo.</span><span class="sxs-lookup"><span data-stu-id="05097-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="05097-133">A ID do locatário fornecida não é reconhecida pelo nosso sistema</span><span class="sxs-lookup"><span data-stu-id="05097-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="05097-134">**Código de erro:** 404</span><span class="sxs-lookup"><span data-stu-id="05097-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="05097-135">**Onde você verá esta mensagem:** Em Power BI quando você estiver se conectando ao aplicativo de modelo de Análise de Uso Microsoft 365 ou ao chamar diretamente as APIs Microsoft 365 Reporting.</span><span class="sxs-lookup"><span data-stu-id="05097-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="05097-136">**Causa:** A ID de locatário fornecida não é válida ou não existe.</span><span class="sxs-lookup"><span data-stu-id="05097-136">**Cause:** The tenant ID you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="05097-137">**Para corrigir esse erro:** Vá para o centro de administração Relatórios Uso e localize o Microsoft 365 de análise de \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> uso na página principal do painel.</span><span class="sxs-lookup"><span data-stu-id="05097-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="05097-138">A ID do locatário está listada no azulejo.</span><span class="sxs-lookup"><span data-stu-id="05097-138">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="05097-139">Você pode copiá-lo daqui e colar na caixa de diálogo para se conectar ao aplicativo de modelo.</span><span class="sxs-lookup"><span data-stu-id="05097-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="05097-140">Reinsira suas credenciais para fazer login no Power BI novamente</span><span class="sxs-lookup"><span data-stu-id="05097-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="05097-141">Código de erro: 302</span><span class="sxs-lookup"><span data-stu-id="05097-141">Error Code: 302</span></span>
  
 <span data-ttu-id="05097-142">**Onde você verá esta mensagem:** Em Power BI quando você estiver se conectando ao aplicativo de modelo de Análise de Uso Microsoft 365 ou ao chamar diretamente as APIs Microsoft 365 Reporting.</span><span class="sxs-lookup"><span data-stu-id="05097-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="05097-143">**Causa:** O código de autorização falhou e pode exigir que você insira suas credenciais novamente.</span><span class="sxs-lookup"><span data-stu-id="05097-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="05097-144">**Para corrigir este erro:** Saia do Power BI e inicie a sessão novamente.</span><span class="sxs-lookup"><span data-stu-id="05097-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="05097-p110">Você não tem a autorização certa para acessar esses dados. Para poder obter acesso aos dados deste serviço, você precisa ser um administrador global ou qualquer um dos administradores do produto</span><span class="sxs-lookup"><span data-stu-id="05097-p110">You do not have the right authorization to access to this data. To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="05097-147">**Código de erro:** 403</span><span class="sxs-lookup"><span data-stu-id="05097-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="05097-148">**Onde você verá esta mensagem:** Em Power BI quando você estiver se conectando ao aplicativo de modelo de Análise de Uso Microsoft 365 ou ao chamar diretamente as APIs Microsoft 365 Reporting.</span><span class="sxs-lookup"><span data-stu-id="05097-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="05097-149">**Causa:** O código de autorização falhou porque o usuário que tentou se conectar ao aplicativo de modelo não tem o nível certo de autorização para acessar esses dados.</span><span class="sxs-lookup"><span data-stu-id="05097-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="05097-150">**Para corrigir esse erro:** Forneça as credenciais de um usuário que seja um administrador  **global,** um administrador do **Exchange,** um administrador do **Skype for Business,** um administrador do **SharePoint,** um leitor **global** ou um leitor de relatório para se conectar ao aplicativo de modelo.</span><span class="sxs-lookup"><span data-stu-id="05097-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="05097-151">Consulte [Sobre funções de administrador](../add-users/about-admin-roles.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="05097-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="05097-152">Falha na atualização</span><span class="sxs-lookup"><span data-stu-id="05097-152">Refresh failed</span></span>

 <span data-ttu-id="05097-153">**Onde você verá esta mensagem:** Email do Power BI ou status com falha no histórico de atualização.</span><span class="sxs-lookup"><span data-stu-id="05097-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="05097-154">**Causa:** Às vezes, as credenciais do usuário que se conectou ao aplicativo de modelo são redefinidas e não atualizadas nas configurações de conexão do aplicativo de modelo fazendo com que o usuário veja erros de falha de atualização.</span><span class="sxs-lookup"><span data-stu-id="05097-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="05097-155">**Para corrigir esse erro:** Em Power BI, encontre o conjuntos de dados correspondente ao aplicativo de  modelo de análise de uso Microsoft 365, selecione agendar atualização e fornecer suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="05097-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="05097-156">Se isso não funcionar, limpe o cache e re-crie o aplicativo de modelo.</span><span class="sxs-lookup"><span data-stu-id="05097-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
