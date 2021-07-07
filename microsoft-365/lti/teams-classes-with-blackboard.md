---
title: Integrar Microsoft Teams classes com Blackboard Learn Ultra
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
description: Integrar Microsoft Teams classes com Blackboard Learn Ultra
ms.openlocfilehash: da98fae3fa5d6be2513147be58747512bea99e16
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314483"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a><span data-ttu-id="f9e08-103">Usar Microsoft Teams classes com Blackboard Learn Ultra</span><span class="sxs-lookup"><span data-stu-id="f9e08-103">Use Microsoft Teams classes with Blackboard Learn Ultra</span></span>

<span data-ttu-id="f9e08-104">O trabalho em equipe está no centro de todas as organizações modernas.</span><span class="sxs-lookup"><span data-stu-id="f9e08-104">Teamwork is at the core of every modern organization.</span></span> <span data-ttu-id="f9e08-105">Ao promover a colaboração, é uma característica de definição de cada instituição bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="f9e08-105">By fostering collaboration, it’s a defining characteristic of every successful institution.</span></span> <span data-ttu-id="f9e08-106">Você pode aprimorar todos os recursos e recursos do Blackboard Learn Ultra emparelhando-os com Microsoft Teams classes.</span><span class="sxs-lookup"><span data-stu-id="f9e08-106">You can enhance all the capabilities and features of Blackboard Learn Ultra by pairing them up with Microsoft Teams classes.</span></span>

<span data-ttu-id="f9e08-107">Suas aulas podem incluir conversas em tempo real, reuniões em vídeo ou interações assíncronas.</span><span class="sxs-lookup"><span data-stu-id="f9e08-107">Your classes might include real-time conversations, video meetings, or asynchronous interactions.</span></span> <span data-ttu-id="f9e08-108">Você pode adicionar experiências de compartilhamento e cocriação de arquivos para seus alunos, tudo em um só lugar.</span><span class="sxs-lookup"><span data-stu-id="f9e08-108">You can add file sharing and cocreation experiences for your students, all in one place.</span></span> <span data-ttu-id="f9e08-109">Microsoft Teams aulas com Learn Ultra redefinem a dinâmica do ensino e o que significa aprendizagem eficaz.</span><span class="sxs-lookup"><span data-stu-id="f9e08-109">Microsoft Teams classes with Learn Ultra redefine the dynamics of teaching and what effective learning means.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9e08-110">Verifique se você definiu com êxito o campo Email da Instituição em seu Sistema de Informações do Aluno (SIS) `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`</span><span class="sxs-lookup"><span data-stu-id="f9e08-110">Ensure that you have successfully set up the Institution Email field in your Student Information System (SIS) `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`</span></span>
>
><span data-ttu-id="f9e08-111">A integração Microsoft Teams classes depende do campo de email da instituição em seu SIS para mapear para o UPN (Nome de Entidade de Usuário) do Microsoft Azure Active Directory (AAD) correto.</span><span class="sxs-lookup"><span data-stu-id="f9e08-111">The Microsoft Teams classes integration relies on the institution email field in your SIS to map to the correct Microsoft Azure Active Directory’s (AAD) User Principal Name (UPN).</span></span> <span data-ttu-id="f9e08-112">Se nenhum email da instituição tiver sido provisionado, isso será padrão para o email existente.</span><span class="sxs-lookup"><span data-stu-id="f9e08-112">If no institution email has been provisioned, this will default to the existing email.</span></span> <span data-ttu-id="f9e08-113">É recomendável que esse campo seja definido para cada usuário garantir que seus dados sejam sincronizados corretamente e que não haja conflito de dados de email entre o Microsoft AAD e o Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="f9e08-113">It’s recommended that this field be set for every user to ensure their data is synchronized correctly and that there is no conflict of email data between Microsoft AAD and Blackboard Learn Ultra.</span></span>
>
> <span data-ttu-id="f9e08-114">Se você não tiver definido esse campo adequadamente no mapeamento do SIS, a integração continuará a funcionar, mas os usuários podem não aparecer nas classes Teams criadas, e erros poderão ocorrer.</span><span class="sxs-lookup"><span data-stu-id="f9e08-114">If you haven’t set this field appropriately in your SIS mapping, the integration will continue to work, but users might not appear in the Teams classes created, and errors could occur.</span></span>

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a><span data-ttu-id="f9e08-115">Suporte ao Mapeamento de Dados Institucionais – Campo do SIS de Email da Instituição</span><span class="sxs-lookup"><span data-stu-id="f9e08-115">Supporting Institutional Data Mapping – Institution Email SIS Field</span></span>

