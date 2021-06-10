---
title: Mover um site do SharePoint para uma localização geográfica diferente
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: Saiba como mover um site SharePoint para uma localização geográfica diferente em seu ambiente multi-geo e comunicar as expectativas das alterações aos seus usuários.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: eed323b2e2b8f68a4a603052657e17495bb17690
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910925"
---
# <a name="move-a-sharepoint-site-to-a-different-geo-location"></a>Mover um site do SharePoint para uma localização geográfica diferente

Com a mudança geográfica do site do SharePoint, é possível migrar os sites do SharePoint para outras localizações geográficas em seu ambiente multigeográfico.

Os seguintes tipos de sites podem ser movidos entre a localizações geográficas:

- Sites conectados ao grupo do Microsoft 365
- Sites modernos sem uma associação com um Grupo do Microsoft 365
- Site Clássico do SharePoint
- Sites de comunicação

Só um Administrador Global ou Administrador do SharePoint pode mover um site entre as localizações geográficas.

Há uma janela de somente leitura durante a mudança geográfica do site do SharePoint de aproximadamente 4 a 6 horas, dependendo do conteúdo do site.

## <a name="best-practices"></a>Práticas recomendadas

- Experimente uma movimentação do site do SharePoint em um site de teste para se familiarizar com o procedimento.
- Valide se o site pode ser movido antes do agendamento ou ao realizar a movimentação.
- Quando possível agende as mudanças geográficas cruzadas dos sites fora do horário comercial para reduzir o impacto do usuário.
- Comunique-se com os usuários afetados antes de mover sites.

## <a name="communicating-to-your-users"></a>Comunicação com os usuários

Ao mover os sites do SharePoint entre locais geográficos, é importante informar os usuários de sites (geralmente qualquer pessoa com a capacidade de editar o site) o que esperar. Isso pode ajudar a reduzir a confusão do usuário e ligações para a assistência técnica. Envie um email aos usuários dos sites antes de mover e deixe-os cientes do seguinte:

- Quando a mudança deve começar e quanto tempo deve demorar
- Para qual localização geográfica o site mudará, e qual é a URL para acessar o novo local
- Eles devem fechar os arquivos e não fazer edições durante a mudança.
- O compartilhamento e permissões de arquivo não mudarão devido a mudança.
- O que esperar da experiência do usuário em um ambiente multigeográfico

Após a conclusão da mudança, envie um email aos seus usuários informando que eles podem continuar a trabalhar no seus sites.

## <a name="scheduling-sharepoint-site-moves"></a>Agendamento de movimentações no site do SharePoint

Você pode agendar a movimentação do site do SharePoint com antecedência (conforme descrito neste artigo). Agende movimentações da seguinte maneira:

- Você pode agendar até 4.000 movimentações por vez.
- Conforme a movimentação se inicia, você pode agendar mais, com no máximo 4.000 movimentações pendentes na fila e a qualquer momento.

Para agendar uma movimentação geográfica do site do SharePoint para o mais tarde, inclua um dos seguintes parâmetros ao começar a movimentação:

- `PreferredMoveBeginDate` – A movimentação provavelmente começará no horário especificado.
- `PreferredMoveEndDate` – A movimentação provavelmente será concluída até o momento especificado, na base do melhor esforço.

A hora deve ser especificada no Tempo Universal Coordenado (UTC) para ambos os parâmetros.

## <a name="moving-the-site"></a>Mover o site

A movimentação geográfica do site do SharePoint requer que você se conecte e realize a movimentação da URL de Administrador do SharePoint na localização geográfica onde está o site.

Por exemplo, se a URL do site for <https://contosohealthcare.sharepoint.com/sites/Turbines> , conecte-se à URL SharePoint Admin em <https://contosohealthcare-admin.sharepoint.com> :

```powershell
Connect-SPOService -Url https://contosohealthcare-admin.sharepoint.com
```

![SharePoint Janela do Shell de Gerenciamento Online mostrando o Connect-SPOService comando](../media/move-onedrive-between-geo-locations-image1.png)

### <a name="validating-the-environment"></a>Validar o ambiente

Recomendamos que antes de agendar a movimentação de qualquer site, execute a validação para garantir que o site possa ser movido.

