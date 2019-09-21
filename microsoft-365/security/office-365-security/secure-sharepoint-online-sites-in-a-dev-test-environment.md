---
title: Proteger sites do SharePoint Online em um ambiente de desenvolvimento/teste
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/18/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: 'Resumo: crie sites de equipe do SharePoint Online públicos, privados, confidenciais e altamente confidenciais em um ambiente de desenvolvimento/teste.'
ms.openlocfilehash: d60d113f9b8eac453e8a516b4d5e373896ace0ec
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073904"
---
# <a name="secure-sharepoint-online-sites-in-a-devtest-environment"></a>Proteger sites do SharePoint Online em um ambiente de desenvolvimento/teste

 **Resumo:** crie sites de equipe do SharePoint Online públicos, privados, confidenciais e altamente confidenciais em um ambiente de desenvolvimento/teste.
  
Este artigo fornece instruções passo a passo para criar um ambiente de desenvolvimento/teste que inclui os quatro tipos diferentes de sites de equipe do SharePoint Online para a solução de [arquivos e sites seguros do SharePoint Online](secure-sharepoint-online-sites-and-files.md).
  
![Todos os quatro sites de equipe no ambiente seguro de desenvolvimento/teste do SharePoint Online.](../media/b0fea489-359c-4c85-a0ad-e4efb4a1e47f.png)
  
Use este ambiente de desenvolvimento/teste para experimentar com os comportamentos de proteção de informações e ajustar as configurações para suas necessidades específicas antes de implantar sites de equipe do SharePoint Online na produção.
  
## <a name="phase-1-create-your-devtest-environment"></a>Fase 1: criar seu ambiente de desenvolvimento/teste

Nesta fase, você deve obter assinaturas de avaliação do Office 365 e do Enterprise Mobility + Security (EMS) para uma organização fictícia.
  
Primeiro, siga as instruções na **Fase 2** do [ambiente de desenvolvimento/de teste do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).
  
Em seguida, inscreva-se para a assinatura de avaliação do EMS e adicione-a à mesma organização de sua assinatura de avaliação do Office 365.
  
