---
title: Migrar consultas de busca avançada do Microsoft defender ATP
description: Saiba como ajustar suas consultas ATP do Microsoft defender para que você possa usá-las na proteção contra ameaças da Microsoft
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, Microsoft defender ATP, mdatp, pesquisa, consulta, telemetria, detecções personalizadas, esquema, Kusto, Microsoft 365, mapeamento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: f56360b28a9fe9de4198d97954a64a429d1d99a5
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429690"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a><span data-ttu-id="51d6d-104">Migrar consultas de busca avançada do Microsoft defender ATP</span><span class="sxs-lookup"><span data-stu-id="51d6d-104">Migrate advanced hunting queries from Microsoft Defender ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="51d6d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="51d6d-105">**Applies to:**</span></span>
- <span data-ttu-id="51d6d-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="51d6d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="51d6d-107">Mova seus fluxos de trabalho de busca avançada do Microsoft defender ATP para procurar ameaças de forma proativa usando um conjunto mais amplo de dados.</span><span class="sxs-lookup"><span data-stu-id="51d6d-107">Move your advanced hunting workflows from Microsoft Defender ATP to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="51d6d-108">Na proteção contra ameaças da Microsoft, você tem acesso a dados de outras soluções de segurança da Microsoft 365, incluindo:</span><span class="sxs-lookup"><span data-stu-id="51d6d-108">In Microsoft Threat Protection, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="51d6d-109">Proteção avançada contra ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="51d6d-109">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="51d6d-110">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="51d6d-110">Office 365 Advanced Threat Protection</span></span>
- <span data-ttu-id="51d6d-111">Segurança no aplicativo na nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="51d6d-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="51d6d-112">Proteção Avançada contra Ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="51d6d-112">Azure Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="51d6d-113">A maioria dos clientes do Microsoft defender ATP pode [usar a proteção contra ameaças da Microsoft sem licenças adicionais](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="51d6d-113">Most Microsoft Defender ATP customers can [use Microsoft Threat Protection without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="51d6d-114">Para começar a fazer a transição de seus fluxos de trabalho de busca avançada do Microsoft defender ATP, [ative a proteção contra ameaças da Microsoft](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="51d6d-114">To start transitioning your advanced hunting workflows from Microsoft Defender ATP, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

<span data-ttu-id="51d6d-115">Você pode migrar sem afetar seus fluxos de trabalho ATP existentes do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="51d6d-115">You can transition without affecting your existing Microsoft Defender ATP workflows.</span></span> <span data-ttu-id="51d6d-116">As consultas salvas permanecem intactas, e as regras de detecção personalizadas continuam a executar e gerar alertas.</span><span class="sxs-lookup"><span data-stu-id="51d6d-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="51d6d-117">No entanto, eles estarão visíveis na proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="51d6d-117">They will, however, be visible in Microsoft Threat Protection.</span></span> 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a><span data-ttu-id="51d6d-118">Tabelas de esquema somente na proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="51d6d-118">Schema tables in Microsoft Threat Protection only</span></span>
<span data-ttu-id="51d6d-119">O [esquema de busca avançada da proteção contra ameaças da Microsoft](advanced-hunting-schema-tables.md) fornece tabelas adicionais contendo dados de várias soluções de segurança da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51d6d-119">The [Microsoft Threat Protection advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="51d6d-120">As tabelas a seguir estão disponíveis somente na proteção contra ameaças da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="51d6d-120">The following tables are available only in Microsoft Threat Protection:</span></span>

