---
title: Políticas comuns de acesso a dispositivos e identidade - Microsoft 365 para empresas | Microsoft Docs
description: Descreve as configurações e as políticas e configurações de identidade comum recomendadas e de acesso a dispositivos.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
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
ms.openlocfilehash: ed49405aa2933c029f7e62d274119550adc379e8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910653"
---
# <a name="common-identity-and-device-access-policies"></a>Identidade comum e políticas de acesso ao dispositivo

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- Azure

Este artigo descreve as políticas recomendadas comuns para proteger o acesso aos serviços de nuvem do Microsoft 365, incluindo aplicativos locais publicados com o Proxy de Aplicativo do Azure Active Directory (Azure AD).

Essas diretrizes abordam como implantar as políticas recomendadas em um ambiente recém-provisionado. A configuração dessas políticas em um ambiente de laboratório separado permite que você entenda e avalie as políticas recomendadas antes de configurar a adoção para seus ambientes de pré-produção e produção. Seu ambiente recém-provisionado pode ser somente na nuvem ou híbrido para refletir suas necessidades de avaliação.

## <a name="policy-set"></a>Conjunto de políticas

O diagrama a seguir ilustra o conjunto recomendado de políticas. Ele mostra a qual camada de proteções cada política se aplica e se as políticas se aplicam a computadores ou telefones e tablets, ou ambas as categorias de dispositivos. Ele também indica onde você configura essas políticas.

