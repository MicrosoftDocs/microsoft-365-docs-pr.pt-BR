---
title: Sites do Microsoft Teams e do SharePoint Online para dados altamente controlados
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/03/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Crie um site de equipe seguro do SharePoint Online um uma equipe do Microsoft Teams para armazenar seus ativos digitais mais importantes e confidenciais.
ms.openlocfilehash: 1243a88e6553b1d58370a60b5e2fec38d3dbcaf6
ms.sourcegitcommit: 681ae93ca1d07532944665cf5d99ff1f08c0b46a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2019
ms.locfileid: "37210047"
---
# <a name="microsoft-teams-and-sharepoint-online-sites-for-highly-regulated-data"></a>Sites do Microsoft Teams e do SharePoint Online para dados altamente controlados

*Este cenário aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*

O Microsoft 365 Enterprise inclui um conjunto completo de serviços em nuvem para que você possa criar, armazenar e proteger seus dados altamente regulados. Isso inclui os dados:

- Sujeitos a regulamentações regionais.
- Mais importantes de sua organização, como segredos comerciais, financeiros ou informações de recursos humanos e estratégias da organização.

Um cenário da Microsoft 365 Enterprise baseada na nuvem, que atende a essa necessidade comercial, requer que você:

- Armazene ativos digitais (documentos, apresentações de slides, planilhas etc.) em um site de equipe do SharePoint Online ou na guia **Arquivos** de uma equipe Microsoft Teams.
- Bloqueie o site ou a equipe para impedir:
   - O acesso a apenas um conjunto específico de contas de usuário por meio de associações de grupo, que inclui aqueles que podem acessar o site de equipe do SharePoint Online, qual o nível de permissão e quem pode administrá-lo.
   - Que membros do site concedam acesso a outras pessoas.
   - Que aqueles que não sejam membros do site solicitem acesso a ele.
- Configurar um rótulo de retenção do Office 365 para seus sites ou equipes do SharePoint Online como uma maneira padrão de definir políticas de retenção nos documentos no site ou na equipe.
- Impedir usuários de enviar arquivos para fora da organização.
- Criptografe os ativos digitais mais importantes do site ou da equipe.
- Adicione permissões aos ativos digitais mais importantes para que, mesmo que sejam compartilhados fora do site, só seja possível abri-lo com as credenciais válidas de uma conta de usuário que tenha a permissão.

A tabela a seguir mapeia os requisitos desse cenário para um recurso do Microsoft 365 Enterprise.

|||
|:-------|:-----|
| **Requisito** | **Recurso do Microsoft 365 Enterprise** |
| Armazenar ativos digitais | Sites e equipes do SharePoint Online no Office 365 |
| Bloquear o site | Permissões do site de equipe do SharePoint Online e grupos do Azure AD |
| Rotular os ativos digitais do site | Rótulos de retenção do Office 365 |
| Bloquear usuários ao enviar arquivos para fora da organização. | Políticas de Prevenção Contra Perda de Dados (DLP) no Office 365 |
| Criptografar todos os ativos digitais do site | Sub-rótulos de Proteção de Informações do Azure no Enterprise Mobility + Security (EMS) |
| Adicionar permissões aos ativos digitais do site | Sub-rótulos da Proteção de Informações do Azure no EMS |
|||

Estas são as configurações para um site do SharePoint Online.