Não há suporte para mover sites com:

- Serviços Corporativos de Conectividade
- Formulários do InfoPath
- Modelos do Gerenciamento de Direitos de Informação (IRM) aplicados

Para garantir que todas as localizações geográficas sejam compatíveis, execute `Get-SPOGeoMoveCrossCompatibilityStatus`. Isto exibirá seu local geográfico e se o ambiente é compatível com a localização geográfica de destino.

Para realizar uma verificação de somente de validação no seu site, use `Start-SPOSiteContentMove` com o `-ValidationOnly` parâmetro para validar se o site pode ser movido. Por exemplo:

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

Isso retornará *Sucesso* se o site está pronto para ser movido ou *Falha* se houver qualquer uma das condições de bloqueio.

### <a name="start-a-sharepoint-site-geo-move-for-a-site-with-no-associated-microsoft-365-group"></a>Iniciar a movimentação geográfica do site do SharePoint para um site sem grupo associado do Microsoft 365

Por padrão, a URL inicial para o site será alterada para a URL da localização geográfica de destino. Por exemplo:

<https://Contoso.sharepoint.com/sites/projectx> para <https://ContosoEUR.sharepoint.com/sites/projectx>

Para sites sem associação ao grupo do Microsoft 365, também é possível renomear o site usando o `-DestinationUrl` parâmetro. Por exemplo:

<https://Contoso.sharepoint.com/sites/projectx> para <https://ContosoEUR.sharepoint.com/sites/projecty>

Para começar a mover site, execute:

```powershell
Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>
```

![Captura de tela da janela do PowerShell mostrando Start-SPOSiteContentMove cmdlet](../media/multi-geo-sharepoint-site-move-powershell.png)

### <a name="start-a-sharepoint-site-geo-move-for-a-microsoft-365-group-connected-site"></a>Iniciar uma movimentação geográfica do site do SharePoint para um site conectado a um Grupo do Microsoft 365

Para mover um site conectado a um Grupo do Office 365, o administrador global ou administrador do SharePoint devem, primeiro, alterar o atributo Local e Data Preferenciais (PDL) do grupo do Office 365.

