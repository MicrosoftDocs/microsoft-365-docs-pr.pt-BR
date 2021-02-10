---
title: Configurações ASF no EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem saber mais sobre as configurações do Filtro de Spam Avançado (ASF) disponíveis nas políticas anti-spam no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ec316c98befada7a793f525be909ba0b8fa5e3ae
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2021
ms.locfileid: "50176046"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>Configurações avançadas de Filtro de Spam (ASF) no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!NOTE]
> As configurações ASF atualmente disponíveis em políticas anti-spam estão em processo de preterido. Recomendamos que você não use essas configurações em políticas anti-spam. A funcionalidade dessas configurações ASF está sendo incorporada em outras partes da pilha de filtragem. Para obter mais informações, consulte [as configurações de política anti-spam do EOP.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

Em todas as organizações do Microsoft 365, as configurações de Filtro de Spam Avançado (ASF) nas políticas anti-spam no EOP permitem que os administradores marquem as mensagens como spam com base em propriedades de mensagens específicas. O ASF direciona especificamente essas propriedades porque elas são comumente encontradas em spam. Dependendo da propriedade, as detecções ASF marcarão a mensagem como **spam** ou **spam de alta confiança.**

> [!NOTE]
> A habilitação de uma ou mais configurações de ASF é uma abordagem agressiva para a filtragem de spam. Não é possível relatar mensagens filtradas por ASF como falsos positivos. Você pode identificar mensagens que foram filtradas pelo ASF por:
>
> - Notificações periódicas de quarentena de spam do usuário final.
>
> - A presença de mensagens filtradas em quarentena.
>
> - Os campos `X-CustomSpam:` X-header específicos que são adicionados às mensagens, conforme descrito neste artigo.

As seções a seguir descrevem as configurações e opções ASF disponíveis em políticas anti-& spam no Centro de Conformidade e Segurança e no PowerShell do Exchange Online ou no PowerShell do EOP autônomo ([New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) e [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)). Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).

## <a name="enable-disable-or-test-asf-settings"></a>Habilitar, desabilitar ou testar configurações ASF

Para cada configuração ASF, as seguintes opções estão disponíveis em políticas anti-spam:

