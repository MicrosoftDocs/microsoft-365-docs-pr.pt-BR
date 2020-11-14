---
title: Como verificar a integridade do serviço Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_ServiceHealthModern
- O365M_ServiceHealthModern
- O365E_ViewStatusServices
- O365E_ServiceHealthModern
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
- IWA160
ms.assetid: 932ad3ad-533c-418a-b938-6e44e8bc33b0
description: Veja o status de integridade dos serviços do Microsoft 365 antes de ligar para o suporte para ver se há uma interrupção ativa do serviço.
ms.openlocfilehash: b1819e455732d142c563f598433c410b0ae60882
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2020
ms.locfileid: "49072754"
---
# <a name="how-to-check-microsoft-365-service-health"></a>Como verificar a integridade do serviço Microsoft 365

[![Rótulo para informar que o centro de administração está mudando e você pode encontrar mais detalhes em aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview?view=o365-worldwide&preserve-view=true)

Você pode exibir a integridade de seus serviços da Microsoft, incluindo o Office na Web, o Yammer, o Microsoft Dynamics CRM e os serviços de nuvem de gerenciamento de dispositivo móvel, na página **integridade do serviço** no centro de [administração do Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339). Se tiver problemas com um serviço em nuvem, poderá verificar a integridade do serviço para determinar se é um problema conhecido com uma resolução em andamento, antes de chamar o suporte ou perder tempo na solução de problemas.

Se você não conseguir entrar no centro de administração, poderá usar a [página status do serviço](https://status.office365.com) para verificar se há problemas conhecidos, impedindo o login no locatário.  Inscreva-se para nos seguir em [@MSFT365status](https://twitter.com/MSFT365Status) no Twitter para ver informações sobre determinados eventos.

  
### <a name="how-to-check-service-health"></a>Como verificar a integridade do serviço

1. Vá para o centro de administração do Microsoft 365 em [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) e entre com uma conta de administrador.

    > [!NOTE]
    > As pessoas às quais a função de administrador global ou do serviço é atribuída podem visualizar a integridade do serviço. Para permitir que os administradores do Exchange, SharePoint e Skype for Business visualizem a integridade do serviço, eles também devem receber a função de administrador do serviço. Para obter mais informações sobre as funções que podem exibir a integridade do serviço, consulte [about admin Roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true#roles-available-in-the-microsoft-365-admin-center).
  
2. Se você não estiver usando o novo centro de administração, na **Home** Page, marque a opção **Experimente o novo centro de administração** alternar no canto superior direito.

3. Para exibir a integridade do serviço, no centro de administração, **Health** vá para  >  **integridade do serviço** de integridade ou selecione o cartão de **integridade do serviço** no **painel inicial**. O cartão de painel indica se há um problema de serviço ativo e links para a página de **integridade do serviço** detalhada.
  
4. Na página **integridade do serviço** , o estado de integridade de cada serviço de nuvem é mostrado em um formato de tabela.

   ![View of current issues in service health](../media/service-health-all-services.png)

A guia **todos os serviços** (o modo de exibição padrão) mostra todos os serviços e seu estado de integridade atual. Um ícone e a coluna **status** indicam o estado de cada serviço. 

Para filtrar o modo de exibição para serviços que estão experimentando um incidente, selecione a guia **incidentes** na parte superior da página. Selecionar a guia **avisos** mostrará apenas os serviços que atualmente têm um comunicado Postado. 

A guia **histórico** mostra o histórico de incidentes e avisos que foram resolvidos.

Se você estiver enfrentando um problema com um serviço do Microsoft 365 e não vê-lo listado na página **integridade do serviço** , fale conosco selecionando **relatar um problema** e preenchimento de forma curta. Examinaremos os dados relacionados e os relatórios de outras organizações para ver o grau de disseminação do problema e se ele se originou com nosso serviço. Se tiver feito isso, vamos adicioná-lo como um novo incidente ou comunicado na página **integridade do serviço** , onde você pode controlar a resolução. Se você não vê-lo aparece na lista em cerca de 30 minutos, considere o suporte de contato para resolver o problema.

Para personalizar a exibição dos serviços exibidos no painel, selecione **Preferences**  >  **modo de exibição personalizado** preferências e desmarque as caixas de seleção dos serviços que você deseja filtrar do modo de exibição do painel de integridade do serviço. Certifique-se de que a caixa de seleção está marcada para cada serviço que você deseja monitorar.    

Para inscrever-se para receber notificações por email de novos incidentes que afetam as alterações de locatário e de status **Preferences** de um incidente ativo, selecione  >  **emails** de preferências, clique em **enviar-me notificações do serviço Heath no email** e especifique:

- Até dois endereços de email.
- Se você deseja notificações para incidentes ou comunicados
- Os serviços para os quais você deseja a notificação

> [!NOTE]
> Cada administrador pode ter suas preferências definidas e o limite acima de dois endereços de email é por conta de administrador.

> [!TIP]
> Você também pode usar o [aplicativo de administração do Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=627216) em seu dispositivo móvel para exibir a integridade do serviço, que é uma ótima maneira de se manter atualizado com as notificações por push. 
  
### <a name="view-details-of-posted-service-health"></a>Exibir detalhes da integridade do serviço postado

No modo de exibição **todos os serviços** , selecionar o status do serviço abrirá um modo de exibição de Resumo de comunicados ou incidentes.
  
[![Uma captura de tela mostrando o comunicado ](../media/service-health-advisory.png) de serviço](../media/service-health-advisory.png#lightbox)

O resumo do aviso ou incidente fornece as seguintes informações:

- **Título** -um resumo do problema.
- **Service** -o nome do serviço afetado.
- **ID** -um identificador numérico para o problema.
- **Status** -como esse problema afeta o serviço.
- **Hora de início** – o horário em que o problema foi iniciado.
- **Última atualização** -a última vez que a mensagem de integridade do serviço foi atualizada. Publicamos mensagens frequentes para que você saiba o progresso que estamos fazendo na aplicação de uma solução.

Selecione o título do problema para ver a página detalhes do problema, que mostra mais informações sobre o problema, incluindo o [histórico](#history) de todas as mensagens postadas enquanto trabalhamos em uma solução.

![Uma captura de tela mostrando detalhes do problema](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a>Traduzir dados da integridade do serviço

Como as explicações de integridade do serviço são postadas em tempo real, elas não são traduzidas automaticamente para o seu idioma, e os detalhes de um evento de serviço estão apenas em inglês. Para traduzir a explicação, siga estas etapas:
  
1. Acesse [Tradutor](https://www.bing.com/translator/).

2. Na página **Integridade do Serviço** , selecione um incidente ou aviso. Em **Mostrar Detalhes** , copie o texto sobre o problema.

3. No Tradutor, cole o texto e escolha **Traduzir**.

### <a name="definitions"></a>Definições

Na maioria das vezes, os serviços serão exibidos como íntegros sem mais informações. Quando um serviço está com um problema, ele é identificado como um aviso ou um incidente e mostra um status atual.
  
> [!TIP]
> Os eventos de manutenção planejados não são exibidos na integridade do serviço. Você pode acompanhar os eventos de manutenção planejados atualizando-se com o **Centro de Mensagens**. Filtre para mensagens categorizadas como Preparar-se para a mudança para descobrir quando a mudança acontecerá, seu efeito e como se preparar para isso. Confira [o centro de mensagens no Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) para obter mais detalhes.
  
### <a name="incidents-and-advisories"></a>Incidentes e avisos

| Ícone | Descrição |
|:-----|:-----|
|![Information icon for advisory](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|Quando um serviço exibe um aviso, estamos cientes de um problema que está afetando alguns usuários, mas o serviço ainda está disponível. Em um aviso, muitas vezes há uma solução para o problema, e o problema pode ser intermitente ou ter alcance e impacto limitados no usuário.  <br/> |
|![Exclamation point icon for incident](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|Quando um serviço exibe um incidente ativo, esse é um problema crítico, e o serviço ou uma função principal do serviço está indisponível. Por exemplo, os usuários podem não conseguir enviar e receber emails, ou não é possível entrar. Os incidentes terão um impacto perceptível nos usuários. Quando há um incidente em andamento, fornecemos atualizações sobre a investigação, os esforços de atenuação e a confirmação de resolução no painel de Integridade do serviço.  <br/> |

### <a name="status-definitions"></a>Definições de status

| Status | Definição |
|:-----|:-----|
|**Investigando** | Estamos cientes de um possível problema e reunindo mais informações sobre o que está acontecendo e o escopo de impacto. |
|**Degradação do serviço** | Confirmamos que existe um problema que pode afetar o uso de um serviço ou recurso. Talvez você veja esse status se um serviço apresentar um desempenho mais lento do que o normal, se houver interrupções intermitentes ou se um recurso não estiver funcionando, por exemplo. |
|**Interrupção do serviço** | Você verá esse status se determinarmos que um problema afeta a capacidade dos usuários de acessar o serviço. Neste caso, a questão é significativa e pode ser reproduzida de forma consistente. |
|**Restaurando o serviço** | A causa do problema foi identificada, sabemos quais ações corretivas devem ser tomadas e estamos no processo de retomar o estado de integridade do serviço. |
|**Recuperação estendida** | Esse status indica que uma ação corretiva está em andamento para restaurar o serviço para a maioria dos usuários, mas levará algum tempo para alcançar todos os sistemas afetados. Você também poderá ver esse status se tivermos feito uma correção temporária para reduzir o impacto enquanto aguardamos para aplicar uma correção permanente. |
|**Investigação suspensa** | Se a nossa investigação detalhada de um problema potencial resultar em uma solicitação de informações adicionais de clientes para nos permitir investigar mais, você verá esse status. Se precisarmos de você para prosseguir, informaremos quais dados ou logs precisamos. |
|**Serviço restaurado** | Confirmamos que a ação corretiva solucionou o problema subjacente, e o serviço foi restaurado para um estado íntegro. Para descobrir o que deu errado, confira os detalhes do problema. |
|**Falso positivo** | Após uma investigação detalhada, confirmamos que o serviço está íntegro e funcionando conforme projetado. Nenhum impacto no serviço foi observado ou a causa do incidente se originou fora do serviço. |
|**Relatório de pós-incidente publicado** | Publicamos um relatório de incidente de postagem para um problema específico que inclui informações de causa raiz e próximas etapas para garantir que um problema semelhante não ocorra. |

### <a name="history"></a>Histórico

A integridade do serviço permite que você examine o status de integridade atual e visualize o histórico de quaisquer comunicados de serviço e incidentes que afetaram seu locatário nos últimos 30 dias. Para exibir a integridade passada de todos os serviços, selecione **Exibir histórico** na página detalhes do problema.
  
![Show link to health history](../media/service-health-view-history.png)
  
Uma lista de todas as mensagens de integridade de serviço postadas no cronograma selecionado é exibida, conforme mostrado abaixo:
  
![View service health history](../media/service-health-history.png)
  
Expanda qualquer linha para exibir mais detalhes sobre o problema.
  
Para obter mais informações sobre nosso compromisso com o tempo de atividade, consulte [operações transparentes do Microsoft 365](https://go.microsoft.com/fwlink/?linkid=848695).

## <a name="related-topics"></a>Tópicos relacionados

[Relatórios de atividades no centro](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 
 de administração do Microsoft 365 [Preferências do centro de mensagens](https://docs.microsoft.com/microsoft-365/admin/manage/message-center?view=o365-worldwide&preserve-view=true#preferences11)
