---
title: Usar a ferramenta de coleção PST para localizar, copiar e excluir arquivos PST em sua organização
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid: MOE150
ms.assetid: 7a150c84-049c-4a9c-8c91-22355b35f2a7
description: Use a ferramenta de coleção PST da Microsoft para pesquisar a rede da sua organização para obter um inventário de arquivos PST espalhados por toda a organização. Após localizar arquivos PST, você pode usar a ferramenta de coleção PST para copiá-los em um local central para que possa importá-los para o Office 365.
ms.openlocfilehash: 736e317318f860936450b7412bc465fc7c9d59e1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073910"
---
# <a name="use-the-pst-collection-tool-to-find-copy-and-delete-pst-files-in-your-organization"></a>Usar a ferramenta de coleção PST para localizar, copiar e excluir arquivos PST em sua organização

> [!IMPORTANT]
> A ferramenta de coleção PST descrita neste artigo não é suportada em nenhum programa ou serviço de suporte padrão da Microsoft. A ferramenta é fornecida como está sem garantia de qualquer tipo. A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica. Todo o risco resultante do uso ou do desempenho da ferramenta e da documentação permanece com você. Em hipótese alguma a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou entrega da ferramenta serão responsáveis por qualquer dano (incluindo, sem limitação, danos à perda de lucros de negócios, interrupção de negócios, perda de informações comerciais ou outras perdas de pecuniary) resultantes do uso ou da incapacidade de usar a ferramenta ou a documentação, mesmo que a Microsoft tenha sido avisada da possibilidade de tais danos.

Você pode usar a ferramenta de coleção PST da Microsoft para pesquisar arquivos PST na rede da sua organização. A ferramenta ajuda você a obter um inventário de arquivos PST espalhados por toda a sua organização. Após localizar arquivos PST, você pode usar a ferramenta de coleção PST para copiá-los em um local central. Ter PSTs em um local e, em seguida, permite que você importe-os para caixas de correio do Exchange Online (ou uma única caixa de correio do Exchange Online), onde você pode aplicar o avançado conjunto de recursos de conformidade no Office 365. Isso inclui a importação de PSTs para caixas de correio de arquivo morto de usuários, pesquisando mensagens específicas nos arquivos PST que você importou usando ferramentas de pesquisa de descoberta eletrônica, retendo mensagens usando as políticas de retenção de descoberta eletrônica e do Office 365 e gerenciando a vida ciclo dessas mensagens usando os recursos de gerenciamento de registros de mensagens no Exchange Online. Após ter certeza de que os arquivos PST que você coletou foram importados com êxito para o Office 365, você pode usar a ferramenta para excluí-los do local original na sua rede. 
  
Outra coisa que você pode fazer com a ferramenta de coleção PST é impedir que os usuários criem novos arquivos PST e alterando os arquivos PST existentes encontrados na rede. Esses recursos de "bloqueio" permitem localizar, coletar e importar um conjunto conhecido de arquivos PST para o Office 365 e impedir a proliferação futura de arquivos PST em sua organização. 
  
## <a name="how-the-pst-collection-tool-works"></a>Como funciona a ferramenta de coleção PST

Veja uma rápida visão geral do processo de usar a ferramenta de coleção PST para localizar, controlar, coletar e excluir arquivos PST em sua organização.
  
![Visão geral do processo da ferramenta de coleção PST](../media/67a29f27-f83c-4f0a-9df4-7ed92d3086fe.png)
  
