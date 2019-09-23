---
title: Aplicar rótulos a dados pessoais no Office 365
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Saiba como usar os rótulos do Office como parte do seu plano de proteção do GDPR.
ms.openlocfilehash: 518e5352861242bfbf9220f876edcb4b616493df
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072340"
---
# <a name="apply-labels-to-personal-data-in-office-365"></a><span data-ttu-id="ffdce-103">Aplicar rótulos a dados pessoais no Office 365</span><span class="sxs-lookup"><span data-stu-id="ffdce-103">Apply labels to personal data in Office 365</span></span>

 <span data-ttu-id="ffdce-104">Use este tópico se você estiver usando rótulos de classificação como parte do seu plano de proteção GDPR.</span><span class="sxs-lookup"><span data-stu-id="ffdce-104">Use this topic if you are using classification labels as part of your GDPR protection plan.</span></span> 

<span data-ttu-id="ffdce-105">Se você estiver usando rótulos para proteção de dados pessoais no Office 365, recomendamos que você comece com [rótulos de retenção](labels.md).</span><span class="sxs-lookup"><span data-stu-id="ffdce-105">If you are using labels for protection of personal data in Office 365, Microsoft recommends you start with [retention labels](labels.md).</span></span> <span data-ttu-id="ffdce-106">Com os rótulos de retenção, você pode:</span><span class="sxs-lookup"><span data-stu-id="ffdce-106">With retention labels, you can:</span></span>
- <span data-ttu-id="ffdce-107">Use o Advanced Data Governance para aplicar automaticamente rótulos com base em tipos de informações confidenciais ou outros critérios.</span><span class="sxs-lookup"><span data-stu-id="ffdce-107">Use Advanced Data Governance to automatically apply labels based on sensitive information types or other criteria.</span></span>
- <span data-ttu-id="ffdce-108">Use rótulos de retenção com a prevenção de perda de dados para aplicar a proteção.</span><span class="sxs-lookup"><span data-stu-id="ffdce-108">Use retention labels with data loss prevention to apply protection.</span></span> 
- <span data-ttu-id="ffdce-109">Usar rótulos com Pesquisa de Conteúdo e Descoberta Eletrônica.</span><span class="sxs-lookup"><span data-stu-id="ffdce-109">Use labels with eDiscovery and Content Search.</span></span> 

<span data-ttu-id="ffdce-110">O Cloud App Security atualmente não suporta rótulos de retenção, mas você pode usar tipos de informações confidenciais do Office 365 com o Cloud App Security para monitorar dados pessoais que residem em outros aplicativos SaaS.</span><span class="sxs-lookup"><span data-stu-id="ffdce-110">Cloud App Security doesn't currently support retention labels, but you can use Office 365 sensitive information types with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>

<span data-ttu-id="ffdce-111">[Rótulos de confidencialidade](sensitivity-labels.md) atualmente são recomendados para a aplicação de rótulos a arquivos locais e em outros serviços de nuvem e provedores.</span><span class="sxs-lookup"><span data-stu-id="ffdce-111">[Sensitivity labels](sensitivity-labels.md) are currently recommended for applying labels to files on premises and in other cloud services and providers.</span></span> <span data-ttu-id="ffdce-112">Também são recomendados para arquivos no Office 365 que exijam criptografia de proteção de informações do Azure para a proteção de dados, como arquivos secretos.</span><span class="sxs-lookup"><span data-stu-id="ffdce-112">These are also recommended for files in Office 365 that require Azure Information Protection encryption for data protection, such as trade secret files.</span></span>

<span data-ttu-id="ffdce-113">Neste momento, usar a proteção de informações do Azure para aplicar a criptografia não é recomendável para arquivos no Office 365 com dados sujeitos ao GDPR.</span><span class="sxs-lookup"><span data-stu-id="ffdce-113">At this time, using Azure Information Protection to apply encryption is not recommended for files in Office 365 with data that is subject to the GDPR.</span></span> <span data-ttu-id="ffdce-114">Os serviços do Office 365 não podem ler em arquivos criptografados AIP no momento.</span><span class="sxs-lookup"><span data-stu-id="ffdce-114">Office 365 services currently cannot read into AIP-encrypted files.</span></span> <span data-ttu-id="ffdce-115">Portanto, o serviço não consegue encontrar dados confidenciais nesses arquivos.</span><span class="sxs-lookup"><span data-stu-id="ffdce-115">Therefore, the service can’t find sensitive data in these files.</span></span>

