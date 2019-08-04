---
title: Adicionar contatos do administrador no portal de administração de área de trabalho gerenciada da Microsoft
description: Diga-nos quem entrar em contato para cada área de foco.
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 68f5d5cb46d4aa643b1b09f9204b24dea3d77eb1
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390528"
---
# <a name="add-admin-contacts-in-microsoft-managed-desktop-admin-portal"></a>Adicionar contatos do administrador no portal de administração de área de trabalho gerenciada da Microsoft

Há várias maneiras de o serviço Microsoft Managed desktop se comunicar com os clientes. Para simplificar a comunicação e garantir que estamos verificando os melhores contatos, você precisa fornecer um conjunto de contatos de administração. As operações de ti de área de trabalho gerenciada da Microsoft contatarão essas pessoas para resolver problemas de solução de problemas para o seu locatário. 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Acesso do Azure Active Directory para o portal de administração de área de trabalho gerenciada da Microsoft

O portal de administração de área de trabalho gerenciada da Microsoft exige que as pessoas que acessam o portal tenham uma destas funções do Azure Active Directory (AD):
- Administrador global
- Administrador de serviço do Intune
- Administrador de cobrança
- Administrador de suporte de serviço

O administrador global deve ser um para inscrever o cliente na área de trabalho gerenciada da Microsoft. Todas as cinco funções têm o mesmo acesso dentro do portal de administração para iniciar e exibir tarefas. Para obter mais informações sobre como atribuir essas funções no Azure AD, consulte [permissões de função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). 

## <a name="admin-contact-focus-areas"></a>Áreas de foco de contato do administrador

Os contatos do administrador devem ser a melhor pessoa ou grupo que pode responder a perguntas e tomar decisões para diferentes áreas de foco. As operações de área de trabalho gerenciada da Microsoft contatarão esses contatos de administração para questões envolvendo solicitações de suporte arquivadas pelo cliente. Esses contatos do administrador receberão notificações para atualizações de solicitação de suporte e novas mensagens. Essas áreas incluem:

Área de foco | Para perguntas sobre
--- | ---
Aplicativos | Solucionando problemas de pacotes de aplicativos
Dispositivos | Integridade do dispositivo, Solucionando problemas com dispositivos de área de trabalho gerenciada da Microsoft
Segurança | Solucionando problemas de segurança com dispositivos de área de trabalho gerenciada da Microsoft
Assistência técnica de ti | nos casos em que o suporte de área de trabalho gerenciada da Microsoft focaliza as permissões do usuário final fora das áreas de suporte do MMD 
Other | Para problemas não cobertos por outras áreas

Quem escolher para esses contatos precisa ter o conhecimento e a autoridade para tomar decisões para seu ambiente de área de trabalho gerenciada da Microsoft. Quando você integra seu ambiente de área de trabalho gerenciada da Microsoft, você é solicitado a adicionar contatos para sua assistência técnica e segurança local. 

Os contatos do administrador são necessários ao [Enviar uma solicitação de suporte](../working-with-managed-desktop/support.md). Você precisará ter um contato de administrador para a área de foco da solicitação de suporte. 

**Para adicionar contatos do administrador**

1.  Entre no [portal de administração de área de trabalho gerenciada da Microsoft](http://aka.ms/mwaasportal). 

2.  Em **suporte**, selecione **contatos do administrador**. 

    ![Menu de suporte, contatos do administrador](images/admincontacts.png)

3. Selecione **Adicionar**.

    ![Botão Adicionar do portal de administração](images/adminadd.png)

4.  Selecione uma **área de foco** e insira as informações do contato. 

    ![a lista de áreas de foco](images/areaoffocus.png)

5. Repita para cada área de foco. 

