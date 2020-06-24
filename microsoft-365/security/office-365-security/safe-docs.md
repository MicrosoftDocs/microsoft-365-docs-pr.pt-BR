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
description: Saiba mais sobre documentos seguros no Microsoft 365 E5 ou Microsoft 365 E5 Security.
ms.openlocfilehash: c574e28a01dc961d898638184afe9ece90e31133
ms.sourcegitcommit: aa7f7350d1342ff9713bb840b2cc96d1a4234ef4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2020
ms.locfileid: "44835341"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="a8a75-103">Documentos seguros no Microsoft 365 e5</span><span class="sxs-lookup"><span data-stu-id="a8a75-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="a8a75-104">Documentos seguros é um recurso no Microsoft 365 E5 ou no Microsoft 365 E5 segurança que usa a [proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para verificar documentos e arquivos abertos no [modo de exibição protegido](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span><span class="sxs-lookup"><span data-stu-id="a8a75-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a8a75-105">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="a8a75-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a8a75-106">Agora, os documentos seguros estão disponíveis para usuários com o Office versão 2004 (12730. x) ou mais.</span><span class="sxs-lookup"><span data-stu-id="a8a75-106">Safe Documents is now generally available to users with Office Version 2004 (12730.x) or greater!</span></span> <span data-ttu-id="a8a75-107">Esse recurso está desativado por padrão e deverá ser habilitado pelo administrador de segurança.</span><span class="sxs-lookup"><span data-stu-id="a8a75-107">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="a8a75-108">Este recurso está disponível apenas para usuários com a licença de segurança do *microsoft 365 E5* ou *do Microsoft 365 E5* (não incluída nos planos ATP do Office 365).</span><span class="sxs-lookup"><span data-stu-id="a8a75-108">This feature is only available to users with the *Microsoft 365 E5* or *Microsoft 365 E5 Security* license (not included in Office 365 ATP plans).</span></span>

- <span data-ttu-id="a8a75-109">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a8a75-109">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a8a75-110">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="a8a75-110">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a8a75-111">Você precisa ter permissões para poder executar os procedimentos deste tópico.</span><span class="sxs-lookup"><span data-stu-id="a8a75-111">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="a8a75-112">Para habilitar e configurar documentos seguros, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de administrador de **segurança** .</span><span class="sxs-lookup"><span data-stu-id="a8a75-112">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="a8a75-113">Para obter mais informações sobre grupos de funções no Centro de Conformidade e Segurança, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a8a75-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="a8a75-114">Como a Microsoft lida com seus dados?</span><span class="sxs-lookup"><span data-stu-id="a8a75-114">How does Microsoft handle your data?</span></span>

<span data-ttu-id="a8a75-115">Para mantê-lo protegido, documentos seguros enviam arquivos para a nuvem de [proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para análise.</span><span class="sxs-lookup"><span data-stu-id="a8a75-115">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span>

- <span data-ttu-id="a8a75-116">Detalhes sobre como a proteção avançada contra ameaças do Microsoft defender lida com seus dados pode ser encontrada [aqui](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="a8a75-116">Details on how Microsoft Defender Advanced Threat Protection handles your data can be found [here](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span></span>
- <span data-ttu-id="a8a75-117">Além das diretrizes acima, os arquivos enviados por documentos seguros não são mantidos no defender além do tempo necessário para análise, que normalmente é menor que 24 horas</span><span class="sxs-lookup"><span data-stu-id="a8a75-117">In addition to the guidelines above, files sent by Safe Documents are not retained in Defender beyond the time needed for analysis, which is typically less than 24 hours</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="a8a75-118">Usar o centro de conformidade de & de segurança para configurar documentos seguros</span><span class="sxs-lookup"><span data-stu-id="a8a75-118">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="a8a75-119">Abra o centro de conformidade & segurança em <https://protection.office.com> .</span><span class="sxs-lookup"><span data-stu-id="a8a75-119">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="a8a75-120">Vá para política de **Gerenciamento de ameaças** \> **Policy** \> **anexos seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="a8a75-120">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="a8a75-121">Na seção **ajudar as pessoas a permanecerem seguras ao confiar em um arquivo para abrir fora do modo de exibição protegido em aplicativos do Office** , configure qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a8a75-121">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="a8a75-122">**Ativar documentos seguros para clientes do Office**</span><span class="sxs-lookup"><span data-stu-id="a8a75-122">**Turn on Safe Documents for Office clients**</span></span>

   - <span data-ttu-id="a8a75-123">**Permitir que as pessoas cliquem no modo de exibição protegido, mesmo se os documentos seguros identificam o arquivo como mal-intencionado**: Recomendamos que você não habilite essa opção.</span><span class="sxs-lookup"><span data-stu-id="a8a75-123">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="a8a75-124">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a8a75-124">When you're finished, click **Save**.</span></span>

![Página de anexos seguros de ATP](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a><span data-ttu-id="a8a75-126">Usar o PowerShell do Exchange Online ou o PowerShell do EOP para configurar documentos seguros</span><span class="sxs-lookup"><span data-stu-id="a8a75-126">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="a8a75-127">Use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a8a75-127">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="a8a75-128">O parâmetro _EnableSafeDocs_ habilita ou desabilita documentos seguros para toda a organização.</span><span class="sxs-lookup"><span data-stu-id="a8a75-128">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="a8a75-129">O parâmetro _AllowSafeDocsOpen_ permite ou impede que os usuários saiam do modo de exibição protegido (ou seja, abrir o documento) se o documento tiver sido identificado como mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="a8a75-129">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="a8a75-130">Este exemplo habilita documentos seguros para toda a organização e impede que os usuários abram documentos identificados como mal-intencionados no modo de exibição protegido.</span><span class="sxs-lookup"><span data-stu-id="a8a75-130">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="a8a75-131">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="a8a75-131">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="a8a75-132">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="a8a75-132">How do I know this worked?</span></span>

<span data-ttu-id="a8a75-133">Para verificar se você habilitou e configurou documentos seguros, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a8a75-133">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="a8a75-134">No centro de conformidade & segurança, vá para a política de **Gerenciamento de ameaças** de \> **Policy** \> **anexos seguros de ATP**e verifique as seleções na seção **ajuda para manter a segurança ao confiar em um arquivo para abrir fora do modo de exibição protegido em aplicativos do Office** .</span><span class="sxs-lookup"><span data-stu-id="a8a75-134">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="a8a75-135">Execute o seguinte comando no PowerShell do Exchange Online e verifique os valores de propriedade:</span><span class="sxs-lookup"><span data-stu-id="a8a75-135">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
