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
ms.openlocfilehash: 6b9bfbb324858e686d87335e55e281d1caf51c73
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287504"
---
# <a name="configure-anti-spam-policies-in-eop"></a>Configurar políticas antispam no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou um cliente independente do Exchange Online Protection (EOP), ou organizações sem as caixas de correio do Exchange Online, as mensagens de e-mail de entrada serão automaticamente protegidas contra spam por EOP. A EOP usa políticas antispam (também conhecidas como políticas de filtro de spam ou políticas de filtro de conteúdo) como parte da defesa geral da sua organização contra spams. Para obter mais informações, consulte [Proteção antispam](anti-spam-protection.md).

Os administradores podem visualizar, editar e configurar (mas não excluir) a política antispam padrão. Para maior granularidade, também é possível criar políticas antispam personalizadas aplicadas a determinados usuários, grupos ou domínios na sua organização. Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.

Você pode configurar políticas anti-spam no Centro de Conformidade e Segurança ou no PowerShell (organizações do Exchange Online PowerShell para Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).

Os elementos básicos de uma política antispam são:

- **A política de filtro de spam**: especifica as ações de vereditos de filtragem de spam e as opções de notificação.
- **A regra de filtro de spam**: especifica a prioridade e os filtros de destinatário (a quem a política se aplica) para uma política de filtro de spam.

A diferença entre esses dois elementos não é óbvia quando você gerencia as políticas antispam no Centro de Segurança e Conformidade:

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

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente à página de **Configurações antispam**, use <https://protection.office.com/antispam>.

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos deste artigo:
  - Para adicionar, modificar e excluir políticas antispam, você precisa ser membro dos grupos de funções **Gerenciamento da Organização** ou **Administrador de Segurança**.
  - Para acesso de somente leitura às políticas anti-spam, você precisa ser membro dos grupos de funções **Leitor Global** ou **Leitor de Segurança**.

  Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

