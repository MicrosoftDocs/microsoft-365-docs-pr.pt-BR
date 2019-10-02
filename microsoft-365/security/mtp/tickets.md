---
title: Criar e acompanhar tíquetes por meio do ServiceNow
description: A central de segurança do Microsoft 365 está sendo aprimorada com a capacidade de criar e controlar de forma nativa as permissões no ServiceNow. Isso permite que os administradores de segurança enviem uma recomendação de Pontuação segura diretamente para o ServiceNow e criem uma permissão.
keywords: segurança, Microsoft 365, M365, Pontuação segura, central de segurança, ServiceNow, tíquetes, tarefas
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b0b8cda81bb6cec3958e7b2a758da191d803a0ed
ms.sourcegitcommit: acf29701bfba3e4843e49a79fde012f3c7a7024a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2019
ms.locfileid: "37350322"
---
# <a name="manage-tickets-through-servicenow"></a>Gerenciar tíquetes pelo ServiceNow

A central de segurança do Microsoft 365 está sendo aprimorada com a capacidade de criar e controlar de forma nativa as permissões no ServiceNow. Isso permite que os administradores de segurança enviem uma ação de melhoria de [Pontuação segura da Microsoft](microsoft-secure-score.md) diretamente para o ServiceNow e crie uma permissão. As permissões de gerenciamento de incidentes e de alterações podem ser criadas.

## <a name="prerequisites"></a>Pré-requisitos

Ter acesso à central de segurança do Microsoft 365 e uma instância do ServiceNow com:  

* Kingston ou versão superior
* Ter credenciais do administrador HI
* Ter privilégios de administrador na instância de fornecedor de destino

O ServiceNow recomenda que os usuários mantenham as configurações da caixa (padrão) em sua instância do ServiceNow.  Ter personalizações pode causar erros ao concluir a lista de verificação de instalação e integração com a central de segurança do Microsoft 365.

## <a name="data-exchange"></a>Troca de dados

Quando você conectar a central de segurança do Microsoft 365 ao ServiceNow, a Microsoft receberá os seguintes dados adicionais:

* Nome da instância do ServiceNow
* ID do cliente do ServiceNow
* Segredo do cliente do ServiceNow
* Tokens de atualização & Access

Quando você cria uma permissão do ServiceNow no centro de segurança do Microsoft 365, os dados a seguir são enviados para o ServiceNow:

* ID de usuário que inicia a criação de tíquete
* Nome da tarefa
* Descrição da tarefa
* Prioridade
* Data de conclusão
* Fonte de recomendação (recomendação do usuário ou recomendação da Microsoft)
* Categoria de recomendação (dispositivos, dados, aplicativos, identidade, infraestrutura)

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>Conectar a central de segurança do Microsoft 365 ao ServiceNow

Navegue até a home page do centro de segurança do Microsoft 365, onde você verá um cartão perguntando se você usa o ServiceNow.

![Você usa o ServiceNow](../images/do-you-use-servicenow-250.png)

A partir daí, você será enviado para a página de configuração do ServiceNow, onde você seguirá as instruções para autorizar o aplicativo do conector 365 da Microsoft.

Ao autorizar a conexão entre o centro de segurança do Microsoft 365 e o ServiceNow, certifique-se de usar o logon e a senha de usuário de integração que você criou nas etapas de instalação e não suas credenciais pessoais.

Depois de seguir as instruções e autorizar a conexão, você pode exibir o status da conexão na página de conexão da central de segurança do Microsoft 365 e na experiência do aplicativo do Microsoft 365 Ticketing Connector. Agora, você está pronto para começar a criar tarefas!

## <a name="create-a-task-and-share-it-to-servicenow"></a>Criar uma tarefa e compartilhá-la para o ServiceNow

Depois que a integração é configurada, você pode criar tarefas do ServiceNow com base em ações específicas de melhoria da Pontuação segura da Microsoft. Vá para qualquer ação de melhoria na pontuação segura no portal da central de segurança do Microsoft 365 e selecione o ícone "compartilhar". Uma das opções de DropDown é o ServiceNow.

