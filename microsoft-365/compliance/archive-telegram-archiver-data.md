---
title: Configurar um conector para arquivar dados de comunicações do Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Os administradores podem configurar um conector teleMessage para importar e arquivar dados de comunicações do Microsoft 365. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: 5db1869a1c386ed75f3d8d1381f598d907d2b5ba
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339437"
---
# <a name="set-up-a-connector-to-archive-telegram-communications-data"></a>Configurar um conector para arquivar dados de comunicações do Telegram

Use o conector TeleMessage no Centro de conformidade do Microsoft 365 para importar e arquivar chats, anexos, arquivos e mensagens e chamadas do Telegram excluídos. Depois de configurar e configurar um conector, ele se conecta à conta teleMessage da sua organização e importa a comunicação móvel dos funcionários usando o Arquivo Mortor do Telegram para caixas de correio em Microsoft 365.

Depois que os dados do conector do Arquivamento do Telegram são armazenados em caixas de correio de usuário, você pode aplicar recursos de conformidade Microsoft 365 como Retenção de Litígio, Pesquisa de conteúdo e políticas de retenção Microsoft 365 dados de comunicação do Telegram. Por exemplo, você pode pesquisar a comunicação do Telegram usando a Pesquisa de Conteúdo ou associar a caixa de correio que contém os dados do conector do Arquivo morto do Telegram com um custodiante em uma Advanced eDiscovery caso. Usar um conector de Arquivamento do Telegram para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a manter-se em conformidade com os regulamentos de governança corporativa e as políticas regulatórias.

## <a name="overview-of-archiving-telegram-communications-data"></a>Visão geral dos dados de comunicações do Telegram de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar dados de comunicações do Microsoft 365.

![Fluxo de trabalho de arquivamento de comunicações do Telegram](../media/TelegramConnectorWorkflow.png)

1. Sua organização trabalha com TeleMessage para configurar um conector de Arquivamento do Telegram. Para obter mais informações, consulte Ativando o Arquivo mortor de [telegrama de TeleMessage para Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-telegram-archiver/).

2. Em tempo real, os dados do Telegram da sua organização são copiados para o site do TeleMessage.

3. O conector do Arquivo Mortor do Telegram criado no Centro de conformidade do Microsoft 365 conecta-se ao site do TeleMessage todos os dias e transfere as mensagens de email das 24 horas anteriores para uma área segura do Azure Armazenamento no Microsoft Cloud.

4. O conector importa os itens de comunicação móvel para a caixa de correio de um usuário específico. Uma nova pasta chamada Arquivo mortor do Telegram será criada na caixa de correio do usuário específico e os itens serão importados para ela. O conector faz esse mapeamento usando o valor da *propriedade endereço email do* usuário. Cada mensagem de email contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem de email.

> Além do mapeamento automático do usuário usando o valor da propriedade endereço *email* do usuário, você também pode definir um mapeamento personalizado carregando um arquivo de mapeamento CSV. Esse arquivo de mapeamento deve conter o Número móvel do usuário e o endereço Microsoft 365 caixa de correio correspondente para cada usuário. Se você habilitar o mapeamento automático do usuário e fornecer um mapeamento personalizado, para cada item de email, o conector procurará primeiro o arquivo de mapeamento personalizado. Se ele não encontrar um usuário Microsoft 365 que corresponda ao número móvel de um usuário, o conector usará a propriedade endereço de email do usuário do item de email. Se o conector não encontrar um usuário Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade de endereço de *email* do usuário do item de email, o item não será importado.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar um conector

- Order the [Telegram archiving service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) and get a valid administration account for your organization. Você precisará entrar nessa conta quando criar o conector no centro de conformidade.

- Registre todos os usuários que exigem arquivamento do Telegram na conta teleMessage. Ao registrar usuários, certifique-se de usar o mesmo endereço de email usado para sua conta Microsoft 365.

- Instale o aplicativo de Arquivamento do Telegram nos telefones celulares de seus funcionários e ative-o. O aplicativo Desarmador do Telegram permite que eles se comuniquem e conversem com outros usuários do Telegram.

- O usuário que cria um conector de Arquivamento do Telegram na Etapa 3 deve receber a função de Exportação de Importação de Caixa de Correio Exchange Online. Isso é necessário para adicionar conectores na página **Conectores de** dados no Centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de funções em Exchange Online".

## <a name="create-a-telegram-archiver-connector"></a>Criar um conector de arquivamento do Telegram

Depois de concluir os pré-requisitos descritos na seção anterior, você pode criar o conector do Arquivo Mortor do Centro de conformidade do Microsoft 365. O conector usa as informações fornecidas para se conectar ao site teleMessage e transfere dados de comunicações do Telegram para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá até <https://compliance.microsoft.com> e clique em **Conectores de dados >** T **elegram Archiver**.

2. Na página **Descrição do produto do Arquivo** do Telegram, clique em Adicionar **conector**.

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Na página **Logon para TeleMessage,** em Etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Próximo**.

    - **Nome de usuário:** Seu nome de usuário teleMessage.

    - **Senha:** Sua senha teleMessage.

5. Depois que o conector for criado, você poderá fechar a janela pop-up e ir para a próxima página.

6. Na página **Mapeamento de** usuário, habilita o mapeamento automático do usuário. Para habilitar o mapeamento personalizado, carregue um arquivo CSV que contém as informações de mapeamento do usuário e clique em **Próximo**.

7. Revise suas configurações e clique em **Concluir** para criar o conector.

8. Vá até a guia Conectores na página **Conectores de** dados para ver o andamento do processo de importação do novo conector.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.