<span data-ttu-id="f9e08-116">Como parte da evolução com integrações de provedores  de nuvem, o Blackboard Learn Ultra criou um novo campo email de instituição, tanto na integração da Estrutura de Sistema de Informações do Aluno quanto em APIs REST públicas, permitindo que as instituições gerenciem o processo de sincronização de dados efetivamente entre Blackboard Learn Ultra e Microsoft AAD.</span><span class="sxs-lookup"><span data-stu-id="f9e08-116">As part of the evolution with Cloud provider integrations, Blackboard Learn Ultra has created a new **Institution Email** field, in both the Student Information System Framework integration and public REST APIs, allowing institutions to manage the data synchronization process effectively between Blackboard Learn Ultra and Microsoft AAD.</span></span>

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a><span data-ttu-id="f9e08-117">O que significa o Email da Instituição e o que ele dá suporte?</span><span class="sxs-lookup"><span data-stu-id="f9e08-117">What does the Institution Email mean and what does it support?</span></span>

<span data-ttu-id="f9e08-118">O **campo Email da** Instituição permite mapeamentos de campo personalizados entre as fontes de dados com suporte externo de um cliente e o Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="f9e08-118">The **Institution Email** field allows customized field mappings between a client’s externally supported data sources and Blackboard Learn Ultra.</span></span> <span data-ttu-id="f9e08-119">Se fontes de dados são provedores de nuvem, como a Microsoft, o Nome de Princípio do Usuário (UPN) é um identificador exclusivo principal para cada usuário que consiste em um prefixo UPN (o nome da conta do usuário) e um sufixo UPN (um nome de domínio DNS) unido com um símbolo @.</span><span class="sxs-lookup"><span data-stu-id="f9e08-119">If data sources are cloud providers, such as Microsoft, the User Principle Name (UPN) is a primary unique identifier for each user consisting of a UPN prefix (the user’s account name) and a UPN suffix (a DNS domain name) joined together with an @ symbol.</span></span> <span data-ttu-id="f9e08-120">Isso cria um endereço de email exclusivo para cada usuário específico dentro do Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f9e08-120">This creates a unique email address for each specific user within the Microsoft Azure Active Directory.</span></span>

<span data-ttu-id="f9e08-121">Para garantir que os dados sejam precisos e que as inscrições ou associações entre as classes Blackboard Learn Ultra e Microsoft Teams sejam atingidas corretamente, o endereço de email de um usuário deve corresponder entre ambos os sistemas.</span><span class="sxs-lookup"><span data-stu-id="f9e08-121">To ensure data is accurate and enrollments or memberships between Blackboard Learn Ultra and Microsoft Teams classes are correctly achieved, a user’s email address must match between both systems.</span></span> <span data-ttu-id="f9e08-122">No Blackboard Learn Ultra, os usuários podem alterar ou substituir o endereço de email existente na interface do usuário, o que pode resultar em erros de sincronização e o usuário não ser adicionado corretamente a uma Equipe de Classe.</span><span class="sxs-lookup"><span data-stu-id="f9e08-122">In Blackboard Learn Ultra, users can change or override their existing email address in the user interface, which could result in sync errors occurring and the user not being correctly added to a Class Team.</span></span> <span data-ttu-id="f9e08-123">O **mapeamento de campo Email** da Instituição garante que esse nível de verificação de segurança e validação possa ser gerenciado corretamente, independentemente de os usuários ter alterado seus emails no Blackboard Learn Ultra ou não.</span><span class="sxs-lookup"><span data-stu-id="f9e08-123">The **Institution Email** field mapping ensures this level of security and validation checking can be correctly managed, regardless if users have changed their email within Blackboard Learn Ultra or not.</span></span>

 <span data-ttu-id="f9e08-124">Quando dois endereços de email são diferentes, ambos:</span><span class="sxs-lookup"><span data-stu-id="f9e08-124">When two email addresses are different, either:</span></span>

