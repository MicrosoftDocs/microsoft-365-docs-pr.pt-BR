---
title: Configurações de ASF no EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre as configurações avançadas de filtro de spam (ASF) que estão disponíveis em políticas antispam no Exchange Online Protection (EOP).
ms.openlocfilehash: b314b8b2a2de72987d9acff688602df0e0947293
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653336"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>Configurações avançadas de filtro de spam (ASF) no EOP

> [!NOTE]
> As configurações de ASF que estão atualmente disponíveis em políticas antispam estão em processo de ser preteridas. Recomendamos que você não use essas configurações em políticas antispam. A funcionalidade dessas configurações de ASF está sendo incorporada a outras partes da pilha de filtragem. Para obter mais informações, consulte [configurações de política antispam do EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).

Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, as configurações avançadas de filtro de spam (ASF) em políticas antispam (também conhecidas como políticas de filtro de spam ou políticas de filtro de conteúdo) permitem que os administradores marquem mensagens como spam com base em Propriedades de mensagens específicas. O ASF destina especificamente essas propriedades, pois elas são comumente encontradas em spam. Dependendo da propriedade, as detecções de ASF marcarão a mensagem como **spam** ou spam de **alta confiança**.

> [!NOTE]
> Habilitar uma ou mais das configurações de ASF é uma abordagem agressiva para a filtragem de spam. Não é possível relatar mensagens filtradas por ASF como falsos positivos. Você pode identificar mensagens que foram filtradas pelo ASF por:
> - Notificações periódicas de quarentena de spam do usuário final.
>
> - A presença de mensagens filtradas em quarentena.
>
> - Os `X-CustomSpam:` campos de cabeçalho X específicos que são adicionados às mensagens, conforme descrito neste tópico.

As seções a seguir descrevem as opções e as configurações de ASF que estão disponíveis em políticas antispam no centro de conformidade & segurança e no PowerShell do Exchange Online ou EOP PowerShell ([New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) e [set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)). Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).

## <a name="enable-disable-or-test-asf-settings"></a>Habilitar, desabilitar ou testar configurações de ASF

Para cada configuração de ASF, as seguintes opções estão disponíveis em políticas antispam:

