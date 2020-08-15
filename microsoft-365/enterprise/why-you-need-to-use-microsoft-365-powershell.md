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
description: 'Resumo: entenda por que você deve usar o PowerShell para gerenciar o Microsoft 365, em alguns casos com mais eficiência e em outros casos por necessidade.'
ms.openlocfilehash: 7220356cd79b03674661ace386fd1d38a7e39587
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686940"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a>Por que você precisa usar o PowerShell para Microsoft 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Com o centro de administração do Microsoft 365, você não só pode gerenciar suas licenças e contas de usuário do Microsoft 365, mas também pode gerenciar seus serviços do Microsoft 365, como o Exchange Online, o Teams e o SharePoint Online. No entanto, você também pode gerenciar esses elementos com os comandos do PowerShell, tirando proveito de um ambiente de linha de comando e de linguagem de script para velocidade, automação e capacidade adicional.
  
Neste artigo, mostraremos a você as seguintes maneiras em que você pode usar o PowerShell para gerenciar o Microsoft 365:
  
- Revelar informações adicionais que você não consegue ver com o centro de administração do Microsoft 365
    
- Configurar recursos e configurações somente para o PowerShell
    
- Executar operações em massa
    
- Filtragem de dados
    
- Imprimir ou salvar dados
    
- Gerenciar entre serviços
    
Antes de começar, entenda que o PowerShell para o Microsoft 365 é um conjunto de módulos para o Windows PowerShell, um ambiente de linha de comando para plataformas e serviços baseados no Windows. Esse ambiente cria um idioma de Shell de comando que pode ser estendido com módulos adicionais e oferece uma maneira de executar comandos ou scripts simples ou complexos. Por exemplo, depois de instalar os módulos do PowerShell para o Microsoft 365 e se conectar à sua assinatura do Microsoft 365, você pode executar este comando para listar todas as caixas de correio de usuário do Microsoft Exchange Online:
  
```powershell
Get-Mailbox
```

A obtenção da lista de caixas de correio também pode ser feita facilmente usando o centro de administração do Microsoft 365, mas contar o número de itens em todas as listas de todos os sites de todos os seus aplicativos Web não pode ser feito facilmente.
  
Observe que o PowerShell para Microsoft 365 foi projetado para aumentar e aprimorar sua capacidade de gerenciar o Microsoft 365, não para substituir o centro de administração do Microsoft 365. Como administrador, você deve se familiarizar com o uso do PowerShell para o Microsoft 365 porque há alguns procedimentos de configuração que só podem ser feitos com o PowerShell para os comandos do Microsoft 365. Nesses casos, você precisará compreender como:
  
- Instale os módulos do PowerShell para Microsoft 365 (feito apenas uma vez para cada computador do administrador).
    
- Conecte-se à sua assinatura do Microsoft 365 (feita uma vez para cada sessão do PowerShell).
    
- Reúna as informações necessárias para executar os comandos do PowerShell necessários para o Microsoft 365.
    
- Execute o PowerShell para comandos do Microsoft 365 com êxito.
    
Depois de aprender essas habilidades básicas, não é necessário listar os usuários de caixa de correio com o comando **Get-Mailbox**, também não é preciso entender como criar um novo comando como o anterior para contar todos os itens nas listas de todos os sites para todos os seus aplicativos da Web. A Microsoft e a comunidade de administradores podem ajudá-lo com isso conforme necessário.
  
## <a name="powershell-for-microsoft-365-can-reveal-additional-information-that-you-cannot-see-with-the-microsoft-365-admin-center"></a>O PowerShell para Microsoft 365 pode revelar informações adicionais que você não consegue ver com o centro de administração do Microsoft 365

O centro de administração 365 da Microsoft exibe muitas informações úteis, mas isso não significa que ela exibe todas as informações possíveis que a Microsoft 365 armazena em usuários, licenças, caixas de correio e sites. Veja um exemplo de **usuários e grupos** no centro de administração do Microsoft 365:
  
![Exemplo de exibição de usuários e grupos no centro de administração do Microsoft 365.](../media/o365-powershell-users-and-groups.png)
  
