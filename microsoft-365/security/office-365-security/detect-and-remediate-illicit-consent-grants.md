---
title: Detectar e remediar concessões de consentimento ilícito
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
localization_priority: Normal
search.appverid:
- MET150
description: Saiba como reconhecer e remediar o consentimento ilícito concede ataques Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cb3ccfbb921c106b671c4409bb95bd200f0efb55
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083003"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>Detectar e remediar concessões de consentimento ilícito

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Resumo**  Saiba como reconhecer e remediar o consentimento ilícito concede ataques Microsoft 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-microsoft-365"></a>Qual é o ataque de concessão de consentimento ilícito Microsoft 365?

Em um ataque de concessão de consentimento ilícito, o invasor cria um aplicativo registrado no Azure que solicita acesso a dados como informações de contato, email ou documentos. Em seguida, o invasor faz com que um usuário final conceda ao aplicativo o consentimento para acessar seus dados por meio de um ataque de phishing ou injetando código ilícito em um site confiável. Após o consentimento do aplicativo ilícito, ele tem acesso no nível da conta aos dados sem a necessidade de uma conta organizacional. As etapas normais de correção, como redefinir senhas para contas violadas ou exigir A autenticação multifato (MFA) em contas, não são eficazes contra esse tipo de ataque, pois são aplicativos de terceiros e são externos à organização.

Esses ataques aproveitam um modelo de interação que presume que a entidade que está chamando as informações seja automação e não humana.

> [!IMPORTANT]
> Você suspeita que está enfrentando problemas com concessões ilícitas de consentimento de um aplicativo, agora? Microsoft Cloud App Security (MCAS) tem ferramentas para detectar, investigar e remediar seus aplicativos OAuth. Este artigo do MCAS tem um tutorial que descreve como investigar aplicativos [OAuth arriscados.](/cloud-app-security/investigate-risky-oauth) Você também pode definir políticas de aplicativo [OAuth](/cloud-app-security/app-permission-policy) para investigar permissões solicitadas pelo aplicativo, quais usuários estão autorizando esses aplicativos e aprovar ou proibir amplamente essas solicitações de permissão.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-microsoft-365"></a>Qual é a aparência de um ataque de concessão de consentimento ilícito Microsoft 365?

Você precisa pesquisar no **log de auditoria para** encontrar sinais, também chamados indicadores de comprometimento (IOC) desse ataque. Para organizações com muitos aplicativos registrados no Azure e uma grande base de usuários, a melhor prática é revisar as concessões de consentimento de suas organizações semanalmente.

### <a name="steps-for-finding-signs-of-this-attack"></a>Etapas para encontrar sinais desse ataque

1. Abra o **Microsoft 365 Defender portal em** e selecione <https://security.microsoft.com> **Audit**. Ou, para ir diretamente para a página **Auditoria,** use <https://security.microsoft.com/auditlogsearch> .

2. Na página **Auditoria,** verifique se a guia **Pesquisa** está selecionada e configure as seguintes configurações:
   - **Intervalo de data e hora**
   - **Atividades**: Verifique se **Mostrar resultados de todas as atividades** está selecionado.

   Quando terminar, clique em **Pesquisar**.

3. Clique na **coluna Atividade** para classificar os resultados e procure Consent **to application**.

4. Selecione uma entrada na lista para ver os detalhes da atividade. Verifique se IsAdminContent está definido como True.

