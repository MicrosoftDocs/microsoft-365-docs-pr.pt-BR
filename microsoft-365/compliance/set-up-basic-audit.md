---
title: Configurar a Auditoria Básica no Microsoft 365
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
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: Este artigo descreve como configurar a Auditoria Básica para que você possa começar a procurar atividades de auditoria executadas por usuários e administradores em sua organização.
ms.openlocfilehash: 59b5c85003ef0e19f7d3dd7417f764f446244652
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52564817"
---
# <a name="set-up-basic-audit-in-microsoft-365"></a>Configurar a Auditoria Básica no Microsoft 365

A Auditoria Básica Microsoft 365 permite que você pesquise registros de auditoria para atividades executadas nos diferentes serviços Microsoft 365 por usuários e administradores. Como a Auditoria Básica está habilitada por padrão para a maioria das organizações Microsoft 365 e Office 365, há apenas algumas coisas que você precisa fazer antes que você e outras pessoas em sua organização possam pesquisar o log de auditoria.

Este artigo discute as etapas a seguir necessárias para configurar a Auditoria Básica.

![Etapas para configurar a Auditoria Básica](../media/BasicAuditingWorkflow.png)

Essas etapas incluem garantir as assinaturas organizacionais adequadas e o licenciamento do usuário necessário para gerar e preservar registros de auditoria e atribuir permissões aos membros da equipe de suas operações de segurança, DE, conformidade e equipes legais para que possam pesquisar o log de auditoria.

Para obter mais informações, consulte [Auditoria Básica em Microsoft 365](auditing-solutions-overview.md#basic-audit).

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a>Etapa 1: Verificar a assinatura da organização e o licenciamento do usuário

O licenciamento para Auditoria Básica requer a assinatura da organização apropriada que fornece acesso à ferramenta de pesquisa de log de auditoria e ao licenciamento por usuário necessário para registrar e reter registros de auditoria.

Quando uma atividade auditada é realizada por um usuário ou administrador, um registro de auditoria é gerado e armazenado no log de auditoria para a sua organização. Na Auditoria Básica, os registros de auditoria são mantidos e pesquisáveis no log de auditoria por 90 dias.

Para ver uma lista de requisitos de assinatura e licenciamento para Auditoria Básica, consulte [Soluções de](auditing-solutions-overview.md#licensing-requirements)auditoria em Microsoft 365 .

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a>Etapa 2: Atribuir permissões para pesquisar o log de auditoria

Os administradores e membros das equipes de investigação devem ser atribuídos View-Only função logs de auditoria ou logs de auditoria em Exchange Online pesquisar o log de auditoria. Por padrão, essas funções são atribuídas aos grupos de funções Gerenciamento de Conformidade e Gerenciamento de Organização na página **Permissões** do centro de administração do Exchange. Os administradores globais no Office 365 e Microsoft 365 são adicionados automaticamente como membros do grupo de funções Gerenciamento da Organização no Exchange Online. Para que um usuário tenha a capacidade de pesquisar o log de auditoria com o nível mínimo de privilégios, você pode criar um grupo de funções personalizado no Exchange Online, adicionar a função Logs de Auditoria Somente para Exibição ou Logs de Auditoria e, em seguida, adicionar o usuário como um membro do novo grupo de funções. Para saber mais, confira [Gerenciar Grupos de Funções do Exchange Online](/Exchange/permissions-exo/role-groups).

A captura de tela a seguir mostra as duas funções relacionadas à auditoria atribuídas ao grupo de função Gerenciamento da Organização no Exchange de administração.

![Funções de auditoria atribuídas ao grupo de funções Exchange Online](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a>Etapa 3: Pesquisar o log de auditoria

Agora você está pronto para pesquisar o log de auditoria no Microsoft 365 de conformidade.

1. Acesse e entre usando uma conta que recebeu as permissões de auditoria <https://compliance.microsoft.com> apropriadas.

2. No painel de navegação esquerdo do centro de conformidade Microsoft 365, clique em **Mostrar tudo** e clique em **Auditoria**.

3. Na página **Auditoria,** configure a pesquisa usando as seguintes condições na **guia Pesquisa.** 

   ![Configurações de pesquisa de log de auditoria](../media/AuditLogSearchToolMCCCallouts.png)

   1. **Data e intervalo de tempo**. Selecione um intervalo de datas e horas para exibir os eventos ocorridos durante esse período. A data e hora são apresentadas na horário local. Os últimos sete dias são selecionados por padrão.
  
   2. **Atividades**. Selecione as atividades a ser pesquisada. Use a caixa de pesquisa para pesquisar atividades para adicionar à lista. Para uma lista parcial de atividades auditadas, consulte [Atividades auditadas](search-the-audit-log-in-security-and-compliance.md#audited-activities). Deixe essa caixa em branco para retornar entradas para todas as atividades auditadas.
  
   3. **Usuários**.  Clique nesta caixa e comece a digitar o nome dos usuários para exibir os resultados da pesquisa. As entradas de log de auditoria para as atividades selecionadas realizadas pelos usuários selecionados nesta caixa são exibidas na lista de resultados. Deixe essa caixa em branco para retornar entradas para todos os usuários (e contas de serviço) na sua organização.
  
   4. **Arquivo, pasta ou site**. Digite alguns ou todos os nomes de arquivo ou pasta para pesquisar atividades relacionadas ao arquivo de pasta que contém a palavra-chave especificada. Você também pode especificar uma URL de um arquivo ou pasta. Se você usar uma URL de um arquivo ou pasta, certifique-se de digitar o caminho de URL completo ou se você digitar uma parte da URL, não inclua caracteres ou espaços especiais. Deixe essa caixa em branco para retornar entradas para todos os arquivos e pastas em sua organização.

4. Clique **em Pesquisar** para executar a pesquisa.

Uma nova página é exibida que mostra que a pesquisa de log de auditoria está em execução. Quando a pesquisa é concluída, os registros de auditoria são exibidos na página. Clique em um registro para exibir uma página de sobremenu com propriedades detalhadas.

Para obter instruções mais detalhadas, consulte [Pesquisar o log de auditoria no centro de conformidade.](search-the-audit-log-in-security-and-compliance.md)
