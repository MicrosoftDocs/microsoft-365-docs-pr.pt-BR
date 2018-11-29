---
title: Pré-requisitos da Área de Trabalho Gerenciada da Microsoft
description: ''
keywords: Serviço Microsoft Managed Desktop, 365 da Microsoft, documentação
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 11/1/2018
ms.openlocfilehash: a7e82c0f4301b00e3d9e923dca10d1630744b8c0
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865191"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Pré-requisitos da Área de Trabalho Gerenciada da Microsoft

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

Sucesso com o Microsoft Desktop gerenciados começa com conhecido, documentados e acordados requisitos para a infra-estrutura do cliente. Esta seção descreve os pré-requisitos. 

Microsoft FastTrack está disponível para ajudar os clientes a atender a esses requisitos e ajudá-lo a se preparar para participar moderno local de trabalho como um serviço. Para obter mais informações, consulte [Microsoft FastTrack](https://fasttrack.microsoft.com/about). 

Área | Detalhes de pré-requisito
--- | ---
Licenciamento | Uma licença do Microsoft 365 E5 ou equivalentes licenças são necessárias.<br><br>Essa licença inclui E5 do Office 365, Windows 10 Enterprise E5 & Enterprise mobilidade + E5 de segurança (EMS). Para obter mais informações, consulte [Microsoft 365 licenciamento](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Conectividade |  Todos os dispositivos de área de trabalho gerenciada do Microsoft exigem conectividade para vários pontos de extremidade de serviço de Microsoft da rede interna organizacional, incluindo:<br>-Windows Update<br>-Microsoft Store for Business<br>-Azure Active Directory<br>-Relatório de erros Windows<br>-Análise de travamento online<br>-Conectados a experiência do usuário e telemetria<br>-App OneDrive para Windows 10<br><br>A lista completa de necessárias do IP e URLs podem ser encontradas na [Configuração de Proxy](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (AD Azure) deve ser a fonte de autoridade para todas as contas de usuário ou contas de usuário devem ser sincronizadas do local do Active Directory usando o Windows Azure AD de conectar, versão 1.1.654.0 ou posterior. Para obter mais informações, consulte [Connect do Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
Autenticação |    Se o Azure AD não for a fonte de autoridade para contas de usuário, você deve configurar um destes procedimentos no Azure Connect da AD:<br>-Sincronização de Hash senha (recomendada)<br>-Autenticação passagem<br>-Federação com o ADFS<br><br>Quando o definindo opções de autenticação com write-back de senha de conectar-se do Azure AD também é necessária. Para obter mais informações, consulte [Write-back de senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).<br><br>Para obter mais informações sobre opções de autenticação do Azure AD, consulte [Opções de entrada do usuário de conectar do Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Office 365 |    É altamente recomendável que os seguintes serviços ser migrados para a nuvem:<br>-Email - migrar para o correio na nuvem, Exchange online ou ser configurado com o Exchange Online híbrido com o Exchange 2013 ou superior, no local.<br>-Arquivos e pastas – migram para o SharePoint Online/Office 365.<br>-Skype para negócios – migrar para o Skype para negócios Online.<br>-Gerenciamento de dispositivo - Microsoft Intune A solução somente em nuvem MDM (não-híbrido) é necessária, que permite que os administradores gerenciem dispositivos Microsoft Desktop gerenciados usando um console web que pode ser acessado a partir em qualquer lugar do mundo. Microsoft Intune é a solução MDM necessária.<br><br>Para obter mais informações, consulte [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Dados de backup e recuperação | Microsoft Desktop gerenciados requer arquivos a ser sincronizados ao OneDrive for Business para proteção. Quaisquer arquivos que não são sincronizados ao OneDrive for Business não há uma garantia pelo Microsoft Desktop gerenciados e podem ser perdidos durante trocas de dispositivo ou chamadas de suporte que requerem uma redefinição do dispositivo. Microsoft Desktop gerenciados não dá suporte para unidades de rede mapeadas.  

[Saiba como cumpre os pré-requisitos para a inscrição do Microsoft Desktop gerenciados.](../get-ready/index.md)

Quando você estiver pronto para começar a área de trabalho gerenciada do Microsoft, contate seu gerente de conta da Microsoft. 