- <span data-ttu-id="f9e08-125">Uma decisão deve ser tomada sobre qual fonte tem precedência e será tomada como emails de pessoa e instituição.</span><span class="sxs-lookup"><span data-stu-id="f9e08-125">A decision must be made as to which source has precedence and will be taken as both the Person and Institution Emails.</span></span>
  <span data-ttu-id="f9e08-126">Ou</span><span class="sxs-lookup"><span data-stu-id="f9e08-126">Or</span></span>
- <span data-ttu-id="f9e08-127">Uma instituição pode definir um mapeamento de campo personalizado em seu Email da Instituição, o que pode resolver um possível conflito.</span><span class="sxs-lookup"><span data-stu-id="f9e08-127">An institution can set a custom field mapping in its Institution Email, which can resolve a potential conflict.</span></span>

<span data-ttu-id="f9e08-128">O **mapeamento de campo Email** da Instituição agora está disponível para todos os tipos de integração do SIS existentes no Advanced Configuration **Configurações** Users Learn Object  >  **Type** Field  >  **Mapping**.</span><span class="sxs-lookup"><span data-stu-id="f9e08-128">The **Institution Email** field mapping is now available for all existing SIS integration types at **Advanced Configuration Settings** > **Users Learn Object Type** > **Field Mapping**.</span></span>

> [!NOTE]
> <span data-ttu-id="f9e08-129">É importante observar que, por padrão, o Email  da Instituição é definido como o Email da Pessoa para todos os formatos do SIS e deve ser exclusivo para cada pessoa. </span><span class="sxs-lookup"><span data-stu-id="f9e08-129">It’s important to note that, by default, the **Institution Email** is set to the **Person Email** for all SIS formats and must be unique for each person.</span></span> <span data-ttu-id="f9e08-130">Todas as integrações existentes que estão configuradas e em execução terão esse mapeamento de dados in-loco, pois o SIS não importará os usuários se o email for duplicado.</span><span class="sxs-lookup"><span data-stu-id="f9e08-130">All existing integrations that are set up and running will have this data mapping in place, as SIS will fail to import users if their email is duplicated.</span></span> <span data-ttu-id="f9e08-131">Se uma instituição exigir a capacidade de alterar o Email da Instituição para **personalizado,** ele precisará gerenciá-lo por meio da configuração **avançada Configurações** no SIS.</span><span class="sxs-lookup"><span data-stu-id="f9e08-131">If an institution requires the ability to change the Institution Email to **custom**, they'll need to manage this through the **Advanced Configuration Settings** in the SIS.</span></span>

## <a name="requirements"></a><span data-ttu-id="f9e08-132">Requirements</span><span class="sxs-lookup"><span data-stu-id="f9e08-132">Requirements</span></span>

<span data-ttu-id="f9e08-133">A Microsoft Teams de classes está disponível apenas para cursos **de Modo de Exibição de Curso Ultra.**</span><span class="sxs-lookup"><span data-stu-id="f9e08-133">The Microsoft Teams classes integration is available for **Ultra Course View courses only**.</span></span> <span data-ttu-id="f9e08-134">Sua instituição precisa concluir esses requisitos para usá-lo:</span><span class="sxs-lookup"><span data-stu-id="f9e08-134">Your institution needs to complete these requirements to use it:</span></span>

- <span data-ttu-id="f9e08-135">Ter Blackboard Learn Ultra Learn SaaS with Ultra Base Navigation enabled</span><span class="sxs-lookup"><span data-stu-id="f9e08-135">Have Blackboard Learn Ultra Learn SaaS with Ultra Base Navigation enabled</span></span>

- <span data-ttu-id="f9e08-136">Habilitar LTI para uso em cursos.</span><span class="sxs-lookup"><span data-stu-id="f9e08-136">Enable LTI for use in courses.</span></span>

  <span data-ttu-id="f9e08-137">a.</span><span class="sxs-lookup"><span data-stu-id="f9e08-137">a.</span></span> <span data-ttu-id="f9e08-138">Vá para o **Painel de Administrador**  >  **Provedores de Ferramentas LTI** Gerenciar Propriedades  >  **Globais**.</span><span class="sxs-lookup"><span data-stu-id="f9e08-138">Go to the **Administrator Panel** > **LTI Tool Providers** > **Manage Global Properties**.</span></span>

  <span data-ttu-id="f9e08-139">b.</span><span class="sxs-lookup"><span data-stu-id="f9e08-139">b.</span></span> <span data-ttu-id="f9e08-140">Selecione **LTI Habilitado em Cursos** e, opcionalmente, selecione **Habilitado em Organizações**.</span><span class="sxs-lookup"><span data-stu-id="f9e08-140">Select **LTI Enabled in Courses**, and optionally, select **Enabled in Organizations**.</span></span>

  <span data-ttu-id="f9e08-141">c.</span><span class="sxs-lookup"><span data-stu-id="f9e08-141">c.</span></span> <span data-ttu-id="f9e08-142">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="f9e08-142">Select **Submit**.</span></span>

