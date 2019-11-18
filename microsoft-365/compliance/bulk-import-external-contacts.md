---
title: Importação em massa de contatos externos para o Exchange Online
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
description: Saiba como os administradores podem usar o PowerShell do Exchange Online e um arquivo CSV para importar contatos externos para a lista de endereços global em massa.
ms.openlocfilehash: 272223d9ab61b2c5ae17043cf4523d49da306de9
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38684928"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>Importação em massa de contatos externos para o Exchange Online

**Este artigo é para administradores. Você está tentando importar contatos para sua própria caixa de correio? Confira [importar contatos para o Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
Sua empresa tem muitos contatos comerciais existentes que você deseja incluir no catálogo de endereços compartilhado (também chamado de lista de endereços global) no Exchange Online? Você deseja adicionar contatos externos como membros de grupos de distribuição, da mesma forma que é possível com os usuários dentro da sua empresa? Em caso afirmativo, você pode usar o PowerShell do Exchange Online e um arquivo CSV (valor separado por vírgula) para importar contatos externos em massa para o Exchange Online. É um processo de três etapas:
  
[Etapa 1: criar um arquivo CSV que contenha informações sobre os contatos externos](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[Etapa 2: criar os contatos externos com o PowerShell](#step-2-create-the-external-contacts-with-powershell) 

[Etapa 3: adicionar informações às propriedades dos contatos externos](#step-3-add-information-to-the-properties-of-the-external-contacts)

Após concluir essas etapas para importar contatos, você pode executar estas tarefas adicionais:
  
- [Adicionar mais contatos externos](#add-more-external-contacts)
  
- [Ocultar contatos externos do catálogo de endereços compartilhado](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>Etapa 1: criar um arquivo CSV que contenha informações sobre os contatos externos

A primeira etapa é criar um arquivo CSV que contenha informações sobre cada contato externo que você deseja importar para o Exchange Online. 
  
1. Copie o seguinte texto em um arquivo de texto no bloco de notas e salve-o em sua área de trabalho como um arquivo CSV usando um sufixo de nome de arquivo. csv; por exemplo, ExternalContacts. csv.
    
    > [!TIP]
    > Se seu idioma contiver caracteres especiais (como **å**, **ä**e **ö** em Sueco), salve o arquivo CSV com UTF-8 ou outra codificação Unicode quando você salvar o arquivo no bloco de notas. 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    A primeira linha, ou linha de cabeçalho, do arquivo CSV lista as propriedades de contatos que podem ser usadas quando você as importa para o Exchange Online. Cada nome de propriedade é separado por uma vírgula. Cada linha sob a linha de cabeçalho representa os valores de propriedade para importar um único contato externo. 
    
    > [!NOTE]
    > Este texto inclui dados de exemplo, que podem ser excluídos. Mas não exclua nem altere a primeira linha (cabeçalho). Ele contém todas as propriedades dos contatos externos. 
  
2. Abra o arquivo CSV no Microsoft Excel para editar o arquivo CSV porque é muito mais fácil usar o Excel para editar o arquivo CSV.
    
3. Crie uma linha para cada contato que você deseja importar para o Exchange Online. Preencha o máximo possível de células. Essas informações serão exibidas no catálogo de endereços compartilhado para cada contato. 
    
    > [!IMPORTANT]
    >  As propriedades a seguir (que são os primeiros quatro itens na linha de cabeçalho) são necessárias para criar um contato externo e devem ser preenchidas no arquivo CSV: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**. O comando do PowerShell executado na etapa 2 usará os valores dessas propriedades para criar os contatos. 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>Etapa 2: criar os contatos externos com o PowerShell

A próxima etapa é usar o arquivo CSV que você criou na etapa 1 e o PowerShell para importar em massa os contatos externos listados no arquivo CSV para o Exchange Online. 
  
1.  Conecte o PowerShell à sua organização do Exchange Online. Para obter instruções detalhadas, consulte [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). Certifique-se de usar o nome de usuário e a senha da sua conta de administrador global do Office 365 quando você se conectar ao PowerShell do Exchange Online. 
    
2. Depois de conectar o PowerShell ao Exchange Online, vá para a pasta da área de trabalho onde você salvou o arquivo CSV na etapa 1; por exemplo `C:\Users\Administrator\desktop`.
    
3. Execute o seguinte comando para criar os contatos externos:

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    Pode levar algum tempo para criar novos contatos, dependendo da quantidade que você está importando. Quando o comando termina de ser executado, o PowerShell exibe uma lista dos novos contatos que foram criados. 
    
4. Para exibir os novos contatos externos, vá para o centro de administração do Exchange (Eat) e clique em **contatos**de **destinatários** \> . 
    
    > [!TIP]
    > Para obter instruções para se conectar ao Eat, consulte [Exchange Admin Center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197). 
  
5. Se necessário, clique em **Atualizar** para atualizar a lista e ver os contatos externos que foram importados. 
    
    Os contatos importados aparecerão no catálogo de endereços compartilhado no Outlook e no Outlook na Web.
    
    > [!NOTE]
    > Você também pode exibir os contatos no centro de administração do Microsoft 365 indo para **os contatos dos usuários** \> ****. 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>Etapa 3: adicionar informações às propriedades dos contatos externos

Após executar o comando na etapa 2, os contatos externos são criados, mas não contêm nenhuma das informações de contato ou organização, que são as informações da maioria das células no arquivo CSV. Isso ocorre porque quando você cria novos contatos externos, somente as propriedades necessárias são preenchidas. Não se preocupe se você não tiver todas as informações preenchidas no arquivo CSV. Se ele não estiver lá, ele não será adicionado.
  
1.  Conecte o PowerShell à sua organização do Exchange Online. Para obter instruções detalhadas, consulte [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Vá para a pasta da área de trabalho onde você salvou o arquivo CSV na etapa 1; por exemplo `C:\Users\Administrator\desktop`.
    
3. Execute os dois comandos a seguir para adicionar as outras propriedades do arquivo CSV aos contatos externos que você criou na etapa 2.
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > O parâmetro _Manager_ pode ser problemático. Se a célula estiver em branco no arquivo CSV, você receberá um erro e nenhuma das informações da propriedade será adicionada ao contato. Se você não precisa especificar um gerente, basta excluir ` -Manager $_.Manager ` do comando anterior do PowerShell. 
  
    Novamente, pode levar algum tempo para atualizar os contatos, dependendo de quantos você importou na etapa 1. 
    
4. Para verificar se as propriedades foram adicionadas aos contatos: 
    
1. No EAC, acesse **Destinatários** \> **Contatos**.
    
2. Clique em um contato e, **** ![em seguida,](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) clique em Editar ícone de edição para exibir as propriedades do contato. 
    
Isso é tudo. Os usuários podem ver os contatos e as informações adicionais no catálogo de endereços Outlook e Outlook na Web.
  
## <a name="add-more-external-contacts"></a>Adicionar mais contatos externos

Você pode repetir as etapas 1 a 3 para adicionar novos contatos externos no Exchange Online. Você ou os usuários de sua empresa podem simplesmente adicionar uma nova linha no arquivo CSV para o novo contato. Em seguida, você pode executar os comandos do PowerShell da etapa 2 e etapa 3 para criar e adicionar informações aos novos contatos.
  
> [!NOTE]
> Ao executar o comando para criar novos contatos, você pode receber um erro dizendo que os contatos criados anteriormente já existem. Mas qualquer contato novo adicionado ao arquivo CSV é criado. 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>Ocultar contatos externos do catálogo de endereços compartilhado>

Algumas empresas podem usar somente contatos externos para que possam ser adicionadas como membros dos grupos de distribuição. Neste cenário, convém ocultar contatos externos do catálogo de endereços compartilhado. Veja como:
  
1.  Conecte o PowerShell à sua organização do Exchange Online. Para obter instruções detalhadas, consulte [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Para ocultar um único contato externo, execute o comando a seguir.
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    Por exemplo, para ocultar pilar Fernandes do catálogo de endereços compartilhado, execute este comando:

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. Para ocultar todos os contatos externos do catálogo de endereços compartilhado, execute este comando:

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

Após ocultá-los, os contatos externos não são exibidos no catálogo de endereços compartilhado, mas você ainda pode adicioná-los como membros de um grupo de distribuição.
