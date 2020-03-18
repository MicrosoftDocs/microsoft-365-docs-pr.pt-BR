---
title: Detectar e corrigir a concessão de autorização ilícita no Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Saiba como reconhecer e corrigir o consentimento ilícito conceder ataque no Office 365.
ms.openlocfilehash: 171dbf586a869e9c85bb1e10b6beb7a2f4e5f425
ms.sourcegitcommit: 01ead889086ecc7dcf5d10244bcf67c5a33c8114
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2020
ms.locfileid: "42710520"
---
# <a name="detect-and-remediate-illicit-consent-grants-in-office-365"></a>Detectar e corrigir a concessão de autorização ilícita no Office 365

**Resumo**  Saiba como reconhecer e corrigir o consentimento ilícito conceder ataque no Office 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>O que é o ataque de concessão de consentimento ilícito no Office 365?

Em um ataque de concessão de consentimento ilícito, o invasor cria um aplicativo registrado pelo Azure que solicita acesso a dados, como informações de contato, email ou documentos. O invasor, então, vaza um usuário final para conceder a ele o consentimento de acessar seus dados através de um ataque de phishing ou injetando código ilícito em um site confiável. Depois que o aplicativo ilícito tiver sido concedido, ele terá acesso de nível de conta aos dados sem a necessidade de uma conta organizacional. Etapas de correção normais, como redefinir senhas para contas violadas ou exigir a autenticação multifator (MFA) em contas, não são eficazes contra esse tipo de ataque, já que são aplicativos de terceiros e são externos à organização. 

Esses ataques aproveitam um modelo de interação que pressupõe que a entidade que está chamando as informações é automação e não é um homem.

