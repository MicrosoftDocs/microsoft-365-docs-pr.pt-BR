---
title: Site do SharePoint Online para ativos digitais altamente confidenciais da Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Resumo: como a contoso implementou um site do SharePoint Online para dados altamente regulamentados para facilitar a colaboração entre suas equipes de pesquisa.'
ms.openlocfilehash: 6c61d02c802a77afeb93a58b59114741c6630f9e
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369522"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>Site do SharePoint Online para ativos digitais altamente confidenciais da Contoso Corporation

 **Resumo:** Como a contoso implementou um site do SharePoint Online para dados altamente regulamentados para facilitar a colaboração entre suas equipes de pesquisa.
  
Os ativos mais valiosos da Contoso são sua propriedade intelectual na forma de segredos comerciais, como técnicas de fabricação proprietárias e especificações de design para produtos que estão em desenvolvimento. Esses ativos estão em formato digital, originalmente armazenados como arquivos em um site do SharePoint Server 2016. Quando a contoso implantou o Microsoft 365 Enterprise, eles queriam migrar seus ativos digitais locais para a nuvem para facilitar o acesso e mais colaboração aberta entre as equipes de pesquisa em Paris, Moscow, Nova York, Pequim e Bangalore. 
  
No entanto, devido à natureza confidencial, o acesso a esses arquivos deve ser:

- Restrito ao conjunto de pessoas que têm permissão para exibir ou alterá-las, com permissões contínuas para o site administrado somente pelos administradores do SharePoint. 
- Protegido por DLP (prevenção contra perda de dados) para impedir que os usuários os distribuam fora do site.
- Criptografado e protegido com listas de controle de acesso para impedir que usuários não autorizados acessem seus conteúdos, mesmo que eles sejam distribuídos fora do site.

Administradores de segurança e do SharePoint no departamento de ti da Contoso decidiram usar um [site do SharePoint Online para dados altamente regulamentados](teams-sharepoint-online-sites-highly-regulated-data.md).
  
A contoso usou estas etapas para criar e proteger sites de equipe do SharePoint Online para suas equipes de pesquisa.

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a>Etapa 1: revisado e verificado os membros dos grupos da equipe de pesquisa

Os administradores de ti da Contoso executaram uma análise do conjunto de grupos de segurança para suas equipes de pesquisa. Eles removeram qualquer pessoa que não seja um pesquisador ou não precisevam de acesso aos ativos de pesquisa. 

Eles também criaram esses novos grupos de segurança:

- **Research-admins**  O conjunto de administradores do SharePoint que têm controle total sobre o site, incluindo a capacidade de modificar permissões.
- **Pesquisa-Membros**  O conjunto de grupos de segurança para as equipes de pesquisa em todo o mundo.
- **Pesquisa-visualizadores**  O conjunto de usuários de gerenciamento, como executivos na organização de pesquisa, que só pode exibir os ativos no site.

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a>Etapa 2: criado um site de equipe do SharePoint Online isolado 

Os administradores do SharePoint da Contoso criaram primeiro um novo site de equipe chamado **pesquisa**. Eles então configurados:

- O nível de permissão controle total para usar o grupo de proprietários de pesquisa do SharePoint, que tem o grupo de segurança **Research-admins** como um membro
- O nível de permissão Editar para usar o grupo de membros de pesquisa do SharePoint, que tem o grupo de segurança **membros de pesquisa** como um membro
- O nível de permissão de leitura para usar o grupo de visitantes de pesquisa do SharePoint, que tem o grupo de segurança de **Visualizador de pesquisa** como membro

Estes são os níveis de permissão do SharePoint resultantes, grupos do SharePoint e seus membros.

![Níveis de permissão do SharePoint, grupos do SharePoint e seus membros](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

Em seguida, eles configuraram restrições adicionais para o site.

Para obter os detalhes de configuração, consulte [implantar um site de equipe do SharePoint Online isolado](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a>Etapa 3: configurar o site para uma política de DLP restritiva

Primeiro, os administradores da Contoso aplicaram o rótulo de retenção **altamente confidencial** do Office 365 ao site de **pesquisa** .

Em seguida, criamos uma nova política de DLP do Office 365 chamada **pesquisa** que:

- Usa o rótulo de retenção **altamente confidencial** do Office 365. 
- É aplicado ao site de **pesquisa** .
- Bloqueia os usuários quando eles tentam compartilhar um ativo digital no site de **pesquisa** fora da contoso.

Para obter detalhes sobre a configuração, consulte [proteger arquivos do SharePoint Online com rótulos de retenção e DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a>Etapa 4: criou um subrótulo da proteção de informações do Azure para o site

Os administradores da Contoso criaram um novo subrótulo de proteção de informações do Azure chamado **pesquisa** do rótulo **altamente confidencial** padrão em uma política com escopo:

- Requer criptografia.
- Permite acesso total por membros do grupo de segurança **Research-Members** .
- Permite o acesso de leitura por membros do grupo de segurança de **visualizadores de pesquisa** .

Em seguida, implantamos o cliente de proteção de informações do Azure nos dispositivos dos membros da equipe de pesquisa.

Para obter detalhes sobre a configuração, consulte [proteger arquivos do SharePoint Online com a proteção de informações do Azure](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection). 

Aqui está a configuração resultante do site de **pesquisa** para ativos altamente confidenciais.

![A configuração resultante do site * * Research * * para ativos altamente confidenciais](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

Arquivos em pastas do site de **pesquisa** são protegidos por:

- O subrótulo de proteção de informações do Azure de **pesquisa** , que aplica criptografia e permssions a cada arquivo que viaja com o arquivo quando ele é movido ou copiado do site de **pesquisa** .
- A política de DLP de **pesquisa** , que usa o rótulo de retenção **altamente confidencial** e as configurações que impedem o arquivo de ser compartilhado com usuários externos.
- O conjunto de permissões de site, que só permite o acesso aos membros dos grupos de segurança e administração de **pesquisa de membros** e **visualizadores** de pesquisa pelos membros do grupo de segurança **Research-admins** .

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a>Etapa 5: migrar os dados de pesquisa do SharePoint local

Os administradores da Contoso mudaram todos os arquivos de pesquisa local no site do SharePoint Server 2016 local para pastas no novo site do SharePoint Online de **pesquisa** .

## <a name="step-6-trained-their-users"></a>Etapa 6: treinado seus usuários 

A equipe de segurança da Contoso treinou as equipes de pesquisa em um curso obrigatório que as apresentou:

- Como acessar o novo site do SharePoint Online de **pesquisa** e seus arquivos existentes.
- Como criar novos arquivos no site e carregar novos arquivos armazenados localmente.
- Uma demonstração de como a política de DLP impede que os arquivos sejam compartilhados externamente.
- Como usar o cliente de proteção de informações do Azure para rotular arquivos de pesquisa com o subrótulo de **pesquisa** .
- Uma demonstração de como o subrótulo de **pesquisa** protege um arquivo mesmo quando ele é vazado do site.

O resultado final é um ambiente seguro no qual os pesquisadores podem colaborar através da organização em um ambiente seguro. 

Se um documento de pesquisa com o subrótulo de **pesquisa** for vazado no site de **pesquisa** , ele será criptografado e acessível somente para os membros dos grupos de segurança **Research-Members** e **Research-visualizadores** com credenciais válidas.

## <a name="next-step"></a>Próxima etapa

[Implantar](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise em sua organização.

