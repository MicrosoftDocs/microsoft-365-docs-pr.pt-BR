---
title: Documentos seguros no Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Saiba mais sobre documentos seguros no Microsoft 365 E5 ou Microsoft 365 E5 Security.
ms.openlocfilehash: 5e91c226102d60368bf08b09ae5f0239f63599d5
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132209"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="a91b6-103">Documentos seguros no Microsoft 365 e5</span><span class="sxs-lookup"><span data-stu-id="a91b6-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="a91b6-104">Documentos seguros é um recurso no Microsoft 365 E5 ou no Microsoft 365 E5 segurança que usa a [proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para verificar documentos e arquivos abertos no [modo de exibição protegido](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span><span class="sxs-lookup"><span data-stu-id="a91b6-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a91b6-105">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="a91b6-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a91b6-106">Os documentos seguros só estão disponíveis para usuários com licenças de segurança *do microsoft 365 E5* ou *Microsoft 365 E5* .</span><span class="sxs-lookup"><span data-stu-id="a91b6-106">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="a91b6-107">Essas licenças não estão incluídas nos planos de proteção avançada contra ameaças (ATP) do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a91b6-107">These licenses are not included in Office 365 Advanced Threat Protection (ATP) plans.</span></span>

- <span data-ttu-id="a91b6-108">Abra o Centro de Conformidade e Segurança em <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="a91b6-108">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="a91b6-109">Para ir diretamente para a página de **anexos seguros de ATP** , abra <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="a91b6-109">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="a91b6-110">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a91b6-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="a91b6-111">Você precisa ter permissões para poder executar os procedimentos deste tópico.</span><span class="sxs-lookup"><span data-stu-id="a91b6-111">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="a91b6-112">Para habilitar e configurar documentos seguros, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de administrador de **segurança** .</span><span class="sxs-lookup"><span data-stu-id="a91b6-112">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="a91b6-113">Para obter mais informações sobre grupos de funções no Centro de Conformidade e Segurança, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a91b6-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="a91b6-114">Para mantê-lo protegido, documentos seguros enviam arquivos para a nuvem de [proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para análise.</span><span class="sxs-lookup"><span data-stu-id="a91b6-114">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="a91b6-115">Os detalhes sobre como o Microsoft defender ATP lida com seus dados podem ser encontrados aqui: [armazenamento e privacidade do Microsoft defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="a91b6-115">Details on how Microsoft Defender ATP handles your data can be found here: [Microsoft Defender ATP data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

- <span data-ttu-id="a91b6-116">Arquivos enviados por documentos seguros não são mantidos no defender além do tempo necessário para análise (normalmente, menos de 24 horas).</span><span class="sxs-lookup"><span data-stu-id="a91b6-116">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="a91b6-117">Usar o centro de conformidade de & de segurança para configurar documentos seguros</span><span class="sxs-lookup"><span data-stu-id="a91b6-117">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="a91b6-118">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** \> **Policy** \> e **anexos seguros de ATP**e clique em **configurações globais**.</span><span class="sxs-lookup"><span data-stu-id="a91b6-118">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="a91b6-119">Na saída **das configurações globais** exibida, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a91b6-119">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a91b6-120">**Ativar documentos seguros para clientes do Office**: mover o botão de alternância para o direito para ativar o recurso: ![ Ativar/desativar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="a91b6-120">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="a91b6-121">**Permitir que as pessoas cliquem através do modo de exibição protegido, mesmo se os documentos seguros identificarem o arquivo como mal-intencionado**: Recomendamos que você deixe esta opção desativada (Mantenha a alternação para a esquerda: ![ desativar ](../../media/scc-toggle-off.png) ).</span><span class="sxs-lookup"><span data-stu-id="a91b6-121">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="a91b6-122">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a91b6-122">When you're finished, click **Save**.</span></span>

   ![Configurações de documentos seguros depois de selecionar as configurações globais na página de anexos seguros de ATP.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="a91b6-124">Usar o PowerShell do Exchange Online para configurar documentos seguros</span><span class="sxs-lookup"><span data-stu-id="a91b6-124">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="a91b6-125">Use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a91b6-125">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="a91b6-126">O parâmetro _EnableSafeDocs_ habilita ou desabilita documentos seguros para toda a organização.</span><span class="sxs-lookup"><span data-stu-id="a91b6-126">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="a91b6-127">O parâmetro _AllowSafeDocsOpen_ permite ou impede que os usuários saiam do modo de exibição protegido (ou seja, abrir o documento) se o documento tiver sido identificado como mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="a91b6-127">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="a91b6-128">Este exemplo habilita documentos seguros para toda a organização e impede que os usuários abram documentos identificados como mal-intencionados no modo de exibição protegido.</span><span class="sxs-lookup"><span data-stu-id="a91b6-128">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="a91b6-129">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="a91b6-129">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="a91b6-130">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="a91b6-130">How do I know this worked?</span></span>

<span data-ttu-id="a91b6-131">Para verificar se você habilitou e configurou documentos seguros, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a91b6-131">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="a91b6-132">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** \> **Policy** \> de **anexos seguros de ATP**, clique em **configurações globais**e verifique o **Ativar documentos seguros para clientes do Office** e **permitir que as pessoas cliquem através do modo de exibição protegido, mesmo se os documentos seguros identificam o arquivo como configurações mal-intencionadas** .</span><span class="sxs-lookup"><span data-stu-id="a91b6-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="a91b6-133">Execute o seguinte comando no PowerShell do Exchange Online e verifique os valores de propriedade:</span><span class="sxs-lookup"><span data-stu-id="a91b6-133">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="a91b6-134">Os arquivos a seguir estão disponíveis para testar a proteção de documentos seguros.</span><span class="sxs-lookup"><span data-stu-id="a91b6-134">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="a91b6-135">Estes documentos são semelhantes aos EICAR.TXT arquivo para testar soluções antimalware e antivírus.</span><span class="sxs-lookup"><span data-stu-id="a91b6-135">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="a91b6-136">Os arquivos não são prejudiciais, mas eles disparam a proteção de documentos seguros.</span><span class="sxs-lookup"><span data-stu-id="a91b6-136">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="a91b6-137">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="a91b6-137">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="a91b6-138">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="a91b6-138">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="a91b6-139">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="a91b6-139">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
