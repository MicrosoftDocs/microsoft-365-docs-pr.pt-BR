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
ms.openlocfilehash: 5d7c6a7b836d0044ba9cde188170dd51f117dd2b
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840368"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Operações e monitoramento da Área de Trabalho Gerenciada da Microsoft

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Gerenciamento de alterações

Em um oferta de serviços, o equilíbrio de responsabilidade sobre coisas como a manutenção de hardware e atualizações de segurança passa para o provedor de serviços (Microsoft) em vez do cliente (você). No entanto, você ainda precisa garantir que softwares não Microsoft e personalizados continuam a funcionar conforme o esperado quando as atualizações são lançados.

Para produtos locais, sua organização assume toda a responsabilidade pelo gerenciamento de alterações.

### <a name="balance-of-responsibility"></a>Equilíbrio de responsabilidade

Capacidade de resposta | Serviço de Área de Trabalho Gerenciada da Microsoft | Software cliente do Microsoft 365 | Servidores e clientes locais | software não Microsoft e personalizado
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
<tr><td>Antes de uma alteração</td><td><ul><li>Definir as expectativas para alterações de serviço.</li><li>Notifique os clientes com cinco dias de antecedência sobre alterações que exigem ação do administrador.</li><li>Para alterações de emergência, aplique uma mitigação antes de notificar.</li></ul></td><td><ul><li>Entender o que esperar de alterações e comunicações.</li><li>Leia o Centro de Mensagens da Área de Trabalho Gerenciada da Microsoft regularmente.</li><li>Revisas e atualizar os processos internos de gerenciamento de alterações.</li><li>Entenda e verifique a conformidade com os requisitos da Área de Trabalho Gerenciada da Microsoft. </li><li>Confirme e aprove, quando necessário.</li></ul></td></tr><tr><td>Durante uma alteração</td><td><ul><li>Lançar e implantar atualizações mensais de segurança e que não são de segurança para clientes do Windows 10 e do Office 365.</li><li>Monitore sinais de dados e filas de suporte para impacto.</li></ul></td><td><ul><li>Verifique o Centro de Mensagens da Área de Trabalho Gerenciada da Microsoft e revise todas as informações adicionais.</li><li>   Tome qualquer ação necessária, se aplicável, e teste os aplicativos.</li><li>Se um cenário de quebra/correção for experimentado, crie uma solicitação de suporte.</li></ul></td></tr><tr><td>Após uma alteração</td><td><ul><li>Colete comentários dos clientes para melhorar a adoção de futuras alterações.</li><li>Monitore sinais de dados e filas de suporte para impacto.</li></ul></td><td><ul><li>Trabalhe com pessoas em sua organização para adotar a alteração.</li><li>   Revise os processos de gerenciamento de mudanças e adoção para oportunidades para obter eficiência.</li><li>Forneça comentários gerais e comentários específicos na ferramenta de comentários do administrador.</li><li>Treine os usuários para fornecer comentários específicos do aplicativo usando o Hub do Windows Feedback e o botão Feliz nos aplicativos do Office.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Tipos de alteração

Há vários tipos de alterações que fazemos regularmente no serviço. O canal de comunicação para essas alterações e as ações pelas que você é responsável varia.

Nem todas as alterações têm o mesmo impacto sobre os usuários ou exigem ação. Algumas são planejadas e outras não planejadas por sua natureza (atualizações não de segurança e atualizações de segurança geralmente não são planejadas). Dependendo do tipo de alteração, o canal de comunicação pode variar. A tabela a seguir lista os tipos de alterações que você pode esperar para o serviço de Área de Trabalho Gerenciada da Microsoft.

