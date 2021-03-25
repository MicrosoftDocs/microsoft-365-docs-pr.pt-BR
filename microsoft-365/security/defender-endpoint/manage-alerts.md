---
title: Gerenciar alertas do Microsoft Defender para Pontos de Extremidade
description: Altere o status dos alertas, crie regras de supressão para ocultar alertas, enviar comentários e revisar o histórico de alterações para alertas individuais com o menu Gerenciar Alerta.
keywords: gerenciar alertas, gerenciar, alertas, status, novo, em andamento, resolvido, resolver alertas, suprimir, suprimir, regras, contexto, histórico, comentários, alterações
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f03c2209b369e6fb9e001452c53073daeb5fe1c6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186996"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a>Gerenciar alertas do Microsoft Defender para Pontos de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

O Defender for Endpoint notifica você sobre possíveis eventos mal-intencionados, atributos e informações contextuais por meio de alertas. Um resumo de novos alertas é exibido no painel Operações de segurança **e** você pode acessar todos os alertas na fila **de alertas.**

Você pode gerenciar alertas selecionando um alerta na fila **alertas** ou a guia **Alertas** da página Dispositivo para um dispositivo individual.

Selecionar um alerta em qualquer um desses locais traz o painel gerenciamento **de alertas**.

![Imagem do painel de gerenciamento de alertas e fila de alertas](images/atp-alerts-selected.png)

## <a name="link-to-another-incident"></a>Link para outro incidente
Você pode criar um novo incidente a partir do alerta ou do link para um incidente existente. 

## <a name="assign-alerts"></a>Atribuir alertas
Se um alerta ainda não estiver atribuído, você poderá selecionar **Atribuir a mim** para atribuir o alerta a si mesmo.


## <a name="suppress-alerts"></a>Suprimir alertas
Pode haver cenários em que você precisa suprimir alertas de aparecer no Centro de Segurança do Microsoft Defender. O Defender for Endpoint permite que você crie regras de supressão para alertas específicos que são conhecidos como ferramentas ou processos conhecidos em sua organização.

As regras de supressão podem ser criadas a partir de um alerta existente. Eles podem ser desabilitados e reenvelizáveis, se necessário.

Quando uma regra de supressão é criada, ela terá efeito a partir do ponto em que a regra for criada. A regra não afetará alertas existentes já na fila, antes da criação da regra. A regra só será aplicada em alertas que atendam às condições definidas após a criação da regra.

Há dois contextos para uma regra de supressão que você pode escolher:

- **Suprimir alerta neste dispositivo**
- **Suprimir alerta na minha organização**

O contexto da regra permite adaptar o que é feito no portal e garantir que apenas alertas reais de segurança sejam a tona no portal.

Você pode usar os exemplos na tabela a seguir para ajudá-lo a escolher o contexto de uma regra de supressão:

| **Context**                           | **Definição**                                                                                                                                              | **Exemplos de cenários**                                                                                                                                                                                                  |
|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Suprimir alerta neste dispositivo**    | Os alertas com o mesmo título de alerta e nesse dispositivo específico serão suprimidos. <br /><br />Todos os outros alertas nesse dispositivo não serão suprimidos. | <ul><li>Um pesquisador de segurança está investigando um script mal-intencionado que foi usado para atacar outros dispositivos em sua organização.</li><li>Um desenvolvedor cria regularmente scripts do PowerShell para sua equipe.</li></ul> |
| **Suprimir alerta na minha organização** | Alertas com o mesmo título de alerta em qualquer dispositivo serão suprimidos.                                                                                         | <ul><li>Uma ferramenta administrativa benigna é usada por todos em sua organização.</li></ul>                                                                                                                               |

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a>Suprimir um alerta e criar uma nova regra de supressão:
Crie regras personalizadas para controlar quando os alertas são suprimidos ou resolvidos. Você pode controlar o contexto para quando um alerta é suprimido especificando o título do alerta, o indicador de comprometimento e as condições. Depois de especificar o contexto, você poderá configurar a ação e o escopo no alerta. 

1. Selecione o alerta que você gostaria de suprimir. Isso gera o **painel gerenciamento de** alertas.

