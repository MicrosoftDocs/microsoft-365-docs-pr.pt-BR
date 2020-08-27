---
title: Configurar um conector para arquivar dados do arquivador de número de empresa de Telemensagem
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
description: Os administradores podem configurar um conector para importar e arquivar dados SMS e MMS do Archiver de número corporativo de Telemensagem. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: 5e82d5a83b80987837cba323342e60c6d2b31b72
ms.sourcegitcommit: b144e8ba1ab0c40fa7e0e8e893b5cb44aa2d8243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47282721"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data-preview"></a>Configurar um conector para arquivar dados de número de empresa (versão prévia)

Use um conector de Telemensagem no centro de conformidade da Microsoft 365 para importar e arquivar mensagens de serviço de mensagens curtas (SMS) e MMS (serviço de mensagens de multimídia), mensagens de chat, gravações de chamada de voz e logs de chamada de voz do arquivador de número da empresa. Depois de configurar e configurar um conector, ele se conecta à conta de Telemensagem de sua organização uma vez por dia e importa os dados de comunicação móvel de funcionários usando o arquivador de número de empresa de Telemensagem para caixas de correio no Microsoft 365.

Depois que os dados do conector do Archiver de número de empresa de Telemensagem são armazenados nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, pesquisa de conteúdo, arquivamento in-loco, auditoria, conformidade de comunicação e políticas de retenção da Microsoft 365 para dados de arquivador de número corporativo. Por exemplo, você pode pesquisar o arquivador de número corporativo de WebMessage Archiver, o MMS e a chamada de voz usando a pesquisa de conteúdo ou associar a caixa de correio que contém os dados do conector Enterprise Number Archiver com um funcionário em uma ocorrência de descoberta eletrônica avançada. O uso de um conector de arquivador de número corporativo para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

## <a name="overview-of-archiving-enterprise-number-data"></a>Visão geral dos dados de número de empresa de arquivamento

A visão geral a seguir explica o processo de usar um conector para arquivar dados de rede corporativa no Microsoft 365.

![Fluxo de trabalho de arquivamento de número corporativo](../media/EnterpriseNumberConnectorWorkflow.png)

1. Sua organização funciona com telemessage para configurar um conector de arquivador de número corporativo. Para obter mais detalhes, consulte [aqui](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/).

2. O conector do arquivador de número corporativo que você cria no centro de conformidade da Microsoft 365 se conecta ao site de Telemensagem todos os dias e transfere as mensagens de email das últimas 24 horas para uma área de armazenamento do Azure segura na nuvem da Microsoft.

3. O conector importa os itens de comunicação móvel para a caixa de correio de um usuário específico. Uma nova pasta chamada Enterprise Number Archiver será criada na caixa de correio do usuário específico e os itens serão importados para ela. O conector faz o mapeamento usando o valor da propriedade de *endereço de email do usuário* . Cada mensagem de email contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem de email. Além do mapeamento automático de usuários usando o valor da propriedade de *endereço de email do usuário* , você também pode definir um mapeamento personalizado carregando um arquivo de mapeamento CSV. Esse arquivo de mapeamento deve conter o número de celular do usuário e o endereço de caixa de correio do Microsoft 365 correspondente para cada usuário. Se você habilitar o mapeamento automático de usuários e fornecer um mapeamento personalizado, para cada item de email, o conector examinará primeiro o arquivo de mapeamento personalizado. Se não encontrar um usuário válido do Microsoft 365 que corresponda ao número de celular de um usuário, o conector usará a propriedade de endereço de email do usuário do item de email. Se o conector não localizar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade de *endereço de email do usuário* do item de email, o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Muitas das etapas de implementação necessárias para arquivar dados de arquivador de número corporativo são externas para o Microsoft 365 e devem ser concluídas para que você possa criar o conector no centro de conformidade.

- Solicite o [serviço arquivador de número corporativo de telemessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) e obtenha uma conta de administração válida para sua organização. Você precisará entrar nessa conta quando criar o conector no centro de conformidade.

- Registre todos os usuários que exigem o número corporativo de arquivamento de rede SMS/MMS na conta de Telemensagem. Ao registrar usuários, certifique-se de usar o mesmo endereço de email usado para a conta do Microsoft 365.

- Instale e ative o aplicativo arquivador de número de empresa de Telemensagem nos telefones celulares de seus funcionários.

- Sua organização deve dar o consentimento para permitir que o serviço de importação do Office 365 acesse dados de caixa de correio em sua organização. Você precisará fornecer esse consentimento ao criar o conector. Para concordar com essa solicitação, [acesse esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), entre com as credenciais de um administrador global do Office 365 e aceite a solicitação. Você precisa concluir esta etapa para poder criar um conector de rede Bell com êxito.

- O usuário que cria um conector de arquivador de número corporativo deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online. Isso é necessário para adicionar conectores na página **conectores de dados** no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

## <a name="create-an-enterprise-number-archiver-connector"></a>Criar um conector de arquivador de número corporativo

Depois de concluir os pré-requisitos descritos na seção anterior, você pode criar um conector de arquivador de número corporativo no centro de conformidade da Microsoft 365. O conector usa as informações que você fornece para se conectar ao site de Telemensagem e transferir mensagens de chamada SMS, MMS e de voz para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Data Connectors** \> **Enterprise Number Archiver**.

2. Na página descrição do produto **arquivador de número corporativo** , clique em **Adicionar conector**

3. Na página **termos de serviço** , clique em **aceitar**.

4. Na página **logon na Telemensagem** , em etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Avançar**.

   - **Nome de usuário:** O nome de usuário de sua mensagem.

   - **Senha:** Sua senha de Telemensagem.

5. Depois que o conector é criado, você pode fechar a janela pop-up e ir para a próxima página.

6. Na página **mapeamento de usuário** , habilite o mapeamento de usuário automático. Para habilitar o mapeamento personalizado, carregue um arquivo CSV que contenha as informações de mapeamento do usuário e clique em **Avançar**.

7. Forneça o consentimento do administrador e clique em **Avançar**.

   Para fornecer o consentimento do administrador, você deve estar conectado com as credenciais de um administrador global do Office 365 e aceitar a solicitação de consentimento. Se você não estiver conectado como um administrador global, poderá ir para [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e entrar usando credenciais de administrador global para aceitar a solicitação.

8. Revise suas configurações e clique em **concluir** para criar o conector.

9. Vá até a guia conectores na página **conectores de dados** para ver o andamento do processo de importação para o novo conector.

## <a name="known-issues"></a>Problemas conhecidos

- O conector não importa nenhum item com mais de 10 MB.