| <span data-ttu-id="51d6d-121">Nome da tabela</span><span class="sxs-lookup"><span data-stu-id="51d6d-121">Table name</span></span> | <span data-ttu-id="51d6d-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="51d6d-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="51d6d-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="51d6d-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="51d6d-124">Arquivos, endereços IP, URLs, usuários ou dispositivos associados a alertas</span><span class="sxs-lookup"><span data-stu-id="51d6d-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="51d6d-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="51d6d-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="51d6d-126">Alertas do Microsoft defender ATP, Office 365 ATP, Microsoft Cloud app Security e Azure ATP, incluindo informações de gravidade e categorias de ameaças</span><span class="sxs-lookup"><span data-stu-id="51d6d-126">Alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="51d6d-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="51d6d-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="51d6d-128">Atividades relacionadas a arquivos em aplicativos e serviços em nuvem</span><span class="sxs-lookup"><span data-stu-id="51d6d-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="51d6d-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="51d6d-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="51d6d-130">Informações sobre arquivos anexados a emails</span><span class="sxs-lookup"><span data-stu-id="51d6d-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="51d6d-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="51d6d-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="51d6d-132">Eventos de email da Microsoft 365, incluindo a entrega de email e eventos de bloqueio</span><span class="sxs-lookup"><span data-stu-id="51d6d-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="51d6d-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="51d6d-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="51d6d-134">Eventos de segurança que ocorrem após a entrega após a Microsoft 365 ter entregue os emails para a caixa de correio de destinatário</span><span class="sxs-lookup"><span data-stu-id="51d6d-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="51d6d-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="51d6d-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="51d6d-136">Informações sobre URLs em emails</span><span class="sxs-lookup"><span data-stu-id="51d6d-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="51d6d-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="51d6d-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="51d6d-138">Eventos envolvendo um controlador de domínio local executando o Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="51d6d-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="51d6d-139">Esta tabela abrange um intervalo de eventos relacionados à identidade e eventos do sistema no controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="51d6d-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="51d6d-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="51d6d-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="51d6d-141">Informações de conta de várias fontes, incluindo o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="51d6d-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="51d6d-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="51d6d-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="51d6d-143">Eventos de autenticação no Active Directory e nos serviços online da Microsoft</span><span class="sxs-lookup"><span data-stu-id="51d6d-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="51d6d-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="51d6d-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="51d6d-145">Consultas para objetos do Active Directory, como usuários, grupos, dispositivos e domínios</span><span class="sxs-lookup"><span data-stu-id="51d6d-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="51d6d-146">Tabela de mapas DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="51d6d-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="51d6d-147">As `AlertInfo` `AlertEvidence` tabelas e substituem a `DeviceAlertEvents` tabela no esquema do Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="51d6d-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender ATP schema.</span></span> <span data-ttu-id="51d6d-148">Além dos dados sobre os alertas de dispositivos, essas duas tabelas incluem dados sobre alertas para identidades, aplicativos e emails.</span><span class="sxs-lookup"><span data-stu-id="51d6d-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="51d6d-149">Use a tabela a seguir para verificar como as `DeviceAlertEvents` colunas são mapeadas para colunas nas `AlertInfo` `AlertEvidence` tabelas e.</span><span class="sxs-lookup"><span data-stu-id="51d6d-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="51d6d-150">Além das colunas da tabela a seguir, a `AlertEvidence` tabela inclui muitas outras colunas que oferecem uma imagem mais holística dos alertas de várias fontes.</span><span class="sxs-lookup"><span data-stu-id="51d6d-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="51d6d-151">Ver todas as colunas AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="51d6d-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="51d6d-152">Coluna DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="51d6d-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="51d6d-153">Onde encontrar os mesmos dados na proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="51d6d-153">Where to find the same data in Microsoft Threat Protection</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="51d6d-154">`AlertInfo``AlertEvidence`tabelas e</span><span class="sxs-lookup"><span data-stu-id="51d6d-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="51d6d-155">`AlertInfo``AlertEvidence`tabelas e</span><span class="sxs-lookup"><span data-stu-id="51d6d-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="51d6d-156">`AlertEvidence` configurável</span><span class="sxs-lookup"><span data-stu-id="51d6d-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="51d6d-157">`AlertEvidence` configurável</span><span class="sxs-lookup"><span data-stu-id="51d6d-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="51d6d-158">`AlertInfo` configurável</span><span class="sxs-lookup"><span data-stu-id="51d6d-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="51d6d-159">`AlertInfo` configurável</span><span class="sxs-lookup"><span data-stu-id="51d6d-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="51d6d-160">`AlertInfo` configurável</span><span class="sxs-lookup"><span data-stu-id="51d6d-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="51d6d-161">`AlertEvidence` configurável</span><span class="sxs-lookup"><span data-stu-id="51d6d-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="51d6d-162">`AlertEvidence` configurável</span><span class="sxs-lookup"><span data-stu-id="51d6d-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="51d6d-163">`AlertEvidence` configurável</span><span class="sxs-lookup"><span data-stu-id="51d6d-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="51d6d-164">`AlertEvidence` configurável</span><span class="sxs-lookup"><span data-stu-id="51d6d-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="51d6d-165">`AlertInfo` configurável</span><span class="sxs-lookup"><span data-stu-id="51d6d-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="51d6d-166">Essa coluna é normalmente usada no Microsoft defender ATP para localizar registros relacionados em outras tabelas.</span><span class="sxs-lookup"><span data-stu-id="51d6d-166">This column is typically used in Microsoft Defender ATP to locate related records in other tables.</span></span> <span data-ttu-id="51d6d-167">Na proteção contra ameaças da Microsoft, você pode obter dados relacionados diretamente da `AlertEvidence` tabela.</span><span class="sxs-lookup"><span data-stu-id="51d6d-167">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="51d6d-168">Essa coluna é normalmente usada no Microsoft defender ATP para obter informações adicionais sobre eventos em outras tabelas.</span><span class="sxs-lookup"><span data-stu-id="51d6d-168">This column is typically used in Microsoft Defender ATP for additional event information in other tables.</span></span> <span data-ttu-id="51d6d-169">Na proteção contra ameaças da Microsoft, você pode obter dados relacionados diretamente da `AlertEvidence` tabela.</span><span class="sxs-lookup"><span data-stu-id="51d6d-169">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a><span data-ttu-id="51d6d-170">Ajustar as consultas ATP existentes do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="51d6d-170">Adjust existing Microsoft Defender ATP queries</span></span>
<span data-ttu-id="51d6d-171">As consultas ATP do Microsoft defender funcionarão como estão, a menos que façam referência à `DeviceAlertEvents` tabela.</span><span class="sxs-lookup"><span data-stu-id="51d6d-171">Microsoft Defender ATP queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="51d6d-172">Para usar essas consultas na proteção contra ameaças da Microsoft, aplique essas alterações:</span><span class="sxs-lookup"><span data-stu-id="51d6d-172">To use these queries in Microsoft Threat Protection, apply these changes:</span></span>

