---
title: Definir configurações globais para configurações de Links seguros no Defender para Office 365
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
description: Os administradores podem aprender a exibir e definir configurações globais (a lista "Bloquear as URLs a seguir" e a proteção para aplicativos do Office 365) para Links Seguros no Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d52a4dc5ed35ec73c1410d6428a581b098bf2c52
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287456"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Definir configurações globais para Links Seguros no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](office-365-atp.md). Se você for um usuário de residência procurando informações sobre Safelinks no Outlook, confira [Segurança avançada Outlook.com](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

O Recurso Links Seguros é um recurso do [Microsoft Defender para Office 365](office-365-atp.md) que fornece verificação de URL de mensagens de email de entrada no fluxo de emails e o tempo de verificação de clique de URLs e links em mensagens de email e em outros locais. Para obter mais informações, consulte [Links seguros no Microsoft Defender para Office 365.](atp-safe-links.md)

Você define a maioria das configurações de Links seguros nas políticas de Links seguros. Para obter instruções, consulte [Configurar políticas de Links seguros no Microsoft Defender para Office 365.](set-up-atp-safe-links-policies.md)

Porém, os Links Seguros também usam configurações globais que se aplicam a todos os usuários incluídos em quaisquer políticas de Links seguros ativas. Estas áreas de configurações globais:

