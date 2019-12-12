---
title: Envios de administradores no Office 365, envios do O365, problema do Office 365 spam, o O365 falso negativo, enviar phishing no Office 365, enviar email para verificação, email suspeito no Office 365, examinar um email, fazer com que a Microsoft examine o phishing, peça à Microsoft para spam, enviar email, enviar email, email do dodgy, email de ator ruim, email suspeito, não confiável
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/06/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Saiba como enviar emails suspeitos, emails de phishing suspeitos, spam e outras mensagens, URLs e arquivos potencialmente nocivos do seu locatário do Office 365 para a Microsoft para verificação.
ms.openlocfilehash: 3d53c8270e84cd6f6298b9b39cc7e37262aed7b0
ms.sourcegitcommit: 9c9044885eb9754ce69f2f08afdcc13c782ce2f9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2019
ms.locfileid: "39915212"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="e2286-103">Como enviar spam, phishing, URLs e arquivos suspeitos à Microsoft para a verificação do Office 365</span><span class="sxs-lookup"><span data-stu-id="e2286-103">How to submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="e2286-104">Os administradores podem enviar emails usando ID de mensagem de arquivo ou rede, URLs e arquivos para verificação da Microsoft no Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2286-104">Admins can send emails by using file or network message ID, URLs, and files for scanning by Microsoft in Office 365.</span></span> <span data-ttu-id="e2286-105">A seção de envios atualizados ainda inclui mensagens relatadas pelo usuário e estão disponíveis para todos os clientes que usam o EOP.</span><span class="sxs-lookup"><span data-stu-id="e2286-105">The updated submissions section still includes user reported messages and available to all customers using EOP.</span></span>

<span data-ttu-id="e2286-106">Ao enviar um email, você receberá informações sobre qualquer política que possa ter permitido o email de entrada em seu locatário, bem como o exame de qualquer URL e anexo no email.</span><span class="sxs-lookup"><span data-stu-id="e2286-106">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="e2286-107">As políticas que podem ter permitido um email incluem a lista de remetentes confiáveis de um usuário individual, bem como as políticas de nível de locatário, como regras ETR.</span><span class="sxs-lookup"><span data-stu-id="e2286-107">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as ETR rules.</span></span> 

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="e2286-108">Como direcionar conteúdo suspeito para a Microsoft para a verificação do Office 365</span><span class="sxs-lookup"><span data-stu-id="e2286-108">How to direct suspicious content to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="e2286-109">Para enviar conteúdo à Microsoft, clique no botão **novo envio** no lado superior esquerdo da página envios.</span><span class="sxs-lookup"><span data-stu-id="e2286-109">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="e2286-110">Um submenu no lado direito da página aparece com a opção de enviar um email, uma URL ou um arquivo.</span><span class="sxs-lookup"><span data-stu-id="e2286-110">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span> 

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="e2286-111">Enviar um email questionável à Microsoft</span><span class="sxs-lookup"><span data-stu-id="e2286-111">Submit a questionable email to Microsoft</span></span>
![Exemplo de envio de email](../media/submission-flyout-email.PNG)
1. <span data-ttu-id="e2286-113">Para enviar um email, selecione **email** e ESPECIFIQUE a **ID da mensagem da rede** de email ou carregue o arquivo de email.</span><span class="sxs-lookup"><span data-stu-id="e2286-113">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span> 

2. <span data-ttu-id="e2286-114">Especifique o (s) destinatário (s) em relação ao qual você gostaria de executar a verificação de política.</span><span class="sxs-lookup"><span data-stu-id="e2286-114">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="e2286-115">A verificação de política determinará se o email ignorou a verificação devido a políticas de nível de usuário ou locatário.</span><span class="sxs-lookup"><span data-stu-id="e2286-115">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span> 

3. <span data-ttu-id="e2286-116">Especifique se o email deve ter sido bloqueado ou não.</span><span class="sxs-lookup"><span data-stu-id="e2286-116">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="e2286-117">Se o email tiver sido bloqueado, especifique se ele deve ter sido bloqueado como spam, phishing ou malware.</span><span class="sxs-lookup"><span data-stu-id="e2286-117">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="e2286-118">Se você não tiver certeza de qual tipo pode ser, use a melhor Judgement.</span><span class="sxs-lookup"><span data-stu-id="e2286-118">If you are not sure what type it might be, use your best judgement.</span></span>  

* <span data-ttu-id="e2286-119">Se o filtro tiver sido ignorado devido às políticas após o envio, você verá informações sobre essa política.</span><span class="sxs-lookup"><span data-stu-id="e2286-119">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

* <span data-ttu-id="e2286-120">Se o filtro não tiver sido ignorado devido a uma ou mais políticas, a verificação será concluída em vários minutos.</span><span class="sxs-lookup"><span data-stu-id="e2286-120">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="e2286-121">Você verá informações adicionais sobre o envio clicando no link status.</span><span class="sxs-lookup"><span data-stu-id="e2286-121">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="e2286-122">Isso inclui os resultados da verificação de política e a veredicto de nova verificação.</span><span class="sxs-lookup"><span data-stu-id="e2286-122">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="e2286-123">Observação isso não executa o email por meio da pilha de filtragem completa do Office 365 ATP novamente, mas executa uma verificação parcial com base em determinados atributos do email, da URL ou do arquivo.</span><span class="sxs-lookup"><span data-stu-id="e2286-123">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span> 

4. <span data-ttu-id="e2286-124">Clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="e2286-124">Click the **Submit** button.</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="e2286-125">Enviar uma URL suspeita para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="e2286-125">Send a suspect URL to Microsoft</span></span>
![Exemplo de envio de email](../media/submission-url-flyout.png)
1. <span data-ttu-id="e2286-127">Para enviar **uma URL de seleção de** URL do submenu.</span><span class="sxs-lookup"><span data-stu-id="e2286-127">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="e2286-128">Digite a URL completa incluindo o protocolo (**https://**).</span><span class="sxs-lookup"><span data-stu-id="e2286-128">Type in the full URL including the protocol (**https://**).</span></span> 

* <span data-ttu-id="e2286-129">Se você tiver selecionado o **deve ter sido filtrado**, especifique se a URL é phishing ou malware.</span><span class="sxs-lookup"><span data-stu-id="e2286-129">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="e2286-130">Clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="e2286-130">Click the **Submit** button.</span></span> 


### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="e2286-131">Enviar um arquivo suspeito para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="e2286-131">Submit a suspected file to Microsoft</span></span>
![Exemplo de envio de email](../media/submission-file-flyout.PNG)
1. <span data-ttu-id="e2286-133">Para enviar **um arquivo de seleção de** arquivo do submenu e carregar o arquivo que você deseja verificar.</span><span class="sxs-lookup"><span data-stu-id="e2286-133">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span> 

2. <span data-ttu-id="e2286-134">Clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="e2286-134">Click the **Submit** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e2286-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e2286-135">Related topics</span></span>

[<span data-ttu-id="e2286-136">Plano 2 de proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="e2286-136">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)
  
[<span data-ttu-id="e2286-137">Proteção contra ameaças no Office 365</span><span class="sxs-lookup"><span data-stu-id="e2286-137">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="e2286-138">Exibir relatórios para a proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="e2286-138">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

