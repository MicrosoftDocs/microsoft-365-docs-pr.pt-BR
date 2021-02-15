---
title: Funções e responsabilidades da Área de Trabalho Gerenciada da Microsoft
description: Este artigo descreve as funções e responsabilidades fornecidas pela Microsoft para a Área de Trabalho Gerenciada da Microsoft.
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

Quando sua organização está inscrita na Área de Trabalho Gerenciada da Microsoft, o que a Microsoft faz por você? E quais são as responsabilidades da sua organização?

## <a name="microsofts-roles-and-responsibilities"></a>Funções e responsabilidades da Microsoft

A Microsoft fornece estas principais funções e responsabilidades:

Função ou responsabilidade | Descrição
--- | ---
Gerenciamento de políticas MDM | A Microsoft aplicará políticas MDM de acordo com as práticas recomendadas e considerará solicitações de alterações de política. Também faremos alterações em seu locatário conforme indicado nas políticas [de dispositivo.](../service-description/device-policies.md)
suporte do usuário | Fornecemos suporte ao usuário para dispositivos, Windows e o pacote de produtos do Microsoft 365 Apps para empresas para todos os usuários inscritos por meio do aplicativo Obter Ajuda pré-instalado em todos os dispositivos da Área de Trabalho Gerenciada da Microsoft. 
Suporte ao serviço de Área de Trabalho Gerenciada da Microsoft | A Microsoft fornecerá suporte ao seu departamento de IT por meio de uma Equipe de Operações de Área de Trabalho Gerenciada da Microsoft. Essa equipe dará suporte a solução de problemas técnicos, solicitações de alteração e gerenciamento de incidentes para o ambiente da Área de Trabalho Gerenciada da Microsoft do cliente. Para obter mais informações, consulte [Suporte de administrador para Área de Trabalho Gerenciada da Microsoft.](../working-with-managed-desktop/admin-support.md)
Monitoramento de segurança | A Microsoft monitorará seus dispositivos da Área de Trabalho Gerenciada da Microsoft usando o Microsoft Defender para o Ponto de Extremidade. Se o Microsoft Managed Desktop Security Operations Center (SOC) detectar uma ameaça, notificaremos você, isolaremos o dispositivo e corrigiremos o problema remotamente. Para obter mais informações, consulte [Segurança.](../service-description/security.md)
Atualizar monitoramento e gerenciamento | Monitoramos ativamente seus dispositivos de Área de Trabalho Gerenciada da Microsoft para garantir que as atualizações mais recentes de qualidade e recursos sejam instaladas para o Microsoft Windows e o Microsoft Office. Para obter mais informações, [consulte Como as atualizações são tratadas.](../service-description/updates.md)
Grupo de usuários e dispositivos | A equipe de operações da Área de Trabalho Gerenciada da Microsoft criará e gerenciará os grupos de usuários e dispositivos necessários como parte das operações de IT. Nenhuma alteração de associação ou configuração é permitida para esses grupos. A alteração desses grupos pode levar a uma configuração inesperada de dispositivos e à perda de funcionalidade. Para quaisquer problemas ou perguntas sobre esses grupos depois de estabelecidos, os administradores de IT podem entrar em contato com as operações da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [Suporte de administrador para Área de Trabalho Gerenciada da Microsoft.](../working-with-managed-desktop/admin-support.md)

## <a name="your-roles-and-responsibilities"></a>Suas funções e responsabilidades

Esse conjunto de funções e responsabilidades comuns é necessário para a implantação, mas não são fornecidos pela Microsoft. Não é exaustivo, mas é aplicável para a maioria das organizações. Há alguns itens que você e a Microsoft compartilham de responsabilidade. 

