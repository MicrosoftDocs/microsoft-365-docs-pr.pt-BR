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
ms.openlocfilehash: 521b5fc2a8efee83b6a2931e7dbc1c713bd63cd2
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094802"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="f160f-104">Migrar consultas de busca avançada do Microsoft Defender para o Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f160f-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f160f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f160f-105">**Applies to:**</span></span>
- <span data-ttu-id="f160f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f160f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f160f-107">Mova seus fluxos de trabalho de busca avançada do Microsoft Defender para o Ponto de Extremidade para procurar proativamente por ameaças usando um conjunto mais amplo de dados.</span><span class="sxs-lookup"><span data-stu-id="f160f-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="f160f-108">No Microsoft 365 Defender, você tem acesso a dados de outras soluções de segurança do Microsoft 365, incluindo:</span><span class="sxs-lookup"><span data-stu-id="f160f-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="f160f-109">Proteção Avançada contra Ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f160f-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="f160f-110">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f160f-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="f160f-111">Segurança no aplicativo na nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f160f-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="f160f-112">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="f160f-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="f160f-113">A maioria dos clientes do Microsoft Defender para Pontos de Extremidade [pode usar o Microsoft 365 Defender sem licenças adicionais.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="f160f-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="f160f-114">Para começar a fazer a transição de seus fluxos de trabalho de busca avançada do Defender para o Ponto de Extremidade, [a ligue o Microsoft 365 Defender.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="f160f-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="f160f-115">Você pode fazer a transição sem afetar o Defender existente para fluxos de trabalho do Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="f160f-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="f160f-116">As consultas salvas permanecem intactas, e as regras de detecção personalizadas continuam a ser executados e geram alertas.</span><span class="sxs-lookup"><span data-stu-id="f160f-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="f160f-117">No entanto, eles estarão visíveis no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f160f-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="f160f-118">Tabelas de esquema somente no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f160f-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="f160f-119">O [esquema de busca avançada do Microsoft 365 Defender](advanced-hunting-schema-tables.md) fornece tabelas adicionais contendo dados de várias soluções de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f160f-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="f160f-120">As tabelas a seguir estão disponíveis apenas no Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="f160f-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="f160f-121">Nome da tabela</span><span class="sxs-lookup"><span data-stu-id="f160f-121">Table name</span></span> | <span data-ttu-id="f160f-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="f160f-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="f160f-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="f160f-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="f160f-124">Arquivos, endereços IP, URLs, usuários ou dispositivos associados a alertas</span><span class="sxs-lookup"><span data-stu-id="f160f-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="f160f-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="f160f-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="f160f-126">Alertas do Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Office 365, Microsoft Cloud App Security e Microsoft Defender para Identidade, incluindo informações de gravidade e categorias de ameaças</span><span class="sxs-lookup"><span data-stu-id="f160f-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="f160f-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="f160f-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="f160f-128">Atividades relacionadas a arquivos em serviços e aplicativos de nuvem</span><span class="sxs-lookup"><span data-stu-id="f160f-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="f160f-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="f160f-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="f160f-130">Informações sobre arquivos anexados a emails</span><span class="sxs-lookup"><span data-stu-id="f160f-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="f160f-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="f160f-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="f160f-132">Eventos de email do Microsoft 365, incluindo eventos de entrega e bloqueio de email</span><span class="sxs-lookup"><span data-stu-id="f160f-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="f160f-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="f160f-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="f160f-134">Eventos de segurança que ocorrem após a entrega, depois que o Microsoft 365 entrega os emails para a caixa de correio do destinatário</span><span class="sxs-lookup"><span data-stu-id="f160f-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="f160f-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="f160f-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="f160f-136">Informações sobre URLs em emails</span><span class="sxs-lookup"><span data-stu-id="f160f-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="f160f-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="f160f-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="f160f-138">Eventos envolvendo um controlador de domínio local executando o Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="f160f-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="f160f-139">Esta tabela abrange uma variedade de eventos relacionados à identidade e eventos do sistema no controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="f160f-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="f160f-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="f160f-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="f160f-141">Informações da conta de várias fontes, incluindo o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f160f-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="f160f-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="f160f-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="f160f-143">Eventos de autenticação no Active Directory e nos serviços online da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f160f-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="f160f-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="f160f-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="f160f-145">Consultas para objetos do Active Directory, como usuários, grupos, dispositivos e domínios</span><span class="sxs-lookup"><span data-stu-id="f160f-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="f160f-146">Tabela Mapear DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="f160f-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="f160f-147">The `AlertInfo` and tables replace the table in the Microsoft Defender for `AlertEvidence` `DeviceAlertEvents` Endpoint schema.</span><span class="sxs-lookup"><span data-stu-id="f160f-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="f160f-148">Além dos dados sobre alertas de dispositivo, essas duas tabelas incluem dados sobre alertas de identidades, aplicativos e emails.</span><span class="sxs-lookup"><span data-stu-id="f160f-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="f160f-149">Use a tabela a seguir para verificar como `DeviceAlertEvents` as colunas são mapeadas para colunas nas `AlertInfo` tabelas e `AlertEvidence` tabelas.</span><span class="sxs-lookup"><span data-stu-id="f160f-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="f160f-150">Além das colunas da tabela a seguir, a tabela inclui muitas outras colunas que fornecem uma imagem mais holística dos `AlertEvidence` alertas de várias fontes.</span><span class="sxs-lookup"><span data-stu-id="f160f-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="f160f-151">Ver todas as colunas AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="f160f-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="f160f-152">Coluna DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="f160f-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="f160f-153">Onde encontrar os mesmos dados no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f160f-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="f160f-154">`AlertInfo` e  `AlertEvidence` tabelas</span><span class="sxs-lookup"><span data-stu-id="f160f-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="f160f-155">`AlertInfo` e  `AlertEvidence` tabelas</span><span class="sxs-lookup"><span data-stu-id="f160f-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="f160f-156">`AlertEvidence` tabela</span><span class="sxs-lookup"><span data-stu-id="f160f-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="f160f-157">`AlertEvidence` tabela</span><span class="sxs-lookup"><span data-stu-id="f160f-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="f160f-158">`AlertInfo` tabela</span><span class="sxs-lookup"><span data-stu-id="f160f-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="f160f-159">`AlertInfo` tabela</span><span class="sxs-lookup"><span data-stu-id="f160f-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="f160f-160">`AlertInfo` tabela</span><span class="sxs-lookup"><span data-stu-id="f160f-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="f160f-161">`AlertEvidence` tabela</span><span class="sxs-lookup"><span data-stu-id="f160f-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="f160f-162">`AlertEvidence` tabela</span><span class="sxs-lookup"><span data-stu-id="f160f-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="f160f-163">`AlertEvidence` tabela</span><span class="sxs-lookup"><span data-stu-id="f160f-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="f160f-164">`AlertEvidence` tabela</span><span class="sxs-lookup"><span data-stu-id="f160f-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="f160f-165">`AlertInfo` tabela</span><span class="sxs-lookup"><span data-stu-id="f160f-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="f160f-166">Essa coluna é normalmente usada no Microsoft Defender para o Ponto de Extremidade para localizar registros relacionados em outras tabelas.</span><span class="sxs-lookup"><span data-stu-id="f160f-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="f160f-167">No Microsoft 365 Defender, você pode obter dados relacionados diretamente da `AlertEvidence` tabela.</span><span class="sxs-lookup"><span data-stu-id="f160f-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="f160f-168">Essa coluna é normalmente usada no Microsoft Defender para o Ponto de Extremidade para obter informações de evento adicionais em outras tabelas.</span><span class="sxs-lookup"><span data-stu-id="f160f-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="f160f-169">No Microsoft 365 Defender, você pode obter dados relacionados diretamente da `AlertEvidence` tabela.</span><span class="sxs-lookup"><span data-stu-id="f160f-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="f160f-170">Ajustar o Microsoft Defender existente para consultas de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="f160f-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="f160f-171">As consultas do Microsoft Defender para Pontos de Extremidade funcionarão como estão, a menos que elas faça referência à `DeviceAlertEvents` tabela.</span><span class="sxs-lookup"><span data-stu-id="f160f-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="f160f-172">Para usar essas consultas no Microsoft 365 Defender, aplique estas alterações:</span><span class="sxs-lookup"><span data-stu-id="f160f-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="f160f-173">Substitua `DeviceAlertEvents` por `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="f160f-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="f160f-174">`AlertInfo`Junte-se a e às `AlertEvidence` tabelas para obter dados `AlertId` equivalentes.</span><span class="sxs-lookup"><span data-stu-id="f160f-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="f160f-175">Consulta original</span><span class="sxs-lookup"><span data-stu-id="f160f-175">Original query</span></span>
<span data-ttu-id="f160f-176">A consulta a seguir `DeviceAlertEvents` usa no Microsoft Defender for Endpoint para obter os alertas que envolvem _powershell.exe:_</span><span class="sxs-lookup"><span data-stu-id="f160f-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="f160f-177">Consulta modificada</span><span class="sxs-lookup"><span data-stu-id="f160f-177">Modified query</span></span>
<span data-ttu-id="f160f-178">A consulta a seguir foi ajustada para uso no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f160f-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="f160f-179">Em vez de verificar o nome do arquivo diretamente de , ele `DeviceAlertEvents` se une e verifica o nome do arquivo nessa `AlertEvidence` tabela.</span><span class="sxs-lookup"><span data-stu-id="f160f-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```



## <a name="see-also"></a><span data-ttu-id="f160f-180">Confira também</span><span class="sxs-lookup"><span data-stu-id="f160f-180">See also</span></span>
- [<span data-ttu-id="f160f-181">Ativar o Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f160f-181">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f160f-182">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="f160f-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f160f-183">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="f160f-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f160f-184">Busca avançada no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f160f-184">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)