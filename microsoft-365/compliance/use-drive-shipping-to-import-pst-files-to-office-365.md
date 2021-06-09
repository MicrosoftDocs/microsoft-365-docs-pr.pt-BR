---
title: Usar o envio de unidade para importar os arquivos PST da sua organização
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 40829b57-793c-4d41-b171-e9270129173d
ms.custom: seo-marvel-apr2020
description: O administrador pode aprender a importar arquivos PST em massa para Microsoft 365 caixas de correio copiando arquivos PST para um disco rígido e, em seguida, enviando-os para a Microsoft.
ms.openlocfilehash: a0858e3c1b6bcbe48a4060e8efaa3094768236fb
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684071"
---
# <a name="use-drive-shipping-to-import-your-organizations-pst-files"></a>Usar o envio de unidade para importar os arquivos PST da sua organização

**Este artigo é para administradores. Você está tentando importar arquivos PST para sua própria caixa de correio? Consulte [Importar email, contatos e calendário de um arquivo .pst Outlook .pst](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
Use o Office 365 de importação e o envio de unidade para importar arquivos PST em massa para caixas de correio de usuário. O Envio de Unidade significa que você copia os arquivos PST em uma unidade de disco rígido e, em seguida, envia essa unidade fisicamente para a Microsoft. Quando a Microsoft recebe seu disco rígido, a equipe do data center copia os dados do disco rígido para uma área de armazenamento na nuvem da Microsoft. Em seguida, você tem a oportunidade de cortar os dados PST importados para as caixas de correio de destino definindo filtros que controlam quais dados são importados. Depois de iniciar o trabalho de importação, o serviço importar os dados PST da área de armazenamento para as caixas de correio do usuário. Usar o envio de unidade para importar arquivos PST para caixas de correio de usuário é uma maneira de migrar o email da sua organização para Office 365.
  
Aqui estão as etapas necessárias para usar o envio de unidade para importar arquivos PST para Microsoft 365 caixas de correio:
  
[Etapa 1: Baixar a chave de armazenamento seguro e a ferramenta de importação PST](#step-1-download-the-secure-storage-key-and-pst-import-tool)

[Etapa 2: copiar os arquivos PST para o disco rígido](#step-2-copy-the-pst-files-to-the-hard-drive)

[Etapa 3: Criar o arquivo de mapeamento de Importação de PST](#step-3-create-the-pst-import-mapping-file)

[Etapa 4: criar um trabalho de Importação de PST no Office 365](#step-4-create-a-pst-import-job-in-office-365)

[Etapa 5: enviar o disco rígido para a Microsoft](#step-5-ship-the-hard-drive-to-microsoft)

[Etapa 6: Filtrar os dados e iniciar o trabalho de importação de PST](#step-6-filter-data-and-start-the-pst-import-job)
  
> [!IMPORTANT]
> Você precisa executar a Etapa 1 uma vez para baixo carregar a chave de armazenamento segura e a ferramenta de importação. Depois de executar essas etapas, siga a Etapa 2 até a Etapa 6 sempre que quiser enviar um disco rígido para a Microsoft. 
  
Para perguntas frequentes sobre como usar o envio de unidade para importar arquivos PST para Office 365, consulte Perguntas frequentes sobre como usar o envio de unidade para [importar arquivos PST](./faqimporting-pst-files-to-office-365.yml#using-drive-shipping-to-import-pst-files). 
  
## <a name="before-you-import-pst-files"></a>Antes de importar arquivos PST

- Você deverá ter a função Exportação Importação da Caixa de Correio no Exchange Online para importar arquivos PST para as caixas de correio do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Importação e Exportação de Caixa de Correio no grupo de função Gerenciamento da Organização. Ou você pode criar um grupo de função, atribuir a função de exportação de importação de caixa de correio e adicionar a si mesmo como membro. Para mais informações, confira as seções "Adicionar uma função a um grupo de funções" ou as seções "Criar um grupo de funções" em [Gerenciar grupos de funções](/Exchange/permissions-exo/role-groups).
    
    Além disso, para criar trabalhos de importação no Microsoft 365 de conformidade, um dos seguintes requisitos deve ser verdadeiro:
    
  - Você precisa ter a função Destinatários de Email no Exchange Online. Por padrão, esta função é atribuída aos grupos de funções de Gerenciamento da Organização e Gerenciamento de Destinatários.
    
    Ou
    
  - É necessário que você seja um administrador global na sua organização.
    
    > [!TIP]
    > Considere a criação de um novo grupo de função no Exchange Online destinado especificamente a importar os arquivos PST para o Office 365. Para o nível mínimo de privilégios necessários para importar os arquivos PST, atribua as funções de Exportação Importação de Caixa de Correio e Destinatários de email ao novo grupo de função e, em seguida, adicione membros. 
  
- Armazene os arquivos PST que pretende copiar no disco rígido, em um servidor de arquivos ou pasta compartilhada da organização. Na Etapa 2, execute a ferramenta de Exportação de Importação do Azure (WAImportExport.exe) que copia os arquivos PST armazenados neste servidor de arquivos ou pasta compartilhada no disco rígido.

- Arquivos PST muito grandes podem afetar o desempenho do processo de importação de PST. Portanto, recomendamos que cada arquivo PST que você copiar para o disco rígido na Etapa 2 não seja maior do que 20 GB.
    
- Apenas unidades de estado sólido (SSDs) de 2,5 polegadas ou discos rígidos internos SATA II/III de 3,5 polegadas são suportados para uso com o serviço Office 365 Import. Use discos rígidos de até 10 TB. Para trabalhos de importação, somente o primeiro volume de dados do disco rígido será processado. O volume de dados deve ser formatado com NTFS. Ao copiar dados para um disco rígido, você pode anexá-los diretamente usando um SSD de 2,5 polegadas ou um conector SATA II/III de 3,5 polegadas ou pode anexá-los externamente usando um SSD externo de 2,5 polegadas ou um adaptador USB de 2,5 polegadas ou 3,5 polegadas SATA II/III.
    
    > [!IMPORTANT]
    > As unidades de disco rígido com um adaptador USB interno não são compatíveis com o serviço de importação do Office 365. Além disso, o disco dentro da caixa do disco rígido externo não pode ser utilizado. Não remova discos rígidos externos. 
  
- O disco rígido no qual você copiar os arquivos PST deve ser criptografado com o BitLocker. A ferramenta WAImportExport.exe usada na etapa 2 o ajudará a configurar o BitLocker. Ele também gera uma chave BitLocker de criptografia usada pela equipe do data center da Microsoft para acessar a unidade para carregar os arquivos PST na área de Armazenamento do Azure na nuvem da Microsoft.
    
- O envio de unidade está disponível por meio de um Microsoft Enterprise Agreement (EA). O envio de unidade não está disponível por meio de um Contrato de Produtos e Serviços da Microsoft (MPSA).
    
- O custo de importação dos arquivos PST para as caixas de correio do Microsoft 365 usando o envio de unidade é de US$ 2 por GB de dados. Por exemplo, se você enviar um disco rígido contendo 1.000 GB (1 TB) de arquivos PST, o custo será de US$ 2.000. Você pode trabalhar com um parceiro para pagar a taxa de importação. Para obter mais informações sobre como encontrar um parceiro, confira [Encontrar seu parceiro ou revendedor do Microsoft 365](../admin/manage/find-your-partner-or-reseller.md).
    
- Você ou a organização devem ter uma conta da FedEx ou da DHL. 
    
  - As organizações nos Estados Unidos, Brasil e Europa devem ter contas fedEx.
    
  - As organizações no Leste Asiático, Sudeste Asiático, Japão, República da Coreia e Austrália devem ter contas DHL.
    
    A Microsoft usa (e cobra) essa conta para retornar o disco rígido para você.
    
- O disco rígido que você enviar para a Microsoft pode cruzar fronteiras internacionais. Nesse caso, você é responsável por garantir que o disco rígido e os dados que ele contém sejam importados e/ou exportados de acordo com as leis aplicáveis. Antes de enviar um disco rígido, peça aos seus consultores para verificar se a unidade e os dados podem ser enviados legalmente para o datacenter identificado da Microsoft. Isso ajuda a garantir que ela chegue à Microsoft em tempo hábil.
    
- Esse procedimento implica copiar e salvar uma chave do armazenamento seguro e uma chave de criptografia BitLocker. Não deixe de tomar medidas para proteger estas chaves, do mesmo modo que o faria com senhas ou outras informações relacionadas à segurança. Por exemplo, você pode salvá-las em um documento do Microsoft Word protegido por senha ou em uma unidade USB criptografada. Consulte a [seção Mais informações](#more-information) para obter um exemplo dessas chaves. 
    
- Depois que os arquivos PST são importados para uma caixa de correio de Microsoft 365, a configuração de retenção da caixa de correio é 24 horas por tempo indeterminado. Isso significa que a política de retenção atribuída à caixa de correio não será processada até que o bloqueio de retenção seja desativado ou que uma data para a desativação seja definida. Por que fazemos isso? Se as mensagens importadas para uma caixa de correio forem antigas, poderão ser excluídas permanentemente (eliminadas) porque o período de retenção expirou com base nas configurações de retenção definidas para a caixa de correio. Colocar a caixa de correio no bloqueio de retenção dará ao proprietário tempo de gerenciar essas mensagens importadas recentemente ou tempo para alterar as configurações de retenção da caixa de correio. Consulte a [seção Mais informações](#more-information) para obter sugestões sobre como gerenciar a retenção. 
    
- Por padrão, o tamanho máximo da mensagem que pode ser recebida por uma caixa de correio do Microsoft 365 é 35 MB. Isso ocorre porque o valor padrão da *Propriedade MaxReceiveSize* de uma caixa de correio está definida como 35 MB. No entanto, o limite para o tamanho máximo de recebimento de mensagens no Microsoft 365 é 150 MB. Portanto, se você importar um arquivo PST que contenha um item com mais de 35 MB, o serviço de importação do Office 365 altera automaticamente o valor da propriedade *MaxReceiveSize* na caixa de correio de destino para 150 MB. Isso permite que mensagens de até 150 MB sejam importadas para as caixas de correio dos usuários. 
    
    > [!TIP]
    > Para identificar o tamanho de recebimento da mensagem de uma caixa de correio, execute esse comando no Exchange Online PowerShell:  `Get-Mailbox <user mailbox> | FL MaxReceiveSize`. 
  
- É possível importar arquivos PST para uma caixa de correio inativa no Office 365. Isso é feito especificando o GUID da caixa de correio inativa no `Mailbox` parâmetro no arquivo de mapeamento de importação de PST. Consulte [a Etapa 3: Criar o arquivo de mapeamento de Importação de PST](#step-3-create-the-pst-import-mapping-file) para obter mais informações. 
    
- Em uma implantação híbrida do Exchange, você pode importar arquivos PST para uma caixa de correio de arquivo morto baseada na nuvem para um usuário cuja caixa de correio principal esteja no local. Para isso, faça o seguinte no arquivo de mapeamento de Importação de PST:
    
  - Especifique o endereço de email para a caixa de correio local do usuário no `Mailbox` parâmetro. 
    
  - Especifique o valor **VERDADEIRO** no `IsArchive` parâmetro. 
    
    Consulte [a Etapa 3: Criar o arquivo de mapeamento de Importação de PST](#step-3-create-the-pst-import-mapping-file) para obter mais informações. 

## <a name="step-1-download-the-secure-storage-key-and-pst-import-tool"></a>Etapa 1: Baixar a chave de armazenamento seguro e a ferramenta de importação PST

A primeira etapa é baixar a chave de armazenamento seguro e a ferramenta e que você usa na Etapa 2 para copiar arquivos PST para o disco rígido.
  
> [!IMPORTANT]
> Você precisa usar o Azure Importação/Exportação versão 1 da ferramenta (WAimportExportV1) para importar arquivos PST com êxito usando o método de envio de unidade. A versão 2 da ferramenta de Importação/Exportação do Azure não tem suporte e usá-la resultará na preparação incorreta do disco rígido para o trabalho de importação. Baixe a ferramenta de Importação/Exportação do Azure Microsoft 365 centro de conformidade seguindo os procedimentos nesta etapa. 
  
1. Vá para <https://compliance.microsoft.com> e entre usando as credenciais de uma conta de administrador em sua organização.

2. No painel de navegação esquerdo do centro de conformidade Microsoft 365, clique em **Importar governança de** \> **informações.**
    
    > [!NOTE]
    > Conforme mencionado anteriormente, você precisa ter as permissões apropriadas para acessar a página **Importar** no centro de conformidade Microsoft 365 de segurança. 
  
3. Na guia **Importar**, clique em ![Adicionar Ícone](../media/ITPro-EAC-AddIcon.gif) **Novo trabalho de importação**.
    
4. No assistente de trabalho de importação, digite um nome para o trabalho de importação PST e clique em **Próximo**. Use letras minúsculas, números, hifens e sublinhados. Não é possível usar letras maiúsculas ou incluir espaços no nome.
    
5. Na página **Escolher tipo de trabalho de** importação, clique em Enviar **discos rígidos** para um de nossos locais físicos e clique em **Próximo**.
    
    ![Clique em Enviar discos rígidos para um de nossos locais físicos para criar um trabalho de importação de envio de unidade](../media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. Na página **Importar Dados**, execute as duas seguintes etapas: 
    
    ![Copie a chave de armazenamento seguro e baixe a ferramenta exportação de importação do Azure na página Importar dados](../media/e22e0b48-e5ce-48e0-95bc-0490a2b3b983.png)
  
    a. Na etapa 2, clique em **Mostrar a chave de armazenamento seguro**. Depois que a chave de  armazenamento for exibida, clique em Copiar para área de transferência e, em seguida, colar e salvá-la em um arquivo para que você possa acessá-la mais tarde.
    
    b. Na etapa 3, baixe a **ferramenta Importação/Exportação do Azure** para baixar e instalar a ferramenta Azure Importação/Exportação (versão 1).
    
    - Na janela pop-up, clique em **Salvar** Salvar como para salvar o arquivo \>  WaImportExportV1.zip em uma pasta em seu computador local. 
    
    - Extraia o WaImportExportV1.zip arquivo.
    
7. Clique **em Cancelar** para fechar o assistente. 
    
    Você volta para a página **Importar** no centro de conformidade Microsoft 365 ao criar o trabalho de importação na Etapa 4. 

## <a name="step-2-copy-the-pst-files-to-the-hard-drive"></a>Etapa 2: copiar os arquivos PST para o disco rígido

A etapa a seguir consiste em usar a ferramenta WAImportExport.exe para copiar arquivos PST no disco rígido. Com essa ferramenta, você criptografa o disco rígido com BitLocker, copia os arquivos PST no disco rígido e cria um arquivo de diário que armazena informações sobre o processo de cópia. Para concluir essa etapa, você deve colocar os arquivos PST em um compartilhamento de arquivos ou servidor de arquivos da organização. Esse local é conhecido como diretório de origem no procedimento a seguir. 

 Como mencionado anteriormente, cada arquivo PST que você copiar para o disco rígido não deve ser maior do que 20 GB. Arquivos PST com mais de 20 GB podem afetar o desempenho do processo de importação de PST iniciado na etapa 6.
  
> [!IMPORTANT]
> Depois de executar a ferramenta WAImportExport.exe pela primeira vez em um disco rígido, use sintaxes diferentes nas próximas execuções. Essa sintaxe é explicada na etapa 4 deste procedimento para copiar arquivos PST para o disco rígido. 
  
1. Abra um prompt de comando no computador local.
    
    > [!TIP]
    > Se você executar o prompt de comando como administrador (selecionando a opção "Executar como Administrador" exibida), o sistema exibirá mensagens de erro na janela do prompt de comando. Isso pode ser útil para solucionar problemas de execução da ferramenta WAImportExport.exe. 
  
2. Vá para o diretório em que instalou a ferramenta WAImportExport.exe na etapa 1.
    
3. Execute o seguinte comando na primeira vez que usar a ferramenta WAImportExport.exe para copiar arquivos PST em um disco rígido.

    ```powershell
    WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /blobtype:BlockBlob /encrypt /logdir:<Log file location>
    ```

    A tabela a seguir descreve os parâmetros e os valores necessários. 
    
    |**Parâmetro**|**Descrição**|**Exemplo**|
    |:-----|:-----|:-----|
    | `/j:` <br/> |Especifica o nome do arquivo de diário. Este arquivo será salvo na mesma pasta em que a ferramenta WAImportExport.exe está localizada. Cada disco rígido enviado para a Microsoft deve incluir um único arquivo de diário. Sempre que executar a ferramenta WAImportTool.exe para copiar arquivos PST em um disco rígido, as informações serão anexadas ao arquivo de diário dessa unidade. 
  <br/> A equipe do data center da Microsoft usa as informações no arquivo de diário para associar o disco rígido ao trabalho de importação criado na Etapa 4 e para carregar os arquivos PST para a área de Armazenamento do Azure na nuvem da Microsoft.  <br/> | `/j:PSTHDD1.jrn` <br/> |
    | `/t:` <br/> |Especifica a letra da unidade do disco rígido quando ele está conectado ao computador local.  <br/> | `/t:h` <br/> |
    | `/id:` <br/> |Especifica o nome da sessão de cópia. A sessão é definida sempre que você executa a ferramenta WAImportExport.exe para copiar arquivos no disco rígido. Os arquivos PST são copiados em uma pasta com o nome da sessão especificado por este parâmetro.   <br/> | `/id:driveship1` <br/> |
    | `/srcdir:` <br/> |Especifica o diretório de origem da organização, que contém os arquivos PST a serem copiados durante a sessão. Certifique-se de colocar o valor deste parâmetro entre aspas duplas (" ").  <br/> | `/srcdir:"\\FILESERVER01\PSTs"` <br/> |
    | `/dstdir:` <br/> |Especifica o diretório de destino na área de Armazenamento do Azure na nuvem da Microsoft onde os PSTs serão carregados. Você deve usar o valor  `ingestiondata/` . Certifique-se de colocar o valor deste parâmetro entre aspas duplas (" ").  <br/> Opcionalmente, você também pode adicionar um caminho de arquivo extra ao valor desse parâmetro. Por exemplo, você pode usar o caminho do arquivo do diretório de origem no disco rígido (convertido em um formato de URL), que é especificado no  `/srcdir:` parâmetro. Por exemplo,  `\\FILESERVER01\PSTs` é alterado para  `FILESERVER01/PSTs` . Nesse caso, você ainda deve  `ingestiondata` incluir no caminho do arquivo. Portanto, neste exemplo, o valor do  `/dstdir:` parâmetro seria  `"ingestiondata/FILESERVER01/PSTs"` .  <br/> Uma das razões para adicionar outros caminhos de arquivo é quando você tem arquivos PST com nomes de arquivos iguais.  <br/> > [!NOTE]> Se você incluir o nome do caminho opcional, o namespace de um arquivo PST depois que ele for carregado para a área de Armazenamento do Azure inclui o nome do caminho e o nome do arquivo PST; por exemplo, `FILESERVER01/PSTs/annb.pst` . Se você não incluir um nome de caminho, o namespace será apenas o nome de arquivo PST; por exemplo  `annb.pst` .           | `/dstdir:"ingestiondata/"` <br/> Ou  <br/>  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` <br/> |
    | `/sk:` <br/> |Especifica a chave da conta de armazenamento obtida na etapa 1. Certifique-se de colocar o valor deste parâmetro entre aspas duplas (" ").  <br/> | `"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ=="` <br/> |
    | `/blobtype:` <br/> |Especifica o tipo de blobs na área de Armazenamento do Azure para a qual importar os arquivos PST. Para importar arquivos PST, use o valor **BlockBlob**. Esse parâmetro é obrigatório.   <br/> | `/blobtype:BlockBlob` <br/> |
    | `/encrypt` <br/> |Esta opção habilita o BitLocker no disco rígido. Este parâmetro é necessário na primeira vez que executar a ferramenta WAImportExport.exe.  <br/> A BitLocker de criptografia é copiada para o arquivo de diário e o arquivo de log criado se você usar o `/logfile:` parâmetro. Conforme explicamos, o arquivo de diário é salvo na mesma pasta em que a ferramenta WAImportExport.exe está localizada.  <br/> | `/encrypt` <br/> |
    | `/logdir:` <br/> |Esse parâmetro opcional especifica uma pasta para salvar arquivos de log. Se não for especificado, os arquivos de log serão salvos na mesma pasta onde WAImportExport.exe ferramenta está localizada. Certifique-se de colocar o valor deste parâmetro entre aspas duplas (" ").  <br/> | `/logdir:"c:\users\admin\desktop\PstImportLogs"` <br/> |
   
    Veja um exemplo da sintaxe para a ferramenta WAImportExport.exe, que usa valores reais para os parâmetros:
    
    ```powershell
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER01\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" blobtype:BlockBlob /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"
    ```

    Depois de executar o comando, o sistema exibe mensagens de status que mostram o andamento da cópia dos arquivos PST no disco rígido. Uma mensagem de status final mostra o número total de arquivos que foram copiados com êxito. 
    
4. Execute este comando sempre que executar a ferramenta WAImportExport.ext para copiar arquivos PST no mesmo disco rígido.

    ```powershell
    WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> /blobtype:BlockBlob 
    ```

    Veja um exemplo da sintaxe para a execução de sessões subsequentes para copiar os arquivos PST no mesmo disco rígido.  

    ```powershell
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER01\PSTs\SecondBatch" /dstdir:"ingestiondata/" /blobtype:BlockBlob
    ```

## <a name="step-3-create-the-pst-import-mapping-file"></a>Etapa 3: Criar o arquivo de mapeamento de Importação de PST

Depois que a equipe do data center da Microsoft carregar os arquivos PST do disco rígido para a área do Azure Armazenamento, o serviço import usará as informações no arquivo de mapeamento de Importação de PST, que é um arquivo CSV (valor separado por vírgula), que especifica para quais caixas de correio de usuário os arquivos PST são importados. Você enviará esse arquivo CSV na etapa seguinte, quando criar um trabalho de Importação de PST.
  
1. [Baixar uma cópia do arquivo de mapeamento para importação de PST](https://go.microsoft.com/fwlink/p/?LinkId=544717).
    
2. Abrir ou salvar o arquivo CSV no computador local. O exemplo a seguir mostra um arquivo de mapeamento para Importação de PST concluído (aberto no Bloco de notas). É muito mais fácil usar o Microsoft Excel para editar o arquivo CSV.

    ```text
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,FILESERVER01/PSTs,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,,,,,
    ```

    A primeira linha ou linha de cabeçalho do arquivo CSV enumera os parâmetros que serão usados pelo serviço de Importação de PST para importar os arquivos PST para as caixas de correio de usuário. Os nomes dos parâmetros são separados por vírgula. Cada linha sob a linha de cabeçalho representa os valores de parâmetro para a importação de um arquivo PST em uma caixa de correio específica. Você precisa de uma linha para cada arquivo PST que foi copiado para o disco rígido. Não deixe de substituir os dados de espaço reservado do arquivo de mapeamento pelos dados reais.

    > [!NOTE]
    > Não altere o conteúdo da linha de cabeçalho, inclusive os parâmetros SharePoint; eles serão ignorados durante o processo de Importação de PST. 
  
3. Use as informações da tabela a seguir para preencher o arquivo CSV com as informações necessárias.
    
    |**Parâmetro**|**Descrição**|**Exemplo**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Especifica o serviço do para o qual os dados serão importados. Para importar arquivos PST nas caixas de correio de usuário, use o  `Exchange`.  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> | Especifica o local da pasta na área de Armazenamento do Azure para a onde os arquivos PST serão copiados quando o disco rígido for enviado para a Microsoft.  <br/>  O que você adicionar nesta coluna no arquivo CSV depende do que você especificou para o parâmetro  `/dstdir:` na etapa anterior. Se você tiver subpastas no local de origem, o valor no parâmetro deverá conter o caminho relativo da `FilePath` subpasta; por exemplo, /folder1/user1/.  <br/>  Se você usou  `/dstdir:"ingestiondata/"` , deixe esse parâmetro em branco no arquivo CSV.  <br/>  Se você incluiu um nome de caminho opcional para o valor do parâmetro (por exemplo, , use esse nome de caminho (sem incluir "ingestiondata") para esse parâmetro no arquivo  `/dstdir:`  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` CSV. O valor desse parâmetro diferencia maiúsculas de minúsculas.  <br/>  De qualquer forma, *não* inclua "ingestiondata" no valor do `FilePath` parâmetro. Deixe esse parâmetro em branco ou especifique apenas o nome do caminho opcional.  <br/> > [!IMPORTANT]> O caso do nome do caminho do arquivo deve ser o mesmo que você especificou no  `/dstdir:` parâmetro na etapa anterior. Por exemplo, se você usou para o nome da subpasta na etapa anterior, mas depois usado no parâmetro no arquivo CSV, a importação do arquivo  `"ingestiondata/FILESERVER01/PSTs"`  `fileserver01/psts`  `FilePath` PST falhará. Certifique-se de usar a mesma capitalização nas duas instâncias.           |(deixar em branco)  <br/> Ou  <br/>  `FILESERVER01/PSTs` <br/> |
    | `Name` <br/> |Especifique o nome do arquivo PST que será importado para a caixa de correio do usuário. O valor desse parâmetro diferencia maiúsculas de minúsculas.  <br/> > [!IMPORTANT]> O caso do nome de arquivo PST no arquivo CSV deve ser o mesmo do arquivo PST que foi carregado para o local de Armazenamento do Azure na Etapa 2. Por exemplo, se você usar `annb.pst` o `Name` no parâmetro no arquivo CSV, mas o nome do arquivo PST atual  para `AnnB.pst`, a importação desse arquivo PST falhará. Certifique-se de que o nome do PST no arquivo CSV usa a mesma capitalização do arquivo PST atual.           | `annb.pst` <br/> |
    | `Mailbox` <br/> |Especifica o endereço de email da caixa de correio para a qual o arquivo PST será importado. Observe que não é possível especificar uma pasta pública porque o Serviço de Importação de PST não é compatível com a importação de arquivos PST para pastas públicas.  <br/> Para importar um arquivo PST para uma caixa de correio inativa, é preciso especificar o GUID da caixa de correio para esse parâmetro. Para obter esse GUID, execute o seguinte comando do PowerShell no Exchange Online:  `Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> > [!NOTE]>, às vezes, você pode ter várias caixas de correio com o mesmo endereço de email, onde uma caixa de correio é uma caixa de correio ativa e a outra está em um estado de exclusão suave (ou inativa). Nesses casos, você precisa especificar o GUID da caixa de correio para identificar exclusivamente a caixa de correio para a qual o arquivo PST será importado. Para obter esse GUID para caixas de correio ativas, execute o seguinte comando do PowerShell:  `Get-Mailbox <identity of active mailbox> | FL Guid`. Para obter o GUID para caixas de correio excluídas (ou inativas) excluídas, execute este comando:  `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid` .           | `annb@contoso.onmicrosoft.com` <br/> Ou  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Especifica se o arquivo PST deve ser importado para a caixa de correio de arquivo morto do usuário. Existem duas opções:<br/> **FALSE** Importa o arquivo PST para a caixa de correio principal do usuário.  <br/> **TRUE** Importa o arquivo PST para a caixa de correio de arquivo morto do usuário. Isso pressupõe que a [caixa de correio de arquivo morto do usuário está habilitada](enable-archive-mailboxes.md). Se definir este parâmetro para `TRUE` e a caixa de correio de arquivo morto do usuário não estiver habilitada, a importação para esse usuário falhará. Se uma importação falhar para um usuário (porque o arquivo morto dele não está habilitado e esta propriedade está definida para `TRUE`), os outros usuários no trabalho de importação não serão afetados.  <br/>  Se você deixar este parâmetro em branco, o arquivo PST será importado para a caixa de correio principal do usuário.  <br/> **Observação:** para importar um arquivo PST para uma caixa de correio de arquivo morto baseada na nuvem de um usuário cuja caixa de correio principal está no local, basta especificar `TRUE` para este parâmetro e especificar o endereço de email da caixa de correio no local do usuário para o parâmetro `Mailbox`.  <br/> | `FALSE` <br/> Ou  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Especifica a pasta da caixa de correio para a qual o arquivo PST será importado.  <br/>  Se você deixar esse parâmetro em branco, o PST será importado para uma nova pasta denominada **Importada** localizada no nível raiz da caixa de correio (no mesmo nível que a pasta Caixa de Entrada e as outras pastas de caixa de correio padrão).  <br/>  Se você especificar  `/` , os itens no arquivo PST serão importados diretamente para a pasta Caixa de Entrada do usuário.  <br/>  Se você especificar  `/<foldername>` , os itens no arquivo PST serão importados para uma pasta chamada  *\<foldername\>* . Por exemplo, se você usar  `/ImportedPst` os itens serão importados para uma pasta chamada **ImportedPst**. Essa pasta estará localizada na caixa de correio do usuário, no mesmo nível da pasta Caixa de Entrada.  <br/> |(deixar em branco)  <br/> Ou  <br/>  `/` <br/> Ou  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Esse parâmetro opcional especifica um valor numérico para a página do código a ser usado para importar arquivos PST no formato de arquivo ANSI. Esse parâmetro é usado para importar arquivos PST de organizações em chinês, japonês e coreano (CJK) porque esses idiomas geralmente usam um DBCS (conjunto de caracteres de dois bytes) para codificação de caracteres. Se esse parâmetro não for usado para importar arquivos PST para idiomas que usam DBCS para nomes de pasta de caixa de correio, os nomes das pastas geralmente ficam incorretos após a importação.  <br/> Para obter uma lista de valores com suporte para esse parâmetro, confira [Identificadores de Página de Código](/windows/win32/intl/code-page-identifiers).  <br/> > [!NOTE]> como mencionado anteriormente, este é um parâmetro opcional e você não precisa incluí-lo no arquivo CSV. Ou você pode incluí-lo e deixar o valor em branco para uma ou mais linhas.           |(deixar em branco)  <br/> Ou  <br/>  `932` (que é o identificador da página de código para ANSI/OEM japonês)  <br/> |
    | `SPFileContainer` <br/> |Deixe este parâmetro em branco para Importação de PST.  <br/> |Não aplicável  <br/> |
    | `SPManifestContainer` <br/> |Deixe este parâmetro em branco para Importação de PST.  <br/> |Não aplicável  <br/> |
    | `SPSiteUrl` <br/> |Deixe este parâmetro em branco para Importação de PST.  <br/> |Não aplicável  <br/> |

## <a name="step-4-create-a-pst-import-job-in-office-365"></a>Etapa 4: criar um trabalho de Importação de PST no Office 365

A etapa a seguir consiste em criar o trabalho de Importação de PST no serviço Importação do Office 365. Conforme explicado anteriormente, você envia o arquivo de mapeamento de Importação de PST criado na Etapa 3. Depois de criar o trabalho, o serviço import usará as informações no arquivo de mapeamento para importar os arquivos PST para a caixa de correio de usuário especificada depois que os arquivos PST são copiados do disco rígido para a área de Armazenamento do Azure e você cria e inicia o trabalho de importação.
  
1. Vá para <https://compliance.microsoft.com> e entre usando as credenciais de uma conta de administrador em sua organização.

2. No painel de navegação esquerdo do centro de conformidade Microsoft 365, clique em **Importar governança de** \> **informações.**

3. Na guia **Importar**, clique em ![Adicionar Ícone](../media/ITPro-EAC-AddIcon.gif) **Novo trabalho de importação**.

    > [!NOTE]
    > Conforme mencionado anteriormente, você precisa ter as permissões apropriadas para acessar a página **Importar** no centro de conformidade Microsoft 365 de segurança.
  
4. Digite um nome para o trabalho de Importação PST e clique em **Avançar**. Use letras minúsculas, números, hifens e sublinhados. Não é possível usar letras maiúsculas ou incluir espaços no nome.

5. Na página **Escolher tipo de trabalho de** importação, clique em Enviar **discos rígidos** para um de nossos locais físicos e clique em **Próximo**.
  
6. Na etapa 6,  clique nas caixas de seleção Eu preparei meus  discos rígidos e tenho acesso aos arquivos de diário de unidade necessários e eu tenho acesso às caixas de seleção de arquivo de mapeamento e clique em **Próximo**.

    ![Clique nas duas caixas de seleção na etapa 6](../media/fad43078-ea68-4acd-b2ed-75a800183262.png)
  
7. Na página **Selecionar o arquivo de unidade,** clique em Selecionar arquivo **de** unidade e vá para a mesma pasta onde a WAImportExport.exe ferramenta está localizada. O arquivo de diário criado na etapa 2 foi copiado nessa pasta.

    ![Clique em Selecionar arquivo de unidade para enviar o arquivo de diário criado quando você WAImportExport.exe ferramenta](../media/1ea35c04-bd88-4d7e-b7d9-dc390149d94f.png)
  
8. Selecione o arquivo de diário; por exemplo, `PSTHDD1.jrn` .

    > [!TIP]
    > Quando você fez a WAImportExport.exe na Etapa 2, o nome do arquivo de diário foi especificado pelo  `/j:` parâmetro.
  
9. Depois que o nome do arquivo de unidade for exibido em **Nome** do arquivo drive, clique em **Validar** para verificar se há erros no arquivo de unidade.

    ![Clique em Validar para validar o arquivo de unidade selecionado](../media/4b707f5a-152a-4e74-b9f5-449c88d1fec4.png)
  
    O arquivo de unidade precisa ser validado com êxito para criar um trabalho de Importação PST. O nome do arquivo é alterado para verde após verde após ser validado com êxito. Se a validação falhar, clique no link **Exibir log**. Um relatório de erro de validação é aberto, com uma mensagem de erro com informações sobre por que o arquivo falhou. 

    > [!NOTE]
    > Você deve adicionar e validar um arquivo de diário para cada disco rígido que você enviar para a Microsoft. 
  
10. Depois de adicionar e validar um arquivo de diário para cada disco rígido que você enviar para a Microsoft, clique em **Próximo**.
    
11. Clique em Adicionar Ícone Selecione arquivo de mapeamento para enviar o arquivo de mapeamento de Importação de ![ ](../media/ITPro-EAC-AddIcon.gif)  PST que você criou na Etapa 3. 

    ![Clique em Selecionar arquivo de mapeamento para enviar o arquivo CSV que você criou para o trabalho de importação](../media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
12. Após o nome do arquivo CSV aparecer em **Nome do arquivo de mapeamento**, clique em **Validar** para verificar se há erros no arquivo CSV. 

    ![Clique em Validar para verificar se há erros no arquivo CSV](../media/4680999d-5538-4059-b878-2736a5445037.png)
  
    O arquivo CSV deve ser validado com êxito para criar um trabalho de importação de PST. O nome do arquivo é alterado para verde após verde após ser validado com êxito. Se a validação falhar, clique no link **Exibir log**. Um relatório de erro de validação é aberto, com uma mensagem de erro para cada linha no arquivo que falhou. 

13. Depois que o arquivo de mapeamento PST for validado com êxito, clique em **Next**.

14. Na página **Fornecer informações de contato,** digite suas informações de contato nas caixas aplicáveis. 

    O endereço para o local da Microsoft para o que você enviar seus discos rígidos é exibido. Esse endereço é gerado automaticamente com base no local do datacenter da Microsoft. Copie esse endereço em um arquivo ou faça uma captura de tela.

15. Leia o documento termos e condições, clique na caixa de seleção e clique em **Salvar** para enviar o trabalho de importação. 

    Quando o trabalho de importação é criado com êxito, uma página de status é exibida explicando as próximas etapas do processo de envio de unidade.

16. Na guia **Importar,** clique em Atualizar ícone Atualizar para exibir o novo trabalho de importação de envio de unidade ![ na lista de trabalhos de ](../media/O365-MDM-Policy-RefreshIcon.gif)  importação. O status é definido como **Aguardando o número de controle**. Você também pode clicar no trabalho de importação para exibir a página de sobremenu de status, que contém informações mais detalhadas sobre o trabalho de importação.

## <a name="step-5-ship-the-hard-drive-to-microsoft"></a>Etapa 5: enviar o disco rígido para a Microsoft

A próxima etapa é enviar o disco rígido para a Microsoft e, em seguida, fornecer o número de rastreamento para o carregamento e retornar informações de envio para o trabalho de envio de unidade. Depois que a unidade for recebida pela Microsoft, levará entre 7 e 10 dias úteis para a equipe do data center carregar seus arquivos PST na área de Armazenamento do Azure para sua organização.
  
> [!NOTE]
> Se você não fornecer o número de controle e retornar informações de envio dentro de 14 dias após a criação do trabalho de importação, o trabalho de importação será expirado. Se isso acontecer, você terá que criar um novo trabalho de importação de envio de unidade (consulte [Etapa 4:](#step-4-create-a-pst-import-job-in-office-365)Criar um trabalho de Importação de PST no Office 365 ) e enviar o arquivo de unidade e o arquivo de mapeamento de importação de PST.
  
### <a name="ship-the-hard-drive"></a>Enviar o disco rígido

Quando enviar discos rígidos para a Microsoft, lembre-se do seguinte:
  
- Não enviar o adaptador SATA para USB; você só precisa enviar o disco rígido.

- Embale o disco rígido de forma adequada; por exemplo, use plástico-bolha ou uma bolsa antiestática.

- Use uma transportadora de entrega de sua preferência para enviar o disco rígido à Microsoft.

- Envie o disco rígido para o endereço da Microsoft, exibido quando você criou o trabalho de importação na etapa 4. Não deixe de incluir o título "Serviço de Importação do Office 365" no endereço para entrega.

- Depois de enviar o disco rígido, lembre-se de anotar o nome da trasportadora e o número de rastreamento. Você vai precisar deles na etapa seguinte.
    
### <a name="enter-the-tracking-number-and-other-shipping-information"></a>Insira o número de rastreamento e outras informações da remessa.

Depois de enviar o disco rígido para a Microsoft, faça o procedimento a seguir na página do serviço Importar.
  
1. Vá para <https://compliance.microsoft.com> e entre usando as credenciais de uma conta de administrador em sua organização.

2. No painel de navegação esquerdo do centro de conformidade Microsoft 365, clique em **Governança de informações > Importar**.

3. Na guia **Importar,** clique no trabalho para o carregamento de unidade para o que você deseja inserir o número de controle.

4. Na página de sobrevoo de status, clique **em Inserir o número de controle**.

5. Forneça as seguintes informações sobre a remessa:

   1. **Transportadora de entrega** Digite o nome da operadora de entrega que você usou para enviar o disco rígido para a Microsoft. 

   2. **Número de controle** Digite o número de rastreamento para o envio do disco rígido. 

   3. **Retornar o número da conta de operadora** Digite o número da conta da sua organização para a operadora listada em **Operadora de retorno**. A Microsoft usa (e cobra) essa conta para enviar seu disco rígido de volta para você. As organizações nos EUA e na Europa devem ter uma conta com o FedEx. As organizações sediadas na Ásia e no restante do mundo devem ter contas da DHL.

6. Clique em **Salvar** para salvar essas informações do trabalho de importação. 

    Na guia **Importar,** clique em Atualizar ícone Atualizar para atualizar as informações do trabalho de importação ![ de envio de ](../media/O365-MDM-Policy-RefreshIcon.gif)  unidade. Observe agora que o status está definido como **Unidades em trânsito**.

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>Etapa 6: Filtrar os dados e iniciar o trabalho de importação de PST

Depois que seu disco rígido for recebido pela Microsoft, o status do trabalho de importação na página Importar **arquivos PST** mudará para **Unidades recebidas**. A equipe do data center usa as informações no arquivo de diário para carregar seus arquivos PST para a área de Armazenamento do Azure para sua organização. Neste ponto, o status muda para **Import in-progress**. Como mencionado anteriormente, levará entre 7 e 10 dias úteis após receber seu disco rígido para carregar os arquivos PST.
  
Depois que os arquivos PST são carregados no Azure, o status é alterado para **Análise em andamento.** Isso indica que Microsoft 365 está analisando os dados nos arquivos PST (de forma segura e segura) para identificar a idade dos itens e os diferentes tipos de mensagem incluídos nos arquivos PST. Quando a análise é concluída e os dados estão prontos para importação, o status do trabalho de importação é alterado para **Análise concluída.** Neste ponto, você tem a opção de importar todos os dados contidos nos arquivos PST ou pode cortar os dados importados definindo filtros que controlam quais dados são importados.
  
1. Vá para <https://compliance.microsoft.com> e entre usando as credenciais de uma conta de administrador em sua organização.

2. No painel de navegação esquerdo do centro de conformidade Microsoft 365, clique em **Governança** de informações \> **Import****.

3. Na guia **Importar,** selecione o trabalho de importação que você criou na Etapa 4 e clique em **Importar para** Office 365 .
  
    Uma página com submenu é exibida com informações sobre os arquivos PST e outras informações sobre o trabalho de importação.

4. Clique **em Importar para Office 365**.

5. A página **Filtrar seus dados** é exibida. Ela contém as informações sobre dados resultantes da análise realizada nos arquivos PST do Office 365, incluindo informações sobre a idade dos dados. Neste ponto, você tem a opção de filtrar os dados que serão importados ou importar todos os dados como estão. 

    ![Você pode cortar os dados dos arquivos PST ou importá-los](../media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
6. Siga um destes procedimentos:

    a. Para cortar os dados importados, clique em **Sim, desejo filtrá-los antes de importá-los**.

    Para obter instruções passo a passo detalhadas sobre como filtrar os dados nos arquivos PST e iniciar o trabalho de importação, confira [Filtrar dados ao importar arquivos PST para o Office 365](filter-data-when-importing-pst-files.md).

    Ou

    b. Para importar todos os dados dos arquivos PST, clique em **Não, Desejo importar tudo** e clique em **Avançar**.

7. Se optar por importar todos os dados, clique em **Importar dados** para iniciar o trabalho de importação. 

    O status do trabalho de importação é exibido na página **Importar arquivos PST.** Clique no ![Ícone Atualizar](../media/O365-MDM-Policy-RefreshIcon.gif) **Atualizar** para atualizar as informações de status exibidas na coluna **Status**.  Clique no trabalho de importação para exibir a página de status do submenu, que exibe informações de status sobre cada arquivo PST sendo importado.. Quando concluir a importação dos arquivos PST nas caixas de correio de usuário, o status passará a ser **Concluído**.

## <a name="view-a-list-of-the-pst-files-uploaded-to-microsoft-365"></a>Exibir uma lista dos arquivos PST carregados para Microsoft 365

Você pode instalar e usar o Gerenciador de Armazenamento do Microsoft Azure (que é uma ferramenta gratuita e de código aberto) para exibir a lista dos arquivos PST que são carregados (pela equipe do data center da Microsoft) para a área de Armazenamento do Azure para sua organização. Você pode fazer isso para verificar se os arquivos PST dos discos rígidos enviados à Microsoft foram carregados com êxito para a área de Armazenamento do Azure.
  
> [!IMPORTANT]
> Não é possível usar o Gerenciador de Armazenamento do Azure para carregar ou modificar arquivos PST. O único método suportado para importar arquivos PST para Microsoft 365 é usar o AzCopy. Além disso, não é possível excluir os arquivos PST que você carregou no blob do Azure. Se você tentar excluir um arquivo PST, receberá um erro sobre não ter as permissões necessárias. Todos os arquivos PST são excluídos automaticamente da área de Armazenamento do Azure. Se não houver trabalhos de importação em andamento, todos os arquivos PST no contêiner ** ingestiondata ** serão excluídos 30 dias após a criação do trabalho de importação mais recente.
  
Execute as etapas a seguir para obter a URL da Assinatura de Acesso Compartilhado (SAS) para sua organização. Essa URL é uma combinação da URL de rede para o local de Armazenamento do Azure na nuvem da Microsoft para sua organização e uma chave SAS. Essa chave fornece as permissões necessárias para acessar o local do Azure Armazenamento sua organização.

Para instalar o Gerenciador de Armazenamento do Azure e se conectar à sua área de armazenamento do Azure:

1. Vá para <https://compliance.microsoft.com> e entre usando as credenciais de uma conta de administrador em sua organização.

2. No painel esquerdo do Centro de Conformidade do Microsoft 365, clique em **controle de informações > Importar**.

3. Na guia **Importar**, clique em ![Adicionar Ícone](../media/ITPro-EAC-AddIcon.gif) **Novo trabalho de importação**.

4. No assistente de trabalho de importação, digite um nome para o trabalho de importação PST e clique em **Próximo**. Use letras minúsculas, números, hifens e sublinhados. Não é possível usar letras maiúsculas ou incluir espaços no nome.

5. Na página **Escolher tipo de trabalho de** importação, clique Upload **seus** dados e clique em **Próximo**.

6. Na etapa 2, clique em **Mostrar URL SAS de carregamento de rede**.

7. Depois que a URL for exibida, copie-a e salve-a em um arquivo. Não deixe de copiar a URL inteira.

    > [!IMPORTANT]
    > Certifique-se de proteger a URL da SAS. Isso pode ser usado por qualquer pessoa para acessar a área de armazenamento do Azure para sua organização.
  
8. Clique **em Cancelar** para fechar o assistente de trabalho de importação.

9. Baixe e instale a [Ferramenta Gerenciador de Armazenamento do Microsoft Azure ](https://go.microsoft.com/fwlink/p/?LinkId=544842).

10. Inicie o Gerenciador de armazenamento do Microsoft Azure, clique com o botão direito do mouse em **Contas de Armazenamento** no painel esquerdo e clique em **Conectar-se ao Armazenamento do Azure**.

    ![Clique com o botão direito em Contas de Armazenamento em Conectar-se ao Armazenamento do Azure](../media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
11. Clique em **Usar uma assinatura de acesso (SAS) URI ou uma cadeia de conexão** e clique em **Avançar**.

12. Clique **em Usar um URI SAS,** colar a URL do SAS obtida na etapa 1 na caixa em **URI** e clique em **Próximo**.

13. Na página **Resumo da conexão**, você pode revisar as informações de conexão e, em seguida, clique em **Conectar**.

    O contêiner **ingestiondata** será aberto. Ele contém os arquivos PST do seu disco rígido. O contêiner **ingestiondata** está localizado em uma **Conta de Armazenamento** \> **(SAS-Serviços Anexados)**\> **Contêineres de Blob**.

    ![O Gerenciador de Armazenamento do Azure exibe uma lista dos arquivos PST que você carregou](../media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
14. Ao terminar de usar o Gerenciador de Armazenamento do Azure, clique com botão direito em **ingestiondata** e, em seguida, clique em **Desanexar** para desconectar-se da sua área de armazenamento do Azure. Caso contrário, você receberá uma mensagem de erro na próxima vez que tentar anexar. 

    ![Clique com o botão direito em ingestão e clique em Desanexar para desconectar da sua área de armazenamento do Azure](../media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)

## <a name="troubleshooting-tips"></a>Dicas de solução de problemas

- **O que acontece se o trabalho de importação falhar devido a erros no arquivo de mapeamento CSV de Importação de PST?** Se um trabalho de importação falhar por causa de erros no arquivo de mapeamento, você não precisa re-reship o disco rígido para a Microsoft para criar um trabalho de importação. Isso porque os arquivos PST do disco rígido que você enviou para o trabalho de importação de envio de unidade já foram carregados para a área de Armazenamento do Azure para sua organização. Nesse caso, você só precisa corrigir os erros no arquivo de mapeamento CSV de Importação de PST e criar um novo trabalho de importação de "carregamento de rede" e enviar o arquivo de mapeamento CSV revisado. Para criar e iniciar um novo trabalho de importação de carregamento de rede, consulte [Etapa 5:](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job) Criar um trabalho de Importação de PST no Microsoft 365 e etapa [6:](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job) filtrar dados e iniciar o trabalho de Importação de PST no tópico "Usar carregamento de rede para importar arquivos PST para Office 365". 
    
    > [!NOTE]
    > Para ajudá-lo a solucionar problemas do arquivo de mapeamento CSV de Importação de PST, use a ferramenta Gerenciador de Armazenamento do Azure para exibir [a](#view-a-list-of-the-pst-files-uploaded-to-microsoft-365) estrutura de pastas no contêiner **de ingestiondata** para os arquivos PST do disco rígido que foram carregados na área de armazenamento do Azure. Erros de arquivo de mapeamento geralmente são causados por um valor incorreto no parâmetro FilePath. Este parâmetro especifica o local de um arquivo PST na área de armazenamento do Azure. Consulte a descrição do parâmetro FilePath na tabela [na Etapa 3](#step-3-create-the-pst-import-mapping-file). Conforme explicado anteriormente, o local dos arquivos PST na área de armazenamento do Azure foi especificado pelo parâmetro quando você correu a ferramenta  `/dstdir:` WAImportExport.exe na [Etapa 2](#step-2-copy-the-pst-files-to-the-hard-drive). 
  
## <a name="more-information"></a>Mais informações

- O envio de unidade é uma maneira eficaz de importar grandes quantidades de dados de mensagens de arquivamento para Microsoft 365 aproveitar os recursos de conformidade disponíveis para sua organização. Depois que os dados de arquivamento são importados para caixas de correio de usuário, você pode:

  - [Habilita caixas de correio de arquivo](enable-archive-mailboxes.md) morto [e](enable-unlimited-archiving.md) arquivamento de expansão automática para dar aos usuários mais espaço de armazenamento de caixa de correio para os dados. 

  - Coloque caixas de correio em [Retenção de Litígio](./create-a-litigation-hold.md) para reter os dados. 

  - Use as [ferramentas de Descoberta Online da](search-for-content.md) Microsoft para pesquisar os dados. 

  - Aplique [Microsoft 365 de](retention.md) retenção para controlar por quanto tempo os dados são mantidos e quais ações tomar após o período de retenção expirar. 

  - [Pesquise o log de auditoria](search-the-audit-log-in-security-and-compliance.md) em busca de eventos relacionados a esses dados. 

  - Importe dados para [caixas de correio inativas para](create-and-manage-inactive-mailboxes.md) arquivar dados para fins de conformidade. 

  - Proteja sua organização contra a [perda de dados](dlp-learn-about-dlp.md) de informações confidenciais. 

- Veja um exemplo da chave da conta de armazenamento seguro e de uma chave de criptografia BitLocker. Este exemplo inclui também a sintaxe para o comando da ferramenta WAImportExport.exe executada para copiar arquivos PST no disco rígido. Não deixe de tomar medidas para proteger esse conteúdo, do mesmo modo que o faria com senhas ou outras informações relacionadas à segurança.

    ```text
    Secure storage account key: 

    yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==

    BitLocker encryption key:

    397386-221353-718905-535249-156728-127017-683716-083391

  COMMAND SYNTAX

  First time:

  WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /blobtype:BlockBlob /encrypt /logdir:<Log file location>

  Subsequent times:

  WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> /blobtype:BlockBlob 

  EXAMPLES

  First time:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER1\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /blobtype:BlockBlob /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"

  Subsequent times:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER1\PSTs\SecondBatch" /dstdir:"ingestiondata/" /blobtype:BlockBlob
    ```

- Como explicado anteriormente, o serviço de importação do Office 365 ativa a configuração de retenção suspensa (para uma duração indefinida) após a importação dos arquivos PST para uma caixa de correio. Isso significa que  *a propriedade RentionHoldEnabled*  está definida como para que a política de retenção atribuída à caixa de correio não  `True` seja processada. Isso dá ao proprietário da caixa de correio o tempo para gerenciar as mensagens importadas recentemente, impedindo que uma política de exclusão ou arquivamento exclua ou arquive mensagens mais antigas. Veja algumas etapas que você pode executar para gerenciar essa retenção: 

  - Após um determinado período de tempo, você pode desativar a retenção executando o  `Set-Mailbox -RetentionHoldEnabled $false` comando. Para obter mais detalhes, consulte [Retenção local de uma caixa de correio em retenção](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold).

  - Você pode configurar a retenção para que ela seja desativada em alguma data no futuro. Faça isso executando o  `Set-Mailbox -EndDateForRetentionHold <date>` comando. Por exemplo, supondo que a data de hoje seja 1º de junho de 2016 e você deseja que a retenção seja desligada em 30 dias, execute o seguinte comando:  `Set-Mailbox -EndDateForRetentionHold 7/1/2016` . Nesse cenário, você deixaria a  *propriedade RentionHoldEnabled*  definida como  *True*. Para obter mais informações, consulte [Set-Mailbox](/powershell/module/exchange/set-mailbox).

  - Você pode alterar as configurações da política de retenção atribuída à caixa de correio para que os itens mais antigos que foram importados não sejam excluídos ou movidos imediatamente para a caixa de correio de arquivo morto do usuário. Por exemplo, você pode aumentar o período de retenção para uma política de exclusão ou arquivamento atribuída à caixa de correio. Nesse cenário, você desabilitaria a retenção na caixa de correio depois de alterar as configurações da política de retenção. Para obter mais informações, consulte [Configurar uma política de arquivamento e exclusão para caixas de correio em sua organização](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
