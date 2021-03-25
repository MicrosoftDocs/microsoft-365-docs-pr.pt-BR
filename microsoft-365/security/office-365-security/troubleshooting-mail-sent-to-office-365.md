---
title: Solução de problemas de emails enviados para o Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Este artigo fornece informações de solução de problemas para problemas de envio de email para caixas de entrada no Microsoft 365 & práticas recomendadas para envio em massa para clientes do Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c3017b0e7d0c583c9038f695f9f47010ff92c18a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203127"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a>Solução de problemas de emails enviados para o Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)

Este artigo fornece informações de solução de problemas para os envios que estão enfrentando problemas ao tentar enviar emails para caixas de entrada no Microsoft 365 e práticas recomendadas para envio em massa para clientes.

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>Você está gerenciando a reputação de envio de IP e domínio?

As tecnologias de filtragem do EOP foram projetadas para fornecer proteção anti-spam para o Microsoft 365, bem como para outros produtos da Microsoft, como Exchange Server. Também aproveitamos SPF, DKIM e DMARC; tecnologias de autenticação de email que ajudam a resolver o problema de spoofing e phishing verificando se o domínio que está enviando o email está autorizado a fazer isso. A filtragem de EOP é influenciada por vários fatores relacionados ao envio de IP, domínio, autenticação, precisão de lista, taxas de reclamações, conteúdo e muito mais. Destes, um dos principais fatores para derrubar a reputação de um remetente e sua capacidade de entregar emails é a taxa de reclamações de lixo eletrônico.

## <a name="are-you-sending-email-from-new-ip-addresses"></a>Você está enviando emails de novos endereços IP?

Endereços IP não usados anteriormente para enviar emails normalmente não têm nenhuma reputação criada em nossos sistemas. Como resultado, os emails de novos IPs têm mais probabilidade de ter problemas de entrega. Depois que o IP tiver criado uma reputação de não enviar spam, o EOP normalmente permitirá uma melhor experiência de entrega de email.

Os novos IPs adicionados para domínios que são autenticados em registros SPF existentes normalmente têm o benefício adicionado de herdar parte da reputação de envio do domínio. Se seu domínio tiver uma boa reputação de envio, os novos IPs poderão ter um tempo de rampa mais rápido. Um novo IP pode esperar ser totalmente apurado dentro de algumas semanas ou mais cedo, dependendo do volume, da precisão da lista e das taxas de reclamação de lixo eletrônico.

## <a name="confirm-that-your-dns-is-set-up-correctly"></a>Confirme se seu DNS está definido corretamente

Para obter instruções sobre como criar e manter registros DNS, incluindo o registro MX necessário para roteamento de email, você precisará entrar em contato com seu provedor de hospedagem DNS.

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>Certifique-se de que você não se anuncia como um IP não-rouável

Podemos não aceitar emails de senders que falham em uma olhada dns reversa. Em alguns casos, os envios legítimos anunciam-se incorretamente como um IP não-in-locar na Internet ao tentar abrir uma conexão com o EOP. Os endereços IP reservados para redes privadas (não-routable) incluem:

- 192.168.0.0/16 (ou 192.168.0.0 - 192.168.255.255)
- 10.0.0.0/8 (ou 10.0.0.0 - 10.255.255.255)
- 172.16.0.0/11 (ou 172.16.0.0 - 172.31.255.255)

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>Você recebeu um relatório de não entrega (NDR) ao enviar emails para um usuário no Office 365

Alguns problemas de entrega são o resultado do endereço IP do remetente ser bloqueado pela Microsoft ou porque a conta de usuário é identificada como remetente proibido devido à atividade de spam anterior. Se você acredita que recebeu a NDR por erro, primeiro siga as instruções na mensagem NDR para resolver o problema.

