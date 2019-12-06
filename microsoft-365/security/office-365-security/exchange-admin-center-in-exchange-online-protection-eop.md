---
title: Centro de administração do Exchange na Proteção do Exchange Online
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: O EAC (Centro de administração do Exchange) é o console de gerenciamento baseado na Web da EOP (Proteção do Exchange Online) da Microsoft.
ms.openlocfilehash: 6ef800b9f440f67d45f3eaa08b4731989fcf2652
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871857"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a>Centro de administração do Exchange na Proteção do Exchange Online

O EAC (Centro de administração do Exchange) é o console de gerenciamento baseado na Web da EOP (Proteção do Exchange Online) da Microsoft.

Procurando a versão do Exchange Server deste tópico? Confira [centro de administração do Exchange no Exchange Server](https://docs.microsoft.com/exchange/architecture/client-access/exchange-admin-center).

Procurando a versão do Exchange Online deste tópico? Confira [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

## <a name="accessing-the-eac"></a>Acessando o EAC

Na maioria dos casos, os clientes do EOP acessarão a Eat através do centro de administração do Microsoft 365. Você encontra um link para a EOP no menu suspenso no bloco **Administrador**, que fica ao lado do bloco **Eu**. Clique no bloco **Administrador** e selecione **Proteção do Exchange Online** no menu suspenso para ir até o EAC.

You can also access the EAC sign in page directly via the following URL: `https://admin.protection.outlook.com/ecp/<companydomain>`. For example, `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`. After specifying your user credentials you will be taken directly into the EAC.

## <a name="common-user-interface-elements-in-the-eac"></a>Elementos da interface do usuário comuns no EAC

Esta seção descreve os elementos da interface do usuário encontrados no EAC.

![EOP-AdminCenter](../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a>Painel de recursos

Este é o primeiro nível de navegação para a maioria das tarefas que você executará no EAC. O painel de recursos é organizado por áreas de recursos.

1. **Destinatários**: aqui você exibirá usuários internos e contatos externos.

2. **Permissões**: Este é o local em que você gerenciará as funções de administrador.

3. **Gerenciamento de conformidade**: aqui você encontrará logs e relatórios de auditoria, como o relatório do grupo de funções de administrador.

4. **Proteção**: aqui você gerenciará a proteção antimalware e antispam para sua organização, além de gerenciar as mensagens em quarentena.

5. **Fluxo de emails**: aqui você gerenciará regras, domínios aceitos e conectores, bem como onde você vai para executar o rastreamento de mensagens.

### <a name="tabs"></a>Guias

As guias são seu segundo nível de navegação. Cada uma das áreas de recursos contém várias guias, cada uma representando um recurso.

### <a name="toolbar"></a>Barra de ferramentas

Ao clicar na maioria das guias, você verá uma barra de ferramentas. A barra de ferramentas possui ícones que realizam ações específicas, A tabela a seguir descreve os ícones e suas ações.

|**Ícone**|**Nome**|**Action**|
|:-----|:-----|:-----|
|![Ícone Adicionar](../media/ITPro-EAC-AddIcon.gif)|Adicionar, Novo|Use esse ícone para criar um novo objeto. Alguns desses ícones têm uma seta para baixo associada, na qual é possível clicar para exibir objetos adicionais que você pode criar.|
|![Ícone de edição](../media/ITPro-EAC-EditIcon.gif)|Editar|Use esse ícone para editar um objeto.|
|![Excluir ícone](../media/ITPro-EAC-DeleteIcon.gif)|Excluir|Use esse ícone para excluir um objeto. Alguns ícones excluídos têm uma seta para baixo na qual é possível clicar para mostrar opções adicionais.|
|![Ícone Pesquisar](../media/ITPro-EAC-.gif)|Pesquisar|Use esse ícone para abrir uma caixa de pesquisa na qual é possível digitar a frase de pesquisa para um objeto que você deseja encontrar.|
|![Ícone Atualizar](../media/ITPro-EAC-RefreshIcon.gif)|Atualizar|Use essa opção para atualizar a exibição de lista.|
|![Ícone Mais opções](../media/ITPro-EAC-MoreOptionsIcon.gif)|Mais opções|Use esse ícone para ver mais ações que podem ser realizadas para os objetos dessa guia. Por exemplo, em **Destinatários \> Usuários**, um clique neste ícone mostra a opção para executar uma **Pesquisa Avançada**.  |
|![Ícone Seta para cima](../media/ITPro-EAC-UpArrowIcon.gif)![Ícone Seta para baixo](../media/ITPro-EAC-DownArrowIcon.gif)|Seta para cima e seta para baixo|Use esses ícones para mover a prioridade de um objeto para cima ou para baixo.|
|![ícone Remover](../media/ITPro-EAC-RemoveIcon.gif)|Remover|Use esse ícone para remover objetos de uma lista.|

### <a name="list-view"></a>Exibição de Lista

Ao selecionar uma guia, na maioria dos casos, você verá uma exibição de lista. O limite visualizável com o modo de exibição em lista do EAC é de aproximadamente 10.000 objetos. Além disso, a paginação está incluída, para que você possa paginar os resultados.

### <a name="details-pane"></a>Painel de Detalhes

Quando você seleciona um objeto na exibição de lista, informações sobre esse objeto são exibidas no painel de detalhes. Em alguns casos, o painel de detalhes inclui tarefas de gerenciamento.

### <a name="me-tile-and-help"></a>Bloco Eu e Ajuda

O bloco **Eu** permite sair do EAC e entrar como um usuário diferente. No menu **suspenso do**![ícone](../media/ITPro-EAC-HelpIcon.gif) ajuda da ajuda, é possível executar as seguintes ações:

1. **Ajuda**: clique ![no ícone](../media/ITPro-EAC-HelpIcon.gif) ajuda para exibir o conteúdo da ajuda online.

2. **Desabilitar bolha de ajuda**: a bolha de ajuda exibe a ajuda contextual para os campos quando você cria ou edita um objeto. Você pode desativar a bolha de Ajuda ou ativá-la se tiver sido desabilitada.

3. **Copyright**: clique neste link para ler o aviso de direitos autorais para o Exchange Online Protection.

4. **Privacidade**: clique para ler a política de privacidade do Exchange Online Protection.

## <a name="supported-browsers"></a>Navegadores com suporte

Para ter a melhor experiência ao usar o EAC, recomendamos que você sempre use os navegadores, clientes do Office e aplicativos mais recentes. Também recomendamos que você instale as atualizações de software quando elas estiverem disponíveis. Para obter mais informações sobre os navegadores e requisitos de sistema compatíveis com o serviço, confira [requisitos de sistema do Office 365](https://go.microsoft.com/fwlink/p/?LinkID=402699).

## <a name="supported-languages-in-eop"></a>Idiomas com suporte na EOP

Os seguintes idiomas têm suporte e estão disponíveis para o Exchange Online Protection.

- Amárico

- Árabe

- Basco (Basco)

- Bengali (Índia)

- Búlgaro

- Catalão

- Chinês (simplificado)

- Chinês (tradicional)

- Croata

- Tcheco

- Dinamarquês

- Holandês

- Holandês

- Inglês

- Estoniano

- Filipino (Filipinas)

- Finlandês

- Francês

- Galego

- Alemão

- Grego

- Gujarati

- Hebraico

- Híndi

- Húngaro

- Islandês

- Indonésio

- Italiano

- Japonês

- Kannada

- Cazaque

- Kiswahili

- Coreano

- Letão

- Lituano

- Malaio (Brunei Darussalam)

- Malaio (Malásia)

- Malaiala

- Marati

- Norueguês (Bokmål)

- Norueguês (Nynorsk)

- Oriá

- Persa

- Polonês

- Português (Brasil)

- Português (Portugal)

- Romeno

- Russo

- Sérvio (cirílico, Sérvia)

- Sérvio (latino)

- Eslovaco

- Esloveno

- Espanhol

- Sueco

- Tâmil

- Telugu

- Tailandês

- Turco

- Ucraniano

- Urdu

- Vietnamita

- Galês


