---
title: Monitoramento e operações de área de trabalho gerenciada da Microsoft
description: ''
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1cd620206f559e6870c6706fc0e40f4b7e45bc84
ms.sourcegitcommit: 7bb340f6b47378bcd1c6e770dc975931470bbc26
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/10/2020
ms.locfileid: "43225892"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Monitoramento e operações de área de trabalho gerenciada da Microsoft

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Gerenciamento de alterações

Em um oferta de serviços, o equilíbrio de responsabilidade sobre coisas como a manutenção de hardware e atualizações de segurança passa para o provedor de serviços (Microsoft) em vez do cliente (você). No entanto, você ainda precisará garantir que o software de terceiros e o personalizado continuem funcionando conforme o esperado quando as atualizações são implantadas.

Para produtos locais, sua organização assume todas as responsabilidades de gerenciamento de alterações.

### <a name="balance-of-responsibility"></a>Equilíbrio de responsabilidade

Responsabilidade | Serviço de área de trabalho gerenciada da Microsoft | Software cliente Microsoft 365 | Servidores e clientes locais | software de terceiros e personalizado
----- | ----- | ----- | ----- | -----
Fornecer nova funcionalidade | Microsoft | Microsoft | Ambos | Cliente
Testar novos recursos para o controle de qualidade |  Microsoft | Microsoft | Ambos | Cliente
Comunicar sobre os novos recursos | Ambos | Ambos | Ambos | Cliente
Integrar software personalizado | Ambos | Ambos | Cliente | Cliente
Aplicar atualizações de segurança | Microsoft | Microsoft | Cliente | Cliente
Manter o software do sistema | Microsoft | Microsoft | Cliente | Cliente
Pacote para implantação | Microsoft | Microsoft | Cliente | Cliente


### <a name="change-process-overview"></a>Visão geral do processo de alteração

Aqui está um resumo de como o processo de alteração é compartilhado entre a Microsoft e os clientes. 



<table>
<tr><th></th><th><p>Função da Microsoft:</p></th><th><p>Função do cliente:</p></th></tr>
<tr><td>Antes de uma alteração</td><td><ul><li>Definir as expectativas para alterações de serviço.</li><li>Notifique os clientes 5 dias antes das alterações que exigem a ação do administrador.</li><li>Para alterações de emergência, aplique uma mitigação antes de notificá-lo.</li></ul></td><td><ul><li>Entender o que esperar de alterações e comunicações.</li><li>Leia o centro de mensagens de área de trabalho gerenciada da Microsoft regularmente.</li><li>Revisas e atualizar os processos internos de gerenciamento de alterações.</li><li>Entenda e verifique a conformidade com os requisitos de área de trabalho gerenciada da Microsoft. </li><li>Confirme e aprove, quando necessário.</li></ul></td></tr><tr><td>Durante uma alteração</td><td><ul><li>Liberar e implantar atualizações mensais de segurança e de não segurança para clientes do Windows 10 e do Office 365.</li><li>Monitorar sinais de dados e filas de suporte para obter impacto.</li></ul></td><td><ul><li>Verifique o centro de mensagens de área de trabalho gerenciada da Microsoft e revise as informações adicionais.</li><li>   Execute qualquer ação necessária, se aplicável, e teste aplicativos.</li><li>Se um cenário de interrupção/correção for experiente, crie uma solicitação de suporte.</li></ul></td></tr><tr><td>Após uma alteração</td><td><ul><li>Coletar comentários dos clientes para melhorar a distribuição de alterações futuras.</li><li>Monitorar sinais de dados e filas de suporte para obter impacto.</li></ul></td><td><ul><li>Trabalhe com pessoas em sua organização para adotar a alteração.</li><li>   Revise os processos de gerenciamento de alterações e adoção para oportunidades de obter eficiência.</li><li>Forneça comentários gerais e comentários específicos sobre a ferramenta de comentários de administrador.</li><li>Treinar os usuários para fornecer comentários específicos do aplicativo usando o Hub de comentários do Windows e o botão de sorriso em aplicativos do Office.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Tipos de alteração

Há vários tipos de alterações que são feitas no serviço periodicamente. O canal de comunicação para essas alterações e as ações pelas quais os clientes são responsáveis varia.

