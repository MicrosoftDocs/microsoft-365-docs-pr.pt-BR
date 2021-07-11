---
title: Suporte ao usuário
description: Explica as opções de suporte conduzido pelo cliente e pelo parceiro.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8063e1b0e76241df946a29ef2c5115bc0dc39aad
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363762"
---
# <a name="user-support"></a>Suporte ao usuário

Os Área de Trabalho Gerenciada da Microsoft podem obter suporte da sua organização (chamamos isso de suporte "conduzido pelo cliente") ou de um parceiro selecionado ("suporte a parceiros"). Nosso objetivo é fornecer uma experiência consistente para os usuários, mantendo os dispositivos seguros com ambas as opções de suporte. Não importa qual opção você escolher, esses mesmos princípios se aplicam: 

- Integração flexível de Área de Trabalho Gerenciada da Microsoft com seus processos de suporte existentes. 
- Limpar funções e responsabilidades entre o provedor de suporte, administradores de TI e Área de Trabalho Gerenciada da Microsoft 
- [Caminhos de escalonamento definidos](#workflow-for-support-providers)
- Documentação fornecida pela Área de Trabalho Gerenciada da Microsoft, juntamente com um portal onde você pode solicitar acesso de dispositivo elevado e escalonamento para nossa equipe de suporte, se necessário.
- Monitoramento e mitigação de ameaças fornecidos pelo Área de Trabalho Gerenciada da Microsoft todos os dias todos os dias

## <a name="roles-and-responsibilities"></a>Funções e responsabilidades

Para garantir a qualidade do serviço sem comprometer a segurança, o provedor de suporte, os administradores de TI e Área de Trabalho Gerenciada da Microsoft têm funções e responsabilidades diferentes.

### <a name="support-provider"></a>Provedor de suporte

Quem fornece suporte (você para suporte ao cliente ou um parceiro para parceiros) é responsável por esses itens:

- Fornecendo todo o suporte do usuário e assistência técnica do primeiro contato até a resolução do usuário
- Cumprir todos os contratos de nível de serviço para suporte ao usuário estabelecido pela sua organização ou em parceria com o provedor de suporte escolhido
- Executar ações específicas de solução de problemas, como solicitar privilégios elevados de dispositivo, conforme descrito em [Obter ajuda para usuários](../working-with-managed-desktop/end-user-support.md)
- Solução de problemas e correção de problemas do usuário, incluindo:
    - Sistema operacional (Windows)
    - Microsoft Apps para empresas
    - Recursos do navegador
    - Problemas de dispositivo
    - Problemas com a infraestrutura, como impressoras, drivers e VPNs
    - Aplicativos de linha de negócios

### <a name="it-admin"></a>Administrador de TI

O administrador de IT é responsável por esses itens:

- Trabalhar com o provedor de suporte para definir e gerenciar contratos de nível de serviço para suporte ao usuário
- Gerenciando privilégios de acesso elevados para a equipe de suporte aprovada. Para obter mais informações, consulte [Habilitar recursos de suporte ao usuário](../get-started/enable-support.md)
- Se houver problemas de dispositivo que afetam vários usuários, escalone-os usando o processo de suporte Área de Trabalho Gerenciada da Microsoft administrador. Para obter mais informações, consulte [Suporte de administrador para Área de Trabalho Gerenciada da Microsoft](../working-with-managed-desktop/admin-support.md).
- Encaminhar problemas relacionados ao hardware para o fornecedor ou fornecedor apropriado
- Mantenha e proteja as configurações de política de segurança de dispositivos Área de Trabalho Gerenciada da Microsoft dispositivos, impedindo que as políticas definidas foram alteradas.

### <a name="microsoft-managed-desktop"></a>Área de trabalho gerenciada da Microsoft

Como provedor de serviços, somos responsáveis por esses itens:

- Fornecendo os meios para acesso de dispositivos elevados e escalonamento de problemas, incluindo documentação
- Mantendo essas informações sobre as funções e responsabilidades atuais
- Responder às solicitações de suporte do administrador de acordo com as definições de gravidade
- Fornecendo monitoramento e mitigação de ameaças para todos os dispositivos inscritos todos os dias todos os dias

## <a name="workflow-for-support-providers"></a>Fluxo de trabalho para provedores de suporte

Se o suporte é conduzido pelo cliente ou pelo parceiro, o fluxo de atividades para uma solicitação de suporte do usuário segue este caminho:

:::image type="content" source="../../media/mmd-support-flow.png" alt-text="Quando um usuário entrar em contato com o suporte, ele funcionará através do sistema de equipe hierárca conforme você projetou. É importante designar um grupo de equipes de suporte que receberá as capacidades de elevação e escalonamento, conhecidas como equipe de escalonamento de suporte. Para problemas Área de Trabalho Gerenciada da Microsoft específicos, eles podem escalar para nossa equipe de Operações. Ou para outros problemas da Microsoft, eles podem rotear para seu canal de suporte existente, Unified ou Premier. Os problemas de hardware sempre devem ser roteados para seu provedor ou fornecedor estabelecido":::

Integrar seus processos existentes a esse fluxo de trabalho para Área de Trabalho Gerenciada da Microsoft dispositivos é flexível, portanto, os detalhes podem ser diferentes. Normalmente, o provedor de suporte segue uma abordagem baseada em camadas ou handoff existente, designando usuários específicos que têm a capacidade de elevar permissões ou escalar problemas para operações Área de Trabalho Gerenciada da Microsoft. É melhor manter esse grupo menor do que a equipe de suporte mais ampla.

Se um problema do usuário precisar ser escalonado para Área de Trabalho Gerenciada da Microsoft, é útil identificar para qual equipe o problema deve ser direcionado. Podemos transferir casos adequadamente, mas economiza tempo para roteá-los para o lugar certo desde o início.

- Problemas específicos Área de Trabalho Gerenciada da Microsoft (por exemplo, uma política ou configuração que é implantada pelo próprio serviço): são escalonados diretamente para a equipe de Operações. Para obter mais informações, consulte [Obter ajuda para usuários](../working-with-managed-desktop/end-user-support.md).
- Problemas de hardware: direto para o fornecedor ou fornecedor de hardware
- Outros problemas: escalone por canais de suporte existentes, seja uma assinatura Unificada ou Premier.

## <a name="provided-support-framework"></a>Estrutura de suporte fornecida


### <a name="elevation-portal"></a>Portal de elevação 

Como Área de Trabalho Gerenciada da Microsoft dispositivos são executados no usuário padrão por padrão, algumas tarefas exigem elevação de privilégios. Para obter mais informações sobre o controle de conta de usuário, consulte [Controle de conta de usuário](/windows/security/identity-protection/user-account-control/user-account-control-overview). Para que a equipe de [](../working-with-managed-desktop/end-user-support.md#elevation-requests) suporte possa executar tarefas durante a solução de problemas para os usuários, fornecemos acesso "just-in-time" a uma conta de administrador. Essa senha acessada com segurança apenas por aqueles que você designa e gira a cada duas horas.  

Para ver as etapas sobre como configurar usuários para acesso a esse portal, consulte [Habilitar recursos de suporte ao usuário](../get-started/enable-support.md).

Para etapas sobre como enviar uma solicitação de elevação, consulte [Solicitações de elevação](../working-with-managed-desktop/end-user-support.md#elevation-requests).

### <a name="escalation-portal"></a>Portal de escalonamento 

Se um problema exigir escalonamento para Área de Trabalho Gerenciada da Microsoft equipe de Operações, a equipe de suporte designada poderá direcionar de forma semelhante a uma solicitação de suporte do administrador de IT.  

> [!NOTE]
> Somente as solicitações de suporte do Sev C podem ser arquivadas dessa maneira. Para um problema que corresponde à descrição de outras gravidades, é recomendável entrar em contato com o administrador de IT apropriado para o arquivo. Para obter mais informações, consulte [Support request severity definitions](../working-with-managed-desktop/admin-support.md#support-request-severity-definitions).

Para ver as etapas sobre como configurar usuários para acesso a esse portal, consulte [Habilitar recursos de suporte ao usuário](../get-started/enable-support.md).

Para etapas sobre como enviar uma solicitação de escalonamento, consulte [Solicitações de escalonamento](../working-with-managed-desktop/end-user-support.md#escalation-requests).
