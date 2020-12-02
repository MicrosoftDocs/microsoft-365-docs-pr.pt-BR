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
ms.openlocfilehash: 76a73372cc7517c3241390e58c28b0b02bffd664
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527692"
---
# <a name="adjust-settings-after-enrollment"></a>Ajustar as configurações após o registro

Após concluir o registro na área de trabalho gerenciada da Microsoft, você precisará ajustar determinadas configurações do Microsoft Intune e do Azure Active Directory (Azure AD) para permitir o gerenciamento e manter a segurança. Defina as configurações a seguir para excluir os grupos do Azure AD que contêm os usuários e dispositivos da área de trabalho gerenciada da Microsoft. Para obter etapas para excluir grupos, consulte [acesso condicional: usuários e grupos](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users).

## <a name="microsoft-intune-settings"></a>Configurações do Microsoft Intune

- Perfil de implantação do piloto automático: excluir os **dispositivos de área de trabalho moderna-todos os**  grupos do Azure AD. Para obter etapas, consulte [registrar dispositivos Windows no Intune usando o Windows AutoPilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).
- Políticas de acesso condicional: excluir o grupo de **contas de serviço de área de trabalho moderna** do Azure AD. Para obter etapas, consulte [acesso condicional: usuários e grupos](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).
- Autenticação multifator: Certifique-se de que quaisquer políticas de acesso condicional que exijam autenticação multifator exclua o grupo de **serviços de área de trabalho** do Azure AD. Para obter mais informações, consulte [políticas de acesso condicional](../get-ready/readiness-assessment-fix.md#conditional-access-policies) e [acesso condicional: exigir MFA para todos os usuários](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).
- Linha de base de segurança: excluir os **dispositivos de área de trabalho moderna-todos os**  grupos do Azure AD. Para obter etapas, consulte [usar linhas de base de segurança para configurar dispositivos Windows 10 no Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).
- Anel de atualização do Windows 10: excluir os **dispositivos de área de trabalho moderna-todos os**  grupos do Azure AD. Para obter etapas, consulte [Manage Windows 10 software updates no Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).


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
