---
title: Aplicar proteção a dados pessoais no Office 365
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
- SPO_Content
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Saiba como usar políticas de prevenção de perda de dados (DLP) para proteger dados pessoais no Office 365.
ms.openlocfilehash: b529a6d58537c4effca3cf198dcf807a0680129d
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596058"
---
# <a name="apply-protection-to-personal-data-in-office-365"></a><span data-ttu-id="cfd65-103">Aplicar proteção a dados pessoais no Office 365</span><span class="sxs-lookup"><span data-stu-id="cfd65-103">Apply protection to personal data in Office 365</span></span>

<span data-ttu-id="cfd65-104">A proteção de informações pessoais no Office 365 inclui o uso de recursos de prevenção contra perda de dados.</span><span class="sxs-lookup"><span data-stu-id="cfd65-104">Protection of personal information in Office 365 includes using data loss prevention capabilities.</span></span> <span data-ttu-id="cfd65-105">Com as políticas de prevenção de perda de dados (DLP) no centro de conformidade, você pode identificar, monitorar e proteger automaticamente informações confidenciais no Office 365.</span><span class="sxs-lookup"><span data-stu-id="cfd65-105">With data loss prevention (DLP) policies in the compliance center, you can identify, monitor, and automatically protect sensitive information across Office 365.</span></span>

<span data-ttu-id="cfd65-p102">Este tópico descreve como usar a DLP para proteger dados pessoais. Este tópico também lista outros recursos de proteção que podem ser usados para garantir a conformidade com o GDPR, incluindo como definir as permissões das bibliotecas do SharePoint e usar as políticas de acesso de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p102">This topic describes how to use DLP to protect personal data. This topic also lists other protection capabilities that can be used to achieve GDPR compliance, including setting permissions in SharePoint libraries and using device access policies.</span></span>

## <a name="apply-protection-using-data-loss-prevention-in-office-365"></a><span data-ttu-id="cfd65-108">Aplicar proteção usando prevenção contra perda de dados no Office 365</span><span class="sxs-lookup"><span data-stu-id="cfd65-108">Apply protection using data loss prevention in Office 365</span></span>

<span data-ttu-id="cfd65-109">Com a DLP, você pode:</span><span class="sxs-lookup"><span data-stu-id="cfd65-109">With DLP, you can:</span></span>

-   <span data-ttu-id="cfd65-110">Identificar informações confidenciais em muitos locais.</span><span class="sxs-lookup"><span data-stu-id="cfd65-110">Identify sensitive information across many locations.</span></span>

-   <span data-ttu-id="cfd65-111">Impedir o compartilhamento acidental de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="cfd65-111">Prevent accidental sharing of sensitive information.</span></span>

-   <span data-ttu-id="cfd65-112">Ajudar os usuários a aprender a manter a conformidade sem interromper o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="cfd65-112">Help users learn how to stay compliant without interrupting their workflow.</span></span>

-   <span data-ttu-id="cfd65-113">Ver relatórios de DLP que mostram conteúdo que corresponde às políticas de DLP da sua organização.</span><span class="sxs-lookup"><span data-stu-id="cfd65-113">View DLP reports showing content that matches your organization’s DLP policies.</span></span>

<span data-ttu-id="cfd65-114">Para mais informações, confira [Visão geral das políticas de prevenção contra perda de dados](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e).</span><span class="sxs-lookup"><span data-stu-id="cfd65-114">For more information, see [Overview of data loss prevention policies](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e).</span></span>

![Opções para criar uma política de Prevenção Contra Perda de Dados](Media/Apply-protection-to-personal-data-in-Office-365-image1.png)

<span data-ttu-id="cfd65-116">Esta ilustração mostra as opções para criar uma política DLP:</span><span class="sxs-lookup"><span data-stu-id="cfd65-116">This illustration shows the options for creating a DLP policy:</span></span>

-   <span data-ttu-id="cfd65-p103">Escolha a proteção a aplicar. A proteção pode incluir:</span><span class="sxs-lookup"><span data-stu-id="cfd65-p103">Choose the protection to apply. Protection can include:</span></span>

    -   <span data-ttu-id="cfd65-119">Dicas de política para usuários</span><span class="sxs-lookup"><span data-stu-id="cfd65-119">Policy tips for users</span></span>

    -   <span data-ttu-id="cfd65-120">Relatório de email para administradores</span><span class="sxs-lookup"><span data-stu-id="cfd65-120">Email report for admins</span></span>

    -   <span data-ttu-id="cfd65-121">Impedir o compartilhamento externamente, internamente ou ambos</span><span class="sxs-lookup"><span data-stu-id="cfd65-121">Prevent sharing externally, internally, or both</span></span>

-   <span data-ttu-id="cfd65-p104">Escolha os critérios para aplicar a proteção. Aplique a proteção a documentos com esse tipo de conteúdo: é possível configurar a política para usar tipos de informações confidenciais e/ou rótulos.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p104">Choose the criteria for applying the protection. Apply the protection to documents with this type of content: you can configure the policy to use sensitive information types and/or labels.</span></span>

### <a name="using-dlp-for-gdpr-compliance"></a><span data-ttu-id="cfd65-124">Usar DLP para conformidade com o GDPR</span><span class="sxs-lookup"><span data-stu-id="cfd65-124">Using DLP for GDPR compliance</span></span>

<span data-ttu-id="cfd65-p105">Um dos principais usos da DPL do Office 365 é identificar dados pessoais relacionados a assuntos de dados da UE no ambiente do Office 365. A DPL do Office 365 pode notificar as equipes de conformidade sobre onde as informações pessoais estão armazenadas no SharePoint Online e no OneDrive for Business, ou quando os usuários enviam email contendo informações pessoais. A DLP pode ainda fornecer dicas de políticas aos seus funcionários ao trabalhar com informações pessoais relacionadas a residentes da UE.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p105">One of the primary uses of Office 365 DLP is to identify personal data related to EU data subjects in your Office 365 environment. Office 365 DLP can notify your compliance teams of where personal information is stored in SharePoint Online and OneDrive for Business, or when users send email containing personal information. DLP can also provide policy tips to your employees when working with personal information related to EU residents.</span></span>

<span data-ttu-id="cfd65-p106">Instruir e aumentar a conscientização em relação a onde os dados de residentes da UE estão armazenados no seu ambiente e como os seus funcionários têm permissão para gerenciá-los representam um nível de proteção de informações usando a DLP do Office 365. Muitas vezes, os funcionários que já têm acesso a esse tipo de informações precisam desse acesso para realizar suas tarefas do dia a dia. A aplicação das políticas de DLP para ajudar a manter a conformidade com o GDPR pode não exigir a restrição do acesso.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p106">Educating and raising awareness to where EU resident data is stored in your environment and how your employees are permitted to handle it represents one level of information protection using Office 365 DLP. Often, employees who already have access to this type of information require this access to do their day to day work. Enforcing DLP policies to help comply with GDPR may not require restricting access.</span></span>

