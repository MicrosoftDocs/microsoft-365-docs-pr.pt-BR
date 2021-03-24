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
description: Entenda como a Contoso usa os recursos de proteção de informações no Microsoft 365 para empresas para proteger seus ativos digitais na nuvem.
ms.openlocfilehash: 3bd778708e30253e53cc465e89f7b783141771de
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051491"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Proteção de Informações da Contoso Corporation

A Contoso está falando sério sobre a segurança das informações. Vazamento ou destruição de propriedade intelectual que descreve seus designs de produtos e técnicas de fabricação proprietárias os colocaria em desvantagem competitiva.

Antes de mover seus ativos digitais confidenciais para a nuvem, a Contoso se certificava de que seus requisitos de classificação e proteção de informações locais eram suportados pelos serviços baseados em nuvem do Microsoft 365 para empresas.

## <a name="contoso-data-security-classification"></a>Classificação de segurança de dados da Contoso

A Contoso realizou uma análise de seus dados e determinou os seguintes níveis de classificação.

| Nível 1: linha de base | Nível 2: Confidencial | Nível 3: altamente controlado |
|:-------|:-----|:-----|
| Os dados são criptografados e estão disponíveis somente para usuários autenticados.<BR> <BR> Fornecido para todos os dados armazenados no local e em cargas de trabalho e armazenamento baseados em nuvem. Os dados são criptografados enquanto residem no serviço e em trânsito entre o serviço e os dispositivos cliente. <BR><BR>Exemplos de dados de Nível 1 são comunicações de negócios normais (email) e arquivos para trabalhadores administrativos, de vendas e de suporte. | Nível 1 mais autenticação forte e proteção contra perda de dados.<BR> <BR> A autenticação forte inclui Azure AD Multi-Factor Authentication (MFA) com validação SMS. A prevenção contra perda de dados garante que informações confidenciais ou críticas não estejam fora da nuvem da Microsoft.<BR><BR>Exemplos de dados de Nível 2 são informações financeiras e legais e dados de pesquisa e desenvolvimento para novos produtos. | Nível 2 mais os níveis mais altos de criptografia, autenticação e auditoria.<BR><BR>Os níveis mais altos de criptografia de dados em repouso e na nuvem, em conformidade com os regulamentos regionais, combinados a MFA com cartões inteligentes, auditoria e alerta granulares.<BR> <BR>Exemplos de dados de Nível 3 são informações pessoais do cliente e do parceiro, especificações de engenharia de produto e técnicas de manufatura proprietárias.  |
||||

## <a name="contoso-information-policies"></a>Políticas de informações da Contoso
A tabela a seguir lista as políticas de informações da Contoso.


| Valor | Access | Retenção de dados | Proteção de informações |
|:-------|:-----|:-----|:-----|
| Baixo valor de negócios (Nível 1: Linha de base) | Permitir acesso a todos.  | 6 meses | Usar criptografia. |
| Valor médio de negócios (Nível 2: Confidencial) | Permitir acesso a funcionários, subcontratados e parceiros da Contoso. <BR><BR> Usar a MFA, o Protocolo TLS e o Gerenciamento de Aplicativos Móveis (MAM) | 2 anos  | Usar valores de hash para integridade de dados.  |
| Alto valor de negócios (Nível 3: altamente controlado) | Permitir acesso aos executivos e clientes potenciais em engenharia e fabricação. <BR> <BR> Rights Management System (RMS) somente com dispositivos de rede gerenciados.  | 7 anos  | Usar assinaturas digitais para não repúdio.  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a>O caminho da Contoso para a proteção de informações com o Microsoft 365 para empresas

A Contoso seguiu estas etapas para preparar o Microsoft 365 para empresas para seus requisitos de proteção de informações:

1. Identificar quais informações proteger

   A Contoso fez uma revisão extensiva de seus ativos digitais existentes localizados em sites e compartilhamentos de arquivos do SharePoint local e classificou cada ativo.

2. Determinar políticas de acesso, retenção e proteção de informações para níveis de dados

   Com base nos níveis de dados, a Contoso determinou requisitos de política detalhados, que foram usados para proteger ativos digitais existentes quando eles foram movidos para a nuvem.

3. Criar rótulos de sensibilidade e suas configurações para os diferentes níveis de informações

   A Contoso criou rótulos de confidencialidade para seus níveis de dados, com rótulos altamente regulamentados incluindo criptografia, permissões e marcas d'água.

