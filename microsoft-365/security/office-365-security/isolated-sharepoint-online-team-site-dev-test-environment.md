---
title: Site de equipe do SharePoint Online isolado no seu ambiente de desenvolvimento/teste
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 'Resumo: Configure um site de equipe do SharePoint Online isolado do restante da organização em seu ambiente de teste/dev do Microsoft 365.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 103ba1ddb2b5123db80be91f40c4fce8c6e2eb3d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286604"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a>Site de equipe do SharePoint Online isolado no seu ambiente de desenvolvimento/teste

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Microsoft Defender para Office 365 plano 1](office-365-atp.md)
- SharePoint Online 


 **Resumo:** Configure um site de equipe do SharePoint Online isolado do restante da organização no ambiente de teste/desv do Microsoft 365.

Os sites de equipe do SharePoint Online no Microsoft 365 são locais para colaboração usando uma biblioteca de documentos comum, um bloco de anotações do OneNote e outros serviços. Em muitos casos, convém ter acesso e colaboração amplos entre departamentos ou organizações. No entanto, em alguns casos, você deseja controlar fortemente o acesso e as permissões para colaboração entre um pequeno grupo de pessoas.

O acesso aos sites de equipe do SharePoint Online e o que os usuários podem fazer é controlado por grupos e níveis de permissão do SharePoint. Por padrão, os sites do SharePoint Online têm três níveis de acesso:

- **Membros**, que podem exibir, criar e modificar recursos no site.
- **Proprietários**, que têm controle total do site, incluindo a capacidade de alterar permissões.
- **Visitantes**, que só podem exibir recursos no site.

Este artigo explica a configuração de um site de equipe isolado do SharePoint Online para um projeto de pesquisa secreto chamado ProjectX. Os requisitos de acesso são:

- Somente os membros do projeto podem acessar o site e seu conteúdo (documentos, Bloco de Anotações do OneNote, Páginas), com níveis de permissão de edição e exibição do SharePoint controlados por meio de associação de grupo.

- Somente o criador do site e os membros de um grupo de Administradores do site podem executar a administração do site, a qual inclui modificação de permissões no nível do site.

Há três fases para configurar um site de equipe isolado do SharePoint Online em seu ambiente de desenvolvimento/teste do Microsoft 365:

1. Crie o ambiente de teste/desv do Microsoft 365.

2. Criação de usuários e grupos para o Projeto X.

3. Crie um novo site de equipe do SharePoint Online projectX e o isole.