> [!NOTE]
>
> Pode levar de 30 minutos até 24 horas para que a entrada de log de auditoria correspondente seja exibida nos resultados da pesquisa depois que um evento ocorrer.
>
> O período de tempo em que um registro de auditoria é mantido e pesquisável no log de auditoria depende da sua assinatura Microsoft 365 e, especificamente, do tipo de licença atribuída a um usuário específico. Para obter mais informações, consulte [Log de auditoria](../../compliance/search-the-audit-log-in-security-and-compliance.md).
>
> Se esse valor for verdadeiro, ele indicará que alguém com acesso ao Administrador Global pode ter concedido amplo acesso aos dados. Se isso for inesperado, tome medidas para [confirmar um ataque](#how-to-confirm-an-attack).

## <a name="how-to-confirm-an-attack"></a>Como confirmar um ataque

Se você tiver uma ou mais instâncias dos IOCs listados acima, será necessário fazer uma investigação posterior para confirmar positivamente que o ataque ocorreu. Você pode usar qualquer um desses três métodos para confirmar o ataque:

- Aplicativos de inventário e suas permissões usando o Azure Active Directory portal. Esse método é completo, mas você só pode verificar um usuário por vez, o que pode levar muito tempo se você tiver muitos usuários para verificar.
- Aplicativos de inventário e suas permissões usando o PowerShell. Esse é o método mais rápido e completo, com a menor quantidade de sobrecarga.
- Verifique individualmente seus aplicativos e permissões e reporte os resultados aos administradores para correção.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventário de aplicativos com acesso em sua organização

Você pode fazer isso para seus usuários com o portal Azure Active Directory ou o PowerShell ou fazer com que seus usuários enumeram individualmente o acesso ao aplicativo.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Etapas para usar o Azure Active Directory Portal

Você pode procurar os aplicativos aos quais qualquer usuário individual concedeu permissões usando o portal Azure Active Directory em <https://portal.azure.com> .

1. Entre no portal do Azure com direitos administrativos.
2. Selecione a Azure Active Directory.
3. Selecione **Usuários**.
4. Selecione o usuário que você deseja revisar.
5. Selecione **Aplicativos**.

Isso mostrará os aplicativos atribuídos ao usuário e quais permissões os aplicativos têm.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Etapas para que seus usuários enumeram o acesso ao aplicativo

Fazer com que os usuários <https://myapps.microsoft.com> acessem e revisem seu próprio acesso ao aplicativo. Eles devem poder ver todos os aplicativos com acesso, exibir detalhes sobre eles (incluindo o escopo de acesso) e revogar privilégios para aplicativos suspeitos ou ilícitos.

### <a name="steps-for-doing-this-with-powershell"></a>Etapas para fazer isso com o PowerShell

A maneira mais simples de verificar o ataque de Concessão de Consentimento Ilícito é executar o [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), que despeja todas as concessões de consentimento OAuth e aplicativos OAuth para todos os usuários em sua posição de .csv arquivo.

#### <a name="pre-requisites"></a>Pré-requisitos

- A biblioteca do Azure AD PowerShell instalada.
- Direitos de administrador global no locatário em que o script será executado.
- Administrador local no computador do qual executará os scripts.

> [!IMPORTANT]
> É ***altamente recomendável*** que você exige autenticação multifafação em sua conta administrativa. Este script dá suporte à autenticação MFA.

1. Entre no computador de onde você executará o script com direitos de administrador local.

2. Baixe ou copie o [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) de GitHub para uma pasta da qual você executará o script. Essa será a mesma pasta na qual o arquivo de saída "permissions.csv" será gravado.

3. Abra uma sessão do PowerShell como administrador e abra para a pasta na qual você salvou o script.

4. Conexão seu diretório usando o [cmdlet Conexão-AzureAD.](/powershell/module/azuread/connect-azuread)

5. Execute este comando do PowerShell:

   ```powershell
   .\Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

O script produz um arquivo chamado Permissions.csv. Siga estas etapas para procurar concessões de permissão ilícitas de aplicativo:

1. Na coluna ConsentType (coluna G) procure o valor "AllPrinciples". A permissão AllPrincipals permite que o aplicativo cliente acesse o conteúdo de todos na área de trabalho. Aplicativos Microsoft 365 nativos precisam dessa permissão para funcionar corretamente. Todos os aplicativos que não são da Microsoft com essa permissão devem ser analisados cuidadosamente.

2. Na coluna Permissão (coluna F), revise as permissões que cada aplicativo delegado tem para o conteúdo. Procure a permissão "Leitura" e "Gravação" ou "*. Permissão All" e revise-os cuidadosamente porque podem não ser apropriados.

3. Revise os usuários específicos que têm consentimentos concedidos. Se usuários de alto perfil ou de alto impacto têm consentimentos inadequados concedidos, você deve investigar mais.

4. Na coluna ClientDisplayName (coluna C), procure aplicativos que pareçam suspeitos. Os aplicativos com nomes mal escritos, nomes super sem graça ou nomes de sons de hackers devem ser analisados cuidadosamente.

## <a name="determine-the-scope-of-the-attack"></a>Determinar o escopo do ataque

Depois de terminar o inventário do acesso ao aplicativo, revise o log de **auditoria** para determinar o escopo completo da violação. Pesquise os usuários afetados, os períodos em que o aplicativo ilícito teve acesso à sua organização e as permissões que o aplicativo tinha. Você pode pesquisar **o log de auditoria** no portal Microsoft 365 Defender [.](../../compliance/search-the-audit-log-in-security-and-compliance.md)

> [!IMPORTANT]
> [A auditoria de caixa](../../compliance/enable-mailbox-auditing.md) de correio e a [auditoria](../../compliance/turn-audit-log-search-on-or-off.md) de atividade para administradores e usuários devem ter sido habilitadas antes do ataque para que você receba essas informações.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Como parar e remediar um ataque de concessão de consentimento ilícito

Depois de identificar um aplicativo com permissões ilícitas, você tem várias maneiras de remover esse acesso.

- Você pode revogar a permissão do aplicativo no portal Azure Active Directory por:
  1. Navegue até o usuário afetado na **folha Azure Active Directory Usuário.**
  2. Selecione **Aplicativos**.
  3. Selecione o aplicativo ilícito.
  4. Clique **em Remover** na broca para baixo.

- Você pode revogar a concessão de consentimento OAuth com o PowerShell seguindo as etapas em [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).

- Você pode revogar a atribuição de função de aplicativo de serviço com o PowerShell seguindo as etapas em [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).

- Você também pode desabilitar completamente a entrada para a conta afetada, o que, por sua vez, desabilitará o acesso do aplicativo aos dados nessa conta. Isso não é ideal para a produtividade do usuário final, é claro, mas se você estiver trabalhando para limitar o impacto rapidamente, pode ser uma correção viável a curto prazo.

- Você pode desativar aplicativos integrados para a sua adimplência. Esta é uma etapa drástica que desabilita a capacidade de os usuários finais concederem consentimento em toda a locatário. Isso impede que seus usuários concedam inadvertidamente acesso a um aplicativo mal-intencionado. Isso não é altamente recomendado, pois prejudica gravemente a capacidade dos usuários de serem produtivos com aplicativos de terceiros. Você pode fazer isso seguindo as etapas em [Ligar ou desligar aplicativos integrados.](../../admin/misc/user-consent.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Proteja o Microsoft 365 como um profissional de segurança cibernética

Sua assinatura do Microsoft 365 vem com um poderoso conjunto de recursos de segurança que você pode usar para proteger seus dados e seus usuários. Use o [roteiro de segurança do Microsoft 365: principais prioridades para os primeiros 30 dias, 90 dias e depois](security-roadmap.md) para implementar práticas recomendadas para proteger o seu locatário do Microsoft 365.

- Tarefas a realizar nos primeiros 30 dias. Estas têm efeito imediato e baixo impacto para seus usuários.
- Tarefas a serem cumpridas em 90 dias. Isso leva um pouco mais de tempo para planejar e implementar, mas melhora muito sua postura de segurança.
- Mais de 90 dias. Essas melhorias são incluídas em seus primeiros 90 dias de trabalho.

## <a name="see-also"></a>Confira também

- [O aplicativo inesperado em minha lista de](/azure/active-directory/application-access-unexpected-application) aplicativos orienta os administradores por meio de várias ações que podem ser tomadas depois de perceber que há aplicativos inesperados com acesso a dados.
- [Integrar aplicativos com Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) é uma visão geral de alto nível de consentimento e permissões.
- [Problemas no desenvolvimento do meu aplicativo](/azure/active-directory/active-directory-application-dev-development-content-map) fornece links para vários artigos relacionados ao consentimento.
- Os objetos principais de aplicativos e serviços [no Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) fornece uma visão geral dos objetos principais aplicativo e serviço que são fundamentais para o modelo de aplicativo.
- [Gerenciar o acesso a aplicativos](/azure/active-directory/active-directory-managing-access-to-apps) é uma visão geral dos recursos que os administradores têm para gerenciar o acesso do usuário aos aplicativos.
