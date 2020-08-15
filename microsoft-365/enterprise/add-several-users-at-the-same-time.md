---
title: Adicionar vários usuários ao mesmo tempo para o Microsoft 365-ajuda para administradores
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_AddUsersCSV
- O365M_AddUsersCSV
- O365E_AddUsersCSV
search.appverid:
- MET150
- MOP150
- MOE150
- MED150
- GMA150
- MBS150
- GEA150
- BCS160
ms.assetid: 1f5767ed-e717-4f24-969c-6ea9d412ca88
description: 'Saiba como adicionar vários usuários ao Microsoft 365 para empresas de uma lista em uma planilha ou outro arquivo formatado por CSV. Assista a um vídeo sobre o YouTube que explica como adicionar contas ao Microsoft 365. No final desse processo, cada usuário com uma conta terá uma caixa de correio do Microsoft 365. '
ms.openlocfilehash: c75f16233a85f48be44082ba3ec9ffb82ef18ff9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687538"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a><span data-ttu-id="791cb-105">Adicionar vários usuários ao mesmo tempo para o Microsoft 365-ajuda para administradores</span><span class="sxs-lookup"><span data-stu-id="791cb-105">Add several users at the same time to Microsoft 365 - Admin Help</span></span>

<span data-ttu-id="791cb-106">Cada pessoa em sua equipe precisa de uma conta de usuário antes de poder entrar e acessar os serviços do Microsoft 365, como emails e Office.</span><span class="sxs-lookup"><span data-stu-id="791cb-106">Each person on your team needs a user account before they can sign in and access Microsoft 365 services, such as email and Office.</span></span> <span data-ttu-id="791cb-107">Se houver muitas pessoas, é possível adicionar todas as contas de uma só vez a partir de uma planilha do Excel ou de outro arquivo salvo em formato CSV.</span><span class="sxs-lookup"><span data-stu-id="791cb-107">If you have a lot of people, you can add their accounts all at once from an Excel spreadsheet or other file saved in CSV format.</span></span> [<span data-ttu-id="791cb-108">Não sabe o que é o formato CSV?</span><span class="sxs-lookup"><span data-stu-id="791cb-108">Not sure what CSV format is?</span></span>](add-several-users-at-the-same-time.md#__toc316652088)
  
> [!NOTE] 
> <span data-ttu-id="791cb-109">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="791cb-109">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a><span data-ttu-id="791cb-110">Adicionar vários usuários no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="791cb-110">Add multiple users in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="791cb-111">Entre no Microsoft 365 com a sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="791cb-111">Sign in to Microsoft 365 with your work or school account.</span></span> 
    
2. <span data-ttu-id="791cb-112">No centro de administração, escolha usuários ativos do **usuário** \> **Active users**.</span><span class="sxs-lookup"><span data-stu-id="791cb-112">In the admin center, choose **Users** \> **Active users**.</span></span>

3. <span data-ttu-id="791cb-113">Selecione **adicionar vários usuários**.</span><span class="sxs-lookup"><span data-stu-id="791cb-113">Select **Add multiple users**.</span></span>

4. <span data-ttu-id="791cb-114">No painel **Importar vários usuários**, opcionalmente, você pode baixar um arquivo CSV de exemplo com ou sem dados de exemplo preenchidos.</span><span class="sxs-lookup"><span data-stu-id="791cb-114">On the **Import multiple users** panel, you can optionally download a sample CSV file with or without sample data filled in.</span></span> 
    
    <span data-ttu-id="791cb-115">A planilha deve incluir **exatamente os mesmos títulos de coluna** que os da planilha de exemplo (Nome de Usuário, Nome, etc...). Se você usar o modelo, abra-o em uma ferramenta de edição de texto, como o Bloco de Notas, e considere a opção de manter todos os dados na linha 1 e inserir dados apenas nas linhas 2 e abaixo.</span><span class="sxs-lookup"><span data-stu-id="791cb-115">Your spreadsheet needs to include the **exact same column headings** as the sample one (User Name, First Name, etc...). If you use the template, open it in a text editing tool, like Notepad, and consider leaving all the data in row 1 alone, and only entering data in rows 2 and below.</span></span> 
    
    <span data-ttu-id="791cb-116">A planilha também precisa incluir valores de nome de usuário (por exemplo, carlos@contoso.com) e um nome para exibição (por exemplo, Carlos Lima) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="791cb-116">Your spreadsheet also needs to include values for the user name (like bob@contoso.com) and a display name (like Bob Kelly) for each user.</span></span> 
    
  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Fax,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,123-555-9821,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,123-555-9822,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,123-555-9823,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,123-555-9824,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,123-555-9825,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. <span data-ttu-id="791cb-117">Insira um caminho de arquivo na caixa ou escolha **Procurar** para navegar até o local do arquivo CSV. Em seguida, escolha **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="791cb-117">Enter a file path into the box, or choose **Browse** to browse to the CSV file location, then choose **Verify**.</span></span>
  
    <span data-ttu-id="791cb-p103">Se houver algum problema com o arquivo, o problema será exibido no painel. Você também pode baixar um arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="791cb-p103">If there are problems with the file, the problem is displayed in the panel. You can also download a log file.</span></span>
    
5. <span data-ttu-id="791cb-120">Na caixa de diálogo **Definir opções do usuário**, você pode definir o status de entrada e escolher a licença de produto que será atribuída a todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="791cb-120">On the **Set user options** dialog you can set the sign-in status and choose the product license that will be assigned to all users.</span></span> 
    
6. <span data-ttu-id="791cb-121">Na caixa de diálogo **Exibir seu resultado**, você pode optar por enviar os resultados a si mesmo ou a outros usuários (as senhas estarão em texto sem formatação), pode ver quantos usuários foram criados e se precisa comprar mais licenças para atribuir a alguns dos novos usuários.</span><span class="sxs-lookup"><span data-stu-id="791cb-121">On the **View your result** dialog you can choose to send the results to either yourself or other users (passwords will be in plain text) and you can see how many users were created, and if you need to purchase more licenses to assign to some of the new users.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="791cb-122">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="791cb-122">Next steps</span></span>
<span data-ttu-id="791cb-123"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="791cb-123"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="791cb-124">Agora que essas pessoas têm contas, elas precisam [baixar e instalar ou reinstalar o Microsoft 365 ou o Office 2016 em um PC ou Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658).</span><span class="sxs-lookup"><span data-stu-id="791cb-124">Now that these people have accounts, they need to [Download and install or reinstall Microsoft 365 or Office 2016 on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> <span data-ttu-id="791cb-125">Cada pessoa em sua equipe pode instalar o Microsoft 365 em até 5 PCs ou Macs.</span><span class="sxs-lookup"><span data-stu-id="791cb-125">Each person on your team can install Microsoft 365 on up to 5 PCs or Macs.</span></span> 
    
- <span data-ttu-id="791cb-126">Cada pessoa também pode [configurar os aplicativos do Office e o email em um dispositivo móvel](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) em até 5 tablets e 5 telefones, como iPhones, iPads e telefones e tablets Android.</span><span class="sxs-lookup"><span data-stu-id="791cb-126">Each person can also [Set up Office apps and email on a mobile device](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) on up to 5 tablets and 5 phones, such as iPhones, iPads, and Android phones and tablets.</span></span> <span data-ttu-id="791cb-127">Dessa forma, elas podem editar arquivos do Office em qualquer lugar.</span><span class="sxs-lookup"><span data-stu-id="791cb-127">This way they can edit Office files from anywhere.</span></span> 
    
    <span data-ttu-id="791cb-128">Consulte [set up Microsoft 365 for Business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) para obter uma lista completa das etapas de configuração.</span><span class="sxs-lookup"><span data-stu-id="791cb-128">See [Set up Microsoft 365 for business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) for an end-to-end list of the setup steps.</span></span> 
    
## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a><span data-ttu-id="791cb-129">Mais informações sobre como adicionar usuários ao Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="791cb-129">More information about how to add users to Microsoft 365</span></span>
<span data-ttu-id="791cb-130"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="791cb-130"><a name="bk_preview"> </a></span></span>

### <a name="not-sure-what-csv-format-is"></a><span data-ttu-id="791cb-131">Não sabe o que é o formato CSV?</span><span class="sxs-lookup"><span data-stu-id="791cb-131">Not sure what CSV format is?</span></span>
<span data-ttu-id="791cb-132"><a name="__toc316652088"> </a></span><span class="sxs-lookup"><span data-stu-id="791cb-132"><a name="__toc316652088"> </a></span></span>

<span data-ttu-id="791cb-p106">Um arquivo CSV é um arquivo com valores separados por vírgulas. Você pode criar ou editar um arquivo como esse com qualquer editor de texto ou programa de planilha, como o Excel.</span><span class="sxs-lookup"><span data-stu-id="791cb-p106">A CSV file is a file with comma separated values. You can create or edit a file like this with any text editor or spreadsheet program, such as Excel.</span></span>
  
<span data-ttu-id="791cb-135">Você pode baixar [esta planilha de exemplo](https://www.microsoft.com/download/details.aspx?id=45485) como ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="791cb-135">You can download [this sample spreadsheet](https://www.microsoft.com/download/details.aspx?id=45485) as a starting point.</span></span> <span data-ttu-id="791cb-136">Lembre-se de que o Microsoft 365 requer títulos de coluna na primeira linha, portanto não os substitua por outra coisa.</span><span class="sxs-lookup"><span data-stu-id="791cb-136">Remember that Microsoft 365 requires column headings in the first row so don't replace them with something else.</span></span> 
  
<span data-ttu-id="791cb-137">Salve o arquivo com um novo nome e especifique o formato CSV.</span><span class="sxs-lookup"><span data-stu-id="791cb-137">Save the file with a new name, and specify CSV format.</span></span>
  
![Uma imagem de como salvar um arquivo em Excel no formato CSV](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
<span data-ttu-id="791cb-p108">Ao salvar o arquivo, você provavelmente receberá um aviso de que alguns recursos da pasta de trabalho serão perdidos se você salvar o arquivo no formato CSV. Não há problema. Clique em **Sim** para continuar.</span><span class="sxs-lookup"><span data-stu-id="791cb-p108">When you save the file, you'll probably get a prompt that some features in your workbook will be lost if you save the file in CSV format. This is okay. Click **Yes** to continue.</span></span> 
  
![Uma imagem da solicitação que você poderá receber no Excel para confirmar se deseja salvar o arquivo em formato CSV](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a><span data-ttu-id="791cb-143">Dicas para formatar a sua planilha</span><span class="sxs-lookup"><span data-stu-id="791cb-143">Tips for formatting your spreadsheet</span></span>
<span data-ttu-id="791cb-144"><a name="__toc314595848"> </a></span><span class="sxs-lookup"><span data-stu-id="791cb-144"><a name="__toc314595848"> </a></span></span>

- <span data-ttu-id="791cb-145">**Preciso dos mesmos títulos de coluna como mostrado na planilha de exemplo?**</span><span class="sxs-lookup"><span data-stu-id="791cb-145">**Do I need the same column headings as in the sample spreadsheet?**</span></span> <span data-ttu-id="791cb-146">Sim.</span><span class="sxs-lookup"><span data-stu-id="791cb-146">Yes.</span></span> <span data-ttu-id="791cb-147">A planilha de exemplo contém títulos de coluna na primeira linha.</span><span class="sxs-lookup"><span data-stu-id="791cb-147">The sample spreadsheet contains column headings in the first row.</span></span> <span data-ttu-id="791cb-148">Esses títulos são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="791cb-148">These headings are required.</span></span> <span data-ttu-id="791cb-149">Para cada usuário que você deseja adicionar ao Microsoft 365, crie uma linha sob o título.</span><span class="sxs-lookup"><span data-stu-id="791cb-149">For each user you want to add to Microsoft 365, create a row under the heading.</span></span> <span data-ttu-id="791cb-150">Se você adicionar, alterar ou excluir qualquer um dos títulos de coluna, o Microsoft 365 pode não conseguir criar usuários a partir das informações no arquivo.</span><span class="sxs-lookup"><span data-stu-id="791cb-150">If you add, change, or delete any of the column headings, Microsoft 365 might not be able to create users from the information in the file.</span></span> 
    
- <span data-ttu-id="791cb-p110">**E se eu não tiver todas as informações necessárias sobre cada usuário?** O nome de usuário e o nome para exibição são obrigatórios, e não será possível adicionar um novo usuário sem essas informações. Caso não tenha alguma outra informação, como o fax, use um espaço e uma vírgula para indicar que o campo deve permanecer em branco.</span><span class="sxs-lookup"><span data-stu-id="791cb-p110">**What if I don't have all the information required for each user?** The user name and display name are required, and you cannot add a new user without this information. If you don't have some of the other information, such as the fax, you can use a space plus a comma to indicate that the field should remain blank.</span></span> 
    
- <span data-ttu-id="791cb-154">**O tamanho da planilha pode ser pequeno ou grande?**</span><span class="sxs-lookup"><span data-stu-id="791cb-154">**How small or large can the spreadsheet be?**</span></span> <span data-ttu-id="791cb-155">A planilha deve ter pelo menos duas linhas.</span><span class="sxs-lookup"><span data-stu-id="791cb-155">The spreadsheet must have at least two rows.</span></span> <span data-ttu-id="791cb-156">One is for the column headings (the user data column label) and one for the user.</span><span class="sxs-lookup"><span data-stu-id="791cb-156">One is for the column headings (the user data column label) and one for the user.</span></span> <span data-ttu-id="791cb-157">You cannot have more than 251 rows.</span><span class="sxs-lookup"><span data-stu-id="791cb-157">You cannot have more than 251 rows.</span></span> <span data-ttu-id="791cb-158">If you need to import more than 250 users, you can create more than one spreadsheet.</span><span class="sxs-lookup"><span data-stu-id="791cb-158">If you need to import more than 250 users, you can create more than one spreadsheet.</span></span> 
    
- <span data-ttu-id="791cb-159">**Que idiomas eu posso usar?**</span><span class="sxs-lookup"><span data-stu-id="791cb-159">**What languages can I use?**</span></span> <span data-ttu-id="791cb-160">Ao criar sua planilha, você pode inserir rótulos de coluna de dados de usuário em qualquer idioma ou caractere, mas não deve alterar a ordem dos rótulos, conforme mostrado no exemplo.</span><span class="sxs-lookup"><span data-stu-id="791cb-160">When you create your spreadsheet, you can enter user data column labels in any language or characters, but you must not change the order of the labels, as shown in the sample.</span></span> <span data-ttu-id="791cb-161">You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.</span><span class="sxs-lookup"><span data-stu-id="791cb-161">You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.</span></span> 
    
- <span data-ttu-id="791cb-p113">**E se eu estiver adicionando usuários de diferentes países ou regiões?** Crie uma planilha separada para cada área. Você precisará percorrer o assistente Adicionar usuários em massa em cada planilha, fornecendo um único local para todos os usuários incluídos no arquivo que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="791cb-p113">**What if I'm adding users from different countries or regions?** Create a separate spreadsheet for each area. You'll need to step through the Bulk add users wizard which each spreadsheet, giving a single location of all users included in the file that you're working with.</span></span> 
    
- <span data-ttu-id="791cb-p114">**Há um limite quanto ao número de caracteres que eu posso usar?** A tabela a seguir mostra os rótulos de colunas de dados de usuário e o respectivo tamanho máximo de caracteres na planilha de exemplo.</span><span class="sxs-lookup"><span data-stu-id="791cb-p114">**Is there a limit to the number of characters I can use?** The following table shows the user data column labels and the maximum character length for each in the sample spreadsheet.</span></span> 
    
|<span data-ttu-id="791cb-167">**Rótulo da coluna de dados do usuário**</span><span class="sxs-lookup"><span data-stu-id="791cb-167">**User data column label**</span></span>|<span data-ttu-id="791cb-168">**Comprimento máximo de caracteres**</span><span class="sxs-lookup"><span data-stu-id="791cb-168">**Maximum character length**</span></span>|
|:-----|:-----|
|<span data-ttu-id="791cb-169">Nome de Usuário (Obrigatório)</span><span class="sxs-lookup"><span data-stu-id="791cb-169">User Name (Required)</span></span>  <br/> |<span data-ttu-id="791cb-170">79 incluindo o sinal de arroba (@), no formato name@domain. \<extension\> .</span><span class="sxs-lookup"><span data-stu-id="791cb-170">79 including the at sign (@), in the format name@domain.\<extension\>.</span></span> <span data-ttu-id="791cb-171">O alias do usuário não pode exceder 50 caracteres e o nome de domínio não pode exceder 48 caracteres.</span><span class="sxs-lookup"><span data-stu-id="791cb-171">The user's alias cannot exceed 50 characters, and the domain name cannot exceed 48 characters.</span></span>  <br/> |
|<span data-ttu-id="791cb-172">Nome</span><span class="sxs-lookup"><span data-stu-id="791cb-172">First Name</span></span>  <br/> |<span data-ttu-id="791cb-173">64</span><span class="sxs-lookup"><span data-stu-id="791cb-173">64</span></span>  <br/> |
|<span data-ttu-id="791cb-174">Sobrenome</span><span class="sxs-lookup"><span data-stu-id="791cb-174">Last Name</span></span>  <br/> |<span data-ttu-id="791cb-175">64</span><span class="sxs-lookup"><span data-stu-id="791cb-175">64</span></span>  <br/> |
|<span data-ttu-id="791cb-176">Nome de Exibição (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="791cb-176">Display Name (required)</span></span>  <br/> |<span data-ttu-id="791cb-177">256</span><span class="sxs-lookup"><span data-stu-id="791cb-177">256</span></span>  <br/> |
|<span data-ttu-id="791cb-178">Cargo</span><span class="sxs-lookup"><span data-stu-id="791cb-178">Job Title</span></span>  <br/> |<span data-ttu-id="791cb-179">64</span><span class="sxs-lookup"><span data-stu-id="791cb-179">64</span></span>  <br/> |
|<span data-ttu-id="791cb-180">Departamento</span><span class="sxs-lookup"><span data-stu-id="791cb-180">Department</span></span>  <br/> |<span data-ttu-id="791cb-181">64</span><span class="sxs-lookup"><span data-stu-id="791cb-181">64</span></span>  <br/> |
|<span data-ttu-id="791cb-182">Número Comercial</span><span class="sxs-lookup"><span data-stu-id="791cb-182">Office Number</span></span>  <br/> |<span data-ttu-id="791cb-183">128</span><span class="sxs-lookup"><span data-stu-id="791cb-183">128</span></span>  <br/> |
|<span data-ttu-id="791cb-184">Telefone Comercial</span><span class="sxs-lookup"><span data-stu-id="791cb-184">Office Phone</span></span>  <br/> |<span data-ttu-id="791cb-185">64</span><span class="sxs-lookup"><span data-stu-id="791cb-185">64</span></span>  <br/> |
|<span data-ttu-id="791cb-186">Telefone Celular</span><span class="sxs-lookup"><span data-stu-id="791cb-186">Mobile Phone</span></span>  <br/> |<span data-ttu-id="791cb-187">64</span><span class="sxs-lookup"><span data-stu-id="791cb-187">64</span></span>  <br/> |
|<span data-ttu-id="791cb-188">Fax</span><span class="sxs-lookup"><span data-stu-id="791cb-188">Fax</span></span>  <br/> |<span data-ttu-id="791cb-189">64</span><span class="sxs-lookup"><span data-stu-id="791cb-189">64</span></span>  <br/> |
|<span data-ttu-id="791cb-190">Endereço</span><span class="sxs-lookup"><span data-stu-id="791cb-190">Address</span></span>  <br/> |<span data-ttu-id="791cb-191">1023</span><span class="sxs-lookup"><span data-stu-id="791cb-191">1023</span></span>  <br/> |
|<span data-ttu-id="791cb-192">Cidade</span><span class="sxs-lookup"><span data-stu-id="791cb-192">City</span></span>  <br/> |<span data-ttu-id="791cb-193">128</span><span class="sxs-lookup"><span data-stu-id="791cb-193">128</span></span>  <br/> |
|<span data-ttu-id="791cb-194">Estado ou Província</span><span class="sxs-lookup"><span data-stu-id="791cb-194">State or Province</span></span>  <br/> |<span data-ttu-id="791cb-195">128</span><span class="sxs-lookup"><span data-stu-id="791cb-195">128</span></span>  <br/> |
|<span data-ttu-id="791cb-196">CEP</span><span class="sxs-lookup"><span data-stu-id="791cb-196">ZIP or Postal Code</span></span>  <br/> |<span data-ttu-id="791cb-197">40</span><span class="sxs-lookup"><span data-stu-id="791cb-197">40</span></span>  <br/> |
|<span data-ttu-id="791cb-198">País ou Região</span><span class="sxs-lookup"><span data-stu-id="791cb-198">Country or Region</span></span>  <br/> |<span data-ttu-id="791cb-199">128</span><span class="sxs-lookup"><span data-stu-id="791cb-199">128</span></span>  <br/> |
   
### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a><span data-ttu-id="791cb-200">Ainda está tendo problemas ao adicionar usuários ao Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="791cb-200">Still having problems when adding users to Microsoft 365?</span></span>

- <span data-ttu-id="791cb-p116">**Verifique se o arquivo está formatado corretamente.** Verifique se os títulos das colunas correspondem àqueles do arquivo de exemplo. Você deverá seguir as regras de tamanho de caracteres e verificar se cada campo está separado por uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="791cb-p116">**Double-check that the spreadsheet is formatted correctly.** Check the column headings to make sure they match the headings in the sample file. Make sure you're following the rules for character lengths and that each field is separated by a comma.</span></span> 
    
- <span data-ttu-id="791cb-204">**Se você não vir os novos usuários no Microsoft 365 imediatamente, aguarde alguns minutos.**</span><span class="sxs-lookup"><span data-stu-id="791cb-204">**If you don't see the new users in Microsoft 365 right away, wait a few minutes.**</span></span> <span data-ttu-id="791cb-205">Pode demorar um pouco para que as alterações entrem em todos os serviços no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="791cb-205">It can take a little while for changes to go across all the services in Microsoft 365.</span></span> 
    
## <a name="related-articles"></a><span data-ttu-id="791cb-206">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="791cb-206">Related articles</span></span>

[<span data-ttu-id="791cb-207">Adicionar usuários individualmente ou em massa ao Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="791cb-207">Add users individually or in bulk to Microsoft 365</span></span>](https://docs.microsoft.com/office365/admin/add-users/add-users)




