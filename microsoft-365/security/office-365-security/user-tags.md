---
title: Marcas de usuário no Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a identificar grupos específicos de usuários com marcas de usuário no Microsoft Defender para Office 365 Plano 2. A filtragem de marca está disponível em alertas, relatórios e investigações no Microsoft Defender para Office 365 para identificar rapidamente os usuários marcados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 62d858fe5962b94f536d4ccbd712e21bdd5caa57
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290124"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Marcas de usuário no Microsoft Defender para Office 365

> [!NOTE]
> O recurso de marcas de usuário está na Visualização, não está disponível para todos e está sujeito a alterações. Para obter informações sobre o cronograma de lançamento, confira o [mapa do Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)

As marcas de usuário são identificadores para grupos específicos de usuários [no Microsoft Defender para Office 365.](office-365-atp.md) Há dois tipos de marcas de usuário:

- **Marcas do** sistema: Atualmente, as contas [de prioridade](../../admin/setup/priority-accounts.md) são o único tipo de marca do sistema.
- **Marcas personalizadas:** você mesmo cria essas marcas de usuário.

Se sua organização tiver o Defender para Office 365 Plano 2 (incluído em sua assinatura ou como um complemento), você pode criar marcas de usuário personalizadas além de usar a marca de contas de prioridade.

Depois de aplicar marcas do sistema ou marcas personalizadas aos usuários, você pode usá-la como filtros em alertas, relatórios e investigações:

- [Alertas no Centro de Conformidade & segurança](alerts.md)
- [Explorador de Ameaças e detecções em tempo real](threat-explorer.md)
- [Relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report)
- [Modos de Exibição de Campanha](campaigns.md)
- Para contas de prioridade, você pode usar os problemas de email para o relatório [de contas prioritárias](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) no Centro de administração do Exchange (EAC).

Este artigo explica como configurar marcas de usuário no Centro de Conformidade e & Segurança. Não há cmdlets no Centro de Conformidade e Segurança & gerenciar marcas de usuário.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a **página de marcas de** usuário, abra <https://protection.office.com/userTags> .

- Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos deste artigo:
  - Para criar, modificar e excluir marcas de usuário,  você precisa ser membro dos grupos de função Gerenciamento da Organização ou **Administrador de** Segurança.
  - Para adicionar e remover membros de marcas de usuário existentes, você precisa ser membro dos grupos de função Gerenciamento da **Organização,** Administrador de Segurança ou **Operador** de Segurança
  - Para acesso somente leitura às marcas de usuário, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.

  Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  - O gerenciamento de marca de usuário é controlado pelas funções Leitor **de Marca,** **Colaborador de Marca** e Gerenciador de **Marca.**

- Você também pode gerenciar e monitorar contas prioritárias no Centro de administração do Microsoft 365. Para obter instruções, consulte [Gerenciar e monitorar contas de prioridade.](../../admin/setup/priority-accounts.md)

## <a name="use-the-security-center-to-create-user-tags"></a>Usar a Central de Segurança para criar marcas de usuário

1. Na Central de Segurança, vá para Gerenciamento **de ameaças Marcas** de \> **usuário.**

2. Na página **Marcas de usuário** que é aberta, clique em Criar **marca.**

3. O **assistente criar marca** é aberto em um novo fly out. Na página **Definir marca,** defina as seguintes configurações:
   - **Nome:** insira um nome exclusivo e descritivo para a marca. Esse é o valor que você verá e usará.
   - **Descrição:** insira uma descrição opcional para a marca.

   Quando terminar, clique em **Avançar**.

4. Na página **Atribuir usuários,** faça uma das seguintes etapas:

   - Clique **em Adicionar usuários.** No fly out exibido, faça uma das seguintes etapas para adicionar usuários ou grupos individuais:
     - Clique na caixa e role a lista para selecionar um usuário ou grupo.
     - Clique na caixa e comece a digitar para filtrar a lista e selecionar um usuário ou grupo.
     - Para adicionar valores adicionais, clique em uma área vazia na caixa.
     - Para remover entradas individuais da  caixa, clique no ícone Remover do ![ usuário ou grupo na ](../../media/scc-remove-icon.png) caixa.
     - Para remover as entradas existentes da lista abaixo da caixa, clique no ícone **Remover** ![ da ](../../media/scc-remove-icon.png) entrada.

     Quando terminar, clique em **Adicionar**.

   - Clique **em Importar** para selecionar um arquivo de texto que contém os endereços de email dos usuários ou grupos. Certifique-se de que o arquivo de texto contenha uma entrada por linha.

   Quando terminar, clique em **Avançar**.

5. Na página **Revisar marca,** revise suas configurações. Você pode clicar **em Editar** na seção específica para fazer alterações.

   Quando terminar, clique em **Enviar.**

## <a name="use-the-security-center-to-view-user-tags"></a>Usar a Central de Segurança para exibir marcas de usuário

1. Na Central de Segurança, vá para Gerenciamento **de ameaças Marcas** de \> **usuário.**

2. Na página **Marcas de** usuário que é aberta, selecione a marca de usuário que você deseja exibir (não clique na caixa de seleção).

3. No submenu somente leitura exibido, revise as configurações.

   Quando terminar, clique em **Fechar**.

## <a name="use-the-security-center-to-modify-user-tags"></a>Usar a Central de Segurança para modificar as marcas de usuário

1. Na Central de Segurança, vá para Gerenciamento **de ameaças Marcas** de \> **usuário.**

2. Na página **Marcas de usuário** que é aberta, selecione a marca de usuário que você deseja exibir e clique em Editar **marca**.

3. O assistente de política é aberto em um **fly out de marca** de edição. Clique **em** Próximo para revisar e modificar as configurações.

   Quando terminar, clique em **Enviar.**

## <a name="use-the-security-center-to-remove-user-tags"></a>Usar a Central de Segurança para remover marcas de usuário

**Observação:** não é possível remover a marca da conta **Priority.**

1. Na Central de Segurança, vá para Gerenciamento **de ameaças Marcas** de \> **usuário.**

2. Na página **Marcas de** usuário que é aberta, selecione a marca de usuário que você deseja remover, clique em Excluir **marca** e **selecione Sim,** remova no aviso exibido.
