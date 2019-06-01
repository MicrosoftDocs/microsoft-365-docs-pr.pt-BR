---
title: Aumentar a proteção contra ameaças para o Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Configurar a proteção avançada contra ameaças do Office 365 e proteger dados confidenciais.
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668371"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="5d98e-103">Configurar recursos de conformidade</span><span class="sxs-lookup"><span data-stu-id="5d98e-103">Set up compliance features</span></span>

<span data-ttu-id="5d98e-104">Seu Microsoft 365 Business vem com recursos para proteger seus dados e dispositivos, e ajudar você a manter seu e as informações confidenciais de seus clientes seguras.</span><span class="sxs-lookup"><span data-stu-id="5d98e-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="5d98e-105">Configurar recursos de DLP</span><span class="sxs-lookup"><span data-stu-id="5d98e-105">Set up DLP features</span></span>

<span data-ttu-id="5d98e-106">Consulte [criar uma política de DLP a partir de um modelo](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) para obter um exemplo de como configurar uma política para proteção contra informações de identificação pessoal (PII).</span><span class="sxs-lookup"><span data-stu-id="5d98e-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="5d98e-107">A DLP vem com vários modelos de política prontos para uso para várias localidades diferentes.</span><span class="sxs-lookup"><span data-stu-id="5d98e-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="5d98e-108">Por exemplo, dados financeiros da Austrália, ato de informações pessoais do Canadá, dados financeiros dos EUA, etc. Veja o [que os modelos de política de DLP incluem](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) para uma lista completa.</span><span class="sxs-lookup"><span data-stu-id="5d98e-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="5d98e-109">Todos esses modelos podem ser habilitados de forma semelhante ao exemplo de modelo PII.</span><span class="sxs-lookup"><span data-stu-id="5d98e-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="5d98e-110">Configurar a retenção de email com o arquivamento do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5d98e-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="5d98e-111">Os recursos de licença de arquivamento do **Exchange Online** ajudam a manter os padrões de conformidade e regulamentação ao preservar o conteúdo de email para descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="5d98e-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="5d98e-112">Isso também ajuda a reduzir o risco no caso de uma ação judicial e oferece uma maneira de recuperar dados após uma violação de segurança ou quando você precisa recuperar itens excluídos.</span><span class="sxs-lookup"><span data-stu-id="5d98e-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="5d98e-113">Você pode usar a retenção de litígio para preservar todo o conteúdo de um usuário ou usar políticas de retenção para personalizar o que você deseja preservar.</span><span class="sxs-lookup"><span data-stu-id="5d98e-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="5d98e-114">**Retenção de litígio:** Você pode preservar todo o conteúdo da caixa de correio, incluindo itens excluídos, colocando a caixa de correio de um usuário em retenção de litígio.</span><span class="sxs-lookup"><span data-stu-id="5d98e-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="5d98e-115">Para colocar uma caixa de correio em retenção de litígio, no centro de administração:</span><span class="sxs-lookup"><span data-stu-id="5d98e-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="5d98e-116">No painel de navegação à esquerda, vá para usuários **ativos**do **usuário** \> .</span><span class="sxs-lookup"><span data-stu-id="5d98e-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="5d98e-117">Selecione um usuário cuja caixa de correio você deseja colocar em retenção de litígio e, no painel de usuário, expanda **configurações de email** e ao lado de **mais configurações** escolha **Editar propriedades do Exchange**.</span><span class="sxs-lookup"><span data-stu-id="5d98e-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="5d98e-118">Na página caixa de correio do usuário, escolha \* \* recursos de caixa de correio \* \* no painel de navegação esquerdo e, em seguida, escolha o link **habilitar** em **retenção de litígio**.</span><span class="sxs-lookup"><span data-stu-id="5d98e-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="5d98e-119">Na caixa de diálogo **retenção de litígio** , é possível especificar a duração da retenção de litígio no campo duração da **retenção de litígio** , deixar o campo vazio se você quiser colocar uma retenção infinita.</span><span class="sxs-lookup"><span data-stu-id="5d98e-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="5d98e-120">Você também pode adicionar notas e direcionar o proprietário da caixa de correio para um site que pode ser necessário para explicar mais sobre \> o **salvamento**de litígio.</span><span class="sxs-lookup"><span data-stu-id="5d98e-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="5d98e-121">**Retenção:** Você pode habilitar políticas de retenção personalizadas, por exemplo, para preservar um período específico de tempo ou excluir o conteúdo permanentemente no final do período de retenção.</span><span class="sxs-lookup"><span data-stu-id="5d98e-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="5d98e-122">Para saber mais, confira [visão geral das políticas de retenção](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="5d98e-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-azure-information-protection-features"></a><span data-ttu-id="5d98e-123">Configurar recursos de proteção de informações do Azure</span><span class="sxs-lookup"><span data-stu-id="5d98e-123">Set up Azure Information Protection features</span></span>

