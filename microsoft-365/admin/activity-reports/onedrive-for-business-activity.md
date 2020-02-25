---
title: Relatórios do Microsoft 365 no centro de administração-atividade do OneDrive for Business
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- SPO_Content
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- ODB150
- ODB160
ms.assetid: 8bbe4bf8-221b-46d6-99a5-2fb3c8ef9353
description: Obter o relatório de uso do OneDrive para sua organização e conhecer a atividade de cada usuário do OneDrive, o número de arquivos compartilhados e o uso do armazenamento.
ms.openlocfilehash: 2c755a9a5cf2f2085ec02029387a884f38aecb53
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237200"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Relatórios do Microsoft 365 no centro de administração-atividade do OneDrive for Business

O painel de **relatórios** do Microsoft 365 mostra a visão geral das atividades em todos os produtos de sua organização. Ele permite a você detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md).
  
Por exemplo, você pode entender a atividade de cada usuário licenciado para uso do OneDrive examinando sua interação com os arquivos no OneDrive. Isso também ajuda você a entender o nível de colaboração atual examinando o número de arquivos compartilhados.
  
> [!NOTE]
> Algumas funcionalidades são introduzidas gradualmente. Isso significa que esse recurso pode ainda não estar disponível ou pode parecer diferente em relação ao que descrevemos nos artigos da Ajuda. Não se preocupe, ele aparecerá em breve! 
  
Se você quiser entender a quantidade de atividade que está ocorrendo em cada conta do OneDrive e o uso do armazenamento, poderá ver o [Relatório de uso do OneDrive](onedrive-for-business-usage.md).
  
> [!NOTE]
> Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou um administrador do Exchange, SharePoint ou Skype for Business para ver os relatórios. 
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Como posso obter o relatório de atividades do OneDrive?

1. No centro de administração do, vá para a página**Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.

    
2. Na lista suspensa **selecionar um relatório** , selecione **atividade**do **onedrive** \> .
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>Interpretar o relatório de atividades do OneDrive for Business

Você pode examinar a atividade do OneDrive for Business nos modos de exibição **Arquivos** e **Usuários**. 
  
![OneDrive Activity Report](../media/316b2a03-8e42-447c-aae8-080813eebe84.png)
  
|||
|:-----|:-----|
|1.  <br/> |O relatório **Atividade do OneDrive for Business** pode ser consultado sobre tendências dos últimos 7, 30, 90 ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela (7) mostrará dados de até 28 dias a partir da data atual (não a data em que o relatório foi gerado).  <br/> |
|2.  <br/> |Os dados em cada relatório normalmente cobrem até as últimas 24 a 48 horas. <br/>|
|3.  <br/> |O modo de exibição **Arquivos** ajuda você a entender o número exclusivo de usuários licenciados que executaram interações do arquivo em relação a qualquer conta do OneDrive.  <br/> |
|4.  <br/> |O modo de exibição **Usuários** ajuda você a entender a tendência no número de usuários ativos do OneDrive. Um usuário é considerado ativo quando executa uma atividade de arquivo (salvar, sincronizar, modificar ou compartilhar) dentro do período especificado.  <br/> Observação: uma atividade de arquivo pode ocorrer várias vezes para um único arquivo, mas só contará como um arquivo ativo. Por exemplo, você pode salvar e sincronizar o mesmo arquivo várias vezes durante um período especificado, mas isso contará somente como um arquivo ativo e um único arquivo sincronizado nos dados.           |
|5.  <br/> | No gráfico **Arquivos**, o eixo Y é a quantidade de arquivos exclusivos que um usuário salvou, sincronizou, modificou ou compartilhou.  <br/>  No gráfico **Usuários**, o eixo Y é o número de usuários exclusivos que executaram interações de arquivo (salvar, sincronizar, modificar ou compartilhar) em uma conta do OneDrive.  <br/>  O eixo X em todos os gráficos é o intervalo de datas selecionado para esse relatório específico.  <br/> |
|6.  <br/> |Você pode filtrar a série que vê no gráfico selecionando um item na legenda. Por exemplo, no gráfico **arquivos** , selecione **exibido ou editado** ou **sincronizado** para ver apenas as informações relacionadas a cada um. Ao alterar essa seleção, as informações da tabela não mudam.  <br/> |
|7.  <br/> | A tabela mostra o detalhamento dos dados no nível do usuário. Você pode adicionar ou remover colunas da tabela.   <br/>  **Username** é o nome de usuário do proprietário da conta do onedrive.  <br/> **Data da Última Atividade (UTC)** é a data mais recente de execução de uma atividade de arquivo na conta do OneDrive no intervalo de datas selecionado. Para ver a atividade que ocorreu em uma data específica, selecione a data diretamente no gráfico.  <br/> ![Selecionar uma data específica no gráfico](../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png)  <br/>  Isso filtrará a tabela para exibir os dados de atividade de arquivo somente para os usuários que realizaram a atividade nesse dia específico.  <br/> **Arquivos exibidos ou editados** é o número de arquivos carregados, baixados, modificados ou exibidos pelo usuário.  <br/> **Arquivos sincronizados** é a quantidade de arquivos que foram sincronizados de um dispositivo de usuário local para a conta do OneDrive.  <br/> **Arquivos compartilhados internamente** é o número de arquivos que foram compartilhados com usuários dentro da organização ou com usuários dentro de grupos (que podem incluir usuários externos).  <br/> **Arquivos compartilhados externamente** é a quantidade de arquivos que foram compartilhados com os usuários de fora da organização.  <br/> **Excluída** indica que a licença do usuário foi removida.  <br/> Observação: a atividade de um usuário excluído ainda será exibida em um relatório, contanto que ele ou ela tenha sido licenciado em algum momento durante o período de tempo selecionado. A coluna **Excluído** ajuda você a observar que o usuário pode não estar mais ativo, mas contribuiu com os dados no relatório.<br/>**Data de exclusão** é a data na qual a licença do usuário foi removida.  <br/> **Produto atribuído** são os produtos da Microsoft 365 que são licenciados para o usuário.  <br/>  Se as políticas da sua organização impedem você de exibir relatórios onde as informações do usuário são identificáveis, você pode alterar a configuração de privacidade de todos esses relatórios. Confira a seção **como ocultar detalhes de nível de usuário?** nos [relatórios de atividades no centro de administração do Microsoft 365](activity-reports.md).  <br/> |
|8.  <br/> |Selecione o ícone ![ **gerenciar colunas** gerenciar colunas](../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) para adicionar ou remover colunas do relatório.  <br/> |
|9.  <br/> |Você também pode exportar os dados do relatório para um arquivo. csv do Excel, selecionando o link de **exportação** . Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados.  <br/> |
|||
   

