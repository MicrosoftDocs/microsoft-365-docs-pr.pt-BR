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
ms.openlocfilehash: 172c400df3adea70a2e2d2e37547fa39e0d3b9cf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928613"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Aplica-se a:**

- Microsoft 365 Defender

>[!IMPORTANT]
> A tabela está atualmente na versão beta e está sendo oferecida a curto prazo para permitir que você cace a entidade de serviço do `AADSpnSignInEventsBeta` Azure Active Directory (AAD) e os eventos de login de identidade gerenciada. Eventualmente, moveremos todas as informações do esquema de logom para a `IdentityLogonEvents` tabela.<br><br>
> Os clientes que podem acessar o Microsoft 365 Defender por meio da solução integrada do Microsoft Defender for Endpoint da Central de Segurança do Azure, mas não têm licenças para o Microsoft Defender para Office, o Microsoft Defender for Identity ou o Microsoft Cloud App Security, não poderão exibir esse esquema. 



A tabela no esquema de busca avançada contém informações sobre a entidade de serviço do Azure Active Directory e as `AADSpnSignInEventsBeta` insições de identidade gerenciada. Você pode saber mais sobre os diferentes tipos de login nos relatórios de atividade de login do [Azure Active Directory - visualização.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Use esta referência para criar consultas quer retiram informações desta tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).





| Nome da coluna     | Tipo de dados | Descrição   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | Data e hora em que o registro foi gerado                                                                                                     |
| `Application`          | string        | Aplicativo que realizou a ação gravada                                                                                                   |
| `ApplicationId`        | string        | Identificador exclusivo do aplicativo                                                                                                           |
| `IsManagedIdentity`    | booliano       | Indica se a login foi iniciada por uma identidade gerenciada                                                                               |
| `ErrorCode`            | int        | Contém o código de erro se ocorrer um erro de login. Para encontrar uma descrição de um código de erro específico, <https://aka.ms/AADsigninsErrorCodes> visite. |
| `CorrelationId`        | string        | Identificador exclusivo do evento de login                                                                                                          |
| `ServicePrincipalName` | string        | Nome da entidade de serviço que iniciou a login                                                                                        |
| `ServicePrincipalId`   | string        | Identificador exclusivo da entidade de serviço que iniciou a login                                                                           |
| `ResourceDisplayName`  | string        | Nome de exibição do recurso acessado                                                                                                           |
| `ResourceId`           | string        | Identificador exclusivo do recurso acessado                                                                                                      |
| `ResourceTenantId`     | string        | Identificador exclusivo do locatário do recurso acessado                                                                                        |
| `IPAddress`            | string        | Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas                                                              |
| `CountryCode`          | string        | Código de duas letras indicando o país onde o endereço IP do cliente está geolocalado                                                                |
| `State`                | string        | Estado em que ocorreu a login, se disponível                                                                                                  |
| `City`                 | string        | Cidade onde o usuário da conta está localizado                                                                                                          |
| `Latitude`             | string        | As coordenadas de norte para sul do local de login                                                                                          |
| `Longitude`            | string        | As coordenadas de leste para oeste do local de login                                                                                            |
| `RequestId`            | string        | Identificador exclusivo da solicitação                                                                                                                |
|`ReportId` | string | Identificador exclusivo do evento | 

 

## <a name="related-articles"></a>Artigos relacionados

-   [AADSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [Visão geral da busca avançada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Aprender a linguagem de consulta](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Compreender o esquema](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