Para muitas finalidades, isso exibe as informações que você precisa saber. No entanto, há ocasiões em que você precisa de mais. Por exemplo, o licenciamento da Microsoft 365 (e os recursos do Microsoft 365 disponíveis para um usuário) dependem parte da localização geográfica desse usuário. As políticas e os recursos que você pode estender para um usuário que reside nos Estados Unidos podem não ser os mesmos que as políticas e os recursos que você pode estender para um usuário que mora na Índia ou na Bélgica. Você pode usar o centro de administração do Microsoft 365 para determinar a localização geográfica de um usuário com estas etapas:
  
1. Clique duas vezes no **Nome de exibição** do usuário.
    
2. No painel de exibição de propriedades do usuário, clique em **detalhes**.
    
3. Na exibição detalhes, clique em **detalhes adicionais**.
    
4. Role para baixo até ver o cabeçalho **País ou região**:
    
     ![Exemplo das informações de região de um usuário no centro de administração do Microsoft 365.](../media/o365-powershell-usage-location.png)
  
5. Escreva o nome de exibição e localização do usuário em um pedaço de papel ou copie e cole no Bloco de notas. 
    
Você deve repetir este procedimento para cada usuário. Quando há muitos usuários, isso pode ser uma tarefa entediante. Com o PowerShell para Microsoft 365, você pode exibir essas informações para todos os seus usuários com o seguinte comando:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
>O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome. Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.
>

Este é um exemplo de exibição:
  
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

> [!TIP]
>  A interpretação deste comando do PowerShell é: obter todos os usuários na assinatura atual do Microsoft 365 ( **Get-AzureADUser** ), mas apenas exibir o nome e o local para cada usuário ( **selecione DisplayName, UsageLocation** ).
  
Como o PowerShell para Microsoft 365 oferece suporte a um idioma de Shell de comando, você pode manipular ainda mais as informações obtidas do comando **Get-AzureADUser** . Por exemplo, talvez você queira classificar esses usuários pelo local, agrupar todos os usuários brasileiros juntos, todos os usuários do Brasil, etc. Este é o comando:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

Este é um exemplo de exibição:
  
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

> [!TIP]
>  A interpretação deste comando do PowerShell é: obter todos os usuários na assinatura atual do Microsoft 365, mas apenas exibir o nome e o local de cada usuário e classificá-los primeiro pelo local e, em seguida, os nomes ( **classificar UsageLocation, DisplayName** ).
  
Você também pode usar a filtragem adicional. Por exemplo, se você quiser ver informações sobre usuários baseados no Brasil, use este comando:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

Este é um exemplo de exibição:
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

> [!TIP]
>  A interpretação deste comando do PowerShell é: obter todos os usuários na assinatura atual do Microsoft 365, cujo local é Brasil ( **onde {$ \_ . UsageLocation-EQ "BR"}** ) e, em seguida, exibe o nome e o local para cada usuário.
  
 **Uma rápida observação sobre domínios maiores**
  
Se você tiver um domínio muito grande com dezenas de milhares de usuários, tentar alguns dos exemplos mostrados neste artigo pode levar a "limitação". Isso significa que, com base em itens como energia de computação e largura de banda de rede disponível, você está tentando fazer um pequeno demais ao mesmo tempo. Por isso, as organizações maiores podem querer dividir alguns desses comandos do PowerShell para Microsoft 365 em dois comandos. Por exemplo, este comando retorna todas as contas de usuário e mostra o nome e o local de cada usuário:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

Isso funciona bem com domínios menores. Em uma grande organização, no entanto, talvez você precise dividi-lo em dois comandos: um comando para armazenar as informações da conta do usuário em uma variável e outro comando para exibir as informações necessárias. Veja um exemplo:
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

A interpretação deste conjunto de comandos do PowerShell é:
- Obter todos os usuários na assinatura atual do Microsoft 365 e armazenar as informações em uma variável chamada $x ( **$x = Get-AzureADUser** ).
- Exibir o conteúdo da variável $x, mas incluir apenas o nome e o local para cada usuário (**$x | Select DisplayName, UsageLocation**).
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a>A Microsoft 365 tem recursos que você só pode configurar com o PowerShell para Microsoft 365

