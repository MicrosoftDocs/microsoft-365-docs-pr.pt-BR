---
title: Criar sites de equipe - Ambiente de desenvolvimento de campanha política
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/21/2018
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 'Resumo: crie sites de equipe do SharePoint Online públicos, privados, confidenciais e altamente confidenciais em um ambiente de desenvolvimento/teste de campanha política.'
ms.openlocfilehash: d22ada823877d4c0996be942c379e12929242eaf
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755231"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a>Criar sites de equipe em um ambiente de desenvolvimento/teste de campanha política

 **Resumo:** crie sites de equipe do SharePoint Online públicos, privados, confidenciais e altamente confidenciais em um ambiente de desenvolvimento/teste de campanha política. 
  
Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution. These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.
  
## <a name="phase-1-create-your-political-campaign-devtest-environment"></a>Fase 1: Criar seu ambiente de desenvolvimento/teste de campanha política

Primeiro, siga as instruções em [Configurar grupos e usuários para um ambiente de desenvolvimento/teste de campanha política](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) para criar assinaturas, usuários e grupos.
  
## <a name="phase-2-create-labels"></a>Fase 2: criar rótulos

Nesta fase, você deve criar os rótulos para os diferentes níveis de segurança para as pastas e documentos do site da equipe do SharePoint Online.
  
