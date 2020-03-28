---
title: Envios de administradores no Office 365, envios do O365, problema do Office 365 spam, o O365 falso negativo, enviar phishing no Office 365, enviar email para verificação, email suspeito no Office 365, examinar um email, fazer com que a Microsoft examine o phishing, peça à Microsoft para spam, enviar email, enviar emails, emails do dodgy, email de ator ruim, email suspeito, não confiável, relatar emails de phishing para a Microsoft, relatar emails de phishing para a Microsoft, relatar emails mal-intencionados para a Microsoft, relatar emails de golpes à Microsoft, relatar malwares em email para a Microsoft, spam email na caixa de entrada Office 365, vírus no email do Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Saiba como enviar emails suspeitos, emails de phishing suspeitos, spam e outras mensagens, URLs e arquivos potencialmente nocivos do seu locatário do Office 365 para a Microsoft para verificação.
ms.openlocfilehash: 539d09f03a8a9c5956f2d1e3584f893b0e4ffbb4
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033609"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="3b9c9-103">Usar o envio do administrador para enviar spam, phishing, URLs e arquivos suspeitos para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3b9c9-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="3b9c9-104">Se você é um administrador em uma organização do Office 365 com caixas de correio no Exchange Online, você pode usar o portal de envios no centro de conformidade & segurança do Office 365 para enviar mensagens de email, URLs e anexos para a Microsoft para verificação.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-104">If you're an admin in an Office 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Office 365 Security & Compliance Center to submit email messages, URLs and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="3b9c9-105">Ao enviar um email, você receberá informações sobre qualquer política que possa ter permitido o email de entrada em seu locatário, bem como o exame de qualquer URL e anexo no email.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="3b9c9-106">As políticas que podem ter permitido um email incluem a lista de remetentes confiáveis de um usuário individual, bem como políticas de nível de locatário, como regras de fluxo de emails do Exchange (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="3b9c9-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="3b9c9-107">Para obter outras maneiras de enviar mensagens de email, URLs e anexos para a Microsoft, consulte</span><span class="sxs-lookup"><span data-stu-id="3b9c9-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3b9c9-108">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="3b9c9-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3b9c9-109">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3b9c9-110">Para ir diretamente para a página de **envio** , <https://protection.office.com/reportsubmission>use.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="3b9c9-111">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3b9c9-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="3b9c9-112">Para se conectar ao PowerShell da Proteção do Exchange Online autônoma, confira [Conectar ao PowerShell da Proteção do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="3b9c9-112">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3b9c9-113">Você precisa receber permissões para executar esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-113">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="3b9c9-114">Para adicionar, modificar e excluir políticas antispam, você precisa ser membro dos grupos de função de gerenciamento da **organização**, **administrador de segurança**ou **leitor de segurança** .</span><span class="sxs-lookup"><span data-stu-id="3b9c9-114">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="3b9c9-115">Para obter mais informações sobre grupos de funções no Centro de Conformidade e Segurança, confira [Permissões no Centro de conformidade e Segurança do Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3b9c9-115">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="3b9c9-116">Para obter mais informações sobre como os usuários podem enviar mensagens e arquivos para a Microsoft, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="3b9c9-116">For more information about how users can submit messages and files to Microsoft see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="3b9c9-117">Como direcionar conteúdo suspeito para a Microsoft para a verificação do Office 365</span><span class="sxs-lookup"><span data-stu-id="3b9c9-117">How to direct suspicious content to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="3b9c9-118">Para enviar conteúdo à Microsoft, clique no botão **novo envio** no lado superior esquerdo da página envios.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-118">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="3b9c9-119">Um submenu no lado direito da página aparece com a opção de enviar um email, uma URL ou um arquivo.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-119">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="3b9c9-120">Enviar um email questionável à Microsoft</span><span class="sxs-lookup"><span data-stu-id="3b9c9-120">Submit a questionable email to Microsoft</span></span>

![Exemplo de envio de email](../../media/submission-flyout-email.PNG)

1. <span data-ttu-id="3b9c9-122">Para enviar um email, selecione **email** e ESPECIFIQUE a **ID da mensagem da rede** de email ou carregue o arquivo de email.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-122">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span>

2. <span data-ttu-id="3b9c9-123">Especifique o (s) destinatário (s) em relação ao qual você gostaria de executar a verificação de política.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-123">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="3b9c9-124">A verificação de política determinará se o email ignorou a verificação devido a políticas de nível de usuário ou locatário.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-124">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span>

3. <span data-ttu-id="3b9c9-125">Especifique se o email deve ter sido bloqueado ou não.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-125">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="3b9c9-126">Se o email tiver sido bloqueado, especifique se ele deve ter sido bloqueado como spam, phishing ou malware.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-126">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="3b9c9-127">Se você não tiver certeza de qual tipo pode ser, use o melhor julgamento.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-127">If you are not sure what type it might be, use your best judgment.</span></span>

   - <span data-ttu-id="3b9c9-128">Se o filtro tiver sido ignorado devido às políticas após o envio, você verá informações sobre essa política.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-128">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   - <span data-ttu-id="3b9c9-129">Se o filtro não tiver sido ignorado devido a uma ou mais políticas, a verificação será concluída em vários minutos.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-129">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="3b9c9-130">Você verá informações adicionais sobre o envio clicando no link status.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-130">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="3b9c9-131">Isso inclui os resultados da verificação de política e a veredicto de nova verificação.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-131">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="3b9c9-132">Observação isso não executa o email por meio da pilha de filtragem completa do Office 365 ATP novamente, mas executa uma verificação parcial com base em determinados atributos do email, da URL ou do arquivo.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-132">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

4. <span data-ttu-id="3b9c9-133">Clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="3b9c9-133">Click the **Submit** button.</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="3b9c9-134">Enviar uma URL suspeita para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3b9c9-134">Send a suspect URL to Microsoft</span></span>

![Exemplo de envio de email](../../media/submission-url-flyout.png)

1. <span data-ttu-id="3b9c9-136">Para enviar **uma URL de seleção de** URL do submenu.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-136">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="3b9c9-137">Digite a URL completa incluindo o protocolo (**https://**).</span><span class="sxs-lookup"><span data-stu-id="3b9c9-137">Type in the full URL including the protocol (**https://**).</span></span>

   <span data-ttu-id="3b9c9-138">Se você tiver selecionado o **deve ter sido filtrado**, especifique se a URL é phishing ou malware.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-138">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="3b9c9-139">Clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="3b9c9-139">Click the **Submit** button.</span></span>

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="3b9c9-140">Enviar um arquivo suspeito para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3b9c9-140">Submit a suspected file to Microsoft</span></span>

![Exemplo de envio de email](../../media/submission-file-flyout.PNG)

1. <span data-ttu-id="3b9c9-142">Para enviar **um arquivo de seleção de** arquivo do submenu e carregar o arquivo que você deseja verificar.</span><span class="sxs-lookup"><span data-stu-id="3b9c9-142">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span>

2. <span data-ttu-id="3b9c9-143">Clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="3b9c9-143">Click the **Submit** button.</span></span>
