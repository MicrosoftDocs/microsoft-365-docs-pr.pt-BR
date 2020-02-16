---
title: Políticas de gerenciamento de risco do Insider (versão prévia)
description: Saiba mais sobre as políticas de gerenciamento de risco do insider no Microsoft 365
keywords: Microsoft 365, gerenciamento de risco do Insider, gerenciamento de riscos, conformidade
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: ac029959470d92fff9c0c5e942cd667f659e307d
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072818"
---
# <a name="insider-risk-management-policies-preview"></a>Políticas de gerenciamento de risco do Insider (versão prévia)

As políticas de gerenciamento de risco do insider determinam quais funcionários estão no escopo e quais tipos de indicadores de risco estão configurados para alertas. Você pode criar rapidamente uma política que se aplica a todos os usuários em sua organização ou definir usuários individuais ou grupos para gerenciamento em uma política. As políticas dão suporte a prioridades de conteúdo para concentrar as condições de política em várias ou em Microsoft Teams, sites do SharePoint, tipos de confidencialidade de dados e rótulos de dados. Usando modelos, eles incluem indicadores de risco específicos e quanto peso são atribuídos dentro de uma política, determinando efetivamente o peso de cada gatilho de alerta na política. Políticas o Windows permite que você defina o intervalo de tempo para aplicar a política às atividades de alerta e é usado para determinar a duração da política após a ativação. O limite máximo de políticas é de cinco políticas ativas ao mesmo tempo. No entanto, é possível configurar políticas adicionais e ativar e desativar políticas, conforme necessário.

## <a name="policy-dashboard"></a>Painel de políticas

O **painel de políticas** permite ver rapidamente as políticas em sua organização e o status atual dos alertas associados a cada política.

- **Nome da política**: o nome atribuído à política no assistente de política.
- **Alertas ativos**: o número de alertas ativos para cada política.
- **Alertas confirmados**: o número total de alertas que resultaram em casos da política nos últimos 365 dias.
- **Ações executadas em alertas**: o número total de alertas que foram confirmados ou descartados pelos últimos 365 dias.
- **Eficácia da política**: a porcentagem determinada pelo total de alertas confirmados dividido pelo total de ações realizadas em alertas (que é a soma dos alertas que foram confirmados ou ignorados no último ano).
- **Ativo**: o status da ocorrência, *Sim* ou *não*.

![Painel de política de gerenciamento de risco do insider](../media/insider-risk-policy-dashboard.png)

## <a name="policy-templates"></a>Modelos de política

Os modelos de gerenciamento de risco do insider são condições de política predefinidas que definem os tipos de indicadores de risco monitorados por uma política. Cada política deve ter um modelo atribuído no assistente de criação de política antes que a política seja criada. Ao criar uma nova política de risco de insider, você escolherá um dos modelos a seguir.

### <a name="departing-employee-data-theft"></a>Como a parte do roubo de dados do funcionário

Quando os funcionários saem da sua organização, há indicadores de risco específicos geralmente associados ao roubo de dados por parte dos funcionários. Este modelo de política prioriza esses indicadores e focaliza a detecção e os alertas nessa área de risco. O roubo de dados para os funcionários de parte pode incluir o download de arquivos do SharePoint Online, a cópia de arquivos para dispositivos portáteis, como unidades USB, impressão de arquivos e cópia de dados para serviços de armazenamento e mensagens na nuvem pessoal próximo à demissão de emprego e datas de término. Este modelo prioriza os indicadores de risco relacionados a essas atividades e como eles se correlacionam com o status de emprego do funcionário.

>[!IMPORTANT]
>Ao usar esse modelo, você deve configurar um conector de RH da Microsoft 365 para importar periodicamente informações de data de demissão e de término para os funcionários de sua organização. Consulte o tópico [importar dados com o conector de RH](import-hr-data.md) para obter orientações passo a passo para configurar o Microsoft 365 HR Connector para sua organização.

### <a name="data-leaks"></a>Vazamentos de dados

A proteção de dados e a prevenção de vazamentos de dados é um desafio constante para a maioria das organizações, especialmente com o rápido aumento de novos dados criados por funcionários, dispositivos e serviços. Os funcionários são capacitados a criar, armazenar e compartilhar informações entre serviços e dispositivos que tornam o gerenciamento de vazamentos de dados cada vez mais complexo e difícil. Os vazamentos de dados podem incluir o compartilhamento acidental de informações fora de sua organização ou roubo de dados com más intenções. Este modelo prioriza a detecção em tempo real de downloads suspeitos de dados do SharePoint Online, compartilhamento de arquivos e pastas, cópia de arquivos para dispositivos portáteis, como unidades USB, impressão de arquivos e cópia de dados para serviços de armazenamento e mensagens na nuvem pessoal.

