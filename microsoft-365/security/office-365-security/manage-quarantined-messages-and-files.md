---
title: Gerenciar arquivos e mensagens em quarentena como um administrador no Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: 'Como administrador, você pode exibir, liberar e relatar mensagens em quarentena falsas positivas no Office 365. Você pode configurar políticas para que o Office 365 Filtre mensagens e as envie para quarentena por vários motivos: porque elas foram identificadas como spam, em massa, phishing, malware ou porque corresponderam a uma regra de fluxo de emails. '
ms.openlocfilehash: 229c2fa859b537c366a02cb27d1e9a71cb9aa6b2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598968"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator-in-office-365"></a>Gerenciar arquivos e mensagens em quarentena como um administrador no Office 365

Como administrador, você pode exibir, liberar e excluir mensagens em quarentena e relatar mensagens em quarentena falsas positivas no Office 365. Você também pode exibir, baixar e excluir arquivos em quarentena capturados pela proteção avançada contra ameaças (ATP) para o SharePoint Online, OneDrive for Business e Microsoft Teams. Você pode configurar políticas para que o Office 365 Filtre mensagens e as envie para quarentena por vários motivos: porque elas foram identificadas como spam, email em massa, emails de phishing, contendo malware ou porque corresponderam a uma regra de fluxo de emails.

Por padrão, o Office 365 envia mensagens de phishing e mensagens contendo malware diretamente para a quarentena. Outras mensagens filtradas são enviadas para a pasta lixo eletrônico dos usuários, a menos que você configure uma política para enviá-las à quarentena.

Você deve ter permissões de administrador global (GA) no Office 365 ou ser um membro de um ou mais grupos de funções do centro de conformidade de & de segurança, para trabalhar com mensagens em quarentena ou arquivos em quarentena. Consulte [permissões no centro de conformidade & segurança do Office 365](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center) para obter mais informações.

## <a name="what-permissions-are-needed-to-access-administrator-quarantine"></a>Quais permissões são necessárias para acessar a quarentena do administrador?

As permissões para gerenciar a quarentena são controladas por associação nos grupos de funções do *centro de conformidade de & de segurança* (especificamente, a função de **quarentena** ). Para obter mais informações sobre funções e grupos de funções no centro de conformidade & segurança, consulte [permissões no centro de conformidade & segurança do Office 365](permissions-in-the-security-and-compliance-center.md).

Os grupos de funções de conformidade de & de segurança que dão permissões para gerenciar a quarentena por padrão são:

- **Gerenciamento de organização** (administradores globais)

- **Administrador de quarentena**

- **Administrador de segurança**

## <a name="view-your-organizations-quarantined-messages"></a>Exibir as mensagens em quarentena da sua organização

1. Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global (ou funções apropriadas de segurança & central de conformidade) na sua organização do Office 365, entre no Office 365 e [vá para o centro de segurança e conformidade](../../compliance/go-to-the-securitycompliance-center.md).

2. Na lista à esquerda, expanda **Gerenciamento de ameaças**, escolha **revisão**e, em seguida, escolha **quarentena**.

    > [!TIP]
    > Para ir diretamente para a página **quarentena** no centro de conformidade de & de segurança, use esta URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)

    Por padrão, o centro de conformidade & segurança exibe todas as mensagens de email em quarentena como spam. As mensagens são classificadas da mais recente à mais antiga, de acordo com a **Data** de recebimento da mensagem. **Remetente**, **Assunto**, e a data de vencimento (em **expiras** ) também são exibidos para cada mensagem. Para classificar um campo, clique no cabeçalho da coluna correspondente. clique no cabeçalho de uma coluna novamente para inverter a ordem da classificação. 

3. Você pode exibir uma lista de todas as mensagens em quarentena ou pode reduzir o conjunto de resultados por filtragem. Nosso sistema permite realizar operações em massa com até 100 itens, portanto a filtragem também pode ajudar a reduzir o conjunto de resultados, se você tiver mais do que essa quantidade de itens. Você pode filtrar mensagens rapidamente por um único motivo de quarentena escolhendo uma opção do filtro na parte superior da página. As opções são:

   - Email identificado como spam

   - Email colocado em quarentena porque correspondeu a uma política definida por uma regra de fluxo de emails (também conhecida como regra de transporte)

   - Email identificado como email em massa

   - Email identificado como email de phishing

   - Email colocado em quarentena porque contém malware

Além disso, como administrador, você pode optar por filtrar todas as mensagens de sua organização ou apenas as mensagens enviadas a você. Os usuários finais só podem exibir e trabalhar com mensagens enviadas para eles.

Você também pode filtrar seus resultados para encontrar mensagens específicas. Para obter dicas, consulte [filtrar resultados e localizar arquivos e mensagens em quarentena](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) neste artigo.

