---
title: Configurar um conector para arquivar dados XSLT/XML no Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados XSLT/XML de Veritas no Microsoft 365. Esse conector permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: 51b05f83c51626bc60dc19b5ec9a63750903281c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163750"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a>Configurar um conector para arquivar dados XSLT/XML

Use um conector Veritas no centro de conformidade do Microsoft 365 para importar e arquivar dados da fonte de página da Web para caixas de correio de usuário em sua organização do Microsoft 365. A Veritas fornece um [conector XSLT/XML](https://globanet.com/xslt-xml) que permite o desenvolvimento rápido de arquivos criados usando XSLT (Extensible Style sheet Language Transformations) para transformar arquivos XML em outros formatos de arquivo (como HTML ou texto) que podem ser importados para o Microsoft 365. O conector converte o conteúdo de um item da fonte XSLT/XML para um formato de mensagem de email e importa o item convertido para caixas de correio do Microsoft 365.

Depois que os dados XSLT/XML são armazenados em caixas de correio de usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Descoberta Eletrônico e políticas de retenção e rótulos de retenção. Usar um conector XSLT/XML para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a permanecer em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-xsltxml-data"></a>Visão geral do arquivamento de dados XSLT/XML

A visão geral a seguir explica o processo de uso de um conector para arquivar dados de origem XSLT/XML no Microsoft 365.

![Fluxo de trabalho de arquivamento para dados XSLT/XML](../media/XSLT-XMLConnectorWorkflow.png)

1. Sua organização trabalha com a fonte XSLT/XML para configurar e configurar um site XSLT/XML.

2. Uma vez a cada 24 horas, as mensagens de chat da fonte XSLT/XML são copiadas para o site Veritas Merge1. O conector também converte o conteúdo em um formato de mensagem de email.

3. O conector XSLT/XML que você cria no centro de conformidade do Microsoft 365, se conecta ao site Veritas Merge1 todos os dias e transfere as mensagens para um local seguro de Armazenamento do Azure na nuvem da Microsoft.

4. O conector importa os itens de mensagem convertidos para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do mapeamento automático do usuário, conforme descrito na Etapa 3. Uma nova subpasta na pasta Caixa de Entrada chamada **XSLT/XML** é criada nas caixas de correio do usuário e os itens de mensagem são importados para essa pasta. O conector faz isso usando o valor da *propriedade Email.* Cada mensagem contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta Veritas Merge1 para conectores da Microsoft. Para criar essa conta, entre em contato com [o Suporte ao Cliente veritas.](https://www.veritas.com/content/support/) Você entrará nessa conta quando criar o conector na Etapa 1.

- O usuário que cria o conector XSLT/XML na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função De importação de importação de caixa de correio no Exchange Online. Essa função é necessária para adicionar conectores na página **Conectores de** dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a um grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-an-xsltxml-connector"></a>Etapa 1: Configurar um conector XSLT/XML

A primeira etapa é acessar os **Conectores** de Dados no centro de conformidade do Microsoft 365 e criar um conector para dados XSLT/XML.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados**  >  **XSLT/XML.**

2. Na página **descrição do produto XSLT/XML,** clique **em Adicionar novo conector**.

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo**.

5. Entre na sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-an-xsltxml-connector"></a>Etapa 2: Configurar um conector XSLT/XML

A segunda etapa é configurar o conector XSLT/XML no site Merge1. Para obter informações sobre como configurar o conector XSLT/XML no site Mesclagem de Veritas1, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf).

Depois de clicar em Salvar &  **Concluir**, a página de mapeamento do usuário no assistente de conector no centro de conformidade do Microsoft 365 será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

1. Para mapear usuários e concluir a configuração do conector no centro de conformidade do Microsoft 365, siga as etapas abaixo:

2. Na página **Mapear usuários XSLT/XML para usuários do Microsoft 365,** habilita o mapeamento automático do usuário. Os itens XSLT/XML incluem uma propriedade chamada *Email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

3. Clique **em Avançar,** revise suas configurações e vá até a página **Conectores** de dados para ver o andamento do processo de importação do novo conector.

## <a name="step-4-monitor-the-xsltxml-connector"></a>Etapa 4: Monitorar o conector XSLT/XML

Depois de criar o conector XSLT/XML, você pode exibir o status do conector no centro de conformidade do Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na nav esquerda.

2. Clique na **guia Conectores** e selecione o **conector XSLT/XML** para exibir a página de sobrevoo. Esta página contém as propriedades e informações sobre o conector.

3. Em **Status do conector com origem**, clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.