---
title: Por que você precisa usar o PowerShell para Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: 'Resumo: entenda por que você deve usar o PowerShell para gerenciar o Microsoft 365, em alguns casos com mais eficiência e, em outros casos, por necessidade.'
ms.openlocfilehash: a60220001a148b3a24a996bb6e0154f80214b019
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924583"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a>Por que você precisa usar o PowerShell para Microsoft 365

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Com o Centro de administração do Microsoft 365, você pode gerenciar suas contas de usuário e licenças do Microsoft 365. Você também pode gerenciar seus serviços do Microsoft 365, como o Exchange Online, o Teams e o SharePoint Online. Se você usar o PowerShell para gerenciar esses serviços, poderá aproveitar o ambiente de linguagem de linha de comando e script para velocidade, automação e recursos adicionais.
  
Este artigo mostra como usar o PowerShell para gerenciar o Microsoft 365 para:
  
- Revelar informações adicionais que você não pode ver no Centro de administração do Microsoft 365
    
- Configurar recursos e configurações só é possível com o PowerShell
    
- Fazer operações em massa
    
- Filtrar dados
    
- Imprimir ou salvar dados
    
- Gerenciar entre serviços
    
Lembre-se de que o PowerShell para o Microsoft 365 é um conjunto de módulos para Windows PowerShell, que é um ambiente de linha de comando para plataformas e serviços baseados no Windows. Esse ambiente cria um idioma de shell de comando que pode ser estendido com módulos adicionais. Ele fornece uma maneira de executar comandos ou scripts simples ou complexos. Por exemplo, depois de instalar o PowerShell para módulos do Microsoft 365 e se conectar à sua assinatura do Microsoft 365, você pode executar o seguinte comando para listar todas as caixas de correio de usuário para Microsoft Exchange Online:
  
```powershell
Get-Mailbox
```

Você também pode obter a lista de caixas de correio usando o Centro de administração do Microsoft 365, mas contar os itens em todas as listas de todos os sites de todos os seus aplicativos Web não é fácil.
  
O PowerShell para o Microsoft 365 foi projetado para ajudá-lo a gerenciar o Microsoft 365, não para substituir o centro de administração do Microsoft 365. Os administradores precisam poder usar o PowerShell para o Microsoft 365 porque existem alguns procedimentos de configuração que só podem ser feitos por meio de comandos do PowerShell para o Microsoft 365. Para esses casos, você precisa saber como:
  
- Instale o PowerShell para módulos do Microsoft 365 (feito apenas uma vez para cada computador administrador).
    
- Conecte-se à sua assinatura do Microsoft 365 (uma vez para cada sessão do PowerShell).
    
- Reúna as informações necessárias para executar os comandos necessários do PowerShell para o Microsoft 365.
    
- Execute os comandos do PowerShell para o Microsoft 365.
    
Depois de aprender essas habilidades básicas, você não precisa listar seus usuários de caixa de correio usando o **comando Get-Mailbox.** Você também não precisa entender como criar um novo comando, como o comando mencionado anteriormente, para contar todos os itens em todas as listas para todos os sites de todos os seus aplicativos Web. A Microsoft e a comunidade de administradores podem ajudá-lo com as tarefas necessárias.
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a>O PowerShell para o Microsoft 365 pode revelar informações que você não pode ver com o centro de administração do Microsoft 365

O Centro de administração do Microsoft 365 exibe muitas informações úteis. Mas ele não exibe todas as informações possíveis que o Microsoft 365 armazena sobre usuários, licenças, caixas de correio e sites. Veja um exemplo para usuários *e grupos* no Centro de administração do Microsoft 365:
  
![Exemplo da exibição de usuários e grupos no Centro de administração do Microsoft 365.](../media/o365-powershell-users-and-groups.png)
  
