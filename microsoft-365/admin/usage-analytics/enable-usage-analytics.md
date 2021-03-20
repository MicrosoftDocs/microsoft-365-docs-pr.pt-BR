---
title: Habilitar a análise de uso do Microsoft 365
f1.keywords:
- CSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Saiba como começar a coletar dados para seu locatário usando o aplicativo de modelo análise de uso do Microsoft 365 no Power BI.
ms.openlocfilehash: 1ef50380041650763961ffbe6e01c63b26800ee3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913869"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="9aa3a-103">Habilitar a análise de uso do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9aa3a-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="9aa3a-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-104">The admin center is changing.</span></span> <span data-ttu-id="9aa3a-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="9aa3a-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="9aa3a-106">A análise de uso do Microsoft 365 ainda não está disponível para o Microsoft 365 US Government Community.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="9aa3a-107">Etapas para habilitar a análise de uso do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9aa3a-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="9aa3a-108">Para começar a usar a análise de uso do Microsoft 365, primeiro você deve disponibilizar os dados no Centro de administração do Microsoft 365 e iniciar o aplicativo de modelo no Power BI.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="9aa3a-109">Obter o Power BI</span><span class="sxs-lookup"><span data-stu-id="9aa3a-109">Get Power BI</span></span>

<span data-ttu-id="9aa3a-110">Se você ainda não tiver o Power BI, poderá [se inscrever no Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="9aa3a-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="9aa3a-111">Selecione **Experimentar gratuitamente** para se inscrever em uma avaliação ou **Comprar agora** para obter o Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="9aa3a-112">Você também pode expandir **Produtos** para comprar uma versão do Power BI.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="9aa3a-113">Você precisa de uma licença do Power BI Pro para instalar, personalizar e distribuir um aplicativo de modelo.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="9aa3a-114">Para obter mais informações, consulte [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="9aa3a-114">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="9aa3a-115">Para compartilhar seus dados, você e as pessoas com quem você compartilha os dados precisam de uma licença do Power BI Pro ou o conteúdo precisa estar em um espaço de trabalho em um [serviço premium do Power BI.](/power-bi/service-premium-what-is)</span><span class="sxs-lookup"><span data-stu-id="9aa3a-115">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="9aa3a-116">Habilitar o aplicativo de modelo</span><span class="sxs-lookup"><span data-stu-id="9aa3a-116">Enable the template app</span></span>

<span data-ttu-id="9aa3a-117">Para habilitar o aplicativo de modelo, você precisa ser um **administrador global.**</span><span class="sxs-lookup"><span data-stu-id="9aa3a-117">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="9aa3a-118">Confira [mais informações sobre funções de](../add-users/about-admin-roles.md) administrador.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-118">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="9aa3a-119">No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="9aa3a-120">Na página **Uso,** localize o cartão de análise de uso do **Microsoft 365** e selecione **Começar**.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="9aa3a-121">No painel Relatórios que é aberto, de acordo com **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="9aa3a-122">O processo de coleta de dados será concluído em duas a 48 horas, dependendo do tamanho do locatário.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-122">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="9aa3a-123">O **botão Ir para o Power BI** será habilitado (não mais cinza) quando a coleta de dados for concluída.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="9aa3a-124">Iniciar o aplicativo de modelo</span><span class="sxs-lookup"><span data-stu-id="9aa3a-124">Start the template app</span></span>

<span data-ttu-id="9aa3a-125">Para iniciar o aplicativo de modelo, você precisa ser um administrador **global,** um leitor de **relatório,** um administrador do **Exchange,** um administrador **do Skype for Business** ou um administrador do **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="9aa3a-125">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="9aa3a-126">Copie a ID do locatário e selecione **Ir para Power BI**.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-126">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="9aa3a-127">Quando chegar ao Power BI, entre.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="9aa3a-128">Em **seguida, selecione** -> **Aplicativos Obter aplicativos** no menu de navegação.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-128">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="9aa3a-129">Na guia **Aplicativos,** digite o Microsoft 365 na caixa de pesquisa e selecione Análise de uso do **Microsoft 365** \> **Obter agora**.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="9aa3a-130">[![Selecione Obter agora](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="9aa3a-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="9aa3a-131">Depois que o aplicativo for instalado.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-131">Once the app is installed.</span></span> <span data-ttu-id="9aa3a-132">Selecione o azulejo para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-132">Select the tile to open it.</span></span>

5.  <span data-ttu-id="9aa3a-133">Selecione **Explorar aplicativo** para exibir o aplicativo com dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-133">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="9aa3a-134">Escolha **Conectar** para conectar o aplicativo aos dados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-134">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="9aa3a-135">Escolha **Conectar**, na tela de análise de uso conectar-se ao **Microsoft 365** e digite a ID do locatário (sem traços) copiada na etapa (1) e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-135">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="9aa3a-136">Na próxima tela, selecione **OAuth2** como o método **Authentication Entrar** \> .</span><span class="sxs-lookup"><span data-stu-id="9aa3a-136">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="9aa3a-137">Se você escolher qualquer outro método de autenticação, a conexão com o aplicativo de modelo falhará.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Escolher conta da Microsoft como método de autenticação](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="9aa3a-139">Depois que o aplicativo de modelo é instaurou o painel de análise de uso do Microsoft 365 estará disponível no Power BI na Web.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-139">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="9aa3a-140">O carregamento inicial do painel levará entre 2 a 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="9aa3a-141">Os agregados de nível de locatário estarão disponíveis em todos os relatórios após a aceitação.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-141">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="9aa3a-142">**Os detalhes no nível do usuário** só estarão disponíveis por volta do dia 5 do próximo mês de calendário após a aceitação em .</span><span class="sxs-lookup"><span data-stu-id="9aa3a-142">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="9aa3a-143">Isso afetará todos os relatórios em Atividade do Usuário (Consulte Navegar e utilizar os relatórios na análise de uso do [Microsoft 365](navigate-and-utilize-reports.md) para ver e usar esses relatórios).</span><span class="sxs-lookup"><span data-stu-id="9aa3a-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="9aa3a-144">Tornar os dados coletados anônimos</span><span class="sxs-lookup"><span data-stu-id="9aa3a-144">Make the collected data anonymous</span></span>

<span data-ttu-id="9aa3a-145">Para tornar anônimos os dados coletados para todos os relatórios, você deve ser um administrador global.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="9aa3a-146">Isso ocultará informações identificáveis, como nomes de usuário, grupo e site em relatórios e no aplicativo de modelo.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="9aa3a-147">No centro de administração, vá para a guia **Configurações** da Organização de Configurações e, em \>  **Serviços,** escolha **Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="9aa3a-148">Selecione **Relatórios** e escolha Exibir **identificadores anônimos.**</span><span class="sxs-lookup"><span data-stu-id="9aa3a-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="9aa3a-149">Essa configuração é aplicada tanto aos relatórios de uso quanto ao aplicativo de modelo.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="9aa3a-150">Selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="9aa3a-150">Select **Save changes**.</span></span>