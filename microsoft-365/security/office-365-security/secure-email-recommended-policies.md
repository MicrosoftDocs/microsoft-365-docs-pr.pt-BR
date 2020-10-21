---
title: Políticas recomendadas para email seguro-Microsoft 365 for Enterprise | Microsoft docs
description: Descreve as políticas para as recomendações da Microsoft sobre como aplicar configurações e políticas de email.
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
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: c8a1609bed124789229c6ae6d1f80b7d9c70bb66
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646806"
---
# <a name="policy-recommendations-for-securing-email"></a>Recomendações de política para proteger o email

Este artigo descreve como implementar as políticas recomendadas de identidade e acesso de dispositivo para proteger emails e clientes de email organizacionais que dão suporte à autenticação moderna e acesso condicional. Este guia é baseado nas [políticas comuns de acesso a identidade e dispositivo](identity-access-policies.md) e também inclui algumas recomendações adicionais.

Essas recomendações são baseadas em três camadas diferentes de segurança e proteção que podem ser aplicadas com base na granularidade das suas necessidades: linha de **base**, **confidencial**e **altamente regulamentada**. Você pode aprender mais sobre esses níveis de segurança e os sistemas operacionais de cliente recomendada, referenciados por essas recomendações na [introdução de configurações e políticas de segurança recomendadas](microsoft-365-policies-configurations.md).

Essas recomendações exigem que seus usuários usem clientes de email modernos, incluindo Outlook para iOS e Android em dispositivos móveis. O Outlook para iOS e Android oferecem suporte aos melhores recursos do Office 365. Esses aplicativos móveis do Outlook também são arquitetados com recursos de segurança que dão suporte ao uso móvel e trabalham em conjunto com outros recursos de segurança de nuvem da Microsoft. Para obter mais informações, consulte [Outlook para IOS e perguntas frequentes sobre Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).

## <a name="update-common-policies-to-include-email"></a>Atualizar políticas comuns para incluir email

Para proteger o email, o diagrama a seguir ilustra quais políticas serão atualizadas a partir das políticas comuns de acesso de dispositivo e identidade.

[![Resumo das atualizações de política para proteger o acesso ao Microsoft Teams e seus serviços dependentes](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

[Veja uma versão maior desta imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

Observe a adição de uma nova política para o Exchange Online bloquear clientes ActiveSync. Isso força o uso do Outlook Mobile.

Se você incluiu o Exchange Online e o Outlook no escopo das políticas quando as configurou, só precisará criar a nova política para bloquear clientes ActiveSync. Revise as políticas listadas na tabela a seguir e faça as adições recomendadas ou confirme se elas já estão incluídas. Cada política vincula as instruções de configuração associadas em [políticas comuns de acesso de dispositivo e identidade](identity-access-policies.md).

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
|**Altamente controlado**|[*Sempre* exigir MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir o Exchange Online na atribuição de aplicativos de nuvem|

## <a name="block-activesync-clients"></a>Bloquear clientes ActiveSync

Essa política impede que os clientes do ActiveSync ignorem outras políticas de acesso condicional. A configuração de política se aplica apenas aos clientes do ActiveSync. Ao selecionar **[exigir política de proteção de aplicativo](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**, essa política bloqueia clientes ActiveSync. Detalhes sobre como criar essa política podem ser encontrados em [exigir política de proteção de aplicativo para acesso de aplicativo em nuvem com acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

- Siga a etapa 2: configurar uma política de acesso condicional do Azure AD para o Exchange Online com o ActiveSync (EAS) "no [cenário 1: os aplicativos do Office 365 exigem aplicativos aprovados com políticas de proteção de aplicativos](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), o que impede que os clientes do Exchange ActiveSync aproveitem a autenticação básica para se conectar ao Exchange Online.

Você também pode usar as políticas de autenticação para [desabilitar a autenticação básica](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), o que força todas as solicitações de acesso para cliente a usar a autenticação moderna.

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Limitar o acesso ao Exchange Online do Outlook na Web

Você pode restringir a capacidade dos usuários de baixar anexos do Outlook na Web em dispositivos umnanaged. Os usuários desses dispositivos podem exibir e editar esses arquivos usando o Office Online sem vazar e armazenar os arquivos no dispositivo. Você também pode impedir que os usuários vejam anexos em um dispositivo não gerenciado.

Estas são as etapas:

1. [Conecte-se a uma sessão do PowerShell remoto do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).
2. Se você ainda não tiver uma política de caixa de correio do OWA, crie uma com o cmdlet [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) .
3. Se você quiser permitir a exibição de anexos, mas não baixar, use este comando:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. Se você deseja bloquear anexos, use este comando:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

4. No portal do Azure, crie uma nova política de acesso condicional com estas configurações:

   **Atribuições > usuários e grupos**: selecione usuários e grupos apropriados para incluir e excluir.

   **Atribuições > aplicativos ou ações em nuvem > aplicativos de nuvem > incluem > selecionar aplicativos**: selecione **Office 365 Exchange Online**

   **Controles de acesso > sessão**: selecionar **usar restrições impostas do aplicativo**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>Exigir que os dispositivos iOS e Android usem o Outlook

Para garantir que os usuários de dispositivos iOS e Android só possam acessar o conteúdo do trabalho ou da escola usando o Outlook para iOS e Android, você precisará de uma política de acesso condicional que tenha como destino os usuários em potencial.

Consulte as etapas para configurar essa política em [gerenciar o acesso à colaboração de mensagens usando o Outlook para IOS e Android]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access).


## <a name="set-up-message-encryption"></a>Configurar a criptografia de mensagens

Com os novos recursos de criptografia de mensagens do Office 365 (OME), que aproveitam os recursos de proteção na proteção de informações do Azure, sua organização pode compartilhar facilmente email protegido com qualquer pessoa em qualquer dispositivo. Os usuários podem enviar e receber mensagens protegidas com outras organizações do Microsoft 365, bem como não clientes usando o Outlook.com, o Gmail e outros serviços de email.

Para obter mais informações, consulte [configurar novos recursos de criptografia de mensagem do Office 365](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).

## <a name="next-steps"></a>Próximas etapas

![Etapa 4: políticas para aplicativos em nuvem da Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configure as políticas de acesso condicional para:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
