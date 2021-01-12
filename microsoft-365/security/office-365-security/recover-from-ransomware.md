---
title: Recuperar de um ataque de ransomware
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.article: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os administradores do Microsoft 365 podem aprender a se recuperar de um ataque de ransomware.
ms.openlocfilehash: 753171578dc7b76aefadf4b8587e84320d98b912
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794443"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="78bd4-103">Recuperar-se de um ataque de ransomware no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="78bd4-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="78bd4-104">Mesmo que você tome todas as precauções para proteger sua organização, ainda poderá ser vítima de um ataque [de ransomware.](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)</span><span class="sxs-lookup"><span data-stu-id="78bd4-104">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="78bd4-105">Ransomware é uma grande empresa e os ataques são muito sofisticados.</span><span class="sxs-lookup"><span data-stu-id="78bd4-105">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="78bd4-106">As etapas neste artigo lhe darão a melhor chance de recuperar dados e parar a propagação interna da infecção.</span><span class="sxs-lookup"><span data-stu-id="78bd4-106">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="78bd4-107">Antes de começar, considere os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="78bd4-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="78bd4-108">Não há garantia de que pagar o resgate retornará o acesso aos seus arquivos.</span><span class="sxs-lookup"><span data-stu-id="78bd4-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="78bd4-109">Na verdade, pagar o resgate pode fazer de você um alvo para mais ransomware.</span><span class="sxs-lookup"><span data-stu-id="78bd4-109">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="78bd4-110">Se você já tiver pago, mas se recuperou sem usar a solução do invasor, entre em contato com seu banco para ver se ele pode bloquear a transação.</span><span class="sxs-lookup"><span data-stu-id="78bd4-110">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="78bd4-111">Também recomendamos que você reporte o ataque de ransomware às autoridades, a sites de relatórios de esquema e a Microsoft, conforme descrito mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="78bd4-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="78bd4-112">É importante que você responda rapidamente ao ataque e suas consequências.</span><span class="sxs-lookup"><span data-stu-id="78bd4-112">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="78bd4-113">Quanto mais tempo você aguardar, menos provável será que você possa recuperar os dados afetados.</span><span class="sxs-lookup"><span data-stu-id="78bd4-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="78bd4-114">Etapa 1: verificar seus backups</span><span class="sxs-lookup"><span data-stu-id="78bd4-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="78bd4-115">Se você tiver backups offline, provavelmente poderá  restaurar os dados criptografados depois de remover a carga de ransomware (malware) do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="78bd4-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="78bd4-116">Se você não tiver backups ou se os backups também foram afetados pelo ransomware, ignore esta etapa.</span><span class="sxs-lookup"><span data-stu-id="78bd4-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="78bd4-117">Etapa 2: Desabilitar a sincronização do Exchange ActiveSync e do OneDrive</span><span class="sxs-lookup"><span data-stu-id="78bd4-117">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="78bd4-118">O ponto-chave aqui é interromper a propagação da criptografia de dados pelo ransomware.</span><span class="sxs-lookup"><span data-stu-id="78bd4-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="78bd4-119">Se você suspeitar de email como um destino da criptografia ransomware, desabilite temporariamente o acesso do usuário às caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="78bd4-119">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="78bd4-120">O Exchange ActiveSync sincroniza dados entre dispositivos e caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="78bd4-120">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="78bd4-121">Para desabilitar o Exchange ActiveSync para uma caixa de correio, confira Como desabilitar o [Exchange ActiveSync para usuários no Exchange Online.](https://support.microsoft.com/help/2795303)</span><span class="sxs-lookup"><span data-stu-id="78bd4-121">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="78bd4-122">Para desabilitar outros tipos de acesso a uma caixa de correio, confira:</span><span class="sxs-lookup"><span data-stu-id="78bd4-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="78bd4-123">[Habilitar ou desabilitar MAPI para uma caixa de correio.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)</span><span class="sxs-lookup"><span data-stu-id="78bd4-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="78bd4-124">Habilitar ou desabilitar o acesso POP3 ou IMAP4 para um usuário</span><span class="sxs-lookup"><span data-stu-id="78bd4-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="78bd4-125">Pausar a sincronização do OneDrive ajudará a proteger seus dados de nuvem contra a atualização por dispositivos potencialmente infectados.</span><span class="sxs-lookup"><span data-stu-id="78bd4-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="78bd4-126">Para saber mais, confira [Como pausar e retomar a sincronização no OneDrive.](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)</span><span class="sxs-lookup"><span data-stu-id="78bd4-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="78bd4-127">Etapa 3: Remover o malware dos dispositivos afetados</span><span class="sxs-lookup"><span data-stu-id="78bd4-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="78bd4-128">Execute uma verificação antivírus completa e atual em todos os computadores e dispositivos suspeitos para detectar e remover a carga associada ao ransomware.</span><span class="sxs-lookup"><span data-stu-id="78bd4-128">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="78bd4-129">Não se esqueça de verificar dispositivos que estão sincronizando dados ou os destinos de unidades de rede mapeadas.</span><span class="sxs-lookup"><span data-stu-id="78bd4-129">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="78bd4-130">Você pode usar [o Windows Defender](https://www.microsoft.com/windows/comprehensive-security) ou (para clientes mais antigos) Microsoft Security [Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span><span class="sxs-lookup"><span data-stu-id="78bd4-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="78bd4-131">Uma alternativa que também ajudará você a remover ransomware ou malware é a [MSRT (Ferramenta](https://www.microsoft.com/download/details.aspx?id=9905)de Remoção de Software Mal-intencionado).</span><span class="sxs-lookup"><span data-stu-id="78bd4-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="78bd4-132">Se essas opções não funcionarem, você poderá experimentar o [Windows Defender Offline](https://support.microsoft.com/help/17466) ou solucionar problemas de detecção e [remoção de malware.](https://support.microsoft.com/help/4466982)</span><span class="sxs-lookup"><span data-stu-id="78bd4-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="78bd4-133">Etapa 4: Recuperar arquivos em um computador ou dispositivo limpo</span><span class="sxs-lookup"><span data-stu-id="78bd4-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="78bd4-134">Depois de concluir a etapa anterior para remover a carga de ransomware do seu ambiente (o que impedirá que o ransomware criptografe ou remova seus arquivos), você poderá usar o Histórico de Arquivos no Windows 10 e no Windows 8.1 ou na Proteção do Sistema no Windows 7 para tentar recuperar seus arquivos e pastas locais. [](https://support.microsoft.com/help/17128)</span><span class="sxs-lookup"><span data-stu-id="78bd4-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="78bd4-135">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="78bd4-135">**Notes**:</span></span>

- <span data-ttu-id="78bd4-136">Alguns ransomware também criptografarão ou excluirão as versões de backup, para que você não possa usar o Histórico de Arquivos ou a Proteção do Sistema para restaurar arquivos.</span><span class="sxs-lookup"><span data-stu-id="78bd4-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="78bd4-137">Se isso acontecer, você precisará usar backups em unidades externas ou dispositivos que não foram afetados pelo ransomware ou pelo OneDrive, conforme descrito na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="78bd4-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="78bd4-138">Se uma pasta estiver sincronizada com o OneDrive e você não estiver usando a versão mais recente do Windows, poderá haver algumas limitações usando o Histórico de Arquivos.</span><span class="sxs-lookup"><span data-stu-id="78bd4-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="78bd4-139">Etapa 5: Recuperar seus arquivos no OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="78bd4-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="78bd4-140">A restauração de arquivos no OneDrive for Business permite que você restaure todo o OneDrive para um momento anterior nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="78bd4-140">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="78bd4-141">Para saber mais, confira [Restaurar o OneDrive.](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)</span><span class="sxs-lookup"><span data-stu-id="78bd4-141">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="78bd4-142">Etapa 6: Recuperar emails excluídos</span><span class="sxs-lookup"><span data-stu-id="78bd4-142">Step 6: Recover deleted email</span></span>

<span data-ttu-id="78bd4-143">No caso raro de o ransomware ter excluído todos os seus emails, você provavelmente poderá recuperar os itens excluídos.</span><span class="sxs-lookup"><span data-stu-id="78bd4-143">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="78bd4-144">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="78bd4-144">For more information, see:</span></span>

- [<span data-ttu-id="78bd4-145">Recuperar mensagens excluídas na caixa de correio de um usuário</span><span class="sxs-lookup"><span data-stu-id="78bd4-145">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="78bd4-146">Recuperar itens excluídos no Outlook para Windows</span><span class="sxs-lookup"><span data-stu-id="78bd4-146">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="78bd4-147">Etapa 7: Reabilitar a sincronização do Exchange ActiveSync e do OneDrive</span><span class="sxs-lookup"><span data-stu-id="78bd4-147">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="78bd4-148">Depois de limpar seus computadores e dispositivos e recuperar seus dados, você poderá reabilitar a sincronização do Exchange ActiveSync e do OneDrive que você desabilitou anteriormente na [Etapa 2.](#step-2-disable-exchange-activesync-and-onedrive-sync)</span><span class="sxs-lookup"><span data-stu-id="78bd4-148">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="78bd4-149">Etapa 8 (Opcional): Bloquear a sincronização do OneDrive para extensões de arquivo específicas</span><span class="sxs-lookup"><span data-stu-id="78bd4-149">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="78bd4-150">Depois de recuperar, você pode impedir que os clientes do OneDrive for Business sincroniem os tipos de arquivo que foram afetados por esse ransomware.</span><span class="sxs-lookup"><span data-stu-id="78bd4-150">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="78bd4-151">Para obter mais informações, [consulte Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="78bd4-151">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="78bd4-152">Relatar o ataque</span><span class="sxs-lookup"><span data-stu-id="78bd4-152">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="78bd4-153">Contatar a aplicação da lei</span><span class="sxs-lookup"><span data-stu-id="78bd4-153">Contact law enforcement</span></span>

<span data-ttu-id="78bd4-154">Entre em contato com as agências locais ou federais.</span><span class="sxs-lookup"><span data-stu-id="78bd4-154">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="78bd4-155">Por exemplo, se você estiver nos Estados Unidos, entre em contato com o escritório de campo [local do FEDERAL,](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) ou [Serviço Secreto.](http://www.secretservice.gov/)</span><span class="sxs-lookup"><span data-stu-id="78bd4-155">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="78bd4-156">Enviar um relatório para o site de relatórios de esquema do seu país</span><span class="sxs-lookup"><span data-stu-id="78bd4-156">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="78bd4-157">Os sites de relatórios de esquema fornecem informações sobre como evitar e evitar fraudes.</span><span class="sxs-lookup"><span data-stu-id="78bd4-157">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="78bd4-158">Eles também fornecem mecanismos para relatar se você foi vítima de um esquema.</span><span class="sxs-lookup"><span data-stu-id="78bd4-158">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="78bd4-159">Austrália: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="78bd4-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="78bd4-160">Canadá: [Centro de Antifalsidade do Canadá](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="78bd4-160">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="78bd4-161">França: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="78bd4-161">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="78bd4-162">Alemanha: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="78bd4-162">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="78bd4-163">Irlanda: [an Garda Vouochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="78bd4-163">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="78bd4-164">Nova Zelândia: [esquemas de assuntos do consumidor](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="78bd4-164">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="78bd4-165">Reino Unido: [Fraude de Ação](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="78bd4-165">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="78bd4-166">Estados Unidos: [On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="78bd4-166">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="78bd4-167">Se o seu país não estiver listado, peça às agências de aplicação da lei local ou federal.</span><span class="sxs-lookup"><span data-stu-id="78bd4-167">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="78bd4-168">Enviar mensagens de email para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="78bd4-168">Submit email messages to Microsoft</span></span>

<span data-ttu-id="78bd4-169">Você pode relatar mensagens de phishing que contêm ransomware usando um dos vários métodos.</span><span class="sxs-lookup"><span data-stu-id="78bd4-169">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="78bd4-170">Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="78bd4-170">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="78bd4-171">Confira também</span><span class="sxs-lookup"><span data-stu-id="78bd4-171">See also</span></span>

- [<span data-ttu-id="78bd4-172">Ransomware</span><span class="sxs-lookup"><span data-stu-id="78bd4-172">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="78bd4-173">Resposta a ransomware : para pagar ou não pagar?</span><span class="sxs-lookup"><span data-stu-id="78bd4-173">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="78bd4-174">Norsk Ransomware responde a um ataque de ransomware com transparência</span><span class="sxs-lookup"><span data-stu-id="78bd4-174">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="78bd4-175">Detecção de ransomware e recuperação de arquivos no OneDrive</span><span class="sxs-lookup"><span data-stu-id="78bd4-175">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="78bd4-176">Relatório de Inteligência de Segurança da Microsoft</span><span class="sxs-lookup"><span data-stu-id="78bd4-176">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="78bd4-177">Habilitar ou desabilitar macros em arquivos do Office</span><span class="sxs-lookup"><span data-stu-id="78bd4-177">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="78bd4-178">Configurações recomendadas para o EOP e o Microsoft Defender para segurança do Office 365</span><span class="sxs-lookup"><span data-stu-id="78bd4-178">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365-atp.md)

- [<span data-ttu-id="78bd4-179">Uma atualização valiosa: a segurança da próxima geração no Windows 10 prova a resiliência contra ataques de ransomware em 2017</span><span class="sxs-lookup"><span data-stu-id="78bd4-179">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="78bd4-180">No mas, Samas: What's in this ransomware's mmodo operandi?</span><span class="sxs-lookup"><span data-stu-id="78bd4-180">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="78bd4-181">Malware locky, para evitar</span><span class="sxs-lookup"><span data-stu-id="78bd4-181">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="78bd4-182">MSRT julho de 2016: Ransomware cerber</span><span class="sxs-lookup"><span data-stu-id="78bd4-182">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="78bd4-183">Os três heads of the Cerberus-like Cerber ransomware</span><span class="sxs-lookup"><span data-stu-id="78bd4-183">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="78bd4-184">Ransomware Trol ransomware influenciado por (o) código Da Vinci</span><span class="sxs-lookup"><span data-stu-id="78bd4-184">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
