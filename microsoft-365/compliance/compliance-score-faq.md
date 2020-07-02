---
title: Perguntas frequentes sobre a pontuação de conformidade da Microsoft (prévia)
f1.keywords:
- NOCSH
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
description: Encontre respostas para perguntas frequentes sobre a pontuação de conformidade da Microsoft, que ajuda as organizações a simplificar e automatizar avaliações de risco.
ms.openlocfilehash: 6ba71620d689e6d028b61ff24f7c837337ef60c6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016196"
---
# <a name="compliance-score-preview-frequently-asked-questions"></a>Nota de conformidade (visualização) perguntas frequentes

## <a name="what-is-compliance-score"></a>O que é a pontuação de conformidade?

A pontuação de conformidade da Microsoft é um recurso de visualização no [centro de conformidade da microsoft 365](microsoft-365-compliance-center.md) que ajuda você a entender a postura de conformidade da sua organização. Ele calcula uma pontuação baseada em risco medindo seu progresso em ações de conclusão que ajudam a reduzir os riscos relacionados à proteção de dados e aos padrões normativos. A pontuação de conformidade fornece mapeamento de controle interno que ajuda a conectar controles comuns entre normas e padrões principais. Esse mapeamento permite que você execute uma ação para satisfazer vários requisitos ao mesmo tempo, ajudando a dimensionar o programa de conformidade.

## <a name="whats-new-in-the-preview-version-of-compliance-score"></a>Quais são as novidades na versão de visualização da Pontuação de conformidade?

Visite as [notas de versão da Pontuação de conformidade](compliance-score-release-notes.md) para saber mais sobre atualizações de recursos e problemas conhecidos.

## <a name="how-do-i-access-compliance-score"></a>Como posso acessar a pontuação de conformidade?