>[!IMPORTANT]
>Ao usar esse modelo, você deve configurar pelo menos uma política de prevenção de perda de dados (DLP) para definir informações confidenciais em sua organização. Consulte o tópico [criar, testar e ajustar uma política de DLP](create-test-tune-dlp-policy.md) para obter orientações passo a passo para configurar as políticas de DLP para sua organização.

### <a name="offensive-language-in-email"></a>Idioma ofensivo no email

Detectar e realizar ações para impedir o comportamento ofensivo e abusivo é um componente essencial da prevenção de riscos. Os classificadores de idiomas ofensivos internos no Microsoft 365 podem examinar mensagens de email enviadas de caixas de correio do Exchange Online em sua organização para diferentes tipos de problemas de conformidade. Esses classificadores usam uma combinação de inteligência artificial e palavras-chave para identificar o idioma em que o email provavelmente viola as políticas antiassédio. Use este modelo para criar rapidamente uma política que use esses classificadores para detectar automaticamente o conteúdo de mensagens de email que pode ser considerado abusivo ou ofensivo. O gerenciamento de risco do insider usa classificadores que verificam as mensagens de email enviadas para termos do idioma inglês e uma inversão para linguagem ofensiva.

## <a name="monitoring-windows"></a>Monitorando janelas

As janelas de monitoramento de diretivas permitem definir períodos de tempo que disparam a ativação de política com base em eventos e atividades para os modelos de política de gerenciamento de risco do insider Dependendo do modelo de política escolhido, as seguintes janelas de monitoramento estarão disponíveis:

- **TimeSpan no escopo**: disponível para todos os modelos de política, o *TimeSpan no escopo* é o número definido de dias que a janela é ativada **após** um evento de acionamento. A janela é ativada por 1 a 30 dias após a ocorrência de um evento de acionamento para qualquer usuário atribuído à política. Por exemplo, você configurou uma política de gerenciamento de risco do insider e definiu o *TimeSpan no escopo* como 30 dias. Vários meses passaram desde que você configurou a política e um evento de acionamento ocorre para um dos usuários incluídos na política. O evento de acionamento ativa o *TimeSpan no escopo* e a política fica ativa para esse usuário por 30 dias após o evento de acionamento ter ocorrido.
- **TimeSpan histórico**: disponível para todos os modelos de política, o *TimeSpan histórico* é o número definido de dias que a janela é ativada **antes** de um evento de acionamento. A janela é ativada para 0 a 180 dias antes da ocorrência de um evento de acionamento para qualquer usuário atribuído à política. Por exemplo, você configurou uma política de gerenciamento de risco do insider e definiu a *TimeSpan histórica* como 90 dias. Vários meses passaram desde que você configurou a política e um evento de acionamento ocorre para um dos usuários incluídos na política. O evento de acionamento ativa o *TimeSpan histórico* e a política reúne as atividades históricas para esse usuário por 90 dias antes do evento de acionamento.
- **Janela de término futuro**: você verá essa configuração na visualização do público, mas ela não é aplicada a nenhuma política e será removida para o lançamento de produção desta solução.
- **Última janela de rescisão**: você verá essa configuração na visualização do público, mas ela não é aplicada a nenhuma política e será removida para o lançamento de produção desta solução.

## <a name="create-a-new-policy"></a>Criar uma nova política

Para criar uma nova política de gerenciamento de risco do Insider, você usará o assistente de política na solução de **Gerenciamento de risco do insider** no centro de conformidade da Microsoft 365.

