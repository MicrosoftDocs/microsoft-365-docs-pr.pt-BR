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
description: Os administradores podem aprender sobre as configurações do Filtro de Spam Avançado (ASF) disponíveis em políticas anti-spam no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 618a3bc24e9053236eca84d4edede4c3b550a481
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921871"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>Configurações avançadas de Filtro de Spam (ASF) no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> As configurações ASF que estão disponíveis atualmente em políticas anti-spam estão em processo de preterido. Recomendamos que você não use essas configurações em políticas anti-spam. A funcionalidade dessas configurações ASF está sendo incorporada a outras partes da pilha de filtragem. Para obter mais informações, consulte [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).

Em todas as organizações do Microsoft 365, as configurações do Filtro de Spam Avançado (ASF) em políticas anti-spam no EOP permitem que os administradores marquem mensagens como spam com base em propriedades de mensagem específicas. O ASF direciona especificamente essas propriedades porque elas são comumente encontradas em spam. Dependendo da propriedade, as detecções ASF marcarão a mensagem como Spam ou **spam** **de alta confiança.**

> [!NOTE]
> Habilenciar uma ou mais configurações do ASF é uma abordagem agressiva para a filtragem de spam. Não é possível relatar mensagens filtradas pelo ASF como falsos positivos. Você pode identificar mensagens que foram filtradas pelo ASF por:
>
> - Notificações periódicas de quarentena de spam do usuário final.
>
> - A presença de mensagens filtradas em quarentena.
>
> - Os campos `X-CustomSpam:` de header X específicos que são adicionados às mensagens conforme descrito neste artigo.

As seções a seguir descrevem as configurações e as opções ASF que estão disponíveis em políticas anti-& spam no Centro de Conformidade e Segurança e no PowerShell do Exchange Online ou no EOP PowerShell autônomo ([New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy) e [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)). Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).

## <a name="enable-disable-or-test-asf-settings"></a>Habilitar, desabilitar ou testar configurações ASF

Para cada configuração ASF, as seguintes opções estão disponíveis em políticas anti-spam:

