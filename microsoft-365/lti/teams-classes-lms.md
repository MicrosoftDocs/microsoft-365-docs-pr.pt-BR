---
title: Usar as classes do Microsoft Teams em seu Sistema de Gerenciamento de Aprendizagem
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
description: Integrar as classes do Microsoft Teams em seu Sistema de Gerenciamento de Aprendizagem
ms.openlocfilehash: 18d33225dd57932af20421c6b3b5dc4fe3b397b8
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327687"
---
# <a name="use-microsoft-teams-classes-in-your-learning-management-system"></a><span data-ttu-id="9cbb7-103">Usar as classes do Microsoft Teams em seu Sistema de Gerenciamento de Aprendizagem</span><span class="sxs-lookup"><span data-stu-id="9cbb7-103">Use Microsoft Teams classes in your Learning Management System</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cbb7-104">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9cbb7-105">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="9cbb7-106">As equipes de classe do Microsoft Teams é um aplicativo de Interoperabilidade de Ferramentas de Aprendizagem (LTI) que ajuda educadores e alunos a navegar facilmente entre seu LmS (Sistema de Gerenciamento de Aprendizagem) e o Teams.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-106">Microsoft Teams class teams is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="9cbb7-107">Os usuários podem acessar suas equipes de classe associadas ao curso diretamente de dentro do LMS.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a><span data-ttu-id="9cbb7-108">Aprovar o aplicativo no locatário do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="9cbb7-108">Approve the app in the Microsoft Azure tenant</span></span>

<span data-ttu-id="9cbb7-109">As tarefas a seguir são concluídas pelo administrador Microsoft Office 365 e o administrador Learn Ultra do Quadro Preto.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-109">The following tasks are completed by the Microsoft Office 365 admin and the Blackboard Learn Ultra admin.</span></span>

<span data-ttu-id="9cbb7-110">Antes de gerenciar a integração no Blackboard Learn Ultra, o administrador do Microsoft Office 365 deve aprovar o aplicativo Blackboard **MSFT Teams for Learn Ultra Azure** para o locatário do Microsoft Azure da instituição.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-110">Before managing the integration within Blackboard Learn Ultra, the Microsoft Office 365 admin must approve the Blackboard **MSFT Teams for Learn Ultra Azure** app for the institution’s Microsoft Azure tenant.</span></span>

1. <span data-ttu-id="9cbb7-111">Encontre sua ID do Locatário da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-111">Find your Microsoft Tenant ID.</span></span> <span data-ttu-id="9cbb7-112">Veja [como encontrar o locatário](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span><span class="sxs-lookup"><span data-stu-id="9cbb7-112">See [how to find the tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span></span>

