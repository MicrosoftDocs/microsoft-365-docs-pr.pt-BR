---
title: Corrigir problemas encontrados pela ferramenta de avaliação de prontidão
description: Ações detalhadas a ser tomadas para cada problema encontrado pela ferramenta
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 75c2967037ae83abca2aaa3cd02d1f6b2ae14caa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925911"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Corrigir problemas encontrados pela ferramenta de avaliação de prontidão

Para cada verificação, a ferramenta relatará um dos quatro resultados possíveis:


|Resultado  |Significado  |
|---------|---------|
|Pronto     | Nenhuma ação é necessária antes de concluir o registro.        |
|Aviso    | Siga as etapas na ferramenta ou neste artigo para ter a melhor experiência com registro e usuários. Você *pode* concluir o registro, mas deve corrigir esses problemas antes de implantar seu primeiro dispositivo.        |
|Não está pronto | *O registro falhará se você não corrigir esses problemas.* Siga as etapas na ferramenta ou neste artigo para resolvê-las.        |
|Error | A função do Azure Active Directory (AD) que você está usando não tem permissão suficiente para executar essa verificação. |

> [!NOTE]
> Os resultados relatados por essa ferramenta refletem o status de suas configurações apenas no ponto específico no tempo em que você a publicou. Se você fizer alterações posteriores nas políticas no Microsoft Intune, no Azure Active Directory ou no Microsoft 365, os itens que estavam "Prontos" podem se tornar "Não prontos". Para evitar problemas com as operações da Área de Trabalho Gerenciada da Microsoft, verifique as configurações específicas descritas neste artigo antes de alterar quaisquer políticas.

## <a name="microsoft-intune-settings"></a>Configurações do Microsoft Intune