- <span data-ttu-id="f9e08-143">Deve ter LTI configurado</span><span class="sxs-lookup"><span data-stu-id="f9e08-143">Must have LTI configured</span></span>

- <span data-ttu-id="f9e08-144">Adicionar Blackboard Learn Ultra Teams Classes LTI Integration</span><span class="sxs-lookup"><span data-stu-id="f9e08-144">Add Blackboard Learn Ultra Teams Classes LTI Integration</span></span>

- <span data-ttu-id="f9e08-145">Adicionar Microsoft Teams classes LTI 1.3 Tool</span><span class="sxs-lookup"><span data-stu-id="f9e08-145">Add Microsoft Teams Classes LTI 1.3 Tool</span></span>

- <span data-ttu-id="f9e08-146">Adicionar a Ferramenta DE API REST e o Compartilhamento de Recursos de Origem Cruzada</span><span class="sxs-lookup"><span data-stu-id="f9e08-146">Add the REST API Tool and Cross-Origin Resource Sharing</span></span>

- <span data-ttu-id="f9e08-147">Configurar e aprovar a integração Microsoft Teams classes</span><span class="sxs-lookup"><span data-stu-id="f9e08-147">Configure and approve Microsoft Teams classes Integration</span></span>

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a><span data-ttu-id="f9e08-148">Adicionar a Ferramenta Learn Ultra Teams Classes LTI 1.3</span><span class="sxs-lookup"><span data-stu-id="f9e08-148">Add the Blackboard Learn Ultra Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="f9e08-149">No Painel **de Administrador,** selecione **Provedores de Ferramentas LTI.**</span><span class="sxs-lookup"><span data-stu-id="f9e08-149">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="f9e08-150">Selecione **registrar a Ferramenta LTI 1.3**.</span><span class="sxs-lookup"><span data-stu-id="f9e08-150">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="f9e08-151">No campo **ID do** Cliente, digite ou copie e colar esta ID:</span><span class="sxs-lookup"><span data-stu-id="f9e08-151">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="f9e08-152">Revise todas as configurações que foram pré-preenchidas e em **Status** da Ferramenta e selecione **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="f9e08-152">Review all settings that have been pre-populated and in **Tool Status**, and then select **Enabled**.</span></span>

5. <span data-ttu-id="f9e08-153">Em **Políticas de Instituição,** selecione **Função em Curso, Nome** e Endereço de **Email** e selecione **Sim** para ambos.</span><span class="sxs-lookup"><span data-stu-id="f9e08-153">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**, and then select **Yes** for both.</span></span>

6. <span data-ttu-id="f9e08-154">Selecione **Permitir acesso de serviço de nível e** Permitir Acesso ao Serviço de **Associação.**</span><span class="sxs-lookup"><span data-stu-id="f9e08-154">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a><span data-ttu-id="f9e08-155">Adicionar a ferramenta Microsoft Teams Classes LTI 1.3</span><span class="sxs-lookup"><span data-stu-id="f9e08-155">Add the Microsoft Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="f9e08-156">No Painel **de Administrador,** selecione **Provedores de Ferramentas LTI.**</span><span class="sxs-lookup"><span data-stu-id="f9e08-156">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="f9e08-157">Selecione **registrar a Ferramenta LTI 1.3**.</span><span class="sxs-lookup"><span data-stu-id="f9e08-157">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="f9e08-158">No campo **ID do** Cliente, digite ou copie e colar esta ID:</span><span class="sxs-lookup"><span data-stu-id="f9e08-158">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. <span data-ttu-id="f9e08-159">Revise todas as configurações que foram pré-preenchidas e em *Status da Ferramenta* e selecione *Habilitado.*</span><span class="sxs-lookup"><span data-stu-id="f9e08-159">Review all settings that have been pre-populated and in *Tool Status* and select *Enabled.*</span></span>