Após localizar uma mensagem em quarentena específica, clique na mensagem para exibir detalhes sobre ela e execute ações, como liberar a mensagem para a caixa de correio de alguém.

## <a name="view-your-organizations-quarantined-files"></a>Exibir os arquivos em quarentena de sua organização

1. Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global (ou funções apropriadas de segurança & central de conformidade) na sua organização do Office 365, entre no Office 365 e [vá para o centro de segurança e conformidade](../../compliance/go-to-the-securitycompliance-center.md).

2. No lado esquerdo, expanda **Gerenciamento de Ameaças**, escolha **Revisão** e escolha **Quarentena**.

   > [!TIP]
   > Para ir diretamente para a página **quarentena** no centro de conformidade de & de segurança, use esta URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)

3. Por padrão, a página exibe mensagens de email em quarentena. Para exibir os arquivos em quarentena, defina os filtros na parte superior da página para mostrar os **arquivos**em quarentena devido a **malware**. Você deve ter permissões de administrador no Office 365 para trabalhar com arquivos em quarentena.

4. Os arquivos são classificados do mais recente para o mais antigo com base na data em que o arquivo foi colocado em quarentena. O **usuário** que modificou o arquivo pela última vez, o **serviço** no qual o arquivo foi postado, o **nome do arquivo**, o **local**, o **tamanho do arquivo**e a data de expiração ( **expira**) também estão listados para cada arquivo. Você pode classificar em um campo clicando em um cabeçalho; clique em um cabeçalho de coluna uma segunda vez para reverter a ordem de classificação.

Você pode exibir uma lista de todos os arquivos em quarentena ou pode pesquisar arquivos específicos por filtragem. Assim como as mensagens, você só pode realizar operações em massa em até 100 itens. Atualmente, o centro de conformidade & segurança permite que você visualize e gerencie arquivos que estão em quarentena porque foram identificados como contendo malware. Para obter dicas, consulte [filtrar resultados e localizar arquivos e mensagens em quarentena](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) neste artigo.

## <a name="to-filter-results-and-find-quarantined-messages-and-files"></a>Para filtrar resultados e localizar arquivos e mensagens em quarentena
<a name="BKMK_AdvSearch"> </a>

Dependendo das suas configurações, pode haver muito de arquivos e mensagens em quarentena. Para localizar uma mensagem ou um arquivo específico ou um conjunto de mensagens ou arquivos, você pode filtrar itens em quarentena com base em uma variedade de informações adicionais.

1. Na página **quarentena** , verifique se a linha superior dos filtros está definida para exibir mensagens ou arquivos conforme apropriado:

   - Para procurar arquivos, defina os filtros para mostrar **arquivos** em quarentena devido a **malware**.

     Para arquivos em quarentena, a página exibe todos os arquivos em quarentena, não apenas os seus, independentemente do que você deseja que seja mostrado.

   - Para pesquisar mensagens em quarentena, defina filtros para mostrar **todos** ou **apenas o meu** **email**. Para o último filtro, escolha o tipo de mensagem em quarentena que você está procurando. Você pode pesquisar por mensagens em quarentena que foram identificadas como **spam**, para mensagens que correspondam a uma regra de fluxo de emails (**regra de transporte**), emails **em massa** , emails de **phishing** ou emails que contenham **malware**.

2. Em **classificar resultados por**, escolha o filtro ou filtros que você deseja usar para Pesquisar nas listas suspensas. As opções variam de acordo com o fato de você estar pesquisando arquivos ou mensagens. Não há suporte para caracteres curinga nos campos de pesquisa no momento.

   Para arquivos e mensagens, você pode optar por filtrar pela data em que a mensagem ou o arquivo foi enviado para a quarentena. É possível especificar a data ou o intervalo de datas, inclusive o horário. Você também pode filtrar os resultados da pesquisa pela data de expiração na qual o arquivo ou a mensagem será excluído da quarentena ou você pode usar uma combinação de filtros. Para pesquisar por data de expiração, escolha **filtro avançado**. Em **expirar**, você pode selecionar mensagens que serão excluídas da quarentena nas próximas 24 horas ( **hoje**), nas próximas 48 horas ( **próximos 2 dias**), na próxima semana (próximos **7 dias**) ou você pode selecionar um intervalo de tempo personalizado.

   Para mensagens, você tem as seguintes opções adicionais:

   - **ID da mensagem**: Use esta para identificar uma mensagem específica quando você souber a ID da mensagem.

     Por exemplo, se uma mensagem específica é enviada por, ou destinada a, um usuário em sua organização, mas ela nunca chega ao seu destino, você pode procurar a mensagem, utilizando um recurso de rastreamento de mensagens.(consulte [Rastreamento de mensagens no Centro de Conformidade e Segurança](message-trace-scc.md)). Se você descobrir que a mensagem foi enviada para a quarentena, talvez porque correspondeu a uma regra de fluxo de emails ou tenha sido identificada como spam, você pode facilmente localizar essa mensagem em quarentena, especificando sua ID de mensagem. Certifique-se de incluir a cadeia de ID de mensagem completa. Isso pode incluir colchetes angulares\<(\>), por exemplo:

     `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`

   - **Endereço de email do remetente**: escolha essa opção para filtrar por um único endereço de email de remetente.

   - **Endereço de email do destinatário**: escolha essa opção para filtrar por um único endereço de email de destinatário.

   - **Assunto**: insira o assunto do endereço de email que você deseja localizar. Como a pesquisa curinga não é suportada, você deve usar o assunto inteiro da mensagem para que a pesquisa retorne a mensagem nos resultados. A pesquisa não diferencia maiúsculas de minúsculas.

