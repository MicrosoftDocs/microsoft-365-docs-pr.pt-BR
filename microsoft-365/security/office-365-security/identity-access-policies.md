---
title: Identidade comum e políticas de acesso a dispositivos - Microsoft 365 para empresas | Microsoft Docs
description: Descreve as configurações e políticas de acesso a dispositivos e identidade comuns recomendadas.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 511f044960c5b723c8e10f6644007036c45d1f44
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988087"
---
# <a name="common-identity-and-device-access-policies"></a>Identidade comum e políticas de acesso ao dispositivo

Este artigo descreve as políticas recomendadas comuns para proteger o acesso aos serviços de nuvem do Microsoft 365, incluindo aplicativos locais publicados com o Proxy de Aplicativo do Azure Active Directory (Azure AD).

Essas diretrizes abordam como implantar as políticas recomendadas em um ambiente recém-provisionado. A configuração dessas políticas em um ambiente de laboratório separado permite que você entenda e avalie as políticas recomendadas antes de preparação da lançamento para seus ambientes de produção e pré-produção. Seu ambiente recém-provisionado pode ser somente na nuvem ou híbrido para refletir suas necessidades de avaliação.

## <a name="policy-set"></a>Conjunto de políticas

O diagrama a seguir ilustra o conjunto recomendado de políticas. Ele mostra a qual camada de proteções cada política se aplica e se as políticas se aplicam a computadores, telefones e tablets, ou ambas as categorias de dispositivos. Ele também indica onde você configura essas políticas.

