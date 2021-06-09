---
title: Modelos de aviso de gerenciamento de risco interno
description: Saiba mais sobre modelos de avisos de gerenciamento de riscos no Microsoft 365
keywords: Microsoft 365, gerenciamento de risco interno, gerenciamento de risco, conformidade
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 3a74c62e84c1cb9e4c749a364c0e5b6da25a8af9
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416475"
---
# <a name="insider-risk-management-notice-templates"></a><span data-ttu-id="4c089-104">Modelos de aviso de gerenciamento de risco interno</span><span class="sxs-lookup"><span data-stu-id="4c089-104">Insider risk management notice templates</span></span>

<span data-ttu-id="4c089-105">Os modelos de aviso de gerenciamento de riscos insider permitem que você envie mensagens de email para os usuários quando suas atividades geram uma combinação de política e alerta.</span><span class="sxs-lookup"><span data-stu-id="4c089-105">Insider risk management notice templates allow you to send email messages to users when their activities generate a policy match and alert.</span></span> <span data-ttu-id="4c089-106">Na maioria dos casos, as ações do usuário que geram alertas são resultado de erros ou atividades inadvertida sem intenção irreversível.</span><span class="sxs-lookup"><span data-stu-id="4c089-106">In most cases, user actions that generate alerts are the result of mistakes or inadvertent activities without ill intent.</span></span> <span data-ttu-id="4c089-107">Os avisos servem como lembretes simples para os usuários serem mais cuidadosos, para fornecer links para informações para treinamento de atualização ou para recursos de política corporativa.</span><span class="sxs-lookup"><span data-stu-id="4c089-107">Notices serve as simple reminders to users to be more careful, to provide links to information for refresher training, or to corporate policy resources.</span></span> <span data-ttu-id="4c089-108">Os avisos podem ser uma parte importante do programa de treinamento de conformidade interna e podem ajudar a criar uma trilha de auditoria documentada para usuários com atividades de risco recorrentes.</span><span class="sxs-lookup"><span data-stu-id="4c089-108">Notices can be an important part of your internal compliance training program and can help create a documented audit trail for users with recurring risk activities.</span></span>

<span data-ttu-id="4c089-109">Crie modelos de aviso se quiser enviar aos usuários um aviso de lembrete de email para as combinações de política como parte do processo de resolução de problemas.</span><span class="sxs-lookup"><span data-stu-id="4c089-109">Create notice templates if you want to send users an email reminder notice for policy matches as part of the issue resolution process.</span></span> <span data-ttu-id="4c089-110">Os avisos só podem ser enviados para o endereço de email do usuário associado ao alerta específico que está sendo revisado.</span><span class="sxs-lookup"><span data-stu-id="4c089-110">Notices can only be sent to the user email address associated with the specific alert being reviewed.</span></span> <span data-ttu-id="4c089-111">Ao selecionar um modelo de aviso para aplicar a uma combinação de política, você pode optar por aceitar os valores de campo definidos no modelo ou substituir os campos conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="4c089-111">When selecting a notice template to apply to a policy match, you can choose to accept the field values defined in the template or overwrite the fields as needed.</span></span>

## <a name="notice-templates-dashboard"></a><span data-ttu-id="4c089-112">Painel de modelos de aviso</span><span class="sxs-lookup"><span data-stu-id="4c089-112">Notice templates dashboard</span></span>

<span data-ttu-id="4c089-113">O **de modelos de avisos** exibe uma lista de modelos de aviso configurados e permite que você crie novos modelos de aviso.</span><span class="sxs-lookup"><span data-stu-id="4c089-113">The **Notices templates dashboard** displays a list of configured notice templates and allows you to create new notice templates.</span></span> <span data-ttu-id="4c089-114">Os modelos de aviso são listados na ordem de data inversa com o modelo de aviso mais recente listado primeiro.</span><span class="sxs-lookup"><span data-stu-id="4c089-114">The notice templates are listed in reverse date order with the most recent notice template listed first.</span></span>