Esta exibição fornece as informações necessárias em muitos casos. No entanto, há momentos em que você precisa de mais. Por exemplo, o licenciamento do Microsoft 365 (e os recursos do Microsoft 365 disponíveis para um usuário) dependem em parte da localização geográfica do usuário. As políticas e recursos que você pode estender a um usuário que mora nos Estados Unidos podem não ser os mesmos que os que você pode estender para um usuário na Índia ou bélgica. Siga estas etapas no Centro de administração do Microsoft 365 para determinar a localização geográfica de um usuário:
  
1. Clique duas vezes no **Nome de exibição** do usuário.
    
2. No painel de exibição de propriedades do usuário, selecione **detalhes**.
    
3. Na exibição de detalhes, selecione **detalhes adicionais**.
    
4. Role até encontrar o título **País ou região**:
    
     ![Exemplo das informações da região para um usuário no Centro de administração do Microsoft 365.](../media/o365-powershell-usage-location.png)
  
5. Escreva o nome de exibição e localização do usuário em um pedaço de papel ou copie e cole no Bloco de notas.
    
Você deve repetir este procedimento para cada usuário. Se você tiver muitos usuários, esse processo poderá ser tedioso. Com o PowerShell para o Microsoft 365, você pode exibir essas informações para todos os seus usuários usando o seguinte comando:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
>O PowerShell Core não dá suporte ao Módulo do Microsoft Azure Active Directory para módulos Windows PowerShell e cmdlets que têm *Msol* em seu nome. Você precisa executar esses cmdlets de Windows PowerShell.
>

Veja um exemplo dos resultados:
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

A interpretação deste comando do PowerShell é: Obter todos os usuários na assinatura atual do Microsoft 365 (**Get-AzureADUser**), mas exibir apenas o nome e o local para cada usuário (**Selecione DisplayName, UsageLocation**).
  
Como o PowerShell para o Microsoft 365 oferece suporte a um idioma de shell de comando, você pode manipular ainda mais as informações obtidas pelo comando **Get-AzureADUser.** Por exemplo, talvez você gostaria de classificar esses usuários por sua localização, agrupando todos os usuários brasileiros, todos os usuários dos Estados Unidos e assim por diante. Aqui está o comando:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

Veja um exemplo dos resultados:
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

A interpretação deste comando do PowerShell é: Obter todos os usuários na assinatura atual do Microsoft 365, mas exibir apenas o nome e o local para cada usuário e classificar primeiro por sua localização e, em seguida, seu nome (**Sort UsageLocation, DisplayName**).
  
Você também pode usar filtragem adicional. Por exemplo, se você quiser ver informações sobre usuários baseados no Brasil, use este comando:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

Veja um exemplo dos resultados:
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

A interpretação deste comando do PowerShell é: Obter todos os usuários na assinatura atual do Microsoft 365 cujo local é Brasil (**Onde {$ \_ . UsageLocation -eq "BR"}**) e, em seguida, exibe o nome e o local para cada usuário.
  
 **Uma observação sobre domínios grandes**
  
Se você tiver um domínio grande com dezenas de milhares de usuários, tentar alguns dos exemplos que mostramos neste artigo pode levar à throttling. Com base em fatores como a energia de computação e a largura de banda de rede disponível, você pode estar tentando fazer muito ao mesmo tempo. Grandes organizações podem querer dividir algumas dessas operações do PowerShell em dois comandos.

Por exemplo, o comando a seguir retorna todas as contas de usuário e mostra o nome e o local de cada uma delas:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

Isso funciona bem com domínios menores. Mas em uma organização grande, talvez você queira dividir essa operação em dois comandos: um comando para armazenar as informações da conta do usuário em uma variável e outro para exibir as informações necessárias. Exemplo:
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

A interpretação desse conjunto de comandos do PowerShell é:
1. Obter todos os usuários na assinatura atual do Microsoft 365 e armazenar as informações em uma variável chamada $x (**$x = Get-AzureADUser**).
1.  Exibe o conteúdo da variável *$x*, mas inclui apenas o nome e o local para cada usuário (**$x | Selecione DisplayName, UsageLocation**).
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a>O Microsoft 365 tem recursos que você só pode configurar com o PowerShell para o Microsoft 365

