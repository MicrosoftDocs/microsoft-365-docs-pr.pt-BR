---
title: Detectar e remediar concessões de autorização ilícitas
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
description: Saiba como reconhecer e remediar o ataque de concessão de autorização ilícita no Microsoft Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a50ce58d91d2ff7b2e31e57830289c870364d9b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288282"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>Detectar e remediar concessões de autorização ilícitas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

**Resumo**  Saiba como reconhecer e remediar o ataque de concessão de autorização ilícita no Office 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>Qual é o ataque de concessão de autorização ilícita no Office 365?

Em um ataque de concessão de consentimento ilícito, o invasor cria um aplicativo registrado no Azure que solicita acesso a dados como informações de contato, email ou documentos. Em seguida, o invasor faz com que um usuário final conceda ao aplicativo o consentimento para acessar seus dados por meio de um ataque de phishing ou injetando código ilícito em um site confiável. Após o consentimento do aplicativo ilícito, ele tem acesso em nível de conta aos dados sem a necessidade de uma conta organizacional. As etapas de correção normal, como redefinir senhas para contas violadas ou exigir A MFA (Autenticação Multifatória) em contas, não são eficazes contra esse tipo de ataque, pois são aplicativos de terceiros e são externos à organização.

Esses ataques aproveitam um modelo de interação que presume que a entidade que está chamando as informações é automação e não uma pessoa.

