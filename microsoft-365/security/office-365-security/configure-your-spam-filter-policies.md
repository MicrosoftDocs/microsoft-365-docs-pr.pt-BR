---
title: Configurar suas políticas de filtro de spam
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/05/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: As configurações básicas de filtro de spam incluem a seleção da ação a ser realizada nas mensagens identificadas como spam.
ms.openlocfilehash: a762f46d9d3834b9c7f9976da6f91ce4e043c206
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871897"
---
# <a name="configure-your-spam-filter-policies"></a>Configurar suas políticas de filtro de spam
As configurações de filtro de spam incluem a seleção da ação a ser realizada nas mensagens identificadas como spam. As configurações de política de filtro de spam são aplicadas apenas a mensagens de entrada e existem dois tipos:

  - Padrão: a política padrão do filtro de spam é usada para definir as configurações de filtro de spam de toda a empresa. Essa política não pode ser renomeada e está sempre ativa.

  - Personalizada: as políticas personalizadas de filtro de spam podem ser granulares e aplicadas a usuários, grupos ou domínios específicos na sua organização. As políticas personalizadas sempre têm precedência sobre a política padrão. Você pode alterar a ordem na qual as políticas personalizadas são executadas, alterando a prioridade de cada uma; no entanto, somente a política de prioridade mais alta (por exemplo, com número mais próximo a 0) será aplicada se várias políticas atenderem ao conjunto de critérios.

## <a name="what-you-must-know-before-you-begin"></a>O que você deve saber antes de começar

Tempo estimado para conclusão: 30 minutos
  
Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver quais são as permissões necessárias, confira a Entrada antispam, no tópico [Permissões de recursos no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions).

As configurações da política de filtro de spam estão todas no SCC (Centro de conformidade e segurança). Para obter mais informações, [Acesse o Centro de conformidade e segurança do Office 365](../../compliance/go-to-the-securitycompliance-center.md). A página de configurações de antispam está dentro da seção do SCC \> **Gerenciamento de ameaças** \> **Política** \> **Antispam**.

## <a name="access-and-create-spam-filter-policies"></a>Acessar e criar políticas de filtro de spam

Na página Configurações de antispam, as configurações padrão podem ser visualizadas na guia Padrão. Para alterar essas configurações, mude para a guia **Personalizado**. Você poderá ver e configurar algumas das configurações padrão na política padrão de filtro de spam.

Para habilitar mais configurações personalizadas ou adicionar políticas personalizadas, altere o seletor **Configurações personalizadas** para **Ligado** para habilitar as políticas personalizadas de filtro de spam. Você pode exibir as políticas personalizadas existentes expandindo-as aqui.

## <a name="configure-custom-spam-filter-policy-settings"></a>Configurar as definições de política personalizada de filtro de spam

1. Selecione e clique em **Editar política** se você estiver editando uma política; caso contrário, clique em **Criar uma política**

2. Você pode especificar um nome exclusivo para políticas personalizadas, mas não é possível renomear o padrão. Opcionalmente, você também pode especificar uma descrição mais detalhada para qualquer política.

