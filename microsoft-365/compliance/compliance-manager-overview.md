---
title: Visão geral do Gerenciador de conformidade da Microsoft
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: O Gerenciador de conformidade da Microsoft é uma ferramenta de avaliação de riscos gratuita baseada em fluxo de trabalho no portal de confiança do serviço Microsoft. O Gerenciador de conformidade permite que você rastreie, atribua e verifique as atividades de conformidade normativa relacionadas aos serviços em nuvem da Microsoft.
ms.openlocfilehash: c88b45fb568b0fe29bc967676ea09e89e9084a62
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072226"
---
# <a name="microsoft-compliance-manager-preview"></a>Gerente de conformidade da Microsoft (versão prévia)

> [!IMPORTANT]
> O Gerenciador de Conformidade não está disponível no Office 365 operado pela 21Vianet, Office 365 Germany, Office 365 US Government Community High (GCC High) ou Office 365 Department of Defense.

[O Microsoft Compliance Manager (versão prévia)](https://servicetrust.microsoft.com/ComplianceManager) é uma ferramenta de avaliação de risco baseada em fluxo de trabalho que permite controlar, atribuir e verificar atividades de conformidade regulatória relacionadas aos serviços de nuvem da Microsoft. Parte de sua assinatura do Microsoft 365, do Office 365 ou do Azure Active Directory, o Gerenciador de conformidade ajuda a gerenciar a conformidade normativa no modelo de responsabilidade compartilhada para os serviços de nuvem da Microsoft. O Gerenciador de conformidade oferece um painel centralizado para visualização de padrões, regulamentos e detalhes de implementação de controle e resultados de teste para avaliações de serviços da Microsoft. Ele também inclui ferramentas que permitem gerenciar as implementações de controle personalizado e o controle de conformidade específico da sua organização.

Com o gerente de conformidade, sua organização pode:
  
- Combinar informações detalhadas de conformidade da Microsoft fornecidas aos auditores e reguladores sobre seus serviços em nuvem com sua auto-avaliação de conformidade para padrões e regulamentações aplicáveis à sua organização. Eles incluem padrões e regulamentos descritos pela International Organization for Standardization (ISO), o National Institute of Standards and Technology (NIST), o Health Insurance Portability and Accountability Act (HIPAA), os dados gerais Regulamentação de proteção (RGPD) e muitas outras.
- Permite que você atribua, rastreie e registre as atividades relacionadas à conformidade e à avaliação, o que pode ajudar sua organização a interrupções para atingir suas metas de conformidade.
- Forneça uma pontuação de conformidade para ajudar a acompanhar o progresso e priorizar os controles de auditoria que ajudam a reduzir a exposição da sua organização a riscos.
- Fornecer um repositório seguro para carregar e gerenciar evidências e outros artefatos relacionados às suas atividades de conformidade.
- Produzir relatórios detalhados do Microsoft Excel, que documentam as atividades de conformidade realizadas pela Microsoft e sua organização para auditores, reguladores e outros revisores de conformidade.

> [!NOTE]
> As ações do cliente fornecidas no gerente de conformidade são recomendações; a sua organização pode avaliar a eficácia dessas recomendações em seu respectivo ambiente normativo antes da implementação. As recomendações encontradas no Gerenciador de conformidade não devem ser interpretadas como garantia de conformidade.

## <a name="compliance-manager-relationships"></a>Relações do gerente de conformidade

O Gerenciador de conformidade usa vários componentes para ajudá-lo com suas atividades de gerenciamento de conformidade. Esses componentes funcionam juntos para fornecer um fluxo de trabalho de gerenciamento completo e relatórios de conformidade sem complicações para auditores.

O diagrama mostra as relações entre os principais componentes do Gerenciador de conformidade:

![Relações no Gerenciador de conformidade versão 3](media/compliance-manager-relationships.png)

## <a name="groups"></a>Grupos

Os [grupos](working-with-compliance-manager.md#groups) são contêineres que permitem organizar as avaliações e compartilhar informações comuns e tarefas de fluxo de trabalho entre avaliações que têm o mesmo ou controles relacionados gerenciados pelo cliente. Quando duas avaliações diferentes no mesmo grupo compartilham o controle gerenciado pelo cliente, a conclusão dos detalhes da implementação, teste e status do controle são automaticamente sincronizadas com o mesmo controle em qualquer outra avaliação no grupo. Isso unifica os itens de ação atribuídos para cada controle no grupo e reduz o trabalho de duplicação. Você também pode optar por usar grupos para organizar. Avaliações por ano, área, padrão de conformidade ou outros agrupamentos para ajudar a organizar seu trabalho de conformidade.

## <a name="assessments"></a>Avaliações

As [avaliações](working-with-compliance-manager.md#assessments) são contêineres que permitem organizar os controles com base nas responsabilidades compartilhadas entre a Microsoft e sua organização para avaliar os riscos de segurança e conformidade do serviço de nuvem. As avaliações ajudam você a implementar proteções de proteção de dados especificadas por um padrão de conformidade e normas, regulamentos ou leis de proteção de dados aplicáveis. Eles ajudam a discernir sua postura de proteção e conformidade de dados contra o padrão do setor selecionado para o serviço de nuvem da Microsoft selecionado. As avaliações são concluídas pela implementação dos controles incluídos na avaliação que mapeiam para um padrão de certificação.

Por padrão, o Gerenciador de conformidade cria as seguintes Avaliações para sua organização:

- Office 365 ISO 27001
- Office 365 NIST 800-53
- Office 365 RGPD

As avaliações incluem vários componentes:
  
- **Serviços no escopo**: cada avaliação se aplica a um conjunto específico de serviços da Microsoft.
- **Controles gerenciados pela Microsoft**: para cada serviço de nuvem, a Microsoft implementa e gerencia um conjunto de controles de conformidade para padrões e regulamentações aplicáveis.
- **Controles gerenciados pelo cliente**: esta é a coleção de controles implementados por sua organização quando você realiza ações para cada controle.
- **Pontuação de avaliação**: a porcentagem da pontuação total possível para os controles gerenciados pelo cliente na avaliação. Isso ajuda a acompanhar a implementação das ações atribuídas a cada controle.

## <a name="controls"></a>Controles

Os [controles](working-with-compliance-manager.md#controls-and-actions) são contêineres de processo de conformidade no gerente de conformidade que definem como gerenciar atividades de conformidade. Esses controles são organizados em famílias de controle que se alinham com a estrutura de avaliação de certificações ou regulamentações correspondentes.

- **ID de controle**: o nome do controle selecionado da certificação ou regulamentação correspondente.
- **Título do controle**: o título da ID de controle da certificação ou regulamentação correspondente.
- **ID do artigo**: Este campo é somente para avaliações do rgpd e especifica o número de artigo correspondente do rgpd.
- **Descrição**: texto de controle da certificação ou regulamentação correspondente. Devido a restrições de direitos autorais, um link para informações relevantes é listado para padrões ISO.

![Controles no Gerenciador de conformidade versão 3](media/compliance-manager-controls.png)

Há três tipos de controles no Gerenciador de conformidade, **controles gerenciados pela Microsoft**, **controles gerenciados pelo cliente**e **controles de gerenciamento compartilhados**

### <a name="microsoft-managed-controls"></a>Controles gerenciados pela Microsoft

Para cada serviço de nuvem, a Microsoft implementa e gerencia um conjunto de controles como parte da conformidade da Microsoft com vários padrões e regulamentações. Cada controle fornece detalhes sobre como a Microsoft implementou o controle e como e quando essa implementação foi testada e validada pela Microsoft e/ou por um auditor independente de terceiros.

### <a name="customer-managed-controls"></a>Controles gerenciados pelo cliente

Este é o conjunto de controles gerenciados pela sua organização. Sua organização é responsável pela implementação de controle gerenciado pelo cliente como parte do seu processo de conformidade para um determinado padrão ou regulamentação. Os controles gerenciados pelo cliente são organizados em famílias de controle para a certificação ou regulamentação correspondente. Use os controles gerenciados pelo cliente para implementar as ações recomendadas sugeridas pela Microsoft como parte de suas atividades de conformidade. Sua organização pode usar orientações prescritivas e ações de cliente recomendadas em cada controle gerenciado pelo cliente para gerenciar o processo de implementação e avaliação desse controle.

Os controles gerenciados pelo cliente nas avaliações também têm funcionalidade de gerenciamento de fluxo de trabalho interna que você pode usar para gerenciar e acompanhar o andamento da avaliação. Com essa funcionalidade de fluxo de trabalho, você pode:

- Atribuir itens de ação para cada controle
- Rastrear itens de ação atribuídos
- Carregar evidências da implementação do controle
- Documentar o teste e a validação do controle
- Marcar os itens de ação conforme implementados e testados

Por exemplo, um responsável pela conformidade de sua organização atribui um item de ação a um administrador de ti com as permissões de responsabilidade e necessárias para executar a ação recomendada. O administrador de ti carrega evidências das tarefas de implementação (capturas de tela das configurações de política ou configuração) e atribui o item de ação de volta ao responsável pela conformidade quando concluído. O responsável pela conformidade avalia a evidência coletada, testa a implementação do controle e registra a data de implementação e os resultados do teste no gerente de conformidade.

### <a name="shared-management-controls"></a>Controles de gerenciamento compartilhados

Um controle compartilhado refere-se a qualquer controle em que a Microsoft e os clientes compartilhem responsabilidades de implementação. Por exemplo, controles relacionados à filtragem pessoal, gerenciamento de contas e senhas e criptografia exigem ações da Microsoft e dos clientes.

## <a name="action-items"></a>Itens de Ação

Os [itens de ações](working-with-compliance-manager.md#controls-and-actions) são incluídos em controles gerenciados pelo cliente como parte da funcionalidade de gerenciamento de fluxo de trabalho interna que você pode usar para gerenciar e acompanhar o progresso da conclusão da avaliação.

As pessoas da sua organização podem usar o Gerenciador de conformidade para analisar os controles gerenciados pelo cliente em todas as avaliações para as quais foram atribuídos. Quando um usuário entra no gerente de conformidade e abre o painel **itens de ação** , uma lista de itens de ação atribuídos a eles é exibida. Dependendo da função de gerente de conformidade atribuída ao usuário, eles podem fornecer detalhes de implementação ou teste, atualizar o status ou atribuir itens de ação.

Os controles de certificação geralmente são implementados por uma pessoa e testados por outra. Por exemplo, depois que os itens de ação atribuídos inicialmente a uma pessoa para implementação são concluídos, os itens de ação são atribuídos à próxima pessoa para testar e carregar evidências. Qualquer usuário com permissões suficientes para as atribuições de controle pode atribuir e Reatribuir itens de ação. Isso permite o gerenciamento central de atribuições de controle e o roteamento descentralizado de itens de ação entre implementadores e testadores.

## <a name="permissions"></a>Permissões

O Gerenciador de conformidade usa um [modelo de permissão](working-with-compliance-manager.md#permissions)de controle de acesso baseado em função. Por padrão, todas as pessoas em sua organização com a conta do Azure Active Directory (Azure AD) têm acesso total e podem executar qualquer ação no Gerenciador de conformidade. Após o controle de acesso baseado em função ter sido implementado pela sua organização, qualquer usuário que não tenha sido atribuído a uma função gerente de conformidade é atribuído acesso de convidado. A equipe de serviço da Microsoft não tem acesso à posição para dados que você insere ou carrega.

Para alterar as permissões padrão e implementar um modelo de controle de acesso baseado em função totalmente, pelo menos um usuário deve ser adicionado a cada função de Gerenciador de conformidade. Após um usuário ser adicionado a uma função, as permissões para executar as ações atribuídas a essa função são removidas do conjunto padrão de permissões disponíveis para todos os usuários. Somente os usuários provisionados com a função poderão acessar o Gerenciador de conformidade e executar as ações permitidas por essa função.

Se você adicionar um usuário à função para gerenciar avaliações, somente os membros dessa função poderão gerenciar avaliações. Se você não adicionar um usuário à função que permite que os usuários leiam os dados em avaliações, todos os usuários em sua organização poderão acessar o Gerenciador de conformidade e ler os dados em qualquer avaliação.
  
## <a name="manage-evidence"></a>Gerenciar evidências

O Gerenciador de conformidade pode armazenar evidências de suas tarefas de implementação para executar testes e validação de controles gerenciados pelo cliente. A evidência inclui documentos, planilhas, capturas de tela, imagens, scripts, arquivos de saída de script e outros arquivos. O Gerenciador de conformidade também recebe automaticamente a telemetria e cria um registro de evidência para itens de ação que estão integrados à pontuação segura. Todos os dados carregados como evidências no gerente de conformidade são armazenados nos Estados Unidos nos sites de armazenamento na nuvem da Microsoft. Esses dados são replicados nas regiões do Azure localizadas no sudeste asiático e na Europa Ocidental.

## <a name="templates"></a>Modelos

O gerente de conformidade fornece [modelos](working-with-compliance-manager.md#templates) pré-configurados para avaliações e permite que você crie modelos personalizados para controles gerenciados pelo cliente para suas necessidades de conformidade. Novos modelos são criados importando as informações de controles de um arquivo do Excel ou você pode criar um modelo a partir de uma cópia de um modelo existente.

Os modelos pré-configurados incluídos no Gerenciador de conformidade são:
 
- [ISO 27001:2013](https://www.iso.org/obp/ui/#iso:std:iso-iec:27001:ed-2:v1:en)
- [ISO 27018:2019](https://www.iso.org/obp/ui/#iso:std:iso-iec:27018:ed-2:v1:en)
- [NIST 800-53](https://csrc.nist.gov/publications/detail/sp/800-53/rev-4/final)
- [NIST 800-171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final)
- [Estrutura NIST cybersecurity (CSF)](https://www.nist.gov/cyberframework)
- [O CCM (Cloud Security Alliance) 3.0.1 (Cloud Control Matrix) 3.0.1](https://cloudsecurityalliance.org/working-groups/cloud-controls-matrix/#_overview)
- [Folheto de segurança de informações do FFIEC Financial Federals (Conselho de análise de instituições financeiras)](https://ithandbook.ffiec.gov/it-booklets/information-security.aspx) 
- [HIPAA](https://www.hhs.gov/hipaa/for-professionals/index.html) / de[alta tecnologia](https://www.hhs.gov/hipaa/for-professionals/special-topics/hitech-act-enforcement-interim-final-rule/index.html)
- [FedRAMP moderado](https://www.fedramp.gov/documents/)
- [RGPD de União Européia](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32016R0679&from=EN)

## <a name="compliance-score"></a>Pontuação de conformidade

A [Pontuação de conformidade](compliance-score-methodology.md) é um componente principal do Gerenciador de conformidade que ajuda sua organização a entender e gerenciar a conformidade. Como a [Pontuação segura da Microsoft](../security/mtp/microsoft-secure-score.md), a pontuação de conformidade é um sistema de pontuação baseado em comportamento para atividades relacionadas à proteção de dados, privacidade e segurança em sua organização. A pontuação de conformidade de uma avaliação é uma expressão de conformidade com um determinado padrão ou regulamentação. Quanto maior a pontuação numérica, melhor a postura de conformidade para a avaliação. A compreensão da metodologia de Pontuação de conformidade é crucial para priorizar as ações obrigatórias de controle gerenciado pelo cliente.
  
> [!IMPORTANT]
> A Pontuação de Conformidade não expressa uma medida absoluta da conformidade organizacional em relação a qualquer padrão ou regulamentação específicos. Ela expressa até que ponto você adotou os controles que podem reduzir os riscos aos dados pessoais e à privacidade individual. Nenhum serviço pode garantir que você esteja em conformidade com um padrão ou regulamentação e a Pontuação de Conformidade não deve ser interpretada como uma garantia de forma alguma.

## <a name="secure-score-integration"></a>Integração da Pontuação segura

O Gerenciador de conformidade é integrado à [Pontuação segura da Microsoft](../security/mtp/microsoft-secure-score.md) para aplicar automaticamente o crédito de Pontuação segura à pontuação de conformidade para itens de ação sincronizados. Isso é configurável para itens de ação individuais e fornece uma atualização contínua entre os itens.

Por exemplo, você tem um requisito relacionado à segurança para ativar o Azure Rights Management em sua organização que também se aplica a um item de ação relacionado à conformidade. Quando o Azure Rights Management é ativado e processado pela pontuação segura, o Gerenciador de conformidade recebe a notificação da atualização e a Pontuação do item de ação é atualizada automaticamente com o crédito de conclusão.

## <a name="ready-to-get-started"></a>Pronto para começar?

Comece a [trabalhar com o Gerenciador de conformidade](working-with-compliance-manager.md) para gerenciar atividades de conformidade regulatória para sua organização.

## <a name="resources"></a>Recursos

- [Guia interativo: avaliar e aprimorar seus controles de proteção de dados com o Gerenciador de conformidade](https://content.cloudguides.com/guides/Compliance%20Manager)
- [Comunidade técnica de segurança, privacidade e conformidade da Microsoft](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/ct-p/SecurityPrivacyCompliance)