## <a name="view-details-about-quarantined-messages-and-files"></a>Exibir detalhes sobre mensagens e arquivos em quarentena

Ao selecionar um item exibido na lista de quarentena, você verá um resumo de suas propriedades no painel de **detalhes** no lado direito do centro de conformidade do & de segurança.

### <a name="details-displayed-for-quarantined-messages"></a>Detalhes exibidos para mensagens em quarentena

- **ID de Mensagem**: identificador exclusivo da mensagem.

- **Endereço do Remetente**: a pessoa que enviou a mensagem.

- **Recebido**: data e hora em que a mensagem foi recebida.

- **Subject**: o texto da linha de assunto da mensagem.

- **Tipo**: mostra se uma mensagem foi identificada como **spam**, **em massa**, **Phish**, corresponde a uma regra de fluxo de emails (**regra de transporte**) ou foi identificada como contendo **malware**.

- **Expira**: a data e a hora em que a mensagem será automaticamente excluída da quarentena.

- **Liberação para**: todos os endereços de email (se houver) para os quais a mensagem foi liberada.

- **Ainda não foi liberado para**: todos os endereços de email (se houver) para os quais a mensagem ainda não foi liberada.

### <a name="details-displayed-for-quarantined-files"></a>Detalhes exibidos para arquivos em quarentena

- **Nome do arquivo** O nome do arquivo em quarentena.

- **Caminho do site** URL que define o local do arquivo no Office 365.

- **Data/hora detectada** A data e a hora em que o arquivo foi colocado em quarentena.

- **Expira** A data em que a mensagem será excluída da quarentena.

- **Detectado por** O método usado para detectar o malware no arquivo. Isso pode ser a ATP (proteção avançada contra ameaças) ou o mecanismo antimalware da Microsoft.

- **Lançado** Descreve se o arquivo foi ou não liberado.

- **Nome do malware** Família e nome do malware detectado no arquivo.

- **ID do documento** Um identificador exclusivo para o documento.

- **Tamanho do arquivo** O tamanho do arquivo em KB.

- **Organização** A identificação exclusiva da sua organização no Office 365.

- **Modificado por** A conta corporativa ou de estudante do usuário que modificou o arquivo pela última vez.

- **Tamanho do arquivo** O tamanho do arquivo em KB.

- **Hash SHA256** O hash do arquivo. Você pode usá-lo para procurar outros repositórios de reputação que você pode ter ou investigar onde senão o arquivo pode estar em seu ambiente.

## <a name="managing-messages-and-files-in-quarantine"></a>Gerenciando mensagens e arquivos em quarentena
<a name="BKMK_ManageQuarantinedItem"> </a>

Após selecionar uma mensagem ou grupo de mensagens, você tem várias opções para gerenciar mensagens em quarentena.

- Não tomar nenhuma medida. Se optar por não fazer nada, o Office 365 excluirá automaticamente a mensagem, após a data de expiração. Por padrão, spam, massa, malware, phishing e mensagens em quarentena porque corresponderam a uma regra de fluxo de emails são mantidas em quarentena por 30 dias. Quando o Office 365 exclui uma mensagem da quarentena, não é possível recuperá-la. Se desejar, você pode alterar o período de retenção para mensagens em quarentena Configurando a configuração **reter spam para (dias)** em suas políticas antispam. Para obter mais informações, consulte [configuração do período de retenção de quarentena](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) neste artigo.

- **Exibir cabeçalho da mensagem**: escolha este link para ver o texto do cabeçalho da mensagem. Para analisar o cabeçalho em camadas, copie o texto do cabeçalho da mensagem para a área de transferência e escolha **analisador de cabeçalho de mensagem da Microsoft** para ir para o analisador de conectividade remota (clique com o botão direito do mouse e escolha **abrir em uma nova guia** se não quiser deixar o Office 365 para concluir essa tarefa). Cole o cabeçalho da mensagem na página na seção analisador de cabeçalho de mensagem e escolha **analisar cabeçalhos**:

