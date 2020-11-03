---
title: Recuperar de um ataque de ransomware
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Os administradores do Microsoft 365 podem aprender a se recuperar de um ataque de ransomware.
ms.openlocfilehash: dd740b19abac9d30196c1ffd82c8a3f377b19dbf
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845535"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="dfbb8-103">Recuperar de um ataque de ransomware no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dfbb8-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="dfbb8-104">Mesmo que você tenha cuidado para proteger sua organização, ainda pode ser vítima de um ataque de [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) .</span><span class="sxs-lookup"><span data-stu-id="dfbb8-104">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="dfbb8-105">O ransomware é grande negócio, e os ataques são sofisticados.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-105">Ransomware is big business, and the attacks are verify sophisticated.</span></span>

<span data-ttu-id="dfbb8-106">As etapas deste tópico lhe dão a melhor chance de recuperar os dados que foram criptografados pelo ransomware e ajudarão a parar a disseminação da infecção em sua organização.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-106">The steps in this topic will give you the best chance to recover data that was encrypted by the ransomware, and will help stop the spread of the infection in your organization.</span></span> <span data-ttu-id="dfbb8-107">Antes de começar, considere os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="dfbb8-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="dfbb8-108">Não há garantias de que o pagamento do resgate retornará o acesso aos seus arquivos.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="dfbb8-109">Na verdade, o pagamento do resgate pode ser um alvo para mais ransomware.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-109">In fact, paying the ransom can make you a target for more ransomware.</span></span> <span data-ttu-id="dfbb8-110">Se você já pagou, mas você conseguiu recuperar seus arquivos com êxito sem precisar usar a resolução do invasor, ligue para o seu banco para ver se eles podem bloquear a transação.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-110">If you've already paid, but you were able to successfully recover your files without having to use the attacker's resolution, you should call your bank to see if they can block the transaction.</span></span> <span data-ttu-id="dfbb8-111">Recomendamos também que você informe o ataque de ransomware à imposição de leis, sites de relatórios de scam e a Microsoft, conforme descrito mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites and Microsoft as described later in this topic.</span></span>

- <span data-ttu-id="dfbb8-112">É muito importante que você responda rapidamente ao ataque e às suas conseqüências.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-112">It's very important that you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="dfbb8-113">Quanto mais tempo você espera, menos provável é que você possa recuperar os dados afetados.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="dfbb8-114">Etapa 1: verificar seus backups</span><span class="sxs-lookup"><span data-stu-id="dfbb8-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="dfbb8-115">Se você tiver backups offline, provavelmente poderá restaurar os dados criptografados **depois** de ter removido a carga de ransomware (malware) de seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="dfbb8-116">Se você não tiver backups ou se os backups também foram afetados pelo ransomware, ignore esta etapa.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-activesync-and-onedrive-sync"></a><span data-ttu-id="dfbb8-117">Etapa 2: desabilitar a sincronização do ActiveSync e do OneDrive</span><span class="sxs-lookup"><span data-stu-id="dfbb8-117">Step 2: Disable ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="dfbb8-118">O ponto principal aqui é interromper a propagação da criptografia de dados pelo ransomware.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="dfbb8-119">Se você suspeita que o email é um destino, você deve desabilitar temporariamente o acesso do usuário às caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-119">If you suspect that email is a target, you should temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="dfbb8-120">O Exchange ActiveSync é usado por dispositivos móveis para sincronizar dados entre o dispositivo e a caixa de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-120">Exchange ActiveSync is used by mobile devices to synchronize data between the device and the Exchange Online mailbox.</span></span>

