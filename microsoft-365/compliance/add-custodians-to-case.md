---
title: Adicionar responsáveis a uma ocorrência de descoberta eletrônica avançada
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
description: Saiba como usar a ferramenta de gerenciamento de responsáveis interna na descoberta eletrônica avançada para coordenar seus fluxos de trabalho e identificar fontes de dados relevantes em um caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: adf5df3bba1956ab1bb658590c1fcf9d4f5a814d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818608"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>Adicionar responsáveis a uma ocorrência de descoberta eletrônica avançada

Use a ferramenta interna de gerenciamento de responsáveis em descoberta eletrônica avançada para coordenar seus fluxos de trabalho em torno do gerenciamento de responsáveis e pela identificação de fontes de dados relevantes, custodial, associadas a um caso. Quando você adiciona um profissional, o sistema pode identificar e colocar automaticamente uma retenção em sua caixa de correio do Exchange e na conta do OneDrive for Business. Durante o processo de descoberta de sua investigação, você também pode identificar outras fontes de dados (como caixas de correio, sites ou equipes) que um objectacessou ou contribuiu. Nessa situação, você pode usar a ferramenta de gerenciamento de responsáveis para associar essas fontes de dados a um determinado funcionário. Depois de adicionar os responsáveis a um caso e associar outra fonte de dados a eles, você pode preservar rapidamente os dados e Pesquisar os dados do custodial.

Use o fluxo de trabalho a seguir para adicionar e gerenciar os responsáveis em casos de descoberta eletrônica avançada. 

![Guia gerenciamento de responsáveis](../media/CustodianMgtPage.png)

## <a name="make-sure-you-have-the-necessary-permissions"></a>Verifique se você tem as permissões necessárias

Para adicionar os responsáveis a um caso, você deve ser membro do grupo de função Gerenciador de descoberta eletrônica. Isso fornecerá as permissões necessárias para adicionar os responsáveis a um caso e colocará uma retenção nas fontes de dados do custodial.


## <a name="step-1-add-potential-custodians"></a>Etapa 1: Adicionar possíveis responsáveis

A primeira etapa é identificar e adicionar os responsáveis à ocorrência.

1. Na home page de **descoberta eletrônica avançada** , clique na ocorrência à qual você deseja adicionar os responsáveis. 
 
2. Clique na guia **responsáveis** e, em seguida, clique em **+ Adicionar responsáveis**.

3. Encontre os responsáveis a adicionar à ocorrência. Digite a primeira parte do nome de uma pessoa para exibir os usuários do Azure Active Directory da sua organização. Quando encontrar a pessoa correta, clique em seu nome para adicioná-la à lista.

   ![Identificar possíveis responsáveis](../media/AddCustodianStep1.png)
 
4. Depois de adicionar todos os responsáveis relevantes, clique em **Avançar** para selecionar as fontes de dados principais dos responsáveis.
  
## <a name="step-2-select-custodian-data-sources"></a>Etapa 2: selecionar fontes de dados de responsáveis

Após adicionar os responsáveis, a ferramenta de responsáveis ajudará você a identificar as fontes de dados principais pertencentes a cada um dos responsáveis. Esses locais de dados são a caixa de correio do Exchange e a conta do OneDrive. 

Para identificar as fontes de dados de responsáveis: 

1. Para selecionar a caixa de correio do Exchange para todos os responsáveis, marque a caixa de seleção **Exchange** na parte superior da coluna. Em seguida, você pode desmarcar a caixa de seleção de qualquer determinado membro para remover uma caixa de correio como um local do custodial. Como alternativa, você pode deixar a caixa de seleção **Exchange** na parte superior da coluna desmarcada e, em seguida, marcar a caixa de seleção para os responsáveis individuais. 
 
   ![Selecionar fontes de dados do custodial](../media/AddCustodianStep2.png)
 
2. Repita a mesma coisa para as contas do OneDrives dos responsáveis. 

    Depois que você seleciona as fontes de dados do responsáveis, o sistema tenta automaticamente identificar e verificar essas fontes de dados e, em seguida, as adiciona à caixa como fontes de dados associadas aos responsáveis.
 
4. Clique em **Avançar** para iniciar a associação de fontes de dados adicionais aos responsáveis no caso.

## <a name="step-3-associate-additional-data-sources-to-a-custodian"></a>Etapa 3: associar fontes de dados adicionais a um funcionário

Dependendo do caso em que você está investigando, talvez também seja necessário Pesquisar (e preservar o conteúdo) em caixas de correio que um determinado participante possa ter acessado, os grupos do Microsoft 365 aos quais um Objecté membro do no momento ou sites que um responsáveis também tenha acessado. Além das fontes de dados dos responsáveis principais que você especificou na etapa anterior, você também pode associar outras fontes de dados da Microsoft a um funcionário no caso. 