- **Visualizar mensagem**: permite exibir versões brutas ou em HTML do texto do corpo da mensagem. No modo de exibição de HTML.

- **Baixar mensagem** ou **baixar arquivo**: escolha esta opção para baixar uma cópia da mensagem ou arquivo para o dispositivo local. Você precisará confirmar se entendeu os riscos associados ao download de itens da quarentena antes que você possa fazer isso. As mensagens são salvas no formato. eml em uma pasta que você especificar. Os arquivos em quarentena são salvos em seu formato original.

- **Excluir**: se quiser, você pode excluir imediatamente um item em quarentena (ou conjunto de itens) em vez de esperar pela data de expiração definida pelo Office 365. Para excluir uma mensagem ou arquivo, na lista quarentena, selecione o item e, em seguida, escolha **excluir**. Para excluir vários itens de uma vez, marque a caixa de seleção à esquerda dos itens na lista quarentena e, em seguida, na página **ações em massa** exibida, escolha **excluir mensagens selecionadas** ou **Excluir arquivos selecionados**.

- **Versão**: Libere um item em quarentena (ou um conjunto de itens) e informe os itens como em quarentena de forma falsa (falsos positivos) à Microsoft.

  Para liberar e relatar uma única mensagem ou arquivo, na lista quarentena, selecione o item, escolha **liberar arquivo** ou **liberar mensagem**. Na próxima página, verifique se **as mensagens de relatório para a Microsoft para** análise ou **arquivos de relatório para a Microsoft para análise** estão selecionadas.

  Para liberar vários itens de uma vez, marque a caixa de seleção à esquerda dos itens na lista quarentena e, em seguida, na página **ações em massa** exibida, escolha **liberar arquivos** ou **liberar mensagens**. Na próxima página, verifique se **as mensagens de relatório para a Microsoft para** análise ou **arquivos de relatório para a Microsoft para análise** estão selecionadas.

Quando você estiver liberando mensagens, esteja ciente do seguinte:

- Quando você executa uma versão em massa de várias mensagens ao mesmo tempo, as mensagens são liberadas para todos os destinatários originalmente identificados. Se você só quiser liberar mensagens somente para destinatários específicos, precisará liberar as mensagens uma de cada vez e identificar os destinatários individualmente.

- Uma mensagem não pode ser liberada mais de uma vez para o mesmo destinatário.

- Quando você estiver liberando uma mensagem para mais de um destinatário, somente os destinatários que não receberam a mensagem aparecerão na lista de possíveis destinatários.

- Quando você optar por relatar falsos positivos, se a mensagem ou as mensagens liberadas forem colocadas em quarentena como spam, em massa, phishing ou como contendo malware, a mensagem também será relatada à equipe de análise de spam da Microsoft. A equipe avaliará e analisará a mensagem e, dependendo dos resultados da análise, as regras de filtro de conteúdo de spam de todo o serviço podem ser ajustadas para permitir a mensagem.

## <a name="setting-the-quarantine-retention-period"></a>Definindo o período de retenção de quarentena
<a name="BKMK_ModQuarantineTime"> </a>

Você pode configurar por quanto tempo as mensagens e os arquivos permanecerão em quarentena antes de expirarem. Por padrão, os itens em quarentena são mantidos por 30 dias. Você define essa configuração para cada política que criar. Você também pode modificar o valor da política padrão, conforme descrito neste artigo.

### <a name="to-modify-the-quarantine-retention-period-for-the-default-spam-filter-policy-in-the-security-and-compliance-center"></a>Para modificar o período de retenção de quarentena para a política de filtro de spam padrão no centro de segurança e conformidade

1. Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global (ou funções apropriadas de segurança & central de conformidade) na sua organização do Office 365, entre no Office 365 e [vá para o centro de segurança e conformidade](../../compliance/go-to-the-securitycompliance-center.md).

2. À esquerda, expanda **Gerenciamento de ameaças**, escolha **política**e, em seguida, escolha **anti-spam**.

    > [!TIP]
    > Para ir diretamente para a página **antispam** no centro de conformidade & segurança, use esta URL: >[https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)

3. Expanda a linha **padrão da política de filtro de spam (AlwaysOn)** .

4. Escolha **Editar política**. As configurações da política de filtro de spam padrão aparecem em uma nova página.

5. Expanda **spam e ações em massa**.

6. Em **quarentena**, na caixa de texto **reter spam por (dias)** , insira a quantidade de tempo que você deseja que o Office 365 retenha mensagens e arquivos em quarentena. O padrão é 30 dias. Este também é o máximo.

7. Selecione **Salvar**.
