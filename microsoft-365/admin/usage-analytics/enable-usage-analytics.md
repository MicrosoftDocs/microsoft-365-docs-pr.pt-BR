---
title: Habilitar Microsoft 365 análise de uso
f1.keywords:
- CSH
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
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Saiba como começar a coletar dados para seu locatário usando o aplicativo Microsoft 365 modelo de Análise de Uso no Power BI.
ms.openlocfilehash: 4a3110ead76621e93e646577189b7b03d65caf1d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286064"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="baf3f-103">Habilitar Microsoft 365 análise de uso</span><span class="sxs-lookup"><span data-stu-id="baf3f-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="baf3f-104">Microsoft 365 análise de uso ainda não está disponível para Microsoft 365 us government Community.</span><span class="sxs-lookup"><span data-stu-id="baf3f-104">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="baf3f-105">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="baf3f-105">Before you begin</span></span>

<span data-ttu-id="baf3f-106">Para começar a usar Microsoft 365 análise de uso, primeiro você deve disponibilizar os dados no Centro de administração do Microsoft 365 e, em seguida, iniciar o aplicativo de modelo Power BI.</span><span class="sxs-lookup"><span data-stu-id="baf3f-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>

## <a name="get-power-bi"></a><span data-ttu-id="baf3f-107">Obter o Power BI</span><span class="sxs-lookup"><span data-stu-id="baf3f-107">Get Power BI</span></span>

