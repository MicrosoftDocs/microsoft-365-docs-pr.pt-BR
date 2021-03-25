---
title: Habilitar o Acesso Condicional para proteger melhor usuários, dispositivos e dados
description: Habilita o Acesso Condicional para impedir que aplicativos sejam executados se um dispositivo for considerado em risco e um aplicativo for determinado como não compatível.
keywords: acesso condicional, bloquear aplicativos, nível de segurança, intune,
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
ms.openlocfilehash: 21d17ee789a4757df10e99514f23cfc26b186405
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166192"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a>Habilitar o Acesso Condicional para proteger melhor usuários, dispositivos e dados 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

O Acesso Condicional é um recurso que ajuda você a proteger melhor seus usuários e informações corporativas, se certificar de que somente dispositivos seguros tenham acesso a aplicativos.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4byD1]

Com o Acesso Condicional, você pode controlar o acesso às informações corporativas com base no nível de risco de um dispositivo. Isso ajuda a manter usuários confiáveis em dispositivos confiáveis usando aplicativos confiáveis.

Você pode definir condições de segurança em quais dispositivos e aplicativos podem executar e acessar informações de sua rede, impondo políticas para impedir a execução de aplicativos até que um dispositivo retorne a um estado compatível. 

A implementação do Acesso Condicional no Defender para Ponto de Extremidade baseia-se nas políticas de conformidade de dispositivos do Microsoft Intune (Intune) e políticas de acesso condicional do Azure Active Directory (Azure AD). 

A política de conformidade é usada com o Acesso Condicional para permitir que apenas dispositivos que cumprem uma ou mais regras de política de conformidade de dispositivo acessem aplicativos. 

## <a name="understand-the-conditional-access-flow"></a>Compreender o fluxo de Acesso Condicional
O Acesso Condicional é colocado no local para que, quando uma ameaça seja vista em um dispositivo, o acesso a conteúdos confidenciais seja bloqueado até que a ameaça seja remediada. 

O fluxo começa com dispositivos que estão sendo vistos com baixo, médio ou alto risco. Essas determinações de risco são enviadas para o Intune. 

Dependendo de como você configura políticas no Intune, o Acesso Condicional pode ser definido para que, quando determinadas condições são atendidas, a política seja aplicada.

Por exemplo, você pode configurar o Intune para aplicar o Acesso Condicional em dispositivos com alto risco.

No Intune, uma política de conformidade de dispositivo é usada em conjunto com o Acesso Condicional do Azure AD para bloquear o acesso a aplicativos. Em paralelo, um processo automatizado de investigação e correção é lançado.

 Um usuário ainda pode usar o dispositivo enquanto a investigação e a correção automatizadas estão ocorrendo, mas o acesso aos dados corporativos é bloqueado até que a ameaça seja totalmente remediada. 

Para resolver o risco encontrado em um dispositivo, você precisará retornar o dispositivo para um estado compatível. Um dispositivo retorna para um estado compatível quando não há risco visto nele. 

Há três maneiras de resolver um risco:
1. Use correção manual ou automatizada.
2. Resolva alertas ativos no dispositivo. Isso removerá o risco do dispositivo.
3. Você pode remover o dispositivo das políticas ativas e, consequentemente, o Acesso Condicional não será aplicado no dispositivo. 

A correção manual exige que um administrador do secops investigue um alerta e a fim de resolver o risco visto no dispositivo. A correção automatizada é configurada por meio das configurações fornecidas na seção a seguir, [Configure Conditional Access](configure-conditional-access.md).

Quando o risco é removido por meio de correção manual ou automatizada, o dispositivo retorna para um estado compatível e o acesso a aplicativos é concedido.

A seguinte sequência de exemplo de eventos explica o Acesso Condicional em ação:

1. Um usuário abre um arquivo mal-intencionado e o Defender para Ponto de Extremidade sinaliza o dispositivo como de alto risco.
2. A avaliação de alto risco é passada para o Intune. Em paralelo, uma investigação automatizada é iniciada para correção da ameaça identificada. Uma correção manual também pode ser feita para correção da ameaça identificada.
3. Com base na política criada no Intune, o dispositivo é marcado como não compatível. Em seguida, a avaliação é comunicada ao Azure AD pela política de Acesso Condicional do Intune. No Azure AD, a política correspondente é aplicada para bloquear o acesso a aplicativos.
4. A investigação e a correção manual ou automatizada são concluídas e a ameaça é removida. O Defender para Ponto de Extremidade vê que não há risco no dispositivo e o Intune avalia que o dispositivo está em estado de conformidade. O Azure AD aplica a política que permite o acesso a aplicativos.
5. Os usuários agora podem acessar aplicativos.

 
## <a name="related-topic"></a>Tópicos relacionados
- [Configurar o Acesso Condicional no Microsoft Defender para Ponto de Extremidade](configure-conditional-access.md)
