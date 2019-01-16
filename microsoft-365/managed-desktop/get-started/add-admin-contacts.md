---
title: Adicionar contatos de administração no portal de administração do Microsoft Desktop gerenciados
description: Diga-nos quem contatar para cada área de foco.
keywords: Serviço Microsoft Managed Desktop, 365 da Microsoft, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 31984609681b6e3b1b6de9996eb8fb0fcf6f5624
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864858"
---
# <a name="add-admin-contacts-in-microsoft-managed-desktop-admin-portal"></a>Adicionar contatos de administração no portal de administração de área de trabalho gerenciada da Microsoft

Há várias maneiras que o serviço do Microsoft Desktop gerenciados se comunica com os clientes. Para simplificar a comunicação e certifique-se de que estamos verificando com os contatos recomendados, você precisará fornecer um conjunto de contatos de admin. As operações de TI de área de trabalho do Microsoft gerenciados contatará essas pessoas para obter ajuda a resolver problemas para seu locatário. 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Acesso ao Active Directory para o portal de administração de área de trabalho gerenciada do Microsoft Azure

Portal de administração de área de trabalho gerenciada do Microsoft requer que as pessoas a acessar o portal tenham uma destas funções do Azure Active Directory (AD):
- Administrador global
- Administrador de serviço Intune
- Administrador de faturamento
- Administrador de suporte de serviço

O Administrador Global deve ser aquele que se inscrevam o cliente de área de trabalho gerenciada do Microsoft.  Todas as cinco funções têm o mesmo acesso dentro do portal de administração para iniciar e exibir tarefas.  Para obter mais informações sobre como atribuir essas funções no Azure AD, consulte [permissões de função de administrador no Windows Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). 

## <a name="admin-contact-focus-areas"></a>Áreas de foco de contato do administrador

Contatos de administração devem ser melhor pessoa ou grupo que pode responder perguntas e tomar decisões para áreas de foco diferentes.  Operações de área de trabalho do Microsoft gerenciados contatará esses contatos Admin para questões envolvendo solicitações de suporte arquivadas pelo cliente.  Esses contatos Admin receberá notificações novas mensagens e atualizações de solicitação de suporte.  Nessas áreas incluem:

Área de foco | Para fazer perguntas sobre
--- | ---
Aplicativos | App empacotamento de solução de problemas
Dispositivos | Integridade do dispositivo, solução de problemas com dispositivos Microsoft Desktop gerenciados
Segurança | Solucionando problemas de segurança com dispositivos Microsoft Desktop gerenciados
Outro | Para problemas não cobertos pelos outras áreas

Quem quiser para essas necessidades contatos tenham o conhecimento e a autoridade para tomar decisões para o seu ambiente de área de trabalho do Microsoft gerenciados. Quando você integrado do Microsoft gerenciado ambiente de área de trabalho, você será solicitado a adicionar contatos à sua assistência técnica e a segurança local. 

Contatos de administrador são necessários quando você [Enviar uma solicitação de suporte](../working-with-managed-desktop/support.md). Você precisará ter um contato de administrador para a área de foco da solicitação de suporte. 

**Para adicionar contatos de admin**

1.  Entre no [portal de administração do Microsoft Desktop gerenciados](http://aka.ms/mwaasportal). 

2.  Em **suporte**, selecione **os contatos de Admin**. 

    ![Menu de suporte, contatos de Admin](images/admincontacts.png)

3. Selecione **Adicionar**.

    ![Botão Adicionar portal de administração](images/adminadd.png)

4.  Selecione uma **área de foco** e insira as informações do contato. 

    ![a lista de áreas de foco](images/areaoffocus.png)

5. Repita para cada área de foco. 

