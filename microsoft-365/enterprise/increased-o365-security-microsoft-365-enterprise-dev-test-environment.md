---
title: Maior segurança do Microsoft 365 para seu ambiente de teste do Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para habilitar configurações de segurança adicionais do Microsoft 365 para o ambiente de teste do Microsoft 365 para empresas.
ms.openlocfilehash: 06273bda00635a65ed9821b2bac23c3a3ee1366a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686797"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>Maior segurança do Microsoft 365 para seu ambiente de teste do Microsoft 365 para empresas

*Este guia de laboratório de teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

Com as instruções deste artigo, você define configurações adicionais do Microsoft 365 para aumentar a segurança no ambiente de teste do Microsoft 365 para empresas.

![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Clique [aqui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos na pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise

Se você só quiser configurar a segurança mais 365 da Microsoft de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você quiser configurar a segurança do Microsoft 365 aumentada em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testando o Microsoft 365 Security não exige o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fase 2: configurar a segurança do Microsoft 365 mais elevado

Nesta fase, você habilitará a segurança do Microsoft 365 aumentada para o ambiente de teste do Microsoft 365 para empresas. Para obter mais detalhes e configurações, consulte [Configure Your locatário for maior segurança](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Configurar o SharePoint Online para bloquear aplicativos que não dão suporte à autenticação moderna

Os aplicativos que não dão suporte à autenticação moderna não podem ter [configurações de acesso de dispositivo e identidade](microsoft-365-policies-configurations.md) aplicadas a eles, que é um elemento importante de proteger sua assinatura do Microsoft 365 e seus ativos digitais. 

1. Vá para o centro de administração do Microsoft 365 ( [https://portal.microsoft.com](https://portal.microsoft.com) ) e entre na sua assinatura de laboratório de teste do microsoft 365 com sua conta de administrador global.
    
  - Se você estiver usando o ambiente leve de teste do Microsoft 365, entre no computador local.
    
  - Se você estiver usando o ambiente de teste corporativo da Microsoft 365 simulado, use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual CLIENT1 e, em seguida, entre no CLIENT1.
 
2. Na nova guia **centro de administração do Microsoft 365** , em **centros de administração** no painel de navegação esquerdo, clique em **SharePoint**.
3. Na nova guia **centro de administração do SharePoint** , clique em **políticas > controle de acesso**.
4. Clique em **aplicativos que não dão suporte à autenticação moderna**, selecione **bloquear acesso**e clique em **salvar**.


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Habilitar a proteção avançada contra ameaças para o SharePoint, o OneDrive for Business e o Microsoft Teams

A proteção avançada contra ameaças do Office 365 (ATP) para o SharePoint, o OneDrive e o Microsoft Teams protege sua organização contra o compartilhamento inadvertidamente de arquivos mal-intencionados.

1. Vá para o [centro de conformidade & segurança](https://protection.office.com) e entre com sua conta de administrador global.

2. No painel de navegação esquerdo, em **Gerenciamento de ameaças**, clique em **política**e em **anexos de segurança ATP**. 

3. Em **proteger arquivos no SharePoint, no onedrive e no Microsoft Teams**. Selecione **Ativar ATP para SharePoint, onedrive e Microsoft Teams**.

4. Clique em **Salvar**.


### <a name="enable-anti-malware"></a>Habilitar Antimalware

Malware é composto por vírus e spywares. Os vírus infectam outros programas e dados e se espalham em todo o computador em busca de programas para infectar. Spyware é um tipo de malware que coleta suas informações pessoais, como informações de logon e dados pessoais, e as envia de volta ao seu autor. 

A Microsoft 365 tem recursos internos de filtragem de malware e spam que ajudam a proteger mensagens de entrada e saída de software mal-intencionado e a protegê-lo contra spam. Para obter mais informações, consulte [anti-spam & proteção Antimalware](../security/office-365-security/anti-spam-and-anti-malware-protection.md).

Para garantir que o processamento Antimalware seja executado em arquivos com tipos de arquivo de anexo comuns:

1. Clique no botão voltar do navegador para voltar à página **política** .
2. Clique em **anti-malware**.
3. Clique duas vezes na política denominada **padrão**.
4. Na janela **política de antimalware** , clique em **configurações**.
4. Em **filtro tipos de anexo comuns**, selecione **ativado**e clique em **salvar**.


## <a name="phase-3-examine-the-security-dashboard"></a>Fase 3: examinar o painel de segurança

O gerenciamento de ameaças no Microsoft 365 pode ajudá-lo a controlar e gerenciar o acesso de dispositivos móveis aos dados da sua organização, ajudar a proteger sua organização contra a perda de dados e ajudar a proteger mensagens de entrada e saída de software mal-intencionado e spam. Você também usa o gerenciamento de ameaças para proteger a reputação do seu domínio e para determinar se ou não os remetentes estão falsificando contas de seu domínio de forma mal-intencionada. 

Para ver o painel de segurança:

1. Se necessário, vá para o [centro de conformidade & segurança](https://protection.office.com) e entre com sua conta de administrador global.

2. No painel de navegação esquerdo, em **Gerenciamento de ameaças**, clique em **painel**.

Dê uma olhada próxima em todos os cartões no painel para se familiarizar com as informações fornecidas.

Para obter mais informações, consulte [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).


## <a name="phase-4-examine-microsoft-secure-score"></a>Fase 4: examinar a pontuação segura da Microsoft

A pontuação segura da Microsoft mostra a postura de segurança como um número, que indica seu nível atual em relação aos recursos disponíveis na sua assinatura. Também fornece uma lista de ações de melhoria que você pode tomar para melhorar sua pontuação.

1. Crie uma nova guia no navegador e vá para a [central de segurança do Microsoft 365](https://security.microsoft.com/)e clique em **Pontuação segura**.
2. Na guia **visão geral**  , anote sua pontuação segura atual e como ela se compara com a média global e inscrições com um número semelhante de licenças.
3. Na guia **ações de melhoria** , leia a lista de ações que você pode tomar para aumentar sua pontuação.

Para obter mais informações, consulte [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).

## <a name="next-steps"></a>Próximas etapas

Explore recursos e funcionalidades adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) em seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação da Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