Nem todas as alterações têm o mesmo impacto sobre os usuários ou exigem ação. Alguns são planejados e alguns não planejados pela natureza (atualizações não relacionadas a segurança e atualizações de segurança não costumam ser planejadas). Dependendo do tipo de alteração, o canal de comunicação pode variar. A tabela a seguir lista os tipos de alterações que você pode esperar para o serviço de área de trabalho gerenciada da Microsoft.

|   | Função |   Atualizações não relacionadas à segurança |  Segurança
--- | --- | --- | ---
**Tipo de alteração** | – Atualizações de recursos<br>– Novos recursos ou aplicativos<br>-Recursos preteridos | Hotfixes de cliente para problemas | Patches de segurança
**Aviso com antecedência** | um aviso de cinco dias para alterações que exigem ação |    Não, eles estão incluídos na versão mensal   | Não, eles estão incluídos na versão mensal 
**Canal de comunicação** | -Central de mensagens<br>– Alerta de email | -Central de mensagens<br>– Alerta de email | -Central de mensagens<br>– Alerta de email
**Requer ação de administração global** | Às vezes |  Raramente |    Raramente 
**Tipo de ação** | Alterar configurações | Comunicar alterações aos usuários | Alterar configurações de administração     
**Requer testes** | Verificar aplicativos de negócios, incluindo serviços de acesso remoto |  Às vezes – testando a correção em relação a processos ou personalizações |   Raramente 
**Exemplos de alteração** | – Atualizações de recursos: portal de administração de ti simplificado envio e análise de tíquete de suporte<br>– Novos recursos ou aplicativos: lançamento semestral de uma atualização de recurso do Windows 10 | Hotfixes baseados em bugs relatados pelo cliente |  


## <a name="standard-operating-procedures"></a>Procedimentos operacionais padrão

O serviço de área de trabalho gerenciada da Microsoft é implementado e operado pela Microsoft na instância de nuvem da Microsoft, onde você pode realizar outras atividades administrativas. A Microsoft é exclusivamente responsável pela instalação, pela configuração e pela operação específica da área de trabalho gerenciada pela Microsoft. 

Para produtos locais, sua organização assume todas as responsabilidades de gerenciamento de configuração e atividades operacionais e de configuração.

Categorias |    A Microsoft irá | Cliente será
--- | --- | ---
Rede (proxy, inspeção de pacote, VPN)  | Avisar e planejar com os clientes para minimizar o risco para os usuários de negócios. | – Criar uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para a Microsoft revisar.<br>– Aplicar uma alteração somente depois que as operações de área de trabalho gerenciada pela Microsoft tiverem sido avaliadas e recomendadas.
Contas de serviço |– Implemente, armazene e gerencie as credenciais com segurança.<br> – Comunique o acesso não autorizado ou use essas credenciais para a equipe de operações de segurança. | – Criar uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para a Microsoft revisar.<br>– Aplicar uma alteração somente depois que as operações de área de trabalho gerenciada pela Microsoft tiverem sido avaliadas e recomendadas.<br>– Não atribua política, autenticação multifator, acesso condicional ou implantação de aplicativo para as contas de serviço de área de trabalho gerenciada da Microsoft.<br>-Não redefina a senha ou use as credenciais.<br>– Abra uma solicitação de suporte do Sev C para operações de área de trabalho gerenciada da Microsoft, caso seja observada atividade suspeita nos logs de auditoria do Intune ou Azure, relacionadas a essas contas de serviço.
Grupos de dispositivos | – Implemente e gerencie a associação de dispositivos nos grupos da área de trabalho gerenciada da Microsoft.<br>– Use os grupos de área de trabalho gerenciada da Microsoft para gerenciar a atribuição e a versão de configuração e atualizações para dispositivos. | – Criar uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para a Microsoft revisar.<br>– Aplicar uma alteração somente depois que as operações de área de trabalho gerenciada pela Microsoft tiverem sido avaliadas e recomendadas.<br>– Não modificar a associação de qualquer grupo de área de trabalho gerenciada da Microsoft.<br>– Use somente os grupos para atribuir certificados corporativos para serviços como VPN, Windows Hello para Business ou criptografia de email ou configuração de perfil de Wi-Fi corporativos.<br>-Onde existe o cogerenciamento, exclua explicitamente todos os grupos da área de trabalho gerenciado da Microsoft ao implantar o cliente do Configuration Manager.
Políticas |  – Implemente e gerencie as políticas de área de trabalho gerenciada da Microsoft que regem o estado de configuração dos dispositivos no serviço.<br>– Implantar atualizações, política ou janelas, usando grupos de dispositivos de forma incremental.<br> -Excluir explicitamente os grupos de área de trabalho gerenciada não Microsoft de direcionamento. | – Criar uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para a Microsoft revisar.<br>– Aplicar uma alteração somente depois que as operações de área de trabalho gerenciada pela Microsoft tiverem sido avaliadas e recomendadas.<br>-Não edite ou atribua políticas de área de trabalho gerenciada da Microsoft a dispositivos ou usuários não gerenciados pelo serviço de área de trabalho gerenciada da Microsoft.
Proteção Avançada contra Ameaças do Microsoft Defender   | Monitore e investigue os dispositivos dentro do escopo do serviço de área de trabalho gerenciada da Microsoft. | – Criar uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para a Microsoft revisar.<br>-Aplicar uma alteração somente depois que as operações de área de trabalho gerenciada pela Microsoft tiverem sido avaliadas e recomendadas
Microsoft Store para empresas |  Configurar e manter o perfil do Windows AutoPilot para o serviço de área de trabalho gerenciada da Microsoft. | – Criar uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para a Microsoft revisar.<br>– Aplicar uma alteração somente depois que as operações de área de trabalho gerenciada pela Microsoft tiverem sido avaliadas e recomendadas.<br>-Não modifique a configuração do perfil do Microsoft AutoPilot da área de trabalho gerenciada do Windows ou adicione/remova dispositivos atribuídos.
Certificados | | -Criar uma solicitação de suporte 60 dias antes da expiração de um certificado, solicitando informações para uma alteração de configuração planejada, incluindo detalhes da configuração, escopo, linha do tempo e outros detalhes pertinentes para a Microsoft revisar.<br>– Aplicar uma alteração somente depois que as operações de área de trabalho gerenciada pela Microsoft tiverem sido avaliadas e recomendadas.<br>– Atualizar todos os certificados necessários para configurar perfis de certificado, perfis VPN e perfis Wi-Fi.




