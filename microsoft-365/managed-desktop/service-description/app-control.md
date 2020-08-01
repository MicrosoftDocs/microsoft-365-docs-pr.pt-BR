---
title: Controle de aplicativos
description: ''
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: f11c7a4aa69c96232a33c565e7bf20d04b96d1f7
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529966"
---
# <a name="app-control"></a>Controle de aplicativos

O controle de aplicativos é uma prática de segurança opcional na área de trabalho gerenciada da Microsoft que restringe a execução de código em dispositivos cliente. Esse controle reduz o risco de malware ou scripts mal-intencionados exigindo que apenas o código assinado por uma lista de editores aprovada pelo cliente possa ser executado. Há muitos benefícios de segurança desse controle, mas destina-se principalmente a proteger dados e identidades de explorações baseadas no cliente.

O Microsoft Managed desktop simplifica o gerenciamento de políticas de controle de aplicativos criando uma política de base que permite cenários de produtividade principal. Você pode estender a confiança para os assinadores adicionais que são específicos para os aplicativos e scripts em seu ambiente. 


Qualquer tecnologia de segurança requer um equilíbrio entre a experiência do usuário, a segurança e o custo. O controle de aplicativos reduz a ameaça de software mal-intencionado em seu ambiente, mas há conseqüências para o usuário final e ações adicionais para seu administrador de ti.

**Segurança adicional:**

Os aplicativos ou scripts que não são confiáveis pela política de controle de aplicativos são impedidos de serem executados em dispositivos.

**Suas responsabilidades adicionais:**

- Você é responsável por testar seus aplicativos para identificar se eles serão bloqueados pela política de controle de aplicativos.
- Se um aplicativo estiver bloqueado, você será responsável por identificar os detalhes necessários do signatário e solicitar uma alteração por meio do portal de administração.

**Responsabilidades de área de trabalho gerenciada da Microsoft:**

- A área de trabalho gerenciada da Microsoft mantém a política básica que permite os principais produtos da Microsoft, como aplicativos do M365, Windows, Teams, OneDrive e assim por diante.
- A área de trabalho gerenciada da Microsoft insere seus assinantes confiáveis e implanta a política atualizada para seus dispositivos.


## <a name="managing-trust-in-applications"></a>Gerenciando a confiança em aplicativos

O Microsoft Managed desktop organizada uma política básica que confia nos principais componentes das tecnologias da Microsoft. Em seguida, você *adiciona* confiança para seus próprios aplicativos e scripts, informando a área de trabalho gerenciada da Microsoft de que você já confia.

### <a name="base-policy"></a>Política de base

A área de trabalho gerenciada da Microsoft, em colaboração com especialistas do Microsoft cybersecurity, cria e mantém uma política padrão que permite que a maioria dos aplicativos implantados por meio do Microsoft Intune bloqueie atividades perigosas, como compilação de código ou execução de arquivos não confiáveis.

A política básica utiliza a seguinte abordagem para restringir a execução do software:

- Os arquivos executados por administradores poderão ser executados.
- Arquivos em locais que *não* estejam em diretórios graváveis pelo usuário poderão ser executados.
- Os arquivos são assinados por um [signatário confiável](#signer-requests).
- A maioria dos arquivos assinados pela Microsoft será executada, mas alguns serão bloqueados para impedir ações de alto risco, como a compilação de código.


[! Importante] se um usuário que não seja um administrador tiver adicionado um aplicativo ou script a um dispositivo (ou seja, ele está em um diretório de usuário gravável), não permitiremos que ele seja executado, a menos que ele já tenha sido especificamente permitido por um administrador. Se um usuário for enganado para tentar instalar o malware, se uma vulnerabilidade em um aplicativo que o usuário executa tentar instalar o malware ou se um usuário tentar executar um aplicativo ou script não autorizado, nossa política interromperá a execução.

### <a name="signer-requests"></a>Solicitações de signatário

Você nos informa quais aplicativos são fornecidos pelos fornecedores de software em que confia por meio da criação de uma *solicitação de signatário*. Ao fazer isso, adicionamos as informações de confiança à política de controle de aplicativos da linha de base e permitem que qualquer software assinado com o certificado do fornecedor seja executado em seus dispositivos.

## <a name="audit-and-enforced-policies"></a>Políticas de auditoria e impostos

O Microsoft Managed desktop usa duas políticas do Microsoft Intune para fornecer controle de aplicativos:

### <a name="audit-policy"></a>Política de auditoria
Essa política cria logs para registrar se um aplicativo ou script será bloqueado pela política imposta. As políticas de auditoria não impõem regras de controle de aplicativos e são direcionadas para fins de teste para identificar se um aplicativo exigirá uma isenção de fornecedor. Ele registra avisos (8003 ou 8006 eventos) no Visualizador de eventos, em vez de bloquear a execução ou a instalação de aplicativos ou scripts especificados.

### <a name="enforced-policy"></a>Política imposta
Essa política bloqueia a execução de aplicativos e scripts não confiáveis e cria logs sempre que um aplicativo ou script é bloqueado. As políticas impostas impedem que os usuários padrão executem aplicativos ou scripts armazenados em diretórios graváveis pelo usuário.

Os dispositivos no grupo de teste têm uma política de auditoria aplicada para que você possa usá-los para validar se algum aplicativo causará problemas. Todos os outros grupos (primeiro, rápido e amplo) usam uma política imposta, portanto, os usuários finais desses grupos não poderão executar aplicativos ou scripts não confiáveis.







