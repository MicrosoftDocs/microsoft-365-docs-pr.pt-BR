---
title: Configurar um conector para arquivar dados móveis do Android
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
description: Os administradores podem configurar um conector de Telemensagem para importar e arquivar chamadas SMS, MMS e de voz de telefones móveis Android. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: 5837d5247ca7ac82389d2781110883058ca98bb7
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620526"
---
# <a name="set-up-a-connector-to-archive-android-mobile-data"></a>Configurar um conector para arquivar dados móveis do Android

Use um conector de Telemensagem no centro de conformidade da Microsoft 365 para importar e arquivar o SMS, MMS, chamadas de voz e logs de chamadas de telefones móveis Android. Depois de configurar e configurar um conector, ele se conecta à conta de Telemensagem de sua organização uma vez por dia e importa a comunicação móvel de funcionários usando o Archiver de Android para caixas de correio no Microsoft 365.

Depois que os dados de telefones móveis Android são armazenados nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, pesquisa de conteúdo e políticas de retenção da Microsoft 365 a dados do arquivo morto do Android. Por exemplo, você pode pesquisar a comunicação móvel do arquivo Android usando a pesquisa de conteúdo ou associar a caixa de correio que contém os dados do conector do Archiver para Android com um funcionário em uma caixa de descoberta eletrônica avançada. Usar um conector do Archiver para Android para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

## <a name="overview-of-archiving-android-mobile-data"></a>Visão geral do arquivamento de dados móveis do Android

A visão geral a seguir explica o processo de usar um conector para arquivar dados móveis do Android no Microsoft 365.

![Fluxo de trabalho do conector do Archiver para Android](../media/AndroidArchiverConnectorWorkflow.png)

1. Sua organização trabalha com a telemessage para configurar um conector do Archiver para Android. Para obter mais informações, consulte [Android Archiver](https://www.telemessage.com/office365-activation-for-android-archiver/).

2. Uma vez a cada 24 horas, SMS, MMS, chamadas de voz e logs de chamadas dos telefones móveis Android da sua organização são copiados para o site de Telemensagem.

3. O conector do Archiver para Android que você cria no centro de conformidade da Microsoft 365 se conecta ao site de Telemensagem todos os dias e transfere os dados do Android das 24 horas anteriores para um local seguro de armazenamento do Azure na nuvem da Microsoft. O conector também converte os dados do Android em um formato de mensagem de email.

4. O conector importa os itens de comunicação móvel para a caixa de correio de um usuário específico. Uma nova pasta chamada Android Archiver é criada na caixa de correio do usuário específico e os itens são importados para ela. O conector faz o mapeamento usando o valor da propriedade de *endereço de email do usuário* . Cada mensagem de email contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem de email. Além do mapeamento automático de usuários usando o valor da propriedade de *endereço de email do usuário* , você também pode definir um mapeamento personalizado carregando um arquivo de mapeamento CSV. Esse arquivo de mapeamento deve conter o número de celular do usuário e o endereço de caixa de correio do Microsoft 365 correspondente para cada usuário. Se você habilitar o mapeamento automático de usuários e fornecer um mapeamento personalizado, para cada item de email, o conector examinará primeiro o arquivo de mapeamento personalizado. Se não encontrar um usuário válido do Microsoft 365 que corresponda ao número de celular de um usuário, o conector usará a propriedade de endereço de email do usuário do item de email. Se o conector não localizar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade de *endereço de email do usuário* do item de email, o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Algumas das etapas de implementação necessárias para arquivar dados de comunicação do Android são externas para o Microsoft 365 e devem ser concluídas para que você possa criar o conector no centro de conformidade.

- Solicite o [serviço arquivador Android de Telemensagem](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) e obtenha uma conta de administração válida para sua organização. Você precisará entrar nessa conta ao criar o conector.

- Registre todos os usuários que exigem o serviço arquivador Android na conta de Telemensagem. Ao registrar usuários, certifique-se de usar o mesmo endereço de email usado para a conta do Microsoft 365.

- Instale e ative o aplicativo Archiver de mensagens do Android nos telefones celulares de seus funcionários.

- O usuário que cria um conector do Archiver para Android deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online. Isso é necessário para adicionar conectores na página **conectores de dados** no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

## <a name="create-an-android-archiver-connector"></a>Criar um conector de arquivador Android

A última etapa é criar um conector do Archiver para Android no centro de conformidade do Microsoft 365. O conector usa as informações que você fornece para se conectar ao site de Telemensagem e transferir a comunicação Android para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **conectores de dados**  >  **Archiver do Android**.

2. Na página descrição do produto do **arquivo morto do Android** , clique em **Adicionar conector**.

3. Na página **termos de serviço** , clique em **aceitar**.

4. Na página **logon na Telemensagem** , em etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Avançar**.

   - **Nome de usuário:** O nome de usuário de sua mensagem.

   - **Senha:** Sua senha de Telemensagem.

5. Depois que o conector é criado, feche a janela pop-up e clique em **Avançar**.

6. Na página **mapeamento de usuário** , habilite mapeamento automático de usuário e clique em **Avançar**. Caso você precise de mapeamento personalizado, carregue um arquivo CSV e clique em **Avançar**.

7. Revise suas configurações e clique em **concluir** para criar o conector.

8. Vá até a guia conectores na página **conectores de dados** para ver o andamento do processo de importação para o novo conector.

## <a name="known-issues"></a>Problemas conhecidos

- No momento, não há suporte para importar anexos ou itens com mais de 10 MB. O suporte para itens maiores estará disponível em uma data posterior.