> [!IMPORTANT]
> Você suspeita que está tendo problemas com concessões ilícitas de consentimento de um aplicativo, no momento? O Microsoft Cloud App Security (MCAS) tem ferramentas para detectar, investigar e remediar seus aplicativos OAuth. Este artigo do MCAS tem um tutorial que descreve como investigar aplicativos [OAuth arriscados.](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth) Você também pode definir políticas de aplicativo [OAuth](https://docs.microsoft.com/cloud-app-security/app-permission-policy) para investigar permissões solicitadas pelo aplicativo, quais usuários estão autorizando esses aplicativos e aprovar ou proibir amplamente essas solicitações de permissão.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>Qual é a aparência de um ataque de concessão de autorização ilícita no Office 365?

Você precisa pesquisar o **log de auditoria** para encontrar sinais, também chamados de Indicadores de Comprometimento (IOC) desse ataque. Para organizações com muitos aplicativos registrados no Azure e uma grande base de usuários, a prática melhor é revisar as concessões de consentimento de suas organizações semanalmente.

### <a name="steps-for-finding-signs-of-this-attack"></a>Etapas para encontrar sinais desse ataque

1. Abra o **Centro de Conformidade & segurança** em <https://protection.office.com> .

2. Navegue até **Pesquisa** e selecione **Pesquisa de log de auditoria.**

3. Pesquise (todas as atividades e todos os usuários) e insira a data de início e a data de término, se necessário, e clique em **Pesquisar.**

4. Clique **nos resultados de** Filtro e insira Consentimento para o aplicativo no **campo** Atividade.

5. Clique no resultado para ver os detalhes da atividade. Clique **em Mais Informações** para obter detalhes da atividade. Verifique se IsAdminContent está definido como True.

> [!NOTE]
>
> Pode levar de 30 minutos a 24 horas para que a entrada de log de auditoria correspondente seja exibida nos resultados da pesquisa depois que um evento ocorre.
>
> O período em que um registro de auditoria é mantido e pesquisável no log de auditoria depende da sua assinatura do Microsoft 365 e, especificamente, do tipo de licença atribuída a um usuário específico. Para obter mais informações, consulte [Log de auditoria.](../../compliance/search-the-audit-log-in-security-and-compliance.md)
>
> Se esse valor for verdadeiro, indica que alguém com acesso de Administrador Global pode ter concedido amplo acesso aos dados. Se isso for inesperado, tome as medidas necessárias [para confirmar um ataque.](#how-to-confirm-an-attack)

## <a name="how-to-confirm-an-attack"></a>Como confirmar um ataque

Se você tiver uma ou mais instâncias dos IOCs listados acima, precisará fazer uma investigação mais precisa para confirmar positivamente que o ataque ocorreu. Você pode usar qualquer um destes três métodos para confirmar o ataque:

- Inventaria aplicativos e suas permissões usando o portal do Azure Active Directory. Esse método é completo, mas você só pode verificar um usuário por vez, o que pode ser muito demorado se você tiver muitos usuários para verificar.

- Inventaria aplicativos e suas permissões usando o PowerShell. Esse é o método mais rápido e mais completo, com a menor quantidade de sobrecarga.

- Fazer com que os usuários verifiquem individualmente seus aplicativos e permissões e re reportem os resultados aos administradores para correção.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventariar aplicativos com acesso em sua organização

Você pode fazer isso para seus usuários com o Portal do Azure Active Directory ou o PowerShell ou fazer com que os usuários enumerem individualmente o acesso ao aplicativo.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Etapas para usar o Portal do Azure Active Directory

Você pode procurar os aplicativos aos quais qualquer usuário individual concedeu permissões usando o Portal do [Azure Active Directory.](https://portal.azure.com/)

1. Entre no Portal do Azure com direitos administrativos.

2. Selecione a folha do Azure Active Directory.

3. Selecione **Usuários**.

4. Selecione o usuário que você deseja analisar.

5. Selecione **Aplicativos**.

Isso mostrará os aplicativos atribuídos ao usuário e quais permissões os aplicativos têm.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Etapas para que seus usuários enumerem o acesso ao aplicativo

Que seus usuários acessem https://myapps.microsoft.com e revisem seu próprio acesso a aplicativos lá. Eles devem ser capazes de ver todos os aplicativos com acesso, exibir detalhes sobre eles (incluindo o escopo de acesso) e ser capazes de revogar privilégios para aplicativos suspeitos ou ilícitos.

### <a name="steps-for-doing-this-with-powershell"></a>Etapas para fazer isso com o PowerShell

A maneira mais simples de verificar o ataque de [ Concessão ](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)de Autorização Ilícita é executar oGet-AzureADPSPermissions.ps1, que despeja todos os aplicativos OAuth e concessões de consentimento do OAuth para todos os usuários em sua adoção em um arquivo .csv.

#### <a name="pre-requisites"></a>Pré-requisitos

- A biblioteca do Azure AD PowerShell instalada.

- Direitos de administrador global no locatário em que o script será executado.

- Administrador Local no computador a partir do qual os scripts serão executados.

> [!IMPORTANT]
> É ***altamente recomendável*** que você refancie a autenticação multifabilativa em sua conta administrativa. Esse script dá suporte à autenticação MFA.

1. Entre no computador em que você executará o script com direitos de administrador local.

2. Baixe ou copie o [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script do GitHub para uma pasta da qual você executará o script. Essa será a mesma pasta na qual o arquivo de saída "permissions.csv" será gravado.

3. Abra uma instância do PowerShell como administrador e abra a pasta em que você salvou o script.

4. Conecte-se ao seu diretório usando o cmdlet [Connect-AzureAD.](https://docs.microsoft.com/powershell/module/azuread/connect-azuread)

5. Execute este comando do PowerShell:

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

O script produz um arquivo chamado Permissions.csv. Siga estas etapas para procurar concessões ilícitas de permissão de aplicativo:

1. Na coluna ConsentType (coluna G), procure o valor "AllPrinciples". A permissão AllPrincipals permite que o aplicativo cliente acesse o conteúdo de todos na loja. Os aplicativos nativos do Microsoft 365 precisam dessa permissão para funcionar corretamente. Todos os aplicativos que não são da Microsoft com essa permissão devem ser analisados cuidadosamente.

2. Na coluna Permissão (coluna F), revise as permissões que cada aplicativo delegado tem para o conteúdo. Procure as permissões "Leitura" e "Gravação" ou "*. Permissão Todos" e revise-as cuidadosamente, pois elas podem não ser apropriadas.

3. Revise os usuários específicos que têm consentimentos concedidos. Se usuários de alto perfil ou alto impacto têm consentimentos inadequados concedidos, você deve investigar mais.

4. Na coluna ClientDisplayName (coluna C), procure aplicativos que pareçam suspeitos. Os aplicativos com nomes errados, nomes super-nativos ou nomes de hacker devem ser analisados cuidadosamente.

## <a name="determine-the-scope-of-the-attack"></a>Determinar o escopo do ataque

Depois de terminar de inventariá-lo, revise o **log de auditoria** para determinar o escopo completo da violação. Pesquise os usuários afetados, os períodos de tempo que o aplicativo ilícito tinha acesso à sua organização e as permissões que o aplicativo tinha. Você pode pesquisar o **log de auditoria** no Centro de Conformidade e Segurança do Microsoft [365.](../../compliance/search-the-audit-log-in-security-and-compliance.md)

> [!IMPORTANT]
> [A auditoria de caixa](../../compliance/enable-mailbox-auditing.md) [de](../../compliance/turn-audit-log-search-on-or-off.md) correio e a auditoria de atividades para administradores e usuários devem ter sido habilitadas antes do ataque para você obter essas informações.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Como parar e remediar um ataque de concessão de autorização ilícita

Depois de identificar um aplicativo com permissões ilícitas, você terá várias maneiras de remover esse acesso.

- Você pode revogar a permissão do aplicativo no Portal do Azure Active Directory:

  - Navegue até o usuário afetado na folha Usuário **do Azure Active Directory.**

  - Selecione **Aplicativos**.

  - Selecione o aplicativo ilícito.

  - Clique **em Remover** na detalhamento.

- Você pode revogar a concessão de consentimento OAuth com o PowerShell seguindo as etapas em [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).

- Você pode revogar a atribuição de função de aplicativo de serviço com o PowerShell seguindo as etapas em [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).

- Você também pode desabilitar a entrada para a conta afetada completamente, o que, por sua vez, desabilitará o acesso do aplicativo aos dados dessa conta. Isso não é ideal para a produtividade do usuário final, é claro, mas se você estiver trabalhando para limitar o impacto rapidamente, pode ser uma correção viável a curto prazo.

- Você pode desativar os aplicativos integrados para a sua aplicação. Esta é uma etapa drástica que desabilita a capacidade dos usuários finais de conceder consentimento em todo o locatário. Isso impede que os usuários concedam inadvertidamente o acesso a um aplicativo mal-intencionado. Isso não é altamente recomendável, pois prejudica gravemente a capacidade dos usuários de serem produtivos com aplicativos de terceiros. Você pode fazer isso seguindo as etapas em Como ligar ou desligar aplicativos [integrados.](../../admin/misc/user-consent.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Proteja o Microsoft 365 como um profissional de segurança cibernética

Sua assinatura do Microsoft 365 vem com um poderoso conjunto de recursos de segurança que você pode usar para proteger seus dados e seus usuários. Use o [roteiro de segurança do Microsoft 365: principais prioridades para os primeiros 30 dias, 90 dias e depois](security-roadmap.md) para implementar práticas recomendadas para proteger o seu locatário do Microsoft 365.

- Tarefas a realizar nos primeiros 30 dias. Estas têm efeito imediato e baixo impacto para seus usuários.

- Tarefas para realizar em 90 dias. Estas levam um pouco mais de tempo para planejar e implementar, mas melhoram muito sua postura de segurança.

- Além de 90 dias. Estes aprimoramentos são desenvolvidos nos seus primeiros 90 dias de trabalho.

## <a name="see-also"></a>Confira também:

- [Aplicativo inesperado em minha lista de aplicativos](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) orienta os administradores por meio de várias ações que eles podem querer realizar depois de perceber que há aplicativos inesperados com acesso aos dados.

- [A integração de aplicativos com o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) é uma visão geral de alto nível de consentimento e permissões.

- [Problemas ao desenvolver meu aplicativo](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) fornece links para vários artigos relacionados ao consentimento.

- Os objetos de entidade de serviço e aplicativo no [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) fornece uma visão geral dos objetos de entidade de serviço e aplicativo que são fundamentais para o modelo de aplicativo.

- [Gerenciar o acesso aos aplicativos](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) é uma visão geral dos recursos que os administradores têm para gerenciar o acesso do usuário aos aplicativos.