![Sites do Microsoft Teams e do SharePoint Online para um cenário de dados altamente regulado](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

Este cenário exige que você já tenha implantado:

- A fase de [identidade](identity-infrastructure.md) e as etapas 1 e 2 da fase de [proteção de informações](infoprotect-infrastructure.md) da infraestrutura de base. 
- Para dados altamente regulados nos sites de equipe do SharePoint Online, o [SharePoint Online](sharepoint-online-onedrive-workload.md).
- Para dados altamente regulados nas equipes do Microsoft Teams, o [Microsoft Teams](teams-workload.md).

As fases a seguir orientam você quanto ao design, à configuração e à geração de adoção dos sites e equipes do SharePoint Online para dados altamente regulados.

Para ver como a Contoso Corporation, uma organização multinacional fictícia representativa, projetou um site do SharePoint Online para suas equipes de pesquisa, consulte esta [configuração de exemplo](contoso-sharepoint-online-site-for-highly-confidential-assets.md).

Uma equipe para dados altamente regulados requer que você primeiro crie um site de equipe do SharePoint Online para dados altamente regulados. Em seguida, você cria uma nova equipe que usa o grupo do Office 365 do site de equipe do SharePoint Online. Consulte a Fase 2, Etapa 4 para obter mais informações.

Estas são as configurações para uma equipe.

![Sites do Microsoft Teams e do SharePoint Online para um cenário de dados altamente regulado](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-team.png)


## <a name="identity-and-device-access-prerequisites"></a>Pré-requisitos de acesso ao dispositivo e identidade

Para proteger o acesso à equipe ou ao site do SharePoint Online, assegure-se de ter configurado [políticas de identidade e de acesso ao dispositivo](identity-access-policies.md) e as [políticas de acesso recomendadas do SharePoint Online](sharepoint-file-access-policies.md).

## <a name="phase-1-design"></a>Fase 1: Design

Para criar um site ou uma equipe do SharePoint Online para dados altamente regulados, primeiro você precisa identificar a finalidade dele. Por exemplo, o departamento de pesquisa e desenvolvimento e uma organização de manufatura precisa de um site do SharePoint Online para armazenar especificações atuais de design de produtos existentes e um local para colaborar em novos produtos. Apenas os membros do departamento de Pesquisa e Desenvolvimento e determinados executivos poderão acessar o site.

Essa finalidade gerará a determinação de itens essenciais de configuração como:

- O conjunto de grupos do SharePoint e os conjuntos de permissão do SharePoint Online
- O conjunto de grupos de acesso, grupos de segurança do Azure AD e seus membros para adicionar aos grupos do SharePoint
- O rótulo de retenção do Office 365 a ser atribuído ao site e o conjunto de políticas DLP para o rótulo
- As configurações do sub-rótulo de Proteção de Informações do Azure que os usuários aplicam a ativos digitais altamente confidenciais armazenados no site

Quando determinado, você usa essas configurações para configurar o site na Fase 2. 

### <a name="step-1-an-isolated-sharepoint-online-site"></a>Etapa 1: Um site isolado do SharePoint Online

A versão bloqueada de um site de equipe do SharePoint Online é conhecida como um site isolado. Ao contrário das configurações padrão de sites de equipe privados, sites isolados são configurados para evitar:

- O acesso daqueles que não são membros de grupos especificados.
- A solicitação de acesso.
- A concessão não autorizada de acesso por membros atuais de grupos especificados.
- Administração do site pelos membros de grupo de acesso.

A segurança dos sites de equipe do SharePoint Online que contêm ativos altamente regulados não muda, a não ser que seja alterada por um administrador do SharePoint para o site.

Consulte [Projetar um site de equipe isolado do SharePoint Online](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site) para obter detalhes para determinar o conjunto de níveis de permissão, grupos do SharePoint, grupos de acesso e membros do grupo.

### <a name="step-2-office-365-retention-labels-and-dlp-policies"></a>Etapa 2: rótulos de retenção do Office 365 e políticas DLP

Quando aplicados a um site de equipe do SharePoint Online, os rótulos de retenção do Office 365 oferecem um método padrão para classificar todos os ativos digitais armazenados no site.
 
Nos sites do SharePoint Online para dados altamente controlados, você precisa determinar qual rótulo de retenção do Office 365 será usado.

Para considerações de design dos rótulos do Office 365, consulte [Rótulos e classificação do Office 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).

Para proteger informações confidenciais e evitar a divulgação acidental ou intencional, use as políticas DLP. Para obter mais informações, consulte esta [visão geral](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).

Para sites do SharePoint para dados altamente controlados, você deve configurar uma política DLP do rótulo de retenção do Office 365 atribuído ao site para bloquear usuários quando eles tentam compartilhar ativos digitais com usuários externos. 

### <a name="step-3-your-azure-information-protection-sub-label"></a>Etapa 3: seu sub-rótulo de Proteção de Informações do Azure

Para fornecer um conjunto de permissões e a criptografia para seus ativos digitais mais importantes, os usuários devem aplicar um rótulo de Proteção de Informações do Azure usando o cliente de Proteção de Informações do Azure. Para usar rótulos de Proteção de Informações do Azure em sites do SharePoint Online para dados altamente regulamentados, você deve configurar um sub-rótulo de Proteção de Informações do Azure em uma política com escopo. 

Um sub-rótulo existe em um rótulo existente. Por exemplo, você pode criar um sub-rótulo Pesquisa e Desenvolvimento no rótulo Altamente Confidencial. Uma política com escopo é uma que se aplica apenas a um subconjunto de usuários. Nos sites do SharePoint Online para dados altamente regulamentados, o escopo é o conjunto de usuários que são membros dos grupos de acesso do site.

As configurações do sub-rótulo aplicado acompanham o ativo. Mesmo que ele seja baixado e compartilhado fora do site, apenas as contas de usuário autenticadas com permissões poderão abri-lo.

### <a name="design-results"></a>Resultados de design

Você determinou o seguinte:

- O conjunto de grupos e níveis de permissão do SharePoint
- O conjunto de grupos de acesso e os membros deles em cada nível de permissão
- O rótulo de retenção apropriado do Office 365 e a política DLP que está associada ao rótulo
- As configurações do sub-rótulo Proteção de Informações do Azure que incluem criptografia e permissões

## <a name="phase-2-configure"></a>Fase 2: Configurar

Nesta fase, você usa as configurações determinadas na Fase 1 e as implementa para criar um site do SharePoint Online para dados altamente regulamentados.

### <a name="step-1-create-and-configure-an-isolated-sharepoint-online-team-site"></a>Etapa 1: criar e configurar um site de equipe do SharePoint Online isolado

Use as instruções em [Implantar um site de equipe do SharePoint Online isolado](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site) para:

- Crie e preencha os grupos de acesso para cada nível de permissão do SharePoint usado no site.
- Crie e configure o site de equipe isolado.

### <a name="step-2-configure-the-site-for-an-office-365-retention-label"></a>Etapa 2: configurar o site para um rótulo de retenção do Office 365

Use as instruções em [Proteger arquivos do SharePoint Online com DLP e rótulos do Office 365](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) para:

- Identificar ou criar o rótulo de retenção do Office 365 e aplicá-lo ao seu site isolado do SharePoint Online.
- Crie e configure a política DLP que bloqueia os usuários quando eles tentam compartilhar um ativo digital em seu site do SharePoint Online fora da organização.

### <a name="step-3-create-an-azure-information-protection-sub-label-for-the-site"></a>Etapa 3: criar um sub-rótulo de Proteção de Informações do Azure no site

Use as instruções em [Proteger arquivos do SharePoint Online com Proteção de Informações do Azure](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection) para: 

- Crie e configure um sub-rótulo Proteção de Informações do Azure em uma política com escopo.
- Implante do cliente de Proteção de Informações do Azure nos computadores de usuário.

### <a name="step-4-optional-create-a-team-for-the-highly-regulated-data"></a>Etapa 4 (opcional): criar e configurar uma equipe para dados altamente regulamentados

Se desejar uma equipe para dados altamente regulamentados, você primeiro cria um site do SharePoint Online para dados altamente regulamentados. Quando cria o site de equipe privado inicial do SharePoint Online, você especifica um nome de grupo do Office 365.

Depois que o site do SharePoint Online altamente regulamentado estiver configurado, use estas etapas para convertê-lo em uma equipe para dados altamente regulamentados:

1. Entrar no Office 365.
2. Na guia **Microsoft Office Home**, clique em **Teams**.
3. Na guia **Microsoft Teams**, no painel **Ingressar ou criar uma equipe**, clique em **Criar equipe**.
4. No painel **Criar sua equipe**, clique em **Criar uma equipe de um grupo existente do Office 365**.
5. Na lista dos grupos do Office 365, selecione o nome do grupo do Office 365 que corresponde ao site do SharePoint Online para dados altamente regulamentados e clique em **Escolher equipe**.

A guia **Arquivos** da nova equipe lista o conteúdo da pasta **Geral** da área **Documentos** do site do SharePoint Online correspondente. Para ver o resto dos recursos do site do SharePoint Online da equipe, clique nas reticências e clique em **Abrir no SharePoint**.

### <a name="configuration-results"></a>Resultados da configuração

Você configurou o seguinte:

- Um site isolado do SharePoint Online
- Um rótulo de retenção do Office 365 atribuído ao site isolado do SharePoint Online
- Uma política DLP para o rótulo de retenção do Office 365
- Um sub-rótulo de Proteção de Informações do Azure de uma política com escopo que os usuários podem aplicar aos ativos digitais mais confidenciais armazenados no site e aplica as permissões
- Se necessário, uma equipe de dados altamente regulamentados com base no site do SharePoint Online

## <a name="phase-3-drive-user-adoption"></a>Fase 3: Gerar adoção do usuário

Um site ou uma equipe do SharePoint Online para dados altamente regulamentados podem proteger os dados apenas se eles sejam constantemente usados para armazenamento e acesso dos ativos digitais confidenciais. Essa é a fase mais difícil, já que ela depende da mudança de comportamento dos usuários. 

Por exemplo, os executivos que estão acostumados a armazenar arquivos confidenciais em unidades USB ou em soluções de armazenamento pessoais na nuvem agora os armazenarão exclusivamente em um site ou equipe do SharePoint Online para dados altamente regulamentados.

### <a name="step-1-train-your-users"></a>Etapa 1: Treinar os usuários

Depois de concluir a configuração, treine o conjunto de usuários que são membros dos grupos de acesso do site:

- Sobre a importância de usar o novo site ou equipe para proteger ativos importantes e as consequências de um vazamento de dados altamente regulamentados, como ramificações legais, multas regulamentares, ransomware ou perda de vantagem competitiva.
- Como acessar o site e os ativos dele.
- Como criar novos arquivos no site e carregar novos arquivos armazenados localmente.
- Como a política DLP bloqueia o compartilhamento de arquivos externamente por parte do usuário.
- Como usar o cliente de Proteção de Informações do Azure para rotular os ativos digitais mais confidenciais com o sub-rótulo configurado.
- Como o sub-rótulo de Proteção de Informações do Azure protege um ativo mesmo quando ele vaza para fora do site ou da equipe.

Este treinamento deve incluir exercícios práticos para que os usuários possam experimentar essas operações e os resultados.

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a>Etapa 2: conduzir análises periódicas de utilização e arquivos

Nas semanas após o treinamento, o administrador do SharePoint do site ou da equipe do SharePoint Online pode:

- Analise a utilização do site ou da equipe e comparar com as expectativas de utilização.
- Verifique se os arquivos altamente confidenciais foram rotulados corretamente com o sub-rótulo Proteção de Informações do Azure.

Repita o treinamento dos usuários conforme necessário.

### <a name="user-adoption-results"></a>Resultados de adoção do usuário

Ativos digitais confidenciais são armazenados exclusivamente nos sites ou equipes do SharePoint Online para dados altamente regulamentados e os ativos mais importantes têm o sub-rótulo de Proteção de Informações do Azure aplicado.

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a>Como a Contoso Corporation implantou o Microsoft 365 Enterprise

Contoso Corporation é uma corporação fictícia mas representante global do conglomerado de produção com sede em Paris, França. Veja como Contoso projetou, configurou e, em seguida adotou a um [site seguro do SharePoint Online site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) para suas equipes de pesquisa em Paris, Moscou, Nova York, Pequim e Bengaluru (Bangalore). 

## <a name="see-also"></a>Confira também

[Guia de implantação](deploy-microsoft-365-enterprise.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)

[Proteger os sites do SharePoint Online em um ambiente de desenvolvimento/teste](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-in-a-dev-test-environment)
