---
title: Criar e gerenciar funções para controle de acesso baseado em função
description: Criar funções e definir as permissões atribuídas à função como parte da implementação do controle de acesso baseado em função no Centro de Segurança do Microsoft Defender
keywords: funções de usuário, funções, rbac de acesso
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
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053832"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a><span data-ttu-id="ace67-104">Criar e gerenciar funções para controle de acesso baseado em função</span><span class="sxs-lookup"><span data-stu-id="ace67-104">Create and manage roles for role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ace67-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ace67-105">**Applies to:**</span></span>
- [<span data-ttu-id="ace67-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ace67-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="ace67-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ace67-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ace67-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="ace67-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ace67-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="ace67-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a><span data-ttu-id="ace67-110">Criar funções e atribuir a função a um grupo do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ace67-110">Create roles and assign the role to an Azure Active Directory group</span></span>

<span data-ttu-id="ace67-111">As etapas a seguir o orientam sobre como criar funções no Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="ace67-111">The following steps guide you on how to create roles in Microsoft Defender Security Center.</span></span> <span data-ttu-id="ace67-112">Ele supõe que você já tenha criado grupos de usuários do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ace67-112">It assumes that you have already created Azure Active Directory user groups.</span></span>

1. <span data-ttu-id="ace67-113">Faça logoff no [Centro de Segurança](https://securitycenter.windows.com/) do Microsoft Defender usando conta com um administrador de segurança ou função de administrador global atribuída.</span><span class="sxs-lookup"><span data-stu-id="ace67-113">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with a Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="ace67-114">No painel de navegação, selecione **Configurações > Funções**.</span><span class="sxs-lookup"><span data-stu-id="ace67-114">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="ace67-115">Selecione **Adicionar item**.</span><span class="sxs-lookup"><span data-stu-id="ace67-115">Select **Add item**.</span></span>

4. <span data-ttu-id="ace67-116">Insira o nome da função, a descrição e as permissões que você gostaria de atribuir à função.</span><span class="sxs-lookup"><span data-stu-id="ace67-116">Enter the role name, description, and permissions you'd like to assign to the role.</span></span>

5. <span data-ttu-id="ace67-117">Selecione **Próximo** para atribuir a função a um grupo de Segurança do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ace67-117">Select **Next** to assign the role to an Azure AD Security group.</span></span>

6. <span data-ttu-id="ace67-118">Use o filtro para selecionar o grupo do Azure AD ao que você gostaria de adicionar a essa função.</span><span class="sxs-lookup"><span data-stu-id="ace67-118">Use the filter to select the Azure AD group that you'd like to add to this role to.</span></span>

7. <span data-ttu-id="ace67-119">**Salvar e fechar**.</span><span class="sxs-lookup"><span data-stu-id="ace67-119">**Save and close**.</span></span>

8. <span data-ttu-id="ace67-120">Aplique as configurações.</span><span class="sxs-lookup"><span data-stu-id="ace67-120">Apply the configuration settings.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ace67-121">Depois de criar funções, você precisará criar um grupo de dispositivos e fornecer acesso ao grupo de dispositivos atribuindo-o a uma função que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="ace67-121">After creating roles, you'll need to create a device group and provide access to the device group by assigning it to a role that you just created.</span></span>

### <a name="permission-options"></a><span data-ttu-id="ace67-122">Opções de permissão</span><span class="sxs-lookup"><span data-stu-id="ace67-122">Permission options</span></span>

- <span data-ttu-id="ace67-123">**Exibir dados**</span><span class="sxs-lookup"><span data-stu-id="ace67-123">**View data**</span></span>
    - <span data-ttu-id="ace67-124">**Operações de segurança** - Exibir todos os dados de operações de segurança no portal</span><span class="sxs-lookup"><span data-stu-id="ace67-124">**Security operations** - View all security operations data in the portal</span></span>
    - <span data-ttu-id="ace67-125">**Gerenciamento de ameaças e vulnerabilidades** - Exibir dados de gerenciamento de ameaças e vulnerabilidades no portal</span><span class="sxs-lookup"><span data-stu-id="ace67-125">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

- <span data-ttu-id="ace67-126">**Ações de correção ativas**</span><span class="sxs-lookup"><span data-stu-id="ace67-126">**Active remediation actions**</span></span>
    - <span data-ttu-id="ace67-127">**Operações de segurança** - Realizar ações de resposta, aprovar ou descartar ações pendentes de correção, gerenciar listas permitidas/bloqueadas para automação e indicadores</span><span class="sxs-lookup"><span data-stu-id="ace67-127">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
    - <span data-ttu-id="ace67-128">**Gerenciamento de ameaças e vulnerabilidades - Tratamento de exceções** - Criar novas exceções e gerenciar exceções ativas</span><span class="sxs-lookup"><span data-stu-id="ace67-128">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
    - <span data-ttu-id="ace67-129">**Gerenciamento de ameaças e vulnerabilidades - Tratamento** de correção - Enviar novas solicitações de correção, criar tíquetes e gerenciar atividades de correção existentes</span><span class="sxs-lookup"><span data-stu-id="ace67-129">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

- <span data-ttu-id="ace67-130">**Investigação de alertas** - Gerenciar alertas, iniciar investigações automatizadas, executar verificações, coletar pacotes de investigação, gerenciar marcas de dispositivo e baixar somente arquivos executáveis portáteis (PE)</span><span class="sxs-lookup"><span data-stu-id="ace67-130">**Alerts investigation** - Manage alerts, initiate automated investigations, run scans, collect investigation packages, manage device tags, and download only portable executable (PE) files</span></span> 

- <span data-ttu-id="ace67-131">**Gerenciar configurações** do sistema de portal - Configurar configurações de armazenamento, siem e configurações da API intel de ameaças (aplica-se globalmente), configurações avançadas, carregamentos automatizados de arquivos, funções e grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="ace67-131">**Manage portal system settings** - Configure storage settings, SIEM and threat intel API settings (applies globally), advanced settings, automated file uploads, roles and device groups</span></span>

    > [!NOTE]
    > <span data-ttu-id="ace67-132">Essa configuração só está disponível na função administrador do Microsoft Defender for Endpoint (padrão).</span><span class="sxs-lookup"><span data-stu-id="ace67-132">This setting is only available in the Microsoft Defender for Endpoint administrator (default) role.</span></span>

- <span data-ttu-id="ace67-133">**Gerenciar configurações de segurança** no Centro de Segurança - Configurar configurações de supressão de alerta, gerenciar exclusões de pastas para automação, dispositivos de integração e offboard e gerenciar notificações de email, gerenciar laboratório de avaliação</span><span class="sxs-lookup"><span data-stu-id="ace67-133">**Manage security settings in Security Center** - Configure alert suppression settings, manage folder exclusions for automation, onboard and offboard devices, and manage email notifications, manage evaluation lab</span></span>

- <span data-ttu-id="ace67-134">**Recursos de resposta ao vivo**</span><span class="sxs-lookup"><span data-stu-id="ace67-134">**Live response capabilities**</span></span>
    - <span data-ttu-id="ace67-135">**Comandos** básicos:</span><span class="sxs-lookup"><span data-stu-id="ace67-135">**Basic** commands:</span></span>
        - <span data-ttu-id="ace67-136">Iniciar uma sessão de resposta ao vivo</span><span class="sxs-lookup"><span data-stu-id="ace67-136">Start a live response session</span></span>
        - <span data-ttu-id="ace67-137">Executar comandos de resposta somente leitura ao vivo em dispositivo remoto (excluindo a cópia e a execução de arquivos</span><span class="sxs-lookup"><span data-stu-id="ace67-137">Perform read only live response commands on remote device (excluding file copy and execution</span></span>
    - <span data-ttu-id="ace67-138">**Comandos** avançados:</span><span class="sxs-lookup"><span data-stu-id="ace67-138">**Advanced** commands:</span></span>
        - <span data-ttu-id="ace67-139">Baixar um arquivo do dispositivo remoto por meio de resposta ao vivo</span><span class="sxs-lookup"><span data-stu-id="ace67-139">Download a file from the remote device via live response</span></span>
        - <span data-ttu-id="ace67-140">Baixar arquivos PE e não-PE da página de arquivo</span><span class="sxs-lookup"><span data-stu-id="ace67-140">Download PE and non-PE files from the file page</span></span>
        - <span data-ttu-id="ace67-141">Carregar um arquivo no dispositivo remoto</span><span class="sxs-lookup"><span data-stu-id="ace67-141">Upload a file to the remote device</span></span>
        - <span data-ttu-id="ace67-142">Exibir um script da biblioteca de arquivos</span><span class="sxs-lookup"><span data-stu-id="ace67-142">View a script from the files library</span></span>
        - <span data-ttu-id="ace67-143">Executar um script no dispositivo remoto da biblioteca de arquivos</span><span class="sxs-lookup"><span data-stu-id="ace67-143">Execute a script on the remote device from the files library</span></span>

<span data-ttu-id="ace67-144">Para obter mais informações sobre os comandos disponíveis, consulte [Investigate devices using Live response](live-response.md).</span><span class="sxs-lookup"><span data-stu-id="ace67-144">For more information on the available commands, see [Investigate devices using Live response](live-response.md).</span></span>
  
## <a name="edit-roles"></a><span data-ttu-id="ace67-145">Editar funções</span><span class="sxs-lookup"><span data-stu-id="ace67-145">Edit roles</span></span>

1. <span data-ttu-id="ace67-146">Faça logoff no [Centro de Segurança](https://securitycenter.windows.com/) do Microsoft Defender usando conta com o administrador de segurança ou a função de administrador global atribuída.</span><span class="sxs-lookup"><span data-stu-id="ace67-146">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="ace67-147">No painel de navegação, selecione **Configurações > Funções**.</span><span class="sxs-lookup"><span data-stu-id="ace67-147">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="ace67-148">Selecione a função que você gostaria de editar.</span><span class="sxs-lookup"><span data-stu-id="ace67-148">Select the role you'd like to edit.</span></span>

4. <span data-ttu-id="ace67-149">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ace67-149">Click **Edit**.</span></span>

5. <span data-ttu-id="ace67-150">Modifique os detalhes ou os grupos atribuídos à função.</span><span class="sxs-lookup"><span data-stu-id="ace67-150">Modify the details or the groups that are assigned to the role.</span></span> 

6. <span data-ttu-id="ace67-151">Clique **em Salvar e fechar**.</span><span class="sxs-lookup"><span data-stu-id="ace67-151">Click **Save and close**.</span></span>

## <a name="delete-roles"></a><span data-ttu-id="ace67-152">Excluir funções</span><span class="sxs-lookup"><span data-stu-id="ace67-152">Delete roles</span></span>

1. <span data-ttu-id="ace67-153">Faça logoff no [Centro de Segurança](https://securitycenter.windows.com/) do Microsoft Defender usando conta com o administrador de segurança ou a função de administrador global atribuída.</span><span class="sxs-lookup"><span data-stu-id="ace67-153">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="ace67-154">No painel de navegação, selecione **Configurações > Funções**.</span><span class="sxs-lookup"><span data-stu-id="ace67-154">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="ace67-155">Selecione a função que você gostaria de excluir.</span><span class="sxs-lookup"><span data-stu-id="ace67-155">Select the role you'd like to delete.</span></span>

4. <span data-ttu-id="ace67-156">Clique no botão drop-down e selecione **Excluir função**.</span><span class="sxs-lookup"><span data-stu-id="ace67-156">Click the drop-down button and select **Delete role**.</span></span>

## <a name="related-topic"></a><span data-ttu-id="ace67-157">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ace67-157">Related topic</span></span>

- [<span data-ttu-id="ace67-158">Permissões básicas do usuário para acessar o portal</span><span class="sxs-lookup"><span data-stu-id="ace67-158">User basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="ace67-159">Criar e gerenciar grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="ace67-159">Create and manage device groups</span></span>](machine-groups.md)