2. <span data-ttu-id="9cbb7-113">Redirecionar o Ponto de Extremidade de Consentimento do Administrador da Plataforma de Identidade da Microsoft de acordo com o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="9cbb7-113">Redirect the Microsoft Identity Platform Admin Consent Endpoint according to the following example:</span></span>

   `https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > <span data-ttu-id="9cbb7-114">Substitua {tenant} pela ID de locatário da Microsoft da sua organização.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-114">Replace {tenant} with your organization’s Microsoft tenant ID.</span></span>

## <a name="register-the-integration-apps"></a><span data-ttu-id="9cbb7-115">Registrar os aplicativos de integração</span><span class="sxs-lookup"><span data-stu-id="9cbb7-115">Register the integration apps</span></span>

<span data-ttu-id="9cbb7-116">Como administrador do Blackboard Learn Ultra, você precisará registrar 2 aplicativos de integração LTI 1.3 em seu ambiente de teste:</span><span class="sxs-lookup"><span data-stu-id="9cbb7-116">As a Blackboard Learn Ultra admin, you'll need to register 2 LTI 1.3 integration apps within your Test environment:</span></span>

- <span data-ttu-id="9cbb7-117">A integração do Blackboard Learn Class Teams para dar suporte à sincronização de lista de participantes</span><span class="sxs-lookup"><span data-stu-id="9cbb7-117">The Blackboard Learn Class Teams integration to support the roster sync</span></span>

- <span data-ttu-id="9cbb7-118">O aplicativo LTI da equipe de classe do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9cbb7-118">The Microsoft Teams class team LTI app</span></span>

1. <span data-ttu-id="9cbb7-119">Anote as seguintes IDs de cliente LTI para ambos os Aplicativos:</span><span class="sxs-lookup"><span data-stu-id="9cbb7-119">Make a note of the following LTI Client IDs for both Apps:</span></span>

    - <span data-ttu-id="9cbb7-120">Quadro-preto - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span><span class="sxs-lookup"><span data-stu-id="9cbb7-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span></span>

    - <span data-ttu-id="9cbb7-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span><span class="sxs-lookup"><span data-stu-id="9cbb7-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span></span>

2. <span data-ttu-id="9cbb7-122">Acesse o Painel de Administração e, em **Integrações,** localize os Provedores de Ferramentas LTI.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-122">Access the Admin Panel, and under **Integrations**, locate the LTI Tool Providers.</span></span>

   ![esta é a caixa de diálogo Provedor de Ferramentas LTI mostra uma lista de provedores](../media/lti-media/lti-tool-providers.png)

3. <span data-ttu-id="9cbb7-124">Selecione **Registrar LTI1.3/Advantage Tool**.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-124">Select **Register LTI1.3/Advantage Tool**.</span></span>

4. <span data-ttu-id="9cbb7-125">Insira o primeiro das IDs do Cliente fornecidas (quadro-negro ou Microsoft) e selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-125">Enter the first of the Client IDs provided (either Blackboard or Microsoft), and select **Submit**.</span></span>

   ![a ferramenta de registro LTI com um campo para inserir a id do cliente](../media/lti-media/register-tool.png)

5. <span data-ttu-id="9cbb7-127">Revise as configurações pré-preenchidas e verifique se o status da ferramenta está marcado como aprovado.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-127">Review the pre-populated settings and ensure that the tool status is marked as approved.</span></span>

6. <span data-ttu-id="9cbb7-128">Role até a parte inferior e selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-128">Scroll to the bottom, and then select **Submit**.</span></span>

7. <span data-ttu-id="9cbb7-129">Repita as etapas anteriores para registrar o segundo dos aplicativos LTI em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-129">Repeat the previous steps to register the second of the LTI apps within your environment.</span></span>

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a><span data-ttu-id="9cbb7-130">Configurar o aplicativo REST e o compartilhamento de recursos de origem cruzada</span><span class="sxs-lookup"><span data-stu-id="9cbb7-130">Set up the REST Application and Cross Origin Resource Sharing</span></span>

<span data-ttu-id="9cbb7-131">O administrador Learn Ultra do Quadro Preto também precisará configurar o Aplicativo REST e a configuração de Compartilhamento de Recursos de Origem Cruzada.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-131">The Blackboard Learn Ultra admin will also need to configure the REST Application and the Cross Origin Resource Sharing configuration.</span></span>

<span data-ttu-id="9cbb7-132">Conclua o seguinte para configurar o aplicativo REST</span><span class="sxs-lookup"><span data-stu-id="9cbb7-132">Complete the following to set up the REST Application</span></span>

1. <span data-ttu-id="9cbb7-133">Acesse a seção Aprender Ferramentas de Administração e selecione **Integrações da API REST** na **seção Integrações.**</span><span class="sxs-lookup"><span data-stu-id="9cbb7-133">Access the Learn Administration Tools, and then select **REST API Integrations** from the **Integrations** section.</span></span>

2. <span data-ttu-id="9cbb7-134">Selecione **Criar integrações** e insira a mesma ID de Aplicativo/Cliente que você ingressou para a ferramenta LTI de Integração de Equipes de Classe Do Quadro De Aprendizado.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-134">Select **Create integrations** and enter the same Application/Client ID that you entered for the Blackboard Learn Class Teams Integration LTI tool.</span></span>

3. <span data-ttu-id="9cbb7-135">Insira o Usuário de Aprendizado (pode ser seu próprio nome de usuário de administrador de aprendizado) ou selecione **Procurar** para localizar.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-135">Enter the Learn User (this could be your own learn admin username), or select **Browse** to locate.</span></span>

4. <span data-ttu-id="9cbb7-136">Selecione **Sim** para **Acesso de Usuário Final**.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-136">Select **Yes** for **End User Access**.</span></span>

5. <span data-ttu-id="9cbb7-137">Selecione **Sim** para **Autorizado para Agir como Usuário**</span><span class="sxs-lookup"><span data-stu-id="9cbb7-137">Select **Yes** for **Authorized to Act as User**</span></span>

6. <span data-ttu-id="9cbb7-138">Selecione **Enviar uma** vez concluído.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-138">Select **Submit** once complete.</span></span>

## <a name="set-up-cross-origin-resource-sharing"></a><span data-ttu-id="9cbb7-139">Configurar o compartilhamento de recursos de origem cruzada</span><span class="sxs-lookup"><span data-stu-id="9cbb7-139">Set up Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="9cbb7-140">Acesse a seção Aprender Ferramentas de Administração e selecione **Compartilhamento de** Recursos de origem cruzada na **seção Integrações.**</span><span class="sxs-lookup"><span data-stu-id="9cbb7-140">Access the Learn Administration Tools, and select **Cross-Origin Resource Sharing** from the **Integrations** section.</span></span>

2. <span data-ttu-id="9cbb7-141">Selecione **Criar Configuração**.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-141">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="9cbb7-142">Insira `https://bb-ms-teams-ultra-ext.api.blackboard.com` a origem.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-142">Enter `https://bb-ms-teams-ultra-ext.api.blackboard.com` in the origin.</span></span>

