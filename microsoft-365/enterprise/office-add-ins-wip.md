---
title: Proteger documentos corporativos executando o Microsoft Office suplementos - Microsoft 365 Enterprise | Documentos do Microsoft
description: Descreve como usar o WIP e Intune para proteger os dados corporativos em documentos executando suplementos do Office.
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/14/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 6871f288a7e5849b147cbf0aedb056f84575f376
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864973"
---
# <a name="use-wip-and-intune-to-protect-enterprise-data-in-documents-running-office-add-ins"></a>Use o WIP e o Intune para proteger dados empresariais em documentos executando suplementos do Office
Quando os usuários em uma organização usam os suplementos do Office para interagir com os dados organizacionais, isso apresenta um risco potencial de que alguns dados podem ser vazados. Você pode usar a WIP (Proteção de Informações do Windows) e o Microsoft Intune para proteger os dados empresariais quando os usuários estão executando suplementos do Office.

[WIP](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip), anteriormente conhecida como EDP (proteção de dados empresariais), permite que as empresas protejam dados empresariais e propriedade intelectual. A WIP também ajuda a proteger dados e aplicativos empresariais contra vazamentos de dados acidentais em dispositivos pessoais e de propriedade da empresa que os funcionários trazem para o trabalho sem a necessidade de alterações no ambiente ou outros aplicativos.

