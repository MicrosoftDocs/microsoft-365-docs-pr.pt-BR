---
title: Equipe isolada para um projeto de segredo superior da Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: 'Resumo: como a contoso usou uma equipe com isolamento de segurança para um projeto de segredo principal para desenvolver um novo pacote de produtos e serviços.'
ms.openlocfilehash: f7b38a7ef43cdb50b46f3e37f855f490dc32cfdf
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521620"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Equipe isolada para um projeto de segredo superior da Contoso Corporation

Após um executivo externo, o CEO da Contoso pediu o desenvolvimento de um novo pacote de produtos e serviços que poderia dobrar os lucros da Contoso nos próximos cinco anos. O projeto de segredo superior para desenvolver o plano de negócios, de engenharia e de mercado foi chamado de **projeto 2x** e o principal pessoal na empresa foi recrutado. 

Os cronogramas para pesquisa e desenvolvimento estavam apertados, o que significava que a colaboração era eficiente e forneceva reuniões seguras, conversas em andamento e armazenamento de arquivos.

Os resultados finais do projeto 2X foram planos de negócios, especificações de produtos e de engenharia e materiais de marketing e agendamentos no formato de arquivos do Word, Excel e PowerPoint. 

Devido à sua natureza confidencial, o acesso a esses arquivos era:

- Restrito aos membros da equipe do projeto 2.
- Criptografado e protegido com permissões para permitir acesso somente aos membros da equipe do Project 2X, mesmo que os arquivos tenham sido distribuídos fora de suas pastas seguras.

A equipe de ti da Contoso usou uma [equipe com isolamento de segurança](secure-teams-security-isolation.md) para o projeto 2 e estas etapas.

## <a name="step-1-created-a-private-team"></a>Etapa 1: criar uma equipe privada

Primeiro, para proteger o acesso ao site do SharePoint subjacente para a equipe, os administradores de ti da Contoso configuraram as [políticas de acesso recomendadas do SharePoint](../enterprise/sharepoint-file-access-policies.md).

Em seguida, um administrador de ti da Contoso criou uma nova equipe privada chamada projeto 2X e adicionou as contas de usuário do projeto 2X como membros.

Para obter detalhes sobre a configuração, consulte [Create a Private Team](secure-teams-security-isolation.md#create-a-private-team).

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>Etapa 2: criou um rótulo de confidencialidade para o projeto 2X Team

Os administradores da Contoso criaram um novo rótulo de sensibilidade chamado **projeto 2x** que:

- Requer criptografia.
- Permite permissões de coautoria para o grupo 2 do projeto do Microsoft 365.

Arquivos na seção **Documents** do projeto subjacente o site do SharePoint é protegido por:

- As permissões de site, que permitem o acesso somente aos membros do grupo 2 do projeto 2X Microsoft 365.
- O rótulo de sensibilidade do projeto 2X, com criptografia e permissões que trafegam com o arquivo se ele for movido ou copiado do site.

Para obter detalhes sobre a configuração, consulte [criar um rótulo de confidencialidade](secure-teams-security-isolation.md#create-a-sensitivity-label).

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>Etapa 3: configurou o site do SharePoint subjacente

Primeiro, para proteger o acesso ao site do SharePoint subjacente para a equipe, os administradores de ti da Contoso configuraram as [políticas de acesso recomendadas do SharePoint](../enterprise/sharepoint-file-access-policies.md).

Em seguida, eles definiram configurações de permissão adicionais para o site a fim de evitar que o projeto 2X Compartilhe o acesso ao site. Para obter detalhes sobre a configuração, consulte [configurações do SharePoint para uma equipe com isolamento de segurança](secure-teams-security-isolation.md#sharepoint-settings).

Veja a seguir a configuração resultante da equipe do projeto 2X.

![A configuração resultante da equipe do projeto 2X](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>Etapa 4: projeto treinado 2 membros da equipe

A equipe de segurança da Contoso treinou o projeto 2 membros da equipe em um curso obrigatório que os apresentou:

- Como acessar a nova equipe do projeto 2, use reuniões e chats e como colaborar em arquivos da equipe.
- Como criar novos arquivos na equipe e carregar novos arquivos criados localmente.
- Uma demonstração de como a política de DLP impede que os arquivos sejam compartilhados externamente.
- Como rotular arquivos com o rótulo de sensibilidade do projeto 2X.
- Uma demonstração de como o rótulo projeto 2X protege um arquivo, mesmo quando ele sai da equipe.

O resultado final era um ambiente seguro no qual o projeto 2X membros da equipe colaboraram em um ambiente seguro para chats, reuniões e arquivos.

Veja a seguir um exemplo de um arquivo armazenado no site subjacente do projeto 2 com o rótulo de sensibilidade do projeto 2 atribuído.

![Um exemplo de um arquivo armazenado no site subjacente do projeto 2](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

Em alguns casos, o Project 2X os membros da equipe baixaram arquivos protegidos pelo rótulo Project 2X para uma unidade local para trabalho offline. No entanto, após serem solicitadas as credenciais ao serem abertas, elas perceberam o erro e as excluíram.

Por causa do ambiente de colaboração do Teams e dos recursos de segurança do Microsoft 365, os detalhes do projeto 2X foram mantidos secretos para a duração do projeto. A contoso anunciou seus planos e está no processo de distribuir os novos produtos e serviços para a encantarão de seus clientes e investidores e para o Chagrin de seus concorrentes.

## <a name="next-step"></a>Próxima etapa

[Implantar uma equipe com isolamento de segurança](secure-teams-security-isolation.md) em sua organização.

