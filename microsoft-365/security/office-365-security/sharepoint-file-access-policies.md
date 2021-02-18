---
title: Políticas de documentos seguros recomendadas - Microsoft 365 para empresas | Microsoft Docs
description: Descreve as políticas para as recomendações da Microsoft sobre como proteger o acesso a arquivos do SharePoint.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: f3a9cc2c3bae32a8fee10e814f96968b864e78a5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290412"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Recomendações de política para proteger arquivos e sites do SharePoint

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- SharePoint Online 


Este artigo descreve como implementar as políticas de acesso a dispositivos e identidade recomendadas para proteger o SharePoint e o OneDrive for Business. Essa orientação se baseia nas políticas comuns de acesso a dispositivos [e identidades.](identity-access-policies.md)

Essas recomendações são baseadas em três camadas diferentes de segurança e proteção para arquivos do SharePoint que podem ser aplicadas com base na granularidade de suas **necessidades:** linha de **base,** sensível e altamente **controlada.** Você pode saber mais sobre essas camadas de segurança e os sistemas operacionais cliente recomendados, referenciados por estas recomendações [na visão geral.](microsoft-365-policies-configurations.md)

Além de implementar essas diretrizes, certifique-se de configurar sites do SharePoint com a quantidade certa de proteção, incluindo a configuração de permissões apropriadas para conteúdo altamente regulamentado e confidenciais.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Atualizando políticas comuns para incluir o SharePoint e o OneDrive for Business

Para proteger arquivos no SharePoint e no OneDrive, o diagrama a seguir ilustra quais políticas atualizar a partir das políticas comuns de identidade e acesso ao dispositivo.

[![Resumo das atualizações de política para proteger o acesso ao Teams e seus serviços dependentes](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

[Ver uma versão maior desta imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

Se você incluiu o SharePoint ao criar as políticas comuns, só precisará criar as novas políticas. Para políticas de Acesso Condicional, o SharePoint inclui o OneDrive.

As novas políticas implementam a proteção de dispositivos para conteúdo altamente regulamentado e confidenciais aplicando requisitos de acesso específicos aos sites do SharePoint especificados por você.

A tabela a seguir lista as políticas que você precisa revisar e atualizar ou criar novas para o SharePoint. As políticas comuns vinculam-se às instruções de configuração associadas no artigo De identidade [comum e políticas de acesso a dispositivos.](identity-access-policies.md)

|Nível de Proteção|Políticas|Mais informações|
|---|---|---|
|**Baseline**|[Exigir MFA quando o risco de login for *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inclua o SharePoint na atribuição de aplicativos de nuvem.|
||[Bloquear clientes sem suporte para a autenticação moderna](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Inclua o SharePoint na atribuição de aplicativos de nuvem.|
||[Aplicar políticas de proteção de dados app](identity-access-policies.md#apply-app-data-protection-policies)|Certifique-se de que todos os aplicativos recomendados estão incluídos na lista de aplicativos. Certifique-se de atualizar a política para cada plataforma (iOS, Android, Windows).|
||[Exigir PCs compatíveis](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Inclua o SharePoint na lista de aplicativos de nuvem.|
||[Usar restrições impostas pelo aplicativo no SharePoint](#use-app-enforced-restrictions-in-sharepoint)|Adicione esta nova política. Isso informa ao Azure Active Directory (Azure AD) para usar as configurações especificadas no SharePoint. Essa política se aplica a todos os usuários, mas afeta apenas o acesso a sites incluídos nas políticas de acesso do SharePoint.|
|**Confidencial**|[Exigir MFA quando o risco de login for *baixo,* *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inclua o SharePoint nas atribuições de aplicativos de nuvem.|
||[Exigir PCs e dispositivos *móveis compatíveis*](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Inclua o SharePoint na lista de aplicativos de nuvem.|
||[Política de controle de acesso do SharePoint:](#sharepoint-access-control-policies)permitir acesso somente do navegador a sites específicos do SharePoint de dispositivos não controlados.|Isso impede a edição e o download de arquivos. Use o PowerShell para especificar sites.|
|**Altamente controlado**|[*Sempre* exigir MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inclua o SharePoint na atribuição de aplicativos de nuvem.|
||[Política de controle de acesso do SharePoint:](#use-app-enforced-restrictions-in-sharepoint)bloquear o acesso a sites específicos do SharePoint de dispositivos não controlados.|Use o PowerShell para especificar sites.|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>Usar restrições impostas pelo aplicativo no SharePoint

Se você implementar controles de acesso no SharePoint, deverá criar essa política de Acesso Condicional no Azure AD para dizer ao Azure AD para impor as políticas configuradas no SharePoint. Essa política se aplica a todos os usuários, mas afeta apenas o acesso aos sites especificados usando o PowerShell quando você cria os controles de acesso no SharePoint.

Para configurar essa política, consulte "Bloquear ou limitar o acesso a determinados conjunto de sites do SharePoint ou contas do OneDrive" no Controle de acesso de dispositivos [não-controlados.](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)

## <a name="sharepoint-access-control-policies"></a>Políticas de controle de acesso do SharePoint

A Microsoft recomenda que você proteja o conteúdo em sites do SharePoint com conteúdo altamente regulamentado e confidenciais com controles de acesso a dispositivos. Você faz isso criando uma política que especifica o nível de proteção e os sites aos que aplicar a proteção.

- Sites confidenciais: permitir acesso somente do navegador. Isso impede que os usuários editem e baixem arquivos.
- Sites altamente regulamentados: bloquear o acesso de dispositivos não autorizados.

Consulte "Bloquear ou limitar o acesso a determinados conjunto de sites do SharePoint ou contas do OneDrive" no Controle de acesso de dispositivos [não-controlados.](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)

## <a name="how-these-policies-work-together"></a>Como essas políticas funcionam em conjunto

É importante entender que as permissões do site do SharePoint são normalmente baseadas na necessidade comercial de acesso aos sites. Essas permissões são gerenciadas por proprietários de sites e podem ser altamente dinâmicas. O uso de políticas de acesso a dispositivos do SharePoint garante a proteção a esses sites, independentemente de os usuários estar atribuídos a um grupo do Azure AD associado à proteção de linha de base, confidenciais ou altamente controladas.

A ilustração a seguir fornece um exemplo de como as políticas de acesso a dispositivos do SharePoint protegem o acesso aos sites de um usuário.

[![Exemplo de como as políticas de acesso a dispositivos do SharePoint protegem sites](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[Ver uma versão maior desta imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

Ele tem políticas de Acesso Condicional de linha de base atribuídas, mas pode ter acesso a sites do SharePoint com proteção altamente regulamentada ou sensível.

- Se o James acessar um site altamente regulamentado ou sensível, ele é membro do uso de seu computador, seu acesso será concedido desde que seu computador seja compatível.
- Se o James acessar um site sensível, ele é membro do uso de seu telefone não-autorizado, o que é permitido para usuários de linha de base, ele receberá acesso somente do navegador ao site sensível devido à política de acesso de dispositivo configurada para esse site.
- Se Paulo Araúque acessar um site altamente regulamentado, ele será membro do uso de seu telefone não autorizado, ele será bloqueado devido à política de acesso configurada para este site. Ele só pode acessar esse site usando seu computador gerenciado e compatível.

## <a name="next-step"></a>Próxima etapa

![Etapa 4: Políticas para aplicativos de nuvem do Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configurar políticas de Acesso Condicional para:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