Para configurar o PDL de um Grupo do Microsoft 365:

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```

Depois de atualizar o PDL, você pode começar a mover site:

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

## <a name="cancel-a-sharepoint-site-geo-move"></a>Cancelar uma movimentação geográfica do site do SharePoint

Você pode parar a movimentação geográfica do site do SharePoint, desde que a movimentação não esteja em andamento ou tenha sido concluída, usando o `Stop-SPOSiteContentMove` cmdlet.

## <a name="determining-the-status-of-a-sharepoint-site-geo-move"></a>Determinar o status de uma movimentação geográfica do site do SharePoint

Você pode determinar o status da movimentação de um site fora da área geográfica conectada usando os seguintes cmdlets:

- [Get-SPOSiteContentMoveState](/powershell/module/sharepoint-online/get-spositecontentmovestate) (sites não conectado a um Grupo)
- [Get-SPOUnifiedGroupMoveState](/powershell/module/sharepoint-online/get-spounifiedgroupmovestate) (sites conectados a grupos)

Use o `-SourceSiteUrl` parâmetro para especificar o site que você deseja ver o status de movimentação.

Os status de movimentação estão descritas na seguinte tabela.

****

|Status|Descrição|
|---|---|
|Pronto para Disparar|Movimentação não iniciada.|
|Agendada|A movimentação está na fila, mas ainda não foi iniciada.|
|InProgress (n/4)|A movimentação está em andamento em um dos seguintes estados: Validação (1/4), Backup (2/4), Restauração (3 4), Limpeza (4/4).|
|Êxito|A movimentação foi concluída com êxito.|
|Falhou|Falha na movimentação.|
|

Você também pode aplicar a opção `-Verbose` para ver informações adicionais sobre a movimentação.

## <a name="user-experience"></a>Experiência do usuário

Os usuários do site devem observar um mínimo de interrupção quando o site for movido para uma localização geográfica diferente. Além de um breve estado somente leitura durante a mudança, permissões e links existentes continuarão a funcionar como esperado quando a movimentação for concluída.

### <a name="site"></a>Site

Enquanto a movimentação estiver em andamento o site é definido como somente leitura. Quando a movimentação estiver concluída, o usuário é direcionado para o novo site na nova localização geográfica ao clicar em indicadores ou outros links para o site.

### <a name="permissions"></a>Permissões

Os usuários com permissões para o site continuarão a ter acesso ao site durante a movimentação e após sua conclusão.

### <a name="sync-client"></a>Cliente Sync

O cliente de sincronização detectará automaticamente e transferirá a sincronização para a nova localização do site assim que a movimentação do site for concluída. O usuário não precisa entrar novamente ou realizar outras ações. (Uma Versão 17.3.6943.0625 ou posterior do cliente de sincronização é necessária.)

Se um usuário atualizar um arquivo enquanto a movimentação geográfica estiver em andamento, o cliente de sincronização o notificará de que uploads de arquivo estão pendentes enquanto a movimentação estiver em andamento.

### <a name="sharing-links"></a>Links de compartilhamento

Quando a movimentação geográfica for concluída, os links compartilhados existentes para os arquivos que foram movidos serão redirecionados automaticamente para a nova localização geográfica.

### <a name="most-recently-used-files-in-office-mru"></a>Arquivos Usados Recentemente do Office (MRU)

O serviço MRU é atualizado com a url do site e suas URLs de conteúdo depois que a movimentação for concluída. Isso se aplica ao Word, Excel e PowerPoint.

### <a name="onenote-experience"></a>Experiência do OneNote

O cliente OneNote win32 e o Aplicativo (Universal) UWP detectarão automaticamente e sincronizarão perfeitamente blocos de anotações à nova localização do site após a movimentação ser concluída. O usuário não precisa entrar novamente ou realizar outras ações. O único indicador visível para o usuário é a sincronização do bloco de anotações que deve falhar quando a movimentação do site estiver em andamento. Essa experiência está disponível nas seguintes versões de cliente do OneNote:

- OneNote win32 – versão 16.0.8326.2096 (e posteriores)
- OneNote UWP – versão 16.0.8431.1006 (e posteriores)
- Aplicativo móvel do OneNote – versão 16.0.8431.1011 (e posteriores)

### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a>Teams (aplicáveis aos sites conectados a um grupo do Microsoft 365)

Quando a movimentação geográfica do site do SharePoint estiver concluída, os usuários terão acesso aos seus arquivos de sites do grupo do Microsoft 365 no aplicativo do Teams. Além disso, os arquivos compartilhados por chats do Teams pelo seu site antes da movimentação geográfica continuarão a funcionar quando a movimentação for concluída.

### <a name="sharepoint-mobile-app-iosandroid"></a>Aplicativo Móvel do SharePoint (iOS/Android)

O aplicativo móvel do SharePoint é compatível com área geográfica cruzada e poderá detectar a nova localização geográfica do site.

### <a name="sharepoint-workflows"></a>Fluxos de trabalho do SharePoint

Os fluxos de trabalho do SharePoint 2013 precisam ser republicados após a movimentação do site. Os fluxos de trabalho do SharePoint 2010 continuam funcionando normalmente.

### <a name="apps"></a>Aplicativos

Se estiver movendo um site com os aplicativos, é preciso reinstalar o aplicativo no novo local de geográfico do site, visto que o aplicativo e suas conexões podem não estar disponíveis na localização geográfica do destino.

### <a name="flow"></a>Fluxo

Na maioria dos casos os fluxos continuarão a funcionar após a mivimentação geográfica do site do SharePoint. É recomendável testá-los depois que a movimentação for concluída.

### <a name="powerapps"></a>PowerApps

PowerApps precisam ser recriados no local de destino.

### <a name="data-movement-between-geo-locations"></a>Movimentação de dados entre localizações geográficas

O SharePoint usa o armazenamento de BLOBs do Azure para o seu conteúdo, enquanto os metadados associado a sites e os arquivos são armazenados no SharePoint. Depois de site ser movimentado da sua localização geográfica de origem para sua localização geográfica de destino, o serviço também moverá seu armazenamento BLOB associado. O Armazenamento BLOB move-se completamente em aproximadamente 40 dias.