<span data-ttu-id="cfd65-p107">No entanto, a conformidade com o GDPR geralmente envolve uma avaliação baseada em risco da organização, da perspectiva de segurança das informações e da perspectiva legal, identificação do tipo e onde as informações pessoais foram armazenadas, bem como se há uma justificativa legal para armazenar e processar essas informações. Com base nessa avaliação, a implementação de políticas para proteger a organização e estar em conformidade com o GDPR pode exigir a remoção do acesso dos funcionários a documentos que contenham informações pessoais de titulares dos dados da UE. Nos casos em que for preciso maior proteção, é possível configurar uma proteção adicional de DLP.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p107">However, complying with GDPR typically involves a risk-based assessment of the organization from both a legal and information security perspective, identification of what type and where personal information is stored, as well as if there's a legal justification to store and process that information. Based on this assessment, implementing policies to protect the organization and comply with GDPR might require removing access for employees to documents that contain personal information for EU data subjects. In cases where further protection is required, additional DLP protection can be configured.</span></span>

<span data-ttu-id="cfd65-p108">A tabela a seguir lista três configurações de aumento de proteção usando DLP. A primeira configuração, reconhecimento, pode ser usada como ponto de partida e nível mínimo de proteção do GDPR.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p108">The following table lists three configurations of increasing protection using DLP. The first configuration, awareness, can be used as a starting point and minimum level of protection for GDPR.</span></span>

### <a name="example-protection-levels-that-can-be-configured-with-dlp-policies-and-used-for-gdpr-compliance"></a><span data-ttu-id="cfd65-136">Exemplo de níveis de proteção que podem ser configurados com políticas DLP e usados para conformidade com o GDPR</span><span class="sxs-lookup"><span data-stu-id="cfd65-136">Example protection levels that can be configured with DLP policies and used for GDPR compliance</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cfd65-137"><strong>Nível de Proteção</strong></span><span class="sxs-lookup"><span data-stu-id="cfd65-137"><strong>Protection level</strong></span></span></th>
<th align="left"><span data-ttu-id="cfd65-138"><strong>Configuração de DLP para documentos com informações pessoais relacionadas a assuntos de dados da UE</strong></span><span class="sxs-lookup"><span data-stu-id="cfd65-138"><strong>DLP configuration for documents with personal information related to EU data subjects</strong></span></span></th>
<th align="left"><span data-ttu-id="cfd65-139"><strong>Benefícios e riscos</strong></span><span class="sxs-lookup"><span data-stu-id="cfd65-139"><strong>Benefits and risks</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="cfd65-140">Reconhecimento</span><span class="sxs-lookup"><span data-stu-id="cfd65-140">Awareness</span></span></td>
<td align="left"><p><span data-ttu-id="cfd65-141">Envie notificações por email para as equipes de conformidade quando esses dados forem encontrados em documentos no SharePoint Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="cfd65-141">Send email notifications to compliance teams when this data is found in documents in SharePoint Online and OneDrive for Business.</span></span></p>
<p><span data-ttu-id="cfd65-142">Personalize e exiba Dicas de Política para funcionários no SharePoint e no OneDrive for Business ao acessar documentos contendo esses dados.</span><span class="sxs-lookup"><span data-stu-id="cfd65-142">Customize and display Policy Tips to employees in SharePoint and OneDrive for Business when accessing documents containing this data.</span></span></p>
<p><span data-ttu-id="cfd65-143">Detectar e relatar quando esses dados estiverem sendo compartilhados.</span><span class="sxs-lookup"><span data-stu-id="cfd65-143">Detect and report when this data is being shared.</span></span></p></td>
<td align="left"><p><span data-ttu-id="cfd65-144">Aumente a conscientização das equipes e funcionários de conformidade sobre onde esses dados são armazenados.</span><span class="sxs-lookup"><span data-stu-id="cfd65-144">Raise awareness with compliance teams and employees about where this data is stored.</span></span></p>
<p><span data-ttu-id="cfd65-145">Instrua os funcionários sobre a política corporativa para lidar com documentos que contêm esses dados.</span><span class="sxs-lookup"><span data-stu-id="cfd65-145">Educate employees on corporate policy for handling documents containing this data.</span></span></p>
<p><span data-ttu-id="cfd65-146">Não impede que os funcionários compartilhem esses dados internamente ou externamente.</span><span class="sxs-lookup"><span data-stu-id="cfd65-146">Does not prevent employees from sharing this data internally or externally.</span></span></p>
<p><span data-ttu-id="cfd65-147">Revise os relatórios de DLP de dados compartilhados e decida se precisa aumentar a proteção.</span><span class="sxs-lookup"><span data-stu-id="cfd65-147">You can review DLP reports for shared data and decide if you need to increase the protection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cfd65-148">Impedir o compartilhamento externo</span><span class="sxs-lookup"><span data-stu-id="cfd65-148">Prevent external sharing</span></span></td>
<td align="left"><p><span data-ttu-id="cfd65-149">Restrinja o acesso a documentos que contenham esses dados no SharePoint Online e no OneDrive for Business quando esse conteúdo for compartilhado com usuários externos.</span><span class="sxs-lookup"><span data-stu-id="cfd65-149">Restrict access to documents that contain this data in SharePoint Online and OneDrive for Business when that content is shared with external users.</span></span></p>
<p><span data-ttu-id="cfd65-150">Impedir o envio de emails com documentos contendo esses dados para destinatários externos.</span><span class="sxs-lookup"><span data-stu-id="cfd65-150">Prevent sending emails with documents that contain this data to external recipients.</span></span></p>
<p><span data-ttu-id="cfd65-151">Detectar e relatar quando esses dados estiverem sendo compartilhados.</span><span class="sxs-lookup"><span data-stu-id="cfd65-151">Detect and report when this data is being shared.</span></span></p></td>
<td align="left"><p><span data-ttu-id="cfd65-152">Impede o compartilhamento externo desses dados enquanto permite que os funcionários trabalhem com esses dados internamente.</span><span class="sxs-lookup"><span data-stu-id="cfd65-152">Prevents external sharing of this data while allowing for employees to work with this data internally.</span></span></p>
<p><span data-ttu-id="cfd65-153">Revise os relatórios de DLP de dados compartilhados internamente e decida se precisa aumentar essa proteção.</span><span class="sxs-lookup"><span data-stu-id="cfd65-153">You can review DLP reports for internally shared data and decide if you need to increase this protection.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="cfd65-154">Impedir o compartilhamento interno e externo</span><span class="sxs-lookup"><span data-stu-id="cfd65-154">Prevent internal and external sharing</span></span></td>
<td align="left"><p><span data-ttu-id="cfd65-155">Restrinja o acesso a documentos que contenham esses dados no SharePoint Online e no OneDrive for Business quando esse conteúdo for compartilhado internamente ou externamente.</span><span class="sxs-lookup"><span data-stu-id="cfd65-155">Restrict access to documents that contain this data in SharePoint Online and OneDrive for Business when that content is shared internally or externally.</span></span></p>
<p><span data-ttu-id="cfd65-156">Impeça o envio de email que contém esses dados para destinatários internos e externos.</span><span class="sxs-lookup"><span data-stu-id="cfd65-156">Prevent sending emails that contain this data to both internal and external recipients.</span></span></p></td>
<td align="left"><p><span data-ttu-id="cfd65-157">Impede o compartilhamento interno e externo desses dados.</span><span class="sxs-lookup"><span data-stu-id="cfd65-157">Prevents internal and external sharing of this data.</span></span></p>
<p><span data-ttu-id="cfd65-158">Os funcionários podem não conseguir concluir tarefas que exijam trabalhar com esses dados.</span><span class="sxs-lookup"><span data-stu-id="cfd65-158">Employees might not be able to complete tasks that require working with this data.</span></span></p>
<p><span data-ttu-id="cfd65-159">Você pode revisar os relatórios de DLP para dados compartilhados internamente e externamente e decidir se é necessário um treinamento para usuário final.</span><span class="sxs-lookup"><span data-stu-id="cfd65-159">You can review DLP reports for internally or externally shared data and decide if end-user training is needed.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cfd65-p109">Observação: conforme os níveis de proteção aumentam, a capacidade dos usuários de acessar informações diminuirá em alguns casos e pode afetar a produtividade ou capacidade de concluir as tarefas diárias. O aumento dos níveis de proteção com a implementação de políticas que afetam os funcionários geralmente é acompanhado por um treinamento de usuários finais, instruindo os usuários sobre novas políticas de segurança e procedimentos para que continuem sendo mais produtivos em um ambiente mais seguro.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p109">Note: As the levels of protection increase, the ability of users to access information will decrease in some cases, and could potentially impact their productivity or ability to complete day to day tasks. Increasing protection levels by implementing policies that impact employees is typically accompanied by end-user training, educating users on new security policies and procedures to help them continue to be productive in a more secure environment.</span></span>