- **Ativado**: o ASF adiciona o campo de cabeçalho X correspondente à mensagem e marca a mensagem como **spam** (SCL 5 ou 6 para [aumentar as configurações de Pontuação de spam](#increase-spam-score-settings)) ou spam de **alta confiança** (SCL 9 para [Marcar como configurações de spam](#mark-as-spam-settings)).

- **Off**: a configuração de ASF está desabilitada. Este é o valor padrão e recomendamos que você não o altere.

- **Test**: o ASF adiciona o campo de cabeçalho X correspondente à mensagem. O que acontece com a mensagem é determinado pelo valor de **Opções do modo de teste** (*TestModeAction*):

  - **Nenhum**: o roteamento de mensagens e a entrega não são afetados pela detecção de ASF. A mensagem ainda está sujeita a outros tipos de filtragem e regras no EOP.

  - **Adicionar texto do cabeçalho x padrão (*AddXHeader*)**: o valor X-header `X-CustomSpam: This message was filtered by the custom spam filter option` é adicionado à mensagem. Você pode usar esse valor em regras de caixa de entrada ou regras de fluxo de emails (também conhecidas como regras de transporte) para afetar o roteamento e a entrega da mensagem.

  - **Enviar mensagem Cco (*BccMessage*)**: os endereços de email especificados (o valor do parâmetro *TestModeBccToRecipients* no PowerShell) são adicionados ao campo Cco da mensagem e a mensagem é entregue aos destinatários Cco. No centro de conformidade & segurança, você separa vários endereços de email por ponto-e-vírgula (;). No PowerShell, você separa vários endereços de email por vírgulas.

  **Observações**:

  - O modo de teste não está disponível para as seguintes configurações ASF:

    - **Filtragem de ID de remetente condicional: falha de hardware** (*MarkAsSpamFromAddressAuthFail*)
    - **Inspersão de NDR**(*MarkAsSpamNdrBackscatter*)
    - **Registro SPF: falha de hardware** (*MarkAsSpamSpfRecordHardFail*)

  - A mesma ação de modo de teste é aplicada a *todas* as configurações de ASF definidas para **testar**. Você não pode configurar ações de modo de teste diferentes para diferentes configurações de ASF.

## <a name="increase-spam-score-settings"></a>Aumentar as configurações de Pontuação de spam

As configurações ASF a seguir definem o nível de confiança de spam (SCL) das mensagens detectadas como 5 ou 6, que corresponde ao veredicto de filtro de **spam** e à ação correspondente em políticas antispam.

****

|Configuração de política antispam|Descrição|X-cabeçalho adicionado|
|---|---|---|
|**Links de imagem para sites remotos** <br/><br/> *IncreaseScoreWithImageLinks*|As mensagens que contêm `<Img>` links de marca HTML para sites remotos (por exemplo, usando http) são marcadas como spam.|`X-CustomSpam: Image links to remote sites`|
|**URL redirecionada para outra porta** <br/><br/> *IncreaseScoreWithRedirectToOtherPort*|A mensagem que contém hiperlinks que redirecionam para portas TCP diferentes de 80 (HTTP), 8080 (HTTP alternativo) ou 443 (HTTPS) são marcadas como spam.|`X-CustomSpam: URL redirect to other port`|
|**Endereço IP numérico na URL** <br/><br/> *IncreaseScoreWithNumericIps*|As mensagens que contêm URLs com base em números (normalmente, endereços IP) são marcadas como spam.|`X-CustomSpam: Numeric IP in URL`|
|**URL para sites da web .biz ou .info** <br/><br/> *IncreaseScoreWithBizOrInfoUrls*|As mensagens que contêm links. biz ou. info no corpo da mensagem são marcadas como spam.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>Marcar como configurações de spam

As configurações ASF a seguir definem o SCL das mensagens detectadas para 9, que corresponde à veredicto de filtro de **spam de alta confiança** e a ação correspondente em políticas antispam.

****

|Configuração de política antispam|Descrição|X-cabeçalho adicionado|
|---|---|---|
|**Mensagens vazias** <br/><br/> *MarkAsSpamEmptyMessages*|Mensagens sem assunto, sem conteúdo no corpo da mensagem e nenhum anexo está marcado como spam de alta confiança.|`X-CustomSpam: Empty Message`|
|**JavaScript ou VBScript em HTML** <br/><br/> *MarkAsSpamJavaScriptInHtml*|As mensagens que usam JavaScript ou Visual Basic Script Edition em HTML são marcadas como spam de alta confiança. <br/><br/> Essas linguagens de script são usadas em mensagens de email para fazer com que ações específicas ocorram automaticamente.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Estrutura ou IMarcas da estrutura em HTML** <br><br/> *MarkAsSpamFramesInHtml*|As mensagens que contêm `<frame>` ou `<iframe>` marcas HTML são marcadas como spam de alta confiança. <br/><br/> Essas marcas são usadas em mensagens de email para formatar a página para exibir texto ou elementos gráficos.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Marcas de objeto em HTML** <br><br/> *MarkAsSpamObjectTagsInHtml*|As mensagens que contêm `<object>` marcas HTML são marcadas como spam de alta confiança. <br/><br/> Essa marca permite que plug-ins ou aplicativos sejam executados em uma janela HTML.|`X-CustomSpam: Object tag in html`|
|**Marcas de inserção em HTML** <br><br/> *MarkAsSpamEmbedTagsInHtml*|A mensagem que contém `<embed>` marcas HTML são marcadas como spam de alta confiança. <br/><br/> Essa marca permite a incorporação de diferentes tipos de documentos de tipos de dados variados em um documento HTML (por exemplo, sons, filmes ou imagens).|`X-CustomSpam: Embed tag in html`|
|**Marca de Formulároo em HTML** <br><br/> *MarkAsSpamFormTagsInHtml*|As mensagens que contêm `<form>` marcas HTML são marcadas como spam de alta confiança. <br/><br/> Essa marca é usada para criar formulários de site. Os anúncios de email geralmente incluem essa marca para solicitar informações do destinatário.|`X-CustomSpam: Form tag in html`|
|**Erros da web em HTML** <br><br/> *MarkAsSpamWebBugsInHtml*|Um *Web bug* (também conhecido como um *Web beacon*) é um elemento gráfico (geralmente, como um pixel de um pixel) que é usado em mensagens de email para determinar se a mensagem foi lida. <br/><br/> As mensagens que contêm Web bugs são marcadas como spam de alta confiança. <br/><br/> Boletins informativos legítimos podem usar Web bugs, embora muitas considerem essa invasão de privacidade. |`X-CustomSpam: Web bug`|
|**Aplicar lista de palavras sensíveis** <br><br/> *MarkAsSpamSensitiveWordList*|A Microsoft mantém uma lista dinâmica, mas não editável, de palavras associadas a mensagens potencialmente ofensivas. <br/><br/> As mensagens que contêm palavras da lista de palavras confidenciais no assunto ou no corpo da mensagem são marcadas como spam de alta confiança.|`X-CustomSpam: Sensitive word in subject/body`|
|**Registro SPF: falha grave** <br><br/> *MarkAsSpamSpfRecordHardFail*|As mensagens enviadas de um endereço IP não especificado no registro SPF (Sender Policy Framework) do SPF no DNS para o domínio de email de origem são marcadas como spam de alta confiança. <br/><br/> O modo de teste não está disponível para esta configuração.|`X-CustomSpam: SPF Record Fail`|
|**Filtragem de ID por remetente condicional: falha grave** <br><br/> *MarkAsSpamFromAddressAuthFail*|Mensagens que a verificação de falha grave de ID de remetente condicional são marcadas como spam. <br/><br/> Essa configuração combina uma verificação de SPF com uma verificação de ID de remetente para ajudar a proteger contra cabeçalhos de mensagens que contêm remetentes falsificados. <br/><br/> O modo de teste não está disponível para esta configuração.|`X-CustomSpam: SPF From Record Fail`|
|**Backscatter NDR** <br><br/> *MarkAsSpamNdrBackscatter*|*Dispersa* são notificações de falha na entrega inúteis (também conhecidas como NDRs ou mensagens de devolução) causadas por remetentes falsificados em mensagens de email. Para obter mais informações, consulte [mensagens de inspersão e EOP](backscatter-messages-and-eop.md). <br/><br/> Não é necessário definir essa configuração nos seguintes ambientes, pois os NDRs legítimos são entregues e a inspersão é marcada como spam: <ul><li>Microsoft 365 organizações com caixas de correio do Exchange Online.</li><li>Organizações de email locais onde você encaminha emails de *saída* por meio do EOP.</li></ul><br/> Em ambientes autônomos do EOP que protegem os emails de entrada para caixas de correio locais, ativar ou desativar essa configuração tem o seguinte resultado: <ul><li> **Ativado**: os NDRs legítimos são entregues e a inspersão é marcada como spam.</li><li>**Off**: NDRs legítimos e dispersa passam por filtragem de spam normal. Os NDRs mais legítimos serão entregues ao remetente da mensagem original. Algumas, mas não todas, o dispersão são marcadas como spam de alta confiança. Por definição, o dispersão só pode ser entregue ao remetente falsificado, e não ao remetente original.</li></ul><br/> O modo de teste não está disponível para esta configuração.|`X-CustomSpam: Backscatter NDR`|
|
