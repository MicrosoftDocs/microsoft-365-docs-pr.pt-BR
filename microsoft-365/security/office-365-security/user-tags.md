---
title: Marcas de usuário no Microsoft defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Os administradores podem saber como identificar grupos específicos de usuários com marcas de usuário no Microsoft defender para Office 365 plano 2. A filtragem de marca está disponível em alertas, relatórios e investigações no Microsoft defender para Office 365 para identificar rapidamente os usuários marcados.
ms.openlocfilehash: 14ebcebeb8081a2de341fd06facabd9f7d55b119
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123614"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Marcas de usuário no Microsoft defender para Office 365

> [!NOTE]
> O recurso de marcas de usuário está em visualização, não está disponível para todos e está sujeito a alterações. Para obter informações sobre o cronograma de lançamento, confira o [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).

Marcas de usuário são identificadores para grupos específicos de usuários no [Microsoft defender para Office 365](office-365-atp.md). Há dois tipos de marcas de usuário:

- **Marcas de sistema**: atualmente, [contas de prioridade](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) é o único tipo de marca do sistema.
- **Marcas personalizadas**: você mesmo cria essas marcas de usuário.

Se sua organização tiver o defender para Office 365 plano 2 (incluído na sua assinatura ou como um complemento), você poderá criar marcas de usuário personalizadas além de usar a marca de contas de prioridade.

Após aplicar marcas de sistema ou marcas personalizadas aos usuários, você pode usar essas marcas como filtros em alertas, relatórios e investigações:

- [Alertas no centro de conformidade & segurança](alerts.md)
- [Gerenciador de ameaças e detecções em tempo real](threat-explorer.md)
- [Relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report)
- [Modos de Exibição de Campanha](campaigns.md)
- Para contas de prioridade, você pode usar o [relatório de problemas de email para contas de prioridade](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) no centro de administração do Exchange (Eat).

Este artigo explica como configurar marcas de usuário no centro de conformidade de & de segurança. Não há cmdlets no centro de conformidade & segurança para gerenciar marcas de usuário.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página **marcas do usuário** , abra <https://protection.office.com/userTags> .

- Para criar, modificar ou remover **marcas de usuário personalizadas**, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de administrador de **segurança** no centro de conformidade de & de segurança. Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

- Para configurar contas de prioridade (marcas de sistema), você precisa ser um [administrador global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) ou um [administrador do Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).

  Você também pode gerenciar e monitorar contas de prioridade no centro de administração do Microsoft 365. Para obter instruções, consulte [gerenciar e monitorar contas de prioridade](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).

## <a name="use-the-security-center-to-create-user-tags"></a>Usar a central de segurança para criar marcas de usuário

1. Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.

2. Na página **marcas de usuário** que é aberta, clique em **criar marca**.

3. O assistente **criar marca** é aberto em uma nova saída. Na página **definir marca** , defina as seguintes configurações:
   - **Name**: Insira um nome exclusivo e descritivo para a marca. Este é o valor que você verá e usará.
   - **Descrição**: Insira uma descrição opcional para a marca.

   Quando terminar, clique em **Avançar**.

4. Na página **atribuir caixas de correio** , execute uma das seguintes etapas:

   - Clique em **adicionar caixas de correio**. Na saída exibida, execute uma das seguintes etapas para adicionar usuários individuais ou grupos:
     - Clique na caixa e role pela lista para selecionar um usuário ou grupo.
     - Clique na caixa e comece a digitar para filtrar a lista e selecione um usuário ou grupo.
     - Para adicionar valores adicionais, clique em uma área vazia na caixa.
     - Para remover entradas individuais da caixa, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) no usuário ou grupo na caixa.
     - Para remover as entradas existentes da lista abaixo da caixa, clique em **remover** ![ ícone ](../../media/scc-remove-icon.png) de remoção na entrada.

     Quando tiver concluído, clique em **Adicionar**.

   - Clique em **importar** para selecionar um arquivo de texto que contenha os endereços de email dos usuários ou grupos. Certifique-se de que o arquivo de texto contém uma entrada por linha.

   Quando terminar, clique em **Avançar**.

5. Na página **rever tag** , revise suas configurações. Você pode clicar em **Editar** na seção específica para fazer alterações.

   Quando tiver concluído, clique em **Enviar**.

## <a name="use-the-security-center-to-view-user-tags"></a>Usar a central de segurança para exibir marcas de usuário

1. Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.

2. Na página **marcas de usuário** que é aberta, selecione a marca de usuário que você deseja exibir (não clique na caixa de seleção).

3. Nos detalhes de somente leitura que aparecerem, revise as configurações.

   Quando terminar, clique em **Fechar**.

## <a name="use-the-security-center-to-modify-user-tags"></a>Usar a central de segurança para modificar marcas de usuário

1. Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.

2. Na página **marcas de usuário** que é aberta, selecione a marca de usuário que você deseja exibir e clique em **Editar marca**.

3. O assistente de política é aberto em uma **marca de edição** de saída. Clique em **Avançar** para revisar e modificar as configurações.

   Quando tiver concluído, clique em **Enviar**.

## <a name="use-the-security-center-to-remove-user-tags"></a>Usar a central de segurança para remover marcas de usuário

**Observação**: não é possível remover a marca de **conta de prioridade** interna.

1. Na central de segurança, vá para as marcas de usuário do gerenciamento de **ameaças** \> **User tags**.

2. Na página **marcas de usuário** que é aberta, selecione a marca de usuário que você deseja remover, clique em **excluir marca** e selecione **Sim, remova** o aviso exibido.
