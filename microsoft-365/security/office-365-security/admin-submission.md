---
title: Envios de administradores no Office 365, envios do O365, problema do Office 365 spam, o O365 falso negativo, enviar phishing no Office 365, enviar email para verificação, email suspeito no Office 365, examinar um email, fazer com que a Microsoft examine o phishing, peça à Microsoft para spam, enviar email, enviar email
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
ms.openlocfilehash: 5ca5eab2feab1243a83eb60c9320fd48dfb59f12
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073927"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="7fa41-103">Como enviar spam, phishing, URLs e arquivos suspeitos à Microsoft para a verificação do Office 365</span><span class="sxs-lookup"><span data-stu-id="7fa41-103">How to submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="7fa41-104">Os administradores podem enviar emails usando ID de mensagem de arquivo ou rede, URLs e arquivos para verificação da Microsoft no Office 365.</span><span class="sxs-lookup"><span data-stu-id="7fa41-104">Admins can send emails by using file or network message ID, URLs, and files for scanning by Microsoft in Office 365.</span></span> <span data-ttu-id="7fa41-105">A seção de envios atualizados ainda inclui mensagens relatadas pelo usuário e estão disponíveis para todos os clientes que usam o EOP.</span><span class="sxs-lookup"><span data-stu-id="7fa41-105">The updated submissions section still includes user reported messages and available to all customers using EOP.</span></span>

<span data-ttu-id="7fa41-106">Ao enviar um email, você receberá informações sobre qualquer política que possa ter permitido o email de entrada em seu locatário, bem como o exame de qualquer URL e anexo no email.</span><span class="sxs-lookup"><span data-stu-id="7fa41-106">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="7fa41-107">As políticas que podem ter permitido um email incluem a lista de remetentes confiáveis de um usuário individual, bem como as políticas de nível de locatário, como regras ETR.</span><span class="sxs-lookup"><span data-stu-id="7fa41-107">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as ETR rules.</span></span> 

## <a name="how-to-submit-content-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="7fa41-108">Como enviar conteúdo para a verificação da Microsoft para o Office 365</span><span class="sxs-lookup"><span data-stu-id="7fa41-108">How to submit content to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="7fa41-109">Para enviar conteúdo à Microsoft, clique no botão **novo envio** no lado superior esquerdo da página envios.</span><span class="sxs-lookup"><span data-stu-id="7fa41-109">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="7fa41-110">Um submenu no lado direito da página aparece com a opção de enviar um email, uma URL ou um arquivo.</span><span class="sxs-lookup"><span data-stu-id="7fa41-110">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span> 

### <a name="submit-an-email-to-microsoft"></a><span data-ttu-id="7fa41-111">Enviar um email para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="7fa41-111">Submit an email to Microsoft</span></span>
![Exemplo de envio de email](../media/submission-flyout-email.PNG)
1. <span data-ttu-id="7fa41-113">Para enviar um email, selecione **email** e ESPECIFIQUE a **ID da mensagem da rede** de email ou carregue o arquivo de email.</span><span class="sxs-lookup"><span data-stu-id="7fa41-113">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span> 

2. <span data-ttu-id="7fa41-114">Especifique o (s) destinatário (s) em relação ao qual você gostaria de executar a verificação de política.</span><span class="sxs-lookup"><span data-stu-id="7fa41-114">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="7fa41-115">A verificação de política determinará se o email ignorou a verificação devido a políticas de nível de usuário ou locatário.</span><span class="sxs-lookup"><span data-stu-id="7fa41-115">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span> 

3. <span data-ttu-id="7fa41-116">Especifique se o email deve ter sido bloqueado ou não.</span><span class="sxs-lookup"><span data-stu-id="7fa41-116">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="7fa41-117">Se o email tiver sido bloqueado, especifique se ele deve ter sido bloqueado como spam, phishing ou malware.</span><span class="sxs-lookup"><span data-stu-id="7fa41-117">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="7fa41-118">Se você não tiver certeza de qual tipo pode ser, use a melhor Judgement.</span><span class="sxs-lookup"><span data-stu-id="7fa41-118">If you are not sure what type it might be, use your best judgement.</span></span>  

* <span data-ttu-id="7fa41-119">Se o filtro tiver sido ignorado devido às políticas após o envio, você verá informações sobre essa política.</span><span class="sxs-lookup"><span data-stu-id="7fa41-119">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

* <span data-ttu-id="7fa41-120">Se o filtro não tiver sido ignorado devido a uma ou mais políticas, a verificação será concluída em vários minutos.</span><span class="sxs-lookup"><span data-stu-id="7fa41-120">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="7fa41-121">Você verá informações adicionais sobre o envio clicando no link status.</span><span class="sxs-lookup"><span data-stu-id="7fa41-121">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="7fa41-122">Isso inclui os resultados da verificação de política e a veredicto de nova verificação.</span><span class="sxs-lookup"><span data-stu-id="7fa41-122">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="7fa41-123">Observação isso não executa o email por meio da pilha de filtragem completa do Office 365 ATP novamente, mas executa uma verificação parcial com base em determinados atributos do email, da URL ou do arquivo.</span><span class="sxs-lookup"><span data-stu-id="7fa41-123">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span> 

4. <span data-ttu-id="7fa41-124">Clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="7fa41-124">Click the **Submit** button.</span></span>

### <a name="submit-a-url-to-microsoft"></a><span data-ttu-id="7fa41-125">Enviar uma URL para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="7fa41-125">Submit a URL to Microsoft</span></span>
![Exemplo de envio de email](../media/submission-url-flyout.png)
1. <span data-ttu-id="7fa41-127">Para enviar **uma URL de seleção de** URL do submenu.</span><span class="sxs-lookup"><span data-stu-id="7fa41-127">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="7fa41-128">Digite a URL completa incluindo o protocolo (**https://**).</span><span class="sxs-lookup"><span data-stu-id="7fa41-128">Type in the full URL including the protocol (**https://**).</span></span> 

* <span data-ttu-id="7fa41-129">Se você tiver selecionado o **deve ter sido filtrado**, especifique se a URL é phishing ou malware.</span><span class="sxs-lookup"><span data-stu-id="7fa41-129">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="7fa41-130">Clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="7fa41-130">Click the **Submit** button.</span></span> 


### <a name="submit-a-file-to-microsoft"></a><span data-ttu-id="7fa41-131">Enviar um arquivo para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="7fa41-131">Submit a file to Microsoft</span></span>
![Exemplo de envio de email](../media/submission-file-flyout.PNG)
1. <span data-ttu-id="7fa41-133">Para enviar **um arquivo de seleção de** arquivo do submenu e carregar o arquivo que você deseja verificar.</span><span class="sxs-lookup"><span data-stu-id="7fa41-133">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span> 

2. <span data-ttu-id="7fa41-134">Clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="7fa41-134">Click the **Submit** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="7fa41-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7fa41-135">Related topics</span></span>

[<span data-ttu-id="7fa41-136">Office 365 plano avançado de proteção contra ameaças 2</span><span class="sxs-lookup"><span data-stu-id="7fa41-136">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)
  
[<span data-ttu-id="7fa41-137">Proteção contra ameaças no Office 365</span><span class="sxs-lookup"><span data-stu-id="7fa41-137">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="7fa41-138">Exibir relatórios para a proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="7fa41-138">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

