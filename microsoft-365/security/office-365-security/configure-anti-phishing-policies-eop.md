---
title: Configurar a política anti-phishing padrão no EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a modificar as configurações antifalsificação disponíveis na política anti-phishing padrão nas organizações do Office 365 com caixas de correio do Exchange Online.
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537528"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a>Configurar a política anti-phishing padrão no EOP

As organizações do Office 365 com caixas de correio do Exchange Online e do proteção autônoma do Exchange Online (EOP) sem caixas de correio do Exchange Online têm uma política anti-phishing padrão. Esta política contém um número limitado de recursos anti-falsificação habilitados por padrão. Para obter mais informações, consulte [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).

As organizações do Office 365 com caixas de correio do Exchange Online podem modificar a política anti-phishing padrão no centro de conformidade & segurança do Office 365 ou no PowerShell do Exchange Online. As organizações autônomas do EOP sem caixas de correio do Exchange Online não podem modificar a política anti-phishing padrão.

Para obter informações sobre como criar e modificar as políticas de anti-phishing mais avançadas da ATP que estão disponíveis na proteção avançada contra ameaças do Office 365, consulte [Configure ATP anti-phishing Policies in office 365](configure-atp-anti-phishing-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página **anti-phishing** , use <https://protection.office.com/antiphishing>.

- Para se conectar ao Exchange Online PowerShell, consulte [Conectar ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

- Você precisa receber permissões para executar esses procedimentos. Para adicionar, modificar e excluir políticas anti-phishing, você precisa ser membro dos grupos de função de gerenciamento da **organização** ou de **administrador de segurança** . Para acesso somente leitura às políticas anti-phishing, você precisa ser membro do grupo de função **leitor de segurança** . Para obter mais informações sobre grupos de funções no Centro de Conformidade e Segurança, confira [Permissões no Centro de conformidade e Segurança do Office 365](permissions-in-the-security-and-compliance-center.md).

- Para nossas configurações recomendadas para a política anti-phishing padrão, consulte [EOP default anti-phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).

- Aguarde até 30 minutos para que a política atualizada seja aplicada.

- Para saber mais sobre onde as políticas anti-phishing são aplicadas no pipeline de filtragem, confira [ordem e precedência de proteção de email no Office 365](how-policies-and-protections-are-combined.md).

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>Usar o centro de conformidade de & de segurança para modificar a política anti-phishing padrão

A política anti-phishing padrão é chamada de padrão do Office365 antiphish e não aparece na lista de políticas. Para modificar a política anti-phishing padrão, siga estas etapas:

1. No centro de conformidade & segurança, vá para **anti-phishing**de **política** \> de **Gerenciamento** \> de ameaças.

2. Na página **anti-phishing** , clique em **política padrão**.

3. A página **editar sua política padrão do Office365 antiphishing** é exibida. Na seção **spoof** , clique em **Editar**.

   Observe que essas configurações são idênticas às configurações de spoof que estão disponíveis nas políticas anti-phishing do ATP.

   - **Falsificação de configurações de filtro**: o valor padrão é **ativado**e recomendamos que você o deixe ligado. Para desativá-la, deslize o botão de alternância para **desativado**. Para obter mais informações, consulte [Configure spoof Intelligence in Office 365](learn-about-spoof-intelligence.md).

     > [!NOTE]
     > Você não precisa desabilitar a proteção contra falsificação se o registro MX não apontar para o Office 365; em vez disso, habilite a filtragem avançada de conectores. Para obter instruções, consulte [filtragem avançada para conectores no Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - **Habilitar o recurso de remetente não autenticado**: Adiciona um ponto de interrogação à foto do remetente se a mensagem falhar nas verificações de autenticação de email. Para obter mais informações, consulte [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings). O valor padrão é **Ativada**. Para desativá-la, deslize o botão de alternância para **desativado**.

   - **Ações**: Especifique a ação a ser executada em mensagens que falham na inteligência de spoof:

     **Se o email for enviado por alguém que não tenha permissão para falsificar seu domínio**:

     - **Mover mensagem para as pastas de lixo eletrônico dos destinatários** (esse é o valor padrão).
     - **Colocar a mensagem em quarentena**

   - **Revise suas configurações**: em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.

     - Você pode clicar em **Editar** em cada seção para saltar de volta para a página relevante.
     - Você pode ativar ou **desativar** as **seguintes** configurações diretamente nesta página:

       - **Habilitar proteção contra falsificação**
       - **Habilitar o recurso de remetente não autenticado**

   Quando tiver terminado, clique em **salvar** em qualquer página.

4. Novamente na página **editar sua política padrão do Office365 antiphishing** , revise suas configurações e clique em **fechar**.

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a>Usar o centro de conformidade de & de segurança para exibir a política anti-phishing padrão

1. No centro de conformidade & segurança e vá para **política** \> de **Gerenciamento** \> de ameaças de anti-phishing do **ATP**.

2. Clique em **política padrão** para exibir a política anti-phishing padrão.

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a>Usar o PowerShell do Exchange Online para configurar a política anti-phishing padrão

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a>Usar o PowerShell para exibir a política anti-phishing padrão

Para exibir a política anti-phishing padrão, execute o seguinte comando:

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a>Usar o PowerShell para modificar a política de anti-phishing padrão

Para modificar a política anti-phishing padrão, use a seguinte sintaxe:

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

Este exemplo altera a ação para mensagens falsificadas que falham verificações de autenticação para quarentena.

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você configurou com êxito a política anti-phishing padrão, execute uma das seguintes etapas:

- No centro de conformidade & segurança, vá para **Threat management** \> **política** \> de gerenciamento de ameaças **anti-phishing** \> clique em **política padrão** e exiba os detalhes no submenu.

- No PowerShell do Exchange Online, execute o seguinte comando e verifique as configurações:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
