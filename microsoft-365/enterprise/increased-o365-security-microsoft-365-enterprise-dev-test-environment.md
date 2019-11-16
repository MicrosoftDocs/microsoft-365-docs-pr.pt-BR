---
title: Maior segurança do Microsoft 365 para seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para habilitar configurações de segurança adicionais do Microsoft 365 para o ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 3173796167a0a9fb59e23ee2dc6eebf5000ed3d7
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672687"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a>Maior segurança do Microsoft 365 para seu ambiente de teste do Microsoft 365 Enterprise

*Este guia de laboratório de teste só pode ser usado para ambientes de teste do Microsoft 365 Enterprise.*

Com as instruções deste artigo, você define configurações adicionais do Microsoft 365 para aumentar a segurança no ambiente de teste do Microsoft 365 Enterprise.

![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Clique [aqui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Criar o ambiente de teste do Microsoft 365 Enterprise

Se você só quiser configurar a segurança mais 365 da Microsoft de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você quiser configurar a segurança do Microsoft 365 aumentada em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testando o Microsoft 365 Security não exige o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica. 


## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fase 2: configurar a segurança do Microsoft 365 mais elevado

Nesta fase, você habilitará a segurança mais 365 da Microsoft para seu ambiente de teste do Microsoft 365 Enterprise. Para obter mais detalhes e configurações, consulte [Configure Your Office 365 locatário for maior segurança](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Configurar o SharePoint Online para bloquear aplicativos que não dão suporte à autenticação moderna

Os aplicativos que não dão suporte à autenticação moderna não podem ter [configurações de acesso de dispositivo e identidade](microsoft-365-policies-configurations.md) aplicadas a eles, que é um elemento importante de proteger sua assinatura do Microsoft 365 e seus ativos digitais. 

1. Vá para o centro de administração do Microsoft[https://portal.microsoft.com](https://portal.microsoft.com)365 () e entre na sua assinatura de laboratório de teste do Office 365 com sua conta de administrador global.
    
  - Se você estiver usando o ambiente leve de teste do Microsoft 365, entre no computador local.
    
  - Se você estiver usando o ambiente de teste corporativo da Microsoft 365 simulado, use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual CLIENT1 e, em seguida, entre no CLIENT1.
 
2. Na nova guia **centro de administração do Microsoft 365** , clique em **centros de administração > SharePoint**.
3. Na nova guia **centro de administração do SharePoint** , clique em **controle de acesso**.
4. Em **aplicativos que não dão suporte à autenticação moderna**, clique em **Bloquear**e, em seguida, clique em **OK**.


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Habilitar a proteção avançada contra ameaças para o SharePoint, o OneDrive for Business e o Microsoft Teams

A proteção avançada contra ameaças do Office 365 (ATP) para o SharePoint, o OneDrive e o Microsoft Teams protege sua organização contra o compartilhamento inadvertidamente de arquivos mal-intencionados.

1. Vá para o [centro de conformidade & segurança do Office 365](https://protection.office.com) e entre com sua conta de administrador global.

2. No painel de navegação esquerdo, em **Gerenciamento de ameaças**, escolha **política > anexos seguros**. 

3. Selecione **Ativar ATP para SharePoint, onedrive e Microsoft Teams**.

4. Clique em **Salvar**.


### <a name="enable-anti-malware"></a>Habilitar Antimalware

Malware é composto por vírus e spywares. Os vírus infectam outros programas e dados e se espalham em todo o computador em busca de programas para infectar. Spyware é um tipo de malware que coleta suas informações pessoais, como informações de logon e dados pessoais, e as envia de volta ao seu autor. 

O Office 365 tem recursos internos de filtragem de malware e spam que ajudam a proteger mensagens de entrada e saída de software mal-intencionado e a proteger contra spam. Para obter mais informações, consulte [anti-spam & proteção Antimalware no Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)

Para garantir que o processamento Antimalware seja executado em arquivos com tipos de arquivo de anexo comuns:

1. Clique no botão voltar do navegador para voltar à página **política** .
2. Clique em **anti-malware**.
3. Clique duas vezes na política denominada **padrão**.
4. Na janela **política de antimalware** , clique em **configurações**.
4. Em **filtro tipos de anexo comuns**, clique **em > salvar**.


## <a name="phase-3-examine-the-threat-management-dashboard"></a>Fase 3: examinar o painel de gerenciamento de ameaças

O gerenciamento de ameaças do Office 365 pode ajudá-lo a controlar e gerenciar o acesso de dispositivos móveis aos dados da sua organização, ajudar a proteger sua organização contra a perda de dados e ajudar a proteger mensagens de entrada e saída de software mal-intencionado e spam. Você também usa o gerenciamento de ameaças para proteger a reputação do seu domínio e para determinar se ou não os remetentes estão falsificando contas de seu domínio de forma mal-intencionada. Para obter mais informações, consulte [Threat Management na central de segurança do Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/threat-management).

<!--
### Office 365 Cloud App Security dashboard

Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).

### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a>Próximas etapas

Consulte a etapa [Configurar maior segurança para o Microsoft 365](infoprotect-configure-increased-security-office-365.md) na fase de **proteção de informações** para obter informações e links para configurar essas definições em produção.

Explore recursos e funcionalidades adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) em seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

