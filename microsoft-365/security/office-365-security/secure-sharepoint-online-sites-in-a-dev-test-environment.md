---
title: Proteger sites do SharePoint Online em um ambiente de desenvolvimento/teste
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/26/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: 'Resumo: Crie sites de equipe do SharePoint Online confidenciais e altamente confidenciais em um ambiente de desenvolvimento/teste.'
ms.openlocfilehash: a88701720147c8bd3e53572c27ba4a1949746cae
ms.sourcegitcommit: bf30a2314376f0b7d577741b97df017969737d11
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/27/2019
ms.locfileid: "39631631"
---
# <a name="secure-sharepoint-online-sites-in-a-devtest-environment"></a>Proteger sites do SharePoint Online em um ambiente de desenvolvimento/teste

Este artigo fornece instruções passo a passo para criar um ambiente de desenvolvimento/teste que inclui os sites confidenciais e altamente confidenciais do SharePoint para a solução de [arquivos e sites seguros do SharePoint Online](secure-sharepoint-online-sites-and-files.md).
  
![Proteção com alto nível de confidencialidade para sites de equipe do SharePoint Online.](../media/sensitive-highly-confidential-sp-sites-dev-test.png)
  
Use esse ambiente de desenvolvimento/teste para testar e ajustar as configurações de suas necessidades específicas antes de implantar esses tipos de equipes na produção.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Criar o ambiente de teste do Microsoft 365 Enterprise

Se você deseja apenas testar equipes confidenciais e altamente confidenciais de uma maneira simples com os requisitos mínimos, siga as instruções em [Configuração de base leve](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).

Caso pretenda testar equipes confidenciais e altamente confidenciais em uma empresa simulada, siga as instruções em [sincronização de hash de senha](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).

>[!Note]
>Testar as equipes confidenciais e altamente confidenciais não exige o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio do Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar equipes confidenciais e altamente confidenciais e experimentá-las em um ambiente que representa uma organização típica.
>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a>Fase 2: criar e configurar seus grupos e usuários do Azure Active Directory (AD)

Nesta fase, você cria e configura os usuários e grupos do Azure AD para sua organização fictícia.
  
Primeiro, crie um conjunto de grupos para uma organização comum com o portal do Azure.
  
