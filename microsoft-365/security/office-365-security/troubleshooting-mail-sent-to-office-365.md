---
title: Solução de problemas de email enviados para o Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
description: Este artigo fornece informações de solução de problemas para remetentes que estão enfrentando problemas ao tentar enviar emails para caixas de entrada no Office 365 e práticas recomendadas para envio de email em massa para clientes do Office 365.
ms.openlocfilehash: 72dd0360038e58c2501728d9032fef95f81d90c2
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604058"
---
# <a name="troubleshooting-mail-sent-to-office-365"></a>Solução de problemas de email enviados para o Office 365

Este artigo fornece informações de solução de problemas para remetentes que estão enfrentando problemas ao tentar enviar emails para caixas de entrada no Office 365 e práticas recomendadas para envio de email em massa para clientes do Office 365.

## <a name="troubleshooting-common-problems-with-mail-delivery-to-office-365"></a>Solucionando problemas comuns com a entrega de emails para o Office 365

Escolha um desses problemas normalmente encontrados.

- [Você está gerenciando sua reputação de envio de IP e de domínio?](#are-you-managing-your-ip-and-domains-sending-reputation)

- [Você está enviando emails de novos endereços IP?](#are-you-sending-email-from-new-ip-addresses)

- [Confirmar se o DNS está configurado corretamente](#confirm-that-your-dns-is-set-up-correctly)

- [Não se anuncie como um IP não roteável](#ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip)

- [Você recebeu uma notificação de falha na entrega (NDR) ao enviar emails para um usuário no Office 365](#you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365)

- [Meu email Redirecionado na pasta lixo eletrônico do destinatário no EOP](#my-email-landed-in-the-recipients-junk-folder-in-eop)

- [O tráfego do meu endereço IP é limitado por EOP](#traffic-from-my-ip-address-is-throttled-by-eop)

### <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>Você está gerenciando sua reputação de envio de IP e de domínio?

As tecnologias de filtragem do EOP são projetadas para fornecer proteções antispam para o Microsoft Office 365, bem como outros produtos da Microsoft, como o Exchange Server, o Microsoft Office Outlook e o Windows Live mail. Também aproveitamos o SPF, DKIM e DMARC; tecnologias de autenticação de email que ajudam a resolver o problema de falsificação e phishing, verificando se o domínio que envia o email está autorizado a fazer isso. A filtragem EOP é influenciada por vários fatores relacionados ao IP de envio, domínio, autenticação, precisão da lista, taxas de reclamação, conteúdo e muito mais. Desses, um dos principais fatores para a condução da reputação de um remetente e sua capacidade de entregar emails é a taxa de reclamação de lixo eletrônico.

### <a name="are-you-sending-email-from-new-ip-addresses"></a>Você está enviando emails de novos endereços IP?

Os endereços IP não usados anteriormente para enviar emails normalmente não têm nenhuma reputação criada em nossos sistemas. Como resultado, os emails de novos IPs têm maior probabilidade de sofrer problemas de entrega. Depois que o IP tiver criado uma reputação de não enviar spam, o EOP geralmente permitirá uma melhor experiência de entrega de email.

Os novos IPs que são adicionados para domínios autenticados em registros SPF existentes normalmente apresentam a vantagem adicional de herdar alguns dos domínios de envio do domínio. Se seu domínio tem uma boa reputação de envio, novos IPs podem ter um tempo de crescimento mais rápido. Um novo IP pode esperar ser totalmente enescalado dentro de algumas semanas ou antes, dependendo do volume, da precisão da lista e das taxas de reclamação de emails de lixo eletrônico.

### <a name="confirm-that-your-dns-is-set-up-correctly"></a>Confirmar se o DNS está configurado corretamente

Para obter instruções sobre como criar e manter registros DNS, incluindo o registro MX exigido para roteamento de email, você precisará entrar em contato com o provedor de hospedagem DNS.

### <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>Não se anuncie como um IP não roteável

Podemos não aceitar emails de remetentes que falham em uma pesquisa de DNS reverso. Em alguns casos, os remetentes legítimos se anunciam incorretamente como um IP que não é roteável pela Internet ao tentar abrir uma conexão com o EOP. Os endereços IP reservados para redes privadas (não roteáveis) incluem:

- 192.168.0.0/16 (ou 192.168.0.0-192.168.255.255)

- 10.0.0.0/8 (ou 10.0.0.0-10.255.255.255)

- 172.16.0.0/11 (ou 172.16.0.0-172.31.255.255)

### <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>Você recebeu uma notificação de falha na entrega (NDR) ao enviar emails para um usuário no Office 365

Alguns problemas de entrega são o resultado do endereço IP do remetente sendo bloqueado pela Microsoft ou porque a conta do usuário é identificada como remetente proibido devido à atividade de spam anterior. Se você achar que recebeu a notificação por erro, primeiro siga as instruções na mensagem de notificação de falha na entrega para resolver o problema.

Para obter mais informações sobre o erro recebido, consulte a lista de códigos de erro em notificações de falha na [entrega de email no Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

 Por exemplo, se você receber a seguinte notificação de falha na entrega, ela indicará que o endereço IP de envio foi bloqueado pela Microsoft.

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

Para solicitar a remoção dessa lista, você pode [usar o portal de deslista para se remover da lista de remetentes bloqueados do Office 365](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

### <a name="my-email-landed-in-the-recipients-junk-folder-in-eop"></a>Meu email Redirecionado na pasta lixo eletrônico do destinatário no EOP

Se uma mensagem foi identificada incorretamente como spam pelo EOP, você poderá trabalhar com o destinatário para enviar essa mensagem falsa positiva para a equipe de análise de spam da Microsoft, que avaliará e analisará a mensagem. Dependendo dos resultados da análise, as regras de filtro de conteúdo de spam de todo o serviço podem ser ajustadas para permitir a mensagem. Você usa email para enviar mensagens para a Microsoft que não devem ser classificadas como spam. Ao fazer isso, certifique-se de usar as etapas do seguinte procedimento.

### <a name="to-use-email-to-submit-false-positive-messages-to-the-microsoft-spam-analysis-team"></a>Para usar o email para enviar mensagens de falso positivo para a equipe de análise de spam da Microsoft

1. Salve a mensagem que você deseja enviar como não spam.

2. Crie uma nova mensagem em branco e anexe a ela a mensagem que não é spam.

    Você pode anexar várias mensagens que não são spam, se necessário.

3. Copie e cole a linha de assunto da mensagem original na linha de assunto da nova mensagem.

    > [!IMPORTANT]
    > Deixe o corpo da nova mensagem vazio.

4. Envie a mensagem para [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).

### <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>O tráfego do meu endereço IP é limitado por EOP

Se você receber uma notificação de falha na EOP que indica que seu endereço IP está sendo limitado por EOP, por exemplo:

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

Você recebeu a notificação de falha na entrega porque a atividade suspeita foi detectada no endereço IP e foi temporariamente restringida enquanto está sendo avaliada. Se a suspeita for limpa através da avaliação, essa restrição será levantada em breve.

### <a name="i-cant-receive-email-from-senders-in-office-365"></a>Não consigo receber emails de remetentes no Office 365

 Para receber mensagens de nossos usuários, certifique-se de que a sua rede permite conexões dos endereços IP que o EOP usa em nossos data centers. Confira mais informações em [endereços IP do Exchange Online Protection](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

## <a name="best-practices-for-bulk-emailing-to-office-365-users"></a>Práticas recomendadas para envio de email em massa para usuários do Office 365

Se você costuma conduzir campanhas de email em massa para os usuários do Office 365 e quiser garantir que seus emails cheguem de forma segura e oportuna, siga as dicas desta seção.

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>Verifique se o nome de: reflete quem está enviando a mensagem

O assunto deve ser um breve resumo do que a mensagem está sobre, e o corpo da mensagem deve indicar claramente e sucintamente o que a oferta, serviço ou produto está. Por exemplo:

Correto:

> De: marketing@shoppershandbag.com <br/> Assunto: Catálogo atualizado para a temporada de Natal!

Incorreto:

> De: someone@outlook.com <br/> Assunto: Catálogos

Quanto mais fácil você fizer isso para que as pessoas saibam quem é e o que você está fazendo, menos dificuldade você terá de fornecer pela maioria dos filtros de spam.

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>Sempre incluir uma opção de cancelamento de assinatura em emails de campanha

Os emails de marketing, especialmente boletins informativos, devem sempre incluir uma forma de inscrever-se em emails futuros. Por exemplo:

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe™ | Privacy Policy`

Alguns remetentes incluem essa opção exigindo que os destinatários enviem um email para um determinado alias com "unsubscribe" no assunto. Isso não é preferível ao exemplo de um clique acima. Se você optar por exigir que os destinatários enviem um email, certifique-se de que ao clicar no link, todos os campos obrigatórios sejam preenchidos previamente.

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>Use a opção de consentimento duplo para o email de marketing ou o registro de boletim informativo

Essa prática recomendada do setor é recomendada se sua empresa requer ou incentiva os usuários a registrar suas informações de contato para acessar seu produto ou serviço. Algumas empresas fazem dele uma prática inscrever automaticamente seus usuários para emails de marketing ou boletins eletrônicos durante o processo de registro, mas isso é considerado uma prática de marketing questionável no mundo da filtragem de email.

Durante o processo de registro, se a caixa de seleção "Sim, envie-me seu boletim informativo" ou "Sim, enviar ofertas especiais" estiver selecionada por padrão, os usuários que não pagarão mais atenção podem inadvertidamente involuntariamente inscrever-se no email de marketing ou boletins informativos de que não deseja receber.

 Recomendamos a opção de consentimento duplo em vez disso, o que significa que a caixa de seleção para os emails de marketing ou boletins informativos está desmarcada por padrão. Além disso, após o formulário de registro ter sido enviado, um email de verificação é enviado para o usuário com uma URL que permite confirmar sua decisão de receber emails de marketing.

 Isso ajuda a garantir que apenas os usuários que desejam receber emails de marketing estão inscritos para os emails, subseqüentemente limpando a empresa de envio de qualquer prática de marketing de email questionável.

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>Garantir que o conteúdo da mensagem de email seja transparente e rastreável

Tão importante quanto a forma como os emails são enviados é o conteúdo que eles contêm. Ao criar conteúdo de email, use as práticas recomendadas a seguir para garantir que seus emails não sejam sinalizados por serviços de filtragem de email:

- Quando a mensagem de email solicita que os destinatários adicionem o remetente ao catálogo de endereços, deve indicar claramente que essa ação não é uma garantia de entrega.

- Redirecionamentos incluídos no corpo da mensagem devem ser semelhantes e consistentes, e não múltiplos e variados. Um redirecionamento neste contexto é qualquer coisa que aponte para longe da mensagem, como links e documentos. Se você tiver muitos links de propaganda ou cancelamento de assinatura ou atualizar os links de perfil, todos eles apontarão para o mesmo domínio. Por exemplo:

  Correto:

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  Incorreto:

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- Evite conteúdo com imagens e anexos grandes ou mensagens que são exclusivamente compostas por uma imagem.

- Suas configurações de privacidade pública ou P3P devem indicar claramente a presença de pixels de rastreamento (Web bugs ou beacons).

### <a name="remove-incorrect-email-aliases-from-your-databases"></a>Remover aliases de email incorretos dos bancos de dados

Qualquer alias de email em seu banco de dados que cria um repercussão é desnecessário e coloca seus emails de saída em risco para mais investigações por serviços de filtragem de email. Verifique se o banco de dados de email está atualizado.
