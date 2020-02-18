---
title: Sites do SharePoint para dados altamente regulamentados
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- SPO_Content
ms.custom: ''
description: Crie um site de equipe do SharePoint seguro para armazenar seus arquivos mais valiosos e confidenciais.
ms.openlocfilehash: c74a2bc59a6ef9d16ecd0dfbed06d577bd98649b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085051"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a>Sites do SharePoint para dados altamente regulamentados

*Este cenário aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*

O Microsoft 365 Enterprise inclui um conjunto completo de serviços baseados em nuvem, para que você possa criar, armazenar, proteger e gerenciar seus dados altamente regulamentados armazenados em arquivos. Isso inclui dados que são:

- Sujeitos a regulamentações regionais.
- Mais importantes de sua organização, como segredos comerciais, financeiros ou informações de recursos humanos e estratégias da organização.

>[!Note]
> Um cenário semelhante usando o Microsoft Teams esta [aqui](secure-teams-highly-regulated-data-scenario.md).
>

Um cenário da Microsoft 365 Enterprise baseada na nuvem, que atende a essa necessidade comercial, requer que você:

- Armazene arquivos (documentos, apresentações de slides, planilhas, etc.) em um site de equipe do SharePoint.
- Bloqueie o site para impedir:
  - Acesso a usuários que não são membros do grupo do Office 365 para o site.
  - Que membros do site concedam acesso a outras pessoas.
  - Que aqueles que não sejam membros do site solicitem acesso a ele.
- Configure um rótulo de retenção do Office 365 para seus sites do SharePoint como uma maneira padrão de impedir que os usuários enviem arquivos fora da organização.
- Criptografe os arquivos mais confidenciais do site com criptografia que acompanha o arquivo.
- Adicione permissões aos arquivos mais confidenciais para que, mesmo que sejam compartilhados fora do site, a abertura do arquivo ainda exija as credenciais válidas de uma conta de usuário que tenha a permissão.

A tabela a seguir mapeia os requisitos desse cenário para um recurso do Microsoft 365 Enterprise.

|||
|:-------|:-----|
| **Requisito** | **Recurso do Microsoft 365 Enterprise** |
| Armazenar arquivos  | Sites de equipe do SharePoint |
| Bloquear o site | Grupos do Office 365 e permissões de site de equipe do SharePoint |
| Rotular os arquivos do site | Rótulos de retenção do Office 365 |
| Bloquear usuários ao enviar arquivos para fora da organização. | Políticas de Prevenção Contra Perda de Dados (DLP) no Office 365 |
| Criptografar todos os arquivos do site | Rótulos ou sub-rótulos de confidencialidade do Office 365 |
| Adicionar permissões aos arquivos do site | Rótulos ou sub-rótulos de confidencialidade do Office 365 |
|||

Aqui está um exemplo de configuração para um site do SharePoint seguro.