<span data-ttu-id="5d98e-124">A proteção de informações do Azure (AIP) ajuda você a classificar e, opcionalmente, proteger seus documentos e emails, aplicando rótulos.</span><span class="sxs-lookup"><span data-stu-id="5d98e-124">Azure Information Protection (AIP) helps you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="5d98e-125">Os rótulos podem ser aplicados automaticamente por administradores que definem regras e condições, manualmente por usuários ou usando uma combinação em que os usuários recebem recomendações.</span><span class="sxs-lookup"><span data-stu-id="5d98e-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="5d98e-126">No Outlook na Web, você pode aplicar os seguintes rótulos e restrições internos aos seus emails:</span><span class="sxs-lookup"><span data-stu-id="5d98e-126">In Outlook on the web you can apply the following built-in labels and restrictions to your emails:</span></span>
  
- <span data-ttu-id="5d98e-127">**Não encaminhar**: os destinatários podem ler a mensagem, mas não podem encaminhar, imprimir ou copiar o conteúdo</span><span class="sxs-lookup"><span data-stu-id="5d98e-127">**Do Not Forward**: Recipients can read the message, but they can't forward, print, or copy content</span></span>
    
- <span data-ttu-id="5d98e-128">**Encrypt**: toda a mensagem é criptografada.</span><span class="sxs-lookup"><span data-stu-id="5d98e-128">**Encrypt**: The entire message is encrypted.</span></span> <span data-ttu-id="5d98e-129">Os destinatários devem confirmar sua identidade antes de acessar o conteúdo criptografado e não podem remover a criptografia.</span><span class="sxs-lookup"><span data-stu-id="5d98e-129">Recipients must confirm their identity before accessing encrypted content and can't remove encryption.</span></span>
    
- <span data-ttu-id="5d98e-130">**Confidencial**: fornece aos funcionários em sua organização permissões completas para o conteúdo e os anexos de email, mas não para pessoas de fora da organização.</span><span class="sxs-lookup"><span data-stu-id="5d98e-130">**Confidential**: Gives the employees in your organization full permissions to the email content and attachments, but not to people outside your organization.</span></span> <span data-ttu-id="5d98e-131">Os proprietários de dados podem controlar e revogar o conteúdo em qualquer ponto.</span><span class="sxs-lookup"><span data-stu-id="5d98e-131">Data owners can track and revoke content at any point.</span></span>
    
- <span data-ttu-id="5d98e-132">**Altamente confidencial**: essa restrição pode ser aplicada a dados altamente confidenciais, permitindo que os funcionários exibam, editem e respondam, mas não encaminhem, imprimam ou copiem os dados.</span><span class="sxs-lookup"><span data-stu-id="5d98e-132">**Highly Confidential**: This restriction can be applied to highly confidential data, allowing employees to view, edit, and reply, but not forward, print, or copy the data.</span></span> <span data-ttu-id="5d98e-133">Os proprietários de dados podem controlar e revogar o conteúdo em qualquer ponto.</span><span class="sxs-lookup"><span data-stu-id="5d98e-133">Data owners can track and revoke content at any point.</span></span>

### <a name="make-sure-azure-information-protection-is-activated"></a><span data-ttu-id="5d98e-134">Verifique se a proteção de informações do Azure está ativada</span><span class="sxs-lookup"><span data-stu-id="5d98e-134">Make sure Azure Information Protection is activated</span></span>

