---
title: Adicionar custodiantes a um Advanced eDiscovery caso
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba como usar a ferramenta de gerenciamento de custodiante Advanced eDiscovery coordenar seus fluxos de trabalho e identificar fontes de dados relevantes em um caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740338"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>Adicionar custodiantes a um Advanced eDiscovery caso

Use a ferramenta de gerenciamento de custodiante Advanced eDiscovery coordenar seus fluxos de trabalho em torno do gerenciamento de custodiantes e da identificação de fontes de dados relevantes e custodiais associadas a um caso. Quando você adiciona um custodiante, o sistema pode identificar e colocar automaticamente uma suspensão na caixa de correio Exchange e OneDrive for Business conta. Durante o processo de descoberta de sua investigação, você também pode identificar outras fontes de dados (como caixas de correio, sites ou Teams) às quais um custodiante acessou ou contribuiu. Nessa situação, você pode usar a ferramenta de gerenciamento de custodiante para associar essas fontes de dados a um custodiante específico. Depois de adicionar os custodiantes a uma ocorrência e associar outra fonte de dados a eles, você poderá preservar rapidamente os dados e pesquisar os dados custodiantes.

Você pode adicionar e gerenciar custodiantes em Advanced eDiscovery casos em quatro etapas:

1. Identifique os custodiantes.

2. Escolha locais de dados custodiados.

3. Configure as configurações de espera.

