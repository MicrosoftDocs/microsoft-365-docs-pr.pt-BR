---
title: Usuários de gerenciamento de risco do Insider (versão prévia)
description: Saiba mais sobre usuários de gerenciamento de risco do insider no Microsoft 365
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
ms.openlocfilehash: a9ff7e38a99a5fe5bd8da5301bec5e19bc015cf3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072779"
---
# <a name="insider-risk-management-users-preview"></a>Usuários de gerenciamento de risco do Insider (versão prévia)

Os usuários de gerenciamento de risco do insider são funcionários em sua organização que estão incluídos em uma ou mais políticas de gerenciamento de risco do insider. Use o **painel usuários** para examinar rapidamente as informações de risco sobre os funcionários e para adicionar um funcionário a uma política de gerenciamento de risco do insider existente. Cada usuário incluído em uma política de gerenciamento de risco do insider possui as seguintes informações exibidas no **painel usuários**:

- **Usuários**: o nome de usuário para um usuário.
- **Nível de risco**: 
- **Alertas ativos**: o número de alertas ativos para todas as políticas.
- **Violações confirmadas**: o número de ocorrências resolvidas como *violação de política confirmada* para o usuário.
- **Caso**: o caso ativo atual do usuário.

![Painel usuários de gerenciamento de risco do insider](../media/insider-risk-users-dashboard.png)

## <a name="view-user-details"></a>Exibir detalhes do usuário

Para exibir mais detalhes sobre a atividade de risco de um usuário, abra o painel de detalhes do usuário clicando duas vezes em um usuário no **painel usuários**. No painel de detalhes, você pode exibir as seguintes informações:

- Guia **perfil de usuário**
    - **Nome e título**: o nome e o título da posição do usuário.
    - **Email do usuário**: o endereço de email do usuário.
    - **Alias**: o alias de rede do usuário.
    - **Organização ou departamento**: a organização ou departamento do usuário.

- Guia **atividade do usuário**
    - **Histórico da atividade recente do usuário**: lista os eventos de acionamento de política e os indicadores de risco para atividades do usuário. Um evento de acionamento pode ser a aceitação de uma data de demissão ou da última data de trabalho agendada para o funcionário. Os indicadores de risco são atividades determinadas para ter um elemento de risco e que são correspondidas às políticas nas quais o usuário está incluído. Eventos e atividades de risco são listados com o item mais recente listado primeiro.

## <a name="add-a-user-to-a-policy"></a>Adicionar um usuário a uma política

Para adicionar um usuário a uma política de gerenciamento de risco do Insider, você usará o assistente de nova política ou a guia **usuários** na solução de **Gerenciamento de risco do insider** no centro de conformidade do Microsoft 365.

Conclua as seguintes etapas para adicionar um usuário a uma política de risco Insider existente:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **usuários** .
2. Selecione **Adicionar um usuário a uma política** na barra de ferramentas.
3. Na caixa de diálogo **Adicionar um novo usuário** , comece a digitar um nome de usuário no campo **usuário** . Selecione o usuário que você deseja adicionar a uma política.
4. Selecione a seta suspensa do campo **política** para exibir as políticas de gerenciamento de risco do insider configuradas. Selecione a política à qual adicionar o usuário.
5. Use o controle deslizante da **janela de monitoramento** para definir os...... O intervalo para a janela de monitoramento é de 5 a 30 dias.
6. Selecione **Adicionar** e depois em **confirmar** para adicionar o usuário à política.
