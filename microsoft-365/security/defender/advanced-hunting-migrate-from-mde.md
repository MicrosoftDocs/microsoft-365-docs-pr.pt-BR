---
title: Migrar consultas de busca avançadas do Microsoft Defender para o Ponto de Extremidade
description: Saiba como ajustar suas consultas do Microsoft Defender para Pontos de Extremidade para que você possa usá-las no Microsoft 365 Defender
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, Microsoft Defender para Ponto de Extremidade, pesquisa, consulta, telemetria, detecções personalizadas, esquema, kusto, mapeamento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ba6f84f9f08d0635dab6ac65eaa697b8e0e73df7
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470683"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="ac120-104">Migrar consultas de busca avançadas do Microsoft Defender para o Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ac120-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ac120-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ac120-105">**Applies to:**</span></span>
- <span data-ttu-id="ac120-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac120-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ac120-107">Mova seus fluxos de trabalho de busca avançados do Microsoft Defender para o Ponto de Extremidade para procurar proativamente ameaças usando um conjunto mais amplo de dados.</span><span class="sxs-lookup"><span data-stu-id="ac120-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="ac120-108">No Microsoft 365 Defender, você tem acesso aos dados de outras soluções Microsoft 365 segurança, incluindo:</span><span class="sxs-lookup"><span data-stu-id="ac120-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="ac120-109">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ac120-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="ac120-110">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="ac120-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="ac120-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ac120-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="ac120-112">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="ac120-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="ac120-113">A maioria dos clientes do Microsoft Defender para Ponto de Extremidade pode [usar o Microsoft 365 Defender sem licenças adicionais.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="ac120-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="ac120-114">Para começar a fazer a transição dos fluxos de trabalho de busca avançada do Defender para o Ponto de Extremidade, a [Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="ac120-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

<span data-ttu-id="ac120-115">Você pode fazer a transição sem afetar seus fluxos de trabalho existentes do Defender para Pontos de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="ac120-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="ac120-116">As consultas salvas permanecem intactas e as regras de detecção personalizadas continuam a ser executados e geram alertas.</span><span class="sxs-lookup"><span data-stu-id="ac120-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="ac120-117">No entanto, eles estarão visíveis no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ac120-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="ac120-118">Tabelas de esquema somente Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac120-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="ac120-119">O [Microsoft 365 esquema](advanced-hunting-schema-tables.md) de busca avançada do Defender fornece tabelas adicionais que contêm dados de várias Microsoft 365 de segurança.</span><span class="sxs-lookup"><span data-stu-id="ac120-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="ac120-120">As tabelas a seguir estão disponíveis apenas no Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="ac120-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="ac120-121">Nome da tabela</span><span class="sxs-lookup"><span data-stu-id="ac120-121">Table name</span></span> | <span data-ttu-id="ac120-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="ac120-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="ac120-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="ac120-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="ac120-124">Arquivos, endereços IP, URLs, usuários ou dispositivos associados a alertas</span><span class="sxs-lookup"><span data-stu-id="ac120-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="ac120-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="ac120-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="ac120-126">Alertas do Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Office 365, Microsoft Cloud App Security e Microsoft Defender para Identidade, incluindo informações de gravidade e categorias de ameaças</span><span class="sxs-lookup"><span data-stu-id="ac120-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="ac120-127">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="ac120-127">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="ac120-128">Informações sobre arquivos anexados a emails</span><span class="sxs-lookup"><span data-stu-id="ac120-128">Information about files attached to emails</span></span> |
| [<span data-ttu-id="ac120-129">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="ac120-129">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="ac120-130">Microsoft 365 de email, incluindo eventos de entrega de email e bloqueio</span><span class="sxs-lookup"><span data-stu-id="ac120-130">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="ac120-131">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="ac120-131">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="ac120-132">Eventos de segurança que ocorrem após a entrega, Microsoft 365 entregar os emails à caixa de correio do destinatário</span><span class="sxs-lookup"><span data-stu-id="ac120-132">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="ac120-133">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="ac120-133">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="ac120-134">Informações sobre URLs em emails</span><span class="sxs-lookup"><span data-stu-id="ac120-134">Information about URLs on emails</span></span> |
| [<span data-ttu-id="ac120-135">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="ac120-135">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="ac120-136">Eventos envolvendo um controlador de domínio local executando o Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="ac120-136">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="ac120-137">Esta tabela abrange um intervalo de eventos relacionados à identidade e eventos do sistema no controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="ac120-137">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="ac120-138">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="ac120-138">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="ac120-139">Informações da conta de várias fontes, incluindo Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ac120-139">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="ac120-140">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="ac120-140">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="ac120-141">Eventos de autenticação no Active Directory e serviços online da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ac120-141">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="ac120-142">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="ac120-142">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="ac120-143">Consultas para objetos do Active Directory, como usuários, grupos, dispositivos e domínios</span><span class="sxs-lookup"><span data-stu-id="ac120-143">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

>[!IMPORTANT]
> <span data-ttu-id="ac120-144">Consultas e detecções personalizadas que usam tabelas de esquema disponíveis apenas no Microsoft 365 Defender só podem ser exibidas no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ac120-144">Queries and custom detections which use schema tables that are only available in Microsoft 365 Defender can only be viewed in Microsoft 365 Defender.</span></span>

## <a name="map-devicealertevents-table"></a><span data-ttu-id="ac120-145">Tabela Mapear DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="ac120-145">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="ac120-146">As `AlertInfo` `AlertEvidence` tabelas e substituem `DeviceAlertEvents` a tabela no esquema do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="ac120-146">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="ac120-147">Além dos dados sobre alertas de dispositivo, essas duas tabelas incluem dados sobre alertas para identidades, aplicativos e emails.</span><span class="sxs-lookup"><span data-stu-id="ac120-147">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="ac120-148">Use a tabela a seguir para verificar como `DeviceAlertEvents` as colunas são mapeadas para colunas `AlertInfo` nas `AlertEvidence` tabelas e.</span><span class="sxs-lookup"><span data-stu-id="ac120-148">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="ac120-149">Além das colunas na tabela a seguir, a tabela inclui muitas outras colunas que fornecem uma imagem mais holística de `AlertEvidence` alertas de várias fontes.</span><span class="sxs-lookup"><span data-stu-id="ac120-149">In addition to the columns in the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="ac120-150">Consulte todas as colunas AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="ac120-150">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="ac120-151">Coluna DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="ac120-151">DeviceAlertEvents column</span></span> | <span data-ttu-id="ac120-152">Onde encontrar os mesmos dados no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac120-152">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="ac120-153">`AlertInfo` e  `AlertEvidence` tabelas</span><span class="sxs-lookup"><span data-stu-id="ac120-153">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="ac120-154">`AlertInfo` e  `AlertEvidence` tabelas</span><span class="sxs-lookup"><span data-stu-id="ac120-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="ac120-155">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="ac120-155">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="ac120-156">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="ac120-156">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="ac120-157">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="ac120-157">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="ac120-158">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="ac120-158">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="ac120-159">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="ac120-159">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="ac120-160">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="ac120-160">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="ac120-161">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="ac120-161">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="ac120-162">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="ac120-162">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="ac120-163">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="ac120-163">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="ac120-164">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="ac120-164">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="ac120-165">Esta coluna normalmente é usada no Microsoft Defender para Endpoint para localizar registros relacionados em outras tabelas.</span><span class="sxs-lookup"><span data-stu-id="ac120-165">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="ac120-166">No Microsoft 365 Defender, você pode obter dados relacionados diretamente da `AlertEvidence` tabela.</span><span class="sxs-lookup"><span data-stu-id="ac120-166">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="ac120-167">Esta coluna geralmente é usada no Microsoft Defender para Endpoint para obter informações adicionais de eventos em outras tabelas.</span><span class="sxs-lookup"><span data-stu-id="ac120-167">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="ac120-168">No Microsoft 365 Defender, você pode obter dados relacionados diretamente da `AlertEvidence` tabela.</span><span class="sxs-lookup"><span data-stu-id="ac120-168">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="ac120-169">Ajustar consultas existentes do Microsoft Defender para Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ac120-169">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="ac120-170">As consultas do Microsoft Defender para Ponto de Extremidade funcionarão como estão, a menos que faça referência à `DeviceAlertEvents` tabela.</span><span class="sxs-lookup"><span data-stu-id="ac120-170">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="ac120-171">Para usar essas consultas no Microsoft 365 Defender, aplique estas alterações:</span><span class="sxs-lookup"><span data-stu-id="ac120-171">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="ac120-172">Substitua `DeviceAlertEvents` por `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="ac120-172">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="ac120-173">Participe e `AlertInfo` as `AlertEvidence` tabelas em `AlertId` para obter dados equivalentes.</span><span class="sxs-lookup"><span data-stu-id="ac120-173">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="ac120-174">Consulta original</span><span class="sxs-lookup"><span data-stu-id="ac120-174">Original query</span></span>
<span data-ttu-id="ac120-175">A consulta a seguir usa o Microsoft Defender para Ponto de Extremidade para `DeviceAlertEvents` obter os alertas que envolvem _powershell.exe_:</span><span class="sxs-lookup"><span data-stu-id="ac120-175">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="ac120-176">Consulta modificada</span><span class="sxs-lookup"><span data-stu-id="ac120-176">Modified query</span></span>
<span data-ttu-id="ac120-177">A consulta a seguir foi ajustada para uso no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ac120-177">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="ac120-178">Em vez de verificar o nome do arquivo diretamente de , ele junta e verifica o nome do arquivo `DeviceAlertEvents` `AlertEvidence` nessa tabela.</span><span class="sxs-lookup"><span data-stu-id="ac120-178">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="ac120-179">Migrar regras de detecção personalizadas</span><span class="sxs-lookup"><span data-stu-id="ac120-179">Migrate custom detection rules</span></span>

<span data-ttu-id="ac120-180">Quando as regras do Microsoft Defender para Ponto de Extremidade são editadas no Microsoft 365 Defender, elas continuam a funcionar como antes se a consulta resultante olhar apenas para tabelas de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ac120-180">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> 

<span data-ttu-id="ac120-181">Por exemplo, alertas gerados por regras de detecção personalizadas que consultam apenas tabelas de dispositivo continuarão a ser entregues ao SIEM e gerarão notificações de email, dependendo de como você configurou isso no Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="ac120-181">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="ac120-182">Quaisquer regras de supressão existentes no Defender para Ponto de Extremidade também continuarão a ser aplicadas.</span><span class="sxs-lookup"><span data-stu-id="ac120-182">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="ac120-183">Depois de editar uma regra do Defender para Ponto de Extremidade para que ela consulte as tabelas de identidade e email, que estão disponíveis apenas no Microsoft 365 Defender, a regra é movida automaticamente para o Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ac120-183">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="ac120-184">Alertas gerados pela regra migrada:</span><span class="sxs-lookup"><span data-stu-id="ac120-184">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="ac120-185">Não estão mais visíveis no portal defender para ponto de extremidade (Central de Segurança do Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="ac120-185">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="ac120-186">Pare de ser entregue ao SIEM ou gere notificações por email.</span><span class="sxs-lookup"><span data-stu-id="ac120-186">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="ac120-187">Para resolver essa alteração, configure as notificações por meio Microsoft 365 Defender para obter os alertas.</span><span class="sxs-lookup"><span data-stu-id="ac120-187">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="ac120-188">Você pode usar a [API Microsoft 365 Defender](api-incident.md) para receber notificações para alertas de detecção do cliente ou incidentes relacionados.</span><span class="sxs-lookup"><span data-stu-id="ac120-188">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="ac120-189">Não será suprimido pelo Microsoft Defender para regras de supressão de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ac120-189">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="ac120-190">Para evitar que alertas são gerados para determinados usuários, dispositivos ou caixas de correio, modifique as consultas correspondentes para excluir essas entidades explicitamente.</span><span class="sxs-lookup"><span data-stu-id="ac120-190">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="ac120-191">Se você editar uma regra dessa forma, será solicitado a confirmar antes que essas alterações sejam aplicadas.</span><span class="sxs-lookup"><span data-stu-id="ac120-191">If you edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="ac120-192">Novos alertas gerados por regras de detecção personalizadas no Microsoft 365 portal do Defender são exibidos em uma página de alerta que fornece as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="ac120-192">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="ac120-193">Título e descrição do alerta</span><span class="sxs-lookup"><span data-stu-id="ac120-193">Alert title and description</span></span> 
- <span data-ttu-id="ac120-194">Ativos afetados</span><span class="sxs-lookup"><span data-stu-id="ac120-194">Impacted assets</span></span>
- <span data-ttu-id="ac120-195">Ações tomadas em resposta ao alerta</span><span class="sxs-lookup"><span data-stu-id="ac120-195">Actions taken in response to the alert</span></span>
- <span data-ttu-id="ac120-196">Resultados da consulta que dispararam o alerta</span><span class="sxs-lookup"><span data-stu-id="ac120-196">Query results that triggered the alert</span></span> 
- <span data-ttu-id="ac120-197">Informações sobre a regra de detecção personalizada</span><span class="sxs-lookup"><span data-stu-id="ac120-197">Information on the custom detection rule</span></span> 
 
> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac120-198">![Imagem da nova página de alerta](../../media/new-alert-page.png)</span><span class="sxs-lookup"><span data-stu-id="ac120-198">![Image of new alert page](../../media/new-alert-page.png)</span></span>

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="ac120-199">Gravar consultas sem DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="ac120-199">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="ac120-200">No esquema Microsoft 365 Defender, as tabelas e são fornecidas para acomodar o conjunto diversificado de informações que acompanham `AlertInfo` `AlertEvidence` alertas de várias fontes.</span><span class="sxs-lookup"><span data-stu-id="ac120-200">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="ac120-201">Para obter as mesmas informações de alerta que você usou para obter da tabela no esquema do Microsoft Defender para Ponto de Extremidade, filtre a tabela e, em seguida, participe de cada ID exclusiva com a tabela, que fornece informações detalhadas sobre eventos e `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` entidades.</span><span class="sxs-lookup"><span data-stu-id="ac120-201">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="ac120-202">Consulte a consulta de exemplo abaixo:</span><span class="sxs-lookup"><span data-stu-id="ac120-202">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="ac120-203">Essa consulta gera muito mais colunas do que `DeviceAlertEvents` no esquema do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="ac120-203">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="ac120-204">Para manter os resultados gerenciáveis, use para obter apenas as colunas em `project` que você está interessado.</span><span class="sxs-lookup"><span data-stu-id="ac120-204">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="ac120-205">O exemplo abaixo projeta colunas em que você pode estar interessado quando a investigação detectou a atividade do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ac120-205">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="ac120-206">Se quiser filtrar entidades específicas envolvidas nos alertas, especifique o tipo de entidade e o valor que você gostaria `EntityType` de filtrar.</span><span class="sxs-lookup"><span data-stu-id="ac120-206">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="ac120-207">O exemplo a seguir procura um endereço IP específico:</span><span class="sxs-lookup"><span data-stu-id="ac120-207">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="ac120-208">Confira também</span><span class="sxs-lookup"><span data-stu-id="ac120-208">See also</span></span>
- [<span data-ttu-id="ac120-209">Ativar o Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac120-209">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ac120-210">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="ac120-210">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ac120-211">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="ac120-211">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ac120-212">Busca avançada no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ac120-212">Advanced hunting in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)