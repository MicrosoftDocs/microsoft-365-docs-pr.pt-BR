---
title: Usar Microsoft Teams classes com quadro-preto
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrar Microsoft Teams classes no seu sistema de gerenciamento Learning de gerenciamento
ms.openlocfilehash: 047f640befa967b78597c5eba93f9c64f22ec1c2
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053246"
---
# <a name="use-microsoft-teams-classes-with-blackboard"></a><span data-ttu-id="73e22-103">Usar Microsoft Teams classes com quadro-preto</span><span class="sxs-lookup"><span data-stu-id="73e22-103">Use Microsoft Teams classes with Blackboard</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73e22-104">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="73e22-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="73e22-105">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="73e22-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="73e22-106">Microsoft Teams é um aplicativo de interoperabilidade de ferramentas (LTI) do Learning que ajuda educadores e alunos a navegar facilmente entre seu Learning Management System (LMS) e Teams.</span><span class="sxs-lookup"><span data-stu-id="73e22-106">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="73e22-107">Os usuários podem acessar suas equipes de classe associadas ao curso diretamente de dentro do LMS.</span><span class="sxs-lookup"><span data-stu-id="73e22-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a><span data-ttu-id="73e22-108">Aprovar o aplicativo no locatário Microsoft Azure locatário</span><span class="sxs-lookup"><span data-stu-id="73e22-108">Approve the app in the Microsoft Azure tenant</span></span>

<span data-ttu-id="73e22-109">As tarefas a seguir são concluídas pelo administrador Microsoft Office 365 e o administrador Learn Ultra do Quadro Preto.</span><span class="sxs-lookup"><span data-stu-id="73e22-109">The following tasks are completed by the Microsoft Office 365 admin and the Blackboard Learn Ultra admin.</span></span>

<span data-ttu-id="73e22-110">Antes de gerenciar Microsoft Office 365 integração no Blackboard Learn Ultra, o administrador do Microsoft Office 365 deve aprovar o MSFT Teams de quadro preto para o aplicativo **Learn Ultra Azure** para o locatário Microsoft Azure da instituição.</span><span class="sxs-lookup"><span data-stu-id="73e22-110">Before managing the integration within Blackboard Learn Ultra, the Microsoft Office 365 admin must approve the Blackboard **MSFT Teams for Learn Ultra Azure** app for the institution’s Microsoft Azure tenant.</span></span>

