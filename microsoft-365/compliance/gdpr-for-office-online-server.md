---
title: RGPD para Servidor do Office Online e para o Servidor do Office Web Apps
description: Saiba mais sobre como atender aos requisitos de RGPD no Exchange Server local.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 747959fcdf8840644e4b7de4de02eb250d062423
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596448"
---
# <a name="gdpr-for-office-web-apps-server-and-office-online-server"></a>RGPD para Servidor do Office Web Apps e Servidor do Office Online

Dados de telemetria do Servidor do Office Web Apps e do Servidor do Office Online são armazenados em forma de logs ULS. Você pode usar [ULSViewer](https://www.microsoft.com/download/details.aspx?id=44020) para exibir os logs ULS do seu locatário local.

Todas as linhas de log contêm uma CorrelationID. Linhas de log relacionadas compartilham a mesma CorrelationID. Cada CorrelationID está vinculada a uma SessionID e uma SessionID pode estar relacionada a muitas CorrelationIDs. Cada SessionID pode estar relacionada a uma única UserID, embora algumas sessões possam ser anônimas e, portanto, não estarem associadas a uma UserID. Para determinar quais dados estão associados a um usuário específico, é possível mapear de uma única UserID para as SessionIDs associadas ao usuário, das SessionIDs para as CorrelationIDs associadas, e dessas CorrelationIDs para todos os logs nessas correlações. Confira o diagrama abaixo para verificar a relação entre as diferentes IDs.

![](media/gdpr-for-office-online-server-image1.jpg)

## <a name="gathering-logs"></a>Coletar logs

Para reunir todos os logs associados com a UserID 1, por exemplo, a primeira etapa é reunir todas as sessões associadas à UserID 1 (ou seja, SessionID 1 e SessionID2). A próxima etapa será reunir todas as correlações associadas com a SessionID 1 (ou seja, CorrelationIDs 1, 2 e 3) e com a SessionID 2 (ou seja, CorrelationID 4). Por fim, reúna todos os logs associados a cada correlação na lista.

1.  Iniciar o ULSViewer

2.  Abra o log ULS correspondente ao período de tempo pretendido; logs ULS são armazenados em %PROGRAMDATA%\\Microsoft\\OfficeWebApps\\Data\\Logs\\ULS

3.  Editar | Modificar Filtro

4.  Aplique um filtro que seja:

    -   EventID igual a apr3y ou

    -   EventID igual a bp2d6

5.  UserIDs com hash estarão na mensagem de qualquer um desses dois eventos

6.  Para apr3y, a mensagem conterá um valor de UserID e um valor de PUID

7.  Para bp2d6, a mensagem conterá uma grande quantidade de informações. O campo de valor LoggableUserId é a UserID com hash.

8.  Depois de obter a UserID com hash dessas duas marcas, o valor de WacSessionId dessa linha no ULSViewer conterá a WacSessionId associada ao usuário

9.  Colete todos os valores de WacSessionId associados com usuários em questão

10. Filtre todos EventId iguais a "xmnv", Message igual a "UserSessionId =\<WacSessionId\>" para a primeira WacSessionId na lista (substituindo a \<WacSessionId\> do filtro pela sua WacSessionId)

11. Colete todos os valores de correlação que correspondam a essa WacSessionId

12. Repita as etapas 10 e 11 para todos os valores de WacSessionId em sua lista de usuários em questão

13. Filtrar para todos os valores de correlação iguais à primeira correlação da sua lista

14. Colete todos os logs correspondentes a essa correlação

15. Repita as etapas 13 e 14 para todos os valores de correlação em sua lista de usuários em questão

## <a name="types-of-data"></a>Tipos de dados

Os logs do Office contêm diversos tipos de dados. A seguir são apresentados exemplos de dados que podem conter logs ULS:

-   Códigos de erro para problemas encontrados durante o uso do produto

-   Cliques de botão e outros dados sobre o uso do aplicativo

-   Dados de desempenho do aplicativo e/ou recursos específicos do aplicativo

-   Informações gerais de localização sobre onde está o computador do usuário (por exemplo, país/região, estado e cidade, derivadas do endereço IP), mas não uma geolocalização precisa

-   Metadados básicos sobre o navegador, por exemplo, o nome e a versão do navegador e informações sobre o computador, como o tipo e a versão do sistema operacional

-   Mensagens de erro do host do documento (por exemplo, OneDrive, SharePoint, Exchange)

-   Informações sobre processos internos do aplicativo não relacionados a ações do usuário
