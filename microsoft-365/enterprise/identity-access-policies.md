---
title: Identidade e dispositivo comuns acessar diretivas - Microsoft 365 Enterprise | Documentos do Microsoft
description: Descreve as políticas para as recomendações da Microsoft sobre como aplicar as configurações e políticas de dispositivo e identidade.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 72a957222ed3bba449e1576873bfc87a614c075b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865314"
---
# <a name="common-identity-and-device-access-policies"></a>Identidade comum e políticas de acesso ao dispositivo
Este artigo descreve o comum recomendado políticas para proteger o acesso para a nuvem de serviços, incluindo aplicativos de local publicado com Proxy de aplicativo do Windows Azure AD. 

Estas diretrizes descrevem como implantar as políticas recomendadas em um ambiente recém-provisionado. Configurar essas políticas em um ambiente de laboratório separado permite compreender e avaliar as políticas recomendadas antes de preparar a distribuição para seus ambientes de produção e pré-produção. Seu ambiente recém-provisionado pode estar somente em nuvem ou ser híbrido.  

## <a name="policy-set"></a>Conjunto de política 

O diagrama a seguir ilustra o conjunto recomendado de diretivas. Ela mostra quais camadas de proteção cada política se aplica e se as diretivas serão aplicadas PCs, telefones e tablets ou ambas as categorias de dispositivos. Ele também indica onde essas diretivas são configuradas.

![Políticas comuns para configurar o acesso de dispositivo e identidade](../images/Identity_device_access_policies_byplan.png)


O restante deste artigo descreve como configurar essas diretivas. 

Usar a autenticação multifator é recomendado antes de inscrição de dispositivos em Intune para garantia de que o dispositivo está em posse do usuário desejado. E você deve registrar os dispositivos em Intune antes da aplicação de políticas de conformidade do dispositivo.

Dar tempo para realizar essas tarefas, recomendamos a implementação das diretivas de linha de base na ordem listada nesta tabela. No entanto, as diretivas MFA para proteção confidencial e altamente regulamentada podem ser implementadas a qualquer momento.


