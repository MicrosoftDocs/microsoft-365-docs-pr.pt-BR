---
title: Políticas de documento seguro recomendadas – Microsoft 365 Enterprise | Microsoft Docs
description: Descreve as políticas para as recomendações da Microsoft sobre como proteger o acesso a arquivos do SharePoint.
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 6429c3dee32087d6e82a427b2f374ec49bab5cac
ms.sourcegitcommit: 98782ee4497d72232462c51a3071fae313282980
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44222680"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Recomendações de política para proteger sites e arquivos do SharePoint

Este artigo descreve como implementar a identidade recomendada e as políticas de acesso a dispositivos para proteger o SharePoint Online e o OneDrive for Business. Este guia é baseado nas [políticas comuns de acesso de dispositivo e identidade](identity-access-policies.md).

Essas recomendações são baseadas em três camadas diferentes de segurança e proteção para arquivos do SharePoint que podem ser aplicadas com base na granularidade das suas necessidades: **Baseline**, **sensitive**e **High Regulation**. Você pode saber mais sobre essas camadas de segurança e os sistemas operacionais de cliente recomendados, mencionados por essas recomendações na [visão geral](microsoft-365-policies-configurations.md).

Além de implementar essas orientações, não deixe de configurar os sites do SharePoint com a quantidade certa de proteção, incluindo a definição de permissões apropriadas para conteúdo confidencial e altamente regulamentado. Para obter mais informações sobre a criação de sites para proteção de linha de base, confidencial e altamente regulamentada, consulte [proteger sites e arquivos do SharePoint Online](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files).

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Atualizando políticas comuns para incluir o SharePoint e o OneDrive for Business

O diagrama a seguir ilustra o conjunto de políticas recomendadas para proteger arquivos no SharePoint Online e no OneDrive for Business. Ele indica quais políticas devem ser atualizadas ou recém-criadas para adicionar proteção para o SharePoint Online e o OneDrive for Business.

![Resumo das políticas do SharePoint Online e do OneDrive](../media/identity-access-ruleset-sharepoint.png)

Se você tiver incluído o SharePoint Online quando criou as políticas comuns, só precisará criar as novas políticas. Ao configurar regras de acesso condicional, o SharePoint Online inclui o OneDrive for Business.

As novas políticas implementam a proteção de dispositivos para conteúdos confidenciais e altamente regulamentados aplicando requisitos de acesso específicos a sites do SharePoint que você especificar.

A tabela a seguir lista as políticas que você precisa analisar e atualizar ou criar novas para o SharePoint Online. O link de políticas comuns para as instruções de configuração associadas no artigo [Common Identity and Device Access Policies](identity-access-policies.md) .

|Nível de Proteção|Políticas|Mais informações|
|:---------------|:-------|:----------------|
|**Baseline**|[Exigir MFA quando o risco de entrada for *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir o SharePoint Online na atribuição de aplicativos de nuvem|
|        |[Bloquear clientes sem suporte para a autenticação moderna](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Incluir o SharePoint Online na atribuição de aplicativos de nuvem|
|        |[Aplicar políticas de proteção de dados do aplicativo](identity-access-policies.md#apply-app-data-protection-policies)|Certifique-se de que todos os aplicativos recomendados estão incluídos na lista de aplicativos. Certifique-se de atualizar a política para cada plataforma (iOS, Android, Windows)|
|        |[Exigir PCs compatíveis](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Incluir o SharePoint Online na lista de aplicativos em nuvem|
|        |[Usar restrições impostas pelo aplicativo no SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online)|Adicione essa nova política. Isso informa ao Azure AD para usar as configurações especificadas no SharePoint Online. Esta regra se aplica a todos os usuários, mas afeta apenas o acesso aos sites incluídos nas políticas de acesso do SharePoint Online|
|**Confidencial**|[Exigir MFA quando o risco de entrada for *baixo*, *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir o SharePoint Online nas atribuições de aplicativos em nuvem|
|         |[Exigir computadores *em conformidade e* dispositivos móveis](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Incluir o SharePoint Online na lista de aplicativos em nuvem|
||[Política de controle de acesso do SharePoint Online](#sharepoint-online-access-control-policies): permitir acesso somente ao navegador para sites específicos do SharePoint de dispositivos não gerenciados|Isso impede a edição e o download de arquivos. Usar o PowerShell para especificar sites|
|**Altamente controlada**|[*Sempre* exigir MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir o SharePoint Online na atribuição de aplicativos de nuvem|
||[Política de controle de acesso do SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online): bloquear o acesso a sites específicos do SharePoint de dispositivos não gerenciados|Usar o PowerShell para especificar sites|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>Usar restrições impostas pelo aplicativo no SharePoint Online

Se você implementar controles de acesso no SharePoint Online, você deve criar essa política de acesso condicional no Azure AD para informar ao Azure AD para impor as políticas que você configurou no SharePoint Online. Essa regra se aplica a todos os usuários, mas afeta apenas o acesso aos sites especificados usando o PowerShell quando você cria os controles de acesso no SharePoint Online.

Para configurar esta política, consulte "bloquear ou limitar o acesso a conjuntos de sites do SharePoint ou contas do OneDrive específicos" neste artigo: [controlar o acesso de dispositivos não gerenciados](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

## <a name="sharepoint-online-access-control-policies"></a>Políticas de controle de acesso do SharePoint Online

A Microsoft recomenda que você proteja o conteúdo em sites do SharePoint com conteúdo confidencial e altamente regulamentado com controles de acesso do dispositivo. Você faz isso criando uma política que especifica o nível de proteção e os sites aos quais aplicar a proteção.

- Sites confidenciais: permitir acesso somente para navegador. Isso impede que os usuários editem e baixem arquivos.
- Sites altamente regulamentados: bloquear o acesso de dispositivos não gerenciados.

Consulte "bloquear ou limitar o acesso a conjuntos de sites do SharePoint ou contas do OneDrive específicos" neste artigo: [controlar o acesso de dispositivos não gerenciados](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

## <a name="how-these-policies-work-together"></a>Como essas políticas funcionam juntas

É importante entender que as permissões do site do SharePoint normalmente são baseadas nas necessidades comerciais de acesso aos sites. Essas permissões são gerenciadas por proprietários de site e podem ser altamente dinâmicas. Usar as políticas de acesso de dispositivo do SharePoint garante a proteção desses sites, independentemente de os usuários serem atribuídos a um grupo do Azure AD associado à proteção de linha de base, confidencial ou altamente regulamentada.

A ilustração a seguir fornece um exemplo de como as políticas de acesso de dispositivo do SharePoint protegem o acesso a sites.

![Como as políticas de acesso de dispositivo do SharePoint protegem sites](../media/SharePoint-rules-scenario.png)

Na ilustração:

- James é atribuído às políticas de acesso condicional associadas à proteção de linha de base, mas pode receber acesso a sites do SharePoint associados à proteção confidencial ou de alta regulamentações.
- Se James acessar um site confidencial ou altamente regulamentado, ele é membro do uso de seu computador, seu acesso é concedido enquanto o computador estiver em conformidade.
- Se James acessar um site confidencial que é membro de usar seu telefone não gerenciado, que é permitido para usuários de linha de base, ele receberá acesso somente ao navegador ao site confidencial devido à política de acesso do dispositivo configurada para este site.
- Se James acessar um site altamente regulamentado, ele é membro do uso de seu telefone não gerenciado, ele será bloqueado devido à política de acesso configurada para este site. Ele só pode acessar esse site usando seu computador gerenciado e compatível.

## <a name="next-steps"></a>Próximas etapas

[Proteger arquivos e sites do SharePoint Online](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