<span data-ttu-id="baf3f-108">Se você ainda não tiver Power BI, poderá inscrever-se [no](https://go.microsoft.com/fwlink/p/?linkid=845347)Power BI Pro .</span><span class="sxs-lookup"><span data-stu-id="baf3f-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="baf3f-109">Selecione **Experimentar gratuitamente** para se inscrever em uma avaliação ou **Comprar agora** para obter Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="baf3f-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>


<span data-ttu-id="baf3f-110">Você também pode expandir **Produtos** para comprar uma versão do Power BI.</span><span class="sxs-lookup"><span data-stu-id="baf3f-110">You can also expand **Products** to buy a version of Power BI.</span></span>

> [!NOTE]
> <span data-ttu-id="baf3f-111">Você precisa de uma Power BI Pro para instalar, personalizar e distribuir um aplicativo de modelo.</span><span class="sxs-lookup"><span data-stu-id="baf3f-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="baf3f-112">Para obter mais informações, consulte [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="baf3f-112">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="baf3f-113">Para compartilhar seus dados, você e as pessoas com quem você compartilha os dados precisam de uma licença de Power BI Pro, ou o conteúdo precisa estar em um espaço de trabalho em um serviço [Power BI premium](/power-bi/service-premium-what-is).</span><span class="sxs-lookup"><span data-stu-id="baf3f-113">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span>

## <a name="enable-the-template-app"></a><span data-ttu-id="baf3f-114">Habilitar o aplicativo de modelo</span><span class="sxs-lookup"><span data-stu-id="baf3f-114">Enable the template app</span></span>

<span data-ttu-id="baf3f-115">Para habilitar o aplicativo de modelo, você precisa ser um **administrador global.**</span><span class="sxs-lookup"><span data-stu-id="baf3f-115">To enable the template app, you have to be a **Global administrator**.</span></span>

<span data-ttu-id="baf3f-116">Confira [mais informações sobre funções de](../add-users/about-admin-roles.md) administrador.</span><span class="sxs-lookup"><span data-stu-id="baf3f-116">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span>

1. <span data-ttu-id="baf3f-117">No centro de administração, vá para a guia Serviços de configurações **Configurações** \>  \>  Org.</span><span class="sxs-lookup"><span data-stu-id="baf3f-117">In the admin center, go to the **Settings** \> **Org settings** \> **Services** tab.</span></span>

2. <span data-ttu-id="baf3f-118">Na guia **Serviços,** selecione  **Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="baf3f-118">On the **Services** tab, select  **Reports**.</span></span>

3. <span data-ttu-id="baf3f-119">No painel Relatórios que é aberto, de definir Tornar dados de relatório disponíveis para Microsoft 365 análise de uso **para** Power BI **como Ao** \> **salvar**.</span><span class="sxs-lookup"><span data-stu-id="baf3f-119">On the Reports panel that opens, set **Make report data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span>

<span data-ttu-id="baf3f-120">O processo de coleta de dados será concluído em duas a 48 horas, dependendo do tamanho do locatário.</span><span class="sxs-lookup"><span data-stu-id="baf3f-120">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="baf3f-121">O **botão Ir para Power BI** será habilitado (não mais cinza) quando a coleta de dados for concluída.</span><span class="sxs-lookup"><span data-stu-id="baf3f-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span>

## <a name="start-the-template-app"></a><span data-ttu-id="baf3f-122">Iniciar o aplicativo de modelo</span><span class="sxs-lookup"><span data-stu-id="baf3f-122">Start the template app</span></span>

<span data-ttu-id="baf3f-123">Para iniciar **o** aplicativo de modelo, você precisa ser um administrador **global,** um leitor de **relatório,** um administrador **Exchange,** um administrador Skype for Business ou um **SharePoint administrador**.</span><span class="sxs-lookup"><span data-stu-id="baf3f-123">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span>

1. <span data-ttu-id="baf3f-124">Copie a ID do locatário e selecione **Ir para Power BI**.</span><span class="sxs-lookup"><span data-stu-id="baf3f-124">Copy the tenant ID and select **Go to Power BI**.</span></span>

2. <span data-ttu-id="baf3f-125">Quando chegar ao Power BI, entre.</span><span class="sxs-lookup"><span data-stu-id="baf3f-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="baf3f-126">Em **seguida, selecione** -> **Aplicativos Obter aplicativos** no menu de navegação.</span><span class="sxs-lookup"><span data-stu-id="baf3f-126">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>

3. <span data-ttu-id="baf3f-127">Na guia **Aplicativos,** digite Microsoft 365 na caixa de pesquisa e selecione Microsoft 365 **análise de** uso \> **Obter agora**.</span><span class="sxs-lookup"><span data-stu-id="baf3f-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="baf3f-128">[![Selecione Obter agora](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="baf3f-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>

4. <span data-ttu-id="baf3f-129">Depois que o aplicativo for instalado.</span><span class="sxs-lookup"><span data-stu-id="baf3f-129">Once the app is installed.</span></span> <span data-ttu-id="baf3f-130">Selecione o azulejo para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="baf3f-130">Select the tile to open it.</span></span>

5. <span data-ttu-id="baf3f-131">Selecione **Explorar aplicativo** para exibir o aplicativo com dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="baf3f-131">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="baf3f-132">Escolha **Conexão** conectar o aplicativo aos dados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="baf3f-132">Choose **Connect** to connect the app to your organization’s data.</span></span>

6. <span data-ttu-id="baf3f-133">Escolha **Conexão**, no Conexão para Microsoft 365 análise de uso, digite **a** ID do locatário (sem traços) que você copiou na etapa (1) e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="baf3f-133">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>

7. <span data-ttu-id="baf3f-134">Na próxima tela, selecione **OAuth2** como o método **Authentication Entrar** \> .</span><span class="sxs-lookup"><span data-stu-id="baf3f-134">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="baf3f-135">Se você escolher qualquer outro método de autenticação, a conexão com o aplicativo de modelo falhará.</span><span class="sxs-lookup"><span data-stu-id="baf3f-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>

    ![Escolher conta da Microsoft como método de autenticação](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)

8. <span data-ttu-id="baf3f-137">Depois que o aplicativo de modelo é instaurou Microsoft 365 painel de análise de uso estará disponível Power BI na Web.</span><span class="sxs-lookup"><span data-stu-id="baf3f-137">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="baf3f-138">O carregamento inicial do painel levará entre 2 a 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="baf3f-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>

<span data-ttu-id="baf3f-139">Os agregados de nível de locatário estarão disponíveis em todos os relatórios após a aceitação.</span><span class="sxs-lookup"><span data-stu-id="baf3f-139">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="baf3f-140">**Os detalhes no nível do usuário** só estarão disponíveis por volta do dia 5 do próximo mês de calendário após a aceitação em .</span><span class="sxs-lookup"><span data-stu-id="baf3f-140">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="baf3f-141">Isso afetará todos os relatórios em Atividade do Usuário (Consulte Navegar e utilizar os relatórios em Microsoft 365 [análise](navigate-and-utilize-reports.md) de uso para dicas sobre como exibir e usar esses relatórios).</span><span class="sxs-lookup"><span data-stu-id="baf3f-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>

## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="baf3f-142">Tornar os dados coletados anônimos</span><span class="sxs-lookup"><span data-stu-id="baf3f-142">Make the collected data anonymous</span></span>

<span data-ttu-id="baf3f-143">Para tornar anônimos os dados coletados para todos os relatórios, você deve ser um administrador global.</span><span class="sxs-lookup"><span data-stu-id="baf3f-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="baf3f-144">Isso ocultará informações identificáveis, como nomes de usuário, grupo e site em relatórios e no aplicativo de modelo.</span><span class="sxs-lookup"><span data-stu-id="baf3f-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>

1. <span data-ttu-id="baf3f-145">No centro de administração, vá para **a** Configurações \> **Org Configurações** e, em **Serviços,** escolha **Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="baf3f-145">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>

2. <span data-ttu-id="baf3f-146">Selecione **Relatórios** e escolha Exibir **identificadores anônimos.**</span><span class="sxs-lookup"><span data-stu-id="baf3f-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="baf3f-147">Essa configuração é aplicada tanto aos relatórios de uso quanto ao aplicativo de modelo.</span><span class="sxs-lookup"><span data-stu-id="baf3f-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>

3. <span data-ttu-id="baf3f-148">Selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="baf3f-148">Select **Save changes**.</span></span>

## <a name="related-content"></a><span data-ttu-id="baf3f-149">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="baf3f-149">Related content</span></span>

<span data-ttu-id="baf3f-150">[Sobre análise de uso](usage-analytics.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="baf3f-150">[About usage analytics](usage-analytics.md) (article)</span></span>\
<span data-ttu-id="baf3f-151">[Obter a versão mais recente da análise de uso](get-the-latest-version-of-usage-analytics.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="baf3f-151">[Get the latest version of usage analytics](get-the-latest-version-of-usage-analytics.md) (article)</span></span>\
<span data-ttu-id="baf3f-152">[Navegue e utilize os relatórios Microsoft 365 análise de uso](navigate-and-utilize-reports.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="baf3f-152">[Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) (article)</span></span>