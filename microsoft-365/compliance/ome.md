---
title: Criptografia de Mensagem
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 02/07/2020
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
ms.custom:
- seo-marvel-apr2020
description: Saiba como enviar e receber mensagens de email criptografadas entre pessoas dentro e fora da sua organização.
ms.openlocfilehash: f601618c3ad44361794720852b391949901122f2
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709617"
---
# <a name="message-encryption"></a>Criptografia de Mensagem

As pessoas geralmente usam email para trocar informações importantes, como dados financeiros, contratos, informações confidenciais de produtos, relatórios e projeções de vendas, informações sobre a saúde de pacientes ou informações sobre clientes e empregados. Portanto, as caixas de correio podem se tornar repositórios de grandes quantidades de informações potencialmente confidenciais, e o vazamento de informações pode se tornar uma séria ameaça à sua organização.

Com a Criptografia de Mensagem do Office 365, sua organização pode enviar e receber mensagens de email criptografadas entre pessoas dentro e fora da sua organização. A Criptografia de Mensagens do Office 365 funciona com Outlook.com, Yahoo!, Gmail e outros serviços de email. A criptografia de mensagem de email ajuda a garantir que apenas os destinatários pretendido possam exibir o conteúdo da mensagem.

## <a name="how-office-365-message-encryption-works"></a>Como funciona a Criptografia de Mensagens do Office 365

O restante deste artigo se aplica aos novos recursos do OME.

