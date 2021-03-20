---
title: Trabalhar com Serviços de consultoria da Microsoft
description: preparação e etapas a seguir para trabalhar com o MCS para empacotar seus aplicativos
keywords: Microsoft Managed Desktop, Microsoft 365, serviço, documentação, aplicativos, MCS, empacotamento
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 04b0c7905c83be2afa46abcfb2d4bb5cd9735e06
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909221"
---
# <a name="working-with-microsoft-consulting-services"></a>Trabalhar com Serviços de consultoria da Microsoft

Você pode se envolver com o Microsoft Consulting Services (MCS) para obter seus aplicativos empacotados para uso com a Área de Trabalho Gerenciada da Microsoft. Para obter detalhes exatos, trabalhe com seu representante de conta para entrar em contato com MCS e escopo do projeto de empacotamento de aplicativos específico.

## <a name="roles-and-responsibilities"></a>Funções e responsabilidades

Para trabalhar com o empacotamento de aplicativos MCS, **você deve fornecer estes elementos:**

- Os arquivos do instalador de origem (por exemplo, setup.exe ou .msi).
- As instruções de instalação, especificando detalhes sobre como a instalação final deve ser. Por exemplo, deve haver um atalho da área de trabalho para o aplicativo? Qual deve ser a visibilidade do aplicativo? O aplicativo deve se conectar a um servidor e, em caso algum, qual deles? Para obter detalhes, consulte o modelo [de solicitação de empacotamento de aplicativos](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).
- Você deve executar seu próprio teste de aceitação para verificar se o aplicativo funciona conforme necessário em seu ambiente.

**O MCS tratará dessas ações:**

- Verificar se o aplicativo é proibido ou restrito no ambiente da Área de Trabalho Gerenciada da Microsoft.
- Teste de instalação, início e desinstalação do aplicativo para garantir a compatibilidade com o Windows 10. Se o MCS descobrir um problema de compatibilidade, eles entregarão o aplicativo para o programa [de](/fasttrack/win-10-desktop-app-assure) Garantia de Aplicativos da Área de Trabalho para correção.
- Empacotando o aplicativo para sua especificação e testando a implantação do aplicativo usando o Microsoft Intune.

## <a name="app-delivery-schedule"></a>Cronograma de entrega de aplicativos

Inicie o processo de empacotamento carregando as informações do aplicativo no portal da Área de Trabalho Gerenciada da Microsoft. A equipe de empacotamento revisa novos envios toda quinta-feira. Após revisão e empacotamento, os aplicativos empacotados são entregues na sexta-feira seguinte. Até cinco aplicativos por semana podem ser empacotados para iniciar, mas o serviço pode ser dimensionado para atender às suas necessidades.

![calendar showing app inflow on a Thursday (the 21st in this example), media validation the next day, packaging on the following Monday (the 25th) and app delivery on the subsequent Friday (the 29th)](../../media/MCS-cal.png)

Você será notificado depois que o aplicativo tiver sido entregue. Nesse ponto, você tem 21 dias para realizar testes de aceitação e aprovar o trabalho no portal da Área de Trabalho Gerenciada da Microsoft. Se descobrir algum problema com o aplicativo durante o teste de aceitação, rejeite o aplicativo no portal da Área de Trabalho Gerenciada da Microsoft e você será conectado por email com um empacotador MCS para entender e resolver o problema.

## <a name="testing-accounts-and-environment"></a>Testar contas e ambiente

Para que a equipe de empacotamento conclua a migração para o Microsoft Intune, recomendamos que você forneça determinadas permissões:
 
-   Acesso aos recursos de Implantação de Aplicativo do Microsoft Intune para o empacotador adicionar e atribuir o aplicativo 
-   Testar grupos, contas de usuário e licenças para que os empacotadores sejam capazes de testar os aplicativos

O MCS usará essas permissões para executar as seguintes ações:
 
-   Garantir que o aplicativo funcione em máquina virtual configurada para a Área de Trabalho Gerenciada da Microsoft
-   Carregando o aplicativo no Microsoft Intune para implantação para seus usuários

Sem essas permissões, é possível que o MCS avance, mas eles não poderão carregar os aplicativos em seu ambiente.