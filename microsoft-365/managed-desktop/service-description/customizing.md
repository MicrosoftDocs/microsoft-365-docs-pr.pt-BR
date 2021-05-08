---
title: Exceções ao plano de serviço
description: Como solicitar exceções ao plano de serviço padrão
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 59a2b8227eb7e410ecf8506ce288978213537edc
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245511"
---
# <a name="exceptions-to-the-service-plan"></a>Exceções ao plano de serviço

Área de Trabalho Gerenciada da Microsoft fornece uma lista de dispositivos com cura, configurações de dispositivo padrão, requisitos de [aplicativos](device-policies.md)e determinadas configurações configuráveis, todas [projetadas](../working-with-managed-desktop/config-setting-overview.md)para fornecer uma experiência segura, produtiva e agradável para os usuários. É melhor sempre permanecer com o serviço conforme fornecido. No entanto, reconhecemos que alguns detalhes do serviço podem não se ajustar exatamente às necessidades da sua organização. Se você acha que precisa alterar o serviço de alguma forma, é importante seguir os seguintes processos para solicitar essas alterações.
 
## <a name="types-of-exceptions"></a>Tipos de exceções

Uma exceção é qualquer adição ou alteração na configuração Área de Trabalho Gerenciada da Microsoft base; os exemplos vão desde a configuração de portas USB até a implantação de um novo driver de dispositivo. Agrupamos várias exceções da seguinte forma:

|Tipo  |Descrição  |
|---------|---------|
|Software de produtividade     |  Software em primeiro plano necessário pelos usuários, restrito pelos requisitos [do aplicativo](mmd-app-requirements.md)       |
|Agentes de segurança & VPNs     |  Software usado para proteger, monitorar ou alterar o comportamento do dispositivo ou da rede       |
|Monitoramento de experiência digital     |  Software usado para rastrear dados no dispositivo de um usuário para relatar à IT       |
|Drivers de hardware ou software     |   Drivers de dispositivo, restritos pelos [requisitos do aplicativo](mmd-app-requirements.md)      |
|Políticas     | Windows 10 ou Microsoft 365 Apps para Grandes Empresas configurações em um dispositivo gerenciado        |
|Dispositivos     | Dispositivos que não estão na lista Área de Trabalho Gerenciada da Microsoft [dispositivos](device-list.md)        |
|Outros     |  Qualquer coisa não coberta pelas outras áreas       |
 
## <a name="request-an-exception"></a>Solicitar uma exceção

Envie solicitações por meio do portal Área de Trabalho Gerenciada da Microsoft Admin criando uma solicitação de alteração. Certifique-se de incluir estes detalhes:

- Tipo de isenção: Qual categoria de exceção é? (consulte a tabela anterior)
- Requisito: Qual é o requisito comercial específico para a exceção?
- Proposta: Qual solução sua empresa está solicitando?
- Linha do tempo: por quanto tempo você deseja que essa exceção durar? 

## <a name="how-we-assess-an-exception-request"></a>Como avaliamos uma solicitação de exceção

Quando analisamos solicitações de exceção, avaliamos esses fatores nesta ordem:
 
1. Alguns aplicativos e políticas que Área de Trabalho Gerenciada da Microsoft implantados em todos os dispositivos não são negociáveis, portanto, sua solicitação não deve afetá-los. Consulte [Configuração do dispositivo](device-policies.md) para obter mais informações.
2. O software de produtividade restrito exigido por um usuário para fazer seu trabalho provavelmente será aprovado. 
3. Se podemos atender aos seus requisitos usando a tecnologia Microsoft, provavelmente aprovaremos sua solicitação para um período de migração de exceção de três a 12 meses (dependendo do escopo do projeto).
4. Se não podemos atender aos seus requisitos usando a tecnologia Microsoft, provavelmente aprovaremos sua solicitação, a menos que ela viole uma das condições abaixo.  

Esses princípios garantem que Área de Trabalho Gerenciada da Microsoft sempre possam atender às suas necessidades enquanto rastreia desvios do nosso modelo padrão. 

## <a name="key-conditions"></a>Principais condições

Analisamos exceções para garantir que elas não violem nenhuma destas condições:

- Uma exceção não deve afetar adversamente a segurança do sistema. 
- Manter a exceção não deve incorrer em um custo significativo para operações Área de Trabalho Gerenciada da Microsoft ou suporte.
- Uma exceção não deve afetar a estabilidade do sistema, por exemplo, causando falhas ou travamentos no modo kernel.
- A alteração não deve nos restringir a operar o serviço ou conflitar com a tecnologia Área de Trabalho Gerenciada da Microsoft principal.

Essas condições podem mudar no futuro. Se fizermos essas alterações, forneceremos um aviso de 30 dias antes de essas condições entrarem em vigor.  Se Área de Trabalho Gerenciada da Microsoft oferecer uma maneira alternativa de atender a uma exceção aprovada, Área de Trabalho Gerenciada da Microsoft notificará o cliente Área de Trabalho Gerenciada da Microsoft alterar a maneira de dar suporte à exceção. 

## <a name="revoking-approval-for-an-exception"></a>Revogando aprovação para uma exceção

Depois que uma exceção solicitada é aprovada e implantada, é possível que descubramos problemas que violam as condições-chave que não eram evidentes quando aprovamos a alteração. Nessa situação, talvez seja preciso revogar a aprovação da exceção.
 
Se isso acontecer, notificaremos você usando o portal Área de Trabalho Gerenciada da Microsoft administrador. Desde a primeira vez que o notificamos, você tem 90 dias para remover a exceção antes que os dispositivos com exceção não sejam mais vinculados Área de Trabalho Gerenciada da Microsoft de nível de serviço. Enviaremos várias notificações de acordo com uma linha do tempo estrita, no entanto, um incidente grave ou uma ameaça pode exigir que alteremos a linha do tempo ou nossas decisões sobre uma exceção. Não removeremos uma *exceção* sem seu consentimento, mas qualquer dispositivo com uma exceção revogada não será mais vinculado pelo nosso contrato de nível de serviço. Aqui está a linha do tempo das notificações que enviaremos a você:

- **Primeiro aviso:** Fornecemos o primeiro aviso de nossa decisão de revogar a aprovação, incluindo informações sobre por que a revogamos, as ações que recomendamos que você tome, o prazo para essas ações e as etapas a serem seguidas se você quiser recorrer da decisão. Esse aviso ocorre com 90 dias de antecedência antes que a exceção precise ser removida de todos os dispositivos. 
- **Segundo aviso (30 dias depois):** Fornecemos um segundo aviso, incluindo as mesmas informações fornecidas no primeiro aviso. 
- **Terceiro aviso (60 dias após o primeiro aviso):** Fornecemos um terceiro aviso, incluindo as mesmas informações fornecidas no primeiro aviso. 
- **Aviso final (uma semana antes do prazo de 90 dias):** Fornecemos um quarto aviso, incluindo as mesmas informações fornecidas no primeiro aviso.
- **90 dias após o primeiro aviso:** Área de Trabalho Gerenciada da Microsoft contratos de nível de serviço não se aplicam mais a dispositivos que tenham a exceção revogada. A qualquer momento, você pode desafiar a decisão e fornecer informações adicionais para consideração, incluindo atualização, alterações de configuração ou alteração de software. 


