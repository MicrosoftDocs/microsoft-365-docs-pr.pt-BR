---
title: A página de entidade de email do Microsoft Defender for Office 365 (MDO)
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: How-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os clientes do Microsoft Defender para Office 365 E5 e ATP P1 e ATP P2 agora podem obter uma exibição de 360 graus de cada email com a página de entidade de email.
ms.openlocfilehash: 3b9198c9d91969d3b57f379d17de33a1c00d37f6
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50143065"
---
# <a name="the-email-entity-page"></a>A página da entidade Email

**Neste artigo:**
- [Atingir a página de entidade de email](#reach-the-email-entity-page)
- [Ler a página de entidade de email](#read-the-email-entity-page)
- [Usar guias de página de entidade de email](#use-email-entity-page-tabs)
- [Novo na página de entidade de email](#new-to-the-email-entity-page)

Os administradores do Microsoft Defender para Office 365 (ou MDO) E5 e MDO P1 e P2 têm uma exibição de 360 graus de email usando a página entidade **Email.** Essa página de ir para email foi criada para aprimorar as informações entregues no [submenu "detalhes](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views)de email" do Explorador de Ameaças.

## <a name="reach-the-email-entity-page"></a>Atingir a página de entidade de email

Um dos centro de segurança e conformidade do Office (protection.office.com) ou o novo centro de segurança do Microsoft 365 (security.microsoft.com) permitirão que você veja e use a página de entidade de email.

|Centro  |URL  |Navegação  |
|---------|---------|---------|
|Conformidade e Segurança |protection.office.com | Explorador de gerenciamento > ameaças   |
|Central de segurança do Microsoft 365 |security.microsoft.com | Email & Collaboration > Explorer |

No Explorador de Ameaças, selecione o assunto de um email que você está investigando. Uma barra de ouro será exibida na parte superior do sub-envio de email para esse email. Esse convite para a nova página diz "Experimente nossa nova página de entidade de email com dados enriquecidos...". Selecione para exibir a nova página.

:::image type="content" source="../../media/email-entities-1-navigation-to-ee.png" alt-text="Você verá uma faixa gold com as palavras *Experimente nossa nova página de entidade de email com dados enriquecidos* para navegar para a nova experiência.":::

:::image type="content" source="../../media/email-entities-2-eep.png" alt-text="Este gráfico da página de entidade de email se concentra nos títulos que você verá. Observe que o header de email é exibido aqui.":::

> [!NOTE]
> As permissões necessárias para exibir e usar essa página são as mesmas que as do Explorador de Ameaças. O administrador deve ser um membro do administrador global ou leitor global, ou administrador de segurança ou leitor de segurança.

## <a name="read-the-email-entity-page"></a>Ler a página de entidade de email

A estrutura foi projetada para ser fácil de ler e navegar rapidamente. Várias guias na parte superior da página permitem que você investigue com mais detalhes. Veja como funciona o layout:

1. Os campos mais necessários estão no lado esquerdo do sub-out. Esses detalhes são "autoaderados", o que significa que eles são ancorados à esquerda, independentemente da guia para a qual você navega no restante do submenu.

    :::image type="content" source="../../media/email-entities-3-left-panel.png" alt-text="Gráfico da página da entidade de email com o lado esquerdo realçado. O título e os fatos sobre a entrega de email estão aqui.":::

2. No canto superior direito estão as ações que podem ser realizadas em um email. Todas as ações que podem ser realizadas por meio do Explorer também estarão disponíveis por meio da página de entidade de email.

    :::image type="content" source="../../media/email-entities-5-preview.png" alt-text="Gráfico da página de entidade de email com o lado *right* realçado, desta vez. Ações como &quot;Visualização de email&quot; e &quot;Ir para a quarentena&quot; estão aqui.":::

3. Uma análise mais profunda pode ser feita pela classificação pelo restante da página. Verifique os detalhes da detecção de email, o status de autenticação de email e o header. Essa área deve ser procurada caso a caso, mas as informações nessas guias estão disponíveis para qualquer email.

    :::image type="content" source="../../media/email-entities-4-middle-panel.png" alt-text="O painel principal desta página inclui o status de autenticação e de um header de email.":::

### <a name="use-email-entity-page-tabs"></a>Usar guias de página de entidade de email

As guias na parte superior da página de entidade permitirão que você investigue emails com eficiência.

1. **Linha do** tempo: a exibição da linha do tempo para um email (de acordo com a linha do tempo do Explorador de Ameaças) mostra a entrega original para eventos pós-entrega que ocorrem em um email. Para emails que não têm ações pós-entrega, a exibição mostra a linha de entrega original na exibição de linha do tempo. Eventos como: Zap (limpeza automática zero hora), Correção, cliques de URL, etc. de fontes como: sistema, administrador e usuário, aparecem aqui, na ordem em que ocorreram.
2. **Análise:** a análise mostra campos que ajudam os administradores a analisar um email em detalhes. Nos casos em que os administradores precisam entender mais sobre detecção, remetente/destinatário e detalhes de autenticação de email, eles devem usar a guia Análise. Links para Anexos e URLs também são encontrados nesta página, em 'Entidades Relacionadas'. Os anexos e as ameaças identificadas são numerados aqui, e clicar levará você diretamente para as páginas de Anexos e URL. Essa guia também tem uma opção de header View *para mostrar o header de email.* Os administradores podem comparar qualquer detalhe dos headers de email, lado a lado com as informações no painel principal, para maior clareza.
3. **Anexos**: examina anexos encontrados no email com outros detalhes encontrados em anexos. O número de anexos mostrado atualmente está limitado a 10. Observe que detalhes de detonação de anexos considerados mal-intencionados também são mostrados aqui.
4. **URLs**: esta guia lista as URLs encontradas no email com outros detalhes sobre as URLs. O número de URLs está limitado a 10 no momento, mas essas 10 são priorizadas para mostrar *URLs mal-intencionadas primeiro.* A priorização economiza tempo e trabalho de suposição. As URLs que foram encontradas como mal-intencionadas e acionada também serão mostradas aqui.
5. **Emails semelhantes:** essa guia lista todos os emails semelhantes à *ID* da mensagem de rede + combinação de destinatários específica para esse email. A semelhança é baseada no *corpo da mensagem,* somente. As determinações feitas em emails para categorizá-los como "semelhantes" não incluem uma consideração *de anexos.*

## <a name="new-to-the-email-entity-page"></a>Novo na página de entidade de email

Há novos recursos que vêm com essa página de entidade de email. Esta é a lista.

### <a name="email-preview-for-cloud-mailboxes"></a>Visualização de email para caixas de correio na nuvem
Os administradores podem visualizar emails em caixas de correio na nuvem, ***se*** os emails ainda estão presentes na nuvem. No caso de uma exclusão temporária (por um administrador ou usuário) ou zap (para quarentena), os emails não estão mais presentes no local da nuvem. Nesse caso, os administradores não poderão visualizar esses emails específicos. Emails que foram descartados ou onde a entrega falhou, nunca entraram realmente na caixa de correio. Como resultado, os administradores também não poderão visualizar esses emails.

> [!WARNING]
>A visualização de emails requer uma função especial chamada ***Visualização** _ a ser atribuída aos administradores. You can add this role by going to _ *Permissions & roles** > **Email & collaboration roles** in *security.microsoft.com*, or **Permissions** in *protection.office.com*. Adicione a ***função De*** visualização a qualquer um dos grupos de função ou uma cópia de um grupo de função que permite que os administradores em sua organização trabalhem no Explorador de Ameaças.

### <a name="detonation-details"></a>Detalhes de detonação

Esses detalhes são específicos para anexos de email e URLs.

Os usuários verão detalhes enriquecidos de detonação de anexos ou hiperlinks mal-intencionados conhecidos encontrados em suas caixas de correio, incluindo a cadeia de detonação, resumo de detonação, captura de tela e detalhes do comportamento observado para ajudar os clientes a entender por que o anexo ou a URL foi considerado mal-intencionado e destruído.
 
- *Cadeia de* acionamento: um único arquivo oucionamento de URL pode disparar várias detonações. A cadeia de detonação rastreia o caminho das detonações, incluindo o arquivo ou URL mal-intencionado original que causou o veredito, e todos os outros arquivos ou URLs que foram causados pelo detonação. Essas URLs ou arquivos anexados podem não estar presentes diretamente no email, mas incluir essa análise é importante para determinar por que o arquivo ou a URL foi considerado mal-intencionado.
- *Resumo de detonação:* fornece informações sobre:
    - Intervalo de tempo de detonação.
    - Veredito do arquivo anexado ou URL.
    - Informações relacionadas (número de arquivo, URLs, IPs ou Domínios), que são outras entidades examinadas durante o a detonação.
- *Captura de tela de* detonação: mostra capturas de tela feitas durante o processo de detonação.
- *Detalhes de* detonação: estes são os detalhes de comportamento exatos de cada processo que ocorreu durante o a detonação.

:::image type="content" source="../../media/email-entities-6-detonation-page.png" alt-text="Captura de tela do resumo de detonação mostrando a cadeia, o resumo, os detalhes de detonação e a captura de tela sob o título *Análise Profunda*.":::

### <a name="other-innovations"></a>Outras inovações

*Marcas:* são marcas aplicadas aos usuários. Se o usuário for um destinatário, os administradores verão uma marca *de* destinatário. Da mesma forma, se o usuário for um remetente, uma marca *de* remetente. Isso aparecerá no lado esquerdo da página de entidades de email (na parte descrita como *fixa* e, portanto, ancorada à página).

*Local de entrega mais* recente: o local de entrega mais recente é o local onde um email foi enviado após ações do sistema, como ZAP, ou ações de administrador, como Mover para Itens Excluídos, terminar. O local de entrega mais recente não se destina a informar aos administradores sobre a localização *atual da* mensagem. Por exemplo, se um usuário exclui uma mensagem ou a move para o arquivo morto, o local de entrega não será atualizado. No entanto, se uma ação do sistema tiver sido realizada e atualizado o local (como uma ZAP que resulta em um email mudando para Quarentena), isso atualizará o local de entrega mais recente para a Quarentena.

*Detalhes do* email: detalhes necessários para uma compreensão mais profunda do email disponível *na* guia Análise.

- Regras de Transporte do *Exchange (ETRs* ou regras de fluxo de mensagens) : Essas regras são aplicadas a uma mensagem na camada de transporte e têm precedência sobre vereditos de phishing e spam. Eles só podem ser criados e modificados no Centro de administração do Exchange, mas se qualquer ETR se aplicar a uma mensagem, o nome ETR e o GUID serão mostrados aqui. Informações valiosas para fins de rastreamento.
    
- *Substituições do* sistema: isso é um meio de fazer exceções ao local de entrega destinado a uma mensagem, substituindo o local de entrega dado pelo sistema (de acordo com a tecnologia de detecção e ameaça).
    
- *Regra de Lixo Eletrônico*: a regra de Caixa de Entrada 'Lixo Eletrônico' está oculta habilitada por padrão em cada caixa de correio.
    - Quando a regra de Lixo eletrônico é habilitada na caixa de correio, o Exchange Online Protection (EOP) é capaz de mover mensagens para Lixo Eletrônico de acordo com alguns critérios. A movimentação pode ser baseada na ação de veredito de filtragem de spam Mover mensagem para a pasta Lixo Eletrônico ou na lista Remetentes Bloqueados na caixa de correio. Desabilitar a regra de Lixo eletrônico impede a entrega de mensagens para a pasta Lixo eletrônico com base na lista De *envios seguros* na caixa de correio.
    - Quando a regra  de lixo eletrônico é desabilitada na caixa de correio, o EOP não pode mover mensagens para a pasta Lixo Eletrônico com base na ação de veredito de filtragem de spam *Mover* mensagem para a pasta Lixo Eletrônico ou o conjunto de listas seguras na caixa de correio.
    
- *Nível de conformidade em massa (BCL)*: o nível de reclamação em massa (BCL) da mensagem. Uma BCL mais alta indica que uma mensagem de email em massa tem mais probabilidade de gerar reclamações (o resultado natural se o email provavelmente for spam).
    
- Nível de confiança de spam *(SCL)*: O nível de confiança de spam (SCL) da mensagem. Um valor mais alto indica que é mais provável que a mensagem seja spam.

- *Nome do* domínio: é o nome de domínio do remetente.
    
- *Proprietário do* domínio: especifica o proprietário do domínio de envio.
    
- *Local do* domínio: especifica o local do domínio de envio.
    
- *Data de Criação do* Domínio: Especifica a data de criação do domínio de envio. Um domínio recém-criado é algo que você pode ter cuidado se outros sinais indicarem algum comportamento suspeito.

*Autenticação de Email*: Os métodos de autenticação de email usados pelo Microsoft 365 incluem SPF, DKIM e DMARC.

- Sender Policy Framework **(SPF):** descreve os resultados da verificação de SPF para a mensagem. Os valores possíveis podem ser:
    - Passagem (endereço IP): a verificação do SPF para a mensagem foi aprovada e inclui o endereço IP do remetente. O cliente está autorizado a enviar ou retransmitir emails em nome do domínio do remetente.
    - Falha (endereço IP): a verificação do SPF para a mensagem falhou e inclui o endereço IP do remetente. Isso também é conhecido como falha grave.
    - Softfail (motivo): o registro SPF designou o host como não sendo permitido enviar, mas está em transição.
    - Neutro: o registro SPF declara explicitamente que não declara se o endereço IP está autorizado a enviar.
    - Nenhuma: o domínio não tem um registro SPF ou o registro SPF não é avaliada como um resultado.
    - Erro temporário: ocorreu um erro temporário. Por exemplo, um erro de DNS. A mesma verificação mais tarde pode ter êxito.
    - Permerror: ocorreu um erro permanente. Por exemplo, o domínio tem um registro SPF mal formatado.

- DomainKeys Identified Mail (**DKIM**):
    - Pass: Indica que a verificação de DKIM para a mensagem foi aprovada.
    - Falha (motivo): indica que a verificação do DKIM para a mensagem falhou e por quê. Por exemplo, se a mensagem não foi assinada ou se a assinatura não foi verificada.
    - Nenhuma: indica que a mensagem não foi assinada. Isso pode ou não indicar que o domínio tem um registro DKIM ou o registro DKIM não foi avaliado como um resultado, apenas que essa mensagem não foi assinada.

- Autenticação, relatórios e conformidade de mensagens baseadas em domínio (**DMARC**):
    - Pass: Indica que a verificação do DMARC para a mensagem foi aprovada.
    - Falha: indica que a verificação do DMARC para a mensagem falhou.
    - Bestguesspass: Indica que não existe nenhum registro TXT do DMARC para o domínio, mas se tivesse existido, a verificação do DMARC para a mensagem teria passado.
    - Nenhuma: indica que não existe nenhum registro TXT do DMARC para o domínio de envio no DNS.

*Autenticação* Composta : esse é um valor usado pelo Microsoft 365 para combinar autenticação de email como SPF, DKIM e DMARC, para determinar se a mensagem é autenticada. Ele usa o *domínio De:* do email como base de avaliação.
