---
title: Criptografia de Mensagem do Office 365
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
description: Com a criptografia de mensagem do Office 365, sua organização pode enviar e receber mensagens de email criptografadas entre pessoas dentro e fora da sua organização. A criptografia de mensagens de email ajuda a garantir que somente os destinatários pretendidos possam exibir o conteúdo da mensagem.
ms.openlocfilehash: ae0d8e831b872c898140612225de39a89f31ae6c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071088"
---
# <a name="office-365-message-encryption"></a>Criptografia de Mensagem do Office 365

As pessoas geralmente usam email para trocar informações importantes, como dados financeiros, contratos, informações confidenciais de produtos, relatórios e projeções de vendas, informações sobre a saúde de pacientes ou informações sobre clientes e empregados. Portanto, as caixas de correio podem se tornar repositórios de grandes quantidades de informações potencialmente confidenciais, e o vazamento de informações pode se tornar uma séria ameaça à sua organização.

Com a criptografia de mensagem do Office 365, sua organização pode enviar e receber mensagens de email criptografadas entre pessoas dentro e fora da sua organização. A criptografia de mensagem do Office 365 funciona com o Outlook.com, Yahoo!, Gmail e outros serviços de email. A criptografia de mensagens de email ajuda a garantir que somente os destinatários pretendidos possam exibir o conteúdo da mensagem.

## <a name="how-office-365-message-encryption-works"></a>Como funciona a criptografia de mensagens do Office 365

O restante deste artigo se aplica aos novos recursos do OME.

> [!NOTE]
> Representantes com permissões de acesso total a uma caixa de correio podem ler mensagens criptografadas que são enviadas para a caixa de correio.