<span data-ttu-id="ffdce-116">Rótulos de retenção podem ser aplicados a email no Exchange Online e esses rótulos funcionam com a prevenção contra a perda de dados do Office 365. </span><span class="sxs-lookup"><span data-stu-id="ffdce-116">Retention labels can be applied to mail in Exchange Online and these labels work with Office 365 data loss prevention.</span></span> 

![Rótulos do Office 365 e rótulos da Proteção de Informações do Azure](Media/Apply-labels-to-personal-data-in-Office-365-image1.png)


<span data-ttu-id="ffdce-118">Na ilustração:</span><span class="sxs-lookup"><span data-stu-id="ffdce-118">In the illustration:</span></span>

-   <span data-ttu-id="ffdce-119">Use os rótulos de retenção em dados pessoais e arquivos de segredos comerciais e altamente regulados no SharePoint Online e no OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="ffdce-119">Use retention labels for personal data and for highly regulated & trade secret files in SharePoint Online and OneDrive for Business.</span></span>
-   <span data-ttu-id="ffdce-120">Os tipos de informações confidenciais do Office 365 podem ser usados dentro do Office 365 e com o Cloud App Security para monitorar dados pessoais que residem em outros aplicativos SaaS. </span><span class="sxs-lookup"><span data-stu-id="ffdce-120">Office 365 sensitive information types can be used within Office 365 and with Cloud App Security to monintor personal data that resides in other SaaS apps.</span></span>
-   <span data-ttu-id="ffdce-121">Use os rótulos de confidencialidade em arquivos de segredos comerciais e altamente regulados, emails do Exchange Online, arquivos de outros serviços SaaS, arquivos em datacenters no local e arquivos em outros provedores de serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="ffdce-121">Use sensitivity labels for highly regulated & trade secret files, Exchange Online email, files in other SaaS services, files in on-premises datacenters, and files in other cloud providers.</span></span>


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a><span data-ttu-id="ffdce-122">Usar os rótulos de retenção e os tipos de informações confidenciais no Microsoft 365 para proteção de informações</span><span class="sxs-lookup"><span data-stu-id="ffdce-122">Use retention labels and sensitive information types across Microsoft 365 for information protection</span></span>

<span data-ttu-id="ffdce-123">A ilustração a seguir mostra como os rótulos de retenção e os tipos de informações confidenciais podem ser usados em políticas de rotulação, de prevenção contra perda de dados e nas políticas do Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="ffdce-123">The following illustration shows how retention labels and sensitive information types can be used in label policies, data loss prevention policies, and with Cloud App Security policies.</span></span>