Conclua as seguintes etapas para criar uma nova política:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **políticas** .
2. Selecione **criar política** para abrir o assistente de política
3. Na página **nova política de riscos de insider** , preencha os seguintes campos:
    - **Nome (obrigatório)**: Insira um nome amigável para a política
    - **Descrição (opcional)**: Insira uma descrição para a política.
    - **Escolher modelo de política (obrigatório)**: selecione um dos [modelos de política](insider-risk-management-policies.md#policy-templates) para definir os tipos de indicadores de risco são monitorados pela política.

    >[!IMPORTANT]
    >Se você selecionar o modelo *vazamentos de dados* , precisará configurar pelo menos uma política DLP que será atribuída posteriormente no assistente. Se você selecionar o modelo de *roubo de dados do funcionário de parte* , precisará configurar o conector de RH para usar os recursos de detecção de sinal completo do modelo de política.

4. Selecione **Avançar** para continuar.
5. Na página **usuários** , selecione **Adicionar usuário ou grupo** para definir quais usuários estão incluídos nas caixas de seleção política ou **todos os usuários e grupos habilitados para email** . Selecione **Avançar** para continuar.
6. Na página **especificar qual conteúdo priorizar (opcional)** , você pode atribuir as fontes para priorizar as atividades de usuário arriscadas:
    - Sites do SharePoint: selecione **Adicionar site do SharePoint** e selecione as organizações do SharePoint que você deseja priorizar. Por exemplo, *"group1@contoso.sharepoint.com/sites/group1"*.
    - Tipo de informação confidencial: selecione **Adicionar tipo de informações confidenciais** e selecione os tipos de sensibilidade que você deseja priorizar. Por exemplo, *"número de conta bancária dos EUA"* e *"número do cartão de crédito"*.
    - Rótulos de sensibilidade: selecione **Adicionar rótulo de confidencialidade** e selecione os rótulos que você deseja priorizar. Por exemplo, *"confidencial"* e *"segredo"*.
7. Selecione **Avançar** para continuar.
8. Na página **escolher indicadores de alerta** , você verá os indicadores incluídos no modelo que você escolheu para essa política. Se você selecionou o modelo *vazamentos de dados* no início do assistente, deverá selecionar uma política de DLP na lista suspensa **política de DLP** .
9. Na página **selecionar janela de monitoramento** , você definirá as [condições da janela de monitoramento](insider-risk-management-policies.md#monitoring-windows) para a política. Configure as janelas de monitoramento conforme apropriado.
10. Selecione **Avançar** para continuar.
11. Na página **revisão** , revise as configurações escolhidas para a política. Selecione **Editar** para alterar qualquer um dos valores da política ou selecione **Enviar** para criar e ativar a política.

## <a name="update-a-policy"></a>Atualizar uma política

Para atualizar uma política de gerenciamento de risco do insider existente, você usará o assistente de política na solução de **Gerenciamento de risco do insider** no centro de conformidade da Microsoft 365.

Conclua as seguintes etapas para gerenciar uma política existente:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **políticas** .
2. No painel de políticas, selecione a política que você deseja gerenciar.
3. Na página detalhes da política, selecione **Editar política**
4. No assistente de política, não é possível editar os seguintes campos:
    - **Nome**: o nome amigável da política
    - **Selecione o guia estratégico**: o modelo usado para definir os tipos de indicadores de risco monitorados pela política.
5. Insira uma nova descrição para a política no campo **Descrição** . Selecione **Avançar** para continuar.
6. Na página **usuários** , selecione **Adicionar usuário ou grupo** para definir quais usuários estão incluídos nas caixas de seleção política ou **todos os usuários e grupos habilitados para email** . Selecione **Avançar** para continuar
7. Na página **especificar qual conteúdo priorizar (opcional)** , atualize as fontes para priorizar as atividades arriscadas do usuário:
    - Sites do SharePoint: selecione **Adicionar site do SharePoint** e selecione as organizações do SharePoint que você deseja priorizar. Por exemplo, *"group1@contoso.sharepoint.com/sites/group1"*.
    - Tipo de informação confidencial: selecione **Adicionar tipo de informações confidenciais** e selecione os tipos de sensibilidade que você deseja priorizar. Por exemplo, *"número de conta bancária dos EUA"* e *"número do cartão de crédito"*.
    - Rótulos de sensibilidade: selecione **Adicionar rótulo de confidencialidade** e selecione os rótulos que você deseja priorizar. Por exemplo, *"confidencial"* e *"segredo"*.
8. Selecione **Avançar** para continuar.
9. Na página **escolher indicadores de alerta** , você verá os indicadores incluídos no modelo que você escolheu para essa política. Se você selecionou o modelo *vazamentos de dados* no início do assistente, deverá selecionar uma política de DLP na lista suspensa **política de DLP** .
10. Na página **selecionar janela de monitoramento** , você definirá as [condições da janela de monitoramento](insider-risk-management-policies.md#monitoring-windows) para a política. Configure as janelas de monitoramento conforme apropriado.
11. Na página **revisão** , revise as configurações escolhidas para a política. Selecione **Editar** para alterar qualquer um dos valores da política ou selecione **Enviar** para atualizar e ative as alterações na política.

## <a name="delete-a-policy"></a>Excluir uma política

>[!NOTE]
>A exclusão de uma política não exclui alertas ativos ou arquivados gerados da política.

Para excluir uma política de gerenciamento de risco do insider existente, conclua as seguintes etapas:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **políticas** .
2. No painel de políticas, selecione a política que você deseja gerenciar.
3. Selecione **excluir** na barra de ferramentas do painel.
4. Na caixa de diálogo **excluir** , selecione **Sim** para excluir a política ou selecione **Cancelar** para fechar a caixa de diálogo.
