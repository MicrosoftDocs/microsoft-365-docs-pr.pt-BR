---
title: Configurar políticas de filtro de spam
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender como criar, modificar e excluir políticas antispam no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2214baa1c205d4e0f634c5a07f4d55522d2ad6b1
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822016"
---
# <a name="configure-anti-spam-policies-in-eop"></a>Configurar políticas antispam no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou um cliente independente do Exchange Online Protection (EOP), ou organizações sem as caixas de correio do Exchange Online, as mensagens de e-mail de entrada serão automaticamente protegidas contra spam por EOP. A EOP usa políticas antispam (também conhecidas como políticas de filtro de spam ou políticas de filtro de conteúdo) como parte da defesa geral da sua organização contra spams. Para obter mais informações, consulte [Proteção antispam](anti-spam-protection.md).

Os administradores podem visualizar, editar e configurar (mas não excluir) a política antispam padrão. Para maior granularidade, também é possível criar políticas antispam personalizadas aplicadas a determinados usuários, grupos ou domínios na sua organização. Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.

Configure políticas antispam no Centro de segurança do Microsoft 365 ou no PowerShell (PowerShell do Exchange Online para organizações do Microsoft 365 com caixas de correio no Exchange Online; PowerShell autônomo da EOP para organizações sem caixas de correio no Exchange Online).

Os elementos básicos de uma política antispam são:

- **A política de filtro de spam**: especifica as ações de vereditos de filtragem de spam e as opções de notificação.
- **A regra de filtro de spam**: especifica a prioridade e os filtros de destinatário (a quem a política se aplica) para uma política de filtro de spam.

A diferença entre esses dois elementos não é óbvia ao gerenciar as políticas antispam no centro de segurança:

- Ao criar uma política antispam, na verdade, você está criando uma regra de filtro de spam e a política de filtro de spam associada ao mesmo tempo, usando o mesmo nome para ambas.
- Ao modificar uma política antispam, as configurações relacionadas a nome, prioridade, habilitado ou desabilitado, e filtros de destinatário modificam a regra do filtro de spam. Todas as demais configurações modificam a política de filtro de spam associada.
- Ao remover uma política antispam, a regra de filtro de spam e a política de filtro de spam associada são removidas.

No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a política e a regra são gerenciadas separadamente. Para obter mais informações, confira a seção [Usar o PowerShell do Exchange Online ou o PowerShell do EOP autônomo para configurar políticas antispam](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) mais adiante neste tópico.

Cada organização tem uma política antispam interna denominada Padrão com estas propriedades:

- A política é aplicada a todos os destinatários da organização, mesmo que não haja nenhuma regra de filtro de spam (filtros de destinatário) associada à política.
- A política tem o valor de prioridade personalizado **Menor**, que não pode ser modificado (a política é sempre aplicada por último). As políticas personalizadas que você cria, sempre têm uma prioridade mais alta.
- A política é a padrão (a propriedade **IsDefault** tem o valor `True`), e não é possível excluir a política padrão.

Para aumentar a eficácia da filtragem de spam, crie políticas antispam personalizadas com configurações mais estritas aplicadas a usuários específicos ou a grupos de usuários.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o centro de segurança em <https://security.microsoft.com>. Para ir diretamente à página de **Políticas antispam**, use <https://security.microsoft.com/antispam>.

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:
  - Para adicionar, modificar e excluir políticas antispam, você precisa ser membro dos grupos de funções **Gerenciamento da Organização** ou **Administrador de Segurança**.
  - Para acesso de somente leitura às políticas anti-spam, você precisa ser membro dos grupos de funções **Leitor Global** ou **Leitor de Segurança**.

  Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

- Para nossas configurações recomendadas para políticas antispam, confira [Configurações da política antispam EOP](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).

## <a name="use-the-security-center-to-create-anti-spam-policies"></a>Usar o centro de segurança para criar políticas antispam

Ao criar uma política antispam personalizada no centro de segurança é gerado, ao mesmo tempo, uma regra de filtro de spam e a política de filtro de spam associada com o mesmo nome para ambas.

1. No centro de segurança, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **seção** Políticas \> **Anti-spam**.

2. Na página **Políticas anti-spam**, clique em ![Criar ícone](../../media/m365-cc-sc-create-icon.png) **Criar política** e selecione **Entrada** na lista suspensa.

3. O assistente de política é aberto. Na **página Nomear política**, defina as seguintes configurações:
   - **Nome**: insira um nome exclusivo e descritivo para a política.
   - **Descrição**: insira uma descrição opcional para a política.

   Ao terminar, clique em **Avançar**.

