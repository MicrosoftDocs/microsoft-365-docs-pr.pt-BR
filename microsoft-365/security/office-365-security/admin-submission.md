---
title: Envios de administradores, envios, problemas de spam, falso negativo, enviar phishing, enviar email para verificação, email suspeito no Office 365, examinar um email, fazer com que a Microsoft examine o phishing, peça à Microsoft para spam, enviar emails, enviar emails, emails do dodgy, email de ator ruim, email suspeito e não confiável, relatar emails de Phish para a Microsoft, relatar emails de phishing para a Microsoft , relatar malware em email para a Microsoft, email de spam na caixa de entrada, vírus em email
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
description: Saiba como enviar emails suspeitos, emails de phishing, spam e outras mensagens, URLs e arquivos potencialmente nocivos da sua empresa para a Microsoft para verificação.
ms.openlocfilehash: 2d86555854f9babd202764f1bad8b548daf52c70
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631376"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="2ebe5-103">Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft</span><span class="sxs-lookup"><span data-stu-id="2ebe5-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="2ebe5-104">Se você for um administrador em uma organização do Microsoft 365 com caixas de correio no Exchange Online, você pode usar o portal de envios no centro de conformidade de & de segurança para enviar mensagens de email, URLs e anexos para a Microsoft para verificação.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-104">If you're an admin in a Microsoft 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="2ebe5-105">Ao enviar um email, você receberá informações sobre qualquer política que possa ter permitido o email de entrada em seu locatário, bem como o exame de qualquer URL e anexo no email.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="2ebe5-106">As políticas que podem ter permitido um email incluem a lista de remetentes confiáveis de um usuário individual, bem como políticas de nível de locatário, como regras de fluxo de emails do Exchange (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="2ebe5-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="2ebe5-107">Para obter outras maneiras de enviar mensagens de email, URLs e anexos para a Microsoft, consulte</span><span class="sxs-lookup"><span data-stu-id="2ebe5-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2ebe5-108">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="2ebe5-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2ebe5-109">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="2ebe5-110">Para ir diretamente para a página de **envio** , <https://protection.office.com/reportsubmission>use.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="2ebe5-111">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2ebe5-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2ebe5-112">Para se conectar ao PowerShell da Proteção do Exchange Online autônoma, confira [Conectar ao PowerShell da Proteção do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="2ebe5-112">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2ebe5-113">Você precisa receber permissões para executar esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-113">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="2ebe5-114">Para adicionar, modificar e excluir políticas antispam, você precisa ser membro dos grupos de função de gerenciamento da **organização**, **administrador de segurança**ou **leitor de segurança** .</span><span class="sxs-lookup"><span data-stu-id="2ebe5-114">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="2ebe5-115">Para obter mais informações sobre grupos de função no centro de conformidade de & de segurança, consulte [permissões no centro de conformidade de & de segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="2ebe5-115">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="2ebe5-116">Para obter mais informações sobre como os usuários podem enviar mensagens e arquivos para a Microsoft, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="2ebe5-116">For more information about how users can submit messages and files to Microsoft see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="how-to-direct-suspicious-content-to-microsoft-scanning"></a><span data-ttu-id="2ebe5-117">Como direcionar conteúdo suspeito para a verificação da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2ebe5-117">How to direct suspicious content to Microsoft scanning</span></span>

<span data-ttu-id="2ebe5-118">Para enviar conteúdo à Microsoft, clique no botão **novo envio** no lado superior esquerdo da página envios.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-118">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="2ebe5-119">Um submenu no lado direito da página aparece com a opção de enviar um email, uma URL ou um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-119">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="2ebe5-120">Enviar um email questionável à Microsoft</span><span class="sxs-lookup"><span data-stu-id="2ebe5-120">Submit a questionable email to Microsoft</span></span>

![Exemplo de envio de email](../../media/submission-flyout-email.PNG)

1. <span data-ttu-id="2ebe5-122">Para enviar um email, selecione **email** e ESPECIFIQUE a **ID da mensagem da rede** de email ou carregue o arquivo de email.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-122">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span>

2. <span data-ttu-id="2ebe5-123">Especifique o (s) destinatário (s) em relação ao qual você gostaria de executar a verificação de política.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-123">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="2ebe5-124">A verificação de política determinará se o email ignorou a verificação devido a políticas de nível de usuário ou locatário.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-124">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span>

3. <span data-ttu-id="2ebe5-125">Especifique se o email deve ter sido bloqueado ou não.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-125">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="2ebe5-126">Se o email tiver sido bloqueado, especifique se ele deve ter sido bloqueado como spam, phishing ou malware.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-126">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="2ebe5-127">Se você não tiver certeza de qual tipo pode ser, use o melhor julgamento.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-127">If you are not sure what type it might be, use your best judgment.</span></span>

   - <span data-ttu-id="2ebe5-128">Se o filtro tiver sido ignorado devido às políticas após o envio, você verá informações sobre essa política.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-128">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   - <span data-ttu-id="2ebe5-129">Se o filtro não tiver sido ignorado devido a uma ou mais políticas, a verificação será concluída em vários minutos.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-129">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="2ebe5-130">Você verá informações adicionais sobre o envio clicando no link status.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-130">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="2ebe5-131">Isso inclui os resultados da verificação de política e a veredicto de nova verificação.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-131">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="2ebe5-132">Observação isso não executa o email por meio da pilha de filtragem completa do Office 365 ATP novamente, mas executa uma verificação parcial com base em determinados atributos do email, da URL ou do arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-132">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

4. <span data-ttu-id="2ebe5-133">Clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="2ebe5-133">Click the **Submit** button.</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="2ebe5-134">Enviar uma URL suspeita para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="2ebe5-134">Send a suspect URL to Microsoft</span></span>

![Exemplo de envio de email](../../media/submission-url-flyout.png)

1. <span data-ttu-id="2ebe5-136">Para enviar **uma URL de seleção de** URL do submenu.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-136">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="2ebe5-137">Digite a URL completa incluindo o protocolo (**https://**).</span><span class="sxs-lookup"><span data-stu-id="2ebe5-137">Type in the full URL including the protocol (**https://**).</span></span>

   <span data-ttu-id="2ebe5-138">Se você tiver selecionado o **deve ter sido filtrado**, especifique se a URL é phishing ou malware.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-138">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="2ebe5-139">Clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="2ebe5-139">Click the **Submit** button.</span></span>

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="2ebe5-140">Enviar um arquivo suspeito para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="2ebe5-140">Submit a suspected file to Microsoft</span></span>

![Exemplo de envio de email](../../media/submission-file-flyout.PNG)

1. <span data-ttu-id="2ebe5-142">Para enviar **um arquivo de seleção de** arquivo do submenu e carregar o arquivo que você deseja verificar.</span><span class="sxs-lookup"><span data-stu-id="2ebe5-142">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span>

2. <span data-ttu-id="2ebe5-143">Clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="2ebe5-143">Click the **Submit** button.</span></span>