<span data-ttu-id="5d98e-135">Para verificar se o AIP está ativado:</span><span class="sxs-lookup"><span data-stu-id="5d98e-135">To verify that AIP is activated :</span></span>

1. <span data-ttu-id="5d98e-136">Entre no [portal do Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="5d98e-136">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="5d98e-137">Selecione **todos os serviços** e digite na *proteção de informações do Azure* na **caixa de pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="5d98e-137">Select **All services** and type in *Azure Information Protection* in the **Search Box**.</span></span>

3. <span data-ttu-id="5d98e-138">Depois que os resultados são exibidos, clique em Iniciar ao lado de **proteção de informações do Azure** para torná-lo favorito e fácil de localizar mais tarde.</span><span class="sxs-lookup"><span data-stu-id="5d98e-138">Once the results display, click the start next to **Azure Information Protection** to make it a favorite and easy to find later.</span></span>

4. <span data-ttu-id="5d98e-139">Selecione \> **ativação da proteção** de **proteção de informações do Azure** e verifique se o status está definido como ativado.</span><span class="sxs-lookup"><span data-stu-id="5d98e-139">Select **Azure Information Protection** \> **Protection activation** and make sure the status is set to activated.</span></span> 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a><span data-ttu-id="5d98e-140">Exibir a política de proteção de informações do Azure e os rótulos padrão</span><span class="sxs-lookup"><span data-stu-id="5d98e-140">View the Azure Information Protection policy and default labels</span></span> 

<span data-ttu-id="5d98e-141">Para exibir e modificar os rótulos existentes:</span><span class="sxs-lookup"><span data-stu-id="5d98e-141">To view, and modify, the existing labels:</span></span>

1. <span data-ttu-id="5d98e-142">No painel de proteção de informações do Azure \*\*\*\* \> , selecione **Rótulos**de classificações.</span><span class="sxs-lookup"><span data-stu-id="5d98e-142">On the Azure Information Protection dashboard, select **Classifications** \> **Labels**.</span></span> <br/><span data-ttu-id="5d98e-143">![Rótulos padrão para a proteção de informações do Azure.](media/AIPLabels.png)</span><span class="sxs-lookup"><span data-stu-id="5d98e-143">![Standard labels for Azure Information Protection.](media/AIPLabels.png)</span></span>

2. <span data-ttu-id="5d98e-144">Você pode escolher qualquer rótulo para exibir opções, você pode alterar o nome de exibição, as cores, etc.</span><span class="sxs-lookup"><span data-stu-id="5d98e-144">You can choose any label to view options, you can change the display name, colors, etc.</span></span>
 
3. <span data-ttu-id="5d98e-145">Confira [modificar e criar novos rótulos](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) se você quiser criar seus próprios.</span><span class="sxs-lookup"><span data-stu-id="5d98e-145">See  [Modify and create new labels](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) if you want to create your own.</span></span> 

### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="5d98e-146">Instalar o cliente de proteção de informações do Azure manualmente</span><span class="sxs-lookup"><span data-stu-id="5d98e-146">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="5d98e-147">Para instalar manualmente o cliente AIP:</span><span class="sxs-lookup"><span data-stu-id="5d98e-147">To manually install the AIP client:</span></span>

1. <span data-ttu-id="5d98e-148">Baixe o **AzInfoProtection. exe** do [centro de download da Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="5d98e-148">Download **AzInfoProtection.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="5d98e-149">Você pode verificar se a instalação funcionou exibindo um documento do Word e certificando-se de que a opção **proteger** está disponível na guia **página inicial** .</span><span class="sxs-lookup"><span data-stu-id="5d98e-149">You can verify that the installation worked by viewing a Word document and making sure that the **Protect** option is available on the **Home** tab.</span></span> <br/><span data-ttu-id="5d98e-150">![Menu suspenso proteção de guia em um documento do Word.](media/Word_Protect.png)</span><span class="sxs-lookup"><span data-stu-id="5d98e-150">![Protection tab drop-down in a Word document.](media/Word_Protect.png)</span></span>

<span data-ttu-id="5d98e-151">Confira mais informações em [instalar o cliente](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="5d98e-151">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
