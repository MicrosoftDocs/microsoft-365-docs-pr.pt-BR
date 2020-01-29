---
title: Remetente não verificado
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Para impedir que mensagens de phishing acessem sua caixa de correio, o Outlook.com e o Outlook na Web verificam se o remetente é quem dizem eles e marcam mensagens suspeitas como lixo eletrônico.
ms.openlocfilehash: b2f66e3aa275c01baf2b8bde3bcca2c3072b5443
ms.sourcegitcommit: 3f8957ddd04b8710bb5f314a0902fdee50c7c9b7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/28/2020
ms.locfileid: "41572697"
---
# <a name="unverified-sender"></a>Remetente não verificado

> [!NOTE]
> Essas atualizações estão sendo lançadas agora e talvez ainda não estejam disponíveis para todos os usuários. Esse recurso tem suporte para usuários do Enterprise outlook.com. No momento, ele não está disponível para clientes do outlook.com.

Para impedir que mensagens de phishing acessem sua caixa de correio, o Outlook.com e o Outlook na Web verificam se o remetente é quem dizem eles e marcam mensagens suspeitas como lixo eletrônico.

> [!IMPORTANT]
> Quando uma mensagem é marcada como um golpe de phishing, o Outlook.com e o Outlook na Web exibem um aviso na parte superior da página, mas todos os links na mensagem ainda podem ser abertos.

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a>Como identificar uma mensagem suspeita em minha caixa de entrada?

O Outlook.com e o Outlook na Web mostram indicadores quando o remetente de uma mensagem não pode ser identificado ou sua identidade é diferente da que você vê no endereço do remetente.

## <a name="you-see-a--in-the-sender-image"></a>Você vê um '? ' na imagem do remetente

Quando o Outlook.com e o Outlook na Web não conseguem verificar a identidade do remetente usando técnicas de autenticação de email, eles exibem um '? ' na foto do remetente.

![A mensagem não passou na verificação](../media/message-did-not-pass-verification.jpg)

Nem todas as mensagens que não são autenticadas são mal-intencionadas. No entanto, você deve ter cuidado para interagir com mensagens que não são autenticadas se você não reconhece o remetente. Ou, se você reconhece um remetente que normalmente não tem um '? ' na imagem do remetente, mas, repentinamente, você começa a vê-lo, que pode ser um sinal de que o remetente está sendo falsificado.

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a>Como gerenciar quais mensagens recebem o tratamento de remetentes não verificados 

Se você for um cliente do Office 365, poderá gerenciar esse recurso através do centro de conformidade & segurança do Office 365.

- No centro de conformidade & segurança, os administradores globais ou de segurança podem ativar ou desativar o recurso, através da proteção contra falsificação na política de anti-golpes. Além disso, você pode usar o cmdlet **set-AntiPhishPolicy** no PowerShell do Exchange Online. Para obter detalhes, consulte [proteção contra phishing no Office 365](anti-phishing-protection.md) e [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy).

    ![Edição de remetentes não autenticados na interface gráfica.](../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- Se um administrador identificou um falso positivo e um remetente não deve receber o tratamento de remetentes não verificados, uma das ações a seguir pode ser executada para adicionar o remetente à lista de permissões de falsificação de inteligência de falsificação:

  - Adicionar o par de domínios por meio da compreensão de inteligência de falsificação. Para obter detalhes, consulte [Walkthrough: spoof Intelligence percepção](walkthrough-spoof-intelligence-insight.md).

  - Adicione o par de domínios por meio do cmdlet **set-PhishFilterPolicy** no PowerShell do Exchange Online. Para obter detalhes, consulte [set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) e [set up Office 365 ATP anti-phishing and anti-phishing Policies](set-up-anti-phishing-policies.md).

Além disso, não aplicamos o tratamento de remetentes não verificados se a mensagem foi entregue à caixa de entrada via regras de fluxo de email (também conhecidas como regras de transporte), lista de domínios seguros (política antispam) ou lista de remetentes seguros.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a>Que critérios o Outlook.com e o Outlook na Web usam para adicionar as propriedades '? ' e ' via '?

Para o '? ' na imagem do remetente: Outlook.com requer que a mensagem passe o SPF ou a autenticação do DKIM e receba uma passagem dMarc ou uma passagem de autenticação composta da Office 365 spoof Intelligence. Para obter detalhes, consulte [set up SPF in Office 365 para ajudar a impedir a falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md) e [uso do DKIM para validar emails de saída enviados do seu domínio personalizado no Office 365](use-dkim-to-validate-outbound-email.md).

Para o via Tag: se o domínio no endereço de for diferente do domínio na assinatura do DKIM ou do email SMTP de, Outlook.com exibe o domínio em um desses dois campos (preferência à assinatura DKIM).

### <a name="how-do-i-remove-the-"></a>Como remover o '? '

Para o '? ' na imagem do remetente: como um remetente, você deve autenticar sua mensagem com o SPF ou o DKIM.

Para o via Tag: como um remetente, você deve garantir que o domínio na assinatura DKIM ou o email SMTP de seja o mesmo que ou seja um subdomínio de, o domínio no endereço de.

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a>O Outlook.com e o Outlook na Web mostram isso para cada mensagem que não aprova a autenticação?

Não necessariamente. O Outlook.com e o Outlook na Web podem ter outras propriedades dentro da mensagem para autenticar o remetente.

## <a name="related-topics"></a>Tópicos relacionados

[Ajudar a proteger sua conta de email do Outlook.com](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[Lidar com phishing ou falsificação no Outlook.com](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[Filtrar lixo eletrônico e spam no Outlook na Web](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