1. Se necessário, entre no centro de administração com as credenciais da conta do administrador global da sua assinatura de avaliação. Para obter ajuda, consulte [Como entrar no Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Na guia **Microsoft Office Home**, clique no bloco **Administração**.
    
3. Na nova guia **Centro de Administração da Microsoft 365** do navegador, clique em **Centros de administração > Segurança&amp; e Conformidade**.
    
4. Na nova guia **Início – Segurança &amp;e Conformidade** do navegador, clique em **Classificações > Rótulos**.
    
5. No painel **Início > Rótulos**, clique em **Criar um rótulo**.
    
6. No painel **Atribuir nome ao seu rótulo**, digite **Interno** e clique em **Avançar**.
    
7. No painel **Configurações do rótulo**, clique em **Avançar**.
    
8. No painel **Examine as configurações**, clique em **Criar este rótulo** e clique em **Fechar**.
    
9. Repita as etapas de 5 a 8 para os rótulos adicionais:
    
  - Private
    
  - Confidencial
    
  - Altamente Confidencial
    
10. No painel **Início > Rótulos**, clique em **Publicar rótulos**.
    
11. No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.
    
12. No painel **Escolher rótulos**, clique em **Adicionar** e selecione todos os quatro rótulos.
    
13. Clique em **Concluído**.
    
14. No painel **Escolher rótulos para publicar**, clique em **Avançar**.
    
15. No painel **Escolher locais**, clique em **Avançar**.
    
16. No painel **Nomear sua política**, digite **Campanha** em **Nome** e clique em **Avançar**.
    
17. No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.
    
## <a name="phase-3-create-your-sharepoint-online-team-sites"></a>Fase 3: Criar seus sites de equipe do SharePoint Online

Nessa fase, você cria e configura sites de equipe do SharePoint Online para a campanha política correspondente aos quatro tipos de sites de equipe do SharePoint Online.
  
### <a name="campaign-wide-team-site"></a>Site de equipe de toda a campanha

Para criar um site de equipe do SharePoint Online público de linha de base, faça o seguinte:
  
1. Se necessário, use um navegador do seu computador local e entre no centro de administração ([https://admin.microsoft.com](https://admin.microsoft.com)) usando sua conta de administrador global.
    
2. Na lista de blocos, clique em **SharePoint**.
    
3. Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.
    
4. Na página **Criar um site**, clique em **Site de equipe**.
    
5. Em **Nome do site**, digite **Toda a campanha**. 
    
6. Na **Descrição do site de equipe**, digite **Site do SharePoint para toda a campanha**.
    
7. Em **Configurações de privacidade**, selecione **Público – qualquer pessoa na organização pode acessar esse site** e clique em **Avançar**.
    
8. No painel **Quem você deseja adicionar?**, clique em **Concluir**.
    
Em seguida, configure a pasta de documentos do site de equipe Toda a campanha com o rótulo Interno.
  
1. Na guia **Toda a campanha – Página inicial** do navegador, clique em **Documentos**.
    
2. Clique no ícone de configurações e clique em **Configurações de biblioteca**.
    
3. Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.
    
4. Em **Configurações – Aplicar Rótulo**, selecione **Interno** e clique em **Salvar**.
    
### <a name="campaign-project-1-team-site"></a>Site de equipe 1 de projeto de campanha

Para criar um site de equipe do SharePoint Online privado de linha de base para um projeto dentro da campanha, faça o seguinte:
  
1. Se necessário, use um navegador do seu computador local e entre no centro de administração ([https://admin.microsoft.com](https://admin.microsoft.com)) usando sua conta de administrador global.
    
2. Na lista de blocos, clique em **SharePoint**.
    
3. Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.
    
4. Na página **Criar um site**, clique em **Site de equipe**.
    
5. Em **Nome do site**, digite **Projeto 1 da campanha**. 
    
6. Na **Descrição do site de equipe**, digite **Site do SharePoint para Projeto 1 de campanha**.
    
7. Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.
    
8. No painel **Quem você deseja adicionar?**, clique em **Concluir**.
    
Em seguida, configure a pasta de documentos do site de equipe Projeto 1 de campanha com o rótulo Privado.
  
1. Na guia **Projeto 1 de campanha – Página inicial** do navegador, clique em **Documentos**.
    
2. Clique no ícone de configurações e clique em **Configurações de biblioteca**.
    
3. Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.
    
4. Em **Configurações – Aplicar Rótulo**, selecione **Privado** e clique em **Salvar**.
    
### <a name="campaign-marketing-team-site"></a>Site de equipe de marketing de campanha

Para criar um site de equipe do SharePoint Online isolado de nível confidencial para recursos de marketing de campanha, faça o seguinte:
  
1. Usando um navegador no seu computador local, entre no centro de administração ([https://admin.microsoft.com](https://admin.microsoft.com)) usando sua conta de administrador global.
    
2. Na lista de blocos, clique em **SharePoint**.
    
3. Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.
    
4. Na página **Criar um site**, clique em **Site de equipe**.
    
5. Em **Nome do site de equipe**, digite **Marketing de campanha**.
    
6. Em **Descrição do site de equipe**, digite **Site do SharePoint para marketing de campanha (confidencial)**.
    
7.  Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.
    
8. No painel **Quem você deseja adicionar?**, clique em **Concluir**.
    
9. Na nova guia **Marketing de campanha** no navegador, na barra de ferramentas, clique no ícone de configurações e depois clique em **Permissões do site**.
    
10. No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.
    
11. Na nova guia **Permissões** no navegador, clique em **Configurações de Solicitação de Acesso**.
    
12. Na caixa de diálogo **Configurações de Solicitação de Acesso**, desmarque as caixas de seleção **Permitir que membros compartilhem o site e arquivos e pastas individuais** e **Permitir que membros convidem outras pessoas para o grupo de membros do site**, digite **ITAdmin1 @**<your organization name> **.onmicrosoft.com** em **Enviar todas as solicitações para acesso** e clique em **OK**.
    
13. Clique em **Membros da campanha de marketing ** na lista.
    
14. Na página **Pessoas e Grupos**, clique em **Novo**.
    
15. Na caixa de diálogo **Compartilhar**, digite **Funcionários sênior e estratégicos**, selecione o item e clique em **Compartilhar**.
    
16. Repita as etapas 14 e 15 para o grupo **Equipe de análise** e a conta de usuário **Regular1**.
    
17. Clique no botão Voltar de seu navegador.
    
18. Clique em **Proprietários da campanha de marketing** na lista.
    
19. Na página **Pessoas e Grupos**, clique em **Novo**.
    
20. Na caixa de diálogo **Compartilhar**, digite **Equipe de TI**, selecione o item e clique em **Compartilhar**.
    
21. Clique no botão Voltar de seu navegador.
    
22. Feche a guia **Pessoas e Grupos** no navegador, clique na guia **Página inicial da campanha de marketing** no navegador e feche o painel **Permissões de site**.
    
Aqui estão os resultados da configuração de permissões:
  
- O grupo do SharePoint **Membros da campanha de marketing ** contém apenas o grupo **Funcionários sênior e estratégicos** (que contém as contas de usuário Candidato, ChiefOfStaff e Strategic1), o grupo **Marketing de campanha** (que contém a conta de administrador global), o grupo **Equipe de análise** (que contém a conta de usuário DataScientist1) e a conta de usuário **Regular1 **.
    
- O grupo do SharePoint **Marketing de campanha – Proprietários** contém apenas o grupo **Equipe de TI** (que contém apenas as contas de usuário ITAdmin1 e ITAdmin2).
    
- O grupo do SharePoint **Marketing de campanha – Visitantes** não contém grupos ou contas de usuário.
    
- Os membros não podem modificar permissões de nível de site (isso pode ser feito apenas por membros do grupo **Marketing de campanhas – Proprietários**).
    
- Outras contas de usuário não podem acessar o site ou seus recursos, mas podem solicitar o acesso ao site, que enviará um email para a caixa de correio da conta de usuário ITAdmin1.
    
Em seguida, configure a pasta de documentos do site de equipe de marketing de campanha com o rótulo Confidencial.
  
1. Na guia **Marketing de campanha – Página inicial** do navegador, clique em **Documentos**.
    
2. Clique no ícone de configurações e clique em **Configurações de biblioteca**.
    
3. Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.
    
4. Em **Configurações – Aplicar Rótulo**, selecione **Confidencial** e clique em **Salvar**.
    
Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization. This DLP policy will apply to resources in the Campaign marketing site.
  
1. Na guia **Microsoft Office Home** no navegador, clique no bloco **Segurança&amp; Conformidade**.
    
2. Na nova guia **Segurança e&amp; Conformidade** no navegador, clique em **Prevenção de perda de dados > Política**.
    
3. No painel **Prevenção de perda de dados**, clique em **+ Criar uma política**.
    
4. No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.
    
5. No painel **Atribuir um nome à política**, digite **Sites de equipe do SharePoint Online de rótulo Confidencial** em **Nome** e clique em **Avançar**.
    
6. No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.
    
7. Na lista de locais, desabilite os locais **Email do Exchange** e **Contas do OneDrive** e clique em **Avançar**.
    
8. No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Editar**.
    
9. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e clique em **Rótulos**.
    
10. No painel **Rótulos**, clique em **+ Adicionar**, selecione o rótulo **Confidencial**, clique em **Adicionar** e clique em **Concluído**.
    
11. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.
    
12. No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Avançar**.
    
13. No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.
    
14. No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.
    
15. Na caixa de texto, digite ou cole o seguinte:
    
  - To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.
    
16. Clique em **OK**.
    
17. No painel **O que deseja fazer se detectarmos informações confidenciais?**, desmarque a caixa de seleção **Impedir que as pessoas compartilhem e restringir o acesso ao conteúdo compartilhado** e clique em **Avançar**.
    
18. No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.
    
19. No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.
    
### <a name="campaign-strategy-team-site"></a>Site de equipe de estratégia de campanha

Para criar um site de equipe do SharePoint Online isolado no nível altamente confidencial para recursos de estratégia de campanha, faça o seguinte:
  
1. Se necessário, use um navegador do seu computador local e entre no centro de administração ([https://admin.microsoft.com](https://admin.microsoft.com)) usando sua conta de administrador global.
    
2. Na lista de blocos, clique em **SharePoint**.
    
3. Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.
    
4. Na página **Criar um site**, clique em **Site de equipe**.
    
5. Em **Nome do site de equipe**, digite **Estratégia da campanha**.
    
6. Em **Descrição do site da equipe**, digite **Site do SharePoint para estratégia da campanha (altamente confidencial)**.
    
7.  Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.
    
8. No painel **Quem você deseja adicionar?**, clique em **Concluir**.
    
9. Na nova guia **Estratégia da campanha** no navegador, na barra de ferramentas, clique no ícone de configurações e depois clique em **Permissões do site**.
    
10. No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.
    
11. Na nova guia **Permissões** no navegador, clique em **Configurações de Solicitação de Acesso**.
    
12. Na caixa de diálogo **Configurações de Solicitação de Acesso**, desmarque **Permitir que os membros compartilhem o site e arquivos e pastas individuais** e **Permitir que os membros convidem outros para o grupo de membros do site** (de forma que todas as três caixas de seleção estejam desmarcadas) e clique em **OK**.
    
13. Clique em **Membros da estratégia da campanha** na lista.
    
14. Na página **Pessoas e Grupos**, clique em **Novo**.
    
15. Na caixa de diálogo **Compartilhar**, digite **Funcionários sênior e estratégicos**, selecione o item e clique em **Compartilhar**.
    
16. Clique em **Proprietários de Estratégia de Campanha** na lista.
    
17. Na página **Pessoas e Grupos**, clique em **Novo**.
    
18. Na caixa de diálogo **Compartilhar**, digite **Equipe de TI**, selecione o item e clique em **Compartilhar**.
    
19. Clique no botão Voltar de seu navegador.
    
20. Feche a guia **Pessoas e Grupos** no navegador, clique na guia **Estratégia de campanha – Página Inicial** no navegador e feche o painel **Permissões do site**.
    
Aqui estão os resultados da configuração de permissões:
  
- O grupo **Membros estratégicos da campanha** do SharePoint contém apenas o grupo **Funcionários sênior e estratégicos** (que contém apenas as contas de usuário Candidato, ChiefOfStaff e Strategic1) e o grupo ** Estratégia da campanha** (que contém a conta de usuário de administrador global).
    
- O grupo do SharePoint **Estratégia da campanha – Proprietários** contém apenas o grupo **Equipe de TI** (que contém apenas as contas de usuário ITAdmin1 e ITAdmin2).
    
- O grupo do SharePoint **Estratégia da campanha – Visitantes** não contém grupos ou contas de usuário.
    
- Os membros não podem modificar permissões de nível de site (isso pode ser feito apenas por membros do grupo **Estratégia da campanha – Proprietários**).
    
- Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.
    
Em seguida, configure a pasta de documentos do Site de equipe de estratégia de campanha com o rótulo Altamente Confidencial.
  
1. Na guia **Estratégia da campanha – Página inicial** do navegador, clique em **Documentos**.
    
2. Clique no ícone de configurações e clique em **Configurações de biblioteca**.
    
3. Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.
    
4. Em **Configurações – Aplicar Rótulo**, selecione **Altamente Confidencial** e clique em **Salvar**.
    
Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization. This DLP policy will apply to resources in the Campaign strategy site.
  
1. Se necessário, use um navegador no seu computador local e entre no centro de administração ([https://admin.microsoft.com](https://admin.microsoft.com)) com uma conta com a função de Administrador de Segurança ou Administrador da Empresa.
    
2. Na guia **Página Inicial do Microsoft Office** no navegador, clique no bloco **Segurança e Conformidade**.
    
3. Na nova guia **Segurança e&amp; Conformidade** no navegador, clique em **Prevenção de perda de dados > Política**.
    
4. No painel **Prevenção de perda de dados**, clique em **+ Criar uma política**.
    
5. No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.
    
6. No painel **Atribuir um nome à política**, digite **Sites de equipe do SharePoint Online de rótulo Altamente Confidencial** em **Nome** e clique em **Avançar**.
    
7. No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.
    
8. Na lista de locais, desabilite os locais **Email do Exchange** e **Contas do OneDrive** e clique em **Avançar**.
    
9. No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Editar**.
    
10. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e clique em **Rótulos**.
    
11. No painel **Rótulos**, clique em **+ Adicionar**, selecione o **rótulo Altamente Confidencial**, clique em **Adicionar** e clique em **Concluído**.
    
12. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.
    
13. No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Avançar**.
    
14. No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.
    
15. No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.
    
16. Na caixa de texto, digite ou cole o seguinte:
    
  - To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.
    
17. Clique em **OK**.
    
18. No painel **O que deseja fazer se detectarmos informações confidenciais?**, selecione **Exigir uma justificativa de negócios para substituir** e clique em **Avançar**.
    
19. No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.
    
20. No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.
    
Use as instruções em [Ativar o Azure RMS com o centro de administração do Microsoft 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).
  
Depois, configure a Proteção de Informações do Azure com uma nova política e sub-rótulo em escopo para proteção e permissões com as seguintes etapas:
  
1. Acesse o centro de administração com uma conta que tenha a função de Administrador de Segurança ou Administrador da Empresa. Para obter ajuda, consulte [Onde entrar no Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Em uma guia separada do navegador, vá para o Portal do Azure ([https://portal.azure.com](https://portal.azure.com)).
    
4. No painel de pesquisa, digite **informações**e, em seguida, clique em **Proteção de Informações do Azure**.

5. Clique em **Rótulos**.
    
6. Clique com o botão direito do mouse no rótulo **Altamente Confidencial** e clique em **Adicionar um sub-rótulo**.
    
7. Digite **CampaignStrategy** em **Nome** e **Rótulo para documentos no Site de equipe de estratégia de campanha** em **Descrição**.
    
8. Em **Definir permissões para documentos e emails que contenham este rótulo**, clique em **Proteger**.
    
9. Na seção **Proteção**, clique em **Azure (chave de nuvem)**.
    
10. Na folha **Proteção**, em **Configurações de proteção**, clique em **+ Adicionar permissões**.
    
11. Na folha **Adicionar permissões**, em **Especificar usuários e grupos**, clique em **+ Procurar no diretório**.
    
12. No painel **Usuários e Grupos do AAD**, selecione **Funcionários sênior e estratégicos** e clique em **Selecionar**.
    
13. Em **Escolher permissões a partir de valores predefinidos ou definir valores personalizados**, clique em **Personalizar** e, em seguida, clique nas caixas de seleção **Exibir Direitos**, **Editar Conteúdo**, **Salvar**, **Responder** e **Responder a Todos**.
    
14. Clique em **OK** duas vezes.
    
15. Na folha **Sub-rótulo**, clique em **Salvar** e em **OK**.

16. Na folha **Proteção de Informações do Azure**, clique em **Políticas > + Adicionar uma nova política**.
    
17. Digite **CampaignStrategy** em **Nome** e **Documentos no Site de equipe de estratégia de campanha** em **Descrição**.
    
18. Clique em **Selecionar usuários ou grupos que obtêm essa política > Usuário/Grupos**e selecione **Funcionários sênior e estratégicos**.
    
19. Clique em **Selecionar > OK**.

20. Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.   

21. Clique em **Salvar** e em **OK**.
  
Agora você está pronto para começar a criar documentos nesses quatro sites e testar o acesso a eles com várias contas de usuário. 
  
Para proteger um documento com a Proteção de Informações do Azure e esse novo rótulo, você deve [instalar o cliente de Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/rms-client/install-client-app) em um computador de teste, instalar o Office do centro de administração e entrar no Microsoft Word com uma conta no grupo **Funcionários sênior e estratégicos** de sua assinatura de avaliação.
  
## <a name="see-also"></a>Confira também

[Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações Agile](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Defina grupos e usuários para um ambiente de desenvolvimento/teste de uma campanha política](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)
  
[Guias do Laboratório de Teste (TLGs) para adoção de nuvem](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[Adoção da nuvem e de soluções híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