Para mapear caixas de correio, sites ou equipes para um determinado local:

1. Na página **selecionar fontes de dados adicionais** , clique em **Adicionar** na linha para os responsáveis específicos. 
  
   ![Mapear fontes de dados adicionais](../media/AddCustodianStep3.PNG)

2. Na página do menu suspenso, você pode especificar uma fonte de dados de qualquer um dos seguintes serviços:
  
   -  **Email do Exchange** -clique em **escolher usuários, grupos ou equipes** e, em seguida, clique em **escolher usuários, grupos ou equipes** novamente. Use a caixa Pesquisar para localizar caixas de correio para associar aos responsáveis. Para especificar as caixas de correio a serem atribuídas aos responsáveis selecionados, use a caixa de pesquisa para localizar caixas de correio de usuário e grupos de distribuição. Você também pode atribuir a caixa de correio associada a um grupo do Microsoft 365 ou a uma equipe da Microsoft. Marque a caixa de seleção usuário, grupo, equipe, clique em **escolher**e em **concluído**.

        > [!NOTE]
        > Ao clicar em escolher usuários, grupos ou equipes para especificar caixas de correio, o seletor de caixa de correio exibido estará vazio. Isso foi desenvolvido para melhorar o desempenho. Para adicionar uma caixa de correio a essa lista, digite um nome ou alias (no mínimo 3 caracteres) na caixa de pesquisa.
     
     - **Sites do SharePoint** -clique em **escolher sites** e clique em **escolher sites** novamente para exibir uma lista de sites do SharePoint em sua organização. Para associar um site ao funcionário, você pode selecionar um site na lista ou pode digitar a URL de um site diferente ou um site associado a um grupo do Microsoft 365, Microsoft Team ou uma conta do OneDrive.
     
     - **Teams** – clique em **escolher equipes** e, em seguida, clique em **escolher o Teams** novamente para exibir uma lista de Microsoft Teams que os responsáveis atualmente são membros. Selecione as equipes que você gostaria de adicionar a seus responsáveis. Depois de selecionado, o sistema identificará automaticamente & selecionar o site do SharePoint associado e a caixa de correio de grupo associados a essa equipe da Microsoft. Clique em **escolher**e em **concluído**.

       ![Mapear fontes de dados](../media/AddCustodianStep4.PNG)
        
      > [!NOTE]
      > Para associar uma equipe adicional a um funcionário, você precisa adicionar separadamente a caixa de correio e o site associados à equipe usando os locais **email do Exchange** e **sites do SharePoint** .

Após concluir a associação de fontes de dados adicionais aos responsáveis, você poderá exibir o número total de caixas de correio, sites e equipes associados a cada um na **página selecionar fontes de dados adicionais**. Depois de finalizar as fontes de dados relevantes para um determinado, essa associação será mantida e usada durante os estágios de coleta, processamento e revisão no fluxo de trabalho de descoberta eletrônica.

## <a name="step-4-place-custodians-on-hold"></a>Etapa 4: colocar os responsáveis em espera

Depois de finalizar os responsáveis e as fontes de dados a serem adicionados ao caso, você pode, opcionalmente, colocar alguns ou todos os responsáveis em espera. Quando você coloca um bloqueador, todo o conteúdo de todos os locais de conteúdo associados aos responsáveis é preservado até que você remova a retenção ou libere os responsáveis da retenção. Em alguns casos, talvez você queira adicionar os responsáveis por um caso sem colocá-los em espera.

Para colocar os responsáveis e as fontes de dados em retenção:

1. Na página **colocar um bloqueio nos responsáveis selecionados** , marque a caixa de seleção **reter** na parte superior da coluna para colocar todos os responsáveis em espera. Você pode desmarcar a caixa de seleção para que todos os responsáveis específicos sejam removidos da isenção. Como alternativa, você pode deixar a caixa de seleção **reter** na parte superior da coluna desmarcada e, em seguida, marcar a caixa de seleção para os responsáveis individuais. 
 
   ![Colocar suspensões](../media/AddCustodianStep5.PNG)

2. Verifique as seleções de retenção de responsáveis e, em seguida, clique em **concluir**.

Se você não colocar uma retenção em um local, os responsáveis e as fontes de dados associadas serão adicionados ao caso, mas o conteúdo dessas fontes de dados não será colocado em espera.

Depois que um Objectfor colocado em espera, uma política de retenção de responsáveis que contenha todas as fontes de custodial será criada automaticamente. Para exibir esta política:

1. Na **Home** Page do caso, clique na guia **isenções** e, em seguida, clique em **CustodianHold-GUID**,  

2. Na página do menu suspenso, clique em **Editar retenção** para exibir todas as fontes de dados do responsáveis que são colocadas em espera.

