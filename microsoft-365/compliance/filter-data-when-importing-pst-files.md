---
title: Filtrar dados ao importar arquivos PST
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
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
description: Saiba como filtrar dados usando o recurso de importação inteligente no serviço de importação do Office 365 ao importar arquivos PST para o Office 365.
ms.openlocfilehash: d511c1277104a27076116fafcb4b71bc851baaca
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817720"
---
# <a name="filter-data-when-importing-pst-files"></a>Filtrar dados ao importar arquivos PST

Use o novo recurso importação inteligente no serviço de importação do Office 365 para filtrar os itens em arquivos PST que realmente são importados para as caixas de correio de destino. Veja como funciona:
  
- Depois de criar e enviar um trabalho de importação de PST, os arquivos PST são carregados para uma área de armazenamento do Azure na nuvem da Microsoft.
    
- O Microsoft 365 analisa os dados nos arquivos PST, de maneira segura, identificando a idade dos itens de caixa de correio e os diferentes tipos de mensagens incluídos nos arquivos PST.
    
- Quando a análise estiver concluída e os dados estão prontos para importação, você tem a opção de importar todos os dados nos arquivos PST como estão ou cortar os dados que são importados definindo filtros que controlam quais dados serão importados. Por exemplo, você pode escolher:
    
  - Importar somente itens de uma determinada idade.
    
  - Importar tipos de mensagem selecionados.
    
  - Excluir mensagens enviadas ou recebidas por pessoas específicas.
    
- Depois de definir as configurações de filtro, o Microsoft 365 importa somente os dados que atendam aos critérios de filtragem para as caixas de correio de destino especificadas no trabalho de importação.
    
O gráfico a seguir mostra o processo de Importação Inteligente e destaca as tarefas realizadas e as tarefas executadas pelo Office 365.
  
