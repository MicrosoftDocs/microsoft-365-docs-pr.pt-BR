---
title: Operações e monitoramento da Área de Trabalho Gerenciada da Microsoft
description: Quem faz o que para vários processos de alteração
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 3e56066f0b4e63fc9b73bbecf5aaa3180ffd2e4f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920415"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Operações e monitoramento da Área de Trabalho Gerenciada da Microsoft

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Gerenciamento de alterações

Em um oferta de serviços, o equilíbrio de responsabilidade sobre coisas como a manutenção de hardware e atualizações de segurança passa para o provedor de serviços (Microsoft) em vez do cliente (você). No entanto, você ainda precisa garantir que o software não Microsoft e personalizado continue a funcionar conforme o esperado quando as atualizações são roladas.

Para produtos locais, sua organização assume toda a responsabilidade pelo gerenciamento de alterações.

### <a name="balance-of-responsibility"></a>Equilíbrio de responsabilidade

Capacidade de resposta | Serviço de Área de Trabalho Gerenciada da Microsoft | Software cliente do Microsoft 365 | Servidores e clientes locais | não Microsoft e software personalizado
----- | ----- | ----- | ----- | -----
Fornecer nova funcionalidade | Microsoft | Microsoft | Ambos | Cliente
Testar novos recursos para o controle de qualidade |  Microsoft | Microsoft | Ambos | Cliente
Comunicar sobre os novos recursos | Ambos | Ambos | Ambos | Cliente
Integrar software personalizado | Ambos | Ambos | Cliente | Cliente
Aplicar atualizações de segurança | Microsoft | Microsoft | Cliente | Cliente
Manter o software do sistema | Microsoft | Microsoft | Cliente | Cliente
Pacote para implantação | Microsoft | Microsoft | Cliente | Cliente


### <a name="change-process-overview"></a>Visão geral do processo de alteração

Veja um resumo de como o processo de alteração é compartilhado entre a Microsoft e os clientes: 



<table>
<tr><th></th><th><p>Função da Microsoft:</p></th><th><p>Função do cliente:</p></th></tr>
<tr><td>Antes de uma alteração</td><td><ul><li>Definir as expectativas para alterações de serviço.</li><li>Notifique os clientes com 5 dias de antecedência para alterações que exigem a ação do administrador.</li><li>Para alterações de emergência, aplique uma mitigação antes de notificar.</li></ul></td><td><ul><li>Entender o que esperar de alterações e comunicações.</li><li>Leia o Centro de Mensagens da Área de Trabalho Gerenciada da Microsoft regularmente.</li><li>Revisas e atualizar os processos internos de gerenciamento de alterações.</li><li>Entenda e verifique a conformidade com os requisitos da Área de Trabalho Gerenciada da Microsoft. </li><li>Confirme e aprove, quando necessário.</li></ul></td></tr><tr><td>Durante uma alteração</td><td><ul><li>Liberar e implantar atualizações mensais de segurança e não segurança para clientes windows 10 e Office 365.</li><li>Monitorar sinais de dados e filas de suporte para impacto.</li></ul></td><td><ul><li>Verifique o Centro de Mensagens da Área de Trabalho Gerenciada da Microsoft e revise quaisquer informações adicionais.</li><li>   Tome qualquer ação necessária, se aplicável, e teste aplicativos.</li><li>Se um cenário de quebra/correção for experimentado, crie uma solicitação de Suporte.</li></ul></td></tr><tr><td>Após uma alteração</td><td><ul><li>Coletar comentários do cliente para melhorar a adoção de alterações futuras.</li><li>Monitorar sinais de dados e filas de suporte para impacto.</li></ul></td><td><ul><li>Trabalhe com pessoas em sua organização para adotar a alteração.</li><li>   Revise os processos de gerenciamento de alterações e adoção para obter oportunidades para obter eficiência.</li><li>Forneça comentários gerais e comentários específicos na ferramenta de comentários do administrador.</li><li>Treine os usuários para fornecer comentários específicos do aplicativo usando o Hub de Feedback do Windows e o botão Desarminho nos aplicativos do Office.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Tipos de alteração

Há vários tipos de alterações que fazemos no serviço regularmente. O canal de comunicação para essas alterações e as ações pelas que você é responsável varia.

