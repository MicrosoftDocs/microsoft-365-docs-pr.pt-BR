---
title: Operações do Microsoft Desktop gerenciados e monitoramento
description: ''
keywords: Serviço Microsoft Managed Desktop, 365 da Microsoft, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 12/18/2018
ms.openlocfilehash: 66945d44df150b5be9af9a9dfe52daa4d7468298
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864853"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Operações do Microsoft Desktop gerenciados e monitoramento

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Gerenciamento de alterações

Em um oferta de serviços, o equilíbrio de responsabilidade para itens como a segurança e a manutenção do hardware atualizações deslocado para o provedor de serviço (Microsoft) em vez do cliente (você). No entanto, você ainda precisará garantir que terceiros e software personalizado continua a funcionar como esperado quando atualizações são distribuídas.

Para produtos de local, sua organização assume toda a responsabilidade de gerenciamento de alteração.

### <a name="balance-of-responsibility"></a>Balanceamento de responsabilidade

Capacidade de resposta | Serviço Microsoft Desktop gerenciados | Software de cliente do Microsoft 365 | Servidores e clientes locais | 3º participante e software personalizado
----- | ----- | ----- | ----- | -----
Fornecer nova funcionalidade | Microsoft | Microsoft | Ambos | Cliente
Testar novos recursos para o controle de qualidade |  Microsoft | Microsoft | Ambos | Cliente
Comunicar sobre os novos recursos | Ambos | Ambos | Ambos | Cliente
Integrar software personalizado | Ambos | Ambos | Cliente | Cliente
Aplicar atualizações de segurança | Microsoft | Microsoft | Cliente | Cliente
Manter o software do sistema | Microsoft | Microsoft | Cliente | Cliente
Pacote de implantação | Microsoft | Microsoft | Cliente | Cliente


### <a name="change-process-overview"></a>Visão geral do processo de alteração

Aqui está um resumo de como o processo de alteração é compartilhado entre a Microsoft e os clientes. 



<table>
<tr><th></th><th><p>Função da Microsoft:</p></th><th><p>Função do cliente:</p></th></tr>
<tr><td>Antes de uma alteração</td><td><ul><li>Definir as expectativas para alterações de serviço.</li><li>Notifica os clientes 5 dias com antecedência para que as alterações que exigem ação do administrador.</li><li>Para alterações de emergência, aplique uma redução de risco antes da informando.</li></ul></td><td><ul><li>Entender o que esperar de alterações e comunicações.</li><li>Leitura gerenciados Desktop mensagem Centro Microsoft regularmente.</li><li>Revisas e atualizar os processos internos de gerenciamento de alterações.</li><li>Entender e verifique a conformidade com os requisitos de Microsoft Desktop gerenciados. </li><li>Reconhecer e aprovar, quando necessário.</li></ul></td></tr><tr><td>Durante uma alteração</td><td><ul><li>Liberar e implantar atualizações de segurança e não relacionadas à segurança mensais para clientes Windows 10 e o Office 365.</li><li>Monitore os sinais de dados e filas de suporte para o impacto.</li></ul></td><td><ul><li>Verifique a Microsoft Managed Desktop Message Center e revise as informações adicionais.</li><li>   Executar qualquer ação que necessário, se aplicável e teste de aplicativos.</li><li>Se um cenário de quebra/correção é apresentaram, crie uma solicitação de suporte.</li></ul></td></tr><tr><td>Após uma alteração</td><td><ul><li>Colete comentários de clientes para melhorar a distribuição das alterações futuras.</li><li>Monitore os sinais de dados e filas de suporte para o impacto.</li></ul></td><td><ul><li>Trabalhar com pessoas da sua organização para adotar a alteração.</li><li>   Revise os processos de gerenciamento de alteração e adoção de oportunidades de eficiência.</li><li>Fornecer comentários gerais e comentários específicos na ferramenta de administração de comentários.</li><li>Treinar usuários para fornecer comentários de aplicativo específico usando o Hub de comentários do Windows e o botão de Smiley nos aplicativos do Office.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Tipos de alteração

