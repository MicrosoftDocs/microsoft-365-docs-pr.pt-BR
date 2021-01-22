---
title: Políticas recomendadas de email seguro - Microsoft 365 para empresas | Microsoft Docs
description: Descreve as políticas para as recomendações da Microsoft sobre como aplicar configurações e políticas de email.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
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
ms.technology: mdo
ms.openlocfilehash: f3654762bf4d4c28a82b1e93829094b9e0386a60
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926517"
---
# <a name="policy-recommendations-for-securing-email"></a>Recomendações de política para proteger o email

Este artigo descreve como implementar as políticas de acesso a dispositivos e identidade recomendadas para proteger clientes de email e email organizacionais que suportam autenticação moderna e acesso condicional. Essa orientação se baseia nas políticas [comuns](identity-access-policies.md) de acesso a dispositivos e identidade e também inclui algumas recomendações adicionais.

Essas recomendações são baseadas em três camadas diferentes de segurança e proteção que podem ser aplicadas com base na granularidade de suas **necessidades:** linha de **base,** sensível e altamente **controlada.** Você pode aprender mais sobre esses níveis de segurança e os sistemas operacionais de cliente recomendada, referenciados por essas recomendações na [introdução de configurações e políticas de segurança recomendadas](microsoft-365-policies-configurations.md).

Essas recomendações exigem que os usuários usem clientes de email modernos, incluindo o Outlook para iOS e Android em dispositivos móveis. O Outlook para iOS e Android oferece suporte para os melhores recursos do Office 365. Esses aplicativos móveis do Outlook também são projetados com recursos de segurança que suportam o uso móvel e trabalham em conjunto com outros recursos de segurança de nuvem da Microsoft. Para saber mais, confira [Perguntas frequentes sobre o Outlook para iOS e Android.](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)

## <a name="update-common-policies-to-include-email"></a>Atualizar políticas comuns para incluir email

Para proteger o email, o diagrama a seguir ilustra quais políticas atualizar a partir das políticas comuns de identidade e acesso a dispositivos.

[![Resumo das atualizações de política para proteger o acesso ao Teams e seus serviços dependentes](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

[Ver uma versão maior desta imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

Observe a adição de uma nova política para o Exchange Online bloquear clientes do ActiveSync. Isso força o uso do Outlook Mobile.

Se você incluiu o Exchange Online e o Outlook no escopo das políticas quando as configura, só precisa criar a nova política para bloquear clientes do ActiveSync. Revise as políticas listadas na tabela a seguir e faça as adições recomendadas ou confirme se elas já estão incluídas. Cada política é vinculada às instruções de configuração associadas [em políticas comuns de acesso a dispositivos e identidade.](identity-access-policies.md)

|Nível de Proteção|Políticas|Mais informações|
|---|---|---|
|**Baseline**|[Exigir MFA quando o risco de login for *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir o Exchange Online na atribuição de aplicativos de nuvem|
||[Bloquear clientes sem suporte para a autenticação moderna](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Incluir o Exchange Online na atribuição de aplicativos de nuvem|
||[Aplicar políticas de proteção de dados app](identity-access-policies.md#apply-app-data-protection-policies)|Certifique-se de que o Outlook está incluído na lista de aplicativos. Certifique-se de atualizar a política para cada plataforma (iOS, Android, Windows)|
||[Exigir aplicativos aprovados e proteção de APLICATIVO](identity-access-policies.md#require-approved-apps-and-app-protection)|Incluir o Exchange Online na lista de aplicativos de nuvem|
||[Exigir PCs compatíveis](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Incluir o Exchange Online na lista de aplicativos de nuvem|
||[Bloquear clientes do ActiveSync](#block-activesync-clients)|Adicionar esta nova política|
|**Confidencial**|[Exigir MFA quando o risco de login for *baixo,* *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir o Exchange Online na atribuição de aplicativos de nuvem|
||[Exigir PCs e dispositivos *móveis compatíveis*](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Incluir o Exchange Online na lista de aplicativos de nuvem|
|**Altamente controlado**|[*Sempre* exigir MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir o Exchange Online na atribuição de aplicativos de nuvem|
|

## <a name="block-activesync-clients"></a>Bloquear clientes do ActiveSync

Essa política impede que os clientes do ActiveSync ignorem outras políticas de Acesso Condicional. A configuração de política se aplica somente aos clientes do ActiveSync. Ao selecionar **[Exigir política de proteção de](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** aplicativo, essa política bloqueia os clientes do ActiveSync. Detalhes sobre como criar essa política podem ser encontrados em Exigir política de proteção de aplicativo para acesso a aplicativos [na nuvem com Acesso Condicional.](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)

- Siga a "Etapa 2: Configurar uma política de Acesso Condicional do Azure AD para o Exchange Online com o ActiveSync (EAS)" no Cenário 1: os aplicativos do [Office 365](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)exigem aplicativos aprovados com políticas de proteção de aplicativos, o que impede que os clientes do Exchange ActiveSync aproveitando a autenticação básica se conectem ao Exchange Online.

Você também pode usar políticas de autenticação para [desabilitar a autenticação básica,](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)o que força todas as solicitações de acesso do cliente a usar a autenticação moderna.

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Limitar o acesso ao Exchange Online a partir do Outlook na Web

Você pode restringir a capacidade de os usuários baixarem anexos do Outlook na Web em dispositivos com um perfil. Os usuários nesses dispositivos podem exibir e editar esses arquivos usando o Office Online sem vazamento e armazenamento dos arquivos no dispositivo. Você também pode impedir que os usuários vejam anexos em um dispositivo não-manado.

Estas são as etapas:

1. [Conecte-se a uma sessão do PowerShell Remoto do Exchange Online.](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)
2. Se você ainda não tiver uma política de caixa de correio do OWA, crie uma com o cmdlet [New-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy)
3. Se você deseja permitir a exibição de anexos, mas sem download, use este comando:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. Se você deseja bloquear anexos, use este comando:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. No portal do Azure, crie uma nova política de Acesso Condicional com estas configurações:

   **Atribuições** \> **Usuários e grupos:** selecione usuários e grupos apropriados para incluir e excluir.

   **Atribuições** \> **Aplicativos ou ações na nuvem** \> **Aplicativos de nuvem** \> **Incluir** \> **Selecionar aplicativos:** Selecionar **o Office 365 Exchange Online**

   **Controles de acesso** \> **Sessão:** Selecionar **Usar restrições impostas pelo aplicativo**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>Exigir que os dispositivos iOS e Android usem o Outlook

Para garantir que os usuários de dispositivos iOS e Android só possam acessar conteúdo comercial ou escolar usando o Outlook para iOS e Android, você precisa de uma política de Acesso Condicional que segmente esses usuários em potencial.

Consulte as etapas para configurar essa política em [Gerenciar o acesso de colaboração de mensagens usando o Outlook para iOS e Android.]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)

## <a name="set-up-message-encryption"></a>Configurar a criptografia de mensagens

Com os novos recursos de Criptografia de Mensagens do Office 365 (OME), que aproveitam os recursos de proteção na Proteção de Informações do Azure, sua organização pode compartilhar facilmente emails protegidos com qualquer pessoa em qualquer dispositivo. Os usuários podem enviar e receber mensagens protegidas com outras organizações do Microsoft 365, bem como não clientes que usam Outlook.com, Gmail e outros serviços de email.

Para saber mais, confira Configurar novos recursos de Criptografia de Mensagem do [Office 365.](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)

## <a name="next-steps"></a>Próximas etapas

![Etapa 4: Políticas para aplicativos de nuvem do Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configurar políticas de Acesso Condicional para:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
