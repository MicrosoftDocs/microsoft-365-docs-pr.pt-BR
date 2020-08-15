---
title: Controles de tecnologia da Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: Este artigo fornece uma visão geral das ferramentas e tecnologias usadas pelo Microsoft for Technology Control no Microsoft 365.
ms.openlocfilehash: 53b7a05dba52fbe8c3bb8502441c67bd2be1957d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686931"
---
# <a name="microsoft-365-technology-controls"></a>Controles de tecnologia da Microsoft 365 

A Microsoft usa várias ferramentas e tecnologias para controlar, gerenciar e auditar o acesso aos dados do cliente em seus serviços online. Eles se aplicam ao Exchange Online, SharePoint Online, Lockbox e Lockbox de cliente, autenticação multifator e muito mais. O Yammer usa controles similares descritos nos [controles de acesso corporativo do Yammer](microsoft-365-yammer-enterprise-access-controls.md).

Os engenheiros da Microsoft 365 têm zero acesso de pé aos dados do cliente da Microsoft 365. Os engenheiros devem passar por um processo de aprovação da Microsoft antes que ocorra o acesso aos dados do cliente para operações de serviço. Se o cliente licenciar o recurso de lockbox de cliente para o Exchange Online e o SharePoint Online, o acesso aos dados do cliente requer a aprovação do cliente. Após a aprovação, as contas administrativas específicas de serviço são o acesso just-in-time provisionado para tarefas exigidas pela solicitação de serviço.

## <a name="lockbox-and-customer-lockbox"></a>Lockbox e Lockbox de cliente

Embora seja raro, um cliente pode solicitar assistência da Microsoft que expõe o conteúdo do cliente a um engenheiro da Microsoft. Para controlar o acesso ao Exchange Online, a Microsoft usa um sistema de controle de acesso chamado lockbox. Antes de qualquer engenheiro da Microsoft acessar qualquer sistema ou dados do Exchange Online ou do SharePoint Online, eles devem enviar uma solicitação de acesso usando o Lockbox. Todas as solicitações de serviço do Exchange Online e do SharePoint Online são tratadas pelo sistema de lockbox. Com o Lockbox e o Lockbox do cliente, todos os acessos aprovados são rastreáveis para um usuário exclusivo, tornando os engenheiros informativos sobre a manipulação dos dados dos clientes.

> [!NOTE]
> O Exchange Online inclui todos os dados do Skype for Business armazenados nas caixas de correio do usuário. A cobertura do Skype for Business não inclui gravações de transmissão de reunião do Skype ou conteúdo carregado em reuniões por usuários. O SharePoint Online inclui o OneDrive for Business.

O Lockbox processa as solicitações que concedem aos engenheiros a capacidade de executar funções operacionais e administrativas dentro do serviço. Os engenheiros enviam solicitações por meio de Lockbox, e o Microsoft Manager deve aprovar a solicitação antes que o engenheiro possa acessar dados do cliente. Após a aprovação do gerente, o engenheiro tem acesso limitado por tempo e com escopo limitado aos dados do cliente para trabalhar no problema do cliente.

O Lockbox de cliente do Microsoft 365 ajuda você a cumprir as obrigações de conformidade, caso precise de procedimentos em vigor para autorização explícita de acesso a dados. Isso é um requisito para alguns padrões de conformidade, como FedRAMP e HIPAA. O Lockbox do cliente insere você no processo de aprovação de Lockbox e fornece a capacidade de controlar a autorização do Microsoft Access para o conteúdo do Exchange Online ou do SharePoint Online para operações de serviço.

Na rara instância, quando um engenheiro de serviços da Microsoft precisa acessar seus dados, você concede acesso somente aos dados necessários para resolver o problema e por um tempo limitado. Se você rejeitar uma solicitação de acesso, os engenheiros da Microsoft não terão acesso ao seu conteúdo e não poderão concluir as operações de serviço. Se você aprovar a solicitação, os engenheiros da Microsoft têm acesso limitado de just-in-time ao conteúdo por meio de interfaces de gerenciamento restritas e monitoradas.