1. <span data-ttu-id="73e22-111">Encontre sua ID do Locatário da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="73e22-111">Find your Microsoft Tenant ID.</span></span> <span data-ttu-id="73e22-112">Veja [como encontrar o locatário](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span><span class="sxs-lookup"><span data-stu-id="73e22-112">See [how to find the tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span></span>

2. <span data-ttu-id="73e22-113">Redirecionar o Ponto de Extremidade de Consentimento do Administrador da Plataforma de Identidade da Microsoft de acordo com o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="73e22-113">Redirect the Microsoft Identity Platform Admin Consent Endpoint according to the following example:</span></span>

   `https://login.microsoftonline.com/{tenant}/adminconsent?client_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > <span data-ttu-id="73e22-114">Substitua {tenant} pela ID de locatário da Microsoft da sua organização.</span><span class="sxs-lookup"><span data-stu-id="73e22-114">Replace {tenant} with your organization’s Microsoft tenant ID.</span></span>

## <a name="register-the-integration-apps"></a><span data-ttu-id="73e22-115">Registrar os aplicativos de integração</span><span class="sxs-lookup"><span data-stu-id="73e22-115">Register the integration apps</span></span>

<span data-ttu-id="73e22-116">Como administrador do Blackboard Learn Ultra, você precisará registrar 2 aplicativos de integração LTI 1.3 em seu ambiente de teste:</span><span class="sxs-lookup"><span data-stu-id="73e22-116">As a Blackboard Learn Ultra admin, you'll need to register 2 LTI 1.3 integration apps within your Test environment:</span></span>

- <span data-ttu-id="73e22-117">A integração de Classe de Aprendizado de Quadro Teams para dar suporte à sincronização de lista de escalas</span><span class="sxs-lookup"><span data-stu-id="73e22-117">The Blackboard Learn Class Teams integration to support the roster sync</span></span>

- <span data-ttu-id="73e22-118">O Microsoft Teams lti da equipe de classe</span><span class="sxs-lookup"><span data-stu-id="73e22-118">The Microsoft Teams class team LTI app</span></span>

1. <span data-ttu-id="73e22-119">Anote as seguintes IDs de cliente LTI para ambos os Aplicativos:</span><span class="sxs-lookup"><span data-stu-id="73e22-119">Make a note of the following LTI Client IDs for both Apps:</span></span>

    - <span data-ttu-id="73e22-120">Quadro-preto - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span><span class="sxs-lookup"><span data-stu-id="73e22-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span></span>

    - <span data-ttu-id="73e22-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span><span class="sxs-lookup"><span data-stu-id="73e22-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span></span>

2. <span data-ttu-id="73e22-122">Acesse o Painel de Administração e, em **Integrações,** localize os Provedores de Ferramentas LTI.</span><span class="sxs-lookup"><span data-stu-id="73e22-122">Access the Admin Panel, and under **Integrations**, locate the LTI Tool Providers.</span></span>

   ![esta é a caixa de diálogo Provedor de Ferramentas LTI mostra uma lista de provedores](../media/lti-media/lti-tool-providers.png)

3. <span data-ttu-id="73e22-124">Selecione **Registrar LTI1.3/Advantage Tool**.</span><span class="sxs-lookup"><span data-stu-id="73e22-124">Select **Register LTI1.3/Advantage Tool**.</span></span>

4. <span data-ttu-id="73e22-125">Insira o primeiro das IDs do Cliente fornecidas (quadro-negro ou Microsoft) e selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="73e22-125">Enter the first of the Client IDs provided (either Blackboard or Microsoft), and select **Submit**.</span></span>

   ![a ferramenta de registro LTI com um campo para inserir a id do cliente](../media/lti-media/register-tool.png)

5. <span data-ttu-id="73e22-127">Revise as configurações pré-preenchidas e verifique se o status da ferramenta está marcado como aprovado.</span><span class="sxs-lookup"><span data-stu-id="73e22-127">Review the pre-populated settings and ensure that the tool status is marked as approved.</span></span>

6. <span data-ttu-id="73e22-128">Role até a parte inferior e selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="73e22-128">Scroll to the bottom, and then select **Submit**.</span></span>

7. <span data-ttu-id="73e22-129">Repita as etapas anteriores para registrar o segundo dos aplicativos LTI em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="73e22-129">Repeat the previous steps to register the second of the LTI apps within your environment.</span></span>

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a><span data-ttu-id="73e22-130">Configurar o aplicativo REST e o compartilhamento de recursos de origem cruzada</span><span class="sxs-lookup"><span data-stu-id="73e22-130">Set up the REST Application and Cross Origin Resource Sharing</span></span>

<span data-ttu-id="73e22-131">O administrador Learn Ultra do Quadro Preto também precisará configurar o Aplicativo REST e a configuração de Compartilhamento de Recursos de Origem Cruzada.</span><span class="sxs-lookup"><span data-stu-id="73e22-131">The Blackboard Learn Ultra admin will also need to configure the REST Application and the Cross Origin Resource Sharing configuration.</span></span>

<span data-ttu-id="73e22-132">Conclua o seguinte para configurar o aplicativo REST</span><span class="sxs-lookup"><span data-stu-id="73e22-132">Complete the following to set up the REST Application</span></span>

1. <span data-ttu-id="73e22-133">Acesse a seção Aprender Ferramentas de Administração e selecione **Integrações da API REST** na **seção Integrações.**</span><span class="sxs-lookup"><span data-stu-id="73e22-133">Access the Learn Administration Tools, and then select **REST API Integrations** from the **Integrations** section.</span></span>

2. <span data-ttu-id="73e22-134">Selecione **Criar integrações** e insira a mesma ID de Aplicativo/Cliente inserida para a ferramenta LTI de Integração Teams Classe de Aprendizado de Quadro Preto.</span><span class="sxs-lookup"><span data-stu-id="73e22-134">Select **Create integrations** and enter the same Application/Client ID that you entered for the Blackboard Learn Class Teams Integration LTI tool.</span></span>

3. <span data-ttu-id="73e22-135">Insira o Usuário de Aprendizado (pode ser seu próprio nome de usuário de administrador de aprendizado) ou selecione **Procurar** para localizar.</span><span class="sxs-lookup"><span data-stu-id="73e22-135">Enter the Learn User (this could be your own learn admin username), or select **Browse** to locate.</span></span>

4. <span data-ttu-id="73e22-136">Selecione **Sim** para **Acesso de Usuário Final**.</span><span class="sxs-lookup"><span data-stu-id="73e22-136">Select **Yes** for **End User Access**.</span></span>

5. <span data-ttu-id="73e22-137">Selecione **Sim** para **Autorizado para Agir como Usuário**</span><span class="sxs-lookup"><span data-stu-id="73e22-137">Select **Yes** for **Authorized to Act as User**</span></span>

6. <span data-ttu-id="73e22-138">Selecione **Enviar uma** vez concluído.</span><span class="sxs-lookup"><span data-stu-id="73e22-138">Select **Submit** once complete.</span></span>

## <a name="set-up-cross-origin-resource-sharing"></a><span data-ttu-id="73e22-139">Configurar o compartilhamento de recursos de origem cruzada</span><span class="sxs-lookup"><span data-stu-id="73e22-139">Set up Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="73e22-140">Acesse a seção Aprender Ferramentas de Administração e selecione **Compartilhamento de** Recursos de origem cruzada na **seção Integrações.**</span><span class="sxs-lookup"><span data-stu-id="73e22-140">Access the Learn Administration Tools, and select **Cross-Origin Resource Sharing** from the **Integrations** section.</span></span>

2. <span data-ttu-id="73e22-141">Selecione **Criar Configuração**.</span><span class="sxs-lookup"><span data-stu-id="73e22-141">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="73e22-142">Insira `https://bb-ms-teams-ultra-ext.api.blackboard.com` a origem.</span><span class="sxs-lookup"><span data-stu-id="73e22-142">Enter `https://bb-ms-teams-ultra-ext.api.blackboard.com` in the origin.</span></span>

4. <span data-ttu-id="73e22-143">Adicione a palavra **Autorização** nos **Headers Permitidos.**</span><span class="sxs-lookup"><span data-stu-id="73e22-143">Add the word **Authorization** in the **Allowed Headers**.</span></span>

5. <span data-ttu-id="73e22-144">Definir **Disponível como** **Sim**.</span><span class="sxs-lookup"><span data-stu-id="73e22-144">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="73e22-145">Selecione **Enviar uma** vez concluído.</span><span class="sxs-lookup"><span data-stu-id="73e22-145">Select **Submit** once complete.</span></span>

## <a name="enable-class-teams-in-blackboard-learn"></a><span data-ttu-id="73e22-146">Habilitar Teams classe em Blackboard Learn</span><span class="sxs-lookup"><span data-stu-id="73e22-146">Enable Class Teams in Blackboard Learn</span></span>

<span data-ttu-id="73e22-147">Depois de habilitar as ferramentas LTI, a próxima etapa será configurar a integração do Microsoft Class Teams do seu próprio locatário Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="73e22-147">Once you've enabled the LTI tools, your next step will be to set up the Microsoft Class Teams integration from your own Microsoft Office 365 tenant.</span></span> <span data-ttu-id="73e22-148">Você pode fazer isso seguindo estas etapas como administrador do Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="73e22-148">You can do this by following these steps as the Blackboard Learn Ultra admin.</span></span>

1. <span data-ttu-id="73e22-149">Em **Aprender Ferramentas de** Administração e  >  **Utilitários,** selecione Microsoft Teams Administrador de **Integração.**</span><span class="sxs-lookup"><span data-stu-id="73e22-149">In **Learn Admin** > **Tools and Utilities**, select **Microsoft Teams Integration Admin**.</span></span>

   ![a caixa de diálogo ferramentas e utilitários com uma lista de ferramentas disponíveis](../media/lti-media/tools-utilities.png)

2. <span data-ttu-id="73e22-151">Selecione a caixa de seleção **Habilitar Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="73e22-151">Select the checkbox for **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="73e22-152">Insira sua ID de locatário conforme referenciado na seção em Administrador do Microsoft O365</span><span class="sxs-lookup"><span data-stu-id="73e22-152">Enter your tenant ID as referenced in the section under Microsoft O365 Admin</span></span>

 > [!NOTE]
 > <span data-ttu-id="73e22-153">Você não poderá salvar as configurações até que o aplicativo tenha sido aprovado pelo administrador do O365. Consulte [Aprovar o aplicativo no Microsoft Azure locatário](#approve-the-app-in-the-microsoft-azure-tenant).</span><span class="sxs-lookup"><span data-stu-id="73e22-153">You won't be able to save the settings until the app has been approved by the O365 admin. See [Approve the app in Microsoft Azure tenant](#approve-the-app-in-the-microsoft-azure-tenant).</span></span>

4. <span data-ttu-id="73e22-154">Quando o administrador global do O365 tiver aprovado o aplicativo Teams quadro-preto no locatário da Microsoft, selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="73e22-154">When the global O365 admin has approved the Blackboard Teams application in your Microsoft Tenant, select **Submit**.</span></span>
