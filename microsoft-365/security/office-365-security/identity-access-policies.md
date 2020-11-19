---
title: Políticas comuns de acesso de dispositivo e identidade-Microsoft 365 for Enterprise | Microsoft docs
description: Descreve as configurações e as políticas de acesso de dispositivos e a identidade comum recomendadas.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: b4468bfc7ef4b6f76d44b328f4e5b6d61d7f06ac
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357834"
---
# <a name="common-identity-and-device-access-policies"></a>Identidade comum e políticas de acesso ao dispositivo

Este artigo descreve as políticas comuns recomendadas para proteger o acesso aos serviços de nuvem do Microsoft 365, incluindo aplicativos locais publicados com o proxy de aplicativo do Azure Active Directory (Azure AD).

Este guia discute como implantar as políticas recomendadas em um ambiente provisionado recentemente. Configurar essas políticas em um ambiente de laboratório separado permite que você entenda e avalie as políticas recomendadas antes de preparar a distribuição para seus ambientes de pré-produção e produção. Seu ambiente provisionado recentemente pode ser apenas na nuvem ou híbrido para refletir suas necessidades de avaliação.

## <a name="policy-set"></a>Conjunto de políticas

O diagrama a seguir ilustra o conjunto de políticas recomendado. Ele mostra qual camada de proteção cada política se aplica e se as políticas se aplicam a PCs ou telefones e tablets ou a ambas as categorias de dispositivos. Ele também indica onde você configura essas políticas.