Nem todas as alterações têm o mesmo impacto sobre os usuários ou exigem ação. Algumas são planejadas e outras não planejadas por sua natureza (as atualizações não de segurança e as atualizações de segurança geralmente não são planejadas). Dependendo do tipo de alteração, o canal de comunicação pode variar. A tabela a seguir lista os tipos de alterações que você pode esperar para o serviço de Área de Trabalho Gerenciada da Microsoft.

|   | Funcionalidade |   Atualizações não relacionadas à segurança |  Segurança
--- | --- | --- | ---
**Tipo de alteração** | - Atualizações de recursos<br>- Novos recursos ou aplicativos<br>- Recursos preterido | Hotfixes de cliente para problemas | Atualizações de segurança
**Aviso com antecedência** | Aviso de cinco dias para alterações que exigem ação | Não, essas alterações são incluídas na versão mensal    | Não, as alterações são incluídas na versão mensal 
**Canal de comunicação** | - Central de Mensagens<br>- Alerta de email | - Central de Mensagens<br>- Alerta de email | - Central de Mensagens<br>- Alerta de email
**Requer ação de administrador global** | Às vezes |  Raramente |    Raramente 
**Tipo de ação** | Alterar configurações | Comunicar alterações aos usuários | Alterar configurações de administração     
**Requer testes** | Verificar aplicativos de negócios, incluindo serviços de acesso remoto |  Às vezes – testando a correção em relação a processos ou personalizações |   Raramente 
**Exemplos de alteração** | - Atualizações de recursos: Envio e revisão simplificados de tíquete de suporte do Portal de Administração de IT<br>- Novos recursos ou aplicativos: Semi-Annual versão de uma atualização de recursos do Windows 10 | Hotfixes baseados em bugs relatados pelo cliente |  


## <a name="standard-operating-procedures"></a>Procedimentos operacionais padrão

O serviço de Área de Trabalho Gerenciada da Microsoft é implementado e operado pela Microsoft em sua instância de nuvem da Microsoft, onde você pode conduzir outras atividades administrativas. A Microsoft é a única responsável pela configuração, configuração e operação específicas da Área de Trabalho Gerenciada da Microsoft. 

Para produtos locais, sua organização assume toda a responsabilidade pelo gerenciamento de configuração e configuração e atividades operacionais.