Você pode acessar as configurações do Intune no Centro de administração do Microsoft Endpoint [Manager.](https://endpoint.microsoft.com)

### <a name="autopilot-deployment-profile"></a>Perfil de implantação do Autopilot

Você não deve ter perfis do Autopilot existentes destinados a grupos atribuídos ou dinâmicos com dispositivos da Área de Trabalho Gerenciada da Microsoft. A Área de Trabalho Gerenciada da Microsoft usa o Autopilot para provisionar novos dispositivos.

**Não está pronto**

Você tem um perfil do Piloto Automático atribuído a todos os dispositivos. Para ver etapas, consulte [Registrar dispositivos Windows no Intune usando o Windows Autopilot](/mem/autopilot/enrollment-autopilot). Após o registro na Área de Trabalho Gerenciada da Microsoft, de definir sua política de Piloto Automático para excluir o grupo Dispositivos modernos do Local de Trabalho **- Todos** os Azure AD.

**Aviso**

Certifique-se de que seus perfis do Autopilot direcionam um grupo atribuído ou dinâmico do Azure AD que não inclui dispositivos da Área de Trabalho Gerenciada da Microsoft. Para ver etapas, consulte [Registrar dispositivos Windows no Intune usando o Windows Autopilot](/mem/autopilot/enrollment-autopilot). Após o registro da Área de Trabalho Gerenciada da Microsoft, de definir os perfis do Piloto Automático para excluir o grupo Dispositivos modernos do Local de **Trabalho -All** Azure AD.


### <a name="certificate-connectors"></a>Conectores de certificado

Se você tiver conectores de certificado que serão usados pelos dispositivos que você deseja registrar na Área de Trabalho Gerenciada da Microsoft, os conectores não devem ter erros. Somente um dos seguintes avisos se aplicará à sua situação, portanto, verifique-os cuidadosamente.

**Aviso**

Nenhum conector de certificado está presente. É possível que você não precise de conectores, mas você deve avaliar se você pode precisar de alguns para conectividade de rede em seus dispositivos da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, [consulte Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).

**Aviso**

Pelo menos um conector de certificado tem um erro. Se você precisar desse conector para fornecer certificados para dispositivos da Área de Trabalho Gerenciada da Microsoft, você deve resolver o erro. Para obter mais informações, [consulte Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).


**Aviso**

Você tem pelo menos um conector de certificado e nenhum erro é relatado. No entanto, em preparação para a implantação, talvez seja necessário criar um perfil para reutilizar o conector para dispositivos da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, [consulte Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).


### <a name="conditional-access-policies"></a>Políticas de acesso condicional

As políticas de acesso condicional não devem impedir que a Área de Trabalho Gerenciada da Microsoft gerencie sua organização do Azure AD (locatário) no Intune e no Azure AD.

**Não está pronto**

Você tem pelo menos uma política de acesso condicional voltada para todos os usuários. Durante o registro, excluiremos as contas de serviço da Área de Trabalho Gerenciada da Microsoft de políticas de acesso condicional relevantes e aplicaremos novas políticas de acesso condicional para restringir o acesso a essas contas. Após o registro, você pode revisar a política de acesso condicional da Área de Trabalho Gerenciada da Microsoft no Microsoft Endpoint Manager. Para saber mais sobre essas contas de serviço, consulte [Procedimentos operacionais padrão](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Aviso**

Você tem políticas de acesso condicional que podem impedir que a Área de Trabalho Gerenciada da Microsoft gerencie o serviço de Área de Trabalho Gerenciada da Microsoft. Durante o registro, excluiremos as contas de serviço da Área de Trabalho Gerenciada da Microsoft de políticas de acesso condicional relevantes e aplicaremos novas políticas de acesso condicional para restringir o acesso a essas contas. Para saber mais sobre essas contas de serviço, consulte [Procedimentos operacionais padrão](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Erro**

A função Administrador do Intune não tem permissões suficientes para essa verificação. Você também precisará de qualquer uma dessas funções do Azure AD atribuídas para executar esta verificação:

- Leitor de segurança
- Administrador de Segurança
- Administrador de Acesso Condicional
- Leitor Global
- Administrador de Dispositivos


### <a name="device-compliance-policies"></a>Políticas de Conformidade de Dispositivo

As políticas de Conformidade de Dispositivo do Intune em sua organização do Azure AD podem afetar dispositivos da Área de Trabalho Gerenciada da Microsoft.

**Não está pronto**

Você tem pelo menos uma política de conformidade voltada para todos os usuários. A Área de Trabalho Gerenciada da Microsoft inclui políticas de conformidade que direcionarão seus dispositivos da Área de Trabalho Gerenciada da Microsoft.  Altere a política para direcionar um grupo específico do Azure AD que não inclui nenhum usuário da Área de Trabalho Gerenciada da Microsoft ou dispositivos. Para ver etapas, [consulte Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).

**Aviso**

Certifique-se de que quaisquer políticas de conformidade que você tenha não tenham como alvo nenhum usuário da Área de Trabalho Gerenciada da Microsoft. Para ver etapas, [consulte Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).



### <a name="device-configuration-profiles"></a>Perfis de Configuração de Dispositivo

Os perfis de Configuração de Dispositivo do Intune em sua organização do Azure AD não devem ser destinados a nenhum dispositivo ou usuário da Área de Trabalho da Microsoft.

**Não está pronto**

Você tem pelo menos um perfil de configuração destinado a todos os usuários, todos os dispositivos ou ambos. Redefina o perfil para direcionar um grupo específico do Azure AD que não inclui nenhum dispositivo da Área de Trabalho Gerenciada da Microsoft. Para etapas, consulte [Criar um perfil com configurações personalizadas no Microsoft Intune](/mem/intune/configuration/custom-settings-configure).

**Aviso**

Certifique-se de que quaisquer políticas de configuração que você tenha não incluam nenhum dispositivo da Área de Trabalho Gerenciado da Microsoft ou usuários. Para etapas, consulte [Criar um perfil com configurações personalizadas no Microsoft Intune](/mem/intune/configuration/custom-settings-configure).



### <a name="device-type-restrictions"></a>Restrições de tipo de dispositivo

Os dispositivos da Área de Trabalho Gerenciada da Microsoft devem ter permissão para se inscrever no Intune.

**Não está pronto**

No momento, você tem pelo menos uma política de restrição de registro configurada para impedir que dispositivos Windows insuem no Intune. Siga as etapas em [Definir](/mem/intune/enrollment/enrollment-restrictions-set) restrições de registro para cada política de restrição de registro que se direciona aos usuários da Área de Trabalho Gerenciada da Microsoft e altere a configuração **do Windows (MDM)** como **Permitir**. No entanto, você pode definir qualquer **dispositivo** **Windows (MDM)** de propriedade pessoal para **Bloquear**. 


### <a name="enrollment-status-page"></a>Página status do registro

No momento, você tem a Página de Status de Registro (ESP) habilitada. Se você pretende participar da visualização pública da Área de Trabalho Gerenciada da Microsoft deste recurso, poderá ignorar esse item. Para obter mais informações, consulte [Experiência de primeira executar com o Autopilot e a Página de Status do Registro.](../get-started/esp-first-run.md)

**Não está pronto**

Você tem o perfil padrão ESP definido como **Mostrar o progresso da configuração do** aplicativo e do perfil. Desabilite essa configuração ou certifique-se de que as atribuições para qualquer grupo do Azure AD não incluam dispositivos da Área de Trabalho Gerenciada da Microsoft seguindo as etapas em Configurar a Página [de Status](/mem/intune/enrollment/windows-enrollment-status)de Registro .

**Aviso**

Certifique-se de que  quaisquer perfis que tenham a configuração Mostrar o aplicativo e a configuração de perfil não sejam atribuídos a nenhum grupo do Azure AD que inclua dispositivos da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, [consulte Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).

### <a name="microsoft-store-for-business"></a>Microsoft Store para empresas

Usamos a Microsoft Store para Empresas e implantamos o aplicativo Portal da Empresa na Área de Trabalho Gerenciada da Microsoft para permitir que os usuários instalem opcionalmente alguns aplicativos, como o Microsoft Project e o Microsoft Visio (quando permitido).

**Não está pronto**

A Microsoft Store para Empresas não está habilitada ou não está sincronizada com o Intune. Para obter mais informações, consulte [Como gerenciar aplicativos comprados](/mem/intune/apps/windows-store-for-business) por volume da Microsoft Store para Empresas com o Microsoft Intune e Instalar o Portal da Empresa do [Intune em dispositivos](../get-started/company-portal.md).

### <a name="multifactor-authentication"></a>Autenticação de vários fatores

A autenticação multifator não deve impedir que a Área de Trabalho Gerenciada da Microsoft gere o gerenciamento da sua organização do Azure AD (locatário) no Intune e no Azure AD.


**Não está pronto**

Você tem algumas políticas de autenticação multifator **definidas** como necessárias para políticas de acesso condicional atribuídas a todos os usuários. Durante o registro, excluiremos as contas de serviço da Área de Trabalho Gerenciada da Microsoft de políticas de acesso condicional relevantes e aplicaremos novas políticas de acesso condicional para restringir o acesso a essas contas. Para saber mais sobre essas contas de serviço, consulte [Procedimentos operacionais padrão](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Aviso**

Você tem a autenticação multifator necessária em políticas de acesso condicional que podem impedir que a Área de Trabalho Gerenciada da Microsoft gerencie o serviço de Área de Trabalho Gerenciada da Microsoft. Durante o registro, excluiremos as contas de serviço da Área de Trabalho Gerenciada da Microsoft de políticas de acesso condicional relevantes e aplicaremos novas políticas de acesso condicional para restringir o acesso a essas contas. Para saber mais sobre essas contas de serviço, consulte [Procedimentos operacionais padrão](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Erro**

A função Administrador do Intune não tem permissões suficientes para essa verificação. Você também precisará de qualquer uma dessas funções do Azure AD atribuídas para executar esta verificação:

- Leitor de segurança
- Administrador de Segurança
- Administrador de Acesso Condicional
- Leitor Global
- Administrador de Dispositivos


### <a name="powershell-scripts"></a>Scripts do PowerShell

Windows PowerShell scripts não podem ser atribuídos de uma maneira que direcionaria dispositivos da Área de Trabalho Gerenciada da Microsoft.  

**Aviso**

Certifique-se de Windows PowerShell scripts em sua organização do Azure AD não se direcionam a qualquer dispositivos ou usuários da Área de Trabalho da Microsoft. Não atribua um script do PowerShell para direcionar todos os usuários, todos os dispositivos ou ambos. Altere a política para usar um Assignment destinado a um grupo específico do Azure AD que não inclua nenhum dispositivo da Área de Trabalho Gerenciado da Microsoft ou usuários. Para obter mais informações, [consulte Usar scripts do PowerShell em dispositivos Windows 10 no Intune](/mem/intune/apps/intune-management-extension).

### <a name="region"></a>Região

Sua região deve ser suportada pela Área de Trabalho Gerenciada da Microsoft.

**Não está pronto**

Sua região de organização do Azure AD não é suportada atualmente pela Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).

**Aviso**

Um ou mais dos países onde sua organização do Azure AD está localizada não é suportado pela Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).


### <a name="security-baselines"></a>Linhas de base de segurança

As políticas de linha de base de segurança não devem direcionar nenhum dispositivo da Área de Trabalho Gerenciada da Microsoft.

**Não está pronto**

Você tem um perfil de linha de base de segurança destinado a todos os usuários, todos os dispositivos ou ambos. Altere a política para usar uma atribuição que se destina a um grupo específico do Azure AD que não inclua nenhum dispositivo da Área de Trabalho Gerenciada da Microsoft. Para etapas, [consulte Usar linhas de base de segurança para configurar dispositivos Windows 10 no Intune](/mem/intune/protect/security-baselines). Durante o registro, aplicamos uma nova linha de base de segurança a todos os dispositivos da Área de Trabalho Gerenciada da Microsoft. Após o registro, você pode revisar a política de linha de base de segurança da Área de Trabalho Gerenciada da Microsoft na área **de** política de configuração do Microsoft Endpoint Manager.

**Aviso**

Certifique-se de que todas as políticas de linha de base de segurança que você excluiu dispositivos da Área de Trabalho Gerenciada da Microsoft. Para etapas, [consulte Usar linhas de base de segurança para configurar dispositivos Windows 10 no Intune](/mem/intune/protect/security-baselines). Durante o registro, aplicamos uma nova linha de base de segurança a todos os dispositivos da Área de Trabalho Gerenciada da Microsoft. O **grupo Dispositivos** Modernos do Local de Trabalho - Todos os Azure AD é um grupo dinâmico que criamos quando você se inscreva na Área de Trabalho Gerenciada da Microsoft, portanto, você terá que voltar para excluir esse grupo após o registro. 


### <a name="windows-apps"></a>Aplicativos do Windows

Revise os aplicativos que você deseja que os usuários da Área de Trabalho Gerenciada da Microsoft tenham.

**Aviso**

Você deve preparar um inventário dos aplicativos que deseja que os usuários da Área de Trabalho Gerenciada da Microsoft tenham. Como esses aplicativos devem ser implantados pelo Intune, avalie o reutilizar aplicativos existentes do Intune. Considere usar o Portal da Empresa (consulte [Install Intune Company Portal on devices](../get-started/company-portal.md) and Enrollment Status Page (ESP) para distribuir aplicativos para seus usuários. Para obter mais informações, consulte [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).

Você pode solicitar ao representante da conta microsoft uma consulta no Microsoft Endpoint Configuration Manager para identificar os aplicativos que estão prontos para migrar para o Intune ou precisam de ajustes.


### <a name="windows-hello-for-business"></a>Windows Hello para Empresas

A Área de Trabalho Gerenciada da Microsoft exige que o Windows Hello para Empresas seja habilitado.

**Não está pronto**

O Windows Hello para Empresas está desabilitado. Habilita-o seguindo as etapas em [Criar uma política do Windows Hello para Empresas](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Aviso**

O Windows Hello para Empresas não está definido. Habilita-o seguindo as etapas em [Criar uma política do Windows Hello para Empresas.](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)


### <a name="windows-10-update-rings"></a>Anéis de atualização do Windows 10

Sua política de "anel de atualização do Windows 10" no Intune não deve direcionar nenhum dispositivo da Área de Trabalho Gerenciada da Microsoft.

**Não está pronto**

Você tem uma política de "toque de atualização" que direciona todos os dispositivos, todos os usuários ou ambos. Altere a política para usar um Assignment destinado a um grupo específico do Azure AD que não inclua nenhum dispositivo da Área de Trabalho Gerenciada da Microsoft. Para ver as etapas, [consulte Gerenciar atualizações de software do Windows 10 no Intune](/mem/intune/protect/windows-update-for-business-configure).

**Aviso**

Certifique-se de que todas as políticas de toque de atualização que você excluiu o grupo Dispositivos Modernos do Local de **Trabalho - Todos** os Azure AD. Se você atribuiu grupos de usuários do Azure AD a essas políticas, certifique-se de que todas as políticas de toque de atualização também excluíram o grupo Local de Trabalho Moderno **-** Todos os Azure AD ao que você adiciona seus usuários da Área de Trabalho Gerenciada da Microsoft (ou um grupo equivalente). Para ver as etapas, [consulte Gerenciar atualizações de software do Windows 10 no Intune](/mem/intune/protect/windows-update-for-business-configure). Os grupos Dispositivos Modernos do Local de Trabalho **-Todos** e Locais de Trabalho Modernos **-Todos** os grupos do Azure AD são grupos que criamos quando você se inscreva na Área de Trabalho Gerenciada da Microsoft, portanto, você terá que voltar para excluir esse grupo após o registro.


## <a name="azure-active-directory-settings"></a>Configurações do Azure Active Directory

Você pode acessar as configurações do Azure Active Directory no [portal do Azure.](https://portal.azure.com)

### <a name="intune-enrollment"></a>Registro no Intune

Os dispositivos Windows 10 em sua organização do Azure AD devem ser capazes de se registrar automaticamente no Intune.

**Aviso**

Certifique-se de que o escopo de usuário do **MDM** está definido **como Alguns** ou **Todos**, não **Nenhum**. Se você escolher **Alguns**, volte após o registro e selecione o  grupo Local de Trabalho Moderno **-All** Azure AD para Grupos ou um grupo equivalente destinado a todos os usuários da Área de Trabalho Gerenciada da Microsoft.  Consulte [Configurar o registro para dispositivos Windows usando o Microsoft Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment).


### <a name="ad-hoc-subscriptions"></a>Assinaturas ad hoc

Aconselha como verificar uma configuração que (se definida como "false") pode impedir que o Roaming de Estado Empresarial funciona corretamente.

**Aviso**

Verifique se **AllowAdHocSubscriptions** está definido como **True**. Caso contrário, o Enterprise State Roaming pode não funcionar. Para obter mais informações, [consulte Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).


### <a name="enterprise-state-roaming"></a>Roaming de Estado da Empresa

O Roaming de Estado Corporativo deve estar habilitado.

**Aviso**

Certifique-se de que o Enterprise State Roaming está habilitado para **Todos ou** para **grupos Selecionados.** Para obter mais informações, consulte [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).

### <a name="licenses"></a>Licenças

Várias licenças são necessárias para usar a Área de Trabalho Gerenciada da Microsoft.

**Não Pronto**

Você não tem todas as licenças de que precisa para usar a Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [Microsoft Managed Desktop technologies](../intro/technologies.md) and More about [licenses](prerequisites.md#more-about-licenses).


### <a name="microsoft-managed-desktop-service-accounts"></a>Contas de serviço da Área de Trabalho Gerenciada da Microsoft

Determinados nomes de conta podem estar em conflito com nomes de conta criados pela Área de Trabalho Gerenciada da Microsoft para gerenciar o serviço de Área de Trabalho Gerenciada da Microsoft.

**Não está pronto**

Você tem pelo menos um nome de conta que conflita com nomes de conta criados pela Área de Trabalho Gerenciada da Microsoft. Trabalhe com seu representante de conta da Microsoft para excluir esses nomes de conta. Não listamos os nomes de conta publicamente para minimizar o risco de segurança. 


### <a name="security-administrator-roles"></a>Funções de administrador de segurança

Os usuários com determinadas funções de segurança devem ter essas funções atribuídas no Microsoft Defender para Ponto de Extremidade.

**Aviso**

Se você tiver usuários atribuídos a qualquer uma dessas funções em sua organização do Azure AD, certifique-se de que eles também tenham essas funções atribuídas no Microsoft Defender para Ponto de Extremidade. Caso contrário, os administradores com essas funções não poderão acessar o portal de administração.

- Operador de segurança
- Leitor global

Para obter mais informações, [consulte Create and manage roles for role-based access control](/windows/security/threat-protection/microsoft-defender-atp/user-roles).


### <a name="security-default"></a>Padrão de segurança

Os padrões de segurança no Azure Active Directory impedirão que a Área de Trabalho Gerenciada da Microsoft gerencie seus dispositivos.

**Não está pronto**

Você tem os padrões de segurança ativas. Desativar os padrões de segurança e configurar políticas de acesso condicional. Para obter mais informações, consulte [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common).

### <a name="self-service-password-reset"></a>Redefinição de senha de autoatendados

A Redefinição de Senha autoatendida (SSPR) pode ser habilitada para todos os usuários da Área de Trabalho Gerenciada da Microsoft, excluindo contas de serviço da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte Tutorial: Permitir que os usuários desbloqueiem suas contas ou redefinir senhas usando a redefinição de senha de [autoatendados do Azure Active Directory.](/azure/active-directory/authentication/tutorial-enable-sspr)

**Aviso**

Certifique-se de que  a configuração Selecionada do SSPR inclua usuários da Área de Trabalho Gerenciada da Microsoft, mas exclua contas de serviço da Área de Trabalho Gerenciada da Microsoft. As contas de serviço da Área de Trabalho Gerenciada da Microsoft não podem funcionar conforme o esperado quando o SSPR está habilitado.  


### <a name="standard-user-role"></a>Função de usuário padrão

Além desses usuários que receberem funções do Azure AD de administrador global e administrador de dispositivos, os usuários da Área de Trabalho Gerenciada da Microsoft serão usuários padrão sem privilégios de administrador local. Todos os outros usuários receberão uma função de usuário padrão quando iniciarem o dispositivo da Área de Trabalho Gerenciada da Microsoft.

**Aviso**

Os usuários da Área de Trabalho Gerenciada da Microsoft não terão privilégios de administrador local em seus dispositivos da Área de Trabalho Gerenciada da Microsoft após o registro.

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps para empresas

### <a name="onedrive"></a>OneDrive

A **configuração Permitir sincronização somente em computadores ingressado em domínios específicos** entrará em conflito com a Área de Trabalho Gerenciada da Microsoft. Você pode acessar as configurações do OneDrive no Centro de administração [do](https://admin.onedrive.com)OneDrive.

**Aviso**

Você está usando a **configuração Permitir sincronização somente em PCs ingressado em domínios específicos.** Essa configuração não funcionará com a Área de Trabalho Gerenciada da Microsoft. Desabilite essa configuração e, em vez disso, configurar o OneDrive para usar uma política de acesso condicional. Consulte [Plan a Conditional Access deployment for](/azure/active-directory/conditional-access/plan-conditional-access) help.