5. <span data-ttu-id="f9e08-160">Em **Políticas de Instituição,** selecione **Função no Curso, Nome** e Endereço de **Email.**</span><span class="sxs-lookup"><span data-stu-id="f9e08-160">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**.</span></span> <span data-ttu-id="f9e08-161">Selecione **Sim** para ambos.</span><span class="sxs-lookup"><span data-stu-id="f9e08-161">Select **Yes** for both.</span></span>

6. <span data-ttu-id="f9e08-162">Selecione **Permitir acesso de serviço de nível e** Permitir Acesso ao Serviço de **Associação.**</span><span class="sxs-lookup"><span data-stu-id="f9e08-162">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-rest-api-tool"></a><span data-ttu-id="f9e08-163">Adicionar a ferramenta DE API REST</span><span class="sxs-lookup"><span data-stu-id="f9e08-163">Add the REST API tool</span></span>

1. <span data-ttu-id="f9e08-164">No Painel **de Administrador,** navegue até **Integrações** e selecione **Rest API Integrations**.</span><span class="sxs-lookup"><span data-stu-id="f9e08-164">From the **Administrator Panel**, navigate to **Integrations** and select **Rest API Integrations**.</span></span>

2. <span data-ttu-id="f9e08-165">Selecione **Criar Integração**.</span><span class="sxs-lookup"><span data-stu-id="f9e08-165">Select **Create Integration**.</span></span>

3. <span data-ttu-id="f9e08-166">No campo **ID do** aplicativo, digite ou copie e colar esta ID:</span><span class="sxs-lookup"><span data-stu-id="f9e08-166">In the **Application ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="f9e08-167">Digite um usuário para essa integração.</span><span class="sxs-lookup"><span data-stu-id="f9e08-167">Type a user for this integration.</span></span>

   <span data-ttu-id="f9e08-168">Esse usuário será aquele com acesso à API inicial do qual o aplicativo está associado.</span><span class="sxs-lookup"><span data-stu-id="f9e08-168">This user will be the one with home API access from which the application is associated.</span></span>

5. <span data-ttu-id="f9e08-169">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="f9e08-169">Select **Submit**.</span></span>

## <a name="add-the-cross-origin-resource-sharing"></a><span data-ttu-id="f9e08-170">Adicionar o compartilhamento de recursos entre origens</span><span class="sxs-lookup"><span data-stu-id="f9e08-170">Add the Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="f9e08-171">No painel **Administrador,** navegue até **Integrações** e selecione \* Compartilhamento de Recursos de *origem cruzada.*</span><span class="sxs-lookup"><span data-stu-id="f9e08-171">From the **Administrator panel**, navigate to **Integrations** and select \**Cross-origin Resource Sharing*.</span></span>

2. <span data-ttu-id="f9e08-172">Selecione **Criar Configuração**.</span><span class="sxs-lookup"><span data-stu-id="f9e08-172">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="f9e08-173">No campo **Origem,** tipo de cópia e colar esta URL:</span><span class="sxs-lookup"><span data-stu-id="f9e08-173">In the **Origin** field, type of copy and paste this URL:</span></span>

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. <span data-ttu-id="f9e08-174">No campo **Headers Permitidos,** digite **Autorização**.</span><span class="sxs-lookup"><span data-stu-id="f9e08-174">In the **Allowed Headers** field, type **Authorization**.</span></span>

5. <span data-ttu-id="f9e08-175">Definir **Disponível como** **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f9e08-175">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="f9e08-176">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="f9e08-176">Select **Submit**.</span></span>

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a><span data-ttu-id="f9e08-177">Configurar e aprovar a integração Microsoft Teams classes</span><span class="sxs-lookup"><span data-stu-id="f9e08-177">Configure and Approve Microsoft Teams classes Integration</span></span>

