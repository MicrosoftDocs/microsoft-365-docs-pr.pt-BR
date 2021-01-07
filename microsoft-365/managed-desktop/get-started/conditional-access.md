---
title: Ajustar as configurações após o registro
description: Como excluir determinadas contas da Microsoft
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e78f0123c909c90ff90be913e8775cc1e5b30313
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777094"
---
# <a name="adjust-settings-after-enrollment"></a>Ajustar as configurações após o registro

Depois de concluir o registro na área de trabalho gerenciada da Microsoft, você precisa ajustar as configurações do Microsoft Intune e do Azure Active Directory (Azure AD) especificadas neste artigo para permitir o gerenciamento e a manutenção da segurança. Defina as configurações a seguir para excluir grupos específicos do Azure AD que contenham os usuários e dispositivos da área de trabalho gerenciada da Microsoft. Para obter etapas para excluir grupos, consulte [acesso condicional: usuários e grupos](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users).

> [!NOTE]
> Se você fizer alterações após o registro em políticas no Microsoft Intune, Azure Active Directory ou Microsoft 365, é possível que a área de trabalho gerenciada da Microsoft possa parar de funcionar corretamente. Para evitar problemas com as operações de área de trabalho gerenciada da Microsoft, verifique as configurações específicas descritas em [corrigir problemas encontrados pela ferramenta de avaliação de prontidão antes de](../get-ready/readiness-assessment-fix.md) alterar qualquer política.


## <a name="microsoft-intune-settings"></a>Configurações do Microsoft Intune

- Perfil de implantação do piloto automático: para perfis do AutoPilot criados por administradores em sua empresa, exclua os **dispositivos de área de trabalho moderna-todos os** grupos do Azure AD. Para obter etapas, consulte [registrar dispositivos Windows no Intune usando o Windows AutoPilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot). Não exclua os dispositivos de área de **trabalho moderna-todos os** grupos do Azure AD de qualquer política de implantação criada pelo Microsoft Managed desktop que tenha "local de trabalho moderno" no nome (por exemplo, **perfil do AutoPilot do local de trabalho moderno**). 
- Políticas de acesso condicional: para políticas de acesso condicional criadas por administradores em sua empresa, exclua o grupo **contas do serviço de área de trabalho moderna** do Azure AD. Para obter etapas, consulte [acesso condicional: usuários e grupos](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Não exclua os dispositivos de área de **trabalho moderna-todos os** grupos do Azure AD de qualquer política criada pelo Microsoft Managed desktop que tenha "local de trabalho moderno" no nome (por exemplo, **estação de trabalho segura de local de trabalho moderno**).
- Autenticação multifator: Certifique-se de que qualquer política de acesso condicional criada por administradores em sua empresa que exijam autenticação multifator exclua o grupo de **serviços de área de trabalho** do Azure AD. Para obter mais informações, consulte [políticas de acesso condicional](../get-ready/readiness-assessment-fix.md#conditional-access-policies) e [acesso condicional: exigir MFA para todos os usuários](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).
- Linha de base de segurança: para políticas de linha de base de segurança criadas por administradores em sua empresa, exclua os **dispositivos de área de trabalho moderna-todos os**  grupos do Azure AD Para obter etapas, consulte [usar linhas de base de segurança para configurar dispositivos Windows 10 no Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines). Não exclua os dispositivos de área de **trabalho moderna-todos os** grupos do Azure AD de qualquer política criada pelo Microsoft Managed desktop que tenha "local de trabalho moderno" no nome (por exemplo, a **linha de base de segurança de área de trabalho moderna**).
- Anel de atualização do Windows 10: para as políticas de anel de atualização do Windows 10 criadas por administradores em sua empresa, exclua os **dispositivos de área de trabalho moderna-todos os**  grupos do Azure AD. Para obter etapas, consulte [Manage Windows 10 software updates no Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure). Não exclua os dispositivos de área de **trabalho moderna-todos os** grupos do Azure AD de qualquer política criada pelo Microsoft Managed desktop que tenha "local de trabalho moderno" no nome (por exemplo, a política de **atualização de área de trabalho moderna** ).


## <a name="azure-active-directory-settings"></a>Configurações do Azure Active Directory

Redefinição de senha de autoatendimento: escolha configuração **selecionada** e, em seguida, selecione **dispositivos de área de trabalho moderna-todos os** grupos do Azure AD. Para obter mais informações, consulte [tutorial: permitir que os usuários desbloqueiem suas contas ou redefinam senhas usando a redefinição de senha de autoatendimento do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Etapas para começar a usar a área de trabalho gerenciada da Microsoft

1. [Adicionar e verificar contatos do administrador no portal de Administração](add-admin-contacts.md)
2. Ajustar as configurações após o registro (este artigo)
3. [Atribuir licenças](assign-licenses.md)
4. [Implantar o Portal da Empresa do Intune](company-portal.md)
5. [Habilitar Roaming de Estado da Empresa](enterprise-state-roaming.md)
6. [Configurar dispositivos](set-up-devices.md)
7. [Preparar usuários para o uso dos dispositivos](get-started-devices.md)
8. [Implantar aplicativos](deploy-apps.md)
