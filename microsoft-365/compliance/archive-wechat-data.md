---
title: Configurar um conector para arquivar dados do WeChat no Microsoft 365
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
description: Configurar e usar um conector no centro de conformidade Microsoft 365 para importar e arquivar dados do WeChat em Microsoft 365.
ms.openlocfilehash: 3ee858cd09c1b6c7bd29dc5e2162753df9f5544a
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861618"
---
# <a name="set-up-a-connector-to-archive-wechat-data-preview"></a>Configurar um conector para arquivar dados do WeChat (visualização)

Use o conector teleMessage no centro de conformidade do Microsoft 365 para importar e arquivar chamadas, chats, anexos, arquivos e mensagens de chamada do WeChat e weCom. Depois de configurar e configurar um conector, ele se conecta à conta teleMessage da sua organização e importa a comunicação móvel de funcionários usando o Arquivo Mortor do WeChat teleMessage para caixas de correio em Microsoft 365.

Depois que os dados do conector do WeChat Archiver são armazenados em caixas de correio de usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Descoberta Eletrônico, Arquivamento In-Place In-Place, Auditoria, Conformidade de comunicação e políticas de retenção Microsoft 365 para dados de comunicação do WeChat. Por exemplo, você pode pesquisar a comunicação do WeChat usando a Pesquisa de Conteúdo ou associar a caixa de correio que contém os dados do conector de arquivamento do WeChat com um custodiante em um caso Advanced eDiscovery arquivo. Usar um conector de Arquivamento do WeChat para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a manter-se em conformidade com os regulamentos de governança corporativa e as políticas regulatórias.

## <a name="overview-of-archiving-wechat-communication-data"></a>Visão geral dos dados de comunicação do WeChat de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar dados de comunicações do WeChat Microsoft 365.

![Fluxo de trabalho de arquivamento para dados de arquivamento do WeChat](../media/WeChatConnectorWorkflow.png)

1. Sua organização trabalha com TeleMessage para configurar um conector de Arquivamento do WeChat.

2. Em tempo real, os dados do WeChat da sua organização são copiados para o site do TeleMessage.

3. O conector do Arquivo Mortor do WeChat criado no centro de conformidade do Microsoft 365 conecta-se ao site do TeleMessage todos os dias e transfere as mensagens de email das 24 horas anteriores para uma área segura do Azure Armazenamento no Microsoft Cloud.

4. O conector importa os itens de comunicação móvel para a caixa de correio de um usuário específico. Uma nova pasta chamada Arquivo Mortor do WeChat será criada na caixa de correio do usuário específico e os itens serão importados para ela. O conector faz o mapeamento usando o valor da *propriedade endereço email do* usuário. Cada mensagem de email contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem de email. Além do mapeamento automático do usuário usando o valor da propriedade endereço *email* do usuário, você também pode definir um mapeamento personalizado carregando um arquivo de mapeamento CSV. Esse arquivo de mapeamento deve conter o Número móvel do usuário e o endereço Microsoft 365 caixa de correio correspondente para cada usuário. Se você habilitar o mapeamento automático do usuário e fornecer um mapeamento personalizado, para cada item de email, o conector procurará primeiro o arquivo de mapeamento personalizado. Se ele não encontrar um usuário Microsoft 365 que corresponda ao número móvel de um usuário, o conector usará a propriedade endereço de email do usuário do item de email. Se o conector não encontrar um usuário Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade de endereço de *email* do usuário do item de email, o item não será importado.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar um conector

- Trabalhe com TeleMessage para configurar um conector de arquivo morto do WeChat. Para obter mais informações, consulte [Ativando o Arquivo Mortor do WeChat do TeleMessage para Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-wechat-archiver/).

- Configurar um conector teleMessage para Microsoft 365 e obter uma conta de administração da empresa válida. Para obter mais informações, [consulte Order Microsoft 365 Mobile Archiving](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-microsoft-365/).

- Registre todos os usuários que exigem arquivamento do WeChat na conta teleMessage com o mesmo endereço de email usado para a conta Microsoft 365 usuário.

- Você precisará instalar o aplicativo WeCom da Tencent nos telefones celulares dos usuários em sua organização e ativá-lo. O aplicativo WeCom permite que os usuários se comuniquem e conversem com outros usuários do WeChat e do WeCom.

- O usuário que cria um conector de Arquivamento do WeChat no centro de conformidade Microsoft 365 deve receber a função De importação de importação de caixa de correio no Exchange Online. Isso é necessário para adicionar conectores na página **Conectores de** dados no centro de conformidade. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de funções em Exchange Online".

- Esse conector de dados está disponível em GCC ambientes na nuvem Microsoft 365 Us Government. Aplicativos e serviços de terceiros podem envolver o armazenamento, a transmissão e o processamento dos dados do cliente da sua organização em sistemas de terceiros que estão fora da infraestrutura do Microsoft 365 e, portanto, não são cobertos pelos compromissos de conformidade e proteção de dados do Microsoft 365. A Microsoft não faz nenhuma representação de que o uso desse produto para se conectar a aplicativos de terceiros implica que esses aplicativos de terceiros são compatíveis com FEDRAMP.

## <a name="create-a-wechat-archiver-connector"></a>Criar um conector de arquivamento do WeChat

Siga as etapas nesta seção para criar um conector de Arquivamento do WeChat no centro Microsoft 365 conformidade. O conector usa as informações fornecidas para se conectar ao site teleMessage e transferir dados de comunicações do WeChat para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá até <https://compliance.microsoft.com> e clique em **Conectores de dados** do  >  **WeChat Archiver**.

2. Na página **Descrição do produto do WeChat Archiver,** clique em **Adicionar conector**

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Na página **Logon para TeleMessage,** em Etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Próximo**.

    - **Nome** de usuário : seu nome de usuário teleMessage.

    - **Senha**: sua senha de TeleMessage.

5. Depois que o conector for criado, você poderá fechar a janela pop-up e ir para a próxima página.

6. Na página **Mapeamento de** usuário, habilita o mapeamento automático do usuário. Você também pode carregar um arquivo CSV de mapeamento de usuário personalizado.

7. Clique **em Próximo,** revise suas configurações e clique em **Concluir** para criar o conector.

8. Vá até a **guia Conectores** na página **Conectores de** dados para ver o andamento do processo de importação do novo conector.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.