- **On**: ASF adds the corresponding X-header field to the message, and either marks the message as **Spam** (SCL 5 or 6 for [Increase spam score settings](#increase-spam-score-settings)) or **High confidence spam** (SCL 9 for Mark as [spam settings](#mark-as-spam-settings)).

- **Desativado:** a configuração ASF está desabilitada. Esse é o valor padrão, e recomendamos que você não o altere.

- **Teste:** o ASF adiciona o campo X-header correspondente à mensagem. O que acontece com a mensagem é determinado pelo valor **de opções** do modo de teste (*TestModeAction).*

  - **Nenhum**: a entrega de mensagens não é afetada pela detecção de ASF. A mensagem ainda está sujeita a outros tipos de filtragem e regras no EOP.

  - **Adicione texto de X-header padrão (*AddXHeader*)**: o valor de X-header `X-CustomSpam: This message was filtered by the custom spam filter option` é adicionado à mensagem. Você pode usar esse valor em regras de Caixa de Entrada ou regras de fluxo de email (também conhecidas como regras de transporte) para afetar a entrega da mensagem.

  - **Enviar mensagem Cc (*BccMessage*)**: os endereços de email especificados (o valor de parâmetro *TestModeBccToRecipients* no PowerShell) são adicionados ao campo Cc da mensagem, e a mensagem é entregue aos destinatários Cc adicionais. No Centro de Conformidade & segurança, separe vários endereços de email por ponto-e-vírgula (;). No PowerShell, você separa vários endereços de email por vírgulas.

  **Observações**:

  - O modo de teste não está disponível para as seguintes configurações ASF:

    - **Filtragem condicional de ID de Remetente: falha grave** (*MarkAsSpamFromAddressAuthFail*)
    - **Backscatter de NDR**(*MarkAsSpamNdrBackscatter*)
    - **Registro SPF: falha grave** (*MarkAsSpamSpfRecordHardFail*)

  - A mesma ação de modo de teste é aplicada a *todas as* configurações ASF definidas como **Test**. Você não pode configurar diferentes ações de modo de teste para configurações ASF diferentes.

## <a name="increase-spam-score-settings"></a>Aumentar as configurações da pontuação de spam

As configurações ASF a seguir configuram o nível de confiança de spam (SCL) das mensagens detectadas como 5 ou 6, que corresponde ao veredito do filtro de **Spam** e à ação correspondente nas políticas anti-spam.

****

|Configuração de política anti-spam|Descrição|X-header adicionado|
|---|---|---|
|**Links de imagem para sites remotos** <p> *IncreaseScoreWithImageLinks*|As mensagens que contêm links de marca HTML para sites remotos `<Img>` (por exemplo, usando http) são marcadas como spam.|`X-CustomSpam: Image links to remote sites`|
|**URL redirecionada para outra porta** <p> *IncreaseScoreWithRedirectToOtherPort*|As mensagens que contêm hiperlinks que redirecionam para portas TCP diferentes de 80 (HTTP), 8080 (HTTP alternativo) ou 443 (HTTPS) são marcadas como spam.|`X-CustomSpam: URL redirect to other port`|
|**Endereço IP numérico na URL** <p> *IncreaseScoreWithNumericIps*|As mensagens que contêm URLs baseadas em numéricos (normalmente, endereços IP) são marcadas como spam.|`X-CustomSpam: Numeric IP in URL`|
|**URL para sites da web .biz ou .info** <p> *IncreaseScoreWithBizOrInfoUrls*|As mensagens que `.biz` `.info` contêm ou links no corpo da mensagem são marcadas como spam.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>Marcar como configurações de spam

As configurações ASF a seguir configuram o SCL das mensagens detectadas como 9, que corresponde ao veredito do filtro de **spam** de alta confiança e à ação correspondente nas políticas anti-spam.

****

|Configuração de política anti-spam|Descrição|X-header adicionado|
|---|---|---|
|**Mensagens vazias** <p> *MarkAsSpamEmptyMessages*|Mensagens sem assunto, sem conteúdo no corpo da mensagem e sem anexos são marcadas como spam de alta confiança.|`X-CustomSpam: Empty Message`|
|**JavaScript ou VBScript em HTML** <p> *MarkAsSpamJavaScriptInHtml*|Mensagens que usam JavaScript ou Visual Basic Script Edition em HTML são marcadas como spam de alta confiança. <p> Esses idiomas de script são usados em mensagens de email para fazer com que ações específicas ocorram automaticamente.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Estrutura ou IMarcas da estrutura em HTML** <p> *MarkAsSpamFramesInHtml*|As mensagens que `<frame>` contêm ou `<iframe>` marcas HTML são marcadas como spam de alta confiança. <p> Essas marcas são usadas em mensagens de email para formatar a página para exibição de texto ou gráficos.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Marcas de objeto em HTML** <p> *MarkAsSpamObjectTagsInHtml*|As mensagens que `<object>` contêm marcas HTML são marcadas como spam de alta confiança. <p> Essa marca permite que plug-ins ou aplicativos executem em uma janela HTML.|`X-CustomSpam: Object tag in html`|
|**Marcas de inserção em HTML** <p> *MarkAsSpamEmbedTagsInHtml*|As mensagens que contêm `<embed>` marcas HTML são marcadas como spam de alta confiança. <p> Essa marca permite a incorporação de diferentes tipos de documentos em um documento HTML (por exemplo, sons, vídeos ou imagens).|`X-CustomSpam: Embed tag in html`|
|**Marca de Formulároo em HTML** <p> *MarkAsSpamFormTagsInHtml*|As mensagens que contêm `<form>` marcas HTML são marcadas como spam de alta confiança. <p> Essa marca é usada para criar formulários de site. Os anúncios de email geralmente incluem essa marca para solicitar informações do destinatário.|`X-CustomSpam: Form tag in html`|
|**Erros da web em HTML** <p> *MarkAsSpamWebBugsInHtml*|Um bug da *Web* (também conhecido como *web beacon)* é um elemento gráfico (geralmente um pixel por pixel por pixel) usado em mensagens de email para determinar se a mensagem foi lida pelo destinatário. <p> As mensagens que contêm bugs da Web são marcadas como spam de alta confiança. <p> Boletins informativos legítimos podem usar bugs da Web, embora muitos considerem isso um erro de privacidade. |`X-CustomSpam: Web bug`|
|**Aplicar lista de palavras sensíveis** <p> *MarkAsSpamSensitiveWordList*|A Microsoft mantém uma lista dinâmica, mas não editável, de palavras associadas a mensagens potencialmente ofensivas. <p> As mensagens que contêm palavras da lista de palavras confidenciais no assunto ou no corpo da mensagem são marcadas como spam de alta confiança.|`X-CustomSpam: Sensitive word in subject/body`|
|**Registro SPF: falha grave** <p> *MarkAsSpamSpfRecordHardFail*|As mensagens enviadas de um endereço IP que não está especificado no registro SPF SPF Sender Policy Framework (SPF) no DNS para o domínio de email de origem são marcadas como spam de alta confiança. <p> O modo de teste não está disponível para essa configuração.|`X-CustomSpam: SPF Record Fail`|
|**Filtragem de ID por remetente condicional: falha grave** <p> *MarkAsSpamFromAddressAuthFail*|As mensagens com falha grave em uma verificação condicional de ID de Remetente são marcadas como spam. <p> Essa configuração combina uma verificação de SPF com uma verificação de ID de Remetente para ajudar a proteger contra os títulos de mensagens que contêm remetentes forjados. <p> O modo de teste não está disponível para essa configuração.|`X-CustomSpam: SPF From Record Fail`|
|**Backscatter NDR** <p> *MarkAsSpamNdrBackscatter*|*Backscatter* é um relatório de não entrega inútil (também conhecido como NDRs ou mensagens de salto) causadas por envios forjados em mensagens de email. Para obter mais informações, consulte [Backscatter messages and EOP](backscatter-messages-and-eop.md). <p> Você não precisa definir essa configuração nos seguintes ambientes, porque as notificações de indemnidade legítimas são entregues e o backscatter é marcado como spam: <ul><li>Organizações do Microsoft 365 com caixas de correio do Exchange Online.</li><li>Organizações de email locais para as quais você *encaminha emails de* saída por meio do EOP.</li></ul> <p> Em ambientes EOP autônomos que protegem o email de entrada para caixas de correio locais, ativas ou ativas dessa configuração tem o seguinte resultado: <ul><li> **On:** NDRs legítimas são entregues e backscatter é marcado como spam.</li><li>**Off:** NDRs legítimos e backscatter passam pela filtragem de spam normal. A maioria das NDRs legítimas será entregue ao remetente da mensagem original. Alguns, mas não todos, backscatter são marcados como spam de alta confiança. Por definição, backscatter só pode ser entregue ao remetente spoofed, não ao remetente original.</li></ul> <p> O modo de teste não está disponível para essa configuração.|`X-CustomSpam: Backscatter NDR`|
|