4. Na página **Usuários, grupos e domínios** exibida, identifique os destinatários internos aos quais a política se aplica (condições do destinatário):
   - **Usuários**: as caixas de correio, os usuários de email, ou os contatos de email especificados na organização.
   - **Grupos**: os grupos de distribuição, os grupos de segurança habilitados para email ou os grupos do Microsoft 365 habilitados na organização.
   - **Domínios**: todos os destinatários nos [domínios aceitos](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados na organização.

   Clique na caixa apropriada, comece a digitar um valor e selecione o valor desejado dos resultados. Repita esse processo quantas vezes for necessário. Para remover uma entrada existente, clique em Remover ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) ao lado do valor.

   Para usuários ou grupos, você pode usar a maioria dos identificadores (nome, nome de exibição, alias, endereço de email, nome da conta etc.), mas o nome de exibição correspondente será mostrado nos resultados. Para os usuários, insira um asterisco (\*) por si só para ver todos os valores disponíveis.

   Vários valores na mesma condição ou exceção usam a lógica OR (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Diferentes condições usam a lógica AND (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

   - **Excluir estes usuários, grupos e domínios**: para adicionar exceções para os destinatários internos aos quais a política se aplica (exceções de destinatários), selecione essa opção e configure as exceções. As configurações e o comportamento são exatamente como as condições.

   Ao terminar, clique em **Avançar**.

5. Na página **Limite de emails em massa e propriedades de spam** exibida, configure as seguintes configurações:

   - **Limite de email em massa**: especifica o BCL (nível de reclamação em massa) de uma mensagem que dispara a ação especificada para o veredito de filtragem de spam **Em massa** configurado na próxima página (maior que o valor especificado, não é maior que ou igual a). Um valor mais alto indica que a mensagem é menos desejável (é mais provável que a mensagem pareça um spam). O valor padrão é 7. Para obter mais informações, confira [BCL (Nível de reclamação em massa) no EOP](bulk-complaint-level-values.md) e [Qual é a diferença entre lixo eletrônico e e-mail em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md).

     Por padrão, a única configuração _MarkAsSpamBulkMail_ do PowerShell é `On` nas políticas antispam. Essa configuração afeta significativamente os resultados de um veredito de filtragem de **Em massa**:

     - **_MarkAspamBulkMail_ está Ativado**: um BCL maior que o limite é convertido em um SCL 6 que corresponde a um veredito de filtragem de **Spam**, e a ação para o veredito de filtragem **Em massa** é executada na mensagem.
     - **_MarkAsSpamBulkMail_ está Desativado**: a mensagem tem o carimbo com o BCL, mas _nenhuma ação_ foi executada para o veredito de filtragem **Em massa**. De fato, o limite de BCL e a ação do veredito de filtragem **Em massa** são irrelevantes.

   - **Aumentar pontuação de spam**, **Marcar como spam**<sup>\*</sup> e **Modo de teste**: contém as configurações de ASF (Filtro de Spam Avançado) que estão desativadas por padrão. As configurações de ASF estão em processo de substituição, e a funcionalidade delas está sendo incorporada a outras partes da pilha de filtragem. Recomendamos deixar todas essas configurações de ASF desativadas em suas políticas antispam.

     Para obter mais detalhes sobre essas configurações, confira [Configurações de filtragem de spam avançadas no EOP](advanced-spam-filtering-asf-options.md).

      <sup>\*</sup> **Contém idiomas específicos** e **A partir destes países/regiões** não fazem parte das configurações de ASF.

   - **Contém idiomas específicos**: clique na caixa e selecione **Ativado** ou **Desativado** na lista suspensa. Se você a ativar, uma caixa será exibida. Comece a digitar o nome de um idioma na caixa. Uma lista filtrada de idiomas com suporte será exibida. Selecione o idioma que está procurando ao encontrá-lo. Repita essa etapa quantas vezes forem necessárias. Para remover um valor existente, clique em remover ![ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) ao lado do valor.

   - **A partir destes países/regiões** _: clique na caixa e selecione *Ativado** ou **Desativado** na lista suspensa. Se você a ativar, uma caixa será exibida. Comece digitando o nome de um país/região na caixa. Uma lista filtrada de países/regiões com suporte será exibida. Quando encontrar o país/região que está procurando, selecione-o. Repita essa etapa quantas vezes forem necessárias. Para remover um valor existente, clique em remover ![ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) ao lado do valor.

   Ao terminar, clique em **Avançar**.

6. Na página **Ações** exibida, de acordo com as seguintes configurações:

   - **Ações de mensagem**: selecione ou revise a ação a ser realizada nas mensagens com base nos seguintes vereditos de filtragem de spam:
     - **Spam**
     - **Spam de alta confiança**
     - **Phishing**
     - **Phishing de alta confiança**
     - **Em massa**

     As ações disponíveis para vereditos de filtragem de spam são descritas na tabela a seguir.

     - Uma marca de seleção ( ![Marca de seleção](../../media/checkmark.png)) indica que a ação está disponível (nem todas as ações estão disponíveis para todos os vereditos).
     - Um asterisco ( <sup>\*</sup> ) após a marca de seleção indica a ação padrão para o veredito de filtragem de spam.

     <br>

     ****

     |Ação|Spam|Alto<br>confiança<br>spam|Phishing|Alto<br>confiança<br>phishing|Em massa|
     |---|:---:|:---:|:---:|:---:|:---:|
     |**Mover mensagem para a pasta Lixo Eletrônico**: a mensagem é enviada para a caixa de correio e movida para a pasta Lixo Eletrônico.<sup>1</sup>|![Marca de seleção](../../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)<sup>\*</sup>|
     |**Adicionar cabeçalho X**: adiciona um cabeçalho X ao cabeçalho da mensagem e entrega a mensagem à caixa de correio. <p> Digite o nome do campo do cabeçalho X (não o valor) posteriormente na caixa **Adicionar o texto do cabeçalho X**. <p> Para vereditos de **Spam** e de **Spam de alta confiança**, a mensagem é movida para a pasta Lixo eletrônico.<sup>1,2</sup>|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)||![Marca de seleção](../../media/checkmark.png)<sup>\*</sup>|
     |**Preceder a linha de assunto com texto**: adiciona o texto ao início da linha de assunto da mensagem. A mensagem é enviada para a caixa de correio e movida para a pasta Lixo Eletrônico.<sup>1,2</sup> <p> Em seguida, insira o texto na caixa **Prefixar a linha de assunto com este texto**.|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)||![Marca de seleção](../../media/checkmark.png)|
     |**Redirecionar mensagem para endereço de email**: envia a mensagem para outros destinatários em vez de enviá-la aos destinatários pretendidos. <p> Especifique os destinatários posteriormente na caixa **Redirecionar para este endereço de email**.|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|
     |**Excluir mensagem**: exclui silenciosamente a mensagem inteira, incluindo todos os anexos.|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)||![Marca de seleção](../../media/checkmark.png)|
     |**Mensagem em quarentena**: envia a mensagem para a quarentena em vez de enviá-la aos destinatários pretendidos. <p> Especifique por quanto tempo a mensagem deve ser mantida na quarentena mais adiante na caixa **Quarentena**.|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|
     |**Nenhuma ação**|||||![Marca de seleção](../../media/checkmark.png)|
     |

     > <sup>1</sup> No Exchange Online, a mensagem será movida para a pasta Lixo Eletrônico se a regra de lixo eletrônico estiver habilitada na caixa de correio (ela é habilitada por padrão). Para obter mais informações, confira [Definir as configurações de lixo eletrônico nas caixas de correio do Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).
     >
     > Em ambientes híbridos onde o EOP protege as caixas de correio locais do Exchange, você precisa configurar regras de fluxo de email (também conhecidas como regras de transporte) no Exchange local para traduzir o veredito de filtragem de spam do EOP para que a regra de lixo eletrônico possa mover a mensagem para o Lixo Pasta de email. Para obter detalhes, confira [Configurar o EOP para enviar spam para a pasta Lixo Eletrônico em ambientes híbridos](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).
     >
     > <sup>2</sup>É possível usar esse valor como uma condição nas regras de fluxo de email para filtrar ou rotear a mensagem.

   - **Manter spam em quarentena por esse número de dias**: especifica por quanto tempo manter a mensagem em quarentena se você selecionar **Colocar mensagem em quarentena** como ação para um veredito de filtragem de spam. Após o período da quarentena, a mensagem será excluída. O valor padrão é de 30 dias. O valor válido é de 1 a 30 dias. Para obter informações sobre quarentena, confira os seguintes tópicos:

     - [Mensagens em quarentena no EOP](quarantine-email-messages.md)
     - [Gerenciar arquivos e mensagens em quarentena como administrador no EOP](manage-quarantined-messages-and-files.md)
     - [Localizar e liberar mensagens em quarentena como usuário no EOP](find-and-release-quarantined-messages-as-a-user.md)

   - **Adicionar o texto do cabeçalho X**: esta caixa é obrigatória e só estará disponível se você tiver selecionado **Adicionar cabeçalho X** como a ação para o veredito de filtragem de spam. O valor especificado é o campo de cabeçalho *nome* adicionado ao cabeçalho da mensagem. O campo de cabeçalho *valor* é sempre `This message appears to be spam`.

     O tamanho máximo é de 255 caracteres, e o valor não pode conter espaços ou dois pontos (:).

     Por exemplo, se você inserir o valor `X-This-is-my-custom-header`, o cabeçalho X adicionado à mensagem será `X-This-is-my-custom-header: This message appears to be spam.`

     Se você inserir um valor contendo espaços ou dois pontos (:), o valor inserido será ignorado, e o cabeçalho X padrão será adicionado à mensagem (`X-This-Is-Spam: This message appears to be spam.`).

   - **Preceder a linha de assunto com este texto**: esta caixa é obrigatória e só estará disponível se você selecionar **Preceder a linha de assunto com texto** como a ação para um veredito de filtragem de spam. Digite o texto a ser adicionado ao início da linha de assunto da mensagem.

   - **Redirecionar para este endereço de email**: esta caixa é obrigatória e só estará disponível se você selecionar **Redirecionar mensagem para o endereço de email** como a ação para um veredito de filtragem de spam. Digite o endereço de email para o qual você deseja enviar a mensagem. É possível inserir diversos valores separados por ponto e vírgula (;).

   - **Habilitar Dicas de Segurança**: por padrão, as Dicas de Segurança estão habilitadas, mas é possível desabilitá-las desmarcando a caixa de seleção. Para obter mais informações sobre as Dicas de Segurança, confira [Dicas de segurança em mensagens de e-mail](safety-tips-in-office-365.md).

   - **Habilitar ZAP (limpeza automática zero hora)**: a ZAP detecta e realiza ações em mensagens já enviadas a caixas de correio do Exchange Online. Para obter mais informações, confira [Limpeza Automática zero hora: proteção contra spam e malware](zero-hour-auto-purge.md).

     A ZAP está ativada por padrão. Quando ZAP está ativada, as seguintes configurações estarão disponíveis:

     - **Habilitar ZAP para mensagens de phishing**: por padrão, a ZAP está habilitada para detecções de phishing, mas é possível desabilitá-la desmarcando a caixa de seleção.
     - **Habilitar ZAP para mensagens de spam**: por padrão, a ZAP está habilitada para detecções de spam, mas é possível desabilitá-la desmarcando a caixa de seleção.

   - **Habilitar notificações de spam para usuário final**: para mais informações, confira a seção [Configurar notificações de spam para usuário final](#configure-end-user-spam-notifications) mais adiante neste tópico.

   Ao terminar, clique em **Avançar**.

7. No submenu de **lista Permissões e bloqueios** exibido, é possível configurar os remetentes de mensagens, por endereço de email ou domínio de email, que podem ignorar a filtragem de spam.

   Na seção **Permitido**, é possível configurar os remetentes e domínios permitidos. Na seção **Bloqueado**, é possível adicionar os remetentes e domínios bloqueados.

   > [!IMPORTANT]
   >
   > Pense bem antes de adicionar domínios à lista de domínios permitidos. Para mais informações, confira [Criar listas de remetentes seguros no EOP](create-safe-sender-lists-in-office-365.md).
   >
   > Nunca adicione seus próprios [domínios aceitos](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) ou domínios comuns (por exemplo, microsoft.com ou office.com) à lista de domínios permitidos. Se esses domínios puderem ignorar a filtragem de spam, isso permitirá que invasores enviem facilmente emails para sua organização.
   >
   > Bloquear manualmente os domínios ao adicioná-los à lista de domínios bloqueados não é algo perigoso, mas pode aumentar sua carga de trabalho administrativa. Para obter mais informações, confira [Criar listas de bloqueios de remetentes no EOP](create-block-sender-lists-in-office-365.md).
   >
   > Em algumas ocasiões, os filtros perderão uma mensagem, você não concordará com o veredito da filtragem, ou nossos sistemas demorarão algum tempo para se ajustar. Nesses casos, a lista de permissões e a lista de bloqueios estarão disponíveis para substituir os vereditos de filtragem atuais. Porém, use estas listas com moderação e temporariamente: listas longas podem se tornar não gerenciáveis, e a pilha de filtragem deverá executar o que precisa ser feito. Se você for manter um domínio permitido por um longo período de tempo, diga ao remetente para verificar se seu domínio está autenticado e configure o DMARC para rejeitá-lo, caso não esteja.

   As etapas para adicionar entradas a qualquer uma das listas são as mesmas:

   1. Clique no link da lista que você deseja configurar:
      - **Permitido** \> **Remetentes**: Clique em **Gerenciar (nn) remetente(s)**.
      - **Permitido** \> **Domínios**: Clique em **Permitir domínios**.
      - **Bloqueado** \> **Remetentes**: Clique em **Gerenciar (nn) remetente(s)**.
      - **Bloqueado** \> **Domínios**: Clique em **Bloquear domínios**.

   2. No submenu exibido, faça as seguintes etapas:
      1. Clique no ![ícone Criar](../../media/m365-cc-sc-create-icon.png) **Adicionar remetentes** ou **Adicionar domínios**.
      2. No submenu **Adicionar remetentes** ou **Adicionar domínios** exibido, insira o endereço de email do remetente na caixa **Remetente** ou o domínio na caixa **Domínio**. Ao digitar, o valor será exibido abaixo da caixa. Quando terminar de digitar o endereço de email ou o domínio, selecione o valor abaixo da caixa.
      3. Repita a etapa anterior quantas vezes for necessário. Para remover uma entrada existente, clique em Remover ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) ao lado do valor.

      Quando terminar, clique em **Adicionar remetentes** ou **Adicionar domínios**.

      De volta ao submenu principal, os remetentes ou os domínios adicionados estarão listados na página. Para remover uma entrada desta página, faça as seguintes etapas:

      1. Selecione uma ou mais entradas na lista. Você também pode usar a caixa de **Pesquisa** para encontrar valores na lista.
      2. Depois de selecionar pelo menos uma entrada, o ícone Excluir ![Ícone Excluir](../../media/m365-cc-sc-delete-icon.png) será exibido.
      3. Clique no ícone Excluir ![Ícone Excluir](../../media/m365-cc-sc-delete-icon.png) para remover as entradas selecionadas.

      Quando terminar, clique em **Concluído**.

      De volta à página de **lista Permissões e bloqueios**, clique em **Avançar** quando tiver lido para continuar.

