---
title: Como trabalhar com os serviços de consultoria da Microsoft
description: preparação e etapas a serem seguidas para trabalhar com MCS para empacotar seus aplicativos
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação, aplicativos, MCS, pacotes
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 39a5102d045d9ed79b631a3b477bd1c72dea76de
ms.sourcegitcommit: 498340389e1c34f49f0b2da382c23c8d5334ae47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2019
ms.locfileid: "34918714"
---
# <a name="working-with-microsoft-consulting-services"></a>Como trabalhar com os serviços de consultoria da Microsoft

Você pode entrar com o Microsoft Consulting Services (MCS) para obter seus aplicativos empacotados para uso com a área de trabalho gerenciada da Microsoft. Para obter detalhes exatos, trabalhe com seu representante de conta para entrar em contato com a MCS e o escopo de seu projeto de pacote de aplicativos específico.

## <a name="roles-and-responsibilities"></a>Funções e responsabilidades

Para trabalhar com o pacote de aplicativos MCS, **você deve fornecer estes elementos**:

- Os arquivos do instalador de origem (por exemplo, setup. exe ou. msi).
- As instruções de instalação, especificando detalhes sobre como a instalação final deve ser verificada. Por exemplo, deve haver um atalho de área de trabalho para o aplicativo? O que a visibilidade do aplicativo deve ser? O aplicativo deve se conectar a um servidor e, em caso afirmativo, qual deles? <!--For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx). -->
- Você deve executar seu próprio teste de aceitação para verificar se o aplicativo funciona conforme você precisa para o seu ambiente.

**O MCS cuidará destas ações:**

- Verificar se o aplicativo é proibido ou restrito no ambiente de área de trabalho gerenciada da Microsoft.
- Teste de instalação, início e desinstalação do aplicativo para garantir a compatibilidade com o Windows 10. Se o MCS descobrir um problema de compatibilidade, ele enviará o aplicativo para o [aplicativo da área de trabalho garantir](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) o programa para correção.
- Empacotar o aplicativo para sua especificação e, em seguida, testar a implantação do aplicativo usando o Microsoft Intune.

## <a name="app-delivery-schedule"></a>Agenda de entrega do aplicativo

Inicie o processo de empacotamento carregando as informações do aplicativo para o portal de área de trabalho gerenciada da Microsoft. A equipe de empacotamento revisa novos envios a cada quinta-feira. Após a revisão e o empacotamento, os aplicativos empacotados são entregues na sexta-feira a seguir. Até cinco aplicativos por semana podem ser empacotados para iniciar, mas o serviço pode ser dimensionado para atender às suas necessidades.

![calendário mostrando datas de revisão, embalagem e entrega de aplicativos](images/MCS-cal.png)

Você será notificado assim que o aplicativo for entregue. Nesse ponto, você tem 21 dias para executar o teste de aceitação e aprovar o trabalho no portal de área de trabalho gerenciada da Microsoft. Se descobrir algum problema com o aplicativo durante o teste de aceitação, rejeite o aplicativo no portal de área de trabalho gerenciada da Microsoft e você será conectado por email com um empacotador MCS para entender e resolver o problema.

## <a name="testing-accounts-and-environment"></a>Testando contas e ambientes

Para a equipe de embalagens concluir a migração para o Microsoft Intune, recomendamos que você forneça determinadas permissões:
 
-   Acesso aos recursos de implantação de aplicativos do Microsoft Intune para o packager adicionar e atribuir o aplicativo 
-   Grupos de teste, contas de usuário e licenças para que os compactadores possam testar os aplicativos

O MCS usará essas permissões para executar as seguintes ações:
 
-   Garantir que o aplicativo funcione na máquina virtual configurada para a área de trabalho gerenciada da Microsoft
-   Carregar o aplicativo no Microsoft Intune para implantação em seus usuários

Sem essas permissões, é possível para o MCS avançar, mas eles não poderão carregar os aplicativos para o seu ambiente.


