---
title: Perguntas frequentes sobre Criptografia de Mensagens
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 05/22/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: Tem uma pergunta sobre como funcionam os novos recursos de proteção de mensagens? Verifique se há uma resposta aqui.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a88d853905ed8462972c9f423254a49424974bb7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066834"
---
# <a name="message-encryption-faq"></a>Perguntas frequentes sobre Criptografia de Mensagens

Tem uma pergunta sobre como funcionam os novos recursos de proteção de mensagens? Verifique se há uma resposta aqui. Além disso, confira as perguntas frequentes sobre a proteção de dados na Proteção de Informações do [Azure](https://docs.microsoft.com/information-protection/get-started/faqs-rms) para obter respostas a perguntas sobre o serviço de proteção de dados, o Azure Rights Management, na Proteção de Informações do Azure.

## <a name="what-is-office-365-message-encryption-ome"></a>O que é a Criptografia de Mensagens do Office 365 (OME)?

O OME combina a criptografia de email e os recursos de gerenciamento de direitos. Os recursos de gerenciamento de direitos são da Proteção de Informações do Azure.

## <a name="who-can-use-ome"></a>Quem pode usar o OME?

Você pode usar os novos recursos para OME sob as seguintes condições:
  
- Se você nunca tiver definido o OME ou o IRM para o Exchange Online no Office 365.

- Se você tiver definido o OME e o IRM, poderá usar essas etapas se estiver usando o serviço Azure Rights Management da Proteção de Informações do Azure.

- Se você estiver usando o Exchange Online com o Serviço de Gerenciamento de Direitos do Active Directory (AD RMS), não será possível habilitar esses novos recursos imediatamente. Em vez disso, você precisa [migrar o AD RMS para a Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) primeiro. Quando você terminar a migração, poderá configurar o OME com êxito.

  Se você optar por continuar a usar o AD RMS local com o Exchange Online em vez de migrar para a Proteção de Informações do Azure, não poderá usar esses novos recursos.

## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>De quais assinaturas preciso para usar os novos recursos do OME?

Para usar os novos recursos do OME, você precisa de um dos seguintes planos:
  
- A Criptografia de Mensagens do Office 365 é oferecida como parte do Office 365 Enterprise E3 e E5, Microsoft Enterprise E3 e E5, Microsoft 365 Business Premium, Office 365 A1, A3 e A5, além do Office 365 Government G3 e G5. Os clientes não precisam de licenças adicionais para receber os novos recursos de proteção da Proteção de Informações do Azure.

- Você também pode adicionar o Plano 1 da Proteção de Informações do Azure aos seguintes planos para receber os novos recursos de Criptografia de Mensagem do Office 365: Exchange Online Plano 1, Exchange Online Plano 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard ou Office 365 Enterprise E1.

- Cada usuário que se beneficia da Criptografia de Mensagens do Office 365 precisa ser licenciado para ser coberto pelo recurso.

- Para ver a lista completa, confira as [descrições de serviço do Exchange Online para](https://technet.microsoft.com/library/exchange-online-service-description.aspx) a Criptografia de Mensagens do Office 365.

## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>Posso usar o Exchange Online com o BYOK (traga sua própria chave) na Proteção de Informações do Azure?

Sim! A Microsoft recomenda que você conclua as etapas para configurar BYOK antes de configurar o OME.
  
Para obter mais informações sobre BYOK, consulte Planejamento e implementação da chave de locatário da Proteção de Informações do [Azure.](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>O OME e BYOK com a Proteção de Informações do Azure alteram a abordagem da Microsoft para solicitações de dados de terceiros, como rotinas?

Não. O OME e a opção de fornecer e controlar suas próprias chaves de criptografia, chamadas BYOK, da Proteção de Informações do Azure não foram projetadas para responder a imposições da lei. O OME, com BYOK para Proteção de Informações do Azure, foi projetado para clientes focados em conformidade. A Microsoft leva muito a sério as solicitações de dados de terceiros para os dados do cliente. Como provedor de serviços de nuvem, sempre defenderemos a privacidade dos dados do cliente. Caso obtenhamos uma surpresa, sempre tentaremos redirecionar o terceiro para o cliente para obter as informações. (Leia o blog de Brad Smith: [protegendo os dados do cliente contra a espionagem do governo).](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/) Publicamos periodicamente informações detalhadas da solicitação que recebemos. Para obter mais informações sobre solicitações de dados de terceiros, consulte Respondendo a solicitações governamentais e de aplicação [da](https://www.microsoft.com/trustcenter/privacy/govt-requests-for-data) lei para acessar dados do cliente na Central de Confiação da Microsoft. Além disso, consulte "Divulgação de dados do cliente" nos Termos [de Serviços Online (OST).](https://www.microsoft.com/Licensing/product-licensing/products.aspx)
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>Como esse recurso está relacionado aos recursos herdado de Criptografia de Mensagens (OME) e Gerenciamento de Direitos de Informação (IRM) do Office 365?

Os novos recursos da Criptografia de Mensagens do Office 365 são uma evolução das soluções existentes de IRM e OME herdadas. A tabela a seguir fornece mais detalhes.
  
**Comparação de OME herddo, IRM e novos recursos do OME**

| Recursos | Versões anteriores do OME | IRM | Novos recursos do OME |
|:-----|:-----|:-----|:-----|
|**Enviar um email criptografado**|Somente por meio de regras de fluxo de emails do Exchange|Usuário final iniciado no Outlook para Windows, Outlook para Mac ou Outlook na Web; ou por meio de regras de fluxo de emails do Exchange|Usuário final iniciado no Outlook para Windows, Outlook para Mac ou Outlook na Web; ou por meio de regras de fluxo de emails|
|**Gerenciamento de direitos**|-|Opção Não Encaminhar e modelos personalizados|Opção Não Encaminhar, opção somente criptografada, modelos padrão e personalizados|
|**Tipo de destinatário com suporte**|Somente destinatários externos|Somente destinatários internos|Destinatários internos e externos|
|**Experiência para destinatário**|Destinatários externos receberam uma mensagem HTML baixada e aberta em um navegador ou aplicativo móvel baixado.|Os destinatários internos só receberam emails criptografados no Outlook para Windows, Outlook para Mac e Outlook na Web.|Destinatários internos e externos recebem emails no Outlook para Windows, Outlook para Mac, Outlook na Web, Outlook para Android e Outlook para iOS ou por meio de um portal da Web, independentemente de eles estão ou não na mesma organização ou em qualquer organização. O portal do OME não requer download separado.|
|**Suporte a "Traga sua própria chave"**|Não disponível|Não disponível| BYOK com suporte|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>Como habilitar os novos recursos do OME para minha organização?

Confira Configurar novos recursos de Criptografia de Mensagem do [Office 365.](set-up-new-message-encryption-capabilities.md)
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>A versão anterior do OME será preterida?

Você ainda pode usar a versão anterior do OME, ela não será preterida no momento. No entanto, recomendamos que as organizações usem a solução OME nova e aprimorada. Os clientes que ainda não implantaram o OME não podem configurar uma nova implantação da versão anterior do OME.
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>Minha organização usa o Active Directory Rights Management, posso usar essa funcionalidade?

Não. Se você estiver usando o Exchange Online com o Serviço de Gerenciamento de Direitos do Active Directory (AD RMS), não será possível habilitar esses novos recursos imediatamente. Em vez disso, você precisa [migrar o AD RMS para a Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) primeiro.
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>Minha organização tem uma implantação híbrida do Exchange. Posso usar esse recurso?

Os usuários locais podem enviar emails criptografados usando regras de fluxo de emails do Exchange Online. Para fazer isso, você precisa rotear emails pelo Exchange Online. Para obter mais informações, consulte a Parte 2: Configurar o email para que ele flua do seu servidor de [email para o Microsoft 365.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>Qual cliente de email preciso usar para criar uma mensagem criptografada do OME? Quais aplicativos são suportados para envio de mensagens protegidas?

Você pode criar mensagens protegidas do Outlook 2016, Do Outlook 2013 para Windows e Mac e do Outlook na Web. Para obter mais informações sobre como enviar mensagens criptografadas, consulte Enviar, exibir e responder a mensagens [criptografadas no Outlook para PC.](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-us&rs=en-us&ad=us)
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>Quais clientes de email têm suporte para ler e responder a emails protegidos?

Os usuários do Microsoft 365 podem ler e responder do Outlook para Windows e Mac (2013 e 2016), Outlook na Web e Outlook Mobile (Android e iOS). Você também pode usar o cliente de email nativo do iOS se sua organização permitir isso. Se você não for um usuário do Microsoft 365, poderá ler e responder a mensagens criptografadas na Web por meio do navegador da Web.

## <a name="what-email-clients-support-the-encrypt-only-protected-emails"></a>Quais clientes de email suportam os emails protegidos somente para criptografia?

Os usuários do Microsoft 365 podem usar o Outlook para PC versões 2019 e o Microsoft 365 para criar emails protegidos com a política somente criptografada.  Isso significa que as mensagens que têm a nova política somente criptografada aplicada podem ser lidas diretamente no Outlook na Web, no Outlook para iOS e Android, e agora no Outlook para PC versões 2019 e no Microsoft 365.

## <a name="is-there-a-size-limit-for-messages-you-can-send-with-ome"></a>Há um limite de tamanho para mensagens que você pode enviar com o OME?

Sim. O tamanho máximo de mensagem que você pode enviar com o OME, incluindo anexos, é de 25 MB. Para obter mais informações, consulte [Limites de mensagens.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits-1)

## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>Quais tipos de arquivo são suportados como anexos em emails protegidos? Os anexos herdam as políticas de proteção associadas a emails protegidos?

Você pode anexar qualquer tipo de arquivo a um email protegido. Com uma exceção, as políticas de proteção são aplicadas apenas nos formatos de arquivo mencionados nos tipos de arquivo suportados pelo cliente de Proteção de Informações do [Azure.](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types) O OME não dá suporte às versões 97-2003 dos seguintes programas do Office: Word (.doc), Excel (.xls) e PowerPoint (.ppt).

Se um formato de arquivo for suportado, como um arquivo do Word, Excel ou PowerPoint, o arquivo estará sempre protegido, mesmo depois que o anexo tiver sido baixado pelo destinatário. Por exemplo, digamos que um anexo está protegido por Não Encaminhar. O destinatário original baixa o arquivo, cria uma mensagem para um novo destinatário e anexa o arquivo. Quando o novo destinatário receber o arquivo, ele não poderá abrir o arquivo protegido.
  
## <a name="are-pdf-file-attachments-supported"></a>Há suporte para anexos de arquivo PDF?

A resposta curta é Sim! A criptografia PDF permite que você proteja documentos PDF confidenciais por meio de comunicação segura ou colaboração segura. Quando você envia emails, o serviço do Office 365 criptografa anexos de arquivo PDF e não o cliente do Outlook.

Para o Outlook na Web, o Outlook para iOS e o Outlook para Android, você pode criptografar PDFs que envia sem etapas adicionais. Esses clientes suportam de forma nativa a criptografia PDF.

A área de trabalho do Outlook não dá suporte nativo à criptografia de anexos de arquivo PDF. Em vez disso, você precisará configurar regras de fluxo de emails do Exchange ou DLP para aplicar criptografia a anexos de PDF primeiro. Quando você envia emails da Área de Trabalho do Outlook com um anexo de PDF, o cliente envia primeiro a mensagem com o anexo para o serviço. Quando o serviço recebe o arquivo, o serviço aplica a proteção OME da política de prevenção de perda de dados (DLP) ou regra de fluxo de emails no Exchange Online. Em seguida, o Exchange Online envia a mensagem com o anexo de arquivo PDF protegido.

Para habilitar a criptografia para anexos de PDF, execute o seguinte comando no [PowerShell do Exchange Online:](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

```powershell
Set-IRMConfiguration -EnablePdfEncryption $true
```

A criptografia PDF permite que você proteja documentos PDF confidenciais por meio de comunicação segura ou colaboração segura. Para todos os clientes do Outlook, mensagens e anexos de PDF não protegidos herdam a proteção OME da política de prevenção de perda de dados (DLP) ou regra de fluxo de emails no Exchange Online. Além disso, se um usuário do Outlook na Web anexar um documento PDF desprotegido e aplicar proteção à mensagem, a mensagem herdará a proteção da mensagem. Os usuários só podem abrir os anexos criptografados em aplicativos que suportam PDFs protegidos (por exemplo, o Portal OME e o Visualizador da Proteção de Informações do Azure).

> [!IMPORTANT]
> O cliente da área de trabalho do Outlook não dá suporte à criptografia PDF.

## <a name="are-onedrive-for-business-attachments-supported"></a>Há suporte para anexos do OneDrive for Business?

Not yet. Os anexos do OneDrive for Business não são suportados e os usuários finais não podem criptografar um email que contenha um anexo do OneDrive for Business na nuvem.
  
## <a name="what-email-clients-support-preview-of-encrypted-attachments-in-protected-emails"></a>Quais clientes de email suportam a visualização de anexos criptografados em emails protegidos?

Quando os anexos são protegidos com um email protegido, os clientes do Outlook fornecem a capacidade de visualizar o documento diretamente. O Outlook dá suporte à visualização de documentos do Office (docx, xlsx, pptx, doc, xls, ppt). O Outlook na Web dá suporte à visualização de documentos do Office (docx, xlsx, pptx) e PDF.  

## <a name="what-email-clients-support-revocation-of-protected-emails"></a>Quais clientes de email suportam revogação de emails protegidos?

O Outlook na Web oferece suporte à revogação de emails protegidos.  Veja [como revogar uma mensagem criptografada que você enviou para](https://docs.microsoft.com/microsoft-365/compliance/revoke-ome-encrypted-mail?view=o365-worldwide#how-to-revoke-an-encrypted-message-that-you-sent) obter detalhes.


## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>Posso criptografar automaticamente as mensagens configurando políticas?

Sim. Use regras de fluxo de emails no Exchange Online para criptografar automaticamente uma mensagem com base em determinadas condições. Por exemplo, você pode criar políticas baseadas na ID do destinatário, no domínio do destinatário ou no conteúdo no corpo ou no assunto da mensagem. Consulte [Definir regras de fluxo de emails para criptografar mensagens de email no Office 365.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail"></a>Posso remover automaticamente a criptografia em emails de entrada e de saída?

Os administradores podem configurar uma regra de fluxo de emails para remover a criptografia de emails de saída. Não é possível configurar uma regra para remover a criptografia de emails de entrada.

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>Posso criptografar automaticamente as mensagens configurando políticas na Prevenção contra Perda de Dados (DLP) por meio do Centro de Conformidade &amp; de Segurança?

Sim! Você pode configurar regras de fluxo de emails no Exchange Online ou usando DLP no Centro de Conformidade &amp; de Segurança.
  
## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>Posso personalizar mensagens criptografadas com a identidade visual da minha empresa?

Sim! Para obter informações sobre como personalizar mensagens de email e o portal OME, consulte Adicionar a marca da sua organização às suas mensagens criptografadas. Confira [Adicionar a marca da sua organização às suas mensagens criptografadas.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>Há recursos de relatórios ou ideias para emails criptografados?

Há um relatório de criptografia no Centro de Conformidade e Segurança. Consulte [Exibir relatórios de segurança de email no Centro de Conformidade e & Segurança.](../security/office-365-security/view-email-security-reports.md)
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>Posso usar a criptografia de mensagens com recursos de conformidade, como a Descoberta eDiscovery?

Sim. Todas as mensagens de email criptografadas são descobertas pelos recursos de conformidade do Microsoft 365.

## <a name="can-i-remove-encryption-from-email"></a>Posso remover a criptografia do email?

Os administradores podem configurar uma regra de fluxo de emails para remover a criptografia do email de saída. Não é possível remover a criptografia usando uma regra de fluxo de emails de mensagens de entrada.

## <a name="is-delegated-access-supported"></a>O acesso delegado é suportado?

Não neste momento.

## <a name="can-i-send-as-a-shared-mailbox-and-encrypt-emails"></a>Posso enviar como uma caixa de correio compartilhada e criptografar emails?

Quando alguém envia uma mensagem de email que corresponde a uma regra de fluxo de emails de criptografia, ela é criptografada antes de ser enviada.

## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>Posso abrir mensagens criptografadas enviadas para uma caixa de correio compartilhada?

Sim! Mensagens criptografadas são suportadas para uma caixa de correio compartilhada.

- Os usuários podem abrir emails protegidos em uma caixa de correio compartilhada onde a caixa de correio compartilhada recebeu um email protegido como parte de um grupo de distribuição.

- Os usuários podem exibir anexos que herdam a proteção do email quando usam o Outlook para Windows, Outlook para Mac e Outlook na Web.

A tabela a seguir lista os clientes com suporte para caixas de correio compartilhadas.

| Plataforma | Ler email | Exibir anexos de email |
|----------|-----------|------------------------|
| Outlook na Web | Sim | Sim                |
| Outlook para Windows| Sim | Sim                |
| Outlook para Mac    | Sim | Sim                |
| Outlook para Android| Sim | Não                 |
| Outlook para iOS    | Sim | Não                 |
|

Existem atualmente duas limitações conhecidas:

- Você não pode abrir anexos para emails recebidos em dispositivos móveis usando o Outlook Mobile.

- Não há suporte para a atribuição por meio de um grupo de segurança habilitado para email. Só damos suporte ao acesso fornecido pela atribuição direta de usuário à caixa de correio compartilhada e esse automapeamento está habilitado para o Exchange Online. O automapeamento é habilitado por padrão para o Exchange Online.

**Para atribuir um usuário à caixa de correio compartilhada**

1. [Conecte-se ao Exchange Online usando o PowerShell Remoto.](https://technet.microsoft.com/library/jj984289?v=exchg.150%29.aspx)

2. Execute o Add-MailboxPermission cmdlet com o parâmetro Automapping. Este exemplo concede a Ayla permissões de acesso total a uma caixa de correio de suporte.

   ```powershell
   Add-MailboxPermission -Identity support@contoso.onmicrosoft.com -User ayla@contoso.com -AccessRights FullAccess -AutoMapping $true
   ```
   
 ## <a name="can-i-open-encrypted-messages-sent-to-another-users-mailbox-with-fullaccess"></a>Posso abrir mensagens criptografadas enviadas para a caixa de correio de outro usuário com Fullaccess?

Os usuários podem abrir mensagens criptografadas, desde que tenham acesso direto e o automação seja ligado. O acesso não será permitido se o acesso for concedido por meio de um grupo de segurança habilitado para email.

## <a name="what-do-i-do-if-i-dont-receive-the-one-time-pass-code-after-i-requested-it"></a>O que devo fazer se não receber o código de acesso único depois de solicitá-lo?

Primeiro, verifique a pasta lixo eletrônico ou spam em seu cliente de email. As configurações de DKIM e DMARC para sua organização podem fazer com que esses emails terminem filtrados como spam.

Em seguida, verifique a quarentena no Centro de Conformidade & segurança. Muitas vezes, as mensagens que contêm um código de acesso único, especialmente as primeiras que sua organização recebe, terminam em quarentena.