A Criptografia de Mensagens do Office 365 é um serviço online criado com base no Microsoft Azure Rights Management (Azure RMS), que faz parte da Proteção de Informações do Azure. Isso inclui políticas de criptografia, identidade e autorização para ajudar a proteger seu email. Você pode criptografar mensagens usando modelos de gerenciamento de direitos, a [opção](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)Não Encaminhar e a [opção somente criptografar.](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

Os usuários podem criptografar mensagens de email e vários anexos usando essas opções. Para uma lista completa de tipos de anexos com suporte, consulte "Tipos de arquivo cobertos por políticas de IRM quando estão anexados a mensagens" em Introdução ao IRM para mensagens [de email.](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)

Como administrador, você também pode definir regras de fluxo de emails para aplicar essa proteção. Por exemplo, você pode criar uma regra que exija a criptografia de todas as mensagens endereçadas a um destinatário específico ou que contenha palavras específicas na linha de assunto e também especifique que os destinatários não possam copiar ou imprimir o conteúdo da mensagem.

Ao contrário da versão anterior do OME, os novos recursos fornecem uma experiência unificada de remetentes, quer você esteja enviando emails dentro da sua organização ou para destinatários fora do Microsoft 365. Além disso, os destinatários que recebem uma mensagem de email protegida enviada para uma conta do Microsoft 365 no Outlook 2016 ou no Outlook na Web, não têm que tomar medidas adicionais para exibir a mensagem. Ele funciona perfeitamente. Os destinatários que usam outros clientes de email e provedores de serviços de email também têm uma experiência aprimorada. Para saber mais, confira Saiba mais sobre mensagens protegidas no [Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) e como abrir [uma mensagem protegida.](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)

Para uma lista detalhada das diferenças entre a versão anterior do OME e os novos recursos do OME, consulte [Comparar versões do OME.](ome-version-comparison.md)

Quando alguém envia uma mensagem de email que corresponde a uma regra de fluxo de emails de criptografia, ela é criptografada antes de ser enviada. Todos os usuários finais do Microsoft 365 que usam clientes do Outlook para ler emails recebem experiências nativas de leitura de primeira classe para emails criptografados e protegidos por direitos, mesmo que não esteja na mesma organização que o remetente. Os clientes do Outlook com suporte incluem a área de trabalho do Outlook, o Outlook Para Mac, o Outlook Mobile para iOS e Android e o Outlook na Web (anteriormente conhecido como Outlook Web App).

Destinatários de mensagens criptografadas que recebem emails criptografados ou protegidos por direitos enviados para suas contas do Outlook.com, Gmail e Yahoo recebem um email de wrapper que os direciona para o Portal do OME onde eles podem autenticar facilmente usando uma conta da Microsoft, Gmail ou credenciais do Yahoo.

Os usuários finais que leem emails criptografados ou protegidos por direitos em clientes que não são do Outlook também usam o portal do OME para exibir mensagens criptografadas e protegidas por direitos que recebem.

Se o remetente do email protegido estiver no GCC Alto e o destinatário estiver fora do GCC High, incluindo usuários comerciais, usuários do Outlook.com e usuários de outros provedores de email, como o Gmail, o destinatário receberá um email wrapper. O email do wrapper direciona o destinatário para o Portal do OME onde o destinatário é capaz de ler e responder à mensagem. Caso contrário, se o remetente e o destinatário estão no ambiente GCC High, mesmo que não esteja na mesma organização, os destinatários que usam clientes do Outlook para ler emails recebem experiências nativas de leitura de primeira classe para emails criptografados e protegidos por direitos. Para obter mais informações sobre a experiência diferente na GCC High, consulte [Comparar versões do OME.](ome-version-comparison.md)

Para obter mais informações sobre limites de tamanho para mensagens e anexos que você pode criptografar usando o OME, consulte [Limites do Exchange Online.](https://technet.microsoft.com/library/exchange-online-limits.aspx)

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Como funciona a Criptografia Avançada de Mensagens do Office 365 sobre o OME

A Criptografia Avançada de Mensagens do Office 365 permite criar vários modelos de identidade visual para que você possa ajustar o controle sobre o email do destinatário e criar experiências de identidade visual personalizadas para dar suporte a uma estrutura organizacional diversificada.

A Criptografia Avançada de Mensagens no Microsoft 365 ajuda você a cumprir obrigações de conformidade que exigem um controle mais flexível sobre o acesso do destinatário externo a emails criptografados. Com a Criptografia Avançada de Mensagens no Office 365, como administrador, você pode controlar emails confidenciais compartilhados fora da organização com políticas automáticas que detectam tipos de informações confidenciais (por exemplo, IDs de pii, financeiros ou de saúde) ou palavras-chave para aprimorar a proteção expirando o acesso por meio de um portal da Web seguro para emails criptografados. Como administrador, você pode controlar ainda mais os emails criptografados acessados por meio de um portal da Web do Microsoft 365 revogando o acesso a um email a qualquer momento.

A revogação e a expiração de mensagens só funcionam para emails que seus usuários enviam a destinatários fora da sua organização. Além disso, os destinatários devem acessar o email por meio do portal da Web. Para garantir que o destinatário use o portal para receber emails, você configura um modelo de identidade visual personalizado que aplica o wrapper. Em seguida, você aplica o modelo de identidade visual em uma regra de fluxo de emails. Para saber mais sobre a Criptografia Avançada de Mensagens, confira a Criptografia de Mensagem Avançada do [Office 365.](ome-advanced-message-encryption.md)

## <a name="defining-rules-for-office-365-message-encryption"></a>Definir regras para a Criptografia de Mensagens do Office 365

Uma maneira de habilitar os novos recursos de Criptografia de Mensagens do Office 365 é para que os administradores do Exchange Online e do Proteção do Exchange Online definam regras de fluxo de emails. Essas regras determinam em quais condições as mensagens de email devem ser criptografadas. Quando uma ação de criptografia é definida para uma regra, todas as mensagens que corresponderem às condições da regra serão criptografadas antes de elas ser enviadas.

As regras de fluxo de emails são flexíveis, o que permite combinar condições para que você possa atender a requisitos de segurança específicos em uma única regra. Por exemplo, você pode criar uma regra para criptografar todas as mensagens que contenham palavras-chave específicas e que sejam endereçadas a destinatários externos. Os novos recursos de Criptografia de Mensagem do Office 365 também criptografam respostas de destinatários de email criptografado.

Para obter mais informações sobre como criar regras de fluxo de emails para aproveitar os novos recursos do OME, consulte Definir regras para a Criptografia de Mensagens do [Office 365.](define-mail-flow-rules-to-encrypt-email.md)

## <a name="get-started-with-the-new-ome-capabilities"></a>Começar a trabalhar com os novos recursos do OME

Se você estiver pronto para começar a usar os novos recursos do OME em sua organização, confira Configurar novos recursos de Criptografia de Mensagem do [Office 365.](set-up-new-message-encryption-capabilities.md)

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>Enviar, visualizar e responder mensagens de email criptografadas

Com a Criptografia de Mensagem do Office 365, os usuários podem enviar emails criptografados do Outlook e do Outlook na Web. Além disso, os administradores podem configurar regras de fluxo de emails no Microsoft 365 para criptografar emails automaticamente com base na correspondência de palavras-chave ou em outras condições.

Os destinatários de mensagens criptografadas que estão nas organizações poderão ler essas mensagens perfeitamente em qualquer versão do Outlook, incluindo Outlook para PC, Outlook para Mac, Outlook na Web, Outlook para iOS e Outlook para Android. Os usuários que recebem mensagens criptografadas em outros clientes de email podem exibir as mensagens no portal do OME.

Para obter orientações detalhadas sobre como enviar e exibir mensagens criptografadas, confira estes artigos.

|Leia este artigo...|Se você estiver...|
|:-----|:-----|
|[Saiba mais sobre mensagens protegidas no Office 365](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|Um usuário final que deseja saber mais sobre como as mensagens criptografadas funcionam e quais opções estão disponíveis para você.|
|[Como abrir uma mensagem protegida?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|Um usuário final que deseja ler uma mensagem protegida que foi enviada para você. Este artigo inclui informações sobre a leitura de mensagens em várias versões do Outlook e de contas de email diferentes, incluindo contas fora do Microsoft 365, como gmail e Yahoo! contas.|
|[Enviar, exibir e responder a mensagens criptografadas no Outlook](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)|Um usuário final que deseja enviar, exibir ou responder a uma mensagem criptografada do Outlook. Mesmo que você não seja membro de uma organização, ainda receberá notificações de mensagens criptografadas enviadas para você no Outlook. Use este artigo para obter instruções sobre como exibir e responder a mensagens criptografadas enviadas do Office 365.|
|[Enviar uma mensagem assinada digitalmente ou criptografada](https://support.microsoft.com/office/send-a-digitally-signed-or-encrypted-message-a18ecf7f-a7ac-4edd-b02e-687b05eff547)|Um usuário final que deseja enviar, exibir ou responder a mensagens criptografadas usando o Outlook para Mac. Este artigo também aborda o uso de métodos de criptografia diferentes do OME, como S/MIME.|
|[Exibir mensagens criptografadas em seu dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|Um usuário final que recebeu uma mensagem criptografada com a Criptografia de Mensagem do Office 365 em seu dispositivo Android, você pode usar o aplicativo visualizador OME gratuito para exibir a mensagem e enviar uma resposta criptografada. Este artigo explica como.|
|[Exibir mensagens criptografadas em seu iPhone ou iPad](https://support.microsoft.com/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)|Um usuário final que recebeu uma mensagem criptografada com a Criptografia de Mensagem do Office 365 no seu iPhone ou iPad, você pode usar o aplicativo visualizador OME gratuito para exibir a mensagem e enviar uma resposta criptografada. Este artigo explica como.|
||
