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
ms.openlocfilehash: 08fe7666f03c7fe60555133292be9e27a9ffa413
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072248"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="3fe45-103">Importação em massa de contatos externos para o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3fe45-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="3fe45-104">**Este artigo é para administradores. Você está tentando importar contatos para sua própria caixa de correio? Confira [importar contatos para o Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="3fe45-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="3fe45-105">Sua empresa tem muitos contatos comerciais existentes que você deseja incluir no catálogo de endereços compartilhado (também chamado de lista de endereços global) no Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="3fe45-105">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online?</span></span> <span data-ttu-id="3fe45-106">Você deseja adicionar contatos externos como membros de grupos de distribuição, da mesma forma que é possível com os usuários dentro da sua empresa?</span><span class="sxs-lookup"><span data-stu-id="3fe45-106">Do you want to add external contacts as members of distribution groups, just like you can with users inside your company?</span></span> <span data-ttu-id="3fe45-107">Em caso afirmativo, você pode usar o PowerShell do Exchange Online e um arquivo CSV (valor separado por vírgula) para importar contatos externos em massa para o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3fe45-107">If so, you can use Exchange Online PowerShell and a CSV (Comma Separated Value) file to bulk import external contacts into Exchange Online.</span></span> <span data-ttu-id="3fe45-108">É um processo de três etapas:</span><span class="sxs-lookup"><span data-stu-id="3fe45-108">It's a three-step process:</span></span>
  
