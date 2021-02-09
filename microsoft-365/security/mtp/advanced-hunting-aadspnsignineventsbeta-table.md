---
title: Tabela AADSpnSignInEventsBeta no esquema de busca avançada
description: Saiba mais sobre as informações associadas à entidade de serviço do Azure Active Directory e à tabela de eventos de login de identidade gerenciada do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, AlertInfo, alerta, entidades, evidências, arquivo, endereço IP, dispositivo, computador, usuário, conta, identidade, AAD
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3eba2459fd9a0af1963ca8d1446b22fc0b1bdb93
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145398"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="1e533-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="1e533-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="1e533-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1e533-105">**Applies to:**</span></span>

- <span data-ttu-id="1e533-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e533-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="1e533-107">A tabela está atualmente na versão beta e está sendo oferecida a curto prazo para permitir que você cace a entidade de serviço do `AADSpnSignInEventsBeta` Azure Active Directory (AAD) e os eventos de login de identidade gerenciada.</span><span class="sxs-lookup"><span data-stu-id="1e533-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="1e533-108">Eventualmente, moveremos todas as informações do esquema de logom para a `IdentityLogonEvents` tabela.</span><span class="sxs-lookup"><span data-stu-id="1e533-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="1e533-109">Os clientes que podem acessar o Microsoft 365 Defender por meio da solução integrada do Microsoft Defender for Endpoint da Central de Segurança do Azure, mas não têm licenças para o Microsoft Defender para Office, o Microsoft Defender for Identity ou o Microsoft Cloud App Security, não poderão exibir esse esquema.</span><span class="sxs-lookup"><span data-stu-id="1e533-109">Customers who can access Microsoft 365 Defender through the Azure Security Center’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="1e533-110">A tabela no esquema de busca avançada contém informações sobre a entidade de serviço do Azure Active Directory e as `AADSpnSignInEventsBeta` insições de identidade gerenciada. Você pode saber mais sobre os diferentes tipos de login nos relatórios de atividade de login do [Azure Active Directory - visualização.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)</span><span class="sxs-lookup"><span data-stu-id="1e533-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="1e533-111">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="1e533-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="1e533-112">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span><span class="sxs-lookup"><span data-stu-id="1e533-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="1e533-113">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="1e533-113">Column name</span></span>     | <span data-ttu-id="1e533-114">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="1e533-114">Data type</span></span> | <span data-ttu-id="1e533-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="1e533-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="1e533-116">datetime</span><span class="sxs-lookup"><span data-stu-id="1e533-116">datetime</span></span>      | <span data-ttu-id="1e533-117">Data e hora em que o registro foi gerado</span><span class="sxs-lookup"><span data-stu-id="1e533-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="1e533-118">string</span><span class="sxs-lookup"><span data-stu-id="1e533-118">string</span></span>        | <span data-ttu-id="1e533-119">Aplicativo que realizou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="1e533-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="1e533-120">string</span><span class="sxs-lookup"><span data-stu-id="1e533-120">string</span></span>        | <span data-ttu-id="1e533-121">Identificador exclusivo do aplicativo</span><span class="sxs-lookup"><span data-stu-id="1e533-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="1e533-122">booliano</span><span class="sxs-lookup"><span data-stu-id="1e533-122">boolean</span></span>       | <span data-ttu-id="1e533-123">Indica se a login foi iniciada por uma identidade gerenciada</span><span class="sxs-lookup"><span data-stu-id="1e533-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="1e533-124">int</span><span class="sxs-lookup"><span data-stu-id="1e533-124">int</span></span>        | <span data-ttu-id="1e533-125">Contém o código de erro se ocorrer um erro de login.</span><span class="sxs-lookup"><span data-stu-id="1e533-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="1e533-126">Para encontrar uma descrição de um código de erro específico, <https://aka.ms/AADsigninsErrorCodes> visite.</span><span class="sxs-lookup"><span data-stu-id="1e533-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="1e533-127">string</span><span class="sxs-lookup"><span data-stu-id="1e533-127">string</span></span>        | <span data-ttu-id="1e533-128">Identificador exclusivo do evento de login</span><span class="sxs-lookup"><span data-stu-id="1e533-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="1e533-129">string</span><span class="sxs-lookup"><span data-stu-id="1e533-129">string</span></span>        | <span data-ttu-id="1e533-130">Nome da entidade de serviço que iniciou a login</span><span class="sxs-lookup"><span data-stu-id="1e533-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="1e533-131">string</span><span class="sxs-lookup"><span data-stu-id="1e533-131">string</span></span>        | <span data-ttu-id="1e533-132">Identificador exclusivo da entidade de serviço que iniciou a login</span><span class="sxs-lookup"><span data-stu-id="1e533-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="1e533-133">string</span><span class="sxs-lookup"><span data-stu-id="1e533-133">string</span></span>        | <span data-ttu-id="1e533-134">Nome de exibição do recurso acessado</span><span class="sxs-lookup"><span data-stu-id="1e533-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="1e533-135">string</span><span class="sxs-lookup"><span data-stu-id="1e533-135">string</span></span>        | <span data-ttu-id="1e533-136">Identificador exclusivo do recurso acessado</span><span class="sxs-lookup"><span data-stu-id="1e533-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="1e533-137">string</span><span class="sxs-lookup"><span data-stu-id="1e533-137">string</span></span>        | <span data-ttu-id="1e533-138">Identificador exclusivo do locatário do recurso acessado</span><span class="sxs-lookup"><span data-stu-id="1e533-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="1e533-139">string</span><span class="sxs-lookup"><span data-stu-id="1e533-139">string</span></span>        | <span data-ttu-id="1e533-140">Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="1e533-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `Country`          | <span data-ttu-id="1e533-141">string</span><span class="sxs-lookup"><span data-stu-id="1e533-141">string</span></span>        | <span data-ttu-id="1e533-142">Código de duas letras indicando o país onde o endereço IP do cliente está geolocalado</span><span class="sxs-lookup"><span data-stu-id="1e533-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="1e533-143">string</span><span class="sxs-lookup"><span data-stu-id="1e533-143">string</span></span>        | <span data-ttu-id="1e533-144">Estado em que ocorreu a login, se disponível</span><span class="sxs-lookup"><span data-stu-id="1e533-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="1e533-145">string</span><span class="sxs-lookup"><span data-stu-id="1e533-145">string</span></span>        | <span data-ttu-id="1e533-146">Cidade onde o usuário da conta está localizado</span><span class="sxs-lookup"><span data-stu-id="1e533-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="1e533-147">string</span><span class="sxs-lookup"><span data-stu-id="1e533-147">string</span></span>        | <span data-ttu-id="1e533-148">As coordenadas de norte para sul do local de login</span><span class="sxs-lookup"><span data-stu-id="1e533-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="1e533-149">string</span><span class="sxs-lookup"><span data-stu-id="1e533-149">string</span></span>        | <span data-ttu-id="1e533-150">As coordenadas de leste para oeste do local de login</span><span class="sxs-lookup"><span data-stu-id="1e533-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="1e533-151">string</span><span class="sxs-lookup"><span data-stu-id="1e533-151">string</span></span>        | <span data-ttu-id="1e533-152">Identificador exclusivo da solicitação</span><span class="sxs-lookup"><span data-stu-id="1e533-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="1e533-153">string</span><span class="sxs-lookup"><span data-stu-id="1e533-153">string</span></span> | <span data-ttu-id="1e533-154">Identificador exclusivo do evento</span><span class="sxs-lookup"><span data-stu-id="1e533-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="1e533-155">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="1e533-155">Related articles</span></span>

-   [<span data-ttu-id="1e533-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="1e533-156">AADSignInEventsBeta</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [<span data-ttu-id="1e533-157">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="1e533-157">Advanced hunting overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="1e533-158">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="1e533-158">Learn the query language</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="1e533-159">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="1e533-159">Understand the schema</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

