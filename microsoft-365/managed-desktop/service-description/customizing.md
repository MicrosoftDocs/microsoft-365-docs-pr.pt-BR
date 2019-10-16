---
title: Personalizar o serviço
description: ''
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b2b74194c9b73e538fc1be937456b76deef75feb
ms.sourcegitcommit: eed48c21790d31a85292f7e39bf1e30c42f10d36
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37523666"
---
# <a name="customize-the-service"></a>Personalizar o serviço

O Microsoft Managed Desktop fornece uma lista de dispositivos organizadas, [configurações de dispositivo padrão](device-policies.md), requisitos de aplicativos e determinadas [configurações configuráveis](../working-with-managed-desktop/config-setting-overview.md), todas projetadas para fornecer uma experiência segura, produtiva e agradável para os usuários finais. É melhor estar sempre com o serviço conforme fornecido. No entanto, reconhecemos que alguns detalhes do serviço podem não se ajustar exatamente às necessidades da sua organização. Se você achar que precisa alterar o serviço de alguma forma, é importante que siga os processos a seguir para solicitar essas alterações.

 
## <a name="types-of-customizations"></a>Tipos de personalização
Uma personalização é qualquer adição ou alteração na configuração base de área de trabalho gerenciada da Microsoft; Os exemplos variam da configuração de portas USB à implantação de um novo agente de segurança. Agrupamos várias personalizações da seguinte maneira:


|Tipo  |Descrição  |
|---------|---------|
|Software de produtividade     |  Software de primeiro plano necessário para usuários finais, restrito pelos [requisitos do aplicativo](mmd-app-requirements.md)       |
|Agentes de segurança & VPNs     |  Software usado para proteger, monitorar ou alterar o comportamento do dispositivo ou da rede       |
|Monitoramento de experiência digital     |  Software usado para rastrear dados no dispositivo de um usuário para relatá-los       |
|Drivers de hardware ou software     |   Drivers de dispositivo, restritos pelos [requisitos do aplicativo](mmd-app-requirements.md)      |
|Políticas     | Configurações do Windows 10 ou do Office 365 ProPlus em um dispositivo gerenciado        |
|Dispositivos     | Dispositivos que não estão na [lista de dispositivos](device-list.md) de área de trabalho gerenciada da Microsoft        |
|Other     |  Qualquer coisa não coberta pelas outras áreas       |



 
## <a name="request-a-customization"></a>Solicitar uma personalização

Envie solicitações através do portal de administração de área de trabalho gerenciada da Microsoft criando uma solicitação de alteração. Certifique-se de incluir estes detalhes:
-   Tipo de personalização: Qual é a categoria de personalização? (consulte a tabela anterior)
-   Requisito: Qual é a necessidade de negócios específica para a personalização?
-   Proposta: qual solução é solicitada pela sua empresa?
-   Linha do tempo: quanto tempo você deseja que essa personalização seja a última? 


## <a name="how-we-assess-a-customization-request"></a>Como avaliamos uma solicitação de personalização

Quando revisamos solicitações de personalização, avaliamos esses fatores nesta ordem:
 
1.  Alguns aplicativos e políticas que a área de trabalho gerenciada da Microsoft implantam em todos os dispositivos não estão negociáveis e, portanto, a solicitação não deve ser afetada. Consulte [configuração de dispositivo](device-policies.md) para obter mais informações.
2.  O software de produtividade restrita exigido por um usuário final para realizar seu trabalho provavelmente será aprovado. 
3.  Se pudermos atender seus requisitos usando a tecnologia da Microsoft, provavelmente aprovaremos sua solicitação para um período de migração de três a doze meses (dependendo do escopo do projeto).
4.  Se não pudermos atender seus requisitos usando a tecnologia da Microsoft, provavelmente aprovaremos sua solicitação, a menos que viole uma das condições abaixo.  

Esses princípios garantem que a área de trabalho gerenciada da Microsoft sempre atenda às suas necessidades enquanto controla os desvios do nosso modelo padrão. 

## <a name="key-conditions"></a>Principais condições

Revisamos personalizações para garantir que elas não violem qualquer uma destas condições:

-   Uma personalização não deve afetar adversamente A segurança do sistema. 
-   A manutenção da personalização não deve incorrer em um custo significativo para as operações de área de trabalho gerenciada da Microsoft ou o suporte.
-   Uma personalização não deve afetar a estabilidade do sistema, por exemplo, fazendo com que o modo kernel trave ou traves.
-   A alteração não deve refazê-los de operar o serviço ou entrar em conflito com a tecnologia de área de trabalho gerenciada da Microsoft principal.

Essas condições podem mudar no futuro. Se fizermos essas alterações, forneceremos um aviso de 30 dias antes das condições que entram em vigor.

## <a name="revoking-approval-for-a-customization"></a>Revogar a aprovação de uma personalização

Depois que uma personalização solicitada é aprovada e implantada, é possível que possamos descobrir problemas que violam as principais condições que não estavam evidentes quando aprovamos a alteração em primeiro lugar. Nessa situação, podemos ter que revogar a aprovação da personalização.
 
Se isso acontecer, vamos notificá-lo usando o portal de administração de área de trabalho gerenciada da Microsoft. Desde a primeira vez que notificamos você, você tem 90 dias para remover a personalização antes que os dispositivos com a personalização não sejam mais associados aos contratos de nível de serviço do Microsoft Managed desktop. Enviaremos várias notificações de acordo com um cronograma estrito, no entanto, um incidente ou ameaça grave pode exigir a alteração da linha do tempo ou de nossas decisões sobre uma personalização. Não *removeremos* uma personalização sem o seu consentimento, mas qualquer dispositivo com uma personalização revogada não será mais vinculado ao nosso contrato de nível de serviço. Aqui está a linha do tempo das notificações que enviaremos para você:

- **Primeiro aviso:** Fornecemos o primeiro aviso da nossa decisão de revogar a aprovação, incluindo informações sobre o motivo pelo qual estamos revogando, as ações que aconselhamos você a realizar, o prazo final dessas ações e as etapas a serem seguidas se você quiser atrair a decisão. É mais de 90 dias antes que a personalização precise ser removida de todos os dispositivos. 
- **Segundo aviso (30 dias depois):** Fornecemos um segundo aviso, incluindo as mesmas informações fornecidas no primeiro aviso. 
- **Terceiro aviso (60 dias após o primeiro aviso):** Fornecemos um terceiro aviso, incluindo as mesmas informações fornecidas no primeiro aviso. 
- **Aviso final (1 semana antes do prazo de 90 dias):** Fornecemos um quarto aviso, incluindo as mesmas informações fornecidas no primeiro aviso.
- **90 dias após o primeiro aviso:** Os contratos de nível de serviço de área de trabalho gerenciada da Microsoft não se aplicam mais a dispositivos que tenham a personalização revogada. A qualquer momento, você pode desafiar a decisão e fornecer informações adicionais para considerar, incluindo atualização, alterações de configuração ou alteração de software. 

