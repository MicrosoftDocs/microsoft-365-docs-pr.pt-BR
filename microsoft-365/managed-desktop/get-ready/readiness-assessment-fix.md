---
title: Corrigir problemas encontrados pela ferramenta de avaliação de prontidão
description: Ações detalhadas a tomar para cada problema que a ferramenta localiza
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 22b5a6353720f8fbee218c138a3c9d0dee444db9
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114914"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Corrigir problemas encontrados pela ferramenta de avaliação de prontidão

Para cada verificação, a ferramenta relatará um dos quatro resultados possíveis:


|Resultado  |Significado  |
|---------|---------|
|Pronto     | Nenhuma ação é necessária antes de concluir o registro.        |
|Aviso    | Siga as etapas na ferramenta ou neste artigo para ter a melhor experiência com o registro e os usuários. Você *pode* concluir o registro, mas deve corrigir esses problemas antes de implantar seu primeiro dispositivo.        |
|Não está pronto | *O registro falhará se você não corrigir esses problemas.* Siga as etapas na ferramenta ou neste artigo para resolvê-las.        |
|Error | A função do Azure Active Directory (AD) que você está usando não tem permissão suficiente para executar essa verificação. |

> [!NOTE]
> Os resultados relatados por essa ferramenta refletem o status de suas configurações apenas no momento específico em que você a publicou. Se você posteriormente fizer alterações nas políticas do Microsoft Intune, do Azure Active Directory ou do Microsoft 365, os itens que estavam "Prontos" poderão se tornar "Não prontos". Para evitar problemas com as operações da Área de Trabalho Gerenciada da Microsoft, verifique as configurações específicas descritas neste artigo antes de alterar as políticas.

## <a name="microsoft-intune-settings"></a>Configurações do Microsoft Intune