1. Crie uma guia separada no navegador e vá para o Portal do Azure[https://portal.azure.com](https://portal.azure.com). Se necessário, entre com as credenciais da conta de administrador global da sua assinatura paga ou de avaliação do Microsoft 365 E5.
    
2. No Portal do Azure, clique em **Azure Active Directory > Grupos**.
    
3. Na folha **Grupos – Todos os grupos**, clique em **+ Novo grupo**.
    
4. Na folha **Grupo**:
    
  - Selecione **Segurança** em **Tipo de grupo**.
    
  - Digite **Pacote C** em **Nome**.
    
  - Escolha **Atribuído** em **Tipo de Associação**.
      
5. Clique em **Criar** e, em seguida, feche a folha **Grupo**.
    
6.  Repita as etapas 3-5 para um novo grupo chamado **equipe de marketing**.
    
Em seguida, configure o licenciamento automático para que os membros de seus grupos recebam automaticamente a atribuição de licenças para suas assinaturas do Office 365 e do EMS.
  
1. No Portal do Azure, clique em **Azure Active Directory > Licenças > Todos os produtos**.
    
2. Na lista, selecione **Microsoft 365 Enterprise E5**e, em seguida, clique em **atribuir**.
    
3. Na folha **Atribuir licença**, clique em **Usuários e grupos**.
    
4. Na lista de grupos, selecione o seguinte:
    
  - Pacote C
    
  - Equipe de marketing
    
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
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2") 
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
    
4. No painel que lista as propriedades da conta de usuário **CEO**, verifique se ele recebeu a atribuição das licenças **Microsoft 365 Enterprise E5** (em ** Licenças de produto**).
    
## <a name="phase-3-create-office-365-retention-labels"></a>Fase 3: Criar etiquetas de retenção do Office 365

Nesta fase, você cria os rótulos de retenção de documentos em seus sites de equipe do SharePoint.

1. Acesse o [portal de conformidade do Microsoft 365](https://compliance.microsoft.com) com sua conta de administrador global.
    
2. Na guia **Início - Conformidade do Microsoft 365** do navegador, clique em **Classificações > Rótulos**.
    
3. Clique em **Rótulos de retenção > Criar um rótulo**.
    
4. No painel **Atribuir nome ao seu rótulo** digite **Confidenciais** em **Atribuir nome ao seu rótulo**, e clique em **Avançar**.

5. No painel **descritores de plano de arquivo**, clique em **próximo**.
    
6. No painel **configurações de etiqueta**, se necessário, defina **retenção** para **no**e, em seguida, clique em **próximo**.
    
7. No painel **Revise suas configurações**, clique em **Criar o rótulo**.
    
8. Repita as etapas 3-7 para um rótulo de retenção adicional chamado **altamente confidencial**.
    
9. No painel **Início > Rótulos**, clique em **Publicar rótulos**.
    
10. No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.
    
11. No painel **Escolher rótulos**, clique em **Adicionar** e selecione todos os quatro rótulos.
    
12. Clique em **Concluído**.
    
13. No painel **Escolher rótulos para publicar**, clique em **Avançar**.
    
14. No painel **Escolher locais**, clique em **Avançar**.
    
15. No painel **Atribuir um nome à política**, digite **Organização de exemplo** em **Nome** e clique em **Avançar**.
    
16. No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.
    
## <a name="phase-4-create-your-team-sites"></a>Fase 4: criar sites de equipes

Nesta fase, você criará e configurará equipes confidenciais e altamente confidenciais para a sua organização de exemplo.

### <a name="sensitive-team-site-for-marketing-campaigns"></a>Site de equipe confidencial para campanhas de marketing

Primeiro, crie uma equipe de nível confidencial para os membros do grupo de marketing colaborarem em campanhas de marketing contínuas.

1. [Criar uma nova equipe privada](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d) com o nome **campanhas de Marketing**.
2.  Na barra de ferramentas do site de equipe do SharePoint, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.
3.  No painel **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.
4.  Em **Permissões de compartilhamento**, selecione **Somente proprietários do site podem compartilhar arquivos, pastas e o site** e clique em **Salvar**.

Em seguida, configure a pasta de documentos do site de equipe SharePoint campanhas de marketing para o rótulo de retenção confidencial.

1.  Na guia **Campanhas de marketing – Página Inicial** do navegador, clique em **Documentos**.
2.  Clique no ícone de configurações e clique em **Configurações de biblioteca**.
3.  Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.
4.  Em **Configurações – Aplicar Rótulo**, escolha **Confidencial** e clique em **Salvar**. 

Em seguida, configure uma política DLP (prevenção de perda de dados) que notifique os usuários quando eles compartilham um documento com o rótulo confidencial, que inclui documentos no site campanhas de marketing, fora da organização.

1. Acesse o [portal de conformidade do Microsoft 365](https://compliance.microsoft.com/) com sua conta de administrador global.
    
2. Na nova guia **conformidade do Microsoft 365** em seu navegador, clique em**Políticas > Prevenção de perda de dados**.
    
3. No painel **Início > Prevenção de perda de dados**, clique em **Criar uma política**.
    
4. No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.
    
5. No painel **Atribuir um nome à política**, digite **Sites do SharePoint de rótulo Confidencial** em **Nome** e clique em **Avançar**.
    
6. No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.
    
7. Na lista de locais, desabilite os locais **email do Exchange**, **contas do OneDrive** e **Mensagens do canal e do chat do Teams** e, em seguida, clique em **Avançar**.
    
8. No painel **Personalizar o tipo de conteúdo que você deseja proteger**, clique em **Editar**.
    
9. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e, em seguida, clique em **Rótulos de retenção**.
    
10. No painel **Rótulos de retenção**, clique em ** Adicionar**, selecione o rótulo **Confidencial**, clique em **Adicionar** e, em seguida, clique em **Concluído**.
    
11. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.
    
12. No painel **personalizar um tipo de conteúdo que deseja proteger**, clique em **próxima**.

13. No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.
    
14. No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.
    
15. Na caixa de texto, digite ou cole o seguinte:
    
  - Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.
    
16. Clique em **OK**.
    
17. No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Avançar**.
    
18. No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.
    
19. No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.

### <a name="company-strategy-team-site"></a>Site de equipe de estratégia empresarial

Primeiro, crie um site de equipe de nível altamente confidencial para que os membros da equipe de liderança sênior colabore na estratégia da empresa.

1. [Criar uma nova equipe privada](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d) com o nome **Estratégia empresarial**.
2.  Na barra de ferramentas do site de equipe do SharePoint, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.
3.  No painel **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.
4.  Em **Permissões de compartilhamento**, **Somente proprietários do site podem compartilhar arquivos, pastas e o site**.
5.  Desative **Permitir solicitações de acesso** e clique em **Salvar**.

Em seguida, configure a pasta de documentos do site da equipe do SharePoint da estratégia da empresa para obter o rótulo altamente confidencial.

1.  Na guia **Estratégia empresarial – Página Inicial** do navegador, clique em **Documentos**.
2.  Clique no ícone de configurações e clique em **Configurações de biblioteca**.
3.  Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.
4.  Em **Configurações – Aplicar Rótulo**, escolha **Altamente Confidencial** e clique em **Salvar**. 

Em seguida, configure uma política DLP que impede os usuários de compartilhar um documento com o rótulo altamente confidencial, que inclui documentos no site de estratégia da empresa, fora da organização.
  
1. Acesse o [portal de conformidade do Microsoft 365](https://compliance.microsoft.com/) com seu administrador global.
    
2. Na nova guia **conformidade do Microsoft 365** em seu navegador, clique em**Políticas > Prevenção de perda de dados**.
    
3. No painel **Início > Prevenção de perda de dados**, clique em **Criar uma política**.
    
4. No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.
    
5. No painel **Atribuir um nome à política**, digite **Sites do SharePoint de rótulo Altamente Confidencial** em **Nome** e clique em **Avançar**.
    
6. No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.
    
7. Na lista de locais, desabilite os locais **email do Exchange**, **contas do OneDrive** e **Mensagens do canal e do chat do Teams** e, em seguida, clique em **Avançar**.
    
8. No painel **Personalizar o tipo de conteúdo que você deseja proteger**, clique em **Editar**.
    
9. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e, em seguida, clique em **Rótulos de retenção**.
    
10. No painel **Rótulos de retenção**, clique em **Adicionar**, selecione o rótulo **Altamente Confidencial**, clique em **Adicionar** e, em seguida, clique em **Concluído**.
    
11. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.
    
12. No painel **personalizar um tipo de conteúdo que deseja proteger**, clique em **próxima**.

13. No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.
    
14. No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.
    
15. Na caixa de texto, digite ou cole o seguinte:
    
  - Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.
    
16. Clique em **OK**.
    
17. No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.

18. No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.
    
19. No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.

Use [estas instruções](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para configurar um rótulo confidencial com as seguintes configurações:

- O nome do rótulo é Estratégia empresarial
- A criptografia está ativada
- O grupo de estratégia empresarial tem permissões de Coautoria.

Depois de criar, publique o novo rótulo. Se entrar como um membro do grupo de estratégias empresarial, você verá o novo rótulo na opção confidencialidade na barra de ferramentas página inicial do Word, Excel e PowerPoint. Selecione o rótulo de estratégia empresarial na opção confidencialidade para atribuir o rótulo a um arquivo.

Os arquivos na seção documentos da estratégia empresarial do site de equipe do SharePoint recebem o rótulo de retenção altamente confidencial e estão sujeitos à política de DLP configurada. Os arquivos também podem ter o rótulo diferencial da estratégia empresarial atribuído.    

Esta é a configuração resultante para as campanhas de marketing e os sites de equipe da estratégia empresarial.

![Proteção com alto nível de confidencialidade para sites de equipe do SharePoint Online.](../media/sensitive-highly-confidential-sp-sites-dev-test.png)
  
## <a name="next-step"></a>Próxima etapa

Quando você estiver pronto para a implantação dos sites do SharePoint Online seguros na produção, consulte [Arquivos e sites do SharePoint Online seguros](secure-sharepoint-online-sites-and-files.md) para obter informações detalhadas e links para os artigos de implantação passo a passo.
  
## <a name="see-also"></a>Confira também

[Proteger arquivos e sites do SharePoint Online](secure-sharepoint-online-sites-and-files.md)
  
[Adoção da nuvem e de soluções híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações Agile](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)




