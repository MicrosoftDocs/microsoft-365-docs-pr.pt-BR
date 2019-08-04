---
title: Proteção de Informações da Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda como a Contoso usa recursos de proteção de informações no Microsoft 365 Enterprise para proteger seus ativos digitais na nuvem.
ms.openlocfilehash: c11636d6fcdb1de634988e85238ce39a703d520d
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074071"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Proteção de Informações da Contoso Corporation

**Resumo:** entenda como a Contoso usa recursos de proteção de informações no Microsoft 365 Enterprise para proteger seus ativos digitais na nuvem.

A Contoso se preocupa com sua segurança e proteção de informações. Por exemplo, o vazamento ou a destruição de sua propriedade intelectual que descreve projetos de produtos e técnicas patenteadas de fabricação, colocaria você em desvantagem competitiva.

Antes de migrar seus ativos digitais mais importantes e confidenciais para a nuvem, eles verificaram se seus requisitos de classificação e proteção de informações no local eram compatíveis e implementados nos serviços baseados em nuvem do Microsoft 365 Enterprise.

## <a name="contosos-data-security-classification"></a>Classificação de segurança de dados da Contoso

A Contoso realizou uma análise de seus dados e determinou os níveis a seguir.

||||
|:-------|:-----|:-----|
| **Nível 1: linha de base** | **Nível 2: confidencial** | **Nível 3: altamente controlado** |
| Os dados são criptografados e estão disponíveis somente para usuários autenticados <BR> <BR> Fornecido para todos os dados armazenados localmente e em armazenamento e cargas de trabalho baseados em nuvem, como o Office 365. Os dados são criptografados enquanto estão no serviço e em trânsito entre o serviço e os dispositivos do cliente. <BR><BR> Exemplos de dados de Nível 1 são comunicações de negócios normais (email) e arquivos para trabalhadores administrativos, de vendas e de suporte. | Nível 1 mais autenticação forte e proteção contra perda de dados: <BR> <BR> A autenticação forte inclui autenticação multifator com validação de SMS. A prevenção de perda de dados garante que informações confidenciais ou críticas não trafeguem fora da rede local. <BR><BR> Exemplos de dados de Nível 2 são informações financeiras e legais e dados de pesquisa e desenvolvimento para novos produtos. | Nível 2 mais os níveis mais altos de criptografia, autenticação e auditoria. <BR> <BR>  Os níveis mais altos de criptografia de dados em repouso e na nuvem, de modo compatível com os regulamentos regionais, combinados com autenticação multifator com cartões inteligentes e auditoria e alertas granulares. <BR> <BR> Exemplos de dados de Nível 3 são informações de identificação pessoal do cliente e do parceiro, especificações de engenharia de produto e técnicas de fabricação proprietárias.  |
||||

## <a name="contosos-information-policies"></a>Políticas de informações da Contoso
As tabela a seguir lista as políticas de informações da Contoso.

|||||
|:-------|:-----|:-----|:-----|
|  | **Acesso** | **Retenção de dados** | **Proteção de informações** |
| Baixo valor de negócios (Nível 1: Linha de base) | Permitir acesso a todos  | Seis meses | Usar criptografia |
| Valor médio de negócios (Nível 2: Confidencial) | Permitir acesso a funcionários, fornecedores e parceiros da Contoso <BR> <BR> Usar a MFA (autenticação multifator), protocolo TLS e o Gerenciamento de Aplicativos Móveis (MAM) | Dois anos  | Usar valores de hash para integridade de dados  |
| Alto valor de negócios (Nível 3: Altamente controlado) | Permitir acesso aos executivos e clientes potenciais em engenharia e fabricação <BR> <BR> Rights Management System (RMS) com dispositivos de rede gerenciados somente  | Sete anos  | Usar assinaturas digitais para não repúdio  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-enterprise"></a>Caminho da Contoso para a proteção de informações com o Microsoft 365 Enterprise

A Contoso usou as seguintes etapas para preparar o Microsoft 365 Enterprise para os requisitos de proteção de informações:

1. Identificou quais informações deveria proteger

   A Contoso realizou uma extensa revisão de seus ativos digitais existentes localizados em sites e compartilhamentos de arquivos locais do SharePoint e classificou cada um deles.

2. Determinou políticas de acesso, de retenção e de proteção de informações para níveis de dados

   Com base nos níveis de dados, a Contoso determinou requisitos de política detalhados, que foram usados para proteger ativos digitais existentes quando eles foram movidos para a nuvem.

3. Criou rótulos de confidencialidade e suas configurações para os diferentes níveis de informações

   A Contoso criou rótulos de confidencialidade para seus níveis de dados, com rótulos confidenciais e altamente controlados incluindo criptografia, permissões e marcas d'água.