4. Revise os custodiantes e conclua o processo.

   [![Guia Fontes no Advanced eDiscovery caso ](../media/AeD-Sources-Tab.png)](../media/AeD-Sources-Tab.png#lightbox)

## <a name="make-sure-you-have-the-necessary-permissions"></a>Certifique-se de ter as permissões necessárias

Para adicionar os custodiantes a um caso, você deve ser membro do grupo de funções do Gerenciador de Descobertas. Isso fornece as permissões necessárias para adicionar os custodiantes a uma ocorrência e colocar uma espera nas fontes de dados de custodiação. Para obter mais informações, confira [Atribuir permissões de Descoberta eletrônica](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).

## <a name="step-1-identify-custodians"></a>Etapa 1: Identificar os custodiantes

1. Acesse e entre com uma conta de usuário que tenha sido atribuída às permissões [https://compliance.microsoft.com](https://compliance.microsoft.com) de Descoberta eDiscovery apropriadas.

2. No painel de navegação esquerdo do Centro de Conformidade do Microsoft 365, clique em **Mostrar tudo** e, a seguir, clique em **Descoberta Eletrônica > Avançada**.

3. Na página **Advanced eDiscovery,** clique na guia **Casos** e selecione o caso ao que deseja adicionar os custodiantes.

4. Clique na **guia Fontes de** dados e clique em Adicionar fonte de **dados** Adicionar  >  **novos custodiantes**.

5. Adicione um ou mais usuários em sua organização como custodiantes ao caso digitando a primeira parte do nome ou alias de uma pessoa. Depois de encontrar a pessoa correta, selecione seu nome para adicioná-la à lista.

## <a name="step-2-choose-custodian-data-locations"></a>Etapa 2: Escolher locais de dados custodiados

Depois de selecionar os custodiantes, o sistema tenta identificar e verificar automaticamente esses usuários e suas fontes de dados. Depois de adicionar os custodiantes à lista, a ferramenta inclui automaticamente a caixa de correio principal e OneDrive conta para cada custodiante. Você pode optar por não incluir essas fontes de dados ao adicionar os custodiantes ao caso.

Além da caixa de correio e da conta OneDrive de um custodiante, você também pode associar outros locais de dados a um custodiante, como um site SharePoint ou uma Equipe da Microsoft de que o custodiante é membro. Isso permite preservar, coletar, analisar e revisar conteúdo em outras fontes de dados associadas aos custodiantes do caso.

Para desmarcar a caixa de correio principal e OneDrive conta de um custodiado:

1. Expanda o custodiante para exibir os locais de dados primários que foram automaticamente associados a cada custodiante.

2. Selecione **Limpar** ao lado de **Caixa** de Correio ou **OneDrive** para remover a caixa de correio ou OneDrive de um custodiante de ser associada como um local de dados para esse custodiante.

   ![Configurar locais para associar a um custodiado](../media/ConfigureCustodianLocations.png)

Para associar outras caixas de correio, sites, Teams ou grupos Yammer a um custodiante específico:

1. Expanda um custodiante para exibir os seguintes serviços para associar locais de dados ao custodiante. Clique **em Editar** ao lado de um serviço para adicionar um local de dados.

   - **Exchange:** use para associar outras caixas de correio ao custodiado. Digite na caixa de pesquisa o nome ou alias (no mínimo três caracteres) de caixas de correio de usuário ou grupos de distribuição. Selecione as caixas de correio a atribuir ao custodiado e clique em **Adicionar**.

   - **SharePoint:** use para associar SharePoint sites ao custodiado. Selecione um site na lista ou procure um site digitando uma URL na caixa de pesquisa. Selecione os sites a atribuir ao custodiado e clique em **Adicionar**.

   - **Teams**: use para atribuir o Microsoft Teams o custodiador é membro atualmente. Selecione as equipes a atribuir ao custodiado e clique em **Adicionar**. Depois de adicionar uma equipe, o sistema identifica e localiza automaticamente o site SharePoint e a caixa de correio de grupo associadas a essa equipe e as atribui ao custodiante.

   - **Yammer:** use para atribuir os grupos Yammer de que o custodiador é membro no momento. Selecione os grupos a atribuir ao custodiado e clique em **Adicionar**. Depois de adicionar uma equipe, o sistema identifica e localiza automaticamente o site SharePoint e a caixa de correio de grupo associadas a esse grupo e atribui-as ao custodiante.

   > [!NOTE]
   > Você pode  usar os seletores de Exchange e SharePoint para associar outras equipes ou grupos de Yammer (de que um custodiante não é membro) a um custodiante.  Para fazer isso, você precisa adicionar a caixa de correio e o site associados a cada equipe ou Yammer grupo.

2. Você pode exibir o número total de caixas de correio, sites, Teams e grupos Yammer atribuídos a cada custodiante expandindo cada custodiante na tabela. Quando você finalizar os locais de dados atribuídos para cada custodiante, essas associações serão mantidas e usadas durante os estágios de coleta, processamento e revisão no fluxo de trabalho Advanced eDiscovery.

3. Depois de adicionar os custodiantes e configurar seus locais de dados, clique em **Próximo** para ir para a página Configurações **de** Espera.  

## <a name="step-3-configure-hold-settings"></a>Etapa 3: Configurar configurações de espera

 Depois de finalizar os custodiantes e seus locais de dados, você pode colocar alguns ou todos os custodiantes em espera. Quando você coloca um custodiante em espera, todo o conteúdo em todos os locais de conteúdo associados ao custodiante é preservado até que você remova a moção ou libere o custodiante da remoção. Em alguns casos, talvez você queira adicionar os custodiantes a um caso sem colocá-los em espera.

Para colocar os custodiantes e fontes de dados em espera:

1. Na página **Configurações de** Espera, você pode aplicar uma responsabilidade a custodiantes individuais selecionando a caixa de seleção na **coluna** De espera.

   Como alternativa, você pode colocar todos os custodiantes em espera selecionando a caixa de seleção **Hold** na parte superior da coluna.

2. Verifique as seleções de espera de custodia e clique em **Próximo**.

   > [!NOTE]
   > Se você não colocar uma responsabilidade em um custodiante, o custodiante e suas fontes de dados associadas serão adicionados ao caso, mas o conteúdo nessas fontes de dados não será preservado pela responsabilidade associada ao caso.

## <a name="step-4-review-the-custodians-and-complete-the-process"></a>Etapa 4: revisar os custodiantes e concluir o processo

Antes de realmente adicionar os custodiantes ao caso, você pode revisar a lista de custodiantes, os locais de dados atribuídos a eles e as configurações de espera.

1. Verifique e revise todas as fontes de dados e a configuração de espera associada a cada custodiante na tabela. Se necessário, volte para as páginas **Identificar custodiante** ou **Manter** para fazer alterações.

2. Clique **em Enviar** para adicionar os custodiantes e seus locais de dados ao caso e aplicar todas as configurações de responsabilidade.

   Os novos custodiantes são adicionados à ocorrência e exibidos na **guia Fontes de** dados.

   [![Custodiantes listados na guia Fontes de dados ](../media/DataSourcesTab.png)](../media/DataSourcesTab.png#lightbox)