1. **[Etapa 1: localizar arquivos pst em sua rede](#step-1-find-pst-files-on-your-network)** -quando você executar a ferramenta para localizar arquivos PST, especifique um local, como uma unidade organizacional que contenha objetos do Active Directory para computadores cliente e servidor. Você também pode pesquisar máquinas específicas ou compartilhamentos de arquivos de rede. Quando você executa a ferramenta, um agente de coleção "leve" é instalado nos computadores de destino. Este agente pesquisa os arquivos PST no computador de destino e, em seguida, envia informações de volta para a ferramenta de coleção PST sobre qualquer arquivo PST localizado. A ferramenta cria arquivos de log que contêm informações sobre os arquivos PST encontrados nos locais especificados. Esses arquivos são usados quando você executa a ferramenta nas etapas posteriores. 
    
2. **[(Opcional) etapa 2: controlar o acesso a arquivos PST](#optional-step-2-control-access-to-pst-files)** -a ferramenta cria um objeto de política de grupo (GPO) com configurações que impedem que os usuários criem ou alterem arquivos pst. Esse GPO é aplicado a todos os usuários no seu domínio. Esta etapa opcional ajuda você a "bloquear" os arquivos PST que foram encontrados na etapa 1, para que você possa coletar, importar e excluí-los sem ter novos arquivos PST criados ou os arquivos PST existentes foram alterados. 
    
3. **[Etapa 3: copiar os arquivos pst para um local de conjunto](#step-3-copy-the-pst-files-to-a-collection-location)** : isso permite que você colete os arquivos pst em um local para que possa importá-los para caixas de correio do Exchange Online usando o serviço de importação do Office 365 na etapa 4. Quando você executa a ferramenta no modo "Collect", cada agente de coleção copia os arquivos PST da máquina de destino para o qual o agente está instalado no local da coleção. 
    
4. **[Etapa 4: importar os arquivos pst para o Office 365](#step-4-import-the-pst-files-to-office-365)** -depois de copiar os arquivos pst para um local, você estará pronto para importá-los para caixas de correio do Exchange Online. 
    
5. **[Etapa 5: excluir os arquivos PST encontrados na sua rede](#step-5-delete-the-pst-files-found-on-your-network)** -depois que os arquivos PST encontrados e coletados tiverem sido importados para caixas de correio do Exchange Online no Office 365, você poderá usar a ferramenta de coleção PST para excluir os arquivos PST dos locais originais onde eles foram encontrados na etapa 1. 

## <a name="before-you-begin"></a>Antes de começar

- Siga estas etapas para baixar a ferramenta de coleção PST no computador local. 
    
    1. [Baixe a ferramenta de coleção PST](https://aka.ms/pstcollectiontool).
    
    2. Na janela pop-up, clique em **salvar** \> **salvar como** para salvar o arquivo PSTCollectionTool. zip em uma pasta no computador local. 
    
    3. Extraia o arquivo PSTCollectionTool. zip em uma pasta no computador local; o nome da pasta padrão é PSTCollectionTool.
    
- Para executar a ferramenta de coleção PST em qualquer modo (localizar, bloquear, copiar ou excluir), você precisa ser membro do grupo de administradores de domínio no seu domínio do Active Directory. 

## <a name="step-1-find-pst-files-on-your-network"></a>Etapa 1: localizar arquivos PST na sua rede

A primeira etapa é executar a ferramenta de coleção PST para localizar arquivos PST em sua organização. Você pode usar a ferramenta para pesquisar os seguintes tipos de locais. 
  
- Unidades organizacionais (UOs) em um domínio local do Active Directory. A ferramenta pesquisa todas as máquinas que estão contidas na OU especificada. 
    
- Computadores cliente e servidor. A ferramenta pesquisa as máquinas especificadas. 
    
- Compartilhamentos de arquivos de rede. A ferramenta pesquisa os compartilhamentos de arquivos de rede especificados. 
    
Confira a descrição do `Locations` parâmetro na tabela no procedimento a seguir para obter exemplos de sintaxe a serem usados para cada um desses tipos de local. 
  
> [!IMPORTANT]
> Você deve executar a ferramenta de coleção PST no modo de localização antes de poder executar outras ações, como bloquear, coletar ou excluir arquivos PST. 
  
1. Abra um prompt de comando (executar como administrador) no computador local.
    
2. Vá para a pasta PSTCollectionTool (ou a pasta para a qual você extraiu o arquivo PSTCollectionTool. zip).
    
3. Mude para o diretório DataCollector.
    
4. Execute o seguinte comando para localizar arquivos PST em um local especificado.
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName <Name> -Locations <Locations to search for PSTs> -LogLocation <Location to store log files> -ConfigurationLocation <Location to store configuration files>
    ```

    A tabela a seguir descreve os parâmetros e seus valores obrigatórios quando você executa o comando DataCollector. exe para localizar arquivos PST. 
    
    |Parâmetro * * * *|****Descrição****|Exemplos * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Especifica o tipo de dados a serem pesquisados. No momento, você pode usar a ferramenta de coleção PST para procurar arquivos PST.  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Especifica o tipo de operação que a ferramenta executará. Use o valor `Find` para localizar arquivos PST nos locais especificados. Observe que a ferramenta pode encontrar e obter informações sobre arquivos PST que estão abertos em arquivos do Outlook e PST que estão conectados a perfis do Outlook.  <br/> | `-Mode Find` <br/> |
    | `JobName` <br/> |Especifica o nome do trabalho da coleção PST. Você usará esse mesmo nome de trabalho ao executar a ferramenta de coleção PST para bloquear, coletar e excluir os arquivos PST que são encontrados quando você executa a ferramenta para localizar arquivos PST. O nome do trabalho também será adicionado aos nomes de arquivo de log e de configuração.  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> | Especifica um ou mais locais para pesquisar arquivos PST. Se você especificar mais de um local, use um ponto e vírgula (;) para separar locais individuais. Não deixe de colocar os valores individuais desse parâmetro com aspas duplas ("").  <br/><br/>   Aqui está o formato de valor de identidade necessário para os tipos de locais que você pode pesquisar.  <br/><br/>        **UOs** – use o DN (nome diferenciado) para identificar UOs; por exemplo:`"OU=NorthAmerica,OU=NWRegion,OU=ITServices,DC=contoso,DC=com"` <br/> > [!IMPORTANT]> não é possível especificar o contêiner de computadores interno (por exemplo, CN = computadores, DC = contoso, DC = com "), pois ele não é uma unidade organizacional.<br/> <br/> **Machines** -use o DN ou o FQDN (nome de domínio totalmente qualificado) para identificar máquinas cliente e servidor em sua rede; por exemplo:  <br/>  BAIXO`"CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"` <br/>  Ou  <br/>  FQDN`"FILESERVER01.contoso.com"` <br/><br/>  **Compartilhamentos de arquivos de rede** -use um nome UNC para identificar os compartilhamentos de arquivos de rede; por exemplo,`"\\FILESERVER02\Users"` <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `LogLocation` <br/> |Especifica a pasta para a qual os arquivos de log serão copiados. Se a pasta não existir, ela será criada quando você executar a ferramenta.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ConfigurationLocation` <br/> |Especifica a pasta para a qual o arquivo de configuração. xml será copiado. Esse arquivo contém informações sobre cada arquivo PST que é encontrado quando você executa a ferramenta. Esse arquivo será usado quando você executar a ferramenta na etapa 3 para copiar os arquivos PST encontrados.  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `ExcludedLocations` <br/> |Esse parâmetro opcional especifica locais a serem ignorados durante uma operação de localização. Você pode excluir UOs, máquinas e compartilhamentos de arquivos de rede específicos. Por exemplo, você pode excluir máquinas, como o computador configurado como SQL Server (ou outros tipos de servidores de aplicativos), aos quais os usuários não têm acesso. Se você especificar mais de um local para exclusão, use um ponto-e-vírgula (;) para separar locais individuais. Não deixe de colocar os valores individuais desse parâmetro com aspas duplas ("").  <br/> | `-ExcludedLocations "SQLSERVER01.contoso.com"` <br/> |
    | `ForceRestart` <br/> |Essa opção opcional permite executar a ferramenta no modo de localização para um trabalho da coleção PST existente. Quando você usa a `ForceRestart` opção, os resultados da operação de localização anterior do trabalho serão descartados e a ferramenta verificará novamente os locais especificados e criará novos arquivos de log e de configuração.  <br/> | `-ForceRestart` <br/> |
   
    Veja um exemplo da sintaxe do comando DataCollector. exe usando valores reais para cada parâmetro:
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -LogLocation "c:\users\admin\desktop\PSTCollection" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"
    ```

    Após executar o comando, são exibidas mensagens de status detalhadas que mostram o andamento da localização de arquivos PST nos locais especificados. Após um tempo, uma mensagem de status final mostra o número total de arquivos PST que foram encontrados, se o trabalho foi concluído e se houve algum erro. As mesmas mensagens de status são copiadas para o arquivo. log.
    
### <a name="results-of-running-datacollectormasterexe-in-the-find-mode"></a>Resultados da execução do DataCollector. exe no modo localizar

Depois de executar com êxito a ferramenta de coleção PST no modo localizar, os arquivos a seguir são criados e armazenados nas pastas especificadas pelos `LogLocation` parâmetros `ConfigurationLocation` e. 
  
- **\>__ JobName localizar\<DateTimeStamp\>. log-o arquivo de log contém as mensagens de status \<** que foram exibidas. Esse arquivo é criado na pasta especificada pelo `LogLocation` parâmetro. 
    
- **\>__ JobName localizar\<DateTimeStamp\>. csv-o arquivo CSV contém uma linha para cada \<** arquivo PST encontrado. As informações de cada PST incluem o computador onde o arquivo PST foi encontrado, o local do caminho completo do arquivo PST, o proprietário do arquivo PST e o tamanho (em kilobytes, KBs) do arquivo PST. Esse arquivo é criado na pasta especificada pelo `LogLocation` parâmetro. 
    
    > [!TIP]
    > Use a ferramenta AutoSoma no Excel para calcular o tamanho total (em KB) de todos os arquivos PST listados no arquivo CSV. Em seguida, você pode usar uma calculadora de conversão para converter o tamanho total em megabytes (MB) ou gigabytes (GB). 
  
- **\>__ JobName localizar\<DateTimeStamp\>. xml-o arquivo XML contém informações sobre os valores de parâmetro que são usados quando você executou a ferramenta \<** no modo localizar. Esse arquivo também contém informações sobre cada arquivo PST encontrado. Os dados nesse arquivo são usados quando você executa a ferramenta novamente para que o mesmo trabalho bloqueie, colete ou exclua os arquivos PST que foram encontrados. Esse arquivo é criado na pasta especificada pelo `ConfigurationLocation` parâmetro. 
    
    > [!IMPORTANT]
    > Não renomeie, altere ou mova este arquivo. Ela é usada pela ferramenta coleção PST quando você executa novamente a ferramenta no modo bloquear, copiar ou excluir para o mesmo trabalho. 

## <a name="optional-step-2-control-access-to-pst-files"></a>Opcion Etapa 2: controlar o acesso a arquivos PST

Esta etapa opcional permite "bloquear" os arquivos PST que foram encontrados na etapa 1 para que você possa coletar e importar um conjunto conhecido de arquivos PST para o Office 365. Quando você executa a ferramenta de coleção PST no modo de bloqueio, acontece o seguinte: 
  
- A ferramenta cria um objeto de política de grupo (GPO) denominado *controles de uso de PST* . Este GPO está vinculado ao seu domínio e se aplica a todos os usuários autenticados em sua organização. 
    
- O GPO controles de uso de PST cria configurações de registro em computadores em sua organização. Dependendo do parâmetro que você usa, é possível criar uma configuração de registro para impedir que os usuários criem novos arquivos PST e uma configuração de registro que impede que os usuários alterem arquivos PST existentes.
    
> [!NOTE]
> Se o controle de acesso a arquivos PST for muito prejudicial à sua organização, considere ignorar esta etapa e realizar a etapa 3 para copiar os arquivos PST para um local central. Em seguida, você pode repetir a etapa 1 para o mesmo trabalho ( `ForceRestart` usando o parâmetro) para localizar outros arquivos PSTs que foram criados após a cópia dos arquivos PSTs para o local da coleção. Se forem encontrados novos arquivos PST, você poderá copiá-los para o local da coleção. Quando você usar o `ForceRestart` parâmetro quando executar novamente a ferramenta no modo localizar, os resultados da operação de localização anterior de um trabalho serão descartados e a ferramenta examinará novamente os locais especificados. 

Para bloquear o acesso a arquivos PST:

1. Abra um prompt de comando (executar como administrador) no computador local.
    
2. Vá para o diretório onde você baixou a ferramenta de coleção PST para.
    
3. Execute o comando a seguir para bloquear o acesso aos arquivos PST encontrados na etapa 1.

    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -BlockChangesToFiles -BlockNewFiles
    ```

    A tabela a seguir descreve os parâmetros e seus valores obrigatórios quando você executa o comando DataCollector. exe para bloquear a criação e a alteração de arquivos PST. 
    
    |Parâmetro * * * *|****Descrição****|Exemplos * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Especifica o tipo de dados a serem pesquisados. No momento, você pode usar a ferramenta de coleção PST para procurar arquivos PST.  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Especifica o tipo de operação que a ferramenta executará. Use o valor `Block` para impedir que os usuários criem novos arquivos pst e faça alterações nos arquivos PST existentes.  <br/> | `-Mode Block` <br/> |
    | `JobName` <br/> |Especifica o nome de um trabalho da coleção PST existente. Você precisa usar esse mesmo nome de trabalho que usou ao executar a ferramenta no modo localizar na etapa 1. Esse nome de trabalho também é adicionado ao nome do arquivo de log que é criado quando você executa a ferramenta no modo de bloqueio.  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |Especifica a pasta que contém o arquivo de configuração. XML que foi criado quando você executou a ferramenta no modo localizar. Use o mesmo valor que você usou para esse parâmetro na etapa 1.  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |Especifica a pasta para a qual o arquivo de log para a operação de bloqueio será copiado. Esse é um parâmetro opcional. Se você não incluir, o arquivo de log será copiado para a pasta onde você baixou a ferramenta de coleção PST. Considere usar o mesmo local de log que você usou ao executar a ferramenta no modo localizar na etapa 1 para que todos os arquivos de log sejam salvos na mesma pasta.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `BlockChangesToFiles` <br/> |Use essa opção para impedir que os usuários alterem um arquivo PST. Quando você usa essa opção, a entrada de registro a seguir é `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\PST\PstDisableGrow` criada: e o valor de dados é definido como 1. Essa configuração do registro é criada nas máquinas da sua organização pelo GPO que é criado quando você executa a ferramenta de coleção PST no modo de bloqueio.  <br/> | `-BlockChangesToFiles` <br/> |
    | `BlockNewFiles` <br/> |Use essa opção para impedir que os usuários criem novos arquivos PST, abrir e importar arquivos PST para o Outlook e exportar arquivos PST do Outlook. Quando você usa essa opção, a entrada de registro a seguir é `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\DisablePst` criada: e o valor de dados é definido como 1. Essa configuração do registro é criada nas máquinas da sua organização pelo GPO que é criado quando você executa a ferramenta de coleção PST no modo de bloqueio.  <br/> | `-BlockNewFiles` <br/> |
   
    Veja um exemplo da sintaxe do comando DataCollector. exe usando valores reais para cada parâmetro:

    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection" -BlockChangesToFiles -BlockNewFiles
    ```

    Você será solicitado a confirmar se deseja bloquear novos arquivos PST ou alterações em arquivos PST existentes. Depois de confirmar que você deseja continuar e que o comando é executado com êxito, uma mensagem é exibida dizendo que um novo GPO, chamado "controles de uso de PST", foi criado.
    
## <a name="step-3-copy-the-pst-files-to-a-collection-location"></a>Etapa 3: copiar os arquivos PST para um local de conjunto

A próxima etapa é copiar os arquivos PST que foram encontrados quando você executou a ferramenta de coleção PST no modo localizar. Isso permite coletar os arquivos PST em um local para que você possa importá-los posteriormente para o Office 365. Antes de copiar os arquivos PST para o local da coleta, considere determinar a quantidade total de espaço de armazenamento necessário. Você pode fazer isso usando o arquivo CSV que foi criado na etapa 1 para calcular o tamanho total de todos os arquivos PST.
  
> [!NOTE]
> Após importar os arquivos PST para o Office 365 e excluí-los do local original, convém excluí-los do local da coleção que você copiou para esta etapa. 
  
1. Abra um prompt de comando (executar como administrador) no computador local.
    
2. Vá para o diretório onde você baixou a ferramenta de coleção PST para.
    
3. Execute o comando a seguir para copiar os arquivos PST para um local especificado.
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName <Name of job from Step 1> -Locations <same locations from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    A tabela a seguir descreve os parâmetros e os valores necessários ao executar o comando DataCollector. exe para copiar os arquivos PST. 
    
    |Parâmetro * * * *|****Descrição****|Exemplos * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Especifica o tipo de dados a serem pesquisados. No momento, você pode usar a ferramenta de coleção PST para procurar arquivos PST.  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Especifica o tipo de operação que a ferramenta executará. Use o valor `Collect` para copiar os arquivos pst que foram encontrados quando você executou a ferramenta no modo localizar. Observe que a ferramenta pode copiar os arquivos PST que estão abertos no Outlook e copiar os arquivos PST que estão conectados aos perfis do Outlook.  <br/> | `-Mode Collect` <br/> |
    | `JobName` <br/> |Especifica o nome de um trabalho da coleção PST existente. Você precisa usar esse mesmo nome de trabalho que usou ao executar a ferramenta no modo localizar na etapa 1. Esse nome de trabalho também é adicionado ao nome do arquivo de log que é criado quando você executa a ferramenta no modo de coleta.  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> |Use o mesmo valor que você usou para o `Locations` parâmetro na etapa 1. Você deve incluir esse parâmetro ao executar a ferramenta no modo de coleta se quiser executar novamente a ferramenta para excluir os arquivos PST de seu local de origem na etapa 5.  <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"; "CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `ConfigurationLocation` <br/> |Especifica a pasta que contém o arquivo de configuração. XML que foi criado quando você executou a ferramenta no modo localizar. Use o mesmo valor que você usou para esse parâmetro na etapa 1.  <br/> | `-ConfigurationLocation "c:\users\admin\desktop \PSTCollection\Configuration"` <br/> |
    | `CopyLocation` <br/> |Especifica o local da coleção onde você deseja copiar os arquivos PST. Você pode copiar arquivos para um servidor de arquivos, um compartilhamento de arquivos de rede ou um disco rígido. O local deve existir antes de executar a ferramenta no modo de coleta. A ferramenta não cria o local e retornará um erro informando que ele não existe.  <br/> Além disso, você precisará Gravar permissões no local da coleção especificado por esse parâmetro.  <br/> | `-CopyLocation "\\FILESERVER03\PSTs"` <br/> |
    | `LogLocation` <br/> |Especifica a pasta para a qual o arquivo de log do modo de coleta será copiado. Esse é um parâmetro opcional. Se você não incluir, o arquivo de log será copiado para a pasta onde você baixou a ferramenta de coleção PST. Considere usar o mesmo local de log que você usou ao executar a ferramenta no modo localizar na etapa 1 para que todos os arquivos de log sejam salvos na mesma pasta.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |Essa opção opcional permite executar novamente a ferramenta no modo de coleção para um trabalho de coleção PST existente. Se você já executou a ferramenta no modo de coleta, mas, em seguida, executou a ferramenta novamente no `ForceRestart` modo de localização com o switch para examinar novamente os locais de arquivos PST, você pode usar essa opção para executar novamente a ferramenta no modo de coleta e copiar novamente os arquivos pst que foram encontrados quando você examinou novamente os locais. Ao usar a `ForceRestart` opção no modo de coleção, a ferramenta ignora qualquer operação de coleta anterior e tenta copiar os arquivos pst do zero.  <br/> | `-ForceRestart` <br/> |
   
    Veja um exemplo da sintaxe da ferramenta DataCollector. exe usando valores reais para cada parâmetro:
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -CopyLocation "\\FILESERVER03\PSTs" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    Após executar o comando, são exibidas mensagens de status detalhadas que mostram o progresso da coleta de arquivos PST que foram encontrados na etapa 1. Após um tempo, uma mensagem de status final mostrará se houve algum erro e o local para o qual o log foi copiado. As mesmas mensagens de status são copiadas para o arquivo. log.
    
### <a name="results-of-running-datacollectormasterexe-in-the-collect-mode"></a>Resultados da execução do DataCollector. exe no modo de coleta

Após executar com êxito o DataCollector. exe no modo de coleta, os arquivos a seguir são criados e armazenados nas pastas especificadas pelos parâmetros `LogLocation` e. `ConfigurationLocation` 
  
- **\>__ JobName coletar\<DateTimeStamp\>. log-o arquivo de log contém as mensagens de status \<** que foram exibidas. Esse arquivo é criado na pasta especificada pelo `LogLocation` parâmetro. 
    
- **\>__ JobName coletar\<DateTimeStamp\>. xml-o arquivo XML contém apenas informações sobre os valores de parâmetro que, em que foram usados pela ferramenta, foram executados no \<** modo de coleta. Os dados nesse arquivo são usados quando você executa a ferramenta de DataCollector. exe novamente para excluir arquivos PST; consulte a [etapa 5](#step-5-delete-the-pst-files-found-on-your-network).
    

## <a name="step-4-import-the-pst-files-to-office-365"></a>Etapa 4: importar os arquivos PST para o Office 365

Após coletar os arquivos PST encontrados na etapa 1, a próxima etapa é importá-los para caixas de correio no Office 365. Como parte ou o processo de importação, você precisará criar um arquivo de mapeamento CSV que contenha uma linha de cada arquivo PST que você deseja importar. As informações em cada linha especificam o nome do arquivo PST, o endereço de email do usuário e se você deseja importar o arquivo PST para a caixa de correio principal ou de arquivo morto do usuário. Use as informações no arquivo **JobName\>_Find_\<DateTimeStamp. csv** (criado na etapa) 1 para ajudá-lo a criar o arquivo de mapeamento CSV. 
  
Para obter instruções passo a passo para importar arquivos PST para o Office 365, consulte um dos seguintes tópicos:
  
- [Usar o carregamento de rede para importar arquivos PST para o Office 365](use-network-upload-to-import-pst-files.md)
    
- [Usar o envio de unidade para importar os arquivos PST para o Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    

## <a name="step-5-delete-the-pst-files-found-on-your-network"></a>Etapa 5: excluir os arquivos PST encontrados na sua rede

Depois que os arquivos PST encontrados e coletados tiverem sido importados para caixas de correio do Exchange Online no Office 365, você poderá usar a ferramenta de coleção PST para excluir os arquivos PST dos locais de origem originais onde foram encontrados na etapa 1. 
  
1. Abra um prompt de comando (executar como administrador) no computador local.
    
2. Vá para o diretório onde você baixou a ferramenta de coleção PST para.
    
3. Execute o comando a seguir para excluir os arquivos PST.

    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    A tabela a seguir descreve os parâmetros e seus valores obrigatórios quando você executa o comando DataCollector. exe para excluir arquivos PST. 
    
    |Parâmetro * * * *|****Descrição****|Exemplos * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Especifica o tipo de dados a serem pesquisados. No momento, você pode usar a ferramenta de coleção PST para procurar arquivos PST. ![espaçador](../media/b078d05c-3aee-4b9f-8805-6a8a9d8970ee.png)           <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Especifica o tipo de operação que a ferramenta executará. Use o valor `Delete` para excluir os arquivos pst que foram encontrados quando você executou a ferramenta no modo localizar.  <br/> | `-Mode Delete` <br/> |
    | `JobName` <br/> |Especifica o nome de um trabalho da coleção PST existente. É necessário usar esse mesmo nome de trabalho que você usou ao executar a ferramenta no modo de localização e no modo de coleta na etapa 1 e etapa 3. Esse nome de trabalho também é adicionado ao nome do arquivo de log que é criado quando você executa a ferramenta no modo de exclusão.  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |Especifica a pasta que contém o arquivo de configuração. XML que foi criado quando você executou a ferramenta no modo de coleta. Use o mesmo valor que você usou para esse parâmetro na etapa 3.  <br/> | `-ConfigurationLocation "c:\users\admin\ desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |Especifica a pasta para a qual o arquivo de log do modo de exclusão será copiado. Esse é um parâmetro opcional. Se você não incluir, o arquivo de log será copiado para a pasta onde você baixou a ferramenta de coleção PST. Considere usar o mesmo local de log que você usou ao executar a ferramenta nos modos localizar e coletar na etapa 1 e etapa 3 para que todos os arquivos de log sejam salvos na mesma pasta.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |Essa opção opcional permite executar novamente a ferramenta no modo de exclusão de um trabalho da coleção PST existente. Se você já executou a ferramenta no modo de exclusão, mas executou a ferramenta novamente no modo localizar com o `ForceRestart` switch para examinar novamente os locais de arquivos PST, você pode usar essa opção para executar novamente a ferramenta no modo de exclusão e excluir os arquivos pst que foram encontrados quando você examinou novamente os locais. Ao usar a `ForceRestart` opção no modo de exclusão, a ferramenta ignora qualquer operação de exclusão anterior e tenta excluir os arquivos PST novamente.  <br/> | `-ForceRestart` <br/> 

    Veja um exemplo da sintaxe da ferramenta DataCollector. exe usando valores reais para cada parâmetro:
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    Após executar o comando, são exibidas mensagens de status detalhadas que mostram o progresso da exclusão dos arquivos PST que foram encontrados na etapa 1 e coletados na etapa 3. Após um tempo, uma mensagem de status final mostrará se houve algum erro e o local para o qual o log foi copiado. As mesmas mensagens de status são copiadas para o arquivo. log.
    
### <a name="results-of-running-datacollectormasterexe-in-the-delete-mode"></a>Resultados da execução do DataCollector. exe no modo de exclusão

Após executar com êxito o DataCollector. exe no modo de exclusão, os arquivos a seguir são criados e armazenados na pasta especificada pelos parâmetros `LogLocation` e. `ConfigurationLocation` 
  
- **\>__ JobName Delete\<DateTimeStamp\>. log-o arquivo de log contém as mensagens de status \<** que foram exibidas. Esse arquivo é criado na pasta especificada pelo `LogLocation` parâmetro. 
    
- **\>__ JobName Delete\<DateTimeStamp\>. xml-o arquivo XML contém apenas informações sobre os valores de parâmetro que, em que foram usados pela ferramenta, foram executados no \<** modo de exclusão. Ele também lista o nome e o caminho do arquivo de cada arquivo PST que foi excluído. Esse arquivo é criado na pasta especificada pelo `ConfigurationLocation` parâmetro. 