### <a name="example-dlp-policy-for-gdpr--awareness"></a><span data-ttu-id="cfd65-162">Exemplo de política DLP para GDPR — Reconhecimento</span><span class="sxs-lookup"><span data-stu-id="cfd65-162">Example DLP policy for GDPR — Awareness</span></span> 

<span data-ttu-id="cfd65-163">Nome: o reconhecimento de dados pessoais sujeitos ao GDPR.</span><span class="sxs-lookup"><span data-stu-id="cfd65-163">Name: Awareness for personal data that is subject to GDPR.</span></span>

<span data-ttu-id="cfd65-164">Descrição: exibir dicas de política para os funcionários, notificar equipes de conformidade quando esses dados forem encontrados no SharePoint Online e OneDrive for Business, detectar e relatar quando esses dados estiverem sendo compartilhados fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="cfd65-164">Description: Display policy tips to employees, notify compliance teams when this data is found in documents in SharePoint Online and OneDrive for Business, detect and report when this data is being shared outside your organization.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cfd65-165"><strong>Controle</strong></span><span class="sxs-lookup"><span data-stu-id="cfd65-165"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="cfd65-166"><strong>Configurações</strong></span><span class="sxs-lookup"><span data-stu-id="cfd65-166"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="cfd65-167">Escolha as informações para proteger</span><span class="sxs-lookup"><span data-stu-id="cfd65-167">Choose information to protect</span></span></td>
<td align="left"><span data-ttu-id="cfd65-168">Selecione um modelo de política personalizada.</span><span class="sxs-lookup"><span data-stu-id="cfd65-168">Select a Custom policy template.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cfd65-169">Locais</span><span class="sxs-lookup"><span data-stu-id="cfd65-169">Locations</span></span></td>
<td align="left"><span data-ttu-id="cfd65-170">Todos os locais no Office 365</span><span class="sxs-lookup"><span data-stu-id="cfd65-170">All locations in Office 365</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="cfd65-171">Localizar conteúdo que contém</span><span class="sxs-lookup"><span data-stu-id="cfd65-171">Find content that contains</span></span></td>
<td align="left"><span data-ttu-id="cfd65-172">Clique em "Editar" e adicione todos os tipos de informações confidenciais coletadas para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="cfd65-172">Click ‘Edit’ and add all the sensitive information types you curated for your environment.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cfd65-173">Detectar quando este conteúdo é compartilhado</span><span class="sxs-lookup"><span data-stu-id="cfd65-173">Detect when this content is shared</span></span></td>
<td align="left"><span data-ttu-id="cfd65-174">Marque esta caixa e selecione "com pessoas fora da minha organização".</span><span class="sxs-lookup"><span data-stu-id="cfd65-174">Check this box and select ‘with people outside my organization.’</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="cfd65-175">Notificar os usuários quando o conteúdo corresponder às configurações de política</span><span class="sxs-lookup"><span data-stu-id="cfd65-175">Notify users when content matches the policy settings</span></span></td>
<td align="left"><p><span data-ttu-id="cfd65-176">Marque esta caixa ("Mostrar dicas de política a usuários e enviar uma notificação de email para eles.")</span><span class="sxs-lookup"><span data-stu-id="cfd65-176">Check this box (“Show policy tips to users and send them an email notification.”)</span></span></p>
<p><span data-ttu-id="cfd65-p110">Clique em "Personalizar a dica e o email" e atualize eles para o seu ambiente. Veja as notificações padrão neste artigo: <a href="https://support.office.com/article/Send-email-notifications-and-show-policy-tips-for-DLP-policies-87496bc5-9601-4473-8021-cb05c71369c1?ui=en-US&amp;rs=en-US&amp;ad=US">Enviar notificações por email e mostrar dicas de política para políticas DLP</a>.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p110">Click ‘Customize the tip and email’ and update these for your environment. See the default notifications in this article: <a href="https://support.office.com/article/Send-email-notifications-and-show-policy-tips-for-DLP-policies-87496bc5-9601-4473-8021-cb05c71369c1?ui=en-US&amp;rs=en-US&amp;ad=US">Send email notifications and show policy tips for DLP policies</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cfd65-179">Detectar quando uma quantidade específica de informações confidenciais estiver sendo compartilhada de uma só vez</span><span class="sxs-lookup"><span data-stu-id="cfd65-179">Detect when a specific amount of sensitive info is being shared at one time</span></span></td>
<td align="left"><p><span data-ttu-id="cfd65-180">"Detectar quando o conteúdo que está sendo compartilhado contém: pelo menos ____ instâncias do mesmo tipo de informação confidencial" — Configure esse valor como 1.</span><span class="sxs-lookup"><span data-stu-id="cfd65-180">‘Detect when content that’s being shared contains: At least ____ instances of the same sensitive info type’ — Set this to 1.</span></span></p>
<p><span data-ttu-id="cfd65-p111">"Enviar relatórios de incidentes por email" — marque esta caixa. Clique em "Escolha o que incluir no relatório e quem receberá". Certifique-se de adicionar a sua equipe de conformidade.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p111">‘Send incident reports in email’ — check this box. Click ‘Choose what to include in the report and who receives it.’ Be sure to add your compliance team.</span></span></p>
<p><span data-ttu-id="cfd65-184">"Restringir quem pode acessar o conteúdo e substituir a política" — desmarque esta caixa de seleção para receber notificações sobre informações confidenciais sem impedir os usuários de acessarem as informações.</span><span class="sxs-lookup"><span data-stu-id="cfd65-184">‘Restrict who can access the content and override the policy’ — clear this checkbox to receive notifications about sensitive information without preventing users from access that information.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cfd65-185">Todos os locais incluem:</span><span class="sxs-lookup"><span data-stu-id="cfd65-185">All locations includes:</span></span>

