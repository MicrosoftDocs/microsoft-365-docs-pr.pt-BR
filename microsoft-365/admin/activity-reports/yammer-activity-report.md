---
title: Relatórios do Microsoft 365 no centro de administração - Relatório de atividades do Yammer
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a
description: Obter o relatório de Atividades do Yammer e saber mais sobre o número de usuários que usam o Yammer para postar, como ou ler uma mensagem.
ms.openlocfilehash: 2bf02c0599f999b0eebb52d119096567bb09508b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387460"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-activity-report"></a>Relatórios do Microsoft 365 no centro de administração - Relatório de atividades do Yammer

Como administrador do Microsoft 365, o painel **Relatórios** mostra dados sobre o uso dos produtos em sua organização. Confira os [relatórios de atividades no centro de administração.](activity-reports.md) Com o **Relatório de atividades do Yammer**, você vai entender o nível de interação da sua organização com o Yammer examinando o número de usuários exclusivos usando o Yammer para postar, curtir ou ler uma mensagem e a quantidade de atividade gerada em toda a organização. 
  
> [!NOTE]
> Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou um administrador do Exchange, SharePoint, Teams Service, Teams Communications ou Skype for Business para ver os relatórios. 
 
## <a name="how-to-get-to-the-yammer-activity-report"></a>Como acessar o relatório de atividade do Yammer

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.

    
2. No **drop-down Selecionar** um relatório, selecione **Atividade do Yammer.** \> 
  
## <a name="interpret-the-yammer-activity-report"></a>Interpretar o relatório de atividades do Yammer

Você pode observar a atividade do Yammer do usuário examinando os gráficos Atividade e Usuários.
  
![Relatório de atividades do Yammer](../../media/92e8b2c6-166a-4154-9824-3fb6bbedf0db.JPG)
  
O relatório de atividade contém as informações a seguir.
  
- Use as guias de dia para exibir o relatório **Atividade do Yammer** sobre tendências dos últimos 7, 30, 90 ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela mostrará dados por até 28 dias a partir da data atual (e não a data em que o relatório foi gerado). 
    
- Cada relatório tem uma data de geração. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas.
    
- O gráfico **Atividade** permite que você entenda a tendência da quantidade de atividade do Yammer ocorrendo em sua organização. Você pode entender a divisão de mensagens postadas, lidas ou curtidas. 
    
    ![Exibição de atividade no relatório de atividades do Yammer](../../media/76983516-2c5f-43a1-a5e3-c414e9f17638.JPG)
  
  - No gráfico **Atividade**, o eixo Y é a contagem de atividades de mensagens postadas, lidas ou curtidas. 
    
- Você pode ver o gráfico **Usuário** para entender a tendência da quantidade de usuários exclusivos que estão gerando as atividades do Yammer. Você pode examinar a tendência de usuários postando, lendo ou curtindo mensagens do Yammer. 
    
    ![Exibição dos usuários no relatório de atividades do Yammer](../../media/b1098162-7b79-430f-bfe4-9d3957d56885.JPG)
  
  - No gráfico de atividades **Usuários**, o eixo Y é o usuário postando, lendo ou curtindo mensagens do Yammer. 
    
  - O eixo X em ambos os gráficos é o intervalo de datas selecionado para esse relatório específico.
    
- Você pode filtrar a série que vê no gráfico selecionando um item na legenda. Por exemplo, no gráfico **Atividade,** selecione **Postado** **,** Lido ou Curtido para ver apenas as informações relacionadas a cada um deles.  
    
    ![Opções postadas, lidas e curtidas](../../media/8b832afc-415c-409b-816f-cb02b7a71e69.png)
  
    Ao alterar essa seleção, as informações da tabela não mudam.
    
- A tabela sob o gráfico mostra um detalhamento das atividades do Yammer no nível de cada usuário.
    
    Você pode usar o menu para filtrar e classificar os dados.
    
    ![Opções de menu para relatórios do Yammer](../../media/9d32240c-f1ff-400b-9c4e-a21b48651530.JPG)
  
    Você também pode adicionar e remover colunas. As colunas disponíveis são:
    
  - **Nome de usuário** é o endereço de email do usuário. Você pode exibir o endereço de email real ou tornar este campo anônimo. 
    
    Esta grade mostra os usuários que se registraram no Yammer usando a conta do Microsoft 365 ou que fizeram logor na rede usando o logor único.
    
  - **Nome para exibição** é o nome completo do usuário. Você pode exibir o endereço de email real ou tornar este campo anônimo. 
    
  - **Estado do usuário** é um dos três valores: Ativados, excluídos ou suspensos. 
    
    Esses relatórios mostram os dados de usuários ativos, suspensos e excluídos. Eles não refletem os usuários pendentes, pois os usuários pendentes não podem publicar, ler ou curtir uma mensagem.
    
  - **Data de alteração de estado (UTC)** é a data em que o estado do usuário foi modificado no Yammer. 
    
  - **Última data de atividade (UTC)** refere-se à última data em que o usuário publicou, leu ou curtiu uma mensagem. 
    
  - **Postados** é o número de mensagens que o usuário postou durante o período especificado. 
    
  - **Lidos** é o número de conversas que o usuário leu durante o período especificado. 
    
  - **Curtidos** é o número de mensagens que o usuário leu durante o período especificado. 
    
  - **Produto atribuído são** os produtos atribuídos a esse usuário. 
    
    Se as políticas da organização impedem a exibição de relatórios em que as informações do usuário podem ser identificadas, você pode alterar as configurações de privacidade para todos esses relatórios. Confira a seção **Como faço para ocultar detalhes no nível do usuário?** Nos relatórios de atividades no centro de administração do Microsoft [365.](activity-reports.md)
    
- Você também pode exportar os dados do relatório para um arquivo .csv do Excel, selecionando o link **Exportar.** Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados. 
    
## <a name="what-data-is-in-these-reports"></a>Que dados fazem parte desses relatórios?

- **Todos os clientes** esses relatórios agregam dados entre todos os clientes, inclusive os que usam o Yammer em um navegador ou em um aplicativo do Android ou iOS. 
    
- **Nenhum dado de rede externa** dados de rede externa não estão incluídos nesses relatórios. 
    
- **Redes ativadas** Esses relatórios mostram dados para a rede do Yammer que faz parte da sua assinatura do Microsoft 365. O gráfico agrega o uso de todos os usuários que se conectaram à rede do Yammer, independentemente de eles usarem o Microsoft 365 ou o Yammer para entrar. 
    

