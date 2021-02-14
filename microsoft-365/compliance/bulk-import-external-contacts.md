---
title: Importar contatos externos em massa para o Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: Saiba como os administradores podem usar o PowerShell do Exchange Online e um arquivo CSV para importar em massa contatos externos para a lista de endereços global.
ms.openlocfilehash: 4d0b1a826583a032fd27c216367e99a6b7f8b371
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636339"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>Importar contatos externos em massa para o Exchange Online

**Este artigo é para administradores. Você está tentando importar contatos para sua própria caixa de correio? Confira [Importar contatos para o Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
Sua empresa tem muitos contatos comerciais existentes que você deseja incluir no livro de endereços compartilhado (também chamado de lista de endereços global) no Exchange Online? Você deseja adicionar contatos externos como membros de grupos de distribuição, assim como você pode com usuários dentro de sua empresa? Em caso afirmativo, você pode usar o PowerShell do Exchange Online e um arquivo CSV (valor separado por vírgula) para importar em massa contatos externos para o Exchange Online. É um processo de três etapas:
  
[Etapa 1: Criar um arquivo CSV que contenha informações sobre os contatos externos](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[Etapa 2: Criar os contatos externos com o PowerShell](#step-2-create-the-external-contacts-with-powershell) 

[Etapa 3: Adicionar informações às propriedades dos contatos externos](#step-3-add-information-to-the-properties-of-the-external-contacts)

Depois de concluir essas etapas para importar contatos, você poderá executar estas tarefas adicionais:
  
- [Adicionar mais contatos externos](#add-more-external-contacts)
  
- [Ocultar contatos externos do livro de endereços compartilhado](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>Etapa 1: Criar um arquivo CSV que contenha informações sobre os contatos externos

A primeira etapa é criar um arquivo CSV que contenha informações sobre cada contato externo que você deseja importar para o Exchange Online. 
  
1. Copie o texto a seguir para um arquivo de texto no Bloco de Notas e salve-o na área de trabalho como um arquivo CSV usando um sufixo de nome de arquivo .csv; por exemplo, ExternalContacts.csv.
    
    > [!TIP]
    > Se o seu idioma contiver caracteres especiais (como **å**, **ä** e **ö** em sueco), salve o arquivo CSV com UTF-8 ou outra codificação Unicode quando você salvar o arquivo no Bloco de Notas. 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    A primeira linha, ou linha de título, do arquivo CSV lista as propriedades de contatos que podem ser usadas ao importá-los para o Exchange Online. Cada nome de propriedade é separado por uma vírgula. Cada linha sob a linha de header representa os valores de propriedade para importar um único contato externo. 
    
    > [!NOTE]
    > Esse texto inclui dados de exemplo, que você pode excluir. Mas não exclua ou altere a primeira linha (header). Ele contém todas as propriedades dos contatos externos. 
  
2. Abra o arquivo CSV no Microsoft Excel para editar o arquivo CSV porque é muito mais fácil usar o Excel para editar o arquivo CSV.
    
3. Crie uma linha para cada contato que você deseja importar para o Exchange Online. Preencha o máximo possível de células. Essas informações serão exibidas no livro de endereços compartilhado de cada contato. 
    
    > [!IMPORTANT]
    >  As seguintes propriedades (que são os quatro primeiros itens na linha de título) são necessárias para criar um contato externo e devem ser preenchidas no arquivo CSV: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**. O comando do PowerShell executado na Etapa 2 usará os valores dessas propriedades para criar os contatos. 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>Etapa 2: Criar os contatos externos com o PowerShell

A próxima etapa é usar o arquivo CSV criado na Etapa 1 e o PowerShell para importar em massa os contatos externos listados no arquivo CSV para o Exchange Online. 
  
1.  Conecte o PowerShell à sua organização do Exchange Online. Para obter instruções passo a passo, confira [Conectar-se ao Exchange Online Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). Certifique-se de usar o nome de usuário e a senha da sua conta de administrador global ao se conectar ao PowerShell do Exchange Online. 
    
2. Depois de conectar o PowerShell ao Exchange Online, vá para a pasta da área de trabalho onde você salvou o arquivo CSV na Etapa 1; por `C:\Users\Administrator\desktop` exemplo.
    
3. Execute o seguinte comando para criar os contatos externos:

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    Pode levar algum tempo para criar os novos contatos, dependendo de quantos você está importando. Quando a execução do comando for concluída, o PowerShell exibirá uma lista dos novos contatos que foram criados. 
    
4. Para exibir os novos contatos externos, vá para o Centro de administração do Exchange (EAC) e clique em **Contatos** \> **de Destinatários.** 
    
    > [!TIP]
    > Para obter instruções sobre como se conectar ao EAC, confira o Centro de administração [do Exchange no Exchange Online.](https://go.microsoft.com/fwlink/p/?LinkId=328197) 
  
5. Se necessário, clique **em Atualizar** para atualizar a lista e ver os contatos externos que foram importados. 
    
    Os contatos importados aparecerão no livro de endereços compartilhado no Outlook e no Outlook na Web.
    
    > [!NOTE]
    > Você também pode exibir os contatos no centro de administração do Microsoft 365 indo para **Contatos** \> **dos Usuários.** 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>Etapa 3: Adicionar informações às propriedades dos contatos externos

Depois de executar o comando na Etapa 2, os contatos externos são criados, mas eles não contêm informações de contato ou organização, que são as informações da maioria das células no arquivo CSV. Isso acontece porque, quando você cria novos contatos externos, somente as propriedades necessárias são preenchidas. Não se preocupe se você não tiver todas as informações preenchidas no arquivo CSV. Se não estiver lá, ele não será adicionado.
  
1.  Conecte o PowerShell à sua organização do Exchange Online. Para obter instruções passo a passo, confira [Conectar-se ao Exchange Online Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Vá para a pasta da área de trabalho onde você salvou o arquivo CSV na Etapa 1; por exemplo, `C:\Users\Administrator\desktop` .
    
3. Execute os dois comandos a seguir para adicionar as outras propriedades do arquivo CSV aos contatos externos que você criou na Etapa 2.
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > O  _parâmetro Manager_ pode ser problemático. Se a célula estiver em branco no arquivo CSV, você receberá um erro e nenhuma das informações de propriedade será adicionada ao contato. Se você não precisar especificar um gerente, basta excluir  ` -Manager $_.Manager ` do comando anterior do PowerShell. 
  
    Novamente, pode levar algum tempo para atualizar os contatos, dependendo de quantos você importou na Etapa 1. 
    
4. Para verificar se as propriedades foram adicionadas aos contatos: 
    
1. No EAC, acesse **Destinatários** \> **Contatos**.
    
2. Clique em um contato e clique no **ícone** ![ Editar para exibir as propriedades do ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) contato. 
    
Isso é tudo. Os usuários podem ver os contatos e as informações adicionais no livro de endereços do Outlook e do Outlook na Web.
  
## <a name="add-more-external-contacts"></a>Adicionar mais contatos externos

Você pode repetir as etapas 1 a 3 para adicionar novos contatos externos no Exchange Online. Você ou usuários em sua empresa podem apenas adicionar uma nova linha no arquivo CSV para o novo contato. Em seguida, você pode executar os comandos do PowerShell nas Etapas 2 e 3 para criar e adicionar informações aos novos contatos.
  
> [!NOTE]
> Ao executar o comando para criar novos contatos, você pode receber um erro dizendo que os contatos criados anteriormente já existem. Mas qualquer novo contato adicionado ao arquivo CSV é criado. 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>Ocultar contatos externos da lista de endereços>

Algumas empresas podem usar contatos externos apenas para que possam ser adicionados como membros de grupos de distribuição. Nesse cenário, eles podem querer ocultar contatos externos do livro de endereços compartilhado. Veja como:
  
1.  Conecte o PowerShell à sua organização do Exchange Online. Para obter instruções passo a passo, confira [Conectar-se ao Exchange Online Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Para ocultar um único contato externo, execute o seguinte comando.
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    Por exemplo, para ocultar Pilar Pinilla do livro de endereços compartilhado, execute este comando:

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. Para ocultar todos os contatos externos do livro de endereços compartilhado, execute este comando:

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

Depois de o ocultar, os contatos externos não serão exibidos no livro de endereços compartilhado, mas você ainda poderá adicioná-los como membros de um grupo de distribuição.