4. Criou sites protegidos do SharePoint Online para dados confidenciais e altamente controlados com permissões que bloqueiam o acesso

   Os sites confidenciais e altamente controlados foram configurados como [sites isolados](https://docs.microsoft.com/office365/enterprise/isolated-sharepoint-online-team-sites), nos quais as permissões padrão do site de equipe do SharePoint Online foram personalizadas para os grupos do Azure Active Directory (Azure AD). Os sites confidenciais e altamente controlados do SharePoint Online também foram configurados com um rótulo de retenção correspondente. Os arquivos armazenados em sites altamente controlados do SharePoint Online são protegidos com o rótulo de confidencialidade Altamente Controlado. Para saber mais, confira o cenário de [sites do Microsoft Teams e SharePoint Online para dados altamente controlados](teams-sharepoint-online-sites-highly-regulated-data.md).

5.  Moveu dados de sites do SharePoint e compartilhamentos de arquivos locais para seus novos sites do SharePoint Online

    Os arquivos migrados para os novos sites do SharePoint Online herdaram os rótulos de retenção padrão atribuídos ao site.

6.  Treinou funcionários para usar os rótulos de confidencialidade para novos documentos, como interagir com a TI da Contoso ao criar novos sites do SharePoint Online e sempre armazenar ativos digitais em sites do SharePoint Online.

    Considerou a parte mais difícil da transição da proteção de informações para a nuvem. Era necessário que a TI e o gerenciamento da Contoso mudasse os maus hábitos de armazenamento de informações dos funcionários da organização para sempre armazenar e rotular seus ativos digitais e nunca usar serviços de armazenamento em nuvem de terceiros ou unidades USB.

## <a name="conditional-access-policies-for-information-protection"></a>Políticas de acesso condicional para proteção de informações

Juntamente com sua infraestrutura de gerenciamento de identidade e dispositivo móvel e como parte de sua implementação do Exchange Online e do SharePoint Online, a Contoso configurou o seguinte conjunto de políticas de acesso condicional e as aplicou aos grupos apropriados do Azure AD:

- [Acesso de aplicativo gerenciados e não gerenciado e políticas de dispositivos](identity-access-policies.md)
- [Políticas de acesso do Exchange Online](secure-email-recommended-policies.md)
- [Políticas de acesso do SharePoint Online](sharepoint-file-access-policies.md)

A Figura 1 mostra um conjunto de políticas resultantes da proteção de informações da Contoso.

![](./media/contoso-info-protect/contoso-info-protect-fig1.png)

**Figura 1: Políticas de acesso condicional do dispositivo, Exchange Online e SharePoint Online**
 
>[!Note]
>A Contoso também configurou políticas de acesso condicional adicionais para identidade e entrada. Confira [Identidade para a Contoso Corporation](contoso-identity.md).
>

Essas políticas garantem que:

- Os aplicativos sejam permitidos e as ações que eles podem realizar sejam definidas por políticas de proteção de aplicativo.
- PCs e dispositivos móveis devem estar compatíveis.
- O Exchange Online utilize a criptografia de mensagem do Office 365 para o Exchange Online.
- O SharePoint Online use restrições impostas pelo aplicativo.
- O SharePoint Online use políticas de controle de acesso para acesso somente por navegador e para bloquear o acesso de dispositivos não gerenciados.

## <a name="mapping-microsoft-365-enterprise-features-to-contosos-data-levels"></a>Mapear recursos do Microsoft 365 Enterprise para os níveis de dados da Contoso

A tabela a seguir mostra o mapeamento dos níveis de dados da Contoso para os recursos de proteção de informações no Microsoft 365 Enterprise.

|||||
|:-------|:-----|:-----|:-----|
| | **Office 365** | **Windows 10 e Office 365 ProPlus** | **EMS** |
| Nível 1: linha de base  | Políticas de acesso condicional do SharePoint Online e Exchange Online <BR> Permissões em sites do SharePoint Online | Rótulos de confidencialidade <BR> BitLocker <BR> Proteção de Informações do Windows | Políticas de acesso condicional de dispositivos e políticas de Gerenciamento de Aplicativos Móveis |
| Nível 2: Confidencial | Nível 1 mais: <BR> <BR> Rótulos de confidencialidade <BR> Rótulos do Office 365 em sites do SharePoint Online <BR> Prevenção contra perda de dados do Office 365 para for SharePoint Online e Exchange Online <BR> Sites isolados do SharePoint Online  | Nível 1 mais: <BR> <BR> Rótulos de confidencialidade em ativos digitais <BR> Gestão de Dados Avançada do Office 365 | Nível 1 |
| Nível 3: altamente controlado | Nível 2 mais: <BR><BR> Criptografia BYOK (Traga sua própria chave) e proteção de informações de segredos comerciais <BR> Azure Key Vault para aplicativos de linha de negócios que interagem com os serviços do Office 365 | Nível 2 | Nível 1 |
|||||


## <a name="next-step"></a>Próxima etapa

[Veja](contoso-security-summary.md) como a Contoso usa os recursos de segurança do Microsoft 365 Enterprise para identidade e gerenciamento de acesso, proteção contra ameaças, proteção de informações e gerenciamento de segurança.

## <a name="see-also"></a>Confira também

[Proteção de Informações para o Microsoft 365 Enterprise](infoprotect-infrastructure.md)

[Guia de implantação](deploy-microsoft-365-enterprise.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)


