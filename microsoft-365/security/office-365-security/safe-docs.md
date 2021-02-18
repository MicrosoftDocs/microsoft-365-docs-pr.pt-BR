---
title: Documentos Seguros no Microsoft Defender para Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Saiba mais sobre Documentos Seguros no Microsoft 365 E5 ou no Microsoft 365 E5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a3f4ed3535c7e53774b9b567b50f7c06e99cef9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288580"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="509a0-103">Documentos Seguros no Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="509a0-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="509a0-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="509a0-104">**Applies to**</span></span>
- [<span data-ttu-id="509a0-105">Plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="509a0-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="509a0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="509a0-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="509a0-107">Documentos Seguros é um recurso do Microsoft 365 E5 ou do Microsoft 365 E5 Security que usa o [Microsoft Defender para](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) Ponto de Extremidade para verificar documentos e arquivos abertos no Exibição [Protegido.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)</span><span class="sxs-lookup"><span data-stu-id="509a0-107">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="509a0-108">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="509a0-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="509a0-109">Os Documentos Seguros estão disponíveis apenas para usuários com licenças de Segurança do *Microsoft 365 E5* ou *Microsoft 365 E5.*</span><span class="sxs-lookup"><span data-stu-id="509a0-109">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="509a0-110">Essas licenças não estão incluídas no Microsoft Defender para planos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="509a0-110">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="509a0-111">Os Documentos Seguros são suportados no Microsoft 365 Apps para empresas (anteriormente conhecido como Office 365 ProPlus) versão 2004 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="509a0-111">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="509a0-112">Abra o Centro de Conformidade e Segurança em <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="509a0-112">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="509a0-113">Para ir diretamente para a página Anexos Seguros da **ATP,** <https://protection.office.com/safeattachmentv2> abra.</span><span class="sxs-lookup"><span data-stu-id="509a0-113">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="509a0-114">Para se conectar ao Windows PowerShell do Exchange Online, confira [Conectar ao Windows PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="509a0-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="509a0-115">Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="509a0-115">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="509a0-116">Para definir as configurações de Documentos Seguros,  você precisa ser membro dos grupos de função Gerenciamento da Organização ou **Administrador de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="509a0-116">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="509a0-117">Para acesso somente leitura às configurações de Documentos Seguros, você precisa ser membro dos grupos de funções Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="509a0-117">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="509a0-118">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="509a0-118">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="509a0-119">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="509a0-119">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="509a0-120">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="509a0-120">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="509a0-121">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="509a0-121">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="509a0-122">Como a Microsoft lida com seus dados?</span><span class="sxs-lookup"><span data-stu-id="509a0-122">How does Microsoft handle your data?</span></span>

<span data-ttu-id="509a0-123">Para mantê-lo protegido, Os Documentos Seguros enviam arquivos para a [nuvem do Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para análise.</span><span class="sxs-lookup"><span data-stu-id="509a0-123">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="509a0-124">Detalhes sobre como o Microsoft Defender para Ponto de Extremidade lida com seus dados podem ser encontrados aqui: Privacidade e armazenamento de dados do Microsoft Defender para Pontos [de Extremidade.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="509a0-124">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="509a0-125">Os arquivos enviados por Documentos Seguros não são mantidos no Defender além do tempo necessário para análise (normalmente, menos de 24 horas).</span><span class="sxs-lookup"><span data-stu-id="509a0-125">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="509a0-126">Usar o Centro de Conformidade & Segurança para configurar Documentos Seguros</span><span class="sxs-lookup"><span data-stu-id="509a0-126">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="509a0-127">No Centro de Conformidade & Segurança, vá para Anexos Seguros da  ATP da Política de Gerenciamento de Ameaças e clique em \>  \>  **Configurações Globais.**</span><span class="sxs-lookup"><span data-stu-id="509a0-127">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="509a0-128">No menu **Desdolização** das configurações Globais exibido, de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="509a0-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="509a0-129">**Ativar Documentos Seguros para clientes do Office:** mover o alternância para a direita para ativar o recurso: ![ Ativar/desativar. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="509a0-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="509a0-130">Permitir **que** as pessoas cliquem por meio do Exibição Protegido, mesmo se os Documentos Seguros identificarem o arquivo como mal-intencionado: recomendamos que você deixe essa opção desligada (deixe o botão de alternância para a esquerda: ![ ](../../media/scc-toggle-off.png) Alternar).</span><span class="sxs-lookup"><span data-stu-id="509a0-130">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="509a0-131">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="509a0-131">When you're finished, click **Save**.</span></span>

   ![Configurações de Documentos Seguros após selecionar Configurações Globais na página Anexos Seguros.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="509a0-133">Usar o PowerShell do Exchange Online para configurar Documentos Seguros</span><span class="sxs-lookup"><span data-stu-id="509a0-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="509a0-134">Use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="509a0-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="509a0-135">O _parâmetro EnableSafeDocs_ habilita ou desabilita Documentos Seguros para toda a organização.</span><span class="sxs-lookup"><span data-stu-id="509a0-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="509a0-136">O _parâmetro AllowSafeDocsOpen_ permite ou impede que os usuários deixem o Exibição Protegido (ou seja, abrir o documento) se o documento tiver sido identificado como mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="509a0-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="509a0-137">Este exemplo habilita documentos seguros para toda a organização e impede que os usuários abrem documentos identificados como mal-intencionados do Modo de Exibição Protegido.</span><span class="sxs-lookup"><span data-stu-id="509a0-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="509a0-138">Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="509a0-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="509a0-139">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="509a0-139">How do I know this worked?</span></span>

<span data-ttu-id="509a0-140">Para verificar se você habilitar e configurar documentos seguros, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="509a0-140">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="509a0-141">No Centro de Conformidade de Segurança  &, vá para Anexos Seguros da POLÍTICA de Gerenciamento de Ameaças da \>  \> **ATP,**   clique em Configurações Globais e verifique a opção Ativar Documentos Seguros para clientes do **Office** e Permitir que as pessoas cliquem em Exibição Protegida, mesmo se Os Documentos Seguros identificarem o arquivo como configurações mal-intencionadas.</span><span class="sxs-lookup"><span data-stu-id="509a0-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="509a0-142">Execute o seguinte comando no PowerShell do Exchange Online e verifique os valores de propriedade:</span><span class="sxs-lookup"><span data-stu-id="509a0-142">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="509a0-143">Os arquivos a seguir estão disponíveis para testar a proteção de Documentos Seguros.</span><span class="sxs-lookup"><span data-stu-id="509a0-143">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="509a0-144">Esses documentos são semelhantes ao arquivo EICAR.TXT para testar soluções anti-malware e antivírus.</span><span class="sxs-lookup"><span data-stu-id="509a0-144">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="509a0-145">Os arquivos não são prejudiciais, mas acionarão a proteção de Documentos Seguros.</span><span class="sxs-lookup"><span data-stu-id="509a0-145">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="509a0-146">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="509a0-146">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="509a0-147">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="509a0-147">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="509a0-148">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="509a0-148">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
