---
title: Habilitar análise de uso do Microsoft 365
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
description: Saiba como iniciar a coleta de dados para o seu locatário usando o aplicativo de modelo de análise de uso do Microsoft 365 no Power BI.
ms.openlocfilehash: b5cb8df7fbe8ce1844d2af3ecaf62c7903d4e98b
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527367"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="72f1a-103">Habilitar análise de uso do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="72f1a-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="72f1a-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="72f1a-104">The admin center is changing.</span></span> <span data-ttu-id="72f1a-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="72f1a-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="72f1a-106">A análise de uso do Microsoft 365 ainda não está disponível para a Comunidade do governo dos EUA da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="72f1a-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="72f1a-107">Etapas para habilitar a análise de uso do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="72f1a-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="72f1a-108">Para começar a usar a análise de uso do Microsoft 365, primeiro você deve tornar os dados disponíveis no centro de administração do Microsoft 365 e, em seguida, iniciar o aplicativo de modelo no Power BI.</span><span class="sxs-lookup"><span data-stu-id="72f1a-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="72f1a-109">Obter o Power BI</span><span class="sxs-lookup"><span data-stu-id="72f1a-109">Get Power BI</span></span>

<span data-ttu-id="72f1a-110">Se você ainda não tem o Power BI, é possível [inscrever-se no Power bi pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="72f1a-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="72f1a-111">Selecione **tentar liberar** para inscrever-se em uma avaliação ou **Compre agora** para obter o Power bi pro.</span><span class="sxs-lookup"><span data-stu-id="72f1a-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="72f1a-112">Você também pode expandir **Produtos** para comprar uma versão do Power BI.</span><span class="sxs-lookup"><span data-stu-id="72f1a-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="72f1a-113">Você precisa de uma licença do Power BI pro para instalar, personalizar e distribuir um aplicativo de modelo.</span><span class="sxs-lookup"><span data-stu-id="72f1a-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="72f1a-114">Para obter mais informações, consulte [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="72f1a-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="72f1a-115">Você precisa de uma licença do Power BI pro para compartilhar seu conteúdo e as pessoas com as quais você o compartilha, ou o conteúdo precisa estar em um espaço de trabalho em uma [capacidade Premium](https://docs.microsoft.com/power-bi/service-premium-what-is).</span><span class="sxs-lookup"><span data-stu-id="72f1a-115">You need a Power BI Pro license to share your content, and the people you share it with do too, or the content needs to be in a workspace in a [Premium capacity](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="72f1a-116">Habilitar o aplicativo de modelo</span><span class="sxs-lookup"><span data-stu-id="72f1a-116">Enable the template app</span></span>

<span data-ttu-id="72f1a-117">Para habilitar o aplicativo de modelo, você deve ser um **administrador global**, um **leitor de relatórios**, um **administrador do Exchange**, **administrador do Skype for Business**ou **administrador do SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="72f1a-117">To enable the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
<span data-ttu-id="72f1a-118">Consulte [sobre funções de administrador](../add-users/about-admin-roles.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="72f1a-118">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="72f1a-119">No centro de administração do, vá para a página**Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.</span><span class="sxs-lookup"><span data-stu-id="72f1a-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="72f1a-120">Na página **uso** , localize o cartão de **análise de uso do Microsoft 365** e selecione **introdução**.</span><span class="sxs-lookup"><span data-stu-id="72f1a-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="72f1a-121">No painel de relatórios que é aberto, defina **disponibilizar dados para a análise de uso do Microsoft 365 para o Power bi** **para ao** \> **salvar**.</span><span class="sxs-lookup"><span data-stu-id="72f1a-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="72f1a-122">Isso iniciará o processo de coleta de dados e será concluído em 2 a 48 horas, dependendo do tamanho do seu locatário.</span><span class="sxs-lookup"><span data-stu-id="72f1a-122">This initiates the data collection process and will complete in 2 to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="72f1a-123">O botão **ir para Power bi** será habilitado (não mais cinza) quando a coleta de dados estiver concluída.</span><span class="sxs-lookup"><span data-stu-id="72f1a-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="initiate-the-template-app"></a><span data-ttu-id="72f1a-124">Iniciar o aplicativo de modelo</span><span class="sxs-lookup"><span data-stu-id="72f1a-124">Initiate the template app</span></span>

<span data-ttu-id="72f1a-125">Para iniciar o aplicativo de modelo, você deve ser um **administrador global**, um **leitor de relatórios**, um **administrador do Exchange**, **administrador do Skype for Business**ou **administrador do SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="72f1a-125">To initiate the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="72f1a-126">Copie a ID do locatário e selecione **ir para o Power bi**.</span><span class="sxs-lookup"><span data-stu-id="72f1a-126">Copy the tenant Id and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="72f1a-127">Quando chegar ao Power BI, entre.</span><span class="sxs-lookup"><span data-stu-id="72f1a-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="72f1a-128">Selecione aplicativos->obter aplicativos no menu de navegação.</span><span class="sxs-lookup"><span data-stu-id="72f1a-128">Select Apps->Get apps from the navigation menu.</span></span>    
  
3. <span data-ttu-id="72f1a-129">Na guia **aplicativos** , digite Microsoft 365 na caixa de pesquisa e selecione análise de **uso do Microsoft 365** \> **agora**.</span><span class="sxs-lookup"><span data-stu-id="72f1a-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="72f1a-130">[![Selecionar obter agora](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="72f1a-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="72f1a-131">Depois que o aplicativo é instalado.</span><span class="sxs-lookup"><span data-stu-id="72f1a-131">Once the app is installed.</span></span> <span data-ttu-id="72f1a-132">Clique no bloco para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="72f1a-132">Click on the tile to open it.</span></span>

5.  <span data-ttu-id="72f1a-133">Clique em **explorar aplicativo** para exibir o aplicativo com dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="72f1a-133">Click **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="72f1a-134">Clique em **conectar** para conectar o aplicativo aos dados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="72f1a-134">Click **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="72f1a-135">Após clicar em **conectar**, na tela **conectar ao Microsoft 365 Usage Analytics** , digite a ID do locatário (sem traços) que você copiou na etapa (1) e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="72f1a-135">After clicking **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, type in the tenant Id (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="72f1a-136">Na tela seguinte, selecione **conta da Microsoft** como o **método de autenticação** \> **entrar**.</span><span class="sxs-lookup"><span data-stu-id="72f1a-136">On the next screen, select **Microsoft account** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="72f1a-137">Se você escolher qualquer outro método de autenticação, a conexão com o aplicativo de modelo irá falhar.</span><span class="sxs-lookup"><span data-stu-id="72f1a-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Escolha a conta da Microsoft como método de autenticação](../../media/ab6f0463-c3f7-4088-a605-67c699fa86ad.png)
  
8. <span data-ttu-id="72f1a-139">Depois que o aplicativo de modelo é instanciado, o painel de análise de uso do Microsoft 365 estará disponível no Power BI na Web.</span><span class="sxs-lookup"><span data-stu-id="72f1a-139">Once the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="72f1a-140">O carregamento inicial do painel levará entre 2 e 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="72f1a-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="72f1a-141">Os agregados de nível do locatário estarão disponíveis em todos os relatórios.</span><span class="sxs-lookup"><span data-stu-id="72f1a-141">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="72f1a-142">Os **detalhes no nível do usuário só ficarão disponíveis após o 1º ou o 15º dia do mês do calendário após o recebimento**.</span><span class="sxs-lookup"><span data-stu-id="72f1a-142">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="72f1a-143">Isso afetará todos os relatórios da atividade do usuário (consulte [navegar e usar a análise de uso dos relatórios no Microsoft 365](navigate-and-utilize-reports.md) para obter dicas sobre como exibir e usar esses relatórios).</span><span class="sxs-lookup"><span data-stu-id="72f1a-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="72f1a-144">Tornar os dados coletados anônimos</span><span class="sxs-lookup"><span data-stu-id="72f1a-144">Make the collected data anonymous</span></span>

<span data-ttu-id="72f1a-145">Para tornar anônimos os dados coletados para todos os relatórios, você deve ser um administrador global.</span><span class="sxs-lookup"><span data-stu-id="72f1a-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="72f1a-146">Isso ocultará as informações de identificação, como nomes de site, de grupo e de usuário em relatórios e no aplicativo de modelo.</span><span class="sxs-lookup"><span data-stu-id="72f1a-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="72f1a-147">No centro de administração, vá para as **Settings** configurações da \> **organização**configurações e, na guia **Serviços** , escolha **relatórios**.</span><span class="sxs-lookup"><span data-stu-id="72f1a-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="72f1a-148">Selecione **relatórios**e, em seguida, escolha **Exibir identificadores anônimos**.</span><span class="sxs-lookup"><span data-stu-id="72f1a-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="72f1a-149">Essa configuração é aplicada tanto para os relatórios de uso quanto para o aplicativo de modelo.</span><span class="sxs-lookup"><span data-stu-id="72f1a-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="72f1a-150">Selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="72f1a-150">Select **Save changes**.</span></span>
