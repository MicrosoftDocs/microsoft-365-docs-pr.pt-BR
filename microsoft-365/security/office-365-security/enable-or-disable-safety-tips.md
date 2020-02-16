---
title: Ativar ou desativar as dicas de segurança no Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
ms.collection:
- M365-security-compliance
description: Informa aos administradores do Office 365 e do EOP como habilitar e desabilitar dicas de segurança em mensagens de email.
ms.openlocfilehash: ae8a3bc9811aa54b0c5ae4cc8a0e2eb9aa80aef0
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42086233"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a>Ativar ou desativar as dicas de segurança no Office 365

O proteção do Exchange Online (EOP) adiciona, ou carimbos, uma dica de segurança a mensagens de email que ele fornece. Essas dicas de segurança fornecem aos destinatários uma forma rápida e Visual de determinar se uma mensagem é de um remetente seguro e verificado, se a mensagem tiver sido marcada como spam pelo Office 365, se a mensagem contiver algo suspeito, como um golpe de phishing, ou se imagens externas tiverem foi bloqueado. Os administradores do Office 365 e do EOP-autônomo podem editar uma configuração de política de spam para habilitar ou desabilitar que as dicas de segurança sejam exibidas no email no Outlook e em outros clientes de email de área de trabalho.

O Office 365 permite dicas de segurança por padrão para sua organização e recomendamos que você as deixe habilitadas para ajudar a combater spam e ataques de phishing. Não é possível desabilitar dicas de segurança para o Outlook na Web.

Para ver exemplos e saber mais sobre as informações exibidas em dicas de segurança, consulte [dicas de segurança em mensagens de email no Office 365.](safety-tips-in-office-365.md)

Neste tópico:

- [Para habilitar ou desabilitar dicas de segurança usando o centro de conformidade &amp; de segurança do Office 365](enable-or-disable-safety-tips.md#SandCCsafetytip)

- [Para habilitar ou desabilitar dicas de segurança usando o PowerShell](enable-or-disable-safety-tips.md#pshellsafetytip)

## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a>Para habilitar ou desabilitar dicas de segurança usando o centro de conformidade &amp; de segurança do Office 365
<a name="SandCCsafetytip"> </a>

1. Acesse [https://protection.office.com](https://protection.office.com).

2. Entre no Office 365 com uma conta corporativa ou de estudante.

3. Escolha **** \> **política**de gerenciamento de ameaças.

4. Na página **política** , escolha **anti-spam**.

    ![Esta captura de tela mostra como acessar a página configurações antispam no centro de conformidade de &amp; segurança.](../../media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)

5. Na página **configurações antispam,** escolha a guia **personalizado** .

    ![Esta captura de tela mostra a localização da guia personalizada na página configurações antispam no centro de conformidade de &amp; segurança.](../../media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)

6. Se necessário, escolha a opção **configurações personalizadas** para ativar as configurações personalizadas. Se a opção configurações personalizadas estiver definida como **desativada**, você não poderá modificar as políticas de filtro de spam.

    ![Esta captura de tela mostra as configurações de política de filtro antispam personalizadas desativadas.](../../media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)

7. Expanda a política de spam que você deseja modificar e, em seguida, escolha **Editar política**. Por exemplo, escolha a seta para baixo ao lado de **política padrão de filtro de spam**. Ou, se quiser, você pode criar uma nova política escolhendo **Adicionar uma política**.

8. Expanda **spam e ações em massa** .

9. Para habilitar as dicas de segurança, em **dicas de segurança**, marque a caixa **de seleção ao** . Para desabilitar as dicas de segurança, desmarque a caixa **de seleção ao** .

10. Selecione **Salvar**.

## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a>Para habilitar ou desabilitar dicas de segurança usando o PowerShell
<a name="pshellsafetytip"> </a>

Os administradores podem usar o PowerShell do Exchange Online para habilitar ou desabilitar dicas de segurança. Use o cmdlet Set-HostedContentFilterPolicy para habilitar ou desabilitar dicas de segurança em uma política de filtro de spam.

1. Conecte-se ao PowerShell do Exchange Online. Para saber mais, confira [conectar-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Execute o cmdlet Set-HostedContentFilterPolicy para habilitar ou desabilitar dicas de segurança:

   ```powershell
   Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true | $false>
   ```

Onde:

- *nome da política* é o nome da política que você deseja modificar, por exemplo, **padrão**.

- `$true`permite dicas de segurança para a política de filtro de spam.

- `$false`desabilita as dicas de segurança da política de filtro de spam.

Por exemplo, para desabilitar as dicas de segurança para a política de filtro de spam padrão, execute o seguinte comando:

```powershell
Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
```

Para obter mais informações sobre esse cmdlet, consulte [set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy).

## <a name="still-need-help"></a>Ainda precisa de ajuda?
<a name="pshellsafetytip"> </a>

Se você desabilitou as dicas de segurança, mas ainda as está vendo nas mensagens de email, Confira estas coisas:

- Não é possível desabilitar dicas de segurança para o Outlook na Web. Tente exibir o mesmo email em outro cliente, como o Outlook.

- As dicas de segurança são ativadas por padrão para todos os usuários que usam o EOP, incluindo todos os que têm o Office 365. Para desabilitar as dicas de segurança da exibição no email, você deve desabilitá-las usando uma política de filtro de spam, conforme descrito neste tópico. Depois de configurar a política, verifique se ela está habilitada. Para obter informações sobre como habilitar políticas de filtro de spam, consulte [Configure Your spam filter Policies](configure-your-spam-filter-policies.md).

Para obter mais maneiras de combater spam e phishing, consulte [Office 365 email anti-spam Protection](anti-spam-protection.md).
