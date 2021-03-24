---
title: Equipe isolada para um projeto secreto da Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: 'Resumo: Como a Contoso usou uma equipe com isolamento de segurança para um projeto top-secret para desenvolver um novo pacote de produtos e serviços.'
ms.openlocfilehash: d5ab2808251ff6a53f8975ea868431691d3301e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051001"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Equipe isolada para um projeto secreto da Contoso Corporation

Depois de um executivo fora do local, o CEO da Contoso ordenou o desenvolvimento de um novo pacote de produtos e serviços que poderia duplicar os lucros da Contoso nos próximos cinco anos. O projeto ultra-secreto para desenvolver o plano de negócios, engenharia e mercado foi denominado **Project 2X** e a equipe-chave em toda a empresa foi recrutada. 

As linhas do tempo para pesquisa e desenvolvimento eram estreitas, o que significava que a colaboração precisava ser eficiente e fornecer reuniões seguras, conversas em andamento e armazenamento de arquivos.

Os produtos resultantes para o Project 2X eram planos de negócios, especificações de produto e engenharia e materiais de marketing e agendamentos na forma de arquivos do Word, Excel e PowerPoint. 

Devido à sua natureza sensível, o acesso a esses arquivos foi:

- Restrito aos membros da equipe do Project 2X e à liderança sênior.
- Criptografado e protegido com permissões para permitir o acesso apenas aos membros da equipe do Project 2X e à liderança sênior, mesmo que os arquivos tenham sido distribuídos fora de suas pastas protegidas.

A equipe de IT da Contoso usou [uma equipe com isolamento de](secure-teams-security-isolation.md) segurança para o Project 2X e essas etapas.

## <a name="step-1-created-a-private-team"></a>Etapa 1: Criar uma equipe privada

Primeiro, para proteger o acesso ao site subjacente do SharePoint para a equipe, os administradores de IT da Contoso configuraram as políticas de acesso recomendadas [do SharePoint.](../security/defender-365-security/sharepoint-file-access-policies.md)

Em seguida, um administrador de IT da Contoso criou uma nova equipe privada chamada Project 2X e adicionou as contas de usuário da equipe do Project 2X como membros. Eles também configuraram a equipe para que apenas os proprietários da equipe do Project 2X possam criar canais privados.

Para obter os detalhes da configuração, consulte [Create a private team](secure-teams-security-isolation.md#create-a-private-team).

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>Etapa 2: Criou um rótulo de sensibilidade para a equipe do Project 2X

Os administradores da Contoso criaram um novo rótulo de sensibilidade chamado **Project 2X** que:

- Criptografia habilitada.
- Permissões Co-Author para o grupo do Project 2X Microsoft 365.
- Permissões permitidas do Visualizador para o grupo de Liderança Sênior.
- Acesso bloqueado a dispositivos não autorizados.

Os arquivos na **seção Documentos** do site subjacente do SharePoint do Project 2X foram protegidos por:

- As permissões de site, que só permitem permissões completas para membros do grupo do Project 2X Microsoft 365 e permissões de leitura para o grupo de Liderança Sênior.
- O rótulo de confidencialidade do Project 2X, com criptografia e permissões que viajam com o arquivo se ele for movido ou copiado do site.

Para obter os detalhes da configuração, [consulte Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>Etapa 3: Configurar o site subjacente do SharePoint

Primeiro, para proteger o acesso ao site subjacente do SharePoint para a equipe, os administradores de IT da Contoso configuraram as políticas de acesso recomendadas [do SharePoint.](../security/defender-365-security/sharepoint-file-access-policies.md)

Em seguida, eles configuraram configurações de permissão adicionais para o site:

- Para impedir que os membros do grupo do Project 2X compartilhem acesso ao site. Para obter os detalhes da configuração, consulte [Configurações do SharePoint para uma equipe com isolamento de segurança](secure-teams-security-isolation.md#sharepoint-settings).
- Para permissões de leitura para o grupo de Liderança Sênior.

Em seguida, eles configuraram configurações de permissão adicionais para o site para impedir que os membros do grupo do Project 2X compartilhem acesso ao site. 

Como canais privados do Project 2X foram criados, o proprietário do grupo desabilitou o compartilhamento de convidados e definiu o link de compartilhamento padrão para **o valor De pessoas** específicas.

Aqui está a configuração resultante da equipe do Project 2X com isolamento de segurança.

![A configuração resultante da equipe do Project 2X](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>Etapa 4: Membros treinados da equipe do Project 2X

A equipe de segurança da Contoso treinou os membros da equipe do Project 2X em um curso obrigatório que os fez passar por:

- Como acessar a nova equipe do Project 2X, usar reuniões e chats e como colaborar em arquivos de equipe.
- Como criar novos arquivos na equipe e carregar novos arquivos criados localmente.
- Como rotular arquivos com o rótulo de sensibilidade do Project 2X.
- Uma demonstração de como o rótulo do Project 2X protege um arquivo mesmo quando ele sai da equipe.

O resultado final foi um ambiente seguro no qual os membros da equipe do Project 2X colaboraram em um ambiente seguro para chats, reuniões e arquivos.

Aqui está um exemplo de um arquivo armazenado no site subjacente do Project 2X com o rótulo de confidencialidade do Project 2X atribuído.

![Um exemplo de um arquivo armazenado no site subjacente do Project 2X](../media/contoso-team-for-top-secret-project-example.png)

Em algumas instâncias, os membros da equipe do Project 2X baixaram arquivos protegidos pelo rótulo do Project 2X para uma unidade local para trabalho offline. 

No entanto, após serem solicitados a solicitar credenciais ao abri-las, eles perceberam o erro e as excluíram.

Devido ao ambiente de colaboração do Teams e aos recursos de segurança do Microsoft 365, os detalhes do Project 2X foram mantidos em segredo durante a duração do projeto. A Contoso anuncia seus planos e está em processo de implantação dos novos produtos e serviços para o deleite de seus clientes e investidores e o adélio de seus concorrentes.

## <a name="next-step"></a>Próxima etapa

[Implante uma equipe com isolamento de segurança](secure-teams-security-isolation.md) em sua organização.

