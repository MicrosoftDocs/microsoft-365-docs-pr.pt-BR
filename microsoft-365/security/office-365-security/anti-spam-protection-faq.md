---
title: Perguntas frequentes sobre a proteção antispam
ms.author: krowley
author: kccross
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
description: Este tópico fornece as perguntas frequentes e respectivas respostas sobre a proteção contra spam. As respostas são aplicáveis aos clientes do Microsoft Exchange Online e do Proteção do Exchange Online (EOP).
ms.openlocfilehash: 7e84aa35d3269e4b22fd8ea868b55249b422f268
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38034182"
---
# <a name="anti-spam-protection-faq"></a>Perguntas frequentes sobre a proteção antispam

Este tópico fornece as perguntas frequentes e respectivas respostas sobre a proteção contra spam. As respostas são aplicáveis aos clientes do Microsoft Exchange Online e do Proteção do Exchange Online (EOP). 
  
> [!TIP]
> Para perguntas e respostas sobre remetente seguro e listas de remetentes bloqueados, confira [listas de remetentes seguros e remetentes bloqueados no Exchange Online](safe-sender-and-blocked-sender-lists-faq.md). Para obter perguntas e respostas sobre a quarentena, veja [Perguntas Frequentes sobre a Quarentena](quarantine-faq.md). 
  
 **P. Por padrão, o que acontece com uma mensagem de spam detectada?**
  
R. **Para mensagens de entrada:** A maioria dos spams é excluída por meio da filtragem de conexão, que se baseia no endereço IP do remetente. O serviço então inspeciona o conteúdo da mensagem. Por padrão, o spam de conteúdo filtrado é enviado para a pasta Lixo Eletrônico do destinatário. Você pode alterar essa ação. Por exemplo, você pode optar por enviar mensagens de spam para a quarentena em vez de configurar a política de filtro de conteúdo. 
  
