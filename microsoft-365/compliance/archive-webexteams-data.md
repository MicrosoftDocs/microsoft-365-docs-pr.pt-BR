---
title: Configurar um conector para dados de equipes WebEx no Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados do conector de equipes WebEx do Globanet no Microsoft 365. Esse conector permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: 76ea8ebc7ce263cf063e619cc5d794501e79c9c3
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816816"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a>Configurar um conector para arquivar dados de equipes do WebEx

Use um conector Globanet no centro de conformidade da Microsoft 365 para importar e arquivar dados de equipes do WebEx para caixas de correio do usuário na sua organização do Microsoft 365. O Globanet fornece um conector de [equipes WebEx](https://globanet.com/webex-teams/) que é configurado para capturar itens de comunicação do WebEx Teams e importá-los para o Microsoft 365. O conector converte o conteúdo de equipes WebEx, como 1:1 chats, conversas de grupo, conversas de canal e anexos da conta de equipes WebEx de sua organização, para um formato de mensagem de email e, em seguida, importa esses itens para a caixa de correio do usuário no Microsoft 365.

Depois que os dados da equipe WebEx são armazenados nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, descoberta eletrônica, políticas de retenção e rótulos de retenção e conformidade de comunicação. O uso de um conector de equipes WebEx para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

## <a name="overview-of-archiving-webex-teams-data"></a>Visão geral do arquivamento de dados de equipes WebEx

A visão geral a seguir explica o processo de usar um conector para arquivar dados de equipes do WebEx no Microsoft 365.

![Fluxo de trabalho de arquivamento para dados de equipes WebEx](../media/WebexTeamsConnectorWorkflow.png)

1. Sua organização trabalha com o WebEx Teams para configurar e configurar um site de equipe WebEx.

2. Uma vez a cada 24 horas, os itens de equipes WebEx são copiados para o site do Globanet Merge1. O conector também converte os itens da equipe WebEx em um formato de mensagem de email.

3. O conector de equipes WebEx que você cria no centro de conformidade da Microsoft 365, conecta-se ao Globanet Merge1 todos os dias e transfere os itens da equipe WebEx para um local seguro de armazenamento do Azure na nuvem da Microsoft.

4. O conector importa itens para as caixas de correio de usuários específicos usando o valor da propriedade *email* do mapeamento de usuário automático, conforme descrito na [etapa 3](#step-3-map-users-and-complete-the-connector-setup). Uma subpasta na pasta caixa de entrada chamada o **WebEx Teams** é criada nas caixas de correio do usuário e os itens são importados para essa pasta. O conector faz isso usando o valor da propriedade *email* . Cada item de equipes WebEx contém essa propriedade, que é preenchida com o endereço de email de cada participante do item.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta do Merge1 do Globanet para conectores da Microsoft. Para criar essa conta, entre em contato com o [suporte ao cliente Globanet](https://globanet.com/ms-connectors-contact). Você entrará nesta conta quando criar o conector na etapa 1.

- Criar um aplicativo em [https://developer.webex.com/](https://developer.webex.com) para buscar dados da sua conta de equipes do WebEx. Para obter instruções passo a passo sobre como criar o aplicativo, consulte [Merge1 do usuário de conectores de terceiros](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)

   Quando você cria este aplicativo, a plataforma WebEx gera um conjunto de credenciais exclusivas. Essas credenciais são usadas na etapa 2 quando você configura o conector de equipes WebEx no site global Merge1.

- O usuário que cria o conector de equipes WebEx na etapa 1 (e conclui-lo na etapa 3) deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online. Essa função é necessária para adicionar conectores na página **conectores de dados** no centro de conformidade da Microsoft 365. Por padrão, essa função não é atribuída a um grupo de função no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-webex-teams-connector"></a>Etapa 1: configurar o conector de equipes WebEx

A primeira etapa é obter acesso aos **conectores de dados** e configurar o conector de [equipes do WebEx](https://globanet.com/webex-teams/) .

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Data Connectors**  >  **WebEx Teams** .

2. Na página descrição do produto da **equipe WebEx** , clique em **Adicionar conector** .

3. Na página **termos de serviço** , clique em **aceitar** .

4. Insira um nome exclusivo que identifique o conector e clique em **Avançar** .

5. Entre em sua conta do Merge1 para configurar o conector.

## <a name="step-2-configure-the-webex-teams-connector-on-the-globanet-merge1-site"></a>Etapa 2: configurar o conector de equipes WebEx no site do Globanet Merge1

A segunda etapa é configurar o conector de equipes WebEx no site do Merge1. Para obter informações sobre como configurar o conector de equipes do WebEx, consulte [Merge1 de terceiros conectores do usuário](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf).

Depois de clicar em **salvar & concluir** , a página **mapeamento de usuário** no assistente de conector no centro de conformidade da Microsoft 365 é exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector no centro de conformidade do Microsoft 365, siga estas etapas:

1. Na página **mapear usuários do teams WebEx para usuários do Microsoft 365** , habilite o mapeamento automático do usuário. Os itens do teams WebEx incluem uma propriedade chamada *email* , que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

2. Na página **consentimento do administrador** , clique em **fornecer consentimento** . Você será redirecionado para o site da Microsoft. Clique em **aceitar** para fornecer o consentimento.
  
   Sua organização deve dar o consentimento para permitir que o serviço de importação do Office 365 acesse dados de caixa de correio em sua organização. Para fornecer o consentimento do administrador, você deve estar conectado com as credenciais de um administrador global do Microsoft 365 e aceitar a solicitação de consentimento. Se você não estiver conectado como um administrador global, poderá ir para [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e entrar usando as credenciais de administrador global para aceitar a solicitação.

3. Clique em **Avançar** , revise suas configurações e vá para a página **conectores de dados** para ver o andamento do processo de importação para o novo conector.

## <a name="step-4-monitor-the-webex-teams-connector"></a>Etapa 4: monitorar o conector de equipes WebEx

Depois de criar o conector de equipes WebEx, você pode visualizar o status do conector no centro de conformidade da Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **conectores de dados** no painel de navegação esquerdo.

2. Clique na guia **conectores** e selecione o conector de **equipes WebEx** para exibir a página de submenu. Esta página contém as propriedades e as informações sobre o conector.

3. Em **status do conector com origem** , clique no link **baixar log** para abrir (ou salvar) o log de status do conector. Esse log contém informações sobre os dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- No momento, não há suporte para importar anexos ou itens com mais de 10 MB. O suporte para itens maiores estará disponível em uma data posterior.
