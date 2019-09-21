---
title: Implantar sites do SharePoint Online para três camadas de proteção
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 'Resumo: Crie e configure sites de equipe do SharePoint Online para vários níveis de proteção de informações.'
ms.openlocfilehash: 2ddf3de7180d384c387bdc335afda6214508e3c5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37070682"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a>Implantar sites do SharePoint Online para três camadas de proteção

 **Resumo:** Crie e configure sites de equipe do SharePoint Online para vários níveis de proteção de informações.
  
Use as etapas neste artigo para projetar e implantar sites de equipe do SharePoint Online de linha de base, confidenciais e altamente confidenciais. Para obter mais informações sobre essas três camadas de proteção, consulte [Arquivos e sites do SharePoint Online seguros](/security/office-365-security/secure-sharepoint-online-sites-and-files.md).
  
## <a name="baseline-sharepoint-online-team-sites"></a>Sites de equipe do SharePoint Online de linha de base

A proteção de linha de base inclui os sites de equipe públicos e privados. Os sites de equipe públicos podem ser descobertos e acessados por qualquer pessoa na organização. Os sites privados podem ser descobertos e acessados somente por membros do grupo do Office 365 associado ao site de equipe. Esses dois tipos de sites de equipe permitem que os membros compartilhem o site com outras pessoas.
  
### <a name="public"></a>Público

Para criar um site de equipe do SharePoint Online de linha de base com permissões e acesso público, faça o seguinte:
  
1. Entre no centro de administração com uma conta que também será usada para administrar o site de equipe do SharePoint Online (um administrador do SharePoint Online). Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Na lista de blocos, clique em **SharePoint**.
    
3. Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.
    
4. Na página **Criar um site**, clique em **Site de equipe**.
    
5. Em **Nome do site**, digite um nome para o site de equipe público. 
    
6. Em **Descrição do site de equipe**, digite uma descrição do objetivo do site.
    
7. Em **Configurações de privacidade**, selecione **Público – qualquer pessoa na organização pode acessar esse site** e clique em **Avançar**.
    
8. No painel **Quem você deseja adicionar?**, clique em **Concluir**.
    
Esta é a configuração resultante.
  
