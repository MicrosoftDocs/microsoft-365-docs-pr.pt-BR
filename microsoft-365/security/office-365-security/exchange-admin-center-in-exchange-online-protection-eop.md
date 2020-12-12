---
title: Centro de administração do Exchange no EOP autônomo
f1.keywords:
- NOCSH
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
description: Saiba mais sobre a interface de gerenciamento da Web no proteção autônoma do Exchange Online (EOP).
ms.openlocfilehash: fc76ecd6dafcf9453a0c6de14917c96c950f8370
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659661"
---
# <a name="exchange-admin-center-in-standalone-eop"></a>Centro de administração do Exchange no EOP autônomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


O centro de administração do Exchange (Eat) é um console de gerenciamento baseado na Web para o proteção do Exchange Online (EOP) autônomo.

Procurando a versão do Exchange Online deste tópico? Confira [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

## <a name="open-the-eac-in-eop"></a>Abra o Eat no EOP

Clientes autônomos do EOP podem acessar o Eat usando os seguintes métodos:

- **No centro de administração do Microsoft 365**:

  1. Vá para <https://admin.microsoft.com> e clique em **Mostrar tudo**.

     ![Clique em Mostrar tudo no centro de administração do Microsoft 365](../../media/m365-center-show-all.png)

  2. Na seção **centros de administração** que aparece, clique em **todos os centros de administração**.

     ![Clique em todos os centros de administração no centro de administração do Microsoft 365](../../media/m365-center-select-all-admin-centers.png)

  3. Na página **todos os centros de administração** que aparece, clique em **proteção do Exchange Online**.

- Ir diretamente para `https://admin.protection.outlook.com/ecp/` .

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a>Elementos de interface do usuário comuns no Eat no EOP

Esta seção descreve os elementos da interface do usuário encontrados no EAC.

![O centro de administração do Exchange no Exchange Online Protection](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a>Painel de recursos

Este é o primeiro nível de navegação para a maioria das tarefas que você executará no EAC. O painel de recursos é organizado por áreas de recursos.

- **Destinatários**: Este é o local em que você exibirá grupos e contatos externos.

- **Permissões**: Este é o local em que você gerenciará funções de administrador.

- **Gerenciamento de conformidade**: aqui você encontrará o relatório do grupo de funções de administrador e o relatório de log de auditoria do administrador.

- **Proteção**: aqui você pode gerenciar políticas Antimalware, a política de filtro de conexão padrão e o DKIM.

  > [!NOTE]
  > Você deve gerenciar políticas antimalware e a política de filtro de conexão padrão no centro de conformidade do & de segurança. Para obter mais informações, consulte [Configure anti-malware Policies in EOP](configure-anti-malware-policies.md) e [Configure Connection Filtering in EOP](configure-the-connection-filter-policy.md).

- **Fluxo de email**: aqui você gerenciará as regras de fluxo de emails (também conhecidas como regras de transporte), domínios aceitos e conectores, bem como onde você pode ir para executar o rastreamento de mensagens.

- **Híbrido**: Este é o local onde você pode executar o [Assistente de configuração híbrida](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)e onde é possível instalar o [módulo do PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).

### <a name="tabs"></a>Guias

As guias são seu segundo nível de navegação. Cada uma das áreas de recursos contém várias guias, cada uma representando um recurso.

### <a name="toolbar"></a>Barra de ferramentas

Ao clicar na maioria das guias, você verá uma barra de ferramentas. A barra de ferramentas possui ícones que realizam ações específicas, A tabela a seguir descreve os ícones e suas ações.

****

|Ícone|Nome|Action|
|---|---|---|
|![Ícone Adicionar](../../media/ITPro-EAC-AddIcon.gif)|Adicionar, Novo|Use esse ícone para criar um novo objeto. Alguns desses ícones têm uma seta para baixo associada, na qual é possível clicar para exibir objetos adicionais que você pode criar.|
|![Ícone de edição](../../media/ITPro-EAC-EditIcon.gif)|Editar|Use esse ícone para editar um objeto.|
|![Excluir ícone](../../media/ITPro-EAC-DeleteIcon.gif)|Excluir|Use esse ícone para excluir um objeto. Alguns ícones excluídos têm uma seta para baixo na qual é possível clicar para mostrar opções adicionais.|
|![Ícone Pesquisar](../../media/ITPro-EAC-.gif)|Pesquisar|Use esse ícone para abrir uma caixa de pesquisa na qual é possível digitar a frase de pesquisa para um objeto que você deseja encontrar.|
|![Ícone Atualizar](../../media/ITPro-EAC-RefreshIcon.gif)|Atualizar|Use essa opção para atualizar a exibição de lista.|
|![Ícone Mais opções](../../media/ITPro-EAC-MoreOptionsIcon.gif)|Mais opções|Use esse ícone para ver mais ações que podem ser realizadas para os objetos dessa guia. Por exemplo, em **Destinatários \> Usuários**, um clique neste ícone mostra a opção para executar uma **Pesquisa Avançada**.  |
|![Ícone Seta para cima](../../media/ITPro-EAC-UpArrowIcon.gif)![Ícone Seta para baixo](../../media/ITPro-EAC-DownArrowIcon.gif)|Seta para cima e seta para baixo|Use esses ícones para mover a prioridade de um objeto para cima ou para baixo.|
|![ícone Remover](../../media/ITPro-EAC-RemoveIcon.gif)|Remover|Use esse ícone para remover objetos de uma lista.|
|

### <a name="list-view"></a>Exibição de Lista

Ao selecionar uma guia, na maioria dos casos, você verá uma exibição de lista. O limite visualizável com o modo de exibição em lista do EAC é de aproximadamente 10.000 objetos. Além disso, a paginação está incluída, para que você possa paginar os resultados.

### <a name="details-pane"></a>Painel de Detalhes

Quando você seleciona um objeto na exibição de lista, informações sobre esse objeto são exibidas no painel de detalhes. Em alguns casos, o painel de detalhes inclui tarefas de gerenciamento.

### <a name="me-tile-and-help"></a>Bloco Eu e Ajuda

O bloco **Eu** permite sair do EAC e entrar como um usuário diferente. No  ![ menu suspenso do ícone ajuda da ajuda ](../../media/ITPro-EAC-HelpIcon.gif) , você pode executar as seguintes ações:

- **Ajuda**: clique ![ no ícone ajuda ](../../media/ITPro-EAC-HelpIcon.gif) para exibir o conteúdo da ajuda online.
- **Feedback**: deixar comentários.
- **Comunidade**: poste uma pergunta para localizar respostas nos fóruns da Comunidade.
- **Desabilitar bolha de ajuda**: a bolha de ajuda exibe a ajuda contextual para os campos quando você cria ou edita um objeto. Você pode desativar a bolha de Ajuda ou ativá-la se tiver sido desabilitada.
- **Show Command Logging**: uma nova janela é aberta e mostra os comandos equivalentes do PowerShell com base no que você configurou no Eat.

## <a name="supported-browsers"></a>Navegadores com suporte

Para ter a melhor experiência ao usar o EAC, recomendamos que você sempre use os navegadores, clientes do Office e aplicativos mais recentes. Também recomendamos que você instale as atualizações de software quando elas estiverem disponíveis. Para obter mais informações sobre os navegadores e requisitos de sistema suportados para o serviço, consulte [System Requirements for Office](https://products.office.com/office-system-requirements).

## <a name="supported-languages"></a>Idiomas compatíveis

Os seguintes idiomas têm suporte e estão disponíveis para o Eat no EOP autônomo.

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
