---
title: Migrar consultas de busca avançada do Microsoft Defender para o Ponto de Extremidade
description: Saiba como ajustar o Microsoft Defender para consultas de ponto de extremidade para que você possa usá-las no Microsoft 365 Defender
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, microsoft defender atp, mdatp, pesquisa, consulta, telemetria, detecções personalizadas, esquema, kusto, microsoft 365, mapeamento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 4e008488bdd733c9a7ce5b418fb838e0fe880d9d
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080730"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="49480-104">Migrar consultas de busca avançada do Microsoft Defender para o Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="49480-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="49480-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="49480-105">**Applies to:**</span></span>
- <span data-ttu-id="49480-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49480-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="49480-107">Mova seus fluxos de trabalho de busca avançada do Microsoft Defender para o Ponto de Extremidade para procurar proativamente por ameaças usando um conjunto mais amplo de dados.</span><span class="sxs-lookup"><span data-stu-id="49480-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="49480-108">No Microsoft 365 Defender, você tem acesso aos dados de outras soluções de segurança do Microsoft 365, incluindo:</span><span class="sxs-lookup"><span data-stu-id="49480-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="49480-109">Proteção Avançada contra Ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="49480-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="49480-110">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="49480-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="49480-111">Segurança no aplicativo na nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="49480-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="49480-112">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="49480-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="49480-113">A maioria dos clientes do Microsoft Defender para Pontos de Extremidade [pode usar o Microsoft 365 Defender sem licenças adicionais.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="49480-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="49480-114">Para começar a fazer a transição de seus fluxos de trabalho de busca avançada do Defender para o Ponto de Extremidade, [a ligue o Microsoft 365 Defender.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="49480-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="49480-115">Você pode fazer a transição sem afetar o Defender existente para fluxos de trabalho do Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="49480-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="49480-116">As consultas salvas permanecem intactas, e as regras de detecção personalizadas continuam a ser executados e geram alertas.</span><span class="sxs-lookup"><span data-stu-id="49480-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="49480-117">No entanto, eles estarão visíveis no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="49480-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="49480-118">Tabelas de esquema somente no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49480-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="49480-119">O [esquema de busca avançada do Microsoft 365 Defender](advanced-hunting-schema-tables.md) fornece tabelas adicionais contendo dados de várias soluções de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="49480-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="49480-120">As tabelas a seguir estão disponíveis apenas no Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="49480-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="49480-121">Nome da tabela</span><span class="sxs-lookup"><span data-stu-id="49480-121">Table name</span></span> | <span data-ttu-id="49480-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="49480-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="49480-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="49480-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="49480-124">Arquivos, endereços IP, URLs, usuários ou dispositivos associados a alertas</span><span class="sxs-lookup"><span data-stu-id="49480-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="49480-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="49480-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="49480-126">Alertas do Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Office 365, Microsoft Cloud App Security e Microsoft Defender para Identidade, incluindo informações de gravidade e categorias de ameaças</span><span class="sxs-lookup"><span data-stu-id="49480-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="49480-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="49480-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="49480-128">Atividades relacionadas a arquivos em aplicativos e serviços em nuvem</span><span class="sxs-lookup"><span data-stu-id="49480-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="49480-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="49480-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="49480-130">Informações sobre arquivos anexados a emails</span><span class="sxs-lookup"><span data-stu-id="49480-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="49480-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="49480-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="49480-132">Eventos de email do Microsoft 365, incluindo eventos de entrega e bloqueio de email</span><span class="sxs-lookup"><span data-stu-id="49480-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="49480-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="49480-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="49480-134">Eventos de segurança que ocorrem após a entrega, depois que o Microsoft 365 entrega os emails para a caixa de correio do destinatário</span><span class="sxs-lookup"><span data-stu-id="49480-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="49480-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="49480-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="49480-136">Informações sobre URLs em emails</span><span class="sxs-lookup"><span data-stu-id="49480-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="49480-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="49480-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="49480-138">Eventos envolvendo um controlador de domínio local executando o Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="49480-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="49480-139">Esta tabela abrange uma variedade de eventos relacionados à identidade e eventos do sistema no controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="49480-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="49480-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="49480-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="49480-141">Informações da conta de várias fontes, incluindo o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="49480-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="49480-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="49480-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="49480-143">Eventos de autenticação no Active Directory e nos serviços online da Microsoft</span><span class="sxs-lookup"><span data-stu-id="49480-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="49480-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="49480-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="49480-145">Consultas para objetos do Active Directory, como usuários, grupos, dispositivos e domínios</span><span class="sxs-lookup"><span data-stu-id="49480-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="49480-146">Tabela Mapear DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="49480-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="49480-147">The `AlertInfo` and tables replace the table in the Microsoft Defender for `AlertEvidence` `DeviceAlertEvents` Endpoint schema.</span><span class="sxs-lookup"><span data-stu-id="49480-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="49480-148">Além dos dados sobre alertas de dispositivo, essas duas tabelas incluem dados sobre alertas de identidades, aplicativos e emails.</span><span class="sxs-lookup"><span data-stu-id="49480-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="49480-149">Use a tabela a seguir para verificar como `DeviceAlertEvents` as colunas são mapeadas para colunas nas `AlertInfo` tabelas e `AlertEvidence` tabelas.</span><span class="sxs-lookup"><span data-stu-id="49480-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="49480-150">Além das colunas da tabela a seguir, a tabela inclui muitas outras colunas que fornecem uma imagem mais holística dos `AlertEvidence` alertas de várias fontes.</span><span class="sxs-lookup"><span data-stu-id="49480-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="49480-151">Ver todas as colunas AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="49480-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="49480-152">Coluna DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="49480-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="49480-153">Onde encontrar os mesmos dados no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49480-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="49480-154">`AlertInfo` e  `AlertEvidence` tabelas</span><span class="sxs-lookup"><span data-stu-id="49480-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="49480-155">`AlertInfo` e  `AlertEvidence` tabelas</span><span class="sxs-lookup"><span data-stu-id="49480-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="49480-156">`AlertEvidence` tabela</span><span class="sxs-lookup"><span data-stu-id="49480-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="49480-157">`AlertEvidence` tabela</span><span class="sxs-lookup"><span data-stu-id="49480-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="49480-158">`AlertInfo` tabela</span><span class="sxs-lookup"><span data-stu-id="49480-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="49480-159">`AlertInfo` tabela</span><span class="sxs-lookup"><span data-stu-id="49480-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="49480-160">`AlertInfo` tabela</span><span class="sxs-lookup"><span data-stu-id="49480-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="49480-161">`AlertEvidence` tabela</span><span class="sxs-lookup"><span data-stu-id="49480-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="49480-162">`AlertEvidence` tabela</span><span class="sxs-lookup"><span data-stu-id="49480-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="49480-163">`AlertEvidence` tabela</span><span class="sxs-lookup"><span data-stu-id="49480-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="49480-164">`AlertEvidence` tabela</span><span class="sxs-lookup"><span data-stu-id="49480-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="49480-165">`AlertInfo` tabela</span><span class="sxs-lookup"><span data-stu-id="49480-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="49480-166">Essa coluna é normalmente usada no Microsoft Defender para o Ponto de Extremidade para localizar registros relacionados em outras tabelas.</span><span class="sxs-lookup"><span data-stu-id="49480-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="49480-167">No Microsoft 365 Defender, você pode obter dados relacionados diretamente da `AlertEvidence` tabela.</span><span class="sxs-lookup"><span data-stu-id="49480-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="49480-168">Essa coluna é normalmente usada no Microsoft Defender para o Ponto de Extremidade para obter informações adicionais sobre o evento em outras tabelas.</span><span class="sxs-lookup"><span data-stu-id="49480-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="49480-169">No Microsoft 365 Defender, você pode obter dados relacionados diretamente da `AlertEvidence` tabela.</span><span class="sxs-lookup"><span data-stu-id="49480-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="49480-170">Ajustar o Microsoft Defender existente para consultas de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="49480-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="49480-171">As consultas do Microsoft Defender para Pontos de Extremidade funcionarão como estão, a menos que elas faça referência à `DeviceAlertEvents` tabela.</span><span class="sxs-lookup"><span data-stu-id="49480-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="49480-172">Para usar essas consultas no Microsoft 365 Defender, aplique estas alterações:</span><span class="sxs-lookup"><span data-stu-id="49480-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="49480-173">Substitua `DeviceAlertEvents` por `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="49480-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="49480-174">`AlertInfo`Junte-se a e às `AlertEvidence` tabelas para obter dados `AlertId` equivalentes.</span><span class="sxs-lookup"><span data-stu-id="49480-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="49480-175">Consulta original</span><span class="sxs-lookup"><span data-stu-id="49480-175">Original query</span></span>
<span data-ttu-id="49480-176">A consulta a seguir `DeviceAlertEvents` usa no Microsoft Defender for Endpoint para obter os alertas que envolvem _powershell.exe:_</span><span class="sxs-lookup"><span data-stu-id="49480-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="49480-177">Consulta modificada</span><span class="sxs-lookup"><span data-stu-id="49480-177">Modified query</span></span>
<span data-ttu-id="49480-178">A consulta a seguir foi ajustada para uso no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="49480-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="49480-179">Em vez de verificar o nome do arquivo diretamente de , ele `DeviceAlertEvents` se une e verifica o nome do arquivo nessa `AlertEvidence` tabela.</span><span class="sxs-lookup"><span data-stu-id="49480-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="49480-180">Migrar regras de detecção personalizadas</span><span class="sxs-lookup"><span data-stu-id="49480-180">Migrate custom detection rules</span></span>

<span data-ttu-id="49480-181">Quando as regras do Microsoft Defender for Endpoint são editadas no Microsoft 365 Defender, elas continuam a funcionar como antes se a consulta resultante analisasse apenas as tabelas do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49480-181">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> <span data-ttu-id="49480-182">Por exemplo, alertas gerados por regras de detecção personalizadas que consultam apenas tabelas de dispositivos continuarão a ser entregues ao SIEM e gerarão notificações por email, dependendo de como você as configurou no Microsoft Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="49480-182">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="49480-183">Quaisquer regras de supressão existentes no Defender para Ponto de Extremidade também continuarão a ser aplicadas.</span><span class="sxs-lookup"><span data-stu-id="49480-183">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="49480-184">Depois de editar uma regra do Defender para Ponto de Extremidade para que ele consulte as tabelas de identidade e email, que só estão disponíveis no Microsoft 365 Defender, a regra é movida automaticamente para o Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="49480-184">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="49480-185">Alertas gerados pela regra migrada:</span><span class="sxs-lookup"><span data-stu-id="49480-185">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="49480-186">Não estão mais visíveis no portal do Defender para Ponto de Extremidade (Central de Segurança do Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="49480-186">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="49480-187">Pare de ser entregue ao SIEM ou gere notificações por email.</span><span class="sxs-lookup"><span data-stu-id="49480-187">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="49480-188">Para resolver essa alteração, configure as notificações por meio do Microsoft 365 Defender para receber os alertas.</span><span class="sxs-lookup"><span data-stu-id="49480-188">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="49480-189">Você pode usar a [API do Microsoft 365 Defender](api-incident.md) para receber notificações de alertas de detecção do cliente ou incidentes relacionados.</span><span class="sxs-lookup"><span data-stu-id="49480-189">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="49480-190">Não será suprimido pelo Microsoft Defender para regras de supressão de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="49480-190">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="49480-191">Para impedir que alertas são gerados para determinados usuários, dispositivos ou caixas de correio, modifique as consultas correspondentes para excluir essas entidades explicitamente.</span><span class="sxs-lookup"><span data-stu-id="49480-191">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="49480-192">Se editar uma regra dessa maneira, você será solicitado a confirmar antes que essas alterações sejam aplicadas.</span><span class="sxs-lookup"><span data-stu-id="49480-192">If you do edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="49480-193">Novos alertas gerados por regras de detecção personalizadas no portal do Microsoft 365 Defender são exibidos em uma página de alerta que fornece as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="49480-193">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="49480-194">Título e descrição do alerta</span><span class="sxs-lookup"><span data-stu-id="49480-194">Alert title and description</span></span> 
- <span data-ttu-id="49480-195">Ativos afetados</span><span class="sxs-lookup"><span data-stu-id="49480-195">Impacted assets</span></span>
- <span data-ttu-id="49480-196">Ações tomadas em resposta ao alerta</span><span class="sxs-lookup"><span data-stu-id="49480-196">Actions taken in response to the alert</span></span>
- <span data-ttu-id="49480-197">Resultados de consulta que dispararam o alerta</span><span class="sxs-lookup"><span data-stu-id="49480-197">Query results that triggered the alert</span></span> 
- <span data-ttu-id="49480-198">Informações sobre a regra de detecção personalizada</span><span class="sxs-lookup"><span data-stu-id="49480-198">Information on the custom detection rule</span></span> 
 
![Imagem da nova página de alerta](../../media/newalertpage.png)

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="49480-200">Gravar consultas sem DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="49480-200">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="49480-201">No esquema do Microsoft 365 Defender, as tabelas e as tabelas são fornecidas para acomodar o conjunto diversificado de informações que acompanham `AlertInfo` `AlertEvidence` alertas de várias fontes.</span><span class="sxs-lookup"><span data-stu-id="49480-201">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="49480-202">Para obter as mesmas informações de alerta que você usou para obter da tabela no esquema do Microsoft Defender para Ponto de Extremidade, filtre a tabela e, em seguida, insinte cada ID exclusiva na tabela, que fornece informações detalhadas de evento e `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` entidade.</span><span class="sxs-lookup"><span data-stu-id="49480-202">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="49480-203">Consulte a consulta de exemplo abaixo:</span><span class="sxs-lookup"><span data-stu-id="49480-203">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="49480-204">Essa consulta gera muito mais colunas do que no `DeviceAlertEvents` esquema do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="49480-204">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="49480-205">Para manter os resultados gerenciáveis, use para obter apenas as `project` colunas em que você está interessado.</span><span class="sxs-lookup"><span data-stu-id="49480-205">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="49480-206">O exemplo abaixo projeta colunas em que você pode estar interessado quando a investigação detectou a atividade do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="49480-206">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="49480-207">Se você quiser filtrar entidades específicas envolvidas nos alertas, poderá fazer isso especificando o tipo de entidade e o valor que você gostaria de `EntityType` filtrar.</span><span class="sxs-lookup"><span data-stu-id="49480-207">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="49480-208">O exemplo a seguir procura um endereço IP específico:</span><span class="sxs-lookup"><span data-stu-id="49480-208">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="49480-209">Confira também</span><span class="sxs-lookup"><span data-stu-id="49480-209">See also</span></span>
- [<span data-ttu-id="49480-210">Ativar o Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49480-210">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="49480-211">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="49480-211">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="49480-212">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="49480-212">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="49480-213">Busca avançada no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="49480-213">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)