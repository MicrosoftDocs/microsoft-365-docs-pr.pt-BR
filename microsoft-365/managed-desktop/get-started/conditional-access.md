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
ms.openlocfilehash: 88a832f6c4e17756bfb25ef5cb7c4c5ecedaf2c0
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794383"
---
# <a name="adjust-settings-after-enrollment"></a>Ajustar as configurações após o registro

Depois que você concluir o registro na Área de Trabalho Gerenciada da Microsoft, algumas configurações de gerenciamento talvez precisem ser ajustadas. Para verificar e ajustar, se necessário, siga estas etapas:

1. Revise as configurações do Microsoft Intune e do Azure Active Directory descritas na próxima seção.
2. Se qualquer um dos itens se aplicar ao seu ambiente, faça os ajustes descritos.
3. Se quiser verificar se todas as configurações estão corretas, você pode re-runcar a ferramenta de avaliação de preparação para garantir que nada entre em conflito com a Área de Trabalho Gerenciada da Microsoft. [](https://aka.ms/mmdart)

> [!NOTE]
> À medida que suas operações continuam nos meses seguintes, se você fizer alterações após o registro nas políticas do Microsoft Intune, do Azure Active Directory ou do Microsoft 365 que afetam a Área de Trabalho Gerenciada da Microsoft, é possível que a Área de Trabalho Gerenciada da Microsoft pare de funcionar corretamente. Para evitar problemas com o serviço, verifique [](../get-ready/readiness-assessment-fix.md) as configurações específicas descritas em Corrigir problemas encontrados pela ferramenta de avaliação de preparação antes de alterar as políticas listadas lá. Você também pode reruncar a ferramenta de avaliação de preparação a qualquer momento.


## <a name="microsoft-intune-settings"></a>Configurações do Microsoft Intune

- Perfil de implantação do Autopilot: se você usar qualquer política do Autopilot, atualize cada uma delas para excluir o grupo Dispositivos de Local de Trabalho Modernos **- Todos** do Azure AD. Para atualizá-los, na seção Grupos excluídos em Atribuições, selecione o grupo **Dispositivos** do Local de Trabalho Moderno **-Todos** os Grupos do Azure AD que foi criado durante o registro da Área de Trabalho Gerenciada da Microsoft.  A Área de Trabalho Gerenciada da Microsoft também terá criado um perfil do **Autopilot,** que terá "Modern Workplace" no nome (o Perfil do Piloto Automático do Local de Trabalho Moderno). Ao atualizar seus próprios perfis do  **Autopilot,** **certifique-se** de não excluir o grupo Dispositivos de Local de Trabalho Moderno - Todos os Azure AD do Perfil do Piloto Automático do Local de Trabalho Moderno criado pela Área de Trabalho Gerenciada da Microsoft.

- Políticas de Acesso Condicional: para políticas de acesso condicional que você criou, exclua o grupo Contas do **Serviço** de Local de Trabalho Moderno do Azure AD. Para etapas, consulte [Acesso Condicional: Usuários e grupos.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups) A Área de Trabalho Gerenciada da Microsoft também terá criado algumas políticas de acesso condicional, todas com "Modern Workplace" no nome (por exemplo, **Modern Workplace Secure Workstation**). Ao atualizar suas próprias políticas de acesso  condicional, certifique-se de não excluir o grupo Dispositivos modernos do Local de Trabalho **-** Todos os Azure AD de quaisquer políticas criadas pela Área de Trabalho Gerenciada da Microsoft.

- Autenticação multifator: certifique-se de que qualquer uma de  suas políticas de acesso condicional que exigem autenticação multifator exclua o grupo contas de serviço do Azure AD modernas. Para obter mais informações, [consulte Políticas de acesso condicional](../get-ready/readiness-assessment-fix.md#conditional-access-policies) e Acesso [Condicional: Exigir MFA para todos os usuários.](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)

- Anel de atualização do Windows 10: para todas as políticas de anel de atualização do Windows 10 que você criou, exclua o grupo Dispositivos Modernos do Local de Trabalho **-** Todos os grupos do Azure AD de cada política. Para etapas, consulte [Criar e atribuir anéis de atualização.](https://docs.microsoft.com/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings) A Área de Trabalho Gerenciada da Microsoft também terá criado algumas políticas de anel de atualização, todas com "Modern Workplace" no nome (por exemplo, **Política do Modern Workplace Update [Ampla]**, Política do Modern Workplace Update **[Rápida]**, **Política do Modern Workplace Update [Primeiro]** e Política de Atualização do Local de Trabalho Moderna **[Teste]**). Ao atualizar suas próprias políticas,  certifique-se de não excluir o grupo Dispositivos do Local de Trabalho Moderno **-** Todos os Azure AD daqueles que a Área de Trabalho Gerenciada da Microsoft criou.


## <a name="azure-active-directory-settings"></a>Configurações do Azure Active Directory

Redefinição de senha de autoatendido: se você usar a redefinição de senha de autoatendido para todos os usuários, ajuste a atribuição para excluir contas de serviço da Área de Trabalho Gerenciada da Microsoft. Para ajustar essa atribuição, crie um grupo dinâmico do Azure AD para todos os usuários, exceto contas de serviço da Área de Trabalho Gerenciada da *Microsoft,* e depois use esse grupo para atribuição em vez de "todos os usuários".

Para ajudá-lo a encontrar e excluir as contas de serviço, aqui está um exemplo de uma consulta dinâmica que você pode usar:

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

Nesta consulta, substitua os @TENANT pelo nome de domínio do locatário.



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Etapas para começar a trabalhar com a Área de Trabalho Gerenciada da Microsoft

1. [Adicionar e verificar contatos do administrador no portal de Administração](add-admin-contacts.md)
2. Ajustar configurações após o registro (este artigo)
3. [Atribuir licenças](assign-licenses.md)
4. [Implantar o Portal da Empresa do Intune](company-portal.md)
5. [Habilitar Roaming de Estado da Empresa](enterprise-state-roaming.md)
6. [Configurar dispositivos](set-up-devices.md)
7. [Preparar usuários para o uso dos dispositivos](get-started-devices.md)
8. [Implantar aplicativos](deploy-apps.md)
