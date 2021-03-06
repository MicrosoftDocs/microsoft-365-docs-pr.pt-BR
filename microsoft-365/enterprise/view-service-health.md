---
title: Como verificar a saúde do serviço do Microsoft 365
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
description: Exibir o status de saúde dos serviços Microsoft 365 antes de chamar o suporte para ver se há uma interrupção ativa do serviço.
ms.openlocfilehash: 95ab260b4950d261eed1288b8fdf1f59883ff15f
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300400"
---
# <a name="how-to-check-microsoft-365-service-health"></a>Como verificar a saúde do serviço do Microsoft 365

[![Rótulo para informar que o centro de administração está mudando e você pode encontrar mais detalhes em aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)

Você pode exibir a saúde do seu serviços Microsoft, incluindo Office na Web, Yammer, Microsoft Dynamics CRM e serviços de nuvem  de gerenciamento de dispositivo móvel, na página Saúde do serviço no [Centro de administração do Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339). Se tiver problemas com um serviço em nuvem, poderá verificar a integridade do serviço para determinar se é um problema conhecido com uma resolução em andamento, antes de chamar o suporte ou perder tempo na solução de problemas.

Se você não conseguir entrar no centro de administração, poderá usar a página [de status](https://status.office365.com) do serviço para verificar se há problemas conhecidos que impedem que você faça logon em seu locatário.  Inscreva-se também para nos [acompanhar](https://twitter.com/MSFT365Status) @MSFT365status no Twitter para ver informações sobre determinados eventos.

## <a name="how-to-check-service-health"></a>Como verificar a integridade do serviço

1. Vá para o Centro de administração do Microsoft 365 [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) em , e entre com uma conta de administrador.

    > [!NOTE]
    > As pessoas que são atribuídas à função de administrador global ou de suporte ao serviço podem exibir a saúde do serviço. Para permitir que os administradores do Exchange, SharePoint e Skype for Business visualizem a integridade do serviço, eles também devem receber a função de administrador do serviço. Para obter mais informações sobre funções que podem exibir a saúde do serviço, consulte [Sobre funções de administrador](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles).

2. Para exibir a saúde do serviço, no centro de administração, acesse Health Service health , ou selecione o cartão de saúde do serviço  >  no **painel 1.**  O cartão de painel indica se há um problema de serviço ativo e links para a página de saúde **do Serviço** detalhada.

3. Na página **Saúde do** serviço, o estado de saúde de cada serviço de nuvem é mostrado em um formato de tabela.

   ![View of current issues in service health](../media/service-health-all-services.png)

A **guia Todos os** serviços (o modo de exibição padrão) mostra todos os serviços, seu estado de saúde atual e quaisquer incidentes ou avisos ativos. Um ícone e status na coluna **Saúde** indicam o estado de cada serviço.

Se houver um incidente ativo ou um aviso para um serviço, eles serão listados diretamente sob o nome do serviço em uma tabela aninhada. Você pode fechar a tabela aninhada para ocultar os incidentes ou avisos nesta exibição clicando no ícone chevron à esquerda do nome do serviço.   

Para filtrar seu exibição para mostrar apenas todos os incidentes ativos, selecione a guia **Incidentes** na parte superior da página. Selecionar a **guia** Avisos mostrará apenas todos os avisos ativos postados.

A **guia Histórico** mostra todos os incidentes e avisos que foram resolvidos nos últimos sete ou 30 dias.

Se você estiver enfrentando um problema com um serviço de Microsoft 365 e não  o vir listado na página de saúde do serviço, conte-nos sobre ele selecionando Relatar um problema **e** concluindo o formulário curto. Vamos ver os dados e relatórios relacionados de outras organizações para ver a generalização do problema e se ele se originou com nosso serviço. Se tiver feito isso, vamos adicioná-lo como  um novo incidente ou aviso na página de saúde do Serviço, onde você pode acompanhar sua resolução. A **página Problemas Relatados** mostrará todos os problemas relatados pelo locatário a partir deste formulário e do status.

Para personalizar sua exibição de quais serviços são mostrados no painel, selecione **Preferências** Exibição personalizada e des limpar as caixas de seleção dos serviços que você deseja filtrar para fora do seu painel de saúde  >  do serviço. Verifique se a caixa de seleção está selecionada para cada serviço que você deseja monitorar.

Para se inscrever nas notificações por email de novos incidentes que afetam o locatário e as alterações de status de um incidente ativo, selecione **Preferências** Email , clique em  >   **Enviar-me** notificações de pagões de serviço no email e especifique:

- Até dois endereços de email.
- Se você deseja notificações para incidentes ou avisos
- Os serviços para os quais você deseja notificação

Você também pode assinar notificações por email para eventos individuais em vez de todos os eventos de um serviço. Para fazer isso, selecione o problema ativo para o qual você deseja receber atualizações de notificação de email, selecione **Gerenciar** notificações para esse problema e especifique: 
- Até dois endereços de email.

> [!NOTE]
> Cada administrador pode ter suas Preferências definidas e o limite acima de dois endereços de email é por conta de administrador.

> [!TIP]
> Você também pode usar o [aplicativo Administração Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=627216) em seu dispositivo móvel para exibir a saúde do serviço, que é uma ótima maneira de se manter atualizado com notificações por push.

### <a name="view-details-of-posted-service-health"></a>Exibir detalhes da integridade do serviço postado

Na exibição **Todos** os serviços, selecione o título do problema para ver a página de detalhes do problema, que mostra mais informações sobre o problema, incluindo um feed de todas as mensagens postadas enquanto trabalhamos em uma solução. 

[![Uma captura de tela mostrando a consultoria de serviço ](../media/service-health-advisory.png)](../media/service-health-advisory.png#lightbox)

O resumo do aviso ou incidente fornece as seguintes informações:

- **Título** - Um resumo do problema.
- **ID** - Um identificador numérico para o problema.
- **Serviço** - O nome do serviço afetado.
- **Última atualização** - A última vez em que a mensagem de saúde do serviço foi atualizada.
- **Tempo estimado de início** - O tempo estimado quando o problema começou.
- **Status** - Como esse problema afeta o serviço.
- **Impacto do** usuário - Uma breve descrição do impacto que esse problema tem no usuário final.
- **Todas as Atualizações** - Postemos mensagens frequentes para que você saiba o progresso que estamos fazendo na aplicação de uma solução.

![Uma captura de tela mostrando detalhes do problema](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a>Traduzir dados da integridade do serviço

Usamos a tradução automática para exibir automaticamente mensagens em seu idioma preferencial. Leia [As postagens da Central de Mensagens](/microsoft-365/admin/manage/language-translation-for-message-center-posts) para obter mais informações sobre como definir seu idioma.

### <a name="definitions"></a>Definições

Na maioria das vezes, os serviços aparecerão como saudáveis sem mais informações. Quando um serviço está com um problema, ele é identificado como um aviso ou um incidente e mostra um status atual.

> [!TIP]
> Os eventos de manutenção planejados não são exibidos na integridade do serviço. Você pode acompanhar os eventos de manutenção planejados atualizando-se com o **Centro de Mensagens**. Filtre para mensagens categorizadas como Preparar-se para a mudança para descobrir quando a mudança acontecerá, seu efeito e como se preparar para isso. Consulte [Central de mensagens em Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) para obter mais detalhes.

### <a name="incidents-and-advisories"></a>Incidentes e avisos

| Icon | Descrição |
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
|**Falso positivo** | Após uma investigação detalhada, confirmamos que o serviço está saudável e funcionando conforme projetado. Nenhum impacto no serviço foi observado ou a causa do incidente originado fora do serviço. |
|**Relatório pós-incidente publicado** | Publicamos um Relatório de Incidentes Post para um problema específico que inclui informações de causa raiz e as próximas etapas para garantir que um problema semelhante não se recidiva. |

### <a name="message-post-types"></a>Tipos de postagem de mensagens

| Tipo | Definição |
|:-----|:-----|
|**Atualização Rápida** | Atualizações incrementais curtas e frequentes para incidentes de impacto geral, disponíveis para todos os clientes. |
|**Detalhes adicionais** | Essas postagens adicionais fornecerão detalhes técnicos e de resolução mais abrangentes para oferecer mais visibilidade sobre o tratamento de incidentes. Isso está disponível para locatários que atendem aos mesmos requisitos descritos para Exchange Online [monitoramento,](/microsoft-365/enterprise/microsoft-365-exchange-monitoring?view=o365-worldwide#requirements) |

### <a name="history"></a>Histórico

A saúde do serviço permite que você veja seu status de saúde atual e ex veja o histórico de quaisquer avisos de serviço e incidentes que afetaram seu locatário nos últimos 30 dias. Para exibir a saúde passada de todos os serviços, selecione **Histórico.**

Para obter mais informações sobre nosso compromisso com o tempo de atividade, consulte [Operações transparentes do Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity).

## <a name="related-topics"></a>Tópicos relacionados

[Relatórios de atividades no Centro de administração do Microsoft 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

[Preferências do Centro de Mensagens](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)

[Como verificar a Windows de versão no Centro de administração](/windows/deployment/update/check-release-health)