[<span data-ttu-id="3fe45-109">Etapa 1: criar um arquivo CSV que contenha informações sobre os contatos externos</span><span class="sxs-lookup"><span data-stu-id="3fe45-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="3fe45-110">Etapa 2: criar os contatos externos com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fe45-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="3fe45-111">Etapa 3: adicionar informações às propriedades dos contatos externos</span><span class="sxs-lookup"><span data-stu-id="3fe45-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="3fe45-112">Após concluir essas etapas para importar contatos, você pode executar estas tarefas adicionais:</span><span class="sxs-lookup"><span data-stu-id="3fe45-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="3fe45-113">Adicionar mais contatos externos</span><span class="sxs-lookup"><span data-stu-id="3fe45-113">Add more external contacts</span></span>](#add-more-external-contacts)
  
- [<span data-ttu-id="3fe45-114">Ocultar contatos externos do catálogo de endereços compartilhado</span><span class="sxs-lookup"><span data-stu-id="3fe45-114">Hide external contacts from the shared address book</span></span>](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="3fe45-115">Etapa 1: criar um arquivo CSV que contenha informações sobre os contatos externos</span><span class="sxs-lookup"><span data-stu-id="3fe45-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="3fe45-116">A primeira etapa é criar um arquivo CSV que contenha informações sobre cada contato externo que você deseja importar para o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3fe45-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="3fe45-117">Copie o seguinte texto em um arquivo de texto no bloco de notas e salve-o em sua área de trabalho como um arquivo CSV usando um sufixo de nome de arquivo. csv; por exemplo, ExternalContacts. csv.</span><span class="sxs-lookup"><span data-stu-id="3fe45-117">Copy the following text to a text file in NotePad, and save it to your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="3fe45-118">Se seu idioma contiver caracteres especiais (como **å**, **ä**e **ö** em Sueco), salve o arquivo CSV com UTF-8 ou outra codificação Unicode quando você salvar o arquivo no bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="3fe45-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    <span data-ttu-id="3fe45-119">A primeira linha, ou linha de cabeçalho, do arquivo CSV lista as propriedades de contatos que podem ser usadas quando você as importa para o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3fe45-119">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online.</span></span> <span data-ttu-id="3fe45-120">Cada nome de propriedade é separado por uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="3fe45-120">Each property name is separated by a comma.</span></span> <span data-ttu-id="3fe45-121">Cada linha sob a linha de cabeçalho representa os valores de propriedade para importar um único contato externo.</span><span class="sxs-lookup"><span data-stu-id="3fe45-121">Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="3fe45-122">Este texto inclui dados de exemplo, que podem ser excluídos.</span><span class="sxs-lookup"><span data-stu-id="3fe45-122">This text includes sample data, which you can delete.</span></span> <span data-ttu-id="3fe45-123">Mas não exclua nem altere a primeira linha (cabeçalho).</span><span class="sxs-lookup"><span data-stu-id="3fe45-123">But don't delete or change the first (header) row.</span></span> <span data-ttu-id="3fe45-124">Ele contém todas as propriedades dos contatos externos.</span><span class="sxs-lookup"><span data-stu-id="3fe45-124">It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="3fe45-125">Abra o arquivo CSV no Microsoft Excel para editar o arquivo CSV porque é muito mais fácil usar o Excel para editar o arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="3fe45-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="3fe45-126">Crie uma linha para cada contato que você deseja importar para o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3fe45-126">Create a row for each contact that you want to import to Exchange Online.</span></span> <span data-ttu-id="3fe45-127">Preencha o máximo possível de células.</span><span class="sxs-lookup"><span data-stu-id="3fe45-127">Populate as many of the cells as possible.</span></span> <span data-ttu-id="3fe45-128">Essas informações serão exibidas no catálogo de endereços compartilhado para cada contato.</span><span class="sxs-lookup"><span data-stu-id="3fe45-128">This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="3fe45-129">As propriedades a seguir (que são os primeiros quatro itens na linha de cabeçalho) são necessárias para criar um contato externo e devem ser preenchidas no arquivo CSV: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span><span class="sxs-lookup"><span data-stu-id="3fe45-129">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span></span> <span data-ttu-id="3fe45-130">O comando do PowerShell executado na etapa 2 usará os valores dessas propriedades para criar os contatos.</span><span class="sxs-lookup"><span data-stu-id="3fe45-130">The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="3fe45-131">Etapa 2: criar os contatos externos com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fe45-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="3fe45-132">A próxima etapa é usar o arquivo CSV que você criou na etapa 1 e o PowerShell para importar em massa os contatos externos listados no arquivo CSV para o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3fe45-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="3fe45-133">Conecte o PowerShell à sua organização do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3fe45-133">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="3fe45-134">Para obter instruções detalhadas, consulte [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="3fe45-134">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span> <span data-ttu-id="3fe45-135">Certifique-se de usar o nome de usuário e a senha da sua conta de administrador global do Office 365 quando você se conectar ao PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3fe45-135">Be sure to use the user name and password for your Office 365 global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="3fe45-136">Depois de conectar o PowerShell ao Exchange Online, vá para a pasta da área de trabalho onde você salvou o arquivo CSV na etapa 1; por exemplo `C:\Users\Administrator\desktop`.</span><span class="sxs-lookup"><span data-stu-id="3fe45-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="3fe45-137">Execute o seguinte comando para criar os contatos externos:</span><span class="sxs-lookup"><span data-stu-id="3fe45-137">Run the following command to create the external contacts:</span></span>

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="3fe45-138">Pode levar algum tempo para criar novos contatos, dependendo da quantidade que você está importando.</span><span class="sxs-lookup"><span data-stu-id="3fe45-138">It might take a while to create the new contacts, depending on how many you're importing.</span></span> <span data-ttu-id="3fe45-139">Quando o comando termina de ser executado, o PowerShell exibe uma lista dos novos contatos que foram criados.</span><span class="sxs-lookup"><span data-stu-id="3fe45-139">When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="3fe45-140">Para exibir os novos contatos externos, vá para o centro de administração do Exchange (Eat) e clique em **contatos**de **destinatários** \> .</span><span class="sxs-lookup"><span data-stu-id="3fe45-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="3fe45-141">Para obter instruções para se conectar ao Eat, consulte [Exchange Admin Center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span><span class="sxs-lookup"><span data-stu-id="3fe45-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span></span> 
  
5. <span data-ttu-id="3fe45-142">Se necessário, clique em **Atualizar** ![ícone](media/O365-MDM-Policy-RefreshIcon.gif) de atualização para atualizar a lista e consulte os contatos externos que foram importados.</span><span class="sxs-lookup"><span data-stu-id="3fe45-142">If necessary, click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="3fe45-143">Os contatos importados aparecerão no catálogo de endereços compartilhado no Outlook e no Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="3fe45-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3fe45-144">Você também pode exibir os contatos no centro de administração do Microsoft 365 indo para **os contatos dos usuários** \> \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="3fe45-144">You can also view the contacts in the Microsoft 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="3fe45-145">Etapa 3: adicionar informações às propriedades dos contatos externos</span><span class="sxs-lookup"><span data-stu-id="3fe45-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="3fe45-146">Após executar o comando na etapa 2, os contatos externos são criados, mas não contêm nenhuma das informações de contato ou organização, que são as informações da maioria das células no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="3fe45-146">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from the most of the cells in the CSV file.</span></span> <span data-ttu-id="3fe45-147">Isso ocorre porque quando você cria novos contatos externos, somente as propriedades necessárias são preenchidas.</span><span class="sxs-lookup"><span data-stu-id="3fe45-147">This is because when you create new external contacts, only the required properties are populated.</span></span> <span data-ttu-id="3fe45-148">Não se preocupe se você não tiver todas as informações preenchidas no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="3fe45-148">Don't worry if you don't have all the information populated in the CSV file.</span></span> <span data-ttu-id="3fe45-149">Se ele não estiver lá, ele não será adicionado.</span><span class="sxs-lookup"><span data-stu-id="3fe45-149">If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="3fe45-150">Conecte o PowerShell à sua organização do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3fe45-150">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="3fe45-151">Para obter instruções detalhadas, consulte [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="3fe45-151">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="3fe45-152">Vá para a pasta da área de trabalho onde você salvou o arquivo CSV na etapa 1; por exemplo `C:\Users\Administrator\desktop`.</span><span class="sxs-lookup"><span data-stu-id="3fe45-152">Go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="3fe45-153">Execute os dois comandos a seguir para adicionar as outras propriedades do arquivo CSV aos contatos externos que você criou na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="3fe45-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="3fe45-154">O parâmetro _Manager_ pode ser problemático.</span><span class="sxs-lookup"><span data-stu-id="3fe45-154">The  _Manager_ parameter might be problematic.</span></span> <span data-ttu-id="3fe45-155">Se a célula estiver em branco no arquivo CSV, você receberá um erro e nenhuma das informações da propriedade será adicionada ao contato.</span><span class="sxs-lookup"><span data-stu-id="3fe45-155">If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact.</span></span> <span data-ttu-id="3fe45-156">Se você não precisa especificar um gerente, basta excluir ` -Manager $_.Manager ` do comando anterior do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fe45-156">If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="3fe45-157">Novamente, pode levar algum tempo para atualizar os contatos, dependendo de quantos você importou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="3fe45-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="3fe45-158">Para verificar se as propriedades foram adicionadas aos contatos:</span><span class="sxs-lookup"><span data-stu-id="3fe45-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="3fe45-159">No EAC, acesse **Destinatários** \> **Contatos**.</span><span class="sxs-lookup"><span data-stu-id="3fe45-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="3fe45-160">Clique em um contato e, \*\*\*\* ![em seguida,](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) clique em Editar ícone de edição para exibir as propriedades do contato.</span><span class="sxs-lookup"><span data-stu-id="3fe45-160">Click a contact and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="3fe45-161">Isso é tudo.</span><span class="sxs-lookup"><span data-stu-id="3fe45-161">That's it!</span></span> <span data-ttu-id="3fe45-162">Os usuários podem ver os contatos e as informações adicionais no catálogo de endereços Outlook e Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="3fe45-162">Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="3fe45-163">Adicionar mais contatos externos</span><span class="sxs-lookup"><span data-stu-id="3fe45-163">Add more external contacts</span></span>

<span data-ttu-id="3fe45-164">Você pode repetir as etapas 1 a 3 para adicionar novos contatos externos no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3fe45-164">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online.</span></span> <span data-ttu-id="3fe45-165">Você ou os usuários de sua empresa podem simplesmente adicionar uma nova linha no arquivo CSV para o novo contato.</span><span class="sxs-lookup"><span data-stu-id="3fe45-165">You or users in your company can just add a new row in the CSV file for the new contact.</span></span> <span data-ttu-id="3fe45-166">Em seguida, você pode executar os comandos do PowerShell da etapa 2 e etapa 3 para criar e adicionar informações aos novos contatos.</span><span class="sxs-lookup"><span data-stu-id="3fe45-166">Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3fe45-167">Ao executar o comando para criar novos contatos, você pode receber um erro dizendo que os contatos criados anteriormente já existem.</span><span class="sxs-lookup"><span data-stu-id="3fe45-167">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist.</span></span> <span data-ttu-id="3fe45-168">Mas qualquer contato novo adicionado ao arquivo CSV é criado.</span><span class="sxs-lookup"><span data-stu-id="3fe45-168">But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="3fe45-169">Ocultar contatos externos do catálogo de endereços compartilhado></span><span class="sxs-lookup"><span data-stu-id="3fe45-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="3fe45-170">Algumas empresas podem usar somente contatos externos para que possam ser adicionadas como membros dos grupos de distribuição.</span><span class="sxs-lookup"><span data-stu-id="3fe45-170">Some companies may use external contacts only so they can be added as members of distribution groups.</span></span> <span data-ttu-id="3fe45-171">Neste cenário, convém ocultar contatos externos do catálogo de endereços compartilhado.</span><span class="sxs-lookup"><span data-stu-id="3fe45-171">In this scenario, they may want to hide external contacts from the shared address book.</span></span> <span data-ttu-id="3fe45-172">Veja como:</span><span class="sxs-lookup"><span data-stu-id="3fe45-172">Here's how:</span></span>
  
1.  <span data-ttu-id="3fe45-173">Conecte o PowerShell à sua organização do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3fe45-173">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="3fe45-174">Para obter instruções detalhadas, consulte [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="3fe45-174">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="3fe45-175">Para ocultar um único contato externo, execute o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="3fe45-175">To hide a single external contact, run the following command.</span></span>
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    <span data-ttu-id="3fe45-176">Por exemplo, para ocultar pilar Fernandes do catálogo de endereços compartilhado, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="3fe45-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. <span data-ttu-id="3fe45-177">Para ocultar todos os contatos externos do catálogo de endereços compartilhado, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="3fe45-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="3fe45-178">Após ocultá-los, os contatos externos não são exibidos no catálogo de endereços compartilhado, mas você ainda pode adicioná-los como membros de um grupo de distribuição.</span><span class="sxs-lookup"><span data-stu-id="3fe45-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>
