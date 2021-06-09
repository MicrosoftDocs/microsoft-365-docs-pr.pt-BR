---
title: Funções e responsabilidades da Área de Trabalho Gerenciada da Microsoft
description: Este artigo descreve as funções e responsabilidades fornecidas pela Microsoft para Área de Trabalho Gerenciada da Microsoft.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 94389fbb9a13b9a880b0c4dcaf67d8adcaff0f98
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841310"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Funções e responsabilidades da Área de Trabalho Gerenciada da Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Quando sua organização está Área de Trabalho Gerenciada da Microsoft, o que a Microsoft faz para você? E quais são as responsabilidades da sua organização?

## <a name="microsofts-roles-and-responsibilities"></a>Funções e responsabilidades da Microsoft

A Microsoft fornece essas principais funções e responsabilidades:

Função ou responsabilidade | Descrição
--- | ---
Gerenciamento de política do MDM | A Microsoft aplicará políticas MDM de acordo com as práticas recomendadas e considerará solicitações de alterações na política. Também faremos alterações em seu locatário, conforme prescrito em [Políticas de dispositivo.](../service-description/device-policies.md)
suporte ao usuário | Fornecemos suporte ao usuário para dispositivos, Windows e o pacote de produtos Microsoft 365 Apps para Grandes Empresas para todos os usuários inscritos por meio do aplicativo Obter Ajuda que é pré-instalado em todos os dispositivos Área de Trabalho Gerenciada da Microsoft. 
Área de Trabalho Gerenciada da Microsoft de serviço | A Microsoft fornecerá suporte ao seu departamento de TECNOLOGIA por meio de uma equipe Área de Trabalho Gerenciada da Microsoft Operações. Essa equipe dará suporte a solução de problemas técnicos, solicitações de alteração e gerenciamento de incidentes para o ambiente de Área de Trabalho Gerenciada da Microsoft do cliente. Para obter mais informações, consulte [Suporte de administrador para Área de Trabalho Gerenciada da Microsoft](../working-with-managed-desktop/admin-support.md).
Monitoramento de segurança | A Microsoft monitorará seus Área de Trabalho Gerenciada da Microsoft usando o Microsoft Defender para Ponto de Extremidade. Se o Área de Trabalho Gerenciada da Microsoft de Operações de Segurança (SOC) detectar uma ameaça, notificaremos você, isolaremos o dispositivo e corrigiremos o problema remotamente. Para obter mais informações, consulte [Segurança](../service-description/security.md).
Atualizar monitoramento e gerenciamento | Monitoramos ativamente seus Área de Trabalho Gerenciada da Microsoft para garantir que as atualizações de recursos e qualidade mais recentes sejam instaladas para o Microsoft Windows e Microsoft Office. Para obter mais informações, consulte [Como as atualizações são tratadas.](../service-description/updates.md)
Grupo de usuários e dispositivos | Área de Trabalho Gerenciada da Microsoft equipe de operações criará e gerenciará grupos de usuários e dispositivos necessários como parte das operações de IT. Nenhuma associação ou alteração de configuração é permitida a esses grupos. Alterar esses grupos pode levar à configuração inesperada de dispositivos e à perda de funcionalidade. Para quaisquer problemas ou dúvidas em torno desses grupos depois de estabelecidos, os administradores de IT podem entrar em contato Área de Trabalho Gerenciada da Microsoft operações. Para obter mais informações, consulte [Suporte de administrador para Área de Trabalho Gerenciada da Microsoft](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Suas funções e responsabilidades

Esse conjunto de funções e responsabilidades comuns é necessário para implantação, mas não são fornecidos pela Microsoft. Não é exaustivo, mas é aplicável para a maioria das organizações. Há alguns itens que você e a Microsoft compartilham responsabilidade. 

Função ou responsabilidade | Descrição
--- | ---
Gerenciamento de alterações | A Microsoft notificará os clientes, com antecedência, quando as alterações precisarem ser feitas em seu ambiente Área de Trabalho Gerenciada da Microsoft ambiente. Para obter mais informações, consulte [alterações de serviço e comunicação.](../service-description/servicechanges.md)<br><br>Você deve ter seu próprio processo de gerenciamento de alterações e ter um contato estabelecido com a equipe Área de Trabalho Gerenciada da Microsoft Operações. Você também deve ter recursos para revisar e aprovar essas alterações. Para obter mais informações, consulte [Operations and monitoring](../service-description/operations-and-monitoring.md).  
O gerenciamento de identidades | Você é responsável por criar contas de usuário, atribuir usuários a grupos e manter os metadados atualizados. 
Microsoft 365 Apps para Grandes Empresas configuração e gerenciamento | A Microsoft é responsável por garantir Office aplicativos são implantados para usuários e esses aplicativos são mantidos atualizados. <br><br> Você é responsável pelo gerenciamento de Microsoft 365 e políticas, incluindo Exchange Online de administração:<br>- Administração de email<br>- Configuração de caixa de correio e regra<br>- Exchange gerenciamento local<br><br>Você também é responsável por ferramentas de colaboração, SharePoint administração de servidores, gerenciamento de domínio e políticas de segurança e informações definidas no centro de administração Microsoft 365 servidor. 
Suporte ao usuário | Você deve fornecer suporte ao usuário para: <br>- Infraestrutura local: toda a conectividade de rede e internet, infraestrutura VPN e configuração do cliente, equipamentos de sala de conferência local, impressoras, servidor proxy e configuração e firewalls.<br><br>- Recursos de nuvem de toda a empresa: email, SharePoint, serviços de colaboração e outra infraestrutura de nuvem relacionada ao impacto da tecnologia em toda a empresa.<br><br>- Linha de negócios e quaisquer outros aplicativos específicos da empresa.
Aplicativos | Funções e responsabilidades variam um pouco para os aplicativos fornecidos como parte Área de Trabalho Gerenciada da Microsoft versus os aplicativos que você fornece. <br><br>Para aplicativos fornecidos pela Microsoft (Microsoft 365 Apps para Grandes Empresas que compõem o Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, Teams e OneNote), a **Microsoft** fornecerá serviço completo para a implantação, atualização e suporte. **Você** deve obter e atribuir licenças para esses aplicativos, adicionar usuários a grupos de segurança e gerenciar o fim da vida útil e implantar todos os complementos necessários.<br><br>Para aplicativos que você fornece (como seus aplicativos de linha de negócios), seja você empacotá-los por conta própria ou contratar um fornecedor que não seja da Microsoft **para** fazer isso, você é responsável por essas ações: <br><br>- Identificar aplicativos necessários para grupos de usuários direcionados<br>- Criação e gerenciamento de grupos do Azure AD para implantação de aplicativos<br>- Empacotando aplicativos para atender Microsoft Intune padrões de implantação<br>- Carregando aplicativos para Microsoft Intune<br>- Testar aplicativos no Área de Trabalho Gerenciada da Microsoft ambiente<br>- Testar aplicativos com seus usuários<br>- Gerenciando e atribuindo usuários a aplicativos<br>- Identificar e implantar atualizações de aplicativos por meio Microsoft Intune<br>- Desinstalar e remover aplicativos quando eles foram retirados<br>- Procuring and assigning licenses<br>- Fornecendo suporte ao usuário para aplicativos de linha de negócios<br>- Gerenciando configurações de aplicativo remotamente<br><br>**A Microsoft** fornecerá Microsoft Intune ferramentas de implantação para fornecer os aplicativos a clientes remotos.<br><br>Para obter mais informações, consulte [Apps](../get-ready/apps.md).
Monitoramento e resposta de segurança | Você é responsável por investigar e resolver incidentes de dispositivos que não Área de Trabalho Gerenciada da Microsoft dispositivos e garantir que Área de Trabalho Gerenciada da Microsoft Equipe de Operações do Área de Trabalho Gerenciada da Microsoft seja informada sobre quaisquer problemas que possam afetar o serviço.
Suporte a operações | Você deve fornecer uma lista de contatos preferenciais e especialistas em assuntos da sua organização. Precisamos desses contatos se houver um incidente operacional não relacionado ao Área de Trabalho Gerenciada da Microsoft. <br><br>Você também é responsável por investigar e resolver incidentes de dispositivos e serviços que não estão no Área de Trabalho Gerenciada da Microsoft e garantir que Área de Trabalho Gerenciada da Microsoft Equipe de Operações do Área de Trabalho Gerenciada da Microsoft esteja sempre informada.
Infraestrutura de rede, incluindo VPN | Você é responsável pela instalação, configuração e gerenciamento (incluindo solução de problemas e depuração) de todas as infraestruturas e serviços relacionados à rede, incluindo conectividade com a Internet, controles de rede, configuração de proxy e infraestrutura de conectividade remota.<br><br>Se um proxy estiver configurado (em hardware ou software), haverá uma coleção de URLs que devem ser permitidas pelo proxy. Você é responsável por solucionar problemas de conflitos ou incompatibilidades devido a vários proxies. Você pode adicionar proxies de rede específicos à sua organização usando configurações configuráveis. Para obter mais informações, consulte [Configurações configuráveis](../working-with-managed-desktop/config-setting-ref.md#proxy).<br><br>Para obter mais informações, consulte [Configuração de Proxy](../get-ready/network.md).
Impressão | Você é responsável por instalar, manter e administrar impressoras e filas de impressão. A impressão em nuvem é uma solução recomendada, mas não é necessária. 




