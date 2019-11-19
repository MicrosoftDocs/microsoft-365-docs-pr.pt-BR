---
title: Equipe para um projeto de segredo superior da Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Resumo: como a contoso usou uma equipe para dados altamente regulamentados de um projeto de segredo superior para desenvolver um novo pacote de produtos e serviços.'
ms.openlocfilehash: 23a967ea7ffdb3497d705a3ddda4d3c56e415b8e
ms.sourcegitcommit: 0ceb79a633f7004e82b80e69b6f7a7329ccec7ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699878"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a>Equipe para um projeto de segredo superior da Contoso Corporation

Após um executivo externo, o CEO da Contoso pediu o desenvolvimento de um novo pacote de produtos e serviços que poderia dobrar os lucros da Contoso nos próximos cinco anos. O projeto de segredo superior para desenvolver o plano de negócios, de engenharia e de mercado foi chamado de **projeto 2x** e o principal pessoal na empresa foi recrutado. 

Os cronogramas para pesquisa e desenvolvimento estavam apertados, o que significava que a colaboração era eficiente e forneceva reuniões seguras, conversas em andamento e armazenamento de arquivos.

Os resultados finais do projeto 2X foram planos de negócios, especificações de produtos e de engenharia e materiais de marketing e agendamentos no formato de arquivos do Word, Excel e PowerPoint. 

Devido à sua natureza confidencial, o acesso a esses arquivos era:

- Restrito aos membros da equipe do projeto 2.
- Protegido por uma política de prevenção contra perda de dados (DLP) para impedir que os membros da equipe do projeto 2 o compartilhem fora da equipe.
- Criptografado e protegido com permissões para permitir acesso somente aos membros da equipe do Project 2X, mesmo que os arquivos tenham sido distribuídos fora da contoso.

A equipe de ti da Contoso usou uma [equipe para dados altamente regulamentados](secure-teams-highly-regulated-data-scenario.md) para o projeto 2x e estas etapas.

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a>Etapa 1: criar uma equipe privada e bloquear o site do SharePoint subjacente

Para proteger o acesso ao site do SharePoint subjacente para a equipe, os administradores de ti da Contoso configuraram as [políticas de acesso recomendadas do SharePoint](sharepoint-file-access-policies.md).

Em seguida, um administrador de ti da Contoso criou uma nova equipe privada chamada projeto 2X e adicionou as contas de usuário do projeto 2X como membros.

Em seguida, eles definiram configurações de permissão adicionais para o site a fim de evitar que o projeto seja compartilhado de compartilhar o acesso ao site e impedir outros de solicitar acesso ao site.

Para obter detalhes sobre a configuração, consulte [configurações do SharePoint para uma equipe altamente regulamentada](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a>Etapa 2: configurou uma política de DLP e o site subjacente para um rótulo de retenção 

Primeiro, os administradores da Contoso aplicaram o rótulo de retenção do Office 365 **altamente confidencial** existente à seção **documentos** do site do SharePoint subjacente da equipe do projeto 2.

Em seguida, criamos uma nova política de DLP do Office 365 chamada **Project 2x** que:

- Usa o rótulo de retenção altamente confidencial do Office 365.
- Bloqueia os usuários quando eles tentam compartilhar um arquivo na equipe do projeto 2X fora da contoso.

Para obter os detalhes de configuração, consulte [proteger arquivos no Microsoft Teams com rótulos de retenção e DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).

## <a name="step-3-created-an-office-365-sensitivity-label-for-the-project-2x-team"></a>Etapa 3: criou um rótulo de confidencialidade do Office 365 para o projeto 2X Team

Os administradores da Contoso criaram um novo rótulo de sensibilidade do Office 365 chamado **projeto 2x** que:

- Requer criptografia.
- Permite permissões de coautoria para o grupo do projeto 2X Office 365.

Veja a seguir a configuração resultante da equipe do projeto 2X.

![A configuração resultante da equipe do projeto 2X](./media/contoso-team-for-highly-confidential-assets/final-config.png)
 
Arquivos na seção Documents do projeto subjacente o site do SharePoint é protegido por:

- As permissões de site, que permitem apenas o acesso aos membros do grupo do projeto 2X do Office 365.
- O rótulo de retenção altamente confidencial, que é atribuído automaticamente a novos arquivos.
- Uma política de DLP que usa o rótulo e as configurações de retenção altamente confidenciais que impedirão o arquivo de ser compartilhado com usuários externos.
- O rótulo de sensibilidade do projeto 2X, com criptografia e permissões que trafegam com o arquivo se ele for movido ou copiado do site.

Aqui está um exemplo de um arquivo armazenado no site subjacente do projeto 2 com o rótulo de retenção altamente regulamentado e o rótulo de sensibilidade do projeto 2X atribuído.

![Um exemplo de um arquivo armazenado no site subjacente do projeto 2](./media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a>Etapa 4: projeto treinado 2 membros da equipe

A equipe de segurança da Contoso treinou o projeto 2 membros da equipe em um curso obrigatório que os apresentou:

- Como acessar a nova equipe do projeto 2, use reuniões e chats e como colaborar em arquivos da equipe.
- Como criar novos arquivos na equipe e carregar novos arquivos criados localmente.
- Uma demonstração de como a política de DLP impede que os arquivos sejam compartilhados externamente.
- Como rotular arquivos com o rótulo de sensibilidade do projeto 2X.
- Uma demonstração de como o rótulo projeto 2X protege um arquivo, mesmo quando ele sai da equipe.

O resultado final era um ambiente seguro no qual o projeto 2X membros da equipe colaboraram em um ambiente seguro para chats, reuniões e arquivos.

Em alguns casos, o Project 2X os membros da equipe baixaram arquivos protegidos pelo rótulo Project 2X para uma unidade local para trabalho offline. No entanto, após serem solicitadas as credenciais ao serem abertas, elas perceberam o erro e as excluíram.

Por causa do ambiente de colaboração do Teams e dos recursos de segurança do Microsoft 365, os detalhes do projeto 2X foram mantidos secretos para a duração do projeto. A contoso anunciou seus planos e está no processo de distribuir os novos produtos e serviços para a encantarão de seus clientes e investidores e para o Chagrin de seus concorrentes.

## <a name="next-step"></a>Próxima etapa

[Implantar](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise em sua organização.

## <a name="see-also"></a>Confira também

[Biblioteca de produtividade do Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)
