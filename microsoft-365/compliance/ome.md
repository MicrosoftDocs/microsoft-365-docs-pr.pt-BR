---
title: Criptografia de Mensagens
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
ms.openlocfilehash: 504fa9918636cd596cde0d242083ccb7b9817e69
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927709"
---
# <a name="message-encryption"></a>Criptografia de Mensagens

As pessoas geralmente usam email para trocar informações importantes, como dados financeiros, contratos, informações confidenciais de produtos, relatórios e projeções de vendas, informações sobre a saúde de pacientes ou informações sobre clientes e empregados. Portanto, as caixas de correio podem se tornar repositórios de grandes quantidades de informações potencialmente confidenciais, e o vazamento de informações pode se tornar uma séria ameaça à sua organização.

Com a Criptografia de Mensagens do Office 365, sua organização pode enviar e receber mensagens de email criptografadas entre pessoas dentro e fora da sua organização. A Criptografia de Mensagens do Office 365 funciona com Outlook.com, Yahoo!, Gmail e outros serviços de email. A criptografia de mensagem de email ajuda a garantir que somente os destinatários pretendido possam exibir o conteúdo da mensagem.

## <a name="how-office-365-message-encryption-works"></a>Como funciona a Criptografia de Mensagens do Office 365

O restante deste artigo se aplica aos novos recursos OME.

A Criptografia de Mensagens do Office 365 é um serviço online criado com base no Microsoft Azure Rights Management (Azure RMS), que faz parte da Proteção de Informações do Azure. Esse serviço inclui políticas de criptografia, identidade e autorização para ajudar a proteger seu email. Você pode criptografar mensagens usando modelos de gerenciamento de direitos, a [opção Não](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)Encaminhar e a opção [somente criptografar](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

Os usuários podem criptografar mensagens de email e vários anexos usando essas opções. Para uma lista completa de tipos de anexos com suporte, consulte "Tipos de arquivo cobertos por políticas de IRM quando estão anexados a [mensagens" em Introdução](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)ao IRM para mensagens de email .

Como administrador, você também pode definir regras de fluxo de emails para aplicar essa proteção. Por exemplo, você pode criar uma regra que exija a criptografia de todas as mensagens endereçadas a um destinatário específico ou que contenha palavras específicas na linha de assunto e também especifique que os destinatários não podem copiar ou imprimir o conteúdo da mensagem.

Ao contrário da versão anterior do OME, os novos recursos fornecem uma experiência unificada de remetentes, seja para enviar emails dentro da sua organização ou para destinatários fora do Microsoft 365. Além disso, os destinatários que recebem uma mensagem de email protegida enviada para uma conta do Microsoft 365 no Outlook 2016 ou no Outlook na Web, não têm que tomar nenhuma outra ação para exibir a mensagem. Ele funciona perfeitamente. Os destinatários que usam outros clientes de email e provedores de serviços de email também têm uma experiência aprimorada. Para obter informações, [consulte Learn about protected messages in Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) and [How do I open a protected message](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098).

Para uma lista detalhada das diferenças entre a versão anterior do OME e os novos recursos OME, consulte [Comparar versões do OME](ome-version-comparison.md).

Quando alguém envia uma mensagem de email que corresponde a uma regra de fluxo de email de criptografia, a mensagem é criptografada antes de ser enviada. Todos os usuários finais do Microsoft 365 que usam clientes do Outlook para ler emails recebem experiências de leitura nativas de primeira classe para emails criptografados e protegidos por direitos, mesmo que não esteja na mesma organização que o remetente. Os clientes do Outlook com suporte incluem a área de trabalho do Outlook, o Outlook Mac, o Outlook mobile no iOS e Android e o Outlook na Web (anteriormente conhecido como Outlook Web App).

Destinatários de mensagens criptografadas que recebem emails criptografados ou protegidos por direitos enviados para suas contas do Outlook.com, Gmail e Yahoo recebem um email de wrapper que os direciona para o Portal OME onde eles podem autenticar facilmente usando uma conta da Microsoft, Gmail ou credenciais do Yahoo.

Os usuários finais que leem emails criptografados ou protegidos por direitos em clientes que não o Outlook também usam o portal OME para exibir mensagens criptografadas e protegidas por direitos que recebem.

Se o remetente do email protegido estiver no GCC High e o destinatário estiver fora do GCC High, incluindo usuários comerciais, Outlook.com usuários e usuários de outros provedores de email, como o Gmail, o destinatário receberá um email de wrapper. O email do wrapper direciona o destinatário para o Portal OME onde o destinatário é capaz de ler e responder à mensagem. Caso contrário, se o remetente e o destinatário estão no ambiente GCC High, mesmo que não esteja na mesma organização, os destinatários que usam clientes do Outlook para ler emails recebem experiências nativas de leitura de primeira classe para emails criptografados e protegidos por direitos. Para obter mais informações sobre a experiência diferente no GCC High, consulte [Comparar versões do OME](ome-version-comparison.md).

