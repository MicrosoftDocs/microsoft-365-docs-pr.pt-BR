---
title: Modelos de aviso de gerenciamento de risco do insider
description: Saiba mais sobre modelos de aviso de gerenciamento de risco do insider no Microsoft 365
keywords: Microsoft 365, gerenciamento de risco do Insider, gerenciamento de riscos, conformidade
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 0211eefe3c4a946bbaa4ad4c8c66e5df7b37091e
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199481"
---
# <a name="insider-risk-management-notice-templates"></a><span data-ttu-id="7e427-104">Modelos de aviso de gerenciamento de risco do insider</span><span class="sxs-lookup"><span data-stu-id="7e427-104">Insider risk management notice templates</span></span>

<span data-ttu-id="7e427-105">Os modelos de aviso de gerenciamento de risco do insider permitem que você envie mensagens de email aos usuários quando suas atividades geram uma correspondência de política e alerta.</span><span class="sxs-lookup"><span data-stu-id="7e427-105">Insider risk management notice templates allow you to send email messages to users when their activities generate a policy match and alert.</span></span> <span data-ttu-id="7e427-106">Na maioria dos casos, as ações do usuário que geram alertas são o resultado de erros ou atividades inadvertidas sem intenção mal.</span><span class="sxs-lookup"><span data-stu-id="7e427-106">In most cases, user actions that generate alerts are the result of mistakes or inadvertent activities without ill intent.</span></span> <span data-ttu-id="7e427-107">Os avisos servem como lembretes simples para que os usuários tenham mais cuidado para fornecer links para informações para o treinamento atualizado ou para recursos de política corporativa.</span><span class="sxs-lookup"><span data-stu-id="7e427-107">Notices serve as simple reminders to users to be more careful, to provide links to information for refresher training, or to corporate policy resources.</span></span> <span data-ttu-id="7e427-108">Os avisos podem ser uma parte importante do seu programa de treinamento de conformidade interno e podem ajudar a criar uma trilha de auditoria documentada para usuários com atividades recorrentes de riscos.</span><span class="sxs-lookup"><span data-stu-id="7e427-108">Notices can be an important part of your internal compliance training program and can help create a documented audit trail for users with recurring risk activities.</span></span>

<span data-ttu-id="7e427-109">Criar modelos de aviso se quiser enviar aos usuários um aviso de lembrete por email para correspondências de política como parte do processo de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="7e427-109">Create notice templates if you want to send users an email reminder notice for policy matches as part of the issue resolution process.</span></span> <span data-ttu-id="7e427-110">Os avisos só podem ser enviados ao endereço de email do usuário associado ao alerta específico que está sendo revisado.</span><span class="sxs-lookup"><span data-stu-id="7e427-110">Notices can only be sent to the user email address associated with the specific alert being reviewed.</span></span> <span data-ttu-id="7e427-111">Ao selecionar um modelo de aviso a ser aplicado a uma correspondência de política, você pode optar por aceitar os valores de campo definidos no modelo ou substituir os campos, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="7e427-111">When selecting a notice template to apply to a policy match, you can choose to accept the field values defined in the template or overwrite the fields as needed.</span></span>

## <a name="notice-templates-dashboard"></a><span data-ttu-id="7e427-112">Painel de modelos de aviso</span><span class="sxs-lookup"><span data-stu-id="7e427-112">Notice templates dashboard</span></span>

<span data-ttu-id="7e427-113">O **painel de modelos de avisos** exibe uma lista de modelos de aviso configurados e permite que você crie novos modelos de aviso.</span><span class="sxs-lookup"><span data-stu-id="7e427-113">The **Notices templates dashboard** displays a list of configured notice templates and allows you to create new notice templates.</span></span> <span data-ttu-id="7e427-114">Os modelos de aviso são listados em ordem de data inversa com o modelo de aviso mais recente listado primeiro.</span><span class="sxs-lookup"><span data-stu-id="7e427-114">The notice templates are listed in reverse date order with the most recent notice template listed first.</span></span>

