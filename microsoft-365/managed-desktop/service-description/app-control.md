---
title: Controle de aplicativo
description: Como usar o controle de aplicativo e confiar em aplicativos
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6f5cc923b5a18b1f45dd186e88228db8c3a891cc
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841298"
---
# <a name="app-control"></a>Controle de aplicativo

O controle de aplicativo é uma prática de segurança opcional na Área de Trabalho Gerenciada da Microsoft que restringe a execução de código em dispositivos cliente. Esse controle reduz o risco de malware ou scripts mal-intencionados, exigindo que somente o código assinado por uma lista de editores aprovada pelo cliente possa ser executado. Há muitos benefícios de segurança desse controle, mas ele visa principalmente proteger os dados e a identidade contra explorações baseadas no cliente.

A Área de Trabalho Gerenciada da Microsoft simplifica o gerenciamento de políticas de controle de aplicativo criando uma política base que habilita os principais cenários de produtividade. Você pode estender a confiança para outros signatários específicos para os aplicativos e scripts em seu ambiente. 


Qualquer tecnologia de segurança exige um equilíbrio entre a experiência do usuário, a segurança e o custo. O controle de aplicativo reduz a ameaça de software mal-intencionado em seu ambiente, mas há consequências para o usuário e outras ações para seu administrador de IT.

**Segurança adicional:**

Aplicativos ou scripts que não são confiáveis pela política de controle de aplicativo são impedidos de ser executados em dispositivos.

**Suas responsabilidades adicionais:**

- Você é responsável por testar seus aplicativos para identificar se eles seriam bloqueados pela política de controle de aplicativo.
- Se um aplicativo for (ou seria bloqueado), você é responsável por identificar os detalhes de signante necessários e solicitar uma alteração por meio do portal de administração.

**Responsabilidades da Área de Trabalho Gerenciada da Microsoft:**

- A Área de Trabalho Gerenciada da Microsoft mantém a política base que habilita os principais produtos da Microsoft, como aplicativos do M365, Windows, Teams, OneDrive e assim por diante.
- A Área de Trabalho Gerenciada da Microsoft insere seus signatários confiáveis e implanta a política atualizada em seus dispositivos.


## <a name="managing-trust-in-applications"></a>Gerenciando a confiança em aplicativos

A Área de Trabalho Gerenciada da Microsoft reúne uma política base que confia nos principais componentes das tecnologias da Microsoft. Em *seguida, você* adiciona confiança para seus próprios aplicativos e scripts informando a Área de Trabalho Gerenciada da Microsoft em quais deles você já confia.

### <a name="base-policy"></a>Política base

A Área de Trabalho Gerenciada da Microsoft, em colaboração com especialistas em segurança cibernética da Microsoft, cria e mantém uma política padrão que habilita a maioria dos aplicativos implantados por meio do Microsoft Intune enquanto bloqueia atividades perigosas, como compilação de código ou execução de arquivos não confidenciais.

A política base tem a seguinte abordagem para restringir a execução de software:

- Os arquivos executados pelos administradores poderão ser executados.
- Arquivos em locais que *não estão em* diretórios que podem ser executados pelo usuário poderão ser executados.
- Os arquivos são assinados por [um signante confiável.](#signer-requests)
- A maioria dos arquivos assinados pela Microsoft será executado, no entanto, alguns são bloqueados para impedir ações de alto risco, como compilação de código.


Se um usuário diferente de um administrador puder ter adicionado um aplicativo ou script a um dispositivo (ou seja, ele está em um diretório que pode ser escrito pelo usuário), não permitiremos que ele seja executado, a menos que ele já tenha sido especificamente permitido por um administrador. Se um usuário for tentado instalar malware, se uma vulnerabilidade em um aplicativo que o usuário executa tentar instalar malware ou se um usuário tentar executar intencionalmente um aplicativo ou script não autorizado, nossa política interromperá a execução.

### <a name="signer-requests"></a>Solicitações do signante

Você nos informa quais aplicativos são fornecidos por editores de software em que você confia, apresentando uma *solicitação de signatário.* Ao fazer isso, adicionamos essas informações de confiança à política de controle do aplicativo de linha de base e permitimos que qualquer software assinado com o certificado desse editor seja executado em seus dispositivos.

## <a name="audit-and-enforced-policies"></a>Políticas auditadas e impostas

A Área de Trabalho Gerenciada da Microsoft usa duas políticas do Microsoft Intune para fornecer controle de aplicativo:

### <a name="audit-policy"></a>Política de auditoria
Essa política cria logs para registrar se um aplicativo ou script seria bloqueado pela política imposta. As políticas de auditoria não impõem regras de controle de aplicativo e são destinadas a fins de teste para identificar se um aplicativo exigirá uma isenção do editor. Ele registra avisos (eventos 8003 ou 8006) no Visualizador de Eventos em vez de bloquear a execução ou a instalação de aplicativos ou scripts especificados.

### <a name="enforced-policy"></a>Política imposta
Essa política impede a execução de scripts e aplicativos não-confiançados e cria logs sempre que um aplicativo ou script é bloqueado. As políticas impostas impedem que os usuários padrão executem aplicativos ou scripts armazenados em diretórios que podem ser gravados pelo usuário.

Os dispositivos no grupo Teste têm uma política de auditoria aplicada para que você possa usá-los para validar se algum aplicativo causará problemas. Todos os outros grupos (Primeiro, Rápido e Amplo) usam uma política imposta, para que os usuários nesses grupos não sejam capazes de executar scripts ou aplicativos não-confiança.