![Compartilhamento do ServiceNow em Pontuação segura](../images/servicenow-share.png)

Uma tarefa será gerada onde você pode definir a prioridade e editar o nome, a descrição ou a data de conclusão. Após todos os campos obrigatórios serem preenchidos, você pode enviar a tarefa para o ServiceNow.

A tarefa estará visível no ServiceNow como uma solicitação de alteração de configuração e segurança do Microsoft 365.

## <a name="track-tickets"></a>Controlar ingressos

Depois que as permissões de gerenciamento de alterações e de gerenciamento de incidentes tiverem sido criadas, elas serão exibidas em cartões na home page do centro de segurança do Microsoft 365. A partir desses cartões, você pode criar um tíquete, exibir todos os tíquetes ou gerenciar a configuração do ServiceNow.

![Tíquetes de gerenciamento de alterações do ServiceNow](../images/change-management-375.png)  ![Tíquetes de gerenciamento de incidentes do ServiceNow](../images/incident-management-375.png)

Para reprovisionar ou gerenciar sua integração do ServiceNow no centro de segurança do Microsoft 365, selecione **gerenciar a configuração do servicenow** em qualquer um dos cartões. A partir daí, você pode remover a conexão atual do ServiceNow e personalizar os nomes de estado de permissão.

Com as permissões do ServiceNow visíveis na central de segurança do Microsoft 365, suas tarefas permanecerão em um local onde poderão ser rastreadas e aplicadas junto com seus outros itens do painel de segurança.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="i-am-receiving-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>Estou recebendo um erro na primeira etapa da lista de verificação de instalação (criação de OAuth)

**Mensagem de erro**: a operação de leitura em relação a ' oauth_entity ' do escopo ' x_mioms_m365ticket ' foi recusada devido à política de acesso entre escopos da tabela

Nosso aplicativo presume que qualquer administrador na instância do ServiceNow possa criar e ler entidades OAuth. Esse erro pode ser causado devido a uma personalização na instância do ServiceNow, que restringe quem pode criar/ler entidades OAuth. O ServiceNow recomenda que os usuários mantenham a funcionalidade da caixa (padrão).

Defina as configurações de tabela "registros de aplicativos" como padrão:

* Rótulo = registradores de aplicativos
* Name = oauth_entity
* Acessível a partir de = todos os escopos do aplicativo
* Caixa de seleção pode ler = marcada

**O ServiceNow recomenda que os usuários mantenham a funcionalidade da caixa (padrão).**

### <a name="how-do-i-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>Como validar a entidade OAuth criada para o conector de conformidade de & de segurança do Microsoft 365?

Vá para a tabela registros de aplicativos (menu > registro de aplicativo > OAuth de sistema) no ServiceNow e localize a entidade OAuth criada por você (nome que você atribuiu).

### <a name="how-do-i-validate-the-integration-user-created-in-step-two-of-installation-checklist-for-microsoft-365-security--compliance-connector"></a>Como validar o usuário de integração criado na etapa dois da lista de verificação de instalação para o conector de conformidade & segurança da Microsoft 365?

Vá para a tabela Users (menu > administração de usuário > usuários) no ServiceNow e localize o usuário de integração criado por você (nome que você atribuiu a ele).

Ao autorizar a conexão entre o centro de segurança do Microsoft 365 e o ServiceNow, certifique-se de usar o logon e a senha de usuário de integração que você criou nas etapas de instalação e não suas credenciais pessoais.

### <a name="i-have-completed-the-installation-and-set-up-steps-but-i-am-unable-to-see-the-servicenow-cards-on-the-home-page-and-cannot-see-the-share-icon-in-microsoft-secure-score"></a>Concluí as etapas de instalação e configuração, mas não consigo ver os cartões do ServiceNow na Home Page e não consigo ver o ícone de compartilhamento na pontuação segura da Microsoft

Verifique o status da página de provisionamento, acessando https://security.microsoft.com/ticketProvisioning. Selecione **salvar** e retornar para a página inicial. Os cartões devem ser exibidos.