Você pode acessar as configurações do Intune no centro de administração do Microsoft Endpoint [Manager.](https://endpoint.microsoft.com)

### <a name="autopilot-deployment-profile"></a>Perfil de implantação do Autopilot

Você não deve ter perfis existentes do Autopilot destinados a grupos atribuídos ou dinâmicos com dispositivos da Área de Trabalho Gerenciada da Microsoft. A Área de Trabalho Gerenciada da Microsoft usa o Autopilot para provisionar novos dispositivos.

**Não está pronto**

Você tem um perfil do Autopilot atribuído a todos os dispositivos. Para ver as etapas, [confira Registrar dispositivos Windows no Intune usando o Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot) Após o registro na Área de Trabalho Gerenciada da Microsoft, de configurar a política do Autopilot para excluir o grupo Dispositivos do Modern **Workplace -All** Azure AD.

**Aviso**

Certifique-se de que seus perfis do Autopilot visam um grupo do Azure AD atribuído ou dinâmico que não inclua dispositivos da Área de Trabalho Gerenciada da Microsoft. Para ver as etapas, [confira Registrar dispositivos Windows no Intune usando o Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot) Após o registro na Área de Trabalho Gerenciada da Microsoft, de configurar seus perfis do Autopilot para excluir o grupo Dispositivos de Local de Trabalho Moderno **-Todos do** Azure AD.


### <a name="certificate-connectors"></a>Conectores de certificado

Se você tiver conectores de certificado que serão usados pelos dispositivos que você deseja registrar na Área de Trabalho Gerenciada da Microsoft, os conectores não devem ter erros. Apenas um dos seguintes avisos será aplicado à sua situação, portanto, verifique-os cuidadosamente.

**Aviso**

Nenhum conector de certificado está presente. É possível que você não precise de nenhum conector, mas você deve avaliar se pode precisar de alguns para conectividade de rede em seus dispositivos da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [Preparar certificados e perfis de rede para a Área de Trabalho Gerenciada da Microsoft.](certs-wifi-lan.md)

**Aviso**

Pelo menos um conector de certificado tem um erro. Se você precisar desse conector para fornecer certificados para dispositivos da Área de Trabalho Gerenciada da Microsoft, deverá resolver o erro. Para obter mais informações, consulte [Preparar certificados e perfis de rede para a Área de Trabalho Gerenciada da Microsoft.](certs-wifi-lan.md)


**Aviso**

Você tem pelo menos um conector de certificado e nenhum erro é relatado. No entanto, na preparação para a implantação, talvez seja necessário criar um perfil para reutilizar o conector para dispositivos da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [Preparar certificados e perfis de rede para a Área de Trabalho Gerenciada da Microsoft.](certs-wifi-lan.md)


### <a name="conditional-access-policies"></a>Políticas de acesso condicional

As políticas de acesso condicional não devem impedir que a Área de Trabalho Gerenciada da Microsoft gerencie sua organização do Azure AD (locatário) no Intune e no Azure AD.

**Não está pronto**

Você tem pelo menos uma política de acesso condicional que segmenta todos os usuários. Durante o registro, excluiremos as contas de serviço da Área de Trabalho Gerenciada da Microsoft das políticas de acesso condicional relevantes e aplicaremos novas políticas de acesso condicional para restringir o acesso a essas contas. Após o registro, você pode revisar a política de acesso condicional da Área de Trabalho Gerenciada da Microsoft no Microsoft Endpoint Manager. Para saber mais sobre essas contas de serviço, consulte [Procedimentos operacionais Padrão.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Aviso**

Você tem políticas de acesso condicional que podem impedir que a Área de Trabalho Gerenciada da Microsoft gerencie o serviço de Área de Trabalho Gerenciada da Microsoft. Durante o registro, excluiremos as contas de serviço da Área de Trabalho Gerenciada da Microsoft das políticas de acesso condicional relevantes e aplicaremos novas políticas de acesso condicional para restringir o acesso a essas contas. Para obter mais informações sobre essas contas de serviço, consulte [Procedimentos operacionais Padrão.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Erro**

A função de Administrador do Intune não tem permissões suficientes para essa verificação. Você também precisará de qualquer uma dessas funções do Azure AD atribuídas para executar esta verificação:

- Leitor de segurança
- Administrador de Segurança
- Administrador de Acesso Condicional
- Leitor global
- Administrador de Dispositivos


### <a name="device-compliance-policies"></a>Políticas de conformidade do dispositivo

As políticas de Conformidade de Dispositivos do Intune em sua organização do Azure AD podem afetar dispositivos da Área de Trabalho Gerenciada da Microsoft.

**Não está pronto**

Você tem pelo menos uma política de conformidade que segmenta todos os usuários. A Área de Trabalho Gerenciada da Microsoft inclui políticas de conformidade que direcionarão seus dispositivos da Área de Trabalho Gerenciada da Microsoft.  Altere a política para direcionar um grupo específico do Azure AD que não inclui nenhum dispositivo ou usuário da Área de Trabalho Gerenciada da Microsoft. Para ver as etapas, [confira Criar uma política de conformidade no Microsoft Intune.](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)

**Aviso**

Certifique-se de que as políticas de conformidade que você tem não visam nenhum usuário da Área de Trabalho Gerenciada da Microsoft. Para ver as etapas, [confira Criar uma política de conformidade no Microsoft Intune.](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)



### <a name="device-configuration-profiles"></a>Perfis de configuração do dispositivo

Os perfis de Configuração de Dispositivo do Intune em sua organização do Azure AD não devem ter como alvo nenhum dispositivo ou usuário da Área de Trabalho da Microsoft.

**Não está pronto**

Você tem pelo menos um perfil de configuração destinado a todos os usuários, todos os dispositivos ou ambos. Redefina o perfil para direcionar um grupo específico do Azure AD que não inclui nenhum dispositivo da Área de Trabalho Gerenciada da Microsoft. Para ver as etapas, [confira Criar um perfil com configurações personalizadas no Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)

**Aviso**

Certifique-se de que quaisquer políticas de configuração que você tenha não incluam qualquer dispositivo ou usuário da Área de Trabalho Gerenciada da Microsoft. Para ver as etapas, [confira Criar um perfil com configurações personalizadas no Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)



### <a name="device-type-restrictions"></a>Restrições de tipo de dispositivo

Os dispositivos da Área de Trabalho Gerenciada da Microsoft devem ter permissão para se inscrever no Intune.

**Não está pronto**

Atualmente, você tem pelo menos uma política de restrição de registro configurada para impedir que dispositivos Windows se inscreverem no Intune. Siga as etapas [em](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) Definir restrições de registro para cada política de restrição de registro que segmenta os usuários da Área de Trabalho Gerenciada da Microsoft e altere a configuração do Windows **(MDM)** para **Permitir.** No entanto, você pode definir qualquer **dispositivo** **Windows (MDM)** de propriedade pessoal como **Block**. 


### <a name="enrollment-status-page"></a>Página status do registro

Atualmente, você tem a Página de Status do Registro (ESP) habilitada. Se você pretende participar da visualização pública da Área de Trabalho Gerenciada da Microsoft desse recurso, ignore esse item. Para obter mais informações, [consulte Experiência de primeira executar com o Autopilot e a página status do registro.](../get-started/esp-first-run.md)

**Não está pronto**

Você tem o perfil padrão ESP definido como Mostrar **o progresso da configuração do aplicativo e do perfil.** Desabilite essa configuração ou certifique-se de que as atribuições para qualquer grupo do Azure AD não incluam dispositivos da Área de Trabalho Gerenciada da Microsoft seguindo as etapas em Configurar a página [de status do registro.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)

**Aviso**

Certifique-se de que  quaisquer perfis que tenham a configuração Mostrar progresso da configuração do aplicativo e do perfil não sejam atribuídos a nenhum grupo do Azure AD que inclua dispositivos da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, [consulte Configurar a página de status do registro.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)

### <a name="microsoft-store-for-business"></a>Microsoft Store para empresas

Usamos a Microsoft Store para Empresas e implantamos o aplicativo Portal da Empresa na Área de Trabalho Gerenciada da Microsoft para permitir que os usuários instalem opcionalmente alguns aplicativos, como o Microsoft Project e o Microsoft Visio (onde permitido).

**Não está pronto**

A Microsoft Store para Empresas não está habilitada ou não está sincronizada com o Intune. Para obter mais informações, consulte Como gerenciar aplicativos comprados por volume da Microsoft Store para Empresas com [o Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) e instalar o Portal da Empresa do [Intune em dispositivos.](../get-started/company-portal.md)

### <a name="multifactor-authentication"></a>Autenticação de vários fatores

A autenticação multifator não deve impedir a Área de Trabalho Gerenciada da Microsoft de gerenciar sua organização do Azure AD (locatário) no Intune e no Azure AD.


**Não está pronto**

Você tem algumas políticas de autenticação multifator definidas como **necessárias** para políticas de acesso condicional atribuídas a todos os usuários. Durante o registro, excluiremos as contas de serviço da Área de Trabalho Gerenciada da Microsoft das políticas de acesso condicional relevantes e aplicaremos novas políticas de acesso condicional para restringir o acesso a essas contas. Para saber mais sobre essas contas de serviço, consulte [Procedimentos operacionais Padrão.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Aviso**

Você tem a autenticação multifator necessária em políticas de acesso condicional que podem impedir que a Área de Trabalho Gerenciada da Microsoft gerencie o serviço área de trabalho gerenciada da Microsoft. Durante o registro, excluiremos as contas de serviço da Área de Trabalho Gerenciada da Microsoft das políticas de acesso condicional relevantes e aplicaremos novas políticas de acesso condicional para restringir o acesso a essas contas. Para obter mais informações sobre essas contas de serviço, consulte [Procedimentos operacionais Padrão.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Erro**

A função de Administrador do Intune não tem permissões suficientes para essa verificação. Você também precisará de qualquer uma dessas funções do Azure AD atribuídas para executar esta verificação:

- Leitor de segurança
- Administrador de Segurança
- Administrador de Acesso Condicional
- Leitor global
- Administrador de Dispositivos


### <a name="powershell-scripts"></a>Scripts do PowerShell

Os scripts do Windows PowerShell não podem ser atribuídos de uma maneira que visar dispositivos da Área de Trabalho Gerenciada da Microsoft.  

**Aviso**

Certifique-se de que os scripts do Windows PowerShell em sua organização do Azure AD não segmentem nenhum dispositivo ou usuário da Área de Trabalho da Microsoft. Não atribua um script do PowerShell para direcionar todos os usuários, todos os dispositivos ou ambos. Altere a política para usar uma Atribuição que segmente um grupo específico do Azure AD que não inclua nenhum dispositivo ou usuário da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, [consulte Usar scripts do PowerShell em dispositivos Windows 10 no Intune.](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)

### <a name="region"></a>Região

Sua região deve ter suporte da Área de Trabalho Gerenciada da Microsoft.

**Não está pronto**

Sua região da organização do Azure AD não é suportada atualmente pela Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte Regiões e idiomas com suporte da Área de Trabalho [Gerenciada da Microsoft.](../service-description/regions-languages.md)

**Aviso**

Um ou mais dos países em que sua organização do Azure AD está localizada não são suportados pela Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte Regiões e idiomas com suporte da Área de Trabalho [Gerenciada da Microsoft.](../service-description/regions-languages.md)


### <a name="security-baselines"></a>Linhas de base de segurança

As políticas de linha de base de segurança não devem direcionar nenhum dispositivo da Área de Trabalho Gerenciada da Microsoft.

**Não está pronto**

Você tem um perfil de linha de base de segurança destinado a todos os usuários, todos os dispositivos ou ambos. Altere a política para usar uma atribuição que segmente um grupo específico do Azure AD que não inclua nenhum dispositivo da Área de Trabalho Gerenciada da Microsoft. Para etapas, consulte [Usar linhas de base de segurança para configurar dispositivos Windows 10 no Intune.](https://docs.microsoft.com/mem/intune/protect/security-baselines) Durante o registro, aplicamos uma nova linha de base de segurança a todos os dispositivos da Área de Trabalho Gerenciada da Microsoft. Após o registro, você pode revisar a política de linha de base de segurança da Área de Trabalho Gerenciada da Microsoft na área **de** política de configuração do Microsoft Endpoint Manager.

**Aviso**

Certifique-se de que quaisquer políticas de linha de base de segurança que você excluiu dispositivos da Área de Trabalho Gerenciada da Microsoft. Para etapas, consulte [Usar linhas de base de segurança para configurar dispositivos Windows 10 no Intune.](https://docs.microsoft.com/mem/intune/protect/security-baselines) Durante o registro, aplicamos uma nova linha de base de segurança a todos os dispositivos da Área de Trabalho Gerenciada da Microsoft. O grupo **Dispositivos** de Local de Trabalho Moderno - Todos do Azure AD é um grupo dinâmico que criamos quando você se inscreva na Área de Trabalho Gerenciada da Microsoft, portanto, você terá que voltar para excluir esse grupo após o registro. 


### <a name="windows-apps"></a>Aplicativos do Windows

Revise os aplicativos que você deseja que os usuários da Área de Trabalho Gerenciada da Microsoft tenham.

**Aviso**

Você deve preparar um inventário dos aplicativos que deseja que os usuários da Área de Trabalho Gerenciada da Microsoft tenham. Como esses aplicativos devem ser implantados pelo Intune, avalie a reutilizar aplicativos existentes do Intune. Considere usar o Portal da Empresa (confira Instalar o Portal da Empresa do [Intune](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) em dispositivos e a Página de Status do Registro (ESP) para distribuir aplicativos aos usuários. Para obter mais informações, consulte [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run).

Você pode solicitar ao representante da conta Microsoft uma consulta no Microsoft Endpoint Configuration Manager para identificar os aplicativos que estão prontos para migrar para o Intune ou precisam de ajustes.


### <a name="windows-hello-for-business"></a>Windows Hello para Empresas

A Área de Trabalho Gerenciada da Microsoft exige que o Windows Hello para Empresas seja habilitado.

**Não está pronto**

O Windows Hello para Empresas está desabilitado. Habilitando-o seguindo as etapas [em Criar uma política do Windows Hello para Empresas](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Aviso**

O Windows Hello para Empresas não está definido. Habilita-o seguindo as etapas em [Criar uma política do Windows Hello para Empresas.](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)


### <a name="windows-10-update-rings"></a>Anéis de atualização do Windows 10

Sua política "Anel de atualização do Windows 10" no Intune não deve direcionar nenhum dispositivo da Área de Trabalho Gerenciada da Microsoft.

**Não está pronto**

Você tem uma política de "anel de atualização" que segmenta todos os dispositivos, todos os usuários ou ambos. Altere a política para usar uma Atribuição que segmente um grupo específico do Azure AD que não inclua nenhum dispositivo da Área de Trabalho Gerenciada da Microsoft. Para ver as etapas, confira Gerenciar atualizações de [software do Windows 10 no Intune.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)

**Aviso**

Certifique-se de que todas as políticas de anel de atualização que você excluiu o grupo Dispositivos modernos do Local de Trabalho **– Todo o** Azure AD. Se você atribuiu grupos de usuários do Azure AD a essas políticas, certifique-se de que todas as políticas de anel de atualização também excluíram o grupo **Modern Workplace -All** Azure AD ao que você adiciona os usuários da Área de Trabalho Gerenciada da Microsoft (ou um grupo equivalente). Para ver as etapas, confira Gerenciar atualizações de [software do Windows 10 no Intune.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure) Os dispositivos modern **workplace -all** e **modern workplace -all** Azure AD groups are groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.


## <a name="azure-active-directory-settings"></a>Configurações do Azure Active Directory

Você pode acessar as configurações do Azure Active Directory no [portal do Azure.](https://portal.azure.com)

### <a name="intune-enrollment"></a>Registro do Intune

Os dispositivos Windows 10 em sua organização do Azure AD devem ser capazes de se inscrever automaticamente no Intune.

**Aviso**

Certifique-se de **que o escopo de usuário MDM** está definido como **Alguns** ou **Todos**, não **Nenhum**. Se você escolher **Alguns**, volte após o registro e selecione Modern **Workplace -All** Azure AD group for **Groups** ou um grupo equivalente destinado a todos os usuários da Área de Trabalho Gerenciada da Microsoft.  Consulte [Configurar o registro para dispositivos Windows usando o Microsoft Intune.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)


### <a name="ad-hoc-subscriptions"></a>Assinaturas ad hoc

Aconselha como verificar uma configuração que (se definida como "false") pode impedir que o Enterprise State Roaming funciona corretamente.

**Aviso**

Certifique-se **de que AllowAdHocSubscriptions** está definido como **True**. Caso contrário, o Enterprise State Roaming pode não funcionar. Para obter mais informações, [consulte Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).


### <a name="enterprise-state-roaming"></a>Roaming de Estado da Empresa

O Enterprise State Roaming deve estar habilitado.

**Aviso**

Certifique-se de que o Enterprise State Roaming está habilitado para **Todos ou** para **grupos Selecionados.** Para saber mais, confira [Habilitar Enterprise State Roaming no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)

### <a name="licenses"></a>Licenças

Várias licenças são necessárias para usar a Área de Trabalho Gerenciada da Microsoft.

**Não está pronto**

Você não tem todas as licenças de que precisa para usar a Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [As tecnologias da Área de Trabalho Gerenciada](../intro/technologies.md) da Microsoft [e muito mais sobre licenças.](prerequisites.md#more-about-licenses)


### <a name="security-account-names"></a>Nomes de contas de segurança

Certos nomes de contas de segurança podem estar em conflito com aqueles criados pela Área de Trabalho Gerenciada da Microsoft.

**Não está pronto**

Você tem pelo menos um nome de conta que entra em conflito com aqueles criados pela Área de Trabalho Gerenciada da Microsoft. Trabalhe com seu representante de conta da Microsoft para excluir esses nomes de conta.


### <a name="security-administrator-roles"></a>Funções de administrador de segurança

Os usuários com determinadas funções de segurança devem ter essas funções atribuídas no Microsoft Defender para Ponto de Extremidade.

**Aviso**

Se você tiver usuários atribuídos a qualquer uma dessas funções em sua organização do Azure AD, certifique-se de que eles também tenham essas funções atribuídas no Microsoft Defender para o Ponto de Extremidade. Caso contrário, os administradores com essas funções não poderão acessar o portal de administração.

- Operador de segurança
- Leitor global

Para obter mais informações, [consulte Criar e gerenciar funções para controle de acesso baseado em função.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)


### <a name="security-default"></a>Padrão de segurança

Os padrões de segurança no Azure Active Directory impedirão que a Área de Trabalho Gerenciada da Microsoft gerencie seus dispositivos.

**Não está pronto**

Os padrões de segurança estão ligado. Desativar os padrões de segurança e configurar políticas de acesso condicional. Para obter mais informações, consulte [Políticas comuns de Acesso Condicional.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)

### <a name="self-service-password-reset"></a>Redefinição de senha de autoatendado

A Redefinição de Senha de Autoatendido (SSPR) pode ser habilitada para todos os usuários da Área de Trabalho Gerenciada da Microsoft, excluindo as contas de serviço da Área de Trabalho Gerenciada da Microsoft. Para saber mais, confira Tutorial: Permitir que os usuários desbloqueiem suas contas ou redefinir senhas usando a redefinição de senha de autoatendenciamento do [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)

**Aviso**

Certifique-se de que a configuração SSPR **Selected** inclui usuários da Área de Trabalho Gerenciada da Microsoft, mas exclui contas de serviço da Área de Trabalho Gerenciada da Microsoft. As contas de serviço da Área de Trabalho Gerenciada da Microsoft não podem funcionar conforme o esperado quando o SSPR está habilitado.  


### <a name="standard-user-role"></a>Função de usuário padrão

Além dos usuários que têm funções do Azure AD atribuídas de Administrador global e administrador de dispositivos, os usuários da Área de Trabalho Gerenciada da Microsoft serão usuários padrão sem privilégios de administrador local. Todos os outros usuários receberão uma função de usuário padrão quando iniciarem o dispositivo de Área de Trabalho Gerenciada da Microsoft.

**Aviso**

Os usuários da Área de Trabalho Gerenciada da Microsoft não terão privilégios de administrador local em seus dispositivos da Área de Trabalho Gerenciada da Microsoft após o registro.

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps para empresas

### <a name="onedrive"></a>OneDrive

A **configuração Permitir sincronização somente em computadores ingressado em domínios específicos** entrará em conflito com a Área de Trabalho Gerenciada da Microsoft. Você pode acessar as configurações do OneDrive no centro de administração [do](https://admin.onedrive.com)OneDrive.

**Aviso**

Você está usando a **configuração Permitir sincronização somente em PCs ingressado em domínios específicos.** Essa configuração não funcionará com a Área de Trabalho Gerenciada da Microsoft. Desabilite essa configuração e, em vez disso, de configurar o OneDrive para usar uma política de acesso condicional. Consulte [Planejar uma implantação de Acesso Condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) para ajuda.