![Os sites do SharePoint para um cenário de dados altamente regulamentados](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

Este cenário exige que você já tenha implantado:

- A fase de [identidade](identity-infrastructure.md) e as etapas 1 e 2 da fase de [proteção de informações](infoprotect-infrastructure.md) da infraestrutura de base. 
- [SharePoint](sharepoint-online-onedrive-workload.md).

As fases a seguir o ajudarão a projetar, configurar e direcionar a adoção de sites do SharePoint para dados altamente regulamentados.

<a name="poster"></a> Confira um resumo de uma página desse cenário no [pôster de sites do SharePoint para dados altamente regulamentados](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf).

[![Pôster de sites do SharePoint para dados altamente regulamentados](../media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)

Você também pode baixar este pôster nos formatos [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf) ou [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx) e imprimir em papel carta, oficial ou tabloide (11 x 17).


## <a name="identity-and-device-access-prerequisites"></a>Pré-requisitos de acesso ao dispositivo e identidade

Para proteger o acesso ao site do SharePoint, assegure-se de ter configurado [políticas de identidade e de acesso ao dispositivo](identity-access-policies.md) e as [políticas de acesso recomendadas do SharePoint](sharepoint-file-access-policies.md).

## <a name="phase-1-design"></a>Fase 1: Design

Para criar um site do SharePoint para dados altamente regulamentados, você deve primeiro identificar sua finalidade. Por exemplo, o departamento de pesquisa e desenvolvimento de uma organização de manufatura precisa de um site do SharePoint para armazenar especificações de design atuais de produtos existentes e um local para colaborar em novos produtos. Somente os membros do departamento de Pesquisa e Desenvolvimento e os executivos selecionados terão permissão para acessar o site.

Essa finalidade gerará a determinação de itens essenciais de configuração como:

- O rótulo de retenção do Office 365 para atribuir à parte Documentos do site e às políticas de DLP para o rótulo
- As configurações de um sub-rótulo de confidencialidade do Office 365 que os usuários aplicam a arquivos altamente confidenciais armazenados no site

Quando determinado, você usa essas configurações para configurar o site na Fase 2. 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a>Etapa 1 rótulos de retenção do Office 365 e políticas DLP

Quando aplicada à parte de Documentos de um site de equipe do SharePoint, os rótulos de retenção do Office 365 fornecem um método padrão de classificação de todos os arquivos armazenados no site.
 
Nos sites do SharePoint para dados altamente controlados, você precisa determinar qual rótulo de retenção do Office 365 será usado.

Para considerações de design dos rótulos do Office 365, consulte [Rótulos e classificação do Office 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).

Para proteger informações confidenciais e evitar a divulgação acidental ou intencional, use as políticas DLP. Para obter mais informações, consulte esta [visão geral](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).

Para sites do SharePoint, você deve configurar uma política DLP do rótulo de retenção do Office 365 atribuído ao site para bloquear usuários quando eles tentam compartilhar arquivos com usuários externos. 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a>Etapa 2: Sub-rótulo de confidencialidade do Office 365

Para fornecer criptografia e um conjunto de permissões aos seus arquivos mais confidenciais, os usuários devem aplicar um rótulo ou sub-rótulo de confidencialidade do Office 365. Existe uma sub-rótulo em um rótulo existente. 

Use um rótulo de confidencialidade quando precisar de um pequeno número de rótulos para de uso global e equipes privadas individuais. Use um sub-rótulo de confidencialidade quando você tiver um grande número de rótulos ou quiser organizar rótulos para sites seguros em seu rótulo altamente regulamentado. 

As configurações do rótulo ou sub-rótulo aplicado acompanham o arquivo. Mesmo que ele tenha sido vazado fora do site, somente as contas de usuário autenticado que têm permissões poderão abri-lo.

### <a name="design-results"></a>Resultados de design

Você determinou o seguinte:

- O rótulo de retenção apropriado do Office 365 e a política DLP que está associada ao rótulo
- As configurações do sub-rótulo de confidencialidade do Office 365 que inclui criptografia e permissões

## <a name="phase-2-configure"></a>Fase 2: Configurar

Nesta fase, você usa as configurações determinadas na Fase 1 e as implementa para criar um site do SharePoint para dados altamente regulamentados.

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a>Etapa 1: Criar um site de equipe do SharePoint privado com proprietários e membros do grupo do Office 365 correspondente

Siga [essas instruções]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) para criar um site de equipe do SharePoint privado.

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a>Etapa 2: Configurar permissões adicionais para o site de equipe do SharePoint

No site do SharePoint, defina estas configurações de permissão.

1. Na barra de ferramentas, clique no ícone Configurações e, em seguida, clique em **Permissões do site**.
2. No painel **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.
3. Em **Permissões de compartilhamento**, **Somente proprietários do site podem compartilhar arquivos, pastas e o site**.
4. Desative **Permitir solicitações de acesso** e clique em **Salvar**.

Com essas configurações, a capacidade de membros do grupo de sites compartilharem o site com outros membros ou de não membros solicitarem acesso ao site é desativada.

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a>Etapa 3: Configurar o site para um rótulo de retenção do Office 365

Use as instruções em [Proteger arquivos do SharePoint com rótulos do Office 365 e DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) para:

1. Crie e publique um rótulo de retenção para dados altamente regulamentados (se necessário).
2. Configure o site para o rótulo de retenção criado na etapa 1.
3. Crie uma política DLP para dados altamente regulamentados que usam o rótulo de retenção criado na etapa 2 e impede que os usuários enviem arquivos fora da organização

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a>Etapa 4: Criar um sub-rótulo de confidencialidade do Office 365 para o site

Ao contrário de um rótulo de confidencialidade para dados altamente regulamentados que qualquer pessoa pode aplicar a qualquer arquivo, um site seguro precisa de seu próprio sub-rótulo, para que os arquivos com o sub-rótulo atribuído:

- São criptografadas e a criptografia acompanha o arquivo.
- Contenham permissões personalizadas para que somente os membros do grupo de sites possam abri-lo.

Para atingir esse nível adicional de segurança para os arquivos armazenados no site, você deve configurar um novo rótulo de confidencialidade ou um sub-rótulo do rótulo geral para arquivos altamente regulamentados. Somente os membros do grupo do site poderão vê-lo na lista de sub-rótulos do rótulo altamente regulamentado.

Use as instruções [aqui](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para configurar um rótulo ou um sub-rótulo do rótulo que você está usando para arquivos altamente regulamentados com as seguintes configurações:

- O nome do rótulo ou sub-rótulo contém o nome do site para facilitar a associação ao atribuir o rótulo ou o sub-rótulo a um arquivo.
- A criptografia está ativada.
- O grupo de sites tem permissões de Coautoria.

### <a name="configuration-results"></a>Resultados da configuração

Você configurou o seguinte:

- Configurações de permissão mais restritivas no site do SharePoint
- Um rótulo de retenção do Office 365 atribuído à parte de Documentos do site do SharePoint
- Uma política DLP para o rótulo de retenção do Office 365
- Um rótulo ou sub-rótulo de confidencialidade do Office 365 que os usuários podem aplicar aos arquivos mais confidenciais armazenados no site, que criptografam o arquivo e permitem apenas o acesso de coautor aos membros do grupo de sites de equipe 

Aqui está a configuração resultante que usa um sub-rótulo do rótulo altamente regulamentado.

![Os sites do SharePoint para um cenário de dados altamente regulamentados](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

Aqui está um exemplo de usuário que aplicou o sub-rótulo em um arquivo armazenado no site.

![Os sites do SharePoint para um cenário de dados altamente regulamentados](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a>Fase 3: Gerar adoção do usuário

Um site do SharePoint para dados altamente regulamentados só poderá proteger os dados se for usado de maneira consistente para o armazenamento e o acesso a arquivos confidenciais. Esta é a fase mais difícil porque depende dos usuários de mudar seus hábitos e preferências. 

Por exemplo, os funcionários que estão acostumados a armazenar arquivos confidenciais em unidades USB ou em soluções de armazenamento pessoal baseadas em nuvem agora precisam armazená-los exclusivamente em um site do SharePoint para obter dados altamente regulamentados.

### <a name="step-1-train-your-users"></a>Etapa 1: treinar os usuários

Depois de concluir sua configuração, treine o conjunto de usuários que são membros do site:

- Sobre a importância de usar o novo site para proteger arquivos valiosos e as consequências de um vazamento de dados altamente regulamentados, como ramificações legais, multas regulatórias, ransomware ou perda de vantagem competitiva.
- Como acessar o site e seus arquivos.
- Como criar novos arquivos no site e carregar novos arquivos armazenados localmente.
- Como a política DLP bloqueia o compartilhamento de arquivos externamente por parte do usuário.
- Como rotular os arquivos mais sensíveis com o rótulo ou sub-rótulo do site.
- Como o rótulo ou o sub-rótulo protege um arquivo, mesmo quando vazado do site.

Este treinamento deve incluir exercícios práticos para que os usuários possam experimentar essas operações e os resultados.

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a>Etapa 2: conduzir análises periódicas de utilização e arquivos

Nas semanas após o treinamento, o administrador do SharePoint para o site do SharePoint pode:

- Analisar o uso do site e compará-lo a expectativas de uso.
- Verificar se os arquivos altamente confidenciais foram rotulados corretamente com o rótulo ou o sub-rótulo de confidencialidade.

  Você pode ver quais arquivos têm um rótulo atribuído exibindo uma pasta no SharePoint Online e adicionando a coluna **Confidencialidade**através da opção **Mostrar/ocultar colunas** em **Adicionar coluna**.


Repita o treinamento dos usuários conforme necessário.

### <a name="user-adoption-results"></a>Resultados de adoção do usuário

Arquivos altamente regulamentados são armazenados exclusivamente em sites do SharePoint para dados altamente regulamentados e os arquivos mais confidenciais possuem o rótulo ou sub-rótulo de confidencialidade do site aplicado.

## <a name="how-the-contoso-corporation-used-a-sharepoint-site-for-highly-regulated-data"></a>Como a Contoso Corporation usou um site do SharePoint para dados altamente regulamentados

A Contoso Corporation é um conglomerado de fabricação global fictício, mas representativo. Veja como Contoso projetou, configurou e, em seguida, orientou a adoção de um [site do SharePoint seguro](contoso-sharepoint-online-site-for-highly-confidential-assets.md) para suas equipes de pesquisa em Paris, Moscou, Nova York, Pequim e Bengaluru (Bangalore). 

## <a name="see-also"></a>Confira também

[Microsoft Teams para dados altamente regulamentados](secure-teams-highly-regulated-data-scenario.md)

[Cargas de trabalho e cenários do Microsoft 365 Enterprise](deploy-workloads.md)

[Biblioteca de produtividade do Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)

[Guia de implantação](deploy-microsoft-365-enterprise.md)
