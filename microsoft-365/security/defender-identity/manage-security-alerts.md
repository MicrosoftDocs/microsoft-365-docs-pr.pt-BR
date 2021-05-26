---
title: Alertas de segurança do Microsoft Defender para Identidade no Microsoft 365 Defender
description: Saiba como gerenciar e revisar alertas de segurança emitidos pelo Microsoft Defender for Identity no Microsoft 365 Defender
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: 0c48c9076d05cd352229477acc28b32185eef54f
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657758"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a>Alertas de segurança do Defender para Identidade no Microsoft 365 Defender

**Aplica-se a:**

- Microsoft 365 Defender
- Microsoft Defender para Identidade

Este artigo explica as noções básicas de como trabalhar com alertas de segurança do [Microsoft Defender for Identity](/defender-for-identity) no centro de segurança Microsoft 365 de [segurança.](/microsoft-365/security/defender/overview-security-center)

Os alertas do Defender para Identidade são integrados na Microsoft 365 de segurança [com](https://security.microsoft.com) um formato de página de alerta de identidade dedicado. Isso marca a primeira etapa da jornada para introduzir a experiência completa do [Microsoft Defender for Identity no Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).

A nova página de alerta de identidade oferece aos clientes do Microsoft Defender for Identity melhor enriquecimento de sinal entre domínios e novos recursos automatizados de resposta de identidade. Ele garante que você permaneça seguro e ajude a melhorar a eficiência de suas operações de segurança.

Um dos benefícios da investigação de alertas por meio do [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) é que os alertas do Microsoft Defender for Identity são correlacionados ainda mais com as informações obtidas de cada um dos outros produtos do pacote. Esses alertas aprimorados são consistentes com os outros formatos de alerta do Microsoft 365 Defender provenientes do [Microsoft Defender para Office 365](/microsoft-365/security/office-365-security) e do Microsoft Defender para Ponto de [Extremidade.](/microsoft-365/security/defender-endpoint) A nova página elimina efetivamente a necessidade de navegar até outro portal de produto para investigar alertas associados à identidade.

Os alertas provenientes do Defender para Identidade agora podem disparar os recursos de investigação e resposta [automatizadas do Microsoft 365 Defender (AIR),](/microsoft-365/security/defender/m365d-autoir) incluindo a correção automática de alertas e a mitigação de ferramentas e processos que podem contribuir para a atividade suspeita.

>[!IMPORTANT]
>Como parte da convergência com o Microsoft 365 Defender, algumas opções e detalhes foram alterados de sua localização no portal defender para identidade. Leia os detalhes abaixo para descobrir onde encontrar os recursos familiares e novos.

## <a name="review-security-alerts"></a>Revisar alertas de segurança

Os alertas podem ser acessados de vários locais, incluindo a página **Alertas,** a página Incidentes, as páginas de **Dispositivos individuais** **e** a partir da página De **busca** avançada. Neste exemplo, revisaremos a página **Alertas.**  

No centro [Microsoft 365 segurança,](https://security.microsoft.com/)vá para **Incidentes & alertas** e, em seguida, **para Alertas**.

![Vá para Incidentes e Alertas, em seguida, Alertas](../../media/defender-identity/incidents-alerts.png)

Para ver alertas do Defender para Identidade, na parte  superior direita selecione **Filtrar** e, em Fontes de serviço, selecione **Microsoft Defender para Identidade** e selecione **Aplicar**:

![Filtrar eventos do Defender para Identidade](../../media/defender-identity/filter-defender-for-identity.png)

Os alertas são exibidos com informações nas seguintes colunas: Nome do **alerta,** **Marcas,** **Gravidade,** Estado de investigação, **Status,** **Categoria,** **Fonte** de **Detecção,** Ativos afetados, Primeira atividade e Última **atividade**.

![Eventos defender para identidade](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a>Gerenciar alertas

Se você clicar **no nome do alerta** para um dos alertas, você irá para a página com detalhes sobre o alerta. No painel esquerdo, você verá um resumo do **que aconteceu**:

![O que aconteceu em alerta](../../media/defender-identity/what-happened.png)

Acima da **caixa O que aconteceu** estão botões para **contas,** host de **destino** **e host** de origem do alerta. Para outros alertas, você pode ver botões para obter detalhes sobre hosts adicionais, contas, endereços IP, domínios e grupos de segurança. Selecione qualquer um deles para obter mais detalhes sobre as entidades envolvidas.

No painel direito, você verá os detalhes **do alerta.** Aqui você pode ver mais detalhes e executar várias tarefas:

- **Classificar esse alerta** - Aqui você pode designar esse alerta como um **alerta True** ou Um **alerta False**

    ![Classificar alerta](../../media/defender-identity/classify-alert.png)

- **Estado de alerta** - Em **Classificação de** Conjunto, você pode classificar o alerta como **True** ou **False**. Em **Atribuído a**, você pode atribuir o alerta a si mesmo ou desaigná-lo.

    ![Estado de alerta](../../media/defender-identity/alert-state.png)

- Detalhes do alerta **-** Em Detalhes de **alerta,** você pode encontrar mais informações sobre o alerta específico, seguir um link para a documentação sobre o tipo de alerta, ver com qual incidente o alerta está associado, revisar quaisquer investigações automatizadas vinculadas a esse tipo de alerta e ver os dispositivos e usuários afetados.

    ![Detalhes do alerta](../../media/defender-identity/alert-details.png)

- **Comentários & histórico** - Aqui você pode adicionar seus comentários ao alerta e ver o histórico de todas as ações associadas ao alerta.

    ![Comentários e histórico](../../media/defender-identity/comments-history.png)

- **Gerenciar alerta** - Se você selecionar **Gerenciar alerta,** você irá para um painel que permitirá que você edite o:
  - **Status** - Você pode escolher **Novo**, **Resolvido** ou **Em andamento**.
  - **Classificação** - Você pode escolher **Alerta true** ou **alerta False.**
  - **Comentário** - Você pode adicionar um comentário sobre o alerta.

    Se você selecionar os três pontos ao lado de **Gerenciar** alerta, poderá consultar um especialista em **ameaças,** exportar o alerta para um arquivo Excel ou Vincular a **outro incidente.** 

    ![Gerenciar alerta](../../media/defender-identity/manage-alert.png)

    >[!NOTE]
    >No arquivo Excel, agora você tem dois links disponíveis: Exibir no **Microsoft Defender para** Identidade e Exibir no Microsoft 365 **Defender**. Cada link o levará ao portal relevante e fornecerá informações sobre o alerta.

## <a name="see-also"></a>Confira também

- [Investigar alertas no Microsoft 365 Defender](../defender/investigate-alerts.md)
