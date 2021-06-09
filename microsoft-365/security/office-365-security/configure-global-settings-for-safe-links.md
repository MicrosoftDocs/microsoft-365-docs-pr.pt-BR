---
title: Configurar configurações globais para Cofre de links no Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a exibir e configurar configurações globais (a lista "Bloquear as URLs a seguir" e a proteção para aplicativos Office 365) para links do Cofre no Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4e77373657d3167ca8f5bafa544923ab3a2320ce
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821976"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Configurar configurações globais para Cofre links no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](defender-for-office-365.md). Se você for um usuário de residência procurando informações sobre Safelinks no Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Cofre Links é um recurso no [Microsoft Defender para](defender-for-office-365.md) Office 365 que fornece verificação de URL de mensagens de email de entrada no fluxo de emails e hora de verificação de clique em URLs e links em mensagens de email e em outros locais. Para obter mais informações, [consulte Cofre Links no Microsoft Defender para Office 365](safe-links.md).

Você configura a maioria Cofre configurações de Links em Cofre Políticas de Links. Para obter instruções, [consulte Set up Cofre Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).

No entanto, Cofre Links também usa as seguintes configurações globais que você configura fora das políticas Cofre Links por conta própria:

- A **lista Bloquear as URLs a** seguir. Essa configuração se aplica a todos os usuários incluídos em qualquer política Cofre Links ativas. Para obter mais informações, consulte ["Bloquear a lista de URLs a seguir" para Cofre Links](safe-links.md#block-the-following-urls-list-for-safe-links)
- Cofre Proteção de links para Office 365 aplicativos. Essas configurações se aplicam a todos os usuários da organização licenciados para o Defender para Office 365, independentemente de os usuários estar incluídos em políticas Cofre Links ativos ou não. Para obter mais informações, [consulte Cofre Configurações de Links para Office 365 aplicativos](safe-links.md#safe-links-settings-for-office-365-apps).

Você pode configurar as configurações globais de Links do Cofre no centro de segurança do Microsoft 365 ou no PowerShell (Exchange Online PowerShell para organizações de Microsoft 365 qualificadas com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio Exchange Online, mas com o Microsoft Defender para assinaturas de complemento do Office 365).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Não há política de links interna ou padrão Cofre, portanto, você precisa criar pelo menos uma política Cofre Links para que a lista bloquear as **URLs a** seguir seja ativa. Para obter instruções, [consulte Set up Cofre Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).

- Abra o centro de segurança em <https://security.microsoft.com>. Para ir diretamente para a página **Cofre Links,** use <https://security.microsoft.com/safelinksv2> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:
  - Para definir as configurações globais para Cofre Links, você precisa ser membro dos grupos de função Gerenciamento da Organização **ou** **Administrador de** Segurança.
  - Para acesso somente leitura às configurações globais para links Cofre, você precisa ser membro dos grupos de função Leitor **Global** ou Leitor **de** Segurança.

  Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

- Para nossos valores recomendados para as configurações globais para links Cofre, [consulte Cofre Configurações de Links.](recommended-settings-for-eop-and-office365.md#safe-links-settings)

- Permitir até 30 minutos para que uma política nova ou atualizada seja aplicada.

- [Novos recursos estão sendo adicionados continuamente ao Microsoft Defender para](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)Office 365 . À medida que novos recursos são adicionados, talvez seja necessário fazer ajustes nas políticas de links Cofre existentes.

## <a name="configure-the-block-the-following-urls-list-in-the-security-center"></a>Configurar a lista "Bloquear as URLs a seguir" no centro de segurança

A **lista Bloquear as URLs** a seguir identifica os links que sempre devem ser bloqueados Cofre verificação de links em aplicativos com suporte. Para obter mais informações, consulte ["Bloquear a lista de URLs a seguir" para Cofre Links](safe-links.md#block-the-following-urls-list-for-safe-links).

1. No centro de segurança, vá para **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras \>  \>  \>  \> **Cofre Links**.

2. Na página **Cofre Links,** clique em **Configurações globais**. Na política **Cofre Links para** sua organização que aparece, vá para a caixa Bloquear as **URLs a** seguir.

3. Configure uma ou mais entradas conforme descrito em Sintaxe de entrada para a lista ["Bloquear as URLs a seguir".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   Quando concluir, clique em **Salvar**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Configurar a lista "Bloquear as URLs a seguir" no PowerShell

Para obter detalhes sobre a sintaxe de entrada, consulte Sintaxe de entrada para a lista ["Bloquear as URLs a seguir".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

Você pode usar o cmdlet **Get-AtpPolicyForO365** para exibir entradas existentes na _propriedade BlockURLs._

- Para adicionar valores que substituirão quaisquer entradas existentes, use a seguinte sintaxe no Exchange Online PowerShell ou Proteção do Exchange Online PowerShell:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  Este exemplo adiciona as seguintes entradas à lista:

  - Bloqueie o domínio, subdomas e caminhos para fabrikam.com.
  - Bloquear a pesquisa de subdomínio, mas não o domínio pai ou outros subdomínios em tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Para adicionar ou remover valores sem afetar outras entradas existentes, use a seguinte sintaxe:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  Este exemplo adiciona uma nova entrada para adatum.com e remove a entrada para fabrikam.com.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security-center"></a>Configurar Cofre proteção de links para Office 365 aplicativos no centro de segurança

Cofre A proteção de links Office 365 aplicativos se aplica a documentos em aplicativos Office desktop, mobile e Web suportados. Para obter mais informações, [consulte Cofre Configurações de Links para Office 365 aplicativos](safe-links.md#safe-links-settings-for-office-365-apps).

1. No centro de segurança, vá para **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras \>  \>  \>  \> **Cofre Links**.

2. Na página **Cofre Links,** clique em **Configurações globais**. Na política **Cofre Links** para sua organização que aparece, configure as seguintes configurações no Configurações que se aplicam **ao** conteúdo na seção aplicativos Office 365 com suporte:

   - **Usar Cofre Links** em aplicativos Office 365 : Verifique se a alternância está à direita para habilitar Cofre Links para aplicativos Office 365 com suporte: ![ Alternar em ](../../media/scc-toggle-on.png) .

   - **Não rastreia quando** os usuários clicam em links protegidos em aplicativos Office 365 : Mova a alternância para a esquerda para controlar os cliques do usuário relacionados a URLs bloqueadas em aplicativos Office 365 suportados: ![ Alternar ](../../media/scc-toggle-off.png) para fora .

   - **Não permitir** que os usuários cliquem na URL original em aplicativos Office 365 : Verifique se a alternância está à direita para impedir que os usuários cliquem na URL bloqueada original em aplicativos Office 365 suportados: ![ Alternar ](../../media/scc-toggle-on.png) .

   Quando concluir, clique em **Salvar**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Configurar Cofre de links para Office 365 aplicativos no PowerShell

Se você preferir usar o PowerShell para configurar a proteção de links Cofre para aplicativos Office 365, use a seguinte sintaxe no Exchange Online PowerShell ou no Proteção do Exchange Online PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

Este exemplo configura as seguintes configurações para a proteção Cofre Links em Office 365 aplicativos:

- Cofre Links para Office 365 aplicativos estão ativados (não estamos usando o _parâmetro EnableSafeLinksForO365Clients_ e o valor padrão é $true).
- Cliques do usuário relacionados a URLs bloqueadas em Office 365 aplicativos são rastreados.
- Os usuários não têm permissão para clicar na URL bloqueada original em aplicativos Office 365 com suporte (não estamos usando o parâmetro _AllowClickThrough_ e o valor padrão é $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você configurou com êxito as configurações globais para links Cofre (a lista Bloquear as **SEGUINTES URLs** e as configurações de proteção de aplicativos Office 365), faça qualquer uma das seguintes etapas:

- No centro de segurança, vá até **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras Cofre Links clique em Configurações globais e verifique as configurações no sobrevoo que \>  \>  \>  \>  \> aparece. 

- No Exchange Online PowerShell ou Proteção do Exchange Online PowerShell, execute o seguinte comando e verifique as configurações:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).