![Painel de modelo de aviso de gerenciamento de riscos do Insider](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a><span data-ttu-id="4c089-116">HTML para avisos</span><span class="sxs-lookup"><span data-stu-id="4c089-116">HTML for notices</span></span>

<span data-ttu-id="4c089-117">Se você quiser criar mais do que uma mensagem de email simples baseada em texto para notificações, você pode criar uma mensagem mais detalhada usando HTML no campo corpo da mensagem de um modelo de aviso.</span><span class="sxs-lookup"><span data-stu-id="4c089-117">If you'd like to create more than a simple text-based email message for notifications, you can create a more detailed message by using HTML in the message body field of a notice template.</span></span> <span data-ttu-id="4c089-118">O exemplo a seguir fornece o formato do corpo da mensagem para um modelo básico de notificação de email baseado em HTML:</span><span class="sxs-lookup"><span data-stu-id="4c089-118">The following example provides the message body format for a basic HTML-based email notification template:</span></span>

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso User Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso User <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso User Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> <span data-ttu-id="4c089-119">A implementação do atributo href HTML nos modelos de aviso de gerenciamento de riscos insider atualmente suporta apenas aspas simples, em vez de aspas duplas para referências de URL.</span><span class="sxs-lookup"><span data-stu-id="4c089-119">HTML href attribute implementation in the insider risk management notice templates currently support only single quotation marks instead of double quotation marks for URL references.</span></span>

## <a name="create-a-new-notice-template"></a><span data-ttu-id="4c089-120">Criar um novo modelo de aviso</span><span class="sxs-lookup"><span data-stu-id="4c089-120">Create a new notice template</span></span>

<span data-ttu-id="4c089-121">Para criar um novo modelo de aviso de gerenciamento de riscos do **insider,** você usará o assistente de aviso na solução de gerenciamento de riscos do Insider no Microsoft 365 de conformidade.</span><span class="sxs-lookup"><span data-stu-id="4c089-121">To create a new insider risk management notice template, you'll use the notice wizard in **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="4c089-122">Conclua as etapas a seguir para criar um novo modelo de aviso de gerenciamento de risco interno:</span><span class="sxs-lookup"><span data-stu-id="4c089-122">Complete the following steps to create a new insider risk management notice template:</span></span>

1. <span data-ttu-id="4c089-123">No centro [Microsoft 365 de conformidade,](https://compliance.microsoft.com)vá para Gerenciamento de riscos **do Insider** e selecione a **guia Modelos de** aviso.</span><span class="sxs-lookup"><span data-stu-id="4c089-123">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="4c089-124">Selecione **Criar modelo de aviso** para abrir o assistente de aviso.</span><span class="sxs-lookup"><span data-stu-id="4c089-124">Select **Create notice template** to open the notice wizard.</span></span>
3. <span data-ttu-id="4c089-125">Na página **Criar um novo modelo de aviso,** conclua os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="4c089-125">On the **Create a new notice template** page, complete the following fields:</span></span>
    - <span data-ttu-id="4c089-126">**Nome do** modelo : Insira um nome amigável para o aviso.</span><span class="sxs-lookup"><span data-stu-id="4c089-126">**Template name**: Enter a friendly name for the notice.</span></span> <span data-ttu-id="4c089-127">Esse nome aparece na lista de avisos no painel de avisos e na lista de seleção de avisos ao enviar avisos de uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="4c089-127">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="4c089-128">**Enviar de**: Insira o endereço de email do remetente para o aviso.</span><span class="sxs-lookup"><span data-stu-id="4c089-128">**Send from**: Enter the sender email address for the notice.</span></span> <span data-ttu-id="4c089-129">Esse endereço aparecerá no campo **De:** em todos os avisos enviados aos usuários, a menos que seja alterado ao enviar um aviso de uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="4c089-129">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="4c089-130">**Campos Cc e Cc:** Usuários opcionais ou grupos a serem notificados da combinação de política, selecionados no Active Directory para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="4c089-130">**Cc and Bcc** fields: Optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="4c089-131">**Assunto**: Informações que aparecem na linha de assunto da mensagem, suporta caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="4c089-131">**Subject**: Information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="4c089-132">**Corpo da** mensagem : Informações que aparecem no corpo da mensagem, suportam valores de texto ou HTML.</span><span class="sxs-lookup"><span data-stu-id="4c089-132">**Message body**: Information that appears in the message body, supports text or HTML values.</span></span>
4. <span data-ttu-id="4c089-133">Selecione **Criar** para criar e salvar o modelo de aviso ou selecione **Cancelar** para fechar sem salvar o modelo de aviso.</span><span class="sxs-lookup"><span data-stu-id="4c089-133">Select **Create** to create and save the notice template or select **Cancel** to close without saving the notice template.</span></span>

## <a name="update-a-notice-template"></a><span data-ttu-id="4c089-134">Atualizar um modelo de aviso</span><span class="sxs-lookup"><span data-stu-id="4c089-134">Update a notice template</span></span>

<span data-ttu-id="4c089-135">Para atualizar um modelo de aviso de gerenciamento de riscos insider existente, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4c089-135">To update an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="4c089-136">No centro [Microsoft 365 de conformidade,](https://compliance.microsoft.com)vá para Gerenciamento de riscos **do Insider** e selecione a **guia Modelos de** aviso.</span><span class="sxs-lookup"><span data-stu-id="4c089-136">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="4c089-137">No painel de avisos, selecione o modelo de aviso que você deseja gerenciar.</span><span class="sxs-lookup"><span data-stu-id="4c089-137">On the notice dashboard, select the notice template you want to manage.</span></span>
3. <span data-ttu-id="4c089-138">Na página detalhes do aviso, selecione **Editar**</span><span class="sxs-lookup"><span data-stu-id="4c089-138">On the notice details page, select **Edit**</span></span>
4. <span data-ttu-id="4c089-139">Na página **Editar,** você pode editar os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="4c089-139">On the **Edit** page, you can edit the following fields:</span></span>
    - <span data-ttu-id="4c089-140">**Nome do** modelo : Insira um novo nome amigável para o aviso.</span><span class="sxs-lookup"><span data-stu-id="4c089-140">**Template name**: Enter a new friendly name for the notice.</span></span> <span data-ttu-id="4c089-141">Esse nome aparece na lista de avisos no painel de avisos e na lista de seleção de avisos ao enviar avisos de uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="4c089-141">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="4c089-142">**Enviar de**: Atualizar o endereço de email do remetente para o aviso.</span><span class="sxs-lookup"><span data-stu-id="4c089-142">**Send from**: Update the sender email address for the notice.</span></span> <span data-ttu-id="4c089-143">Esse endereço aparecerá no campo **De:** em todos os avisos enviados aos usuários, a menos que seja alterado ao enviar um aviso de uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="4c089-143">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="4c089-144">**Campos Cc e Cc:** Atualize usuários opcionais ou grupos a serem notificados da combinação de política, selecionados no Active Directory para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="4c089-144">**Cc and Bcc** fields: Update optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="4c089-145">**Assunto**: Atualize as informações que aparecem na linha de assunto da mensagem, suporta caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="4c089-145">**Subject**: Update information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="4c089-146">**Corpo da** mensagem : Atualize as informações que aparecem no corpo da mensagem, suporta valores de texto ou HTML.</span><span class="sxs-lookup"><span data-stu-id="4c089-146">**Message body**: Update information that appears in the message body, supports text or HTML values.</span></span>
5. <span data-ttu-id="4c089-147">Selecione **Salvar** para atualizar e salvar o aviso ou selecione **Cancelar** para fechar sem salvar o modelo de aviso.</span><span class="sxs-lookup"><span data-stu-id="4c089-147">Select **Save** to update and save the notice or select **Cancel** to close without saving the notice template.</span></span>

## <a name="delete-a-notice-template"></a><span data-ttu-id="4c089-148">Excluir um modelo de aviso</span><span class="sxs-lookup"><span data-stu-id="4c089-148">Delete a notice template</span></span>

<span data-ttu-id="4c089-149">Para excluir um modelo de aviso de gerenciamento de risco interno existente, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4c089-149">To delete an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="4c089-150">No centro [Microsoft 365 de conformidade,](https://compliance.microsoft.com)vá para Gerenciamento de riscos **do Insider** e selecione a **guia Modelos de** aviso.</span><span class="sxs-lookup"><span data-stu-id="4c089-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="4c089-151">No painel de avisos, selecione o modelo de aviso que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="4c089-151">On the notice dashboard, select the notice template you want to delete.</span></span>
3. <span data-ttu-id="4c089-152">Selecione o **ícone Excluir** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="4c089-152">Select the **Delete** icon on the toolbar.</span></span>
4. <span data-ttu-id="4c089-153">Para excluir o modelo de aviso, selecione **Sim** na caixa de diálogo excluir.</span><span class="sxs-lookup"><span data-stu-id="4c089-153">To delete the notice template, select **Yes** in the delete dialog.</span></span> <span data-ttu-id="4c089-154">Para cancelar a exclusão, selecione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="4c089-154">To cancel the deletion, select **Cancel**.</span></span>