4. <span data-ttu-id="9cbb7-143">Adicione a palavra **Autorização** nos **Headers Permitidos.**</span><span class="sxs-lookup"><span data-stu-id="9cbb7-143">Add the word **Authorization** in the **Allowed Headers**.</span></span>

5. <span data-ttu-id="9cbb7-144">Definir **Disponível como** **Sim**.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-144">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="9cbb7-145">Selecione **Enviar uma** vez concluído.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-145">Select **Submit** once complete.</span></span>

## <a name="enable-class-teams-in-blackboard-learn"></a><span data-ttu-id="9cbb7-146">Habilitar equipes de classe no quadro-preto Aprender</span><span class="sxs-lookup"><span data-stu-id="9cbb7-146">Enable Class Teams in Blackboard Learn</span></span>

<span data-ttu-id="9cbb7-147">Depois de habilitar as ferramentas LTI, sua próxima etapa será configurar a integração do Microsoft Class Teams do seu próprio locatário Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-147">Once you've enabled the LTI tools, your next step will be to set up the Microsoft Class Teams integration from your own Microsoft Office 365 tenant.</span></span> <span data-ttu-id="9cbb7-148">Você pode fazer isso seguindo estas etapas como administrador do Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-148">You can do this by following these steps as the Blackboard Learn Ultra admin.</span></span>

1. <span data-ttu-id="9cbb7-149">Em **Aprender Ferramentas de** Administração e  >  **Utilitários,** selecione Administrador de **Integração do Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="9cbb7-149">In **Learn Admin** > **Tools and Utilities**, select **Microsoft Teams Integration Admin**.</span></span>

   ![a caixa de diálogo ferramentas e utilitários com uma lista de ferramentas disponíveis](../media/lti-media/tools-utilities.png)

2. <span data-ttu-id="9cbb7-151">Selecione a caixa de seleção **Habilitar o Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-151">Select the checkbox for **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="9cbb7-152">Insira sua ID de locatário conforme referenciado na seção em Administrador do Microsoft O365</span><span class="sxs-lookup"><span data-stu-id="9cbb7-152">Enter your tenant ID as referenced in the section under Microsoft O365 Admin</span></span>

 > [!NOTE]
 > <span data-ttu-id="9cbb7-153">Você não poderá salvar as configurações até que o aplicativo tenha sido aprovado pelo administrador do O365. Consulte [Aprovar o aplicativo no locatário do Microsoft Azure.](#approve-the-app-in-the-microsoft-azure-tenant)</span><span class="sxs-lookup"><span data-stu-id="9cbb7-153">You won't be able to save the settings until the app has been approved by the O365 admin. See [Approve the app in Microsoft Azure tenant](#approve-the-app-in-the-microsoft-azure-tenant).</span></span>

4. <span data-ttu-id="9cbb7-154">Quando o administrador global do O365 tiver aprovado o aplicativo Blackboard Teams em seu Locatário da Microsoft, selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-154">When the global O365 admin has approved the Blackboard Teams application in your Microsoft Tenant, select **Submit**.</span></span>
