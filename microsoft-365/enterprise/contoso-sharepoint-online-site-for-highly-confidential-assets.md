---
title: Site do SharePoint Online para ativos digitais altamente confidenciais da Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Architecture
description: 'Resumo: Como Contoso implementou um site do SharePoint Online para altamente regulamentados dados para facilitar a colaboração entre sua pesquisa equipes.'
ms.openlocfilehash: 697ddb27b56fd529e9c73b89d9f07b8731ad76c3
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865270"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>Site do SharePoint Online para ativos digitais altamente confidenciais da Contoso Corporation

 **Resumo:** Como a Contoso implementou um site do SharePoint Online para dados altamente regulamentados para facilitar a colaboração entre suas equipes de pesquisa.
  
Ativos mais valiosos da Contoso sua propriedade intelectual na forma de segredos comerciais, como o proprietário de fabricação técnicas e crie as especificações para os produtos que estão em desenvolvimento. Esses ativos estão em formato digital, originalmente armazenado como arquivos em um site do SharePoint Server 2016. Quando Contoso implantado Microsoft 365 Enterprise, eles queriam fazer a transição de seus ativos digitais do local para a nuvem para facilitar o acesso e mais vulnerável colaboração entre as equipes de pesquisa em Bangalore, Moscou, Nova York, Pequim e Paris. 
  
No entanto, devido à sua natureza confidencial, acesso a esses arquivos deve ser:

- Restrito ao conjunto de pessoas que têm permissão para exibir ou alterá-los, com permissões em andamento para o site administrado somente por administradores do SharePoint. 
- Protegido com Data Loss Prevention (DLP) para impedir que usuários distribuí-las fora do site.
- Listas para impedir que usuários não autorizados acessem seus conteúdos, mesmo que elas sejam distribuídas fora do site de controle de acesso criptografado e protegido com.

Os administradores de segurança e o SharePoint em Contoso do departamento de TI decidiu usar um [site do SharePoint Online para altamente regulamentado dados](teams-sharepoint-online-sites-highly-regulated-data.md).
  
A Contoso usou estas etapas para criar e proteger um sites de equipe do SharePoint Online para suas equipes de pesquisa.

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a>Etapa 1: Revisar e verificar os membros de grupos de equipe de pesquisa

Os administradores de TI da Contoso executada uma análise do conjunto de grupos de segurança para suas equipes de pesquisa. Eles removidos, qualquer pessoa que não estava Pesquisador ou não foram necessárias para o acesso aos ativos research. 

Eles também e criado esses novos grupos de segurança:

- **Administração de pesquisa**  O conjunto de administradores do SharePoint que têm controle total sobre o site, incluindo a capacidade de modificar permissões.
- **Membros de pesquisa**  O conjunto de grupos de segurança para as equipes de pesquisa em todo o mundo.
- **Visualizadores de pesquisa**  O conjunto de usuários de gerenciamento, como executivos da organização research, que pode exibir os ativos no site.

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a>Etapa 2: Criado um site de equipe do SharePoint Online isolado 

Administradores da Contoso SharePoint criado pela primeira vez um novo site de equipe denominado **Research**. Em seguida, eles configurados:

- O nível de permissão Controle total para usar o grupo de proprietários do SharePoint Research, que tem o grupo de segurança **Administradores de pesquisa** como membro
- O nível de permissão Editar para usar Research grupo membros do SharePoint, que tem o grupo de segurança **Membros Research** como membro
- O nível de permissão de leitura para usar o grupo do SharePoint de visitantes Research, que tem o grupo de segurança de **Pesquisa-visualizadores** como membro

Aqui estão os níveis de permissão do SharePoint resultantes, grupos do SharePoint e seus membros.

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

Em seguida, eles configurados restrições adicionais para o site.

Para obter os detalhes de configuração, consulte [Deploy um site de equipe do SharePoint Online isolado](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).

## <a name="step-3-configured-the-site-for-a-restrictive-office-365-label-dlp-policy"></a>Etapa 3: Configurado o site para um rótulo do Office 365 restritivo política de DLP

Em primeiro lugar, a Contoso admins aplicadas o rótulo do Office 365 **Altamente confidenciais** para o site de **pesquisa** .

Em seguida, criou uma nova política de DLP do Office 365 denominado **Research** :

- Usa o rótulo do Office 365 **Altamente confidenciais** . 
- É aplicado ao site de **pesquisa** .
- Impede que os usuários compartilhem documentos.

Para obter os detalhes de configuração, consulte [arquivos de proteger o SharePoint Online com o Office 365 rótulos e DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a>Etapa 4: Criado um rótulo de subsites de proteção de informações do Windows Azure para o site

Administradores da Contoso criados um novo rótulo de subsites de proteção de informações do Azure denominado **Research** do rótulo padrão **Altamente confidenciais** em uma política com escopo que:

- Requer criptografia.
- Permite acesso total por membros do grupo de segurança **Membros Research** .
- Permite o acesso de leitura por membros do grupo de segurança **Visualizadores Research** .

Em seguida, ele implantou o cliente de proteção de informações do Windows Azure para os dispositivos de membros da equipe de pesquisa.

Para obter os detalhes de configuração, consulte [proteger o SharePoint Online arquivos com proteção de informações do Windows Azure](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection). 

Aqui está a configuração resultante do site **Research** para ativos altamente confidenciais.

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a>Etapa 5: Migrados os dados de pesquisa do SharePoint local

Os administradores da Contoso movido que todos os locais de arquivos no site local 2016 do SharePoint Server para pastas no novo site do SharePoint Online **Research** pesquisas.

## <a name="step-6-trained-their-users"></a>Etapa 6: Treinados seus usuários 

A equipe de segurança Contoso treinada as equipes de pesquisa em um curso obrigatório que apresentado etapas-los por meio de:

- Como acessar o novo site do SharePoint Online de **pesquisa** e seus arquivos existentes.
- Como criar novos arquivos no site e carregar novos arquivos armazenados localmente.
- Uma demonstração de como a política de DLP impede que arquivos sejam compartilhados externamente.
- Como usar o cliente de proteção de informações do Windows Azure para rotular research arquivos com o rótulo de subsites **Research** .
- Uma demonstração de como o rótulo de subsites **Research** protege um arquivo mesmo quando ele tenha vazado do site.

O resultado final é um ambiente seguro, na qual os pesquisadores podem colaborar em toda a organização em um ambiente seguro. 

Se um documento de pesquisa com o rótulo de subsites **Research** tenha vazado do site **Research** , é criptografada e acessível somente aos membros dos grupos de segurança **Membros de pesquisa** e **Visualizadores de pesquisa** com credenciais válidas.

## <a name="next-step"></a>Próxima etapa

[Implantar](deploy-microsoft-365-enterprise.md) o Microsoft 365 Enterprise na sua organização.

