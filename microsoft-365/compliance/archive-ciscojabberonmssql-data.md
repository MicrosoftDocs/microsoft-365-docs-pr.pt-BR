---
title: Configurar um conector para arquivar o Cisco Jabber em MS SQL dados em Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar o Cisco Jabber no MS SQL dados da Veritas no Microsoft 365. Esse conector permite que você arquive dados de fontes de dados de terceiros em Microsoft 365. Depois de arquivar esses dados, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros.
ms.openlocfilehash: 01899e4142d6e60fb10a101f7af8e9b4143a38c8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764293"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-ms-sql-data"></a>Configurar um conector para arquivar o Cisco Jabber em dados SQL MS

Use um conector Veritas no centro de conformidade Microsoft 365 para importar e arquivar dados da plataforma Cisco Jabber para caixas de correio de usuário em sua Microsoft 365 organização. A Veritas fornece um conector [Cisco Jabber](https://globanet.com/jabber/) configurado para capturar itens do Banco de Dados SQL MS do Jabber, como mensagens de chat 1:1 e chats de grupo e, em seguida, importar esses itens para Microsoft 365. O conector recupera dados do MS do Cisco Jabber Banco de Dados SQL, processa-o e converte o conteúdo da conta Cisco Jabber de um usuário em um formato de mensagem de email e importa esses itens para a caixa de correio do usuário em Microsoft 365.

Depois que os dados do Cisco Jabber são armazenados em caixas de correio de usuário, você pode aplicar Microsoft 365 de conformidade, como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção e rótulos de retenção e conformidade de comunicação. Usar um conector Cisco Jabber para importar e arquivar dados em Microsoft 365 pode ajudar sua organização a permanecer em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-cisco-jabber-data"></a>Visão geral dos dados cisco jabber de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar o Cisco Jabber em MS SQL dados em Microsoft 365.

![Fluxo de trabalho de arquivamento para dados cisco jabber](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. Sua organização trabalha com a Cisco para configurar e configurar um Cisco Jabber no MS Banco de Dados SQL.

2. Uma vez a cada 24 horas, os itens cisco Jabber são copiados do MS Banco de Dados SQL para o site Veritas Merge1. O conector também converte o conteúdo das mensagens de chat em um formato de mensagem de email.

3. O conector Cisco Jabber que você cria no centro de conformidade do Microsoft 365 conecta-se ao site da Mesclagem de Veritas1 todos os dias e transfere os itens para um local seguro do Azure Armazenamento na nuvem da Microsoft.

4. O mapeamento automático do usuário como conector importa itens para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do descrito [na Etapa 3](#step-3-map-users-and-complete-the-connector-setup). Uma subpasta na pasta Caixa de Entrada chamada **Cisco Jabber no MS** SQL é criada nas caixas de correio do usuário e os itens de mensagem são importados para essa pasta. O conector determina para qual caixa de correio importar itens usando o valor da *propriedade Email.* Cada item Cisco Jabber contém essa propriedade, que é preenchida com o endereço de email de cada participante.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta Veritas Merge1 para conectores da Microsoft. Para criar essa conta, entre em contato com [o Suporte ao Cliente veritas.](https://www.veritas.com/content/support/) Você entrará nessa conta quando criar o conector na Etapa 1.

- Configurar um MS Banco de Dados SQL recuperar itens jabber antes de criar o conector na Etapa 1. Você especificará as configurações de conexão para o MS Banco de Dados SQL ao configurar o conector Cisco Jabber na Etapa 2. Para obter mais informações, consulte o Guia do Usuário [Merge1 Third-Party Connectors.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)

- O usuário que cria o conector Cisco Jabber na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função De exportação de importação de caixa de correio no Exchange Online. Essa função é necessária para adicionar conectores na página **Conectores** de dados no Microsoft 365 de conformidade. Por padrão, essa função não é atribuída a um grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de funções em Exchange Online".

## <a name="step-1-set-up-the-cisco-jabber-on-ms-sql-connector"></a>Etapa 1: Configurar o Cisco Jabber no conector de SQL MS

A primeira etapa é acessar os **Conectores** de Dados no centro de conformidade Microsoft 365 e criar um conector para Cisco Jabber em dados SQL MS.

1. Vá até [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados** Cisco  >  **Jabber no MS SQL**.

2. Na página **Cisco Jabber no MS SQL** descrição do produto, clique **em Adicionar conector**.

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo**.

5. Entre na sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-the-cisco-jabber-on-ms-sql-connector-on-the-veritas-merge1-site"></a>Etapa 2: Configurar o Cisco Jabber no conector SQL MS no site Veritas Merge1

A segunda etapa é configurar o Cisco Jabber no conector SQL MS no site Veritas Merge1. Para obter informações sobre como configurar o Cisco Jabber no conector SQL MS, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

Depois de clicar em Salvar &  **Concluir**, a página de mapeamento do usuário no assistente de conector no Microsoft 365 de conformidade será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector no Microsoft 365 de conformidade, siga estas etapas:

1. Na página **Mapear o Cisco Jabber no MS SQL usuários para** Microsoft 365 usuários, habilita o mapeamento automático do usuário. Os itens cisco jabber no MS SQL incluem uma propriedade chamada *Email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um Microsoft 365 usuário, os itens serão importados para a caixa de correio desse usuário.

2. Clique **em Avançar,** revise suas configurações e vá até a página **Conectores** de dados para ver o andamento do processo de importação do novo conector.

## <a name="step-4-monitor-the-cisco-jabber-connector"></a>Etapa 4: Monitorar o conector Cisco Jabber

Depois de criar o Cisco Jabber no conector de SQL MS, você poderá exibir o status do conector no centro de conformidade Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na nav esquerda.

2. Clique na **guia Conectores** e selecione o **Cisco Jabber no conector SQL MS** para exibir a página de sobrevoo. Esta página contém as propriedades e informações sobre o conector.

3. Em **Status do conector com origem**, clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.
