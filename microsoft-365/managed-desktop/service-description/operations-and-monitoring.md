---
title: Operações do Microsoft Desktop gerenciados e monitoramento
description: ''
keywords: Serviço Microsoft Managed Desktop, 365 da Microsoft, documentação
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 00bdc95c191ce16be219cf0dc251f72eaf054e22
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864853"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Operações do Microsoft Desktop gerenciados e monitoramento

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Gerenciamento de alterações

Microsoft e clientes compartilharão gerenciamento de alterações para o serviço Microsoft Desktop gerenciados. Responsabilidades são diferentes para um serviço online versus um servidor local ou do cliente. 

### <a name="change-process-overview"></a>Visão geral do processo de alteração

Aqui está um resumo de como o processo de alteração é compartilhado entre a Microsoft e os clientes. 



<table>
<tr><th></th><th><p>A Microsoft irá:</p></th><th><p>Os clientes serão:</p></th></tr>
<tr><td>Antes de uma alteração</td><td><ul><li>Notifica os clientes 5 dias com antecedência para que as alterações que exigem ação do administrador.</li><li>Para alterações de emergência, aplique uma redução de risco antes da informando.</li></ul></td><td><ul><li>Leia e compreenda o e-mail de notificação.</li><li>Reconhecer e aprovar, quando necessário.</li></ul></td></tr><tr><td>Durante uma alteração</td><td><ul><li>Implantar alteração para Windows 10 e o Office, versão atualizações de segurança e não relacionadas à segurança, conforme necessário.</li><li>Monitorar telemetria e encaminhamento de suporte para problemas inesperados.</li></ul></td><td><ul><li>Gerencie o processo de gerenciamento de alterações interno.</li><li>Crie uma solicitação de suporte, se necessário.</li></ul></td></tr><tr><td>Após uma alteração</td><td><ul><li>Colete comentários de clientes para melhorar a distribuição das alterações futuras.</li><li>Monitorar telemetria e encaminhamento de suporte para problemas inesperados.</li></ul></td><td><ul><li>Leia e compreenda o e-mail de notificação.</li><li>Fornecer comentários gerais e comentários específicos na ferramenta de administração de comentários.</li><li>Treinar usuários para fornecer comentários de aplicativo específico usando o Hub de comentários do Windows e o botão de Smiley nos aplicativos do Office.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Tipos de alteração

Há vários tipos de alterações feitas ao serviço regularmente. O canal de comunicação para essas alterações e as ações que os clientes são responsáveis pela varia.

Os seguintes tipos de alterações podem ser esperados:

Tipo de alteração | Notificação | Ação de cliente
--- | --- | ---
Atualizações de recurso e novos componentes de serviço | Email | -Alterar aos usuários se comuniquem<br><br> -Act conforme exigido pela Microsoft<br><br> -Ação deve ser realizada em 48 horas
Segurança atualizações, atualizações mensais e configurações de linha de base | Email, boletim de segurança ou entrada vulnerabilidades comuns e exposições (CVE) | -Atualizações serão implantadas usando a nossa [estratégia de gerenciamento de atualização](updates.md)de segurança mensal.<br><br> -Configurações para reduzir as ameaças serão implantadas para toda a organização para proteger a organização. (ISSO NÃO PARECE SER DE UMA AÇÃO DO CLIENTE)
Atualizações de qualidade, incluindo hotfixes, atualizações de serviço e não relacionadas à segurança impacto diretiva de linha de base | Email | Informará quando necessário.
Atualizações de emergência: necessários de atualizações de software, configuração ou serviço a atenuar:<br><br> -Riscos de segurança crítico<br><br> -Perda de dados<br><br> -Acesso aos dados de telemetria de gerenciamento de dispositivos do Microsoft Desktop gerenciados | Informará quando necessário.

## <a name="standard-operating-procedures"></a>Procedimentos operacionais padrão

Esse serviço é implementado e operado pela Microsoft em um ambiente onde você realizar outras atividades administrativas. A Microsoft está exclusivamente responsável pela instalação, configuração e operação da Microsoft Managed específicos da área de trabalho. 

Para produtos de local, sua organização tem toda a responsabilidade de gerenciamento operacional e atividades de configuração.