Há vários tipos de alterações feitas ao serviço regularmente. O canal de comunicação para essas alterações e as ações que os clientes são responsáveis pela varia.

Nem todas as alterações tenham o mesmo impacto sobre os usuários ou exigem ação. Alguns são alguns planejadas e por sua própria natureza (atualizações não relacionadas à segurança e atualizações de segurança não são geralmente planejadas). Dependendo do tipo de alteração, o canal de comunicação pode variar. A tabela a seguir lista os tipos de alterações que você pode esperar para o serviço Microsoft Desktop gerenciados.

|   | Funcionalidade |   Atualizações que não são de segurança |  Segurança
--- | --- | --- | ---
**Tipo de alteração** | -Atualizações recurso<br>-Novos recursos ou aplicativos<br>-Recursos preteridos | Hotfixes de cliente para problemas | Patches de segurança
**Notificação prévia** | Aviso de cinco dias para que as alterações que exigem ação |    Não, essas informações serão incluídas na versão mensal   | Não, essas informações serão incluídas na versão mensal 
**Canal de comunicação** | -Centro message<br>-Alerta email | -Centro message<br>-Alerta email | -Centro message<br>-Alerta email<br>-Boletim de segurança do ou CVE 
**Requer a ação do administrador de locatário** | Às vezes |  Raramente |    Raramente 
**Tipo de ação** | Alterar configurações | Comunicar alterações aos usuários | Alterar configurações de administração     
**Requer testes** | Verifique os aplicativos de negócios, incluindo serviços de acesso remoto |  Às vezes – testando a correção em relação a processos ou personalizações |   Raramente 
**Exemplos de alteração** | -Atualizações de recursos: Portal de administração de TI simplificado revisão e envio de tíquete de suporte<br>-Novos recursos ou aplicativos: semi-estruturados anual lançamento de uma atualização de recurso do Windows 10 | Hotfixes baseados em bugs relatados pelo cliente |  


## <a name="standard-operating-procedures"></a>Procedimentos operacionais padrão

O serviço Microsoft Desktop gerenciados é implementado e operado pela Microsoft em sua instância de nuvem da Microsoft onde é possível conduzir outras atividades administrativas. A Microsoft está exclusivamente responsável pela instalação, configuração e operação da Microsoft Managed específicos da área de trabalho. 

Para produtos de local, sua organização tem toda a responsabilidade de gerenciamento de configuração e a configuração e atividades operacionais.

