---
title: Marcas de usuário no Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a identificar grupos específicos de usuários com marcas de usuário no Microsoft Defender para Office 365 Plano 2. A filtragem de marca está disponível em alertas, relatórios e investigações no Microsoft Defender para Office 365 identificar rapidamente os usuários marcados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3ac53891e0eb106ab3681251cc4cb8c969b51f8a
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083111"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Marcas de usuário no Microsoft Defender para Office 365

> [!NOTE]
> O recurso de marcas de usuário está em Visualização, não está disponível para todos e está sujeito a alterações. Para obter informações sobre o cronograma de lançamento, confira [o roteiro Microsoft 365 .](https://www.microsoft.com/microsoft-365/roadmap)

As marcas de usuário são identificadores para grupos específicos de usuários no [Microsoft Defender para Office 365](defender-for-office-365.md). Há dois tipos de marcas de usuário:

- **Marcas do** sistema : Atualmente, [contas de prioridade](../../admin/setup/priority-accounts.md) é o único tipo de marca do sistema.
- **Marcas personalizadas**: você mesmo cria essas marcas de usuário.

Se sua organização tiver o Defender para Office 365 Plano 2 (incluído na sua assinatura ou como complemento), você poderá criar marcas de usuário personalizadas, além de usar a marca de contas de prioridade.

> [!NOTE]
> Atualmente, você só pode aplicar marcas de usuário a usuários de caixa de correio.

Depois de aplicar marcas de sistema ou marcas personalizadas aos usuários, você pode usar essas marcas como filtros em alertas, relatórios e investigações:

- [Alertas](alerts.md)
- [Políticas de alerta personalizadas](../../compliance/alert-policies.md#viewing-alerts)
- [Explorador de Ameaças e detecções em tempo real](threat-explorer.md)
- [Página de entidade de email](mdo-email-entity-page.md#other-innovations)
- [Relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report)
- [Modos de Exibição de Campanha](campaigns.md)
- Para contas prioritárias, você pode usar o [relatório Problemas de email](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) para contas prioritárias no centro de administração Exchange (EAC).

Este artigo explica como configurar marcas de usuário no Microsoft 365 Defender portal. Não há cmdlets no portal Microsoft 365 Defender gerenciar marcas de usuário.

Para ver como as marcas de usuário fazem parte da estratégia para ajudar a proteger contas de usuário de alto impacto, consulte [Recomendações](security-recommendations-for-priority-accounts.md)de segurança para contas de prioridade em Microsoft 365 .

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com/>. Para ir diretamente para a **página Marcas de** usuário, abra <https://security.microsoft.com/securitysettings/userTags> .

- Você precisa ter permissões atribuídas no portal Microsoft 365 Defender antes de poder fazer os procedimentos neste artigo:
  - Para criar, modificar e excluir marcas de usuário, você precisa ser membro dos grupos de função Gerenciamento da Organização **ou** Administrador **de** Segurança.
  - Para adicionar e remover membros de marcas de usuário existentes, você precisa ser membro dos grupos de função Gerenciamento da **Organização,** Administrador de Segurança ou Operador **de** Segurança
  - Para acesso somente leitura a marcas de usuário, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.

  Para obter mais informações, veja [Permissões no portal do Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

  > [!NOTE]
  >
  > - Adicionar usuários à função Azure Active Directory correspondente no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no _portal_ Microsoft 365 Defender e permissões para outros recursos no Microsoft 365. Para obter mais informações, confira [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  >
  > - O gerenciamento de marca de usuário é controlado pelas funções **Leitor de Marca e** Gerenciador de **Marca.**

- Você também pode gerenciar e monitorar contas de prioridade no Centro de administração do Microsoft 365. Para obter instruções, consulte [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).

- Para obter informações sobre como proteger contas _privilegiadas_ (contas de administrador), consulte [este tópico](/azure/architecture/framework/security/critical-impact-accounts).

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a>Usar o portal Microsoft 365 Defender para criar marcas de usuário

1. No portal Microsoft 365 Defender, acesse email **Configurações** \> **email & marcas** \> **de usuário de colaboração**.

2. Na página **Marcas de usuário,** clique em ![ Criar ícone de marca Criar ](../../media/m365-cc-sc-create-icon.png) **marca**.

3. O **assistente Criar marca** é aberto em um novo sobrevoo. Na página **Definir marca,** configure as seguintes configurações:
   - **Nome**: insira um nome exclusivo e descritivo para a marca. Esse é o valor que você verá e usará. Observe que você não pode renomear uma marca depois de criar.
   - **Descrição**: insira uma descrição opcional para a marca.

   Ao terminar, clique em **Avançar**.

4. Na página **Atribuir membros,** faça uma das seguintes etapas:
   - Clique ![ em Adicionar ícone de membros Adicionar ](../../media/m365-cc-sc-create-icon.png) **membros**. No fly out que aparece, faça qualquer uma das etapas a seguir para adicionar usuários ou grupos individuais:
     - Clique na caixa e role a lista para selecionar um usuário ou grupo.
     - Clique na caixa e comece a digitar para filtrar a lista e selecionar um usuário ou grupo.
     - Para adicionar valores adicionais, clique em uma área vazia na caixa.
     - Para remover entradas individuais, clique em ![Remover ícone de entrada](../../media/m365-cc-sc-remove-selection-icon.png) ao lado da entrada na caixa.
     - Para remover todas as entradas, clique em Remover ícone de entrada no item Usuários de nn selecionados e grupos ![ ](../../media/m365-cc-sc-remove-selection-icon.png) de **nn** abaixo da caixa.

     Quando terminar, clique em **Adicionar**.

     De volta à **página Atribuir membros,** você também pode remover entradas clicando em ![ Excluir ícone ao lado da ](../../media/m365-cc-sc-delete-icon.png) entrada.

   - Clique **em Importar** para selecionar um arquivo de texto que contém os endereços de email dos usuários ou grupos. Certifique-se de que o arquivo de texto contenha uma entrada por linha.

   Ao terminar, clique em **Avançar**.

5. Na página **Revisar marca** que aparece, revise suas configurações. Você pode selecionar **Editar** em cada seção para modificar as configurações da seção. Ou você pode clicar em **Voltar** ou selecionar a página específica no assistente.

   Quando terminar, clique em **Enviar** e clique em **Concluído**.

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a>Usar o portal Microsoft 365 Defender para exibir marcas de usuário

1. No portal Microsoft 365 Defender, acesse email **Configurações** \> **email & marcas** \> **de usuário de colaboração**.

2. Na página **Marcas de usuário,** as seguintes propriedades são exibidas na lista de marcas de usuário:

   - **Tag**: O nome da marca do usuário. Observe que isso inclui a marca do sistema de conta **de prioridade** integrado.
   - **Aplicado a**: O número de membros
   - **Última modificação**
   - **Criado em**

3. Quando você seleciona uma marca de usuário clicando no nome, os detalhes são exibidos em um sobremenu.

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a>Usar o portal Microsoft 365 Defender para modificar marcas de usuário

1. No portal Microsoft 365 Defender, acesse email **Configurações** \> **email & marcas** \> **de usuário de colaboração**.

2. Na página **Marcas de usuário,** selecione a marca do usuário na lista e clique em Editar ícone ![ de marca Editar ](../../media/m365-cc-sc-edit-icon.png) **marca**.

3. No sobremenu de detalhes exibido, o mesmo assistente e configurações estão disponíveis conforme descrito na seção Usar o portal Microsoft 365 Defender [para](#use-the-microsoft-365-defender-portal-to-create-user-tags) criar marcas de usuário anteriormente neste artigo.

   **Observações**:

   - A **página Definir marca** não está disponível para a marca do sistema de conta **De** prioridade, portanto, você não pode renomear essa marca ou alterar a descrição.
   - Você não pode renomear uma marca personalizada, mas pode alterar a descrição.

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a>Usar o portal Microsoft 365 Defender para remover marcas de usuário

> [!NOTE]
> Não é possível remover a marca do sistema de conta **De prioridade** integrado.

1. No portal Microsoft 365 Defender, acesse email **Configurações** \> **email & marcas** \> **de usuário de colaboração**.

2. Na página **Marcas de usuário,** selecione a marca do usuário na lista e clique em Excluir ícone ![ de marca Excluir ](../../media/m365-cc-sc-delete-icon.png) **marca**.

3. Leia o aviso na caixa de diálogo de confirmação exibida e clique em **Sim, remova**.