8. Na página **Revisão** exibida, revise suas configurações. Você pode selecionar **Editar** em cada seção para modificar as configurações da seção. Ou você pode clicar em **Voltar** ou selecionar a página específica no assistente.

   Quando terminar, clique em **Criar**.

9. Na mensagem de confirmação exibida, clique em **Concluído**.

## <a name="use-the-security-center-to-view-anti-spam-policies"></a>Usar o centro de segurança para exibir políticas antispam

1. No centro de segurança, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **seção** Políticas \> **Anti-spam**.

2. Na página **Políticas anti-spam**, procure um dos seguintes valores:
   - O valor **Tipo** é a **Política antispam personalizada** 
   - O valor **Nome** é a **Política de entrada antispam (Padrão)** 

   As propriedades a seguir são exibidas na lista de políticas antispam:

   - **Nome**
   - **Status**
   - **Prioridade**
   - **Tipo**

3. Ao selecionar uma política antispam clicando no nome, as configurações da política serão exibidas em um submenu.

## <a name="use-the-security-center-to-modify-anti-spam-policies"></a>Usar o centro de segurança para modificar políticas antispam

1. No centro de segurança, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **seção** Políticas \> **Anti-spam**.

2. Na página **Políticas antispam**, selecione uma política antispam da lista clicando no nome:
   - Uma política personalizada que você criou em que o valor da coluna **Tipo** é **Política antispam personalizada**.
   - A política padrão denominada **Política de entrada antispam (Padrão)**.