1. Se necessário, entre no centro de administração [Microsoft 365](https://admin.microsoft.com) com as credenciais da conta do administrador global da sua assinatura de avaliação.
    
2. Na navegação à esquerda, clique em **cobrança > Serviços de compra**.
    
3. Na página **Comprar serviços**, encontre o item **Enterprise Mobility + Security E5**. Passe o ponteiro do mouse sobre ele e clique em **Iniciar avaliação gratuita**.
    
4. Na página **Confirmar seu pedido**, clique em **Experimentar agora**.
    
5. Na página **Recibo do pedido**, clique em **Continuar**.
    
Em seguida, habilite a licença do Enterprise Mobility + Security E5 para sua conta de administrador global.
  
1. Na guia **centro de administração do Microsoft 365** no navegador, na navegação à esquerda, clique em **Usuários > Usuários ativos**.
    
2. Clique em sua conta de administrador global e, em seguida, clique em **Editar** para **Licenças de produto**.
    
3. No painel **Licenças de produto**, mude a licença de produto de **Enterprise Mobility + Security E5** para **Ativada**, clique em **Salvar** e clique em **Fechar** duas vezes.
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a>Fase 2: criar e configurar seus grupos e usuários do Azure Active Directory (AD)

Nesta fase, você cria e configura os usuários e grupos do Azure AD para sua organização fictícia.
  
Primeiro, crie um conjunto de grupos para uma organização comum com o portal do Azure.
  
1. Abra uma guia separada no navegador e vá para o Portal do Azure em [https://portal.azure.com](https://portal.azure.com). Se necessário, entre com as credenciais da conta de administrador global da sua assinatura de avaliação do Office 365 E5.
    
2. No Portal do Azure, clique em **Azure Active Directory > Grupos**.
    
3. Na folha **Grupos – Todos os grupos**, clique em **+ Novo grupo**.
    
4. Na folha **Grupo**:
    
  - Escolha **Office 365** em **Tipo de Grupo**.
    
  - Digite **Pacote C** em **Nome**.
    
  - Escolha **Atribuído** em **Tipo de Associação**.
      
5. Clique em **Criar** e, em seguida, feche a folha **Grupo**.
    
6. Repita as etapas 3 a 5 para os seguintes nomes de grupo:
    
  - Equipe de TI
    
  - Equipe de pesquisa
    
  - Equipe regular
    
  - Equipe de marketing
    
  - Equipe de vendas
    
7. Mantenha aberta a guia do portal do Azure no navegador.
    
Em seguida, configure o licenciamento automático para que os membros de seus grupos recebam automaticamente a atribuição de licenças para suas assinaturas do Office 365 e do EMS.
  
1. No Portal do Azure, clique em **Azure Active Directory > Licenças > Todos os produtos**.
    
2. Na lista, escolha **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5** e clique em **Atribuir**.
    
3. Na folha **Atribuir licença**, clique em **Usuários e grupos**.
    
4. Na lista de grupos, selecione o seguinte:
    
  - Pacote C
    
  - Equipe de TI
    
  - Equipe de pesquisa
    
  - Equipe regular
    
  - Equipe de marketing
    
  - Equipe de vendas
    
5. Clique em **Selecionar** e clique em **Atribuir**.
    
6. Feche a guia do Portal do Azure no navegador.
    
Em seguida, conecte-se ao módulo [PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Preencha o nome da organização, seu local e uma senha comum. Execute esses comandos no prompt de comando do PowerShell ou no ISE (Ambiente de Script Integrado) para criar contas de usuário e adicioná-las aos grupos:
  
```
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Research staff"
$userNames=@("Researcher1") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Regular staff"
$userNames=@("Regular1", "Regular2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Sales staff"
$userNames=@("SalesPerson1") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> O uso de uma senha comum aqui é para a automação e facilidade de configuração para um ambiente de desenvolvimento/teste. Obviamente, isso é recomendado para assinaturas de produção. 
  
Use essas etapas para verificar se o licenciamento baseado em grupo está funcionando corretamente.
  
1. Na guia **Microsoft Office Home** do navegador, clique no bloco **Administração**.
    
2. Na nova guia **Centro de administração do Microsoft 365** do seu navegador, clique em **Usuários**.
    
3. Na lista de usuários, clique em **CEO**.
    
4. No painel que lista as propriedades da conta de usuário **CEO**, verifique se ele recebeu a atribuição das licenças **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5** (em **Licenças de produto**).
    
## <a name="phase-3-create-office-365-retention-labels"></a>Fase 3: Criar etiquetas de retenção do Office 365

Nesta fase, você deve criar os rótulos para os diferentes níveis de segurança das pastas e documentos do site de equipe do SharePoint Online.


1. Acesse o [portal de conformidade do Microsoft 365](https://compliance.microsoft.com) com sua conta de administrador global.
    
2. Na guia **Início - Conformidade do Microsoft 365** do navegador, clique em **Classificações > Rótulos**.
    
3. Clique em **Rótulos de retenção > Criar um rótulo**.
    
4. No painel **Atribuir nome ao seu rótulo** digite **Público interno** em **Atribuir nome ao seu rótulo**, e clique em **Avançar**.

5. No painel **descritores de plano de arquivo**, clique em **próximo**.
    
6. No painel **configurações de etiqueta**, se necessário, defina **retenção** para **no**e, em seguida, clique em **próximo**.
    
7. No painel **Revise suas configurações**, clique em **Criar o rótulo**.
    
8. Repita as etapas 3 a 7 para etiquetas adicionais com esses nomes:
    
  - Private
    
  - Confidencial
    
  - Altamente Confidencial
  
9. No painel **Início > Rótulos**, clique em **Publicar rótulos**.
    
10. No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.
    
11. No painel **Escolher rótulos**, clique em **Adicionar** e selecione todos os quatro rótulos.
    
12. Clique em **Concluído**.
    
13. No painel **Escolher rótulos para publicar**, clique em **Avançar**.
    
14. No painel **Escolher locais**, clique em **Avançar**.
    
15. No painel **Atribuir um nome à política**, digite **Organização de exemplo** em **Nome** e clique em **Avançar**.
    
16. No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.
    
## <a name="phase-4-create-your-sharepoint-online-team-sites"></a>Fase 4: criar sites de equipe do SharePoint Online

Nesta fase, você cria e configura os quatro tipos de sites de equipe do SharePoint Online para sua organização de exemplo.
  
### <a name="organization-wide-team-site"></a>Site de equipe de toda a organização

Para criar um site de equipe do SharePoint Online público de linha de base, faça o seguinte:
  
1. Se necessário, entre no [Portal do Office 365](https://portal.office.com) com as credenciais da conta de administrador global da sua assinatura de avaliação.
    
2. Na lista de blocos, clique em **SharePoint**.
    
3. Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.
    
4. Na página **Criar um site**, clique em **Site de equipe**.
    
5. Em **Nome do site**, digite **Toda a organização**. 
    
6. Na **Descrição do site de equipe**, digite **Site do SharePoint para toda a organização**.
    
7. Em **Configurações de privacidade**, escolha **Público – qualquer pessoa na organização pode acessar esse site** e clique em **Avançar**.
    
8. No painel **Quem você deseja adicionar?**, clique em **Concluir**.
    
Em seguida, configure a pasta de documentos do site de equipe Toda a organização para o rótulo Público interno.
  
1. Na guia **Toda a organização – Página Inicial** do navegador, clique em **Documentos**.
    
2. Clique no ícone de configurações e em **Configurações de biblioteca**.
    
3. Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.
    
4. Em **Configurações – Aplicar Rótulo**, escolha **Público interno** e clique em **Salvar**.
    
### <a name="project-1-team-site"></a>Site de equipe do projeto 1

Para criar um site de equipe básico e privado do SharePoint Online para um projeto dentro da organização, faça o seguinte:
  
1. Se necessário, entre no [Portal do Office 365](https://portal.office.com) com as credenciais da conta de administrador global da sua assinatura de avaliação.
    
2. Na lista de blocos, clique em **SharePoint**.
    
3. Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.
    
4. Na página **Criar um site**, clique em **Site de equipe**.
    
5. Em **Nome do site**, digite **Projeto 1**. 
    
6. Na **Descrição do site de equipe**, digite **Site do SharePoint para Projeto 1**.
    
7. Em **Configurações de privacidade**, escolha **Privado – somente membros podem acessar esse site** e clique em **Avançar**.
    
8. No painel **Quem você deseja adicionar?**, clique em **Concluir**.
    
Em seguida, configure a pasta de documentos do site de equipe Projeto 1 para o rótulo Privado.
  
1. Na guia **Projeto 1 – Página Inicial** do navegador, clique em **Documentos**.
    
2. Clique no ícone de configurações e em **Configurações de biblioteca**.
    
3. Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.
    
4. Em **Configurações – Aplicar Rótulo**, escolha **Privado** e clique em **Salvar**.
    
### <a name="marketing-campaigns-team-site"></a>Site de equipe de campanhas de marketing

Para criar um site de equipe do SharePoint Online isolado e com nível confidencial para recursos de campanha de marketing, faça o seguinte:

 
1. Se necessário, entre no [Portal do Office 365](https://portal.office.com) com as credenciais da conta de administrador global da sua assinatura de avaliação.
    
2. Na lista de blocos, clique em **SharePoint**.
    
3. Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.
    
4. Na página **Criar um site**, clique em **Site de equipe**.
    
5. Em **Nome do site de equipe**, digite **Campanhas de marketing**.
    
6. Em **Descrição do site de equipe**, digite **Site do SharePoint para recursos de campanha de marketing (confidencial)**.
    
7.  Em **Configurações de privacidade**, escolha **Privado – somente membros podem acessar esse site** e clique em **Avançar**.
    
8. No painel **Quem você deseja adicionar?**, clique em **Concluir**.
    
9. Na nova guia **Campanhas de marketing** no navegador, na barra de ferramentas, clique no ícone de configurações e em **Permissões do site**.
    
10. No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.
    
11. Na nova guia **Permissões** no navegador, clique em **Configurações de Solicitação de Acesso**.
    
12. Na caixa de diálogo **Configurações de Solicitação de Acesso**, desmarque as caixas de seleção **Permitir que membros compartilhem o site e arquivos e pastas individuais** e **Permitir que membros convidem outras pessoas para o grupo de membros do site**, digite **AdminTI1@**\<nome da organização>**.onmicrosoft.com** em **Enviar todas as solicitações para acesso** e clique em **OK**.
    
13. Clique em **Membros de campanhas de marketing** na lista.
    
14. Na página **Pessoas e Grupos**, clique em **Novo**.
    
15. Na caixa de diálogo **Compartilhar**, digite **Equipe de marketing**, selecione-a e clique em **Compartilhar**.
    
16. Repita as etapas 14 e 15 para a conta de usuário **Pesquisador1**.
    
17. Clique no botão voltar de seu navegador.
    
18. Clique em **Proprietários de campanhas de marketing** na lista.
    
19. Na página **Pessoas e Grupos**, clique em **Novo**.
    
20. Na caixa de diálogo **Compartilhar**, digite **Equipe de TI**, selecione o item e clique em **Compartilhar**.
    
21. Clique no botão voltar de seu navegador.
    
22. Feche a guia **Pessoas e Grupos** no navegador, clique na guia **Campanhas de marketing – Página Inicial** no navegador e feche o painel **Permissões de site**.
    
Estes são os resultados da configuração de permissões:
  
- O grupo do SharePoint **Campanhas de marketing – membros** contém apenas o grupo **Campanhas de marketing** (que contém a conta de usuário de administrador global), o grupo **Equipe de marketing** (que contém as conas de usuário Marketing1 e Marketing2) e a conta de usuário **Researcher1**.
    
- O grupo do SharePoint **Campanhas de marketing – Proprietários** contém apenas o grupo **Equipe de TI** (que contém apenas as contas de usuário ITAdmin1 e ITAdmin2).
    
- O grupo do SharePoint **Campanhas de marketing – Visitantes** não contém grupos ou contas de usuário.
    
- Os membros não podem modificar permissões de nível de site (isso pode ser feito apenas por membros do grupo **Campanhas de marketing – Proprietários**).
    
- Outras contas de usuário não podem acessar o site ou seus recursos, mas podem solicitar o acesso ao site, que enviará um email para a caixa de correio da conta de usuário AdminTI1.
    
Em seguida, configure a pasta de documentos do site de equipe Campanhas de marketing para o rótulo Confidencial.
  
1. Na guia **Campanhas de marketing – Página Inicial** do navegador, clique em **Documentos**.
    
2. Clique no ícone de configurações e em **Configurações de biblioteca**.
    
3. Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.
    
4. Em **Configurações – Aplicar Rótulo**, escolha **Confidencial** e clique em **Salvar**.
    
Em seguida, configure uma política DLP (prevenção de perda de dados) que notifica os usuários quando eles compartilham um documento em um site de equipe do SharePoint Online com o rótulo Confidencial, que inclui o site de Campanhas de marketing, fora da organização.

1. Acesse o [portal de conformidade do Microsoft 365](https://compliance.microsoft.com/) com sua conta de administrador global.
    
2. Na nova guia **conformidade do Microsoft 365** em seu navegador, clique em**Políticas > Prevenção de perda de dados**.
    
3. No painel **Início > Prevenção de perda de dados**, clique em **Criar uma política**.
    
4. No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e, em seguida, clique em **Avançar**.
    
5. No painel **Atribuir um nome à política**, digite **Sites de equipe do SharePoint Online de rótulo Confidencial** em **Nome** e clique em **Avançar**.
    
6. No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.
    
7. Na lista de locais, desabilite os locais **email do Exchange**, **contas do OneDrive** e **Mensagens do canal e do chat do Teams** e, em seguida, clique em **Avançar**.
    
8. No painel **Personalizar o tipo de conteúdo que você deseja proteger**, clique em **Editar**.
    
9. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e, em seguida, clique em **Rótulos de retenção**.
    
10. No painel **Rótulos de retenção**, clique em ** Adicionar**, selecione o rótulo **Confidencial**, clique em **Adicionar** e, em seguida, clique em **Concluído**.
    
11. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.
    
12. No painel **personalizar um tipo de conteúdo que deseja proteger**, clique em **próxima**.

13. No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.
    
14. No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.
    
15. Na caixa de texto, digite ou cole uma das dicas a seguir, dependendo de se você implementou a Proteção de Informações do Azure para proteger arquivos altamente confidenciais:
    
  - Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.
    
16. Clique em **OK**.
    
17. No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Avançar**.
    
18. No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.
    
19. No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.
  
### <a name="company-strategy-team-site"></a>Site de equipe de estratégia empresarial

Para criar um site de equipe do SharePoint Online isolado no nível altamente confidencial para recursos corporativos estratégicos dos diretores da organização, faça o seguinte:
  
1. Se necessário, entre no [Portal do Office 365](https://portal.office.com) com as credenciais da conta de administrador global da sua assinatura de avaliação.
    
2. Na lista de blocos, clique em **SharePoint**.
    
3. Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.
    
4. Na página **Criar um site**, clique em **Site de equipe**.
    
5. Em **Nome do site da equipe**, digite **Estratégia da empresa**.
    
6. Em **Descrição do site da equipe**, digite **Site do SharePoint para estratégia empresarial (altamente confidencial)**.
    
7.  Em **Configurações de privacidade**, escolha **Privado – somente membros podem acessar esse site** e clique em **Avançar**.
    
8. No painel **Quem você deseja adicionar?**, clique em **Concluir**.
    
9. Na nova guia **Estratégia da campanha** no navegador, na barra de ferramentas, clique no ícone de configurações e, depois, em **Permissões do site**.
    
10. No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.
    
11. Na nova guia **Permissões** no navegador, clique em **Configurações de Solicitação de Acesso**.
    
12. Na caixa de diálogo **Configurações de Solicitação de Acesso**, desmarque **Permitir que membros compartilhem o site e arquivos e pastas individuais** e **Permitir que os membros convidem outros para o grupo de membros do site** (de forma que todas as três caixas de seleção estejam desmarcadas) e clique em **OK**.
    
13. Clique em **Membros da estratégia empresarial** na lista.
    
14. Na página **Pessoas e Grupos**, clique em **Novo**.
    
15. Na caixa de diálogo **Compartilhar**, digite **Pacote C**, marque-a e clique em **Compartilhar**.
    
16. Clique em **Estratégia empresarial – Proprietários** na lista.
    
17. Na página **Pessoas e Grupos**, clique em **Novo**.
    
18. Na caixa de diálogo **Compartilhar**, digite **Equipe de TI**, selecione o item e clique em **Compartilhar**.
    
19. Clique no botão voltar de seu navegador.
    
20. Feche a guia **Pessoas e Grupos** no navegador, clique na guia **Estratégia de campanha – Página Inicial** no navegador e feche o painel **Permissões do site**.
    
Estes são os resultados da configuração de permissões:
  
- O grupo do SharePoint **Estratégia da empresa – Membros** contém apenas o grupo **Pacote C** (que contém apenas as contas de usuário do CEO, do CFO e do CIO) e o grupo **Estratégia da empresa** (que contém apenas a conta de usuário de administrador global).
    
- O grupo do SharePoint **Estratégia empresarial – Proprietários** contém apenas o grupo **Equipe de TI** (que contém apenas as contas de usuário AdminTI1 e AdminTI2).
    
- O grupo do SharePoint **Estratégia empresarial – Visitantes** não contém grupos ou contas de usuário.
    
- Os membros não podem modificar permissões de nível de site (isso pode ser feito apenas por membros do grupo **Estratégia da empresa – Proprietários**).
    
- Outras contas de usuário não podem acessar o site ou seus recursos ou solicitar o acesso ao site. As permissões adicionais para o site devem ser feias pelo administrador global ou por um membro do grupo **Estratégia da empresa – Proprietários**.
    
Em seguida, configure a pasta de documentos do site da equipe de estratégia da empresa para o rótulo Altamente Confidencial.
  
1. Na guia **Estratégia empresarial – Página Inicial** do navegador, clique em **Documentos**.
    
2. Clique no ícone de configurações e em **Configurações de biblioteca**.
    
3. Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.
    
4. Em **Configurações – Aplicar Rótulo**, escolha **Altamente Confidencial** e clique em **Salvar**.
    
Em seguida, configure uma política DLP que bloqueia os usuários quando eles compartilham um documento em um site de equipe do SharePoint Online com o rótulo Altamente Confidencial, que inclui o site de Estratégia da empresa, fora da organização.
  
1. Acesse o [portal de conformidade do Microsoft 365](https://compliance.microsoft.com/) com seu administrador global.
    
2. Na nova guia **conformidade do Microsoft 365** em seu navegador, clique em**Políticas > Prevenção de perda de dados**.
    
3. No painel **Início > Prevenção de perda de dados**, clique em **Criar uma política**.
    
4. No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e, em seguida, clique em **Avançar**.
    
5. No painel **Atribuir um nome à política**, digite **Sites de equipe do SharePoint Online de rótulo Altamente Confidencial** em **Nome** e clique em **Avançar**.
    
6. No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.
    
7. Na lista de locais, desabilite os locais **email do Exchange**, **contas do OneDrive** e **Mensagens do canal e do chat do Teams** e, em seguida, clique em **Avançar**.
    
8. No painel **Personalizar o tipo de conteúdo que você deseja proteger**, clique em **Editar**.
    
9. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e, em seguida, clique em **Rótulos de retenção**.
    
10. No painel **Rótulos de retenção**, clique em **Adicionar**, selecione o rótulo **Altamente Confidencial**, clique em **Adicionar** e, em seguida, clique em **Concluído**.
    
11. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.
    
12. No painel **personalizar um tipo de conteúdo que deseja proteger**, clique em **próxima**.

13. No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.
    
14. No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.
    
15. Na caixa de texto, digite ou cole uma das dicas a seguir, dependendo de se você implementou a Proteção de Informações do Azure para proteger arquivos altamente confidenciais:
    
  - Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.
    
16. Clique em **OK**.
    
17. No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.

18. No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.
    
19. No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.
   
    
Em seguida, siga as instruções em [Ativar o Azure RMS com o centro de administração do Microsoft 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).
  
Depois, configure a Proteção de Informações do Azure com uma nova política e sub-rótulo em escopo para o grupo de Pacote C para proteção e permissões com as seguintes etapas:
  
1. Se necessário, entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) com sua conta de administrador global.
    
2. Em uma guia separada do navegador, vá para o Portal do Azure ([https://portal.azure.com](https://portal.azure.com)).
    
3. Se esta é a primeira vez que você configura a Proteção de Informações do Azure, confira estas [instruções](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).
    
4. No painel de lista, clique em **Todos os serviços**, digite **informações** e clique em **Proteção de Informações do Azure**.

5. Clique em **Rótulos**.
    
6. Clique com o botão direito do mouse no rótulo **Altamente Confidencial** e clique em **Adicionar um sub-rótulo**.
    
7. Digite **Membros do Pacote C** em **Nome** e **Descrição**.
    
8. Em **Definir permissões para documentos e emails que contenham este rótulo**, clique em **Proteger**.
    
9. Na seção **Proteção**, clique em **Azure (chave de nuvem)**.
    
10. Na folha **Proteção**, em **Configurações de proteção**, clique em **+ Adicionar permissões**.
    
11. Na folha **Adicionar permissões**, em **Especificar usuários e grupos**, clique em **+ Procurar no diretório**.
    
12. No painel **Usuários e Grupos do AAD**, escolha **Pacote C** e clique em **Selecionar**.
    
13. Em **Escolher permissões a partir de valores predefinidos ou definir valores personalizados**, clique em **Personalizar** e, em seguida, clique nas caixas de seleção **Exibir Direitos**, **Editar Conteúdo**, **Salvar**, **Responder** e **Responder a Todos**.
    
14. Clique em **OK** duas vezes.
    
15. Na folha **Sub-rótulo**, clique em **Salvar** e em **OK**.

16. Na folha **Proteção de Informações do Azure**, clique em **Políticas > + Adicionar uma nova política**.
    
17. Digite **EstratégiaEmpresarial** em **Nome da política** e **Documentos no site da equipe de Estratégia empresarial** em **Descrição**.
    
18. Clique em **Selecionar usuários ou grupos que obtêm essa política > Usuário/Grupos**e, em seguida, selecione **Pacote C**.
    
19. Clique em **Selecionar > OK**.

20. Clique em **Adicionar ou remover rótulos**. No painel **Política: Adicionar ou remover rótulos**, clique em **Pacote C** e, em seguida, clique em **OK**.   

21. Clique em **Salvar** e em **OK**.
    
Para proteger um documento com a Proteção de Informações do Azure e esse novo rótulo, você deve [instalar o cliente de Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/rms-client/install-client-app) em um computador de teste, instale o Office no centro de administração e entre no Microsoft Word com um conta no grupo **C-Suite** da sua assinatura de avaliação.
  
Agora você está pronto para criar documentos nestes quatro sites e testar o acesso a eles com várias contas de usuário em sua assinatura de avaliação.
  
Aqui está a configuração geral para todos os quatro sites de equipe do SharePoint Online.
  
![Todos os quatro sites de equipe no ambiente seguro de desenvolvimento/teste do SharePoint Online.](../media/b0fea489-359c-4c85-a0ad-e4efb4a1e47f.png)
  
## <a name="next-step"></a>Próxima etapa

Quando você estiver pronto para a implantação dos sites do SharePoint Online seguros na produção, consulte [Arquivos e sites do SharePoint Online seguros](secure-sharepoint-online-sites-and-files.md) para obter informações detalhadas e links para os artigos de implantação passo a passo.
  
## <a name="see-also"></a>Confira também

[Proteger arquivos e sites do SharePoint Online](secure-sharepoint-online-sites-and-files.md)
  
[Adoção da nuvem e de soluções híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações Agile](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)