- <span data-ttu-id="cfd65-186">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cfd65-186">SharePoint Online</span></span>

- <span data-ttu-id="cfd65-187">Contas do OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="cfd65-187">OneDrive for Business accounts</span></span>

- <span data-ttu-id="cfd65-188">Caixas de correio do Exchange</span><span class="sxs-lookup"><span data-stu-id="cfd65-188">Exchange mailboxes</span></span>

<span data-ttu-id="cfd65-189">Como a Pesquisa de Conteúdo, no momento, não permite testar tipos de informações confidenciais com email, considere criar políticas separadas para o Exchange com um subconjunto de tipos de informações confidenciais em cada política e monitore a distribuição dessas políticas.</span><span class="sxs-lookup"><span data-stu-id="cfd65-189">Because Content Search doesn’t currently let you test sensitive information types with email, consider creating separate policies for Exchange with a subset of sensitive information types in each policy and monitoring the rollout of these policies.</span></span>

## <a name="additional-protection-you-can-apply-to-protect-personal-data-in-office-365"></a><span data-ttu-id="cfd65-190">Proteção adicional que pode ser aplicada para proteger dados pessoais no Office 365</span><span class="sxs-lookup"><span data-stu-id="cfd65-190">Additional protection you can apply to protect personal data in Office 365</span></span>

<span data-ttu-id="cfd65-p112">Os tipos de informações confidenciais, os rótulos e as políticas de proteção contra perda de dados ajudam a identificar os documentos que contêm dados específicos e a aplicar proteção. No entanto, essas proteções dependem da configuração de permissões apropriadas de acesso a dados, usuários com contas que não sejam comprometidas e dispositivos saudáveis.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p112">Sensitive information types, labels, and data loss protection policies help you identify documents containing specific data and apply protection. However, these protections depend on appropriate permissions being set for access to data, users with accounts that aren't compromised, and devices that are healthy.</span></span>

<span data-ttu-id="cfd65-193">A ilustração a seguir detalha uma proteção adicional que pode ser aplicada para proteger o acesso a dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="cfd65-193">The following illustration details additional protection you can apply to protect access to personal data.</span></span>