![Painel de modelos de aviso de gerenciamento de risco](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a><span data-ttu-id="7e427-116">HTML para avisos</span><span class="sxs-lookup"><span data-stu-id="7e427-116">HTML for notices</span></span>

<span data-ttu-id="7e427-117">Se quiser criar mais de uma mensagem de email baseada em texto simples para notificações, você poderá criar uma mensagem mais detalhada usando HTML no campo corpo da mensagem de um modelo de aviso.</span><span class="sxs-lookup"><span data-stu-id="7e427-117">If you'd like to create more than a simple text-based email message for notifications, you can create a more detailed message by using HTML in the message body field of a notice template.</span></span> <span data-ttu-id="7e427-118">O exemplo a seguir fornece o formato de corpo da mensagem para um modelo de notificação de email baseado em HTML básico:</span><span class="sxs-lookup"><span data-stu-id="7e427-118">The following example provides the message body format for a basic HTML-based email notification template:</span></span>

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
> <span data-ttu-id="7e427-119">A implementação de atributo HTML href nos modelos de aviso de gerenciamento de risco do insider atualmente suporta apenas aspas simples em vez de aspas duplas para referências de URL.</span><span class="sxs-lookup"><span data-stu-id="7e427-119">HTML href attribute implementation in the insider risk management notice templates currently support only single quotation marks instead of double quotation marks for URL references.</span></span>

## <a name="create-a-new-notice-template"></a><span data-ttu-id="7e427-120">Criar um novo modelo de aviso</span><span class="sxs-lookup"><span data-stu-id="7e427-120">Create a new notice template</span></span>

<span data-ttu-id="7e427-121">Para criar um novo modelo de aviso de gerenciamento de risco do Insider, você usará o assistente de aviso na solução de **Gerenciamento de risco do insider** no centro de conformidade da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e427-121">To create a new insider risk management notice template, you'll use the notice wizard in **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="7e427-122">Conclua as etapas a seguir para criar um novo modelo de aviso de gerenciamento de risco do insider:</span><span class="sxs-lookup"><span data-stu-id="7e427-122">Complete the following steps to create a new insider risk management notice template:</span></span>

1. <span data-ttu-id="7e427-123">No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **modelos de aviso** .</span><span class="sxs-lookup"><span data-stu-id="7e427-123">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="7e427-124">Selecione **criar modelo de aviso** para abrir o assistente de aviso.</span><span class="sxs-lookup"><span data-stu-id="7e427-124">Select **Create notice template** to open the notice wizard.</span></span>
3. <span data-ttu-id="7e427-125">Na página **criar um novo modelo de aviso** , preencha os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="7e427-125">On the **Create a new notice template** page, complete the following fields:</span></span>
    - <span data-ttu-id="7e427-126">**Nome do modelo**: Insira um nome amigável para o aviso.</span><span class="sxs-lookup"><span data-stu-id="7e427-126">**Template name**: Enter a friendly name for the notice.</span></span> <span data-ttu-id="7e427-127">Esse nome aparece na lista de avisos no painel de aviso e na lista de seleção de aviso ao enviar avisos de uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="7e427-127">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="7e427-128">**Enviar de**: Insira o endereço de email do remetente para o aviso.</span><span class="sxs-lookup"><span data-stu-id="7e427-128">**Send from**: Enter the sender email address for the notice.</span></span> <span data-ttu-id="7e427-129">Esse endereço aparecerá no campo **de:** em todos os avisos enviados aos usuários, a menos que sejam alterados ao enviar um aviso de um caso.</span><span class="sxs-lookup"><span data-stu-id="7e427-129">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="7e427-130">Campos **CC e Cco** : usuários ou grupos opcionais que serão notificados da correspondência da política, selecionados no Active Directory para a sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="7e427-130">**Cc and Bcc** fields: Optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="7e427-131">**Subject**: as informações que aparecem na linha de assunto da mensagem dão suporte a caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="7e427-131">**Subject**: Information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="7e427-132">**Corpo da mensagem**: as informações que aparecem no corpo da mensagem dão suporte a valores de texto ou HTML.</span><span class="sxs-lookup"><span data-stu-id="7e427-132">**Message body**: Information that appears in the message body, supports text or HTML values.</span></span>
4. <span data-ttu-id="7e427-133">Selecione **criar** para criar e salvar o modelo de aviso ou selecione **Cancelar** para fechar sem salvar o modelo de aviso.</span><span class="sxs-lookup"><span data-stu-id="7e427-133">Select **Create** to create and save the notice template or select **Cancel** to close without saving the notice template.</span></span>

## <a name="update-a-notice-template"></a><span data-ttu-id="7e427-134">Atualizar um modelo de aviso</span><span class="sxs-lookup"><span data-stu-id="7e427-134">Update a notice template</span></span>

<span data-ttu-id="7e427-135">Para atualizar um modelo de aviso de gerenciamento de risco do insider existente, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="7e427-135">To update an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="7e427-136">No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **modelos de aviso** .</span><span class="sxs-lookup"><span data-stu-id="7e427-136">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="7e427-137">No painel de aviso, selecione o modelo de aviso que você deseja gerenciar.</span><span class="sxs-lookup"><span data-stu-id="7e427-137">On the notice dashboard, select the notice template you want to manage.</span></span>
3. <span data-ttu-id="7e427-138">Na página detalhes do aviso, selecione **Editar**</span><span class="sxs-lookup"><span data-stu-id="7e427-138">On the notice details page, select **Edit**</span></span>
4. <span data-ttu-id="7e427-139">Na página **Editar** , você pode editar os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="7e427-139">On the **Edit** page, you can edit the following fields:</span></span>
    - <span data-ttu-id="7e427-140">**Nome do modelo**: Insira um novo nome amigável para o aviso.</span><span class="sxs-lookup"><span data-stu-id="7e427-140">**Template name**: Enter a new friendly name for the notice.</span></span> <span data-ttu-id="7e427-141">Esse nome aparece na lista de avisos no painel de aviso e na lista de seleção de aviso ao enviar avisos de uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="7e427-141">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="7e427-142">**Enviar de**: Atualize o endereço de email do remetente para o aviso.</span><span class="sxs-lookup"><span data-stu-id="7e427-142">**Send from**: Update the sender email address for the notice.</span></span> <span data-ttu-id="7e427-143">Esse endereço aparecerá no campo **de:** em todos os avisos enviados aos usuários, a menos que sejam alterados ao enviar um aviso de um caso.</span><span class="sxs-lookup"><span data-stu-id="7e427-143">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="7e427-144">Campos **CC e Cco** : atualizar usuários ou grupos opcionais a serem notificados sobre a correspondência da política, selecionados no Active Directory para a sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="7e427-144">**Cc and Bcc** fields: Update optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="7e427-145">**Assunto**: atualização de informações que aparece na linha de assunto da mensagem, com suporte para caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="7e427-145">**Subject**: Update information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="7e427-146">**Corpo da mensagem**: atualização de informações que aparece no corpo da mensagem, suporta valores de texto ou HTML.</span><span class="sxs-lookup"><span data-stu-id="7e427-146">**Message body**: Update information that appears in the message body, supports text or HTML values.</span></span>
5. <span data-ttu-id="7e427-147">Selecione **salvar** para atualizar e salvar o aviso ou selecione **Cancelar** para fechar sem salvar o modelo de aviso.</span><span class="sxs-lookup"><span data-stu-id="7e427-147">Select **Save** to update and save the notice or select **Cancel** to close without saving the notice template.</span></span>

## <a name="delete-a-notice-template"></a><span data-ttu-id="7e427-148">Excluir um modelo de aviso</span><span class="sxs-lookup"><span data-stu-id="7e427-148">Delete a notice template</span></span>

<span data-ttu-id="7e427-149">Para excluir um modelo de aviso de gerenciamento de risco do insider existente, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="7e427-149">To delete an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="7e427-150">No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **modelos de aviso** .</span><span class="sxs-lookup"><span data-stu-id="7e427-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="7e427-151">No painel de aviso, selecione o modelo de aviso que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="7e427-151">On the notice dashboard, select the notice template you want to delete.</span></span>
3. <span data-ttu-id="7e427-152">Selecione o ícone **excluir** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="7e427-152">Select the **Delete** icon on the toolbar.</span></span>
4. <span data-ttu-id="7e427-153">Para excluir o modelo de aviso, selecione **Sim** na caixa de diálogo Excluir.</span><span class="sxs-lookup"><span data-stu-id="7e427-153">To delete the notice template, select **Yes** in the delete dialog.</span></span> <span data-ttu-id="7e427-154">Para cancelar a exclusão, selecione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="7e427-154">To cancel the deletion, select **Cancel**.</span></span>
