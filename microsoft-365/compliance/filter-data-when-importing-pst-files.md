---
title: Filtrar dados ao importar arquivos PST
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
ms.custom: seo-marvel-apr2020
description: Saiba como filtrar dados usando o recurso de importação inteligente no Microsoft 365 de importação quando você importar arquivos PST para Microsoft 365.
ms.openlocfilehash: fc89467e3ea9c0af86ec6b9ef6a9d7d61079e116
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730565"
---
# <a name="filter-data-when-importing-pst-files"></a>Filtrar dados ao importar arquivos PST

Use o novo recurso importação inteligente no serviço de importação Microsoft 365 para filtrar os itens em arquivos PST que realmente são importados para as caixas de correio de destino. Veja como funciona:
  
- Depois de criar e enviar um trabalho de importação PST, os arquivos PST são carregados em uma área de armazenamento do Azure na nuvem da Microsoft.
  
- Microsoft 365 analisa os dados nos arquivos PST, de forma segura e segura, identificando a idade dos itens de caixa de correio e os diferentes tipos de mensagem incluídos nos arquivos PST.
  
- Quando a análise é concluída e os dados estão prontos para importação, você tem a opção de importar todos os dados nos arquivos PST como está ou cortar os dados importados definindo filtros que controlam quais dados são importados. Por exemplo, você pode optar por:
  
  - Importe apenas itens de uma determinada idade.
  
  - Importar tipos de mensagem selecionados.
  
  - Exclua mensagens enviadas ou recebidas por pessoas específicas.
  
- Depois de configurar as configurações de filtro, Microsoft 365 importa somente os dados que atendam aos critérios de filtragem para as caixas de correio de destino especificadas no trabalho de importação.
  
O gráfico a seguir mostra o processo de Importação Inteligente e realça as tarefas executadas e as tarefas executadas por Office 365.
  
