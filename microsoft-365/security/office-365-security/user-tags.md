---
title: Marcas de usuário
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
description: Os administradores podem aprender a identificar grupos específicos de usuários com marcas de usuário no Oiffce 365 ATP plano 2. A filtragem de marca está disponível em alertas, relatórios e investigações no Office 365 ATP para identificar rapidamente os usuários marcados.
ms.openlocfilehash: d47c5c00e3cf0362c44aebc18d11db4bba68a149
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48210018"
---
# <a name="user-tags-in-the-microsoft-security-center"></a>Marcas de usuário no centro de segurança da Microsoft

As marcas de usuário são identificadores de grupos específicos de usuários no [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md). [As contas de prioridade](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) são um tipo de marca de usuário. Se sua organização tiver o plano de ATP 2 do Office 365 (incluído na sua assinatura ou como um complemento), você poderá criar marcas de usuário personalizadas além de usar a marca de contas de prioridade.

Após aplicar marcas a usuários específicos, você pode usar essas marcas como filtros em alertas, relatórios e investigações:

- [Alertas no centro de conformidade & segurança](alerts.md)
- [Gerenciador de ameaças e detecções em tempo real](threat-explorer.md)
- [Relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report)
- [Modos de exibição de campanha](campaigns.md)

Este artigo explica como configurar marcas de usuário na central de segurança.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra a central de segurança em <https://security.microsoft.com/> . Para ir diretamente para a página **marcas do usuário** , abra <https://security.microsoft.com/securitysettings/userTags> .

- Para criar, modificar ou remover marcas de usuário, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de administrador de **segurança** no centro de conformidade de & de segurança. Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

- Você também pode gerenciar e monitorar contas de prioridade no centro de administração do Microsoft 365. Para obter instruções, consulte [gerenciar e monitorar contas de prioridade](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).

## <a name="use-the-security-center-to-create-user-tags"></a>Usar a central de segurança para criar marcas de usuário

1. Na central de segurança, vá para **configurações** de \> **email & colaboração** de \> **usuário**.

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

1. Na central de segurança, vá para **configurações** de \> **email & colaboração** de \> **usuário**.

2. Na página **marcas de usuário** que é aberta, selecione a marca de usuário que você deseja exibir (não clique na caixa de seleção).

3. Nos detalhes de somente leitura que aparecerem, revise as configurações.

   Quando terminar, clique em **Fechar**.

## <a name="use-the-security-center-to-modify-user-tags"></a>Usar a central de segurança para modificar marcas de usuário

1. Na central de segurança, vá para **configurações** de \> **email & colaboração** de \> **usuário**.

2. Na página **marcas de usuário** que é aberta, selecione a marca de usuário que você deseja exibir e clique em **Editar marca**.

3. O assistente de política é aberto em uma **marca de edição** de saída. Clique em **Avançar** para revisar e modificar as configurações.

   Quando tiver concluído, clique em **Enviar**.

## <a name="use-the-security-center-to-remove-user-tags"></a>Usar a central de segurança para remover marcas de usuário

**Observação**: não é possível remover a marca de **conta de prioridade** interna.

1. Na central de segurança, vá para **configurações** de \> **email & colaboração** de \> **usuário**.

2. Na página **marcas de usuário** que é aberta, selecione a marca de usuário que você deseja remover, clique em **excluir marca**e selecione **Sim, remova** o aviso exibido.
