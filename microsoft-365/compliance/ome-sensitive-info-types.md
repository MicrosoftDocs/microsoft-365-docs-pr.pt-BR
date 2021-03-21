---
title: Criar uma política de tipo de informação confidenciais usando a Criptografia de Mensagens do Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: Saiba como criar uma política de tipo de informação confidenciais para sua organização usando a Criptografia de Mensagens do Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ad570f64122aecd245b912b1b6545a5950e838cc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927739"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>Criar uma política de tipo de informação confidenciais para sua organização usando a Criptografia de Mensagens

Você pode usar as regras de fluxo de emails do Exchange ou a Prevenção contra Perda de Dados (DLP) para criar uma política de tipo de informação confidenciais com a Criptografia de Mensagens do Office 365. Para criar uma regra de fluxo de emails do Exchange, você pode usar o Centro de administração do Exchange (EAC) ou o PowerShell.

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>Para criar a política usando regras de fluxo de emails no EAC

Entre no Centro de administração do Exchange (EAC) e acesse **Regras de fluxo de**  >  **emails.** Na página Regras, crie uma regra que aplique a Criptografia de Mensagem do Office 365. Você pode criar uma regra com base em condições como a presença de determinadas palavras-chave ou tipos de informações confidenciais na mensagem ou anexo.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>Para criar a política usando regras de fluxo de emails no PowerShell

Use uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, inicie uma sessão de Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Use os cmdlets Set-IRMConfiguration e New-TransportRule para criar a política.

## <a name="example-mail-flow-rule-created-with-powershell"></a>Regra de fluxo de emails de exemplo criada com o PowerShell

Execute os seguintes comandos no PowerShell para criar uma regra de fluxo de emails do Exchange que criptografa automaticamente emails enviados fora da sua organização com a opção somente criptografia se os emails ou seus anexos contêm os seguintes tipos de informações confidenciais:

- Número de roteamento ABA
- Número do cartão de crédito
- Número da Agência de Imposição de Drogas (DEA)
- EUA / Reino Unido. passport number
- Número da conta bancária dos EUA
- Número de identificação de contribuinte individual (ITIN) dos EUA
- Número de seguridade social dos EUA (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

Para obter mais informações, [consulte Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) e [New-TransportRule](/powershell/module/exchange/new-transportrule).

## <a name="how-recipients-access-attachments"></a>Como os destinatários acessam anexos

Depois que a Microsoft criptografa uma mensagem, os destinatários têm acesso irrestrito a anexos quando acessam e abrem seus emails criptografados.

## <a name="to-prepare-for-this-change"></a>Para se preparar para essa alteração

Talvez você queira atualizar qualquer documentação do usuário final e materiais de treinamento aplicáveis para preparar as pessoas em sua organização para essa alteração. Compartilhe esses recursos de Criptografia de Mensagens do Office 365 com seus usuários conforme apropriado:

- [Enviar, exibir e responder a mensagens criptografadas no Outlook para PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Vídeo do Microsoft 365 Essentials: Criptografia de Mensagens do Office](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>Exibir essas alterações no log de auditoria

O Microsoft 365 audita essa atividade e a disponibiliza aos administradores. A operação é 'New-TransportRule' e um trecho de uma entrada de auditoria de exemplo da Pesquisa de Log de Auditoria no Centro de Conformidade e Segurança & está abaixo:

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>Para desabilitar ou personalizar a política de tipos de informações confidenciais

Depois de criar a regra de fluxo [](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) de emails do Exchange, você pode desabilitar ou editar a regra indo para Regras de fluxo de email no Centro de administração do Exchange (EAC) e desabilitar a regra " Criptografar emails confidenciais de saída (regra de caixa de   >   *correio)*".