![O processo de Importação Inteligente no Office 365](../media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="create-a-pst-import-job"></a>Criar um trabalho de importação PST

- As etapas neste tópico pressupuem que você criou um trabalho de importação PST no serviço Office 365 Import usando o carregamento de rede ou o envio de unidade. Para obter instruções passo a passo, consulte um dos seguintes tópicos:
    
  - [Usar o carregamento de rede para importar arquivos PST para o Office 365](use-network-upload-to-import-pst-files.md)
    
  - [Usar o envio de unidade para importar os arquivos PST para o Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- Depois de criar um trabalho de importação usando o carregamento de rede, o & status do trabalho de importação na página Importar no Centro de Conformidade e Segurança é definido como Análise em **andamento,** o que significa que o Microsoft 365 está analisando os dados nos arquivos PST que você carregou. Clique **em Atualizar** atualização para atualizar o status do trabalho de ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) importação. 
    
- Para trabalhos de importação de envio de unidade, os dados serão analisados pelo Microsoft 365 depois que a equipe do datacenter da Microsoft receber seu disco rígido e carregar os arquivos PST para a área de armazenamento do Azure para sua organização.
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a>Filtrar dados que são importados para caixas de correio

Depois de criar um trabalho de importação PST, siga estas etapas para filtrar os dados antes de importá-los para Office 365.
  
1. Vá para <https://compliance.microsoft.com> e entre usando as credenciais de uma conta de administrador em sua organização.
    
2. No painel esquerdo do Centro de Conformidade do Microsoft 365, clique em **controle de informações** \> **Importar**.
    
    Os trabalhos de importação para sua organização estão listados na **guia Importar.** O **valor concluído** análise na coluna **Status** indica os trabalhos de importação que foram analisados pelo Microsoft 365 e estão prontos para importação.
    
    ![O status completo da análise indica Microsoft 365 analisar os dados em arquivos PST](../media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. Selecione o trabalho de importação que você deseja concluir e clique em **Importar para Office 365**.
  
    Uma página com submenu é exibida com informações sobre os arquivos PST e outras informações sobre o trabalho de importação.

4. Clique **em Importar para Office 365**.
    
    A página **Filtrar seus dados** é exibida. Ele contém informações sobre os dados nos arquivos PST para o trabalho de importação, incluindo informações sobre a idade dos dados. 
    
    ![A página Filtrar seus dados mostra informações de dados dos arquivos PST para o trabalho de importação](../media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. Com base em se você deseja ou não cortar os dados importados para Microsoft 365, em Deseja filtrar seus **dados?**, faça um dos seguintes:
  
    a. Clique **em Sim, quero filtre-o** antes de importar para cortar os dados que você importa e clique em **Próximo.**
  
    A **página Importar dados Office 365 página** é exibida com informações detalhadas sobre dados da análise que Microsoft 365 realizada. 
  
    ![Microsoft 365 exibe informações detalhadas de sua análise dos arquivos PST](../media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    O gráfico nesta página mostra a quantidade de dados que serão importados. As informações sobre cada tipo de mensagem encontrada nos arquivos PST são exibidas no gráfico. Você pode passar o cursor sobre cada barra para exibir informações específicas sobre esse tipo de mensagem. Também há uma listada com valores de idade diferentes com base na análise dos arquivos PST. Quando você seleciona uma idade na listada, o gráfico é atualizado para mostrar quantos dados serão importados para a idade selecionada. 
  
    b. Para configurar filtros de adição para reduzir a quantidade de dados importados, clique **em Mais opções de filtragem.**
  
    ![Configurar os filtros na página Mais opções para cortar os dados importados](../media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    Você pode configurar esses filtros:
  
      - **Idade** - Selecione uma idade para que somente os itens mais novos do que a idade especificada serão importados. Consulte a [seção Mais informações](#more-information) para obter uma descrição sobre como Microsoft 365 determina os buckets de idade para o filtro **Idade.** 
  
      - **Tipo** - Esta seção mostra todos os tipos de mensagem encontrados nos arquivos PST para o trabalho de importação. Você pode desmarcar uma caixa ao lado de um tipo de mensagem que deseja excluir. Não é possível excluir o outro tipo de mensagem. Consulte a [seção Mais informações](#more-information) para obter uma lista de itens de caixa de correio incluídos na categoria Other.
  
      - **Usuários** - Você pode excluir mensagens enviadas ou recebidas por pessoas específicas. Para excluir pessoas que aparecem no campo De: para: ou no  campo Cc: de mensagens, clique em Excluir usuários ao lado desse tipo de destinatário. Digite o endereço de email (endereço SMTP) da pessoa, clique em Adicionar novo ícone para adicioná-los à lista de usuários excluídos para esse tipo de destinatário e clique em Salvar para salvar a lista de usuários  ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) excluídos.  
  
        > [!NOTE]
        > Microsoft 365 não mostra informações de dados resultantes da configuração do **filtro Pessoas.** No entanto, se você definir esse filtro para excluir mensagens enviadas ou recebidas por pessoas específicas, essas mensagens serão excluídas durante o processo de importação real. 
  
    c. Clique **em Aplicar** na página Mais opções de **filtragem** para salvar suas configurações de filtro. 
  
    Os insights de dados na página **Importar** dados para Office 365 são atualizados com base nas configurações do filtro, incluindo a quantidade total de dados que serão importados com base nas configurações do filtro. Um resumo das configurações do filtro também é mostrado. Você pode clicar **em Editar** ao lado de um filtro para alterar a configuração, se necessário. 
  
    ![As informações de dados são atualizadas com base nas configurações do filtro](../media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    d. Clique em **Avançar**.
  
    Uma página de status é exibida mostrando as configurações do filtro. Novamente, você pode editar qualquer uma das configurações de filtro.
  
    e. Clique **em Importar dados** para iniciar a importação. A quantidade total de dados que serão importados é exibida. 
  
    Ou
  
    a. Clique **em Não, quero importar tudo para** importar todos os dados nos arquivos PST para Office 365 e clique em **Próximo**.
  
    b. Na página **Importar dados para Office 365,** clique em **Importar dados** para iniciar a importação. A quantidade total de dados que serão importados é exibida. 
  
6. Na guia **Importar,** clique em **Atualizar** ![ atualização ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) . O status do trabalho de importação é exibido na coluna **Status.**
  
7. Clique na importação do trabalho para exibir informações mais detalhadas, como o status de cada arquivo PST e as configurações de filtro que você configurou.

## <a name="more-information"></a>Mais informações

- Como Microsoft 365 determina os incrementos para o filtro de idade? Quando Microsoft 365 analisa um arquivo PST, ele analisa o carimbo de hora enviado ou recebido de cada item (se um item tiver um carimbo de data/hora enviado e recebido, a data mais antiga será selecionada). Em seguida, Microsoft 365 o valor do ano para esse data/hora e compara-o com a data atual para determinar a idade do item. Essas idades são então usadas como os valores na listada para o filtro **Idade.** Por exemplo, se um arquivo PST tiver mensagens de 2016, 2015 e 2014, os valores no filtro **Idade** seriam **1** ano, **2** anos e **3 anos.**
  
- A tabela a seguir lista os tipos de  mensagem incluídos  na outra categoria no filtro Tipo na página Mais opções de sobrevoo (consulte Etapa 5b no procedimento anterior).  Atualmente, você não pode excluir itens na categoria "Outros" ao importar PSTs para Office 365. 
  
    |**ID da classe de mensagens**|**Itens de caixa de correio que usam essa classe de mensagem**|
    |:-----|:-----|
    |IPM. Atividade  <br/> |Entradas de Diário  <br/> |
    |IPM.Document  <br/> |Documentos e arquivos (não anexados a uma mensagem de email)  <br/> |
    |IPM. Arquivo  <br/> |(mesmo que IPM.Document)  <br/> |
    |IPM. Note.IMC.Notification  <br/> |Relatórios enviados pelo Internet Mail Conexão, que é o Exchange Server gateway para a Internet  <br/> |
    |IPM. Observação.Microsoft.Fax  <br/> |Mensagens de fax  <br/> |
    |IPM. Observação.Rules.Oof.Template.Microsoft  <br/> |Mensagens autoreletivas fora do escritório  <br/> |
    |IPM. Observação.Rules.ReplyTemplate.Microsoft  <br/> |Respostas enviadas por uma regra de caixa de entrada  <br/> |
    |IPM. OLE. Classe  <br/> |Exceções para uma série recorrente  <br/> |
    |IPM. Recall.Report  <br/> |Relatórios de cancelamento de mensagens  <br/> |
    |IPM. Remote  <br/> |Mensagens de email remotas  <br/> |
    |IPM. Relatório  <br/> |Relatórios de status do item  <br/> |
