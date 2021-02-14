---
title: Modelos de aviso de gerenciamento de riscos insider
description: Saiba mais sobre modelos de aviso de gerenciamento de risco interno no Microsoft 365
keywords: Microsoft 365, gerenciamento de riscos insider, gerenciamento de riscos, conformidade
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
# <a name="insider-risk-management-notice-templates"></a><span data-ttu-id="ede63-104">Modelos de aviso de gerenciamento de riscos insider</span><span class="sxs-lookup"><span data-stu-id="ede63-104">Insider risk management notice templates</span></span>

<span data-ttu-id="ede63-105">Os modelos de aviso de gerenciamento de riscos insider permitem que você envie mensagens de email aos usuários quando suas atividades geram uma política de match e alerta.</span><span class="sxs-lookup"><span data-stu-id="ede63-105">Insider risk management notice templates allow you to send email messages to users when their activities generate a policy match and alert.</span></span> <span data-ttu-id="ede63-106">Na maioria dos casos, as ações do usuário que geram alertas são o resultado de erros ou atividades inadvertida sem má intenção.</span><span class="sxs-lookup"><span data-stu-id="ede63-106">In most cases, user actions that generate alerts are the result of mistakes or inadvertent activities without ill intent.</span></span> <span data-ttu-id="ede63-107">Os avisos servem como lembretes simples para que os usuários tenham mais cuidado, forneçam links para informações sobre treinamento atualizado ou recursos de política corporativa.</span><span class="sxs-lookup"><span data-stu-id="ede63-107">Notices serve as simple reminders to users to be more careful, to provide links to information for refresher training, or to corporate policy resources.</span></span> <span data-ttu-id="ede63-108">Os avisos podem ser uma parte importante do seu programa de treinamento de conformidade interna e podem ajudar a criar uma trilha de auditoria documentada para usuários com atividades de risco recorrentes.</span><span class="sxs-lookup"><span data-stu-id="ede63-108">Notices can be an important part of your internal compliance training program and can help create a documented audit trail for users with recurring risk activities.</span></span>

<span data-ttu-id="ede63-109">Crie modelos de aviso se quiser enviar aos usuários um aviso de lembrete por email para as diretivas que fazem parte do processo de resolução de problemas.</span><span class="sxs-lookup"><span data-stu-id="ede63-109">Create notice templates if you want to send users an email reminder notice for policy matches as part of the issue resolution process.</span></span> <span data-ttu-id="ede63-110">Os avisos só podem ser enviados para o endereço de email do usuário associado ao alerta específico que está sendo revisado.</span><span class="sxs-lookup"><span data-stu-id="ede63-110">Notices can only be sent to the user email address associated with the specific alert being reviewed.</span></span> <span data-ttu-id="ede63-111">Ao selecionar um modelo de aviso a ser aplicado a uma política de acordo, você pode optar por aceitar os valores de campo definidos no modelo ou substituir os campos conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ede63-111">When selecting a notice template to apply to a policy match, you can choose to accept the field values defined in the template or overwrite the fields as needed.</span></span>

## <a name="notice-templates-dashboard"></a><span data-ttu-id="ede63-112">Painel de modelos de aviso</span><span class="sxs-lookup"><span data-stu-id="ede63-112">Notice templates dashboard</span></span>

<span data-ttu-id="ede63-113">O **painel de modelos de Avisos** exibe uma lista de modelos de aviso configurados e permite que você crie novos modelos de aviso.</span><span class="sxs-lookup"><span data-stu-id="ede63-113">The **Notices templates dashboard** displays a list of configured notice templates and allows you to create new notice templates.</span></span> <span data-ttu-id="ede63-114">Os modelos de aviso são listados na ordem de data inversa com o modelo de aviso mais recente listado primeiro.</span><span class="sxs-lookup"><span data-stu-id="ede63-114">The notice templates are listed in reverse date order with the most recent notice template listed first.</span></span>

