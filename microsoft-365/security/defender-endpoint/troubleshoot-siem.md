---
title: Solucionar problemas de integração de ferramentas SIEM no Microsoft Defender ATP
description: Solucionar problemas que podem surgir ao usar ferramentas SIEM com o Microsoft Defender ATP.
keywords: solução de problemas, siem, segredo do cliente, segredo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: c1c8fdb0b6e84d4265defb95d91b59a584b7f4c2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185774"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a><span data-ttu-id="71488-104">Solucionar problemas de integração de ferramentas SIEM</span><span class="sxs-lookup"><span data-stu-id="71488-104">Troubleshoot SIEM tool integration issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="71488-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="71488-105">**Applies to:**</span></span>
- [<span data-ttu-id="71488-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="71488-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="71488-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71488-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="71488-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="71488-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="71488-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="71488-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="71488-110">Talvez seja necessário solucionar problemas ao puxar detecções em suas ferramentas SIEM.</span><span class="sxs-lookup"><span data-stu-id="71488-110">You might need to troubleshoot issues while pulling detections in your SIEM tools.</span></span>

<span data-ttu-id="71488-111">Esta página fornece etapas detalhadas para solucionar problemas que você pode encontrar.</span><span class="sxs-lookup"><span data-stu-id="71488-111">This page provides detailed steps to troubleshoot issues you might encounter.</span></span>


## <a name="learn-how-to-get-a-new-client-secret"></a><span data-ttu-id="71488-112">Saiba como obter um novo segredo do cliente</span><span class="sxs-lookup"><span data-stu-id="71488-112">Learn how to get a new client secret</span></span>
<span data-ttu-id="71488-113">Se o segredo do cliente expirar ou se você tiver perdido a cópia fornecida quando estava habilitando o aplicativo de ferramenta SIEM, você precisará obter um novo segredo.</span><span class="sxs-lookup"><span data-stu-id="71488-113">If your client secret expires or if you've misplaced the copy provided when you were enabling the SIEM tool application,  you'll need to get a new secret.</span></span>

1. <span data-ttu-id="71488-114">Faça logon no [portal de gerenciamento do Azure.](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="71488-114">Login to the [Azure management portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="71488-115">Selecione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="71488-115">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="71488-116">Selecione seu locatário.</span><span class="sxs-lookup"><span data-stu-id="71488-116">Select your tenant.</span></span>

4. <span data-ttu-id="71488-117">Clique **em Registros de aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="71488-117">Click **App registrations**.</span></span> <span data-ttu-id="71488-118">Em seguida, na lista aplicativos, selecione o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="71488-118">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="71488-119">Selecione **a seção** Chaves e forneça uma descrição de chave e especifique a duração da validade da chave.</span><span class="sxs-lookup"><span data-stu-id="71488-119">Select **Keys** section, then provide a key description and specify the key validity duration.</span></span>

6. <span data-ttu-id="71488-120">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="71488-120">Click **Save**.</span></span> <span data-ttu-id="71488-121">O valor da chave é exibido.</span><span class="sxs-lookup"><span data-stu-id="71488-121">The key value is displayed.</span></span>

7. <span data-ttu-id="71488-122">Copie o valor e salve-o em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="71488-122">Copy the value and save it in a safe place.</span></span>


## <a name="error-when-getting-a-refresh-access-token"></a><span data-ttu-id="71488-123">Erro ao obter um token de acesso de atualização</span><span class="sxs-lookup"><span data-stu-id="71488-123">Error when getting a refresh access token</span></span>
<span data-ttu-id="71488-124">Se você encontrar um erro ao tentar obter um token de atualização ao usar a API de inteligência de ameaça ou as ferramentas SIEM, você precisará adicionar a URL de resposta para o aplicativo relevante no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="71488-124">If you encounter an error when trying to get a refresh token when using the threat intelligence API or SIEM tools, you'll need to add reply URL for relevant application in Azure Active Directory.</span></span>

1. <span data-ttu-id="71488-125">Faça logon no [portal de gerenciamento do Azure.](https://ms.portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="71488-125">Login to the [Azure management portal](https://ms.portal.azure.com).</span></span>

2. <span data-ttu-id="71488-126">Selecione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="71488-126">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="71488-127">Selecione seu locatário.</span><span class="sxs-lookup"><span data-stu-id="71488-127">Select your tenant.</span></span>

4. <span data-ttu-id="71488-128">Clique **em Registros de Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="71488-128">Click **App Registrations**.</span></span> <span data-ttu-id="71488-129">Em seguida, na lista aplicativos, selecione o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="71488-129">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="71488-130">Adicione a seguinte URL:</span><span class="sxs-lookup"><span data-stu-id="71488-130">Add the following URL:</span></span>
   - <span data-ttu-id="71488-131">Para a União Europeia: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="71488-131">For the European Union: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="71488-132">Para o Reino Unido: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="71488-132">For the United Kingdom: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="71488-133">Para os Estados Unidos:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` .</span><span class="sxs-lookup"><span data-stu-id="71488-133">For the United States:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback`.</span></span>
 
6. <span data-ttu-id="71488-134">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="71488-134">Click **Save**.</span></span>

## <a name="error-while-enabling-the-siem-connector-application"></a><span data-ttu-id="71488-135">Erro ao habiltar o aplicativo de conector SIEM</span><span class="sxs-lookup"><span data-stu-id="71488-135">Error while enabling the SIEM connector application</span></span>
<span data-ttu-id="71488-136">Se você encontrar um erro ao tentar habilitar o aplicativo de conector SIEM, verifique as configurações do bloqueador pop-up do navegador.</span><span class="sxs-lookup"><span data-stu-id="71488-136">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="71488-137">Ele pode estar bloqueando a nova janela que está sendo aberta quando você habilita o recurso.</span><span class="sxs-lookup"><span data-stu-id="71488-137">It might be blocking the new window being opened when you enable the capability.</span></span>




><span data-ttu-id="71488-138">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="71488-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="71488-139">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="71488-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a><span data-ttu-id="71488-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="71488-140">Related topics</span></span>
- [<span data-ttu-id="71488-141">Habilitar a integração do SIEM no Microsoft Defender para Endpoint</span><span class="sxs-lookup"><span data-stu-id="71488-141">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="71488-142">Configurar ArcSight para puxar o Microsoft Defender para detecções de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="71488-142">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="71488-143">Pull detections to your SIEM tools</span><span class="sxs-lookup"><span data-stu-id="71488-143">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="71488-144">Campos de Detecção de Ponto de Extremidade do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="71488-144">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="71488-145">Puxar o Microsoft Defender para detecções de ponto de extremidade usando a API REST</span><span class="sxs-lookup"><span data-stu-id="71488-145">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