- <span data-ttu-id="51d6d-173">Substituir `DeviceAlertEvents` por `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="51d6d-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="51d6d-174">Ingresse no `AlertInfo` e nas `AlertEvidence` tabelas `AlertId` para obter os dados equivalentes.</span><span class="sxs-lookup"><span data-stu-id="51d6d-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="51d6d-175">Consulta original</span><span class="sxs-lookup"><span data-stu-id="51d6d-175">Original query</span></span>
<span data-ttu-id="51d6d-176">A consulta a seguir usa o `DeviceAlertEvents` Microsoft defender ATP para obter os alertas que envolvem _powershell.exe_:</span><span class="sxs-lookup"><span data-stu-id="51d6d-176">The following query uses `DeviceAlertEvents` in Microsoft Defender ATP to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="51d6d-177">Consulta modificada</span><span class="sxs-lookup"><span data-stu-id="51d6d-177">Modified query</span></span>
<span data-ttu-id="51d6d-178">A seguinte consulta foi ajustada para uso na proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="51d6d-178">The following query has been adjusted for use in Microsoft Threat Protection.</span></span> <span data-ttu-id="51d6d-179">Em vez de verificar o nome do arquivo diretamente de `DeviceAlertEvents` , ele entra `AlertEvidence` e verifica o nome do arquivo nessa tabela.</span><span class="sxs-lookup"><span data-stu-id="51d6d-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="51d6d-180">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="51d6d-180">Related topics</span></span>
- [<span data-ttu-id="51d6d-181">Habilitar a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="51d6d-181">Turn on Microsoft Threat Protection</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="51d6d-182">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="51d6d-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="51d6d-183">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="51d6d-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="51d6d-184">Busca avançada no Microsoft defender ATP</span><span class="sxs-lookup"><span data-stu-id="51d6d-184">Advanced hunting in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)