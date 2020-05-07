---
title: Perguntas frequentes sobre criptografia de mensagens
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 04/13/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: Tem uma pergunta sobre como funcionam os novos recursos de proteção de mensagens? Verifique se há uma resposta aqui.
ms.openlocfilehash: 75b414aecfbe9d3952d7e3c5994946775d353a6f
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049516"
---
# <a name="message-encryption-faq"></a>Perguntas frequentes sobre criptografia de mensagens

Tem uma pergunta sobre como funcionam os novos recursos de proteção de mensagens? Verifique se há uma resposta aqui. Além disso, dê uma olhada em [perguntas frequentes sobre a proteção de dados na proteção de informações do Azure](https://docs.microsoft.com/information-protection/get-started/faqs-rms) para obter respostas para perguntas sobre o serviço de proteção de dados, o Azure Rights Management, na proteção de informações do Azure.

## <a name="what-is-office-365-message-encryption-ome"></a>O que é a criptografia de mensagem do Office 365 (OME)?

O OME combina recursos de gerenciamento de direitos e criptografia de email. Os recursos de gerenciamento de direitos são compatíveis com a proteção de informações do Azure.
  
## <a name="who-can-use-ome"></a>Quem pode usar o OME?

Você pode usar os novos recursos para o OME sob as seguintes condições:
  
- Se você nunca configurou o OME ou o IRM para Exchange Online no Office 365.

- Se você tiver configurado o OME e o IRM, poderá usar estas etapas se estiver usando o serviço de gerenciamento de direitos do Azure da proteção de informações do Azure.

- Se estiver usando o Exchange Online com o Active Directory Rights Management Service (AD RMS), você não poderá habilitar esses novos recursos imediatamente. Em vez disso, você precisa [migrar primeiro o AD RMS para a proteção de informações do Azure](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) . Após concluir a migração, você pode configurar com êxito o OME.

  Se você optar por continuar a usar o AD RMS local com o Exchange Online em vez de migrar para a proteção de informações do Azure, não será possível usar esses novos recursos.

## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>Quais assinaturas são necessárias para usar os novos recursos do OME?

Para usar os novos recursos do OME, você precisa de um dos seguintes planos:
  
- A criptografia de mensagem do Office 365 é oferecida como parte do Office 365 Enterprise E3 e e5, Microsoft Enterprise E3 e e5, Microsoft 365 Business Premium, Office 365 a1, a3 e a5 e Office 365 governo G3 e G5. Os clientes não precisam de licenças adicionais para receber os novos recursos de proteção baseados na proteção de informações do Azure.

- Você também pode adicionar o plano de proteção de informações do Azure 1 aos seguintes planos para receber os novos recursos de criptografia de mensagens do Office 365: Exchange Online plano 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard ou Office 365 Enterprise E1.

- Todos os usuários que se beneficiam da criptografia de mensagens do Office 365 precisam ser licenciados para serem cobertos pelo recurso.

- Para obter a lista completa, Confira as [descrições de serviço do Exchange Online](https://technet.microsoft.com/library/exchange-online-service-description.aspx) para a criptografia de mensagem do Office 365.

## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>Posso usar o Exchange Online com a sua própria chave (BYOK) na proteção de informações do Azure?

Sim! A Microsoft recomenda que você conclua as etapas para configurar o BYOK antes de configurar o OME.
  
Para obter mais informações sobre o BYOK, consulte [Planning and Implementing Your Azure Information Protection locatário Key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key).
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>O OME e o BYOK com a proteção de informações do Azure alteram a abordagem da Microsoft para solicitações de dados de terceiros, como intimações?

Não. OME e a opção de fornecer e controlar suas próprias chaves de criptografia, chamadas BYOK, da proteção de informações do Azure não foram projetadas para responder às intimações de aplicação de leis. O OME, com o BYOK para proteção de informações do Azure, foi projetado para clientes focados em conformidade. A Microsoft leva muito seriamente as solicitações de terceiros para os dados dos clientes. Como um provedor de serviços de nuvem, sempre defendemos a privacidade dos dados do cliente. No evento, obtemos uma intimação, tentamos sempre redirecionar o terceiro para o cliente para obter as informações. (Leia o blog de Brad Smith: [proteção dos dados do cliente a partir do rastreamento governamental](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Publicamos informações detalhadas sobre a solicitação que recebemos periodicamente. Para obter mais informações sobre solicitações de dados de terceiros, confira [responder a solicitações de imposição de leis e de órgãos governamentais para acessar dados do cliente](https://www.microsoft.com/trustcenter/privacy/govt-requests-for-data) na central de confiabilidade da Microsoft. Além disso, consulte "divulgação de dados do cliente" nos [termos dos serviços online (OST)](https://www.microsoft.com/Licensing/product-licensing/products.aspx).
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>Como esse recurso está relacionado aos recursos herdados de criptografia de mensagem do Office 365 (OME) e gerenciamento de direitos de informação (IRM)?

Os novos recursos da criptografia de mensagem do Office 365 são uma evolução das soluções existentes do IRM e do OME herdadas. A tabela a seguir fornece mais detalhes.
  
**Comparação entre os recursos herdados OME, IRM e novos OME**

|**Funcionalidade**|**Versões anteriores do OME**|**IRM**|**Novos recursos do OME**|
|:-----|:-----|:-----|:-----|
|**Enviar um email criptografado**|Somente por meio de regras de fluxo de email do Exchange|Usuário final iniciado pelo Outlook para Windows, Outlook para Mac ou Outlook na Web; ou por meio de regras de fluxo de email do Exchange|Usuário final iniciado pelo Outlook para Windows, Outlook para Mac ou Outlook na Web; ou por meio de regras de fluxo de emails|
|**Gerenciamento de direitos**|-|Opção não encaminhar e modelos personalizados|Opção não encaminhar, opção somente criptografia, modelos padrão e personalizados|
|**Tipo de destinatário suportado**|Somente destinatários externos|Somente destinatários internos|Destinatários internos e externos|
|**Experiência para o destinatário**|Destinatários externos receberam uma mensagem HTML que eles baixaram e abriram em um navegador ou aplicativo móvel baixado.|Os destinatários internos receberam apenas emails criptografados no Outlook para Windows, no Outlook para Mac e no Outlook na Web.|Destinatários internos e externos recebem emails no Outlook para Windows, no Outlook para Mac, no Outlook na Web, no Outlook para Android e no Outlook para iOS ou por meio de um portal da Web, independentemente de estarem ou não na mesma organização ou em qualquer organização. O portal do OME não requer download separado.|
|**Traga seu próprio suporte de chave**|Não disponível|Não disponível| BYOK com suporte|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>Como habilitar os novos recursos do OME para minha organização?

Confira [configurar os novos recursos de criptografia de mensagens do Office 365](set-up-new-message-encryption-capabilities.md).
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>A versão anterior do OME será preterida?

Você ainda pode usar a versão anterior do OME, ela não será preterida no momento. No entanto, incentivamos as organizações a usar a solução nova e aprimorada do OME. Os clientes que ainda não implantaram o OME não podem configurar uma nova implantação da versão anterior do OME.
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>Minha organização usa o Active Directory Rights Management, posso usar essa funcionalidade?

Não. Se estiver usando o Exchange Online com o Active Directory Rights Management Service (AD RMS), você não poderá habilitar esses novos recursos imediatamente. Em vez disso, você precisa [migrar primeiro o AD RMS para a proteção de informações do Azure](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) .
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>Minha organização tem uma implantação híbrida do Exchange. Posso usar esse recurso?

Os usuários locais podem enviar mensagens criptografadas usando regras de fluxo de email do Exchange Online. Para fazer isso, você precisa encaminhar emails pelo Exchange Online. Para obter mais informações, consulte [parte 2: configurar o email para que ele flua do seu servidor de email para o Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365).
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>Qual cliente de email preciso usar para criar uma mensagem criptografada do OME? Quais aplicativos têm suporte para o envio de mensagens protegidas?

Você pode criar mensagens protegidas do Outlook 2016 e do Outlook 2013 para Windows e Mac e do Outlook na Web.
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>Quais clientes de email têm suporte para ler e responder a emails protegidos?

Os usuários do Microsoft 365 podem ler e responder do Outlook para Windows e Mac (2013 e 2016), Outlook na Web e Outlook Mobile (Android e iOS). Você também pode usar o cliente de correio nativo do iOS se sua organização permitir. Se você não for um usuário do Microsoft 365, poderá ler e responder a mensagens criptografadas na Web através do navegador da Web.
  
## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>Quais tipos de arquivo são suportados como anexos em emails protegidos? Os anexos herdam as políticas de proteção associadas a emails protegidos?

Você pode anexar qualquer tipo de arquivo a um email protegido, no entanto, as políticas de proteção são aplicadas somente nos formatos de arquivo mencionados [aqui](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types).
  
Se houver suporte para um formato de arquivo, como um arquivo do Word, Excel ou PowerPoint, o arquivo estará sempre protegido, mesmo depois que o anexo tiver sido baixado pelo destinatário. Por exemplo, se um anexo estiver protegido por não encaminhar, e o destinatário original baixar e encaminhar o anexo para um novo destinatário, o novo destinatário não poderá abrir o arquivo protegido.
  
## <a name="are-pdf-file-attachments-supported"></a>Há suporte para anexos de arquivos PDF?

A resposta curta é sim! A criptografia de PDF permite proteger documentos PDF confidenciais por meio de comunicação segura ou colaboração segura. Quando você envia um email, o serviço do Office 365 criptografa anexos de arquivo PDF não o cliente Outlook.

Para o Outlook na Web, Outlook para iOS e Outlook para Android, você pode criptografar PDFs enviados sem nenhuma etapa adicional. Esses clientes oferecem suporte nativo à criptografia PDF.

O Outlook desktop não oferece suporte nativo à criptografia de anexos de arquivos PDF. Em vez disso, você precisará configurar as regras de fluxo de email do Exchange ou DLP para aplicar a criptografia a anexos em PDF primeiro. Quando você envia emails da área de trabalho do Outlook com um anexo em PDF, o cliente envia a mensagem com o anexo para o serviço primeiro. Quando o serviço recebe o arquivo, o serviço aplica a proteção OME da política de prevenção contra perda de dados (DLP) ou regra de fluxo de emails no Exchange Online. Em seguida, o Exchange Online envia a mensagem com o anexo de arquivo PDF protegido.

Para habilitar a criptografia para anexos em PDF, execute o seguinte comando no [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):

```powershell
Set-IRMConfiguration -EnablePdfEncryption $true
```

## <a name="are-onedrive-for-business-attachments-supported"></a>Há suporte para anexos do OneDrive for Business?

Not yet. Não há suporte para anexos do OneDrive for Business, e os usuários finais não podem criptografar um email que contenha um anexo do OneDrive for Business em nuvem.
  
## <a name="what-email-clients-support-preview-of-encrypted-attachments-in-protected-emails"></a>Quais clientes de email dão suporte à visualização de anexos criptografados em emails protegidos?

Quando os anexos são protegidos com um email protegido, os clientes do Outlook oferecem a capacidade do tha de visualizar o documento diretamente. O Outlook oferece suporte à visualização de documentos do Office (docx, xlsx, pptx, Doc, xls, ppt). O Outlook na Web oferece suporte à visualização de documentos do Office (docx, xlsx, pptx) e PDF.  

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>Posso criptografar mensagens automaticamente Configurando políticas?

Sim. Use regras de fluxo de email no Exchange Online para criptografar automaticamente uma mensagem com base em determinadas condições. Por exemplo, você pode criar políticas com base na ID do destinatário, domínio do destinatário ou no conteúdo do corpo ou assunto da mensagem. Consulte [definir regras de fluxo de emails para criptografar mensagens de email no Office 365](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail"></a>Posso remover automaticamente a criptografia em emails de entrada e de saída?

Os administradores podem configurar uma regra de fluxo de emails para remover a criptografia de emails de saída. Você não pode configurar uma regra para remover a criptografia de email de entrada.

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>Posso criptografar mensagens automaticamente Configurando políticas na prevenção de perda de dados (DLP) por &amp; meio do centro de conformidade de segurança?

Sim! Você pode configurar regras de fluxo de email no Exchange Online ou usando DLP no centro de &amp; conformidade de segurança.
  
## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>Posso personalizar mensagens criptografadas com a identidade visual da minha empresa?

Sim! Para obter informações sobre como personalizar mensagens de email e o portal do OME, consulte Adicionar a marca da sua organização às mensagens criptografadas. Confira [Adicionar a marca da sua organização às mensagens criptografadas](add-your-organization-brand-to-encrypted-messages.md).
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>Há alguma capacidade de relatórios ou insights para emails criptografados?

Há um relatório de criptografia no centro de segurança e conformidade. Confira [exibir relatórios de segurança de email no centro de conformidade de & de segurança](../security/office-365-security/view-email-security-reports.md).
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>Posso usar a criptografia de mensagem com recursos de conformidade, como eDiscovery?

Sim. Todas as mensagens de email criptografadas são detectáveis pelos recursos de conformidade do Microsoft 365.

## <a name="can-i-remove-encryption-from-email"></a>Posso remover a criptografia de email?

Os administradores podem configurar uma regra de fluxo de emails para remover a criptografia de emails de saída. Não é possível remover a criptografia usando uma regra de fluxo de emails de mensagens de entrada.

## <a name="is-delegated-access-supported"></a>Há suporte para o acesso delegado?

Não neste momento.

## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>Posso abrir mensagens criptografadas enviadas para uma caixa de correio compartilhada?

Sim! As mensagens criptografadas têm suporte para uma caixa de correio compartilhada.

- Os usuários podem abrir emails protegidos em uma caixa de correio compartilhada onde a caixa de correio compartilhada recebeu um email protegido como parte de um grupo de distribuição.

- Os usuários podem exibir anexos que herdam a proteção de email quando usam o Outlook para Windows, o Outlook para Mac e o Outlook na Web.

A tabela a seguir lista os clientes com suporte para caixas de correio compartilhadas.

| Plataforma | Ler email | Exibir anexos de email |
|----------|-----------|------------------------|
| Outlook na Web | Sim | Sim                |
| Outlook para Windows| Sim | Sim                |
| Outlook para Mac    | Sim | Sim                |
| Outlook para Android| Sim | Não                 |
| Outlook para iOS    | Sim | Não                 |
|

Há duas limitações conhecidas no momento:

- Só há suporte para o acesso fornecido pela atribuição direta do usuário à caixa de correio compartilhada. Não há suporte para atribuição por meio de um grupo de segurança habilitado para email.

- Não é possível abrir anexos de emails recebidos em dispositivos móveis usando o Outlook Mobile.