![Painel de modelo de aviso de gerenciamento de riscos interno](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a><span data-ttu-id="ede63-116">HTML para avisos</span><span class="sxs-lookup"><span data-stu-id="ede63-116">HTML for notices</span></span>

<span data-ttu-id="ede63-117">Se você quiser criar mais do que uma mensagem de email simples baseada em texto para notificações, crie uma mensagem mais detalhada usando HTML no campo do corpo da mensagem de um modelo de aviso.</span><span class="sxs-lookup"><span data-stu-id="ede63-117">If you'd like to create more than a simple text-based email message for notifications, you can create a more detailed message by using HTML in the message body field of a notice template.</span></span> <span data-ttu-id="ede63-118">O exemplo a seguir fornece o formato do corpo da mensagem para um modelo básico de notificação de email baseado em HTML:</span><span class="sxs-lookup"><span data-stu-id="ede63-118">The following example provides the message body format for a basic HTML-based email notification template:</span></span>

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
> <span data-ttu-id="ede63-119">A implementação de atributos html href nos modelos de aviso de gerenciamento de risco interno atualmente suporta apenas aspas simples em vez de aspas duplas para referências de URL.</span><span class="sxs-lookup"><span data-stu-id="ede63-119">HTML href attribute implementation in the insider risk management notice templates currently support only single quotation marks instead of double quotation marks for URL references.</span></span>

## <a name="create-a-new-notice-template"></a><span data-ttu-id="ede63-120">Criar um novo modelo de aviso</span><span class="sxs-lookup"><span data-stu-id="ede63-120">Create a new notice template</span></span>

<span data-ttu-id="ede63-121">Para criar um novo modelo de aviso de gerenciamento de riscos, você usará o assistente de aviso na solução de gerenciamento de riscos do **Insider** no centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ede63-121">To create a new insider risk management notice template, you'll use the notice wizard in **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="ede63-122">Conclua as seguintes etapas para criar um novo modelo de aviso de gerenciamento de risco interno:</span><span class="sxs-lookup"><span data-stu-id="ede63-122">Complete the following steps to create a new insider risk management notice template:</span></span>

1. <span data-ttu-id="ede63-123">No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do **Insider** e selecione a guia Modelos **de** Aviso.</span><span class="sxs-lookup"><span data-stu-id="ede63-123">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="ede63-124">Selecione **Criar modelo de aviso** para abrir o assistente de aviso.</span><span class="sxs-lookup"><span data-stu-id="ede63-124">Select **Create notice template** to open the notice wizard.</span></span>
3. <span data-ttu-id="ede63-125">Na página **Criar um novo modelo de aviso,** preencha os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="ede63-125">On the **Create a new notice template** page, complete the following fields:</span></span>
    - <span data-ttu-id="ede63-126">**Nome do** modelo: insira um nome amigável para o aviso.</span><span class="sxs-lookup"><span data-stu-id="ede63-126">**Template name**: Enter a friendly name for the notice.</span></span> <span data-ttu-id="ede63-127">Esse nome aparece na lista de avisos no painel de aviso e na lista de seleção de avisos ao enviar avisos de uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="ede63-127">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="ede63-128">**Enviar de:** insira o endereço de email do remetente para o aviso.</span><span class="sxs-lookup"><span data-stu-id="ede63-128">**Send from**: Enter the sender email address for the notice.</span></span> <span data-ttu-id="ede63-129">Esse endereço aparecerá no campo **De:** em todos os avisos enviados aos usuários, a menos que seja alterado ao enviar um aviso de uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="ede63-129">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="ede63-130">**Campos Cc e Cc:** Usuários ou grupos opcionais a serem notificados sobre a política de match, selecionados no Active Directory para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="ede63-130">**Cc and Bcc** fields: Optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="ede63-131">**Assunto**: as informações que aparecem na linha de assunto da mensagem têm suporte para caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="ede63-131">**Subject**: Information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="ede63-132">**Corpo da** mensagem: informações que aparecem no corpo da mensagem, suportam valores de texto ou HTML.</span><span class="sxs-lookup"><span data-stu-id="ede63-132">**Message body**: Information that appears in the message body, supports text or HTML values.</span></span>
4. <span data-ttu-id="ede63-133">Selecione **Criar para** criar e salvar o modelo de aviso ou **cancelar** para fechar sem salvar o modelo de aviso.</span><span class="sxs-lookup"><span data-stu-id="ede63-133">Select **Create** to create and save the notice template or select **Cancel** to close without saving the notice template.</span></span>

## <a name="update-a-notice-template"></a><span data-ttu-id="ede63-134">Atualizar um modelo de aviso</span><span class="sxs-lookup"><span data-stu-id="ede63-134">Update a notice template</span></span>

<span data-ttu-id="ede63-135">Para atualizar um modelo de aviso de gerenciamento de riscos insider existente, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="ede63-135">To update an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="ede63-136">No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do **Insider** e selecione a guia Modelos **de** Aviso.</span><span class="sxs-lookup"><span data-stu-id="ede63-136">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="ede63-137">No painel de aviso, selecione o modelo de aviso que você deseja gerenciar.</span><span class="sxs-lookup"><span data-stu-id="ede63-137">On the notice dashboard, select the notice template you want to manage.</span></span>
3. <span data-ttu-id="ede63-138">Na página de detalhes do aviso, selecione **Editar**</span><span class="sxs-lookup"><span data-stu-id="ede63-138">On the notice details page, select **Edit**</span></span>
4. <span data-ttu-id="ede63-139">Na página **Editar,** você pode editar os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="ede63-139">On the **Edit** page, you can edit the following fields:</span></span>
    - <span data-ttu-id="ede63-140">**Nome do** modelo: insira um novo nome amigável para o aviso.</span><span class="sxs-lookup"><span data-stu-id="ede63-140">**Template name**: Enter a new friendly name for the notice.</span></span> <span data-ttu-id="ede63-141">Esse nome aparece na lista de avisos no painel de aviso e na lista de seleção de avisos ao enviar avisos de uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="ede63-141">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="ede63-142">**Enviar de:** atualizar o endereço de email do remetente para o aviso.</span><span class="sxs-lookup"><span data-stu-id="ede63-142">**Send from**: Update the sender email address for the notice.</span></span> <span data-ttu-id="ede63-143">Esse endereço aparecerá no campo **De:** em todos os avisos enviados aos usuários, a menos que seja alterado ao enviar um aviso de uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="ede63-143">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="ede63-144">**Campos Cc e Cc:** Atualizar usuários ou grupos opcionais para serem notificados sobre a política de match, selecionados no Active Directory para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="ede63-144">**Cc and Bcc** fields: Update optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="ede63-145">**Assunto:** atualize as informações que aparecem na linha de assunto da mensagem, com suporte para caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="ede63-145">**Subject**: Update information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="ede63-146">**Corpo da** mensagem: atualizar as informações que aparecem no corpo da mensagem, dá suporte a valores de texto ou HTML.</span><span class="sxs-lookup"><span data-stu-id="ede63-146">**Message body**: Update information that appears in the message body, supports text or HTML values.</span></span>
5. <span data-ttu-id="ede63-147">Selecione **Salvar** para atualizar e salvar o aviso ou **selecione Cancelar** para fechar sem salvar o modelo de aviso.</span><span class="sxs-lookup"><span data-stu-id="ede63-147">Select **Save** to update and save the notice or select **Cancel** to close without saving the notice template.</span></span>

## <a name="delete-a-notice-template"></a><span data-ttu-id="ede63-148">Excluir um modelo de aviso</span><span class="sxs-lookup"><span data-stu-id="ede63-148">Delete a notice template</span></span>

<span data-ttu-id="ede63-149">Para excluir um modelo de aviso de gerenciamento de risco interno existente, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="ede63-149">To delete an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="ede63-150">No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do **Insider** e selecione a guia Modelos **de** Aviso.</span><span class="sxs-lookup"><span data-stu-id="ede63-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="ede63-151">No painel de aviso, selecione o modelo de aviso que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="ede63-151">On the notice dashboard, select the notice template you want to delete.</span></span>
3. <span data-ttu-id="ede63-152">Selecione o **ícone Excluir** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="ede63-152">Select the **Delete** icon on the toolbar.</span></span>
4. <span data-ttu-id="ede63-153">Para excluir o modelo de aviso, selecione **Sim** na caixa de diálogo excluir.</span><span class="sxs-lookup"><span data-stu-id="ede63-153">To delete the notice template, select **Yes** in the delete dialog.</span></span> <span data-ttu-id="ede63-154">Para cancelar a exclusão, selecione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="ede63-154">To cancel the deletion, select **Cancel**.</span></span>
