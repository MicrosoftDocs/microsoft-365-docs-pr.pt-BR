---
title: Mover um site do OneDrive para um local geográfico diferente
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Encontre informações sobre como mover um site do OneDrive para um local geográfico diferente, incluindo como agendar movimentações de site e expectativas de comunicação para os usuários.
ms.openlocfilehash: 59b3fb47fd195967e7af056c7a71fb4e736471d1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686895"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a><span data-ttu-id="6025e-103">Mover um site do OneDrive para um local geográfico diferente</span><span class="sxs-lookup"><span data-stu-id="6025e-103">Move a OneDrive site to a different geo location</span></span> 

<span data-ttu-id="6025e-p101">Com a movimentação geográfica do OneDrive, você pode mover o OneDrive de um usuário para um local geográfico diferente. A movimentação geográfica do OneDrive é executada pelo administrador do SharePoint Online ou pelo administrador global do Microsoft 365. Antes de iniciar uma movimentação geográfica do OneDrive, lembre-se de notificar o usuário de que o OneDrive está sendo movido e recomenda que eles fechem todos os arquivos durante a movimentação. (Se o usuário tiver um documento aberto usando o cliente do Office durante a movimentação, após a conclusão da movimentação, o documento precisará ser salvo no novo local.) A movimentação pode ser agendada para um momento futuro, se desejado.</span><span class="sxs-lookup"><span data-stu-id="6025e-p101">With OneDrive geo move, you can move a user's OneDrive to a different geo location. OneDrive geo move is performed by the SharePoint Online administrator or the Microsoft 365 global administrator. Before you start a OneDrive geo move, be sure to notify the user whose OneDrive is being moved and recommend they close all files for the duration of the move. (If the user has a document open using the Office client during the move, then upon move completion the document will need to be saved to the new location.) The move can be scheduled for a future time, if desired.</span></span>

<span data-ttu-id="6025e-p102">O serviço do OneDrive usa o armazenamento de blob do Azure para armazenar conteúdo. O blob de armazenamento associado ao OneDrive do usuário será movido da origem para a localização geográfica de destino em 40 dias de destino do OneDrive que estão sendo disponibilizados para o usuário. O acesso ao OneDrive do usuário será restaurado assim que o OneDrive de destino estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="6025e-p102">The OneDrive service uses Azure Blob Storage to store content. The Storage blob associated with the user's OneDrive will be moved from the source to destination geo location within 40 days of destination OneDrive being available to the user. The access to the user's OneDrive will be restored as soon as the destination OneDrive is available.</span></span>

<span data-ttu-id="6025e-p103">Durante a janela de movimentação geográfica do OneDrive (entre 2 e 6 horas), o OneDrive do usuário é definido como somente leitura. O usuário ainda pode acessar os arquivos pelo cliente de sincronização do OneDrive ou pelo site do OneDrive no SharePoint Online. Após a conclusão da movimentação geográfica do OneDrive, o usuário será automaticamente conectado ao seu OneDrive na localização geográfica destinada quando navegar para o OneDrive no inicializador de aplicativos do Microsoft 365. O cliente de sincronização começará automaticamente a sincronizar do novo local.</span><span class="sxs-lookup"><span data-stu-id="6025e-p103">During OneDrive geo move window (about 2-6 hours) the user's OneDrive is set to read-only. The user can still access their files via the OneDrive sync client or their OneDrive site in SharePoint Online. After OneDrive geo move is complete, the user will be automatically connected to their OneDrive at the destination geo location when they navigate to OneDrive in the Microsoft 365 app launcher. The sync client will automatically begin syncing from the new location.</span></span>

