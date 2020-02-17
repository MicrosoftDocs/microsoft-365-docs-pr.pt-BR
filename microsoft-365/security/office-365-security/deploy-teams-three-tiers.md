---
title: Implantar equipes para três camadas de proteção para arquivos
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
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
description: Crie e configure equipes com o Microsoft Teams para vários níveis de proteção de informações para arquivos.
ms.openlocfilehash: 63a4b6763165f38e1de5331324e5a7b3573ea0f1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083314"
---
# <a name="deploy-teams-for-three-tiers-of-protection-for-files"></a>Implantar equipes para três camadas de proteção para arquivos

Use as etapas neste artigo para projetar e implantar equipes de linha de base, confidenciais e altamente confidenciais. Para obter mais informações sobre essas três camadas de proteção, confira [Proteção de arquivos no Microsoft Teams](secure-files-in-teams.md).

## <a name="baseline-teams"></a>Equipes de linha de base

A proteção de linha de base inclui as equipes públicas e privadas. As equipes públicas podem ser descobertas e acessadas por qualquer pessoa na organização. Os sites privados podem ser descobertos e acessados somente por membros do grupo do Office 365 associado à equipe. Ambos os tipos de equipes permitem aos membros compartilhar o site com outras pessoas.

### <a name="public"></a>Público

Siga as instruções [neste artigo](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) para criar uma equipe de base com acesso e permissões públicas.

Esta é a configuração resultante.

![Proteção de nível de linha de base para uma equipe pública.](../../media/baseline-public-team.png)

### <a name="private"></a>Privado

Siga as instruções [neste artigo](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) para criar uma equipe de base com acesso e permissões privadas.

Esta é a configuração resultante.

![Proteção de nível de linha de base para uma equipe privada.](../../media/baseline-private-team.png)

## <a name="sensitive-teams"></a>Dados confidenciais

Para uma equipe confidencial, comece [criando uma equipe privada](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).

Em seguida, configure o site subjacente do SharePoint para evitar o compartilhamento por membros da equipe.

1. Na barra de ferramentas da equipe, clique em **Arquivos**.

2. Clique nas reticências e em **Abrir no SharePoint**.

3. Na barra de ferramentas do site do SharePoint subjacente, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.

4. No painel **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.

5. Em **Permissões de compartilhamento**, selecione **Somente proprietários do site podem compartilhar arquivos, pastas e o site** e clique em **Salvar**.

Esta é a configuração resultante.

![Proteção confidencial para uma equipe.](../../media/sensitive-team.png)

## <a name="highly-confidential-teams"></a>Equipes altamente confidenciais

Com uma equipe altamente confidencial, comece [criando uma equipe privada](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).

Em seguida, configure o site subjacente do SharePoint para evitar compartilhamentos por membros da equipe e solicitações de acesso por não membros da equipe.

1. Na barra de ferramentas da equipe, clique em **Arquivos**.

2. Clique nas reticências e em **Abrir no SharePoint**.

3. Na barra de ferramentas do site do SharePoint subjacente, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.

4. No painel **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.

5. Em **Permissões de compartilhamento**, **Somente proprietários do site podem compartilhar arquivos, pastas e o site**.

6. Desative **Permitir solicitações de acesso** e clique em **Salvar**.

Esta é a configuração resultante.

![Proteção altamente confidencial para uma equipe.](../../media/highly-confidential-team.png)

## <a name="next-step"></a>Próxima etapa

[Proteger arquivos em equipes com rótulos de retenção e DLP](deploy-teams-retention-DLP.md)

## <a name="see-also"></a>Confira também

[Proteger arquivos no Microsoft Teams](secure-files-in-teams.md)

[Adoção da nuvem e de soluções híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