4.  Mover dados de sites locais e compartilhamentos de arquivos do SharePoint para seus novos sites do SharePoint

    Os arquivos migrados para os novos sites do SharePoint herdaram os rótulos de retenção padrão atribuídos ao site.

5.  Treinar funcionários como usar rótulos de sensibilidade para novos documentos, como interagir com a IT da Contoso ao criar novos sites do SharePoint e sempre armazenar ativos digitais em sites do SharePoint

    A alteração de hábitos de armazenamento de informações de funcionários ruins geralmente é considerada a parte mais difícil da transição de proteção de informações para a nuvem. A CONTOSO IT e o gerenciamento necessários para fazer com que os funcionários rotulem e armazenem sempre seus ativos digitais na nuvem, evitem usar compartilhamentos de arquivos locais e não usem serviços de armazenamento em nuvem de terceiros ou unidades USB.

## <a name="conditional-access-policies-for-information-protection"></a>Políticas de Acesso Condicional para proteção de informações

Como parte de sua versão do Exchange Online e do SharePoint, a Contoso configurou o seguinte conjunto de políticas de Acesso Condicional e as aplicou aos grupos apropriados:

- [Acesso de aplicativo gerenciados e não gerenciado e políticas de dispositivos](../security/defender-365-security/identity-access-policies.md)
- [Políticas de acesso do Exchange Online](../security/defender-365-security/secure-email-recommended-policies.md)
- [Políticas de acesso do SharePoint](../security/defender-365-security/sharepoint-file-access-policies.md)

Aqui está o conjunto resultante de políticas da Contoso para proteção de informações.

![Políticas de Acesso Condicional do Dispositivo, do Exchange Online e do SharePoint ](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>A Contoso também configurou políticas de Acesso condicional adicionais para identidade e entrada.  Confira, [Identidade da Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).
>

Essas políticas garantem que:

- Os aplicativos permitidos e as ações que podem ser tomadas com os dados da organização são definidas por políticas de proteção de aplicativos.
- PCs e dispositivos móveis devem estar compatíveis.
- O Exchange Online usa a criptografia de mensagem do Office 365 (OME) para o Exchange Online.
- O SharePoint usa restrições impostas pelo aplicativo.
- O SharePoint usa políticas de controle de acesso para acesso somente por navegador e para bloquear o acesso de dispositivos não gerenciados.

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a>Mapeamento do Microsoft 365 para recursos corporativos para níveis de dados da Contoso

A tabela a seguir mapeia os níveis de dados da Contoso para recursos de proteção de informações no Microsoft 365 para empresas.

| Nível | Serviços de nuvem do Microsoft 365 | Aplicativos do Windows 10 e do Microsoft 365 para empresas | Segurança e conformidade |
|:-------|:-----|:-----|:-----|
| Nível 1: linha de base  | Políticas de Acesso Condicional do SharePoint e do Exchange Online <BR> Permissões em sites do SharePoint  | Rótulos de confidencialidade <BR> BitLocker <BR> Proteção de Informações do Windows | Políticas de Acesso Condicional de Dispositivos e políticas de Gerenciamento de Aplicativos Móveis |
| Nível 2: Confidencial | Nível 1 mais: <BR> <BR> Rótulos de confidencialidade <BR> Rótulos de retenção do Microsoft 365 em sites do SharePoint <BR> Prevenção contra perda de dados do SharePoint Online e do Exchange Online <BR> Sites isolados do SharePoint   | Nível 1 mais: <BR> <BR> Rótulos de confidencialidade em ativos digitais  | Nível 1 |
| Nível 3: altamente controlado | Nível 2 mais: <BR><BR> Traga sua própria criptografia BYOK (chave) e proteção para informações de segredo comercial <BR> Azure Key Vault para aplicativos de linha de negócios que interagem com serviços do Microsoft 365 | Nível 2 | Nível 1 |
|||||

Aqui está a configuração de proteção de informações da Contoso resultante.

![Configurações resultantes da proteção de informações da Contoso](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>Próxima etapa

Saiba como a Contoso usa os recursos de segurança no [Microsoft 365](contoso-security-summary.md) para empresas para gerenciamento de identidade e acesso, proteção contra ameaças, proteção de informações e gerenciamento de segurança.

## <a name="see-also"></a>Confira também

[Roteiro de segurança](../security/defender-365-security/security-roadmap.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)