Categories |    A Microsoft irá | O cliente irá
--- | --- | ---
Rede (proxy, inspeção de pacotes, VPN)  | Aconselhá-lo e planejar com os clientes para minimizar o risco para os usuários comerciais. | - Crie uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para a Microsoft revisar.<br>- Aplique apenas uma alteração depois que As Operações de Área de Trabalho Gerenciadas da Microsoft foram avaliadas e aconselhadas.
Contas de serviço |- Implemente, armazene e gerencie com segurança as credenciais.<br> - Comunique o acesso não autorizado ou o uso dessas credenciais à sua equipe de Operações de Segurança. | - Crie uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para a Microsoft revisar.<br>- Aplique apenas uma alteração depois que As Operações de Área de Trabalho Gerenciadas da Microsoft foram avaliadas e aconselhadas.<br>- Não atribua política, autenticação multifator, acesso condicional ou implantação de aplicativo às Contas de Serviço de Área de Trabalho Gerenciada da Microsoft.<br>- Não redefinir a senha ou usar as credenciais.<br>– Abra uma solicitação de suporte do Sev C para Operações de Área de Trabalho Gerenciadas da Microsoft se atividade suspeita for observada nos logs de auditoria do Intune ou do Azure, relacionados a essas contas de serviço.
Grupos de dispositivos | - Implemente e gerencie a associação de dispositivos em grupos da Área de Trabalho Gerenciada da Microsoft.<br>- Use os grupos da Área de Trabalho Gerenciada da Microsoft para gerenciar a atribuição e a versão de configuração e atualizações para dispositivos. | - Crie uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para a Microsoft revisar.<br>- Aplique apenas uma alteração depois que As Operações de Área de Trabalho Gerenciadas da Microsoft foram avaliadas e aconselhadas.<br>- Não modifique a associação de nenhum grupo da Área de Trabalho Gerenciada da Microsoft.<br>- Use apenas os grupos para atribuir certificados corporativos para serviços como VPN, Windows Hello para Empresas ou criptografia de email ou configuração de perfil Wi-Fi corporativa.<br>- Onde o co-gerenciamento existe, exclua explicitamente todos os grupos da Área de Trabalho Gerenciada da Microsoft ao implantar o cliente do Configuration Manager.
Políticas |  - Implemente e gerencie as políticas da Área de Trabalho Gerenciada da Microsoft que governam o estado de configuração dos dispositivos no serviço.<br>- Implantar atualizações, na política ou no Windows, usando grupos de dispositivos incrementalmente.<br> - Exclua explicitamente o direcionamento de grupos que não são da Área de Trabalho Gerenciada da Microsoft. | - Crie uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para a Microsoft revisar.<br>- Aplique apenas uma alteração depois que As Operações de Área de Trabalho Gerenciadas da Microsoft foram avaliadas e aconselhadas.<br>- Não edite ou atribua políticas de Área de Trabalho Gerenciada da Microsoft a dispositivos ou usuários não gerenciados pelo serviço de Área de Trabalho Gerenciada da Microsoft.
Microsoft Defender para Ponto de Extremidade | Monitore e investigue dispositivos no escopo do serviço de Área de Trabalho Gerenciada da Microsoft. | - Crie uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para a Microsoft revisar.<br>- Aplicar somente uma alteração depois que As Operações de Área de Trabalho Gerenciadas da Microsoft foram avaliadas e aconselhadas
Microsoft Store para empresas |  Configure e mantenha o perfil do Windows Autopilot para o serviço de Área de Trabalho Gerenciada da Microsoft. | - Crie uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para a Microsoft revisar.<br>- Aplique apenas uma alteração depois que As Operações de Área de Trabalho Gerenciadas da Microsoft foram avaliadas e aconselhadas.<br>- Não modifique a configuração do perfil do Microsoft Managed Desktop Windows Autopilot ou adicione/remova dispositivos atribuídos.
Certificados | | - Crie uma solicitação de suporte 60 dias antes de um certificado expirar, solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para a Microsoft revisar.<br>- Aplique apenas uma alteração depois que As Operações de Área de Trabalho Gerenciadas da Microsoft foram avaliadas e aconselhadas.<br>- Atualize todos os certificados necessários para configurar perfis de certificado, perfis VPN e Wi-Fi perfis.




## <a name="device-wipe-with-factory-reset"></a>Apagar dispositivo com redefinição de fábrica

A equipe de Operações de Área de Trabalho Gerenciada da Microsoft pode executar uma redefinição de fábrica dos dispositivos inscritos no serviço quando necessário. A redefinição é útil se você precisar dar um dispositivo a um funcionário diferente ou se um funcionário sair da empresa. 

Há alguns requisitos:

- O administrador global deve enviar uma solicitação de serviço.
- Inclua o nome do computador do dispositivo na solicitação.
- A conta de usuário deve estar no Azure AD antes de redefinirmos o dispositivo.

A equipe de Operações de Área de Trabalho Gerenciada fará o seguinte:

- Procure o nome do dispositivo no Intune
- Enviar o comando de redefinição de fábrica para o dispositivo

>[!NOTE]
>Não remova a conta de usuário do Azure AD antes que o dispositivo seja redefinido. Se o usuário não estiver no Azure AD, o Intune não poderá enviar o comando de redefinição de fábrica para o dispositivo. 

O dispositivo será inicializado na "experiência fora da caixa", e todos os aplicativos e configurações pré-instalados serão aplicados novamente. O usuário do dispositivo precisa fornecer informações iniciais de configuração novamente. 

Quando o dispositivo for redefinido, você poderá dá-lo a uma pessoa diferente em sua organização. Nenhum dos dados do usuário anterior ou dados corporativos estará no dispositivo. O próximo usuário passará pelo mesmo processo que a pessoa anterior fez com um novo dispositivo da Área de Trabalho Gerenciada da Microsoft.

O BitLocker é um componente-chave da segurança de dados neste processo. Com a criptografia BitLocker em dispositivos da Área de Trabalho Gerenciada da Microsoft, os dados na unidade permanecem seguros mesmo depois que o dispositivo foi redefinido de fábrica. Todos os dados que estava na unidade não estarão disponíveis para o próximo usuário do dispositivo. Para obter mais informações, consulte [Visão geral do BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview).

Para obter mais informações, consulte [Factory reset a device](/intune/remote-actions/devices-wipe#factory-reset-a-device).