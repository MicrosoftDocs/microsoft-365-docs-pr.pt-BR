---
title: Gerenciar pessoas de interesse em investigações de dados (prévia)
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
description: Saiba como gerenciar pessoas de interesse para criar o escopo de suas informações de pesquisa ou de exibição, como os logs de contato, local e atividade.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 85f6bdbe7a0602f8ce0038a4aca912896d5c2079
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528167"
---
# <a name="manage-people-of-interest-in-data-investigations-preview"></a>Gerenciar pessoas de interesse em investigações de dados (prévia)

As investigações de dados geralmente envolvem pessoas de interesse. Normalmente, elas são pessoas que possuem dados incorretos, confidenciais ou mal-intencionados que você está investigando ou tentando corrigir. Em **investigações de dados (prévia)**, você pode adicioná-los para descobrir suas fontes de dados a serem usadas no escopo da pesquisa ou exibir informações adicionais, como o contato, o local e os logs de atividade. 


## <a name="add-people-of-interest"></a>Adicionar pessoas de interesse

Na guia **pessoas de interesse** , você pode adicionar pessoas de interesse e descobrir suas fontes de dados, como caixas de correio do Exchange ou o site do onedrive for Business, que você pode usar para fazer o escopo da pesquisa. Quando o escopo é reduzido por pessoas de interesse, as pesquisas são mais precisas e exatas porque a ferramenta reprocessa quaisquer dados não indexados, como imagens ou tipos de arquivo não suportados. Você também pode ver as informações de contato, as informações de local e os logs de atividades que você pode usar para iniciar comunicações ou investigar ainda mais suas atividades. 

Para adicionar pessoas de interesse a uma investigação:

1. Na página **investigações de dados (visualização)** , vá para sua investigação.
 
2. Depois de selecionar uma investigação, vá para a guia **pessoas de interesse** e clique em **+ adicionar pessoas de interesse**. 
 
3. Escolha as pessoas que você deseja adicionar à investigação. Você pode começar digitando para pesquisar e selecionar os usuários do Azure Active Directory da sua organização.
 
4. Depois de finalizar a lista de pessoas de interesse, clique em **Avançar** para mapear suas fontes de dados. 

5. Opcion Para cada pessoa, selecione **Exchange** para adicionar a caixa de correio principal do Exchange da pessoa e o **onedrive** para adicionar o site principal do onedrive for Business da pessoa.

6. Opcion Clique em **Avançar** para adicionar outras fontes de dados que você deseja associar às pessoas de seu interesse.

7. Opcion Selecione **Atualizar** para atribuir locais de conteúdo, como caixas de correio, sites e equipes a uma pessoa. 

8. Opcion No submenu:
   
    -  **Caixas de correio do Exchange** -clique em **escolher usuários, grupos ou equipes** e, em seguida, clique em **escolher usuários, grupos ou equipes** novamente. Para adicionar mais caixas de correio, use a caixa de pesquisa para localizar caixas de correio de usuários e grupos de distribuição. Você também pode adicionar caixas de correio usadas para armazenar um grupo do Microsoft 365 ou uma informação da equipe da Microsoft. Marque a caixa de seleção usuário, grupo, equipe, clique em **escolher**e em **concluído**.

        > [!NOTE]
        > Ao clicar em escolher usuários, grupos ou equipes para especificar caixas de correio, o seletor de caixa de correio exibido estará vazio. Isso foi desenvolvido para melhorar o desempenho. Para adicionar pessoas a esta lista, digite um nome (no mínimo 3 caracteres) na caixa de pesquisa.
     
     - **Sites do SharePoint** -clique em **escolher sites** e clique em **escolher sites** novamente para especificar sites adicionais do SharePoint e do onedrive for Business que você deseja adicionar a uma pessoa. Você também pode adicionar a URL do site do SharePoint para um grupo do Microsoft 365 ou uma equipe da Microsoft. Digite a URL de cada site que você deseja atribuir. Clique em **escolher**e em **concluído**.
     - **Microsoft Teams** – clique em **escolher equipes** e, em seguida, clique em **escolher equipes** novamente para exibir uma lista de grupos do Microsoft Team dos quais a pessoa é membro de hoje. Selecione as equipes que você deseja adicionar à pessoa. Depois de selecionado, o sistema identificará automaticamente & selecionar o site do SharePoint associado e a caixa de correio de grupo associados a essa equipe da Microsoft. Clique em **escolher**e em **concluído**.
        
      > [!NOTE]
      > Para adicionar outras Teams da Microsoft, você precisará adicionar separadamente a caixa de correio e o site do SharePoint, conforme mostrado acima.

Depois de concluir o mapeamento de fontes de dados para pessoas de interesse, você poderá ver o resumo do total de caixas de correio, sites e equipes que você acabou de adicionar. Se você mapear outras fontes de dados para pessoas de interesse e escopo sua pesquisa por pessoas de interesse, o mapeamento de documentos para pessoas de interesse persistirá durante a investigação, facilitando a organização de evidências ou geração de relatórios por pessoas de interesse. 

## <a name="view-additional-people-of-interest-information"></a>Exibir outras pessoas de informações de interesse

Na guia **pessoas de interesse** , clique em uma pessoa que você adicionou. Em um submenu, você verá:

- Informações de contato

  - **Nome para exibição**: o nome da pessoa exibida no catálogo de endereços. Normalmente, essa é a combinação de nome, inicial do meio e sobrenome.
  - **Mail/SMTP**: o endereço SMTP da pessoa, por exemplo, Jeff@contoso.onmicrosoft.com.  
  - **Título**: título do trabalho.
  - **Departamento**: o nome do departamento no qual a pessoa trabalha.
  - **Gerente**: gerente da pessoa. O gerente recebe qualquer comunicação de escalonamento para esta pessoa.
  
- Informações de local

  - **Cidade**: a cidade na qual a pessoa está localizada.
  - **Estado**: o estado ou província no qual a pessoa está localizada.
  - **País/região**: o país/região em que a pessoa está localizada; por exemplo, "US" ou "ru".
  - **Office**: o local da pessoa na empresa.

- Status de processamento

  - **Status de indexação**: status da indexação profunda das fontes de dados
  - **Hora da última atualização de indexação**: Timestamp de quando o trabalho de indexação profunda foi disparado pela última vez.
  - **Fontes de dados**: mostra a contagem de caixas de correio, sites e equipes mapeadas para a pessoa

- Atualizar índice
    - Você pode reindexar as fontes de dados dessa pessoa. 

- Exibir atividade 

    - Você pode exibir e pesquisar logs de atividades do usuário. Para obter mais informações, consulte [Exibir pessoas de interesse atividade](view-people-of-interest-activity.md) 