3. Na seção **Ações em massa e spam**:

  - Selecione uma ação para os tipos de **Spam**, **Spam de alta confiança**, **Email de phishing de alta confiança** e **Email de phishing** e **Emails em massa**. Os valores disponíveis são: 

    - **Mover mensagem para a pasta Lixo Eletrônico:** envia a mensagem para a pasta Lixo Eletrônico dos destinatários especificados. Esta é a ação padrão para spam, spam de alta confiança e em massa.<br/><br/>

    > [!NOTE]
    > Para essa ação funcionar com as caixas de correio locais, é necessário configurar duas regras de fluxo de email do Exchange (também conhecido como regras de transporte) nos seus servidores locais para detectar cabeçalhos de spam adicionados pelo EOP. Para obter mais detalhes, confira como [Garantir que o spam seja direcionado para a pasta Lixo Eletrônico de cada usuário](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Esta etapa é fundamental para clientes autônomos do EOP (Proteção do Exchange Online).

    - **Adicionar cabeçalho X:** envia a mensagem para os destinatários especificados, mas adiciona o texto cabeçalho X ao cabeçalho da mensagem para identificá-la como spam. Usando esse texto como um identificador, opcionalmente, você pode criar regras da caixa de entrada ou usar um dispositivo downstream para agir na mensagem. O texto do cabeçalho X padrão é **Esta mensagem parece ser spam**.<br/>Você pode personalizar o texto cabeçalho X usando a caixa de entrada **Adicionar este texto cabeçalho X**. Se você personalizar o texto do cabeçalho X, esteja ciente das seguintes condições: 
    
      - Se você especificar somente o cabeçalho no formato \< *cabeçalho*  \>, quando não houver espaços no \<  *cabeçalho*  \>, os dois pontos serão colocados no texto personalizado, seguidos pelo texto padrão. Por exemplo, se você especificar "Este-é-o-meu-cabeçalho-personalizado", o texto do cabeçalho X aparecerá como "Este-é-o-meu-cabeçalho-personalizado: esta mensagem parece ser spam". 
        
      - Se você incluir espaços no texto de cabeçalho personalizado, ou se você adicionar os dois pontos você mesmo (como "X Este é meu cabeçalho personalizado" ou "X-Este-é-meu-cabeçalho-personalizado:"), o texto do cabeçalho X volta para o padrão como "X-Isso-é-Spam: esta mensagem parece ser spam".
    
      - Você não pode especificar o texto do cabeçalho no formato \< *cabeçalho*  \>:\<  *valor*  \>. Se fizer isso, os valores antes e depois dos dois pontos serão ignorados e o texto X-cabeçalho padrão aparecerá: "X-Isto-É-Spam: esta mensagem parece ser spam". 
      
      - Lembre-se de que os emails com esse cabeçalho X talvez ainda sejam movidos para a pasta Lixo eletrônico da caixa de correio devido a uma configuração de lixo eletrônico. Você pode alterar isso desabilitando esse recurso com Set-MailboxJunkEmailConfiguration.

    - **Preceder a linha do assunto com texto:** envia a mensagem para os destinatários pretendidos mas precede a linha do assunto com o texto especificado na caixa de entrada **Prefixar a linha do assunto com este texto**. Usando esse texto como um identificador, você pode, opcionalmente, criar regras para filtrar ou rotear as mensagens, conforme o necessário. 

    - **Redirecionar mensagem para endereço de email:** envia a mensagem para um endereço de email designado em vez de enviá-lo para os destinatários pretendidos. Especificar o endereço de "redirecionamento" na caixa de entrada **Redirecionar para este endereço de email**.

    - **Excluir mensagem:** exclui a mensagem inteira, incluindo todos os anexos. 
        
    - **Mensagem em quarentena:** envia a mensagem para a quarentena em vez de para os destinatários pretendidos. Esta é a ação padrão para phishing. Se você selecionar essa opção, na caixa de entrada **Manter spam por (dias)**, especifique a quantidade de dias durante os quais a mensagem de spam ficará em quarentena. (Ela será automaticamente excluída após o tempo decorrido. O valor padrão é de 30 dias, que é o valor máximo. O valor mínimo é 1 dia).<br/><br/>DICA: para obter informações sobre como os administradores podem gerenciar mensagens de email residentes na quarentena no EAC, confira [Quarentena](quarantine.md) e [Localizar e liberar mensagens em quarentena como um administrador](find-and-release-quarantined-messages-as-an-administrator.md). >  Para saber mais sobre como configurar mensagens de notificação de spam para os usuários, confira [Configurar notificações de spam do usuário final no EOP](configure-end-user-spam-notifications-in-eop.md) ou [Configurar notificações de spam do usuário final no Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md). 

  - Configure **Selecione o limite** para determinar como deseja tratar os emails em massa como spam, com base no BCL (Nível de reclamação em massa) da mensagem. Você pode escolher uma configuração de limite de 1 a 9, em que 1 indica a maior parte dos emails em massa como spam e 9 permite que a maior parte dos emails em massa sejam entregues. O serviço então executa a ação configurada; por exemplo, enviar a mensagem para a pasta Lixo Eletrônico do destinatário. Confira [Valores de nível de reclamação em massa](bulk-complaint-level-values.md) e [Qual é a diferença entre lixo eletrônico e email em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md) para obter mais detalhes. 

4. Na página **Propriedades de spam**, você pode definir as opções de Modo de teste para a política, configurando: 
    
      - **Nenhuma** Não tomar ação de modo de teste na mensagem. É o padrão. 
        
      - **Adicionar o texto de cabeçalho X de teste padrão** A seleção dessa opção envia a mensagem aos destinatários especificados, mas também adiciona um cabeçalho X especial à mensagem para identificá-la como uma correspondência de uma opção de filtragem de spam avançada específica. 
        
      - **Enviar uma mensagem de Cco para este endereço** A seleção dessa opção envia uma cópia oculta da mensagem ao endereço de email que você especificou na caixa de entrada. <br/><br/>Para obter mais informações sobre as opções de filtragem avançada de spam, incluindo descrições sobre cada opção e o texto do cabeçalho X que está associado a cada uma, confira [Opções de filtragem de spam avançadas](advanced-spam-filtering-asf-options.md).

5. Somente em casos de políticas personalizadas, clique no item do menu **Aplicar para** e, em seguida, crie uma regra baseada na condição para especificar os usuários, grupos, e domínios aos quais se aplica esta política. É possível criar várias condições, se elas forem únicas. 
    
      - Para selecionar usuários, selecione **O destinatário é**. Na caixa de diálogo subsequente, selecione um ou mais remetentes da sua empresa na lista de seletor de usuários e então clique em **adicionar**. Para adicionar remetentes que não estão na lista, digite os seus endereços de email e então clique em **Verificar nomes**. Nessa caixa, também é possível usar caracteres curinga para vários endereços de email (por exemplo: \*@ _domainname_). Ao finalizar suas seleções, clique em **ok** para retornar a tela principal. 
        
      - Para selecionar grupos, selecione **O destinatário é membro de**. Em seguida, na caixa de diálogo posterior, selecione ou especifique os grupos. Clique em **ok** para retornar à tela principal. 
        
      - Para selecionar domínios, selecione **O domínio do destinatário é**. Em seguida, na caixa de diálogo posterior, adicione os domínios. Clique em **ok** para retornar à tela principal. <br/><br/>Você pode criar exceções dentro da regra. Por exemplo, você pode filtrar mensagens de todos os domínios, exceto para um determinado domínio. Clique em **Adicionar exceção** e, em seguida, crie suas condições de exceção da mesma forma que criou as demais condições.<br/><br/>A aplicação de uma política de spam a um grupo tem suporte apenas para **Grupos de segurança habilitados para email**. 
  
6. Clique em **Salvar**. Um resumo das configurações de política aparecerá no painel direito.

A política padrão não pode ser desabilitada ou excluída e as políticas personalizadas sempre têm precedência sobre a política padrão. Nas políticas personalizadas, você pode marcar ou desmarcar as caixas de seleção na coluna **HABILITADO** para habilitá-las ou desabilitá-las. Por padrão, todas as políticas estão habilitadas. Para excluir uma política personalizada, selecione a política, clique no ícone ![Excluir ícone](../media/ITPro-EAC-DeleteIcon.gif) **Excluir** e depois confirme que você deseja excluir a política.

> [!TIP]
> Você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas clicando no ![Ícone de seta para cima](../media/ITPro-EAC-UpArrowIcon.gif) e ![Ícone de seta para baixo](../media/ITPro-EAC-DownArrowIcon.gif). A política que tem uma **PRIORIDADE** de **0** será executada primeiro, seguida por **1**, **2** e assim por diante. 
  
## <a name="use-remote-powershell-to-configure-spam-filter-policies"></a>Usar o PowerShell remoto para configurar políticas de filtro de spam

Você também pode configurar e aplicar políticas de filtro de conteúdo no PowerShell. Para saber como usar o Windows PowerShell para se conectar ao Exchange Online, confira o artigo [Conectar-se ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554). Para saber como usar o Windows PowerShell para se conectar à Proteção do Exchange Online, confira [Conectar-se ao PowerShell do Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=627290).
  
- [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterpolicy) Exibir suas configurações de filtro de spam. 
    
- [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy) Editar suas configurações de filtro de spam. 
    
- [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterpolicy) Criar uma nova política personalizada de filtro de spam. 
    
- [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterpolicy) Excluir uma política personalizada de filtro de spam. 
    
Para aplicar uma política personalizada de filtro de spam a usuários, grupos e/ou domínios, use o cmdlet do [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterrule) (para criar uma nova regra de filtragem que possa ser aplicada a políticas personalizadas) ou o cmdlet [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule) (para editar uma regra de filtro existente que possa ser aplicada a políticas personalizadas). Para habilitar ou desabilitar a regra aplicada à política, use o cmdlet [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedcontentfilterrule) ou o cmdlet do [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedcontentfilterrule). 
  
## <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para garantir que o spam esteja sendo adequadamente detectado e tratado, você pode enviar uma mensagem GTUBE por meio do serviço. Semelhante ao arquivo de teste de antivírus EICAR, o GTUBE oferece um teste pelo qual você pode verificar se o serviço está detectando spam de entrada. Uma mensagem GTUBE sempre deverá ser detectada como spam pelo filtro de spam, e as ações executadas na mensagem deverão corresponder às suas configurações.
  
Inclua o seguinte texto do GTUBE em uma mensagem de email em uma única linha, sem espaços ou quebras de linha:
  
```
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="fine-tuning-your-spam-filter-policy-to-prevent-false-positives-and-false-negatives"></a>Otimizar sua política de filtro de spam para evitar falsos positivos e falsos negativos

Você também pode habilitar as técnicas avançadas de filtragem de spam, caso queira adotar uma abordagem mais agressiva de filtragem de spam. Para configurações gerais de spam que se apliquem a toda a organização, consulte [Prevenir email falso positivo marcado como spam com uma lista segura ou outras técnicas](https://go.microsoft.com/fwlink/p/?LinkId=534224) ou [Bloquear spam de email com o filtro de spam do Office 365 para evitar problemas de falsos negativos](reduce-spam-email.md). Elas serão úteis se você tiver o controle de nível de administrador e quiser impedir falsos positivos ou falsos negativos.

## <a name="allowblock-lists"></a>Listas de permissões/bloqueios

De vez em quando, os filtros perdem a mensagem ou nossos sistemas demoram algum tempo para se ajustar. Nesse caso, a política antispam tem uma lista de permissões e outra de bloqueios, disponíveis para substituir o veredicto atual. Essa opção deve ser usada com moderação, pois as listas podem se tornar temporariamente não gerenciáveis porque a pilha de filtragem deverá executar o que precisa ser feito.

As listas de permissões e bloqueios são configuradas como parte de uma política antispam do cliente:

1. Na seção **Listas de permissões**, você pode especificar as entradas, como remetentes ou domínios, que sempre serão entregues à caixa de entrada. Os emails dessas entradas não são processados pelo filtro de spam. 
    
      - Adicione remetentes confiáveis à Lista de permissões de remetentes. Clique em **Editar**![Ícone Adicionar](../media/ITPro-EAC-AddIcon.gif) e, na caixa de diálogo de seleção, adicione os endereços dos remetentes que deseja permitir. Você pode separar várias entradas usando ponto-e-vírgula ou uma nova linha. Clique em **Salvar** para retornar à página **Listas de permissões**. 
        
      - Adicione domínios confiáveis à Lista de permissões de domínios. Clique em **Editar**![Ícone Adicionar](../media/ITPro-EAC-AddIcon.gif) e, na caixa de diálogo de seleção, adicione os domínios que deseja permitir. Você pode separar várias entradas usando ponto-e-vírgula ou uma nova linha. Clique em **Salvar** para retornar à página **Listas de permissões**. 

> [!CAUTION]
> Você não deve listar os domínios aceitos (domínios que você possui) ou domínios comuns, como Microsoft.com, office.com, etc. a uma Lista de permissões. Isso permite aos fraudadores enviar emails sem restrições para sua organização.

2. Na página **Listas de Bloqueios**, você pode especificar as entradas, como remetentes ou domínios, que sempre serão marcadas como spam. O serviço aplicará a ação de spam de alta confiança configurada nos emails que corresponderem a essas entradas. 
    
      - Adicione remetentes indesejados à lista de Bloqueios de remetentes. Clique em **Editar**![Ícone Adicionar](../media/ITPro-EAC-AddIcon.gif) e, na caixa de diálogo de seleção, adicione os endereços dos remetentes que deseja bloquear. Você pode separar várias entradas usando ponto-e-vírgula ou uma nova linha. Clique em **Salvar** para retornar à página **Listas de bloqueios**. 
        
      - Adicione domínios indesejados à lista de Bloqueio de domínios. Clique em **Editar**![Ícone Adicionar](../media/ITPro-EAC-AddIcon.gif) e, na caixa de diálogo de seleção, adicione os domínios que deseja bloquear. Você pode separar várias entradas usando ponto-e-vírgula ou uma nova linha. Clique em **Salvar** para retornar à página **Listas de bloqueios**.

> [!TIP]
>  Podem haver situações nas quais a sua organização pode não concordar com o veredicto fornecido pelo serviço. Nesse caso, talvez você queira manter a Lista de permissões ou bloqueio permanente. No entanto, se você pretende colocar um domínio na Lista de permissões por longos períodos de tempo, deve informar ao remetente para verificar se o domínio está autenticado e configurar o DMARC para rejeitá-lo, caso não esteja.

## <a name="for-more-information"></a>Para obter mais informações
<a name="sectionSection6"> </a>

[Configurando seu domínio para DMARC](use-dmarc-to-validate-email.md)
  
[Quarentena](quarantine.md)
  
[Impedir falsos positivos marcados como spam usando uma lista confiável ou outras técnicas](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[Bloquear spam de email com o filtro de spam do Office 365 para evitar problemas de falsos negativos](https://go.microsoft.com/fwlink/p/?LinkId=534225)

[Níveis de confiança de spam](spam-confidence-levels.md)
  

