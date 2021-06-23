---
title: Arquivar dados da plataforma CellTrust SL2 para Microsoft 365
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
description: Saiba como configurar e usar um conector de dados SL2 CellTrust para importar e arquivar dados de comunicações móveis.
ms.openlocfilehash: 0929a92978f9b48d40153b3cc7328e5e05b54fd0
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096916"
---
# <a name="archive-data-from-celltrust-sl2-to-microsoft-365-preview"></a>Arquivar dados de CellTrust SL2 para Microsoft 365 (visualização)

O CellTrust SL2 captura dados de comunicações móveis e se integra com as principais tecnologias de arquivamento para atender aos requisitos de descoberta eletrônica para regulamentações como FINRA, HIPAA, FOIA e TCPA. O Conector de Dados SL2 importa itens de comunicação móveis para Microsoft 365. Este artigo descreve o processo de integração do SL2 com Microsoft 365 usando o Conector de Dados SL2 cellTrust para arquivamento. Concluir esse processo supõe que você se inscreveu no serviço SL2 cellTrust e está familiarizado com a arquitetura SL2. Para obter informações sobre SL2, consulte <www.celltrust.com>.

Depois que os dados são importados para caixas de correio de usuário no Microsoft 365, você pode aplicar recursos de conformidade Microsoft 365 como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção Microsoft 365 e conformidade de comunicação. Usar o CellTrust SL2 Data Connector para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-with-the-celltrust-sl2-data-connector"></a>Visão geral do arquivamento com o Conector de Dados SL2 CellTrust

A plataforma SL2 de CellTrust captura dados de comunicação de várias fontes. As fontes de dados SL2 são de pessoa para pessoa (P2P) ou Application-to-Person (A2P). O processo descrito neste artigo pertence apenas a fontes de dados P2P. Para todas as fontes de dados P2P, pelo menos uma parte na colaboração é um usuário SL2 que está inscrito no serviço SL2. A visão geral a seguir explica o processo de uso do Conector de Dados SL2 cellTrust em Microsoft 365.

![Fluxo de trabalho de arquivamento para o serviço SL2 CellTrust](../media/CellTrustSL2ConnectorWorkflow.png)

1. Os usuários SL2 enviam e recebem dados de e para os serviços SL2 na Microsoft Azure nuvem.

2. Sua organização tem um domínio SL2 no ambiente do Serviço de Nuvem SL2 da CellTrust. Seu domínio pode ter uma ou mais unidades organizacionais (OUs). O Serviço de Nuvem SL2 transfere seus dados para uma área altamente segura na plataforma Microsoft Azure, para que seus dados nunca saiam do ambiente Microsoft Azure ambiente. Dependendo do seu plano SL2 (Enterprise, SMB ou Governo), seu domínio é hospedado no Microsoft Azure Global ou Microsoft Azure Government.

3. Depois de criar o Conector de Dados do CellTrust SL2, seu domínio e as OUs (independentemente do plano SL2), comece a enviar dados para Microsoft 365. O feed de dados é estruturado para dar suporte a relatórios com base em fontes de dados, OUs ou no domínio por si só. Como resultado, sua organização precisa de apenas um conector para alimentar todas as fontes de dados para Microsoft 365.

4. O conector cria uma pasta em cada usuário mapeado com uma licença Office 365 nomeada **CellTrust SL2**. Esse mapeamento conecta um usuário do CellTrust SL2 a uma caixa de correio Office 365 usando um endereço de email. Se uma ID de usuário no CellTrust SL2 não tiver nenhuma Office 365, os dados do usuário não serão arquivados.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar um conector

