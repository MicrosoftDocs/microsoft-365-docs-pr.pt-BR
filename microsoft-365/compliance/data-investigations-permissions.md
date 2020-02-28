---
title: Atribuir permissões para investigações de dados (versão prévia)
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
description: Este artigo descreve como configurar as permissões necessárias para usar a ferramenta de investigações de dados no Microsoft 365.
ms.openlocfilehash: 855d288c373bd2525afa3b8b7a3bbd894c4683a2
ms.sourcegitcommit: 7930fb8327bbd3594fde52f2dbf91e0f5d92f684
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2020
ms.locfileid: "42328133"
---
# <a name="assign-permissions-for-data-investigations-preview"></a>Atribuir permissões para investigações de dados (versão prévia)

Para acessar uma investigação de dados no centro de conformidade do Office 365 ou do Microsoft 365, você precisa ser membro do grupo de função do investigador de dados. Para adicionar membros a um grupo de funções, você deve ser membro do grupo de função gerenciamento da organização ou atribuir a função de gerenciamento de função no centro de conformidade de & de segurança. Depois que um usuário se torna membro do grupo de função do investigador de dados, eles podem criar, acessar e conduzir investigações nas investigações de dados das quais você é membro.

Para atribuir permissões de investigações de dados:

1. Acesse [https://protection.office.com](https://protection.office.com) e entre usando as credenciais de uma conta de administrador em sua organização.

2. No centro de conformidade & segurança, clique em **permissões**.

3. Clique no grupo de função **Data Investigator** e, em seguida, ao lado de **Membros** na página do submenu, clique em **Editar**.

4. Clique em **escolher Membros** e clique em **Adicionar**. Selecione os usuários que você deseja adicionar como investigadores de dados e clique em **Adicionar**.

5. Depois de adicionar todos os usuários, clique em **concluído** e, em seguida, clique em **salvar** para salvar as alterações no grupo de funções.

> [!NOTE]
> A função de gerenciamento de investigação de dados que é atribuída ao grupo de função do investigador de dados fornece as permissões necessárias para acessar a ferramenta de investigações de dados no centro de conformidade do Office 365 ou Microsoft 365. Por padrão, essa função não é atribuída ao grupo de função gerenciamento da organização, o que significa que os administradores globais em sua organização podem não conseguir acessar a ferramenta de investigações de dados por padrão. Para corrigir isso, você pode adicionar administradores globais ao grupo de função data Investigator ou adicionar a função de gerenciamento de investigação de dados ao grupo de funções Gerenciamento da organização. Uma terceira opção seria criar um grupo de função personalizado e atribuir a função de gerenciamento de investigação de dados (e outras funções) e adicionar membros apropriados. Para obter mais informações sobre grupos de funções e funções, consulte [permissões no centro de conformidade & segurança do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).
