---
title: Corrigir problemas encontrados pela ferramenta de avaliação de prontidão
description: Ações detalhadas a serem tomadas para cada problema que a ferramenta encontrar
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b77313a18a5744549e492de991e282bc34dbb6da
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002412"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Corrigir problemas encontrados pela ferramenta de avaliação de prontidão

Para cada verificação, a ferramenta relatará um dos quatro resultados possíveis:


|Resultado  |Significado  |
|---------|---------|
|Pronto     | Nenhuma ação é necessária antes de concluir o registro.        |
|Recomendações    | Siga as etapas na ferramenta ou neste artigo para obter a melhor experiência com o registro e para os usuários. Você *pode* concluir o registro, mas deve corrigir esses problemas antes de implantar o primeiro dispositivo.        |
|Não está pronto | *O registro falhará se você não corrigir esses problemas.* Siga as etapas na ferramenta ou neste artigo para resolvê-los.        |
|Error | A função de diretor do Azure Active Directory (AD) que você está usando não tem permissão suficiente para executar essa verificação. |

## <a name="microsoft-intune-settings"></a>Configurações do Microsoft Intune

### <a name="autopilot-deployment-profile"></a>Perfil de implantação do piloto automático

Você não deve ter perfis do AutoPilot existentes que se destinam a grupos atribuídos ou dinâmicos usados pela área de trabalho gerenciada da Microsoft. O Microsoft Managed desktop usa o piloto automático para provisionar novos dispositivos.

**Não está pronto**

Você tem um perfil do AutoPilot atribuído a todos os dispositivos. Para obter etapas, consulte [registrar dispositivos Windows no Intune usando o Windows AutoPilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot). Após o registro de área de trabalho gerenciada da Microsoft, defina a política de piloto automático para excluir os **dispositivos de local de trabalho modernos-todos os** grupos do Azure AD

**Recomendações**

Verifique se os perfis do AutoPilot têm como destino um grupo do Azure Active Directory atribuído ou dinâmico que não inclui os dispositivos de área de trabalho gerenciada da Microsoft que serão criados no registro. Para obter etapas, consulte [registrar dispositivos Windows no Intune usando o Windows AutoPilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot). Após o registro de área de trabalho gerenciada da Microsoft, defina a política de piloto automático para excluir os **dispositivos de local de trabalho modernos-todos os** grupos do Azure AD


### <a name="certificate-connectors"></a>Conectores de certificado

Se você tiver conectores de certificado usados pelos dispositivos que deseja registrar na área de trabalho gerenciada da Microsoft, os conectores não poderão ter erros. Apenas um dos seguintes comunicados será aplicado à sua situação, portanto, verifique-os cuidadosamente.

**Recomendações**

Nenhum conector de certificado está presente. É possível que você não precise de nenhum conector, mas deve avaliar se você pode precisar de alguma conectividade de rede para os dispositivos de área de trabalho gerenciada da Microsoft. Para obter mais informações, consulte [preparar certificados e perfis de rede para a área de trabalho gerenciada da Microsoft](certs-wifi-lan.md).

**Recomendações**

Pelo menos um conector de certificado tem um erro. Se você precisar desse conector para conectividade com dispositivos de área de trabalho gerenciada da Microsoft, você deve resolver o erro. Para obter mais informações, consulte [preparar certificados e perfis de rede para a área de trabalho gerenciada da Microsoft](certs-wifi-lan.md).


**Recomendações**

Você tem pelo menos um conector de certificado e nenhum erro é relatado. No entanto, talvez seja necessário criar um perfil para reutilizar o conector para dispositivos de área de trabalho gerenciada da Microsoft. Para obter mais informações, consulte [preparar certificados e perfis de rede para a área de trabalho gerenciada da Microsoft](certs-wifi-lan.md).


### <a name="conditional-access-policies"></a>Políticas de acesso condicional

As políticas de acesso condicional em sua organização do Azure AD não devem ser direcionadas a usuários do Microsoft Manage desktop.

**Não está pronto**