[![Políticas comuns para configurar o acesso a identidades e dispositivos](../../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

[Ver uma versão maior desta imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

Veja um resumo em PDF de uma página com links para as políticas individuais:

[![Imagem em miniatura para identidade e proteção de dispositivo para o manual do Microsoft 365](../../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br> [Exibir como um PDF](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| [Baixar como pdf](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

O restante deste artigo descreve como configurar essas políticas.

> [!NOTE]
> É recomendável exigir o uso da MFA (autenticação multifatória) antes de registrar dispositivos no Intune para garantir que o dispositivo está na posse do usuário pretendido. Você deve registrar dispositivos no Intune antes de impor políticas de conformidade do dispositivo.

Para dar tempo para realizar essas tarefas, recomendamos implementar as políticas de linha de base na ordem listada nesta tabela. No entanto, as políticas de MFA para níveis de proteção confidenciais e altamente regulamentados podem ser implementadas a qualquer momento.

|Nível de Proteção|Políticas|Mais informações|
|---|---|---|
|**Baseline**|[Exigir MFA quando o risco de login for *médio* ou *alto*](#require-mfa-based-on-sign-in-risk)||
||[Bloquear clientes sem suporte para a autenticação moderna](#block-clients-that-dont-support-modern-authentication)|Os clientes que não usam a autenticação moderna podem ignorar as políticas de Acesso Condicional, portanto, é importante bloqueá-los.|
||[Usuários de alto risco devem alterar a senha](#high-risk-users-must-change-password)|Força os usuários a alterarem a senha ao entrar se atividades de alto risco são detectadas para sua conta.|
||[Aplicar políticas de proteção de dados de aplicativo](#apply-app-data-protection-policies)|Uma política de Proteção de Aplicativos do Intune por plataforma (Windows, iOS/iPadOS, Android).|
||[Exigir aplicativos aprovados e proteção de aplicativos](#require-approved-apps-and-app-protection)|Impõe a proteção de aplicativo móvel para telefones e tablets usando iOS, iPadOS ou Android.|
||[Definir políticas de conformidade do dispositivo](#define-device-compliance-policies)|Uma política para cada plataforma.|
||[Exigir PCs compatíveis](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Impõe o gerenciamento do Intune de computadores usando o Windows ou o MacOS.|
|**Confidencial**|[Exigir MFA quando o risco de login for *baixo,* *médio* ou *alto*](#require-mfa-based-on-sign-in-risk)||
||[Exigir PCs e dispositivos *móveis compatíveis*](#require-compliant-pcs-and-mobile-devices)|Impõe o gerenciamento do Intune para computadores (Windows ou MacOS) e telefones ou tablets (iOS, iPadOS ou Android).|
|**Altamente controlado**|[*Sempre* exigir MFA](#require-mfa-based-on-sign-in-risk)|
|

## <a name="assigning-policies-to-groups-and-users"></a>Atribuindo políticas a grupos e usuários

Antes de configurar políticas, identifique os grupos do Azure AD que você está usando para cada camada de proteção. Normalmente, a proteção de linha de base se aplica a todos na organização. Um usuário incluído na linha de base e na proteção sensível terá todas as políticas de linha de base aplicadas, além das políticas confidenciais. A proteção é cumulativa e a política mais restritiva é imposta.

Uma prática recomendada é criar um grupo do Azure AD para exclusão de Acesso Condicional. Adicione esse grupo a todas as políticas de Acesso  Condicional no valor **Excluir** da configuração Usuários e grupos na seção **Atribuições.** Isso oferece um método para fornecer acesso a um usuário enquanto você soluciona problemas de acesso. Isso é recomendado como uma solução temporária apenas. Monitore esse grupo em busca de alterações e certifique-se de que o grupo de exclusão está sendo usado somente conforme o esperado.

Aqui está um exemplo de atribuição de grupo e exclusões para exigir MFA.

![Exemplo de atribuição de grupo e exclusões para políticas de MFA](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

Aqui estão os resultados:

- Todos os usuários devem usar a MFA quando o risco de login for médio ou alto.

- Os membros do grupo De equipe executiva devem usar a MFA quando o risco de login for baixo, médio ou alto.

  Nesse caso, os membros do grupo De equipe executiva combinam as políticas de Acesso Condicional de linha de base e confidenciais. Os controles de acesso para ambas as políticas são combinados, o que neste caso é equivalente à política de Acesso Condicional sensível.

- Os membros do grupo Top Secret Project X são sempre obrigados a usar a MFA

  Nesse caso, os membros do grupo Top Secret Project X combinam as políticas de Acesso Condicional de linha de base e de Acesso Condicional altamente controladas. Os controles de acesso para ambas as políticas são combinados. Como o controle de acesso para a política de Acesso Condicional altamente controlada é mais restritivo, ele é usado.

Tenha cuidado ao aplicar níveis mais altos de proteção a grupos e usuários. Por exemplo, membros do grupo Top Secret Project X precisarão usar a MFA sempre que entrarem, mesmo que não estão trabalhando no conteúdo altamente regulamentado do Project X.

Todos os grupos do Azure AD criados como parte dessas recomendações devem ser criados como grupos do Microsoft 365. Isso é importante para a implantação de rótulos de sensibilidade ao proteger documentos no Microsoft Teams e no SharePoint.

![Captura de tela para criar grupos do Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>Exigir MFA com base no risco de login

Você deve fazer com que seus usuários se registrem na MFA antes de exigir seu uso. Se você tiver o Microsoft 365 E5, o Microsoft 365 E3 com o complemento Proteção contra Ameaças do Identity &, o Office 365 com EMS E5 ou licenças individuais do Azure AD Premium P2, poderá usar a política de registro da MFA com o Azure AD Identity Protection para exigir que os usuários se registrem na MFA. O [trabalho de pré-requisito](identity-access-prerequisites.md) inclui o registro de todos os usuários com a MFA.

Depois que os usuários são registrados, você pode exigir a MFA para entrar com uma nova política de Acesso Condicional.

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais.
2. Na lista de serviços do Azure, escolha **Azure Active Directory.**
3. Na lista **Gerenciar,** escolha **Segurança** e Acesso **Condicional.**
4. Escolha **Nova política** e digite o nome da nova política.

As tabelas a seguir descrevem as configurações de política de Acesso Condicional para exigir a MFA com base no risco de entrada.

Na seção **Atribuições:**

|Configuração|Propriedades|Valores|Anotações|
|---|---|---|---|
|Usuários e grupos|Incluir|**Selecione usuários e grupos > Usuários e grupos:** selecione grupos específicos que contêm contas de usuário direcionadas.|Comece com o grupo que inclui contas de usuário piloto.|
||Excluir|**Usuários e grupos:** selecione seu grupo de exceção de Acesso Condicional; contas de serviço (identidades de aplicativo).|A associação deve ser modificada de forma temporária e necessária.|
|Aplicativos ou ações na nuvem|**Aplicativos de nuvem > Incluir**|**Selecionar aplicativos:** selecione os aplicativos aos quais você deseja aplicar essa política. Por exemplo, selecione Exchange Online.||
|Condições|||Configure condições específicas para seu ambiente e necessidades.|
||Risco de entrada||Consulte as diretrizes na tabela a seguir.|
|

### <a name="sign-in-risk-condition-settings"></a>Configurações de condição de risco de login

Aplique as configurações de nível de risco com base no nível de proteção que você está direcionando.

|Nível de proteção|Valores de nível de risco necessários|Action|
|---|---|---|
|Linha de base|Alto, médio|Verifique ambos.|
|Confidencial|Alto, médio, baixo|Verifique todos os três.|
|Altamente controlado||Deixe todas as opções desmarcadas para sempre impor a MFA.|
|

Na seção **Controles do Access:**

|Configuração|Propriedades|Valores|Action|
|---|---|---|---|
|Conceder|**Grant access**||Selecionar|
|||**Exigir autenticação multifa factor**|Cheque|
||**Exigir todos os controles selecionados**||Selecionar|
|

Escolha **Selecionar** para salvar as **configurações** de Concessão.

Por fim, **selecione Ativado** **para Habilitar política** e, em seguida, escolha **Criar**.

Considere também usar a [ferramenta What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para testar a política.

## <a name="block-clients-that-dont-support-modern-authentication"></a>Bloquear clientes que não oferecem suporte à autenticação moderna

Use as configurações nessas tabelas para uma política de Acesso Condicional para bloquear clientes que não suportam autenticação moderna.

Confira [este artigo](../../enterprise/microsoft-365-client-support-modern-authentication.md) para ver uma lista de clientes no Microsoft 365 que não são portadores da autenticação moderna.

Na seção **Atribuições:**

|Configuração|Propriedades|Valores|Anotações|
|---|---|---|---|
|Usuários e grupos|Incluir|**Selecione usuários e grupos > Usuários e grupos:** selecione grupos específicos que contêm contas de usuário direcionadas.|Comece com o grupo que inclui contas de usuário piloto.|
||Excluir|**Usuários e grupos:** selecione seu grupo de exceção de Acesso Condicional; contas de serviço (identidades de aplicativo).|A associação deve ser modificada de forma temporária e necessária.|
|Aplicativos ou ações na nuvem|**Aplicativos de nuvem > Incluir**|**Selecionar aplicativos:** selecione os aplicativos correspondentes aos clientes que não suportam a autenticação moderna.||
|Condições|**Aplicativos cliente**|Escolha **Sim** para **Configurar** <p> Limpar as marcas de seleção para **aplicativos** móveis **e navegadores e clientes da área de trabalho**||
|

Na seção **Controles do Access:**

|Configuração|Propriedades|Valores|Action|
|---|---|---|---|
|Conceder|**Bloquear acesso**||Selecionar|
||**Exigir todos os controles selecionados**||Selecionar|
|

Escolha **Selecionar** para salvar as **configurações** de Concessão.

Por fim, **selecione Ativado** **para Habilitar política** e, em seguida, escolha **Criar**.

Considere usar a [ferramenta What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para testar a política.

Para o Exchange Online, você pode usar políticas de autenticação para desabilitar a autenticação [Básica,](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)o que força todas as solicitações de acesso para cliente a usar a autenticação moderna.

## <a name="high-risk-users-must-change-password"></a>Usuários de alto risco devem alterar a senha

Para garantir que todas as contas comprometidas de todos os usuários de alto risco sejam forçadas a executar uma alteração de senha ao entrar, você deve aplicar a seguinte política.

Faça logon no [Portal do Microsoft Azure (https://portal.azure.com)](https://portal.azure.com/) com suas credenciais de administrador e, em seguida, navegue até **Azure AD Identity Protection > Política de Risco do Usuário**.

Na seção **Atribuições:**

|Tipo|Propriedades|Valores|Action|
|---|---|---|---|
|Usuários|Incluir|**Todos os usuários**|Selecionar|
|Risco do usuário|**High**||Selecionar|
|

Na segunda seção **Assignments:**

|Tipo|Propriedades|Valores|Action|
|---|---|---|---|
|Access|**Permitir acesso**||Selecionar|
|||**Requer a alteração de senha**|Cheque|
|

Escolha **Feito** para salvar as **configurações** do Access.

Por fim, **selecione Em** para **Impor política** e, em seguida, escolha **Salvar**.

Considere usar a [ferramenta What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para testar a política.

Use essa política em conjunto com Configurar a proteção por senha do [Azure AD,](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)que detecta e bloqueia senhas fracas conhecidas e suas variantes e termos fracos adicionais específicos para sua organização. Usar a proteção por senha do Azure AD garante que as senhas alteradas sejam fortes.

## <a name="apply-app-data-protection-policies"></a>Aplicar políticas de proteção de dados app

As Políticas de Proteção de Aplicativos (APP) definem quais aplicativos são permitidos e as ações que eles podem tomar com os dados da sua organização. As opções disponíveis no APP permitem que as organizações adaptem a proteção às suas necessidades específicas. Para alguns, pode não ser óbvio quais configurações de política são necessárias para implementar um cenário completo. Para ajudar as organizações a priorizar a proteção do ponto de extremidade do cliente móvel, a Microsoft introduziu a taxonomia para a estrutura de proteção de dados do APP para gerenciamento de aplicativos móveis iOS e Android.

A estrutura de proteção de dados do APP é organizada em três níveis de configuração distintos, com cada nível criando do nível anterior:

- **A proteção de dados básicos** empresariais (Nível 1) garante que os aplicativos sejam protegidos com um PIN e criptografados e executem operações de limpeza seletiva. Para dispositivos Android, esse nível valida o atestado de dispositivo Android. Essa é uma configuração de nível de entrada que fornece um controle de proteção de dados semelhante nas políticas de caixa de correio do Exchange Online e apresenta a IT e a população de usuários ao APP.
- **A proteção de dados aprimorada** corporativa (Nível 2) apresenta mecanismos de prevenção contra vazamento de dados de APP e requisitos mínimos do sistema operacional. Essa é a configuração aplicável à maioria dos usuários móveis que acessam dados do trabalho ou da escola.
- **A proteção de dados corporativos** de alto nível (Nível 3) apresenta mecanismos avançados de proteção de dados, configuração de PIN aprimorada e defesa contra ameaças do APP Mobile. Essa configuração é desejável para os usuários que estão acessando dados de alto risco.

Para ver as recomendações específicas para cada nível de configuração e os aplicativos mínimos que devem ser protegidos, revise a estrutura de proteção de dados usando [políticas de proteção de aplicativo.](https://docs.microsoft.com/mem/intune/apps/app-protection-framework)

Usando os princípios descritos nas configurações de acesso a identidades e [dispositivos,](microsoft-365-policies-configurations.md)as camadas de proteção de linha de base e confidenciais são mapeados de perto com as configurações de proteção de dados aprimorada corporativa de Nível 2. A camada de proteção altamente regulamentada é mapeada de perto para as configurações de alta proteção de dados corporativas de Nível 3.

|Nível de Proteção|Política de Proteção de Aplicativos|Mais informações|
|---|---|---|
|Linha de base|[Proteção de dados aprimorada de nível 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|As configurações de política impostas no nível 2 incluem todas as configurações de política recomendadas para o nível 1 e apenas adiciona ou atualiza as configurações de política abaixo para implementar mais controles e uma configuração mais sofisticada do que o nível 1.|
|Confidencial|[Proteção de dados aprimorada de nível 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|As configurações de política impostas no nível 2 incluem todas as configurações de política recomendadas para o nível 1 e apenas adiciona ou atualiza as configurações de política abaixo para implementar mais controles e uma configuração mais sofisticada do que o nível 1.|
|Altamente Regulamentado|[Proteção de dados de alta empresa de nível 3](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|As configurações de política impostas no nível 3 incluem todas as configurações de política recomendadas para os níveis 1 e 2 e apenas adiciona ou atualiza as configurações de política abaixo para implementar mais controles e uma configuração mais sofisticada do que o nível 2.|
|

Para criar uma nova política de proteção de aplicativo para cada plataforma (iOS e Android) no Microsoft Endpoint Manager usando as configurações da estrutura de proteção de dados, você pode:

1. Crie manualmente as políticas seguindo as etapas em Como criar e implantar políticas de proteção [de aplicativos com o Microsoft Intune.](https://docs.microsoft.com/mem/intune/apps/app-protection-policies)
2. Importe o exemplo de modelos JSON da Estrutura de Configuração da Política de Proteção de Aplicativo [do Intune](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) com [scripts do PowerShell do Intune.](https://github.com/microsoftgraph/powershell-intune-samples)

## <a name="require-approved-apps-and-app-protection"></a>Exigir aplicativos aprovados e proteção de APLICATIVO

Para impor as políticas de proteção do APP aplicadas no Intune, você deve criar uma política de Acesso Condicional para exigir aplicativos cliente aprovados e as condições definidas nas políticas de proteção do APP.

Impor políticas de proteção de APLICATIVO requer um conjunto de políticas descritas em Exigir política de proteção de aplicativo para acesso de aplicativos na nuvem [com Acesso Condicional.](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access) Essas políticas estão incluídas neste conjunto recomendado de políticas de configuração de identidade e acesso.

Para criar a política de Acesso Condicional que exige aplicativos aprovados e proteção de APLICATIVO, siga a "Etapa 1: Configurar uma política de Acesso Condicional do Azure AD para o Microsoft 365" no Cenário 1: os aplicativos do [Microsoft 365](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)exigem aplicativos aprovados com políticas de proteção de aplicativos, que permitem o Outlook para iOS e Android, mas impede que clientes do Exchange ActiveSync com capacidade OAuth se conectem ao Exchange Online.

   > [!NOTE]
   > Essa política garante que os usuários móveis possam acessar todos os pontos de extremidade do Office usando os aplicativos aplicáveis.

Se você estiver habilitando o acesso móvel ao Exchange Online, implemente o bloqueio de clientes [do ActiveSync,](secure-email-recommended-policies.md#block-activesync-clients)o que impede que os clientes do Exchange ActiveSync aproveitando a autenticação básica se conectem ao Exchange Online. Essa política não é ilustrada na parte superior deste artigo. Ele é descrito e descrito nas [recomendações de política para proteger emails.](secure-email-recommended-policies.md)

Para criar a política de Acesso Condicional que exige o Edge para iOS e Android, siga a "Etapa 2: Configurar uma política de Acesso Condicional do Azure AD para o Microsoft 365" no Cenário [2:](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-2-browser-apps-require-approved-apps-with-app-protection-policies)os aplicativos do navegador exigem aplicativos aprovados com políticas de proteção de aplicativo, que permite que o Edge para iOS e Android, mas impede que outros navegadores da Web de dispositivo móvel se conectem aos pontos de extremidade do Microsoft 365.

 Essas políticas aproveitam os controles de [concessão Exigem aplicativo cliente aprovado](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) e [exigem política de proteção de aplicativo.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)

Por fim, bloquear a autenticação herdda para outros aplicativos cliente em dispositivos iOS e Android garante que esses clientes não podem ignorar políticas de Acesso Condicional. Se você estiver seguindo as orientações neste artigo, já configurou clientes De bloqueio que não suportam [autenticação moderna.](#block-clients-that-dont-support-modern-authentication)

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Definir políticas de conformidade do dispositivo

As políticas de conformidade do dispositivo definem os requisitos que os dispositivos devem atender para serem determinados como compatíveis. Você cria políticas de conformidade de dispositivos do Intune no centro de administração do Microsoft Endpoint Manager.

Você deve criar uma política para cada computador, telefone ou plataforma de tablet:

- Administrador de dispositivo Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 e posterior
- Windows 10 e posterior

Para criar políticas de conformidade de dispositivos, entre no Centro de Administração  do [Microsoft Endpoint Manager](https://endpoint.microsoft.com) com suas credenciais de administrador e navegue até Políticas de Conformidade \> **de** \> **Dispositivos.** Selecione **Criar Política.**

Para que as políticas de conformidade do dispositivo sejam implantadas, elas devem ser atribuídas a grupos de usuários. Atribua uma política depois de criar e salvá-la. No centro de administração, selecione a política e selecione **Atribuições.** Depois de selecionar os grupos que você deseja receber a política, selecione **Salvar** para salvar essa atribuição de grupo e implantar a política.

Para obter orientações passo a passo sobre como criar políticas de conformidade no Intune, consulte Criar uma política de conformidade no [Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) na documentação do Intune.

### <a name="recommended-settings-for-windows-10-and-later"></a>Configurações recomendadas para o Windows 10 e versões posteriores

As configurações a seguir são recomendadas para computadores que executam o Windows 10 e versões posteriores, conforme configurado na Etapa **2:** Configurações de conformidade, do processo de criação de política.

Para **ver as regras > de avaliação** do Serviço de Atestado de Saúde do Windows, consulte esta tabela.

|Propriedades|Valor|Action|
|---|---|---|
|Exigir BitLocker|Exigir|Selecionar|
|Exigir que a Inicialização Segura seja habilitada no dispositivo|Exigir|Selecionar|
|Exigir integridade de código|Exigir|Selecionar|
|

Para **propriedades de dispositivo,** especifique os valores apropriados para versões do sistema operacional com base em suas políticas de SEGURANÇA e DE IT.

Para **Conformidade do Configuration Manager,** selecione **Exigir**.

Para **segurança do** sistema, consulte esta tabela.

|Tipo|Propriedades|Valor|Action|
|---|---|---|---|
|Password|Exigir uma senha para desbloquear dispositivos móveis|Exigir|Selecionar|
||Senhas simples|Bloquear|Selecionar|
||Tipo de senha|Padrão do dispositivo|Selecionar|
||Tamanho mínimo da senha|6 |Tipo|
||Máximo de minutos de inatividade antes que a senha seja necessária|15 |Tipo <p> Essa configuração é suportada nas versões Android 4.0 e superior ou KNOX 4.0 e superior. Para dispositivos iOS, ele tem suporte para iOS 8.0 e superior.|
||Vencimento da senha (dias)|41|Tipo|
||Número de senhas anteriores para evitar a reutilização|5 |Tipo|
||Exigir senha quando o dispositivo retornar do estado ocioso (Celular e Holográfico)|Exigir|Disponível para Windows 10 e posterior|
|Criptografia|Criptografia de armazenamento de dados no dispositivo|Exigir|Selecionar|
|Segurança do dispositivo|Firewall|Exigir|Selecionar|
||Antivírus|Exigir|Selecionar|
||Antispyware|Exigir|Selecionar <p> Essa configuração requer uma solução Anti-Spyware registrada na Central de Segurança do Windows.|
|Defender|Microsoft Defender Antimalware|Exigir|Selecionar|
||Versão mínima do Microsoft Defender Antimalware||Tipo <p> Só há suporte para área de trabalho do Windows 10. A Microsoft recomenda versões com até cinco atrás da versão mais recente.|
||Assinatura do Microsoft Defender Antimalware atualizada|Exigir|Selecionar|
||Proteção em tempo real|Exigir|Selecionar <p> Suporte apenas para área de trabalho do Windows 10|
|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para Ponto de Extremidade

|Tipo|Propriedades|Valor|Action|
|---|---|---|---|
|Regras do Microsoft Defender para Ponto de Extremidade|Exigir que o dispositivo está na pontuação de risco do computador ou na pontuação de risco da máquina|Médio|Selecionar|
|

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Exigir computadores compatíveis (mas não telefones e tablets compatíveis)

Antes de adicionar uma política para exigir PCs compatíveis, certifique-se de registrar dispositivos para gerenciamento no Intune. O uso da autenticação multifa factor é recomendado antes de registrar dispositivos no Intune para garantir que o dispositivo está em posse do usuário pretendido.

Para exigir PCs compatíveis:

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais.
2. Na lista de serviços do Azure, escolha **Azure Active Directory.**
3. Na lista **Gerenciar,** escolha **Segurança** e Acesso **Condicional.**
4. Escolha **Nova política** e digite o nome da nova política.

5. Em **Atribuições,** escolha **Usuários e grupos** e inclua a quem você deseja aplicar a política. Também exclua seu grupo de exclusão de Acesso Condicional.

6. Em **Atribuições,** escolha **Aplicativos ou ações na nuvem.**

7. For **Include**, choose **Select apps > Select**, and then select the desired apps from the Cloud **apps** list. Por exemplo, selecione Exchange Online. Escolha **Selecionar** quando terminar.

8. Para exigir computadores compatíveis (mas não telefones e tablets em conformidade), em **Atribuições,** escolha **Condições > plataformas de dispositivo.** Selecione **Sim** para **Configurar.** Choose  **Select device platforms,** select **Windows** and **macOS**, and then choose **Done**.

9. Em **Controles de acesso,** escolha **Conceder** .

10. Escolha **Conceder acesso e** marque Exigir que o dispositivo seja marcado como **compatível.** Para vários controles, selecione **Exigir todos os controles selecionados.** Ao concluir, escolha **Selecionar**.

11. Selecione **Ativado para** **Habilitar política** e, em seguida, escolha **Criar**.

> [!NOTE]
> Certifique-se de que seu dispositivo seja compatível antes de habilenciar essa política. Caso contrário, você poderá ser bloqueado e não poderá alterar essa política até que sua conta de usuário seja adicionada ao grupo de exclusão de Acesso Condicional.

## <a name="require-compliant-pcs-and-mobile-devices"></a>Exigir PCs e dispositivos *móveis compatíveis*

Para exigir conformidade para todos os dispositivos:

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais.
2. Na lista de serviços do Azure, escolha **Azure Active Directory.**
3. Na lista **Gerenciar,** escolha **Segurança** e Acesso **Condicional.**
4. Escolha **Nova política** e digite o nome da nova política.

5. Em **Atribuições,** escolha **Usuários e grupos** e inclua a quem você deseja aplicar a política. Também exclua seu grupo de exclusão de Acesso Condicional.

6. Em **Atribuições,** escolha **Aplicativos ou ações na nuvem.**

7. For **Include**, choose **Select apps > Select**, and then select the desired apps from the Cloud **apps** list. Por exemplo, selecione Exchange Online. Escolha **Selecionar** quando terminar.

8. Em **Controles de acesso,** escolha **Conceder** .

9. Escolha **Conceder acesso e** marque Exigir que o dispositivo seja marcado como **compatível.** Para vários controles, selecione **Exigir todos os controles selecionados.** Ao concluir, escolha **Selecionar**.

10. Selecione **Ativado para** **Habilitar política** e, em seguida, escolha **Criar**.

> [!NOTE]
> Certifique-se de que seu dispositivo seja compatível antes de habilenciar essa política. Caso contrário, você poderá ser bloqueado e não poderá alterar essa política até que sua conta de usuário seja adicionada ao grupo de exclusão de Acesso Condicional.

## <a name="next-step"></a>Próxima etapa

[![Etapa 3: Políticas para usuários convidados e externos](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[Saiba mais sobre recomendações de política para usuários convidados e externos](identity-access-policies-guest-access.md)