2.  Selecione **Criar uma regra de supressão.**

    Você pode criar uma condição de supressão usando esses atributos. Um operador AND é aplicado entre cada condição, portanto, a supressão ocorre somente se todas as condições são atendidas.
    
    * Arquivo SHA1
    * Nome do arquivo - curinga com suporte
    * Caminho da pasta - curinga com suporte
    * Endereço IP
    * URL - curinga com suporte
    * Linha de comando - curinga com suporte

3. Selecione o **IOC de acionamento.**
    
4. Especifique a ação e o escopo no alerta. <br>
   Você pode resolver automaticamente um alerta ou escondê-lo do portal. Os alertas que são resolvidos automaticamente serão exibidos na seção resolvida da fila de alertas, da página de alerta e da linha do tempo do dispositivo e serão exibidos como resolvidos no Defender para APIs do Ponto de Extremidade. <br><br> Os alertas marcados como ocultos serão suprimidos de todo o sistema, tanto nos alertas associados do dispositivo quanto no painel e não serão transmitidos no Defender para APIs do Ponto de Extremidade.


5. Insira um nome de regra e um comentário.

6. Clique em **Salvar**.

#### <a name="view-the-list-of-suppression-rules"></a>Exibir a lista de regras de supressão

1. No painel de navegação, selecione **Configurações**  >  **Supressão de alerta**.

2. A lista de regras de supressão mostra todas as regras que os usuários em sua organização criaram.

Para obter mais informações sobre como gerenciar regras de supressão, consulte [Gerenciar regras de supressão](manage-suppression-rules.md)

## <a name="change-the-status-of-an-alert"></a>Alterar o status de um alerta

Você pode categorizar alertas (como **Novo**, **Em Andamento** ou **Resolvido)** alterando seu status à medida que a investigação progride. Isso ajuda você a organizar e gerenciar como sua equipe pode responder a alertas.

Por exemplo, um líder de equipe pode revisar todos os **novos** alertas e decidir atribuí-los à fila **Em** Andamento para análise posterior.

Como alternativa, o líder da equipe  pode atribuir o alerta à fila Resolvido se ele sabe que o alerta é benigno, proveniente de um dispositivo irrelevante (como um pertencente a um administrador de segurança) ou está sendo tratado por meio de um alerta anterior.



## <a name="alert-classification"></a>Classificação de alerta
Você pode optar por não definir uma classificação ou especificar se um alerta é um alerta verdadeiro ou um alerta falso. É importante fornecer a classificação de verdadeiro positivo/falso positivo. Essa classificação é usada para monitorar a qualidade do alerta e tornar os alertas mais precisos. O campo "determinação" define fidelidade adicional para uma classificação "verdadeiro positivo". 

## <a name="add-comments-and-view-the-history-of-an-alert"></a>Adicionar comentários e exibir o histórico de um alerta
Você pode adicionar comentários e exibir eventos históricos sobre um alerta para ver as alterações anteriores feitas no alerta.

Sempre que uma alteração ou comentário é feita em um alerta, ela é registrada na seção **Comentários e** histórico.

Os comentários adicionados aparecem instantaneamente no painel.


## <a name="related-topics"></a>Tópicos relacionados
- [Gerenciar regras de supressão](manage-suppression-rules.md)
- [Exibir e organizar a fila de alertas do Microsoft Defender for Endpoint](alerts-queue.md)
- [Investigar alertas do Microsoft Defender para Pontos de Extremidade](investigate-alerts.md)
- [Investigar um arquivo associado a um alerta do Microsoft Defender para Ponto de Extremidade](investigate-files.md)
- [Investigar dispositivos na lista do Microsoft Defender for Endpoint Devices](investigate-machines.md)
- [Investigar um endereço IP associado a um alerta do Microsoft Defender para Ponto de Extremidade](investigate-ip.md)
- [Investigar um domínio associado a um alerta do Microsoft Defender para Ponto de Extremidade](investigate-domain.md)
- [Investigar uma conta de usuário no Microsoft Defender para Ponto de Extremidade](investigate-user.md)