- **On**: ASF adiciona o campo de header X correspondente à mensagem e marca a mensagem como **Spam** (SCL 5 ou 6 para Aumentar configurações de pontuação de spam [)](#increase-spam-score-settings)ou spam de alta confiança (SCL 9 para Mark como configurações de **spam** ). [](#mark-as-spam-settings)

- **Desativado**: a configuração ASF está desabilitada. Esse é o valor padrão e recomendamos que você não altere.

- **Teste**: ASF adiciona o campo de header X correspondente à mensagem. O que acontece com a mensagem é determinado pelo valor **Opções de** modo de teste (*TestModeAction*).

  - **Nenhum**: a entrega de mensagens não é afetada pela detecção ASF. A mensagem ainda está sujeita a outros tipos de filtragem e regras no EOP.

  - **Adicionar texto de header X padrão (*AddXHeader*)**: o valor de header X `X-CustomSpam: This message was filtered by the custom spam filter option` é adicionado à mensagem. Você pode usar esse valor em regras de caixa de entrada ou regras de fluxo de emails (também conhecidas como regras de transporte) para afetar a entrega da mensagem.

  - **Enviar mensagem Bcc (*BccMessage*)**: Os endereços de email especificados (o valor do parâmetro *TestModeBccToRecipients* no PowerShell) são adicionados ao campo Cc da mensagem e a mensagem é entregue aos destinatários Cc adicionais. No Centro de Conformidade & segurança, você separa vários endereços de email por ponto-e-vírgula (;). No PowerShell, você separa vários endereços de email por vírgulas.

  **Observações**:

  - O modo de teste não está disponível para as seguintes configurações ASF:

    - **Filtragem de ID do Remetente Condicional: falha dura** (*MarkAsSpamFromAddressAuthFail*)
    - **Backscatter de NDR**(*MarkAsSpamNdrBackscatter*)
    - **Registro SPF: falha grave** (*MarkAsSpamSpfRecordHardFail*)

  - A mesma ação de modo de teste é aplicada a todas *as* configurações ASF definidas como **Test**. Não é possível configurar diferentes ações de modo de teste para configurações ASF diferentes.

## <a name="increase-spam-score-settings"></a>Aumentar as configurações de pontuação de spam

As configurações ASF a seguir definirão o nível de confiança de spam (SCL) das mensagens detectadas como 5 ou 6, que corresponde ao veredito do filtro de **spam** e à ação correspondente em políticas anti-spam.

****

|Configuração de política anti-spam|Descrição|Header X adicionado|
|---|---|---|
|**Links de imagem para sites remotos** <p> *IncreaseScoreWithImageLinks*|As mensagens que `<Img>` contêm links de marca HTML para sites remotos (por exemplo, usando http) são marcadas como spam.|`X-CustomSpam: Image links to remote sites`|
|**URL redirecionada para outra porta** <p> *IncreaseScoreWithRedirectToOtherPort*|A mensagem que contém hiperlinks que redirecionam para portas TCP diferentes de 80 (HTTP), 8080 (HTTP alternativo) ou 443 (HTTPS) são marcadas como spam.|`X-CustomSpam: URL redirect to other port`|
|**Endereço IP numérico na URL** <p> *IncreaseScoreWithNumericIps*|As mensagens que contêm URLs baseadas em numéricos (normalmente, endereços IP) são marcadas como spam.|`X-CustomSpam: Numeric IP in URL`|
|**URL para sites da web .biz ou .info** <p> *IncreaseScoreWithBizOrInfoUrls*|As mensagens que `.biz` contêm `.info` ou links no corpo da mensagem são marcadas como spam.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>Marcar como configurações de spam

As configurações asf a seguir definirão a SCL das mensagens detectadas como 9, que corresponde ao veredito do filtro de **spam** de alta confiança e à ação correspondente em políticas anti-spam.

****

|Configuração de política anti-spam|Descrição|Header X adicionado|
|---|---|---|
|**Mensagens vazias** <p> *MarkAsSpamEmptyMessages*|Mensagens sem assunto, sem conteúdo no corpo da mensagem e sem anexos são marcadas como spam de alta confiança.|`X-CustomSpam: Empty Message`|
|**JavaScript ou VBScript em HTML** <p> *MarkAsSpamJavaScriptInHtml*|As mensagens que usam JavaScript ou Visual Basic Script Edition em HTML são marcadas como spam de alta confiança. <p> Esses idiomas de script são usados em mensagens de email para fazer com que ações específicas ocorram automaticamente.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Estrutura ou IMarcas da estrutura em HTML** <p> *MarkAsSpamFramesInHtml*|As mensagens que `<frame>` contêm ou `<iframe>` marcas HTML são marcadas como spam de alta confiança. <p> Essas marcas são usadas em mensagens de email para formatar a página para exibição de texto ou gráficos.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Marcas de objeto em HTML** <p> *MarkAsSpamObjectTagsInHtml*|As mensagens que contêm `<object>` marcas HTML são marcadas como spam de alta confiança. <p> Essa marca permite que plug-ins ou aplicativos executem em uma janela HTML.|`X-CustomSpam: Object tag in html`|
|**Marcas de inserção em HTML** <p> *MarkAsSpamEmbedTagsInHtml*|A mensagem que contém `<embed>` marcas HTML são marcadas como spam de alta confiança. <p> Essa marca permite a incorporação de diferentes tipos de documentos em um documento HTML (por exemplo, sons, vídeos ou imagens).|`X-CustomSpam: Embed tag in html`|
|**Marca de Formulároo em HTML** <p> *MarkAsSpamFormTagsInHtml*|As mensagens que contêm `<form>` marcas HTML são marcadas como spam de alta confiança. <p> Essa marca é usada para criar formulários de site. Anúncios de email geralmente incluem essa marca para solicitar informações do destinatário.|`X-CustomSpam: Form tag in html`|
|**Erros da web em HTML** <p> *MarkAsSpamWebBugsInHtml*|Um *bug da Web* (também conhecido como web *beacon*) é um elemento gráfico (geralmente tão pequeno quanto um pixel por um pixel) que é usado em mensagens de email para determinar se a mensagem foi lida pelo destinatário. <p> As mensagens que contêm bugs da Web são marcadas como spam de alta confiança. <p> Boletins informativos legítimos podem usar bugs da Web, embora muitos considerem isso uma invasão de privacidade. |`X-CustomSpam: Web bug`|
|**Aplicar lista de palavras sensíveis** <p> *MarkAsSpamSensitiveWordList*|A Microsoft mantém uma lista dinâmica, mas não editável de palavras associadas a mensagens potencialmente ofensivas. <p> As mensagens que contêm palavras da lista de palavras confidenciais no assunto ou no corpo da mensagem são marcadas como spam de alta confiança.|`X-CustomSpam: Sensitive word in subject/body`|
|**Registro SPF: falha grave** <p> *MarkAsSpamSpfRecordHardFail*|As mensagens enviadas de um endereço IP que não está especificado no registro SPF (Estrutura de Política de Remetente) do SPF no DNS para o domínio de email de origem são marcadas como spam de alta confiança. <p> O modo de teste não está disponível para essa configuração.|`X-CustomSpam: SPF Record Fail`|
|**Filtragem de ID por remetente condicional: falha grave** <p> *MarkAsSpamFromAddressAuthFail*|As mensagens com falha grave em uma verificação de ID de Remetente condicional são marcadas como spam. <p> Essa configuração combina uma verificação SPF com uma verificação de ID do Remetente para ajudar a proteger contra os headers de mensagens que contêm remetentes forjados. <p> O modo de teste não está disponível para essa configuração.|`X-CustomSpam: SPF From Record Fail`|
|**Backscatter NDR** <p> *MarkAsSpamNdrBackscatter*|*Backscatter* é relatórios de não entrega inúteis (também conhecidos como NDRs ou mensagens de bounce) causados por envios forjados em mensagens de email. Para obter mais informações, consulte [Backscatter messages and EOP](backscatter-messages-and-eop.md). <p> Você não precisa configurar essa configuração nos seguintes ambientes, pois as NDRs legítimas são entregues e o backscatter é marcado como spam: <ul><li>Organizações do Microsoft 365 com caixas de correio do Exchange Online.</li><li>Organizações de email locais onde você *roteia* emails de saída por meio do EOP.</li></ul> <p> Em ambientes EOP autônomos que protegem emails de entrada para caixas de correio locais, a a opção de ligar ou desligar essa configuração tem o seguinte resultado: <ul><li> **On**: NDRs legítimos são entregues e backscatter é marcado como spam.</li><li>**Off**: NDRs legítimos e backscatter passam por filtragem de spam normal. A maioria das NDRs legítimas será entregue ao remetente da mensagem original. Alguns, mas não todos, backscatter são marcados como spam de alta confiança. Por definição, o backscatter só pode ser entregue ao remetente spoofed, não ao remetente original.</li></ul> <p> O modo de teste não está disponível para essa configuração.|`X-CustomSpam: Backscatter NDR`|
|