Para obter mais informações sobre o erro recebido, consulte a lista de códigos de erro em Relatórios de email que não são de [entrega no Exchange Online](/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

 Por exemplo, se você receber a seguinte NDR, ele indicará que o endereço IP de envio foi bloqueado pela Microsoft:

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

Para solicitar a remoção dessa lista, você pode usar o portal de lista para remover a si mesmo da lista de [envios bloqueados.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a>Meu email foi parar na pasta Lixo Eletrônico do destinatário

Se uma mensagem foi identificada incorretamente como spam pelo EOP, você pode trabalhar com o destinatário para enviar essa mensagem falso positivo à Equipe de Análise de Spam da Microsoft, que avaliará e analisará a mensagem. Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>O tráfego do meu endereço IP é acelerada pelo EOP

Se você receber uma NDR do EOP que indica que seu endereço IP está sendo acelerada pelo EOP, por exemplo:

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

Você recebeu a NDR porque atividades suspeitas foram detectadas a partir do endereço IP e ela foi temporariamente restrita enquanto ela está sendo avaliada ainda mais. Se a suspeita for limpa por meio da avaliação, essa restrição será suspensa em breve.

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a>Não posso receber emails de envios no Microsoft 365

 Para receber mensagens de nossos usuários, certifique-se de que sua rede permita conexões dos endereços IP que o EOP usa em nossos datacenters. Para obter mais informações, consulte [Endereços IP da Proteção do Exchange Online](../../enterprise/urls-and-ip-address-ranges.md).

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a>Práticas recomendadas para envio em massa de emails para usuários do Microsoft 365

Se você geralmente conduz campanhas de email em massa para usuários do Microsoft 365 e deseja garantir que seus emails cheguem de forma segura e em tempo hábil, siga as dicas nesta seção.

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>Verifique se o nome De reflete quem está enviando a mensagem

O Assunto deve ser um breve resumo do que se trata a mensagem e o corpo da mensagem deve indicar de forma clara e sucinta sobre o que é a oferta, o serviço ou o produto. Por exemplo:

Correto:

> De: marketing@shoppershandbag.com <br> Assunto: Catálogo atualizado para a estação de Natal!

Incorreto:

> De: someone@outlook.com <br> Assunto: Catálogos

Quanto mais fácil você facilitar para as pessoas saberem quem você é e o que você está fazendo, menos dificuldade você terá para entregar através da maioria dos filtros de spam.

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>Sempre inclua uma opção de cancelamento de assinatura em emails de campanha

Emails de marketing, especialmente boletins informativos, sempre devem incluir uma maneira de cancelar a assinatura de emails futuros. Por exemplo:

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

Alguns destinatários incluem essa opção exigindo que os destinatários enviem um email para um determinado alias com "Cancelar assinatura" no assunto. Isso não é preferível ao exemplo de um clique acima. Se você optar por exigir que os destinatários enviem um email, certifique-se de que, quando clicarem no link, todos os campos necessários serão pré-preenchidos.

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>Use a opção de aceitação dupla para o registro de email de marketing ou boletim informativo

Essa prática recomendada do setor é recomendada se sua empresa exigir ou incentivar os usuários a registrar suas informações de contato para acessar seu produto ou serviços. Algumas empresas fazem com que seja prática inscrever automaticamente seus usuários para emails de marketing ou boletins informativos eletrônicos durante o processo de registro, mas isso é considerado uma prática de marketing questionável no mundo da filtragem de email.

Durante o processo de registro, se a caixa de seleção "Sim, envie-me seu boletim informativo" ou "Sim, envie-me ofertas especiais" por padrão, os usuários que não prestarem atenção poderão se inscrever inadimplentemente para emails de marketing ou boletins informativos que eles não querem receber.

 Em vez disso, recomendamos a opção de aceitação dupla, o que significa que a caixa de seleção para emails de marketing ou boletins informativos está desmarcada por padrão. Além disso, depois que o formulário de registro é enviado, um email de verificação é enviado ao usuário com uma URL que permite que ele confirme sua decisão de receber emails de marketing.

 Isso ajuda a garantir que apenas os usuários que querem receber emails de marketing sejam inscrevíveis para os emails, limpando subsequentemente a empresa de envio de quaisquer práticas questionáveis de marketing de email.

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>Verifique se o conteúdo da mensagem de email é transparente e rastreável

Tão importante quanto a maneira como os emails são enviados é o conteúdo que eles contêm. Ao criar conteúdo de email, use as seguintes práticas recomendadas para garantir que seus emails não sejam sinalizados pelos serviços de filtragem de email:

- Quando a mensagem de email solicita que os destinatários adicionem o remetente ao livro de endereços, ela deve dizer claramente que essa ação não é uma garantia de entrega.

- Os redirecionamentos incluídos no corpo da mensagem devem ser semelhantes e consistentes, e não múltiplos e variados. Um redirecionamento nesse contexto é qualquer coisa que aponta para longe da mensagem, como links e documentos. Se você tiver muitos links de anúncio ou cancelamento de assinatura ou atualizar os links de perfil, todos eles devem apontar para o mesmo domínio. Por exemplo:

  Correto (todos os domínios são os mesmos):

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  Incorreto (todos os domínios são diferentes):

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- Evite conteúdo com imagens e anexos grandes ou mensagens compostas exclusivamente por uma imagem.

- Suas configurações de privacidade pública ou P3P devem definir claramente a presença de pixels de controle (bugs da Web ou sinalizadores).

### <a name="remove-incorrect-email-aliases-from-your-databases"></a>Remover aliases de email incorretos de seus bancos de dados

Qualquer alias de email em seu banco de dados que crie um retorno é desnecessário e coloca seus emails de saída em risco para maior análise pelos serviços de filtragem de email. Verifique se o banco de dados de email está atualizado.