Vá para o [centro de conformidade da microsoft 365](https://compliance.microsoft.com/) e **entre** com uma função de administrador de administração global, administrador de conformidade ou administrador de dados de conformidade da 365 Microsoft. Selecione a **Pontuação de conformidade** no painel de navegação esquerdo. Em seguida, você deve ver seu [painel de Pontuação de conformidade com sua pontuação](compliance-score-setup.md#understand-the-compliance-score-dashboard). Se você não tiver o acesso apropriado à função, o administrador global da sua organização poderá conceder a você permissão.

## <a name="what-roles-or-permissions-are-needed-to-use-compliance-score"></a>Quais funções ou permissões são necessárias para usar a pontuação de conformidade?

A pontuação de conformidade usa um modelo de permissão RBAC (controle de acesso baseado em função). As ações que você pode executar dependem do tipo de função atribuído a você. O administrador global do Microsoft 365 da sua organização é a pessoa que pode executar as funções de instalação e administrar funções na pontuação de conformidade. No mínimo, os usuários precisam da função **leitor global do Azure ad** para ler os dados na pontuação de conformidade. Saiba mais sobre permissões, funções e procedimentos de configuração na [configuração de Pontuação de conformidade](compliance-score-setup.md).

## <a name="what-is-the-difference-between-compliance-score-and-compliance-manager"></a>Qual é a diferença entre a pontuação de conformidade e o gerente de conformidade?

A pontuação de conformidade e o Gerenciador de conformidade compartilham o mesmo backend. Tudo o que você fizer em uma ferramenta será apresentado na outra ferramenta. Eles residem em dois locais diferentes: a pontuação de conformidade está no centro de conformidade da Microsoft 365 e o gerente de conformidade está no portal de confiança do serviço Microsoft. Considere a pontuação de conformidade como uma versão simplificada do gerente de conformidade, fornecendo uma visão mais completa da postura de conformidade atual da sua organização e as etapas que você pode tomar para melhorá-lo.

Embora seja possível realizar várias ações diretamente dentro da Pontuação de conformidade, algumas funcionalidades residem no Gerenciador de conformidade durante a visualização pública. Leia mais sobre a [relação entre a pontuação de conformidade e o gerente de conformidade](compliance-score.md#relationship-to-compliance-manager).

Gerenciador de conformidade do Access [no portal de confiança do serviço Microsoft](https://servicetrust.microsoft.com/ComplianceManager/V3). Certifique-se de **selecionar Gerenciador de conformidade** no menu suspenso de navegação superior, que tem os recursos mais atuais, e *não o Gerenciador de conformidade (clássico)*, que contém os recursos de lançamento antecipado.

## <a name="should-i-use-compliance-score-or-compliance-manager"></a>Devo usar a pontuação de conformidade ou o gerente de conformidade?

A pontuação de conformidade é útil para todos em sua organização que exercem uma função em conformidade. Com a pontuação de conformidade, você não precisa estar familiarizado com regulamentos e padrões para ajudar a melhorar a proteção de dados da sua organização. A pontuação de conformidade é o local ideal para todos os usuários. A partir daqui, você pode ver sua pontuação de conformidade, saber quais ações recomendadas podem ajudar a minimizar riscos e gerenciar suas avaliações.

Por enquanto, o gerente de conformidade é o local onde você pode criar modelos personalizados para criar avaliações. Saiba mais sobre [quais ações são compatíveis apenas com o Gerenciador de conformidade durante a](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager) visualização pública.

## <a name="if-i-have-a-high-score-does-it-mean-im-fully-compliant"></a>Se eu tiver uma pontuação alta, isso significa que estou totalmente em conformidade?

Não. Sua pontuação de conformidade mede seu progresso na conclusão de ações recomendadas que ajudam a reduzir os riscos relacionados à proteção de dados e aos padrões normativos. Ele não expressa uma medida absoluta da conformidade organizacional com qualquer padrão ou regulamentação específico. A pontuação de conformidade não deve ser interpretada como uma garantia de qualquer forma.

## <a name="what-regulations-and-standards-does-compliance-score-monitor"></a>Que regulamentações e padrões o monitor de Pontuação de conformidade?

A pontuação de conformidade fornece uma pontuação inicial com base na linha de base de proteção de dados da Microsoft 365, que é um conjunto de controles que inclui normas e padrões do setor comuns. Essa linha de base desenha elementos primariamente da NIST CSF (National Institute of Standards and Technology cybersecurity Framework) e ISO (International Organization for Standardization), bem como do FedRAMP (programa de gerenciamento de riscos e autorização federal) e RGPD (regulamentação geral de proteção de dados da União Europeia).

As organizações podem criar e adicionar avaliações personalizadas que sejam mais relevantes para sua organização. Use um dos [modelos](compliance-score-templates.md)de nota de conformidade prontos para usar, personalizar um modelo da Microsoft com seus próprios controles e ações ou criar seu próprio modelo. Leia os detalhes sobre como [trabalhar com avaliações e modelos](compliance-score-assessments.md).

## <a name="how-does-compliance-score-continuously-assess-my-environment"></a>Como a pontuação de conformidade avalia continuamente meu ambiente?

A pontuação de conformidade verifica automaticamente o ambiente e usa a pontuação segura para detectar as configurações do sistema. Saiba mais sobre a [avaliação contínua](compliance-score-methodology.md#how-compliance-score-continuously-assesses-controls).

## <a name="what-is-the-difference-between-compliance-score-and-secure-score"></a>Qual é a diferença entre a pontuação de conformidade e a pontuação segura?

A pontuação de conformidade fornece uma ampla visão da postura de conformidade e proteção de dados da sua organização. A pontuação de conformidade também fornece ferramentas de fluxo de trabalho internas; Ele permite que as organizações atribuam trabalho aos usuários, acompanhem a implementação do controle e o status do teste e carreguem evidências e criem relatórios de auditoria.

A pontuação segura da Microsoft é uma ferramenta de análise de segurança para ajudar a entender a postura de segurança. [Saiba mais sobre a pontuação segura e como ela funciona](../security/mtp/microsoft-secure-score-new.md).

## <a name="which-cloud-services-are-covered-by-compliance-score"></a>Quais serviços de nuvem são cobertos pela pontuação de conformidade?

A pontuação de conformidade atualmente fornece Avaliações para o Office 365 e o Intune. A cobertura expandida é esperada em futuras versões e será observada nas [notas de versão da Pontuação de conformidade](compliance-score-release-notes.md).

## <a name="can-i-use-compliance-score-for-non-microsoft-products"></a>Posso usar a pontuação de conformidade para produtos que não são da Microsoft?

Embora a pontuação de conformidade forneça monitoramento contínuo e ações recomendadas apenas para os serviços de nuvem da Microsoft, você pode adicionar avaliações personalizadas no Gerenciador de conformidade para os serviços locais de terceiros. Dessa forma, você pode usar a pontuação de conformidade da Microsoft como uma ferramenta de gerenciamento de conformidade SaaS para ajudá-lo a gerenciar todos os controles em seus ativos digitais.

Você pode usar um dos [modelos](compliance-score-templates.md) de nota de conformidade prontos para usar para criar Avaliações para padrões específicos ou [criar seu próprio modelo](working-with-compliance-manager.md#create-a-template), que você precisará fazer no Gerenciador de conformidade.

## <a name="how-do-i-delete-a-template-or-assessment-i-no-longer-need"></a>Como faço para excluir um modelo ou avaliação de que eu não preciso mais?

Para excluir uma avaliação, abra a avaliação que você deseja excluir e selecione **excluir avaliação**. Observe que a exclusão de uma avaliação é permanente. Exiba detalhes adicionais sobre como [excluir avaliações](compliance-score-assessments.md#delete-an-assessment). A exclusão de uma avaliação não exclui o modelo. Os modelos não podem ser excluídos, mas podem ser ocultados do modo de exibição. Revise [as instruções para ocultar modelos](working-with-compliance-manager.md#hide-a-template-or-an-assessment).

## <a name="what-test-procedures-does-microsoft-follow-for-controls"></a>Quais procedimentos de teste a Microsoft segue para controles?

A Microsoft participa de auditorias anuais para controles. Você pode examinar os relatórios de auditoria de nossos auditores, que estão disponíveis para download no [portal de confiança do serviço Microsoft](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3).

## <a name="why-are-some-controls-tested-annually-and-others-tested-every-three-years"></a>Por que alguns controles são testados anualmente, e outros testaram a cada três anos?

A avaliação do FedRAMP é um exemplo de por que esse pode ser o caso. Ele é conduzido todos os anos e testa uma cruz de controles entre as famílias de controle mais importantes. O FedRAMP classifica os controles como **principais** quando são importantes o suficiente para exigir testes anuais. Os controles designados como não principais são testados a cada três anos. Um subconjunto de controles que abrangem todas as famílias de controle principais são testados anualmente. Dessa forma, cada auditoria anual examina os cenários no quadro para garantir que a solução seja robusta. Leia mais sobre o [processo de avaliação anual do FedRAMP](https://www.fedramp.gov/annual-assessment-guidance/).
