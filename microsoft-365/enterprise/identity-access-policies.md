---
title: Políticas comuns de acesso de dispositivo e identidade-Microsoft 365 Enterprise | Microsoft docs
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
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 9912b05c07599c5ad0c0ed7fec91ae2572bd2ead
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289305"
---
# <a name="common-identity-and-device-access-policies"></a>Identidade comum e políticas de acesso ao dispositivo
Este artigo descreve as políticas comuns recomendadas para proteger o acesso a serviços de nuvem, incluindo aplicativos locais publicados com o proxy de aplicativo do Azure AD. 

Este guia discute como implantar as políticas recomendadas em um ambiente provisionado recentemente. Configurar essas políticas em um ambiente de laboratório separado permite que você entenda e avalie as políticas recomendadas antes de preparar a distribuição para seus ambientes de pré-produção e produção. Seu ambiente provisionado recentemente pode ser apenas na nuvem ou híbrido.  

## <a name="policy-set"></a>Conjunto de políticas 

O diagrama a seguir ilustra o conjunto de políticas recomendado. Ele mostra qual camada de proteção cada política se aplica e se as políticas se aplicam a PCs ou telefones e tablets ou a ambas as categorias de dispositivos. Também indica onde essas políticas estão configuradas.

![Políticas comuns para configurar a identidade e o acesso ao dispositivo](../images/Identity_device_access_policies_byplan.png)


O restante deste artigo descreve como configurar essas políticas. 

É recomendável usar a autenticação multifator antes de registrar dispositivos no Intune para garantir que o dispositivo esteja na posse do usuário desejado. Você também deve inscrever dispositivos no Intune antes de impor políticas de conformidade do dispositivo.

Para dar tempo para realizar essas tarefas, recomendamos implementar as políticas de linha de base na ordem listada nesta tabela. No enTanto, as políticas da MFA de proteção confidencial e altamente regulamentada podem ser implementadas a qualquer momento.


