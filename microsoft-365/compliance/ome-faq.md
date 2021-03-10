---
title: Perguntas frequentes sobre criptografia de mensagens
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
ms.openlocfilehash: 1bb5e93b08b74f5691c76e9a59bf9fa970e08f36
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597191"
---
# <a name="message-encryption-faq"></a>Perguntas frequentes sobre criptografia de mensagens

Tem uma pergunta sobre como funcionam os novos recursos de proteção de mensagens? Verifique se há uma resposta aqui. Além disso, confira Perguntas frequentes sobre a proteção de dados no [Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/faqs-rms) para obter respostas a perguntas sobre o serviço de proteção de dados, Gerenciamento de Direitos do Azure, na Proteção de Informações do Azure.

## <a name="what-is-office-365-message-encryption-ome"></a>O que é a Criptografia de Mensagens do Office 365 (OME)?

O OME combina recursos de criptografia de email e gerenciamento de direitos. Os recursos de gerenciamento de direitos são alimentados pela Proteção de Informações do Azure.

## <a name="who-can-use-ome"></a>Quem pode usar o OME?

Você pode usar os novos recursos para OME nas seguintes condições:
  
- Se você nunca tiver configurar o OME ou o IRM para o Exchange Online no Office 365.

- Se você tiver definido o OME e o IRM, poderá usar essas etapas se estiver usando o serviço de Gerenciamento de Direitos do Azure da Proteção de Informações do Azure.

- Se você estiver usando o Exchange Online com o serviço de Gerenciamento de Direitos do Active Directory (AD RMS), não poderá habilitar esses novos recursos imediatamente. Em vez disso, você precisa [migrar o AD RMS para a Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) primeiro. Quando terminar a migração, você poderá configurar com êxito o OME.

  Se você optar por continuar a usar o AD RMS local com o Exchange Online em vez de migrar para a Proteção de Informações do Azure, não poderá usar esses novos recursos.

## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>Quais assinaturas preciso para usar os novos recursos OME?

Para usar os novos recursos OME, você precisa de um dos seguintes planos:
  
- A Criptografia de Mensagens do Office 365 é oferecida como parte do Office 365 Enterprise E3 e E5, Microsoft Enterprise E3 e E5, Microsoft 365 Business Premium, Office 365 A1, A3 e A5 e Office 365 Government G3 e G5. Os clientes não precisam de licenças adicionais para receber os novos recursos de proteção com a Proteção de Informações do Azure.

- Você também pode adicionar o Plano 1 de Proteção de Informações do Azure aos seguintes planos para receber os novos recursos de Criptografia de Mensagens do Office 365: Plano 1 do Exchange Online, Plano 2 do Exchange Online, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard ou Office 365 Enterprise E1.

- Cada usuário que se beneficia da Criptografia de Mensagens do Office 365 precisa ser licenciado para ser coberto pelo recurso.