> [!TIP]
> Clique [aqui](https://aka.ms/catlgstack) para ver um mapa visual para todos os artigos da pilha do Guia do Laboratório de Teste do One Microsoft Cloud.

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a>Fase 1: Criar seu ambiente de desenvolvimento/teste leve ou simulado do Microsoft 365

Se você quiser apenas criar um site de equipe do SharePoint Online isolado de maneira leve com os requisitos mínimos, siga as instruções nas fases 2 e 3 da configuração [de base leve.](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

Se você quiser criar um site de equipe do SharePoint Online isolado em uma configuração corporativa simulada, siga as instruções na sincronização de hash de senha para seu ambiente de teste do [Microsoft 365.](../../enterprise/password-hash-sync-m365-ent-test-environment.md)

> [!NOTE]
> Criar um site isolado do SharePoint Online não exige o ambiente de teste/dev corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta do AD DS (Serviços de Domínio Active Directory). Ele é fornecido aqui como uma opção para que você possa testar um site do SharePoint Online isolado e fazer testes com ele em um ambiente que representa uma organização comum.

## <a name="phase-2-create-user-accounts-and-access-groups"></a>Fase 2: Criar contas de usuário e grupos de acesso

Use as instruções em [Conectar-se ao Office 365 PowerShell](../../enterprise/connect-to-microsoft-365-powershell.md) para se conectar à sua assinatura de avaliação com sua conta de administrador global de:

- Seu computador (para o leve ambiente de dev/teste do Microsoft 365).

- A máquina virtual CLIENT1 (para o ambiente dev/teste corporativo simulado do Microsoft 365).

Para criar os novos grupos de acesso para o site de equipe do SharePoint Online do ProjectX, execute estes comandos no prompt do Módulo Do Windows Azure Active Directory para Windows PowerShell:

```powershell
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

Preencha o nome de sua organização (exemplo: contosotoycompany), o código de país com dois caracteres de seu local e execute os seguintes comandos no prompt do Módulo do Windows Azure Active Directory para Windows PowerShell:

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Na exibição do comando **New-MsolUser**, anote a senha gerada para a conta de Designer Chefe e grave-a em um local seguro.

Execute os seguintes comandos no prompt do Módulo do Windows Azure Active Directory para Windows PowerShell:

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Na exibição do comando **New-MsolUser**, anote a senha gerada para a conta de Pesquisador Chefe e grave-a em um local seguro.

Execute os seguintes comandos no prompt do Módulo do Windows Azure Active Directory para Windows PowerShell:

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Na exibição do comando **New-MsolUser**, anote a senha gerada para a conta de VP de Desenvolvimento e grave-a em um local seguro.

Em seguida, para adicionar as novas contas aos novos grupos de acesso, execute estes comandos do PowerShell no prompt do Módulo Do Windows Azure Active Directory para Windows PowerShell:

```powershell
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

Resultados:

- O ProjectX-Members grupo de acesso de grupo contém as contas de usuário Designer Chefe e Pesquisador Chefe

- O ProjectX-Admins grupo de acesso contém a conta de administrador global da sua assinatura de avaliação

- O ProjectX-Viewers grupo de acesso de grupo contém a conta de usuário vp de desenvolvimento

A Figura 1 mostra os grupos de acesso e sua associação.

**Figura 1:**

![Os grupos do Microsoft 365 e sua associação a um site de grupo do SharePoint Online isolado](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a>Fase 3: Criar um novo site de equipe do SharePoint Online projectX e isolá-lo

Para criar um site de equipe do SharePoint Online para o ProjectX, faça o seguinte:

1. Usando um navegador no computador local (configuração leve) ou no CLIENT1 (configuração corporativa simulada), entre no Centro de administração do Microsoft 365 usando sua conta de administrador <https://admin.microsoft.com> global.

2. Na lista de blocos, clique em **SharePoint**.

3. Na nova guia do SharePoint em seu navegador, clique em **Criar site**.

4. Em **Nome do site de equipe**, digite **Projeto X**. Em **Configurações de privacidade**, selecione Privado - somente membros podem acessar este **site**.

5. Em **Descrição do site de equipe**, digite **Site do SharePoint para o Projeto X** e clique em **Avançar**.

6. No painel **Quem você quer adicionar?**, clique em **Concluir**.

7. Na nova guia **Projeto X-Página Inicial** em seu navegador, na barra de ferramentas, clique no ícone de configurações e depois clique em **Permissões do site**.

8. No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.

9. Na nova guia **Permissões: Projeto X** em seu navegador, clique em **Configurações de Solicitação de Acesso**.

10. Na caixa de diálogo **Configurações de Solicitações de Acesso**, desmarque **Permitir que os membros compartilhem o site e arquivos e pastas individuais** e **Permitir solicitações de acesso** (para que todas as três caixas de seleção sejam desmarcadas) e, depois, clique em **OK**.

11. Clique em **Membros do Projeto X** na lista.

12. Na página **Pessoas e Grupos**, clique em **Novo**.

13. Na caixa de diálogo **Compartilhar**, digite **Projeto X-Membros**, selecione-o e clique em **Compartilhar**.

14. Clique no botão voltar de seu navegador.

15. Clique em **Proprietários do Projeto X** na lista.

16. Na página **Pessoas e Grupos**, clique em **Novo**.

17. Na caixa de diálogo **Compartilhar**, digite **Projeto X-Administradores**, selecione-o e clique em **Compartilhar**.

18. Clique no botão voltar de seu navegador.

19. Clique em **Visitantes do Projeto X** na lista.

20. Na página **Pessoas e Grupos**, clique em **Novo**.

21. Na caixa de diálogo **Compartilhar**, digite **Projeto X-Visualizadores**, selecione-o e clique em **Compartilhar**.

22. Feche a guia **Pessoas e Grupos** em seu navegador, clique na guia **Projeto X-Página Inicial** em seu navegador e feche o painel **Permissões do site**.

Estes são os resultados da configuração das permissões:

- O grupo membros do ProjectX do SharePoint contém apenas o grupo de acesso ProjectX-Members (que contém apenas as contas de usuário Designer Chefe e Pesquisador Chefe) e o grupo ProjectX (que contém apenas a conta de usuário de administrador global).

- O grupo do SharePoint de proprietários do ProjectX contém apenas o grupo ProjectX-Admins de acesso (que contém apenas a conta de usuário de administrador global).

- O grupo do SharePoint de Visitantes do ProjectX contém apenas o grupo ProjectX-Viewers de acesso (que contém apenas a conta de usuário vp de desenvolvimento).

- Os membros não podem modificar as permissões no nível do site (isso só pode ser feito por membros do grupo Projeto X-Administradores).

- Outras contas de usuário não podem acessar o site ou seus recursos ou solicitar acesso ao site.

A Figura 2 mostra os grupos do SharePoint e suas associações.

**Figura 2**

![Os grupos do SharePoint Online e sua associação a um site de grupo do SharePoint Online isolado](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

Agora vamos demonstrar o acesso usando a conta de usuário do Designer Chefe:

1. Feche a guia **Projeto X-Página Inicial** em seu navegador e clique na guia **Microsoft Office Home** em seu navegador.

2. Clique no nome do administrador global e clique em **Sair**.

3. Entre no centro de administração do Microsoft 365 usando o nome da conta <https://admin.microsoft.com> do Designer Chefe e sua senha.

4. Na lista de blocos, clique em **SharePoint**.

5. Na nova guia **do SharePoint** no navegador, digite **Projeto X** na caixa de pesquisa, ative a pesquisa e clique no site de equipe **do ProjectX.** Você verá uma nova guia no navegador para o site de equipe do ProjectX.

6. Clique no ícone de configurações. Observe que não há opção para **Permissões de Site**. Isso está correto, pois somente os membros do grupo Projeto X-Administradores podem modificar as permissões no site

7. Abra o bloco de notas ou um editor de texto de sua escolha.

8. Copie a URL do site de equipe do ProjectX e a colar em uma nova linha no Bloco de Notas ou no editor de texto.

9. Na nova guia **Projeto X-Página Inicial** em seu navegador, clique em **Documentos**.

10. Copie a URL da pasta de documentos do Projeto X e cole-a em uma nova linha no Bloco de Notas ou em seu editor de texto.

11. Na nova guia **Projeto X-Documentos** em seu navegador, clique em **Novo > Documento do Word**.

12. Digite algum texto na página, aguarde até que o status indique **Salvo,** clique no botão Voltar no navegador e atualize a página. Você deverá ver um novo **Document.docx** na pasta **Documentos**.

13. Clique nas reticências do documento **Document.docx** e clique em **Obter um link**.

14. Copie a URL na caixa de diálogo **Compartilhar "Document.docx"** e a copie em uma nova linha no Bloco de Notas ou no editor de texto e feche a caixa de diálogo **Compartilhar 'Document.docx'.**

15. Feche as guias **Projeto X-Documentos** e **SharePoint** em seu navegador e clique na guia **Microsoft Office Home**.

16. Clique no nome **Designer Chefe** e clique em **Sair**.

Agora vamos demonstrar o acesso usando a conta de usuário vp de desenvolvimento:

1. Entre no Centro de administração do Microsoft 365 usando o nome da conta <https://admin.microsoft.com> vp de desenvolvimento e sua senha.

2. Na lista de blocos, clique em **SharePoint**.

3. Na nova guia **do SharePoint** no navegador, digite **Projeto X** na caixa de pesquisa, ative a pesquisa e clique no site de equipe **do ProjectX.** Você verá uma nova guia em seu navegador para o site de equipe do ProjectX.

4. Clique em **Documentos** e clique no arquivo **Document.docx**.

5. Na guia **Document.docx** em seu navegador, tente modificar o texto. Você deve ver uma mensagem informando que **Este documento é somente leitura.** Isso é esperado, pois a conta de usuário de VP de Desenvolvimento só tem permissões de exibição no site.

6. Feche as guias **Document.docx**, **Projeto X-Documentos** e **SharePoint** em seu navegador.

7. Clique na guia **Microsoft Office Home**, clique no nome **VP de Desenvolvimento** e clique em **Sair**.

Agora vamos demonstrar o acesso com uma conta de usuário que não tem permissões:

1. Entre no Centro de administração do Microsoft 365 usando o nome da conta <https://admin.microsoft.com> do Usuário 3 e sua senha.

2. Na lista de blocos, clique em **SharePoint**.

3. 	Na nova guia **SharePoint** em seu navegador, digite **Projeto X** na caixa de pesquisa e ative a pesquisa. Você deverá ver a mensagem **Não houve resultados para sua pesquisa.**

4. Na instância aberta do Bloco de Notas ou de seu editor de texto, copie a URL do site do Projeto X na barra de endereços de seu navegador e pressione **Enter**. Você deverá ver uma página **Acesso Negado**.

5. No Bloco de Notas ou seu editor de texto, copie a URL da pasta Documentos do Projeto X e cole-a na barra de endereços de seu navegador e pressione **Enter**. Você deverá ver uma página **Acesso Negado**.

6. No Bloco de Notas ou seu editor de texto, copie a URL do arquivo Documents.docx na barra de endereços de seu navegador e pressione **Enter**. Você deverá ver uma página **Acesso Negado**.

7. Feche a guia **SharePoint** em seu navegador, clique na guia **Microsoft Office Home**, clique no nome **Usuário 3** e clique em **Sair**.

Seu site isolado do SharePoint Online agora está pronto para sua experimentação adicional.

## <a name="next-step"></a>Próxima etapa

Quando estiver pronto para implantar um site de equipe do SharePoint Online isolado na produção, confira as considerações de design passo a passo no [Projetar um site de equipe do SharePoint Online isolado](design-an-isolated-sharepoint-online-team-site.md).

## <a name="see-also"></a>Confira também

[Sites de equipe do SharePoint Online isolados](isolated-sharepoint-online-team-sites.md)

[Guias do Laboratório de Teste (TLGs) para adoção de nuvem](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[A configuração base de empresa simulada](../../enterprise/simulated-ent-base-configuration-microsoft-365-enterprise.md)

[A configuração de base leve](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

[Centro de soluções e arquitetura do Microsoft 365](../../solutions/index.yml)