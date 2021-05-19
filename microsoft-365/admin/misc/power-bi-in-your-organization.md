---
title: Power BI em sua organização
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- PWB150
ms.assetid: d7941332-8aec-4e5e-87e8-92073ce73dc5
ROBOTS: NOINDEX
description: Saiba mais Power BI e como os usuários em sua organização podem usar esse serviço de análise de negócios.
ms.openlocfilehash: 34a48ed6ee854f0057e79ba86dbd888a65b41c5e
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537422"
---
# <a name="power-bi-in-your-organization"></a>Power BI em sua organização

Esta página descreve como os usuários em sua organização podem usar o Power BI para Office 365 e como você pode controlar a forma de aquisição desse serviço por sua organização.

## <a name="what-is-power-bi"></a>O que é Power BI?

O Microsoft Power BI permite aos usuários visualizar dados, compartilhar descobertas e colaborar de maneiras novas e intuitivas. Para saber mais, veja o [site do Power BI](https://powerbi.microsoft.com/en-us/).
  
## <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>As Power BI atendem aos requisitos de conformidade nacionais, regionais e específicos do setor?

Para saber mais sobre Power BI conformidade, consulte o [Centro de Confiação da Microsoft.](https://go.microsoft.com/fwlink/?LinkId=785324)
  
## <a name="how-do-users-sign-up-for-power-bi"></a>Como os usuários podem se inscrever para obter o Power BI?

Como administrador, você pode se inscrever para obter o Power BI por meio do [site do Power BI](https://powerbi.microsoft.com/en-us/). Você também pode se inscrever por meio da página serviços de compra no Microsoft 365 de administração. Ao se inscrever no Power BI, um administrador pode atribuir licenças de assinatura a usuários que precisam ter acesso.
  
Além disso, usuários individuais em sua organização podem se inscrever no Power BI por meio do [site do Power BI](https://powerbi.microsoft.com/en-us/). Quando um usuário em sua organização se inscreve no Power BI, uma licença do Power BI é atribuída automaticamente a ele.
  
## <a name="how-do-individual-users-in-my-organization-sign-up"></a>Como usuários individuais em minha organização podem se inscrever?

Há três cenários que podem se aplicar aos usuários em sua organização:
  
### <a name="scenario-1-your-organization-already-has-an-existing-microsoft-365-environment-and-the-user-signing-up-for-power-bi-already-has-a-microsoft-365-account"></a>Cenário 1: Sua organização já tem um ambiente de Microsoft 365 existente e o usuário que se ins inscrever no Power BI já tem uma conta Microsoft 365.

Neste cenário, se um usuário já tiver uma conta do trabalho ou da escola no locatário (por exemplo, contoso.com), mas ainda não tiver o Power BI, a Microsoft simplesmente ativará o plano para essa conta e o usuário será notificado automaticamente sobre como usar o serviço do Power BI.
  
### <a name="scenario-2-your-organization-has-an-existing-microsoft-365-environment-and-the-user-signing-up-for-power-bi-doesnt-have-a-microsoft-365-account"></a>Cenário 2: sua organização tem um ambiente de Microsoft 365 existente e o usuário que se ins inscrever no Power BI não tem uma conta Microsoft 365.

Nesse cenário, o usuário tem um endereço de email no domínio da sua organização (por exemplo, contoso.com), mas ainda não tem uma conta Microsoft 365. Neste caso, o usuário pode se inscrever no Power BI e obterá uma conta automaticamente. Isso permite que o usuário acesse o serviço do Power BI. Por exemplo, se uma funcionária chamada Nancy usar seu endereço de email de trabalho (por exemplo, Nancy@contoso.com) para se inscrever, a Microsoft adicionará Automaticamente Nancy como usuário no ambiente Microsoft 365 Contoso e ativará o Power BI dessa conta.
  
### <a name="scenario-3-your-organization-does-not-have-a-microsoft-365-environment-connected-to-your-email-domain"></a>Cenário 3: Sua organização não tem um ambiente Microsoft 365 conectado ao seu domínio de email.

Não há ações administrativas que sua organização precise tirar proveito Power BI.
  
> [!IMPORTANT]
> Se sua organização tiver vários domínios de email e você preferir que todas as extensões de endereço de email sejam no mesmo locatário, antes que qualquer usuário crie seu locatário principal, adicione todos os domínios de endereço de email a esse locatário antes que qualquer usuário crie seu locatário principal. Não há mecanismo automatizado para mover usuários entre locatários após a criação. Para obter mais informações sobre esse processo, consulte If I have multiple [domains, can I](#if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to) control the tenant that users are added to? later in this article and [Add a domain to Office 365](../setup/add-domain.md) online.
  
## <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>Como isso mudará minha maneira de gerenciar identidades dos usuários em minha organização hoje?

Se a sua organização já tiver um ambiente Microsoft 365 existente e todos os usuários em sua organização têm contas Microsoft 365, o gerenciamento de identidade não mudará.
  
Se sua organização já tiver um ambiente de Microsoft 365 existente, mas nem todos os usuários em sua organização têm contas Microsoft 365, criaremos um usuário no locatário e atribuiremos licenças com base no endereço de email de estudante ou trabalho do usuário. Isso significa que o número de usuários que você gerencia a qualquer momento específico crescerá à medida que os usuários em sua organização se inscreverem no serviço.
  
Se você estiver gerenciando seu diretório local e usar o AD FS (Serviços de Federação do Active Directory), a Microsoft não adicionará usuários a seu locatário, e os usuários que tentarem ingressar no locatário receberão uma mensagem para contatar o administrador da organização.
  
Se sua organização não tiver um ambiente Microsoft 365 conectado ao seu domínio de email, não haverá nenhuma alteração na forma como você gerencia a identidade. Os usuários serão adicionados a um novo diretório de usuários somente na nuvem, e você terá a opção de assumir o controle como administrador do locatário e gerenciá-los.
  
## <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Qual é o processo para gerenciar um locatário criado pela Microsoft para meus usuários?

Se um locatário for criado pela Microsoft, você poderá solicitá-lo e gerenciá-lo seguindo estas etapas:
  
1. Ingresse no locatário [inscrevendo-se no Power BI](https://go.microsoft.com/fwlink/?LinkId=522448) com um domínio de endereço de email que corresponda ao domínio de locatário que você deseja gerenciar. Por exemplo, se a Microsoft tiver criado o locatário contoso.com, você precisará ingressar no locatário com um endereço de email que termine com @contoso.com.

1. Solicite o controle de administração, verificando a propriedade do domínio: quando estiver no locatário, você poderá se autopromover à função de administrador, verificando a propriedade de domínio. Para fazer isso, siga estas etapas:

::: moniker range="o365-worldwide"

3. Vá para [https://admin.microsoft.com](https://admin.microsoft.com).

::: moniker-end

::: moniker range="o365-germany"

3. Acesse [https://portal.office.de](https://portal.office.de).

::: moniker-end

::: moniker range="o365-21vianet"

3. Acesse [https://portal.partner.microsoftonline.cn](https://portal.partner.microsoftonline.cn).

::: moniker-end

4. Selecione o ícone do inicializador de aplicativos no canto superior esquerdo e escolha **Administrador**.

    ![Launcher de aplicativo com o aplicativo Admin realçado](../../media/4eea9dbc-591b-48be-9916-322d41c6525b.png)
  
5. Leia as instruções na página **Tornar-se o** administrador e selecione **Sim, quero ser o administrador**.

    > [!NOTE]
    >  Se essa opção não aparecer, já há um administrador no local.
  
## <a name="if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to"></a>Se eu tiver vários domínios, posso controlar o locatário ao que os usuários são adicionados?

Se você não fizer nada, será criado um locatário para cada domínio e subdomínio de email de usuários.
  
Se você quiser que todos os usuários estejam no mesmo locatário independentemente de suas extensões de endereço de email:
  
- Crie antecipadamente um locatário de destino ou use um locatário existente e adicione todos os domínios e subdomínios existentes que você deseja que sejam consolidados nesse locatário. Em seguida, todos os usuários com endereços de email terminados nesses domínios e subdomínios ingressarão automaticamente no locatário de destino quando se inscreverem.

> [!IMPORTANT]
> Não há mecanismos automatizados com suporte para mover os usuários entre locatários depois que eles forem criados. Para saber mais sobre como adicionar domínios a um único Microsoft 365 locatário, consulte [Adicionar um domínio a Office 365](../setup/add-domain.md).

> [!IMPORTANT]
> Para obter mais informações e orientações sobre como gerenciar locatários, consulte [O que é Power BI administração?](/power-bi/service-admin-administering-power-bi-in-your-organization).
  
## <a name="how-can-i-prevent-users-from-joining-my-existing-tenant"></a>Como posso impedir que os usuários insuem meu locatário existente?

Há etapas que você pode seguir como administrador para impedir que os usuários insumentem seu locatário existente. Se você impedir os usuários de ingressar no locatário, as tentativas dos usuários de entrar falharão e serão direcionadas para entrar em contato com o administrador da organização. Você não precisa repetir esse processo se já tiver desabilitado a distribuição automática de licenças antes (por exemplo, Office 365 Education para alunos, professores e funcionários).
  
As etapas exigem o uso do Windows PowerShell. Para começar a usar o Windows PowerShell, consulte o [Guia de Introdução do PowerShell](/powershell/scripting/overview).
  
Para executar as etapas a seguir, você deve instalar a versão mais recente de 64 bits do [módulo Azure Active Directory V2 PowerShell](https://www.powershellgallery.com/packages/AzureADPreview/2.0.2.5).
  
Após escolher o link, selecione **Executar** para executar o pacote de instalação.
  
**Desabilitar o ingresso automático do locatário**: use este comando do Windows PowerShell para impedir que novos usuários ingressem em um locatário gerenciado:
  
Para desabilitar o ingresso automático no locatário para novos usuários:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $false`
  
Para habilitar o ingresso automático no locatário para novos usuários:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
> [!NOTE]
> Esse bloqueio impede que novos usuários em sua organização se inssuem para Power BI. Os usuários que se inscreverem no Power BI antes de desabilitar novas inscrições para sua organização ainda manterão suas licenças. Consulte o guia Como remover Power BI para usuários que já se [inscreveram?](#how-do-i-remove-power-bi-for-users-that-already-signed-up) para obter instruções sobre como você pode remover o acesso ao Power BI para usuários que se inscreveram anteriormente no serviço.
  
## <a name="how-can-i-allow-users-to-join-my-existing-tenant"></a>Como posso permitir que os usuários participem do meu locatário existente?

Para permitir que os usuários ingressem em seu locatário, execute o comando oposto conforme descrito na pergunta acima:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
## <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>Como posso verificar o bloqueio foi ativado em meu locatário?

Use o seguinte script do PowerShell:  `Get-MsolCompanyInformation | fl allow*`
  
## <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>Como impedir que meus usuários existentes comecem a usar o Power BI?

**Desabilitar a distribuição automática de licenças:** Use esse script do Windows PowerShell para desabilitar as distribuições automáticas de licenças a usuários existentes. Você não precisa repetir esse processo se já tiver desabilitado a distribuição automática de licenças antes (por exemplo, Office 365 Education para alunos, professores e funcionários).
  
Para desabilitar as distribuições automáticas de licenças a usuários existentes:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $false`
  
Para habilitar a distribuição automática de licenças a usuários existentes:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
> [!NOTE]
> O *sinalizador AllowAdHocSubscriptions* é usado para controlar vários recursos de usuário em sua organização, incluindo a capacidade de os usuários se inscreverem no Serviço de Gerenciamento de Direitos do Azure. A alteração desse sinalizador afetará todos esses recursos.
  
## <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>Como faço para permitir que os meus usuários existentes se inscrevam no Power BI?

Para permitir que os usuários existentes se inscrevam no Power BI, execute o comando oposto conforme descrito na pergunta acima:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
## <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>Como remover o Power BI para usuários que já se inscreveram?

Se um usuário se inscreveu no Power BI, mas você não deseja mais que ele tenha acesso ao Power BI, você pode remover a licença Power BI para esse usuário.
  
::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

::: moniker-end

2. Encontre o usuário para o que você deseja remover a licença e selecione seu nome.

3. Na guia **Licenças e Aplicativos,** des limpar a **caixa** de Power BI Microsoft.

4. Selecione **Salvar alterações**.

## <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>Como posso saber se novos usuários ingressaram no meu locatário?

Os usuários que ingressarem em seu locatário como parte desse programa receberão uma licença exclusiva, que você poderá filtrar dentro no painel do usuário ativo, no painel do administrador.
  
Para criar essa nova exibição, no centro de administração, siga as etapas para em [Criar um exibição de usuário personalizado.](../add-users/create-edit-or-delete-a-custom-user-view.md#create-a-custom-user-view) Em **Licença de produto atribuída,** selecione Microsoft **Power BI**. Depois que a nova exibição tiver sido criada, você poderá ver todos os usuários em seu locatário que se registraram neste programa.
  
## <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>Devo estar preparado para outras questões?

Você poderá experimentar um aumento nas solicitações de redefinição de senha. Para obter informações sobre esse processo, consulte [Redefinir uma senha de usuário](../add-users/reset-passwords.md).
  
Você pode remover um usuário de seu locatário por meio do processo padrão no centro de administração. No entanto, se o usuário ainda tiver um endereço de email ativo de sua organização, ele poderá reingressar, a menos que você bloqueie o ingresso de todos os usuários.
  
## <a name="why-did-1-million-licenses-for-microsoft-power-bi-show-up-in-my-tenant"></a>Por que 1 milhão de licenças para a Microsoft Power BI aparecer no meu locatário?

Como uma organização qualificada, os usuários em sua organização estão qualificados para usar o serviço do Microsoft Power BI, e essas licenças representam a capacidade disponível para novos usuários do Power BI em seu locatário. Não há qualquer cobrança por essas licenças. Se você optou por permitir que os usuários se inscrevam no Power BI, eles receberão uma dessas licenças gratuitas disponíveis quando concluirem o processo de assinatura. Você também pode optar por atribuir essas licenças a usuários por meio do centro de administração.
  
## <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>Isso é gratuito? Serei cobrado por essas licenças?

Essas licenças são para a versão gratuita do Power BI. Se você estiver interessado em recursos adicionais, confira a versão do Power BI Pro.
  
## <a name="why-1-million-licenses"></a>Por que um milhão de licenças?

Escolhemos um número grande o suficiente para que a maioria das organizações tenha licenças amplas para fornecer esse benefício sem demora para seus usuários.
  
## <a name="what-if-i-need-more-than-1-million-licenses"></a>E se eu precisar de mais de um milhão de licenças?

Contate o representante de contas da Microsoft para obter mais informações, caso necessite adquirir licenças adicionais.