- Para nossas configurações recomendadas para políticas antispam, confira [Configurações da política antispam EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a>Usar o Centro de Conformidade e Segurança para criar políticas antispam

Criar uma política antispam personalizada no Centro de Conformidade e Segurança gera uma regra de filtro de spam e a política de filtro de spam associada ao mesmo tempo, com o mesmo nome para ambas.

1. No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.

2. Na página **Configurações antispam**, clique em **Criar uma política**.

3. No submenu **Nova política de filtro de spam** que é aberto, defina as seguintes configurações:

   - **Nome**: insira um nome exclusivo e descritivo para a política. Não use os seguintes caracteres: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.

      Caso você tenha criado anteriormente alguma política antispam no EAC (Centro de administração do Exchange) que contenha esses caracteres, renomeie a política no PowerShell. Para obter instruções, confira a seção [Usar o PowerShell para modificar regras de filtro de spam](#use-powershell-to-modify-spam-filter-rules) mais adiante neste tópico.

   - **Descrição**: digite uma descrição opcional para a política.

4. (Opcional) Expanda a seção **Ações de spam e em massa** e verifique ou defina as seguintes configurações:

   - **Selecionar a ação a ser executada para emails de spam e em massa recebidos**: selecione ou revise a ação a ser realizada em relação às mensagens com base nos seguintes vereditos de filtragem de spam:

     - **Spam**
     - **Spam de alta confiança**
     - **Email de phishing**
     - **Email de phishing de alta confiança**
     - **Email em massa**

     As ações disponíveis para vereditos de filtragem de spam são descritas na tabela a seguir.

     - Uma marca de seleção ( ![Marca de seleção](../../media/checkmark.png)) indica que a ação está disponível (nem todas as ações estão disponíveis para todos os vereditos de filtragem de spam).
     - Um asterisco ( <sup>\*</sup> ) após a marca de seleção indica a ação padrão para o veredito de filtragem de spam.

     ****

     |Ação|Spam|Alto<br>confiança<br>spam|Phishing<br>email|Alto<br>confiança<br>phishing<br>email|Em massa<br>email|
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
     > Em ambientes da EOP autônoma, em que a EOP protege as caixas de correio locais do Exchange, é preciso configurar regras de fluxo de email (também conhecidas como regras de transporte) no Exchange local para traduzir o veredito de filtragem de spam do EOP, de modo que a regra do lixo eletrônico possa mover as mensagens para a pasta de Lixo Eletrônico. Para obter detalhes, confira [Configurar a EOP autônoma para enviar spam à pasta Lixo Eletrônico em ambientes híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).
     >
     > <sup>2</sup>É possível usar esse valor como uma condição nas regras de fluxo de email para filtrar ou rotear a mensagem.

   - **Selecionar o limite**: especifica o BCL (nível de reclamação em massa) de uma mensagem que dispara a ação especificada para o veredito de filtragem de spam de **Email em massa** (maior que o valor especificado, não superior ou igual a ele). Um valor mais alto indica que a mensagem é menos desejável (é mais provável que a mensagem pareça um spam). O valor padrão é 7. Para obter mais informações, confira [BCL (Nível de reclamação em massa) no EOP](bulk-complaint-level-values.md) e [Qual é a diferença entre lixo eletrônico e e-mail em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md).

     Por padrão, a única configuração _MarkAsSpamBulkMail_ do PowerShell é `On` nas políticas antispam. Essa configuração afeta significativamente os resultados de um veredito de filtragem de **Email em massa**:

     - **_MarkAsSpamBulkMail_ está Ativada**: um BCL maior do que o limite é convertido para um SCL 6 que corresponde a um veredito de filtragem de **Spam**, e a ação para o veredito de filtragem de **Email em massa** é executada na mensagem.

     - **_MarkAsSpamBulkMail_ é Desativada**: a mensagem tem o carimbo do BCL, mas _nenhuma ação_ é realizada para o veredito de filtragem de **Email em massa**. De fato, o limite do BCL e a ação do veredito de filtragem de **Email em massa** são irrelevantes.

   - **Quarentena**: especifica por quanto tempo manter a mensagem em quarentena se você selecionar **Colocar mensagem em quarentena** como ação para um veredito de filtragem de spam. Após o período da quarentena, a mensagem será excluída. O valor padrão é de 30 dias. O valor válido é de 1 a 30 dias. Para obter informações sobre quarentena, confira os seguintes tópicos:

     - [Mensagens em quarentena no EOP](quarantine-email-messages.md)
     - [Gerenciar arquivos e mensagens em quarentena como administrador no EOP](manage-quarantined-messages-and-files.md)
     - [Localizar e liberar mensagens em quarentena como usuário no EOP](find-and-release-quarantined-messages-as-a-user.md)

   - **Adicionar o texto do cabeçalho X**: esta caixa é obrigatória e só estará disponível se você tiver selecionado **Adicionar cabeçalho X** como a ação para o veredito de filtragem de spam. O valor especificado é o campo de cabeçalho *nome* adicionado ao cabeçalho da mensagem. O campo de cabeçalho *valor* é sempre `This message appears to be spam`.

     O tamanho máximo é de 255 caracteres, e o valor não pode conter espaços ou dois pontos (:).

     Por exemplo, se você inserir o valor `X-This-is-my-custom-header`, o cabeçalho X adicionado à mensagem será `X-This-is-my-custom-header: This message appears to be spam.`

     Se você inserir um valor contendo espaços ou dois pontos (:), o valor inserido será ignorado, e o cabeçalho X padrão será adicionado à mensagem (`X-This-Is-Spam: This message appears to be spam.`).

   - **Preceder a linha de assunto com este texto**: esta caixa é obrigatória e só estará disponível se você selecionar **Preceder a linha de assunto com texto** como a ação para um veredito de filtragem de spam. Digite o texto a ser adicionado ao início da linha de assunto da mensagem.

   - **Redirecionar para este endereço de email**: esta caixa é obrigatória e só estará disponível se você selecionar **Redirecionar mensagem para o endereço de email** como a ação para um veredito de filtragem de spam. Digite o endereço de email para o qual você deseja enviar a mensagem. É possível inserir diversos valores separados por ponto e vírgula (;).

   - **Dicas de Segurança**: por padrão, as Dicas de Segurança estão habilitadas, mas é possível desabilitá-las desmarcando a caixa de seleção **Ativado**. Para obter mais informações sobre as Dicas de Segurança, confira [Dicas de segurança em mensagens de e-mail](safety-tips-in-office-365.md).

   Configurações de **Limpeza Automática Zero Hora**: a ZAP detecta e realiza ações em mensagens já enviadas a caixas de correio do Exchange Online. Para obter mais informações sobre a ZAP, confira [Limpeza Automática Zero Hora – proteção contra spam e malware](zero-hour-auto-purge.md).

   - **ZAP de spam**: por padrão, a ZAP é habilitada para detecções de spam, mas é possível desabilitá-la desmarcando a caixa de seleção **Ativado**.

   - **ZAP de phishing**: por padrão, a ZAP é habilitada para detecções de phishing, mas é possível desabilitá-la desmarcando a caixa de seleção **Ativado**.

5. (Opcional) Expanda a seção **Listas de permissão** para configurar os remetentes de mensagens por endereço ou domínio de email que podem ignorar a filtragem de spam:

   > [!CAUTION]
   >
   > - Pense bem antes de adicionar domínios aqui. Para mais informações, consulte [Crie listas de remetentes seguros no EOP](create-safe-sender-lists-in-office-365.md).
   >
   > - Nunca adicione domínios aceitos (domínios que pertencem a você) ou domínios comuns (por exemplo, microsoft.com ou office.com) à lista de domínios permitidos. Isso permitirá que invasores enviem emails que ignorem a filtragem de spam da sua organização.

   - **Permitir remetente**: clique em **Editar**. No submenu **Lista de remetentes permitidos** exibido:

      a. Insira o endereço de email do remetente. Você pode especificar vários endereços de email separados por ponto e vírgula (;).

      b. Click ![Ícone Adicionar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) para adicionar os remetentes.

      Repita essas etapas quantas vezes for necessário.

      Os remetentes que você adicionou aparecem na seção **Remetente Permitido** no submenu. Para excluir um remetente, clique em ![ícone Remover](../../media/scc-remove-icon.png).

      Quando concluir, clique em **Salvar**.

   - **Permitir domínio**: clique em **Editar**. No submenu **Lista de domínios permitidos** exibido, execute estas etapas:

      a. Insira o domínio. Vários domínios podem ser especificados, separados por ponto e vírgula (;).

      b. Click ![Ícone Adicionar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) para adicionar os domínios.

      Repita essas etapas quantas vezes for necessário.

      Os domínios que você adicionou aparecem na seção **Domínio Permitido** no submenu. Para excluir um domínio, clique em ![ícone Remover](../../media/scc-remove-icon.png).

      Quando concluir, clique em **Salvar**.

6. (Opcional) Expanda a seção **Listas de bloqueios** para configurar os remetentes de mensagens por endereço ou domínio de email que sempre serão marcados como spam de alta confidencialidade:

   > [!NOTE]
   > Bloquear manualmente os domínios não é perigoso, mas pode aumentar sua carga de trabalho administrativa. Para obter mais informações, confira [Criar listas de bloqueios de remetentes no EOP](create-block-sender-lists-in-office-365.md).

   - **Bloquear remetente**: clique em **Editar**. No submenu **Lista de remetentes bloqueados** exibido, siga estas etapas:

      a. Insira o endereço de email do remetente. Você pode especificar vários endereços de email separados por ponto e vírgula (;). Curingas (*) não são permitidos.

      b. Click ![Ícone Adicionar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) para adicionar os remetentes.

      Repita essas etapas quantas vezes for necessário.

      Os remetentes que você adicionou aparecem na seção **Remetente bloqueado** no submenu. Para excluir um remetente, clique em ![botão Remover](../../media/scc-remove-icon.png).

      Quando concluir, clique em **Salvar**.

   - **Bloquear domínio**: clique em **Editar**. No submenu **Lista de domínios bloqueados** exibido:

      a. Insira o domínio. Vários domínios podem ser especificados, separados por ponto e vírgula (;). Curingas (*) não são permitidos.

      b. Click ![Ícone Adicionar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) para adicionar os domínios.

      Repita essas etapas quantas vezes for necessário.

      Os domínios que você adicionou aparecem na lista **Domínio Bloqueado** no submenu. Para excluir um domínio, clique em ![botão Remover](../../media/scc-remove-icon.png).

      Quando concluir, clique em **Salvar**.

7. (Opcional) Expanda a seção **Spam internacional** para configurar os países de origem ou idiomas de email bloqueados pela filtragem de spam:

   - **Filtrar mensagens de email escritas nos seguintes idiomas**: esta configuração é exibida por padrão (**Status: DESATIVADO**). Clique em **Editar**. No submenu **Configurações de spam internacionais** exibido, defina as seguintes configurações:

     - **Filtrar mensagens de email escritas nos seguintes idiomas**: marque a caixa de seleção para habilitar esta configuração. Desmarque a caixa de seleção para desabilitar a configuração.

     - Clique na caixa e comece a digitar o *nome* do idioma. Uma lista filtrada de idiomas com suporte será exibida, juntamente com o código ISO 639-2 de duas letras do idioma correspondente. Quando encontrar o idioma que está procurando, selecione-o. Repita essa etapa quantas vezes forem necessárias.

       A lista de idiomas selecionados aparecerá no submenu. Para excluir um idioma, clique em ![Botão Remover](../../media/scc-remove-icon.png).

     Quando concluir, clique em **Salvar**.

   - **Filtrar mensagens de email enviadas dos seguintes países ou regiões**: esta configuração é exibida por padrão (**Status: DESATIVADO**). Para habilitar, clique em **Editar**. No submenu **Configurações de spam internacionais** exibido, defina as seguintes configurações:

     - **Filtrar mensagens de email enviadas dos seguintes países ou regiões**: marque a caixa de seleção para habilitar esta configuração. Desmarque a caixa de seleção para desabilitar a configuração.

     - Clique na caixa e comece a digitar o *nome* do país ou região. Uma lista filtrada de países com suporte será exibida, juntamente com o código ISO 3166-1 de duas letras do país correspondente. Quando encontrar o país ou região que está procurando, selecione-o. Repita essa etapa quantas vezes forem necessárias.

       A lista de países selecionados aparecerá no submenu. Para excluir um país ou região, clique em ![Botão Remover](../../media/scc-remove-icon.png).

     Quando concluir, clique em **Salvar**.

8. A seção opcional **Propriedades de spam** contém configurações de ASF (filtragem de spam avançada) que estão desativadas por padrão. As configurações de ASF estão em processo de substituição, e a funcionalidade delas está sendo incorporada a outras partes da pilha de filtragem. Recomendamos deixar todas essas configurações de ASF desativadas em suas políticas antispam.

   Para obter mais detalhes sobre essas configurações, confira [Configurações de filtragem de spam avançadas no EOP](advanced-spam-filtering-asf-options.md).

9. (Obrigatório) Expanda a seção **Aplicada a** para identificar os destinatários internos aos quais a política se aplica.

    Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

    O mais fácil é clicar em **Adicionar uma condição** três vezes para ver todas as condições disponíveis. Clique em ![botão Remover](../../media/scc-remove-icon.png) para remover condições que você não queira configurar.

    - **O domínio do destinatário é**: Especifica os destinatários em um ou mais domínios aceitos configurados na sua organização.  Clique na caixa **Adicionar uma marca** para ver e selecionar um domínio. Clique novamente na caixa **Adicionar uma marca** para selecionar domínios adicionais se mais de um domínio estiver disponível.

    - **O destinatário é**: especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização. Clique em **Adicionar uma marca** e comece a digitar para filtrar a lista. Clique novamente na caixa **Adicionar uma marca** para selecionar destinatários adicionais.

    - **O destinatário é um membro de**: especifica um ou mais grupos em sua organização. Clique em **Adicionar uma marca** e comece a digitar para filtrar a lista. Clique novamente na caixa **Adicionar uma marca** para selecionar destinatários adicionais.

    - **Exceto se**: para adicionar exceções à regra, clique em **Adicionar uma condição** três vezes para ver todas as exceções disponíveis. As configurações e o comportamento são exatamente como as condições.

10. Quando concluir, clique em **Salvar**.

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a>Usar o Centro de Conformidade e Segurança para visualizar políticas antispam

1. No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.

2. Na página **Configurações antispam**, clique em ![ícone Expandir](../../media/scc-expand-icon.png) para expandir uma política antispam:

   - A política padrão chamada **Política de filtro de spam padrão**.

   - Uma política personalizada que você criou em que o valor da coluna **Tipo** é **Política antispam personalizada**.

3. As configurações de política importantes são exibidas nos detalhes de política expandida que são exibidos. Para ver mais detalhes, clique em **Editar política**.

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a>Usar o Centro de Conformidade e Segurança para modificar políticas antispam

1. No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.

2. Na página **Configurações antispam**, clique em ![ícone Expandir](../../media/scc-expand-icon.png) para expandir uma política antispam:

   - A política padrão chamada **Política de filtro de spam padrão**.

   - Uma política personalizada que você criou em que o valor da coluna **Tipo** é **Política antispam personalizada**.

3. Clique em **Editar política**.

Para políticas antispam, as configurações disponíveis no submenu exibido são idênticas às descritas na seção [Usar o Centro de Conformidade e Segurança para criar políticas antispam](#use-the-security--compliance-center-to-create-anti-spam-policies).

Para a política antispam padrão chamada **Política de filtragem de spam padrão**, a seção **Aplicada a** não está disponível (a política se aplica a todos), e não é possível renomear a política.

Para habilitar ou desabilitar uma política, definir a ordem de prioridade da política ou configurar notificações de quarentena de usuário final, confira as seções a seguir.

### <a name="enable-or-disable-anti-spam-policies"></a>Habilitar ou desabilitar políticas antispam

1. No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.

2. Na página **Configurações antispam**, clique em ![ícone Expandir](../../media/scc-expand-icon.png) para expandir uma política personalizada que você criou (o valor na coluna **Tipo** é **Política antispam personalizada**).

3. Nos detalhes exibidos da política expandida, observe o valor na coluna **Ativado**.

   Mova o botão de alternância para a esquerda para desabilitar a política: ![Desativar](../../media/scc-toggle-off.png)

   Mova o botão de alternância para a direita para habilitar a política: ![Ativar](../../media/scc-toggle-on.png)

Não é possível desabilitar a política antispam padrão.

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>Definir a prioridade das políticas antispam personalizadas

Por padrão, as políticas antispam recebem uma prioridade com base na ordem em que foram criadas (políticas mais novas têm prioridade menor do que as políticas mais antigas). Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade). Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.

Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).

As políticas antispam personalizadas são exibidas na ordem em que são processadas (a primeira política tem o valor de **Prioridade** 0). A política antispam padrão chamada **Política de filtro de spam padrão** tem o valor de prioridade **Menor**, e isso não pode ser alterado.

 **Observação**: no Centro de Conformidade e Segurança, só é possível alterar a política antispam depois de criá-la. No PowerShell, é possível substituir a prioridade padrão ao criar a regra de filtro de spam (o que pode afetar a prioridade das regras existentes).

Para alterar a prioridade de uma política, mova a política para cima ou para baixo na lista (não é possível modificar diretamente o número de **Prioridade** no Centro de Conformidade e Segurança).

1. No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.

2. Na página **Configurações antispam**, encontre as políticas em que o valor na coluna **Tipo** é **Política antispam personalizada**. Observe os valores na coluna **Prioridade**:

   - A política antispam personalizada com maior prioridade tem o valor ![ícone Seta para baixo](../../media/ITPro-EAC-DownArrowIcon.png) **0**.

   - A política antispam personalizada com menor prioridade tem o valor ![ícone Seta para cima](../../media/ITPro-EAC-UpArrowIcon.png) **n** (por exemplo, ![ícone Seta para cima](../../media/ITPro-EAC-UpArrowIcon.png) **3**).

   - Se você tem três ou mais políticas antispam personalizadas, as políticas entre a maior e menor prioridade têm valores ![ícone Seta para cima](../../media/ITPro-EAC-UpArrowIcon.png)![ícone Seta para baixo](../../media/ITPro-EAC-DownArrowIcon.png) **n** (por exemplo, ![ícone Seta para cima](../../media/ITPro-EAC-UpArrowIcon.png)![ícone Seta para baixo](../../media/ITPro-EAC-DownArrowIcon.png) **2**).

3. Clique em ![ícone Seta para cima](../../media/ITPro-EAC-UpArrowIcon.png) ou ![ícone Seta para baixo](../../media/ITPro-EAC-DownArrowIcon.png) para mover a política antispam personalizada na lista de prioridade.

### <a name="configure-end-user-spam-notifications"></a>Configurar as notificações de spam para usuário final

Quando um veredito de filtragem de spam coloca uma mensagem em quarentena, é possível configurar as notificações de spam para usuário final de modo que os destinatários saibam o que houve com as mensagens que foram enviadas para eles. Para obter mais informações sobre essas notificações, confira [Notificações de spam para usuário final no EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).

1. No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.

2. Na página **Configurações antispam**, clique em ![ícone Expandir](../../media/scc-expand-icon.png) para expandir uma política antispam:

   - A política padrão chamada **Política de filtro de spam padrão**.

   - Uma política personalizada que você criou em que o valor da coluna **Tipo** é **Política antispam personalizada**.

3. Nos detalhes da política expandida, clique em **Configurar as notificações de spam para usuário final**.

4. Na caixa de diálogo **\<Policy Name\>** que se abre, defina as seguintes configurações:

   - **Habilitar as notificações de spam para usuário final**: selecione a caixa de seleção para habilitar as notificações. Desmarque a caixa de seleção para desabilitar as notificações.

   - **Enviar notificações de spam para usuário final a cada (dias)**: selecione a frequência de envio das notificações. O valor padrão é de 3 dias. Você pode inserir de 1 a 15 dias.

     Há três ciclos de notificação de spam para o usuário final dentro de um período de 24 horas que se iniciam nos seguintes horários: 01:00 UTC, 08:00 UTC e 16:00 UTC.

     > [!NOTE]
     > Se perdermos uma notificação durante um ciclo anterior, um ciclo subsequente gerará a notificação. Isso pode dar a impressão da ocorrência de várias notificações dentro do mesmo dia.

   - **Idioma da notificação**: clique no menu suspenso selecionar um idioma disponível na lista. O valor padrão é **Padrão**, o que significa inglês.

   Quando concluir, clique em **Salvar**.

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a>Usar o Centro de Conformidade e Segurança para remover políticas antispam

1. No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.

2. Na página **Configurações antispam**, clique em ![ícone Expandir](../../media/scc-expand-icon.png) para expandir a política personalizada que você deseja excluir (a coluna **Tipo** é **Política antispam personalizada**).

3. Nas informações da política expandida, clique em **Excluir política**.

4. Clique em **Sim** na caixa de diálogo exibida.

Não é possível remover a política padrão.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a>Use o Exchange Online PowerShell ou EOP PowerShell autônomo para configurar políticas anti-spam

Conforme descrito anteriormente, uma política antispam consiste em uma política de filtro de spam e uma regra de filtro de spam.

No Exchange Online PowerShell ou no EOP PowerShell autônomo, a diferença entre políticas de filtro de spam e regras de filtro de spam é aparente. Gerencie políticas de filtro de spam usando os cmdlets **\*-HostedContentFilterPolicy** e gerencie regras de filtro de spam usando os cmdlets **\*-HostedContentFilterRule**.

- No PowerShell, crie primeiro a política de filtro de spam, para depois criar a regra de filtro de spam que identifica a política à qual a regra se aplica.
- No PowerShell, modifique as configurações da política de filtro de spam e da regra de filtro de spam separadamente.
- Quando você remove uma política de filtro de spam do PowerShell, a regra de filtro de spam correspondente não é removida automaticamente e vice-versa.

As seguintes configurações de política antispam só estão disponíveis no PowerShell:

- O parâmetro _MarkAsSpamBulkMail_ que é `On` por padrão. Os efeitos dessa configuração foram explicados anteriormente na seção [Usar o Centro de Conformidade e Segurança para criar políticas antispam](#use-the-security--compliance-center-to-create-anti-spam-policies) deste tópico.

- As seguintes configurações de notificações da quarentena de spam para usuário final:

  - O parâmetro _DownloadLink_, que mostra ou oculta o link para a Ferramenta de Relatórios de Lixo Eletrônico para Outlook.

  - O parâmetro _EndUserSpamNotificationCustomSubject_, que você pode usar para personalizar a linha de assunto da notificação.

### <a name="use-powershell-to-create-anti-spam-policies"></a>Usar o PowerShell para criar políticas antispam

A criação de uma política antispam no PowerShell é um processo de duas etapas:

1. Crie a política de filtro de spam.
2. Crie a regra de filtro de spam que especifica a política de filtro de spam à qual a regra se aplica.

 **Observações**:

- você pode criar uma nova regra de filtro de spam e atribuir uma política de filtro de spam existente e não associada a ela. Não é possível associar uma regra de filtro de spam a mais de uma política de filtro de spam.

- Você pode definir as seguintes configurações em novas políticas de filtro de spam no PowerShell que não estarão disponíveis no Centro de Conformidade e Segurança até que você crie a política:

  - Crie a nova política como desabilitada (_Habilitada_ `$false` no cmdlet **New-HostedContentFilterRule**).
  - Defina a prioridade da política durante a criação (_Prioridade__\<Number\>_) no cmdlet **New-HostedContentFilterRule**).

- Uma nova política de filtro de spam criada no PowerShell não ficará visível no Centro de Conformidade e Segurança até você atribua a política a uma regra de filtro de spam.

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>Etapa 1: usar o PowerShell para criar uma política de filtro de spam

Para criar uma política de filtro de spam, use esta sintaxe:

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

Esse exemplo cria uma política de filtro de spam chamada Contoso Executives com as seguintes configurações:

- Colocar mensagens em quarentena quando o veredicto de filtragem de spam for spam ou spam de alta confiança.

- O BCL 6 dispara a ação para um veredito de filtragem de spam de email em massa.

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> **New-HostedContentFilterPolicy** e **Set-HostedContentFilterPolicy** contêm um parâmetro _ZapEnabled_ mais antigo, bem como parâmetros _PhishZapEnabled_ e _SpamZapEnabled_ mais novos. O parâmetro _ZapEnabled_ foi depreciado em fevereiro de 2020. Os parâmetros _PhishZapEnabled_ e _SpamZapEnabled_ herdavam os valores deles do parâmetro _ZapEnabled_. No entanto, se você usar os parâmetros _PhishZapEnabled_ e _SpamZapEnabled_ em um comando ou usar as configurações de **ZAP de spam** ou **ZAP de phishing** na política no Centro de Conformidade e Segurança, o valor do parâmetro _ZapEnabled_ será ignorado. Em outras palavras, não use o parâmetro _ZapEnabled_; em vez disso, use os parâmetros _PhishZapEnabled_ e _SpamZapEnabled_.

Para obter mais informações detalhadas de sintaxe e parâmetro, confira [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).

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

Para obter mais informações detalhadas de sintaxe e parâmetro, confira [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule).

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

Para obter mais informações detalhadas de sintaxe e parâmetro, confira [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).

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

Para obter mais informações detalhadas de sintaxe e parâmetro, confira [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule).

### <a name="use-powershell-to-modify-spam-filter-policies"></a>Usar o PowerShell para modificar políticas de filtro de spam

Além dos itens a seguir, as mesmas configurações estão disponíveis quando você modifica uma política de filtro de spam no Windows PowerShell, como ao criar a política conforme descrito anteriormente na seção [Etapa 1: usar o PowerShell para criar uma política de filtro de spam](#step-1-use-powershell-to-create-a-spam-filter-policy) deste tópico.

- A opção _MakeDefault_ que transforma a política especificada em política padrão (aplicada a todos, sempre com a **Menor** prioridade, e que pode ser excluída) só está disponível quando você modifica uma política de filtro de spam no PowerShell.

- Não é possível renomear uma política de filtro de spam (o cmdlet **Set-HostedContentFilterPolicy** não tem o parâmetro _Name_). Quando você renomeia uma política antispam no Centro de Conformidade e Segurança, só é possível renomear a _regra_ do filtro de spam.

Para modificar uma política de filtro de spam, use esta sintaxe:

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

Para obter mais informações detalhadas de sintaxe e parâmetro, confira [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).

### <a name="use-powershell-to-modify-spam-filter-rules"></a>Usar o PowerShell para modificar regras de filtro de spam

A única configuração que não está disponível quando você modifica uma regra de filtro de spam no PowerShell é o parâmetro _Enabled_, que permite criar uma regra desabilitada. Para habilitar ou desabilitar regras de filtro de spam existentes, confira a próxima seção.

Do contrário, nenhuma configuração adicional estará disponível quando você modificar a regra de filtro de spam no PowerShell. As mesmas configurações estão disponíveis quando você cria uma regra conforme descrito anteriormente na seção [Etapa 2: usar o PowerShell para criar uma regra de filtro de spam](#step-2-use-powershell-to-create-a-spam-filter-rule) deste tópico.

Para modificar uma regra de filtro de spam, use esta sintaxe:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

Este exemplo renomeia a regra de filtro de spam chamada `{Fabrikam Spam Filter}` que pode causar problemas no Centro de Conformidade e Segurança.

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

Para obter mais informações detalhadas de sintaxe e parâmetro, confira [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule).

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

Para obter informações detalhadas de sintaxe e parâmetro, confira [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule) e [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule).

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

Para obter informações detalhadas de sintaxe e parâmetro, confira [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy).

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

Para obter informações detalhadas de sintaxe e parâmetro, confira [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>Enviar uma mensagem do GTUBE para testar as configurações de política de spam

> [!NOTE]
> Essas etapas só funcionarão se a organização de email da qual você está enviando a mensagem do GTUBE não tiver verificação de spam de saída. Se ela tiver, a mensagem de teste não poderá ser enviada.

O GTUBE (teste genérico para email em massa não solicitado) é uma cadeia de caracteres de texto incluída em uma mensagem de texto para verificar as configurações antispam da sua organização. A mensagem do GTUBE é similar ao arquivo de texto do EICAR (Instituto Europeu para Pesquisa de Antivírus de Computador) em configurações de malware de teste.

Inclua o seguinte texto do GTUBE em uma mensagem de email em uma única linha, sem espaços ou quebras de linha:

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a>Listas de permissões/bloqueios

De vez em quando, os filtros perdem a mensagem ou nossos sistemas demoram algum tempo para se ajustar. Nesse caso, a política antispam tem uma lista de permissões e outra de bloqueios, disponíveis para substituir o veredicto atual. Essa opção deve ser usada com moderação, pois as listas podem se tornar temporariamente não gerenciáveis porque a pilha de filtragem deverá executar o que precisa ser feito.

> [!TIP]
> Podem haver situações nas quais a sua organização pode não concordar com o veredicto fornecido pelo serviço. Nesse caso, talvez você queira manter a Lista de permissões ou bloqueio permanente. No entanto, se você pretende colocar um domínio na Lista de permissões por longos períodos de tempo, deve informar ao remetente para verificar se o domínio está autenticado e configurar o DMARC para rejeitá-lo, caso não esteja.
