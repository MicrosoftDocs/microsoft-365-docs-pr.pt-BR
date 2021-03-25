---
title: A página da entidade de email do Microsoft Defender para Office 365 (MDO)
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os clientes do Microsoft Defender para Office 365 E5 e ATP P1 e ATP P2 agora podem obter uma exibição de 360 graus de cada email com a página da entidade de email.
ms.openlocfilehash: 0fbf3843aa6e6cef1e748d3b71a68a42efd6fc24
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51202980"
---
# <a name="the-email-entity-page"></a>A página de entidade de email

**Neste artigo:**
- [Alcançar a página da entidade de email](#reach-the-email-entity-page)
- [Ler a página da entidade de email](#read-the-email-entity-page)
- [Usar guias de página de entidade de email](#use-email-entity-page-tabs)
- [Novo na página entidade de email](#new-to-the-email-entity-page)

Os administradores do Microsoft Defender para Office 365 (ou MDO) E5 e MDO P1 e P2 têm uma exibição de 360 graus de email usando a página entidade **Email.** Essa página de email de ida e volta foi criada para aprimorar as informações entregues no [submenu "detalhes de email" do Explorador](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views)de Ameaças.

## <a name="reach-the-email-entity-page"></a>Alcançar a página da entidade de email

Um dos centro de Conformidade e Segurança do Office existente (protection.office.com) ou o novo Centro de Segurança do Microsoft 365 (security.microsoft.com) permitirão que você veja e use a página entidade de email..

|Centro  |URL  |Navegação  |
|---------|---------|---------|
|Conformidade e Segurança |protection.office.com | Gerenciamento de > Explorer   |
|Centro de segurança do Microsoft 365 |security.microsoft.com | Email & Colaboração > Explorer |

No Explorador de Ameaças, selecione o assunto de um email que você está investigando. Uma barra de ouro será exibida na parte superior do sub-envio de email para esse email. Este convite para a nova página, lê 'Experimente nossa nova página de entidade de email com dados enriquecidos...'. Selecione para exibir a nova página.

:::image type="content" source="../../media/email-entities-1-navigation-to-ee.png" alt-text="Você verá uma faixa dourada com as palavras *Experimente nossa nova página de entidade de email com dados enriquecidos* para navegar até a nova experiência.":::

:::image type="content" source="../../media/email-entities-2-eep.png" alt-text="Este gráfico da página da entidade de email se concentra nos títulos que você verá. Observe que o header de email é exibido aqui.":::

> [!NOTE]
> As permissões necessárias para exibir e usar essa página são as mesmas que exibir o Explorador de Ameaças. O administrador deve ser membro do administrador global ou leitor global, ou administrador de segurança ou leitor de segurança.

## <a name="read-the-email-entity-page"></a>Ler a página da entidade de email

A estrutura foi projetada para ser fácil de ler e navegar rapidamente. Várias guias ao longo da parte superior da página permitem que você investigue com mais detalhes. Veja como funciona o layout:

1. Os campos mais necessários estão no lado esquerdo do sub-piloto. Esses detalhes são "grudados", o que significa que eles são ancorados à esquerda, independentemente da guia para a qual você navega no restante do submenu.

    :::image type="content" source="../../media/email-entities-3-left-panel.png" alt-text="Gráfico da página da entidade de email com o lado esquerdo realçado. O título e os fatos sobre a entrega de email estão aqui.":::

2. No canto superior direito estão as ações que podem ser tomadas em um email. Todas as ações que podem ser realizadas por meio do Explorer também estarão disponíveis por meio da página entidade de email.

    :::image type="content" source="../../media/email-entities-5-preview.png" alt-text="Gráfico da página da entidade de email com o lado *right* realçado, desta vez. Ações como 'Visualização de email' e 'Ir para quarentena' estão aqui.":::

3. Uma análise mais profunda pode ser feita ao classificar o restante da página. Verifique os detalhes da detecção de email, o status de autenticação de email e o header. Essa área deve ser procurada caso a caso, mas as informações nessas guias estão disponíveis para qualquer email.

    :::image type="content" source="../../media/email-entities-4-middle-panel.png" alt-text="O painel principal desta página inclui o header de email e o status de autenticação.":::

### <a name="use-email-entity-page-tabs"></a>Usar guias de página de entidade de email

As guias ao longo da parte superior da página de entidade permitirão que você investigue emails com eficiência.

1. **Linha** do tempo : a exibição da linha do tempo de um email (de acordo com a linha do tempo do Explorador de Ameaças) mostra a entrega original para eventos pós-entrega que ocorrem em um email. Para emails que não têm ações pós-entrega, a exibição mostra a linha de entrega original no tempo de exibição. Eventos como: limpeza automática de hora zero (ZAP), correção, cliques de URL, et cetera, de fontes como: sistema, administrador e usuário, aparecem aqui, na ordem em que ocorreram.
2. **Análise**: A análise mostra campos que ajudam os administradores a analisar um email detalhadamente. Para os casos em que os administradores precisam entender mais sobre os detalhes de detecção, remetente/destinatário e autenticação de email, eles devem usar a guia Análise. Links para Anexos e URLs também são encontrados nesta página, em "Entidades Relacionadas". Os anexos e as ameaças identificadas são numerados aqui e clicar levará você diretamente para as páginas Anexos e URL. Essa guia também tem uma opção De exibição de header para *mostrar o header de email*. Os administradores podem comparar qualquer detalhe dos headers de email, lado a lado com informações no painel principal, para obter mais clareza.
3. **Anexos**: isso examina anexos encontrados no email com outros detalhes encontrados em anexos. O número de anexos mostrados atualmente está limitado a 10. Observe que detalhes de detonação para anexos considerados mal-intencionados também são mostrados aqui.
4. **URLs**: Esta guia lista URLs encontradas no email com outros detalhes sobre as URLs. O número de URLs está limitado a 10 no momento, mas essas 10 são priorizadas para mostrar *URLs mal-intencionadas primeiro.* A priorização economiza tempo e trabalho de suposição. As URLs que foram encontradas como mal-intencionadas e detonadas também serão mostradas aqui.
5. **Emails semelhantes**: esta guia lista todos os emails semelhantes à *id da* mensagem de rede + combinação de destinatários específica desse email. A semelhança é baseada apenas *no corpo da* mensagem. As determinações feitas em emails para categorizá-los como "semelhantes" não incluem uma consideração de *anexos*.

## <a name="new-to-the-email-entity-page"></a>Novo na página entidade de email

Há novos recursos que vêm com essa página de entidade de email. Aqui está a lista.

### <a name="email-preview-for-cloud-mailboxes"></a>Visualização de email para caixas de correio de nuvem
Os administradores podem visualizar emails em caixas de correio de nuvem, ***se*** os emails ainda estão presentes na Nuvem. No caso de uma exclusão suave (por um administrador ou usuário) ou ZAP (para quarentena), os emails não estão mais presentes no local da nuvem. Nesse caso, os administradores não poderão visualizar esses emails específicos. Emails que foram descartados ou onde a entrega falhou, nunca chegou realmente à caixa de correio. Como resultado, os administradores também não poderão visualizar esses emails.

> [!WARNING]
>A visualização de emails requer uma função especial chamada ***Preview** _ a ser atribuída aos administradores. Você pode adicionar essa função indo para _ *Permissões*& funções * > **Funções** de colaboração email & em *security.microsoft.com* ou **Permissões** em *protection.office.com*. Adicione a ***função Visualização*** a qualquer um dos grupos de função ou uma cópia de um grupo de funções que permite que os administradores em sua organização trabalhem no Explorador de Ameaças.

### <a name="detonation-details"></a>Detalhes da detonação

Esses detalhes são específicos para anexos de email e URLs.

Os usuários verão detalhes de detonação enriquecidos para anexos ou hiperlinks mal-intencionados conhecidos encontrados em suas caixas de correio, incluindo a cadeia de detonação, resumo de detonação, captura de tela e detalhes de comportamento observados para ajudar os clientes a entender por que o anexo ou URL foi considerado mal-intencionado e detonado.
 
- *Cadeia de detonação*: um único arquivo ou uma detonação de URL pode disparar várias detonações. A cadeia de detonação rastreia o caminho das detonações, incluindo o arquivo mal-intencionado original ou a URL que causou o veredito, e todos os outros arquivos ou URLs efetivados pela detonação. Essas URLs ou arquivos anexados podem não estar diretamente presentes no email, mas incluir essa análise é importante para determinar por que o arquivo ou URL foi considerado mal-intencionado.
- *Resumo da detonação*: isso fornece informações sobre:
    - Intervalo de tempo de detonação.
    - Veredito do arquivo anexado ou URL.
    - Informações relacionadas (número de arquivo, URLs, IPs ou Domínios), que são outras entidades examinadas durante a detonação.
- *Captura de tela de* detonação : isso mostra capturas de tela feitas durante o processo de detonação.
- *Detalhes da* detonação : Estes são os detalhes exatos do comportamento de cada processo que ocorreu durante a detonação.

:::image type="content" source="../../media/email-entities-6-detonation-page.png" alt-text="Captura de tela do resumo de detonação mostrando a cadeia, resumo, detalhes de detonação e captura de tela sob o título *Análise Profunda*.":::

### <a name="other-innovations"></a>Outras inovações

*Tags*: São marcas aplicadas aos usuários. Se o usuário for um destinatário, os administradores verão uma marca *de* destinatário. Da mesma forma, se o usuário for um remetente, uma marca *de* remetente. Isso aparecerá no lado esquerdo da página entidades de email (na parte descrita como *pegante* e, portanto, ancorada à página).

*Local de entrega mais* recente : o local de entrega mais recente é o local onde um email foi parar após ações do sistema, como ZAP, ou ações de administrador como Mover para Itens Excluídos, concluir. O local de entrega mais recente não se destina a informar os administradores sobre o local *atual da* mensagem. Por exemplo, se um usuário exclui uma mensagem ou a move para o arquivo morto, o local de entrega não será atualizado. No entanto, se uma ação do sistema tiver sido realizada e atualizado o local (como um ZAP resultando em um email mudando para Quarentena), isso atualizaria o local de entrega mais recente para Quarentena.

*Detalhes de* email : Detalhes necessários para uma compreensão mais profunda do email disponível *na* guia Análise.

- Regras de Transporte do *Exchange (ETRs* ou regras de fluxo de emails) : Essas regras são aplicadas a uma mensagem na camada de transporte e têm precedência sobre vereditos de phishing e spam. Eles só podem ser criados e modificados no Centro de administração do Exchange, mas se qualquer ETR se aplicar a uma mensagem, o nome ETR e o GUID serão mostrados aqui. Informações valiosas para fins de controle.
    
- *Substituições do* sistema : isso é um meio de fazer exceções ao local de entrega destinado a uma mensagem substituindo o local de entrega dado pelo sistema (de acordo com a tecnologia de detecção e ameaça).
    
- *Regra de Caixa de* Correio de Lixo Eletrônico : 'Lixo eletrônico' é a regra de Caixa de Entrada oculta habilitada por padrão em cada caixa de correio.
    - Quando a regra lixo eletrônico é habilitada na caixa de correio, a Proteção do Exchange Online (EOP) é capaz de mover mensagens para Lixo Eletrônico de acordo com alguns critérios. A movimentação pode ser baseada na ação de veredito de filtragem de spam *Mover* mensagem para a pasta Lixo Eletrônico ou na lista Remetentes Bloqueados na caixa de correio. Desabilitar a regra lixo eletrônico impede a entrega de mensagens para a pasta Lixo Eletrônico com base na lista *De envios seguros* na caixa de correio.
    - Quando a regra  de lixo eletrônico é desabilitada na caixa de correio, o EOP não pode mover mensagens para a pasta Lixo Eletrônico com base na ação de veredito de filtragem de spam *Mover* mensagem para a pasta Lixo Eletrônico ou a coleção de listas seguras na caixa de correio.
    
- *Nível de conformidade em massa (BCL)*: o nível de reclamação em massa (BCL) da mensagem. Uma BCL mais alta indica que uma mensagem de email em massa tem mais probabilidade de gerar reclamações (o resultado natural se o email provavelmente for spam).
    
- *Nível de Confiança de Spam (SCL)*: O nível de confiança de spam (SCL) da mensagem. Um valor mais alto indica que é mais provável que a mensagem seja spam.

- *Nome de* domínio : é o nome de domínio do remetente.
    
- *Proprietário do* Domínio : Especifica o proprietário do domínio de envio.
    
- *Local do* Domínio : Especifica o local do domínio de envio.
    
- *Data de criação do* domínio : especifica a data de criação do domínio de envio. Um domínio recém-criado é algo que você pode ter cuidado se outros sinais indicarem algum comportamento suspeito.

*Autenticação de Email*: Os métodos de autenticação de email usados pelo Microsoft 365 incluem SPF, DKIM e DMARC.

- Estrutura de Política de Remetente (**SPF**): descreve os resultados da verificação SPF da mensagem. Os valores possíveis podem ser:
    - Passagem (endereço IP): a verificação SPF da mensagem passada e inclui o endereço IP do remetente. O cliente está autorizado a enviar ou retransmitir emails em nome do domínio do remetente.
    - Fail (endereço IP): a verificação SPF da mensagem falhou e inclui o endereço IP do remetente. Isso também é conhecido como falha grave.
    - Softfail (motivo): o registro SPF designou o host como não sendo permitido enviar, mas está em transição.
    - Neutro: o registro SPF declara explicitamente que não afirma se o endereço IP está autorizado a enviar.
    - Nenhum: o domínio não tem um registro SPF ou o registro SPF não é avaliada como um resultado.
    - Temperror: ocorreu um erro temporário. Por exemplo, um erro de DNS. A mesma verificação mais tarde pode ter êxito.
    - Permerror: ocorreu um erro permanente. Por exemplo, o domínio tem um registro SPF mal formatado.

- DomainKeys Identified Mail (**DKIM**):
    - Passagem: indica a verificação DKIM da mensagem passada.
    - Falha (motivo): indica que a verificação DKIM da mensagem falhou e por quê. Por exemplo, se a mensagem não foi assinada ou se a assinatura não foi verificada.
    - Nenhum: Indica que a mensagem não foi assinada. Isso pode ou não indicar que o domínio tem um registro DKIM ou o registro DKIM não foi avaliado como um resultado, apenas que essa mensagem não foi assinada.

- Autenticação, relatórios e conformidade de mensagens baseadas em domínio (**DMARC**):
    - Passagem: indica a verificação DMARC da mensagem passada.
    - Falha: indica que a verificação DMARC da mensagem falhou.
    - Bestguesspass: Indica que não existe nenhum registro TXT DMARC para o domínio, mas se um tivesse existido, a verificação DMARC da mensagem teria passado.
    - Nenhuma: indica que não existe nenhum registro TXT DMARC para o domínio de envio no DNS.

*Autenticação* Composta : esse é um valor usado pelo Microsoft 365 para combinar autenticação de email como SPF, DKIM e DMARC, para determinar se a mensagem é autenticada. Ele usa o *domínio From:* do email como base de avaliação.