Você tem pelo menos uma política de acesso condicional que se destina a todos os usuários. Redefina a política para direcionar um grupo específico do Azure AD que não inclui o grupo Azure AD de contas de serviço de área de trabalho gerenciada da Microsoft que serão criadas no registro. Para obter etapas, consulte [acesso condicional: usuários e grupos](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).

**Recomendações**

Certifique-se de que as políticas de acesso condicional que você excluiu o grupo de **contas do serviço de área de trabalho moderna** do Azure AD. Para obter etapas, consulte [ajustar o acesso condicional](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access). O grupo de **serviços de área de trabalho moderna** grupo do Azure AD é um grupo dinâmico que criamos para o serviço ao se inscrever. Você precisará voltar para excluir esse grupo após o registro. Para saber mais sobre essas contas de serviço, consulte [Standard Operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Error**

A função de administrador do Intune não tem permissões suficientes para esta verificação. Você também precisará de qualquer uma destas funções do Azure AD atribuídas para executar esta verificação:

- Leitor de segurança
- Administrador de Segurança
- Administrador de acesso condicional
- Leitor global
- Administrador de dispositivos


### <a name="device-compliance-policies"></a>Políticas de conformidade do dispositivo

As políticas de conformidade do dispositivo do Intune em sua organização do Azure AD não devem ser direcionadas a usuários do Microsoft Managed desktop.

**Não está pronto**

Você tem pelo menos uma política de conformidade voltada para todos os usuários. Redefina a política para direcionar um grupo específico do Azure AD que não inclui nenhum usuário da área de trabalho gerenciada da Microsoft. Para obter etapas, consulte [criar uma política de conformidade no Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).

**Recomendações**

Certifique-se de que as políticas de conformidade que você não incluiu nenhum usuário da área de trabalho gerenciado da Microsoft. Para obter etapas, consulte [criar uma política de conformidade no Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).



### <a name="device-configuration-policies"></a>Políticas de configuração de dispositivo

As políticas de configuração de dispositivo do Intune em sua organização do Azure AD não devem ser direcionadas a nenhum dispositivo ou usuário do Microsoft Manage desktop.

**Não está pronto**

Você tem pelo menos uma política de configuração voltada para todos os usuários, todos os dispositivos ou ambos. Redefina a política para direcionar um grupo específico do Azure AD que não inclua nenhum dispositivo de área de trabalho gerenciado da Microsoft. Para obter etapas, consulte [criar uma política de conformidade no Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).

**Recomendações**

Certifique-se de que as políticas de conformidade que você não incluiu nenhum dispositivo ou usuário do Microsoft Managed desktop. Para obter etapas, consulte [criar uma política de conformidade no Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).



### <a name="device-type-restrictions"></a>Restrições de tipo de dispositivo

Os dispositivos de área de trabalho gerenciada da Microsoft devem ter permissão para se inscrever no Intune.

**Não está pronto**

Siga as etapas em [definir restrições de registro](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) para alterar a configuração para **permitir**.


### <a name="enrollment-status-page"></a>Página de status do registro

No momento, você tem a página de status de registro (ESP) habilitada. Se você estiver participando da visualização pública desse recurso, poderá ignorar esse item. Para obter mais informações, consulte [experiência de primeira execução com o AutoPilot e a página status do registro](../get-started/esp-first-run.md).

**Não está pronto**

Você tem o perfil padrão ESP definido para **mostrar o progresso da configuração de perfil e aplicativo**. Desabilite essa configuração ou certifique-se de que as atribuições para qualquer grupo do Azure AD não incluam dispositivos da área de trabalho gerenciada da Microsoft seguindo as etapas descritas em [Configurar a página status do registro](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).

**Recomendações**

Certifique-se de que todos os perfis que têm a configuração de **andamento da configuração mostrar aplicativo e perfil** não estão atribuídos a nenhum grupo do Azure AD que inclua dispositivos de área de trabalho gerenciado da Microsoft. Para obter mais informações, consulte [Configurar a página status do registro](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).

### <a name="intune-enrollment"></a>Registro do Intune

Os dispositivos Windows 10 em sua organização do Azure AD devem ser registrados automaticamente no Intune.

**Recomendações**

Certifique-se de que o escopo de usuário MDM está definido como **alguns** ou **todos** , não **nenhum**. Se você escolher **alguns** , volte após o registro e selecione o **local de trabalho moderno – todos os** grupos do Azure ad para **grupos**.


### <a name="microsoft-store-for-business"></a>Microsoft Store para empresas

Usamos a Microsoft Store para empresas para que você possa baixar o portal da empresa para implantar alguns aplicativos, como o Microsoft Project e o Microsoft Visio.

**Não está pronto**

A Microsoft Store para empresas não está habilitada ou não está sincronizada com o Intune. Para obter mais informações, consulte [como gerenciar aplicativos comprados por volume da Microsoft Store para empresas com o Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) e [instalar o portal da empresa do Intune em dispositivos](../get-started/company-portal.md).

### <a name="multi-factor-authentication"></a>Autenticação multifator

A autenticação multifator não deve ser aplicada acidentalmente às contas de serviço de área de trabalho gerenciada da Microsoft.


**Não está pronto**

Você tem algumas políticas de autenticação multifator (MFA) definidas como "obrigatórias" para políticas de acesso condicional que são atribuídas a todos os usuários. Altere a política para usar uma atribuição que tenha como destino um grupo específico do Azure AD que não inclua nenhum dispositivo de área de trabalho gerenciado da Microsoft. Para obter mais informações, consulte [políticas de acesso condicional](#conditional-access-policies) e [acesso condicional: exigir MFA para todos os usuários](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).

**Recomendações**

Certifique-se de que todas as políticas de acesso condicional que exijam a MFA excluam o grupo do **local de trabalho moderno – todo** o Azure AD. Para obter mais informações, consulte [políticas de acesso condicional](#conditional-access-policies) e [acesso condicional: exigir MFA para todos os usuários](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa). O **ambiente de trabalho moderno – todos os** grupos do Azure AD é um grupo dinâmico criado quando você se inscreve na área de trabalho gerenciada da Microsoft, portanto, você terá que voltar a excluir esse grupo após o registro.

**Error**

A função de administrador do Intune não tem permissões suficientes para esta verificação. Você também precisará de qualquer uma destas funções do Azure AD atribuídas para executar esta verificação:

- Leitor de segurança
- Administrador de Segurança
- Administrador de acesso condicional
- Leitor global
- Administrador de dispositivos


### <a name="powershell-scripts"></a>Scripts do PowerShell

Os scripts do Windows PowerShell não podem ser atribuídos de uma maneira que direcione dispositivos da área de trabalho gerenciada da Microsoft.  

**Recomendações**

Certifique-se de que os scripts do Windows PowerShell em sua organização do Azure AD não se destinam a nenhum dispositivo ou usuário do Microsoft Manage desktop. Não atribua um script do PowerShell para direcionar todos os usuários, todos os dispositivos ou ambos. Altere a política para usar uma atribuição que tenha como destino um grupo específico do Azure AD que não inclua nenhum dispositivo de área de trabalho gerenciado da Microsoft. Para obter mais informações, consulte [usar scripts do PowerShell em dispositivos Windows 10 no Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).

### <a name="region"></a>Região

Sua região deve ser compatível com a área de trabalho gerenciada da Microsoft.

**Não está pronto**

Sua região da organização do Azure AD não é suportada atualmente pela Microsoft Managed desktop. Para obter mais informações, consulte [áreas e idiomas compatíveis com o Microsoft Managed desktop](../service-description/regions-languages.md).

**Recomendações**

Um ou mais países onde sua organização do Azure AD está localizada não é suportado pela área de trabalho gerenciada da Microsoft. Para obter mais informações, consulte [áreas e idiomas compatíveis com o Microsoft Managed desktop](../service-description/regions-languages.md).


### <a name="security-baselines"></a>Linhas de base de segurança

As políticas de linha de base de segurança não devem ter como destino nenhum dispositivo de área de trabalho gerenciado

**Não está pronto**

Você tem um perfil de linha de base de segurança direcionado a todos os usuários, todos os dispositivos ou ambos. Altere a política para usar uma atribuição que tenha como destino um grupo específico do Azure AD que não inclua nenhum dispositivo de área de trabalho gerenciado da Microsoft. Para obter etapas, consulte [usar linhas de base de segurança para configurar dispositivos Windows 10 no Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).

**Recomendações**

Certifique-se de que as políticas de linha de base de segurança que você tenha excluído dispositivos de desktop gerenciados da Microsoft Para obter etapas, consulte [usar linhas de base de segurança para configurar dispositivos Windows 10 no Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines). Os **dispositivos de área de trabalho moderna – todos os** grupos do Azure ad são um grupo dinâmico que criamos quando você se inscreve na área de trabalho gerenciada da Microsoft, portanto, você terá que voltar a excluir esse grupo após o registro.


### <a name="windows-apps"></a>Aplicativos do Windows

Revise os aplicativos que você deseja que seus usuários do Microsoft Managed desktop tenham.

**Recomendações**

Você deve preparar um inventário dos aplicativos que você deseja que seus usuários de área de trabalho gerenciada da Microsoft tenham. Como esses aplicativos devem ser implantados pelo Intune, avalie a reutilização de aplicativos existentes do Intune. Considere usar o portal da empresa (Confira [instalar o portal da empresa do Intune em dispositivos](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) e a página de status de registro (ESP) para distribuir aplicativos aos seus usuários. Para obter mais informações, consulte [aplicativos na área de trabalho gerenciada da Microsoft](apps.md) e [experiência de primeira execução com o AutoPilot e a página status do registro](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run).

Você pode solicitar ao representante da sua conta da Microsoft uma consulta no Microsoft Endpoint Configuration Manager para identificar os aplicativos que estão prontos para migrar para o Intune ou que precisam de ajuste.


### <a name="windows-hello-for-business"></a>Windows Hello para Empresas

A área de trabalho gerenciada da Microsoft exige que o Windows Hello para empresas seja habilitado.

**Não está pronto**

O Windows Hello para empresas está desabilitado. Habilite-o seguindo as etapas em [criar uma política do Windows Hello para empresas](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Recomendações**

O Windows Hello para empresas não está configurado. Habilite-o seguindo as etapas em [criar uma política do Windows Hello para empresas](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).


### <a name="windows-10-update-rings"></a>Toques de atualização do Windows 10

A política do "Windows 10 Update Ring" no Intune não deve ser direcionada a nenhum dispositivo de área de trabalho gerenciado da Microsoft.

**Não está pronto**

Você tem uma política de "anel de atualização" voltada para todos os dispositivos, todos os usuários ou ambos. Altere a política para usar uma atribuição que tenha como destino um grupo específico do Azure AD que não inclua nenhum dispositivo de área de trabalho gerenciado da Microsoft. Para obter etapas, consulte [Manage Windows 10 software updates no Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).

**Recomendações**

Certifique-se de que qualquer política de anel de atualização que você tenha excluído os **dispositivos de área de trabalho modernos-todos os** grupos do Azure AD. Se você tiver atribuído o grupo de usuários do Azure AD a essas políticas, certifique-se de que todas as políticas de anel de atualização que você tenha excluído também o grupo de trabalho do Microsoft Azure Active Directory que inclui os usuários da área **de** trabalho gerenciada da Microsoft. Para obter etapas, consulte [Manage Windows 10 software updates no Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure). Tanto os **dispositivos de área de trabalho moderna – todos os** **grupos do Azure** Active Directory são atribuídos aos grupos que criamos quando você se inscreve na área de trabalho gerenciada da Microsoft, portanto, você precisa retornar para excluir esse grupo após o registro.


## <a name="azure-active-directory-settings"></a>Configurações do Azure Active Directory


### <a name="ad-hoc-subscriptions"></a>Assinaturas ad hoc

Aconselha a verificar uma configuração que (se definida como "false") pode impedir que o roaming de estado corporativo funcione corretamente.

**Recomendações**

Verifique se **AllowAdHocSubscriptions** está definido como **true**. Caso contrário, o roaming de estado corporativo pode não funcionar. Para obter mais informações, consulte [set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).


### <a name="enterprise-state-roaming"></a>Roaming de Estado da Empresa

O roaming de estado corporativo deve ser habilitado.

**Recomendações**

Certifique-se de que o roaming de estado corporativo está habilitado para **todos** ou para grupos **selecionados** . Para obter mais informações, consulte [habilitar o roaming de estado corporativo no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).

### <a name="licenses"></a>Licenças

É necessário ter várias licenças para usar a área de trabalho gerenciada da Microsoft.

**Não está pronto**

Você não tem todas as licenças necessárias para usar a área de trabalho gerenciada da Microsoft. Para obter mais informações, consulte [tecnologias de área de trabalho gerenciada da Microsoft](../intro/technologies.md) e [mais sobre licenças](prerequisites.md#more-about-licenses).


### <a name="security-account-names"></a>Nomes de contas de segurança

Determinados nomes de contas de segurança podem entrar em conflito com aqueles criados pela área de trabalho gerenciada pela Microsoft.

**Não está pronto**

Você tem pelo menos um nome de conta que entrará em conflito com aqueles criados pela área de trabalho gerenciada pela Microsoft. Trabalhe com seu representante de conta da Microsoft para excluir esses nomes de conta.


### <a name="security-administrator-roles"></a>Funções de administrador de segurança

Os usuários com determinadas funções de segurança devem ter os atribuídos no Microsoft defender para ponto de extremidade.

**Recomendações**

Se você tiver usuários atribuídos a qualquer uma dessas funções em sua organização do Azure AD, verifique se eles também têm essas funções atribuídas no Microsoft defender para ponto de extremidade. Caso contrário, os administradores com essas funções não poderão acessar o portal de administração.

- Operador de segurança
- Leitor global

Para obter mais informações, consulte [Create and Manage Roles for Role-Based Access Control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).


### <a name="security-default"></a>Padrão de segurança

Os padrões de segurança no Azure Active Directory impedirão que a área de trabalho gerenciada da Microsoft gerencie seus dispositivos.

**Não está pronto**

Os padrões de segurança estão ativados. Desative os padrões de segurança e configure as políticas de acesso condicional. Para obter mais informações, consulte [políticas de acesso condicional comuns](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).

### <a name="self-service-password-reset"></a>Redefinição de senha de autoatendimento

A redefinição de senha de autoatendimento (SSPR) deve estar habilitada para todos os usuários da área de trabalho gerenciada da Microsoft, excluindo contas de serviço de desktop gerenciado Para obter mais informações, consulte [tutorial: permitir que os usuários desbloqueiem suas contas ou redefinam senhas usando a redefinição de senha de autoatendimento do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).

**Recomendações**

Verifique se a configuração **selecionada** SSPR inclui dispositivos de área de trabalho gerenciada da Microsoft, mas exclui as contas de serviço de área de trabalho gerenciada da Microsoft. As contas de serviço de área de trabalho gerenciada da Microsoft não podem funcionar como esperado quando o SSPR está habilitado.  


### <a name="standard-user-role"></a>Função de usuário padrão

Além dos usuários que recebem as funções do Azure AD do administrador global e do administrador de dispositivos, os usuários da área de trabalho gerenciada da Microsoft serão usuários padrão sem privilégios de administrador local. Todos os outros usuários receberão uma função de usuário padrão quando iniciarem o dispositivo de área de trabalho gerenciada da Microsoft.

**Recomendações**

Os usuários da área de trabalho gerenciada da Microsoft não terão privilégios de administrador local em seus dispositivos de área de trabalho gerenciados da Microsoft após o registro.

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps para empresas

### <a name="onedrive"></a>OneDrive

A configuração **permitir sincronização somente em computadores associados a domínios específicos** entrará em conflito com a área de trabalho gerenciada da Microsoft.

**Recomendações**

Você está usando a configuração **permitir sincronização somente em computadores associados a domínios específicos** . Essa configuração não funcionará com a área de trabalho gerenciada da Microsoft. Desabilite essa configuração e configure o OneDrive para usar uma política de acesso condicional. Consulte [planejar uma implantação de acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) para obter ajuda.