![O processo de Importação Inteligente no Office 365](../media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="create-a-pst-import-job"></a>Criar um trabalho de importação de PST

- As etapas neste tópico presumem que você tenha criado um trabalho de importação de PST no serviço de importação do Office 365 usando o carregamento de rede ou o envio de unidade. Para obter instruções passo a passo, consulte um dos seguintes tópicos:
    
  - [Usar o carregamento de rede para importar arquivos PST para o Office 365](use-network-upload-to-import-pst-files.md)
    
  - [Usar o envio de unidade para importar os arquivos PST para o Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- Depois de criar um trabalho de importação usando o carregamento de rede, o status do trabalho de importação na página Importar no Centro de Conformidade & e Segurança é definido como Análise em **andamento,** o que significa que o Microsoft 365 está analisando os dados nos arquivos PST que você carregou. Clique **em Atualizar** para atualizar o status do trabalho de ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) importação. 
    
- Para trabalhos de importação de envio de unidade, os dados serão analisados pelo Microsoft 365 depois que a equipe do datacenter da Microsoft receber seu disco rígido e carregar os arquivos PST na área de armazenamento do Azure para sua organização.
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a>Filtrar dados que são importados para caixas de correio

Depois de criar um trabalho de importação de PST, siga estas etapas para filtrar os dados antes de importá-los para o Office 365.
  
1. Vá para [https://protection.office.com/](https://protection.office.com/) e entre usando as credenciais de uma conta de administrador em sua organização. 
    
2. Clique **em Governança de Informações** \> **Importar** Arquivos \> **PST de Importação.**
    
    Os trabalhos de importação para sua organização estão listados na página **Importar arquivos PST.** Observe que o **valor concluído** da Análise na coluna **Status** indica os trabalhos de importação que foram analisados pelo Microsoft 365 e estão prontos para importação. 
    
    ![O status completo da análise indica que o Microsoft 365 analisou os dados em arquivos PST](../media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. Clique **em Pronto para importar para o Office 365** para o trabalho de importação que você deseja concluir. 
    
    Uma página com submenu é exibida com informações sobre os arquivos PST e outras informações sobre o trabalho de importação.
    
4. Clique **em Importar para o Office 365.**
    
    A página **Filtrar seus dados** é exibida. Ele contém informações de dados sobre os dados nos arquivos PST para o trabalho de importação, incluindo informações sobre a idade dos dados. 
    
    ![A página Filtrar seus dados mostra informações de dados dos arquivos PST para o trabalho de importação](../media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. Com base em se você deseja ou não cortar os dados que são importados para o Microsoft 365, em Você deseja filtrar seus **dados?**, faça um dos seguintes:
    
    a. Click **Yes, I want to filter it before importing** to trim the data that you import, and then click **Next**.
    
    A **página Importar dados para o Office 365** é exibida com informações de dados detalhadas da análise que o Microsoft 365 realizou. 
    
    ![O Microsoft 365 exibe informações de dados detalhadas de sua análise dos arquivos PST](../media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    O gráfico nesta página mostra a quantidade de dados que serão importados. As informações sobre cada tipo de mensagem encontrada nos arquivos PST são exibidas no gráfico. Você pode passar o cursor sobre cada barra para exibir informações específicas sobre esse tipo de mensagem. Há também uma lista drop-down com valores de idade diferentes com base na análise dos arquivos PST. Quando você seleciona uma idade na lista drop-down, o gráfico é atualizado para mostrar a quantos dados serão importados para a idade selecionada. 
    
    b. Para configurar filtros de adição para reduzir a quantidade de dados importados, clique em **Mais opções de filtragem.**
    
    ![Configurar os filtros na página Mais opções para cortar os dados importados](../media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    Você pode configurar estes filtros:
    
      - **Idade** - Selecione uma idade para que somente os itens mais novos do que a idade especificada sejam importados. Confira a [seção Mais informações](#more-information) para obter uma descrição sobre como o Microsoft 365 determina os buckets de idade para o filtro **de** idade. 
    
      - **Tipo** - Esta seção mostra todos os tipos de mensagem encontrados nos arquivos PST para o trabalho de importação. Você pode desmarcar uma caixa ao lado de um tipo de mensagem que deseja excluir. Observe que você não pode excluir o tipo de mensagem Other. Consulte a [seção Mais informações](#more-information) para obter uma lista de itens de caixa de correio incluídos na categoria Outros. 
    
      - **Usuários** - Você pode excluir mensagens enviadas ou recebidas por pessoas específicas. Para excluir as pessoas que aparecem no campo De: , no campo  Para: ou no campo Cc: das mensagens, clique em Excluir usuários ao lado desse tipo de destinatário. Digite o endereço de email (endereço SMTP) da pessoa, clique no ícone Adicionar Novo para adicioná-lo à lista de usuários excluídos desse tipo de destinatário e clique em Salvar para salvar a lista de usuários  ![ excluídos. ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)  
    
        > [!NOTE]
        > O Microsoft 365 não mostra informações de dados resultantes da configuração do **filtro Pessoas.** No entanto, se você definir esse filtro para excluir mensagens enviadas ou recebidas por pessoas específicas, essas mensagens serão excluídas durante o processo de importação real. 
  
    c. Clique **em Aplicar** na página de **menus "Mais opções** de filtragem" para salvar as configurações de filtro. 
    
    As informações de dados na página Importar dados para o **Office 365** são atualizadas com base em suas configurações de filtro, incluindo a quantidade total de dados que serão importados com base nas configurações de filtro. Observe que um resumo das configurações de filtro também é mostrado. Você pode clicar **em Editar** ao lado de um filtro para alterar a configuração, se necessário. 
    
    ![As informações de dados são atualizadas com base em suas configurações de filtro](../media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    d. Clique em **Avançar**.
    
    Uma página de status é exibida mostrando as configurações de filtro. Novamente, você pode editar qualquer uma das configurações de filtro.
    
    e. Clique **em Importar dados** para iniciar a importação. Observe que a quantidade total de dados que serão importados é exibida. 
    
    Ou
    
    a. Click **No, I want to import everything** to import all data in the PST files to Office 365, and then click **Next**.
    
    b. Na página **Importar dados para o Office 365,** clique em Importar **dados** para iniciar a importação. Observe que a quantidade total de dados que serão importados é exibida. 
    
6. Na página **Importar arquivos PST,** clique em  ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) Atualizar. O status do trabalho de importação é exibido na **coluna Status.** 
    
7. Clique na importação do trabalho para exibir informações mais detalhadas, como o status de cada arquivo PST e as configurações de filtro que você definiu.

  
## <a name="more-information"></a>Mais informações

- Como o Microsoft 365 determina os incrementos do filtro de idade? Quando o Microsoft 365 analisa um arquivo PST, ele analisa o carimbo de data/hora enviado ou recebido de cada item (se um item tiver um carimbo de data/hora enviado e recebido, a data mais antiga será selecionada). Em seguida, o Microsoft 365 analisa o valor do ano para esse timestamp e o compara com a data atual para determinar a idade do item. Essas idades são, então, usadas como os valores na lista de lista lista para o filtro **Idade.** Por exemplo, se um arquivo PST tiver mensagens de 2016, 2015 e  2014, os valores no filtro idade seriam **1 ano,** **2** anos e **3 anos.**
    
- A tabela a seguir lista os  tipos de  mensagem incluídos na categoria Outros no filtro Tipo na página Mais opções do **menu** out (consulte a Etapa 5b do procedimento anterior). Atualmente, você não pode excluir itens na categoria "Outros" ao importar PSTs para o Office 365. 
    
    |**ID da classe de mensagens**|**Itens de caixa de correio que usam essa classe de mensagem**|
    |:-----|:-----|
    |IPM. Atividade  <br/> |Entradas de Diário  <br/> |
    |IPM.Document  <br/> |Documentos e arquivos (não anexados a uma mensagem de email)  <br/> |
    |IPM. Arquivo  <br/> |(o mesmo que IPM.Document)  <br/> |
    |IPM. Note.IMC.Notification  <br/> |Relatórios enviados pelo Internet Mail Connect, que é o gateway do Exchange Server para a Internet  <br/> |
    |IPM. Note.Microsoft.Fax  <br/> |Mensagens de fax  <br/> |
    |IPM. Note.Rules.Oof.Template.Microsoft  <br/> |Mensagens de resposta automática de fora do escritório  <br/> |
    |IPM. Note.Rules.ReplyTemplate.Microsoft  <br/> |Respostas enviadas por uma regra de caixa de entrada  <br/> |
    |IPM. OLE. Classe  <br/> |Exceções para uma série recorrente  <br/> |
    |IPM. Recall.Report  <br/> |Relatórios de cancelamento de mensagens  <br/> |
    |IPM. Remoto  <br/> |Mensagens de email remotas  <br/> |
    |IPM. Relatório  <br/> |Relatórios de status do item  <br/> |
