---
title: Adicionar e verificar contatos do administrador no portal de Administração
description: Diga-nos quem entrar em contato para cada área de foco.
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9233118a2112aae33a5b784b6495709cbd3345f5
ms.sourcegitcommit: ef658406da9d081e5e7a5f3aac8290c2f03f7aff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2020
ms.locfileid: "41004916"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>Adicionar e verificar contatos do administrador no portal de Administração

Há várias maneiras de o serviço Microsoft Managed desktop se comunicar com os clientes. Para simplificar a comunicação e garantir que estamos verificando com as pessoas certas, você precisa fornecer um conjunto de contatos de administração. As operações de ti de área de trabalho gerenciada da Microsoft contatarão essas pessoas para resolver problemas de solução de problemas para o seu locatário.

> [!IMPORTANT]
> Você pode já ter adicionado esses contatos no portal de administração. Em caso afirmativo, Reserve um momento para verificar se a lista de contatos é precisa, pois a área de trabalho gerenciada da Microsoft **deve** ser capaz de encontrá-las se ocorrer um incidente grave.

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Acesso do Azure Active Directory para o portal de administração de área de trabalho gerenciada da Microsoft

O portal de administração de área de trabalho gerenciada da Microsoft exige que as pessoas que acessam o portal tenham uma destas funções do Azure Active Directory (AD):
- Administrador global
- Administrador de serviço do Intune
- Leitor global
- Administrador de suporte de serviço

O administrador global deve ser o para inscrever sua organização na área de trabalho gerenciada da Microsoft. Todas as cinco funções têm o mesmo acesso dentro do portal de administração para iniciar e exibir tarefas. Para obter mais informações sobre como atribuir essas funções no Azure AD, consulte [permissões de função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). 

## <a name="admin-contact-areas-of-focus"></a>Áreas de contato do administrador de foco

Os contatos do administrador devem ser a melhor pessoa ou grupo que pode responder a perguntas e tomar decisões para diferentes áreas de foco. **As operações de área de trabalho gerenciada da Microsoft contatarão esses contatos de administração para questões envolvendo solicitações de suporte arquivadas pelo cliente.** Esses contatos do administrador receberão notificações para atualizações de solicitação de suporte e novas mensagens. Essas áreas incluem:

Área de foco | Para perguntas sobre
--- | ---
Pacote de aplicativos | Solucionando problemas de pacotes de aplicativos
Dispositivos | Integridade do dispositivo, Solucionando problemas com dispositivos de área de trabalho gerenciada da Microsoft
Segurança | Solucionando problemas de segurança com dispositivos de área de trabalho gerenciada da Microsoft
Assistência técnica de ti | nos casos em que nossa equipe de suporte passa as permissões do usuário final para fora das áreas de suporte da área de trabalho gerenciada da Microsoft 
Outros | Para problemas não cobertos por outras áreas

**Quem escolher para esses contatos precisa ter o conhecimento e a autoridade para tomar decisões para seu ambiente de área de trabalho gerenciada da Microsoft.** Quando você integra seu ambiente de área de trabalho gerenciada da Microsoft, você é solicitado a adicionar contatos para sua assistência técnica e segurança local. 

Os contatos do administrador são necessários ao [Enviar uma solicitação de suporte](../service-description/support.md). Você precisará ter um contato de administrador para a área de foco da solicitação de suporte. 

**Para adicionar contatos do administrador**

1.  Entre no [portal de administração de área de trabalho gerenciada da Microsoft](https://aka.ms/mwaasportal). 

2.  Em **suporte**, selecione **contatos do administrador**. 

    ![Menu de suporte, contatos do administrador próximo à parte superior selecionada](images/admincontacts.png)

3. Selecione **Adicionar**.

    ![Portal de administração, botão Adicionar, à esquerda de exportar e atualizar](images/adminadd.png)

4.  Selecione uma **área de foco** e insira as informações do contato. 

    ![a lista de áreas de foco, como outros, aplicativos e segurança](images/areaoffocus.png)

5. Repita para cada área de foco. 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Etapas para começar a usar a área de trabalho gerenciada da Microsoft

1. Adicionar e verificar contatos de administrador no portal de administração (este tópico)
2. [Ajustar o acesso condicional](conditional-access.md)
3. [Atribuir licenças](assign-licenses.md)
4. [Instalar o portal da empresa do Intune em dispositivos](company-portal.md)
5. [Habilitar Roaming de Estado da Empresa](enterprise-state-roaming.md)
6. [Configurar dispositivos de área de trabalho gerenciada da Microsoft](set-up-devices.md)
7. [Preparar usuários para o uso dos dispositivos](get-started-devices.md)
8. [Implantar aplicativos em dispositivos](deploy-apps.md)