- Para ver a lista completa, consulte as descrições de serviço [do Exchange Online](https://technet.microsoft.com/library/exchange-online-service-description.aspx) para a Criptografia de Mensagens do Office 365.

## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>Posso usar o Exchange Online com sua própria chave (BYOK) na Proteção de Informações do Azure?

Sim! A Microsoft recomenda que você conclua as etapas para configurar BYOK antes de configurar o OME.
  
Para obter mais informações sobre BYOK, consulte [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key).
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>O OME e BYOK com a Proteção de Informações do Azure alteram a abordagem da Microsoft para solicitações de dados de terceiros, como intimações?

Não. OME e a opção de fornecer e controlar suas próprias chaves de criptografia, chamadas BYOK, da Proteção de Informações do Azure não foram projetadas para responder a intimações de imposição da lei. OME, com BYOK para a Proteção de Informações do Azure, foi projetado para clientes com foco em conformidade. A Microsoft leva muito a sério as solicitações de terceiros para dados do cliente. Como provedor de serviços de nuvem, sempre defendemos a privacidade dos dados do cliente. Caso obtenhamos uma intimação, sempre tentaremos redirecionar o terceiro para o cliente para obter as informações. (Leia o blog de Brad Smith: [Protegendo os dados do cliente contra a espionagem governamental](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Publicamos periodicamente informações detalhadas da solicitação que recebemos. Para obter mais informações sobre solicitações de dados de terceiros, consulte [Respondendo](https://www.microsoft.com/trustcenter/privacy/govt-requests-for-data) a solicitações governamentais e de aplicação da lei para acessar dados do cliente no Centro de Confiança da Microsoft. Além disso, consulte "Divulgação de dados do cliente" nos Termos de [Serviços Online (OST)](https://www.microsoft.com/Licensing/product-licensing/products.aspx).
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>Como esse recurso está relacionado aos recursos herdado da Criptografia de Mensagens do Office 365 (OME) e do Gerenciamento de Direitos de Informação (IRM)?

Os novos recursos para a Criptografia de Mensagens do Office 365 são uma evolução das soluções existentes do IRM e do OME herdadas. A tabela a seguir fornece mais detalhes.
  
**Comparação de recursos OME, IRM e OME herdáveis**

| Recursos | Versões anteriores do OME | IRM | Novos recursos OME |
|:-----|:-----|:-----|:-----|
|**Enviando um email criptografado**|Somente por meio de regras de fluxo de emails do Exchange|Usuário final iniciado do Outlook para Windows, Outlook para Mac ou Outlook na Web; ou por meio de regras de fluxo de emails do Exchange|Usuário final iniciado do Outlook para Windows, Outlook para Mac ou Outlook na Web; ou por meio de regras de fluxo de emails|
|**Gerenciamento de direitos**|-|Opção Não Encaminhar e modelos personalizados|Opção Não Encaminhar, opção somente criptografar, modelos padrão e personalizados|
|**Tipo de destinatário com suporte**|Somente destinatários externos|Somente destinatários internos|Destinatários internos e externos|
|**Experiência para destinatário**|Destinatários externos receberam uma mensagem HTML baixada e aberta em um navegador ou aplicativo móvel baixado.|Os destinatários internos receberam apenas emails criptografados no Outlook para Windows, Outlook para Mac e Outlook na Web.|Destinatários internos e externos recebem emails no Outlook para Windows, Outlook para Mac, Outlook na Web, Outlook para Android e Outlook para iOS ou por meio de um portal da Web, independentemente de eles estão ou não na mesma organização ou em qualquer organização. O portal OME não requer download separado.|
|**Traga suporte a Sua Própria Chave**|Não disponível|Não disponível| BYOK com suporte|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>Como habilitar os novos recursos OME para minha organização?

Consulte Configurar novos recursos de Criptografia de Mensagens do [Office 365.](set-up-new-message-encryption-capabilities.md)
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>A versão anterior do OME será preterida?

Você ainda pode usar a versão anterior do OME, ela não será preterida no momento. No entanto, é altamente recomendável que as organizações usem a solução OME nova e aprimorada. Os clientes que ainda não implantaram o OME não podem configurar uma nova implantação da versão anterior do OME.
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>Minha organização usa o Gerenciamento de Direitos do Active Directory, posso usar essa funcionalidade?

Não. Se você estiver usando o Exchange Online com o serviço de Gerenciamento de Direitos do Active Directory (AD RMS), não poderá habilitar esses novos recursos imediatamente. Em vez disso, você precisa [migrar o AD RMS para a Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) primeiro.
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>Minha organização tem uma implantação híbrida do Exchange. Posso usar esse recurso?

Os usuários locais podem enviar emails criptografados usando regras de fluxo de emails do Exchange Online. Para fazer isso, você precisa rotear emails por meio do Exchange Online. Para obter mais informações, consulte Parte 2: Configurar o email para fluir do [seu servidor de email para o Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365).
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>Qual cliente de email preciso usar para criar uma mensagem criptografada OME? Quais aplicativos são suportados para enviar mensagens protegidas?

Você pode criar mensagens protegidas do Outlook 2016, do Outlook 2013 para Windows e Mac e do Outlook na Web. Para obter mais informações sobre como enviar mensagens criptografadas, consulte [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-us&rs=en-us&ad=us).
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>Quais clientes de email têm suporte para ler e responder a emails protegidos?

Os usuários do Microsoft 365 podem ler e responder do Outlook para Windows e Mac (2013 e 2016), Do Outlook na Web e do Outlook mobile (Android e iOS). Você também pode usar o cliente de email nativo do iOS se sua organização permitir. Se você não for um usuário do Microsoft 365, poderá ler e responder a mensagens criptografadas na Web por meio do navegador da Web.

## <a name="what-email-clients-support-the-encrypt-only-protected-emails"></a>Quais clientes de email suportam emails protegidos somente criptografia?

Os usuários do Microsoft 365 podem usar o Outlook para pc versões 2019 e o Microsoft 365 para criar emails protegidos com a política somente criptografia.  Isso significa que as mensagens que têm a nova política somente criptografada aplicada podem ser lidas diretamente no Outlook na Web, no Outlook para iOS e Android e agora no Outlook para pc versões 2019 e Microsoft 365.

## <a name="is-there-a-size-limit-for-messages-you-can-send-with-ome"></a>Há um limite de tamanho para mensagens que você pode enviar com o OME?

Sim. O tamanho máximo da mensagem que você pode enviar com o OME, incluindo anexos, é de 25 MB. Para obter mais informações, consulte [Limites de mensagens](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits-1).

## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>Quais tipos de arquivo são suportados como anexos em emails protegidos? Os anexos herdam as políticas de proteção associadas a emails protegidos?

Você pode anexar qualquer tipo de arquivo a um email protegido. Com uma exceção, as políticas de proteção são aplicadas somente nos formatos de arquivo mencionados em Tipos de arquivo suportados pelo cliente de Proteção de Informações do [Azure](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types). O OME não dá suporte às versões 97-2003 dos seguintes programas do Office: Word (.doc), Excel (.xls) e PowerPoint (.ppt).

Se um formato de arquivo for suportado, como um arquivo do Word, Excel ou PowerPoint, o arquivo será sempre protegido, mesmo depois que o anexo tiver sido baixado pelo destinatário. Por exemplo, digamos que um anexo seja protegido por Não Encaminhar. O destinatário original baixa o arquivo, cria uma mensagem para um novo destinatário e anexa o arquivo. Quando o novo destinatário receber o arquivo, o destinatário não poderá abrir o arquivo protegido.
  
## <a name="are-pdf-file-attachments-supported"></a>Há suporte para anexos de arquivo PDF?

A resposta curta é sim! A criptografia PDF permite proteger documentos PDF confidenciais por meio de comunicação segura ou colaboração segura. Quando você envia emails, o serviço do Office 365 criptografa anexos de arquivo PDF e não o cliente do Outlook.

Para o Outlook na Web, o Outlook para iOS e o Outlook para Android, você pode criptografar PDFs que você envia sem qualquer etapa adicional. Esses clientes nações suportam criptografia PDF.

A área de trabalho do Outlook não dá suporte nativo à criptografia de anexos de arquivo PDF. Em vez disso, você precisará configurar regras de fluxo de emails do Exchange ou DLP para aplicar criptografia a anexos PDF primeiro. Quando você envia emails da Área de Trabalho do Outlook com um anexo PDF, o cliente envia a mensagem com o anexo para o serviço primeiro. Quando o serviço recebe o arquivo, o serviço aplica a proteção OME da política de prevenção contra perda de dados (DLP) ou regra de fluxo de emails no Exchange Online. Em seguida, o Exchange Online envia a mensagem com o anexo de arquivo PDF protegido.

Para habilitar a criptografia para anexos PDF, execute o seguinte comando no [PowerShell do Exchange Online:](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

```powershell
Set-IRMConfiguration -EnablePdfEncryption $true
```

A criptografia PDF permite proteger documentos PDF confidenciais por meio de comunicação segura ou colaboração segura. Para todos os clientes do Outlook, mensagens e anexos PDF desprotegidos herdam a proteção OME da política de prevenção contra perda de dados (DLP) ou a regra de fluxo de emails no Exchange Online. Além disso, se um usuário do Outlook na Web anexar um documento PDF desprotegido e aplicar proteção à mensagem, a mensagem herdará a proteção da mensagem. Os usuários só podem abrir os anexos criptografados em aplicativos que suportam PDFs protegidos (por exemplo, o Portal OME e o Visualizador de Proteção de Informações do Azure).

> [!IMPORTANT]
> O cliente da área de trabalho do Outlook não dá suporte à criptografia PDF.

## <a name="are-onedrive-for-business-attachments-supported"></a>Há suporte para anexos do OneDrive for Business?

Not yet. Os anexos do OneDrive for Business não são suportados e os usuários finais não podem criptografar um email que contém um anexo do OneDrive for Business na nuvem.
  
## <a name="what-email-clients-support-preview-of-encrypted-attachments-in-protected-emails"></a>Quais clientes de email suportam a visualização de anexos criptografados em emails protegidos?

Quando os anexos são protegidos com um email protegido, os clientes do Outlook fornecem a capacidade de visualizar o documento diretamente. O Outlook dá suporte à visualização de documentos do Office (docx, xlsx, pptx, doc, xls, ppt). O Outlook na Web dá suporte à visualização de documentos do Office (docx, xlsx, pptx) e PDF.  

## <a name="what-email-clients-support-revocation-of-protected-emails"></a>Quais clientes de email suportam revogação de emails protegidos?

O Outlook na Web dá suporte à revogação de emails protegidos.  Consulte [Como revogar uma mensagem criptografada que você enviou para](https://docs.microsoft.com/microsoft-365/compliance/revoke-ome-encrypted-mail?view=o365-worldwide#how-to-revoke-an-encrypted-message-that-you-sent) obter detalhes.


## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>Posso criptografar automaticamente mensagens configurando políticas?

Sim. Use regras de fluxo de emails no Exchange Online para criptografar automaticamente uma mensagem com base em determinadas condições. Por exemplo, você pode criar políticas baseadas na ID do destinatário, no domínio do destinatário ou no conteúdo no corpo ou no assunto da mensagem. Consulte [Definir regras de fluxo de emails para criptografar mensagens de email no Office 365](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail"></a>Posso remover automaticamente a criptografia em emails de entrada e saída?

Os administradores podem configurar uma regra de fluxo de emails para remover a criptografia para emails de saída. Não é possível configurar uma regra para remover a criptografia para emails de entrada.

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>Posso criptografar automaticamente mensagens configurando políticas na Prevenção contra Perda de Dados (DLP) por meio do Centro &amp; de Conformidade e Segurança?

Sim! Você pode configurar regras de fluxo de emails no Exchange Online ou usando DLP no Centro &amp; de Conformidade de Segurança.
  
## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>Posso personalizar mensagens criptografadas com a identidade visual da minha empresa?

Sim! Para obter informações sobre como personalizar mensagens de email e o portal OME, consulte Add your organization's brand to your encrypted messages. Consulte [Adicionar a marca da sua organização às suas mensagens criptografadas](add-your-organization-brand-to-encrypted-messages.md).
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>Há recursos de relatórios ou ideias para emails criptografados?

Há um relatório de criptografia no Centro de Segurança e Conformidade. Consulte [Exibir relatórios de segurança de email no Centro de Conformidade & Segurança.](../security/office-365-security/view-email-security-reports.md)
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>Posso usar a criptografia de mensagens com recursos de conformidade, como a Descoberta eDiscovery?

Sim. Todas as mensagens de email criptografadas são descobertas pelos recursos de conformidade do Microsoft 365.

## <a name="can-i-remove-encryption-from-email"></a>Posso remover a criptografia do email?

Os administradores podem configurar uma regra de fluxo de emails para remover a criptografia. Você não pode remover a criptografia usando uma regra de fluxo de emails do email que é aplicada por outra organização, a menos que o email seja encriptado usando proteção somente criptografada.

## <a name="is-delegated-access-supported"></a>O acesso delegado é suportado?

Não neste momento.

## <a name="can-i-send-as-a-shared-mailbox-and-encrypt-emails"></a>Posso enviar como uma caixa de correio compartilhada e criptografar emails?

Quando alguém envia uma mensagem de email que corresponde a uma regra de fluxo de email de criptografia, a mensagem é criptografada antes de ser enviada.

## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>Posso abrir mensagens criptografadas enviadas para uma caixa de correio compartilhada?

Sim! As mensagens criptografadas são suportadas para uma caixa de correio compartilhada.

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

Atualmente, há duas limitações conhecidas:

- Não é possível abrir anexos para emails recebidos em dispositivos móveis usando o Outlook mobile.

- Não suportamos a atribuição por meio de um grupo de segurança habilitado para email. Suportamos apenas o acesso fornecido pela atribuição direta do usuário à caixa de correio compartilhada e essa automação está habilitada para o Exchange Online. A automação é habilitada por padrão para o Exchange Online.

**Para atribuir um usuário à caixa de correio compartilhada**

1. [Conectar-se ao Exchange Online usando o PowerShell Remoto.](https://technet.microsoft.com/library/jj984289?v=exchg.150%29.aspx)

2. Execute o cmdlet Add-MailboxPermission com o parâmetro Automapping. Este exemplo concede permissões de acesso total a Ayla a uma caixa de correio de suporte.

   ```powershell
   Add-MailboxPermission -Identity support@contoso.onmicrosoft.com -User ayla@contoso.com -AccessRights FullAccess -AutoMapping $true
   ```
   
 ## <a name="can-i-open-encrypted-messages-sent-to-another-users-mailbox-with-fullaccess"></a>Posso abrir mensagens criptografadas enviadas para a caixa de correio de outro usuário com Fullaccess?

Os usuários podem abrir mensagens criptografadas desde que tenham acesso direto e a automação seja ativas. O acesso não será permitido se o acesso for concedido por meio de um grupo de segurança habilitado para email.

## <a name="what-do-i-do-if-i-dont-receive-the-one-time-pass-code-after-i-requested-it"></a>O que faço se não receber o código de passagem único depois de solicitá-lo?

Primeiro, verifique a pasta lixo eletrônico ou spam em seu cliente de email. As configurações DKIM e DMARC para sua organização podem fazer com que esses emails terminem filtrados como spam.

Em seguida, verifique a quarentena no Centro de Conformidade & Segurança. Muitas vezes, as mensagens que contêm um código de passagem única, especialmente as primeiras que sua organização recebe, terminam em quarentena.