![Proteção adicional para dar segurança ao acesso a dados pessoais](Media/Apply-protection-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="cfd65-195">Para maior acessibilidade, a tabela a seguir fornece as mesmas informações da ilustração.</span><span class="sxs-lookup"><span data-stu-id="cfd65-195">For accessibility, the following table provides the same information in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cfd65-196"><strong>Escopo de proteção</strong></span><span class="sxs-lookup"><span data-stu-id="cfd65-196"><strong>Scope of protection</strong></span></span></th>
<th align="left"><span data-ttu-id="cfd65-197"><strong>Funcionalidades</strong></span><span class="sxs-lookup"><span data-stu-id="cfd65-197"><strong>Capabilities</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="cfd65-198">Proteção no nível do email e documento (inclui emails em trânsito, mas, no momento, não inclui caixas de correio em repouso)</span><span class="sxs-lookup"><span data-stu-id="cfd65-198">Document and email-level protection (includes mail in transit, but not currently mailboxes at rest)</span></span></td>
<td align="left"><p><span data-ttu-id="cfd65-199">Tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="cfd65-199">Sensitive information types</span></span></p>
<p><span data-ttu-id="cfd65-200">Rótulos do Office.</span><span class="sxs-lookup"><span data-stu-id="cfd65-200">Office labels</span></span></p>
<p><span data-ttu-id="cfd65-201">Políticas de prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="cfd65-201">Data loss prevention policies</span></span></p>
<p><span data-ttu-id="cfd65-202">Criptografia de Mensagem do Office 365 para email</span><span class="sxs-lookup"><span data-stu-id="cfd65-202">Office 365 Message Encryption for email</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cfd65-203">Proteção no nível da biblioteca e site (inclui sites do SharePoint Online e OneDrive for Business)</span><span class="sxs-lookup"><span data-stu-id="cfd65-203">Site and library-level protection (includes SharePoint Online and OneDrive for Business sites)</span></span></td>
<td align="left"><p><span data-ttu-id="cfd65-204">Permissões para bibliotecas e sites do SharePoint Online e do OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="cfd65-204">Permissions for SharePoint Online and OneDrive for Business sites and libraries</span></span></p>
<p><span data-ttu-id="cfd65-205">Políticas de compartilhamento externo do SharePoint Online e OneDrive for Business (no nível do site)</span><span class="sxs-lookup"><span data-stu-id="cfd65-205">External sharing policies for SharePoint Online and OneDrive for Business (site-level)</span></span></p>
<p><span data-ttu-id="cfd65-206">Políticas de acesso de dispositivo no nível do site</span><span class="sxs-lookup"><span data-stu-id="cfd65-206">Site-level device access policies</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="cfd65-207">Proteção de acesso a serviços (inclui acesso a todos os serviços do Office 365)</span><span class="sxs-lookup"><span data-stu-id="cfd65-207">Service access protection (includes access to all services in Office 365)</span></span></td>
<td align="left"><p><span data-ttu-id="cfd65-208">Proteção à identidade e ao acesso a dispositivos no pacote Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="cfd65-208">Identity and device access protection in Enterprise Mobility + Security (EMS) suite</span></span></p>
<p><span data-ttu-id="cfd65-209">Gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="cfd65-209">Privileged access management</span></span></p>
<p><span data-ttu-id="cfd65-210">Recursos de segurança do Windows 10</span><span class="sxs-lookup"><span data-stu-id="cfd65-210">Windows 10 security capabilities</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cfd65-211">O restante deste artigo fornecerá mais informações sobre cada uma dessas categorias de proteção.</span><span class="sxs-lookup"><span data-stu-id="cfd65-211">The rest of this article provides more information on each of these categories of protection.</span></span>

### <a name="capabilities-that-are-ok-to-use-with-gdpr"></a><span data-ttu-id="cfd65-212">Funcionalidades que podem ser usadas com o GDPR</span><span class="sxs-lookup"><span data-stu-id="cfd65-212">Capabilities that are OK to use with GDPR</span></span>

<span data-ttu-id="cfd65-p113">Você pode usar as seguintes funcionalidades em um ambiente configurado para conformidade com o GDPR. Esses recursos não são necessários para a conformidade com o GDPR, mas podem ser usados sem afetar sua capacidade de descobrir, proteger, monitorar e informar sobre dados relacionados à conformidade do GDPR.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p113">You can use the following capabilities in an environment configured for GDPR compliance. These capabilities are not necessary for GDPR compliance, but they can be used without adversely affecting your ability to discover, protect, monitor, and report on data related to GDPR compliance.</span></span>

<span data-ttu-id="cfd65-p114">Chave de Cliente — Permite que os clientes forneçam e mantenham o controle sobre as chaves de criptografia que são usadas para criptografar dados em repouso no Office 365. Recomendado somente para clientes que tenham a necessidade regulatória de gerenciar suas próprias chaves de criptografia.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p114">Customer Key — Allows customers to provide and retain control over the encryption keys that are used to encrypt data at rest within Office 365. Recommended only for customers with a regulatory need to manage their own encryption keys.</span></span>

<span data-ttu-id="cfd65-p115">Sistema de Proteção de Dados do Cliente — O sistema de proteção de dados do cliente permite controlar como um engenheiro de suporte da Microsoft acessa os seus dados, se necessário, para corrigir um problema técnico com base em cada caso. Controle se deseja dar ao engenheiro de suporte acesso aos seus dados ou não. Um tempo de expiração é fornecido com cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p115">Customer Lockbox — Customer lockbox allows you to control how a Microsoft support engineer accesses your data, if needed, to fix a technical issue on a case by case basis. You can control whether to give the support engineer access to your data or not. An expiration time is provided with each request.</span></span>

## <a name="site-and-library-level-protection"></a><span data-ttu-id="cfd65-220">Proteção no nível da biblioteca e site</span><span class="sxs-lookup"><span data-stu-id="cfd65-220">Site and library-level protection</span></span>

### <a name="permissions-for-sharepoint-and-onedrive-for-business-libraries"></a><span data-ttu-id="cfd65-221">Permissões para bibliotecas e documentos do SharePoint e do OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="cfd65-221">Permissions for SharePoint and OneDrive for Business libraries</span></span>

<span data-ttu-id="cfd65-p116">Use permissões do SharePoint para fornecer ou restringir o acesso de usuário ao site ou conteúdo. Adicione usuários individuais ou grupos do Azure Active Directory aos grupos padrão do SharePoint. Ou crie um grupo personalizado para um controle mais refinado.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p116">Use permissions in SharePoint to provide or restrict user access to the site or its contents. Add individual users or Azure Active Directory groups to the default SharePoint groups. Or, create a custom group for finer-grain control.</span></span>

![Níveis de permissão de controle total para somente exibição](Media/Apply-protection-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="cfd65-p117">A ilustração apresenta os níveis de permissão, desde Controle total a Somente exibição. A tabela a seguir inclui as mesmas informações.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p117">The illustration plots permission levels from Full control to View Only. The following table includes the same information.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cfd65-228"><strong>Controle total</strong></span><span class="sxs-lookup"><span data-stu-id="cfd65-228"><strong>Full Control</strong></span></span></th>
<th align="left"><span data-ttu-id="cfd65-229"><strong>Design</strong></span><span class="sxs-lookup"><span data-stu-id="cfd65-229"><strong>Design</strong></span></span></th>
<th align="left"><span data-ttu-id="cfd65-230"><strong>Editar</strong></span><span class="sxs-lookup"><span data-stu-id="cfd65-230"><strong>Edit</strong></span></span></th>
<th align="left"><span data-ttu-id="cfd65-231"><strong>Colaboração</strong></span><span class="sxs-lookup"><span data-stu-id="cfd65-231"><strong>Contribute</strong></span></span></th>
<th align="left"><span data-ttu-id="cfd65-232"><strong>Leitura</strong></span><span class="sxs-lookup"><span data-stu-id="cfd65-232"><strong>Read</strong></span></span></th>
<th align="left"><span data-ttu-id="cfd65-233"><strong>Somente Exibição</strong></span><span class="sxs-lookup"><span data-stu-id="cfd65-233"><strong>View Only</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"></td>
<td align="left"><span data-ttu-id="cfd65-234">Contribuir + aprovar e personalizar</span><span class="sxs-lookup"><span data-stu-id="cfd65-234">Contribute + approve and customize</span></span></td>
<td align="left"><span data-ttu-id="cfd65-235">Contribuir + adicionar, editar e excluir listas (não apenas itens da lista)</span><span class="sxs-lookup"><span data-stu-id="cfd65-235">Contribute + add, edit, and delete lists (not just list items)</span></span></td>
<td align="left"><span data-ttu-id="cfd65-236">Exibir, adicionar, atualizar e excluir documentos e itens da lista.</span><span class="sxs-lookup"><span data-stu-id="cfd65-236">View, add, update, delete list items and documents</span></span></td>
<td align="left"><span data-ttu-id="cfd65-237">Exibir e baixar</span><span class="sxs-lookup"><span data-stu-id="cfd65-237">View and download</span></span></td>
<td align="left"><span data-ttu-id="cfd65-238">Exibir sem baixar</span><span class="sxs-lookup"><span data-stu-id="cfd65-238">View, no download</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cfd65-239">Mais informações:</span><span class="sxs-lookup"><span data-stu-id="cfd65-239">More information:</span></span>

-   [<span data-ttu-id="cfd65-240">Compreender os níveis de permissão no SharePoint</span><span class="sxs-lookup"><span data-stu-id="cfd65-240">Understanding permission levels in SharePoint</span></span>](https://support.office.com/en-US/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)

-   [<span data-ttu-id="cfd65-241">Compreender os grupos do SharePoint</span><span class="sxs-lookup"><span data-stu-id="cfd65-241">Understanding SharePoint groups</span></span>](https://support.office.com/en-US/article/Understanding-SharePoint-groups-94d9b261-161e-4ace-829e-eca1c8cd2eb8)

### <a name="external-sharing-policies-for-sharepoint-and-onedrive-for-business-libraries"></a><span data-ttu-id="cfd65-242">Políticas de compartilhamento externo para bibliotecas do SharePoint e OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="cfd65-242">External sharing policies for SharePoint and OneDrive for Business libraries</span></span>

<span data-ttu-id="cfd65-p118">Muitas organizações permitem o compartilhamento externo para dar suporte à colaboração. Descubra como suas configurações de locatário estão configuradas. Em seguida, revise as configurações de compartilhamento externo para sites que contêm dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p118">Many organizations allow external sharing to support collaboration. Find out how your tenant-wide settings are configured. Then review the external sharing settings for sites that contain personal data.</span></span>

<span data-ttu-id="cfd65-246">Um usuário externo é alguém de fora da sua organização que é convidado a acessar seus documentos e sites do SharePoint Online, mas não tem uma licença para sua assinatura do Microsoft Office 365 ou SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cfd65-246">An external user is someone outside of your organization who is invited to access your SharePoint Online sites and documents but doesn't have a license for your SharePoint Online or Microsoft Office 365 subscription.</span></span>

<span data-ttu-id="cfd65-247">As políticas de compartilhamento externo se aplicam ao SharePoint Online e OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="cfd65-247">External sharing policies apply to both SharePoint Online and OneDrive for Business.</span></span>

-   <span data-ttu-id="cfd65-248">É preciso ser um administrador do SharePoint Online para configurar as políticas de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="cfd65-248">You must be a SharePoint Online admin to configure sharing policies.</span></span>

-   <span data-ttu-id="cfd65-249">É preciso ser um Proprietário de site ou ter permissões de controle total para compartilhar um site ou documento com usuários externos.</span><span class="sxs-lookup"><span data-stu-id="cfd65-249">You must be a Site Owner or have full control permissions to share a site or document with external users.</span></span>

<span data-ttu-id="cfd65-250">A tabela a seguir resume os controles que você pode configurar.</span><span class="sxs-lookup"><span data-stu-id="cfd65-250">The following table summarizes the controls you can configure.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cfd65-251"><strong>Categoria de controle</strong></span><span class="sxs-lookup"><span data-stu-id="cfd65-251"><strong>Control category</strong></span></span></th>
<th align="left"><span data-ttu-id="cfd65-252"><strong>Opções</strong></span><span class="sxs-lookup"><span data-stu-id="cfd65-252"><strong>Options</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="cfd65-253">Tipo de compartilhamento</span><span class="sxs-lookup"><span data-stu-id="cfd65-253">Type of sharing</span></span></td>
<td align="left"><p><span data-ttu-id="cfd65-254">Não permitir o compartilhamento fora da sua organização (pode ser definido para conjuntos de sites individuais)</span><span class="sxs-lookup"><span data-stu-id="cfd65-254">Don’t allow sharing outside your organization (can be set for individual site collections)</span></span></p>
<p><span data-ttu-id="cfd65-255">Permitir o compartilhamento somente com usuários externos autenticados (permitir novos ou limitar aos já existentes, pode ser definido para conjuntos de sites individuais)\*</span><span class="sxs-lookup"><span data-stu-id="cfd65-255">Allow sharing to authenticated external users only (allow new or limit to existing, can be set for individual site collections)\*</span></span></p>
<p><span data-ttu-id="cfd65-256">Permitir o compartilhamento com usuários externos com um link de acesso anônimo (pode ser definido para conjuntos de sites individuais)</span><span class="sxs-lookup"><span data-stu-id="cfd65-256">Allow sharing to external users with an anonymous access link (can be set for individual site collections)</span></span></p>
<p><span data-ttu-id="cfd65-257">Limitar o compartilhamento externo usando domínios (lista permitir e negar)</span><span class="sxs-lookup"><span data-stu-id="cfd65-257">Limit external sharing using domains (allow and deny list)</span></span></p>
<p><span data-ttu-id="cfd65-258">Escolha o tipo de link padrão (anônimo, compartilhável na empresa ou restrito)</span><span class="sxs-lookup"><span data-stu-id="cfd65-258">Choose the default link type (anonymous, company shareable, or restricted)</span></span></p>
</td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cfd65-259">O que os usuários externos podem fazer</span><span class="sxs-lookup"><span data-stu-id="cfd65-259">What external users can do</span></span></td>
<td align="left"><p><span data-ttu-id="cfd65-260">Impedir que os usuários externos compartilhem arquivos, pastas, sites que eles não possuem</span><span class="sxs-lookup"><span data-stu-id="cfd65-260">Prevent external users from sharing files, folders, sites they don’t own</span></span></p>
<p><span data-ttu-id="cfd65-261">Exigir que os usuários externos aceitem convites de compartilhamento com a mesma conta para a qual o convite foi enviado</span><span class="sxs-lookup"><span data-stu-id="cfd65-261">Require external users to accept sharing invitations with the same account the invitation was sent to</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="cfd65-262">Notificações</span><span class="sxs-lookup"><span data-stu-id="cfd65-262">Notifications</span></span></td>
<td align="left"><p><span data-ttu-id="cfd65-p119">Disponível atualmente só no OneDrive for Business. Notificar os proprietários quando:</span><span class="sxs-lookup"><span data-stu-id="cfd65-p119">Currently only available in OneDrive for Business. Notify owners when:</span></span></p>
- <p><span data-ttu-id="cfd65-265">Os usuários convidarem usuários externos adicionais para os arquivos compartilhados</span><span class="sxs-lookup"><span data-stu-id="cfd65-265">Users invite additional external users to shared files</span></span></p>
- <p><span data-ttu-id="cfd65-266">Os usuários externos aceitarem convites para acessar os arquivos</span><span class="sxs-lookup"><span data-stu-id="cfd65-266">External users accept invitations to access files</span></span></p>
- <p><span data-ttu-id="cfd65-267">Um link de acesso anônimo for criado ou alterado</span><span class="sxs-lookup"><span data-stu-id="cfd65-267">An anonymous access link is created or changed</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cfd65-268">Mais informações:</span><span class="sxs-lookup"><span data-stu-id="cfd65-268">More information:</span></span>

-   [<span data-ttu-id="cfd65-269">Gerenciar compartilhamento externo para o ambiente do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cfd65-269">Manage external sharing for your SharePoint Online environment</span></span>](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&rs=en-US&ad=US)

-   [<span data-ttu-id="cfd65-270">Compartilhar sites ou documentos com pessoas de fora da organização</span><span class="sxs-lookup"><span data-stu-id="cfd65-270">Share sites or documents with people outside your organization</span></span>](https://support.office.com/en-US/article/Share-sites-or-documents-with-people-outside-your-organization-80e49744-e30f-44db-8d51-16661b1d4232)

### <a name="site-level-device-access-policies"></a><span data-ttu-id="cfd65-271">Políticas de acesso de dispositivo no nível do site</span><span class="sxs-lookup"><span data-stu-id="cfd65-271">Site-level device access policies</span></span>

<span data-ttu-id="cfd65-p120">O SharePoint Online e o OneDrive for Business permitem configurar as políticas de acesso a dispositivos no nível do site. Isso permite configurar maior proteção para sites com dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p120">SharePoint Online and OneDrive for Business let you configure device access policies at the site level. This lets you configure more protection for sites with sensitive data.</span></span>

<span data-ttu-id="cfd65-274">Se você configurar políticas de acesso de dispositivo no nível do site, certifique-se de coordená-las com as políticas a nível de locatário e também com as políticas de acesso configuradas no Azure Active Directory, Intune e Gerenciamento de Aplicativos do Intune.</span><span class="sxs-lookup"><span data-stu-id="cfd65-274">If you configure site-level device access policies, be sure to coordinate these with tenant-level policies and also with access policies that are configured in Azure Active Directory, Intune, and Intune App Management.</span></span>

<span data-ttu-id="cfd65-p121">As políticas de acesso de dispositivos do SharePoint e do OneDrive for Business exigem políticas com suporte no Azure Active Directory e no Microsoft Intune, dependendo do cenário que está sendo implementado. A tabela a seguir resume os objetivos que podem ser alcançados com as políticas de acesso de dispositivos e indica quais produtos exigem políticas com suporte.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p121">Device access policies for SharePoint and OneDrive for Business require supporting policies in Azure Active Directory and Microsoft Intune depending on the scenario you're implementing. The following table summarizes objectives you can achieve with device access policies and indicates which products require supporting policies.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="cfd65-277">Só permitir o acesso de locais de endereço IP específicos</span><span class="sxs-lookup"><span data-stu-id="cfd65-277">Only allow access from specific IP address locations</span></span></th>
<th align="left"><span data-ttu-id="cfd65-278">Impedir que os usuários baixem arquivos para dispositivos que não ingressaram no domínio</span><span class="sxs-lookup"><span data-stu-id="cfd65-278">Prevent users from downloading files to non-domain joined devices</span></span></th>
<th align="left"><span data-ttu-id="cfd65-279">Bloquear o acesso em dispositivos que não ingressaram no domínio</span><span class="sxs-lookup"><span data-stu-id="cfd65-279">Block access on non-domain joined devices</span></span></th>
<th align="left"><span data-ttu-id="cfd65-280">Impedir que os usuários baixem arquivos para dispositivos que não estão em conformidade</span><span class="sxs-lookup"><span data-stu-id="cfd65-280">Prevent users from downloading files to non-compliant devices</span></span></th>
<th align="left"><span data-ttu-id="cfd65-281">Bloquear o acesso a dispositivos que não estão em conformidade</span><span class="sxs-lookup"><span data-stu-id="cfd65-281">Block access on non-compliant devices</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="cfd65-282">Centro de administração do SharePoint</span><span class="sxs-lookup"><span data-stu-id="cfd65-282">SharePoint admin center</span></span></td>
<td align="left"><span data-ttu-id="cfd65-283">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-283">Yes</span></span></td>
<td align="left"><span data-ttu-id="cfd65-284">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-284">Yes</span></span></td>
<td align="left"><span data-ttu-id="cfd65-285">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-285">Yes</span></span></td>
<td align="left"><span data-ttu-id="cfd65-286">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-286">Yes</span></span></td>
<td align="left"><span data-ttu-id="cfd65-287">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-287">Yes</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cfd65-288">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="cfd65-288">Azure Active Directory</span></span></td>
<td align="left"></td>
<td align="left"><span data-ttu-id="cfd65-289">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-289">Yes</span></span></td>
<td align="left"><span data-ttu-id="cfd65-290">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-290">Yes</span></span></td>
<td align="left"><span data-ttu-id="cfd65-291">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-291">Yes</span></span></td>
<td align="left"><span data-ttu-id="cfd65-292">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-292">Yes</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="cfd65-293">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="cfd65-293">Microsoft Intune</span></span></td>
<td align="left"></td>
<td align="left"></td>
<td align="left"></td>
<td align="left"><span data-ttu-id="cfd65-294">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-294">Yes</span></span></td>
<td align="left"><span data-ttu-id="cfd65-295">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-295">Yes</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cfd65-296">Mais informações: [Centro de administração do SharePoint Online: controlar o acesso de dispositivos não gerenciados](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="cfd65-296">More information: [SharePoint Online admin center: Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&rs=en-US&ad=US).</span></span>

## <a name="service-access-protection-for-identities-and-devices"></a><span data-ttu-id="cfd65-297">Proteção de acesso a serviços de identidades e dispositivos</span><span class="sxs-lookup"><span data-stu-id="cfd65-297">Service access protection for identities and devices</span></span>

<span data-ttu-id="cfd65-p122">A Microsoft recomenda configurar a proteção de identidades e dispositivos que acessam o serviço. Seus esforços para proteger o acesso aos serviços do Office 365 também podem ser usados para proteger outros serviços de SaaS, serviços de PaaS e até aplicativos em outros provedores de nuvem.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p122">Microsoft recommends you configure protection for identities and devices that access the service. The work you put into protecting access to Office 365 services can also be used to protect access to other SaaS services, PaaS services, and even apps in other cloud providers.</span></span>

<span data-ttu-id="cfd65-300">A proteção de acesso de identidades e dispositivos oferece um parâmetro de proteção para garantir que as identidades não sejam comprometidas, que os dispositivos estejam em segurança e que os dados da organização que são acessados nos dispositivos estejam isolados e protegidos.</span><span class="sxs-lookup"><span data-stu-id="cfd65-300">Access protection for identities and devices provides a baseline of protection to ensure that identities aren't compromised, devices are safe, and organization data that is accessed on devices is isolated and protected.</span></span>

<span data-ttu-id="cfd65-301">Como ponto de partida para as orientações de configuração e recomendações, confira [Diretrizes de segurança da Microsoft para campanhas políticas, organizações sem fins lucrativos e outras organizações Agile](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).</span><span class="sxs-lookup"><span data-stu-id="cfd65-301">For starting point recommendations and configuration guidance, see [Microsoft security guidance for political campaigns, nonprofits, and other agile organizations](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).</span></span>

<span data-ttu-id="cfd65-302">Para ambientes com identidade híbrida com o AD FS, confira [Recomendações de configurações e políticas de segurança](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).</span><span class="sxs-lookup"><span data-stu-id="cfd65-302">For hybrid identity environments with AD FS, see [Recommended security policies and configurations](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).</span></span>

<span data-ttu-id="cfd65-p123">A ilustração a seguir descreve como os serviços em nuvem (SaaS, PaaS), tipos de conta (contas de domínio de locatário vs. contas B2B) e funcionalidades de recursos de acesso estão relacionados. É importante observar quais funcionalidades podem ser usadas com contas B2B.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p123">The following illustration describes how cloud services (SaaS, PaaS), account types (tenant domain accounts vs. B2B accounts), and service access capabilities relate. It’s important to note which capabilities can be used with B2B accounts.</span></span>

![Serviços em nuvem, tipos de conta e funcionalidades de acesso](Media/Apply-protection-to-personal-data-in-Office-365-image4.png)

<span data-ttu-id="cfd65-306">Para fins de acessibilidade, o restante desta seção descreverá esta ilustração.</span><span class="sxs-lookup"><span data-stu-id="cfd65-306">For accessibility, the rest of this section describes this illustration.</span></span>

### <a name="cloud-services"></a><span data-ttu-id="cfd65-307">Serviços em nuvem</span><span class="sxs-lookup"><span data-stu-id="cfd65-307">Cloud services</span></span>

<span data-ttu-id="cfd65-p124">O Azure Active Directory fornece acesso de identidade para qualquer serviço em nuvem, incluindo de outros provedores diferentes da Microsoft, como o Amazon Web Services. A ilustração mostra o Office 365, "Outro aplicativo de SaaS" e "aplicativo de PaaS". Setas apontam do Azure Active Directory para cada um desses serviços, mostrando que o Active Directory do Azure pode ser usado para autenticação em todos esses tipos de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p124">Azure Active Directory provides identity access to any cloud service, including non-Microsoft providers such as Amazon Web Services. The illustration shows Office 365, “Other SaaS app,” and “PaaS app.” Arrows point from Azure Active Directory to each of these services, showing that Azure Active Directory can be used for authentication to all of these app types.</span></span>

### <a name="types-of-accounts"></a><span data-ttu-id="cfd65-311">Tipos de contas</span><span class="sxs-lookup"><span data-stu-id="cfd65-311">Types of accounts</span></span>

<span data-ttu-id="cfd65-p125">Contas de domínio do locatário são contas que você adiciona ao seu locatário e gerencia diretamente. Contas B2B são para usuários de fora da sua organização que você convida para colaborar. Estas podem ser outras contas do Office 365, contas de outra organização ou contas de cliente (como Gmail). A ilustração mostra ambos os tipos de conta no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p125">Tenant domain accounts are account you add to your tenant and manage directly. B2B accounts are accounts for users outside your organization you invite to collaborate with. These can be other Office 365 accounts, other organization accounts, or consumer accounts (such as Gmail). The illustration shows both account types within Azure Active Directory.</span></span>

### <a name="capabilities"></a><span data-ttu-id="cfd65-316">Funcionalidades</span><span class="sxs-lookup"><span data-stu-id="cfd65-316">Capabilities</span></span>

<span data-ttu-id="cfd65-p126">As funcionalidades na tabela a seguir protege identidades e dispositivos. A tabela indica quais funcionalidades também podem ser usadas com contas B2B, de modo similar à ilustração.</span><span class="sxs-lookup"><span data-stu-id="cfd65-p126">The capabilities in the following table protect identities and devices. The table indicates which capabilities can also be used with B2B accounts, similar to the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cfd65-319"><strong>Funcionalidade</strong></span><span class="sxs-lookup"><span data-stu-id="cfd65-319"><strong>Capability</strong></span></span></th>
<th align="left"><span data-ttu-id="cfd65-320"><strong>Funciona com contas de domínio do locatário</strong></span><span class="sxs-lookup"><span data-stu-id="cfd65-320"><strong>Works with tenant domain accounts</strong></span></span></th>
<th align="left"><span data-ttu-id="cfd65-321"><strong>Funciona com contas B2B do Azure (sem licenciamento adicional)</strong></span><span class="sxs-lookup"><span data-stu-id="cfd65-321"><strong>Works with Azure B2B accounts (without additional licensing)</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="cfd65-322">Autenticação multifatorial e acesso condicional</span><span class="sxs-lookup"><span data-stu-id="cfd65-322">Multi-factor authentication and conditional access</span></span></td>
<td align="left"><span data-ttu-id="cfd65-323">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-323">Yes</span></span></td>
<td align="left"><span data-ttu-id="cfd65-324">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-324">Yes</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cfd65-325">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="cfd65-325">Azure AD Identity Protection</span></span></td>
<td align="left"><span data-ttu-id="cfd65-326">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-326">Yes</span></span></td>
<td align="left"><span data-ttu-id="cfd65-327">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-327">Yes</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="cfd65-328">Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="cfd65-328">Azure AD Privileged Identity Management</span></span></td>
<td align="left"><span data-ttu-id="cfd65-329">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-329">Yes</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cfd65-330">Gerenciamento de Aplicativos Móveis (MAM)</span><span class="sxs-lookup"><span data-stu-id="cfd65-330">Mobile Application Management (MAM)</span></span></td>
<td align="left"><span data-ttu-id="cfd65-331">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-331">Yes</span></span></td>
<td align="left"></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="cfd65-332">Gerenciamento e registro de dispositivos</span><span class="sxs-lookup"><span data-stu-id="cfd65-332">Device enrollment and management</span></span></td>
<td align="left"><span data-ttu-id="cfd65-333">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-333">Yes</span></span></td>
<td align="left"><span data-ttu-id="cfd65-334">Apenas uma organização pode gerenciar um dispositivo</span><span class="sxs-lookup"><span data-stu-id="cfd65-334">Only one organization can manage a device</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cfd65-335">As funcionalidades de segurança do Windows 10 (acesso condicional com base na conformidade do dispositivo requer o gerenciamento de dispositivos)</span><span class="sxs-lookup"><span data-stu-id="cfd65-335">Windows 10 security capabilities (conditional access based on device compliance requires device management)</span></span></td>
<td align="left"><span data-ttu-id="cfd65-336">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-336">Yes</span></span></td>
<td align="left"><span data-ttu-id="cfd65-337">Sim</span><span class="sxs-lookup"><span data-stu-id="cfd65-337">Yes</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cfd65-338">Adicione licenças a contas B2B para oferecer a esses usuários funcionalidades adicionais, se necessário, para proteger o acesso a dados pessoais no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="cfd65-338">You can add licenses to B2B accounts to give these users additional capabilities, if needed, to protect access to personal data in your environment.</span></span>
