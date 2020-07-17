---
title: Criar e acompanhar tíquetes do ServiceNow no centro de segurança do Microsoft 365
description: Saiba como criar e acompanhar tíquetes no ServiceNow do centro de segurança do Microsoft 365.
keywords: segurança, Microsoft 365, M365, Pontuação segura, central de segurança, ServiceNow, tíquetes, tarefas
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 16ee37b1c7bf33c902db35af2d29744f42830ea7
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094829"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="b7634-104">Criar e acompanhar tíquetes do ServiceNow no centro de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b7634-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

<span data-ttu-id="b7634-105">O [centro de segurança do Microsoft 365](overview-security-center.md) foi aprimorado com a capacidade de criar e controlar de forma nativa as permissões no ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="b7634-105">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="b7634-106">Saiba mais sobre o ServiceNow</span><span class="sxs-lookup"><span data-stu-id="b7634-106">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="b7634-107">Na central de segurança, os administradores de segurança podem enviar uma ação de melhoria de [Pontuação segura da Microsoft](microsoft-secure-score.md) diretamente para o ServiceNow e criar uma permissão.</span><span class="sxs-lookup"><span data-stu-id="b7634-107">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="b7634-108">As permissões de gerenciamento de incidentes e de alterações podem ser criadas.</span><span class="sxs-lookup"><span data-stu-id="b7634-108">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="b7634-109">Eles podem ser rastreados na home page do centro de segurança e o ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="b7634-109">They can then be tracked in the security center home page, and ServiceNow.</span></span>

- [<span data-ttu-id="b7634-110">**Saiba mais sobre os pré-requisitos, a troca de dados e a solução de problemas**</span><span class="sxs-lookup"><span data-stu-id="b7634-110">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="b7634-111">**Gerenciar tíquetes do ServiceNow no centro de conformidade** (em breve)</span><span class="sxs-lookup"><span data-stu-id="b7634-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="b7634-112">Conectar a central de segurança do Microsoft 365 ao ServiceNow</span><span class="sxs-lookup"><span data-stu-id="b7634-112">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="b7634-113">Navegue até a home page do centro de segurança do Microsoft 365 para ver o cartão de conexão do ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="b7634-113">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Você usa o ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="b7634-115">Selecione "conectar ao ServiceNow" para ir para a página de configuração do ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="b7634-115">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="b7634-116">Siga as instruções para autorizar o aplicativo conector 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b7634-116">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="b7634-117">Antes de autorizar a conexão entre o centro de segurança do Microsoft 365 e o ServiceNow, certifique-se de usar o logon e a senha de usuário de integração que você criou nas etapas de instalação.</span><span class="sxs-lookup"><span data-stu-id="b7634-117">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="b7634-118">Não use suas credenciais pessoais.</span><span class="sxs-lookup"><span data-stu-id="b7634-118">Do not use your personal credentials.</span></span>

<span data-ttu-id="b7634-119">Após ter seguido as orientações e autorizar a conexão, veja o status da conexão na página conexão da central de segurança do Microsoft 365 e na experiência do aplicativo do Microsoft 365 Ticketing Connector.</span><span class="sxs-lookup"><span data-stu-id="b7634-119">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="b7634-120">Agora, você está pronto para começar a criar tarefas!</span><span class="sxs-lookup"><span data-stu-id="b7634-120">Now you are all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="b7634-121">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="b7634-121">Troubleshooting</span></span>

<span data-ttu-id="b7634-122">Saiba mais sobre os erros comuns que você pode encontrar no processo de conexão e como atenuá-los, na [seção solução de problemas](tickets.md#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="b7634-122">Learn common errors you may encounter in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="b7634-123">Criar uma tarefa e compartilhá-la para o ServiceNow</span><span class="sxs-lookup"><span data-stu-id="b7634-123">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="b7634-124">Depois que a integração é configurada, crie tarefas do ServiceNow com base em ações específicas de melhoria da [Pontuação segura da Microsoft](microsoft-secure-score.md) .</span><span class="sxs-lookup"><span data-stu-id="b7634-124">Once the integration is set up, create ServiceNow tasks based on specific [Microsoft Secure Score](microsoft-secure-score.md) improvement actions.</span></span> <span data-ttu-id="b7634-125">Vá para qualquer ação de melhoria na pontuação segura no portal da central de segurança do Microsoft 365 e selecione **compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="b7634-125">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select **Share**.</span></span> <span data-ttu-id="b7634-126">Uma das opções de DropDown é o ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="b7634-126">One of the dropdown options is ServiceNow.</span></span>

<span data-ttu-id="b7634-127">Uma tarefa é gerada onde você pode definir a prioridade e editar o nome, a descrição ou a data de conclusão.</span><span class="sxs-lookup"><span data-stu-id="b7634-127">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="b7634-128">Após todos os campos obrigatórios serem preenchidos, envie a tarefa para o ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="b7634-128">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="b7634-129">A tarefa está visível no ServiceNow como uma solicitação de alteração de configuração e segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b7634-129">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="b7634-130">Controlar ingressos</span><span class="sxs-lookup"><span data-stu-id="b7634-130">Track tickets</span></span>

<span data-ttu-id="b7634-131">Depois que o gerenciamento de alterações e as permissões de gerenciamento de incidentes tiverem sido criados, eles serão exibidos em cartões na home page do centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b7634-131">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="b7634-132">A partir desses cartões, você pode criar um tíquete, exibir todos os tíquetes ou gerenciar a configuração do ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="b7634-132">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Tíquetes de gerenciamento de alterações do ServiceNow](../../media/change-management-375.png)  ![Tíquetes de gerenciamento de incidentes do ServiceNow](../../media/incident-management-375.png)

<span data-ttu-id="b7634-135">Para reprovisionar ou gerenciar sua integração do ServiceNow no centro de segurança do Microsoft 365, selecione **gerenciar a configuração do servicenow** em qualquer um dos cartões.</span><span class="sxs-lookup"><span data-stu-id="b7634-135">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="b7634-136">A partir daí, remova a conexão atual do ServiceNow e personalize os nomes de estado de tíquete.</span><span class="sxs-lookup"><span data-stu-id="b7634-136">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="b7634-137">Com as permissões do ServiceNow visíveis no centro de segurança do Microsoft 365, suas tarefas residem em um local onde elas podem ser rastreadas e aplicadas junto com seus outros itens do painel de segurança.</span><span class="sxs-lookup"><span data-stu-id="b7634-137">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="b7634-138">Recursos</span><span class="sxs-lookup"><span data-stu-id="b7634-138">Resources</span></span>

- [<span data-ttu-id="b7634-139">Saiba mais sobre os pré-requisitos, a troca de dados e a solução de problemas</span><span class="sxs-lookup"><span data-stu-id="b7634-139">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="b7634-140">Classificação de Segurança da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b7634-140">Microsoft Secure Score</span></span>](microsoft-secure-score.md)