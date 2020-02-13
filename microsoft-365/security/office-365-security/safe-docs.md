---
title: Documentos seguros no Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Saiba mais sobre documentos seguros no Office 365 ATP.
ms.openlocfilehash: db73fc152a5a580a28bf6d8424ebc2a139cf3303
ms.sourcegitcommit: c2a36b16e354e20db5fd6275175ca856eae55bfc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "41960337"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a><span data-ttu-id="65091-103">Documentos seguros no Office 365 proteção avançada contra ameaças</span><span class="sxs-lookup"><span data-stu-id="65091-103">Safe Documents in Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="65091-104">Documentos seguros é um recurso da proteção avançada contra ameaças do Office 365 (ATP) que usa a [proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para verificar documentos e arquivos abertos no [modo de exibição protegido](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span><span class="sxs-lookup"><span data-stu-id="65091-104">Safe Documents is a feature in Office 365 Advanced Threat Protection (ATP) that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="65091-105">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="65091-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="65091-106">Para se conectar ao Exchange Online PowerShell, confira [Conectar ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="65091-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="65091-107">Para se conectar ao PowerShell do Exchange Online Protection, confira [conectar-se ao PowerShell do Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="65091-107">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="65091-108">Você precisa ter permissões para poder executar os procedimentos deste tópico.</span><span class="sxs-lookup"><span data-stu-id="65091-108">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="65091-109">Para habilitar e configurar documentos seguros, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de administrador de **segurança** .</span><span class="sxs-lookup"><span data-stu-id="65091-109">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="65091-110">Para obter mais informações sobre grupos de função no centro de conformidade & segurança, consulte [permissões no centro de conformidade & segurança do Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="65091-110">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-office-365-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="65091-111">Usar o centro de conformidade & segurança do Office 365 para configurar documentos seguros</span><span class="sxs-lookup"><span data-stu-id="65091-111">Use the Office 365 Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="65091-112">Abra o centro de conformidade & segurança do Office <https://protection.office.com>365 em.</span><span class="sxs-lookup"><span data-stu-id="65091-112">Open the Office 365 Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="65091-113">Vá para \*\*\*\* \> **política** \> de gerenciamento de ameaças **anexos seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="65091-113">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="65091-114">Na seção **ajudar as pessoas a permanecerem seguras ao confiar em um arquivo para abrir fora do modo de exibição protegido em aplicativos do Office** , configure qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="65091-114">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="65091-115">**Ative documentos seguros para clientes do Office (os arquivos também serão enviados para a nuvem da Microsoft para análises profundas)**</span><span class="sxs-lookup"><span data-stu-id="65091-115">**Turn on Safe Documents for Office clients (Files will also be sent to Microsoft Cloud for deep analyses)**</span></span>

   - <span data-ttu-id="65091-116">**Permitir que as pessoas cliquem no modo de exibição protegido, mesmo se os documentos seguros identificam o arquivo como mal-intencionado**: Recomendamos que você não habilite essa opção.</span><span class="sxs-lookup"><span data-stu-id="65091-116">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="65091-117">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="65091-117">When you're finished, click **Save**.</span></span>

![Página de anexos seguros de ATP](../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-safe-documents"></a><span data-ttu-id="65091-119">Usar o PowerShell do Exchange Online ou do Exchange Online Protection para configurar documentos seguros</span><span class="sxs-lookup"><span data-stu-id="65091-119">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="65091-120">Use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="65091-120">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- <span data-ttu-id="65091-121">O parâmetro _EnableSafeDocs_ habilita ou desabilita documentos seguros para toda a organização.</span><span class="sxs-lookup"><span data-stu-id="65091-121">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="65091-122">O parâmetro _AllowSafeDocsOpen_ permite ou impede que os usuários saiam do modo de exibição protegido (ou seja, abrir o documento) se o documento tiver sido identificado como mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="65091-122">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="65091-123">Este exemplo habilita documentos seguros para toda a organização e impede que os usuários abram documentos identificados como mal-intencionados no modo de exibição protegido.</span><span class="sxs-lookup"><span data-stu-id="65091-123">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="65091-124">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="65091-124">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="65091-125">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="65091-125">How do I know this worked?</span></span>

<span data-ttu-id="65091-126">Para verificar se você habilitou e configurou documentos seguros, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="65091-126">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="65091-127">No centro de conformidade & segurança, vá para a **política** \> de **Gerenciamento** \> de ameaças de **anexos seguros de ATP**e verifique as seleções na seção **ajuda para manter a segurança ao confiar em um arquivo para abrir fora do modo de exibição protegido em aplicativos do Office** .</span><span class="sxs-lookup"><span data-stu-id="65091-127">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="65091-128">Execute o seguinte comando no PowerShell do Exchange Online e verifique os valores de propriedade:</span><span class="sxs-lookup"><span data-stu-id="65091-128">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