<span data-ttu-id="6025e-115">Os procedimentos deste artigo exigem o [Módulo PowerShell do Microsoft SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588).</span><span class="sxs-lookup"><span data-stu-id="6025e-115">The procedures in this article require the [Microsoft SharePoint Online PowerShell Module](https://www.microsoft.com/download/details.aspx?id=35588).</span></span>

## <a name="communicating-to-your-users"></a><span data-ttu-id="6025e-116">Comunicação com seus usuários</span><span class="sxs-lookup"><span data-stu-id="6025e-116">Communicating to your users</span></span>

<span data-ttu-id="6025e-p104">Ao mover os sites do OneDrive entre locais geográficos, é importante comunicar aos seus usuários o que esperar. Isso pode ajudar a reduzir a confusão do usuário e chamadas para o suporte técnico. Envie um email para seus usuários antes de fazer as movimentações com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="6025e-p104">When moving OneDrive sites between geo locations, it's important to communicate to your users what to expect. This can help reduce user confusion and calls to your help desk. Email your users before the move and let them know the following information:</span></span>

- <span data-ttu-id="6025e-120">Quando a mudança deve começar e quanto tempo deve demorar</span><span class="sxs-lookup"><span data-stu-id="6025e-120">When the move is expected to start and how long it is expected to take</span></span>
- <span data-ttu-id="6025e-121">Para qual localização geográfica o OneDrive mudará, e qual é a URL para acessar o novo local</span><span class="sxs-lookup"><span data-stu-id="6025e-121">What geo location their OneDrive is moving to, and the URL to access the new location</span></span>
- <span data-ttu-id="6025e-122">Eles devem fechar os arquivos e não fazer edições durante a mudança.</span><span class="sxs-lookup"><span data-stu-id="6025e-122">They should close their files and not make edits during the move.</span></span>
- <span data-ttu-id="6025e-123">O compartilhamento e permissões de arquivo não mudarão devido a mudança.</span><span class="sxs-lookup"><span data-stu-id="6025e-123">File permissions and sharing will not change as a result of the move.</span></span>
- <span data-ttu-id="6025e-124">O que esperar da [experiência do usuário em um ambiente multigeográfico](multi-geo-user-experience.md)</span><span class="sxs-lookup"><span data-stu-id="6025e-124">What to expect from the [user experience in a multi-geo environment](multi-geo-user-experience.md)</span></span>

<span data-ttu-id="6025e-125">Após a conclusão da mudança, envie um email aos seus usuários informando que eles podem continuar a trabalhar com o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6025e-125">Be sure to send your users an email when the move has successfully completed informing them that they can resume working in OneDrive.</span></span>

## <a name="scheduling-onedrive-site-moves"></a><span data-ttu-id="6025e-126">Agendar movimentações do site do OneDrive</span><span class="sxs-lookup"><span data-stu-id="6025e-126">Scheduling OneDrive site moves</span></span>

<span data-ttu-id="6025e-p105">Você pode agendar as movimentações de site do OneDrive com antecedência (conforme descrito posteriormente neste artigo). Recomendamos começar com um pequeno número de usuários para validar seus fluxos de trabalho e estratégias de comunicação. Quando você estiver familiarizado com o processo, poderá agendar as movimentações da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="6025e-p105">You can schedule OneDrive site moves in advance (described later in this article). We recommend that you start with a small number of users to validate your workflows and communication strategies. Once you are comfortable with the process, you can schedule moves as follows:</span></span>

- <span data-ttu-id="6025e-130">Você pode agendar até 4.000 movimentações por vez.</span><span class="sxs-lookup"><span data-stu-id="6025e-130">You can schedule up to 4,000 moves at a time.</span></span>
- <span data-ttu-id="6025e-131">Conforme a movimentação se inicia, você pode agendar mais, com no máximo 4.000 movimentações pendentes na fila e a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="6025e-131">As the moves begin, you can schedule more, with a maximum of 4,000 pending moves in the queue and any given time.</span></span>
- <span data-ttu-id="6025e-132">O tamanho máximo de um OneDrive que pode ser movido é de 1 terabyte (1 TB)</span><span class="sxs-lookup"><span data-stu-id="6025e-132">The maximum size of a OneDrive that can be moved is 1 terabyte (1 TB).</span></span>

## <a name="moving-a-onedrive-site"></a><span data-ttu-id="6025e-133">Mover um site do OneDrive</span><span class="sxs-lookup"><span data-stu-id="6025e-133">Moving a OneDrive site</span></span>

<span data-ttu-id="6025e-p106">Para executar uma movimentação geográfica do OneDrive, o administrador do locatário deve primeiro definir o local de dados preferencial do usuário (PDL) para o local geográfico apropriado. Depois que a PDL estiver definida, aguarde pelo menos 24 horas para que a atualização da PDL seja sincronizada nos locais geográficos antes de iniciar a movimentação geográfica do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6025e-p106">To perform a OneDrive geo move, the tenant administrator must first set the user's Preferred Data Location (PDL) to the appropriate geo location. Once the PDL is set, wait for at least 24 hours for the PDL update to sync across the geo locations before starting the OneDrive geo move.</span></span>

<span data-ttu-id="6025e-136">Ao usar os cmdlets de movimentação geográfica, conecte-se ao serviço SPO na localização geográfica atual do OneDrive do usuário, usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="6025e-136">When using the geo move cmdlets, connect to SPO Service at the user's current OneDrive geo location, using the following syntax:</span></span>

`Connect-SPOService -url https://<tenantName>-admin.sharepoint.com`

<span data-ttu-id="6025e-137">Por exemplo: para mover o OneDrive do usuário ' Matt@contosoenergy.onmicrosoft.com ', conecte-se ao centro de administração do SharePoint EUR, pois o OneDrive do usuário está na localização geográfica EUR:</span><span class="sxs-lookup"><span data-stu-id="6025e-137">For example: To move OneDrive of user 'Matt@contosoenergy.onmicrosoft.com', connect to EUR SharePoint Admin center as the user's OneDrive is in EUR geo location:</span></span>

`Connect-SPOSservice -url https://contosoenergyeur-admin.sharepoint.com`

![Captura de tela da janela do PowerShell mostrando o cmdlet connect-sposervice](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a><span data-ttu-id="6025e-139">Validar o ambiente</span><span class="sxs-lookup"><span data-stu-id="6025e-139">Validating the environment</span></span>

<span data-ttu-id="6025e-140">Antes de começar uma movimentação geográfica do OneDrive, recomendamos validar o ambiente.</span><span class="sxs-lookup"><span data-stu-id="6025e-140">Before you start a OneDrive geo move, we recommend that you validate the environment.</span></span>

<span data-ttu-id="6025e-141">Para garantir que todos os locais geográficos são compatíveis, execute:</span><span class="sxs-lookup"><span data-stu-id="6025e-141">To ensure that all geo locations are compatible, run:</span></span>

`Get-SPOGeoMoveCrossCompatibilityStatus`

<span data-ttu-id="6025e-142">Você verá uma lista da localização geográfica e se o conteúdo poder ser movido, será indicado como "Compatível".</span><span class="sxs-lookup"><span data-stu-id="6025e-142">You will see a list of your geo locations and whether content can be moved between will be denoted as "Compatible".</span></span> <span data-ttu-id="6025e-143">Se o comando retornar "Incompatível", repita a validação do status em uma data posterior.</span><span class="sxs-lookup"><span data-stu-id="6025e-143">If the command returns "Incompatible" please retry validating the status at a later date.</span></span>

<span data-ttu-id="6025e-144">Se OneDrive contiver um subsite, por exemplo, não pode ser movido.</span><span class="sxs-lookup"><span data-stu-id="6025e-144">If a OneDrive contains a subsite, for example, it cannot be moved.</span></span> <span data-ttu-id="6025e-145">Você pode usar o cmdlet Start-SPOUserAndContentMove com o parâmetro -ValidationOnly para validar se o OneDrive pode ser movido:</span><span class="sxs-lookup"><span data-stu-id="6025e-145">You can use the Start-SPOUserAndContentMove cmdlet with the -ValidationOnly parameter to validate if the OneDrive is able to be moved:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly`

<span data-ttu-id="6025e-p109">Isso retornará Sucesso se o OneDrive estiver pronto para ser movido ou Falha se houver um bloqueio legal ou um subsite que impeça a movimentação. Após validar se o OneDrive está pronto para a movimentação, você pode iniciá-la.</span><span class="sxs-lookup"><span data-stu-id="6025e-p109">This will return Success if the OneDrive is ready to be moved or Fail if there is a legal hold or subsite that would prevent the move. Once you have validated that the OneDrive is ready to move, you can start the move.</span></span>

## <a name="start-a-onedrive-geo-move"></a><span data-ttu-id="6025e-148">Iniciar uma movimentação geográfica do OneDrive</span><span class="sxs-lookup"><span data-stu-id="6025e-148">Start a OneDrive geo move</span></span>

<span data-ttu-id="6025e-149">Para iniciar a movimentação, execute:</span><span class="sxs-lookup"><span data-stu-id="6025e-149">To start the move, run:</span></span>  

`Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>`

<span data-ttu-id="6025e-150">Usando estes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="6025e-150">Using these parameters:</span></span>

-   <span data-ttu-id="6025e-151">_UserPrincipalName_ – UPN do usuário cujo OneDrive está sendo movido.</span><span class="sxs-lookup"><span data-stu-id="6025e-151">_UserPrincipalName_ – UPN of the user whose OneDrive is being moved.</span></span>

-   <span data-ttu-id="6025e-p110">_DestinationDataLocation_ – localização geográfica onde o onedrive precisa ser movido. Deve ser igual ao local de dados preferencial do usuário.</span><span class="sxs-lookup"><span data-stu-id="6025e-p110">_DestinationDataLocation_ – Geo-Location where the OneDrive needs to be moved. This should be same as the user's preferred data location.</span></span>

<span data-ttu-id="6025e-154">Por exemplo, para mover o OneDrive de carlos@contosoenergy.onmicrosoft.com de EUR para AUS, execute:</span><span class="sxs-lookup"><span data-stu-id="6025e-154">For example, to move the OneDrive of matt@contosoenergy.onmicrosoft.com from EUR to AUS, run:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS`

![Captura de tela da janela do PowerShell mostrando o cmdlet Start-SPOUserAndContentMove](../media/move-onedrive-between-geo-locations-image2.png)

<span data-ttu-id="6025e-156">Para agendar uma movimentação geográfica posteriormente, use um dos seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="6025e-156">To schedule a geo move for a later time, use one of the following parameters:</span></span>

-   <span data-ttu-id="6025e-p111">_PreferredMoveBeginDate_ – a movimentação provavelmente começará no horário especificado. A hora deve ser especificada como UTC (Tempo Universal Coordenado).</span><span class="sxs-lookup"><span data-stu-id="6025e-p111">_PreferredMoveBeginDate_ – The move will likely begin at this specified time. Time must be specified in Coordinated Universal Time (UTC).</span></span>

-   <span data-ttu-id="6025e-p112">_PreferredMoveEndDate_ – a movimentação provavelmente será concluída no horário especificado, conforme o melhor esforço. A hora deve ser especificada como UTC (Tempo Universal Coordenado).</span><span class="sxs-lookup"><span data-stu-id="6025e-p112">_PreferredMoveEndDate_ – The move will likely be completed by this specified time, on a best effort basis. Time must be specified in Coordinated Universal Time (UTC).</span></span> 

## <a name="cancel-a-onedrive-geo-move"></a><span data-ttu-id="6025e-161">Cancelar uma movimentação geográfica do OneDrive</span><span class="sxs-lookup"><span data-stu-id="6025e-161">Cancel a OneDrive geo move</span></span> 

<span data-ttu-id="6025e-162">Você pode parar a movimentação geográfica do OneDrive de um usuário, desde que a movimentação não esteja em andamento ou seja concluída usando o cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6025e-162">You can stop the geo move of a user's OneDrive, provided the move is not in progress or completed by using the cmdlet:</span></span>

`Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>`

<span data-ttu-id="6025e-163">Em que _UserPrincipalName_ é o UPN do usuário cuja movimentação do OneDrive você deseja parar.</span><span class="sxs-lookup"><span data-stu-id="6025e-163">Where _UserPrincipalName_ is the UPN of the user whose OneDrive move you want to stop.</span></span>

## <a name="determining-current-status"></a><span data-ttu-id="6025e-164">Determinar o status atual</span><span class="sxs-lookup"><span data-stu-id="6025e-164">Determining current status</span></span>

<span data-ttu-id="6025e-165">Você pode verificar o status de uma movimentação geográfica do OneDrive dentro ou fora da geografia à qual você está conectado usando o cmdlet Get-SPOUserAndContentMoveState.</span><span class="sxs-lookup"><span data-stu-id="6025e-165">You can check the status of a OneDrive geo move in or out of the geo that you're connected to by using the Get-SPOUserAndContentMoveState cmdlet.</span></span>

<span data-ttu-id="6025e-166">Os status de movimentação estão descritas na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="6025e-166">The move statuses are described in the following table.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6025e-167"><strong>Status</strong></span><span class="sxs-lookup"><span data-stu-id="6025e-167"><strong>Status</strong></span></span></th>
<th align="left"><span data-ttu-id="6025e-168"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="6025e-168"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="6025e-169">NotStarted</span><span class="sxs-lookup"><span data-stu-id="6025e-169">NotStarted</span></span></td>
<td align="left"><span data-ttu-id="6025e-170">Movimentação não iniciadas.</span><span class="sxs-lookup"><span data-stu-id="6025e-170">The move has not started.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="6025e-171">InProgress (<em>n</em>/4)</span><span class="sxs-lookup"><span data-stu-id="6025e-171">InProgress (<em>n</em>/4)</span></span></td>
<td align="left"><span data-ttu-id="6025e-172">A movimentação está em andamento em um dos seguintes estados: Validação (1/4), Backup (2/4), Restauração (3 4), Limpeza (4/4).</span><span class="sxs-lookup"><span data-stu-id="6025e-172">The move is in progress in one of the following states: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="6025e-173">Êxito</span><span class="sxs-lookup"><span data-stu-id="6025e-173">Success</span></span></td>
<td align="left"><span data-ttu-id="6025e-174">A movimentação foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="6025e-174">The move has completed successfully.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="6025e-175">Falhou</span><span class="sxs-lookup"><span data-stu-id="6025e-175">Failed</span></span></td>
<td align="left"><span data-ttu-id="6025e-176">Falha na movimentação.</span><span class="sxs-lookup"><span data-stu-id="6025e-176">The move failed.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6025e-177">Para localizar o status da movimentação de um usuário específico, use o parâmetro UserPrincipalName:</span><span class="sxs-lookup"><span data-stu-id="6025e-177">To find the status of a specific user's move, use the UserPrincipalName parameter:</span></span>

`Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>`

<span data-ttu-id="6025e-178">Para localizar o status de todas as movimentações de ou para a localização geográfica à qual você está conectado, use o parâmetro Movestate com um dos seguintes valores: não iniciado, InProgress, Success, Failed, All.</span><span class="sxs-lookup"><span data-stu-id="6025e-178">To find the status of all of the moves in or out of the geo location that you're connected to, use the MoveState parameter with one of the following values: NotStarted, InProgress, Success, Failed, All.</span></span>

`Get-SPOUserAndContentMoveState -MoveState <value>`

<span data-ttu-id="6025e-179">Você também pode adicionar o parâmetro `-Verbose` para obter descrições mais detalhadas do estado de movimentação.</span><span class="sxs-lookup"><span data-stu-id="6025e-179">You can also add the `-Verbose` parameter for more verbose descriptions of the move state.</span></span>

## <a name="user-experience"></a><span data-ttu-id="6025e-180">Experiência do Usuário</span><span class="sxs-lookup"><span data-stu-id="6025e-180">User Experience</span></span>

<span data-ttu-id="6025e-p113">Os usuários do OneDrive deverão enfrentar um mínimo de interrupção se o OneDrive for movido para uma localização geográfica diferente. Além de um breve estado somente leitura durante a movimentação, as permissões e os links existentes continuarão a funcionar como esperado quando a movimentação for concluída.</span><span class="sxs-lookup"><span data-stu-id="6025e-p113">Users of OneDrive should notice minimal disruption if their OneDrive is moved to a different geo location. Aside from a brief read-only state during the move, existing links and permissions will continue to work as expected once the move is completed.</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="6025e-183">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="6025e-183">OneDrive for Business</span></span>

<span data-ttu-id="6025e-p114">Enquanto a movimentação estiver em andamento, o OneDrive do usuário será definido como somente leitura. Após a conclusão da movimentação, o usuário será direcionado para o OneDrive no novo local geográfico quando navegar até o OneDrive no iniciador de aplicativos Microsoft 365 ou em um navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="6025e-p114">While the move is in progress the user's OneDrive is set to read-only. Once the move is completed, the user is directed to their OneDrive in the new geo location when they navigate to OneDrive the Microsoft 365 app launcher or a web browser.</span></span>

### <a name="permissions-on-onedrive-content"></a><span data-ttu-id="6025e-186">Permissões sobre o conteúdo do OneDrive</span><span class="sxs-lookup"><span data-stu-id="6025e-186">Permissions on OneDrive content</span></span>

<span data-ttu-id="6025e-187">Os usuários com permissões para o conteúdo do OneDrive continuarão a ter acesso ao conteúdo durante a movimentação e após sua conclusão.</span><span class="sxs-lookup"><span data-stu-id="6025e-187">Users with permissions to OneDrive content will continue to have access to the content during the move and after it's complete.</span></span>

### <a name="onedrive-sync-client"></a><span data-ttu-id="6025e-188">Cliente de sincronização do OneDrive</span><span class="sxs-lookup"><span data-stu-id="6025e-188">OneDrive Sync Client</span></span> 

<span data-ttu-id="6025e-p115">O cliente de sincronização do OneDrive detectará automaticamente e transferirá perfeitamente a sincronização para o novo local do OneDrive após a conclusão da movimentação geográfica do OneDrive. O usuário não precisa entrar novamente nem realizar outras ações. (Precisa da versão 17.3.6943.0625 ou posterior do cliente de sincronização.)</span><span class="sxs-lookup"><span data-stu-id="6025e-p115">The OneDrive sync client will automatically detect and seamlessly transfer syncing to the new OneDrive location once the OneDrive geo move is complete. The user does not need to sign-in again or take any other action.  (Version 17.3.6943.0625 or later of the sync client required.)</span></span>

<span data-ttu-id="6025e-192">Se um usuário atualizar um arquivo enquanto a movimentação geográfica do OneDrive estiver em andamento, o cliente de sincronização o notificará de que uploads de arquivo estão pendentes enquanto a movimentação estiver em andamento.</span><span class="sxs-lookup"><span data-stu-id="6025e-192">If a user updates a file while the OneDrive geo move is in progress, the sync client will notify them that file uploads are pending while the move is underway.</span></span>

### <a name="sharing-links"></a><span data-ttu-id="6025e-193">Links de compartilhamento</span><span class="sxs-lookup"><span data-stu-id="6025e-193">Sharing links</span></span> 

<span data-ttu-id="6025e-194">Após a conclusão da movimentação geográfica do OneDrive, os links compartilhados existentes para os arquivos que foram movidos serão redirecionados automaticamente para a nova localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="6025e-194">Upon OneDrive geo move completion, the existing shared links for the files that were moved will automatically redirect to the new geo location.</span></span>

### <a name="onenote-experience"></a><span data-ttu-id="6025e-195">Experiência do OneNote</span><span class="sxs-lookup"><span data-stu-id="6025e-195">OneNote Experience</span></span> 

<span data-ttu-id="6025e-p116">O cliente do OneNote para win32 e o aplicativo UWP (Universal) detectarão automaticamente e sincronizarão perfeitamente os blocos de anotações com o novo local no OneDrive após a conclusão da movimentação geográfica do OneDrive. O usuário não precisa entrar novamente nem realizar outras ações. O único indicador visível para o usuário é que a sincronização de bloco de anotações falha quando a movimentação geográfica do OneDrive está em andamento. Essa experiência está disponível nas seguintes versões do cliente do OneNote:</span><span class="sxs-lookup"><span data-stu-id="6025e-p116">OneNote win32 client and UWP (Universal) App will automatically detect and seamlessly sync notebooks to the new OneDrive location once OneDrive geo move is complete. The user does not need to sign-in again or take any other action. The only visible indicator to the user is notebook sync would fail when OneDrive geo move is in progress. This experience is available on the following OneNote client versions:</span></span>

-   <span data-ttu-id="6025e-200">OneNote win32 – versão 16.0.8326.2096 (e posteriores)</span><span class="sxs-lookup"><span data-stu-id="6025e-200">OneNote win32 – Version 16.0.8326.2096 (and later)</span></span>

-   <span data-ttu-id="6025e-201">OneNote UWP – versão 16.0.8431.1006 (e posteriores)</span><span class="sxs-lookup"><span data-stu-id="6025e-201">OneNote UWP – Version 16.0.8431.1006 (and later)</span></span>

-   <span data-ttu-id="6025e-202">Aplicativo móvel do OneNote – versão 16.0.8431.1011 (e posteriores)</span><span class="sxs-lookup"><span data-stu-id="6025e-202">OneNote Mobile App – Version 16.0.8431.1011 (and later)</span></span>

### <a name="teams-app"></a><span data-ttu-id="6025e-203">Aplicativo de equipes</span><span class="sxs-lookup"><span data-stu-id="6025e-203">Teams app</span></span>

<span data-ttu-id="6025e-p117">Após a conclusão da movimentação geográfica do OneDrive, os usuários terão acesso aos arquivos do OneDrive no aplicativo do Teams. Além disso, arquivos compartilhados por chat do Teams no OneDrive antes da movimentação geográfica continuarão funcionando após a movimentação ser concluída.</span><span class="sxs-lookup"><span data-stu-id="6025e-p117">Upon OneDrive geo move completion, users will have access to their OneDrive files on the Teams app. Additionally, files shared via Teams chat from their OneDrive prior to geo move will continue to work after move is complete.</span></span>

### <a name="onedrive-for-business-mobile-app-ios"></a><span data-ttu-id="6025e-206">Aplicativo móvel do OneDrive for Business (iOS)</span><span class="sxs-lookup"><span data-stu-id="6025e-206">OneDrive for Business Mobile App (iOS)</span></span> 

<span data-ttu-id="6025e-207">Após a conclusão da movimentação geográfica do OneDrive, o usuário precisa sair e entrar novamente no aplicativo móvel do iOS para fazer a sincronização com o novo local do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6025e-207">Upon OneDrive geo move completion, the user would need to sign out and sign in again on the iOS Mobile App to sync to the new OneDrive location.</span></span>

### <a name="existing-followed-groups-and-sites"></a><span data-ttu-id="6025e-208">Grupos e sites seguidos existentes</span><span class="sxs-lookup"><span data-stu-id="6025e-208">Existing followed groups and sites</span></span>

<span data-ttu-id="6025e-p118">Os sites e grupos seguidos serão exibidos no OneDrive do usuário independentemente da localização geográfica. Sites e grupos hospedados em outro local geográfico serão abertos em uma guia separada.</span><span class="sxs-lookup"><span data-stu-id="6025e-p118">Followed sites and groups will show up in the user's OneDrive regardless of their geo location. Sites and groups hosted in another geo location will open in a separate tab.</span></span>

### <a name="delve-geo-url-updates"></a><span data-ttu-id="6025e-211">Atualizações da URL geográfica do Delve</span><span class="sxs-lookup"><span data-stu-id="6025e-211">Delve Geo URL updates</span></span>

<span data-ttu-id="6025e-212">Os usuários serão enviados para a geografia do Delve correspondente à sua PDL somente depois que o OneDrive tiver sido movido para a nova geografia.</span><span class="sxs-lookup"><span data-stu-id="6025e-212">Users will be sent to the Delve geo corresponding to their PDL only after their OneDrive has been moved to the new geo.</span></span>