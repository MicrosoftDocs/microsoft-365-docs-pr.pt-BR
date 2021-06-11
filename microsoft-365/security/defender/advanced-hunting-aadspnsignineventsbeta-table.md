---
title: Tabela AADSpnSignInEventsBeta no esquema de busca avançado
description: Saiba mais sobre informações associadas à Azure Active Directory de serviço e à tabela de eventos de login de identidade gerenciada do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, AlertInfo, alerta, entidades, evidências, arquivo, endereço IP, dispositivo, máquina, usuário, conta, identidade, AAD
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
ms.technology: m365d
ms.openlocfilehash: f74972bcd5d0ddaab58d82b72a55991fda44e3b1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583539"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="edbef-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="edbef-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="edbef-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="edbef-105">**Applies to:**</span></span>

- <span data-ttu-id="edbef-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="edbef-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="edbef-107">A tabela está atualmente em beta e está sendo oferecida em curto prazo para permitir que você cace a entidade de serviço Azure Active Directory (AAD) e os eventos de login de identidade `AADSpnSignInEventsBeta` gerenciada.</span><span class="sxs-lookup"><span data-stu-id="edbef-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="edbef-108">Eventualmente, moveremos todas as informações de esquema de login para a `IdentityLogonEvents` tabela.</span><span class="sxs-lookup"><span data-stu-id="edbef-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span>



<span data-ttu-id="edbef-109">A tabela no esquema de busca avançado contém informações sobre Azure Active Directory entidade de serviço e logins de identidade `AADSpnSignInEventsBeta` gerenciada. Você pode saber mais sobre os diferentes tipos de logins em Azure Active Directory relatórios de atividade de login [- visualização](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span><span class="sxs-lookup"><span data-stu-id="edbef-109">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="edbef-110">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="edbef-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="edbef-111">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span><span class="sxs-lookup"><span data-stu-id="edbef-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="edbef-112">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="edbef-112">Column name</span></span>     | <span data-ttu-id="edbef-113">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="edbef-113">Data type</span></span> | <span data-ttu-id="edbef-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="edbef-114">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="edbef-115">datetime</span><span class="sxs-lookup"><span data-stu-id="edbef-115">datetime</span></span>      | <span data-ttu-id="edbef-116">Data e hora em que o registro foi gerado</span><span class="sxs-lookup"><span data-stu-id="edbef-116">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="edbef-117">string</span><span class="sxs-lookup"><span data-stu-id="edbef-117">string</span></span>        | <span data-ttu-id="edbef-118">Aplicativo que realizou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="edbef-118">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="edbef-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="edbef-119">string</span></span>        | <span data-ttu-id="edbef-120">Identificador exclusivo do aplicativo</span><span class="sxs-lookup"><span data-stu-id="edbef-120">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="edbef-121">booliano</span><span class="sxs-lookup"><span data-stu-id="edbef-121">boolean</span></span>       | <span data-ttu-id="edbef-122">Indica se a assinatura foi iniciada por uma identidade gerenciada</span><span class="sxs-lookup"><span data-stu-id="edbef-122">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="edbef-123">int</span><span class="sxs-lookup"><span data-stu-id="edbef-123">int</span></span>        | <span data-ttu-id="edbef-124">Contém o código de erro se ocorrer um erro de login.</span><span class="sxs-lookup"><span data-stu-id="edbef-124">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="edbef-125">Para encontrar uma descrição de um código de erro específico, visite <https://aka.ms/AADsigninsErrorCodes> .</span><span class="sxs-lookup"><span data-stu-id="edbef-125">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="edbef-126">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="edbef-126">string</span></span>        | <span data-ttu-id="edbef-127">Identificador exclusivo do evento de login</span><span class="sxs-lookup"><span data-stu-id="edbef-127">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="edbef-128">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="edbef-128">string</span></span>        | <span data-ttu-id="edbef-129">Nome da entidade de serviço que iniciou a login</span><span class="sxs-lookup"><span data-stu-id="edbef-129">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="edbef-130">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="edbef-130">string</span></span>        | <span data-ttu-id="edbef-131">Identificador exclusivo da entidade de serviço que iniciou a login</span><span class="sxs-lookup"><span data-stu-id="edbef-131">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="edbef-132">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="edbef-132">string</span></span>        | <span data-ttu-id="edbef-133">Nome de exibição do recurso acessado</span><span class="sxs-lookup"><span data-stu-id="edbef-133">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="edbef-134">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="edbef-134">string</span></span>        | <span data-ttu-id="edbef-135">Identificador exclusivo do recurso acessado</span><span class="sxs-lookup"><span data-stu-id="edbef-135">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="edbef-136">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="edbef-136">string</span></span>        | <span data-ttu-id="edbef-137">Identificador exclusivo do locatário do recurso acessado</span><span class="sxs-lookup"><span data-stu-id="edbef-137">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="edbef-138">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="edbef-138">string</span></span>        | <span data-ttu-id="edbef-139">Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="edbef-139">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `Country`          | <span data-ttu-id="edbef-140">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="edbef-140">string</span></span>        | <span data-ttu-id="edbef-141">Código de duas letras indicando o país onde o endereço IP do cliente está geolocado</span><span class="sxs-lookup"><span data-stu-id="edbef-141">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="edbef-142">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="edbef-142">string</span></span>        | <span data-ttu-id="edbef-143">Estado em que a login ocorreu, se disponível</span><span class="sxs-lookup"><span data-stu-id="edbef-143">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="edbef-144">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="edbef-144">string</span></span>        | <span data-ttu-id="edbef-145">Cidade onde o usuário da conta está localizado</span><span class="sxs-lookup"><span data-stu-id="edbef-145">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="edbef-146">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="edbef-146">string</span></span>        | <span data-ttu-id="edbef-147">As coordenadas norte a sul do local de login</span><span class="sxs-lookup"><span data-stu-id="edbef-147">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="edbef-148">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="edbef-148">string</span></span>        | <span data-ttu-id="edbef-149">As coordenadas de leste a oeste do local de login</span><span class="sxs-lookup"><span data-stu-id="edbef-149">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="edbef-150">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="edbef-150">string</span></span>        | <span data-ttu-id="edbef-151">Identificador exclusivo da solicitação</span><span class="sxs-lookup"><span data-stu-id="edbef-151">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="edbef-152">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="edbef-152">string</span></span> | <span data-ttu-id="edbef-153">Identificador exclusivo do evento</span><span class="sxs-lookup"><span data-stu-id="edbef-153">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="edbef-154">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="edbef-154">Related articles</span></span>

-   [<span data-ttu-id="edbef-155">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="edbef-155">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="edbef-156">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="edbef-156">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="edbef-157">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="edbef-157">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="edbef-158">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="edbef-158">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)