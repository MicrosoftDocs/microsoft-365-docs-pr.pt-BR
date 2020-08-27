---
title: Configurar um conector para arquivar dados de rede do TELUS no Microsoft 365
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
ROBOTS: NOINDEX, NOFOLLOW
description: Os administradores podem configurar um conector de Telemensagem para importar e arquivar dados do SMS da rede do TELUS no Microsoft 365. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: f52ead856aeaabdf229a4798359042fd2651f777
ms.sourcegitcommit: b144e8ba1ab0c40fa7e0e8e893b5cb44aa2d8243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47282649"
---
# <a name="set-up-a-connector-to-archive-telus-network-data-preview"></a>Configurar um conector para arquivar dados de rede do TELUS (visualização)

Use o conector de Telemensagem no centro de conformidade da Microsoft 365 para importar e arquivar dados de serviço de mensagens curtas (SMS) da rede do TELUS da sua organização. Depois de configurar e configurar um conector, ele se conecta à rede do TELUS da sua organização uma vez a cada dia e importa os dados do SMS para caixas de correio no Microsoft 365.

Depois que as mensagens SMS são armazenadas nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, pesquisa de conteúdo e políticas de retenção da Microsoft 365 a dados do TELUS. Por exemplo, você pode pesquisar mensagens SMS do TELUS usando a pesquisa de conteúdo ou associar a caixa de correio que contém os dados do TELUS a um funcionário em uma caixa de descoberta eletrônica avançada. O uso de um conector de rede do TELUS para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

## <a name="overview-of-archiving-telus-network-data"></a>Visão geral do arquivamento de dados de rede do TELUS

A visão geral a seguir explica o processo de usar um conector para arquivar dados de rede do TELUS no Microsoft 365.

![Fluxo de trabalho de arquivamento de rede do TELUS](../media/TelusNetworkConnectorWorkflow.png)

1. Sua organização funciona com telemessage e TELUS para configurar um conector de rede do TELUS. Para obter mais informações, consulte [Telus Network archiverr](https://www.telemessage.com/office365-activation-for-telus-network-archiver/).

2. Uma vez a cada 24 horas, as mensagens SMS da rede do TELUS da sua organização são copiadas para o site de Telemensagem.

3. O conector de rede TELUS que você cria no centro de conformidade da Microsoft 365 conecta-se ao site de Telemensagem todos os dias e transfere as mensagens SMS das últimas 24 horas para um local seguro de armazenamento do Azure na nuvem da Microsoft. O conector também converte o conteúdo das mensagens SMS em um formato de mensagem de email.

4. O conector importa os itens de comunicação móvel para a caixa de correio de um usuário específico. Uma nova pasta chamada **Telus SMS Network Archiver** é criada na caixa de correio do usuário específico e os itens são importados para ela. O conector faz o mapeamento usando o valor da propriedade de *endereço de email do usuário* . Cada mensagem SMS contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem SMS.

   Além do mapeamento automático de usuários usando o valor da propriedade de *endereço de email do usuário* , você também pode implementar o mapeamento personalizado carregando um arquivo de mapeamento CSV. Este arquivo de mapeamento contém o número de telefone celular e o endereço de email correspondente do Microsoft 365 para usuários em sua organização. Se você habilitar o mapeamento de usuário automático e o mapeamento personalizado, para cada item do TELUS, o conector examinará primeiro o arquivo de mapeamento personalizado. Se não encontrar um usuário válido do Microsoft 365 que corresponda ao número de telefone celular de um usuário, o conector usará os valores na propriedade de endereço de email do item que está tentando importar. Se o conector não localizar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade de endereço de email do item TELUS, o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Muitas das etapas de implementação necessárias para arquivar dados de rede do TELUS são externas para o Microsoft 365 e devem ser concluídas para que você possa criar um conector no centro de conformidade.

- Solicite o [serviço arquivador de rede do Telus por meio da telemessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) e obtenha uma conta de administração válida para sua organização. Você precisará entrar nessa conta quando criar o conector no centro de conformidade.

- Obtenha os detalhes do contato de cobrança e conta de rede do TELUS para que você possa preencher os formulários de integração de mensagens e solicitar o serviço de arquivamento de mensagens do TELUS.

- Registre todos os usuários que exigem o arquivamento de rede SMS do TELUS na conta de Telemensagem. Ao registrar usuários, certifique-se de usar o mesmo endereço de email usado para a conta do Microsoft 365.

- Seus funcionários devem ter telefones móveis de propriedade corporativa e responsáveis corporativos na rede móvel do theTELUS. O arquivamento de mensagens no Microsoft 365 não está disponível para funcionários de propriedade ou para trazer seus próprios dispositivos (BYOD).

- Sua organização deve dar o consentimento para permitir que o serviço de importação do Office 365 acesse dados de caixa de correio em sua organização. Você precisará fornecer esse consentimento ao criar o conector. Para concordar com essa solicitação, [acesse esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), entre com as credenciais de um administrador global do Office 365 e aceite a solicitação. Você precisa concluir esta etapa para poder criar com êxito o conector de rede do TELUS.

- O usuário que cria um conector de rede TELUS deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online. Isso é necessário para adicionar conectores na página **conectores de dados** no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

## <a name="create-a-telus-network-connector"></a>Criar um conector de rede do TELUS

Depois de concluir os pré-requisitos descritos na seção anterior, você pode criar o TELUS Network Connector no centro de conformidade da Microsoft 365. O conector usa as informações que você fornece para se conectar ao site de Telemensagem e transferir mensagens SMS para as caixas de caixa de correio de usuário correspondentes no Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **conectores de dados**  >  **Telus rede**.

2. Na página descrição de produto de **rede do Telus** , clique em **Adicionar conector**

3. Na página **termos de serviço** , clique em **aceitar**.

4. Na página **logon na Telemensagem** , em etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Avançar**.

   - **Nome de usuário:** O nome de usuário de sua mensagem.

   - **Senha:** Sua senha de Telemensagem.

5. Depois que o conector é criado, você pode fechar a janela pop-up e ir para a próxima página.

6. Na página **mapeamento de usuário** , habilite mapeamento automático de usuário e clique em **Avançar**. Caso você precise de mapeamento personalizado, carregue um arquivo CSV e clique em **Avançar**.

7. Forneça o consentimento do administrador e clique em **Avançar**.

   Para fornecer o consentimento do administrador, você deve estar conectado com as credenciais de um administrador global do Office 365 e aceitar a solicitação de consentimento. Se você não estiver conectado como um administrador global, poderá ir para [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e entrar usando credenciais de administrador global para aceitar a solicitação.

8. Revise suas configurações e clique em **concluir** para criar o conector.

9. Vá até a guia conectores na página **conectores de dados** para ver o andamento do processo de importação para o novo conector.

## <a name="known-issues"></a>Problemas conhecidos

- O conector não importa nenhum item com mais de 10 MB.