[![Políticas comuns para configurar a identidade e o acesso ao dispositivo](../../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

[Veja uma versão maior desta imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

Veja um resumo do PDF de uma página com links para as políticas individuais:

[![Imagem em miniatura para proteção de identidade e dispositivo para o folheto do Microsoft 365](../../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br/>  [Exibir como um PDF](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| [Baixar como um PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

O restante deste artigo descreve como configurar essas políticas.

> [!NOTE]
> É recomendável exigir o uso da MFA (autenticação multifator) antes de registrar dispositivos no Intune para garantir que o dispositivo esteja na posse do usuário desejado. Você deve registrar dispositivos no Intune antes de reforçar as políticas de conformidade do dispositivo.

Para dar tempo para realizar essas tarefas, recomendamos implementar as políticas de linha de base na ordem listada nesta tabela. No entanto, as políticas da MFA de níveis confidenciais e altamente regulamentados de proteção podem ser implementadas a qualquer momento.

|Nível de Proteção|Políticas|Mais informações|
|---|---|---|
|**Baseline**|[Exigir MFA quando o risco de entrada for *médio* ou *alto*](#require-mfa-based-on-sign-in-risk)||
||[Bloquear clientes sem suporte para a autenticação moderna](#block-clients-that-dont-support-modern-authentication)|Os clientes que não usam a autenticação moderna podem ignorar as políticas de acesso condicional, portanto, é importante bloqueá-los.|
||[Usuários de alto risco devem alterar a senha](#high-risk-users-must-change-password)|Obriga os usuários a alterarem a senha ao entrar se a atividade de alto risco for detectada para sua conta.|
||[Aplicar políticas de proteção de dados do aplicativo](#apply-app-data-protection-policies)|Uma política de proteção de aplicativos do Intune por plataforma (Windows, iOS/iPadOS, Android).|
||[Exigir aplicativos aprovados e proteção de aplicativos](#require-approved-apps-and-app-protection)|Impõe proteção de aplicativos móveis para telefones e tablets usando iOS, iPadOS ou Android.|
||[Definir políticas de conformidade do dispositivo](#define-device-compliance-policies)|Uma política para cada plataforma.|
||[Exigir PCs compatíveis](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Impõe o gerenciamento do Intune de PCs usando o Windows ou o MacOS.|
|**Confidencial**|[Exigir MFA quando o risco de entrada for *baixo*, *médio* ou *alto*](#require-mfa-based-on-sign-in-risk)||
||[Exigir computadores *em conformidade e* dispositivos móveis](#require-compliant-pcs-and-mobile-devices)|Impõe o gerenciamento do Intune para ambos os PCs (Windows ou MacOS) e telefones ou tablets (iOS, iPadOS ou Android).|
|**Altamente controlado**|[*Sempre* exigir MFA](#require-mfa-based-on-sign-in-risk)|
|

## <a name="assigning-policies-to-groups-and-users"></a>Atribuindo políticas a grupos e usuários

Antes de configurar as políticas, identifique os grupos do Azure AD que você está usando para cada camada de proteção. Normalmente, a proteção de linha de base se aplica a todas as pessoas na organização. Um usuário que está incluído na linha de base e proteção confidencial terá todas as políticas de linha de base aplicadas mais as políticas confidenciais. A proteção é cumulativa e a política mais restritiva é imposta.

Uma prática recomendada é criar um grupo do Azure AD para exclusão de acesso condicional. Adicione esse grupo a todas as suas políticas de acesso condicional no valor de **exclusão** da configuração **usuários e grupos** na seção **atribuições** . Isso fornece um método para fornecer acesso a um usuário enquanto você soluciona problemas de acesso. Isso é recomendado somente como uma solução temporária. Monitore esse grupo para alterações e certifique-se de que o grupo de exclusão esteja sendo usado apenas conforme o esperado.

Veja um exemplo de atribuição de grupo e exclusões para exigir MFA.

![Atribuições de grupo de exemplo e exclusões para políticas de MFA](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

Estes são os resultados:

- Todos os usuários precisam usar a MFA quando o risco de entrada for médio ou alto.

- Os membros do grupo executivo staff precisam usar a MFA quando o risco de entrada for baixo, médio ou alto.

  Nesse caso, os membros do grupo executivo staff correspondem tanto à linha de base quanto às políticas de acesso condicional sensíveis. Os controles de acesso para ambas as políticas são combinados, o que, nesse caso, é equivalente à política de acesso condicional confidencial.

- Os membros do grupo de principais projetos do Project X sempre são necessários para usar MFA

  Nesse caso, os membros do grupo de principais projetos do Project X correspondem à linha de base e às políticas de acesso condicional altamente regulamentadas. Os controles de acesso para ambas as políticas são combinados. Como o controle de acesso para a política de acesso condicional altamente regulamentada é mais restritivo, ele é usado.

Tenha cuidado ao aplicar níveis mais altos de proteção a grupos e usuários. Por exemplo, os membros do grupo de principais projetos do Project X serão necessários para usar a MFA sempre que eles entrarem, mesmo se não estiverem trabalhando no conteúdo altamente regulamentado para o Project X.

Todos os grupos do Azure AD criados como parte dessas recomendações devem ser criados como grupos do Microsoft 365. Isso é importante para a implantação de rótulos de confidencialidade ao proteger documentos no Microsoft Teams e no SharePoint.

![Captura de tela para a criação de grupos do Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>Exigir a MFA com base no risco de entrada

Os usuários devem se registrar na MFA antes de exigir seu uso. Se você tiver o Microsoft 365 e5, a Microsoft 365 E3 com a identidade & complemento de proteção contra ameaças, Office 365 com EMS E5 ou licenças do Azure AD Premium P2 individuais, você poderá usar a política de registro da MFA com a proteção de identidade do Azure AD para exigir que os usuários se registrem para MFA. O [trabalho de pré-requisito](identity-access-prerequisites.md) inclui o registro de todos os usuários com a MFA.

Depois que os usuários estiverem registrados, você poderá exigir a MFA de entrar com uma nova política de acesso condicional.

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais.
2. Na lista de serviços do Azure, escolha **Azure Active Directory**.
3. Na lista **gerenciar** , escolha **segurança** e, em seguida, escolha **acesso condicional**.
4. Escolha **nova política** e digite o nome da nova política.

As tabelas a seguir descrevem as configurações de política de acesso condicional para exigir a MFA com base no risco de entrada.

Na seção **assignments** :

|Setting|Propriedades|Valores|Anotações|
|---|---|---|---|
|Usuários e grupos|Incluir|**Selecione usuários e grupos > usuários e grupos**: selecionar grupos específicos contendo contas de usuário direcionadas.|Comece com o grupo que inclui as contas de usuário piloto.|
||Excluir|**Usuários e grupos**: Selecione seu grupo de exceções de acesso condicional; contas de serviço (identidades de aplicativos).|A associação deve ser modificada de acordo com a necessidade e temporária.|
|Ações ou aplicativos de nuvem|**Os aplicativos de nuvem > incluem**|**Selecionar aplicativos**: selecione os aplicativos para os quais você deseja aplicar essa política. Por exemplo, selecione Exchange Online.||
|Condições|||Configurar condições específicas para seu ambiente e necessidades.|
||Risco de entrada||Confira as orientações na tabela a seguir.|
|

### <a name="sign-in-risk-condition-settings"></a>Configurações de condição de risco de entrada

Aplique as configurações de nível de risco com base no nível de proteção que você está direcionando.

|Nível de proteção|Valores de nível de risco necessários|Action|
|---|---|---|
|Linha de base|Alto, médio|Verifique ambos.|
|Confidencial|Alta, média, baixa|Verifique todos os três.|
|Altamente controlado||Deixe todas as opções desmarcadas para sempre impor a MFA.|
|

Na seção **controles de acesso** :

|Setting|Propriedades|Valores|Action|
|---|---|---|---|
|Conceder|**Grant access**||Selecionar|
|||**Exigir autenticação multifator**|Verificar|
||**Exigir todos os controles selecionados**||Selecionar|
|

Escolha **selecionar** para salvar as configurações de **concessão** .

Por fim, selecione **ativado** para **habilitar política** e, em seguida, escolha **criar**.

Considere também usar a ferramenta [e se](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para testar a política.

## <a name="block-clients-that-dont-support-modern-authentication"></a>Bloquear clientes que não oferecem suporte à autenticação moderna

Use as configurações dessas tabelas para uma política de acesso condicional para bloquear clientes que não dão suporte à autenticação moderna.

Confira [Este artigo](../../enterprise/microsoft-365-client-support-modern-authentication.md) para obter uma lista de clientes no Microsoft 365 que fazem a autenticação moderna do suporte.

Na seção **assignments** :

|Setting|Propriedades|Valores|Anotações|
|---|---|---|---|
|Usuários e grupos|Incluir|**Selecione usuários e grupos > usuários e grupos**: selecionar grupos específicos contendo contas de usuário direcionadas.|Comece com o grupo que inclui as contas de usuário piloto.|
||Excluir|**Usuários e grupos**: Selecione seu grupo de exceções de acesso condicional; contas de serviço (identidades de aplicativos).|A associação deve ser modificada de acordo com a necessidade e temporária.|
|Ações ou aplicativos de nuvem|**Os aplicativos de nuvem > incluem**|**Selecionar aplicativos**: selecione os aplicativos correspondentes aos clientes que não dão suporte à autenticação moderna.||
|Condições|**Aplicativos cliente**|Escolha **Sim** para **Configurar** <br/> Limpar as marcas de seleção de **navegador** e **aplicativos móveis e clientes de desktop**||
|

Na seção **controles de acesso** :

|Setting|Propriedades|Valores|Action|
|---|---|---|---|
|Conceder|**Bloquear acesso**||Selecionar|
||**Exigir todos os controles selecionados**||Selecionar|
|

Escolha **selecionar** para salvar as configurações de **concessão** .

Por fim, selecione **ativado** para **habilitar política** e, em seguida, escolha **criar**.

Considere usar a ferramenta [e se](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para testar a política.

Para o Exchange Online, você pode usar políticas de autenticação para [desabilitar a autenticação básica](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), o que força todas as solicitações de acesso para cliente a usar a autenticação moderna.

## <a name="high-risk-users-must-change-password"></a>Usuários de alto risco devem alterar a senha

Para garantir que todas as contas comprometidas de usuários de alto risco sejam forçadas a executar uma alteração de senha ao entrar, você deve aplicar a política a seguir.

Faça logon no [Portal do Microsoft Azure (https://portal.azure.com)](https://portal.azure.com/) com suas credenciais de administrador e, em seguida, navegue até **Azure AD Identity Protection > Política de Risco do Usuário**.

Na seção **assignments** :

|Tipo|Propriedades|Valores|Action|
|---|---|---|---|
|Usuários|Incluir|**Todos os usuários**|Selecionar|
|Risco do usuário|**High**||Selecionar|
|

Na segunda seção de **atribuições** :

|Tipo|Propriedades|Valores|Action|
|---|---|---|---|
|Access|**Permitir acesso**||Selecionar|
|||**Requer a alteração de senha**|Verificar|
|

Escolha **concluído** para salvar as configurações de **acesso** .

Por fim, selecione **ativado** para **impor política** e, em seguida, escolha **salvar**.

Considere usar a ferramenta [e se](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para testar a política.

Use essa política junto com a [configuração de proteção de senha do Azure ad](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad), que detecta e bloqueia senhas fracas conhecidas e suas variantes e outros termos fracos que são específicos para sua organização. O uso da proteção de senha do Azure AD garante que as senhas alteradas sejam fortes.

## <a name="apply-app-data-protection-policies"></a>Aplicar políticas de proteção de dados do aplicativo

As políticas de proteção de aplicativos (aplicativo) definem quais aplicativos são permitidos e as ações que eles podem realizar com os dados da sua organização. As opções disponíveis no aplicativo permitem que as organizações adaptem a proteção às suas necessidades específicas. Para alguns, talvez não seja óbvio quais configurações de política são necessárias para implementar um cenário completo. Para ajudar as organizações a priorizar a proteção de ponto de extremidade do cliente móvel, a Microsoft introduziu a taxonomia de sua estrutura de proteção de dados do aplicativo para o gerenciamento de aplicativos móveis iOS e Android.

A estrutura de proteção de dados do aplicativo é organizada em três níveis de configuração distintos, e cada nível cria o nível anterior:

- A **proteção de dados do Enterprise Basic** (nível 1) garante que os aplicativos estão protegidos com PIN e criptografados e realiza operações de apagamento seletivo. Para dispositivos Android, esse nível valida o atestado de dispositivo Android. Esta é uma configuração de nível de entrada que fornece controle de proteção de dados semelhante nas políticas de caixa de correio do Exchange Online e apresenta a população e o preenchimento do usuário para o aplicativo.
- **Enterprise Enhanced Data Protection** (Level 2) apresenta mecanismos de prevenção de perda de dados de aplicativo e requisitos mínimos de so. Esta é a configuração que se aplica à maioria dos usuários móveis que acessam dados corporativos ou de estudante.
- **Alta proteção de dados da empresa** (nível 3) apresenta mecanismos avançados de proteção de dados, configuração de PIN avançado e defesa contra ameaças móveis de aplicativos. Essa configuração é desejável para usuários que estão acessando dados de alto risco.

Para ver as recomendações específicas para cada nível de configuração e os aplicativos mínimos que devem ser protegidos, revise a [estrutura de proteção de dados usando políticas de proteção de aplicativos](https://docs.microsoft.com/mem/intune/apps/app-protection-framework).

Usando os princípios descritos nas configurações de [acesso a dispositivos e identidades](microsoft-365-policies-configurations.md), a linha de base e as camadas de proteção sensíveis mapeiam em conjunto com as configurações de proteção avançada de dados da empresa de nível 2. A camada de proteção altamente regulamentada é mapeada de perto das configurações de alta proteção de dados da empresa de nível 3.

|Nível de Proteção|Política de proteção de aplicativos|Mais informações|
|---|---|---|
|Linha de base|[Proteção avançada de dados de nível 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|As configurações de política aplicadas no nível 2 incluem todas as configurações de política recomendadas para o nível 1 e somente adiciona ou atualiza as configurações de política abaixo para implementar mais controles e uma configuração mais sofisticada do que o nível 1.|
|Confidencial|[Proteção avançada de dados de nível 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|As configurações de política aplicadas no nível 2 incluem todas as configurações de política recomendadas para o nível 1 e somente adiciona ou atualiza as configurações de política abaixo para implementar mais controles e uma configuração mais sofisticada do que o nível 1.|
|Altamente regulamentado|[Nível 3 de alta proteção de dados corporativos](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|As configurações de política impostas no nível 3 incluem todas as configurações de política recomendadas para o nível 1 e 2, e somente adiciona ou atualiza as configurações de política abaixo para implementar mais controles e uma configuração mais sofisticada do que o nível 2.|
|

Para criar uma nova política de proteção de aplicativos para cada plataforma (iOS e Android) no Microsoft Endpoint Manager usando as configurações da estrutura de proteção de dados, você pode:

1. Crie manualmente as políticas seguindo as etapas descritas em [como criar e implantar políticas de proteção de aplicativos com o Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/app-protection-policies).
2. Importe os [modelos JSON da estrutura de configuração de política de proteção de aplicativo do Intune](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) de exemplo com os [scripts do PowerShell do Intune](https://github.com/microsoftgraph/powershell-intune-samples).

## <a name="require-approved-apps-and-app-protection"></a>Exigir aplicativos aprovados e proteção de aplicativos

Para impor as políticas de proteção de aplicativo aplicadas no Intune, você deve criar uma política de acesso condicional para exigir aplicativos cliente aprovados e as condições definidas nas políticas de proteção de aplicativos.

A aplicação de políticas de proteção de aplicativos requer um conjunto de políticas descritas em na [requer política de proteção de aplicativo para o acesso de aplicativo em nuvem com acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access). Essas políticas são incluídas neste conjunto recomendado de políticas de configuração de identidade e acesso.

Para criar a política de acesso condicional que requer aplicativos aprovados e proteção de aplicativos, siga "etapa 1: configurar uma política de acesso condicional do Azure AD para a Microsoft 365" no [cenário 1: os aplicativos da Microsoft 365 exigem aplicativos aprovados com políticas de proteção de aplicativos](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), o que permite o Outlook para IOS e Android, mas bloqueia clientes compatíveis com OAuth do Exchange

   > [!NOTE]
   > Essa política garante que os usuários móveis possam acessar todos os pontos de extremidade do Office usando os aplicativos aplicáveis.

Se você estiver habilitando o acesso móvel ao Exchange Online, implemente [os clientes do Block ActiveSync](secure-email-recommended-policies.md#block-activesync-clients), o que impede que os clientes do Exchange ActiveSync aproveitem a autenticação básica para se conectar ao Exchange Online. Essa política não é mostrada na ilustração no início deste artigo. Ele é descrito e desfigurado nas [recomendações de política para proteger o email](secure-email-recommended-policies.md).

 Essas políticas aproveitam os controles Grant [exigem aplicativo cliente aprovado](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) e [exigem a política de proteção de aplicativos](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

Por fim, o bloqueio de autenticação herdada para outros aplicativos cliente em iOS e dispositivos Android garante que esses clientes não possam ignorar as políticas de acesso condicional. Se você estiver seguindo as orientações deste artigo, já configurou [clientes de bloco que não dão suporte à autenticação moderna](#block-clients-that-dont-support-modern-authentication).

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Definir políticas de conformidade de dispositivos

As políticas de conformidade de dispositivos definem os requisitos que os dispositivos devem atender para serem determinados como em conformidade. Você cria políticas de conformidade de dispositivo do Intune a partir do centro de administração do Microsoft Endpoint Manager.

Você deve criar uma política para cada PC, telefone ou plataforma Tablet:

- Administrador do dispositivo Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8,1 e posterior
- Windows 10 e posterior

Para criar políticas de conformidade de dispositivos, faça logon no [centro de administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com) com suas credenciais de administrador e, em seguida, navegue até políticas de políticas de conformidade de **dispositivos**  >  **Compliance policies**  >  **Policies**. Selecione **criar política**.

Para que as políticas de conformidade do dispositivo sejam implantadas, elas devem ser atribuídas a grupos de usuários. Você atribui uma política depois de criá-la e salvá-la. No centro de administração, selecione a política e, em seguida, selecione **atribuições**. Após selecionar os grupos para os quais você deseja receber a política, selecione **salvar** para salvar a atribuição de grupo e implantar a política.

Para obter uma orientação passo a passo sobre a criação de políticas de conformidade no Intune, consulte [criar uma política de conformidade no Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) na documentação do Intune.

### <a name="recommended-settings-for-windows-10-and-later"></a>Configurações recomendadas para Windows 10 e posterior

As configurações a seguir são recomendadas para computadores que executam o Windows 10 e posterior, conforme configurado na **etapa 2: configurações de conformidade** do processo de criação de políticas.

Para obter **integridade do dispositivo > regras de avaliação do serviço de atestado de integridade do Windows**, Confira esta tabela.

|Propriedades|Valor|Action|
|---|---|---|
|Exigir BitLocker|Precisa|Selecionar|
|Exigir que a inicialização segura seja habilitada no dispositivo|Precisa|Selecionar|
|Exigir integridade de código|Precisa|Selecionar|
|

Para **Propriedades de dispositivo**, especifique os valores apropriados para as versões do sistema operacional com base em suas políticas de segurança e de ti.

Para obter conformidade com o **Gerenciador de configurações**, selecione **exigir**.

Para **segurança do sistema**, Confira esta tabela.

|Tipo|Propriedades|Valor|Action|
|---|---|---|---|
|Password|Exigir uma senha para desbloquear dispositivos móveis|Precisa|Selecionar|
||Senhas simples|Bloquear|Selecionar|
||Tipo de senha|Padrão do dispositivo|Selecionar|
||Tamanho mínimo da senha|6 |Tipo|
||Máximo de minutos de inatividade antes que a senha seja necessária|15 |Tipo <br/> Essa configuração tem suporte para o Android versões 4,0 e superior ou o KNOX 4,0 e superior. Para dispositivos iOS, ele é compatível com iOS 8,0 e superior.|
||Vencimento da senha (dias)|41|Tipo|
||Número de senhas anteriores para evitar reutilização|5 |Tipo|
||Exigir senha quando o dispositivo retornar do estado ocioso (móvel e Holographic)|Precisa|Disponível para Windows 10 e posterior|
|Criptografia|Criptografia do armazenamento de dados no dispositivo|Precisa|Selecionar|
|Segurança do dispositivo|Firewall|Precisa|Selecionar|
||Antivírus|Precisa|Selecionar|
||AntiSpyware|Precisa|Selecionar <br/> Esta configuração requer uma solução anti-spyware registrada com a central de segurança do Windows.|
|Defender|Microsoft Defender Antimalware|Precisa|Selecionar|
||Versão mínima do Microsoft Defender Antimalware||Tipo <br/> Compatível apenas com a área de trabalho do Windows 10. A Microsoft recomenda as versões não mais do que cinco atrás da versão mais recente.|
||Assinatura do Microsoft Defender Antimalware atualizada|Precisa|Selecionar|
||Proteção em tempo real|Precisa|Selecionar <br/> Compatível apenas com a área de trabalho do Windows 10|
|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para Ponto de Extremidade

|Tipo|Propriedades|Valor|Action|
|---|---|---|---|
|Microsoft defender para regras de ponto de extremidade|Exigir que o dispositivo esteja no ou abaixo da Pontuação de risco da máquina|Médio|Selecionar|
|

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Exigir computadores compatíveis (mas telefones e tablets não compatíveis)

Antes de adicionar uma política para exigir computadores compatíveis, não deixe de inscrever dispositivos para gerenciamento no Intune. É recomendável usar a autenticação multifator antes de registrar dispositivos no Intune para garantir que o dispositivo esteja na posse do usuário desejado.

Para exigir computadores compatíveis:

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais.
2. Na lista de serviços do Azure, escolha **Azure Active Directory**.
3. Na lista **gerenciar** , escolha **segurança** e, em seguida, escolha **acesso condicional**.
4. Escolha **nova política** e digite o nome da nova política.

5. Em **assignments**, escolha **Users and Groups** e inclua a quem você deseja aplicar a política. Também excluir seu grupo de exclusão de acesso condicional.

6. Em **assignments**, escolha **aplicativos de nuvem ou ações**.

7. Para **incluir**, escolha **selecionar aplicativos > selecione** e, em seguida, selecione os aplicativos desejados na lista de **aplicativos de nuvem** . Por exemplo, selecione Exchange Online. Escolha **selecionar** quando concluído.

8. Para exigir que computadores compatíveis (mas com telefones e tablets não compatíveis), em **assignments**, escolha **condições > plataformas de dispositivos**. Selecione **Sim** para **Configurar**. Escolha  **Selecionar plataformas de dispositivo**, selecione **Windows** e **MacOS** e, em seguida, escolha **concluído**.

9. Em **controles de acesso**, escolha **conceder** .

10. Escolha **conceder acesso** e marque **exigir que o dispositivo seja marcado como em conformidade**. Para vários controles, selecione **exigir todos os controles selecionados**. Quando concluir, escolha **selecionar**.

11. Selecione **ativado** para **habilitar a política** e, em seguida, escolha **criar**.

> [!NOTE]
> Certifique-se de que o dispositivo está em conformidade antes de habilitar esta política. Caso contrário, você pode ter bloqueado e não poderá alterar essa política até que sua conta de usuário tenha sido adicionada ao grupo de exclusão de acesso condicional.

## <a name="require-compliant-pcs-and-mobile-devices"></a>Exigir computadores *em conformidade e* dispositivos móveis

Para exigir a conformidade de todos os dispositivos:

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais.
2. Na lista de serviços do Azure, escolha **Azure Active Directory**.
3. Na lista **gerenciar** , escolha **segurança** e, em seguida, escolha **acesso condicional**.
4. Escolha **nova política** e digite o nome da nova política.

5. Em **assignments**, escolha **Users and Groups** e inclua a quem você deseja aplicar a política. Também excluir seu grupo de exclusão de acesso condicional.

6. Em **assignments**, escolha **aplicativos de nuvem ou ações**.

7. Para **incluir**, escolha **selecionar aplicativos > selecione** e, em seguida, selecione os aplicativos desejados na lista de **aplicativos de nuvem** . Por exemplo, selecione Exchange Online. Escolha **selecionar** quando concluído.

8. Em **controles de acesso**, escolha **conceder** .

9. Escolha **conceder acesso** e marque **exigir que o dispositivo seja marcado como em conformidade**. Para vários controles, selecione **exigir todos os controles selecionados**. Quando concluir, escolha **selecionar**.

10. Selecione **ativado** para **habilitar a política** e, em seguida, escolha **criar**.

> [!NOTE]
> Certifique-se de que o dispositivo está em conformidade antes de habilitar esta política. Caso contrário, você pode ter bloqueado e não poderá alterar essa política até que sua conta de usuário tenha sido adicionada ao grupo de exclusão de acesso condicional.

## <a name="next-step"></a>Próxima etapa

[![Etapa 3: políticas para usuários convidados e externos](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[Saiba mais sobre as recomendações de política para usuários convidados e externos](identity-access-policies-guest-access.md)