|   | Funcionalidade |   Atualizações não relacionadas à segurança |  Segurança
--- | --- | --- | ---
**Tipo de alteração** | - Atualizações de recursos<br>- Novos recursos ou aplicativos<br>- Recursos preterido | Hotfixes de cliente para problemas | Atualizações de segurança
**Aviso com antecedência** | Aviso de cinco dias para alterações que exigem ação | Não, essas alterações são incluídas na versão mensal    | Não, as alterações são incluídas na versão mensal 
**Canal de comunicação** | - Centro de Mensagens<br>- Alerta de email | - Centro de Mensagens<br>- Alerta de email | - Centro de Mensagens<br>- Alerta de email
**Requer ação de administrador global** | Às vezes |  Raramente |    Raramente 
**Tipo de ação** | Alterar configurações | Comunicar alterações aos usuários | Alterar configurações de administração     
**Requer testes** | Verificar aplicativos de negócios, incluindo serviços de acesso remoto |  Às vezes – testando a correção em relação a processos ou personalizações |   Raramente 
**Exemplos de alteração** | - Atualizações de recursos: envio e revisão de tíquetes de suporte simplificados do Portal de Administração de IT<br>- Novos recursos ou aplicativos: Semi-Annual versão de uma atualização de recursos do Windows 10 | Hotfixes baseados em bugs relatados pelo cliente |  


## <a name="standard-operating-procedures"></a>Procedimentos operacionais padrão

O serviço área de trabalho gerenciada da Microsoft é implementado e operado pela Microsoft em sua instância de nuvem da Microsoft, onde você pode realizar outras atividades administrativas. A Microsoft é a única responsável pela instalação, configuração e operação específicas da Área de Trabalho Gerenciada da Microsoft. 

Para produtos locais, sua organização assume toda a responsabilidade pelo gerenciamento da instalação, configuração e atividades operacionais.

Categorias |    A Microsoft irá | O cliente irá
--- | --- | ---
Rede (proxy, inspeção de pacotes, VPN)  | Aconselhá-lo e planejar com os clientes para minimizar o risco para os usuários comerciais. | - Crie uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para análise da Microsoft.<br>- Aplique uma alteração somente depois que as Operações da Área de Trabalho Gerenciada da Microsoft avaliarem e aconselhá-la.
Contas de serviço |- Implemente, armazene e gerencie com segurança as credenciais.<br> - Comunique o acesso não autorizado ou o uso dessas credenciais à sua equipe de Operações de Segurança. | - Crie uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para análise da Microsoft.<br>- Aplique uma alteração somente depois que as Operações da Área de Trabalho Gerenciada da Microsoft avaliarem e aconselhá-la.<br>- Não atribua política, autenticação multifator, acesso condicional ou implantação de aplicativos às Contas de Serviço de Área de Trabalho Gerenciada da Microsoft.<br>- Não redefinir a senha ou usar as credenciais.<br>- Abra uma solicitação de suporte de Sev C para operações da Área de Trabalho Gerenciada da Microsoft se atividades suspeitas são observadas nos logs de auditoria do Intune ou do Azure, relacionados a essas contas de serviço.
Grupos de dispositivos | – Implemente e gerencie a associação de dispositivos em grupos da Área de Trabalho Gerenciada da Microsoft.<br>- Use os grupos da Área de Trabalho Gerenciada da Microsoft para gerenciar a atribuição e a versão de configuração e atualizações para dispositivos. | - Crie uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para análise da Microsoft.<br>- Aplique uma alteração somente depois que as Operações da Área de Trabalho Gerenciada da Microsoft avaliarem e aconselhá-la.<br>- Não modifique a associação de nenhum grupo da Área de Trabalho Gerenciada da Microsoft.<br>- Use somente os grupos para atribuir certificados corporativos para serviços como VPN, Windows Hello para Empresas ou criptografia de email ou configuração de perfil de Wi-Fi corporativa.<br>- Onde o co-gerenciamento existe, exclua explicitamente todos os grupos da Área de Trabalho Gerenciada da Microsoft ao implantar o cliente do Configuration Manager.
Políticas |  – Implemente e gerencie as políticas da Área de Trabalho Gerenciada da Microsoft que regem o estado de configuração dos dispositivos dentro do serviço.<br>- Implantar atualizações, na política ou no Windows, de forma incremental usando Grupos de Dispositivos.<br> - Excluir explicitamente o direcionamento de grupos da Área de Trabalho Gerenciada que não são da Microsoft. | - Crie uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para análise da Microsoft.<br>- Aplique uma alteração somente depois que as Operações da Área de Trabalho Gerenciada da Microsoft avaliarem e aconselhá-la.<br>- Não edite ou atribua políticas da Área de Trabalho Gerenciada da Microsoft a dispositivos ou usuários não gerenciados pelo serviço de Área de Trabalho Gerenciada da Microsoft.
Microsoft Defender para Ponto de Extremidade | Monitore e investigue dispositivos dentro do escopo do serviço de Área de Trabalho Gerenciada da Microsoft. | - Crie uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para análise da Microsoft.<br>- Aplicar uma alteração somente depois que as Operações da Área de Trabalho Gerenciada da Microsoft avaliarem e aconselhá-la
Microsoft Store para empresas |  Configure e mantenha o perfil do Windows Autopilot para o serviço área de trabalho gerenciada da Microsoft. | - Crie uma solicitação de suporte solicitando informações para uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes para análise da Microsoft.<br>- Aplique uma alteração somente depois que as Operações da Área de Trabalho Gerenciada da Microsoft avaliarem e aconselhá-la.<br>- Não modifique a configuração do perfil do Windows Autopilot da Área de Trabalho Gerenciada da Microsoft ou adicione/remova dispositivos atribuídos.
Certificados | | - Crie uma solicitação de suporte 60 dias antes da expiração de um certificado, solicitando informações sobre uma alteração de configuração planejada, incluindo detalhes de configuração, escopo, linha do tempo e outros detalhes pertinentes que a Microsoft deve analisar.<br>- Aplique uma alteração somente depois que as Operações da Área de Trabalho Gerenciada da Microsoft avaliarem e aconselhá-la.<br>- Atualize todos os certificados necessários para configurar perfis de certificado, perfis VPN e Wi-Fi certificados.