|Nível de Proteção|Políticas|Mais informações|
|:---------------|:-------|:----------------|
|**Baseline**|[Exigir MFA quando o risco de entrada for *médio* ou *alto*](#require-mfa-based-on-sign-in-risk)| |
|        |[Bloquear clientes que não dão suporte à autenticação moderna](#block-clients-that-dont-support-modern-authentication)|Os clientes que não usam a autenticação moderna podem ignorar as regras de acesso condicional, portanto, é importante bloquear esses|
|        |[Usuários de alto risco devem alterar a senha](#high-risk-users-must-change-password)|Obriga os usuários a alterarem a senha ao entrar se a atividade de alto risco for detectada para sua conta|
|        |[Definir políticas de proteção de aplicativos](#define-app-protection-policies)|Uma política por plataforma (iOS, Android, Windows).|
|        |[Exigir aplicativos aprovados](#require-approved-apps)|Impõe proteção de aplicativos móveis para telefones e tablets|
|        |[Definir políticas de conformidade do dispositivo](#define-device-compliance-policies)|Uma política para cada plataforma|
|        |[Exigir computadores compatíveis](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Impõe o gerenciamento de computadores do Intune|
|**Confidencial**|[Exigir MFA quando o risco de entrada for *baixo*, *médio* ou *alto*](#require-mfa-based-on-sign-in-risk)| |
|         |[Exigir computadores *em conformidade e* dispositivos móveis](#require-compliant-pcs-and-mobile-devices)|Impõe o gerenciamento do Intune para PCs e telefones/tablets|
|**Altamente regulamentado**|[*Sempre* exigir MFA](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>Atribuindo políticas aos usuários
Antes de configurar as políticas, identifique os grupos do Azure AD que você está usando para cada camada de proteção. Normalmente, a proteção de linha de base se aplica a todas as pessoas na organização. Um usuário que está incluído na linha de base e proteção confidencial terá todas as políticas de linha de base aplicadas mais as políticas confidenciais. A proteção é cumulativa e a política mais restritiva é imposta. 

Uma prática recomendada é criar um grupo do Azure AD para exclusão de acesso condicional. Adicione esse grupo a todas as suas regras de acesso condicional em "exclude". Isso fornece um método para fornecer acesso a um usuário enquanto você soluciona problemas de acesso. Isso é recomendado somente como uma solução temporária. Monitore esse grupo para alterações e certifique-se de que o grupo de exclusão esteja sendo usado apenas conforme o esperado. 

O diagrama a seguir fornece um exemplo de atribuição e exclusões do usuário.

![Exemplo de atribuição e exclusões de usuário para regras MFA](../images/identity-access-policies-assignment.png)

Na ilustração, a "equipe de" projeto de segredo principal X "é atribuída uma política de acesso condicional que requer MFA *sempre*. Seja criterioso ao aplicar níveis mais altos de proteção aos usuários. Os membros desta equipe de projeto serão solicitados a fornecer duas formas de autenticação sempre que fizerem logon, mesmo que não estejam exibindo conteúdo altamente regulamentado.  

Todos os grupos do Azure AD criados como parte dessas recomendações devem ser criados como grupos do Office 365. Isso é importante principalmente para a implantação da AIP (Proteção de Informações do Azure) ao proteger documentos no SharePoint Online.

![Captura de tela para criar grupos do Office 365](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>Exigir a MFA com base no risco de entrada
Antes de exigir a MFA, primeiro use uma política de registro do MFA de proteção de identidade para registrar usuários para MFA. Depois que os usuários são registrados, é possível aplicar a MFA de entrada. O [trabalho de pré-requisito](identity-access-prerequisites.md) inclui o registro de todos os usuários com a MFA.

Para criar uma nova política de acesso condicional: 

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais. Após entrar com êxito, você verá o painel do Azure.

2. Escolha **Azure Active Directory** no menu à esquerda.

3. Na seção **Segurança**, escolha **Acesso condicional**.

4. Escolha **Nova política**.

![Política de AC de linha de base](./media/secure-email/CA-EXO-policy-1.png)

 As tabelas a seguir descrevem as configurações de política de acesso condicional a serem implementadas para essa política.

**Atribuições**

|Tipo|Propriedades|Valores|Anotações|
|:---|:---------|:-----|:----|
|Usuários e grupos|Incluir|Selecionar usuários e grupos – selecione grupos de segurança específicos que contém os usuários de destino|Inicie com o grupo de segurança, incluindo usuários piloto|
||Excluir|Grupo de segurança de exceção, contas de serviço (identidades de aplicativo)|Associação modificada de acordo com a necessidade de uma base temporária|
|Aplicativos em nuvem|Incluir|Selecione os aplicativos para os quais você deseja aplicar essa regra. Por exemplo, selecione Office 365 Exchange Online||
|Condições|Configurado|Sim|Configure específicos para suas necessidades e ambiente|
|Risco de entrada|Nível de risco||Veja as orientações na tabela a seguir|

**Risco de entrada**

Aplique as configurações com base no nível de proteção que você está direcionando.

|Propriedade	|Nível de proteção|Valores|Anotações|
|:---|:---------|:-----|:----|
|Nível de risco|Linha de base|Alto, médio|Marque ambos|
| |Confidencial|Alta, média, baixa|Marque todos os três|
| |Altamente controlada| |Deixar todas as opções desmarcadas para sempre impor a MFA|

**Controles de acesso**

|Tipo|Propriedades|Valores|Anotações|
|:---|:---------|:-----|:----|
|Conceder|Conceder acesso|True|Selecionado|
||Exigir MFA|verdadeiro|Verificar|
||Exigir que o dispositivo seja marcado como em conformidade|False||
||Exigir dispositivo híbrido associado ao AD do Azure|False||
||Exigir aplicativo cliente aprovado|Falso||
||Exigir todos os controles selecionados|verdadeiro|Selecionado|

> [!NOTE]
> Certifique-se de habilitar essa política, escolhendo **Ativar**. Considere também usar a ferramenta [e se](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para testar a política.



## <a name="block-clients-that-dont-support-modern-authentication"></a>Bloquear clientes que não dão suporte à autenticação moderna
1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais. Após entrar com êxito, você verá o painel do Azure.

2. Escolha **Azure Active Directory** no menu à esquerda.

3. Na seção **Segurança**, escolha **Acesso condicional**.

4. Escolha **Nova política**.

As tabelas a seguir descrevem as configurações de política de acesso condicional a serem implementadas para essa política.

**Atribuições**

|Tipo|Propriedades|Valores|Anotações|
|:---|:---------|:-----|:----|
|Usuários e grupos|Incluir|Selecionar usuários e grupos – selecione grupos de segurança específicos que contém os usuários de destino|Inicie com o grupo de segurança, incluindo usuários piloto|
||Excluir|Grupo de segurança de exceção, contas de serviço (identidades de aplicativo)|Associação modificada de forma temporária, conforme o necessário|
|Aplicativos em nuvem|Incluir|Selecione os aplicativos para os quais você deseja aplicar essa regra. Por exemplo, selecione Office 365 Exchange Online||
|Condições|Configurado|Sim|Configurar aplicativos cliente|
|Aplicativos cliente|Configurado|Sim|Aplicativos móveis e clientes de desktop, outros clientes (selecione ambos)|

**Controles de acesso**

|Tipo|Propriedades|Valores|Anotações|
|:---|:---------|:-----|:----|
|Conceder|Bloquear acesso|True|Selecionado|
||Exigir MFA|False||
||Exigir que o dispositivo seja marcado como em conformidade|False||
||Exigir dispositivo híbrido associado ao AD do Azure|False||
||Exigir aplicativo cliente aprovado|Falso||
||Exigir todos os controles selecionados|verdadeiro|Selecionado|

> [!NOTE]
> Certifique-se de habilitar essa política, escolhendo **Ativar**. Considere também usar a ferramenta [e se](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para testar a política.



## <a name="high-risk-users-must-change-password"></a>Usuários de alto risco devem alterar a senha
Para garantir que todas as contas comprometidas de usuários de alto risco sejam forçadas a executar uma alteração de senha ao entrar, você deve aplicar a política a seguir.

Faça logon no [Portal do Microsoft Azure (http://portal.azure.com)](http://portal.azure.com/) com suas credenciais de administrador e, em seguida, navegue até **Azure AD Identity Protection > Política de Risco do Usuário**.

**Atribuições**

|Tipo|Propriedades|Valores|Anotações|
|:---|:---------|:-----|:----|
|Usuários|Incluir|todos os usuários|Selecionada|
||Excluir|Nenhum||
|Condições|Risco do usuário|Alta|Selecionada|

**Controles**

| Tipo | Propriedades | Valores                  | Anotações |
|:-----|:-----------|:------------------------|:------|
|      | Acesso     | Permitir acesso            | True  |
|      | Acesso     | Requer a alteração de senha | verdadeiro  |

**Revisão:** não aplicável

> [!NOTE]
> Certifique-se de habilitar essa política, escolhendo **Ativar**. Considere também usar a ferramenta [e se](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para testar a política

## <a name="define-app-protection-policies"></a>Definir políticas de proteção de aplicativos
As políticas de proteção de aplicativos definem quais aplicativos são permitidos e as ações que eles podem realizar com os dados da sua organização. Criar políticas de proteção de aplicativos do Intune de dentro do portal do Azure. 

Criar uma política para cada plataforma:
- iOS
- Android
- Windows 10

Para criar uma nova política de proteção de aplicativos, faça logon no portal do Microsoft Azure com suas credenciais de administrador e navegue até **aplicativos móveis > políticas de proteção de aplicativos**. Escolha **Adicionar uma política**.

Há pequenas diferenças nas opções de política de proteção de aplicativo entre o iOS e o Android. A política abaixo é especificamente para Android. Use este como um guia para suas outras políticas.

A lista recomendada de aplicativos inclui o seguinte:
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

|Tipo|Propriedades|Valores|Anotações|
|:---|:---------|:-----|:----|
|Realocação de dados|Impedir backup do Android|Sim|No iOS isso especificamente indicará o iTunes e o iCloud|
||Permitir que o aplicativo transfira dados para outros aplicativos|Aplicativos gerenciados por política||
||Permitir que o aplicativo receba dados de outros aplicativos|Aplicativos gerenciados por política||
||Impedir "Salvar como"|Sim||
||Selecione em quais serviços de armazenamento os dados corporativos podem ser salvos|OneDrive for Business, SharePoint||
||Restringir recortar, copiar e colar com outros aplicativos|Aplicativos gerenciados por política com colar no||
||Restringir a exibição de conteúdo da Web no Managed Browser|Não||
||Criptografar dados do aplicativo|Sim|No iOS, selecione a opção: Quando o dispositivo está bloqueado|
||Desabilitar a criptografia de aplicativos quando o dispositivo estiver habilitado|Sim|DesAbilite essa configuração para evitar a criptografia dupla|
||Desabilitar a sincronização de contatos|Não||
||Desabilitar a impressão|Não||
|Acessar|Solicitar PIN para acesso|Sim||
||Selecionar tipo|Numeric||
||Permitir PIN simples|Não||
||Tamanho do PIN|6||
||Permitir a impressão digital em vez do PIN|Sim||
||Desabilitar PIN do aplicativo quando o PIN do dispositivo for gerenciado|Sim||
||Exigir credenciais corporativas para acesso|Não||
||Verificar novamente o requisito de acesso após (minutos)|até||
||Bloquear captura de tela e Assistente do Android|Não|No iOS isso não é uma opção disponível|
|Requisitos de segurança de entrada|Máximo de tentativas de PIN|0,5|Redefinir PIN|
||Período de cortesia offline|720|Bloquear acesso|
||Intervalo offline (dias) antes do apagamento dos dados do aplicativo|90|Limpar dados|
||Dispositivos desBloqueados/com raiz| |Limpar dados|

Ao concluir, lembre-se de selecionar "criar". Repita as etapas acima e substitua a plataforma selecionada (menu suspenso) por iOS. Isso cria duas políticas de aplicativo, portanto, após criar a política, atribua grupos à política e implante-a.

Para editar as políticas e atribuir essas políticas aos usuários, consulte [como criar e atribuir políticas de proteção de aplicativos](https://docs.microsoft.com/intune/app-protection-policies). 

## <a name="require-approved-apps"></a>Exigir aplicativos aprovados
Para exigir aplicativos aprovados:

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais. Após entrar com êxito, você verá o painel do Azure.

2. Escolha **Azure Active Directory** no menu à esquerda.

3. Na seção **Segurança**, escolha **Acesso condicional**.

4. Escolha **Nova política**.

5. Insira um nome para a política e escolha os **Usuários e grupos** aos quais deseja aplicar a política.

6. Escolha **Aplicativos na nuvem**.

7. Escolha **selecionar aplicativos**, selecione os aplicativos desejados na lista **aplicativos de nuvem** . Por exemplo, selecione Office 365 Exchange Online. Escolha **selecionar** e **concluir**.

8. Escolha **Conceder** na seção **Controles de acesso**.

9. Escolha **conceder acesso**, selecione **exigir aplicativo cliente aprovado**. Para vários controles, selecione **exigir os controles selecionados**e, em seguida, escolha **selecionar**. 

10. Escolha **Criar**.

## <a name="define-device-compliance-policies"></a>Definir políticas de conformidade de dispositivos

As políticas de conformidade de dispositivos definem os requisitos para os quais os dispositivos devem aderir para serem marcados como em conformidade. Criar políticas de conformidade de dispositivo do Intune de dentro do portal do Azure. 

Criar uma política para cada plataforma:
- Android
- Android Enterprise
- iOS
- macOS
- Esta configuração está disponível nos seguintes tipos de dispositivos:
- Windows 8,1 e posterior
- Windows 10 e posterior

Para criar políticas de conformidade de dispositivos, faça logon no portal do Microsoft Azure com suas credenciais de administrador e, em seguida, navegue até **conformidade de dispositivo do Intune >**. Selecione **criar política**.

As configurações a seguir são recomendadas para o Windows 10.

**Integridade do dispositivo: regras de avaliação do serviço de atestado de integridade do Windows**

|Propriedades|Valores|Anotações|
|:---------|:-----|:----|
|Exigir BitLocker|Precisa||
|Exigir que a inicialização segura seja habilitada no dispositivo|Precisa||
|Exigir integridade de código|Precisa||


**Propriedades do dispositivo**

|Tipo|Propriedades|Valores|Anotações|
|:---|:---------|:-----|:----|
|Versão do sistema operacional|Tudo|Não configurado||

Para todas as políticas acima para serem consideradas implantadas, elas devem ser direcionadas para grupos de usuários. Você pode fazer isso criando a política (ao salvar) ou posterior selecionando **gerenciar implantação** na seção **política** (mesmo nível de adição).

**Segurança do sistema**

|Tipo|Propriedades|Valores|Anotações|
|:---|:---------|:-----|:----|
|Senha|Exigir uma senha para desbloquear dispositivos móveis|Precisa||
||Senhas simples|Bloquear||
||Tipo de senha|Padrão do dispositivo||
||Tamanho mínimo da senha|6||
||Máximo de minutos de inatividade antes que a senha seja necessária|15|Essa configuração tem suporte para o Android versões 4,0 e superior ou o KNOX 4,0 e superior. Para dispositivos iOS, ele é compatível com iOS 8,0 e superior|
||Vencimento da senha (dias)|41||
||Número de senhas anteriores para evitar reutilização|0,5||
||Exigir senha quando o dispositivo retornar do estado ocioso (móvel e Holographic)|Precisa|Disponível para Windows 10 e posterior|
|Criptografia|Criptografia do armazenamento de dados no dispositivo|Precisa||
|Segurança do dispositivo|Firewall|Precisa||
||Antivírus|Precisa||
||AntiSpyware|Precisa|Esta configuração requer uma solução anti-spyware registrada com a central de segurança do Windows|
|Defender|Windows Defender Antimalware|Precisa||
||Versão mínima do Windows Defender Antimalware||Compatível apenas com a área de trabalho do Windows 10. A Microsoft recomenda as versões não mais do que cinco atrás da versão mais recente|
||Assinatura antimalware do Windows Defender atualizada|Precisa||
||Proteção em tempo real|Precisa|Compatível apenas com a área de trabalho do Windows 10|

**Windows Defender ATP**

|Tipo|Propriedades|Valores|Anotações|
|:---|:---------|:-----|:----|
|Regras de proteção avançada contra ameaças do Windows Defender|Exigir que o dispositivo esteja no ou abaixo da Pontuação de risco da máquina|Médio||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Exigir computadores compatíveis (mas telefones e tablets não compatíveis)
Antes de adicionar uma política para exigir computadores compatíveis, não deixe de inscrever dispositivos para gerenciamento no Intune. É recomendável usar a autenticação multifator antes de registrar dispositivos no Intune para garantir que o dispositivo esteja na posse do usuário desejado. 

Para exigir computadores compatíveis:

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais. Após entrar com êxito, você verá o painel do Azure.

2. Escolha **Azure Active Directory** no menu à esquerda.

3. Na seção **Segurança**, escolha **Acesso condicional**.

4. Escolha **Nova política**.

5. Insira um nome para a política e escolha os **Usuários e grupos** aos quais deseja aplicar a política.

6. Escolha **Aplicativos na nuvem**.

7. Escolha **selecionar aplicativos**, selecione os aplicativos desejados na lista **aplicativos de nuvem** . Por exemplo, selecione Office 365 Exchange Online. Escolha **selecionar** e **concluir**.

8. Para exigir que os computadores em conformidade, mas não compatíveis com telefones e tablets, escolha **condições** e **plataformas de dispositivos**. Escolha **Selecionar plataformas de dispositivo** e selecione **Windows** e **MacOS**.

9. Escolha **Conceder** na seção **Controles de acesso**.

10. Escolha **conceder acesso**, selecione **exigir que o dispositivo seja marcado como em conformidade**. Para vários controles, selecione **exigir todos os controles selecionados**e, em seguida, escolha **selecionar**. 

11. Escolha **Criar**.

Se seu objetivo for exigir computadores móveis *e* PCs compatíveis, não selecione plataformas. Isso impõe a conformidade de todos os dispositivos. 

## <a name="require-compliant-pcs-and-mobile-devices"></a>Exigir computadores *em conformidade e* dispositivos móveis

Para exigir a conformidade de todos os dispositivos:

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais. Após entrar com êxito, você verá o painel do Azure.

2. Escolha **Azure Active Directory** no menu à esquerda.

3. Na seção **Segurança**, escolha **Acesso condicional**.

4. Escolha **Nova política**.

5. Insira um nome para a política e escolha os **Usuários e grupos** aos quais deseja aplicar a política.

6. Escolha **Aplicativos na nuvem**.

7. Escolha **selecionar aplicativos**, selecione os aplicativos desejados na lista **aplicativos de nuvem** . Por exemplo, selecione Office 365 Exchange Online. Escolha **selecionar** e **concluir**.

8. Escolha **Conceder** na seção **Controles de acesso**.

9. Escolha **conceder acesso**, selecione **exigir que o dispositivo seja marcado como em conformidade**. Para vários controles, selecione **exigir todos os controles selecionados**e, em seguida, escolha **selecionar**. 

10. Escolha **Criar**.

Ao criar essa política, não selecione plataformas. Isso impõe dispositivos compatíveis.


## <a name="next-steps"></a>Próximas etapas

[Saiba mais sobre recomendações de política para proteger o email](secure-email-recommended-policies.md)
