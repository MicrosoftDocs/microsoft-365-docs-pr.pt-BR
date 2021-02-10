---
title: Perguntas frequentes sobre a proteção antispam
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem exibir perguntas frequentes e respostas sobre a proteção anti-spam no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8620ad3f99c45dae3442ec89d879124053c1a005
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175974"
---
# <a name="anti-spam-protection-faq"></a>Perguntas frequentes sobre a proteção antispam

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Este tópico fornece perguntas frequentes e respostas sobre a proteção anti-malware para organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online.

Para obter perguntas e respostas sobre a quarentena, veja [Perguntas Frequentes sobre a Quarentena](quarantine-faq.md).

Para perguntas e respostas sobre a proteção anti-malware, consulte Perguntas frequentes sobre [a proteção anti-malware.](anti-malware-protection-faq-eop.md)

Para perguntas e respostas sobre a proteção anti-spoofing, consulte Perguntas frequentes sobre a proteção [anti-spoofing.](anti-spoofing-protection-faq.md)

## <a name="by-default-what-happens-to-a-spam-detected-message"></a>Por padrão, o que acontece com uma mensagem detectada por spam?

**Para mensagens de entrada:** A maioria dos spams é excluída por meio da filtragem de conexão, que se baseia no endereço IP do servidor de email de origem. As políticas anti-spam (também conhecidas como políticas de filtro de spam ou políticas de filtro de conteúdo) inspecionam e classificam mensagens como spam, em massa ou phishing. Por padrão, as mensagens classificadas como spam ou em massa são entregues na pasta Lixo Eletrônico do destinatário, enquanto as mensagens classificadas como phishing são colocadas em quarentena. Você pode modificar a política anti-spam padrão (aplicada a todos os destinatários) ou pode criar políticas anti-spam personalizadas com configurações mais estritas para grupos específicos de usuários (por exemplo, você pode colocar em quarentena o spam enviado aos executivos). Para obter mais informações, [consulte Configurar políticas anti-spam](configure-your-spam-filter-policies.md) e configurações de política [anti-spam recomendadas.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

> [!IMPORTANT]
> Em implantações híbridas em que o EOP protege caixas de correio locais, você precisa configurar duas regras de fluxo de emails do Exchange (também conhecidas como regras de transporte) em sua organização local do Exchange para detectar os headers de filtragem de spam do EOP que são adicionados às mensagens. Para obter detalhes, confira [Configurar a EOP autônoma para enviar spam à pasta Lixo Eletrônico em ambientes híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

 **Para mensagens de saída:** A mensagem é roteada pelo [pool](high-risk-delivery-pool-for-outbound-messages.md) de entrega de alto risco ou retorna ao remetente em um relatório de não entrega (também conhecido como NDR ou mensagem de rejeição). Para obter mais informações sobre a proteção contra spam de saída, consulte [Controles de spam de saída.](outbound-spam-controls.md)

## <a name="whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a>O que é uma variante de spam de dia zero e como ela é tratada pelo serviço?

Uma variante de spam de dia zero é uma variante de spam de primeira geração, anteriormente desconhecida, que nunca foi capturada ou analisada, portanto, nossos filtros anti-spam ainda não têm informações disponíveis para detectá-los. Depois que uma amostra de spam de dia zero for capturada e analisada por nossos analistas de spam, se atender aos critérios de classificação de spam, nossos filtros anti-spam serão atualizados para detectá-lo e não serão mais considerados "dia zero".

**Observação:** Se você receber uma mensagem que pode ser uma variante de spam de dia zero, para nos ajudar a melhorar o serviço, envie a mensagem para a Microsoft usando um dos métodos descritos em mensagens de relatório e arquivos para a [Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a>Preciso configurar o serviço para fornecer proteção anti-spam?

Depois de se inscrever no serviço e adicionar seu domínio, a filtragem de spam será habilitada automaticamente. Por padrão, a filtragem de spam é ajustada para protegê-lo sem precisar de nenhuma configuração adicional (além da exceção anteriormente notada para clientes autônomos do EOP em ambientes híbridos). Como administrador, você pode editar as configurações padrão de filtragem de spam para atender melhor às necessidades da sua organização. Para maior granularidade, você também pode criar políticas anti-spam e políticas anti-spam de saída que são aplicadas a usuários, grupos ou domínios específicos em sua organização. Diretrizes personalizadas sempre prevalecem sobre as diretrizes padrão, mas você pode alterar a prioridade (isto é, a ordem de execução) das suas diretrizes personalizadas.

Para mais informações, confira os seguintes tópicos:

[Configurações recomendadas para o EOP e o Microsoft Defender para segurança do Office 365](recommended-settings-for-eop-and-office365-atp.md)

[Configurar a filtragem de conexão no EOP](configure-the-connection-filter-policy.md)

[Configurar políticas antispam no EOP](configure-your-spam-filter-policies.md)

[Configuração da política de spam de saída](configure-the-outbound-spam-policy.md)

## <a name="if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a>Se eu fizer uma alteração em uma política anti-spam, quanto tempo demora depois que eu salvo minhas alterações para que elas entrem em vigor?

Pode levar até 1 hora para que as alterações entrem em efeito.

## <a name="is-bulk-email-filtering-automatically-enabled"></a>A filtragem de email em massa está habilitada automaticamente?

Sim. Para obter mais informações sobre email em massa, consulte [Qual é a diferença entre lixo eletrônico e email em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md).

## <a name="does-the-service-provide-url-filtering"></a>O serviço fornece filtragem de URL?

Sim, o serviço tem um filtro de URL que verifica se há URLs nas mensagens. Se forem detectadas URLs associadas a spam ou conteúdo malicioso conhecido, a mensagem será marcada como spam.

## <a name="how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a>Como os clientes que usam o serviço podem enviar mensagens de falso negativo (spam) e falso positivo (não spam) para a Microsoft?

Mensagens de spam e não spam podem ser enviadas à Microsoft para análise de várias maneiras. Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="can-i-get-spam-reports"></a>Posso obter relatórios de spam?

Sim, por exemplo, você pode obter um relatório de detecção de spam no Centro de administração do Microsoft 365. Este relatório mostra o volume de spam como uma contagem de mensagens exclusivas. Para obter mais informações sobre relatórios, consulte os seguintes links:

Clientes do Exchange Online: [monitoramento, relatórios e rastreamento de mensagens no Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)

Clientes autônomos do EOP: [Relatórios e rastreamento de mensagens no Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)

## <a name="someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a>Alguém me enviou uma mensagem e não consigo encontrá-la. Suspeito que ele possa ter sido detectado como spam. Há uma ferramenta que eu possa usar para descobrir?

Sim, a ferramenta de rastreamento de mensagens permite que você siga as mensagens de email à medida que elas passam pelo serviço, a fim de descobrir o que aconteceu com elas. Para obter mais informações sobre como usar a ferramenta de rastreamento de mensagens para descobrir por que uma mensagem foi marcada como spam, consulte Uma mensagem foi [marcada como spam?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)

## <a name="will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a>O serviço limitará (limite de taxa) meu email se meus usuários enviarem spam de saída?

Se mais da metade dos emails enviados de um usuário pelo serviço dentro de um determinado período de tempo (por exemplo, por hora) for determinado como spam pelo EOP, o usuário será impedido de enviar mensagens. Na maioria dos casos, se uma mensagem de saída for determinada como spam, ela será roteada através do pool de entrega de alto risco, o que reduz a probabilidade do pool de IP de saída normal ser adicionado a uma lista de bloqueios.

Você pode enviar uma notificação para um endereço de email especificado quando um remetente for impedido de enviar spam de saída. Para obter mais informações sobre essa configuração, [consulte Configurar a política de spam de saída.](configure-the-outbound-spam-policy.md)

## <a name="can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a>Posso usar um provedor antimalware e antispam de terceiros juntamente com o Exchange Online?

Sim. Embora recomendemos que você aponte seu registro MX para a Microsoft, sabemos que há razões comerciais legítimas para rotear seu email para outro lugar que não seja a Microsoft primeiro.

- **Entrada:** altere seus registros MX para apontar para o provedor de terceiros e redirecione as mensagens para o EOP para processamento adicional. Para obter mais informações, consulte [Filtragem aprimorada para conectores no Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- **Saída:** configure o roteamento de host inteligente do Microsoft 365 para o provedor de terceiros de destino.

## <a name="does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a>A Microsoft tem alguma documentação sobre como posso me proteger contra tentativas de phishing?

Sim. Para obter mais informações, [consulte Proteger sua privacidade na Internet](https://support.microsoft.com/help/4091455)

## <a name="are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a>As mensagens de spam e malware são investigadas para identificar quem as enviou ou são transferidas para entidades legais?

O objetivo do serviço é detectar e remover spam e malware, embora possamos, de vez em quando, investigar campanhas de spam ou de ataque particularmente perigosas ou prejudiciais, e processar legalmente os responsáveis. Isso pode envolver o trabalho conjunto com unidades legais de combate ao crime digital, para derrubar a botnet de um remetente de spam, impedir que o remetente de spam utilize o serviço (caso esteja usando o serviço para enviar emails) e passar informações à polícia para fins de processo criminal.

## <a name="what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a>Quais são as melhores práticas de email de saída que garantirão que meu email seja entregue?

As diretrizes apresentadas abaixo são as práticas recomendas para o envio de mensagens de email de saída.

- **O domínio de email de origem deve resolver no DNS.**

  Por exemplo, se o remetente for user@fabrikam, o domínio fabrikam será resolvido para o endereço IP 192.0.43.10.

  Se um domínio de envio não tiver nenhum registro A e nenhum registro MX no DNS, o serviço encaminhará a mensagem por seu pool de entrega de risco mais alto, independentemente de o conteúdo da mensagem ser spam ou não. Para obter mais informações sobre o pool de entrega de risco mais alto, consulte Pool de entrega de alto [risco para mensagens de saída.](high-risk-delivery-pool-for-outbound-messages.md)

- **O servidor de email de saída deve ter uma entrada de DNS reverso (PTR).**

  Por exemplo, se o endereço IP da fonte de email for 192.0.43.10, a entrada de DNS reverso `43-10.any.icann.org` será .'

- **Os comandos HELO/EHLO e MAIL FROM devem ser consistentes e estar presentes na forma de um nome de domínio em vez de um endereço IP.**

  O comando HELO/EHLO deve ser configurado para corresponder com o DNS reverso do endereço IP de envio para que o domínio continue o mesmo nas diversas partes dos cabeçalhos de mensagem.

- **Certifique-se de que os registros SPF adequados estejam configurados no DNS.**

  Os registros SPF são um mecanismo para a validação de que os emails enviados de um domínio realmente vêm desse domínio e de que os emails não são falsificados. Para obter mais informações sobre registros SPF, consulte os seguintes links:

  [Configurar o SPF para ajudar a prevenir falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [Perguntas frequentes sobre domínios](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

- **Assinatura de email com DKIM, assinar com canonização relaxada.**

  Se um remetente deseja assinar suas mensagens usando o Email Identificado por Chaves de Domínio (DKIM) e desejam enviar mensagens de saída pelo serviço, eles devem assinar usando o algoritmo de canonização de cabeçalho relaxada. Assinar com canonização de cabeçalho estrita pode invalidar a assinatura quando ela passar pelo serviço.

- **Os proprietários do domínio devem ter informações precisas no banco de dados WHOIS.**

  Isso identifica os proprietários do domínio e como contatá-los inserindo a empresa pai estável, ponto de contato e servidores de nome.

- **Para remetentes de mala direta, o nome De: deve refletir quem está enviando a mensagem e a linha de assunto da mensagem deve ser um resumo breve do assunto da mensagem.**

  O corpo da mensagem deve ter uma indicação clara da oferta, serviço ou produto. Por exemplo, se um remetente estiver enviando uma mala direta para a empresa Contoso, veja a seguir como deverão ficar os campos De e Assunto:

  > De: marketing@contoso.com <br> Assunto: Novo catálogo atualizado para a temporada de Natal!

  Veja a seguir é um exemplo do que não fazer, porque isso não é descritivo:

  > De: usuário@hotmail.com <br> Assunto: Catálogos

- **Se for enviar uma mala direta para vários destinatários e a mensagem estiver em formato de boletim informativo, deve haver uma maneira de cancelar a assinatura na parte inferior da mensagem.**

  A opção de cancelamento da assinatura deve ter a seguinte aparência:

  > Esta mensagem foi enviada para exemplo@contoso.com por remetente@fabrikam.com. Atualizar perfil/endereço de email | Remoção instantânea com **o |** &trade; Política de Privacidade

- **Se for enviar uma mala direta, a aquisição da lista deve ser realizada utilizando double opt-in. Se você for remetente de mala direta, o double opt-in é uma prática recomendada da indústria.**

  O Double opt-in é a prática que exige que um usuário passe por dois processos para confirmar o recebimento de correio de marketing:

  1. No primeiro processo, o usuário clica em uma caixa de seleção desmarcada anteriormente, onde ele opta por receber mais ofertas ou mensagens de email do comerciante.

  2. No segundo processo, o comerciante envia um email de confirmação para o endereço de email do usuário, pedindo que ele clique em um link com limite de tempo para concluir a confirmação.

  Usar o double opt-in ajuda a formar uma boa reputação para os remetentes de mala direta.

- **Os remetentes de mala direta devem criar conteúdo transparente pelo qual possam ser responsabilizados:**

  1. A verbosidade solicitando que os destinatários adicionem o remetente ao catálogo de endereços deve indicar claramente que tal ação não é uma garantia de entrega.

  2. Ao construir redirecionamentos no corpo da mensagem, use um estilo de vínculo consistente.

  3. Não envie imagens nem anexos grandes, nem mensagens compostas por apenas uma imagem.

  4. Ao empregar pixels de rastreamento (bugs da Web ou avisos), indique claramente a presença deles em sua privacidade pública ou configurações P3P.

- **Formatar mensagens de salto de saída.**

  Ao gerar mensagens de notificação de status de entrega (também conhecidas como notificações de não entrega, NDRs ou mensagens de rejeição), os envios devem seguir o formato de um salto conforme especificado na [RFC 3464.](https://www.ietf.org/rfc/rfc3464.txt)

- **Remover endereços de email de devolução para usuários inexistentes.**

  Se você receber uma NDR indicando que um endereço de email não está mais em uso, remova da sua lista o alias de email inexistente. Os endereços de email mudam ao longo do tempo e as pessoas às vezes os descartam.

- **Use o programa de Serviços de Dados de Rede Inteligente do Hotmail (SNDS) .**

  O Hotmail usa um programa chamado Serviços de Dados de Rede Inteligente do Hotmail que permite que os remetentes verifiquem as reclamações enviadas pelos usuários finais. O SNDS é o portal principal para a solução de problemas de entrega ao Hotmail.