A criptografia de mensagem do Office 365 é um serviço online desenvolvido no Microsoft Azure Rights Management (Azure RMS), que faz parte da proteção de informações do Azure. Isso inclui políticas de criptografia, identidade e autorização para ajudar a proteger seu email. Você pode criptografar mensagens usando modelos de gerenciamento de direitos, a [opção não encaminhar](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)e a [opção somente criptografia](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

Os usuários podem então criptografar mensagens de email e uma variedade de anexos do Office 365 usando essas opções. Para obter uma lista completa de tipos de anexo compatíveis, consulte ["tipos de arquivo cobertos por políticas de IRM quando estão anexados a mensagens" em Introdução ao IRM para mensagens de email](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM).

Como administrador, você também pode definir regras de fluxo de email para aplicar essa proteção. Por exemplo, você pode criar uma regra que exija a criptografia de todas as mensagens endereçadas a um destinatário específico ou que contenha palavras específicas na linha de assunto, além de especificar que os destinatários não possam copiar ou imprimir o conteúdo da mensagem.

Ao contrário da versão anterior do OME, os novos recursos oferecem uma experiência de remetente unificado se você estiver enviando emails dentro da sua organização ou para destinatários fora do Office 365. Além disso, os destinatários que recebem uma mensagem de email protegida enviadas para uma conta do Office 365 no Outlook 2016 ou no Outlook na Web não precisam realizar qualquer ação adicional para exibir a mensagem. Funciona perfeitamente. Os destinatários que usam outros clientes de email e provedores de serviço de email também têm uma experiência aprimorada. Para obter informações, consulte [saiba mais sobre mensagens protegidas no Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) e [como eu abro uma mensagem protegida](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098).

Para obter uma lista detalhada das diferenças entre a versão anterior do OME e os novos recursos do OME, consulte [comparar versões do ome](ome-version-comparison.md).

Quando alguém envia uma mensagem de email que corresponde a uma regra de fluxo de mensagens de criptografia, a mensagem é criptografada antes de ser enviada. Todos os usuários finais do Office 365 que usam os clientes do Outlook para ler email recebem experiências de leitura nativas de primeira classe para mensagens criptografadas e protegidas por direitos, mesmo que não estejam na mesma organização que o remetente. Os clientes do Outlook com suporte incluem a área de trabalho do Outlook, o Outlook Mac, o Outlook Mobile no iOS e o Android, e o Outlook na Web (anteriormente conhecido como Outlook Web App).

Os destinatários de mensagens criptografadas que recebem mensagens criptografadas ou protegidas por direitos enviados para suas contas do Outlook.com, do Gmail e do Yahoo recebem um email de wrapper que os direciona para o portal do OME onde podem autenticar facilmente usando uma conta da Microsoft, Gmail ou Credenciais do Yahoo.

Os usuários finais que lêem mensagens criptografadas ou protegidas por direitos em clientes diferentes do Outlook também usam o portal OME para exibir mensagens criptografadas e protegidas por direitos recebidas.

Se o remetente do email protegido estiver em GCC alto e o destinatário estiver fora da GCC alta, incluindo os usuários do Office 365, usuários do Outlook.com e usuários de outros provedores de email, como o Gmail, o destinatário receberá um email de conteúdo adicional. O email do invólucro direciona o destinatário para o portal do OME em que o destinatário é capaz de ler e responder à mensagem. Caso contrário, se o remetente e o destinatário estiverem no ambiente GCC High, mesmo que eles não estejam na mesma organização, os destinatários que usam os clientes do Outlook para ler emails recebem experiências de leitura nativas de primeira classe para emails criptografados e protegidos por direitos . Para obter mais informações sobre a experiência diferente em GCC High, consulte [Compare versions of ome](ome-version-comparison.md).

Para obter mais informações sobre os limites de tamanho de mensagens e anexos que você pode criptografar usando o OME, consulte [limites do Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx).

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Como a criptografia de mensagem avançada do Office 365 funciona na parte superior do OME

O Office 365 Advanced Message Encryption permite que você crie vários modelos de identidade visual para que possa ajustar o controle sobre o email de destinatário e criar experiências de identidade visual personalizada para dar suporte a uma estrutura organizacional diferente.

A criptografia de mensagem avançada no Office 365 ajuda a atender às obrigações de conformidade que exigem controle mais flexível sobre o acesso do destinatário externo a emails criptografados. Com a criptografia de mensagem avançada no Office 365, como administrador, você pode controlar emails confidenciais compartilhados fora da organização com políticas automáticas que detectam tipos de informações confidenciais (por exemplo, PII, finanças ou IDs de integridade) ou palavras-chave para melhorar proteção ao expirar o acesso por meio de um portal da Web seguro para emails criptografados. Além disso, como administrador, você pode controlar ainda mais emails criptografados acessados externamente por meio de um portal da Web do Office 365, revogando o acesso a um email a qualquer momento.

A revogação e a expiração de mensagens só funcionam para emails enviados por seus usuários para destinatários fora da organização do Office 365. Além disso, os destinatários devem acessar o email através do portal da Web. Para garantir que o destinatário use o portal para receber emails, você deve configurar um modelo personalizado de identidade visual que aplica o invólucro. Em seguida, você aplica o modelo de identidade visual em uma regra de fluxo de emails. Para obter mais informações sobre a criptografia avançada de mensagens, consulte [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md).

## <a name="defining-rules-for-office-365-message-encryption"></a>Definir regras para a Criptografia de Mensagens do Office 365

Uma maneira de habilitar os novos recursos para a criptografia de mensagem do Office 365 é para os administradores do Exchange Online e do Exchange Online Protection definir regras de fluxo de email. Essas regras determinam sob quais condições as mensagens de email devem ser criptografadas. Quando uma ação de criptografia é definida para uma regra, quaisquer mensagens que correspondam às condições de regra são criptografadas antes de serem enviadas.

As regras de fluxo de emails são flexíveis, permitindo que você combine condições para que possa atender a requisitos específicos de segurança em uma única regra. Por exemplo, você pode criar uma regra para criptografar todas as mensagens que contenham palavras-chave específicas e que sejam endereçadas a destinatários externos. Os novos recursos da criptografia de mensagem do Office 365 também criptografam respostas de destinatários de emails criptografados.

Para obter mais informações sobre como criar regras de fluxo de email para aproveitar os novos recursos do OME, consulte [definir regras para a criptografia de mensagem do Office 365](define-mail-flow-rules-to-encrypt-email.md).

## <a name="get-started-with-the-new-ome-capabilities"></a>Introdução aos novos recursos do OME

Se você estiver pronto para começar a usar os novos recursos do OME em sua organização, confira [configurar os novos recursos de criptografia de mensagens do Office 365](set-up-new-message-encryption-capabilities.md).

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>Enviar, visualizar e responder mensagens de email criptografadas

Com a criptografia de mensagem do Office 365, os usuários podem enviar emails criptografados do Outlook e do Outlook na Web. Além disso, os administradores podem configurar regras de fluxo de email no Office 365 para criptografar emails automaticamente com base na correspondência de palavras-chave ou outras condições.

Os destinatários de mensagens criptografadas que estão nas organizações do Office 365 poderão ler essas mensagens de forma transparente em qualquer versão do Outlook, incluindo o Outlook para PC, o Outlook para Mac, o Outlook na Web, o Outlook para iOS e o Outlook para Android. Os usuários que recebem mensagens criptografadas em outros clientes de email podem exibir as mensagens no portal do OME.

Para obter orientações detalhadas sobre como enviar e exibir mensagens criptografadas, consulte estes artigos:

|||
|:-----|:-----|
|Leia este artigo...|Se você for...|
|[Saiba mais sobre mensagens protegidas no Office 365](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|Um usuário final que deseja saber mais sobre como funcionam as mensagens criptografadas e quais opções estão disponíveis para você.|
|[Como abro uma mensagem protegida?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|Um usuário final que deseja ler uma mensagem protegida que foi enviada a você. Este artigo inclui informações sobre a leitura de mensagens em várias versões do Outlook e de diferentes contas de email, incluindo aquelas fora do Office 365, como Gmail e Yahoo! las.|
|[Enviar, exibir e responder a mensagens criptografadas no Outlook](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)|Um usuário final que deseja enviar, exibir ou responder a uma mensagem criptografada do Outlook. Mesmo que você não seja membro de uma organização do Office 365, ainda receberá uma notificação de mensagens criptografadas enviadas para você no Outlook. Use este artigo para obter instruções sobre como exibir e responder a mensagens criptografadas enviadas do Office 365.|
|[Enviar uma mensagem assinada digitalmente ou criptografada](https://support.office.com/article/a18ecf7f-a7ac-4edd-b02e-687b05eff547)|Um usuário final que deseja enviar, exibir ou responder a mensagens criptografadas usando o Outlook para Mac. Este artigo também cobre o uso de métodos de criptografia diferentes de OME, como S/MIME.|
|[Exibir mensagens criptografadas no seu dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|Um usuário final que recebeu uma mensagem criptografada com a criptografia de mensagem do Office 365 no seu dispositivo Android, você pode usar o aplicativo OME Viewer gratuito para exibir a mensagem e enviar uma resposta criptografada. Este artigo explica como.|
|[Exibir mensagens criptografadas no seu iPhone ou iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)|Um usuário final que recebeu uma mensagem criptografada com a criptografia de mensagem do Office 365 em seu iPhone ou iPad, você pode usar o aplicativo OME Viewer gratuito para exibir a mensagem e enviar uma resposta criptografada. Este artigo explica como.|
||
