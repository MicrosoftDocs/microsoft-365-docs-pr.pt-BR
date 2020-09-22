---
title: Proteção contra ameaças
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Os administradores podem saber mais sobre a proteção contra ameaças no Microsoft 365 e configurar como usá-la para sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ad74e9bdcd7b937873108d2ba049c16db8c235b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202574"
---
# <a name="protect-against-threats"></a><span data-ttu-id="2b3f6-103">Proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="2b3f6-103">Protect against threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2b3f6-104">Aqui está um guia de início rápido que divide a configuração da proteção avançada contra ameaças em partes.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-104">Here's a quick-start guide that breaks the configuration of Advanced Threat Protection into chunks.</span></span> <span data-ttu-id="2b3f6-105">Se você é novo em recursos de proteção contra ameaças no Office 365, não tem certeza de onde começar, ou se você aprende melhor *fazendo*isso, use este guia como uma lista de verificação e um ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-105">If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b3f6-106">**As configurações iniciais recomendadas são incluídas para cada tipo de política; no entanto, muitas opções estão disponíveis e você pode ajustar suas configurações para atender às necessidades específicas da sua organização**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-106">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="2b3f6-107">Aguarde aproximadamente 30 minutos para que as políticas ou as alterações funcionem da mesma forma por meio do datacenter.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-107">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="2b3f6-108">Requirements</span><span class="sxs-lookup"><span data-stu-id="2b3f6-108">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="2b3f6-109">Assinaturas</span><span class="sxs-lookup"><span data-stu-id="2b3f6-109">Subscriptions</span></span>

<span data-ttu-id="2b3f6-110">Os recursos de proteção contra ameaças estão incluídos em *todas as* assinaturas do Microsoft ou do Office 365; no entanto, algumas assinaturas têm recursos avançados.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-110">Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features.</span></span> <span data-ttu-id="2b3f6-111">A tabela a seguir lista os recursos de proteção incluídos neste artigo junto com os requisitos mínimos de assinatura.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-111">The table below lists the protection features included in this article together with the minimum subscription requirements.</span></span>

> [!TIP]
> <span data-ttu-id="2b3f6-112">Observe que, além das instruções para ativar a auditoria, *as etapas* iniciam o anti-malware, o anti-phishing e o antispam, que são marcados como parte do Office 365 proteção do Exchange Online (**EOP**).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-112">Notice that, beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**).</span></span> <span data-ttu-id="2b3f6-113">Isso pode parecer estranho em um artigo avançado de proteção contra ameaças, até que você lembre que a proteção avançada contra ameaças (**ATP**) contém e se baseia no EOP.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-113">This can seem odd in an Advanced Threat Protection article, until you remember Advanced Threat Protection (**ATP**) contains, and builds on, EOP.</span></span>

****