## <a name="device-wipe-with-factory-reset"></a>Apagaamento de dispositivo com redefinição de fábrica

A equipe de Operações de Área de Trabalho Gerenciada da Microsoft pode executar uma redefinição de fábrica dos dispositivos inscritos no serviço quando necessário. A redefinição é útil se você precisar dar um dispositivo a um funcionário diferente ou se um funcionário sair da empresa. 

Existem alguns requisitos:

- O administrador global deve enviar uma solicitação de serviço.
- Inclua o nome do computador do dispositivo na solicitação.
- A conta de usuário deve estar no Azure AD antes de redefinirmos o dispositivo.

A equipe de Operações de Área de Trabalho Gerenciada fará o seguinte:

- Procurar o nome do dispositivo no Intune
- Enviar o comando de redefinição de fábrica para o dispositivo

>[!NOTE]
>Não remova a conta de usuário do Azure AD antes que o dispositivo seja redefinido. Se o usuário não estiver no Azure AD, o Intune não poderá enviar o comando de redefinição de fábrica para o dispositivo. 

O dispositivo será inicializado na "experiência inicial", e todos os aplicativos e configurações pré-instalados serão aplicados novamente. O usuário do dispositivo precisa fornecer informações iniciais de configuração novamente. 

Quando o dispositivo tiver sido redefinido, você poderá dá-lo a uma pessoa diferente em sua organização. Nenhum dos dados do usuário anterior ou dados corporativos estará no dispositivo. O próximo usuário passará pelo mesmo processo que a pessoa anterior fez com um novo dispositivo de Área de Trabalho Gerenciada da Microsoft.

O BitLocker é um componente essencial da segurança de dados nesse processo. Com a criptografia BitLocker em dispositivos da Área de Trabalho Gerenciada da Microsoft, os dados na unidade permanecem seguros mesmo após o dispositivo ter sido redefinido de fábrica. Todos os dados que estava na unidade não estarão disponíveis para o próximo usuário do dispositivo. Para obter mais informações, consulte [a visão geral do BitLocker.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)

Para obter mais informações, consulte [Redefinição de fábrica de um dispositivo.](https://docs.microsoft.com/intune/remote-actions/devices-wipe#factory-reset-a-device) 