Para obter mais informações sobre limites de tamanho para mensagens e anexos que você pode criptografar usando o OME, consulte [Limites do Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Como funciona a Criptografia Avançada de Mensagens do Office 365 em cima do OME

A Criptografia Avançada de Mensagens do Office 365 permite que você crie vários modelos de identidade visual para ajustar o controle sobre o email do destinatário e criar experiências personalizadas de identidade visual para dar suporte a uma estrutura organizacional diversificada.

A Criptografia Avançada de Mensagens no Microsoft 365 ajuda você a cumprir obrigações de conformidade que exigem um controle mais flexível sobre o acesso do destinatário externo a emails criptografados. Com a Criptografia avançada de Mensagens no Office 365, como administrador, você pode controlar emails confidenciais compartilhados fora da organização com políticas automáticas que detectam tipos de informações confidenciais (por exemplo, PII, IDs financeiras ou de saúde) ou palavras-chave para aprimorar a proteção expirando o acesso por meio de um portal web seguro para emails criptografados. Como administrador, você pode controlar ainda mais os emails criptografados acessados por meio de um portal da Web do Microsoft 365 revogando o acesso a um email a qualquer momento.

A revogação e a expiração de mensagens só funcionam para emails que seus usuários enviam para destinatários fora da sua organização. Além disso, os destinatários devem acessar o email por meio do portal da Web. Para garantir que o destinatário use o portal para receber emails, você configura um modelo de identidade visual personalizado que aplica o wrapper. Em seguida, você aplica o modelo de identidade visual em uma regra de fluxo de emails. Para obter mais informações sobre Criptografia Avançada de Mensagens, consulte Criptografia de Mensagem Avançada do [Office 365](ome-advanced-message-encryption.md).

## <a name="defining-rules-for-office-365-message-encryption"></a>Definir regras para a Criptografia de Mensagens do Office 365

Uma maneira de habilitar os novos recursos para a Criptografia de Mensagens do Office 365 é para administradores do Exchange Online e do Exchange Online Protection definirem regras de fluxo de emails. Essas regras determinam em que condições as mensagens de email devem ser criptografadas. Quando uma ação de criptografia é definida para uma regra, todas as mensagens que corresponderem às condições de regra são criptografadas antes de ser enviadas.

As regras de fluxo de emails são flexíveis, o que permite combinar condições para que você possa atender a requisitos de segurança específicos em uma única regra. Por exemplo, você pode criar uma regra para criptografar todas as mensagens que contenham palavras-chave específicas e que sejam endereçadas a destinatários externos. Os novos recursos para a Criptografia de Mensagens do Office 365 também criptografam respostas de destinatários de email criptografado.

Para obter mais informações sobre como criar regras de fluxo de emails para aproveitar os novos recursos OME, consulte [Define Rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md).

## <a name="get-started-with-the-new-ome-capabilities"></a>Começar com os novos recursos OME

Se você estiver pronto para começar a usar os novos recursos OME em sua organização, consulte Configurar novos recursos de Criptografia de Mensagens do [Office 365.](set-up-new-message-encryption-capabilities.md)

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>Enviar, visualizar e responder mensagens de email criptografadas

Com a Criptografia de Mensagens do Office 365, os usuários podem enviar emails criptografados do Outlook e do Outlook na Web. Além disso, os administradores podem configurar regras de fluxo de emails no Microsoft 365 para criptografar automaticamente emails com base na correspondência de palavras-chave ou em outras condições.

Os destinatários de mensagens criptografadas que estão em organizações poderão ler essas mensagens perfeitamente em qualquer versão do Outlook, incluindo Outlook para PC, Outlook para Mac, Outlook na Web, Outlook para iOS e Outlook para Android. Os usuários que recebem mensagens criptografadas em outros clientes de email podem exibir as mensagens no portal OME.

Para obter orientações detalhadas sobre como enviar e exibir mensagens criptografadas, confira estes artigos.

|Leia este artigo...|Se você estiver...|
|:-----|:-----|
|[Saiba mais sobre mensagens protegidas no Office 365](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|Um usuário final que deseja saber mais sobre como funcionam as mensagens criptografadas e quais opções estão disponíveis para você.|
|[Como abrir uma mensagem protegida?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|Um usuário final que deseja ler uma mensagem protegida que foi enviada para você. Este artigo inclui informações sobre a leitura de mensagens em várias versões do Outlook e de contas de email diferentes, incluindo as contas fora do Microsoft 365, como gmail e Yahoo! contas.|
|[Enviar, exibir e responder a mensagens criptografadas no Outlook](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)|Um usuário final que deseja enviar, exibir ou responder a uma mensagem criptografada do Outlook. Mesmo que você não seja membro de uma organização, ainda receberá uma notificação de mensagens criptografadas enviadas para você no Outlook. Use este artigo para obter instruções sobre como exibir e responder a mensagens criptografadas enviadas do Office 365.|
|[Enviar uma mensagem assinada digitalmente ou criptografada](https://support.microsoft.com/office/send-a-digitally-signed-or-encrypted-message-a18ecf7f-a7ac-4edd-b02e-687b05eff547)|Um usuário final que deseja enviar, exibir ou responder a mensagens criptografadas usando o Outlook para Mac. Este artigo também aborda o uso de métodos de criptografia diferentes do OME, como S/MIME.|
|[Exibir mensagens criptografadas em seu dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|Um usuário final que recebeu uma mensagem criptografada com a Criptografia de Mensagens do Office 365 em seu dispositivo Android, você pode usar o aplicativo visualizador OME gratuito para exibir a mensagem e enviar uma resposta criptografada. Este artigo explica como.|
|[Exibir mensagens criptografadas em seu iPhone ou iPad](https://support.microsoft.com/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)|Um usuário final que recebeu uma mensagem criptografada com a Criptografia de Mensagem do Office 365 em seu iPhone ou iPad, você pode usar o aplicativo visualizador OME gratuito para exibir a mensagem e enviar uma resposta criptografada. Este artigo explica como.|
||