![Proteção de nível de linha de base para um site de equipe do SharePoint Online público.](media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a>Privado

Para criar um site de equipe do SharePoint Online de linha de base com permissões e acesso privado, faça o seguinte:
  
1. Entre no centro de administração com uma conta que também será usada para administrar o site de equipe do SharePoint Online (um administrador do SharePoint Online). Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Na lista de blocos, clique em **SharePoint**.
    
3. Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.
    
4. Na página **Criar um site**, clique em **Site de equipe**.
    
5. Em **Nome do site**, digite um nome para o site de equipe privado. 
    
6. Em **Descrição do site de equipe,** digite uma descrição do objetivo do site.
    
7. Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.
    
8. No painel **Quem você deseja adicionar?**, em **Adicionar membros**, digite os nomes das contas de usuário que têm acesso a esse site de equipe privado.
    
9. Quando você terminar de adicionar o conjunto inicial de membros ao site, clique em **Concluir**.
    
Esta é a configuração resultante.
  
![Proteção de nível de linha de base para um site de equipe do SharePoint Online privado.](media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a>Sites de equipe do SharePoint Online confidenciais

Um site de equipe do SharePoint Online confidencial é um site de equipe isolado, o que significa que as permissões são controladas por meio da associação em grupos do SharePoint, em vez de ser membro do grupo do Office 365 associado ao site de equipe.
  
Para criar um site de equipe isolado, siga estas duas etapas principais.
  
### <a name="step-1-design-your-isolated-site"></a>Etapa 1: Projetar o site isolado

Para projetar o site de equipe isolado, você precisa determinar:
  
- Seus níveis de permissão e grupos do SharePoint.
    
- O conjunto de grupos de acesso que serão membros dos grupos do SharePoint.
    
     O conjunto de grupos de acesso recomendado é um para os membros do site, um para os visualizadores do site e um para os administradores do site.
    
- Se você usará grupos aninhados dentro de seus grupos de acesso.
    
Por exemplo, os níveis de permissão e estrutura de grupo recomendados têm essa aparência:
  
|**Grupo do SharePoint**|**Nível de permissão**|**Grupo de acesso (exemplos)**|
|:-----|:-----|:-----|
|Membros do [nome do site]  <br/> |Editar  <br/> |Membros do [nome do site]  <br/> |
|Visitantes do [nome do site]  <br/> |Ler  <br/> |Visualizadores do [nome do site]  <br/> |
|Proprietários do [nome do site]  <br/> |Controle total  <br/> |Administradores do [nome do site]  <br/> |
   
Os níveis de permissão e grupos do SharePoint são criados por padrão para um site de equipe. Você precisa determinar os nomes dos seus grupos de acesso.
  
Para obter os detalhes do processo de design, consulte [Projetar um site de equipe do SharePoint Online isolado](/security/office-365-security/design-an-isolated-sharepoint-online-team-site.md).
  
### <a name="step-2-deploy-your-isolated-site"></a>Etapa 2: Implantar o site isolado

Para implantar seu site isolado, primeiro você precisa:
  
- Determinar as contas de usuário e os grupos a serem adicionados a cada um dos seus grupos de acesso.
    
- Criar os grupos de acesso e adicionar os membros de usuário e grupo.
    
Para obter as etapas detalhadas, consulte a **Fase 1** de [Implantar um site de equipe do SharePoint Online isolado](/security/office-365-security/design-an-isolated-sharepoint-online-team-site.md).
  
Em seguida, crie o site de equipe do SharePoint Online com estas etapas.
  
1. Entre no centro de administração com uma conta que também será usada para administrar o site de equipe do SharePoint Online (um administrador do SharePoint Online). Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Na lista de blocos, clique em **SharePoint**.
    
3. Na nova guia **SharePoint** do navegador, clique em **+ Criar site**.
    
4. Na página **Criar um site**, clique em **Site de equipe**.
    
5. Em **Nome do site**, digite um nome para o site de equipe privado.
    
6. Na descrição de **Site de equipe**, digite uma descrição opcional.
    
7. Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.
    
8. No painel **Quem você deseja adicionar?**, clique em **Concluir**.
    
Em seguida, no novo site de equipe do SharePoint Online, configure as permissões com estas etapas.
  
1. Determine o nome UPN do administrador de TI ou outra pessoa que será responsável por responder e resolver as solicitações de acesso ao site (belindan@contoso.com é um exemplo de um UPN). 
    
2. Na barra de ferramentas, clique no ícone Configurações e, em seguida, clique em **Permissões do site**.
    
3. No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.
    
4. Na nova guia **Permissões** do navegador, clique em **Configurações de Solicitação de Acesso**.
    
5. Na caixa de diálogo **Configurações de Solicitações de Acesso**:
    
  - Desmarque as caixas de seleção **Permitir que os membros compartilhem o site e arquivos e pastas individuais** e **Permitir que os membros convidem outras pessoas para o grupo de membros do site**.
    
  - Digite o UPN do seu administrador de TI da etapa 1 em **Enviar todas as solicitações de acesso**.
    
  - Clique em **OK**.
    
6. Na guia **Permissões** do navegador, clique em **Membros do [nome do site]** na lista.
    
7. Em **Pessoas e Grupos**, clique em **Novo**.
    
8. Na caixa de diálogo **Compartilhar**, digite o nome do grupo de acesso dos membros do seu site para esse site, selecione-o e clique em **Compartilhar**.
    
9. Clique no botão Voltar de seu navegador.
    
10. Clique em **Proprietários do [nome do site]** na lista.
    
11. Em **Pessoas e Grupos**, clique em **Novo**.
    
12. Na caixa de diálogo **Compartilhar**, digite o nome do grupo de acesso dos administradores do site para esse site, selecione-o e clique em **Compartilhar**.
    
13. Clique no botão Voltar de seu navegador.
    
14. Clique em **Visitantes do [nome do site]** na lista.
    
15. Em **Pessoas e Grupos**, clique em **Novo**.
    
16. Na caixa de diálogo **Compartilhar**, digite o nome do grupo de acesso dos visualizadores do site para esse site, selecione-o e clique em **Compartilhar**.
    
17. Feche a guia **Permissões** do navegador.
    
Os resultados dessas configurações de permissão são:
  
- O grupo do SharePoint **Proprietários do [nome do site]** contém o grupo de acesso de administradores de site, em que todos os membros têm o nível de permissão **Controle total**.
    
- O grupo do SharePoint **Membros do [nome do site]** contém o grupo de acesso de membros de site, em que todos os membros têm o nível de permissão **Editar**.
    
- O grupo do SharePoint **Visitantes do [nome do site]** contém o grupo de acesso de visualizadores de site, em que todos os membros têm o nível de permissão **Ler**.
    
- A capacidade de os membros convidarem outros membros está desabilitada.
    
- A capacidade de não membros solicitarem o acesso está habilitada.
    
Esta é a configuração resultante.
  
![Proteção de nível confidencial para um site de equipe isolado do SharePoint Online.](media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
Os membros do site, por meio da associação de grupo em um dos grupos de acesso, agora podem colaborar com segurança nos recursos do site.
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a>Sites de equipe do SharePoint Online altamente confidenciais

Um site de equipe do SharePoint Online altamente confidencial é um site de equipe isolado, o que significa que as permissões são controladas por meio da associação em grupos do SharePoint, em vez de ser membro do grupo do Office 365 associado ao site de equipe.
  
Para criar um site de equipe isolado para colaboração e informações altamente confidenciais, há duas etapas principais.
  
### <a name="step-1-design-your-isolated-site"></a>Etapa 1: Projetar o site isolado

Para projetar o site de equipe isolado, você precisa determinar:
  
- Seus níveis de permissão e grupos do SharePoint.
    
- O conjunto de grupos de acesso que serão membros dos grupos do SharePoint.
    
     O conjunto de grupos de acesso recomendado é um para os membros do site, um para os visualizadores do site e um para os administradores do site.
    
- Se você usará grupos aninhados dentro de seus grupos de acesso.
    
Por exemplo, os níveis de permissão e estrutura de grupo recomendados têm essa aparência:
  
|**Grupo do SharePoint**|**Nível de permissão**|**Grupo de acesso (exemplos)**|
|:-----|:-----|:-----|
|Membros do [nome do site]  <br/> |Editar  <br/> |Membros do [nome do site]  <br/> |
|Visitantes do [nome do site]  <br/> |Ler  <br/> |Visualizadores do [nome do site]  <br/> |
|Proprietários do [nome do site]  <br/> |Controle total  <br/> |Administradores do [nome do site]  <br/> |
   
Os níveis de permissão e grupos do SharePoint são criados por padrão para um site de equipe. Você precisa determinar os nomes dos seus grupos de acesso.
  
Para obter os detalhes do processo de design, consulte [Projetar um site de equipe do SharePoint Online isolado](/security/office-365-security/design-an-isolated-sharepoint-online-team-site.md).
  
### <a name="step-2-deploy-your-isolated-site"></a>Etapa 2: Implantar o site isolado

Para implantar seu site isolado, primeiro você precisa:
  
- Determinar os membros do grupo e usuário de cada um dos grupos de acesso.
    
- Criar os grupos de acesso e adicionar os membros de usuário e grupo.
    
- Criar um site de equipe isolado que usa os grupos de acesso.
    
Para obter as etapas detalhadas, confira [Implantar um site de equipe do SharePoint Online isolado](/security/office-365-security/design-an-isolated-sharepoint-online-team-site.md).
  
Os resultados das configurações de permissão são:
  
- O grupo do SharePoint **Proprietários do [nome do site]** contém o grupo de acesso de administradores de site, em que todos os membros têm o nível de permissão **Controle total**.
    
- O grupo do SharePoint **Membros do [nome do site]** contém o grupo de acesso de membros de site, em que todos os membros têm o nível de permissão **Editar**.
    
- O grupo do SharePoint **Visitantes do [nome do site]** contém o grupo de acesso de visualizadores de site, em que todos os membros têm o nível de permissão **Ler**.
    
- A capacidade de os membros convidarem outros membros está desabilitada.
    
- A capacidade de não membros solicitarem o acesso está desabilitada.
    
Esta é a configuração resultante.
  
![Proteção com alto nível de confidencialidade para um site de equipe isolado do SharePoint Online.](media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
Os membros do site, por meio da associação de grupo em um dos grupos de acesso, agora podem colaborar com segurança nos recursos do site.
  
## <a name="next-step"></a>Próxima etapa

[Proteger arquivos do SharePoint Online com DLP e rótulos do Office 365](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a>Confira também

[Proteger arquivos e sites do SharePoint Online](/security/office-365-security/secure-sharepoint-online-sites-and-files.md)
  
[Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações do Agile](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Adoção da nuvem e de soluções híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
