---
title: 'Configurar a compreensão do conteúdo (versão prévia) '
description: Como configurar o Project Cortex.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 5fcc7f78bfc12faae19ce2a3fbc77c4348da01de
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612697"
---
# <a name="set-up-content-understanding-preview"></a>Configurar a compreensão do conteúdo (versão prévia)

> [!Note] 
> O conteúdo deste artigo é para a visualização privada do Project Cortex. [Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).

Os administradores podem usar o centro de administração do Microsoft 365 para configurar e configurar a compreensão do conteúdo. 

Antes da instalação, certifique-se de planejar a melhor maneira de configurar e configurar a compreensão do conteúdo em seu ambiente. Por exemplo, você precisará fazer considerações sobre o seguinte:
- Quais sites do SharePoint você habilitará o processamento de formulários? Todos eles, alguns ou selecionar sites?
- Nome do seu centro de conteúdo e quem é o administrador do site principal?

Um administrador também pode fazer alterações nas configurações selecionadas a qualquer momento após a configuração por meio das configurações de gerenciamento de compreensão do conteúdo no centro de administração do Microsoft 365.


## <a name="requirements"></a>Requisitos 
Você precisa ter permissões de administrador global ou administrador do SharePoint para poder acessar o centro de administração do Microsoft 365 e configurar a compreensão do conteúdo.


## <a name="to-set-up-content-understanding"></a>Para configurar a compreensão do conteúdo

1. No centro de administração do Microsoft 365, selecione **configuração**e, em seguida, exiba a seção de **conhecimento organizacional** .
2. Na seção **conhecimento organizacional** , selecione **automatizar a compreensão do conteúdo**.<br/>

    ![Página de configuração de conhecimento organizacional](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. Na página **automatizar o conteúdo** **, clique em introdução para** orientá-lo no processo de instalação.<br/>

    ![Iniciar a instalação](../media/content-understanding/admin-content-understanding-get-started.png)</br>


4. Na página **Configurar processamento de formulário** , você pode escolher se deseja permitir que os usuários possam usar o Construtor ai para criar modelos de processamento de formulário em bibliotecas de documentos específicas do SharePoint. Uma opção de menu estará disponível na faixa de opções da biblioteca de documentos para **criar um modelo de processamento de formulário** em bibliotecas de documentos do SharePoint na qual ele está habilitado.
 
     Para **quais bibliotecas do SharePoint devem mostrar a opção para criar um modelo de processamento de formulário**, você pode selecionar:</br>
    - **Todas as bibliotecas do SharePoint** para torná-lo disponível para todas as bibliotecas do SharePoint em seu locatário.</br>
    - **Somente as bibliotecas nos sites selecionados**e, em seguida, selecione os sites nos quais você deseja torná-lo disponível.</br>
    - **Nenhuma biblioteca do SharePoint** , se você não quiser disponibilizá-la para nenhum site (você pode alterar isso após a instalação).
</br>

   ![Configurar o processamento de formulários](../media/content-understanding/admin-configforms.png)
</br>

   > [!Note]
   > Habilitar essa configuração em uma biblioteca de documentos do SharePoint não afeta os modelos existentes aplicados à biblioteca ou a capacidade de aplicar modelos de compreensão de documentos a uma biblioteca. 

    
5. Na página **criar centro de conteúdo** , você pode criar um site do centro de conteúdo do SharePoint no qual os usuários podem criar e gerenciar modelos de compreensão de documentos. </br>
    a. Em **nome do site**, digite o nome que você deseja dar ao site do centro de conteúdo.</br>
    b. O **endereço do site** mostrará a URL do seu site, com base no que você selecionou para o nome do site.</br>

    > [!Note] 
    > Embora seja possível selecionar qualquer idioma suportado, observe que o conteúdo entendendo modelos só pode ser criado para o inglês.</br>

      ![Criar centro de conteúdo](../media/content-understanding/admin-cu-create-cc.png)</br>


    Selecione **Avançar**.
6. Na página **concluir e revisar** , você pode examinar a configuração selecionada e optar por fazer alterações. Se estiver satisfeito com suas seleções, selecione **Ativar**.



7. A página **conteúdo de compreensão ativada** será exibida, confirmando que o sistema adicionou suas preferências de processamento de formulário e criando o site do centro de conteúdo. Selecione **Concluído**.

8. Você retornará à página **automatizar o conteúdo de compreensão** . Nessa página, você pode selecionar **gerenciar** para fazer quaisquer alterações nas suas definições de configuração. 

## <a name="see-also"></a>Confira também



  