Categories |    Ações
--- | ---
Contas de serviço |  A Microsoft irá:<br><br> -Implemente, com segurança armazenar e gerenciar as credenciais<br><br> -Comunicar o uso dessas credenciais para a sua equipe de operações de segurança ou acesso não autorizado<br><br><br><br>Os clientes serão:<br><br> -Abrir uma solicitação de suporte informativos com operações de área de trabalho do Microsoft gerenciados ao planejar uma alteração que pode afetar as contas<br><br> -Não atribuir a diretiva, a autenticação multifator, acesso condicional ou implantação de aplicativos para as contas de serviço de área de trabalho gerenciada do Microsoft<br><br> -Não redefinir a senha ou use as credenciais<br><br> -Abrir uma solicitação de suporte para operações de área de trabalho gerenciada do Microsoft Sev C se atividades suspeitas é observada em logs de auditoria Intune ou Azure, relacionados a essas contas de serviço
Grupos de dispositivos | A Microsoft irá:<br><br> -Implementar e gerenciar a associação de dispositivos dentro dos grupos de área de trabalho do Microsoft gerenciados<br><br> -Use os grupos do Microsoft Desktop gerenciados para gerenciar a atribuição e a versão de configuração e atualizações de dispositivos<br><br><br><br>Os clientes serão:<br><br> -Abrir uma solicitação de suporte informativos com operações de área de trabalho do Microsoft gerenciados ao planejar uma alteração que pode afetar os grupos<br><br> -Não modifique a associação de qualquer grupo Microsoft Desktop gerenciados<br><br> -Usar apenas os grupos para atribuir certificados corporativos para serviços, como a VPN, Windows Olá para criptografia de email ou de negócios ou configuração de perfil corporativa Wi-Fi<br><br> -Onde o gerenciamento de colegas existe, explicitamente excluir todos os grupos do Microsoft Desktop gerenciados ao implantar o cliente do Gerenciador de configuração
Diretivas |  A Microsoft irá:<br><br> -Implementar e gerenciar as políticas de Microsoft Desktop gerenciados que governam o estado de configuração de dispositivos dentro do serviço<br><br> -Implantar atualizações, a política ou Windows, incrementalmente usando grupos de dispositivos<br><br> -Explicitamente excluir grupos de não - Microsoft Managed Desktop direcionamento<br><br><br><br>Cliente será:<br><br> -Abrir um tíquete de suporte informativos com operações de área de trabalho do Microsoft gerenciados ao planejar uma alteração que pode afetar o estado de configuração desejada de dispositivos<br><br> -Não editar ou atribuir políticas de Microsoft Desktop gerenciados para dispositivos ou usuários que não é gerenciados pelo serviço Microsoft Desktop gerenciados
Proteção Avançada Contra Ameaças do Windows Defender | A Microsoft irá:<br><br> -Monitorar e investigar dispositivos dentro do escopo do serviço Microsoft Desktop gerenciados<br><br><br><br>Cliente será:<br><br> -Abrir um tíquete de suporte informativos com operações de área de trabalho do Microsoft gerenciados ao planejar uma alteração que pode afetar os recursos de monitoramento ou investigação do Microsoft Managed Desktop Security Operations Center
Microsoft Store para Empresas |  A Microsoft irá:<br><br> -Configurar e manter o perfil de piloto automático do Windows para o serviço Microsoft Desktop gerenciados<br><br><br><br>Cliente será:<br><br> -Abrir um tíquete de suporte informativos com operações de área de trabalho do Microsoft gerenciados ao planejar uma alteração que abrir pode afetar o acesso ao repositório de ou modificar o perfil do Microsoft Managed Desktop Windows piloto automático<br><br> -Não modifique a configuração do perfil do Microsoft Managed Desktop Windows piloto automático ou adicionar/remover dispositivos atribuídos
Certificados |  Cliente será:<br><br> -Abrir um tíquete de suporte informativos com Microsoft Managed Desktop operações 60 dias antes de qualquer certificado expirando<br><br> -Atualizar todos os certificados que são necessárias para configurar: perfis, os perfis VPN e Wi-Fi perfis de certificado



## <a name="device-wipe-with-factory-reset"></a>Apagamento do dispositivo com a restauração de fábrica

Equipe de operações de área de trabalho gerenciado pode fazer um alocador redefinida em dispositivos gerenciados pelo Microsoft Desktop gerenciados que precisam ser criada. Isso é útil se você precisa fornecer um dispositivo a um funcionário diferente, ou se um funcionário deixa a sua empresa. 

Existem alguns requisitos:

- Administrador de locatário do cliente deve enviar uma solicitação de serviço
- Precisamos o nome do computador para o dispositivo
- Conta de usuário deve estar no Azure AD antes que fazemos a redefinição

Equipe de operações de área de trabalho gerenciada será:

- Procure o nome do dispositivo no Intune
- Enviar que comando de redefinição de fábrica ao dispositivo

>[!NOTE]
>Não remova a conta de usuário do Windows Azure AD antes da restauração de fábrica. Se o usuário não estiver no Azure AD, Intune não pode enviar que o alocador de redefinir o comando para o dispositivo. 

O dispositivo será carregado OOBE e todos os aplicativos pré-instalados e configurações serão aplicadas novamente. O usuário do dispositivo precisa fornecer inicial Configure informações novamente. 

Quando o dispositivo for redefinido, você pode atribuir a uma pessoa diferente em sua organização. Nenhum dos dados ou os dados da empresa do usuário anteriores estará no dispositivo. O próximo usuário modificará o mesmo processo que a pessoa anterior efetuou com um novo dispositivo de área de trabalho do Microsoft gerenciados.

O BitLocker é um componente essencial da segurança dos dados nesse processo. Com a criptografia de BitLocker em dispositivos Microsoft Desktop gerenciado, os dados na unidade permanecem seguros mesmo após a restauração de fábrica tiver sido aplicada ao dispositivo. Todos os dados que estava na unidade não estará disponíveis para o próximo usuário do dispositivo. Para obter mais informações, consulte [Visão geral de disco BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).

Para obter mais informações, consulte a [restauração de fábrica um dispositivo](https://docs.microsoft.com/intune/devices-wipe#factory-reset-a-device). 
