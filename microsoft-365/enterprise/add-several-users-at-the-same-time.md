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
ms.openlocfilehash: a970fbfa28214543e34011f1310742c6fb811d09
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071508"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a>Adicionar vários usuários ao mesmo tempo para o Microsoft 365-ajuda para administradores

Cada pessoa em sua equipe precisa de uma conta de usuário antes de poder entrar e acessar os serviços do Microsoft 365, como emails e Office. Se houver muitas pessoas, é possível adicionar todas as contas de uma só vez a partir de uma planilha do Excel ou de outro arquivo salvo em formato CSV. [Não sabe o que é o formato CSV?](add-several-users-at-the-same-time.md#__toc316652088)
  
> [!NOTE] 
> Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a>Adicionar vários usuários no centro de administração do Microsoft 365

1. Entre no Microsoft 365 com a sua conta corporativa ou de estudante. 
    
2. No centro de administração, escolha usuários ativos do **usuário** \> **Active users**.

3. Selecione **adicionar vários usuários**.

4. No painel **Importar vários usuários** , opcionalmente, você pode baixar um arquivo CSV de exemplo com ou sem dados de exemplo preenchidos. 
    
    Sua planilha precisa incluir exatamente os **mesmos cabeçalhos de coluna** que o exemplo um (nome de usuário, nome e assim por diante). Se você usar o modelo, abra-o em uma ferramenta de edição de texto, como o bloco de notas, e considere deixar todos os dados na linha 1 e apenas inserir dados nas linhas 2 e abaixo. 
    
    A planilha também precisa incluir valores de nome de usuário (por exemplo, carlos@contoso.com) e um nome para exibição (por exemplo, Carlos Lima) para cada usuário. 
    
  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. Insira um caminho de arquivo na caixa ou escolha **Procurar** para navegar até o local do arquivo CSV. Em seguida, escolha **Verificar**.
  
    Se houver algum problema com o arquivo, o problema será exibido no painel. Você também pode baixar um arquivo de log.
    
5. Na caixa de diálogo **Definir opções do usuário** , você pode definir o status de entrada e escolher a licença de produto que será atribuída a todos os usuários. 
    
6. Na caixa de diálogo **Exibir seu resultado** , você pode optar por enviar os resultados a si mesmo ou a outros usuários (as senhas estarão em texto sem formatação), pode ver quantos usuários foram criados e se precisa comprar mais licenças para atribuir a alguns dos novos usuários. 

## <a name="next-steps"></a>Próximas etapas
<a name="bk_preview"> </a>

- Agora que essas pessoas têm contas, elas precisam [baixar e instalar ou reinstalar o Microsoft 365 ou o Office 2016 em um PC ou Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658). Cada pessoa em sua equipe pode instalar o Microsoft 365 em até 5 PCs ou Macs. 
    
- Cada pessoa também pode [configurar os aplicativos do Office e o email em um dispositivo móvel](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) em até 5 tablets e 5 telefones, como iPhones, iPads e telefones e tablets Android. Dessa forma, elas podem editar arquivos do Office em qualquer lugar. 
    
    Consulte [set up Microsoft 365 for Business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) para obter uma lista completa das etapas de configuração. 
    
## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a>Mais informações sobre como adicionar usuários ao Microsoft 365
<a name="bk_preview"> </a>

### <a name="not-sure-what-csv-format-is"></a>Não sabe o que é o formato CSV?
<a name="__toc316652088"> </a>

Um arquivo CSV é um arquivo com valores separados por vírgulas. Você pode criar ou editar um arquivo como esse com qualquer editor de texto ou programa de planilha, como o Excel.
  
Você pode baixar [esta planilha de exemplo](https://www.microsoft.com/download/details.aspx?id=45485) como ponto de partida. Lembre-se de que o Microsoft 365 requer títulos de coluna na primeira linha, portanto não os substitua por outra coisa. 
  
Salve o arquivo com um novo nome e especifique o formato CSV.
  
![Uma imagem de como salvar um arquivo em Excel no formato CSV](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
Ao salvar o arquivo, você provavelmente receberá um aviso de que alguns recursos da pasta de trabalho serão perdidos se você salvar o arquivo no formato CSV. Não há problema. Clique em **Sim** para continuar. 
  
![Uma imagem da solicitação que você poderá receber no Excel para confirmar se deseja salvar o arquivo em formato CSV](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a>Dicas para formatar a sua planilha
<a name="__toc314595848"> </a>

- **Preciso dos mesmos títulos de coluna como mostrado na planilha de exemplo?** Sim. A planilha de exemplo contém títulos de coluna na primeira linha. Esses títulos são obrigatórios. Para cada usuário que você deseja adicionar ao Microsoft 365, crie uma linha sob o título. Se você adicionar, alterar ou excluir qualquer um dos títulos de coluna, o Microsoft 365 pode não conseguir criar usuários a partir das informações no arquivo. 
    
- **E se eu não tiver todas as informações necessárias sobre cada usuário?** O nome de usuário e o nome para exibição são obrigatórios, e não será possível adicionar um novo usuário sem essas informações. Caso não tenha alguma outra informação, como o fax, use um espaço e uma vírgula para indicar que o campo deve permanecer em branco. 
    
- **O tamanho da planilha pode ser pequeno ou grande?** A planilha deve ter pelo menos duas linhas. One is for the column headings (the user data column label) and one for the user. You cannot have more than 251 rows. If you need to import more than 250 users, you can create more than one spreadsheet. 
    
- **Que idiomas eu posso usar?** Ao criar sua planilha, você pode inserir rótulos de coluna de dados de usuário em qualquer idioma ou caractere, mas não deve alterar a ordem dos rótulos, conforme mostrado no exemplo. You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format. 
    
- **E se eu estiver adicionando usuários de diferentes países ou regiões?** Crie uma planilha separada para cada área. Você precisará percorrer o assistente Adicionar usuários em massa em cada planilha, fornecendo um único local para todos os usuários incluídos no arquivo que você está trabalhando. 
    
- **Há um limite quanto ao número de caracteres que eu posso usar?** A tabela a seguir mostra os rótulos de colunas de dados de usuário e o respectivo tamanho máximo de caracteres na planilha de exemplo. 
    
|**Rótulo da coluna de dados do usuário**|**Comprimento máximo de caracteres**|
|:-----|:-----|
|Nome de Usuário (Obrigatório)  <br/> |79 incluindo o sinal de arroba (@), no formato name@domain. \<extension\> . O alias do usuário não pode exceder 50 caracteres e o nome de domínio não pode exceder 48 caracteres.  <br/> |
|Nome  <br/> |64  <br/> |
|Sobrenome  <br/> |64  <br/> |
|Nome de Exibição (obrigatório)  <br/> |256  <br/> |
|Cargo  <br/> |64  <br/> |
|Departamento  <br/> |64  <br/> |
|Número Comercial  <br/> |128  <br/> |
|Telefone Comercial  <br/> |64  <br/> |
|Telefone Celular  <br/> |64  <br/> |
|Fax  <br/> |64  <br/> |
|Endereço  <br/> |1023  <br/> |
|Cidade  <br/> |128  <br/> |
|Estado ou Província  <br/> |128  <br/> |
|CEP  <br/> |40  <br/> |
|País ou Região  <br/> |128  <br/> |
   
### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a>Ainda está tendo problemas ao adicionar usuários ao Microsoft 365?

- **Verifique se o arquivo está formatado corretamente.** Verifique se os títulos das colunas correspondem àqueles do arquivo de exemplo. Você deverá seguir as regras de tamanho de caracteres e verificar se cada campo está separado por uma vírgula. 
    
- **Se você não vir os novos usuários no Microsoft 365 imediatamente, aguarde alguns minutos.** Pode demorar um pouco para que as alterações entrem em todos os serviços no Microsoft 365. 
    
## <a name="related-articles"></a>Artigos relacionados

[Adicionar usuários individualmente ou em massa ao Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/add-users)