O Centro de administração do Microsoft 365 destina-se a fornecer acesso a tarefas administrativas comuns e úteis que se aplicam à maioria dos ambientes. Em outras palavras, o Centro de administração do Microsoft 365 foi projetado para que o administrador típico possa realizar as tarefas de gerenciamento mais comuns. Mas há algumas tarefas que não podem ser feitas no centro de administração.
  
Por exemplo, o Centro de administração do Skype for Business Online fornece algumas opções para criar convites de reunião personalizados:
  
![Exemplo da exibição de convites de reunião personalizados no Centro de administração do Skype for Business Online.](../media/o365-powershell-meeting-invitation.png)
  
Com essas configurações, você pode adicionar um toque de personalização e profissionalismo a convites de reunião. Mas há mais configurações de reunião do que simplesmente criar convites de reunião personalizados. Por exemplo, por padrão, as reuniões permitem:
  
- Usuários anônimos obterem entrada automática para cada reunião.
    
- Participantes gravem a reunião.
    
- Todos os usuários da sua organização serem designado como apresentadores quando eles entrarem na reunião.
    
Essas configurações não estão disponíveis no Centro de administração do Skype for Business Online. Você pode controlá-los do PowerShell para o Microsoft 365. Aqui está um comando que desabilita essas três configurações:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> Para executar esse comando, você deve instalar o Módulo do PowerShell do [Skype for Business Online. ](https://www.microsoft.com/download/details.aspx?id=39366)
  
A interpretação deste comando do PowerShell é:
 
1. Nas configurações para novas reuniões do Skype for Business Online (**Set-CsMeetingConfiguration**), desabilitar permitindo que usuários anônimos obtenham entrada automática em reuniões (**-AdmitAnonymousUsersByDefault $False**).
2.  Desabilitar a capacidade de os participantes gravarem reuniões (**-AllowConferenceRecording $False**).
3. Não designe todos os usuários de sua organização como apresentadores (**-DesignateAsPresenter "None"**).
  
Para restaurar essas configurações padrão (habilitar as opções), execute este comando:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

Há outros cenários semelhantes também, e é por isso que os administradores devem saber como executar comandos do PowerShell para o Microsoft 365.
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a>O PowerShell para o Microsoft 365 é ótimo para operações em massa

Interfaces visuais como o Centro de administração do Microsoft 365 são mais valiosas quando você tem uma única operação a ser realizada. Por exemplo, se você precisar desabilitar uma conta de usuário, poderá usar o centro de administração para localizar e limpar rapidamente uma caixa de seleção. Isso pode ser mais fácil do que executar uma operação semelhante no PowerShell.
  
Mas se você precisar alterar muitas coisas ou algumas coisas selecionadas em um conjunto grande de outras coisas, o Centro de administração do Microsoft 365 pode não ser a melhor ferramenta. Por exemplo, digamos que você tenha que alterar o prefixo em milhares de números de telefone ou remover o usuário *específico Ken Myer* de todos os sites do SharePoint Online. Como você faria isso no centro de administração do Microsoft 365?
  
Para o último exemplo, diga que você tem várias centenas de sites do SharePoint Online e não sabe de quais ken Meyer é membro. Você teria que começar no Centro de administração do Microsoft 365 e executar este procedimento para cada site:
  
1. Selecione a **URL** do site.
    
2. Na caixa **propriedades do conjunto de sites,** selecione o link Endereço do **Site** para abrir o site.
    
3. No site, selecione **Compartilhar**.
    
4. Na caixa **de diálogo** Compartilhar, selecione o link que mostra todos os usuários que têm permissões para o site:
    
     ![Exemplo de como exibir os membros de um site do SharePoint Online no Centro de administração do SharePoint Online.](../media/o365-powershell-view-permissions.png)
  
5. Na caixa **de diálogo Compartilhado com,** selecione **Avançado**.
    
6. Role para baixo a lista de usuários, encontre e selecione Ken Myer (supondo que ele tenha permissões para o site) e selecione **Remover Permissões do Usuário**.
    
Isso levaria muito *tempo* para várias centenas de sites.
  
A alternativa é executar o seguinte comando no PowerShell para o Microsoft 365 para remover Ken Myer de todos os seus sites:
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> Este comando requer que você instale o módulo do PowerShell do [SharePoint Online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) 
  
A interpretação deste comando do PowerShell é: Obter todos os sites do SharePoint na assinatura atual do Microsoft 365 (**Get-SPOSite**) e para cada site remover Ken Meyer da lista de usuários que podem acessá-lo (**ForEach {Remove-SPOUser -Site $ \_ . Url -LoginName "kenmyer \@ litwareinc.com"}**).
  
Falamos para o Microsoft 365 remover Ken Meyer de todos os sites, incluindo aqueles aos quais ele não tem acesso. Portanto, os resultados mostrarão erros para os sites aos qual ele não tem acesso. Podemos usar uma condição adicional neste comando para remover Ken Meyer somente dos sites que o têm na lista de logon. Mas os erros retornados não causam danos aos próprios sites. Esse comando pode levar alguns minutos para ser executado em centenas de sites, em vez de horas de trabalho por meio do Centro de administração do Microsoft 365.
  
Aqui está outro exemplo de operação em massa. Use este comando para adicionar *Bonnie Kearney*, uma nova administradora do SharePoint, a todos os sites da organização:
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

A interpretação deste comando do PowerShell é: Obter todos os sites do SharePoint na assinatura atual do Microsoft 365 e para cada site permitir acesso a Bonnie Kearney adicionando seu nome de logon ao grupo Membros do site (**ForEach {Add-SPOUser -Site $ \_ . Url -LoginName "bkearney \@ litwareinc.com" -Group "Members"}**).
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a>O PowerShell para o Microsoft 365 é ótimo na filtragem de dados

O Centro de administração do Microsoft 365 fornece várias maneiras de filtrar seus dados para localizar facilmente um subconjunto de informações direcionado. Por exemplo, o Exchange facilita a filtragem de praticamente qualquer propriedade da caixa de correio de um usuário. Por exemplo, aqui está a lista de caixas de correio para todos os usuários que moram na cidade de Bloomington:
  
![Exemplo de uma pesquisa avançada no Centro de administração do Microsoft 365 para a lista de caixas de correio de todos os usuários que moram na cidade de Bloomington.](../media/o365-powershell-advanced-search.png)
  
O Centro de administração do Exchange também permite que você combine critérios de filtro. Por exemplo, você pode encontrar as caixas de correio de todas as pessoas que moram em Bloomington e trabalham no departamento de Finanças.
  
Mas há limitações para o que você pode fazer no Centro de Administração do Exchange. Por exemplo, você não pôde encontrar facilmente as caixas de correio de pessoas que moram em *Bloomington* ou San Diego, ou as caixas de correio de todas as pessoas que não moram em Bloomington.
  
Você pode usar o seguinte comando do PowerShell para o Microsoft 365 para obter uma lista de caixas de correio para todas as pessoas que moram em Bloomington ou San Diego:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

Veja um exemplo dos resultados:
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

A interpretação deste comando do PowerShell é: Obter todos os usuários na assinatura atual do Microsoft 365 que tenham uma caixa de correio na cidade de San Diego ou Bloomington (**Onde {$ \_ . RecipientTypeDetails -eq "UserMailbox" -and ($ \_ . Cidade -eq "San Diego" -ou $ \_ . City -eq "Bloomington")}**), e, em seguida, exibir o nome e a cidade para cada um (**Selecione DisplayName, City**).
  
E aqui está o comando para listar todas as caixas de correio para pessoas que moram em qualquer lugar, exceto Bloomington:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

Veja um exemplo dos resultados:
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

A interpretação deste comando do PowerShell é: Obter todos os usuários na assinatura atual do Microsoft 365 que tenham uma caixa de correio não localizada na cidade de Bloomington (**Onde {$ \_ . RecipientTypeDetails -eq "UserMailbox" -and $ \_ . City -ne "Bloomington"}**) e, em seguida, exibir o nome e a cidade para cada um.
  
### <a name="use-wildcards"></a>Usar caracteres curinga

Você também pode usar caracteres curinga em seus filtros do PowerShell para corresponder a parte de um nome. Por exemplo, suponha que você esteja procurando uma conta de usuário. Tudo o que você pode lembrar é que o sobrenome do usuário era *Anderson* ou talvez *Henderson* ou *Jorgenson*.
  
Você pode rastrear esse usuário no centro de administração do Microsoft 365 usando a ferramenta de pesquisa e realizando três pesquisas diferentes:
  
- Uma para  *Mendes* 
    
- Uma para  *Gonçalves* 
    
- Uma para  *Gomes* 
    
Como todos esses três nomes terminam em "filho", você pode dizer ao PowerShell para exibir todos os usuários cujo nome termina em "filho". Aqui está o comando:
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

A interpretação deste comando do PowerShell é: Obter todos os usuários na assinatura atual do Microsoft 365, mas usar um filtro que lista apenas os usuários cujos sobrenomes terminam em "filho" (**-Filter '{LastName -like " \* son"}'**). O \* representa qualquer conjunto de caracteres, que são letras no sobrenome do usuário.
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a>O PowerShell para o Microsoft 365 facilita a impressão ou a economia de dados

O Centro de administração do Microsoft 365 permite exibir listas de dados. Veja um exemplo do Centro de administração do Skype for Business Online exibindo uma lista de usuários que foram habilitados para o Skype for Business Online:
  
![Exemplo do Centro de administração do Skype for Business Online exibindo uma lista de usuários que foram habilitados para o Skype for Business Online.](../media/o365-powershell-lync-users.png)
  
Para salvar essas informações em um arquivo, você deve colar em um documento ou planilha do Microsoft Excel. Qualquer caso pode exigir formatação adicional. Além disso, o Centro de administração do Microsoft 365 não oferece uma maneira de imprimir diretamente a lista exibida.
  
Felizmente, você pode usar o PowerShell para não apenas exibir a lista, mas salvá-la em um arquivo que pode ser facilmente importado para o Excel. Aqui está um comando de exemplo para salvar dados de usuário do Skype for Business Online em um arquivo CSV (valores separados por vírgula), que pode ser facilmente importado como uma tabela em uma planilha do Excel:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

Veja um exemplo dos resultados:
  
![Exemplo de uma tabela importada para uma planilha do Excel para dados de usuário do Skype for Business Online que foram salvos em um arquivo de valores separados por vírgulas.](../media/o365-powershell-data-in-excel.png)
  
A interpretação deste comando do PowerShell é: Obter todos os usuários do Skype for Business Online na assinatura atual do Microsoft 365 (**Get-CsOnlineUser**); obtenha apenas o nome de usuário, UPN e local (**Selecione DisplayName, UserPrincipalName, UsageLocation**); e salve essas informações em um arquivo CSV chamado C: \\ Logs \\SfBUsers.csv (**Export-Csv -Path "C: \\ Logs \\SfBUsers.csv" -NoTypeInformation**).
  
Você também pode usar opções para salvar essa lista como um arquivo XML ou uma página HTML. Na verdade, com comandos adicionais do PowerShell, você pode salvá-lo diretamente como um arquivo do Excel, com qualquer formatação personalizada que quiser.
  
Você também pode enviar a saída de um comando do PowerShell que exibe uma lista diretamente para a impressora padrão no Windows. Aqui está um comando de exemplo:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

O seu documento impresso ficará assim:
  
![Exemplo de um documento impresso que foi a saída de um comando do PowerShell enviado diretamente para a impressora padrão no Windows.](../media/o365-powershell-printed-data.png)
  
A interpretação deste comando do PowerShell é: Obter todos os usuários do Skype for Business Online na assinatura atual do Microsoft 365; obter apenas o nome de usuário, UPN e local; e, em seguida, envie essas informações para a impressora padrão do Windows (**Out-Printer**).
  
O documento impresso tem a mesma formatação simples que a exibição na janela de comando do PowerShell. Para obter uma cópia impressa, basta adicionar **| Out-Printer** até o final do comando.
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a>O PowerShell para o Microsoft 365 permite que você gerencie entre produtos de servidor

Os componentes que comem o Microsoft 365 foram projetados para trabalhar em conjunto. Por exemplo, suponha que você adicione um novo usuário ao Microsoft 365 e especifique informações como o departamento do usuário e o número de telefone. Essas informações estarão disponíveis se você acessar as informações do usuário em qualquer um dos serviços do Microsoft 365: Skype for Business Online, Exchange ou SharePoint.
  
Mas isso é para informações comuns que abrangem o pacote de produtos. Informações específicas do produto, como informações sobre a caixa de correio do Exchange de um usuário, normalmente não estão disponíveis no pacote. Por exemplo, informações sobre se a caixa de correio de um usuário está habilitada ou não está disponível apenas no Centro de administração do Exchange.
  
Suponha que você queira fazer um relatório que mostre as seguintes informações sobre todos os seus usuários:
  
- O nome de exibição do usuário
    
- Se o usuário está licenciado para o Microsoft 365
    
- Se a caixa de correio do Exchange do usuário está habilitada
    
- Se o usuário está habilitado para o Skype for Business online
    
Você não pode produzir facilmente esse relatório no Centro de administração do Microsoft 365. Em vez disso, você teria que criar um documento separado para armazenar as informações, como uma planilha do Excel. Em seguida, obter todos os nomes de usuário e informações de licenciamento do Centro de administração do Microsoft 365, obter informações de caixa de correio do Centro de Administração do Exchange, obter informações do Skype for Business Online do Centro de Administração do Skype for Business Online e combinar essas informações.
  
A alternativa é usar um script do PowerShell para compilar o relatório para você.
  
O script de exemplo a seguir é mais complicado do que os comandos que você viu até agora neste artigo. No entanto, ele mostra o potencial de usar o PowerShell para criar exibições de informações difíceis de obter de outra forma. Este é o script para compilar e exibir a lista de que você precisa:
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

Veja um exemplo dos resultados:
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

A interpretação deste script do PowerShell é:  

1. Obter todos os usuários na assinatura atual do Microsoft 365 e armazenar as informações em uma variável chamada *$x* (**$x = Get-AzureADUser**).
1. Inicie um loop que executa todos os usuários na variável $x (**foreach ($i em $x)**).  
1. Defina uma variável *chamada $y* e armazene as informações de caixa de correio do usuário nele ( $y =**Get-Mailbox -Identity $i.UserPrincipalName**).
1. Adicione uma nova propriedade às informações do usuário chamada *IsMailBoxEnabled*. De defini-lo como o valor da propriedade IsMailBoxEnabled da caixa de correio do usuário (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).
1. Defina uma variável chamada *$y*, e armazene as informações do Skype for Business Online do usuário nele (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).
1. Adicione uma nova propriedade às informações do usuário chamadas *EnabledForSfB*. De defini-lo como o valor da propriedade Enabled das informações do Skype for Business Online do usuário (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).
1. Exibe a lista de usuários, mas inclui apenas seu nome, se eles estão licenciados e as duas novas propriedades que indicam se sua caixa de correio está habilitada e se elas estão habilitadas para o Skype for Business Online (**$x | Selecione DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).
  
## <a name="see-also"></a>Confira também

[Introdução ao Windows PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)
  
[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Usar o PowerShell do Windows para criar relatórios no Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md)