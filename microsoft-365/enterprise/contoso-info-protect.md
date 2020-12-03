---
title: Proteção de Informações da Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda como a contoso usa os recursos de proteção de informações no Microsoft 365 for Enterprise para proteger seus ativos digitais na nuvem.
ms.openlocfilehash: 7cc51110a0bc4c87e57e71b2ddb42aa0dbaa288d
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558499"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Proteção de Informações da Contoso Corporation

A contoso é uma séria sobre a segurança de suas informações. Vazamento ou destruição de propriedade intelectual que descreve seus designs de produto e técnicas de fabricação proprietária as colocam em uma desvantagem competitiva.

Antes de mover seus ativos digitais confidenciais para a nuvem, a contoso tomou a certeza de que seus requisitos de proteção e classificação de informações no local foram suportados pelos serviços baseados em nuvem do Microsoft 365 para empresas.

## <a name="contoso-data-security-classification"></a>Classificação de segurança de dados da contoso

A contoso realizou uma análise de seus dados e determinou os seguintes níveis de classificação.

| Nível 1: linha de base | Nível 2: Confidencial | Nível 3: altamente controlado |
|:-------|:-----|:-----|
| Os dados são criptografados e estão disponíveis somente para usuários autenticados.<BR> <BR> Fornecido para todos os dados armazenados no local e em armazenamento baseado em nuvem e cargas de trabalho. Os dados são criptografados enquanto residem no serviço e em trânsito entre os dispositivos de cliente e serviço. <BR><BR>Exemplos de dados de Nível 1 são comunicações de negócios normais (email) e arquivos para trabalhadores administrativos, de vendas e de suporte. | Nível 1 mais autenticação forte e proteção contra perda de dados.<BR> <BR> A autenticação forte inclui a MFA (autenticação multifator) do Azure AD com a validação do SMS. A prevenção contra perda de dados garante que as informações confidenciais ou críticas não trafegam fora da nuvem da Microsoft.<BR><BR>Exemplos de dados de Nível 2 são informações financeiras e legais e dados de pesquisa e desenvolvimento para novos produtos. | Nível 2 mais os níveis mais altos de criptografia, autenticação e auditoria.<BR><BR>Os níveis mais altos de criptografia de dados em repouso e na nuvem, em conformidade com os regulamentos regionais, combinados a MFA com cartões inteligentes, auditoria e alerta granulares.<BR> <BR>Exemplos de dados de nível 3 são informações pessoais de cliente e de parceiro, especificações de engenharia de produto e técnicas de fabricação proprietárias.  |
||||

## <a name="contoso-information-policies"></a>Políticas de informações da contoso
A tabela a seguir lista as políticas de informações da contoso.


| Valor | Acesso | Retenção de dados | Proteção de informações |
|:-------|:-----|:-----|:-----|
| Baixo valor de negócios (Nível 1: Linha de base) | Permitir acesso a todos.  | 6 meses | Usar criptografia. |
| Valor médio de negócios (Nível 2: Confidencial) | Permitir acesso a funcionários, subcontratados e parceiros da contoso. <BR><BR> Usar a MFA, o Protocolo TLS e o Gerenciamento de Aplicativos Móveis (MAM) | 2 anos  | Usar valores de hash para integridade de dados.  |
| Alto valor de negócios (Nível 3: altamente controlado) | Permitir acesso aos executivos e clientes potenciais em engenharia e fabricação. <BR> <BR> Rights Management System (RMS) somente com dispositivos de rede gerenciados.  | 7 anos  | Usar assinaturas digitais para não repúdio.  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a>O caminho da Contoso para a proteção de informações com o Microsoft 365 para empresas

A contoso seguiu estas etapas para preparar o Microsoft 365 for Enterprise para seus requisitos de proteção de informações:

1. Identificar quais informações proteger

   A contoso realizou uma ampla análise de seus ativos digitais existentes localizados em sites e compartilhamentos de arquivos locais do SharePoint e classificou cada ativo.

2. Determinar políticas de acesso, retenção e proteção de informações para níveis de dados

   Com base nos níveis de dados, a Contoso determinou requisitos de política detalhados, que foram usados para proteger ativos digitais existentes quando eles foram movidos para a nuvem.