- Verifique se você tem um domínio no ambiente de serviço de nuvem CellTrust SL2. Para obter informações adicionais sobre como obter um domínio SL2 de produção ou avaliação, [Contate CellTrust](https://www.celltrust.com/contact-us/#form).

- Obtenha as credenciais para acessar a conta de administrador do domínio SL2.

- O usuário que cria o conector de dados SL2 cellTrust na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função De exportação de importação de caixa de correio no Exchange Online. Essa função é necessária para adicionar conectores na página **Conectores de** dados no Centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a um grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de funções em Exchange Online".

## <a name="step-1-create-a-celltrust-sl2-connector"></a>Etapa 1: Criar um conector SL2 CellTrust

A primeira etapa é criar um conector de dados no Centro de conformidade do Microsoft 365.

1. Vá até <https://compliance.microsoft.com> e clique **em Conectores de dados** no painel de navegação esquerdo.

2. Na guia **Visão** geral, clique **em Filtrar** e selecione **Por CellTrust** e aplique o filtro.

   ![Configurar filtro para exibir conectores CellTrust](../media/DataConnectorsFilter.png)

3. Clique **em CellTrust SL2 (visualização**).

4. Na página **Descrição do produto CellTrust SL2 (visualização),** clique **em Adicionar conector**.

5. Na página **Termos de serviço,** clique em **Aceitar**.

6. Insira um nome exclusivo que identifique o conector e clique em **Próximo**. O nome que você inserir identificará o conector na página **Conectores de** dados após a criação.

7. Na página **Entrar na sua conta CellTrust,** clique em Entrar em **CellTrust**. Você será redirecionado para o **Portal CellTrust** para Microsoft 365 em uma nova janela do navegador.

## <a name="step-2-select-the-domains-or-ous-to-archive"></a>Etapa 2: Selecionar os domínios ou as OUs para arquivar

A próxima etapa é entrar em uma conta de administrador para seu domínio SL2 CellTrust e selecionar os domínios e as OUs para arquivar Microsoft 365.

1. Na página Conector de **Microsoft 365 CellTrust,** selecione seu ambiente no serviço de nuvem SL2 para exibir uma página de entrada.

   Normalmente, você deve ver uma opção representando seu ambiente. No entanto, se você tiver domínios em mais de um ambiente, verá opções para cada ambiente. Depois de fazer uma seleção, você será redirecionado para a página de logon SL2.

2. Entre com suas credenciais de conta de Administrador de Domínio ou UO.

   Se você entrar como administrador de domínio SL2, verá o nome do seu domínio e das OUs nesse domínio. Se você não tiver OUs, você verá apenas o nome do seu domínio. Se você fizer logoff como Administrador da UO, verá apenas o nome da sua UO.

3. Habilita as unidades de negócios que você deseja arquivar. Selecionar o domínio não selecionará automaticamente as OUs. Você deve habilitar cada UO separadamente para arquivar.

   ![Habilitar OUs para arquivar](../media/EnableCellTrustOUs.png)

4. Quando terminar suas seleções, feche a janela do navegador e retorne para a página do assistente Centro de conformidade do Microsoft 365. Depois de alguns segundos, o assistente avança automaticamente para a próxima etapa de mapeamento de usuários.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

A última etapa é mapear usuários e concluir a instalação do conector no Centro de conformidade do Microsoft 365.

1. Na página **Mapeamento de** usuário, selecione **Habilitar** mapeamento automático do usuário se o endereço de email para usuários for o mesmo no SL2 e Microsoft 365. Caso contrário, você deve carregar manualmente endereços de email de usuário carregando um arquivo CSV que mapeia o endereço SL2 dos usuários para seu endereço Microsoft 365 endereço.

2. Clique **em Próximo,** revise suas configurações e clique em **Concluir** para criar o conector.

   O novo conector é adicionado à lista na página **Conectores de** dados.

## <a name="get-help-from-celltrust"></a>Obter ajuda de CellTrust

Consulte a página Suporte ao Cliente [CellTrust](https://www.celltrust.com/contact-us/#support) para obter detalhes sobre como contatar a CellTrust para obter ajuda para configurar um conector de dados SL2 cellTrust.

## <a name="more-information"></a>Mais informações

- Um administrador de domínio pode configurar um conector para o domínio ou qualquer OUs nesse domínio. Se você usar a conta de Administrador da UO, só poderá configurar um conector para essa OU específica.

- Para concluir com êxito as etapas acima, você deve ter uma licença Microsoft 365 E5 e ter os direitos de Microsoft Office administrador apropriados.

- Para testar o novo conector, envie uma mensagem de texto usando seu aplicativo móvel SL2 ou do portal SL2. Vá para sua Microsoft 365 de correio e abra a pasta **SL2 CellTrust** em sua Caixa de Entrada. Pode levar alguns minutos para as mensagens de texto aparecerem em sua caixa de correio.

- Muitas leis e regulamentos exigem que a comunicação eletrônica seja preservada de forma que, quando solicitada, ela possa ser produzida como evidência. A Descoberta Eletrônica (Descoberta Eletrônica) é usada para cumprir a produção de comunicação eletrônica. Enterprise As soluções de Arquivamento de Informações (EIA) foram projetadas para executar a Descoberta Eletrônica e fornecer recursos como gerenciamento de política de retenção, classificação de dados e supervisão de conteúdo. Microsoft 365 oferece uma solução de retenção de longo prazo para conformidade com os regulamentos e padrões que afetam sua organização.

- O termo *arquivamento* conforme usado neste documento refere-se ao arquivamento no contexto de uso em uma solução Enterprise Arquivamento de Informações (EIA). As soluções do EIA têm recursos de Descoberta Externa que produzem documentos para processos judiciais, litígios, auditorias e investigações. O arquivamento no contexto de backup e restauração usado para recuperação de desastres e continuidade de negócios não é o uso pretendido do termo neste documento.
