---
title: Uma visão geral dos aplicativos LTI
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: amitman, sovaish
ms.date: 06/15/2021
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- M365-modern-desktop
localization_priority: None
description: Saiba mais sobre Learning interoperabilidade de ferramentas (LTI) Office aplicativos no M365 e como eles ajudarão os educadores ao integrarem Office aplicativos ao seu sistema de gerenciamento Learning (LMS).
ms.openlocfilehash: 4fd7b25b6463eec4f681e3090bb65db8b00351a8
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256670"
---
# <a name="integrating-microsoft-products-with-your-learning-management-system-lms"></a><span data-ttu-id="f646c-103">Integrando produtos Microsoft ao seu Learning de Gerenciamento (LMS)</span><span class="sxs-lookup"><span data-stu-id="f646c-103">Integrating Microsoft products with your Learning Management System (LMS)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f646c-104">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="f646c-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f646c-105">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="f646c-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

- [<span data-ttu-id="f646c-106">OneDrive LTI com Canvas</span><span class="sxs-lookup"><span data-stu-id="f646c-106">OneDrive LTI with Canvas</span></span>](#onedrive-lti-with-canvas)
- [<span data-ttu-id="f646c-107">Teams Reuniões LTI com Canvas</span><span class="sxs-lookup"><span data-stu-id="f646c-107">Teams Meetings LTI with Canvas</span></span>](#teams-meetings-lti-with-canvas)
- [<span data-ttu-id="f646c-108">Teams Classes LTI</span><span class="sxs-lookup"><span data-stu-id="f646c-108">Teams Classes LTI</span></span>](#teams-classes-lti)

<span data-ttu-id="f646c-109">A Microsoft Education e nossos parceiros de terceiros entendem que o fluxo de ensino e aprendizagem, invariavelmente, cruza os limites da solução.</span><span class="sxs-lookup"><span data-stu-id="f646c-109">Microsoft Education and our third-party partners understand that the flow of teaching and learning invariably crosses solution boundaries.</span></span> <span data-ttu-id="f646c-110">Estamos trabalhando para oferecer experiências mais perfeitas, manter educadores e alunos focados em seus objetivos, em vez de ter que fazer malabarismo com ferramentas.</span><span class="sxs-lookup"><span data-stu-id="f646c-110">We're working on providing more seamless experiences, keeping educators and learners focused on their goals, rather than having to juggle tools.</span></span> <span data-ttu-id="f646c-111">Estamos integrando produtos da Microsoft onde quer que ocorra o ensino e a aprendizagem, incluindo dentro e Learning Sistemas de Gerenciamento (LMS).</span><span class="sxs-lookup"><span data-stu-id="f646c-111">We're integrating Microsoft products wherever teaching and learning occurs, including within and alongside Learning Management Systems (LMS).</span></span> <span data-ttu-id="f646c-112">Trabalhamos com nossos parceiros LMS para criar um pacote de ferramentas usando o padrão de interoperabilidade de ferramentas [Learning (LTI)](https://www.imsglobal.org/activity/learning-tools-interoperability) que traz o melhor da Microsoft diretamente para seu LMS.</span><span class="sxs-lookup"><span data-stu-id="f646c-112">We've worked with our LMS partners to create a suite of tools using the [Learning Tools Interoperability (LTI) standard](https://www.imsglobal.org/activity/learning-tools-interoperability) that brings the best of Microsoft directly into your LMS.</span></span>

<span data-ttu-id="f646c-113">Essas ferramentas incluem um novo aplicativo OneDrive LTI, um novo aplicativo LTI de reuniões Teams reuniões e um novo aplicativo Teams LTI de classe.</span><span class="sxs-lookup"><span data-stu-id="f646c-113">These tools include a new OneDrive LTI app, a new Teams Meetings LTI app, and a new Class Teams LTI app.</span></span> <span data-ttu-id="f646c-114">Essas novas ferramentas são altamente seguras e totalmente compatíveis com os padrões LTI 1.3 e LTI Advantage.</span><span class="sxs-lookup"><span data-stu-id="f646c-114">These new tools are highly secure and fully compatible with LTI 1.3 and LTI Advantage standards.</span></span> <span data-ttu-id="f646c-115">O OneDrive LTI permite que educadores e alunos OneDrive arquivos de armazenamento em nuvem e Office 365 diretamente em fluxos de trabalho de atribuição e criação de conteúdo em um LMS.</span><span class="sxs-lookup"><span data-stu-id="f646c-115">The OneDrive LTI app allows educators and students to bring OneDrive cloud storage and Office 365 files directly into assignment and content creation workflows within an LMS.</span></span> <span data-ttu-id="f646c-116">O Teams de reuniões LTI permite que educadores e alunos gerenciem, agendem e acessem suas reuniões Teams de dentro de um hub de reuniões em seu LMS.</span><span class="sxs-lookup"><span data-stu-id="f646c-116">The Teams Meetings LTI app allows educators and students to manage, schedule, and access their Teams Meetings from within a meetings hub in their LMS.</span></span> <span data-ttu-id="f646c-117">O aplicativo Teams LTI de classe permite que os educadores criem uma equipe para seu curso em seu LMS usando a lista de cursos LMS com atualizações de lista diária.</span><span class="sxs-lookup"><span data-stu-id="f646c-117">The Class Teams LTI app allows educators to create a team for their course within their LMS using the LMS course roster with daily roster updates.</span></span> <span data-ttu-id="f646c-118">Em seguida, os alunos podem acessar a equipe de dentro do LMS.</span><span class="sxs-lookup"><span data-stu-id="f646c-118">Students can then access the team right from within the LMS.</span></span> <span data-ttu-id="f646c-119">Estamos animados em trazer essas novas ferramentas aos clientes e continuar a melhorar nossas soluções de acordo com seus comentários.</span><span class="sxs-lookup"><span data-stu-id="f646c-119">We are excited to bring these new tools to customers and continue to improve our solutions according to your feedback.</span></span>

## <a name="onedrive-lti-with-canvas"></a><span data-ttu-id="f646c-120">OneDrive LTI com Canvas</span><span class="sxs-lookup"><span data-stu-id="f646c-120">OneDrive LTI with Canvas</span></span>

<span data-ttu-id="f646c-121">Saiba mais sobre como usar Microsoft OneDrive com seu Learning De gerenciamento (LMS).</span><span class="sxs-lookup"><span data-stu-id="f646c-121">Learn more about using Microsoft OneDrive with your Learning Management System (LMS).</span></span>

- <span data-ttu-id="f646c-122">**Traz Microsoft Office 365 diretamente para seus fluxos de trabalho**</span><span class="sxs-lookup"><span data-stu-id="f646c-122">**Brings Microsoft Office 365 directly into your workflows**</span></span>

<span data-ttu-id="f646c-123">O Microsoft OneDrive LTI se integra ao seu LMS para Microsoft OneDrive e Microsoft Office 365 diretamente nos fluxos de trabalho mais importantes que incluem:</span><span class="sxs-lookup"><span data-stu-id="f646c-123">The Microsoft OneDrive LTI app integrates with your LMS to bring Microsoft OneDrive and Microsoft Office 365 directly into your most important workflows that include:</span></span>

- <span data-ttu-id="f646c-124">Anexando recursos e organizando conteúdo.</span><span class="sxs-lookup"><span data-stu-id="f646c-124">Attaching resources and organizing content.</span></span>
- <span data-ttu-id="f646c-125">Iniciando documentos colaborativos.</span><span class="sxs-lookup"><span data-stu-id="f646c-125">Starting collaborative documents.</span></span>
- <span data-ttu-id="f646c-126">Criação e classificação de atribuições.</span><span class="sxs-lookup"><span data-stu-id="f646c-126">Creating and grading assignments.</span></span>

- <span data-ttu-id="f646c-127">**Seguro e totalmente em conformidade com os padrões LTI mais recentes**</span><span class="sxs-lookup"><span data-stu-id="f646c-127">**Secure and fully compliant with latest LTI standards**</span></span>

<span data-ttu-id="f646c-128">O Microsoft OneDrive LTI App é compatível com LTI 1.3 e LTI Advantage.</span><span class="sxs-lookup"><span data-stu-id="f646c-128">The Microsoft OneDrive LTI App is compatible with LTI 1.3 and LTI Advantage.</span></span> <span data-ttu-id="f646c-129">Essa vantagem permite uma experiência de usuário altamente segura e integrada.</span><span class="sxs-lookup"><span data-stu-id="f646c-129">This advantage allows for a highly secure and tightly integrated user experience.</span></span>

- <span data-ttu-id="f646c-130">**Experiência do usuário moderna e rica**</span><span class="sxs-lookup"><span data-stu-id="f646c-130">**Modern and Rich User Experience**</span></span>

<span data-ttu-id="f646c-131">O Microsoft OneDrive LTI app traz o melhor da Microsoft para sua experiência lms.</span><span class="sxs-lookup"><span data-stu-id="f646c-131">The Microsoft OneDrive LTI App brings the best of Microsoft right into your LMS experience.</span></span> <span data-ttu-id="f646c-132">Estamos melhorando a integração de Office 365 existente em seu LMS, fornecendo uma experiência de usuário mais moderna, completa com um selador de arquivos Microsoft OneDrive novo e expandido e experiências de edição mais ricas para arquivos Office.</span><span class="sxs-lookup"><span data-stu-id="f646c-132">We're improving upon the existing Office 365 integration in your LMS by delivering a more modern user experience, complete with a new and expanded Microsoft OneDrive file picker and richer editing experiences for Office files.</span></span> <span data-ttu-id="f646c-133">A Microsoft também será totalmente a Microsoft OneDrive aplicativo LTI daqui para frente, o que significa que você sempre receberá o mais recente e o melhor da Microsoft automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f646c-133">Microsoft will also fully own the Microsoft OneDrive LTI App going forward, which means you’ll always get the latest and greatest from Microsoft automatically.</span></span>

<span data-ttu-id="f646c-134">O Microsoft OneDrive LTI App permite que você:</span><span class="sxs-lookup"><span data-stu-id="f646c-134">The Microsoft OneDrive LTI App allows you to:</span></span>

- <span data-ttu-id="f646c-135">Anexe Office 365 arquivos, incluindo documentos do Word, PowerPoint apresentações e Excel do Editor de Conteúdo Rico.</span><span class="sxs-lookup"><span data-stu-id="f646c-135">Attach Office 365 files including Word documents, PowerPoint presentations, and Excel from the Rich Content Editor.</span></span>
- <span data-ttu-id="f646c-136">Distribua Office 365 de nuvem.</span><span class="sxs-lookup"><span data-stu-id="f646c-136">Distribute Office 365 cloud assignments.</span></span>
- <span data-ttu-id="f646c-137">Exibir e organizar seus arquivos pessoais e Microsoft OneDrive curso.</span><span class="sxs-lookup"><span data-stu-id="f646c-137">View and organize your personal and course Microsoft OneDrive files.</span></span>
- <span data-ttu-id="f646c-138">Crie colaborações nas quais os membros do curso possam trabalhar juntos em documentos compartilhados em tempo real.</span><span class="sxs-lookup"><span data-stu-id="f646c-138">Create collaborations where course members can work together on shared documents in real time.</span></span>
- <span data-ttu-id="f646c-139">Acesse várias Microsoft OneDrive, incluindo contas pessoais e de estudante.</span><span class="sxs-lookup"><span data-stu-id="f646c-139">Access multiple Microsoft OneDrive accounts, including personal and school accounts.</span></span>
- <span data-ttu-id="f646c-140">Integre Office 365 arquivos com seus módulos de curso.</span><span class="sxs-lookup"><span data-stu-id="f646c-140">Integrate Office 365 files with your course modules.</span></span>
- <span data-ttu-id="f646c-141">Use sua conta da Microsoft para fazer o login único com seu LMS.</span><span class="sxs-lookup"><span data-stu-id="f646c-141">Use your Microsoft account for single sign-on with your LMS.</span></span>

<span data-ttu-id="f646c-142">Para etapas de configuração, [consulte Use Microsoft OneDrive LTI com Canvas](use-onedrive-with-lms.md).</span><span class="sxs-lookup"><span data-stu-id="f646c-142">For configuration steps, see [Use Microsoft OneDrive LTI with Canvas](use-onedrive-with-lms.md).</span></span>

## <a name="teams-lti-apps"></a><span data-ttu-id="f646c-143">Teams Aplicativos LTI</span><span class="sxs-lookup"><span data-stu-id="f646c-143">Teams LTI apps</span></span>

### <a name="teams-meetings-lti-with-canvas"></a><span data-ttu-id="f646c-144">Teams Reuniões LTI com Canvas</span><span class="sxs-lookup"><span data-stu-id="f646c-144">Teams Meetings LTI with Canvas</span></span>

<span data-ttu-id="f646c-145">Microsoft Teams reuniões O aplicativo LTI ajuda os administradores a incorporar Teams reuniões no curso LMS da instituição educacional.</span><span class="sxs-lookup"><span data-stu-id="f646c-145">Microsoft Teams meetings LTI app helps admins incorporate Teams meetings into their educational institution's LMS course.</span></span> <span data-ttu-id="f646c-146">Educadores e alunos podem exibir reuniões passadas e futuras, agendar reuniões individuais ou recorrentes e participar de reuniões de equipe relacionadas ao curso, tudo de dentro de seu LMS.</span><span class="sxs-lookup"><span data-stu-id="f646c-146">Educators and students can view past and upcoming meetings, schedule individual or recurring meetings, and join team meetings related to the course, all from within their LMS.</span></span>

<span data-ttu-id="f646c-147">Para etapas de configuração, [consulte Use Microsoft Teams reuniões com Canvas](teams-meetings-with-canvas.md).</span><span class="sxs-lookup"><span data-stu-id="f646c-147">For configuration steps, see [Use Microsoft Teams meetings with Canvas](teams-meetings-with-canvas.md).</span></span>

### <a name="teams-classes-lti"></a><span data-ttu-id="f646c-148">Teams Classes LTI</span><span class="sxs-lookup"><span data-stu-id="f646c-148">Teams Classes LTI</span></span>

<span data-ttu-id="f646c-149">O Microsoft Teams de classes LTI ajuda educadores e alunos a navegar entre seus LMS e Teams.</span><span class="sxs-lookup"><span data-stu-id="f646c-149">The Microsoft Teams classes LTI app helps educators and students navigate between their LMS and Teams.</span></span> <span data-ttu-id="f646c-150">Os usuários podem acessar suas equipes de classe associadas ao curso diretamente de dentro do LMS.</span><span class="sxs-lookup"><span data-stu-id="f646c-150">Users can access their class teams associated with their course directly from within their LMS.</span></span> <span data-ttu-id="f646c-151">Você pode encontrar as etapas de configuração abaixo:</span><span class="sxs-lookup"><span data-stu-id="f646c-151">You can find configuration steps below:</span></span>

- <span data-ttu-id="f646c-152">**Teams classes LTI com Canvas** [Use Microsoft Teams classes com Canvas](teams-classes-with-canvas.md).</span><span class="sxs-lookup"><span data-stu-id="f646c-152">**Teams Classes LTI with Canvas** [Use Microsoft Teams classes with Canvas](teams-classes-with-canvas.md).</span></span>
