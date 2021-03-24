---
title: Tabela AADSignInEventsBeta no esquema de busca avançado
description: Saiba mais sobre informações associadas à tabela de eventos de login do Azure Active Directory do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, arquivo, endereço IP, dispositivo, máquina, usuário, conta, identidade, AAD
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
ms.openlocfilehash: 7b595496c28710bfa25fc88653425242770bf57f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053238"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Aplica-se a:**

- Microsoft 365 Defender

>[!IMPORTANT]
> A tabela está atualmente em beta e está sendo oferecida em curto prazo para permitir que você cace os eventos de logom do `AADSignInEventsBeta` Azure Active Directory (AAD). Eventualmente, moveremos todas as informações de esquema de login para a `IdentityLogonEvents` tabela.<br><br>
> Os clientes que podem acessar o Microsoft 365 Defender por meio da solução integrada do Microsoft Defender for Endpoint do Centro de Segurança do Azure, mas não têm licenças para o Microsoft Defender para Office, o Microsoft Defender para Identidade ou o Microsoft Cloud App Security, não poderão exibir esse esquema. 

 

A tabela no esquema de busca avançado contém informações sobre as inspeções interativas e não interativas do `AADSignInEventsBeta` Azure Active Directory. Saiba mais sobre as inscrições nos relatórios de atividade de login do [Azure Active Directory - visualização](/azure/active-directory/reports-monitoring/concept-all-sign-ins).

Use esta referência para criar consultas quer retiram informações desta tabela.
Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).

 

 

