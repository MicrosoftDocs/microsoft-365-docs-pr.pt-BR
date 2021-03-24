---
title: Habilitar a integração do SIEM no Microsoft Defender para Endpoint
description: Habilita a integração siem para receber detecções em sua solução de gerenciamento de informações de segurança e eventos (SIEM).
keywords: habilitar conector siem, siem, conector, informações de segurança e eventos
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 337eb28b7e4b4a7c57b63ff45fb1cea81db43604
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054396"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="ea065-104">Habilitar a integração do SIEM no Microsoft Defender para Endpoint</span><span class="sxs-lookup"><span data-stu-id="ea065-104">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ea065-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ea065-105">**Applies to:**</span></span>
- [<span data-ttu-id="ea065-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ea065-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


><span data-ttu-id="ea065-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="ea065-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ea065-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="ea065-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

<span data-ttu-id="ea065-109">Habilita a integração do SIEM (gerenciamento de eventos e informações de segurança) para que você possa obter detecções do Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="ea065-109">Enable security information and event management (SIEM) integration so you can pull detections from Microsoft Defender Security Center.</span></span> <span data-ttu-id="ea065-110">Puxe detecções usando sua solução SIEM ou conectando-se diretamente à API REST de detecções.</span><span class="sxs-lookup"><span data-stu-id="ea065-110">Pull detections using your SIEM solution or by connecting directly to the detections REST API.</span></span>

>[!NOTE]
>- <span data-ttu-id="ea065-111">[O Alerta do Microsoft Defender para Ponto](alerts.md) de Extremidade é composto por uma ou mais detecções.</span><span class="sxs-lookup"><span data-stu-id="ea065-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="ea065-112">[O Microsoft Defender para Detecção de Ponto](api-portal-mapping.md) de Extremidade é composto do evento suspeito ocorrido no Dispositivo e seus detalhes de Alerta relacionados.</span><span class="sxs-lookup"><span data-stu-id="ea065-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
>- <span data-ttu-id="ea065-113">A API de Alerta do Microsoft Defender para Ponto de Extremidade é a API mais recente para consumo de alerta e contém uma lista detalhada de evidências relacionadas para cada alerta.</span><span class="sxs-lookup"><span data-stu-id="ea065-113">The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="ea065-114">Para obter mais informações, consulte [Métodos de alerta e propriedades](alerts.md) e [Alertas de lista.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="ea065-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ea065-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="ea065-115">Prerequisites</span></span>

- <span data-ttu-id="ea065-116">O usuário que ativa a configuração deve ter permissões para criar um aplicativo no Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="ea065-116">The user who activates the setting must have permissions to create an app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="ea065-117">Esta é alguém com as seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="ea065-117">This is someone with the following roles:</span></span> 

  - <span data-ttu-id="ea065-118">Administrador de Segurança e Administrador Global</span><span class="sxs-lookup"><span data-stu-id="ea065-118">Security Administrator and either Global Administrator</span></span>
  - <span data-ttu-id="ea065-119">Administrador de Aplicativos de Nuvem</span><span class="sxs-lookup"><span data-stu-id="ea065-119">Cloud Application Administrator</span></span>
  - <span data-ttu-id="ea065-120">Administrador de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="ea065-120">Application Administrator</span></span>
  - <span data-ttu-id="ea065-121">Proprietário da entidade de serviço</span><span class="sxs-lookup"><span data-stu-id="ea065-121">Owner of the service principal</span></span>

- <span data-ttu-id="ea065-122">Durante a ativação inicial, uma tela pop-up é exibida para que as credenciais sejam inseridas.</span><span class="sxs-lookup"><span data-stu-id="ea065-122">During the initial activation, a pop-up screen is displayed for credentials to be entered.</span></span> <span data-ttu-id="ea065-123">Certifique-se de permitir pop-ups para este site.</span><span class="sxs-lookup"><span data-stu-id="ea065-123">Make sure that you allow pop-ups for this site.</span></span>

## <a name="enabling-siem-integration"></a><span data-ttu-id="ea065-124">Habilitando a integração siem</span><span class="sxs-lookup"><span data-stu-id="ea065-124">Enabling SIEM integration</span></span> 
1. <span data-ttu-id="ea065-125">No painel de navegação, selecione **Configurações**  >  **SIEM**.</span><span class="sxs-lookup"><span data-stu-id="ea065-125">In the navigation pane, select **Settings** > **SIEM**.</span></span>

    ![Imagem da integração siem do menu Configurações1](images/enable_siem.png)

    >[!TIP]
    ><span data-ttu-id="ea065-127">Se você encontrar um erro ao tentar habilitar o aplicativo de conector SIEM, verifique as configurações do bloqueador pop-up do navegador.</span><span class="sxs-lookup"><span data-stu-id="ea065-127">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="ea065-128">Ele pode estar bloqueando a nova janela que está sendo aberta quando você habilita o recurso.</span><span class="sxs-lookup"><span data-stu-id="ea065-128">It might be blocking the new window being opened when you enable the capability.</span></span> 

2. <span data-ttu-id="ea065-129">Selecione **Habilitar integração siem**.</span><span class="sxs-lookup"><span data-stu-id="ea065-129">Select **Enable SIEM integration**.</span></span> <span data-ttu-id="ea065-130">Isso ativa a seção detalhes de acesso do conector **SIEM** com valores pré-preenchidos e um aplicativo é criado em seu locatário do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="ea065-130">This activates the **SIEM connector access details** section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span>

    > [!WARNING]
    ><span data-ttu-id="ea065-131">O segredo do cliente é exibido apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="ea065-131">The client secret is only displayed once.</span></span> <span data-ttu-id="ea065-132">Certifique-se de manter uma cópia dela em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="ea065-132">Make sure you keep a copy of it in a safe place.</span></span><br>
     

    ![Imagem da integração siem do menu Configurações2](images/siem_details.png)

3. <span data-ttu-id="ea065-134">Escolha o tipo SIEM que você usa em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ea065-134">Choose the SIEM type you use in your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ea065-135">Se você selecionar o HP ArcSight, precisará salvar esses dois arquivos de configuração:</span><span class="sxs-lookup"><span data-stu-id="ea065-135">If you select HP ArcSight, you'll need to save these two configuration files:</span></span><br>
   > - <span data-ttu-id="ea065-136">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="ea065-136">WDATP-connector.jsonparser.properties</span></span>
   > - <span data-ttu-id="ea065-137">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="ea065-137">WDATP-connector.properties</span></span> <br>

   <span data-ttu-id="ea065-138">Se você quiser se conectar diretamente à API REST de detecções por meio de acesso programático, escolha **API Genérica**.</span><span class="sxs-lookup"><span data-stu-id="ea065-138">If you want to connect directly to the detections REST API through programmatic access, choose **Generic API**.</span></span>

4. <span data-ttu-id="ea065-139">Copie os valores individuais ou selecione **Salvar detalhes no arquivo** para baixar um arquivo que contém todos os valores.</span><span class="sxs-lookup"><span data-stu-id="ea065-139">Copy the individual values or select **Save details to file** to download a file that contains all the values.</span></span>

5. <span data-ttu-id="ea065-140">Selecione **Gerar tokens** para obter um token de acesso e atualização.</span><span class="sxs-lookup"><span data-stu-id="ea065-140">Select **Generate tokens** to get an access and refresh token.</span></span>
  
   > [!NOTE]
   > <span data-ttu-id="ea065-141">Você precisará gerar um novo token refresh a cada 90 dias.</span><span class="sxs-lookup"><span data-stu-id="ea065-141">You'll need to generate a new Refresh token every 90 days.</span></span> 

6. <span data-ttu-id="ea065-142">Siga as instruções para criar um registro de aplicativo [do Azure AD](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) para o Microsoft Defender para Ponto de Extremidade e atribua as permissões corretas a ele para ler alertas.</span><span class="sxs-lookup"><span data-stu-id="ea065-142">Follow the instructions for [creating an Azure AD app registration for Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) and assign the correct permissions to it to read alerts.</span></span>

<span data-ttu-id="ea065-143">Agora você pode prosseguir com a configuração da solução SIEM ou a conexão com a API REST de detecções por meio do acesso programático.</span><span class="sxs-lookup"><span data-stu-id="ea065-143">You can now proceed with configuring your SIEM solution or connecting to the detections REST API through programmatic access.</span></span> <span data-ttu-id="ea065-144">Você precisará usar os tokens ao configurar sua solução SIEM para permitir que ele receba detecções do Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="ea065-144">You'll need to use the tokens when configuring your SIEM solution to allow it to receive detections from Microsoft Defender Security Center.</span></span>

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a><span data-ttu-id="ea065-145">Integrar o Microsoft Defender para Ponto de Extremidade com IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="ea065-145">Integrate Microsoft Defender for Endpoint with IBM QRadar</span></span> 
<span data-ttu-id="ea065-146">Você pode configurar o IBM QRadar para coletar detecções do Microsoft Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="ea065-146">You can configure IBM QRadar to collect detections from Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="ea065-147">Para obter mais informações, consulte [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span><span class="sxs-lookup"><span data-stu-id="ea065-147">For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

## <a name="see-also"></a><span data-ttu-id="ea065-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="ea065-148">See also</span></span>
- [<span data-ttu-id="ea065-149">Configurar o HP ArcSight para puxar o Microsoft Defender para detecções de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="ea065-149">Configure HP ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="ea065-150">Campos de Detecção de Ponto de Extremidade do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ea065-150">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="ea065-151">Puxar o Microsoft Defender para detecções de ponto de extremidade usando a API REST</span><span class="sxs-lookup"><span data-stu-id="ea065-151">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="ea065-152">Solucionar problemas de integração de ferramentas SIEM</span><span class="sxs-lookup"><span data-stu-id="ea065-152">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