3. Criar rótulos de sensibilidade e suas configurações para os diferentes níveis de informações

   A Contoso criou rótulos de confidencialidade para seus níveis de dados, com rótulos altamente regulamentados incluindo criptografia, permissões e marcas d'água.

4.  Mover dados de sites e compartilhamentos de arquivos locais do SharePoint para seus novos sites do SharePoint

    Os arquivos migrados para os novos sites do SharePoint herdaram os rótulos de retenção padrão atribuídos ao site.

5.  Treinar funcionários como usar rótulos de confidencialidade para novos documentos, como interagir com a contoso ao criar novos sites do SharePoint e sempre armazenar ativos digitais em sites do SharePoint

    Alterar informações incorretas do trabalhador-os hábitos de armazenamento costumam ser considerados a parte mais difícil da transição de proteção de informações para a nuvem. A ti e o gerenciamento da Contoso necessários para que os funcionários sempre rotulem e armazenem seus ativos digitais na nuvem, evite usar compartilhamentos de arquivos locais e não usar serviços de armazenamento em nuvem de terceiros ou unidades USB.

## <a name="conditional-access-policies-for-information-protection"></a>Políticas de Acesso Condicional para proteção de informações

Como parte de sua distribuição do Exchange Online e do SharePoint, a contoso configurou o seguinte conjunto de políticas de acesso condicional e as aplicou aos grupos apropriados:

- [Acesso de aplicativo gerenciados e não gerenciado e políticas de dispositivos](../security/office-365-security/identity-access-policies.md)
- [Políticas de acesso do Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)
- [Políticas de acesso do SharePoint](../security/office-365-security/sharepoint-file-access-policies.md)

Veja a seguir o conjunto resultante de políticas da Contoso para proteção de informações.

![Políticas de Acesso Condicional do Dispositivo, do Exchange Online e do SharePoint ](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>A Contoso também configurou políticas de Acesso condicional adicionais para identidade e entrada.  Confira, [Identidade da Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).
>

Essas políticas garantem que:

- Os aplicativos que são permitidos e as ações que eles podem executar com os dados da organização são definidos pelas políticas de proteção de aplicativos.
- PCs e dispositivos móveis devem estar compatíveis.
- O Exchange Online usa a criptografia de mensagem do Office 365 (OME) para o Exchange Online.
- O SharePoint usa restrições impostas por aplicativo.
- O SharePoint usa políticas de controle de acesso para acesso somente por navegador e para bloquear o acesso de dispositivos não gerenciados.

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a>Mapeando o Microsoft 365 para recursos corporativos para níveis de dados da contoso

A tabela a seguir mapeia os níveis de dados da Contoso para recursos de proteção de informações no Microsoft 365 para empresas.

| Nível | Serviços em nuvem da Microsoft 365 | Aplicativos do Windows 10 e do Microsoft 365 para empresas | Segurança e conformidade |
|:-------|:-----|:-----|:-----|
| Nível 1: linha de base  | Políticas de Acesso Condicional do SharePoint e do Exchange Online <BR> Permissões em sites do SharePoint  | Rótulos de confidencialidade <BR> BitLocker <BR> Proteção de Informações do Windows | Políticas de Acesso Condicional de Dispositivos e políticas de Gerenciamento de Aplicativos Móveis |
| Nível 2: Confidencial | Nível 1 mais: <BR> <BR> Rótulos de confidencialidade <BR> Rótulos de retenção do Microsoft 365 em sites do SharePoint <BR> Prevenção contra perda de dados do SharePoint Online e do Exchange Online <BR> Sites isolados do SharePoint   | Nível 1 mais: <BR> <BR> Rótulos de confidencialidade em ativos digitais  | Nível 1 |
| Nível 3: altamente controlado | Nível 2 mais: <BR><BR> Traga sua chave (BYOK) criptografia e proteção para informações de segredo comercial <BR> Azure Key Vault para aplicativos de linha de negócios que interagem com os serviços do Microsoft 365 | Nível 2 | Nível 1 |
|||||

Aqui está a configuração resultante da proteção de informações da contoso.

![Configurações resultantes da proteção de informações da Contoso](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>Próxima etapa

Saiba como a contoso usa os [recursos de segurança da Microsoft 365 para empresas](contoso-security-summary.md) para gerenciamento de identidade e acesso, proteção contra ameaças, proteção de informações e gerenciamento de segurança.

## <a name="see-also"></a>Confira também

[Roteiro de segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)