Categories |    A Microsoft irá | Cliente será
--- | --- | ---
Rede (proxy, inspeção de pacotes, VPN)  | Aviso e planeje com clientes para minimizar os riscos aos usuários corporativos. | -Crie uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, cronograma e outros detalhes pertinentes para a Microsoft analisar.<br>-Se aplicam somente uma alteração depois que operações de área de trabalho do Microsoft gerenciados tem avaliou e aconselhado.
Contas de serviço |-Implemente, com segurança armazenar e gerenciar as credenciais.<br> -Se comunicar uso dessas credenciais para a sua equipe de operações de segurança ou acesso não autorizado. | -Crie uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, cronograma e outros detalhes pertinentes para a Microsoft analisar.<br>-Se aplicam somente uma alteração depois que operações de área de trabalho do Microsoft gerenciados tem avaliou e aconselhado.<br>-Não atribua política, a autenticação multifator, acesso condicional ou implantação de aplicativos para as contas de serviço de área de trabalho gerenciada do Microsoft.<br>-Não redefinir a senha ou use as credenciais.<br>-Abra uma solicitação de suporte de Sev C para operações de área de trabalho gerenciada da Microsoft se atividades suspeitas é observada em logs de auditoria Intune ou Azure, relacionados a essas contas de serviço.
Grupos de dispositivos | -Implementar e gerenciar a associação de dispositivos dentro dos grupos de área de trabalho do Microsoft gerenciados.<br>-Use os grupos do Microsoft Desktop gerenciados para gerenciar a atribuição e a versão de configuração e atualizações de dispositivos. | -Crie uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, cronograma e outros detalhes pertinentes para a Microsoft analisar.<br>-Se aplicam somente uma alteração depois que operações de área de trabalho do Microsoft gerenciados tem avaliou e aconselhado.<br>-Não modifique a associação de qualquer grupo Microsoft Desktop gerenciados.<br>-Use apenas os grupos para atribuir certificados corporativos para serviços, como a VPN, Windows Olá para criptografia de email ou de negócios ou configuração de perfil corporativa Wi-Fi.<br>-Onde colegas gerenciamento existe, explicitamente excluir todos os grupos do Microsoft Desktop gerenciados ao implantar o cliente do Gerenciador de configuração.
Diretivas |  -Implementar e gerenciar as políticas de Microsoft Desktop gerenciados que governam o estado de configuração de dispositivos dentro do serviço.<br>-Implante atualizações, política ou Windows, incrementalmente usando grupos de dispositivos.<br> -Explicitamente exclua grupos de não - Microsoft Managed Desktop direcionamento. | -Crie uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, cronograma e outros detalhes pertinentes para a Microsoft analisar.<br>-Se aplicam somente uma alteração depois que operações de área de trabalho do Microsoft gerenciados tem avaliou e aconselhado.<br>-Não editar ou atribuir políticas de Microsoft Desktop gerenciados para dispositivos ou usuários que não é gerenciados pelo serviço Microsoft Desktop gerenciados.
Proteção Avançada Contra Ameaças do Windows Defender | Monitorar e investigar dispositivos dentro do escopo do serviço Microsoft Desktop gerenciados. | -Crie uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, cronograma e outros detalhes pertinentes para a Microsoft analisar.<br>-Se aplicam somente uma alteração depois que operações de área de trabalho do Microsoft gerenciados tem avaliou e aconselhado
Microsoft Store para Empresas |  Configurar e manter o perfil de piloto automático do Windows para o serviço Microsoft Desktop gerenciados. | -Crie uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, cronograma e outros detalhes pertinentes para a Microsoft analisar.<br>-Se aplicam somente uma alteração depois que operações de área de trabalho do Microsoft gerenciados tem avaliou e aconselhado.<br>-Não modifique a configuração do perfil do Microsoft Managed Desktop Windows piloto automático ou adicionar/remover dispositivos atribuídos.
Certificados | | -Crie uma solicitação de suporte 60 dias antes de um certificado expirando, solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, cronograma e outros detalhes pertinentes para a Microsoft analisar.<br>-Se aplicam somente uma alteração depois que operações de área de trabalho do Microsoft gerenciados tem avaliou e aconselhado.<br>-Atualize todos os certificados que são necessários para configurar perfis de certificado, os perfis VPN e Wi-Fi perfis.




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

Quando o dispositivo for redefinido, você pode atribuir a uma pessoa diferente em sua organização. Nenhum dos dados ou os dados da empresa do usuário anterior será no dispositivo. O próximo usuário modificará o mesmo processo que a pessoa anterior efetuou com um novo dispositivo de área de trabalho do Microsoft gerenciados.

O BitLocker é um componente essencial da segurança dos dados nesse processo. Com a criptografia de BitLocker em dispositivos Microsoft Desktop gerenciado, os dados na unidade permanecem seguros mesmo após a restauração de fábrica tiver sido aplicada ao dispositivo. Todos os dados que estava na unidade não estará disponíveis para o próximo usuário do dispositivo. Para obter mais informações, consulte [Visão geral de disco BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).

Para obter mais informações, consulte a [restauração de fábrica um dispositivo](https://docs.microsoft.com/intune/devices-wipe#factory-reset-a-device). 