- A **lista Bloquear as URLs a** seguir. Para obter mais informações, [consulte a lista "Bloquear as URLs a seguir" para Links seguros](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- Proteção de Links Seguros para aplicativos do Office 365. Para obter mais informações, consulte [Configurações de Links seguros para aplicativos do Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)

Você pode definir as configurações globais de & Links seguros no Centro de Conformidade e Segurança ou no PowerShell (PowerShell do Exchange Online para organizações qualificadas do Microsoft 365 com caixas de correio no Exchange Online; PowerShell do EOP autônomo para organizações sem caixas de correio do Exchange Online, mas com assinaturas de complemento do Microsoft Defender para Office 365).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Os recursos fornecidos pelas configurações globais de Links seguros são aplicados apenas aos usuários incluídos nas políticas ativas de Links seguros. Não há uma política de Links seguros interna ou padrão, portanto, você precisa criar pelo menos uma política de Links seguros para que essas configurações globais sejam ativas. Para obter instruções, consulte [Configurar políticas de Links seguros no Microsoft Defender para Office 365.](set-up-atp-safe-links-policies.md)

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página **Links seguros,** use <https://protection.office.com/safelinksv2> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos deste artigo:
  - Para definir as configurações globais para Links Seguros,  você precisa ser membro dos grupos de função Gerenciamento da Organização ou **Administrador de** Segurança.
  - Para acesso somente leitura às configurações globais de Links Seguros, você precisa ser membro dos grupos de funções Leitor **Global** ou **Leitor de** Segurança.

  Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

- Para nossos valores recomendados para as configurações globais de Links seguros, consulte [configurações de Links seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)

- Permita até 30 minutos para que uma política nova ou atualizada seja aplicada.

- [Novos recursos estão sendo adicionados continuamente ao Microsoft Defender para Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365) À medida que novos recursos são adicionados, talvez seja necessário fazer ajustes nas políticas de Links seguros existentes.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>Configure a lista "Bloquear as URLs a seguir" no Centro de Conformidade e & Segurança

A **lista bloquear as URLs a** seguir identifica os links que sempre devem ser bloqueados pela verificação de Links seguros em aplicativos suportados. Para obter mais informações, [consulte a lista "Bloquear as URLs a seguir" para Links seguros.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)

1. No Centro de Conformidade & Segurança,  vá para Links Seguros da ATP da Política de Gerenciamento de Ameaças e clique em \>  \>  **Configurações Globais.**

2. Na política **de Links seguros para sua organização,** vá para a caixa Bloquear as **URLs a** seguir.

3. Configure uma ou mais entradas conforme descrito na sintaxe entry para a lista ["Bloquear as URLs a seguir".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   Quando concluir, clique em **Salvar**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Configurar a lista "Bloquear as URLs a seguir" no PowerShell

Para obter detalhes sobre a sintaxe de entrada, consulte a sintaxe de entrada para [a lista "Bloquear as URLs a seguir".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

Você pode usar o cmdlet **Get-AtpPolicyForO365** para exibir entradas existentes na _propriedade BlockURLs._

- Para adicionar valores que substituirão quaisquer entradas existentes, use a seguinte sintaxe no PowerShell do Exchange Online ou no PowerShell da Proteção do Exchange Online:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  Este exemplo adiciona as seguintes entradas à lista:

  - Bloqueie o domínio, sub-domínios e caminhos para fabrikam.com.
  - Bloquear a pesquisa de subdomínio, mas não o domínio pai ou outros subdomínios no tailspintoys.com

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

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Configurar a proteção de Links seguros para aplicativos do Office 365 no Centro de Conformidade & Segurança

A proteção de Links Seguros para aplicativos do Office 365 se aplica a documentos em aplicativos da Web, móveis e da área de trabalho do Office com suporte. Para obter mais informações, consulte [Configurações de Links seguros para aplicativos do Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)

1. No Centro de Conformidade & Segurança,  vá para Links Seguros da ATP da Política de Gerenciamento de Ameaças e clique em \>  \>  **Configurações Globais.**

2. Na política **de Links seguros para sua** organização, desdossa as seguintes configurações nas Configurações que se aplicam ao conteúdo, exceto à seção de **email:**

   - **Aplicativos do Office 365:** verifique se a alternância está à direita para habilitar o recurso Links Seguros para aplicativos com suporte do Office 365: ![ Ativar/ativar. ](../../media/scc-toggle-on.png)

   - **Não rastreia quando** os usuários clicam em Links Seguros: mova o botão de alternância para a esquerda para controlar os cliques do usuário relacionados a URLs bloqueadas nos aplicativos do Office 365 com suporte: ![ ](../../media/scc-toggle-off.png) Alternar.

   - Não permitir que os usuários cliquem em Links Seguros para a **URL original:** verifique se o botão de alternância está à direita para impedir que os usuários cliquem até a URL bloqueada original nos aplicativos do Office 365 com suporte: Ligar/ ![ ](../../media/scc-toggle-on.png)

   Quando concluir, clique em **Salvar**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Configurar a proteção de Links Seguros para aplicativos do Office 365 no PowerShell

Se você preferir usar o PowerShell para configurar a proteção de Links seguros para aplicativos do Office 365, use a seguinte sintaxe no PowerShell do Exchange Online ou no PowerShell da Proteção do Exchange Online:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

Este exemplo define as seguintes configurações para a proteção de Links seguros em aplicativos do Office 365:

- O recurso Links Seguros para aplicativos do Office 365 está ativado (não estamos usando o parâmetro _EnableSafeLinksForO365Clients_ e o valor padrão é $true).
- Cliques do usuário relacionados a URLs bloqueadas em aplicativos do Office 365 suportados são rastreados.
- Os usuários não têm permissão para clicar na URL bloqueada original nos aplicativos do Office 365 com suporte (não estamos usando o parâmetro _AllowClickThrough_ e o valor padrão é $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você definiu com êxito as configurações globais para Links Seguros (a lista bloquear as seguintes **URLs** e as configurações de proteção de aplicativos do Office 365), faça uma das seguintes etapas:

- No Centro de Conformidade & Segurança,  vá para Links Seguros da ATP da Política de Gerenciamento de Ameaças, clique em Configurações Globais e verifique as configurações no menu desdopado \>  \> que aparece. 

- No PowerShell do Exchange Online ou no PowerShell da Proteção do Exchange Online, execute o seguinte comando e verifique as configurações:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).