<span data-ttu-id="dfbb8-121">Para desabilitar o ActiveSync para uma caixa de correio, confira [como desabilitar o Exchange ActiveSync para usuários no Exchange Online](https://support.microsoft.com/help/2795303).</span><span class="sxs-lookup"><span data-stu-id="dfbb8-121">To disable ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="dfbb8-122">Para desabilitar outros tipos de acesso a uma caixa de correio, confira:</span><span class="sxs-lookup"><span data-stu-id="dfbb8-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="dfbb8-123">[Habilitar ou desabilitar o MAPI para uma caixa de correio](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span><span class="sxs-lookup"><span data-stu-id="dfbb8-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="dfbb8-124">Habilitar ou desabilitar o acesso POP3 ou IMAP4 para um usuário</span><span class="sxs-lookup"><span data-stu-id="dfbb8-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="dfbb8-125">Pausar o OneDrive Sync ajudará a proteger os dados da nuvem contra a atualização de dispositivos potencialmente infectados.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="dfbb8-126">Para obter mais informações, consulte [como pausar e retomar a sincronização no onedrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span><span class="sxs-lookup"><span data-stu-id="dfbb8-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="dfbb8-127">Etapa 3: remover o malware dos dispositivos afetados</span><span class="sxs-lookup"><span data-stu-id="dfbb8-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="dfbb8-128">Execute uma verificação antivírus completa com as atualizações mais recentes em todos os computadores e dispositivos suspeitos para detectar e remover a carga associada ao ransomware.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-128">Run a full antivirus scan with the latest updates on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span> <span data-ttu-id="dfbb8-129">Não esqueça dispositivos que estão sincronizando dados ou o destino de unidades de rede mapeadas (esses computadores e dispositivos precisam ser verificados também).</span><span class="sxs-lookup"><span data-stu-id="dfbb8-129">Don't forget devices that are synchronizing data, or the target of mapped network drives (those computers and devices need to be scanned, too).</span></span>

<span data-ttu-id="dfbb8-130">Você pode usar o [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) ou (para clientes mais antigos) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span><span class="sxs-lookup"><span data-stu-id="dfbb8-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="dfbb8-131">Uma alternativa que também ajudará você a remover o ransomware ou malware é a [ferramenta de remoção de software mal-intencionado (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span><span class="sxs-lookup"><span data-stu-id="dfbb8-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="dfbb8-132">Se essas opções não funcionarem, você poderá experimentar o [Windows Defender offline](https://support.microsoft.com/help/17466) ou [solucionar problemas com a detecção e remoção de malware](https://support.microsoft.com/help/4466982).</span><span class="sxs-lookup"><span data-stu-id="dfbb8-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="dfbb8-133">Etapa 4: recuperar arquivos em um computador ou dispositivo limpo</span><span class="sxs-lookup"><span data-stu-id="dfbb8-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="dfbb8-134">Após concluir a etapa anterior para remover a carga de ransomware do seu ambiente (que impedirá que o ransomware Criptografe ou remova seus arquivos), você poderá usar o histórico de [arquivos](https://support.microsoft.com/help/17128) no Windows 10 e no Windows 8,1 ou na proteção do sistema no Windows 7 para tentar recuperar seus arquivos e pastas locais.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="dfbb8-135">**Observações** :</span><span class="sxs-lookup"><span data-stu-id="dfbb8-135">**Notes** :</span></span>

- <span data-ttu-id="dfbb8-136">Um ransomware também criptografará ou excluirá as versões de backup, portanto, não será possível usar o histórico de arquivos ou a proteção do sistema para restaurar arquivos.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="dfbb8-137">Se isso acontecer, você precisará usar backups em unidades ou dispositivos externos que não foram afetados pelo ransomware ou pelo OneDrive, conforme descrito na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="dfbb8-138">Se uma pasta for sincronizada com o OneDrive e você não estiver usando a versão mais recente do Windows, pode haver algumas limitações usando o histórico de arquivos.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="dfbb8-139">Etapa 5: recuperar seus arquivos no OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="dfbb8-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="dfbb8-140">Arquivos Restore in OneDrive for Business permite restaurar todo o OneDrive para um ponto anterior no tempo nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-140">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="dfbb8-141">Para obter mais informações, consulte [Restore Your onedrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span><span class="sxs-lookup"><span data-stu-id="dfbb8-141">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="dfbb8-142">Etapa 6: recuperar emails excluídos</span><span class="sxs-lookup"><span data-stu-id="dfbb8-142">Step 6: Recover deleted email</span></span>

<span data-ttu-id="dfbb8-143">No caso raro em que o ransomware excluiu todos os seus emails, provavelmente você poderá recuperar os itens excluídos.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-143">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="dfbb8-144">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="dfbb8-144">For more information, see:</span></span>

- [<span data-ttu-id="dfbb8-145">Recuperar mensagens excluídas na caixa de correio de um usuário</span><span class="sxs-lookup"><span data-stu-id="dfbb8-145">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="dfbb8-146">Recuperar itens excluídos no Outlook para Windows</span><span class="sxs-lookup"><span data-stu-id="dfbb8-146">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="dfbb8-147">Etapa 7: reabilitar a sincronização do Exchange ActiveSync e do OneDrive</span><span class="sxs-lookup"><span data-stu-id="dfbb8-147">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="dfbb8-148">Depois de limpar seus computadores e dispositivos e recuperar seus dados, você pode reabilitar o ActiveSync e a sincronização do OneDrive que você desabilitou anteriormente na [etapa 2](#step-2-disable-activesync-and-onedrive-sync).</span><span class="sxs-lookup"><span data-stu-id="dfbb8-148">After you've cleaned your computers and devices and recovered your data, you can re-enable ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="dfbb8-149">Etapa 8 (opcional): bloquear a sincronização do OneDrive para extensões de arquivo específicas</span><span class="sxs-lookup"><span data-stu-id="dfbb8-149">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="dfbb8-150">Após a recuperação, você pode impedir que clientes do OneDrive for Business sincronizem os tipos de arquivo que foram afetados por esse ransomware.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-150">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="dfbb8-151">Para obter mais informações, consulte [set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="dfbb8-151">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="dfbb8-152">Relatar o ataque</span><span class="sxs-lookup"><span data-stu-id="dfbb8-152">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="dfbb8-153">Cumprimento de leis de contato</span><span class="sxs-lookup"><span data-stu-id="dfbb8-153">Contact law enforcement</span></span>

<span data-ttu-id="dfbb8-154">Você deve entrar em contato com suas agências de cumprimento de leis local ou federal.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-154">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="dfbb8-155">Por exemplo, se estiver nos Estados Unidos, você pode entrar em contato com o [campo local do FBI](https://www.fbi.gov/contact-us/field), o [ic3](http://www.ic3.gov/complaint/default.aspx) ou o [serviço secreto](http://www.secretservice.gov/).</span><span class="sxs-lookup"><span data-stu-id="dfbb8-155">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="dfbb8-156">Enviar um relatório para o site de relatório de scam do seu país</span><span class="sxs-lookup"><span data-stu-id="dfbb8-156">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="dfbb8-157">Os sites de relatórios de scam fornecem informações sobre como prevenir e evitar golpes.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-157">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="dfbb8-158">Eles também fornecem mecanismos para relatar se você é vítima de scam.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-158">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="dfbb8-159">Austrália: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="dfbb8-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="dfbb8-160">Canadá: [Centro antifraude canadense](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="dfbb8-160">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="dfbb8-161">França: [Agence Nationale de la Sécurité des Systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="dfbb8-161">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="dfbb8-162">Alemanha: [Bundesamt für Sicherheit em der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="dfbb8-162">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="dfbb8-163">Irlanda: [um Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="dfbb8-163">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="dfbb8-164">Nova Zelândia: [golpes do consumidor](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="dfbb8-164">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="dfbb8-165">Reino Unido: [fraude de ação](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="dfbb8-165">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="dfbb8-166">Estados Unidos: [no protetor online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="dfbb8-166">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="dfbb8-167">Se o seu país não estiver listado, pergunte às agências de cumprimento de leis local ou federal.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-167">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="dfbb8-168">Enviar mensagens de email para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="dfbb8-168">Submit email messages to Microsoft</span></span>

<span data-ttu-id="dfbb8-169">É possível relatar mensagens de phishing que contenham ransomware usando um dos vários métodos.</span><span class="sxs-lookup"><span data-stu-id="dfbb8-169">You can report phishing message that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="dfbb8-170">Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="dfbb8-170">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dfbb8-171">Confira também</span><span class="sxs-lookup"><span data-stu-id="dfbb8-171">See also</span></span>

- [<span data-ttu-id="dfbb8-172">Ransomware</span><span class="sxs-lookup"><span data-stu-id="dfbb8-172">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="dfbb8-173">Resposta de ransomware — para pagar ou não?</span><span class="sxs-lookup"><span data-stu-id="dfbb8-173">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="dfbb8-174">Norsk Hydro responde a ataques de ransomware com transparência</span><span class="sxs-lookup"><span data-stu-id="dfbb8-174">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="dfbb8-175">Detecção de ransomware e recuperação de seus arquivos no OneDrive</span><span class="sxs-lookup"><span data-stu-id="dfbb8-175">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="dfbb8-176">Relatório de inteligência de segurança da Microsoft</span><span class="sxs-lookup"><span data-stu-id="dfbb8-176">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="dfbb8-177">Habilitar ou desabilitar macros em arquivos do Office</span><span class="sxs-lookup"><span data-stu-id="dfbb8-177">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="dfbb8-178">Configurações recomendadas para a segurança do EOP e do Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="dfbb8-178">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [<span data-ttu-id="dfbb8-179">Uma atualização valioso: a segurança da próxima geração no Windows 10 comprova resistente contra epidemias de ransomware no 2017</span><span class="sxs-lookup"><span data-stu-id="dfbb8-179">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="dfbb8-180">Nenhum mas, Samas: o que há no modus operando do ransomware?</span><span class="sxs-lookup"><span data-stu-id="dfbb8-180">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="dfbb8-181">Malware com proteção, sorte de evitá-la</span><span class="sxs-lookup"><span data-stu-id="dfbb8-181">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="dfbb8-182">MSRT de julho de 2016: cerber ransomware</span><span class="sxs-lookup"><span data-stu-id="dfbb8-182">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="dfbb8-183">Os três cabeçalhos do ransomware Cerberus-like cerber</span><span class="sxs-lookup"><span data-stu-id="dfbb8-183">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="dfbb8-184">Ransomware Troldesh influenciado por (o) da Vinci de código</span><span class="sxs-lookup"><span data-stu-id="dfbb8-184">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