O centro de administração do Microsoft 365 destina-se a fornecer acesso às tarefas administrativas mais comuns ou significativas que se aplicam à maioria das pessoas. Em outras palavras, o centro de administração do Microsoft 365 foi projetado para que o administrador típico pudesse usar a ferramenta para realizar as tarefas de gerenciamento mais comuns. Por essa definição, isso significa que há algumas tarefas que não podem ser concluídas usando o centro de administração do Microsoft 365.
  
Por exemplo, o Centro de administração Skype for Business online fornece algumas opções para criar convites personalizados para reunião:
  
![Exemplo da exibição de convites de reunião personalizados no Centro de administração do Skype for Business Online.](../media/o365-powershell-meeting-invitation.png)
  
Com essas configurações, você pode adicionar um toque de personalização e profissionalismo a convites de reunião. No entanto, há muito mais configurações de reunião do que simplesmente criar convites personalizados de reunião. Por exemplo, por padrão, as reuniões permitem:
  
- Usuários anônimos obterem entrada automática para cada reunião.
    
- Participantes gravem a reunião.
    
- Todos os usuários da sua organização serem designado como apresentadores quando eles entrarem na reunião.
    
Essas configurações não estão disponíveis no centro de administração do Skype for Business online. No entanto, você pode controlá-los do PowerShell para o Microsoft 365. Veja um comando que desabilita essas três configurações:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> Este comando requer que você instale o [Módulo do PowerShell Skype for Business Online ](https://www.microsoft.com/download/details.aspx?id=39366). 
  
> [!TIP]
>  A interpretação deste comando do PowerShell é: para as configurações para novas reuniões do Skype for Business online ( **set-CsMeetingConfiguration** ), desabilitar a permissão de usuários anônimos para obter a entrada automática de reuniões ( **-AdmitAnonymousUsersByDefault $false** ), desabilitar a capacidade dos participantes de registrarem reuniões (- **AllowConferenceRecording $false** ) e não designar todos os usuários da organização como apresentadores (- **DesignateAsPresenter "nenhum"** ).
  
Se você mudar de ideia e desejar restaurar essas configurações padrão (todas são ativadas), execute este comando:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

Isso é apenas um exemplo. Há outros, por isso, você, como administrador, precisa se familiarizar com a execução de comandos do PowerShell para o Microsoft 365.
  
## <a name="powershell-for-microsoft-365-is-great-at-carrying-out-bulk-operations"></a>O PowerShell para Microsoft 365 é ótimo para realizar operações em massa

Historicamente, interfaces visuais como o centro de administração do Microsoft 365 são mais valiosas quando você tem uma única operação a ser executada. Por exemplo, se for necessário desabilitar uma conta de usuário, você poderá usar o centro de administração do Microsoft 365 para localizar e desmarcar rapidamente uma caixa de seleção. Isso pode ser mais simples do que executar uma operação semelhante no PowerShell.
  
Mas se você precisar alterar muitas coisas ou algumas coisas selecionadas dentro de um grande conjunto de outras coisas, o centro de administração do Microsoft 365 pode não ser o melhor uso do tempo. Por exemplo, se você tivesse que alterar o prefixo em milhares de números de telefone ou você precisava remover um usuário específico, Ken Myer, de todos os seus sites do SharePoint Online, como faria isso no centro de administração do Microsoft 365?
  
Para o último exemplo, você tem centenas de sites do SharePoint Online e não sabe nem mesmo saber quais são os que Ken Araújo é membro. Isso significa que você terá que começar no centro de administração do Microsoft 365 e, em seguida, executar este procedimento para cada site:
  
1. Clicar na **URL** do site.
    
2. Na caixa **Propriedades da coleção de sites**, clicar no link **Endereço de Site da Web** para abrir o site.
    
3. No site, clicar em **Compartilhar**.
    
4. Na caixa de diálogo **Compartilhar** clicar no link que mostra a você todos os usuários que têm permissão para o site:
    
     ![Exemplo de como exibir os membros de um site do SharePoint Online no Centro de administração do SharePoint Online.](../media/o365-powershell-view-permissions.png)
  
5. Na caixa de diálogo **Compartilhado com** clicar em **Avançado**.
    
6. Rolar pela lista de usuários, encontrar e selecionar Paulo Araújo (supondo que ele tem permissões para o site) e então clicar em **Remover Permissões do Usuário**.
    
Pode demorar muito tempo para você fazer isso em uma centena de sites.
  
A alternativa é usar o PowerShell para o Microsoft 365 e o seguinte comando para remover Ken Myer de todos os sites:
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> Este comando requer que você instale o [módulo do PowerShell do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps). 
  
> [!TIP]
>  A interpretação deste comando do PowerShell é: obter todos os sites do SharePoint na assinatura atual do Microsoft 365 ( **Get-SPOSite** ) e para cada site, remover Ken Araújo da lista de usuários que podem acessá-lo ( **foreach {remove-marido-site $ \_ . URL-LoginName "kenmyer@litwareinc.com"}** ).
  
Como estamos dizendo para a Microsoft 365 para remover Ken Araújo de todos os sites, incluindo aqueles nos quais ele não tem acesso, a exibição desse comando mostrará erros para aqueles sites nos quais ele não tem acesso no momento. Podemos usar uma condição adicional nesse comando para remover Paulo Araújo somente de sites com ele esteja na lista de login, mas os erros listados não provocam danos aos sites. Este comando pode levar alguns minutos para ser executado em centenas de sites, em vez de horas de trabalho por meio do centro de administração do Microsoft 365.
  
Este é outro exemplo de operação em massa. Use este comando para adicionar Mila Moraes, uma nova administradora do SharePoint, para todos os sites na organização:
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

> [!TIP]
>  A interpretação deste comando do PowerShell é: obter todos os sites do SharePoint na assinatura atual do Microsoft 365 e para cada site, permitir o acesso Kearney do Bonnie adicionando seu nome de logon ao grupo de membros do site ( **foreach {Add-marido-site $ \_ . URL-LoginName "bkearney@litwareinc.com"-Group "Members"}** ).
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a>O PowerShell para Microsoft 365 é ótimo para filtrar dados

O centro de administração do Microsoft 365 fornece várias maneiras diferentes de filtrar seus dados para localizar de forma rápida e fácil um subconjunto de informações direcionado. Por exemplo, o Exchange facilita a filtragem de praticamente qualquer propriedade da caixa de correio de um usuário. Por exemplo, esta é uma lista de caixas de correio para todos os usuários que moram em Belo Horizonte:
  
![Exemplo de uma pesquisa avançada no centro de administração do Microsoft 365 para a lista de caixas de correio para todos os usuários que moram na cidade do belo horizonte.](../media/o365-powershell-advanced-search.png)
  
O Centro de administração do Exchange também permite que você combine critérios de filtro. Por exemplo, você pode encontrar as caixas de correio para todas as pessoas que moram em Belo Horizonte e que trabalham no departamento financeiro. 
  
No entanto, existem limitações no que você pode fazer no Centro de administração do Exchange. Por exemplo, talvez você queira localizar caixas de correio de quem mora em Belo Horizonte ou Curitiba ou caixas de correio para todas as pessoas que não moram em Belo Horizonte. 
  
Com o PowerShell para Microsoft 365, você pode obter uma lista de caixas de correio para todas as pessoas que vivem nas cidades de Belo Horizonte ou San Diego com este comando:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

Este é um exemplo de exibição:
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

> [!TIP]
>  A interpretação deste comando do PowerShell é: obter todos os usuários na assinatura atual do Microsoft 365 que tenha uma caixa de correio nas cidades de San Diego ou Belo Horizonte ( **onde {$ \_ . RecipientTypeDetails-EQ "UserMailbox"-e ($ \_ . City-eq "San Diego"-ou $ \_ . City-eq "Belo Horizonte")}** ), em seguida, exibe o nome e a cidade para cada ( **selecione DisplayName, City** ).
  
Este é o comando para listar todas as caixas de correio de quem mora em qualquer lugar, exceto Belo Horizonte:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

Este é um exemplo de exibição:
  
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

> [!TIP]
>  A interpretação deste comando do PowerShell é: obter todos os usuários na assinatura atual do Microsoft 365 que possua uma caixa de correio não localizada na cidade de Belo Horizonte ( **onde {$ \_ . RecipientTypeDetails-EQ "UserMailbox"-e $ \_ . City-NE "Belo Horizonte"}** ) e, em seguida, exiba o nome e a cidade de cada um.
  
Você também pode usar caracteres curinga em seus filtros do PowerShell para corresponder a parte de um nome. Por exemplo, suponha que você esteja procurando uma conta de usuário, e tudo o que você pode lembrar é que seu sobrenome era Anderson, ou talvez Gonçalves, ou talvez seja Gomes.
  
Você pode rastrear esse usuário no centro de administração do Microsoft 365 usando a ferramenta de pesquisa e executando três pesquisas diferentes:
  
- Uma para  *Mendes* 
    
- Uma para  *Gonçalves* 
    
- Uma para  *Gomes* 
    
Como todos os três desses nomes terminam em "Son", você pode dizer ao PowerShell para exibir todos os usuários cujo nome termina em "Son". Este é o comando:
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

> [!TIP]
>  A interpretação deste comando do PowerShell é: obter todos os usuários na assinatura atual do Microsoft 365, mas usar um filtro que liste apenas os usuários cujos sobrenomes terminam em "Son" ( **-Filter ' {LastName-like " \* Son"} '** ). O \* significa um conjunto de caracteres, que são letras no caso do sobrenome do usuário.
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a>O PowerShell para Microsoft 365 facilita a impressão ou a gravação de dados

O centro de administração 365 da Microsoft permite exibir listas de dados. Veja um exemplo do centro de administração do Skype for Business online que exibe uma lista de usuários que foram habilitados para o Skype for Business Online:
  
![Exemplo do Centro de administração do Skype for Business Online exibindo uma lista de usuários que foram habilitados para o Skype for Business Online.](../media/o365-powershell-lync-users.png)
  
Para salvar essas informações em um arquivo, você deve copiá-lo e colá-lo em um documento ou no Excel. Em ambos os casos, a cópia pode exigir uma formatação adicional. Além disso, o centro de administração do Microsoft 365 não oferece uma maneira de imprimir diretamente a lista exibida.
  
Felizmente, você pode usar o PowerShell para não apenas exibir a lista, mas salvá-la em um arquivo que pode ser facilmente importado para o Excel. Veja a seguir um exemplo de comando para salvar dados de usuário do Skype for Business online em um arquivo de valores separados por vírgula (CSV), um arquivo que pode ser importado facilmente como uma tabela em uma planilha do Excel:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

Este é um exemplo de exibição:
  
![Exemplo de uma tabela importada para uma planilha do Excel para os dados do usuário do Skype for Business Online que foram salvos em um arquivo de valores separados por vírgula (CSV).](../media/o365-powershell-data-in-excel.png)
  
> [!TIP]
>  A interpretação deste comando do PowerShell é: obter todos os usuários do Skype for Business online na assinatura atual do Microsoft 365 ( **Get-CsOnlineUser** ), obter apenas o nome de usuário, o UPN e o local ( **selecione DisplayName, userPrincipalName, UsageLocation** ) e, em seguida, salve essas informações no arquivo CSV denominado c: logs \\ \\SfBUsers.csv ( **Export-CSV-Path "C: \\ logs \\SfBUsers.csv"-NoTypeInformation**
  
Você também pode usar opções para salvar a lista como um arquivo XML ou como uma página HTML. Na verdade, com os comandos adicionais do PowerShell, você poderia salvá-la diretamente como um arquivo do Excel, com qualquer formatação personalizada desejada. 
  
Você também pode enviar a saída de um comando do PowerShell que exibe uma lista diretamente para a impressora padrão no Windows. Este é um exemplo de comando:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

O seu documento impresso ficará assim:
  
![Exemplo de um documento impresso que foi a saída de um comando do PowerShell listado diretamente para a impressora padrão no Windows.](../media/o365-powershell-printed-data.png)
  
> [!TIP]
>  A interpretação deste comando do PowerShell é: obter todos os usuários do Skype for Business online na assinatura atual do Microsoft 365, obter apenas o nome de usuário, o UPN e o local e enviá-las para a impressora padrão do Windows ( **Out-Printer** ).
  
O documento impresso tem a mesma formatação simples que a exibição na janela de comando do PowerShell, mas depois que você tiver criado um comando do PowerShell para listar o que precisa, basta adicionar **| Out-Printer** para o final do comando para obter uma cópia impressa para trabalhar.
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a>O PowerShell para Microsoft 365 permite que você gerencie nos produtos de servidor

Os diferentes componentes que compõem o Microsoft 365 são projetados para funcionar juntos. Por exemplo, suponha que você adicione um novo usuário ao Microsoft 365 e, quando fizer isso, especifique informações como o departamento e o número de telefone do usuário. Essas informações estarão disponíveis se você acessar as informações do usuário usando qualquer um dos serviços do Microsoft 365: Skype for Business Online, Exchange ou SharePoint Online.
  
Mas isso se trata de informações genéricas que existem em todo o conjunto de produtos. Informações específicas do produto, por exemplo, as informações sobre uma caixa de correio do Exchange do usuário, geralmente não estão disponíveis em todo o pacote. Por exemplo, se você deseja saber se a caixa de correio do usuário está habilitada ou não, essas informações estão disponíveis somente no Centro de administração do Exchange. 
  
Suponha que você queira fazer um relatório que mostre as seguintes informações sobre todos os seus usuários:
  
- O nome de exibição do usuário
    
- Se o usuário está licenciado para o Microsoft 365
    
- Se a caixa de correio do Exchange do usuário está habilitada
    
- Se o usuário está habilitado para o Skype for Business online
    
No momento, você não pode usar o centro de administração do Microsoft 365 para produzir um relatório desse tipo com facilidade. Em vez disso, você precisará criar um documento separado para armazenar as informações, como uma planilha do Excel, e obter todos os nomes de usuário e informações de licenciamento do centro de administração do Microsoft 365, obter informações de caixa de correio do centro de administração do Exchange, obter informações do Skype for Business Online do centro de administração do Skype for Business Online e agrupar e combinar essas informações.
  
A alternativa é usar um script do PowerShell para compilar esse relatório para você.
  
O script de exemplo a seguir é mais complicado do que os comandos que vimos até agora neste artigo. No entanto, ele mostra o potencial de usar o PowerShell para criar modos de exibição de informações que são muito difíceis de fazer caso contrário. Aqui está o script que pode compilar e exibir a lista necessária:
  
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

Este é um exemplo de exibição:
  
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

- Obter todos os usuários na assinatura atual do Microsoft 365 e armazenar as informações em uma variável chamada $x ( **$x = Get-AzureADUser** ).
- Iniciar um loop que é executado em todos os usuários na variável denominada $x (**foreach ($i in $x)**).  
- Definir uma variável chamada $y e armazenar as informações da caixa de correio do usuário nela (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).
- Adicionar uma nova propriedade à informação do usuário chamada IsMailBoxEnabled e configurá-la para o valor da propriedade IsMailBoxEnabled da caixa de correio do usuário (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).
- Definir uma variável chamada $y e armazenar as informações do usuário do Skype for Business Online nela (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).
- Adicionar uma nova propriedade à informação do usuário chamada EnabledForSfB e configurá-la para o valor da propriedade Habilitada das informações do usuário do Skype for Business Online (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).
- Exibir a lista de usuários, mas incluir apenas os nomes, informar se eles estão licenciados e incluir as duas novas propriedades que indicam se as caixas de correio deles estão ativadas e se elas estão habilitadas para o Skype for Business Online ( **$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB** ).
  
## <a name="see-also"></a>Veja também

[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)
  
[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Usar o PowerShell do Windows para criar relatórios no Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md)

