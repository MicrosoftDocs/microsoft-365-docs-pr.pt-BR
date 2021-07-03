---
title: Tabela AADSignInEventsBeta no esquema de busca avançado
description: Saiba mais sobre informações associadas Azure Active Directory tabela de eventos de login do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, arquivo, endereço IP, dispositivo, máquina, usuário, conta, identidade, AAD
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
ms.openlocfilehash: edc9a1e40275631752ca1252a16071f4b07f07f9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286322"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> A tabela está atualmente em beta e está sendo oferecida em curto prazo para permitir que você cace os eventos de Azure Active Directory `AADSignInEventsBeta` (AAD). Eventualmente, moveremos todas as informações de esquema de login para a `IdentityLogonEvents` tabela.

A tabela no esquema de busca avançada contém informações sobre Azure Active Directory de `AADSignInEventsBeta` logins interativos e não interativos. Saiba mais sobre entrar em Azure Active Directory relatórios de atividade de login [- visualização](/azure/active-directory/reports-monitoring/concept-all-sign-ins).

Use esta referência para criar consultas quer retiram informações desta tabela. Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).

<br>

****

|Nome da coluna|Tipo de dados|Descrição|
|---|---|---|
|`Timestamp`|datetime|Data e hora em que o registro foi gerado|
|`Application`|string|Aplicativo que realizou a ação gravada|
|`ApplicationId`|string|Identificador exclusivo do aplicativo|
|`LogonType`|string|Tipo de sessão de logon, especificamente interativa, interativa remota (RDP), rede, lote e serviço|
|`ErrorCode`|int|Contém o código de erro se ocorrer um erro de login. Para encontrar uma descrição de um código de erro específico, visite <https://aka.ms/AADsigninsErrorCodes> .|
|`CorrelationId`|string|Identificador exclusivo do evento de login|
|`SessionId`|string|Número exclusivo atribuído a um usuário pelo servidor de um site durante a visita ou sessão|
|`AccountDisplayName`|string|Nome do usuário da conta exibido no livro de endereços. Normalmente, uma combinação de um nome ou nome determinado, uma inicial do meio e um sobrenome ou sobrenome.|
|`AccountObjectId`|string|Identificador exclusivo da conta no Azure AD|
|`AccountUpn`|string|Nome principal do usuário (UPN) da conta|
|`IsExternalUser`|int|Indica se o usuário que se inscreveu é externo. Valores possíveis: -1 (não definido), 0 (não externo), 1 (externo).|
|`IsGuestUser`|booliano|Indica se o usuário que se inscreveu é um convidado no locatário|
|`AlternateSignInName`|string|Nome principal do usuário local (UPN) do usuário que está se inndo no Azure AD|
|`LastPasswordChangeTimestamp`|datetime|Data e hora em que o usuário que se inscreveu pela última vez alterou sua senha|
|`ResourceDisplayName`|string|Nome de exibição do recurso acessado|
|`ResourceId`|string|Identificador exclusivo do recurso acessado|
|`ResourceTenantId`|string|Identificador exclusivo do locatário do recurso acessado|
|`DeviceName`|string|Nome de domínio totalmente qualificado (FQDN) da máquina|
|`AadDeviceId`|string|Identificador exclusivo do dispositivo no Azure AD|
|`OSPlatform`|string|Plataforma do sistema operacional em execução no computador. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.|
|`DeviceTrustType`|string|Indica o tipo de confiança do dispositivo conectado. Somente para cenários de dispositivo gerenciado. Os valores possíveis são Workplace, AzureAd e ServerAd.|
|`IsManaged`|int|Indica se o dispositivo que iniciou a entrada é um dispositivo gerenciado (1) ou não um dispositivo gerenciado (0)|
|`IsCompliant`|int|Indica se o dispositivo que iniciou a entrada é compatível (1) ou não compatível (0)|
|`AuthenticationProcessingDetails`|string|Detalhes sobre o processador de autenticação|
|`AuthenticationRequirement`|string|Tipo de autenticação necessário para a assinatura. Valores possíveis: multiFactorAuthentication (MFA foi necessário) e singleFactorAuthentication (nenhum MFA foi necessário).|
|`TokenIssuerType`|int|Indica se o emissor de token é Azure Active Directory (0) ou Serviços de Federação do Active Directory (1)|
|`RiskLevelAggregated`|int|Nível de risco agregado durante a assinatura. Valores possíveis: 0 (nível de risco agregado não definido), 1 (nenhum), 10 (baixo), 50 (médio) ou 100 (alto).|
|`RiskDetails`|int|Detalhes sobre o estado de risco do usuário que se inscreveu|
|`RiskState`|int|Indica o estado de usuário arriscado. Valores possíveis: 0 (nenhum), 1 (seguro confirmado), 2 (remediado), 3 (ignorado), 4 (em risco) ou 5 (confirmado comprometido).|
|`UserAgent`|string|Informações do agente do usuário do navegador da Web ou de outro aplicativo cliente|
|`ClientAppUsed`|string|Indica o aplicativo cliente usado|
|`Browser`|string|Detalhes sobre a versão do navegador usado para entrar|
|`ConditionalAccessPolicies`|string|Detalhes das políticas de acesso condicional aplicadas ao evento de entrada|
|`ConditionalAccessStatus`|int|Status das políticas de acesso condicional aplicadas à entrada. Os valores possíveis são 0 (políticas aplicadas), 1 (falha na tentativa de aplicar políticas) ou 2 (políticas não aplicadas).|
|`IPAddress`|string|Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas|
|`Country`|string|Código de duas letras indicando o país onde o endereço IP do cliente está geolocado|
|`State`|string|Estado em que a login ocorreu, se disponível|
|`City`|string|Cidade onde o usuário da conta está localizado|
|`Latitude`|string|As coordenadas norte a sul do local de login|
|`Longitude`|string|As coordenadas de leste a oeste do local de login|
|`NetworkLocationDetails`|string|Detalhes de local de rede do processador de autenticação do evento de login|
|`RequestId`|string|Identificador exclusivo da solicitação|
|`ReportId`|string|Identificador exclusivo do evento|
|

## <a name="related-articles"></a>Artigos relacionados

- [AADSpnSignInEventsBeta](./advanced-hunting-aadspnsignineventsbeta-table.md)
- [Visão geral da busca avançada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [Aprender a linguagem de consulta](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
- [Compreender o esquema](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