## <a name="device-wipe-with-factory-reset"></a>Apagamento de dispositivos com redefinição de fábrica

A equipe de operações de área de trabalho gerenciada da Microsoft pode executar uma restauração de fábrica de dispositivos registrados no serviço quando necessário. Isso será útil se você precisar fornecer um dispositivo para um funcionário diferente ou se um funcionário sair da sua empresa. 

Há alguns requisitos:

- O administrador global deve enviar uma solicitação de serviço.
- Inclua o nome do computador do dispositivo na solicitação.
- A conta de usuário deve estar no Azure AD antes de reiniciar o dispositivo.

A equipe de operações de área de trabalho gerenciada fará o seguinte:

- Pesquisar o nome do dispositivo no Intune
- Enviar o comando de redefinição de fábrica ao dispositivo

>[!NOTE]
>Não remova a conta de usuário do Azure AD antes de o dispositivo ser redefinido. Se o usuário não estiver no Azure AD, o Intune não poderá enviar o comando de redefinição de fábrica ao dispositivo. 

O dispositivo será inicializado na "experiência inicial" e todos os aplicativos e configurações pré-instalados serão aplicados novamente. O usuário do dispositivo precisa fornecer informações iniciais de configuração novamente. 

Quando o dispositivo tiver sido redefinido, você poderá fornecê-lo a uma pessoa diferente na sua organização. Nenhum dos dados do usuário anterior ou dados da empresa estarão no dispositivo. O próximo usuário passará pelo mesmo processo que a pessoa anterior fazia com um novo dispositivo de área de trabalho gerenciada pela Microsoft.

O BitLocker é um componente essencial da segurança dos dados nesse processo. Com a criptografia BitLocker nos dispositivos de área de trabalho gerenciada da Microsoft, os dados na unidade permanecem seguros, mesmo após o dispositivo como redefinição de fábrica. Os dados que estavam na unidade não estarão disponíveis para o próximo usuário do dispositivo. Para obter mais informações, consulte [visão geral do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).

Para obter mais informações, consulte [redefinição de fábrica de um dispositivo](https://docs.microsoft.com/intune/remote-actions/devices-wipe#factory-reset-a-device). 
