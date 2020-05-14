---
title: Políticas recomendadas para email seguro – Microsoft 365 Enterprise | Microsoft Docs
description: Descreve as políticas para as recomendações da Microsoft sobre como aplicar configurações e políticas de email.
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
ms.openlocfilehash: e469f0d1c0be85aeb5f98a4f2e6e2758cddd8450
ms.sourcegitcommit: 98782ee4497d72232462c51a3071fae313282980
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44222692"
---
# <a name="policy-recommendations-for-securing-email"></a>Recomendações de política para proteger o email

Este artigo descreve como implementar as políticas recomendadas de identidade e acesso de dispositivo para proteger emails e clientes de email organizacionais que dão suporte à autenticação moderna e acesso condicional. Este guia é baseado nas [políticas comuns de acesso a identidade e dispositivo](identity-access-policies.md) e também inclui algumas recomendações adicionais.

Essas recomendações são baseadas em três camadas diferentes de segurança e proteção que podem ser aplicadas com base na granularidade das suas necessidades: linha de **base**, **confidencial**e **altamente regulamentada**. Você pode aprender mais sobre esses níveis de segurança e os sistemas operacionais de cliente recomendada, referenciados por essas recomendações na [introdução de configurações e políticas de segurança recomendadas](microsoft-365-policies-configurations.md).

Essas recomendações exigem que seus usuários usem clientes de email modernos, incluindo Outlook para iOS e Android em dispositivos móveis. O Outlook para iOS e Android oferecem suporte aos melhores recursos do Office 365. Esses aplicativos móveis do Outlook também são arquitetados com recursos de segurança que dão suporte ao uso móvel e trabalham em conjunto com outros recursos de segurança de nuvem da Microsoft. Para obter mais informações, consulte [Outlook para IOS e perguntas frequentes sobre Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).

## <a name="updating-common-policies-to-include-email"></a>Atualizando políticas comuns para incluir email

O diagrama a seguir ilustra as políticas comuns de acesso de dispositivo e identidades e indica quais políticas precisam ser atualizadas para proteger o email. Observe a adição de uma nova regra para o Exchange Online bloquear clientes ActiveSync. Isso força o uso do Outlook Mobile.

![Resumo das atualizações de política para proteção de email](../media/identity-access-ruleset-mail.png)

Se você incluiu o Exchange Online e o Outlook no escopo das políticas quando as configurou, só precisará criar a nova política para bloquear clientes ActiveSync. Revise as políticas listadas na tabela a seguir e faça as adições recomendadas ou confirme se elas já estão incluídas. Cada regra vincula as instruções de configuração associadas no artigo [Common Identity and Device Access Policies](identity-access-policies.md) .

|Nível de Proteção|Políticas|Mais informações|
|:---------------|:-------|:----------------|
|**Baseline**|[Exigir MFA quando o risco de entrada for *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir o Exchange Online na atribuição de aplicativos de nuvem|
|        |[Bloquear clientes sem suporte para a autenticação moderna](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Incluir o Exchange Online na atribuição de aplicativos de nuvem|
|        |[Aplicar políticas de proteção de dados do aplicativo](identity-access-policies.md#apply-app-data-protection-policies)|Certifique-se de que o Outlook esteja incluído na lista de aplicativos. Certifique-se de atualizar a política para cada plataforma (iOS, Android, Windows)|
|        |[Exigir aplicativos aprovados e proteção de aplicativos](identity-access-policies.md#require-approved-apps-and-app-protection)|Incluir o Exchange Online na lista de aplicativos em nuvem|
|        |[Exigir PCs compatíveis](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Incluir o Exchange Online na lista de aplicativos em nuvem|
|        |[Bloquear clientes ActiveSync](#block-activesync-clients)|Adicionar esta nova política| 
|**Confidencial**|[Exigir MFA quando o risco de entrada for *baixo*, *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| Incluir o Exchange Online na atribuição de aplicativos de nuvem|
|         |[Exigir computadores *em conformidade e* dispositivos móveis](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Incluir o Exchange Online na lista de aplicativos em nuvem|
|**Altamente controlada**|[*Sempre* exigir MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir o Exchange Online na atribuição de aplicativos de nuvem|

## <a name="block-activesync-clients"></a>Bloquear clientes ActiveSync

Essa política impede que os clientes do ActiveSync ignorem outras regras de acesso condicional. A configuração de regra só se aplica aos clientes do ActiveSync. Ao selecionar **[exigir política de proteção de aplicativo](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**, essa política bloqueia clientes ActiveSync. Detalhes sobre como criar essa política podem ser encontrados em [exigir política de proteção de aplicativo para acesso de aplicativo em nuvem com acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Siga a etapa 2: configurar uma política de acesso condicional do Azure AD para o Exchange Online com o ActiveSync (EAS) "no [cenário 1: os aplicativos do Office 365 exigem aplicativos aprovados com políticas de proteção de aplicativos](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), o que impede que os clientes do Exchange ActiveSync aproveitem a autenticação básica para se conectar ao Exchange Online.

## <a name="set-up-message-encryption"></a>Configurar a criptografia de mensagens

Com os novos recursos de criptografia de mensagens do Office 365 (OME), que aproveitam os recursos de proteção na proteção de informações do Azure, sua organização pode compartilhar facilmente email protegido com qualquer pessoa em qualquer dispositivo. Os usuários podem enviar e receber mensagens protegidas com outras organizações do Microsoft 365, bem como não clientes usando o Outlook.com, o Gmail e outros serviços de email.

Para obter mais informações, consulte [configurar novos recursos de criptografia de mensagem do Office 365](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).

## <a name="next-steps"></a>Próximas etapas

[Saiba mais sobre as recomendações de política para proteger arquivos e sites do SharePoint](sharepoint-file-access-policies.md)
