---
title: Usar OneDrive Learning interoperabilidade de ferramentas
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
description: Crie e grade atribuições, crie e crie e crie conteúdo do curso e colabore em arquivos em tempo real com o novo aplicativo de interoperabilidade de ferramentas OneDrive Learning ferramentas.
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256922"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="fe55f-103">Usar Microsoft OneDrive LTI com Canvas</span><span class="sxs-lookup"><span data-stu-id="fe55f-103">Use Microsoft OneDrive LTI with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe55f-104">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="fe55f-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="fe55f-105">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="fe55f-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="integrate-with-canvas"></a><span data-ttu-id="fe55f-106">Integrar-se ao Canvas</span><span class="sxs-lookup"><span data-stu-id="fe55f-106">Integrate with Canvas</span></span>

<span data-ttu-id="fe55f-107">A pessoa que executa essa integração deve ser um administrador do Canvas e um administrador do Microsoft 365 locatário.</span><span class="sxs-lookup"><span data-stu-id="fe55f-107">The person who performs this integration should be an admin of Canvas and an admin of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="fe55f-108">Entre no portal Microsoft Azure com a conta de administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="fe55f-108">Sign in to the Microsoft Azure portal with the tenant admin account.</span></span> <span data-ttu-id="fe55f-109">O administrador de locatários do Azure também deve ter a função de administrador de grupo.</span><span class="sxs-lookup"><span data-stu-id="fe55f-109">The Azure tenant administrator should also have the Group administrator role.</span></span>

    ![administrador de grupo realçada](../media/lti-media/lti-group-admin.png)

2. <span data-ttu-id="fe55f-111">Entre no portal do Microsoft [OneDrive LTI](https://odltiappnl.azurewebsites.net/admin).</span><span class="sxs-lookup"><span data-stu-id="fe55f-111">Sign in to the Microsoft [OneDrive LTI portal](https://odltiappnl.azurewebsites.net/admin).</span></span>

3. <span data-ttu-id="fe55f-112">Aceite as permissões para concluir a assinatura.</span><span class="sxs-lookup"><span data-stu-id="fe55f-112">Accept the permissions to complete the sign-in.</span></span>

    ![aceitar permissões](../media/lti-media/lti-permissions.png)

4. <span data-ttu-id="fe55f-114">Selecione **Adicionar Locatário LTI**.</span><span class="sxs-lookup"><span data-stu-id="fe55f-114">Select **Add LTI Tenant**.</span></span>

     ![adicionar locatário LTI](../media/lti-media/lti-add-tenant.png)

5. <span data-ttu-id="fe55f-116">Selecione **Plataforma de Consumidor LTI** como **Canvas** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="fe55f-116">Select **LTI Consumer Platform** as **Canvas** from the dropdown.</span></span>

6. <span data-ttu-id="fe55f-117">Selecione **URL da Base de Tela** e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="fe55f-117">Select **Canvas Base URL** and then select **Next**.</span></span>

    ![selecione Canvas e adicione URL base](../media/lti-media/lti-canvas-base-url.png)

   <span data-ttu-id="fe55f-119">A próxima tela mostra campos que são confidenciais para você.</span><span class="sxs-lookup"><span data-stu-id="fe55f-119">The next screen shows fields that are confidential to you.</span></span>

7. <span data-ttu-id="fe55f-120">Selecione **Próximo** em ??</span><span class="sxs-lookup"><span data-stu-id="fe55f-120">Select **Next** from ??</span></span> <span data-ttu-id="fe55f-121">page.</span><span class="sxs-lookup"><span data-stu-id="fe55f-121">page.</span></span> <span data-ttu-id="fe55f-122">OS REVISADORES PODEM PREENCHER O ESPAÇO EM BRANCO AQUI?</span><span class="sxs-lookup"><span data-stu-id="fe55f-122">CAN REVIEWERS FILL IN THE BLANK HERE?</span></span>

8. <span data-ttu-id="fe55f-123">Selecione **Next** na tela que mostra informações confidenciais para você.</span><span class="sxs-lookup"><span data-stu-id="fe55f-123">Select **Next** in the screen that shows information that's confidential to you.</span></span>

   <span data-ttu-id="fe55f-124">A tela final do portal do Azure mostra as próximas etapas para adicionar sua instância do Canvas.</span><span class="sxs-lookup"><span data-stu-id="fe55f-124">The final screen of the Azure portal shows the next steps for adding your Canvas instance.</span></span>

9. <span data-ttu-id="fe55f-125">Copie as Chaves do Desenvolvedor desta tela.</span><span class="sxs-lookup"><span data-stu-id="fe55f-125">Copy the Developer Keys from this screen.</span></span> <span data-ttu-id="fe55f-126">Você usará ao criar a instância canvas.</span><span class="sxs-lookup"><span data-stu-id="fe55f-126">You'll use when you create the Canvas instance.</span></span>

## <a name="add-the-canvas-instance"></a><span data-ttu-id="fe55f-127">Adicionar a instância do Canvas</span><span class="sxs-lookup"><span data-stu-id="fe55f-127">Add the Canvas instance</span></span>

1. <span data-ttu-id="fe55f-128">Em sua instância do Canvas, desmarque **As Chaves** do Desenvolvedor de  >  **Administrador.**</span><span class="sxs-lookup"><span data-stu-id="fe55f-128">In your Canvas instance, deselect **Admin** > **Developer Keys**.</span></span>

2. <span data-ttu-id="fe55f-129">Escolha **LTI Key** no menu suspenso em **Chave do Desenvolvedor.**</span><span class="sxs-lookup"><span data-stu-id="fe55f-129">Choose **LTI Key** in the dropdown on **Developer Key**.</span></span>

   ![Obter as chaves do desenvolvedor LTI](../media/lti-media/lti-developer-keys.png)

3. <span data-ttu-id="fe55f-131">Colar as chaves do desenvolvedor aqui.</span><span class="sxs-lookup"><span data-stu-id="fe55f-131">Paste the developer keys here.</span></span>

     ![Colar as chaves do desenvolvedor](../media/lti-media/lti-developer-keys.png)

   <span data-ttu-id="fe55f-133">A chave é criada no **modo** OFF</span><span class="sxs-lookup"><span data-stu-id="fe55f-133">The key gets created in **OFF** mode</span></span>

   ![As chaves de desenvolvedor criadas no modo desligado](../media/lti-media/lti-copy-developer-keys.png)

4. <span data-ttu-id="fe55f-135">Copie o texto realçado.</span><span class="sxs-lookup"><span data-stu-id="fe55f-135">Copy the highlighted text.</span></span>
    <span data-ttu-id="fe55f-136">Isso serve como ID do Cliente no Microsoft OneDrive lti portal.</span><span class="sxs-lookup"><span data-stu-id="fe55f-136">This serves as Client ID in Microsoft OneDrive LTI portal.</span></span>

5. <span data-ttu-id="fe55f-137">Colar o texto no campo **ID do** Cliente Microsoft OneDrive portal LTI e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="fe55f-137">Paste the text into the **Client ID** field in Microsoft OneDrive LTI portal, and then select **Next**.</span></span>

6. <span data-ttu-id="fe55f-138">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fe55f-138">Select **Save**.</span></span>

7. <span data-ttu-id="fe55f-139">Exibir as configurações selecionando **Exibir Locatários LTI**.</span><span class="sxs-lookup"><span data-stu-id="fe55f-139">View the settings by selecting **View LTI Tenants**.</span></span>