As ações realizadas pelo engenheiro de suporte são registradas para fins de auditoria e podem ser acessadas por meio da [API de atividade de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis) e do [centro de segurança e conformidade](https://protection.office.com/).

>[!NOTE]
> O Lockbox do cliente está disponível no [Microsoft 365 E5](https://products.office.com/business/office-365-enterprise-e5-business-software) como uma compra complementar. Para obter mais informações, consulte [solicitações de lockbox do cliente Microsoft 365](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2).

## <a name="just-in-time-access"></a>Acesso just-in-time

A Microsoft usa o princípio de acesso just-in-time (JIT) para a Microsoft 365 para reduzir os riscos de violação de credenciais e ataques laterais. O JIT remove o acesso administrativo persistente aos serviços e substitui os direitos por meio da capacidade de elevar essas funções sob demanda. A remoção dos direitos de acesso persistente dos administradores garante que as credenciais estejam disponíveis somente quando forem necessárias e reduzem os riscos de roubo de credenciais.

O modelo de acesso JIT exige que os engenheiros solicitem privilégios elevados por um período limitado para realizar tarefas administrativas. Além disso, os engenheiros usam contas temporárias criadas com senhas complexas geradas por máquina e recebem apenas as funções que permitem executar tarefas necessárias. Por exemplo, o acesso administrativo concedido pela lockbox é limitado por tempo e a quantidade de tempo que o acesso concedido depende da função solicitada. Um engenheiro especifica a duração do tempo de acesso necessário na solicitação para o sistema de lockbox. O sistema de lockbox rejeita solicitações quando o tempo solicitado excede o tempo máximo permitido para a elevação. Após a expiração, o acesso administrativo é removido e a conta temporária expira.

Quando autorizado e aprovado para acesso, os engenheiros recebem uma senha administrativa de uso único gerada pelo sistema de autorização. Novas senhas são geradas cada vez que uma solicitação de acesso elevado é aprovada. A senha é copiada em uma senha segura, é separada das credenciais do engenheiro para o ambiente corporativo da Microsoft e só é válida para a sessão de acesso elevado aprovado.

## <a name="constrained-management-interfaces"></a>Interfaces de gerenciamento restritas

Os engenheiros usam duas interfaces de gerenciamento para executar tarefas administrativas: área de trabalho remota através de gateways de serviço de terminal seguros (TSGs) e PowerShell remoto. Dentro dessas interfaces de gerenciamento, as políticas de software e os controles de acesso colocam restrições significativas em quais aplicativos são executados e quais comandos e cmdlets estão disponíveis.

Os servidores da Microsoft 365 restringem sessões simultâneas a uma sessão por administrador de equipe por serviço, por servidor. TSGs permitir apenas uma única sessão simultânea para os usuários e não permitir várias sessões. Usando uma única sessão por servidor, o TSGs permite que os administradores da equipe de serviço do Microsoft 365 se conectem a vários servidores simultaneamente para que os administradores possam efetivamente realizar suas tarefas. Os administradores da equipe de serviço não têm nenhuma permissão no TSGs. O TSG é usado apenas para impor os requisitos de criptografia e autenticação multifator (MFA). Depois que o administrador da equipe de serviço se conecta a um servidor específico por meio de um TSG, o servidor específico impõe um limite de sessão de um por administrador.

As restrições de uso e os requisitos de conexão e configuração do pessoal do Microsoft 365 são estabelecidos pelas políticas de grupo do Active Directory. Essas políticas incluem as seguintes características:

- TSGs Use apenas a criptografia validada pelo [FIPS](https://www.microsoft.com/TrustCenter/Compliance/FIPS) 140-2.
- As sessões do TSG desconectam após 30 minutos de inatividade.
- As sessões do TSG fazem logoff automaticamente após 24 horas.

As conexões com o TSGs também exigem o MFA usando um cartão inteligente físico separado e uma conta separada das credenciais corporativas da Microsoft da engenharia. Os engenheiros são emitidos diferentes cartões inteligentes para várias plataformas e as plataformas de gerenciamento de segredos garantem o armazenamento seguro de credenciais. TSGs usar as políticas de grupo do Active Directory para controlar quem pode fazer logon em servidores remotos, o número de sessões permitidas e as configurações de tempo limite de ociosidade. Políticas adicionais limitam o acesso a aplicativos permitidos e restringem o acesso à Internet.

Além do acesso remoto usando o TSGs especialmente configurado, o Exchange Online permite que os usuários com a função de operações do engenheiro de serviço acessem determinada funcionalidade administrativa em servidores de produção usando o PowerShell remoto. Para fazer isso, o usuário deve estar autorizado para acesso somente leitura (depuração) ao ambiente de produção do Microsoft 365. O escalonamento de privilégio é habilitado da mesma forma que está habilitado para o TSGs usando o processo de lockbox.

Para acesso remoto, cada datacenter tem um IP virtual com balanceamento de carga que serve como um único ponto de acesso. Os cmdlets remotos do PowerShell disponíveis são baseados no nível de privilégio identificado na declaração de acesso obtida durante a autenticação. Esses cmdlets fornecem a única funcionalidade administrativa acessível por usuários que se conectam usando este método. O PowerShell remoto limita o escopo dos comandos disponíveis para o engenheiro e se baseia no nível de acesso concedido por meio do processo de lockbox. Por exemplo, no Exchange Online, o Get-Mailbox pode estar disponível, mas Set-Mailbox não.
