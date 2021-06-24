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
description: Saiba mais Cofre documentos em Microsoft 365 E5 ou Microsoft 365 E5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e1bd2150a04e51e0d06c6cd1c17a71a032df1a5
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108602"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="ec769-103">Documentos Seguros no Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ec769-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ec769-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="ec769-104">**Applies to**</span></span>
- [<span data-ttu-id="ec769-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec769-105">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ec769-106">Cofre Documentos é um recurso no Microsoft 365 E5 ou Microsoft 365 E5 Security que usa o [Microsoft Defender para](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) Ponto de Extremidade para examinar documentos e arquivos abertos no [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) ou no Application [Guard](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)para Office .</span><span class="sxs-lookup"><span data-stu-id="ec769-106">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) or [Application Guard for Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ec769-107">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="ec769-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ec769-108">Cofre Os documentos estão disponíveis apenas para usuários com *Microsoft 365 E5* ou *Microsoft 365 E5 Security* licenças.</span><span class="sxs-lookup"><span data-stu-id="ec769-108">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="ec769-109">Essas licenças não estão incluídas no Microsoft Defender para Office 365 planos.</span><span class="sxs-lookup"><span data-stu-id="ec769-109">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="ec769-110">Cofre Os documentos são suportados no Microsoft 365 Apps para Grandes Empresas (anteriormente conhecido como Office 365 ProPlus) versão 2004 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="ec769-110">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="ec769-111">Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="ec769-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="ec769-112">Para ir diretamente para a página **Cofre Anexos,** use <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="ec769-112">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="ec769-113">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ec769-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="ec769-114">Você precisa de permissões **Exchange Online** antes de poder fazer os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="ec769-114">You need permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ec769-115">Para configurar Cofre documentos, você precisa ser membro dos grupos de função Gerenciamento da Organização **ou** Administrador **de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="ec769-115">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="ec769-116">Para acessar somente leitura Cofre configurações de Documentos, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="ec769-116">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="ec769-117">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="ec769-117">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="ec769-118">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ec769-118">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ec769-119">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ec769-119">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="ec769-120">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="ec769-120">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="ec769-121">Como a Microsoft lida com seus dados?</span><span class="sxs-lookup"><span data-stu-id="ec769-121">How does Microsoft handle your data?</span></span>

<span data-ttu-id="ec769-122">Para mantê-lo protegido, Cofre Documentos envia arquivos para a nuvem [do Microsoft Defender para Ponto](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) de Extremidade para análise.</span><span class="sxs-lookup"><span data-stu-id="ec769-122">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="ec769-123">Detalhes sobre como o Microsoft Defender for Endpoint lida com seus dados podem ser encontrados aqui: Microsoft Defender para armazenamento de dados do Ponto de Extremidade [e privacidade.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="ec769-123">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="ec769-124">Os arquivos enviados por Cofre Documentos não são mantidos no Defender além do tempo necessário para análise (normalmente, menos de 24 horas).</span><span class="sxs-lookup"><span data-stu-id="ec769-124">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-microsoft-365-defender-to-configure-safe-documents"></a><span data-ttu-id="ec769-125">Usar o Microsoft 365 Defender para configurar Cofre Documentos</span><span class="sxs-lookup"><span data-stu-id="ec769-125">Use the Microsoft 365 Defender to configure Safe Documents</span></span>

1. <span data-ttu-id="ec769-126">Abra o portal Microsoft 365 Defender e acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \> **Políticas** \> **Cofre Anexos**.</span><span class="sxs-lookup"><span data-stu-id="ec769-126">Open the Microsoft 365 Defender portal and go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="ec769-127">Na página **Cofre Anexos,** clique em **Configurações globais**.</span><span class="sxs-lookup"><span data-stu-id="ec769-127">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="ec769-128">Nas **configurações globais** que aparecem, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="ec769-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>
   - <span data-ttu-id="ec769-129">**Ativar Cofre Documentos para** clientes Office : Mova a alternância para a direita para ativar o recurso: ![ Ativar a alternância ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="ec769-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="ec769-130">**Permitir que** as pessoas cliquem em Exibição Protegida, mesmo que Cofre Documentos identificaram o arquivo como mal-intencionado : recomendamos que você deixe essa opção desligada (deixe a alternância para a esquerda: Alternar para fora ![ ](../../media/scc-toggle-off.png) ).</span><span class="sxs-lookup"><span data-stu-id="ec769-130">**Allow people to click through Protected View even if Safe Documents identified the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="ec769-131">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ec769-131">When you're finished, click **Save**.</span></span>

   ![Cofre Configurações de documentos após selecionar configurações globais na página Cofre Anexos.](../../media/safe-docs-global-settings.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="ec769-133">Usar Exchange Online PowerShell para configurar Cofre Documentos</span><span class="sxs-lookup"><span data-stu-id="ec769-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="ec769-134">Use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="ec769-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="ec769-135">O _parâmetro EnableSafeDocs_ habilita ou desabilita Cofre documentos para toda a organização.</span><span class="sxs-lookup"><span data-stu-id="ec769-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="ec769-136">O _parâmetro AllowSafeDocsOpen_ permite ou impede que os usuários deixe o Protected View (ou seja, abrindo o documento) se o documento tiver sido identificado como mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="ec769-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="ec769-137">Este exemplo habilita Cofre documentos para toda a organização e impede que os usuários abriam documentos identificados como mal-intencionados do Modo de Exibição Protegido.</span><span class="sxs-lookup"><span data-stu-id="ec769-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="ec769-138">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="ec769-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a><span data-ttu-id="ec769-139">Integração ao Microsoft Defender for Endpoint Service para habilitar recursos de auditoria</span><span class="sxs-lookup"><span data-stu-id="ec769-139">Onboard to the Microsoft Defender for Endpoint Service to enable auditing capabilities</span></span>

<span data-ttu-id="ec769-140">Para implantar o Microsoft Defender para Ponto de Extremidade, você precisa passar pelas várias fases de implantação.</span><span class="sxs-lookup"><span data-stu-id="ec769-140">To deploy Microsoft Defender for Endpoint, you need to go through the various phases of deployment.</span></span> <span data-ttu-id="ec769-141">Após a integração, você pode configurar recursos de auditoria no Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="ec769-141">After onboarding, you can configure auditing capabilities in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="ec769-142">Para saber mais, confira [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding).</span><span class="sxs-lookup"><span data-stu-id="ec769-142">To learn more, see [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding).</span></span> <span data-ttu-id="ec769-143">Se precisar de ajuda adicional, consulte Solução de problemas de integração do [Microsoft Defender para Ponto de Extremidade.](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)</span><span class="sxs-lookup"><span data-stu-id="ec769-143">If you need additional help, refer to [Troubleshoot Microsoft Defender for Endpoint onboarding issues](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="ec769-144">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="ec769-144">How do I know this worked?</span></span>

<span data-ttu-id="ec769-145">Para verificar se você habilitar e configurar Cofre Documentos, faça qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="ec769-145">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="ec769-146">No portal do Microsoft 365 Defender, acesse Email **& Políticas** de Colaboração & Página Políticas de Ameaças de Regras Políticas Cofre Configurações globais de \>  \>  \>  \> **anexos** e \>    verifique a página Ativar documentos do Cofre para clientes do Office e Permitir que as pessoas cliquem em Exibir Protegido mesmo que documentos Cofre identifiquem o arquivo como configurações mal-intencionadas.</span><span class="sxs-lookup"><span data-stu-id="ec769-146">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments** \> **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="ec769-147">Execute o seguinte comando no Exchange Online PowerShell e verifique os valores da propriedade:</span><span class="sxs-lookup"><span data-stu-id="ec769-147">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="ec769-148">Os arquivos a seguir estão disponíveis para testar a proteção Cofre Documentos.</span><span class="sxs-lookup"><span data-stu-id="ec769-148">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="ec769-149">Esses documentos são semelhantes ao arquivo EICAR.TXT para testar soluções anti-malware e antivírus.</span><span class="sxs-lookup"><span data-stu-id="ec769-149">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="ec769-150">Os arquivos não são prejudiciais, mas dispararão a proteção Cofre Documentos.</span><span class="sxs-lookup"><span data-stu-id="ec769-150">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="ec769-151">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="ec769-151">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="ec769-152">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="ec769-152">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="ec769-153">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="ec769-153">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
