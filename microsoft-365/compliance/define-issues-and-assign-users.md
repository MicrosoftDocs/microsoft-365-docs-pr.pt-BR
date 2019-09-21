---
title: Definir problemas e atribuir usuários na descoberta eletrônica avançada do Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 48d37ee7-05bd-4cb8-9723-a8959ad23fbe
description: Saiba como adicionar ou editar um problema, incluindo a atribuição de usuários a ele ou a exclusão de um problema para um caso de descoberta eletrônica na descoberta eletrônica avançada do Office 365.
ms.openlocfilehash: a7dad3cce54a3162cedf3c14e521f5e8fe966acf
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071302"
---
# <a name="define-issues-and-assign-users-in-office-365-advanced-ediscovery"></a>Definir problemas e atribuir usuários na descoberta eletrônica avançada do Office 365

> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Na descoberta eletrônica avançada, um ou mais problemas podem ser definidos em um caso. A definição de problemas permite categorização adicional de tópicos. Ao se conectar a um novo caso, um único problema padrão é fornecido. Você pode editar o nome do problema padrão e atribuir usuários ao problema. 
  
## <a name="adding-or-editing-an-issue-and-assigning-users"></a>Adicionando ou editando um problema e atribuindo usuários

1. Na \> guia **configuração \> de relevância de relevância** selecione **problemas**.
    
    ![Problemas de instalação de relevância](media/dfd8f9ef-b167-4ed9-980e-00ae98a97169.png)
  
2. Para adicionar um problema, clique no ícone * * + * *. A caixa de diálogo **Adicionar problema** é exibida. 
    
    ![Problema de adição de instalação de Relevância](media/c8e94982-139a-472a-b85d-282f2d742046.png)
  
    Para editar um problema, clique no ícone **Editar** . 
    
3. Em **nome do problema**, digite um nome que seja descritivo e significativo para o caso. 
    
4. Em **Descrição**, digite as informações sobre o problema.
    
5. Marque a caixa de seleção **habilitar treinamento simultâneo** para habilitar a opção. Essa configuração permite que vários revisores trabalhem no mesmo problema simultaneamente (em amostras separadas). 
    
6. Em **atribuir usuários a serem emitidos**, na lista **todos os usuários** , selecione um usuário a ser atribuído ao problema e clique na seta voltada para a direita para adicionar o usuário à lista de **usuários selecionados** . Repita conforme necessário. Na janela exibida acima, "admin" é exibido como um usuário selecionado. 
    
    > [!NOTE]
    > A atribuição de usuários a problemas pode ser modificada antes ou depois de um ciclo de treinamento de relevância. 
  
7. Em **usuários selecionados**, na lista suspensa ao lado do nome do usuário selecionado, selecione um dos seguintes modos de amostragem: 
    
  - **Ativado**: os arquivos podem ser exibidos e marcados. Essa é a configuração padrão.
    
  - **Idle**: os arquivos podem ser exibidos; Tagged é opcional.
    
  - **Off**: os arquivos não podem ser exibidos ou marcados.
    
8. Quando terminar de adicionar problemas, clique em **OK**.
    
## <a name="deleting-issues"></a>Problemas de exclusão

Os problemas podem ser excluídos (ou seja, removidos do banco de dados) imediatamente após serem definidos e nenhum trabalho real foi feito para esse problema. 
  
1. Na guia **configuração \> de relevância de relevância** , selecione **problemas**.
    
2. Selecione o problema a ser excluído do banco de dados e clique em **excluir**.
    
3. Uma mensagem de confirmação é exibida. Clique em **Sim** para confirmar. 
    
4. Clique em **OK**.
    
## <a name="see-also"></a>Confira também

[Descoberta Eletrônica Avançada do Office 365](office-365-advanced-ediscovery.md)
  
[Como configurar carregamentos para adicionar os arquivos importados](set-up-loads-to-add-imported-files.md)
  
[Como definir as palavras-chave realçadas e opções avançadas](define-highlighted-keywords-and-advanced-options.md)