|<span data-ttu-id="2b3f6-114">Tipo de proteção</span><span class="sxs-lookup"><span data-stu-id="2b3f6-114">Protection type</span></span>|<span data-ttu-id="2b3f6-115">Requisito de assinatura</span><span class="sxs-lookup"><span data-stu-id="2b3f6-115">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="2b3f6-116">Log de auditoria (para fins de relatórios)</span><span class="sxs-lookup"><span data-stu-id="2b3f6-116">Audit logging (for reporting purposes)</span></span>|[<span data-ttu-id="2b3f6-117">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2b3f6-117">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|<span data-ttu-id="2b3f6-118">Proteção antimalware</span><span class="sxs-lookup"><span data-stu-id="2b3f6-118">Anti-malware protection</span></span>|<span data-ttu-id="2b3f6-119">[Proteção do Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span><span class="sxs-lookup"><span data-stu-id="2b3f6-119">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span></span>|
|<span data-ttu-id="2b3f6-120">Proteção anti-phishing</span><span class="sxs-lookup"><span data-stu-id="2b3f6-120">Anti-phishing protection</span></span>|[<span data-ttu-id="2b3f6-121">EOP</span><span class="sxs-lookup"><span data-stu-id="2b3f6-121">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="2b3f6-122">Proteção antispam</span><span class="sxs-lookup"><span data-stu-id="2b3f6-122">Anti-spam protection</span></span>|[<span data-ttu-id="2b3f6-123">EOP</span><span class="sxs-lookup"><span data-stu-id="2b3f6-123">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="2b3f6-124">Limpeza automática de zero horas (para email)</span><span class="sxs-lookup"><span data-stu-id="2b3f6-124">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="2b3f6-125">EOP</span><span class="sxs-lookup"><span data-stu-id="2b3f6-125">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="2b3f6-126">Proteção contra URLs e arquivos mal-intencionados em emails e documentos do Office (links seguros e anexos seguros)</span><span class="sxs-lookup"><span data-stu-id="2b3f6-126">Protection from malicious URLs and files in email and Office documents (safe links and safe attachments)</span></span>|<span data-ttu-id="2b3f6-127">[Proteção avançada contra ameaças do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (**ATP**)</span><span class="sxs-lookup"><span data-stu-id="2b3f6-127">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (**ATP**)</span></span>|
|<span data-ttu-id="2b3f6-128">Ativar a ATP para cargas de trabalho do SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2b3f6-128">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>| [<span data-ttu-id="2b3f6-129">ATP</span><span class="sxs-lookup"><span data-stu-id="2b3f6-129">ATP</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide)|
|<span data-ttu-id="2b3f6-130">Proteção anti-phishing avançada</span><span class="sxs-lookup"><span data-stu-id="2b3f6-130">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="2b3f6-131">ATP</span><span class="sxs-lookup"><span data-stu-id="2b3f6-131">ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="2b3f6-132">Funções e permissões</span><span class="sxs-lookup"><span data-stu-id="2b3f6-132">Roles and permissions</span></span>

<span data-ttu-id="2b3f6-133">Para configurar as políticas de ATP, você deve ter uma função apropriada no [centro de conformidade de & de segurança](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-133">To configure ATP policies, you must be assigned an appropriate role in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="2b3f6-134">Confira a tabela abaixo para funções que podem executar essas ações.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-134">Take a look at the table below for roles that can do these actions.</span></span>

****

|<span data-ttu-id="2b3f6-135">Função ou grupo de funções</span><span class="sxs-lookup"><span data-stu-id="2b3f6-135">Role or role group</span></span>|<span data-ttu-id="2b3f6-136">Onde saber mais</span><span class="sxs-lookup"><span data-stu-id="2b3f6-136">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="2b3f6-137">administrador global</span><span class="sxs-lookup"><span data-stu-id="2b3f6-137">global administrator</span></span>|[<span data-ttu-id="2b3f6-138">Sobre as funções de administrador do Microsoft 365 </span><span class="sxs-lookup"><span data-stu-id="2b3f6-138">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="2b3f6-139">Administrador de Segurança</span><span class="sxs-lookup"><span data-stu-id="2b3f6-139">Security Administrator</span></span>|[<span data-ttu-id="2b3f6-140">Permissões da função de administrador no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2b3f6-140">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="2b3f6-141">Gerenciamento de Organização do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2b3f6-141">Exchange Online Organization Management</span></span>|[<span data-ttu-id="2b3f6-142">Permissões no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2b3f6-142">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="2b3f6-143">e</span><span class="sxs-lookup"><span data-stu-id="2b3f6-143">and</span></span><br> [<span data-ttu-id="2b3f6-144">PowerShell do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2b3f6-144">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="2b3f6-145">Para saber mais, confira [permissões no &amp; centro de conformidade de segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-145">To learn more, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="2b3f6-146">Antes de começar, ative o log de auditoria para relatórios e investigação</span><span class="sxs-lookup"><span data-stu-id="2b3f6-146">Before you begin, turn on Audit logging for reporting and investigation</span></span>

<span data-ttu-id="2b3f6-147">Inicie o log de auditoria no início.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-147">Start your audit logging early.</span></span> <span data-ttu-id="2b3f6-148">Você precisará de **auditoria para realizar** algumas das etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-148">You'll need auditing to be **ON** for certain of the steps that follow.</span></span> <span data-ttu-id="2b3f6-149">O log de auditoria está disponível em assinaturas que incluem o [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-149">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="2b3f6-150">Para exibir dados em relatórios de proteção contra ameaças, como o [painel de segurança](security-dashboard.md), [relatórios de segurança de email](view-email-security-reports.md)e [Explorer](threat-explorer.md), o log de auditoria deve estar *ativado*.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-150">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*.</span></span> <span data-ttu-id="2b3f6-151">Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-151">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="2b3f6-152">Parte 1-proteção Antimalware</span><span class="sxs-lookup"><span data-stu-id="2b3f6-152">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="2b3f6-153">A [proteção Antimalware](anti-malware-protection.md) está disponível em assinaturas que incluem [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-153">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="2b3f6-154">No [centro de conformidade & segurança](https://protection.office.com), escolha **Threat management**  >  **Policy**  >  **anti-malware**de política de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-154">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="2b3f6-155">Clique duas vezes na política **padrão** e, em seguida, escolha **configurações**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-155">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="2b3f6-156">Especifique as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="2b3f6-156">Specify the following settings:</span></span>

    - <span data-ttu-id="2b3f6-157">Na seção **resposta de detecção de malware** , mantenha a configuração padrão **no**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-157">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="2b3f6-158">Na seção **filtro de tipos de anexo comuns** , escolha **ativado**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-158">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="2b3f6-159">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-159">Click **Save**.</span></span>

<span data-ttu-id="2b3f6-160">Para saber mais sobre opções de política Antimalware, consulte [Configure anti-malware Policies](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-160">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---anti-phishing-protection"></a><span data-ttu-id="2b3f6-161">Parte 2-proteção contra phishing</span><span class="sxs-lookup"><span data-stu-id="2b3f6-161">Part 2 - Anti-phishing protection</span></span>

<span data-ttu-id="2b3f6-162">[Anti-phishing]</span><span class="sxs-lookup"><span data-stu-id="2b3f6-162">[Anti-phishing]</span></span>

<span data-ttu-id="2b3f6-163">A [proteção contra phishing](anti-phishing-protection.md) está disponível em assinaturas que incluem [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-163">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="2b3f6-164">A proteção contra phishing avançada está disponível na [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-164">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="2b3f6-165">O procedimento a seguir descreve como configurar uma política anti-phishing do ATP.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-165">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="2b3f6-166">As etapas são semelhantes à configuração de uma política anti-phishing (sem ATP).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-166">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="2b3f6-167">No [centro de conformidade & segurança](https://protection.office.com), escolha política de **Gerenciamento de ameaças**  >  **Policy**  >  **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-167">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="2b3f6-168">Clique em **política padrão**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-168">Click **Default policy**.</span></span>

3. <span data-ttu-id="2b3f6-169">Na seção **representação** , clique em **Editar**e especifique as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="2b3f6-169">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="2b3f6-170">Na guia **Adicionar usuários para proteger** *, ative a* proteção.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-170">On the **Add users to protect** tab, turn *On* protection.</span></span> <span data-ttu-id="2b3f6-171">Em seguida, adicione usuários, como os membros da diretoria da sua organização, seu CEO, CFO e outros líderes seniores.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-171">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="2b3f6-172">(Você pode digitar um endereço de email individual ou clicar para exibir uma lista.)</span><span class="sxs-lookup"><span data-stu-id="2b3f6-172">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="2b3f6-173">Na guia **adicionar domínios para proteger** , ative **automaticamente os domínios que eu sou proprietário**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-173">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="2b3f6-174">Se você tiver domínios personalizados, adicione-os agora.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-174">If you have custom domains, add them now.</span></span>

   - <span data-ttu-id="2b3f6-175">Na guia **ações** , selecione **colocar a mensagem em quarentena** para as opções **usuário representado** e **domínio representado** .</span><span class="sxs-lookup"><span data-stu-id="2b3f6-175">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="2b3f6-176">Além disso, ative as dicas de segurança de representação.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-176">Also, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="2b3f6-177">Na guia **inteligência de caixa de correio** , verifique se a inteligência de caixa de correio está ativada e ative a proteção de representação baseada em inteligência de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-177">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on and turn on mailbox intelligence-based impersonation protection.</span></span> <span data-ttu-id="2b3f6-178">Na lista **se o email é enviado por um usuário representado** , escolha **colocar a mensagem em quarentena**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-178">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="2b3f6-179">Na guia **Adicionar remetentes confiáveis e domínios** , especifique os remetentes ou domínios confiáveis que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-179">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="2b3f6-180">**Salve** na guia **revisar suas configurações** depois de revisar suas configurações.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-180">**Save** on the **Review your settings** tab after you've reviewed your settings.</span></span>

4. <span data-ttu-id="2b3f6-181">Na seção **spoof** , clique em **Editar**e especifique as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="2b3f6-181">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="2b3f6-182">Na guia **configurações de filtro de falsificação** , verifique se a proteção contra falsificação está ativada.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-182">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="2b3f6-183">Na guia **ações** , escolha **colocar a mensagem em quarentena**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-183">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="2b3f6-184">**Salve** na guia **revisar suas configurações** depois de revisar as alterações.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-184">**Save** on the **Review your settings** tab after you have reviewed your changes.</span></span> <span data-ttu-id="2b3f6-185">(Se você não fez nenhuma alteração, **cancele**.)</span><span class="sxs-lookup"><span data-stu-id="2b3f6-185">(If you didn't make any changes, **Cancel**.)</span></span>

5. <span data-ttu-id="2b3f6-186">Feche a página de configurações de política padrão.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-186">Close the default policy settings page.</span></span>

<span data-ttu-id="2b3f6-187">Para saber mais sobre suas opções de política anti-phishing, consulte [Configure ATP anti-phishing Policies](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-187">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-3---anti-spam-protection"></a><span data-ttu-id="2b3f6-188">Parte 3-proteção antispam</span><span class="sxs-lookup"><span data-stu-id="2b3f6-188">Part 3 - Anti-spam protection</span></span>

<span data-ttu-id="2b3f6-189">A [proteção](anti-spam-protection.md) antispam está disponível em assinaturas que incluem [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-189">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="2b3f6-190">No [centro de conformidade & segurança](https://protection.office.com), escolha **Threat management**  >  **Policy**  >  **anti-spam**de política de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-190">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="2b3f6-191">Na guia **Personalizar** , ative as configurações personalizadas.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-191">On the **Custom** tab, turn on Custom settings.</span></span>

3. <span data-ttu-id="2b3f6-192">Expanda **política de filtro de spam padrão**, clique em **Editar política**e especifique as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="2b3f6-192">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="2b3f6-193">Na seção **ações de spam e em massa** , defina o limite para um valor de 5 ou 6.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-193">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="2b3f6-194">Na seção **permitir listas** , revise (e/ou edite) seus remetentes e domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-194">In the **Allow lists** section, review (and/or edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="2b3f6-195">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-195">Click **Save**.</span></span>

<span data-ttu-id="2b3f6-196">Para saber mais sobre suas opções de política antispam, consulte [Configure anti-spam Policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-196">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments"></a><span data-ttu-id="2b3f6-197">Parte 4-proteção contra URLs e arquivos mal-intencionados (links seguros e anexos seguros)</span><span class="sxs-lookup"><span data-stu-id="2b3f6-197">Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments)</span></span>

<span data-ttu-id="2b3f6-198">A proteção de horário de clique de URLs e arquivos mal-intencionados está disponível em assinaturas que incluem o [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-198">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP).</span></span> <span data-ttu-id="2b3f6-199">Ela é configurada por meio de [anexos seguros de ATP](atp-safe-attachments.md) e políticas de [links seguros de ATP](atp-safe-links.md) .</span><span class="sxs-lookup"><span data-stu-id="2b3f6-199">It's set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="2b3f6-200">Políticas de anexos seguros de ATP</span><span class="sxs-lookup"><span data-stu-id="2b3f6-200">ATP Safe Attachments policies</span></span>

<span data-ttu-id="2b3f6-201">Para configurar [anexos de segurança ATP](atp-safe-attachments.md), você deve definir pelo menos uma política de anexos seguros de ATP.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-201">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="2b3f6-202">No [centro de conformidade & segurança](https://protection.office.com), escolha a política de **Gerenciamento de ameaça**  >  **Policy**  >  **anexos seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-202">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="2b3f6-203">Selecione a opção **ativar a ATP para SharePoint, onedrive e Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-203">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="2b3f6-204">Na seção **proteger anexos de email** , clique no sinal de mais ( **+** ).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-204">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="2b3f6-205">Especifique as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="2b3f6-205">Specify the following settings:</span></span>

   - <span data-ttu-id="2b3f6-206">Na caixa **nome** , digite `Block malware` .</span><span class="sxs-lookup"><span data-stu-id="2b3f6-206">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="2b3f6-207">Na seção resposta, escolha **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-207">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="2b3f6-208">Na seção **redirecionar anexo** , selecione a opção **habilitar redirecionamento**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-208">In the **Redirect attachment** section, select the option **Enable redirect**.</span></span> <span data-ttu-id="2b3f6-209">Especifique o endereço de email para o operador ou administrador de segurança da sua organização, que examinará os arquivos detectados.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-209">Specify the email address for your organization's security administrator or operator, who will review detected files.</span></span>

   - <span data-ttu-id="2b3f6-210">Na seção **aplica-se** a, escolha **o domínio do destinatário**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-210">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="2b3f6-211">Em seguida, selecione o seu domínio, escolha **Adicionar**e **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-211">Then, select your domain, choose **Add**, and then **OK**.</span></span>

5. <span data-ttu-id="2b3f6-212">**Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-212">**Save**.</span></span>

6. <span data-ttu-id="2b3f6-213">(**Etapa adicional recomendada**) Como administrador global ou administrador do SharePoint Online, execute o cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** com o parâmetro **DisallowInfectedFileDownload** definido como  *true* para seu ambiente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-213">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Microsoft 365 environment.</span></span> <span data-ttu-id="2b3f6-214">(Isso impede que as pessoas abram, movam, copiem ou compartilhem arquivos detectados como mal-intencionados.)</span><span class="sxs-lookup"><span data-stu-id="2b3f6-214">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="2b3f6-215">Para saber mais, confira [configurar as políticas de anexos seguros do Microsoft office 365 ATP](set-up-atp-safe-attachments-policies.md) e [ativar o Office 365 ATP para SharePoint, onedrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-215">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="2b3f6-216">Políticas de links seguros de ATP</span><span class="sxs-lookup"><span data-stu-id="2b3f6-216">ATP Safe Links policies</span></span>

<span data-ttu-id="2b3f6-217">Para configurar [links de ATP seguros](atp-safe-links.md), revise e edite sua política padrão e adicione uma política para usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-217">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="2b3f6-218">No [centro de conformidade & segurança](https://protection.office.com), escolha política de **Gerenciamento de ameaça**  >  **Policy**  >  **links seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-218">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="2b3f6-219">Clique duas vezes na política **padrão** .</span><span class="sxs-lookup"><span data-stu-id="2b3f6-219">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="2b3f6-220">Na seção **usar links seguros em** , selecione a opção **Microsoft 365 aplicativos para empresas, Office para IOS e Android**e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-220">In the **Use safe links in** section, select the option **Microsoft 365 Apps for enterprise, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="2b3f6-221">Na seção **políticas que se aplicam a destinatários específicos** , clique no sinal de mais ( **+** ).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-221">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="2b3f6-222">Especifique as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="2b3f6-222">Specify the following settings:</span></span>

   - <span data-ttu-id="2b3f6-223">Na caixa **nome** , digite um nome, como `Safe Links` .</span><span class="sxs-lookup"><span data-stu-id="2b3f6-223">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="2b3f6-224">Na seção **Selecionar ação** , escolha **ativado**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-224">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="2b3f6-225">Selecione estas opções:</span><span class="sxs-lookup"><span data-stu-id="2b3f6-225">Select these options:</span></span>

     - <span data-ttu-id="2b3f6-226">**Usar anexos seguros para examinar Conteúdo baixável**</span><span class="sxs-lookup"><span data-stu-id="2b3f6-226">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="2b3f6-227">**Aplicar links seguros a mensagens de email enviadas dentro da organização**</span><span class="sxs-lookup"><span data-stu-id="2b3f6-227">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="2b3f6-228">**Não permitir que os usuários cliquem por meio de links seguros para a URL original**</span><span class="sxs-lookup"><span data-stu-id="2b3f6-228">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="2b3f6-229">Na seção **aplica-se** a, escolha **o domínio do destinatário**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-229">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="2b3f6-230">Em seguida, selecione o seu domínio, escolha **Adicionar**e **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-230">Then, select your domain, choose **Add**, and then **OK**.</span></span>

6. <span data-ttu-id="2b3f6-231">**Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-231">**Save**.</span></span>

<span data-ttu-id="2b3f6-232">Para saber mais, confira [Configurar políticas de Links Seguros ATP do Office 365](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-232">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads"></a><span data-ttu-id="2b3f6-233">Parte 5-ativar a ATP para cargas de trabalho do SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2b3f6-233">Part 5 - Turn on ATP for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>

<span data-ttu-id="2b3f6-234">Cargas de trabalho como o SharePoint, o OneDrive e o Microsoft Teams são criadas para colaboração.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-234">Workloads like SharePoint, OneDrive, and Teams are built for collaboration.</span></span> <span data-ttu-id="2b3f6-235">O uso de ATP ajuda no bloqueio e na detecção de arquivos identificados como mal-intencionados em sites de equipe e bibliotecas de documentos.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-235">Using ATP helps with blocking and detection of files that are identified as malicious in team sites and document libraries.</span></span> <span data-ttu-id="2b3f6-236">Você pode ler mais sobre como isso funciona [aqui](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-236">You can read more about how that works [here](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams?view=o365-worldwide).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b3f6-237">**Antes de iniciar esse procedimento, certifique-se de que o log de auditoria já esteja ativado para seu ambiente do Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-237">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="2b3f6-238">Isso geralmente é feito por alguém que tenha a função de logs de auditoria atribuída no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-238">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="2b3f6-239">Para obter mais informações, consulte [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md)!</span><span class="sxs-lookup"><span data-stu-id="2b3f6-239">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!</span></span>

1. <span data-ttu-id="2b3f6-240">Vá até <https://protection.office.com> e entre com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-240">Go to <https://protection.office.com>, and sign in with your work or school account.</span></span>

2. <span data-ttu-id="2b3f6-241">No centro de conformidade & segurança, no painel de navegação esquerdo, em **Gerenciamento de ameaças**, **Policy** escolha \> **anexos seguros**da política.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-241">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>

   ![No centro de conformidade & segurança, escolha política de gerenciamento de ameaças \>](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. <span data-ttu-id="2b3f6-243">Selecione **Ativar ATP para SharePoint, onedrive e Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-243">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

   ![Ativar a proteção avançada contra ameaças para o SharePoint Online, o OneDrive for Business e o Microsoft Teams](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. <span data-ttu-id="2b3f6-245">**Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-245">**Save**.</span></span>

5. <span data-ttu-id="2b3f6-246">Revise (e, conforme apropriado, edite) as [políticas de anexos seguros](set-up-atp-safe-attachments-policies.md) da sua organização e [as políticas de links seguros](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-246">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

6. <span data-ttu-id="2b3f6-247">Recomenda Como administrador global ou administrador do SharePoint Online, execute o cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** com o parâmetro _DisallowInfectedFileDownload_ definido como `$true` .</span><span class="sxs-lookup"><span data-stu-id="2b3f6-247">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to `$true`.</span></span>

   - <span data-ttu-id="2b3f6-248">`$true` bloqueia todas as ações (exceto excluir) para arquivos detectados.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-248">`$true` blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="2b3f6-249">As pessoas não podem abrir, mover, copiar ou compartilhar arquivos detectados.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-249">People cannot open, move, copy, or share detected files.</span></span>
   - <span data-ttu-id="2b3f6-250">`$false` bloqueia todas as ações, exceto excluir e baixar.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-250">`$false` blocks all actions except Delete and Download.</span></span> <span data-ttu-id="2b3f6-251">As pessoas podem optar por aceitar o risco e baixar um arquivo detectado.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-251">People can choose to accept the risk and download a detected file.</span></span>

   > [!TIP]
   > <span data-ttu-id="2b3f6-252">Para saber mais sobre como usar o PowerShell com o Microsoft 365, confira [gerenciar o microsoft 365 com o PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-252">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).</span></span>

7. <span data-ttu-id="2b3f6-253">Aguarde até 30 minutos para que as alterações se espalhem para todos os datacenters da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-253">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

### <a name="now-set-up-alerts-for-detected-files"></a><span data-ttu-id="2b3f6-254">Agora configure alertas para arquivos detectados</span><span class="sxs-lookup"><span data-stu-id="2b3f6-254">Now set up alerts for detected files</span></span>

<span data-ttu-id="2b3f6-255">Para receber notificações quando um arquivo no SharePoint Online, no OneDrive for Business ou no Microsoft Teams foi identificado como mal-intencionado, você pode configurar um alerta.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-255">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="2b3f6-256">No [centro de conformidade & segurança](https://protection.office.com), escolha **alertas** \> **Gerenciar alertas**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-256">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="2b3f6-257">Escolha **nova política de alerta**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-257">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="2b3f6-258">Especifique um nome para o alerta.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-258">Specify a name for the alert.</span></span> <span data-ttu-id="2b3f6-259">Por exemplo, você pode digitar arquivos mal-intencionados em bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-259">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="2b3f6-260">Digite uma descrição para o alerta.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-260">Type a description for the alert.</span></span> <span data-ttu-id="2b3f6-261">Por exemplo, você pode digitar notifica os administradores quando arquivos mal-intencionados são detectados no SharePoint Online, no OneDrive ou no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-261">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="2b3f6-262">Na seção **Enviar este alerta quando...** , defina:</span><span class="sxs-lookup"><span data-stu-id="2b3f6-262">In the **Send this alert when...** section, set:</span></span>

   <span data-ttu-id="2b3f6-263">a.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-263">a.</span></span> <span data-ttu-id="2b3f6-264">Na lista **atividades** , escolha **malware detectado em arquivo**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-264">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="2b3f6-265">b.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-265">b.</span></span> <span data-ttu-id="2b3f6-266">Deixe o campo **usuários** vazio.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-266">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="2b3f6-267">Na seção **Enviar este alerta para...** , selecione um ou mais administradores globais, administradores de segurança ou leitores de segurança que devem receber notificações quando um arquivo mal-intencionado for detectado.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-267">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="2b3f6-268">**Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-268">**Save**.</span></span>

<span data-ttu-id="2b3f6-269">Para saber mais sobre alertas, confira [criar alertas de atividade no centro de conformidade de & de segurança](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-269">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2b3f6-270">Quando terminar de configurar o, use estes links para iniciar investigações de carga de trabalho:</span><span class="sxs-lookup"><span data-stu-id="2b3f6-270">When you're finished configuring, use these links to start workload investigations:</span></span>
>
> - [<span data-ttu-id="2b3f6-271">Exibir informações sobre arquivos mal-intencionados detectados no SharePoint, no OneDrive ou no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2b3f6-271">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
> - [<span data-ttu-id="2b3f6-272">O que fazer quando um arquivo mal-intencionado é encontrado no SharePoint Online, no OneDrive ou no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2b3f6-272">What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams</span></span>](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
> - [<span data-ttu-id="2b3f6-273">Gerenciar arquivos e mensagens em quarentena como um administrador no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b3f6-273">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a><span data-ttu-id="2b3f6-274">Parte 6-configurações adicionais a serem definidas</span><span class="sxs-lookup"><span data-stu-id="2b3f6-274">Part 6 - Additional settings to configure</span></span>

<span data-ttu-id="2b3f6-275">Além de configurar a proteção contra malware, URLs e arquivos mal-intencionados, phishing e spam, recomendamos que você configure a limpeza automática de zero hora.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-275">Along with configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend you configure zero-hour auto purge.</span></span>

### <a name="zero-hour-auto-purge-for-email-in-eop"></a><span data-ttu-id="2b3f6-276">Limpeza automática de zero horas para email no EOP</span><span class="sxs-lookup"><span data-stu-id="2b3f6-276">Zero-hour auto purge for email in EOP</span></span>

<span data-ttu-id="2b3f6-277">[A limpeza automática de zero horas](zero-hour-auto-purge.md) (zap) está disponível em assinaturas que incluem [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-277">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="2b3f6-278">Essa proteção é ativada por padrão; no entanto, as seguintes condições devem ser atendidas para que a proteção entre em vigor:</span><span class="sxs-lookup"><span data-stu-id="2b3f6-278">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="2b3f6-279">As ações de spam são definidas para **mover mensagens para a pasta lixo eletrônico** em [políticas antispam](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-279">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="2b3f6-280">Os usuários têm mantido suas [configurações padrão de lixo eletrônico](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)e não desativaram a proteção de lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-280">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and haven't turned off junk email protection.</span></span>

<span data-ttu-id="2b3f6-281">Para saber mais, confira [exclusão automática de zero horas-proteção contra spam e malware](zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="2b3f6-281">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

## <a name="post-setup-tasks-and-next-steps"></a><span data-ttu-id="2b3f6-282">Tarefas pós-instalação e próximas etapas</span><span class="sxs-lookup"><span data-stu-id="2b3f6-282">Post-setup tasks and next steps</span></span>

<span data-ttu-id="2b3f6-283">Depois de configurar os recursos de proteção contra ameaças, certifique-se de monitorar como esses recursos estão funcionando!</span><span class="sxs-lookup"><span data-stu-id="2b3f6-283">After configuring the threat protection features, make sure to monitor how those features are working!</span></span> <span data-ttu-id="2b3f6-284">Revise e revise suas políticas para que elas façam o que você precisa.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-284">Review and revise your policies so that they do what you need them to.</span></span> <span data-ttu-id="2b3f6-285">Além disso, Assista a novos recursos e atualizações de serviço que podem agregar valor.</span><span class="sxs-lookup"><span data-stu-id="2b3f6-285">Also, watch for new features and service updates that can add value.</span></span>

****

|<span data-ttu-id="2b3f6-286">O que fazer</span><span class="sxs-lookup"><span data-stu-id="2b3f6-286">What to do</span></span>|<span data-ttu-id="2b3f6-287">Recursos para saber mais</span><span class="sxs-lookup"><span data-stu-id="2b3f6-287">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="2b3f6-288">Veja como os recursos de proteção contra ameaças estão trabalhando para sua organização exibindo relatórios</span><span class="sxs-lookup"><span data-stu-id="2b3f6-288">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="2b3f6-289">Painel de segurança</span><span class="sxs-lookup"><span data-stu-id="2b3f6-289">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="2b3f6-290">Relatórios de segurança de email</span><span class="sxs-lookup"><span data-stu-id="2b3f6-290">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="2b3f6-291">Relatórios para o Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="2b3f6-291">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="2b3f6-292">Explorador de Ameaças</span><span class="sxs-lookup"><span data-stu-id="2b3f6-292">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="2b3f6-293">Revisar e revisar periodicamente suas políticas de proteção contra ameaças, conforme necessário</span><span class="sxs-lookup"><span data-stu-id="2b3f6-293">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="2b3f6-294">Classificação de segurança</span><span class="sxs-lookup"><span data-stu-id="2b3f6-294">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="2b3f6-295">Relatórios inteligentes e insights</span><span class="sxs-lookup"><span data-stu-id="2b3f6-295">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="2b3f6-296">Investigação de ameaças e recursos de resposta da Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b3f6-296">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="2b3f6-297">Assista a novos recursos e atualizações de serviço</span><span class="sxs-lookup"><span data-stu-id="2b3f6-297">Watch for new features and service updates</span></span>|[<span data-ttu-id="2b3f6-298">Opções de lançamento direcionado e padrão</span><span class="sxs-lookup"><span data-stu-id="2b3f6-298">Standard and Targeted release options</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[<span data-ttu-id="2b3f6-299">Centro de Mensagens</span><span class="sxs-lookup"><span data-stu-id="2b3f6-299">Message Center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[<span data-ttu-id="2b3f6-300">Roteiro do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b3f6-300">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="2b3f6-301">Descrições de serviço</span><span class="sxs-lookup"><span data-stu-id="2b3f6-301">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|<span data-ttu-id="2b3f6-302">Saiba mais sobre as configurações de segurança padrão e rígidas para o EOP e a ATP</span><span class="sxs-lookup"><span data-stu-id="2b3f6-302">Learn the details about recommended Standard and Strict security configurations for EOP and ATP</span></span> | [<span data-ttu-id="2b3f6-303">Configurações recomendadas para o EOP e a segurança ATP do Office 365</span><span class="sxs-lookup"><span data-stu-id="2b3f6-303">Recommended settings for EOP and Office 365 ATP security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) |
