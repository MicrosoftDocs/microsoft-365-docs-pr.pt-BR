---
title: Políticas de documentos seguros recomendadas-Microsoft 365 for Enterprise | Microsoft docs
description: Descreve as políticas para as recomendações da Microsoft sobre como proteger o acesso a arquivos do SharePoint.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 1c6cdc626b31a486b8858efcff76480d31769740
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547796"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Recomendações de política para proteger sites e arquivos do SharePoint

Este artigo descreve como implementar a identidade recomendada e as políticas de acesso a dispositivos para proteger o SharePoint e o OneDrive for Business. Este guia é baseado nas [políticas comuns de acesso de dispositivo e identidade](identity-access-policies.md).

Essas recomendações são baseadas em três camadas diferentes de segurança e proteção para arquivos do SharePoint que podem ser aplicadas com base na granularidade das suas necessidades: **Baseline**, **sensitive**e **High Regulation**. Você pode saber mais sobre essas camadas de segurança e os sistemas operacionais de cliente recomendados, mencionados por essas recomendações na [visão geral](microsoft-365-policies-configurations.md).

Além de implementar essas orientações, não deixe de configurar os sites do SharePoint com a quantidade certa de proteção, incluindo a definição de permissões apropriadas para conteúdo confidencial e altamente regulamentado.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Atualizando políticas comuns para incluir o SharePoint e o OneDrive for Business

Para proteger arquivos no SharePoint e no OneDrive, o diagrama a seguir ilustra quais políticas serão atualizadas a partir das políticas comuns de acesso de dispositivo e identidade.

[![Resumo das atualizações de política para proteger o acesso ao Microsoft Teams e seus serviços dependentes](../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

[Veja uma versão maior desta imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

Se você incluiu o SharePoint ao criar as políticas comuns, só precisará criar as novas diretivas. Para políticas de acesso condicional, o SharePoint inclui o OneDrive.

As novas políticas implementam a proteção de dispositivos para conteúdos confidenciais e altamente regulamentados aplicando requisitos de acesso específicos a sites do SharePoint que você especificar.

A tabela a seguir lista as políticas que você precisa analisar e atualizar ou criar novas para o SharePoint. O link de políticas comuns para as instruções de configuração associadas no artigo [Common Identity and Device Access Policies](identity-access-policies.md) .

|Nível de Proteção|Políticas|Mais informações|
|:---------------|:-------|:----------------|
|**Baseline**|[Exigir MFA quando o risco de entrada for *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir o SharePoint na atribuição de aplicativos em nuvem.|
|        |[Bloquear clientes sem suporte para a autenticação moderna](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Incluir o SharePoint na atribuição de aplicativos em nuvem.|
|        |[Aplicar políticas de proteção de dados do aplicativo](identity-access-policies.md#apply-app-data-protection-policies)|Certifique-se de que todos os aplicativos recomendados estão incluídos na lista de aplicativos. Certifique-se de atualizar a política para cada plataforma (iOS, Android, Windows).|
|        |[Exigir PCs compatíveis](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Incluir o SharePoint na lista de aplicativos em nuvem.|
|        |[Usar restrições impostas pelo aplicativo no SharePoint](#use-app-enforced-restrictions-in-sharepoint)|Adicione essa nova política. Isso informa ao Azure Active Directory (Azure AD) para usar as configurações especificadas no SharePoint. Essa política se aplica a todos os usuários, mas afeta apenas o acesso aos sites incluídos nas políticas de acesso do SharePoint.|
|**Confidencial**|[Exigir MFA quando o risco de entrada for *baixo*, *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir o SharePoint nas atribuições de aplicativos em nuvem.|
|         |[Exigir computadores *em conformidade e* dispositivos móveis](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Inclua o SharePoint na lista de aplicativos em nuvem.|
||[Política de controle de acesso do SharePoint](#sharepoint-access-control-policies): permitir acesso somente ao navegador para sites específicos do SharePoint de dispositivos não gerenciados.|Isso impede a edição e o download de arquivos. Use o PowerShell para especificar sites.|
|**Altamente controlado**|[*Sempre* exigir MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir o SharePoint na atribuição de aplicativos em nuvem.|
||[Política de controle de acesso do SharePoint](#use-app-enforced-restrictions-in-sharepoint): bloquear o acesso a sites do SharePoint específicos de dispositivos não gerenciados.|Use o PowerShell para especificar sites.|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>Usar restrições impostas pelo aplicativo no SharePoint

Se você implementar controles de acesso no SharePoint, você deve criar essa política de acesso condicional no Azure AD para informar ao Azure AD para impor as políticas que você configura no SharePoint. Essa política se aplica a todos os usuários, mas afeta apenas o acesso aos sites especificados usando o PowerShell quando você cria os controles de acesso no SharePoint.

Para configurar esta política, consulte "bloquear ou limitar o acesso a conjuntos de sites do SharePoint ou contas do OneDrive específicos" em [controlar o acesso de dispositivos não gerenciados](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

## <a name="sharepoint-access-control-policies"></a>Políticas de controle de acesso do SharePoint

A Microsoft recomenda que você proteja o conteúdo em sites do SharePoint com conteúdo confidencial e altamente regulamentado com controles de acesso do dispositivo. Você faz isso criando uma política que especifica o nível de proteção e os sites aos quais aplicar a proteção.

- Sites confidenciais: permitir acesso somente para navegador. Isso impede que os usuários editem e baixem arquivos.
- Sites altamente regulamentados: bloquear o acesso de dispositivos não gerenciados.

Consulte "bloquear ou limitar o acesso a conjuntos de sites do SharePoint ou contas do OneDrive específicos" em [controlar o acesso de dispositivos não gerenciados](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

## <a name="how-these-policies-work-together"></a>Como essas políticas funcionam juntas

É importante entender que as permissões do site do SharePoint normalmente são baseadas nas necessidades comerciais de acesso aos sites. Essas permissões são gerenciadas por proprietários de site e podem ser altamente dinâmicas. Usar as políticas de acesso de dispositivo do SharePoint garante a proteção desses sites, independentemente de os usuários serem atribuídos a um grupo do Azure AD associado à proteção de linha de base, confidencial ou altamente regulamentada.

A ilustração a seguir fornece um exemplo de como as políticas de acesso de dispositivo do SharePoint protegem o acesso a sites de um usuário.

[![Exemplo de como as políticas de acesso de dispositivo do SharePoint protegem os sites](../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[Veja uma versão maior desta imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

James tem políticas de acesso condicional de linha de base atribuídas, mas pode receber acesso a sites do SharePoint com proteção confidencial ou altamente regulamentada.

- Se James acessar um site confidencial ou altamente regulamentado, ele é membro do uso de seu computador, seu acesso é concedido enquanto o computador estiver em conformidade.
- Se James acessar um site confidencial que é membro de usar seu telefone não gerenciado, que é permitido para usuários de linha de base, ele receberá acesso somente ao navegador ao site confidencial devido à política de acesso do dispositivo configurada para este site.
- Se James acessar um site altamente regulamentado, ele é membro do uso de seu telefone não gerenciado, ele será bloqueado devido à política de acesso configurada para este site. Ele só pode acessar esse site usando seu computador gerenciado e compatível.

## <a name="next-step"></a>Próxima etapa

![Etapa 4: políticas para aplicativos em nuvem da Microsoft 365](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configure as políticas de acesso condicional para:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)

