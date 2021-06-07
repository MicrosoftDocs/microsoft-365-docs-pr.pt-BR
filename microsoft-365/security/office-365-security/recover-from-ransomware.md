---
title: Recuperar de um ataque de ransomware
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365 administradores podem aprender a se recuperar de um ataque de ransomware.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 473591a02b78043153d505dda6dd7ef5ac6e3961
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789046"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="9d0e3-103">Recuperar de um ataque de ransomware no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d0e3-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9d0e3-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="9d0e3-104">**Applies to**</span></span>
- [<span data-ttu-id="9d0e3-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9d0e3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9d0e3-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="9d0e3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9d0e3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9d0e3-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="9d0e3-108">Mesmo que você tome todas as precauções para proteger sua organização, ainda poderá ser vítima de um ataque [de ransomware.](/windows/security/threat-protection/intelligence/ransomware-malware)</span><span class="sxs-lookup"><span data-stu-id="9d0e3-108">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="9d0e3-109">O ransomware é uma grande empresa e os ataques são muito sofisticados.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-109">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="9d0e3-110">As etapas deste artigo darão a você a melhor chance de recuperar dados e interromper a propagação interna da infecção.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-110">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="9d0e3-111">Antes de começar, considere os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="9d0e3-111">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="9d0e3-112">Não há garantias de que pagar o resgate retornará o acesso aos arquivos.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-112">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="9d0e3-113">Na verdade, pagar o resgate pode torná-lo um alvo para mais ransomware.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-113">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="9d0e3-114">Se você já pagou, mas se recuperou sem usar a solução do invasor, entre em contato com seu banco para ver se ele pode bloquear a transação.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-114">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="9d0e3-115">Também recomendamos que você reporte o ataque de ransomware à aplicação da lei, aos sites de relatórios de fraude e à Microsoft, conforme descrito posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-115">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="9d0e3-116">É importante que você responda rapidamente ao ataque e suas consequências.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-116">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="9d0e3-117">Quanto mais tempo você esperar, menor será a probabilidade de recuperar os dados afetados.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-117">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="9d0e3-118">Etapa 1: Verificar seus backups</span><span class="sxs-lookup"><span data-stu-id="9d0e3-118">Step 1: Verify your backups</span></span>

<span data-ttu-id="9d0e3-119">Se você tiver backups offline, provavelmente poderá  restaurar os dados criptografados depois de remover a carga de ransomware (malware) do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-119">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="9d0e3-120">Se você não tiver backups ou se seus backups também foram afetados pelo ransomware, você pode ignorar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-120">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="9d0e3-121">Etapa 2: Desabilitar Exchange ActiveSync e OneDrive sincronização</span><span class="sxs-lookup"><span data-stu-id="9d0e3-121">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="9d0e3-122">O ponto chave aqui é parar a propagação da criptografia de dados pelo ransomware.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-122">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="9d0e3-123">Se você suspeitar de email como um destino da criptografia de ransomware, desabilite temporariamente o acesso do usuário às caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-123">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="9d0e3-124">Exchange ActiveSync sincroniza dados entre dispositivos e Exchange Online caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-124">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="9d0e3-125">Para desabilitar Exchange ActiveSync para uma caixa de correio, consulte [Como desabilitar](https://support.microsoft.com/help/2795303)o Exchange ActiveSync para usuários em Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="9d0e3-125">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="9d0e3-126">Para desabilitar outros tipos de acesso a uma caixa de correio, consulte:</span><span class="sxs-lookup"><span data-stu-id="9d0e3-126">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="9d0e3-127">[Habilitar ou desabilitar MAPI para uma caixa de correio](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span><span class="sxs-lookup"><span data-stu-id="9d0e3-127">[Enable or disable MAPI for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="9d0e3-128">Habilitar ou desabilitar o acesso POP3 ou IMAP4 para um usuário</span><span class="sxs-lookup"><span data-stu-id="9d0e3-128">Enable or Disable POP3 or IMAP4 access for a user</span></span>](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="9d0e3-129">Pausar OneDrive sincronização ajudará a proteger seus dados de nuvem contra serem atualizados por dispositivos potencialmente infectados.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-129">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="9d0e3-130">Para obter mais informações, [consulte How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span><span class="sxs-lookup"><span data-stu-id="9d0e3-130">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="9d0e3-131">Etapa 3: Remover o malware dos dispositivos afetados</span><span class="sxs-lookup"><span data-stu-id="9d0e3-131">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="9d0e3-132">Execute uma verificação completa e atual do antivírus em todos os computadores e dispositivos suspeitos para detectar e remover a carga associada ao ransomware.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-132">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="9d0e3-133">Não se esqueça de examinar dispositivos que estão sincronizando dados ou os destinos de unidades de rede mapeadas.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-133">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="9d0e3-134">Você pode usar [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) ou (para clientes mais antigos) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span><span class="sxs-lookup"><span data-stu-id="9d0e3-134">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="9d0e3-135">Uma alternativa que também ajudará você a remover ransomware ou malware é a Ferramenta de Remoção de Software Mal-Intencionado [(MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)</span><span class="sxs-lookup"><span data-stu-id="9d0e3-135">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="9d0e3-136">Se essas opções não funcionarem, você poderá tentar Windows Defender [offline](https://support.microsoft.com/help/17466) ou solucionar problemas com a detecção e [a remoção de malware.](https://support.microsoft.com/help/4466982)</span><span class="sxs-lookup"><span data-stu-id="9d0e3-136">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="9d0e3-137">Etapa 4: Recuperar arquivos em um computador ou dispositivo limpo</span><span class="sxs-lookup"><span data-stu-id="9d0e3-137">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="9d0e3-138">Depois de concluir a etapa anterior para remover a carga de ransomware do seu ambiente (o que impedirá que o ransomware criptografe ou remova seus arquivos), você poderá usar o Histórico de Arquivos no Windows 10 e Windows 8.1 ou Proteção do Sistema no Windows 7 para tentar recuperar seus arquivos e pastas locais. [](https://support.microsoft.com/help/17128)</span><span class="sxs-lookup"><span data-stu-id="9d0e3-138">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="9d0e3-139">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="9d0e3-139">**Notes**:</span></span>

- <span data-ttu-id="9d0e3-140">Alguns ransomware também criptografarão ou excluirão as versões de backup, para que você não possa usar o Histórico de Arquivos ou a Proteção do Sistema para restaurar arquivos.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-140">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="9d0e3-141">Se isso acontecer, você precisará usar backups em unidades externas ou dispositivos que não foram afetados pelo ransomware ou OneDrive conforme descrito na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-141">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="9d0e3-142">Se uma pasta for sincronizada com OneDrive e você não estiver usando a versão mais recente do Windows, pode haver algumas limitações usando o Histórico de Arquivos.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-142">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="9d0e3-143">Etapa 5: Recuperar seus arquivos em sua OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="9d0e3-143">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="9d0e3-144">A restauração de arquivos OneDrive for Business permite que você restaure todo o OneDrive para um ponto de tempo anterior nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-144">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="9d0e3-145">Para obter mais informações, consulte [Restaurar OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span><span class="sxs-lookup"><span data-stu-id="9d0e3-145">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="9d0e3-146">Etapa 6: Recuperar emails excluídos</span><span class="sxs-lookup"><span data-stu-id="9d0e3-146">Step 6: Recover deleted email</span></span>

<span data-ttu-id="9d0e3-147">No caso raro de o ransomware ter excluído todos os emails, você provavelmente poderá recuperar os itens excluídos.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-147">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="9d0e3-148">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="9d0e3-148">For more information, see:</span></span>

- [<span data-ttu-id="9d0e3-149">Recuperar mensagens excluídas na caixa de correio de um usuário</span><span class="sxs-lookup"><span data-stu-id="9d0e3-149">Recover deleted messages in a user's mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="9d0e3-150">Recuperar itens excluídos no Outlook para Windows</span><span class="sxs-lookup"><span data-stu-id="9d0e3-150">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="9d0e3-151">Etapa 7: Habilitar Exchange ActiveSync sincronização OneDrive sincronização</span><span class="sxs-lookup"><span data-stu-id="9d0e3-151">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="9d0e3-152">Depois de limpar seus computadores e dispositivos e recuperar seus dados, você poderá habilitar Exchange ActiveSync e OneDrive sincronização que você desabilitou anteriormente na [Etapa 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span><span class="sxs-lookup"><span data-stu-id="9d0e3-152">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="9d0e3-153">Etapa 8 (Opcional): Bloquear OneDrive sincronização para extensões de arquivo específicas</span><span class="sxs-lookup"><span data-stu-id="9d0e3-153">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="9d0e3-154">Após a recuperação, você pode impedir que OneDrive for Business clientes sincronem os tipos de arquivo afetados por esse ransomware.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-154">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="9d0e3-155">Para obter mais informações, [consulte Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="9d0e3-155">For more information, see [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="9d0e3-156">Relatar o ataque</span><span class="sxs-lookup"><span data-stu-id="9d0e3-156">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="9d0e3-157">Contatar a aplicação da lei</span><span class="sxs-lookup"><span data-stu-id="9d0e3-157">Contact law enforcement</span></span>

<span data-ttu-id="9d0e3-158">Entre em contato com suas agências de aplicação da lei local ou federal.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-158">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="9d0e3-159">Por exemplo, se você estiver nos Estados Unidos, poderá entrar em contato com o escritório de campo local do [FBI,](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) ou [Serviço Secreto.](http://www.secretservice.gov/)</span><span class="sxs-lookup"><span data-stu-id="9d0e3-159">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="9d0e3-160">Enviar um relatório para o site de relatórios de fraude do seu país</span><span class="sxs-lookup"><span data-stu-id="9d0e3-160">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="9d0e3-161">Os sites de relatórios de fraude fornecem informações sobre como evitar e evitar fraudes.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-161">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="9d0e3-162">Eles também fornecem mecanismos para relatar se você foi vítima de fraude.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-162">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="9d0e3-163">Austrália: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="9d0e3-163">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="9d0e3-164">Canadá: [Centro Antifrafra do Canadá](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="9d0e3-164">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="9d0e3-165">França: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="9d0e3-165">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="9d0e3-166">Alemanha: [Bundesamt für Sicherheit no der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="9d0e3-166">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="9d0e3-167">Irlanda: [An Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="9d0e3-167">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="9d0e3-168">Nova Zelândia: [Esquemas de Casos de Consumidor](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="9d0e3-168">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="9d0e3-169">Nacionales [da Suíça Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)</span><span class="sxs-lookup"><span data-stu-id="9d0e3-169">Switzerland [Nationales Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)</span></span>

- <span data-ttu-id="9d0e3-170">Reino Unido: [Fraude de Ação](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="9d0e3-170">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="9d0e3-171">Estados Unidos: [On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="9d0e3-171">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="9d0e3-172">Se seu país não estiver listado, pergunte às agências de aplicação da lei local ou federal.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-172">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="9d0e3-173">Enviar mensagens de email para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="9d0e3-173">Submit email messages to Microsoft</span></span>

<span data-ttu-id="9d0e3-174">Você pode relatar mensagens de phishing que contêm ransomware usando um dos vários métodos.</span><span class="sxs-lookup"><span data-stu-id="9d0e3-174">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="9d0e3-175">Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="9d0e3-175">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9d0e3-176">Confira também</span><span class="sxs-lookup"><span data-stu-id="9d0e3-176">See also</span></span>

- [<span data-ttu-id="9d0e3-177">Ransomware</span><span class="sxs-lookup"><span data-stu-id="9d0e3-177">Ransomware</span></span>](/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="9d0e3-178">Resposta ao ransomware para pagar ou não pagar?</span><span class="sxs-lookup"><span data-stu-id="9d0e3-178">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="9d0e3-179">O Norsk Hydro responde ao ataque de ransomware com transparência</span><span class="sxs-lookup"><span data-stu-id="9d0e3-179">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="9d0e3-180">Detecção e recuperação de ransomware em OneDrive</span><span class="sxs-lookup"><span data-stu-id="9d0e3-180">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="9d0e3-181">Inteligência de Segurança da Microsoft Relatório</span><span class="sxs-lookup"><span data-stu-id="9d0e3-181">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="9d0e3-182">Habilitar ou desabilitar macros em Office arquivos</span><span class="sxs-lookup"><span data-stu-id="9d0e3-182">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="9d0e3-183">Configurações recomendadas para o EOP e o Microsoft Defender para Office 365 segurança</span><span class="sxs-lookup"><span data-stu-id="9d0e3-183">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365.md)

- [<span data-ttu-id="9d0e3-184">Uma atualização valiosa: a segurança de próxima geração no Windows 10 se mostra resiliente contra surtos de ransomware em 2017</span><span class="sxs-lookup"><span data-stu-id="9d0e3-184">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="9d0e3-185">Sem massa, Samas: O que há no modus operandi desse ransomware?</span><span class="sxs-lookup"><span data-stu-id="9d0e3-185">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="9d0e3-186">Malware locky, sorte de evitá-lo</span><span class="sxs-lookup"><span data-stu-id="9d0e3-186">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="9d0e3-187">MSRT julho de 2016: ransomware cerber</span><span class="sxs-lookup"><span data-stu-id="9d0e3-187">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="9d0e3-188">As três cabeças do ransomware Cerberus-like</span><span class="sxs-lookup"><span data-stu-id="9d0e3-188">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="9d0e3-189">Ransomware Troldesh influenciado pelo (o) código Da Vinci</span><span class="sxs-lookup"><span data-stu-id="9d0e3-189">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