![Rótulos do Office e tipos de informações confidenciais](Media/Apply-labels-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="ffdce-125">Para maior acessibilidade, a tabela a seguir fornece os mesmos exemplos da ilustração.</span><span class="sxs-lookup"><span data-stu-id="ffdce-125">For accessibility, the following table provides the same examples in the illustration.</span></span>

<table><span data-ttu-id="ffdce-126">
<thead>
<tr class="header">
<th align="left"><strong>Elementos de classificação</strong></span><span class="sxs-lookup"><span data-stu-id="ffdce-126">Classification elements</span></span></th>
<th align="left"><span data-ttu-id="ffdce-127"><strong>Políticas de rotulação – dois exemplos</strong></span><span class="sxs-lookup"><span data-stu-id="ffdce-127"><strong>Label policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="ffdce-128"><strong>Políticas de prevenção contra perda de dados – dois exemplos</strong></span><span class="sxs-lookup"><span data-stu-id="ffdce-128"><strong>Data loss prevention policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="ffdce-129"><strong>Políticas do Cloud App Security para todos os aplicativos SaaS – um exemplo</strong></span><span class="sxs-lookup"><span data-stu-id="ffdce-129"><strong>Cloud App Security policies for all SaaS apps — 1 example</strong></span></span></th>
</tr><span data-ttu-id="ffdce-130">
</thead>
<tbody>
<tr class="odd">
<td align="left">Rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="ffdce-130">Retention labels.</span></span> <span data-ttu-id="ffdce-131">Exemplos: Pessoal, Público, Dados do cliente, Dados de RH, Confidencial, Altamente confidencial</span><span class="sxs-lookup"><span data-stu-id="ffdce-131">Examples: Personal, Public, Customer data, HR data, Confidential, Highly confidential</span></span></td>
<td align="left"><p><span data-ttu-id="ffdce-p105">Aplicar automaticamente este rótulo...</span><span class="sxs-lookup"><span data-stu-id="ffdce-p105">Auto apply this label . . .</span></span></p>
<p><span data-ttu-id="ffdce-135">Dados do cliente</span><span class="sxs-lookup"><span data-stu-id="ffdce-135">Customer data</span></span></p>
<p><span data-ttu-id="ffdce-p106">...aos documentos que correspondam a estes tipos de informações confidenciais...</span><span class="sxs-lookup"><span data-stu-id="ffdce-p106">. . . to documents that match these sensitive information types . . .</span></span></p>
<p><span data-ttu-id="ffdce-142">&lt;lista de exemplos de tipos de informações confidenciais&gt;</span><span class="sxs-lookup"><span data-stu-id="ffdce-142">&lt;list of example sensitive information types&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffdce-p107">Aplicar esta proteção...</span><span class="sxs-lookup"><span data-stu-id="ffdce-p107">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="ffdce-146">&lt;definir proteção&gt;</span><span class="sxs-lookup"><span data-stu-id="ffdce-146">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="ffdce-p108">...aos documentos com este rótulo...</span><span class="sxs-lookup"><span data-stu-id="ffdce-p108">. . . to documents with this label . . .</span></span></p>
<p><span data-ttu-id="ffdce-153">Dados do cliente</span><span class="sxs-lookup"><span data-stu-id="ffdce-153">Customer data</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffdce-p109">Alertar quando os arquivos com esses atributos...</span><span class="sxs-lookup"><span data-stu-id="ffdce-p109">Alert when files with these attributes . . .</span></span></p>
<p><span data-ttu-id="ffdce-157">Escolha um ou mais atributos: atributo PII predefinido, tipo de informação confidencial do Office 365, rótulo de confidencialidade (API), expressão personalizada</span><span class="sxs-lookup"><span data-stu-id="ffdce-157">Choose one or more attribute: predefined PII attribute, Office 365 sensitive information type, sensitivity label (AIP), custom expression</span></span></p>
<p><span data-ttu-id="ffdce-158">.</span><span class="sxs-lookup"><span data-stu-id="ffdce-158">.</span></span> <span data-ttu-id="ffdce-159">.</span><span class="sxs-lookup"><span data-stu-id="ffdce-159">.</span></span> <span data-ttu-id="ffdce-160">.</span><span class="sxs-lookup"><span data-stu-id="ffdce-160">.</span></span> <span data-ttu-id="ffdce-161">que forem compartilhados fora da organização em qualquer aplicativo SaaS sancionado.</span><span class="sxs-lookup"><span data-stu-id="ffdce-161">in any sanctioned SaaS app are shared outside the organization</span></span></p><p><span data-ttu-id="ffdce-162">Obs.: rótulos de retenção atualmente não são suportados pelo Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="ffdce-162">Note: Retention labels are currently not supported in Cloud App Security.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ffdce-p111">Tipos de informações confidenciais. Exemplos: Número Nacional de Identificação da Bélgica, Número do cartão de crédito, Número de Cartão de Identidade da Croácia, ID nacional da Finlândia</span><span class="sxs-lookup"><span data-stu-id="ffdce-p111">Sensitive information types. Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</span></span></td>
<td align="left"><p><span data-ttu-id="ffdce-p112">Publicar rótulos para os usuários aplicarem manualmente...</span><span class="sxs-lookup"><span data-stu-id="ffdce-p112">Publish these labels for users to manually apply . . .</span></span></p>
<p><span data-ttu-id="ffdce-168">&lt;selecionar rótulos&gt;</span><span class="sxs-lookup"><span data-stu-id="ffdce-168">&lt;select labels&gt;</span></span></p>
<p><span data-ttu-id="ffdce-p113">...nestes locais...</span><span class="sxs-lookup"><span data-stu-id="ffdce-p113">. . . to these locations . . .</span></span></p>
<p><span data-ttu-id="ffdce-175">&lt;todos os locais ou escolher locais específicos&gt;</span><span class="sxs-lookup"><span data-stu-id="ffdce-175">&lt;all locations or choose specific locations&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffdce-p114">Aplicar esta proteção...</span><span class="sxs-lookup"><span data-stu-id="ffdce-p114">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="ffdce-179">&lt;definir proteção&gt;</span><span class="sxs-lookup"><span data-stu-id="ffdce-179">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="ffdce-p115">...aos documentos que correspondam a estes tipos de informações confidenciais&gt;</span><span class="sxs-lookup"><span data-stu-id="ffdce-p115">. . . to documents that match these sensitive information types&gt;</span></span></p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a><span data-ttu-id="ffdce-184">Priorizar as políticas de aplicação automática de rótulos</span><span class="sxs-lookup"><span data-stu-id="ffdce-184">Prioritize auto-apply label policies</span></span>

<span data-ttu-id="ffdce-p116">Para os dados pessoais sujeitos ao GDPR, a Microsoft recomenda a aplicação automática de rótulos usando os tipos de informações confidenciais que você selecionou para seu ambiente. É importante que as políticas de aplicação automática de rótulos sejam bem pensadas e testadas para alcançar o comportamento pretendido.</span><span class="sxs-lookup"><span data-stu-id="ffdce-p116">For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment. It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.</span></span>

<span data-ttu-id="ffdce-p117">Tanto a ordem de criação das políticas de aplicação automática quanto o fato de os usuários também aplicarem rótulos afetam o resultado. Por isso, é importante planejar a distribuição com atenção. Veja o que é preciso saber.</span><span class="sxs-lookup"><span data-stu-id="ffdce-p117">The order that auto-apply policies are created and whether users are also applying these labels affect the result. So, it is important to carefully plan the roll-out. Here’s what you need to know.</span></span>

### <a name="one-label-at-a-time"></a><span data-ttu-id="ffdce-189">Um rótulo por vez</span><span class="sxs-lookup"><span data-stu-id="ffdce-189">One label at a time</span></span>

<span data-ttu-id="ffdce-190">Só é possível atribuir um rótulo a um documento.</span><span class="sxs-lookup"><span data-stu-id="ffdce-190">You can only assign one label to a document.</span></span>

### <a name="older-auto-apply-policies-win"></a><span data-ttu-id="ffdce-191">As políticas de aplicação automática mais antigas têm prioridade</span><span class="sxs-lookup"><span data-stu-id="ffdce-191">Older auto-apply policies win</span></span>

<span data-ttu-id="ffdce-p118">Se houver várias regras de atribuição de um rótulo de aplicação automática e o conteúdo atender às condições de várias regras, o rótulo para a regra mais antiga será atribuído. Por esse motivo, é importante planejar as políticas de rotulação com atenção antes de configurá-las. Se uma organização precisar de uma alteração na prioridade das políticas de rotulação, será necessário excluí-las e recriá-las.</span><span class="sxs-lookup"><span data-stu-id="ffdce-p118">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned. For this reason, it is important to plan the label policies carefully before configuring them. If an organization requires a change to the priority of the label policies, they will need to delete and recreate them.</span></span>

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a><span data-ttu-id="ffdce-195">Os rótulos aplicados manualmente pelo usuário prevalecem sobre os rótulos com aplicação automática</span><span class="sxs-lookup"><span data-stu-id="ffdce-195">Manual user-applied labels trump auto-applied labels</span></span>

<span data-ttu-id="ffdce-p119">Os rótulos aplicados manualmente pelo usuário prevalecem sobre os rótulos com aplicação automática.As políticas de aplicação automática não podem substituir um rótulo já aplicado por um usuário. Porém, os usuários podem substituir rótulos aplicados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ffdce-p119">Manual user applied labels trump auto-applied labels. Auto-apply policies cannot replace a label that is already applied by a user. Users can replace labels that are auto-applied.</span></span>

### <a name="auto-assigned-labels-can-be-updated"></a><span data-ttu-id="ffdce-199">Os rótulos atribuídos automaticamente podem ser atualizados</span><span class="sxs-lookup"><span data-stu-id="ffdce-199">Auto-assigned labels can be updated</span></span>

<span data-ttu-id="ffdce-200">Os rótulos atribuídos automaticamente podem ser atualizados por políticas de rotulação mais recentes ou por atualizações das políticas existentes.</span><span class="sxs-lookup"><span data-stu-id="ffdce-200">Auto-assigned labels can be updated by either newer label policies or by updates to existing policies.</span></span>

<span data-ttu-id="ffdce-201">Seu plano para a implementação de rótulos deve:</span><span class="sxs-lookup"><span data-stu-id="ffdce-201">Be sure your plan for implementing labels includes:</span></span>

-   <span data-ttu-id="ffdce-202">Priorizar a ordem de criação de políticas de aplicação automática.</span><span class="sxs-lookup"><span data-stu-id="ffdce-202">Prioritizing the order that auto-apply policies are created.</span></span>

-   <span data-ttu-id="ffdce-p120">Deixar tempo suficiente para a aplicação automática de rótulos antes da distribuição para os usuários aplicarem manualmente. Pode levar até sete dias para que os rótulos sejam aplicados a todo o conteúdo que atende às condições.</span><span class="sxs-lookup"><span data-stu-id="ffdce-p120">Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply. It can take up to seven days for the labels to be applied to all content that matches the conditions.</span></span>

### <a name="example-priority-for-creating-the-auto-apply-policies"></a><span data-ttu-id="ffdce-205">Exemplo de prioridade para a criação de políticas de aplicação automática</span><span class="sxs-lookup"><span data-stu-id="ffdce-205">Example priority for creating the auto-apply policies</span></span>

<table><span data-ttu-id="ffdce-206">
<thead>
<tr class="header">
<th align="left"><strong>Rótulos</strong></span><span class="sxs-lookup"><span data-stu-id="ffdce-206">Labels</span></span></th>
<th align="left"><span data-ttu-id="ffdce-207"><strong>Ordem de prioridade para a criação de políticas de aplicação automática </strong></span><span class="sxs-lookup"><span data-stu-id="ffdce-207"><strong>Priority order to create auto-apply policies</strong></span></span></th>
</tr><span data-ttu-id="ffdce-208">
</thead>
<tbody>
<tr class="odd">
<td align="left">Recursos Humanos — Dados de Funcionários</span><span class="sxs-lookup"><span data-stu-id="ffdce-208">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="ffdce-209">1</span><span class="sxs-lookup"><span data-stu-id="ffdce-209">1</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ffdce-210">Dados do cliente</span><span class="sxs-lookup"><span data-stu-id="ffdce-210">Customer Data</span></span></td>
<td align="left"><span data-ttu-id="ffdce-211">2</span><span class="sxs-lookup"><span data-stu-id="ffdce-211">2</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ffdce-212">Altamente confidencial</span><span class="sxs-lookup"><span data-stu-id="ffdce-212">Highly Confidential</span></span></td>
<td align="left"><span data-ttu-id="ffdce-213">3</span><span class="sxs-lookup"><span data-stu-id="ffdce-213">3</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ffdce-214">Recursos humanos – dados salariais</span><span class="sxs-lookup"><span data-stu-id="ffdce-214">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="ffdce-215">4</span><span class="sxs-lookup"><span data-stu-id="ffdce-215">4</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ffdce-216">Confidencial</span><span class="sxs-lookup"><span data-stu-id="ffdce-216">Confidential</span></span></td>
<td align="left"><span data-ttu-id="ffdce-217">5</span><span class="sxs-lookup"><span data-stu-id="ffdce-217">5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ffdce-218">Público</span><span class="sxs-lookup"><span data-stu-id="ffdce-218">Public</span></span></td>
<td align="left"><span data-ttu-id="ffdce-219">6</span><span class="sxs-lookup"><span data-stu-id="ffdce-219">6</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ffdce-220">Pessoal</span><span class="sxs-lookup"><span data-stu-id="ffdce-220">Personal</span></span></td>
<td align="left"><span data-ttu-id="ffdce-221">Nenhuma política de aplicação automática</span><span class="sxs-lookup"><span data-stu-id="ffdce-221">No auto-apply policy</span></span></td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a><span data-ttu-id="ffdce-222">Criar rótulos e políticas de aplicação automática de rótulos</span><span class="sxs-lookup"><span data-stu-id="ffdce-222">Create labels and auto-apply label policies</span></span>

<span data-ttu-id="ffdce-223">Crie rótulos e políticas no centro de segurança e no centro de conformidade.</span><span class="sxs-lookup"><span data-stu-id="ffdce-223">Create labels and policies in the scurity center or the compliance center.</span></span>

<table><span data-ttu-id="ffdce-224">
<thead>
<tr class="header">
<th align="left"><strong>Etapa</strong></span><span class="sxs-lookup"><span data-stu-id="ffdce-224">Step</span></span></th>
<th align="left"><span data-ttu-id="ffdce-225"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="ffdce-225"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffdce-226">Conceder permissões aos membros da sua equipe de conformidade.</span><span class="sxs-lookup"><span data-stu-id="ffdce-226">Give permissions to members of your compliance team.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffdce-p121">Os membros da equipe de conformidade que criarão os rótulos precisam de permissões para usar o centro de segurança e/ou o centro de conformidade. Acesse as Permissões, no centro de segurança ou no centros de conformidade e modifique os membros do grupo Administrador de Conformidade.</span><span class="sxs-lookup"><span data-stu-id="ffdce-p121">Members of your compliance team who will create labels need permissions to use the security center and/or the compliance center. Go to Permissions in the security center or the compliance center and modify the members of the Compliance Administrator group.</span></span></p>
<p><span data-ttu-id="ffdce-229">Confira <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Conceder aos usuários acesso ao centro de segurança e/ou o centro de conformidade</a>.</span><span class="sxs-lookup"><span data-stu-id="ffdce-229">See <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Give users access to the security center and/or the compliance center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffdce-230">Crie rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="ffdce-230">Create retention labels.</span></span></p></td>
<td align="left"><span data-ttu-id="ffdce-231">Acesse Classificações, no centro de Segurança ou centro de Conformidade, escolha Rótulos de retenção e crie os rótulos para o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="ffdce-231">Go to Classifications in the Security center or the Compliance center, choose Retention labels, and create the labels for your environment.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffdce-232">Criar políticas de aplicação automática para rótulos.</span><span class="sxs-lookup"><span data-stu-id="ffdce-232">Create auto-apply policies for labels.</span></span></p></td>
<td align="left"><span data-ttu-id="ffdce-p122">Acesse Classificações, no centro de segurança ou centro de conformidade, escolha políticas de Rotulação e crie as políticas para a aplicação automática de rótulos. Certifique-se de criar as políticas por ordem de prioridade.</span><span class="sxs-lookup"><span data-stu-id="ffdce-p122">Go to Classification in security center or the compliance center, choose Label policies, and create the policies for auto-applying labels. Be sure to create these policies in the prioritized order.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ffdce-235">A ilustração a seguir mostra como criar um rótulo de aplicação automática para o Rótulo dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="ffdce-235">The following illustration shows how to create an auto-apply label for the Customer data label.</span></span>

![Criar e aplicar um rótulo para dados do cliente](Media/Apply-labels-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="ffdce-237">Na ilustração:</span><span class="sxs-lookup"><span data-stu-id="ffdce-237">In the illustration:</span></span>

-   <span data-ttu-id="ffdce-238">O rótulo "Dados do cliente" foi criado.</span><span class="sxs-lookup"><span data-stu-id="ffdce-238">The “Customer data” label is created.</span></span>

-   <span data-ttu-id="ffdce-239">Os tipos de informações confidenciais desejados para o GDPR foram listados: Número Nacional de Identificação da Bélgica, Número do cartão de crédito, Número de Cartão de Identidade da Croácia, ID nacional da Finlândia.</span><span class="sxs-lookup"><span data-stu-id="ffdce-239">The desired sensitive information types for GDPR are listed: Belgium National Number, Credit Card Number, Croatia Identity Card Number, Finland National ID.</span></span>

-   <span data-ttu-id="ffdce-240">Criar uma política de aplicação automática atribui o rótulo "Dados do cliente" a todo arquivo com um dos tipos de informação confidencial que você adicionar à política.</span><span class="sxs-lookup"><span data-stu-id="ffdce-240">Create an auto-apply policy assigns the label “Customer data” to any file that includes one of the sensitive information types that you add to the policy.</span></span>
