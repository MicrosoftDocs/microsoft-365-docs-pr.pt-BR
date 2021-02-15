---
title: Configurar um conector para arquivar a Cisco Jabber em dados do MS SQL no Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados da Cisco Jabber da Globalnet no Microsoft 365. Esse conector permite arquivar dados de fontes de dados de terceiros no Microsoft 365. Depois de arquivar esses dados, você pode usar recursos de conformidade como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros.
ms.openlocfilehash: 2790a29cdfa090372976d78de2e5cc5e5c5ce12e
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620037"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-data"></a>Configurar um conector para arquivar dados da Cisco Jabber

Use um conector Globalnet no centro de conformidade do Microsoft 365 para importar e arquivar dados da plataforma Cisco Jabber para caixas de correio de usuário em sua organização do Microsoft 365. A Globalnet fornece um conector [Cisco Jabber](https://globanet.com/jabber/) configurado para capturar itens do Banco de Dados SQL do Jabber, como mensagens de chat 1:1 e chats de grupo e, em seguida, importar esses itens para o Microsoft 365. O conector recupera dados do Banco de Dados SQL do Cisco Jabber, processa-os e converte o conteúdo da conta cisco Jabber de um usuário em um formato de mensagem de email e importa esses itens para a caixa de correio do usuário no Microsoft 365.

Depois que os dados da Cisco Jabber são armazenados em caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção e rótulos de retenção e conformidade de comunicação. Usar um conector Cisco Jabber para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a manter a conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-cisco-jabber-data"></a>Visão geral do arquivamento de dados da Cisco Jabber

A visão geral a seguir explica o processo de uso de um conector para arquivar dados da Cisco Jabber no Microsoft 365.

![Fluxo de trabalho de arquivamento para dados cisco Jabber](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. Sua organização trabalha com a Cisco para configurar um Cisco Jabber no banco de dados SQL do MS.

2. Uma vez a cada 24 horas, os itens da Cisco Jabber são copiados do Banco de Dados SQL do MS para o site Globalnet Merge1. O conector também converte o conteúdo das mensagens de chat em um formato de mensagem de email.

3. O conector Cisco Jabber que você cria no centro de conformidade do Microsoft 365 conecta-se ao site Globalnet Merge1 todos os dias e transfere os itens para um local de armazenamento seguro do Azure na nuvem da Microsoft.

4. O mapeamento automático do usuário como conector importa itens para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do descrito na [Etapa 3.](#step-3-map-users-and-complete-the-connector-setup) Uma subpasta na pasta Caixa de Entrada chamada Cisco Jabber no **MS SQL** é criada nas caixas de correio do usuário, e os itens da mensagem são importados para essa pasta. O conector determina para qual caixa de correio os itens serão importados usando o valor da *propriedade Email.* Cada item Cisco Jabber contém essa propriedade, que é preenchida com o endereço de email de cada participante.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta Globalnet Merge1 para conectores da Microsoft. Para criar essa conta, entre em contato com o Suporte [ao Cliente Globalnet.](https://globanet.com/ms-connectors-contact/) Você entrará nessa conta quando criar o conector na Etapa 1.

- Configurar um banco de dados SQL do MS para recuperar itens jabber antes de criar o conector na Etapa 1. Você especificará as configurações de conexão para o banco de dados SQL do MS ao configurar o conector Cisco Jabber na Etapa 2. Para obter mais informações, consulte o Guia do Usuário de Conectores [de Terceiros merge1.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)

- O usuário que cria o conector Cisco Jabber na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função Importar Exportar Caixa de Correio no Exchange Online. Essa função é necessária para adicionar conectores na página Conectores **de dados** no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a um grupo de funções no Exchange Online. Você pode adicionar a função Importar Exportar Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Importar Exportar Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) as [seções](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Criar grupos de função ou Modificar grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-cisco-jabber-connector"></a>Etapa 1: Configurar o conector Cisco Jabber

A primeira etapa é  acessar os Conectores de Dados no centro de conformidade do Microsoft 365 e criar um conector para Cisco Jabber nos dados do MS SQL.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados** Cisco  >  **Jabber no MS SQL.**

2. Na página **Descrição do produto Cisco Jabber no MS SQL,** clique **em Adicionar conector.**

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo.**

5. Entre em sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-the-cisco-jabber-connector-on-the-globanet-merge1-site"></a>Etapa 2: Configurar o conector Cisco Jabber no site Globalnet Merge1

A segunda etapa é configurar o Cisco Jabber no conector MS SQL no site Globalnet Merge1. Para obter informações sobre como configurar o Cisco Jabber no conector MS SQL, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

Depois que você clicar em Salvar  **& Concluir,** a página de mapeamento do usuário no assistente de conector no centro de conformidade do Microsoft 365 será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: Mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector no centro de conformidade do Microsoft 365, siga estas etapas:

1. On the **Map Cisco Jabber on MS SQL users to Microsoft 365 users** page, enable automatic user mapping. O Cisco Jabber em itens do MS SQL incluem uma propriedade chamada *Email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

2. Clique **em Avançar,** revise suas configurações e vá para a página Conectores de dados para ver o progresso do processo de importação do novo conector. 

## <a name="step-4-monitor-the-cisco-jabber-connector"></a>Etapa 4: Monitorar o conector Cisco Jabber

Depois de criar o Cisco Jabber no conector MS SQL, você pode exibir o status do conector no centro de conformidade do Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na barra de entrada esquerda.

2. Clique na **guia Conectores** e selecione **o Cisco Jabber no** conector MS SQL para exibir a página do flyout. Esta página contém as propriedades e informações sobre o conector.

3. Em **Status do Conector com origem,** clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- No momento, não há suporte para a importação de anexos ou itens maiores do que 10 MB. O suporte para itens maiores estará disponível posteriormente.