Função ou responsabilidade | Descrição
--- | ---
Gerenciamento de alterações | A Microsoft notificará os clientes com antecedência quando for necessário fazer alterações em seu ambiente de Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [alterações de serviço e comunicação.](../service-description/servicechanges.md)<br><br>Você deve ter seu próprio processo de gerenciamento de alterações e ter um contato estabelecido com a equipe de Operações de Área de Trabalho Gerenciada da Microsoft. Você também deve ter recursos para revisar e aprovar essas alterações. Para obter mais informações, [consulte Operações e monitoramento.](../service-description/operations-and-monitoring.md)  
O gerenciamento de identidades | Você é responsável por criar contas de usuário, atribuir usuários a grupos e manter os metadados atualizados. 
Configuração e gerenciamento do Microsoft 365 Apps para empresas | A Microsoft é responsável por garantir que os aplicativos do Office sejam implantados para os usuários e que esses aplicativos sejam mantidos atualizados. <br><br> Você é responsável por gerenciar serviços e políticas do Microsoft 365, incluindo as responsabilidades de administração do Exchange Online:<br>- Administração de email<br>- Configuração de caixa de correio e regra<br>- Gerenciamento local do Exchange<br><br>Você também é responsável pelas ferramentas de colaboração, administração do servidor do SharePoint, gerenciamento de domínio e políticas de segurança e informações definidas no centro de administração do Microsoft 365. 
Suporte ao usuário | Você deve fornecer suporte ao usuário para: <br>- Infraestrutura local: toda a conectividade de rede e internet, infraestrutura VPN e configuração de cliente, equipamento de sala de conferência local, impressoras, servidor proxy e configuração e firewalls.<br><br>– Recursos de nuvem para toda a empresa: email, SharePoint, serviços de colaboração e outras infraestruturas de nuvem relacionadas à área de tecnologia de toda a empresa.<br><br>- Linha de negócios e quaisquer outros aplicativos específicos da empresa.
Aplicativos | As funções e responsabilidades variam um pouco para os aplicativos fornecidos como parte da Área de Trabalho Gerenciada da Microsoft em relação aos aplicativos que você fornece. <br><br>Para aplicativos fornecidos pela Microsoft (Microsoft 365 Apps para empresas que abrangem Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, Teams e OneNote), a **Microsoft** fornecerá serviço completo para a implantação, atualização e suporte. **Você** deve obter e atribuir licenças para esses aplicativos, adicionar usuários a grupos de segurança, gerenciar o fim da vida útil e implantar quaisquer complementos necessários.<br><br>Para aplicativos que você fornece (como seus aplicativos de linha de negócios), se você empacotá-los por conta própria ou envolver um fornecedor que não seja da Microsoft para fazer **isso,** você é responsável por estas ações: <br><br>- Identificando aplicativos necessários para grupos de usuários direcionados<br>- Criar e gerenciar grupos do Azure AD para implantação de aplicativos<br>– Empacotando aplicativos para atender aos padrões de implantação do Microsoft Intune<br>- Carregar aplicativos no Microsoft Intune<br>– Testando aplicativos no ambiente da Área de Trabalho Gerenciada da Microsoft<br>- Testando aplicativos com seus usuários<br>- Gerenciando e atribuindo usuários a aplicativos<br>- Identificar e implantar atualizações de aplicativos por meio do Microsoft Intune<br>- Desinstalar e remover aplicativos quando eles foram retirados<br>- Comprar e atribuir licenças<br>– Fornecer suporte ao usuário para aplicativos de linha de negócios<br>- Gerenciando configurações do aplicativo remotamente<br><br>**A Microsoft** fornecerá ferramentas de implantação do Microsoft Intune para entregar os aplicativos a clientes remotos.<br><br>Para obter mais informações, consulte [Aplicativos.](../get-ready/apps.md)
Monitoramento e resposta de segurança | Você é responsável por investigar e resolver incidentes para dispositivos que não são dispositivos da Área de Trabalho Gerenciada da Microsoft e garantir que a Equipe de Operações de Área de Trabalho Gerenciada da Microsoft seja informada sobre quaisquer problemas que possam afetar o serviço.
Suporte a operações | Você deve fornecer uma lista de contatos preferenciais e especialistas no assunto em sua organização. Precisamos desses contatos se houver um incidente operacional não relacionado à Área de Trabalho Gerenciada da Microsoft. <br><br>Você também é responsável por investigar e resolver incidentes para dispositivos e serviços que não estão na Área de Trabalho Gerenciada da Microsoft e garantir que a Equipe de Operações de Área de Trabalho Gerenciada da Microsoft sempre seja informada.
Infraestrutura de rede, incluindo VPN | Você é responsável pela instalação, configuração e gerenciamento (incluindo solução de problemas e depuração) de todas as infraestruturas e serviços relacionados à rede, incluindo conectividade com a Internet, controles de rede, configuração de proxy e infraestrutura de conectividade remota.<br><br>Se um proxy estiver configurado (em hardware ou software), haverá uma coleção de URLs que devem ser permitidas pelo proxy. Você é responsável por solucionar quaisquer conflitos ou incompatibilidades devido a vários proxies. Você pode adicionar proxies de rede específicos à sua organização usando configurações configuráveis. Para obter mais informações, consulte [Configurações configuráveis.](../working-with-managed-desktop/config-setting-ref.md#proxy)<br><br>Para obter mais informações, consulte [Configuração de Proxy.](../get-ready/network.md)
Impressão | Você é responsável por instalar, manter e administrar impressoras e filas de impressão. A impressão na nuvem é uma solução recomendada, mas não é necessária. 