O [Intune](https://www.microsoft.com/cloud-platform/microsoft-intune) fornece um conjunto diversificado de ferramentas para gerenciar seu ambiente móvel complexo. A combinação do Intune de opções de gerenciamento de dispositivo e gerenciamento de aplicativos móveis fornece aos administradores de TI e aos usuários finais a flexibilidade para gerenciar e proteger a produtividade móvel.

Você pode usar o Intune para [criar e implantar sua política de WIP](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/overview-create-wip-policy). Com o Intune, você pode escolher seus aplicativos protegidos e seu nível de proteção de WIP, além de encontrar dados empresariais na rede.

Com a WIP e o Intune:

-   As empresas podem fornecer a imposição de política de dados empresariais razoável, mesmo quando os dados são baixados em dispositivos pessoais.

-   As empresas podem usar educação de política contextual para informar os usuários sobre como se proteger contra a divulgação acidental de dados para serviços e aplicativos não gerenciados.

-   Os usuários finais podem estar em conformidade com políticas de dados corporativos sem interromper o fluxo de trabalho típico.

-   Os usuários finais podem transicionar perfeitamente entre a produtividade pessoal e de trabalho.

A WIP e o Intune são executados silenciosamente em segundo plano e são praticamente invisíveis quando os usuários não misturam conteúdo pessoal e corporativo.

Os [Suplementos do Office](https://dev.office.com/docs/add-ins/overview/office-add-ins) são criados com base em tecnologias da Web. Eles trazem o poder e as informações da Web para aplicativos do Office. Os suplementos interagem com o conteúdo em um aplicativo do Office por meio das APIs disponíveis no Office.js. Os princípios fundamentais dos suplementos do Office incluem:

-   **Segurança**: a arquitetura de plataforma JavaScript do Office garante que o código do suplemento esteja em uma área restrita e seja executado em um processo separado em relação ao aplicativo do Office host. Isso permite que a plataforma realize a ação corretiva quando um suplemento não atende aos padrões de desempenho ou é potencialmente mal intencionado notificando o usuário e, em alguns casos, desabilitando o suplemento. Essa arquitetura funciona em todas as plataformas que dão suporte a suplementos do Office.

-   **Resiliência**: a natureza "fora do processo" da plataforma do suplemento garante que o suplemento em si não afete a experiência do usuário ou o desempenho do aplicativo do Office host. Isso é essencial para manter o Office rápido e responsivo para as ações do usuário.

-   **Plataforma cruzada**: escreva uma vez, execute em qualquer lugar em que o Office é executado. Os suplementos têm suporte atualmente no Windows, Office Online, Mac e iPad. O suporte para suplementos na plataforma Android e Universal estará disponível em breve.

Os suplementos do Office podem trabalhar com conteúdo empresarial e potencialmente confidencial em um documento. Como parte de extensibilidade de aplicativos, os suplementos herdam o acesso da política de aplicativo host. Por exemplo, se as configurações de WIP impedirem que o Word acesse o conteúdo empresarial, os suplementos não conseguirão acessar o conteúdo empresarial em um documento Word.

Uma das metas dos suplementos é remover qualquer problema de bloqueio para os usuários finais enquanto garante que os administradores de empresa possam bloquear suplementos se necessário. Os principais princípios de suplementos do Office em relação à habilitação de proteção de dados incluem:

-   Fornecer uma maneira para os administradores de TI bloquearem o carregamento dos suplementos.

-   Minimizar ou eliminar o trabalho exigido pelos administradores para deixar os suplementos prontos para empresa.

-   Minimizar os prompts e mensagens para usuários finais durante o uso do suplemento.

-   Eliminar os prompts para os usuários finais quando o documento e o suplemento têm o mesmo contexto.

## <a name="add-ins-and-wip"></a>Suplementos e WIP

Quando você habilita a WIP em seu ambiente, pode habilitar os cenários a seguir para seus suplementos do Office:

-   Os suplementos do Office são ativados usando o contexto do documento. Para o Outlook, o contexto para o suplemento é baseado na caixa de correio ativa atual. As permissões do suplemento são claramente definidas no prompt de confiança antes de o suplemento ser ativado. O usuário decide se o suplemento é apropriado em um documento específico e se deseja permitir que o suplemento seja executado.

-   Os administradores podem usar a política de grupo para bloquear todos os suplementos da Office Store ou todos os suplementos do Office. Isso significa que os usuários podem ativar somente suplementos confiáveis de um [catálogo corporativo do SharePoint ou do Office 365](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog).

-   Os administradores podem bloquear os suplementos no nível de firewall usando o MDM (gerenciamento de dispositivo móvel). Observe que isso não funciona para cenários de dispositivos móveis ou de BYOD (Traga seu próprio dispositivo).

-   Os suplementos aplicam a operação de copiar e colar entre os contextos empresarial e pessoal. Por exemplo, quando um usuário copia de um suplemento de contexto empresarial e cola em um documento pessoal, o prompt da ação de copiar e colar padrão entre contextos é exibido.

A tabela a seguir lista o comportamento esperado do suplemento em documentos e contextos pessoais e empresariais quando a WIP está habilitada.

> [!NOTE]
> - As operações de recortar, copiar e colar dentro e fora do aplicativo host funcionam como esperado em todos os cenários.
> - A transferência de dados para serviços de suplemento não é protegida em todos os cenários.

|**Tipo de documento ou caixa de correio**|**Suplemento no contexto pessoal**|**Suplemento no contexto empresarial**|
|:----------------|:-------------------------------------------------|:---------------------------------------------------|
|**Pessoal**     |O suplemento é carregado no contexto pessoal.<br><br>Não é permitida a navegação para URLs corporativas (mesmo se for em seu próprio domínio de aplicativo).<br><br>A navegação para URLS pessoais é permitida|O suplemento falha ao carregar ou ativar.<br><br>Se o contexto do documento for elevado (por exemplo: salvando-o em um local da empresa):<br><br>- A navegação para URLs corporativas é permitida.<br><br>- A navegação para URLs pessoais é permitida.|
|**Empresarial**   |O suplemento é carregado no contexto empresarial.<br><br>A navegação para URLs corporativas é permitida.<br><br>A navegação para URLs pessoais é permitida.|O suplemento é carregado no contexto empresarial.<br><br>A navegação para URLs corporativas é permitida.<br><br>A navegação para URLs pessoais é permitida.|
|**Não salvos**      |O suplemento é carregado no contexto pessoal.<br><br>Não é permitida a navegação para URLs corporativas (mesmo se for em seu próprio domínio de aplicativo).<br><br>A navegação para URLs pessoais é permitida.|O suplemento é carregado no contexto empresarial e o documento é convertido silenciosamente para o contexto empresarial. Isso significa que o documento deve ser salvo em um local empresarial.<br><br>A navegação para URLs corporativas é permitida. A navegação para URLs pessoais é permitida.            |


## <a name="add-ins-and-intune"></a>Suplementos e Intune

No Office para iPad, os suplementos do Office no momento têm suporte para Word, Excel e PowerPoint. Outlook atualmente dá suporte a suplementos no iOS (iPad e iPhone). Os administradores do Outlook podem desligar os suplementos por padrão, incluindo suplementos instalados pelo desenvolvedor e habilitar somente os suplementos específicos aprovados por sua organização. A tabela a seguir descreve o suporte para cenários de proteção de dados para suplementos em execução no Office para dispositivos iOS que usam as ferramentas de proteção de aplicativo do Intune.

> [!NOTE]
> Para obter informações sobre os suplementos do Outlook em execução em dispositivos Android e iOS, consulte [Gerenciar o acesso de usuário aos suplementos para Outlook](https://technet.microsoft.com/library/jj943757(v=exchg.150).aspx) e [Suplementos para Outlook](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx).

|**Tipo de documento ou caixa de correio**|**Suplementos no contexto pessoal para iOS com a Proteção de Aplicativo do Intune<sup>*</sup>**|**Suplementos no contexto empresarial para iOS com a Proteção de Aplicativo do Intune<sup>*</sup>**|
|:-----|:-----|:-----|
|**Pessoal**|O uso de suplementos não é afetado pela proteção de aplicativo do Intune em documentos pessoais.|O uso de suplementos não é afetado pela proteção de aplicativo do Intune em documentos pessoais.|
|**Empresarial**|Suplementos pessoais podem ser ativados.<br><br>As políticas de proteção do aplicativo do Intune podem proteger os cenários de recorte, cópia, colagem e transferência de dados entre o suplemento e outros aplicativos no dispositivo.<br><br>A transferência de dados para serviços de suplemento não é protegida.|Suplementos empresariais podem ser ativados. Os administradores podem controlar quais suplementos são publicados por meio de ferramentas de gerenciamento do Office [(Implantação centralizada no Office 365)](https://support.office.com/article/Deploy-Office-add-ins-in-the-Office-365-admin-center-737e8c86-be63-44d7-bf02-492fa7cd9c3f).<br><br>As políticas de proteção do aplicativo do Intune podem proteger os cenários de recorte, cópia, colagem e transferência de dados entre o suplemento e outros aplicativos no dispositivo.<br><br>A transferência de dados para serviços de suplemento não é protegida.|

>**<sup>*</sup>** Os administradores podem usar a [Implantação centralizada do Office 365](https://support.office.com/article/Deploy-Office-add-ins-in-the-Office-365-admin-center-737e8c86-be63-44d7-bf02-492fa7cd9c3f) para implantar suplementos do Word, Excel e PowerPoint para usuários individuais, grupos ou uma organização diretamente do Centro de administração do Office 365 ou usando scripts PowerShell. Quando os usuários abrem um aplicativo do Office no Windows, Mac ou Office Online, o suplemento é instalado automaticamente em sua faixa de opções.

## <a name="summary"></a>Resumo

Considerando os princípios em relação aos suplementos do Office, a WIP e o Intune permitem que os administradores gerenciem os dados empresariais e forneçam as ferramentas que os usuários finais precisam para realizar seu trabalho. Isso cria a possibilidade de os dados empresariais vazarem para fora dos limites da organização. As APIs JavaScript do Office no momento não fornecem uma maneira de os desenvolvedores reconhecerem o tipo de dados sendo transmitido entre o suplemento e o documento do Office. Isso exige que os desenvolvedores tragam à tona vários prompts para o usuário e em alguns casos marquem erroneamente arquivos pessoais como arquivos empresariais, o que pode ter um efeito negativo na experiência do usuário e não se alinha com os princípios de proteção de dados.

A Microsoft está comprometida em proteger os dados do cliente e continuará a investir em tornar as tecnologias do Intune e da WIP e a experiência melhores para os clientes.

## <a name="learn-more"></a>Saiba mais

-   [Diretrizes gerais e práticas recomendadas para WIP (Proteção de Informações do Windows)](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/guidance-and-best-practices-wip)

-   [O que é o Intune?](https://docs.microsoft.com/intune/introduction-intune)

-   [Visão geral dos métodos de registro do dispositivo](https://docs.microsoft.com/sccm/mdm/plan-design/device-enrollment-methods)

-   [Alterar sua autoridade de MDM](https://docs.microsoft.com/sccm/mdm/deploy-use/change-mdm-authority)

-   [Prepare-se para configurar as políticas de proteção do aplicativo para Windows 10](https://docs.microsoft.com/intune-classic/deploy-use/get-ready-to-configure-app-protection-policies-for-windows-10)