[![Políticas comuns para configurar identidade e acesso a dispositivos](../../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

Aqui está um resumo pdf de uma página com links para as políticas individuais:

[![Imagem em miniatura para identidade e proteção de dispositivos para o microsoft 365 handout](../../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br> [Exibir como um PDF](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| [Baixar como um PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

O restante deste artigo descreve como configurar essas políticas.

> [!NOTE]
> É recomendável o uso da autenticação multifafação (MFA) antes de registrar dispositivos no Intune para garantir que o dispositivo está na posse do usuário pretendido. Você deve registrar dispositivos no Intune antes de impor políticas de conformidade de dispositivos.

Para dar tempo para realizar essas tarefas, recomendamos implementar as políticas de linha de base na ordem listada nesta tabela. No entanto, as políticas de MFA para níveis de proteção confidenciais e altamente regulamentados podem ser implementadas a qualquer momento.

|Nível de Proteção|Políticas|Mais informações|
|---|---|---|
|**Baseline**|[Exigir MFA quando o risco de entrar é *médio* ou *alto*](#require-mfa-based-on-sign-in-risk)||
||[Bloquear clientes sem suporte para a autenticação moderna](#block-clients-that-dont-support-multi-factor)|Os clientes que não usam autenticação moderna podem ignorar políticas de Acesso Condicional, portanto, é importante bloqueá-los.|
||[Usuários de alto risco devem alterar a senha](#high-risk-users-must-change-password)|Força os usuários a alterar sua senha ao entrar se atividade de alto risco for detectada para sua conta.|
||[Aplicar políticas de proteção de dados do aplicativo](#apply-app-data-protection-policies)|Uma política de Proteção de Aplicativo do Intune por plataforma (Windows, iOS/iPadOS, Android).|
||[Exigir aplicativos aprovados e proteção de aplicativos](#require-approved-apps-and-app-protection)|Impõe a proteção de aplicativos móveis para telefones e tablets usando iOS, iPadOS ou Android.|
||[Definir políticas de conformidade de dispositivo](#define-device-compliance-policies)|Uma política para cada plataforma.|
||[Exigir PCs compatíveis](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Impõe o gerenciamento do Intune de computadores usando Windows ou MacOS.|
|**Confidencial**|[Exigir MFA quando o risco de entrar é *baixo,* *médio* ou *alto*](#require-mfa-based-on-sign-in-risk)||
||[Exigir PCs e *dispositivos* móveis compatíveis](#require-compliant-pcs-and-mobile-devices)|Impõe o gerenciamento do Intune para computadores (Windows ou MacOS) e telefones ou tablets (iOS, iPadOS ou Android).|
|**Altamente controlado**|[*Sempre* exigir MFA](#require-mfa-based-on-sign-in-risk)|
|

## <a name="assigning-policies-to-groups-and-users"></a>Atribuindo políticas a grupos e usuários

Antes de configurar políticas, identifique os grupos do Azure AD que você está usando para cada camada de proteção. Normalmente, a proteção da linha de base se aplica a todos na organização. Um usuário incluído para a linha de base e proteção sensível terá todas as políticas de linha de base aplicadas mais as políticas confidenciais. A proteção é cumulativa e a política mais restritiva é imposta.

Uma prática recomendada é criar um grupo do Azure AD para exclusão de Acesso Condicional. Adicione esse grupo a todas as suas políticas de Acesso Condicional no valor **Excluir** da configuração Usuários **e** grupos na seção **Atribuições.** Isso oferece um método para fornecer acesso a um usuário enquanto você soluciona problemas de acesso. Isso é recomendado apenas como uma solução temporária. Monitore esse grupo para alterações e certifique-se de que o grupo de exclusão está sendo usado apenas conforme o esperado.

Aqui está um exemplo de atribuição de grupo e exclusões para exigir MFA.

![Exemplo de atribuição de grupo e exclusões para políticas MFA](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

Aqui estão os resultados:

- Todos os usuários devem usar o MFA quando o risco de entrar for médio ou alto.

- Os membros do grupo De equipe executiva são obrigados a usar o MFA quando o risco de entrar é baixo, médio ou alto.

  Nesse caso, os membros do grupo De equipe executiva combinam com a linha de base e as políticas confidenciais de Acesso Condicional. Os controles de acesso para ambas as políticas são combinados, o que, nesse caso, é equivalente à política de Acesso Condicional sensível.

- Os membros do grupo do Projeto X do Top Secret são sempre necessários para usar o MFA

  Nesse caso, os membros do grupo Do Projeto X do Top Secret combinam com a linha de base e as políticas de Acesso Condicional altamente regulamentados. Os controles de acesso para ambas as políticas são combinados. Como o controle de acesso para a política de Acesso Condicional altamente regulamentado é mais restritivo, ele é usado.

Tenha cuidado ao aplicar níveis mais altos de proteção a grupos e usuários. Por exemplo, membros do grupo Top Secret Project X serão necessários para usar o MFA sempre que eles entrarem, mesmo que eles não estão trabalhando no conteúdo altamente regulamentado para o Project X.

Todos os grupos do Azure AD criados como parte dessas recomendações devem ser criados como grupos do Microsoft 365. Isso é importante para a implantação de rótulos de sensibilidade ao proteger documentos no Microsoft Teams e no SharePoint.

![Captura de tela para criar grupos do Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>Exigir MFA com base no risco de entrar

Você deve fazer com que seus usuários se registrem no MFA antes de exigir seu uso. Se você tiver o Microsoft 365 E5, o Microsoft 365 E3 com o complemento Identity & Threat Protection, o Office 365 com EMS E5 ou licenças individuais do Azure AD Premium P2, poderá usar a política de registro MFA com a Proteção de Identidade do Azure AD para exigir que os usuários se registrem no MFA. O [trabalho de pré-requisito](identity-access-prerequisites.md) inclui o registro de todos os usuários com MFA.

Depois que seus usuários são registrados, você pode exigir MFA para entrar com uma nova política de Acesso Condicional.

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais.
2. Na lista de serviços do Azure, escolha **Azure Active Directory**.
3. Na lista **Gerenciar,** escolha **Segurança** e, em seguida, escolha **Acesso Condicional**.
4. Escolha **Nova política** e digite o nome da nova política.

As tabelas a seguir descrevem as configurações de política de Acesso Condicional para exigir MFA com base no risco de entrada.

Na seção **Atribuições:**

|Setting|Propriedades|Valores|Anotações|
|---|---|---|---|
|Usuários e grupos|Incluir|**Selecione usuários e grupos > Usuários e grupos**: Selecione grupos específicos que contenham contas de usuário direcionadas.|Comece com o grupo que inclui contas de usuário piloto.|
||Excluir|**Usuários e grupos**: selecione seu grupo de exceção de Acesso Condicional; contas de serviço (identidades de aplicativo).|A associação deve ser modificada de forma temporária e necessária.|
|Aplicativos ou ações na nuvem|**Aplicativos de nuvem > Incluir**|**Selecione aplicativos**: selecione os aplicativos aos quais você deseja aplicar essa política. Por exemplo, selecione Exchange Online.||
|Condições|||Configure condições específicas para seu ambiente e necessidades.|
||Risco de entrada||Consulte as diretrizes na tabela a seguir.|
|

### <a name="sign-in-risk-condition-settings"></a>Configurações de condição de risco de login

Aplique as configurações de nível de risco com base no nível de proteção que você está direcionando.

|Nível de proteção|Valores de nível de risco necessários|Action|
|---|---|---|
|Linha de base|Alto, médio|Verifique ambos.|
|Confidencial|Alto, médio, baixo|Verifique todos os três.|
|Altamente controlado||Deixe todas as opções desmarcadas para sempre impor o MFA.|
|

Na seção **Controles do Access:**

|Setting|Propriedades|Valores|Action|
|---|---|---|---|
|Conceder|**Grant access**||Selecionar|
|||**Exigir autenticação multifa factor**|Cheque|
||**Exigir todos os controles selecionados**||Selecionar|
|

Escolha **Selecionar** para salvar as **configurações conceder.**

Por fim, selecione **Ativar** **para Habilitar política** e, em seguida, escolha **Criar**.

Considere também usar a [ferramenta E se](/azure/active-directory/active-directory-conditional-access-whatif) para testar a política.

## <a name="block-clients-that-dont-support-multi-factor"></a>Bloquear clientes que não suportam vários fatores

Use as configurações nessas tabelas para uma política de Acesso Condicional para bloquear clientes que não suportam autenticação multifacional.

Consulte [este artigo](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md) para ver uma lista de clientes no Microsoft 365 que suportam a autenticação multifa factor.

Na seção **Atribuições:**

|Setting|Propriedades|Valores|Anotações|
|---|---|---|---|
|Usuários e grupos|Incluir|**Selecione usuários e grupos > Usuários e grupos**: Selecione grupos específicos que contenham contas de usuário direcionadas.|Comece com o grupo que inclui contas de usuário piloto.|
||Excluir|**Usuários e grupos**: selecione seu grupo de exceção de Acesso Condicional; contas de serviço (identidades de aplicativo).|A associação deve ser modificada de forma temporária e necessária.|
|Aplicativos ou ações na nuvem|**Aplicativos de nuvem > Incluir**|**Selecione aplicativos**: Selecione os aplicativos correspondentes aos clientes que não suportam autenticação moderna.||
|Condições|**Aplicativos cliente**|Escolha **Sim** para **Configurar** <p> Limpar as marcas de verificação **para aplicativos de navegador** e móveis e clientes de área de **trabalho**||
|

Na seção **Controles do Access:**

|Setting|Propriedades|Valores|Action|
|---|---|---|---|
|Conceder|**Bloquear acesso**||Selecionar|
||**Exigir todos os controles selecionados**||Selecionar|
|

Escolha **Selecionar** para salvar as **configurações conceder.**

Por fim, selecione **Ativar** **para Habilitar política** e, em seguida, escolha **Criar**.

Considere usar a [ferramenta E se](/azure/active-directory/active-directory-conditional-access-whatif) para testar a política.

Para o Exchange Online, você pode usar políticas de autenticação para [desabilitar](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)a autenticação básica , o que força todas as solicitações de acesso do cliente a usar a autenticação moderna.

## <a name="high-risk-users-must-change-password"></a>Usuários de alto risco devem alterar a senha

Para garantir que todas as contas comprometidas de todos os usuários de alto risco sejam forçadas a executar uma alteração de senha ao entrar, você deve aplicar a seguinte política.

Faça logon no [Portal do Microsoft Azure (https://portal.azure.com)](https://portal.azure.com/) com suas credenciais de administrador e, em seguida, navegue até **Azure AD Identity Protection > Política de Risco do Usuário**.

Na seção **Atribuições:**

|Tipo|Propriedades|Valores|Action|
|---|---|---|---|
|Usuários|Incluir|**Todos os usuários**|Selecionar|
|Risco do usuário|**High**||Selecionar|
|

Na segunda seção **Atribuições:**

|Tipo|Propriedades|Valores|Action|
|---|---|---|---|
|Access|**Permitir acesso**||Selecionar|
|||**Requer a alteração de senha**|Cheque|
|

Escolha **Feito** para salvar as **configurações** do Access.

Por fim, selecione **On** for **Enforce policy** e, em seguida, escolha **Salvar**.

Considere usar a [ferramenta E se](/azure/active-directory/active-directory-conditional-access-whatif) para testar a política.

Use essa política em conjunto com a Proteção de senha do [Azure AD](/azure/active-directory/authentication/concept-password-ban-bad), que detecta e bloqueia senhas fracas conhecidas e suas variantes e termos fracos adicionais específicos à sua organização. Usar a proteção de senha do Azure AD garante que as senhas alteradas sejam fortes.

## <a name="apply-app-data-protection-policies"></a>Aplicar políticas de proteção de dados do APP

As Políticas de Proteção de Aplicativos (APP) definem quais aplicativos são permitidos e as ações que podem ser tomadas com os dados da sua organização. As opções disponíveis no APP permitem que as organizações adaptem a proteção às suas necessidades específicas. Para alguns, pode não ser óbvio quais configurações de política são necessárias para implementar um cenário completo. Para ajudar as organizações a priorizar o fortalecimento do ponto de extremidade do cliente móvel, a Microsoft introduziu taxonomia para sua estrutura de proteção de dados do APP para gerenciamento de aplicativos móveis iOS e Android.

A estrutura de proteção de dados do APP é organizada em três níveis de configuração distintos, com cada nível criando o nível anterior:

- **A proteção de dados básicos** da empresa (Nível 1) garante que os aplicativos sejam protegidos com um PIN e criptografados e executem operações de limpeza seletiva. Para dispositivos Android, esse nível valida o atestado de dispositivo Android. Essa é uma configuração de nível de entrada que fornece controle de proteção de dados semelhante nas políticas de caixa de correio do Exchange Online e introduz a IT e a população de usuários ao APP.
- **A proteção de dados aprimorada** da empresa (Nível 2) introduz mecanismos de prevenção de vazamento de dados do APP e requisitos mínimos do sistema operacional. Essa é a configuração aplicável à maioria dos usuários móveis que acessam dados de trabalho ou de estudante.
- **A proteção de dados altos** da empresa (Nível 3) introduz mecanismos avançados de proteção de dados, configuração aprimorada de PIN e Defesa contra Ameaças Móveis do APP. Essa configuração é desejável para usuários que estão acessando dados de alto risco.

Para ver as recomendações específicas para cada nível de configuração e os aplicativos mínimos que devem ser protegidos, revise a estrutura de proteção de dados usando políticas de proteção [de aplicativos.](/mem/intune/apps/app-protection-framework)

Usando os princípios descritos em Configurações de acesso a identidade e dispositivo, as [camadas](microsoft-365-policies-configurations.md)de proteção Baseline e Sensitive mapeiam de perto com as configurações de proteção de dados avançadas da empresa de Nível 2. A camada de proteção altamente regulamentada mapeia de perto as configurações de alta proteção de dados corporativos de Nível 3.

|Nível de Proteção|Política de Proteção de Aplicativos|Mais informações|
|---|---|---|
|Linha de base|[Proteção de dados aprimorada de nível 2](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|As configurações de política impostas no nível 2 incluem todas as configurações de política recomendadas para o nível 1 e apenas adiciona ou atualiza as configurações de política abaixo para implementar mais controles e uma configuração mais sofisticada do que o nível 1.|
|Confidencial|[Proteção de dados aprimorada de nível 2](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|As configurações de política impostas no nível 2 incluem todas as configurações de política recomendadas para o nível 1 e apenas adiciona ou atualiza as configurações de política abaixo para implementar mais controles e uma configuração mais sofisticada do que o nível 1.|
|Altamente regulamentado|[Proteção de dados de alta empresa de nível 3](/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|As configurações de política impostas no nível 3 incluem todas as configurações de política recomendadas para os níveis 1 e 2 e adiciona ou atualiza apenas as configurações de política abaixo para implementar mais controles e uma configuração mais sofisticada do que o nível 2.|
|

Para criar uma nova política de proteção de aplicativos para cada plataforma (iOS e Android) no Microsoft Endpoint Manager usando as configurações da estrutura de proteção de dados, você pode:

1. Crie manualmente as políticas seguindo as etapas em Como criar e implantar políticas de proteção de [aplicativos com o Microsoft Intune](/mem/intune/apps/app-protection-policies).
2. Import the sample [Intune App Protection Policy Configuration Framework templates JSON](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) with [Intune's PowerShell scripts](https://github.com/microsoftgraph/powershell-intune-samples).

## <a name="require-approved-apps-and-app-protection"></a>Exigir aplicativos aprovados e proteção de APLICATIVO

Para impor as políticas de proteção de APLICATIVO que você aplicou no Intune, você deve criar uma política de Acesso Condicional para exigir aplicativos cliente aprovados e as condições definidas nas políticas de proteção do APP.

A imposição de políticas de proteção de APLICATIVO requer um conjunto de políticas descritas em Exigir política de proteção de aplicativos para acesso a [aplicativos na](/azure/active-directory/conditional-access/app-protection-based-conditional-access)nuvem com Acesso Condicional . Essas políticas estão incluídas neste conjunto recomendado de políticas de configuração de acesso e identidade.

Para criar a política de Acesso Condicional que exige aplicativos aprovados e proteção de APLICATIVO, siga "Etapa 1: Configurar uma política de Acesso Condicional do Azure AD para o Microsoft 365" no Cenário 1: os aplicativos do [Microsoft 365](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)exigem aplicativos aprovados com políticas de proteção de aplicativos , o que permite o Outlook para iOS e Android, mas impede que os clientes do OAuth Exchange ActiveSync se conectem ao Exchange Online.

   > [!NOTE]
   > Esta política garante que os usuários móveis possam acessar todos os pontos de extremidade do Office usando os aplicativos aplicáveis.

Se você estiver habilitando o acesso móvel ao Exchange Online, implemente Bloquear clientes [ActiveSync](secure-email-recommended-policies.md#block-activesync-clients), o que impede que Exchange ActiveSync clientes que aproveitando a autenticação básica se conectem ao Exchange Online. Esta política não é retratada na ilustração na parte superior deste artigo. Ele é descrito e retratado em [Recomendações de política para proteger emails.](secure-email-recommended-policies.md)

Para criar a política de Acesso Condicional que exige o Edge para iOS e Android, siga "Etapa 2: Configurar uma política de Acesso Condicional do Azure AD para o Microsoft 365" no Cenário [2:](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-2-browser-apps-require-approved-apps-with-app-protection-policies)Os aplicativos do navegador exigem aplicativos aprovados com políticas de proteção de aplicativos, o que permite o Edge para iOS e Android, mas impede que outros navegadores da Web de dispositivo móvel se conectem aos pontos de extremidade do Microsoft 365.

 Essas políticas aproveitam os controles de concessão [Exigir aplicativo cliente aprovado](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) e Exigir política de proteção de [aplicativo.](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)

Por fim, bloquear a autenticação herdda para outros aplicativos cliente em dispositivos iOS e Android garante que esses clientes não podem ignorar políticas de Acesso Condicional. Se você estiver seguindo as diretrizes neste artigo, já configurou os clientes Block que não suportam [autenticação moderna.](#block-clients-that-dont-support-multi-factor)

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Definir políticas de conformidade de dispositivo

As políticas de conformidade de dispositivo definem os requisitos que os dispositivos devem atender para serem determinados como compatíveis. Você cria políticas de conformidade de dispositivo do Intune no Centro de administração do Microsoft Endpoint Manager.

Você deve criar uma política para cada computador, telefone ou plataforma de tablet:

- Administrador de dispositivos Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 e posterior
- Windows 10 e posterior

Para criar políticas de conformidade de dispositivo, faça logoff no Centro de Administração do [Microsoft Endpoint Manager](https://endpoint.microsoft.com) com suas credenciais de administrador e navegue até **Políticas** de \> **Conformidade de** \> **Dispositivos.** Selecione **Criar Política**.

Para que as políticas de conformidade do dispositivo sejam implantadas, elas devem ser atribuídas a grupos de usuários. Você atribui uma política depois de criar e salvá-la. No centro de administração, selecione a política e selecione **Atribuições**. Depois de selecionar os grupos que você deseja receber a política, selecione **Salvar** para salvar essa atribuição de grupo e implantar a política.

Para obter orientações passo a passo sobre a criação de políticas de conformidade no Intune, consulte Criar uma política de conformidade no [Microsoft Intune](/mem/intune/protect/create-compliance-policy) na documentação do Intune.

### <a name="recommended-settings-for-windows-10-and-later"></a>Configurações recomendadas para Windows 10 e posteriores

As configurações a seguir são recomendadas para computadores que executam o Windows 10 e posteriores, conforme configurado na Etapa **2:** Configurações de conformidade , do processo de criação de política.

Para **regras de > avaliação do Serviço** de Atestado de Saúde do Windows para dispositivos, consulte esta tabela.

|Propriedades|Valor|Action|
|---|---|---|
|Exigir BitLocker|Exigir|Selecionar|
|Exigir que a inicialização segura seja habilitada no dispositivo|Exigir|Selecionar|
|Exigir integridade de código|Exigir|Selecionar|
|

Para **propriedades de dispositivo,** especifique os valores apropriados para versões do sistema operacional com base em suas políticas de segurança e DEH.

Para **Conformidade do Configuration Manager,** selecione **Exigir**.

Para **segurança do** sistema, consulte esta tabela.

|Tipo|Propriedades|Valor|Action|
|---|---|---|---|
|Password|Exigir uma senha para desbloquear dispositivos móveis|Exigir|Selecionar|
||Senhas simples|Bloquear|Selecionar|
||Tipo de senha|Padrão do dispositivo|Selecionar|
||Tamanho mínimo da senha|6 |Tipo|
||Máximo de minutos de inatividade antes que a senha seja necessária|15 |Tipo <p> Essa configuração é suportada para versões android 4.0 e superior ou KNOX 4.0 e superior. Para dispositivos iOS, ele tem suporte para iOS 8.0 e superior.|
||Vencimento da senha (dias)|41|Tipo|
||Número de senhas anteriores para evitar reutilização|5 |Tipo|
||Exigir senha quando o dispositivo retornar do estado ocioso (Mobile e Holographic)|Exigir|Disponível para Windows 10 e posterior|
|Criptografia|Criptografia de armazenamento de dados no dispositivo|Exigir|Selecionar|
|Segurança do Dispositivo|Firewall|Exigir|Selecionar|
||Antivírus|Exigir|Selecionar|
||Antispyware|Exigir|Selecionar <p> Essa configuração requer uma solução Anti-Spyware registrada no Centro de Segurança do Windows.|
|Defender|Microsoft Defender Antimalware|Exigir|Selecionar|
||Versão mínima do Microsoft Defender Antimalware||Tipo <p> Somente com suporte para área de trabalho do Windows 10. A Microsoft recomenda versões não mais de cinco atrás da versão mais recente.|
||Assinatura do Microsoft Defender Antimalware atualizada|Exigir|Selecionar|
||Proteção em tempo real|Exigir|Selecionar <p> Somente com suporte para área de trabalho do Windows 10|
|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para Ponto de Extremidade

|Tipo|Propriedades|Valor|Action|
|---|---|---|---|
|Regras do Microsoft Defender para Ponto de Extremidade|Exigir que o dispositivo seja em ou sob a pontuação de risco da máquina|Médio|Selecionar|
|

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Exigir computadores compatíveis (mas não telefones e tablets compatíveis)

Antes de adicionar uma política para exigir PCs compatíveis, certifique-se de registrar dispositivos para gerenciamento no Intune. O uso da autenticação multifaionária é recomendado antes de registrar dispositivos no Intune para garantir que o dispositivo está na posse do usuário pretendido.

Para exigir PCs compatíveis:

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais.
2. Na lista de serviços do Azure, escolha **Azure Active Directory**.
3. Na lista **Gerenciar,** escolha **Segurança** e, em seguida, escolha **Acesso Condicional**.
4. Escolha **Nova política** e digite o nome da nova política.

5. Em **Atribuições,** escolha **Usuários e grupos** e inclua a quem você deseja que a política se aplique. Também exclua seu grupo de exclusão de Acesso Condicional.

6. Em **Atribuições,** escolha **Aplicativos ou ações em nuvem.**

7. Para **Incluir**, **escolha Selecionar aplicativos > Selecionar** e selecione os aplicativos desejados na lista **Aplicativos de** nuvem. Por exemplo, selecione Exchange Online. Escolha **Selecionar** quando terminar.

8. Para exigir computadores compatíveis (mas não telefones e tablets compatíveis), em **Atribuições,** escolha **Condições > plataformas de dispositivo.** Selecione **Sim** para **Configurar**. Escolha  **Selecionar plataformas de dispositivo,** selecione **Windows** **e macOS** e escolha **Feito**.

9. Em **Controles de Acesso,** escolha **Conceder** .

10. Escolha **Conceder acesso e** verifique Exigir que o dispositivo seja marcado como **compatível**. Para vários controles, selecione **Exigir todos os controles selecionados**. Quando estiver concluído, escolha **Selecionar**.

11. Selecione **Ativado para** **Habilitar política** e, em seguida, escolha **Criar**.

> [!NOTE]
> Certifique-se de que seu dispositivo seja compatível antes de habilbiligá-la. Caso contrário, você poderá ser bloqueado e não poderá alterar essa política até que sua conta de usuário seja adicionada ao grupo de exclusão do Acesso Condicional.

## <a name="require-compliant-pcs-and-mobile-devices"></a>Exigir PCs e *dispositivos* móveis compatíveis

Para exigir conformidade para todos os dispositivos:

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais.
2. Na lista de serviços do Azure, escolha **Azure Active Directory**.
3. Na lista **Gerenciar,** escolha **Segurança** e, em seguida, escolha **Acesso Condicional**.
4. Escolha **Nova política** e digite o nome da nova política.

5. Em **Atribuições,** escolha **Usuários e grupos** e inclua a quem você deseja que a política se aplique. Também exclua seu grupo de exclusão de Acesso Condicional.

6. Em **Atribuições,** escolha **Aplicativos ou ações em nuvem.**

7. Para **Incluir**, **escolha Selecionar aplicativos > Selecionar** e selecione os aplicativos desejados na lista **Aplicativos de** nuvem. Por exemplo, selecione Exchange Online. Escolha **Selecionar** quando terminar.

8. Em **Controles de Acesso,** escolha **Conceder** .

9. Escolha **Conceder acesso e** verifique Exigir que o dispositivo seja marcado como **compatível**. Para vários controles, selecione **Exigir todos os controles selecionados**. Quando estiver concluído, escolha **Selecionar**.

10. Selecione **Ativado para** **Habilitar política** e, em seguida, escolha **Criar**.

> [!NOTE]
> Certifique-se de que seu dispositivo seja compatível antes de habilbiligá-la. Caso contrário, você poderá ser bloqueado e não poderá alterar essa política até que sua conta de usuário seja adicionada ao grupo de exclusão do Acesso Condicional.

## <a name="next-step"></a>Próxima etapa

[![Etapa 3: Políticas para usuários convidados e externos](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[Saiba mais sobre recomendações de política para usuários convidados e externos](identity-access-policies-guest-access.md)