---
title: Ocultar a interface do Microsoft Defender Antivírus
description: Você pode ocultar o tile de proteção contra vírus e ameaças no aplicativo Segurança do Windows.
keywords: bloqueio da interface do usuário, modo sem cabeça, ocultar aplicativo, ocultar configurações, ocultar interface
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 06ee2f1cb68df0a957818e1fccb45628487c39fd
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274911"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a><span data-ttu-id="13dee-104">Impedir que os usuários vejam ou interajam com a interface do usuário do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="13dee-104">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="13dee-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="13dee-105">**Applies to:**</span></span>

- [<span data-ttu-id="13dee-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="13dee-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="13dee-107">Você pode usar a Política de Grupo para impedir que os usuários nos pontos de extremidade possam ver a interface do Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="13dee-107">You can use Group Policy to prevent users on endpoints from seeing the Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="13dee-108">Você também pode impedi-los de pausar verificações.</span><span class="sxs-lookup"><span data-stu-id="13dee-108">You can also prevent them from pausing scans.</span></span>

## <a name="hide-the-microsoft-defender-antivirus-interface"></a><span data-ttu-id="13dee-109">Ocultar a interface do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="13dee-109">Hide the Microsoft Defender Antivirus interface</span></span>

<span data-ttu-id="13dee-110">No Windows 10, versões 1703, ocultar a interface ocultará as notificações do Microsoft Defender Antivírus e impedirá que o & proteção contra vírus apareça no aplicativo segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="13dee-110">In Windows 10, versions 1703, hiding the interface will hide Microsoft Defender Antivirus notifications and prevent the Virus & threat protection tile from appearing in the Windows Security app.</span></span>

<span data-ttu-id="13dee-111">Com a configuração definida como **Habilitado:**</span><span class="sxs-lookup"><span data-stu-id="13dee-111">With the setting set to **Enabled**:</span></span>

![Captura de tela do Windows Security sem o ícone de escudo e a seção proteção contra vírus e ameaças](images/defender/wdav-headless-mode-1703.png)

<span data-ttu-id="13dee-113">Com a configuração definida como **Desabilitada** ou não configurada:</span><span class="sxs-lookup"><span data-stu-id="13dee-113">With the setting set to **Disabled** or not configured:</span></span>

![Captura de tela do Windows Security mostrando o ícone de escudo e a seção proteção contra vírus e ameaças](images/defender/wdav-headless-mode-off-1703.png)

>[!NOTE]
><span data-ttu-id="13dee-115">Ocultar a interface também impedirá que as notificações do Microsoft Defender Antivírus apareçam no ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="13dee-115">Hiding the interface will also prevent Microsoft Defender Antivirus notifications from appearing on the endpoint.</span></span> <span data-ttu-id="13dee-116">As notificações do Microsoft Defender para Ponto de Extremidade ainda serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="13dee-116">Microsoft Defender for Endpoint notifications will still appear.</span></span> <span data-ttu-id="13dee-117">Você também pode configurar individualmente [as notificações que aparecem nos pontos de extremidade](configure-notifications-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="13dee-117">You can also individually [configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md)</span></span>

<span data-ttu-id="13dee-118">Em versões anteriores do Windows 10, a configuração ocultará a interface Windows Defender cliente.</span><span class="sxs-lookup"><span data-stu-id="13dee-118">In earlier versions of Windows 10, the setting will hide the Windows Defender client interface.</span></span> <span data-ttu-id="13dee-119">Se o usuário tentar abri-lo, ele receberá um aviso informando: "O administrador do sistema tem acesso restrito a esse aplicativo".</span><span class="sxs-lookup"><span data-stu-id="13dee-119">If the user attempts to open it, they will receive a warning that says, "Your system administrator has restricted access to this app."</span></span>

![Mensagem de aviso quando o modo sem cabeça está habilitado no Windows 10, versões anteriores a 1703](images/defender/wdav-headless-mode-1607.png)

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a><span data-ttu-id="13dee-121">Usar a Política de Grupo para ocultar a interface do Microsoft Defender AV dos usuários</span><span class="sxs-lookup"><span data-stu-id="13dee-121">Use Group Policy to hide the Microsoft Defender AV interface from users</span></span>

1. <span data-ttu-id="13dee-122">Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="13dee-122">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="13dee-123">Usando o **Editor de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="13dee-123">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="13dee-124">Clique **em Modelos Administrativos**.</span><span class="sxs-lookup"><span data-stu-id="13dee-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="13dee-125">Expanda a árvore para componentes do Windows > interface do Cliente do **Microsoft Defender Antivírus >.**</span><span class="sxs-lookup"><span data-stu-id="13dee-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="13dee-126">Clique duas vezes na **configuração Habilitar modo de interface** do usuário sem cabeça e de definir a opção **como Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="13dee-126">Double-click the **Enable headless UI mode** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="13dee-127">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="13dee-127">Click **OK**.</span></span> 

<span data-ttu-id="13dee-128">Consulte [Impedir que os usuários modifiquem localmente](configure-local-policy-overrides-microsoft-defender-antivirus.md) as configurações de política para obter mais opções sobre como impedir que os usuários formem modificar a proteção em seus PCs.</span><span class="sxs-lookup"><span data-stu-id="13dee-128">See [Prevent users from locally modifying policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) for more options on preventing users form modifying protection on their PCs.</span></span>

## <a name="prevent-users-from-pausing-a-scan"></a><span data-ttu-id="13dee-129">Impedir que os usuários pausem uma verificação</span><span class="sxs-lookup"><span data-stu-id="13dee-129">Prevent users from pausing a scan</span></span>

<span data-ttu-id="13dee-130">Você pode impedir que os usuários pausem verificações, o que pode ser útil para garantir que as verificações agendadas ou sob demanda não sejam interrompidas pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="13dee-130">You can prevent users from pausing scans, which can be helpful to ensure scheduled or on-demand scans are not interrupted by users.</span></span>

> [!NOTE]
> <span data-ttu-id="13dee-131">Essa configuração não é suportada no Windows 10.</span><span class="sxs-lookup"><span data-stu-id="13dee-131">This setting is not supported on Windows 10.</span></span>

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a><span data-ttu-id="13dee-132">Usar a Política de Grupo para impedir que os usuários pausem uma verificação</span><span class="sxs-lookup"><span data-stu-id="13dee-132">Use Group Policy to prevent users from pausing a scan</span></span>

1. <span data-ttu-id="13dee-133">Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="13dee-133">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="13dee-134">Usando o **Editor de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="13dee-134">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="13dee-135">Clique **em Modelos Administrativos**.</span><span class="sxs-lookup"><span data-stu-id="13dee-135">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="13dee-136">Expanda a árvore para **componentes do Windows**  >  **Microsoft Defender**  >  **Antivírus Scan**.</span><span class="sxs-lookup"><span data-stu-id="13dee-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="13dee-137">Clique duas vezes na **configuração Permitir que os usuários pausem a verificação** e de definir a opção como **Desabilitada**.</span><span class="sxs-lookup"><span data-stu-id="13dee-137">Double-click the **Allow users to pause scan** setting and set the option to **Disabled**.</span></span> <span data-ttu-id="13dee-138">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="13dee-138">Click **OK**.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="13dee-139">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="13dee-139">Related articles</span></span>

- [<span data-ttu-id="13dee-140">Configurar as notificações que aparecem nos pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="13dee-140">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)

- [<span data-ttu-id="13dee-141">Configurar a interação do usuário final com o Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="13dee-141">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [<span data-ttu-id="13dee-142">Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="13dee-142">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)