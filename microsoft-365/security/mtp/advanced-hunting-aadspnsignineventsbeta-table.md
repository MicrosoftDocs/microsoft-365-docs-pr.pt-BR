---
title: Tabela AADSpnSignInEventsBeta no esquema de busca avançada
description: Saiba mais sobre as informações associadas à entidade de serviço do Azure Active Directory e à tabela de eventos de login de identidade gerenciada do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, AlertInfo, alerta, entidades, evidências, arquivo, endereço IP, dispositivo, computador, usuário, conta, identidade, AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 42acf24ce9b941fffb1ce0ed4b67216bd8c1de47
ms.sourcegitcommit: 4482c174e0e68e0fbbc7ad9ef6b0e78dc34ac85a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2021
ms.locfileid: "49784294"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="b2e75-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="b2e75-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="b2e75-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b2e75-105">**Applies to:**</span></span>

- <span data-ttu-id="b2e75-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b2e75-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="b2e75-107">A tabela está atualmente na versão beta e está sendo oferecida a curto prazo para permitir que você cace a entidade de serviço do `AADSpnSignInEventsBeta` Azure Active Directory (AAD) e os eventos de login de identidade gerenciada.</span><span class="sxs-lookup"><span data-stu-id="b2e75-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="b2e75-108">Eventualmente, moveremos todas as informações do esquema de logom para a `IdentityLogonEvents` tabela.</span><span class="sxs-lookup"><span data-stu-id="b2e75-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="b2e75-109">Os clientes que podem acessar o Microsoft 365 Defender por meio da solução integrada do Microsoft Defender for Endpoint da Central de Segurança do Azure, mas não têm licenças para o Microsoft Defender para Office, o Microsoft Defender for Identity ou o Microsoft Cloud App Security, não poderão exibir esse esquema.</span><span class="sxs-lookup"><span data-stu-id="b2e75-109">Customers who can access Microsoft 365 Defender through the Azure Security Center’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="b2e75-110">A tabela no esquema de busca avançada contém informações sobre a entidade de serviço do Azure Active Directory e as `AADSpnSignInEventsBeta` insições de identidade gerenciada. Você pode saber mais sobre os diferentes tipos de login nos relatórios de atividade de login do [Azure Active Directory - visualização.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)</span><span class="sxs-lookup"><span data-stu-id="b2e75-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="b2e75-111">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="b2e75-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="b2e75-112">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span><span class="sxs-lookup"><span data-stu-id="b2e75-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="b2e75-113">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="b2e75-113">Column name</span></span>     | <span data-ttu-id="b2e75-114">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="b2e75-114">Data type</span></span> | <span data-ttu-id="b2e75-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="b2e75-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="b2e75-116">datetime</span><span class="sxs-lookup"><span data-stu-id="b2e75-116">datetime</span></span>      | <span data-ttu-id="b2e75-117">Data e hora em que o registro foi gerado</span><span class="sxs-lookup"><span data-stu-id="b2e75-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="b2e75-118">string</span><span class="sxs-lookup"><span data-stu-id="b2e75-118">string</span></span>        | <span data-ttu-id="b2e75-119">Aplicativo que realizou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="b2e75-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="b2e75-120">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b2e75-120">string</span></span>        | <span data-ttu-id="b2e75-121">Identificador exclusivo do aplicativo</span><span class="sxs-lookup"><span data-stu-id="b2e75-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="b2e75-122">booliano</span><span class="sxs-lookup"><span data-stu-id="b2e75-122">boolean</span></span>       | <span data-ttu-id="b2e75-123">Indica se a login foi iniciada por uma identidade gerenciada</span><span class="sxs-lookup"><span data-stu-id="b2e75-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="b2e75-124">int</span><span class="sxs-lookup"><span data-stu-id="b2e75-124">int</span></span>        | <span data-ttu-id="b2e75-125">Contém o código de erro se ocorrer um erro de login.</span><span class="sxs-lookup"><span data-stu-id="b2e75-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="b2e75-126">Para encontrar uma descrição de um código de erro específico, <https://aka.ms/AADsigninsErrorCodes> visite.</span><span class="sxs-lookup"><span data-stu-id="b2e75-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="b2e75-127">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b2e75-127">string</span></span>        | <span data-ttu-id="b2e75-128">Identificador exclusivo do evento de login</span><span class="sxs-lookup"><span data-stu-id="b2e75-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="b2e75-129">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b2e75-129">string</span></span>        | <span data-ttu-id="b2e75-130">Nome da entidade de serviço que iniciou a login</span><span class="sxs-lookup"><span data-stu-id="b2e75-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="b2e75-131">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b2e75-131">string</span></span>        | <span data-ttu-id="b2e75-132">Identificador exclusivo da entidade de serviço que iniciou a login</span><span class="sxs-lookup"><span data-stu-id="b2e75-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="b2e75-133">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b2e75-133">string</span></span>        | <span data-ttu-id="b2e75-134">Nome de exibição do recurso acessado</span><span class="sxs-lookup"><span data-stu-id="b2e75-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="b2e75-135">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b2e75-135">string</span></span>        | <span data-ttu-id="b2e75-136">Identificador exclusivo do recurso acessado</span><span class="sxs-lookup"><span data-stu-id="b2e75-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="b2e75-137">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b2e75-137">string</span></span>        | <span data-ttu-id="b2e75-138">Identificador exclusivo do locatário do recurso acessado</span><span class="sxs-lookup"><span data-stu-id="b2e75-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="b2e75-139">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b2e75-139">string</span></span>        | <span data-ttu-id="b2e75-140">Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="b2e75-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `CountryCode`          | <span data-ttu-id="b2e75-141">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b2e75-141">string</span></span>        | <span data-ttu-id="b2e75-142">Código de duas letras indicando o país onde o endereço IP do cliente está geolocalado</span><span class="sxs-lookup"><span data-stu-id="b2e75-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="b2e75-143">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b2e75-143">string</span></span>        | <span data-ttu-id="b2e75-144">Estado em que ocorreu a login, se disponível</span><span class="sxs-lookup"><span data-stu-id="b2e75-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="b2e75-145">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b2e75-145">string</span></span>        | <span data-ttu-id="b2e75-146">Cidade onde o usuário da conta está localizado</span><span class="sxs-lookup"><span data-stu-id="b2e75-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="b2e75-147">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b2e75-147">string</span></span>        | <span data-ttu-id="b2e75-148">As coordenadas de norte para sul do local de login</span><span class="sxs-lookup"><span data-stu-id="b2e75-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="b2e75-149">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b2e75-149">string</span></span>        | <span data-ttu-id="b2e75-150">As coordenadas de leste para oeste do local de login</span><span class="sxs-lookup"><span data-stu-id="b2e75-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="b2e75-151">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b2e75-151">string</span></span>        | <span data-ttu-id="b2e75-152">Identificador exclusivo da solicitação</span><span class="sxs-lookup"><span data-stu-id="b2e75-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="b2e75-153">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b2e75-153">string</span></span> | <span data-ttu-id="b2e75-154">Identificador exclusivo do evento</span><span class="sxs-lookup"><span data-stu-id="b2e75-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="b2e75-155">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="b2e75-155">Related articles</span></span>

-   [<span data-ttu-id="b2e75-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="b2e75-156">AADSignInEventsBeta</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [<span data-ttu-id="b2e75-157">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="b2e75-157">Advanced hunting overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="b2e75-158">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="b2e75-158">Learn the query language</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="b2e75-159">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="b2e75-159">Understand the schema</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

