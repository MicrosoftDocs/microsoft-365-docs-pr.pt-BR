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
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a><span data-ttu-id="cb9d1-103">Criar uma política de tipo de informação confidenciais para sua organização usando a Criptografia de Mensagens</span><span class="sxs-lookup"><span data-stu-id="cb9d1-103">Create a sensitive information type policy for your organization using Message Encryption</span></span>

<span data-ttu-id="cb9d1-104">Você pode usar as regras de fluxo de emails do Exchange ou a Prevenção contra Perda de Dados (DLP) para criar uma política de tipo de informação confidenciais com a Criptografia de Mensagens do Office 365.</span><span class="sxs-lookup"><span data-stu-id="cb9d1-104">You can use either Exchange mail flow rules or Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="cb9d1-105">Para criar uma regra de fluxo de emails do Exchange, você pode usar o Centro de administração do Exchange (EAC) ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb9d1-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="cb9d1-106">Para criar a política usando regras de fluxo de emails no EAC</span><span class="sxs-lookup"><span data-stu-id="cb9d1-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="cb9d1-107">Entre no Centro de administração do Exchange (EAC) e acesse **Regras de fluxo de**  >  **emails.**</span><span class="sxs-lookup"><span data-stu-id="cb9d1-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="cb9d1-108">Na página Regras, crie uma regra que aplique a Criptografia de Mensagem do Office 365.</span><span class="sxs-lookup"><span data-stu-id="cb9d1-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="cb9d1-109">Você pode criar uma regra com base em condições como a presença de determinadas palavras-chave ou tipos de informações confidenciais na mensagem ou anexo.</span><span class="sxs-lookup"><span data-stu-id="cb9d1-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="cb9d1-110">Para criar a política usando regras de fluxo de emails no PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb9d1-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="cb9d1-111">Use uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, inicie uma sessão de Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cb9d1-111">Use a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="cb9d1-112">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="cb9d1-112">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="cb9d1-113">Use os cmdlets Set-IRMConfiguration e New-TransportRule para criar a política.</span><span class="sxs-lookup"><span data-stu-id="cb9d1-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

## <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="cb9d1-114">Regra de fluxo de emails de exemplo criada com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb9d1-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="cb9d1-115">Execute os seguintes comandos no PowerShell para criar uma regra de fluxo de emails do Exchange que criptografa automaticamente emails enviados fora da sua organização com a opção somente criptografia se os emails ou seus anexos contêm os seguintes tipos de informações confidenciais:</span><span class="sxs-lookup"><span data-stu-id="cb9d1-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the encrypt-only option if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="cb9d1-116">Número de roteamento ABA</span><span class="sxs-lookup"><span data-stu-id="cb9d1-116">ABA routing number</span></span>
- <span data-ttu-id="cb9d1-117">Número do cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="cb9d1-117">Credit card Number</span></span>
- <span data-ttu-id="cb9d1-118">Número da Agência de Imposição de Drogas (DEA)</span><span class="sxs-lookup"><span data-stu-id="cb9d1-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="cb9d1-119">EUA / Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="cb9d1-119">U.S. / U.K.</span></span> <span data-ttu-id="cb9d1-120">passport number</span><span class="sxs-lookup"><span data-stu-id="cb9d1-120">passport number</span></span>
- <span data-ttu-id="cb9d1-121">Número da conta bancária dos EUA</span><span class="sxs-lookup"><span data-stu-id="cb9d1-121">U.S. bank account number</span></span>
- <span data-ttu-id="cb9d1-122">Número de identificação de contribuinte individual (ITIN) dos EUA</span><span class="sxs-lookup"><span data-stu-id="cb9d1-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="cb9d1-123">Número de seguridade social dos EUA (SSN)</span><span class="sxs-lookup"><span data-stu-id="cb9d1-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

<span data-ttu-id="cb9d1-124">Para obter mais informações, [consulte Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) e [New-TransportRule](/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="cb9d1-124">For more information, see [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) and [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="cb9d1-125">Como os destinatários acessam anexos</span><span class="sxs-lookup"><span data-stu-id="cb9d1-125">How recipients access attachments</span></span>

<span data-ttu-id="cb9d1-126">Depois que a Microsoft criptografa uma mensagem, os destinatários têm acesso irrestrito a anexos quando acessam e abrem seus emails criptografados.</span><span class="sxs-lookup"><span data-stu-id="cb9d1-126">After Microsoft encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="cb9d1-127">Para se preparar para essa alteração</span><span class="sxs-lookup"><span data-stu-id="cb9d1-127">To prepare for this change</span></span>

<span data-ttu-id="cb9d1-128">Talvez você queira atualizar qualquer documentação do usuário final e materiais de treinamento aplicáveis para preparar as pessoas em sua organização para essa alteração.</span><span class="sxs-lookup"><span data-stu-id="cb9d1-128">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="cb9d1-129">Compartilhe esses recursos de Criptografia de Mensagens do Office 365 com seus usuários conforme apropriado:</span><span class="sxs-lookup"><span data-stu-id="cb9d1-129">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="cb9d1-130">Enviar, exibir e responder a mensagens criptografadas no Outlook para PC</span><span class="sxs-lookup"><span data-stu-id="cb9d1-130">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="cb9d1-131">Vídeo do Microsoft 365 Essentials: Criptografia de Mensagens do Office</span><span class="sxs-lookup"><span data-stu-id="cb9d1-131">Microsoft 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="cb9d1-132">Exibir essas alterações no log de auditoria</span><span class="sxs-lookup"><span data-stu-id="cb9d1-132">View these changes in the audit log</span></span>

<span data-ttu-id="cb9d1-133">O Microsoft 365 audita essa atividade e a disponibiliza aos administradores.</span><span class="sxs-lookup"><span data-stu-id="cb9d1-133">Microsoft 365 audits this activity and makes it available to administrators.</span></span> <span data-ttu-id="cb9d1-134">A operação é 'New-TransportRule' e um trecho de uma entrada de auditoria de exemplo da Pesquisa de Log de Auditoria no Centro de Conformidade e Segurança & está abaixo:</span><span class="sxs-lookup"><span data-stu-id="cb9d1-134">The operation is 'New-TransportRule' and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="cb9d1-135">Para desabilitar ou personalizar a política de tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="cb9d1-135">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="cb9d1-136">Depois de criar a regra de fluxo [](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) de emails do Exchange, você pode desabilitar ou editar a regra indo para Regras de fluxo de email no Centro de administração do Exchange (EAC) e desabilitar a regra " Criptografar emails confidenciais de saída (regra de caixa de   >   *correio)*".</span><span class="sxs-lookup"><span data-stu-id="cb9d1-136">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule "*Encrypt outbound sensitive emails (out of box rule)*".</span></span>