| Nome da coluna                 | Tipo de dados | Descrição          |
|---------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Timestamp`                       | datetime      | Data e hora em que o registro foi gerado                                                                                                                                         |
| `Application`                     | string        | Aplicativo que realizou a ação gravada                                                                                                                                       |
| `ApplicationId`                   | cadeia de caracteres        | Identificador exclusivo do aplicativo                                                                                                                                               |
| `LogonType`                       | cadeia de caracteres        | Tipo de sessão de logon, especificamente interativa, interativa remota (RDP), rede, lote e serviço                                                                              |
| `ErrorCode`                       | int        | Contém o código de erro se ocorrer um erro de login. Para encontrar uma descrição de um código de erro específico, visite <https://aka.ms/AADsigninsErrorCodes> .                                     |
| `CorrelationId`                   | cadeia de caracteres        | Identificador exclusivo do evento de login                                                                                                                                              |
| `SessionId`                       | cadeia de caracteres        | Número exclusivo atribuído a um usuário pelo servidor de um site durante a visita ou sessão                                                                                     |
| `AccountDisplayName`              | cadeia de caracteres        | Nome do usuário da conta exibido no livro de endereços. Normalmente, uma combinação de um nome ou nome determinado, uma inicial do meio e um sobrenome ou sobrenome.                             |
| `AccountObjectId`                 | cadeia de caracteres        | Identificador exclusivo da conta no Azure AD                                                                                                                                       |
| `AccountUpn`                      | cadeia de caracteres        | Nome principal do usuário (UPN) da conta                                                                                                                                            |
| `IsExternalUser`                  | int        | Indica se o usuário que se inscreveu é externo. Valores possíveis: -1 (não definido) , 0 (não externo), 1 (externo).                                                                   |
| `IsGuestUser`                     | booliano       | Indica se o usuário que se inscreveu é um convidado no locatário                                                                                                                  |
| `AlternateSignInName`             | cadeia de caracteres        | Nome principal do usuário local (UPN) do usuário que está se inndo no Azure AD                                                                                                            |
| `LastPasswordChangeTimestamp`     | datetime        | Data e hora em que o usuário que se inscreveu pela última vez alterou sua senha                                                                                                              |
| `ResourceDisplayName`             | cadeia de caracteres        | Nome de exibição do recurso acessado                                                                                                                                               |
| `ResourceId`                      | cadeia de caracteres        | Identificador exclusivo do recurso acessado                                                                                                                                          |
| `ResourceTenantId`                | cadeia de caracteres        | Identificador exclusivo do locatário do recurso acessado                                                                                                                            |
| `DeviceName`                      | cadeia de caracteres        | Nome de domínio totalmente qualificado (FQDN) da máquina                                                                                                                                   |
| `AadDeviceId`                     | cadeia de caracteres   |      Identificador exclusivo do dispositivo no Azure AD                                                                                                                                                                               |
| `OSPlatform`                      | string        | Plataforma do sistema operacional em execução no computador. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.  |
| `DeviceTrustType`                 | string        | Indica o tipo de confiança do dispositivo conectado. Somente para cenários de dispositivo gerenciado. Os valores possíveis são Workplace, AzureAd e ServerAd.                                     |
| `IsManaged`                       | int       | Indica se o dispositivo que iniciou a entrada é um dispositivo gerenciado (1) ou não um dispositivo gerenciado (0)                                                                         |
| `IsCompliant`                     | int       | Indica se o dispositivo que iniciou a entrada é compatível (1) ou não compatível (0)                                                                                       |
| `AuthenticationProcessingDetails` | cadeia de caracteres        | Detalhes sobre o processador de autenticação                                                                                                                                          |
| `AuthenticationRequirement`       | cadeia de caracteres        | Tipo de autenticação necessário para a assinatura. Valores possíveis: multiFactorAuthentication (MFA foi necessário) e singleFactorAuthentication (nenhum MFA foi necessário).                |
| `TokenIssuerType`                 | int        | Indica se o emissor de token é o Azure Active Directory (0) ou os Serviços de Federação do Active Directory (1)                                                                             |
| `RiskLevelAggregated`                       | int        | Nível de risco agregado durante a assinatura. Valores possíveis: 0 (nível de risco agregado não definido), 1 (nenhum), 10 (baixo), 50 (médio) ou 100 (alto).                               |
| `RiskDetails`                      | int        | Detalhes sobre o estado de risco do usuário que se inscreveu                                                                                                                            |
| `RiskState`                       | int        | Indica o estado de usuário arriscado. Valores possíveis: 0 (nenhum), 1 (seguro confirmado), 2 (remediado), 3 (ignorado), 4 (em risco) ou 5 (confirmado comprometido).                                |
| `UserAgent`                       | cadeia de caracteres        | Informações do agente do usuário do navegador da Web ou de outro aplicativo cliente                                                                                                             |
| `ClientAppUsed`                   | cadeia de caracteres        | Indica o aplicativo cliente usado                                                                                                                                                       |
| `Browser`                         | cadeia de caracteres        | Detalhes sobre a versão do navegador usado para entrar                                                                                                                            |
| `ConditionalAccessPolicies`       | cadeia de caracteres        | Detalhes das políticas de acesso condicional aplicadas ao evento de entrada                                                                                                             |
| `ConditionalAccessStatus`         | int        | Status das políticas de acesso condicional aplicadas à entrada. Os valores possíveis são 0 (políticas aplicadas), 1 (falha na tentativa de aplicar políticas) ou 2 (políticas não aplicadas).      |
| `IPAddress`                       | cadeia de caracteres        | Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas                                                                                                  |
| `Country`                     | cadeia de caracteres        | Código de duas letras indicando o país onde o endereço IP do cliente está geolocado                                                                                                    |
| `State`                           | cadeia de caracteres        | Estado em que a login ocorreu, se disponível                                                                                                                                      |
| `City`                            | cadeia de caracteres        | Cidade onde o usuário da conta está localizado                                                                                                                                              |
| `Latitude`                        | cadeia de caracteres        | As coordenadas norte a sul do local de login                                                                                                                              |
| `Longitude`                       | cadeia de caracteres        | As coordenadas de leste a oeste do local de login                                                                                                                                |
| `NetworkLocationDetails`          | cadeia de caracteres        | Detalhes de local de rede do processador de autenticação do evento de login                                                                                                       |
| `RequestId`                       | cadeia de caracteres        |  Identificador exclusivo da solicitação                                                                                                                                                   |
|`ReportId` | cadeia de caracteres | Identificador exclusivo do evento |

 

 

## <a name="related-articles"></a>Artigos relacionados

-   [AADSpnSignInEventsBeta](./advanced-hunting-aadspnsignineventsbeta-table.md)
-   [Visão geral da busca avançada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Aprender a linguagem de consulta](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Compreender o esquema](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

 