<span data-ttu-id="f9e08-178">Para integrar com êxito sua instância Learn Ultra do Quadro Microsoft Teams com classes de Microsoft Teams, você precisará garantir que o aplicativo Blackboard Learn Ultra seja aprovado para acesso em seu locatário Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="f9e08-178">To successfully integrate your Blackboard Learn Ultra instance with Microsoft Teams classes, you'll need to make sure the Blackboard Learn Ultra application is approved for access within your Microsoft Azure tenant.</span></span> <span data-ttu-id="f9e08-179">Este é um processo que precisará ser concluído pelo administrador global Microsoft 365 sua instituição.</span><span class="sxs-lookup"><span data-stu-id="f9e08-179">This is a process that will need to be completed by your institution’s Microsoft 365 Global Admin.</span></span>

<span data-ttu-id="f9e08-180">Esse processo pode ser feito antes ou depois de você ter configurado os aplicativos LTI em sua Instância De Aprendizado de Quadro Preto.</span><span class="sxs-lookup"><span data-stu-id="f9e08-180">This process can be done either before or after you have configured the LTI applications in your Blackboard Learn Ultra Instance.</span></span>

### <a name="before-configuring-the-lti-applications"></a><span data-ttu-id="f9e08-181">Antes de configurar os aplicativos LTI</span><span class="sxs-lookup"><span data-stu-id="f9e08-181">Before Configuring the LTI Applications</span></span>

<span data-ttu-id="f9e08-182">Se você optar por aprovar o aplicativo Azure classes ultra Teams Blackboard antes de configurar as integrações LTI, será necessário redirecionar para o Ponto de Extremidade de Consentimento do Administrador da Plataforma de Identidade da **Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="f9e08-182">If you choose to approve the Blackboard Learn Ultra Teams Classes Azure app before configuring the LTI integrations, you'll need to redirect to the **Microsoft Identity Platform Admin Consent Endpoint**.</span></span> <span data-ttu-id="f9e08-183">A URL é mostrada:</span><span class="sxs-lookup"><span data-stu-id="f9e08-183">The URL is shown:</span></span>

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> <span data-ttu-id="f9e08-184">Você substituirá **{Tenant}** pela ID Microsoft Azure locatário específica.</span><span class="sxs-lookup"><span data-stu-id="f9e08-184">You’ll replace **{Tenant}** with your specific institutional Microsoft Azure tenant ID.</span></span>

### <a name="after-configuring-the-lti-applications"></a><span data-ttu-id="f9e08-185">Depois de configurar os aplicativos LTI</span><span class="sxs-lookup"><span data-stu-id="f9e08-185">After Configuring the LTI Applications</span></span>

1. <span data-ttu-id="f9e08-186">No Painel **administrador,** navegue até **Ferramentas e Utilitários** e **selecione Microsoft Teams Administrador de Integração.**</span><span class="sxs-lookup"><span data-stu-id="f9e08-186">On the **Administrator Panel**, navigate to **Tools and Utilities** and select **Microsoft Teams Integration Admin**.</span></span>

2. <span data-ttu-id="f9e08-187">Selecione **Habilitar Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="f9e08-187">Select **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="f9e08-188">Adicione sua **ID do Locatário da Microsoft** ao campo de texto disponível.</span><span class="sxs-lookup"><span data-stu-id="f9e08-188">Add your **Microsoft Tenant ID** into the available text field.</span></span>

4. <span data-ttu-id="f9e08-189">Escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="f9e08-189">Choose one of the following options:</span></span>

   - <span data-ttu-id="f9e08-190">Se o aplicativo tiver pré-consentimento, ele mostrará uma pequena marca de seleção.</span><span class="sxs-lookup"><span data-stu-id="f9e08-190">If the app has pre-consent, it will show a small checkmark.</span></span> <span data-ttu-id="f9e08-191">Se a marca de seleção for exibida, selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="f9e08-191">If the checkmark appears, select **Submit**.</span></span>

   - <span data-ttu-id="f9e08-192">Se o consentimento não tiver sido aprovado, siga as etapas descritas para gerar a URL para consentimento e enviá-la ao administrador global Microsoft 365 para aprovação.</span><span class="sxs-lookup"><span data-stu-id="f9e08-192">If consent hasn’t been approved, follow the steps described to generate the URL for consent and send it to the Microsoft 365 Global Admin for approval.</span></span>

5. <span data-ttu-id="f9e08-193">Depois de confirmar a aprovação, selecione **Repetir para** confirmar e selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="f9e08-193">Once you've confirmation of approval, select **Retry** to confirm, and then select **Submit**.</span></span>