> [!IMPORTANT]
> Para clientes autônomos do EOP: para garantir que a ação **mover mensagem para a pasta lixo eletrônico** funcione com caixas de correio locais, você deve configurar duas regras de fluxo de mensagens do Exchange (também conhecidas como regras de transporte) em seus servidores locais para detectar cabeçalhos de spam adicionados pelo EOP. Para obter detalhes, consulte [Garantir que o spam seja direcionado para a pasta Lixo Eletrônico de cada usuário](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
 **Para mensagens de saída:** A mensagem foi roteada através do pool de entrega de risco mais alto ou foi devolvida sem ser entregue; em cujo caso o remetente receberá uma mensagem de notificação de status de entrega (DSN) informando que a mensagem não pôde ser entregue. 
  
 **P. o que é uma variante de spam de dia zero e como ela é manipulada pelo serviço?**
  
R. Uma variante de spam de dia zero é uma última geração, uma variante anteriormente desconhecida de spam que nunca foi capturada ou analisada, portanto, nossos filtros de conteúdo de spam ainda não têm informações disponíveis para detectá-lo. Após uma amostra de spam de zero dias ser capturada e analisada por nossos analistas de spam, se ela atender aos critérios de classificação de spam, nossos filtros de conteúdo de spam são atualizados para detectar e não são mais considerados "de dia zero". ( **Observação:** se você receber uma mensagem que pode ser uma variante de spam de dia zero, para nos ajudar a melhorar o serviço, envie a mensagem para a Microsoft usando um dos métodos descritos em [enviar mensagens de spam, não spam e golpes de phishing para a Microsoft para análise](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).)
  
 **P. Eu preciso configurar o serviço para fornecer proteção contra spam?**
  
R. Depois de se inscrever no serviço e adicionar o seu domínio, a filtragem de spam é automaticamente habilitada em toda a empresa por meio das políticas padrão contra spam. As políticas padrão são ajustadas para protegê-lo sem a necessidade de configuração adicional (salvo a exceção mencionada acima para os clientes autônomos do EOP). Como administrador, você pode editar as políticas padrão contra spam para que sejam adaptadas para atender às necessidades da sua organização da melhor maneira possível. Para obter uma granularidade melhor, você também pode criar políticas de filtragem de conteúdo personalizadas e aplicá-las a usuários, grupos ou domínios específicos na sua organização. Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.
  
Para obter mais informações sobre como configurar suas políticas contra spam, consulte os seguintes tópicos:
  
[Configurar a política do filtro de conexão](configure-the-connection-filter-policy.md)
  
[Configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md)
  
[Configuração da política de spam de saída](configure-the-outbound-spam-policy.md)
  
 **P. Se eu fizer uma alteração em uma política contra spam, quanto tempo demora para que as alterações façam efeito após eu salvá-las?**
  
R. Pode levar até 1 hora para que as alterações entrem em efeito.
  
 **P. A filtragem de email em massa é habilitada automaticamente?**
  
R. Por padrão, a opção de filtragem avançada de spam de **email em massa** está habilitada para novos clientes. Para os clientes migrados, esta configuração corresponderá com sua configuração FOPE. Para saber mais sobre emails em massa, veja [Qual é a diferença entre lixo eletrônico e email em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md)
  
 **P. O serviço oferece filtragem de URL?**
  
R. Sim, o serviço possui um filtro de URL que verifica se há URLs nas mensagens. Se forem detectadas URLs associadas a spam ou conteúdo malicioso conhecido, a mensagem será marcada como spam.
  
 **P. Como os clientes que utilizam o serviço podem enviar falsos negativos (spam) e falsos positivos (não spam) para a Microsoft?**
  
R. Mensagens de spam e não spam podem ser enviadas para a Microsoft para análise de várias maneiras. Para obter mais informações, consulte [enviar mensagens de spam, não spam e golpes de phishing para a Microsoft para análise](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). 
  
 **P. Posso obter relatórios de spam?**
  
R. Sim, por exemplo, você pode obter um relatório de detecção de spam no centro de administração do Microsoft 365. Este relatório mostra o volume de spam como uma contagem de mensagens exclusivas. Para obter mais informações sobre relatórios, consulte os seguintes links:
  
Clientes do Exchange Online: [monitoramento, relatórios e rastreamento de mensagens no Exchange Online](https://technet.microsoft.com/library/87bdeeae-bd80-4a3b-95c5-62fbaf97c2e8.aspx)
  
Clientes do Exchange Online Protection: [relatórios e rastreamento de mensagens no Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)
  
 **P. Alguém me enviou uma mensagem e eu não consigo encontrá-la. Desconfio que ela foi detectada como spam. Existe uma ferramenta que posso usar para descobrir?**
  
R. Sim, a ferramenta de rastreamento de mensagens permite que você siga as mensagens de email à medida que elas passam pelo serviço, a fim de descobrir o que aconteceu com elas. Para obter mais informações sobre como usar a ferramenta de rastreamento de mensagem para descobrir por que uma mensagem foi marcada como spam, confira [a mensagem foi marcada como spam?](https://technet.microsoft.com/library/aa49e3f9-a5b1-4410-aac2-ddbbf3f5bfb2.aspx#BKMB_Whywasamessagemarkedasspam)
  
 **Q. O serviço limitará (limite de taxa) meu email se os meus usuários enviarem spam de saída?**
  
R. Se mais de metade das mensagens enviadas de um usuário por meio do serviço dentro de um determinado período (por exemplo, por hora), for considerada como spam pelo Office 365, o usuário será impedido de enviar mensagens. Na maioria dos casos, se uma mensagem de saída é determinada como spam, ela é roteada através do pool de entrega de alto risco, que reduz a probabilidade de o pool de IP de saída normal ser adicionado a uma lista de bloqueios.
  
Você pode enviar uma notificação para um endereço de email especificado quando um remetente for impedido de enviar spam de saída. Para obter mais informações sobre essa configuração, consulte [Configure the Outbound Spam Policy](configure-the-outbound-spam-policy.md).
  
 **P. Posso usar um provedor de antispam e antimalware de terceiros em conjunto com o Exchange Online?**
  
R. Sim, você pode configurar outro serviço de filtragem de spam e malwares para proteger suas caixas de correio do Exchange Online. Para fazer isso para emails de entrada, você deve redirecionar suas mensagens para o provedor de terceiros, alterando os registros MX para que apontem para o provedor de terceiros e, em seguida, redirecione as mensagens para o EOP para processamento adicional. Para fazer isso para emails de saída, configure o destino de entrega de mensagem para o provedor de terceiros (host inteligente), conforme mostrado em [Scenario: Outbound Smart Hosting](https://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx).
  
 **P. A Microsoft possui alguma documentação sobre como eu posso me proteger contra golpes de phishing?**
  
P. Sim. Veja estes artigos:
  
[Obtenha ajuda contra golpes de phishing, fraude da loteria e outros tipos de golpes](https://go.microsoft.com/fwlink/p/?LinkId=325606)
  
[Golpes de web e email: Como ajudar você a se proteger](https://go.microsoft.com/fwlink/p/?LinkID=325607)
  
 **P. As mensagens de spam e malware são investigadas para identificar quem as enviou ou são transferidas para entidades legais?**
  
R. O objetivo do serviço é detectar e remover spam e malware, embora possamos, de vez em quando, investigar campanhas de spam ou de ataque particularmente perigosas ou prejudiciais, e processar legalmente os responsáveis. Isso pode envolver o trabalho conjunto com unidades legais de combate ao crime digital, para derrubar a botnet de um remetente de spam, impedir que o remetente de spam utilize o serviço (caso esteja usando o serviço para enviar emails) e passar informações à polícia para fins de processo criminal.
  
 **P. O que é um conjunto de práticas recomendadas de email de saída que garante que o meu email seja entregue?**
  
R. As diretrizes apresentadas abaixo são as práticas recomendas para o envio de mensagens de email de saída.
  
1. **O domínio de envio do email deve resolver em DNS.**
    
    Por exemplo, se o remetente for usuário@exemplo.com, o domínio exemplo.com resolve no endereço IP 192.0.43.10. Se um domínio de envio não tiver nenhum registro A e nenhum registro MX no DNS, o serviço encaminhará a mensagem por seu pool de entrega de risco mais alto, independentemente de o conteúdo da mensagem ser spam ou não. Para obter mais informações sobre o pool de entrega de risco mais alto, consulte [pool de entrega de alto risco para mensagens de saída](high-risk-delivery-pool-for-outbound-messages.md). 
    
2. **O endereço IP de envio do servidor de email de saída deve ter uma entrada de DNS reverso (PTR).**
    
    Por exemplo, se o envio for do endereço IP 192.0.43.10, a entrada de DNS reverso deste IP é 43-10.any.icann.org. 
    
3. **Os comandos HELO/EHLO e MAIL FROM devem ser consistentes e estar presentes na forma de um nome de domínio em vez de um endereço IP.**
    
    O comando HELO/EHLO deve ser configurado para corresponder com o DNS reverso do endereço IP de envio para que o domínio continue o mesmo nas diversas partes dos cabeçalhos de mensagem.
    
4. **Certifique-se de que os registros SPF adequados estejam configurados no DNS.**
    
    Os registros SPF são um mecanismo para a validação de que os emails enviados de um domínio realmente vêm desse domínio e de que os emails não são falsificados. Para obter mais informações sobre registros SPF, consulte os seguintes links:
    
    [Configurar o SPF no Office 365 para ajudar a evitar falsificações](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
    
    [Criar registros DNS do Office 365](https://go.microsoft.com/fwlink/?LinkID=275414)
    
5. **Assinatura de email com DKIM, assinar com canonização relaxada.**
    
    Se um remetente deseja assinar suas mensagens usando o Email Identificado por Chaves de Domínio (DKIM) e desejam enviar mensagens de saída pelo serviço, eles devem assinar usando o algoritmo de canonização de cabeçalho relaxada. Assinar com canonização de cabeçalho estrita pode invalidar a assinatura quando ela passar pelo serviço.
    
6. **Os proprietários do domínio devem ter informações precisas no banco de dados WHOIS.**
    
    Isso identifica os proprietários do domínio e como contatá-los inserindo a empresa pai estável, ponto de contato e servidores de nome.
    
7. **Para remetentes de mala direta, o nome De: deve refletir quem está enviando a mensagem e a linha de assunto da mensagem deve ser um resumo breve do assunto da mensagem.**
    
    O corpo da mensagem deve ter uma indicação clara da oferta, serviço ou produto. Por exemplo, se um remetente estiver enviando uma mala direta para a empresa Contoso, veja a seguir como deverão ficar os campos De e Assunto:
    
    De: marketing@contoso.com
    
    Assunto: Novo catálogo atualizado para a temporada de Natal! 
    
    Veja a seguir é um exemplo do que não fazer, porque isso não é descritivo:
    
    De: usuário@hotmail.com
    
    Assunto: Catálogos
    
8. **Se for enviar uma mala direta para vários destinatários e a mensagem estiver em formato de boletim informativo, deve haver uma maneira de cancelar a assinatura na parte inferior da mensagem.**
    
    A opção de cancelamento da assinatura deve ter a seguinte aparência:
    
    Esta mensagem foi enviada para exemplo@contoso.com por remetente@fabrikam.com. Atualizar Perfil/Endereço de Email | Remoção Instantânea com **SafeUnsubscribe** | Política de privacidade
    
9. **Se for enviar uma mala direta, a aquisição da lista deve ser realizada utilizando double opt-in. Se você for remetente de mala direta, o double opt-in é uma prática recomendada da indústria.**
    
    O Double opt-in é a prática que exige que um usuário passe por dois processos para confirmar o recebimento de correio de marketing:
    
1. No primeiro processo, o usuário clica em uma caixa de seleção desmarcada anteriormente, onde ele opta por receber mais ofertas ou mensagens de email do comerciante.
    
2. No segundo processo, o comerciante envia um email de confirmação para o endereço de email do usuário, pedindo que ele clique em um link com limite de tempo para concluir a confirmação.
    
    Usar o double opt-in ajuda a formar uma boa reputação para os remetentes de mala direta.
    
10. **Os remetentes de mala direta devem criar conteúdo transparente pelo qual possam ser responsabilizados:**
    
1. A verbosidade solicitando que os destinatários adicionem o remetente ao catálogo de endereços deve indicar claramente que tal ação não é uma garantia de entrega.
    
2. Ao construir redirecionamentos no corpo da mensagem, use um estilo de vínculo consistente.
    
3. Não envie imagens nem anexos grandes, nem mensagens compostas por apenas uma imagem.
    
4. Ao empregar pixels de rastreamento (bugs da Web ou avisos), indique claramente a presença deles em sua privacidade pública ou configurações P3P.
    
11. **Formatar notificações de status de entrega de saída.**
    
    Ao gerar as mensagens de notificação de status de entrega, os remetentes devem seguir o formato de uma mensagem de devolução, conforme especificado em [RFC 3464](https://go.microsoft.com/fwlink/?LinkId=279715).
    
12. **Remover endereços de email de devolução para usuários inexistentes.**
    
    Se você receber uma NDR indicando que um endereço de email não está mais em uso, remova da sua lista o alias de email inexistente. Os endereços de email mudam ao longo do tempo e as pessoas às vezes os descartam.
    
13. **Use o programa de Serviços de Dados de Rede Inteligente do Hotmail (SNDS) .**
    
    O Hotmail usa um programa chamado Serviços de Dados de Rede Inteligente do Hotmail que permite que os remetentes verifiquem as reclamações enviadas pelos usuários finais. O SNDS é o portal principal para a solução de problemas de entrega ao Hotmail.
    
## <a name="for-more-information"></a>Para obter mais informações

[Proteção anti-spam de emails do Office 365](https://support.office.com/article/6a601501-a6a8-4559-b2e7-56b59c96a586)
  
[Remetente seguro e listas de remetentes bloqueados no Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)
  
[Cabeçalhos de mensagem antispam](anti-spam-message-headers.md)
  
[Mnsagens backscatter e EOP](backscatter-messages-and-eop.md)
  

