---
title: Implantar sites do SharePoint Online para três camadas de proteção
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 'Resumo: Crie e configure sites de equipe do SharePoint Online para vários níveis de proteção de informações.'
ms.openlocfilehash: 1827c4a19cfd31a236dfbd58e454c610cae14477
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42075501"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a>Implantar sites do SharePoint Online para três camadas de proteção

Use as etapas neste artigo para projetar e implantar sites de equipe do SharePoint Online de linha de base, confidenciais e altamente confidenciais. Para obter mais informações sobre essas três camadas de proteção, consulte [Arquivos e sites do SharePoint Online seguros](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).
  
## <a name="baseline-sharepoint-online-team-sites"></a>Sites de equipe do SharePoint Online de linha de base

A proteção de linha de base inclui os sites de equipe públicos e privados. Os sites de equipe públicos podem ser descobertos e acessados por qualquer pessoa na organização. Os sites privados podem ser descobertos e acessados somente por membros do grupo do Office 365 associado ao site de equipe. Esses dois tipos de sites de equipe permitem que os membros compartilhem o site com outras pessoas.
  
### <a name="public"></a>Público

Para criar um site de equipe do SharePoint Online de linha de base com permissões e acesso público, siga [essas instruções](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).

Esta é a configuração resultante.
  
![Proteção de nível de linha de base para um site de equipe do SharePoint Online público.](../media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a>Privado

Para criar um site de equipe do SharePoint Online de linha de base com permissões e acesso privado, siga [essas instruções](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).
  
Esta é a configuração resultante.
  
![Proteção de nível de linha de base para um site de equipe do SharePoint Online privado.](../media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a>Sites confidenciais de equipe do SharePoint Online

Sites de equipe Confidenciais do SharePoint Online são iniciados como um site de equipe privado.
  
Primeiro, crie o site de equipe do SharePoint Online privado com [estas instruções](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).

Em seguida, no novo site de equipe do SharePoint Online, configure as permissões adicionais com estas etapas.

1.  Na barra de ferramentas do site de equipe do SharePoint, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.
2.  No painel **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.
3.  Em **Permissões de compartilhamento**, selecione **Somente proprietários do site podem compartilhar arquivos, pastas e o site** e clique em **Salvar**.

Os resultados dessas configurações de permissão são:

- A capacidade dos membros de compartilhar com outros membros está desabilitada.
- A capacidade de não membros solicitarem o acesso está habilitada.

Esta é a configuração resultante.
  
![Proteção de nível confidencial para um site de equipe isolado do SharePoint Online.](../media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
Os membros do site, por meio da associação de grupo em um dos grupos de acesso, agora podem colaborar com segurança nos recursos do site.
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a>Sites de equipe do SharePoint Online altamente confidenciais

Um site de equipe do SharePoint Online altamente confidencial é um site de equipe privado com configurações de permissões adicionais.

Primeiro, crie o site de equipe do SharePoint Online privado com [estas instruções](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).

Em seguida, no novo site de equipe do SharePoint Online, configure as permissões adicionais com estas etapas.

1.  Na barra de ferramentas do site de equipe do SharePoint, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.
2.  No painel **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.
3.  Em **Permissões de compartilhamento**, **Somente proprietários do site podem compartilhar arquivos, pastas e o site**.
4. Desative **Permitir solicitações de acesso** e clique em **Salvar**.

Os resultados dessas configurações de permissão são:

- A capacidade dos membros de compartilhar com outros membros está desabilitada.
- A capacidade de não membros solicitarem o acesso está desabilitada.

Esta é a configuração resultante.
  
![Proteção com alto nível de confidencialidade para um site de equipe isolado do SharePoint Online.](../media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
Os membros do site, por meio da associação de grupo em um dos grupos de acesso, agora podem colaborar com segurança nos recursos do site.
  
## <a name="next-step"></a>Próxima etapa

[Proteger arquivos do SharePoint Online com DLP e rótulos do Office 365](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a>Confira também

[Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações do Agile](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Adoção da nuvem e de soluções híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