3. No submenu de detalhes da política exibido, selecione **Editar** em cada seção para modificar as configurações da seção. Para mais informações sobre as configurações, confira a seção anterior [Usar o centro de segurança para criar políticas antispam](#use-the-security-center-to-create-anti-spam-policies) neste artigo.

   Para a política antispam padrão, a seção **Aplicada a** não está disponível (a política se aplica a todos), e não é possível renomear a política.

Para habilitar ou desabilitar uma política, definir a ordem de prioridade da política ou configurar notificações de quarentena de usuário final, confira as seções a seguir.

### <a name="enable-or-disable-anti-spam-policies"></a>Habilitar ou desabilitar políticas antispam

Não é possível desabilitar a política antispam padrão.

1. No centro de segurança, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **seção** Políticas \> **Anti-spam**.

2. Na página **Políticas antispam**, selecione uma política com o **Valor de tipo** da **Política antispam personalizada** na lista clicando no nome.

3. Na parte superior do submenu de detalhes da política exibido, você verá um dos seguintes valores:
   - **Política desativada**: para ativar a política, clique no ![ícone Ativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Ativar** .
   - **Política ativada**: para desativar a política, clique no ![ícone Desativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Desativar**.

4. Na caixa de diálogo de confirmação exibida, clique em **Ativar** ou **Desativar**.

5. Clique em **Fechar** no submenu de detalhes da política.

De volta à página da política principal, o valor **Status** da política será **Ativado** ou **Desativado**.

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>Definir a prioridade das políticas antispam personalizadas

Por padrão, as políticas antispam recebem uma prioridade baseada na ordem em que elas foram criadas (as políticas mais recentes são de prioridade mais baixa do que as políticas mais antigas). Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade). Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.

Para alterar a prioridade de uma política, clique em **Aumentar prioridade** ou **Diminuir prioridade** nas propriedades da política (não é possível modificar diretamente o número da **Prioridade** no centro de segurança). Alterar a prioridade de uma política só faz sentido se você tiver várias políticas.

 **Observações**:

- No centro de segurança, só é possível alterar a prioridade da política antispam depois de criá-la. No PowerShell, é possível substituir a prioridade padrão ao criar a regra de filtro de spam (o que pode afetar a prioridade das regras existentes).
- As políticas antispam são processadas na ordem em que são exibidas (a primeira política tem o valor de **Prioridade** 0). A política antispam padrão tem o valor de prioridade **Mais baixo**, e isso não pode ser alterado.

1. No centro de segurança, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **seção** Políticas \> **Anti-spam**.

2. Na página **Políticas antispam**, selecione uma política com o **Valor de tipo** da **Política antispam personalizada** na lista clicando no nome.

3. Na parte superior do submenu de detalhes da política exibido, você verá **Aumentar a prioridade** ou **Diminuir a prioridade** com base no valor de prioridade atual e no número de políticas personalizadas:
   - A política antispam com o valor **Prioridade** **0** tem apenas a opção **Diminuir prioridade** disponível.
   - A política anti-spam com o valor de **Prioridade** mais baixo (por exemplo, **3**) tem apenas a opção **Aumentar prioridade** disponível.
   - Se você tiver três ou mais políticas antispam, as políticas entre os valores de prioridade mais altos e mais baixos têm as opções **Aumentar prioridade** e **Diminuir prioridade** disponíveis.

   Clique no ![ícone Aumentar prioridade](../../media/m365-cc-sc-increase-icon.png) **Aumentar prioridade** ou no ![ícone Diminuir prioridade](../../media/m365-cc-sc-decrease-icon.png) **Diminuir prioridade** para alterar o valor da **Prioridade**.

4. Quando terminar, clique em **Fechar** no submenu de detalhes da política.

### <a name="configure-end-user-spam-notifications"></a>Configurar as notificações de spam para usuário final

Quando um veredito de filtragem de spam coloca uma mensagem em quarentena, é possível configurar as notificações de spam para usuário final de modo que os destinatários saibam o que houve com as mensagens que foram enviadas para eles. Para obter mais informações sobre essas notificações, confira [Notificações de spam para usuário final no EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).

1. No centro de segurança, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **seção** Políticas \> **Anti-spam**.

2. Na página **Políticas antispam**, selecione uma política antispam da lista clicando no nome:
   - Uma política personalizada que você criou em que o valor da coluna **Tipo** é **Política antispam personalizada**.
   - A política padrão denominada **Política de entrada antispam (Padrão)**.

3. No submenu de detalhes da política exibido, clique em **Editar** na seção **Ações**. No submenu **Ações** exibido, defina as seguintes configurações:

   - **Habilitar notificações de spam do usuário final**: selecione a caixa de seleção para habilitar as notificações ou desmarque a caixa de seleção para desabilitar as notificações. Quando você marca a caixa de seleção, são exibidas as seguintes configurações adicionais:

     - **Enviar notificações de spam para usuário final a cada (dias)**: selecione a frequência de envio das notificações. O valor padrão é de 3 dias. Você pode inserir de 1 a 15 dias.

       Há três ciclos de notificação de spam para o usuário final dentro de um período de 24 horas que se iniciam nos seguintes horários: 01:00 UTC, 08:00 UTC e 16:00 UTC.

       > [!NOTE]
       > Se perdermos uma notificação durante um ciclo anterior, um ciclo subsequente gerará a notificação. Isso pode dar a impressão da ocorrência de várias notificações no mesmo dia.

     - **Idioma**: clique no menu suspenso e selecione um idioma disponível na lista. O valor padrão é **Padrão**, o que significa inglês.

   Quando concluir, clique em **Salvar**.

4. De volta ao submenu de detalhes da política, clique em **Fechar**.

## <a name="use-the-security-center-to-remove-custom-anti-spam-policies"></a>Usar o centro de segurança para remover políticas anti-spam

Quando você usa o centro de segurança para remover uma política anti-spam, a regra de filtro de spam e a política de filtro de spam correspondente são excluídas. Você não pode remover a política antispam padrão.

1. No centro de segurança, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **seção** Políticas \> **Anti-spam**.

2. Na página **Políticas antispam**, selecione uma política com o **Valor de tipo** da **Política antispam personalizada** na lista clicando no nome. Na parte superior do submenu de detalhes da política exibido, clique no ![ícone Mais ações](../../media/m365-cc-sc-more-actions-icon.png) **Mais ações** \> ![ícone Excluir política](../../media/m365-cc-sc-delete-icon.png) **Excluir política**.

3. Na caixa de diálogo de confirmação exibida, clique em **Sim**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a>Use o Exchange Online PowerShell ou EOP PowerShell autônomo para configurar políticas anti-spam

Conforme descrito anteriormente, uma política antispam consiste em uma política de filtro de spam e uma regra de filtro de spam.

No Exchange Online PowerShell ou no EOP PowerShell autônomo, a diferença entre políticas de filtro de spam e regras de filtro de spam é aparente. Gerencie políticas de filtro de spam usando os cmdlets **\*-HostedContentFilterPolicy** e gerencie regras de filtro de spam usando os cmdlets **\*-HostedContentFilterRule**.

- No PowerShell, crie primeiro a política de filtro de spam, para depois criar a regra de filtro de spam que identifica a política à qual a regra se aplica.
- No PowerShell, modifique as configurações da política de filtro de spam e da regra de filtro de spam separadamente.
- Quando você remove uma política de filtro de spam do PowerShell, a regra de filtro de spam correspondente não é removida automaticamente e vice-versa.

As seguintes configurações de política antispam só estão disponíveis no PowerShell:

- O parâmetro _MarkAsSpamBulkMail_ que é `On` por padrão. Os efeitos dessa configuração foram explicados anteriormente na seção [Usar o centro de segurança para criar políticas antispam](#use-the-security-center-to-create-anti-spam-policies) deste tópico.

- As seguintes configurações de notificações da quarentena de spam para usuário final:
  - O parâmetro _DownloadLink_, que mostra ou oculta o link para a Ferramenta de Relatórios de Lixo Eletrônico para Outlook.
  - O parâmetro _EndUserSpamNotificationCustomSubject_, que você pode usar para personalizar a linha de assunto da notificação.

### <a name="use-powershell-to-create-anti-spam-policies"></a>Usar o PowerShell para criar políticas antispam

A criação de uma política antispam no PowerShell é um processo de duas etapas:

1. Crie a política de filtro de spam.
2. Crie a regra de filtro de spam que especifica a política de filtro de spam à qual a regra se aplica.

 **Observações**:

- você pode criar uma nova regra de filtro de spam e atribuir uma política de filtro de spam existente e não associada a ela. Não é possível associar uma regra de filtro de spam a mais de uma política de filtro de spam.
- Defina as seguintes configurações nas novas políticas de filtro de spam no PowerShell que não estão disponíveis no centro de segurança até que você crie a política:
  - Crie a nova política como desabilitada (_Habilitada_ `$false` no cmdlet **New-HostedContentFilterRule**).
  - Defina a prioridade da política durante a criação (_Prioridade__\<Number\>_) no cmdlet **New-HostedContentFilterRule**).

- Uma nova política de filtro de spam criada no PowerShell não ficará visível no centro de segurança até você atribua a política a uma regra de filtro de spam.

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>Etapa 1: usar o PowerShell para criar uma política de filtro de spam

Para criar uma política de filtro de spam, use esta sintaxe:

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

Esse exemplo cria uma política de filtro de spam chamada Contoso Executives com as seguintes configurações:

- Colocar mensagens em quarentena quando o veredicto de filtragem de spam for spam ou spam de alta confiança.
- O BCL 7, 8 ou 9 dispara a ação para um veredito de filtragem de spam de email em massa.

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

Para obter mais informações detalhadas de sintaxe e parâmetro, confira [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a>Etapa 2: usar o PowerShell para criar uma regra de filtro de spam

Para criar uma regra de filtro de spam, use esta sintaxe:

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

Esse exemplo cria uma nova regra de filtro de spam chamada Contoso Executives com as seguintes configurações:

- A política de filtro de spam chamada Contoso Executives é associada à regra.
- A regra se aplica aos membros do grupo chamado Contoso Executives Group.

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

Para obter mais informações detalhadas de sintaxe e parâmetro, confira [New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule).

### <a name="use-powershell-to-view-spam-filter-policies"></a>Usar o PowerShell para visualizar políticas de filtro de spam

Para retornar uma lista de resumo de todas as políticas de filtro de spam, execute este comando:

```PowerShell
Get-HostedContentFilterPolicy
```

Para retornar informações detalhadas sobre uma política de filtro de spam específica, use esta sintaxe:

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

Este exemplo retorna todos os valores de propriedade da política de filtro de spam chamada Executives.

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

Para obter mais informações detalhadas de sintaxe e parâmetro, confira [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).

### <a name="use-powershell-to-view-spam-filter-rules"></a>Usar o PowerShell para visualizar regras de filtro de spam

Para visualizar regras de filtro de spam existentes, use a seguinte sintaxe:

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

Para retornar uma lista de resumo de todas as regras de filtro de spam, execute este comando:

```PowerShell
Get-HostedContentFilterRule
```

Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

Para retornar informações detalhadas sobre uma regra de filtro de spam específica, use esta sintaxe:

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

Este exemplo retorna todos os valores de propriedade da regra de filtro de spam chamada Contoso Executives.

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

Para obter mais informações detalhadas de sintaxe e parâmetro, confira [Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule).

### <a name="use-powershell-to-modify-spam-filter-policies"></a>Usar o PowerShell para modificar políticas de filtro de spam

Além dos itens a seguir, as mesmas configurações estão disponíveis quando você modifica uma política de filtro de spam no Windows PowerShell, como ao criar a política conforme descrito anteriormente na seção [Etapa 1: usar o PowerShell para criar uma política de filtro de spam](#step-1-use-powershell-to-create-a-spam-filter-policy) deste tópico.

- A opção _MakeDefault_ que transforma a política especificada em política padrão (aplicada a todos, sempre com a **Menor** prioridade, e que pode ser excluída) só está disponível quando você modifica uma política de filtro de spam no PowerShell.
- Não é possível renomear uma política de filtro de spam (o cmdlet **Set-HostedContentFilterPolicy** não tem o parâmetro _Name_). Quando você renomeia uma política antispam no centro de segurança, só é possível renomear a _regra_ do filtro de spam.

Para modificar uma política de filtro de spam, use esta sintaxe:

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

Para obter mais informações detalhadas de sintaxe e parâmetro, confira [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).

### <a name="use-powershell-to-modify-spam-filter-rules"></a>Usar o PowerShell para modificar regras de filtro de spam

A única configuração que não está disponível quando você modifica uma regra de filtro de spam no PowerShell é o parâmetro _Enabled_, que permite criar uma regra desabilitada. Para habilitar ou desabilitar regras de filtro de spam existentes, confira a próxima seção.

Do contrário, nenhuma configuração adicional estará disponível quando você modificar a regra de filtro de spam no PowerShell. As mesmas configurações estão disponíveis quando você cria uma regra conforme descrito anteriormente na seção [Etapa 2: usar o PowerShell para criar uma regra de filtro de spam](#step-2-use-powershell-to-create-a-spam-filter-rule) deste tópico.

Para modificar uma regra de filtro de spam, use esta sintaxe:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

Este exemplo renomeia a regra de filtro de spam existente chamada `{Fabrikam Spam Filter}`.

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

Para obter mais informações detalhadas de sintaxe e parâmetro, confira [Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule).

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a>Usar o PowerShell para habilitar ou desabilitar regras de filtro de spam

Habilitar ou desabilitar uma regra de filtro de spam no PowerShell habilita ou desabilita toda a política antispam (a regra de filtro de spam e a política de filtro de spam atribuída). Não é possível habilitar ou desabilitar a política antispam padrão (ela é sempre aplicada a todos os destinatários).

Para habilitar ou desabilitar uma regra de filtro de spam no PowerShell, use esta sintaxe:

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

Este exemplo desabilita a regra de filtro de spam chamada Marketing Department.

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

Este exemplo habilita a mesma regra.

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

Para obter informações detalhadas de sintaxe e parâmetro, confira [Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule) e [Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule).

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a>Usar o PowerShell para definir a prioridade das regras de filtro de spam

O valor mais alto de prioridade que pode ser definido em uma regra é 0. O valor mais baixo que pode ser definido depende do número de regras. Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4. Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras. Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.

Para definir a prioridade de uma regra de filtro de spam no PowerShell, use a seguinte sintaxe:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

Este exemplo define a prioridade da regra chamada Marketing Department como 2. Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

**Observações**:

- para definir a prioridade de uma nova regra ao criá-la, use o parâmetro _Prioridade_ no cmdlet **New-HostedContentFilterRule**.
- A política de filtro de spam padrão não tem uma regra de filtro de spam correspondente e sempre tem o valor de prioridade inalterável **Menor**.

### <a name="use-powershell-to-remove-spam-filter-policies"></a>Usar o PowerShell para remover políticas de filtro de spam

Quando você usa o PowerShell para remover uma política de filtro de spam, a regra de filtro de spam correspondente não é removida.

Para remover uma política de filtro de spam no PowerShell, use esta sintaxe:

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

Este exemplo remove a política de filtro de spam chamada Marketing Department.

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

Para obter informações detalhadas de sintaxe e parâmetro, confira [Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy).

### <a name="use-powershell-to-remove-spam-filter-rules"></a>Usar o PowerShell para remover regras de filtro de spam

Quando você usa o PowerShell para remover uma regra de filtro de spam, a política de filtro de spam correspondente não é removida.

Para remover uma regra de filtro de spam no PowerShell, use esta sintaxe:

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

Este exemplo remove a regra de filtro de spam chamada Marketing Department.

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

Para obter informações detalhadas de sintaxe e parâmetro, confira [Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>Enviar uma mensagem do GTUBE para testar as configurações de política de spam

> [!NOTE]
> Essas etapas só funcionarão se a organização de email da qual você está enviando a mensagem GTUBE não tiver verificação de spam de saída. Se isso acontecer, você não poderá enviar a mensagem de teste.

O GTUBE (teste genérico para email em massa não solicitado) é uma cadeia de caracteres de texto incluída em uma mensagem de texto para verificar as configurações antispam da sua organização. A mensagem do GTUBE é similar ao arquivo de texto do EICAR (Instituto Europeu para Pesquisa de Antivírus de Computador) em configurações de malware de teste.

Inclua o seguinte texto do GTUBE em uma mensagem de email em uma única linha, sem espaços ou quebras de linha:

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```
