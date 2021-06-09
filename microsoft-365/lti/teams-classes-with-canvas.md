---
title: Usar Microsoft Teams classes com Canvas
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
description: Integrar Microsoft Teams com o Canvas
ms.openlocfilehash: 1a16d6a4f5e0cfbb592c335163bb4e33fd3c1301
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821863"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="3a41a-103">Usar Microsoft Teams classes com Canvas</span><span class="sxs-lookup"><span data-stu-id="3a41a-103">Use Microsoft Teams classes with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a41a-104">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="3a41a-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3a41a-105">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="3a41a-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="3a41a-106">Microsoft Teams classes é um aplicativo de Interoperabilidade de Ferramentas de Aprendizagem (LTI) que ajuda educadores e alunos a navegar facilmente entre seu LMS (Sistema de Gerenciamento de Aprendizagem) e Teams.</span><span class="sxs-lookup"><span data-stu-id="3a41a-106">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="3a41a-107">Os usuários podem acessar suas equipes de classe associadas ao curso diretamente de dentro do LMS.</span><span class="sxs-lookup"><span data-stu-id="3a41a-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="3a41a-108">Microsoft Office 365 Admin</span><span class="sxs-lookup"><span data-stu-id="3a41a-108">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="3a41a-109">Antes de gerenciar a integração do Microsoft Teams no Instructure Canvas, é importante que o aplicativo **microsoft-Teams-Sync-for-Canvas** do Canvas do Canvas seja aprovado pelo administrador do Microsoft Office 365 da sua instituição em seu locatário do Microsoft Azure antes de concluir a configuração do administrador do Canvas.</span><span class="sxs-lookup"><span data-stu-id="3a41a-109">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="3a41a-110">Entre no Canvas.</span><span class="sxs-lookup"><span data-stu-id="3a41a-110">Sign in to Canvas.</span></span>
 
2. <span data-ttu-id="3a41a-111">Selecione o link **Administrador** na navegação global e selecione sua conta.</span><span class="sxs-lookup"><span data-stu-id="3a41a-111">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="3a41a-112">Na navegação do administrador, selecione o link **Configurações** e, em seguida, a **guia** Integrações.</span><span class="sxs-lookup"><span data-stu-id="3a41a-112">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span> 

4. <span data-ttu-id="3a41a-113">Insira seu atributo de logon e nome de locatário da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3a41a-113">Enter your Microsoft tenant name and login attribute.</span></span> 

   <span data-ttu-id="3a41a-114">O atributo login será usado para associar o usuário do Canvas a um Azure Active Directory usuário.</span><span class="sxs-lookup"><span data-stu-id="3a41a-114">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span> 

5. <span data-ttu-id="3a41a-115">Selecione **Atualizar Configurações** uma vez feito.</span><span class="sxs-lookup"><span data-stu-id="3a41a-115">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="3a41a-116">Para aprovar o acesso ao **aplicativo Microsoft-Teams-Sync-for-Canvas** do Canvas do Canvas, selecione o link Conceder acesso **ao** locatário.</span><span class="sxs-lookup"><span data-stu-id="3a41a-116">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="3a41a-117">Você será redirecionado para o Ponto de Extremidade de Consentimento de Administrador da Plataforma de Identidade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3a41a-117">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![permissões](media/permissions.png)

7. <span data-ttu-id="3a41a-119">Selecione **Aceitar**.</span><span class="sxs-lookup"><span data-stu-id="3a41a-119">Select **Accept**.</span></span>
 
8. <span data-ttu-id="3a41a-120">Habilita Microsoft Teams sincronização ativando a alternância.</span><span class="sxs-lookup"><span data-stu-id="3a41a-120">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="3a41a-122">Administrador do Canvas</span><span class="sxs-lookup"><span data-stu-id="3a41a-122">Canvas Admin</span></span>

<span data-ttu-id="3a41a-123">Configurar a integração Microsoft Teams LTI 1.3.</span><span class="sxs-lookup"><span data-stu-id="3a41a-123">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="3a41a-124">Como administrador do Canvas, você precisará adicionar o aplicativo LTI de classes Microsoft Teams no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="3a41a-124">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="3a41a-125">Anote a ID do Cliente LTI para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3a41a-125">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="3a41a-126">Microsoft Teams classes - 17000000000570</span><span class="sxs-lookup"><span data-stu-id="3a41a-126">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="3a41a-127">Configurações **do Administrador do** Access  >  **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="3a41a-127">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="3a41a-128">Selecione **+ Aplicativo** para adicionar os aplicativos Teams LTI.</span><span class="sxs-lookup"><span data-stu-id="3a41a-128">Select **+ App** to add the Teams LTI apps.</span></span> 
 
   ![external-apps](media/external-apps.png)

3. <span data-ttu-id="3a41a-130">Selecione **Por ID do Cliente para** o tipo de configuração.</span><span class="sxs-lookup"><span data-stu-id="3a41a-130">Select **By Client ID** for configuration type.</span></span>

   ![adicionar aplicativo](media/add-app.png)

4. <span data-ttu-id="3a41a-132">Insira a ID do Cliente fornecida e selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="3a41a-132">Enter the Client ID provided, and then select **Submit**.</span></span>
   
   <span data-ttu-id="3a41a-133">Você notará o nome do aplicativo LTI Microsoft Teams classes para a ID do Cliente para confirmação.</span><span class="sxs-lookup"><span data-stu-id="3a41a-133">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span> 

5. <span data-ttu-id="3a41a-134">Selecionar **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="3a41a-134">Select **Install**.</span></span>

   <span data-ttu-id="3a41a-135">O Microsoft Teams de classes LTI será adicionado à lista de aplicativos externos.</span><span class="sxs-lookup"><span data-stu-id="3a41a-135">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
