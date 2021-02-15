---
title: Configurar um conector para arquivar dados de página da Web no Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados de Captura de Página da Web da Globalnet no Microsoft 365. Esse conector permite arquivar dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros da sua organização.
ms.openlocfilehash: 5d793bea8a22d9908551fff67c9d27afffdf1d86
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619817"
---
# <a name="set-up-a-connector-to-archive-webpage-data"></a>Configurar um conector para arquivar dados de página da Web

Use um conector Globalnet no centro de conformidade do Microsoft 365 para importar e arquivar dados de páginas da Web para caixas de correio do usuário em sua organização do Microsoft 365. A Globalnet fornece um conector de Captura de Página da [Web](https://globanet.com/webpage-capture) que captura páginas da Web específicas (e quaisquer links nessas páginas) em um site específico ou em um domínio inteiro. O conector converte o conteúdo da página da Web em um formato de arquivo PDF, PNG ou personalizado e anexa os arquivos convertidos a uma mensagem de email e, em seguida, importa esses itens de email para as caixas de correio do usuário no Microsoft 365.

Depois que o conteúdo da página da Web é armazenado em caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Descoberta e políticas de retenção e rótulos de retenção. Usar um conector de captura de página da Web para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a manter a conformidade com políticas governamentais e regulamentar.

## <a name="overview-of-archiving-webpage-data"></a>Visão geral dos dados de página da Web de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar o conteúdo da página da Web no Microsoft 365.

![Fluxo de trabalho de arquivamento para dados de página da Web](../media/WebPageCaptureConnectorWorkflow.png)

1. Sua organização trabalha com a fonte da página da Web para configurar e configurar um site de Captura de Página da Web.

2. Uma vez a cada 24 horas, os itens de fontes de página da Web são copiados para o site Globalnet Merge1. O conector também converte e anexa o conteúdo de uma página da Web a uma mensagem de email.

3. O conector de Captura de Página da Web que você cria no centro de conformidade do Microsoft 365, conecta-se ao site Globalnet Merge1 todos os dias e transfere os itens de página da Web para um local seguro de Armazenamento do Azure na nuvem da Microsoft.

4. O conector importa os itens de página da Web convertidos para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do mapeamento automático de usuário, conforme descrito na [Etapa 3.](#step-3-map-users-and-complete-the-connector-setup) Uma subpasta na pasta Caixa de Entrada chamada Captura de Página da **Web** é criada nas caixas de correio do usuário, e os itens da página da Web são importados para essa pasta. O conector faz isso usando o valor da *propriedade Email.* Cada item de página da Web contém essa propriedade, que é preenchida com os endereços de email fornecidos quando você configura o conector de captura de página da Web na [Etapa 2](#step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site).

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta Globalnet Merge1 para conectores da Microsoft. Para criar essa conta, entre em contato com o Suporte [ao Cliente Globalnet.](https://globanet.com/ms-connectors-contact/) Você entrará nessa conta quando criar o conector na Etapa 1.

- Você precisa trabalhar com o suporte globalnet para configurar um formato de arquivo personalizado para converter os itens de página da Web. Para obter mais informações, consulte o Guia do Usuário de Conectores de Terceiros merge1 em 

- O usuário que cria o conector de Captura de Página da Web na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função Importar Exportar Caixa de Correio no Exchange Online. Essa função é necessária para adicionar conectores na página Conectores **de dados** no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a um grupo de funções no Exchange Online. Você pode adicionar a função Importar Exportar Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Importar Exportar Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) as [seções](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Criar grupos de função ou Modificar grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-webpage-capture-connector"></a>Etapa 1: Configurar o conector de captura de página da Web

A primeira etapa é acessar os Conectores de Dados e **criar** um conector para os dados de origem da Página da Web.

1. Vá até [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em Captura de página da Web   >  **conectores de dados.**

2. Na página **Captura de página da Web de** descrição do produto, clique em Adicionar **conector.**

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo.**

5. Entre em sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site"></a>Etapa 2: Configurar o conector de Captura de Página da Web no site Globalnet Merge1

A segunda etapa é configurar o conector de Captura de Página da Web no site Globalnet Merge1. Para obter informações sobre como configurar o conector de captura de página da Web, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf).

Depois que você clicar em Salvar  **& Concluir,** a página de mapeamento do usuário no assistente de conector no centro de conformidade do Microsoft 365 será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: Mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector no centro de conformidade do Microsoft 365, siga as etapas abaixo:

1. Na página **Mapear Captura de Página da Web para usuários do Microsoft 365,** habilita o mapeamento automático de usuários. Os itens de Captura de página da Web incluem uma propriedade chamada *Email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

2. Clique **em Avançar,** revise suas configurações e vá para a página Conectores de dados para ver o progresso do processo de importação do novo conector. 

## <a name="step-4-monitor-the-webpage-capture-connector"></a>Etapa 4: Monitorar o conector de captura de página da Web

Depois de criar o conector de Captura de Página da Web, você pode exibir o status do conector no centro de conformidade do Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na barra de entrada esquerda.

2. Clique na **guia Conectores** e selecione o conector de **Captura de Página** da Web para exibir a página do flyout. Esta página contém as propriedades e informações sobre o conector.

3. Em **Status do Conector com origem,** clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- No momento, não há suporte para a importação de anexos ou itens maiores do que 10 MB. O suporte para itens maiores estará disponível posteriormente.