|Nível de Proteção|Diretivas|Mais informações|
|:---------------|:-------|:----------------|
|**Linha de base**|[Exige MFA após a entrada risco *média* ou *alta*](#require-mfa-based-on-sign-in-risk)| |
|        |[Bloquear os clientes que não oferecem suporte a autenticação moderna](#block-clients-that-dont-support-modern-authentication)|Clientes que não usam autenticação moderna poderá ignorar regras de acesso condicional, portanto, é importante bloquear essas.|
|        |[Usuários de alto risco devem alterar a senha](#high-risk-users-must-change-password)|Força os usuários alterem sua senha ao fazer logon se forem detectadas atividades de alto risco para sua conta.|
|        |[Definir políticas de proteção de aplicativos](#define-app-protection-policies)|Uma política por plataforma (iOS, Android, Windows).|
|        |[Exigem aplicativos aprovados](#require-approved-apps)|Impõe a proteção de aplicativos móveis para telefones e tablets|
|        |[Definir políticas de conformidade do dispositivo](#define-device-compliance-policies)|Uma política em cada plataforma.|
|        |[Exigir compatível com PCs](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Impõe Intune gerenciamento de PCs|
|**Confidencial**|[Exige MFA após a entrada risco *baixa*, *média* ou *alta*](#require-mfa-based-on-sign-in-risk)| |
|         |[Exigir compatível com PCs *e* dispositivos móveis](#require-compliant-pcs-and-mobile-devices)|Impõe Intune gerenciamento para PCs e telefone/tablets.|
|**Altamente controlada**|[*Sempre* solicitar MFA](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>Atribuir políticas aos usuários
Antes de configurar políticas, identifique os grupos do Azure AD que você está usando para cada camada de proteção. Normalmente, a proteção de linha de base aplica-se a todas as pessoas na organização. Um usuário que está incluído por base e proteção confidencial terá todas as políticas de linha de base aplicadas plus as políticas confidenciais. Proteção é cumulativa e a política mais restritiva é aplicada. 

Uma prática recomendada é criar um grupo do Azure AD para exclusão de acesso condicional. Adicione a esse grupo para todas as regras de acesso condicional em "Excluir". Isso proporciona um método para fornecer acesso a um usuário enquanto você solucionar problemas de acesso. Isso é recomendado apenas uma solução temporária. Monitorar a este grupo para que as alterações e certifique-se de que o grupo de exclusão está sendo usado apenas como pretendido. 

O diagrama a seguir fornece um exemplo de atribuição de usuário e exclusões.

![Atribuição de usuário de exemplo e exclusões para regras MFA](../images/identity-access-policies-assignment.png)

Na ilustração "superior secreta equipe do projeto X" é atribuído uma política de acesso condicional que requer MFA *sempre*. Ser criterioso ao aplicar níveis mais altos de proteção aos usuários. Membros da equipe projeto deverão fornecer duas formas de autenticação toda vez que efetuam logon, mesmo se eles não estão exibindo o conteúdo altamente regulamentado.  

 Todos os grupos do Azure AD criados como parte dessas recomendações deve ser criado como grupos do Office 365. Isso é especificamente importante para a implantação de proteção de informações do Windows Azure (AIP) quando a proteção de documentos no SharePoint Online.

![Captura de tela de criação de grupos do Office 365](../images/identity-device-AAD-groups.png)




## <a name="require-mfa-based-on-sign-in-risk"></a>Exigir MFA com base na entrada risco
Antes de solicitar a MFA, use uma política de registro de MFA de proteção de identidade para registrar os usuários para MFA. Depois que os usuários estão registrados, você pode impor MFA para entrar. O [trabalho de pré-requisito](identity-access-prerequisites.md) inclui registrando todos os usuários com MFA.

Para criar uma nova política de acesso condicional: 

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais. Depois de entrar com êxito, você verá o Painel do Azure.

2. Escolha **Azure Active Directory** no menu à esquerda.

3. Na seção **Segurança**, escolha **Acesso condicional**.

4. Escolha **nova política** , conforme mostrado na captura de tela abaixo:

![Política de AC de linha de base](./media/secure-email/CA-EXO-policy-1.png)

 As tabelas a seguir descreve as configurações de política de acesso condicional implementar para esta diretiva.

**Atribuições**

|Tipo|Propriedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Usuários e grupos|Incluir|Selecionar usuários e grupos – selecione grupos de segurança específicos que contém os usuários de destino|Inicie com o grupo de segurança, incluindo usuários piloto.|
||Excluir|Grupo de segurança de exceção, contas de serviço (identidades de aplicativo)|Associação modificada de forma temporária, conforme o necessário|
|Aplicativos em nuvem|Incluir|Selecione os aplicativos que você deseja que esta regra se aplique. Por exemplo, selecione Exchange Online do Office 365||
|Condições|Configurado|Sim|Configure específicos para suas necessidades e ambiente|
|Risco de entrada|Nível de risco||Consulte as orientações na tabela a seguir|

**Risco de entrada**

Aplica as configurações com base no nível de proteção que você está direcionando.

|Propriedade|Nível de proteção|Valores|Notas|
|:---|:---------|:-----|:----|
|Nível de risco|Linha de base|Alto, médio|Marque ambos|
| |Confidencial|Alta, média, baixa|Marque todos os três|
| |Altamente controlada| |Deixe todas as opções desmarcada para impor sempre MFA|

**Controles de acesso**

|Tipo|Propriedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Conceder|Conceder acesso|verdadeiro|Selecionada|
||Exigir MFA|verdadeiro|Verificar|
||Exigir o dispositivo para ser marcado como compatível|Falso||
||Exigem o dispositivo de unidas híbrida Azure AD|Falso||
||Requer aplicativo cliente aprovado|Falso||
||Exigir todos os controles selecionados|verdadeiro|Selecionada|

> [!NOTE]
> Certifique-se de que habilite essa diretiva, clicando **no**. Também considere usando a ferramenta [se](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para testar a diretiva



## <a name="block-clients-that-dont-support-modern-authentication"></a>Bloquear os clientes que não oferecem suporte a autenticação moderna
1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais. Depois de entrar com êxito, você verá o Painel do Azure.

2. Escolha **Azure Active Directory** no menu à esquerda.

3. Na seção **Segurança**, escolha **Acesso condicional**.

4. Escolha **Nova política**.

As tabelas a seguir descreve as configurações de política de acesso condicional implementar para esta diretiva.

**Atribuições**

|Tipo|Propriedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Usuários e grupos|Incluir|Selecionar usuários e grupos – selecione grupos de segurança específicos que contém os usuários de destino|Inicie com o grupo de segurança, incluindo usuários piloto.|
||Excluir|Grupo de segurança de exceção, contas de serviço (identidades de aplicativo)|Associação modificada de forma temporária, conforme o necessário|
|Aplicativos em nuvem|Incluir|Selecione os aplicativos que você deseja que esta regra se aplique. Por exemplo, selecione Exchange Online do Office 365||
|Condições|Configurado|Sim|Configurar aplicativos do cliente|
|Aplicativos do cliente|Configurado|Sim|Aplicativos móveis e clientes de área de trabalho, outros clientes (selecione ambos)|

**Controles de acesso**

|Tipo|Propriedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Conceder|Bloquear acesso|verdadeiro|Selecionada|
||Exigir MFA|Falso||
||Exigir o dispositivo para ser marcado como compatível|Falso||
||Exigem o dispositivo de unidas híbrida Azure AD|Falso||
||Requer aplicativo cliente aprovado|Falso||
||Exigir todos os controles selecionados|verdadeiro|Selecionada|

> [!NOTE]
> Certifique-se de que habilite essa diretiva, clicando **no**. Também considere usando a ferramenta [se](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para testar a diretiva



## <a name="high-risk-users-must-change-password"></a>Usuários de alto risco devem alterar a senha
Para garantir que todas as contas de usuários de alto risco comprometidas sejam forçadas a executar uma alteração de senha ao entrar, você deve aplicar a política a seguir.

Faça logon no [portal do Microsoft Azure (http://portal.azure.com) ](http://portal.azure.com/) com suas credenciais de administrador e navegue até **proteção de identidade do Windows Azure AD > política de risco de usuário**.

**Atribuições**

|Tipo|Propriedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Usuários|Incluir|todos os usuários|Selecionada|
||Excluir|Nenhum||
|Condições|Risco do usuário|Alta|Selecionada|

**Controles**

| Tipo | Propriedades | Valores                  | Observações |
|:-----|:-----------|:------------------------|:------|
|      | Acessar     | Permitir acesso            | verdadeiro  |
|      | Acessar     | Requer a alteração de senha | verdadeiro  |

**Revisão:** não aplicável

> [!NOTE]
> Certifique-se de que habilite essa diretiva, clicando **no**. Também considere usando a ferramenta [se](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para testar a diretiva

## <a name="define-app-protection-policies"></a>Definir políticas de proteção de aplicativos
Políticas de proteção de aplicativos que definem quais aplicativos são permitidos e as ações que eles podem executar com dados de sua organização. Crie Intune app políticas de proteção de dentro do portal do Azure. 

Crie uma diretiva em cada plataforma:
- iOS
- Android
- Windows 10

Para criar uma nova política de proteção de aplicativo, faça logon no portal do Microsoft Azure com suas credenciais de administrador e navegue até **aplicativos móveis > políticas de proteção de aplicativos**. Clique em **Adicionar uma política**.

Há pequenas diferenças na proteção app com opções de política entre iOS e Android. O abaixo política é especificamente para Android. Use esta opção como um guia para as outras políticas.

Lista de aplicativos recomendada inclui o seguinte:
- PowerPoint
- Excel
- Word
- Microsoft Teams
- Microsoft SharePoint
- Visualizador do Microsoft Visio
- OneDrive
- OneNote
- Outlook

As tabelas a seguir descrevem as configurações recomendadas:

|Tipo|Propriedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Realocação de dados|Impedir backup do Android|Sim|No iOS isso especificamente indicará o iTunes e o iCloud|
||Permitir que o aplicativo transfira dados para outros aplicativos|Aplicativos gerenciados por política||
||Permitir que o aplicativo receba dados de outros aplicativos|Aplicativos gerenciados por política||
||Impedir "Salvar como"|Sim||
||Selecione em quais serviços de armazenamento os dados corporativos podem ser salvos|OneDrive for Business, do SharePoint||
||Restringir recortar, copiar e colar com outros aplicativos|Aplicativos com Colar no gerenciada de política||
||Restringir a exibição de conteúdo da Web no Managed Browser|Não||
||Criptografar dados do aplicativo|Sim|No iOS, selecione a opção: Quando o dispositivo está bloqueado|
||Desabilitar a criptografia do aplicativo quando o dispositivo está habilitado|Sim|Desative esta configuração para evitar a criptografia dupla|
||Desabilitar a sincronização de contatos|Não||
||Desabilitar a impressão|Não||
|Acessar|Solicitar PIN para acesso|Sim||
||Selecione o tipo|Numérico||
||Permitir PIN simples|Não||
||Tamanho do PIN|6 ||
||Permitir a impressão digital em vez do PIN|Sim||
||Desabilitar app PIN quando o PIN do dispositivo é gerenciado|Sim||
||Exigem credenciais corporativas para acesso|Não||
||Verificar novamente o requisito de acesso após (minutos)|30||
||Bloquear captura de tela e Assistente do Android|Não|No iOS isso não é uma opção disponível|
|Requisitos de segurança de entrada|Tentativas máximas PIN|5 |Redefinir Pin|
||Período de cortesia offline|720|Bloquear acesso|
||Intervalo offline (dias) antes do apagamento dos dados do aplicativo|90|Apagar dados|
||Dispositivos Jailbroken/raiz| |Apagar dados|

Ao concluir, lembre-se de clicar em "Criar". Repita as etapas acima e substitua a plataforma selecionada (menu suspenso) por iOS. Isso cria duas políticas de aplicativo, portanto, após criar a política, atribua grupos à política e implante-a.

Para editar as políticas e atribuir essas políticas a usuários, consulte [como criar e atribuir políticas de proteção de aplicativos](https://docs.microsoft.com/intune/app-protection-policies). 

## <a name="require-approved-apps"></a>Exigem aplicativos aprovados
Para exigir a aplicativos aprovados:

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais. Depois de entrar com êxito, você verá o Painel do Azure.

2. Escolha **Azure Active Directory** no menu à esquerda.

3. Na seção **Segurança**, escolha **Acesso condicional**.

4. Escolha **Nova política**.

5. Insira um nome para a política e escolha os **Usuários e grupos** aos quais deseja aplicar a política.

6. Escolha **Aplicativos na nuvem**.

7. Escolha **Selecionar aplicativos**, selecione os aplicativos desejados na lista de **aplicativos na nuvem** . Por exemplo, selecione Exchange Online do Office 365. Clique em **Selecionar** e **feito**.

8. Escolha **Conceder** na seção **Controles de acesso**.

9. Escolha **conceder acesso**, selecione **exigir aprovados pelo aplicativo cliente**.  Para vários controles, selecione **exigir os controles selecionados**e selecione **Selecionar**. 

10. Clique em **Criar**.

## <a name="define-device-compliance-policies"></a>Definir políticas de conformidade do dispositivo

Políticas de conformidade do dispositivo definem os requisitos que dispositivos devem aderir para ser marcado como compatível. Crie o dispositivo Intune políticas de conformidade de dentro do portal do Azure. 

Crie uma diretiva em cada plataforma:
- Android
- Android enterprise
- iOS
- macOS
- Windows Phone 8.1
- Windows 8.1 e posterior
- Windows 10 e posterior

Para criar políticas de conformidade de dispositivo, faça logon no portal do Microsoft Azure com suas credenciais de administrador e navegue até **Intune > conformidade do dispositivo**. Clique em **Criar política**.

As configurações a seguir são recomendadas para Windows 10.

**Integridade de dispositivo: as regras de avaliação do serviço de certificação de integridade do Windows**

|Propriedades|Valores|Notas|
|:---------|:-----|:----|
|Requerer BitLocker|Obrigatório||
|Exigir inicialização seguro a ser habilitada no dispositivo|Obrigatório||
|Requer integridade de código|Obrigatório||


**Propriedades do dispositivo**

|Tipo|Propriedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Versão do sistema operacional|Tudo|Não configurado||

Para todas as políticas acima para serem consideradas implantadas, elas devem ser direcionadas para grupos de usuários. Você pode fazer isso criando a política (ao Salvar) ou posteriormente selecionando Gerenciar Implantação na seção Política (no mesmo nível de Adicionar).

**Segurança do sistema**

|Tipo|Propriedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Senha|Exigir uma senha para desbloquear os dispositivos móveis|Obrigatório||
||Senhas simples|Bloquear||
||Tipo de senha|Padrão de dispositivo||
||Tamanho mínimo da senha|6 ||
||Máximo de minutos de inatividade antes que a senha é obrigatória|15 |Essa configuração é suportada para Android versões 4.0 e acima ou KNOX 4.0 e acima. Para dispositivos iOS, ele é suportado para iOS 8.0 e acima.|
||Vencimento da senha (dias)|41||
||Número de senhas anteriores para evitar a reutilização|5 ||
||Exigir senha quando o dispositivo retorna a partir de um estado ocioso (Mobile e Holographic)|Obrigatório|Disponível para o Windows 10 e versões posteriores.|
|Criptografia|Criptografia de armazenamento de dados no dispositivo|Obrigatório||
|Segurança de dispositivo|Firewall|Obrigatório||
||Antivírus|Obrigatório||
||AntiSpyware|Obrigatório|Essa configuração requer uma solução antispyware registrada na Central de segurança do Windows.|
|Defender|Windows Defender Antimalware|Obrigatório||
||Versão mínima do Windows Defender Antimalware||Só tem suporte para desktop do Windows 10. A Microsoft recomenda versões não mais de cinco por trás da versão mais recente.|
||Assinatura do Windows Defender Antimalware atualizada|Obrigatório||
||Proteção em tempo real|Obrigatório|Só tem suporte para desktop do Windows 10.|

**Windows Defender ATP**

|Tipo|Propriedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Regras de proteção de ameaça avançado do Windows Defender|Exigir o dispositivo esteja em ou subordinadas a pontuação de risco de máquina|Médio||





## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Exigir compatível com PCs (mas não compatível com telefones e tablets)
Antes de adicionar uma diretiva para exigir compatível com PCs, certifique-se de registrar os dispositivos de gerenciamento em Intune. Usar a autenticação multifator é recomendado antes de inscrição de dispositivos em Intune para garantia de que o dispositivo está em posse do usuário desejado. 

Para exigir PCs compatível com:

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais. Depois de entrar com êxito, você verá o Painel do Azure.

2. Escolha **Azure Active Directory** no menu à esquerda.

3. Na seção **Segurança**, escolha **Acesso condicional**.

4. Escolha **Nova política**.

5. Insira um nome para a política e escolha os **Usuários e grupos** aos quais deseja aplicar a política.

6. Escolha **Aplicativos na nuvem**.

7. Escolha **Selecionar aplicativos**, selecione os aplicativos desejados na lista de **aplicativos na nuvem** . Por exemplo, selecione Exchange Online do Office 365. Clique em **Selecionar** e **feito**.

8. Para exigir compatível com PCs, mas não compatível com telefones e tablets, escolha **plataformas de dispositivo**e **condições** . Escolha "plataformas do dispositivo selecionado" e selecione **Windows** e **macOS**.

9. Escolha **Conceder** na seção **Controles de acesso**.

10. Escolha **conceder acesso**, selecione **exigir o dispositivo deve ser marcado como compatível com**.  Para vários controles, selecione **exigir todos os controles selecionados**e selecione **Selecionar**. 

11. Clique em **Criar**.

Se o seu objetivo é exigem compatível com PCs *e* dispositivos móveis, não marque plataformas. Isso impõe FIPS para todos os dispositivos. 




## <a name="require-compliant-pcs-and-mobile-devices"></a>Exigir compatível com PCs *e* dispositivos móveis

Para exigir a conformidade para todos os dispositivos:

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais. Depois de entrar com êxito, você verá o Painel do Azure.

2. Escolha **Azure Active Directory** no menu à esquerda.

3. Na seção **Segurança**, escolha **Acesso condicional**.

4. Escolha **Nova política**.

5. Insira um nome para a política e escolha os **Usuários e grupos** aos quais deseja aplicar a política.

6. Escolha **Aplicativos na nuvem**.

7. Escolha **Selecionar aplicativos**, selecione os aplicativos desejados na lista de **aplicativos na nuvem** . Por exemplo, selecione Exchange Online do Office 365. Clique em **Selecionar** e **feito**.

8. Escolha **Conceder** na seção **Controles de acesso**.

9. Escolha **conceder acesso**, selecione **exigir o dispositivo deve ser marcado como compatível com**. Para vários controles, selecione **exigir todos os controles selecionados**e selecione **Selecionar**. 

10. Clique em **Criar**.

Ao criar essa diretiva, não marque plataformas. Aplica a dispositivos incompatíveis.















<!---
#### Data loss prevention
The goal for your device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain or enroll their PCs into management with Microsoft Intune or System Center Configuration Manager.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact

For most organizations, it is important to be able to set user expectations around when and for which conditions they will be expected to sign into Office 365 to access their email.  

Users typically benefit from single sign-on (SSO) except during the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users may be asked to MFA whenever a **medium or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Sensitive
This section describes the recommendations for the sensitive tier of data, identity, and device protection. These recommendations are for customers who have a subset of data that must be protected at higher levels or require all data to be protected at these higher levels.

You can apply increased protection to all or specific data sets in your Office 365 environment. For example, you can apply policies to ensure sensitive data is only shared between protected apps to prevent data loss. We recommend protecting identities and devices that access sensitive data with comparable levels of security.

### Conditional access policy settings
#### Identity protection

You can give users single sign-on (SSO) experience as described in earlier sections. You only need to intervene when necessary based on [risk events](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Require MFA on **low or above** risk sessions
* Require secure password change for high risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data loss prevention

The goal for these device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their PCs to an Active Directory Domain or enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 email.

Users typically benefit from single sign-on (SSO) except under the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to MFA whenever a **low or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Highly regulated
This section describes the recommendations for the highly regulated tier of data, identity, and device protection. These recommendations are for customers who may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

### Conditional access policy settings
#### Identity protection

For the highly regulated tier Microsoft recommends enforcing MFA for all new sessions.
* Require MFA for all new sessions
* Require secure password change for **high** risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data Loss Prevention
The goal for these device and app management policies is to prevent data loss in the event of a lost or stolen device. This is done by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

For the highly regulated tier, we recommend requiring apps that support Intune App Protection policy running only on Intune compliant or domain-joined devices.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain, **or** enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that devices used to access Office 365 email and files are managed by Intune or company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are Low risk as determined by a third-party MTP like Lookout or SkyCure.|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 files.

* Users configured as highly regulated will be required to re-authenticate with MFA after their session expires.
* When users at risk sign-in they will be asked to change their password after completing MFA.
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to perform MFA whenever they begin a new session.  
  * Users will be required to use email apps that support the Intune App Protection SDK
  * Users will be required to access emails from Intune compliant or AD domain-joined devices.
--->
## <a name="next-steps"></a>Próximas etapas

[Saiba mais sobre recomendações de política para proteger o email](secure-email-recommended-policies.md)
