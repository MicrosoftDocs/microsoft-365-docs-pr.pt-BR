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
description: 'Resumo: como a Contoso usou uma equipe com isolamento de segurança para um projeto secreto para desenvolver um novo pacote de produtos e serviços.'
ms.openlocfilehash: b8794502afcb77a8e597a1b05dfc92acd093f23a
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656058"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Equipe isolada para um projeto secreto da Contoso Corporation

Após um executivo externo, o CEO da Contoso solicitou o desenvolvimento de um novo pacote de produtos e serviços que poderia duplicar os lucros da Contoso nos próximos cinco anos. O projeto secreto para desenvolver o plano comercial, de engenharia e de mercado foi denominado **Projeto 2X** e a equipe principal em toda a empresa foi recrutada. 

Os cronogramas de pesquisa e desenvolvimento estavam rígidos, o que significa que a colaboração precisava ser eficiente e fornecer reuniões seguras, conversas contínuas e armazenamento de arquivos.

Os produtos resultantes do Project 2X foram planos de negócios, especificações de produto e engenharia e materiais de marketing e agendamentos na forma de arquivos do Word, Excel e PowerPoint. 

Devido à sua natureza sensível, o acesso a esses arquivos foi:

- Restrito aos membros da equipe do Project 2X e à liderança sênior.
- Criptografado e protegido com permissões para permitir o acesso apenas aos membros da equipe do Project 2X e à liderança sênior, mesmo se os arquivos foram distribuídos fora de suas pastas protegidas.

A equipe de IT da Contoso usou [uma equipe com isolamento de](secure-teams-security-isolation.md) segurança para o Project 2X e estas etapas.

## <a name="step-1-created-a-private-team"></a>Etapa 1: Criar uma equipe privada

Primeiro, para proteger o acesso ao site subjacente do SharePoint para a equipe, os administradores de IT da Contoso configuraram as políticas de acesso recomendadas [do SharePoint.](../security/office-365-security/sharepoint-file-access-policies.md)

Em seguida, um administrador de IT da Contoso criou uma nova equipe privada chamada Project 2X e adicionou as contas de usuário da equipe do Project 2X como membros. Eles também configuraram a equipe para que apenas os proprietários da equipe do Project 2X possam criar canais privados.

Para obter os detalhes da configuração, [consulte Criar uma equipe privada.](secure-teams-security-isolation.md#create-a-private-team)

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>Etapa 2: Criou um rótulo de sensibilidade para a equipe do Project 2X

Os administradores da Contoso criaram um novo rótulo de sensibilidade chamado **Project 2X** que:

- Criptografia habilitada.
- Permissões Co-Author permissões para o grupo do Microsoft 2X do Project 365.
- Permissões de Visualizador Permitidas para o grupo liderança sênior.
- Acesso bloqueado a dispositivos não autorizados.

Os arquivos na **seção Documentos** do site subjacente do SharePoint do Project 2X foram protegidos por:

- As permissões de site, que só permitem permissões completas a membros do grupo Do Project 2X microsoft 365 e permissões de leitura para o grupo de Liderança Sênior.
- O rótulo de confidencialidade do Project 2X, com criptografia e permissões que viajam com o arquivo se ele for movido ou copiado do site.

Para obter os detalhes de configuração, [consulte Criar um rótulo de sensibilidade.](secure-teams-security-isolation.md#create-a-sensitivity-label)

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>Etapa 3: Configurar o site subjacente do SharePoint

Primeiro, para proteger o acesso ao site subjacente do SharePoint para a equipe, os administradores de IT da Contoso configuraram as políticas de acesso recomendadas [do SharePoint.](../security/office-365-security/sharepoint-file-access-policies.md)

Em seguida, eles definiram configurações de permissão adicionais para o site:

- Para impedir que os membros do grupo do Project 2X compartilhem acesso ao site. Para obter os detalhes de configuração, [confira As configurações do SharePoint para uma equipe com isolamento de segurança.](secure-teams-security-isolation.md#sharepoint-settings)
- Para permissões de leitura para o grupo liderança sênior.

Em seguida, eles definiram configurações de permissão adicionais para o site para impedir que os membros do grupo do Project 2X compartilhem acesso ao site. 

Como canais privados para o Project 2X foram criados, o proprietário do grupo desabilitou o compartilhamento de convidados e definiu o link de compartilhamento padrão para o **valor de pessoas** específicas.

Esta é a configuração resultante da equipe do Project 2X com isolamento de segurança.

![A configuração resultante da equipe do Project 2X](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>Etapa 4: Membros treinados da equipe do Project 2X

A equipe de segurança da Contoso treinamentou os membros da equipe do Project 2X em um curso obrigatório que os pesquisa:

- Como acessar a nova equipe do Project 2X, usar reuniões e chats e como colaborar em arquivos da equipe.
- Como criar novos arquivos na equipe e carregar novos arquivos criados localmente.
- Como rotular arquivos com o rótulo de sensibilidade do Project 2X.
- Uma demonstração de como o rótulo do Project 2X protege um arquivo mesmo quando ele sai da equipe.

O resultado final foi um ambiente seguro no qual os membros da equipe do Project 2X colaboraram em um ambiente seguro para chats, reuniões e arquivos.

Aqui está um exemplo de um arquivo armazenado no site do Project 2X subjacente com o rótulo de confidencialidade do Project 2X atribuído.

![Um exemplo de um arquivo armazenado no site do Project 2X subjacente](../media/contoso-team-for-top-secret-project-example.png)

Em alguns casos, os membros da equipe do Project 2X baixaram arquivos protegidos pelo rótulo do Project 2X em uma unidade local para trabalho offline. 

No entanto, depois de serem solicitados a solicitar credenciais ao abri-las, eles percebidoam seu erro e as excluíram.

Devido ao ambiente de colaboração do Teams e aos recursos de segurança do Microsoft 365, os detalhes do Project 2X foram mantidos em segredo durante o projeto. A Contoso anunciaram seus planos e está em processo de implantação dos novos produtos e serviços para a satisfação de seus clientes e investidores e o chagrin de seus concorrentes.

## <a name="next-step"></a>Próxima etapa

[Implante uma equipe com isolamento de segurança](secure-teams-security-isolation.md) em sua organização.

