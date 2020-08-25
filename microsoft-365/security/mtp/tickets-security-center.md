---
title: Criar e acompanhar tíquetes do ServiceNow no centro de segurança do Microsoft 365
description: Saiba como criar e acompanhar tíquetes no ServiceNow do centro de segurança do Microsoft 365.
keywords: segurança, Microsoft 365, M365, Pontuação segura, central de segurança, ServiceNow, tíquetes, tarefas
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
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
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: bd5bf8533d38337c063acdf0dda073e4961e416a
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867240"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a>Criar e acompanhar tíquetes do ServiceNow no centro de segurança do Microsoft 365

O [centro de segurança do Microsoft 365](overview-security-center.md) foi aprimorado com a capacidade de criar e controlar de forma nativa as permissões no ServiceNow. [Saiba mais sobre o ServiceNow](https://www.servicenow.com/)

Na central de segurança, os administradores de segurança podem enviar uma ação de melhoria de [Pontuação segura da Microsoft](microsoft-secure-score.md) diretamente para o ServiceNow e criar uma permissão. As permissões de gerenciamento de incidentes e de alterações podem ser criadas. Rastreie as permissões na home page da central de segurança e o ServiceNow.

- [**Saiba mais sobre os pré-requisitos, a troca de dados e a solução de problemas**](tickets.md)
- **Gerenciar tíquetes do ServiceNow no centro de conformidade** (em breve)

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>Conectar a central de segurança do Microsoft 365 ao ServiceNow

Navegue até a home page do centro de segurança do Microsoft 365 para ver o cartão de conexão do ServiceNow.

![Você usa o ServiceNow](../../media/do-you-use-servicenow-250.png)

Selecione "conectar ao ServiceNow" para ir para a página de configuração do ServiceNow. Siga as instruções para autorizar o aplicativo conector 365 da Microsoft.

> [!NOTE]
> Antes de autorizar a conexão entre o centro de segurança do Microsoft 365 e o ServiceNow, certifique-se de usar o logon e a senha de usuário de integração que você criou nas etapas de instalação. Não use suas credenciais pessoais.

Depois de seguir as instruções e autorizar a conexão, veja o status da conexão na página conexão do centro de segurança do Microsoft 365 e na experiência do aplicativo do Microsoft 365 Ticketing Connector. Agora você está pronto para começar a criar tarefas!

### <a name="troubleshooting"></a>Solução de problemas

Saiba mais sobre os erros comuns que você pode encontrar no processo de conexão e como atenuá-los, na [seção solução de problemas](tickets.md#troubleshooting).

## <a name="create-a-task-and-share-it-to-servicenow"></a>Criar uma tarefa e compartilhá-la para o ServiceNow

Depois que a integração é configurada, crie tarefas do ServiceNow com base em ações específicas de melhoria da [Pontuação segura da Microsoft](microsoft-secure-score.md) . Vá para qualquer ação de melhoria de Pontuação segura no centro de segurança do Microsoft 365 e selecione **compartilhar**. Uma das opções de DropDown é o ServiceNow.

Uma tarefa é gerada onde você pode definir a prioridade e editar o nome, a descrição ou a data de conclusão. Após todos os campos obrigatórios serem preenchidos, envie a tarefa para o ServiceNow.

A tarefa está visível no ServiceNow como uma solicitação de alteração de configuração e segurança do Microsoft 365.

## <a name="track-tickets"></a>Controlar ingressos

Depois que o gerenciamento de alterações e as permissões de gerenciamento de incidentes tiverem sido criados, eles serão exibidos em cartões na home page do centro de segurança do Microsoft 365. A partir desses cartões, você pode criar um tíquete, exibir todos os tíquetes ou gerenciar a configuração do ServiceNow.

![Tíquetes de gerenciamento de alterações do ServiceNow](../../media/change-management-375.png)  ![Tíquetes de gerenciamento de incidentes do ServiceNow](../../media/incident-management-375.png)

Para reprovisionar ou gerenciar sua integração do ServiceNow no centro de segurança do Microsoft 365, selecione **gerenciar a configuração do servicenow** em qualquer um dos cartões. A partir daí, remova a conexão atual do ServiceNow e personalize os nomes de estado de tíquete.

Com as permissões do ServiceNow visíveis no centro de segurança do Microsoft 365, suas tarefas residem em um local onde elas podem ser rastreadas e aplicadas junto com seus outros itens do painel de segurança.

## <a name="resources"></a>Recursos

- [Saiba mais sobre os pré-requisitos, a troca de dados e a solução de problemas](tickets.md)
- [Classificação de Segurança da Microsoft](microsoft-secure-score.md)