> [!IMPORTANT]
> Você suspeita que está tendo problemas com o consentimento ilícito-subsídios de um aplicativo, agora? O Microsoft Cloud app Security (MCAS) tem ferramentas para detectar, investigar e corrigir seus aplicativos OAuth. Este artigo do MCAS tem um tutorial que descreve como [analisar aplicativos OAuth arriscados](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth). Você também pode definir [as políticas de aplicativo OAuth](https://docs.microsoft.com/cloud-app-security/app-permission-policy) para investigar as permissões solicitadas pelo aplicativo, quais usuários estão autorizando esses aplicativos e, amplamente, aprovar ou proibir essas solicitações de permissões.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>O que um invasor de concessão de consentimento ilícito parece no Office 365?

Você precisa pesquisar o **log de auditoria** do Office 365 para encontrar sinais, também chamados de os indicadores de comprometimento (IOC) desse ataque. Para organizações com muitos aplicativos registrados pelo Azure e uma grande base de usuários, a prática recomendada é revisar as autorizações de consentimento de suas organizações por semana.

### <a name="steps-for-finding-signs-of-this-attack"></a>Etapas para encontrar sinais desse ataque

1. Abra o **centro de conformidade e segurança** em seu locatário do Office 365.

2. Navegue até **pesquisa** e selecione **pesquisa de log de auditoria**.

3. Pesquisa (todas as atividades e todos os usuários) e insira a data de início e a data de término, se necessário, e clique em **Pesquisar**. 

4. Filtre os resultados para obter o consentimento do aplicativo e adicione OAuth2PermissionGrant.

5. Clique no resultado para ver os detalhes da atividade. Clique em **mais informações** para obter detalhes da atividade. Verifique se IsAdminContent está definido como true.

> [!NOTE]
> * Pode levar de 30 minutos até 24 horas para que a entrada do log de auditoria correspondente seja exibida nos resultados da pesquisa após a ocorrência de um evento. <br/><br/> O período de tempo que um registro de auditoria é mantido e pesquisável no log de auditoria depende da sua assinatura do Office 365 e, especificamente, do tipo da licença atribuída a um usuário específico. Para obter mais informações, consulte [log de auditoria](../../compliance/search-the-audit-log-in-security-and-compliance.md).
Se esse valor for true, ele indicará que alguém com acesso de administrador global pode ter concedido acesso amplo aos dados. Se isso for inesperado, execute etapas para [confirmar um ataque](#how-to-confirm-an-attack).

## <a name="how-to-confirm-an-attack"></a>Como confirmar um ataque

Se você tiver uma ou mais instâncias do IOCs listadas acima, precisará fazer mais investigações para confirmar positivamente que o ataque ocorreu. Você pode usar qualquer um destes três métodos para confirmar o ataque.

- Aplicativos de inventário e suas permissões usando o portal do Azure Active Directory. Este método é completo, mas você só pode verificar um usuário de cada vez, o que pode ser muito demorado se você tiver muitos usuários para verificar.

- Aplicativos de inventário e suas permissões usando o PowerShell. Esse é o método mais rápido e completo, com a menor quantidade de sobrecarga.

- Peça aos usuários que verifiquem seus aplicativos e permissões individualmente e relatam os resultados de volta aos administradores para correção.

## <a name="inventory-apps-with-access-in-your-organization"></a>Aplicativos de inventário com acesso em sua organização

Você pode fazer isso para seus usuários com o portal do Azure Active Directory ou o PowerShell ou fazer com que os usuários enumerem individualmente o acesso ao aplicativo.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Etapas para usar o portal do Azure Active Directory

Você pode pesquisar os aplicativos aos quais qualquer usuário individual concedeu permissões usando o [portal do Azure Active Directory](https://portal.azure.com/).

1. Entre no portal do Azure com direitos administrativos.

2. Selecione a folha do Azure Active Directory.

3. Selecione **Usuários**.

4. Selecione o usuário que você deseja revisar.

5. Selecione **aplicativos**.

Isso mostrará os aplicativos atribuídos ao usuário e as permissões que os aplicativos têm.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Etapas para que os usuários enumerem o acesso ao aplicativo

Peça aos usuários para https://myapps.microsoft.com revisar e examinar o acesso de seu próprio aplicativo. Eles devem ser capazes de ver todos os aplicativos com acesso, exibir detalhes sobre eles (incluindo o escopo de acesso) e revogar privilégios para aplicativos suspeitos ou ilícitos.

### <a name="steps-for-doing-this-with-powershell"></a>Etapas para fazer isso com o PowerShell

A maneira mais simples de verificar o consentimento ilícito de concessão é executar o [Get-AzureADPSPermissions. ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), que irá despejar todos os subsídios de consentimento OAuth e aplicativos OAuth para todos os usuários em sua locação em um arquivo. csv.

#### <a name="pre-requisites"></a>Pré-requisitos

- A biblioteca do Azure AD PowerShell instalada.

- Direitos de administrador global no locatário em que o script será executado.

- Administrador local no computador a partir do qual o irá executar os scripts.

> [!IMPORTANT]
> É ***altamente recomendável*** que você exija a autenticação multifator em sua conta administrativa. Esse script oferece suporte à autenticação da MFA.

1. Entre no computador em que você executará o script com direitos de administrador local.

2. Baixe ou copie o script [Get-AzureADPSPermissions. ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) do GitHub para uma pasta a partir da qual você executará o script. Essa será a mesma pasta para a qual o arquivo de saída "Permissions. csv" será gravado.

3. Abra uma instância do PowerShell como administrador e abra a pasta para a qual você salvou o script.

4. Conecte-se ao seu diretório usando o cmdlet [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) .

5. Execute este comando do PowerShell:

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

O script produz um arquivo chamado Permissions. csv. Siga estas etapas para procurar por subsídios de permissão de aplicativo ilícitos:

1. Na coluna resenttype (coluna G), procure o valor "multiprincípios". A permissão de entidades de segurança permite que o aplicativo cliente acesse o conteúdo de todos os usuários na locação. Aplicativos nativos do Office 365 precisam que essa permissão funcione corretamente. Todo aplicativo não-Microsoft com essa permissão deve ser revisado com cuidado.

2. Na coluna permissão (coluna F) revise as permissões que cada aplicativo delegado tem para conteúdo. Procure por permissões de "leitura" e "gravação" ou "*. All ", e revise-as cuidadosamente porque elas podem não ser apropriadas.

3. Revise os usuários específicos que foram concedidos. Se os usuários de alto perfil ou alto impacto tiverem autorização inadequada, você deverá investigar mais.

4. Na coluna ClientDisplayName (coluna C), procure aplicativos que parecem suspeitos. Os aplicativos com nomes digitados incorretamente, nomes Bland ou nomes de som de hackers devem ser revisados com cuidado.

## <a name="determine-the-scope-of-the-attack"></a>Determinar o escopo do ataque

Após concluir o inventário do acesso ao aplicativo, revise o **log de auditoria** do Office 365 para determinar o escopo completo da violação. Pesquisar os usuários afetados, os intervalos de tempo que o aplicativo ilícito tinha acesso à sua organização e as permissões que o aplicativo tinha. Você pode pesquisar o **log de auditoria** no [centro de segurança e conformidade do Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

> [!IMPORTANT]
> A [auditoria de caixa de correio](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) e [a auditoria de atividades para administradores e usuários](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) devem ter sido habilitadas antes do ataque para obter essas informações.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Como interromper e corrigir um ataque de concessão de consentimento ilícito

Após identificar um aplicativo com permissões ilícita, você tem várias maneiras de remover esse acesso.

- Você pode revogar a permissão do aplicativo no portal do Azure Active Directory:

  - Navegue até o usuário afetado na folha de **usuários do Azure Active Directory** .

  - Selecione **aplicativos**.

  - Selecione o aplicativo ilícito.

  - Clique em **remover** na busca detalhada.

- Você pode revogar a concessão de consentimento OAuth com o PowerShell seguindo as etapas em [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).

- Você pode revogar a atribuição da função de aplicativo de serviço com o PowerShell seguindo as etapas em [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).

- Você também pode desabilitar a entrada para a conta afetada, o que, por sua vez, desabilitará o acesso do aplicativo aos dados dessa conta. Isso não é ideal para a produtividade do usuário final, mas se você estiver trabalhando para limitar o impacto rapidamente, pode ser uma remediação de curto prazo viável.

- Você pode desativar aplicativos integrados para sua locação. Esta é uma etapa drástica que desabilita a capacidade de os usuários finais concederem o consentimento por todo o locatário. Isso impede que os usuários conceda acidentalmente acesso a um aplicativo mal-intencionado. Isso não é altamente recomendado, pois ele prejudica seriamente a capacidade dos usuários de ser produtiva com aplicativos de terceiros. Você pode fazer isso seguindo as etapas em [ativando ou desativando aplicativos integrados](https://docs.microsoft.com/office365/admin/misc/integrated-apps).

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Proteja o Office 365 como um profissional de cibersegurança

Sua assinatura do Office 365 vem com um poderoso conjunto de recursos de segurança que você pode usar para proteger seus dados e seus usuários. Use o [roteiro de segurança do Office 365: Principais prioridades para os primeiros 30 dias, 90 dias e além](security-roadmap.md), para implementar práticas recomendadas pela Microsoft para proteger o seu locatário do Office 365.

- Tarefas a realizar nos primeiros 30 dias. Estas têm efeito imediato e baixo impacto para seus usuários.

- Tarefas para realizar em 90 dias. Estas levam um pouco mais de tempo para planejar e implementar, mas melhoram muito sua postura de segurança.

- Além de 90 dias. Estes aprimoramentos são desenvolvidos nos seus primeiros 90 dias de trabalho.

## <a name="see-also"></a>Confira também:

- [Aplicativo inesperado na lista meus aplicativos](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) orienta os administradores por meio de várias ações que podem ser tomadas após perceber que há aplicativos inesperados com acesso aos dados.

- A [integração de aplicativos com o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) é uma visão geral de consentimento e permissões de alto nível.

- [Problemas para desenvolver meu aplicativo](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) fornece links para vários artigos relacionados a consentimento.

- Os [objetos de entidade de serviço e de aplicativo no Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) fornece uma visão geral dos objetos de entidade de serviço e aplicativo que são fundamentais para o modelo de aplicativo.

- [Manage Access to apps](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) é uma visão geral dos recursos que os administradores precisam para gerenciar o acesso de usuários aos aplicativos.
