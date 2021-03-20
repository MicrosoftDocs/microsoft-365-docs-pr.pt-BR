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
description: Use este Guia de Laboratório de Teste para habilitar configurações de segurança adicionais do Microsoft 365 no ambiente de teste do Microsoft 365 para empresas.
ms.openlocfilehash: 928deae34dc16c70776eb512188d1a36ae169da5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909781"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>Maior segurança do Microsoft 365 para seu ambiente de teste do Microsoft 365 para empresas

*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

Com as instruções neste artigo, você configura configurações adicionais do Microsoft 365 para aumentar a segurança em seu ambiente de teste do Microsoft 365 para empresas.

![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Clique [aqui](../downloads/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos na pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: criar seu ambiente de teste do Microsoft 365 para empresas

Se você deseja apenas configurar a segurança aumentada do Microsoft 365 de forma leve com os requisitos mínimos, siga as instruções em [Configuração base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se você quiser configurar a maior segurança do Microsoft 365 em uma empresa simulada, siga as instruções em [Autenticação passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testar a segurança aumentada do Microsoft 365 não exige o ambiente de teste empresarial simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio do Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar o licenciamento automatizado e a associação ao grupo e experimentá-lo em um ambiente que representa uma organização típica. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fase 2: Configurar maior segurança do Microsoft 365

Nesta fase, você habilita maior segurança do Microsoft 365 para seu ambiente de teste do Microsoft 365 para empresas. Para obter detalhes e configurações adicionais, consulte [Configure your tenant for increased security](/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Configurar o SharePoint Online para bloquear aplicativos que não suportam autenticação moderna

Os aplicativos que não suportam a autenticação moderna não podem ter configurações de identidade e acesso a [dispositivos aplicadas](../security/office-365-security/microsoft-365-policies-configurations.md) a eles, o que é um elemento importante para proteger sua assinatura do Microsoft 365 e seus ativos digitais. 

1. Vá para o Centro de administração do Microsoft 365 ( ) e entre na assinatura do laboratório de teste do [https://portal.microsoft.com](https://portal.microsoft.com) Microsoft 365 com sua conta de administrador global.
    
  - Se você estiver usando o ambiente de teste leve do Microsoft 365, entre no computador local.
    
  - Se você estiver usando o ambiente de teste do Microsoft 365 empresarial simulado, use o portal do [Azure](https://portal.azure.com) para se conectar à máquina virtual CLIENT1 e entre no CLIENT1.
 
2. Na nova guia Centro de administração do **Microsoft 365,** em **Centros de administração** no painel de navegação esquerdo, clique em **SharePoint**.
3. Na nova guia Centro de **administração do SharePoint,** clique em **Políticas > Controle de Acesso.**
4. Clique **em Aplicativos que não suportam autenticação moderna,** selecione **Bloquear** acesso e clique em **Salvar**.


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Habilitar o Defender para Office 365 para SharePoint, OneDrive for Business e Microsoft Teams

O Defender for Office 365 para SharePoint, OneDrive e Microsoft Teams protege sua organização contra o compartilhamento inadvertido de arquivos mal-intencionados.

1. Vá para o [Centro de Conformidade & segurança](https://protection.office.com) e entre com sua conta de administrador global.

2. No painel de navegação esquerdo, em **Gerenciamento de ameaças,** clique em **Política** e em **Anexos Seguros.** 

3. Em **Proteger arquivos no SharePoint, no OneDrive e no Microsoft Teams.** selecione **Ativar a ATP para SharePoint, OneDrive e Microsoft Teams.**

4. Clique em **Salvar**.


### <a name="enable-anti-malware"></a>Habilitar anti-malware

Malware é composto por vírus e spywares. Os vírus infectam outros programas e dados e se espalham em todo o computador em busca de programas para infectar. Spyware é um tipo de malware que coleta suas informações pessoais, como informações de logon e dados pessoais, e as envia de volta ao seu autor. 

O Microsoft 365 tem recursos de filtragem de malware e spam integrados que ajudam a proteger mensagens de entrada e saída de software mal-intencionado e ajudam a proteger você contra spam. Para obter mais informações, consulte [Anti-spam & anti-malware protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).

Para garantir que o processamento anti-malware está sendo executado em arquivos com tipos de arquivo de anexo comuns:

1. Clique no botão voltar no navegador para voltar à **página Política.**
2. Clique **em Anti-malware**.
3. Clique duas vezes na política chamada **Padrão**.
4. Na janela **Política anti-malware,** clique **em Configurações**.
4. Em **Filtro Tipos de Anexo Comuns,** selecione **Em** e clique em **Salvar**.


## <a name="phase-3-examine-the-security-dashboard"></a>Fase 3: Examinar o painel de segurança

O gerenciamento de ameaças no Microsoft 365 pode ajudá-lo a controlar e gerenciar o acesso de dispositivo móvel aos dados da sua organização, ajudar a proteger sua organização contra perda de dados e ajudar a proteger mensagens de entrada e saída contra software mal-intencionado e spam. Você também usa o gerenciamento de ameaças para proteger a reputação do seu domínio e para determinar se os enviadores são ou não mal-intencionados a spoofing de contas do seu domínio. 

Para ver o painel de segurança:

1. Se necessário, vá para o Centro de [Conformidade](https://protection.office.com) & segurança e entre com sua conta de administrador global.

2. No painel de navegação esquerdo, em **Gerenciamento de ameaças,** clique em **Painel**.

Dê uma olhada de perto em todos os cartões no painel para se familiarizar com as informações fornecidas.

Para obter mais informações, consulte [Painel de Segurança](../security/office-365-security/security-dashboard.md).


## <a name="phase-4-examine-microsoft-secure-score"></a>Fase 4: Examinar a Pontuação Segura da Microsoft

A Pontuação Segura da Microsoft mostra sua postura de segurança como um número, o que indica seu nível atual em relação aos recursos disponíveis em sua assinatura. Ele também oferece uma lista de ações de melhoria que você pode tomar para melhorar sua pontuação.

1. Crie uma nova guia no navegador e vá para o Centro de Segurança do [Microsoft 365](https://security.microsoft.com/)e clique em **Pontuação segura.**
2. Na guia **Visão**  geral, observe sua Pontuação Segura atual e como ela se compara com a média global e assinaturas com um número semelhante de licenças.
3. Na guia **Ações de melhoria,** leia a lista de ações que você pode tomar para aumentar sua pontuação.

Para obter mais informações, consulte [Microsoft Secure Score](../security/mtp/microsoft-secure-score.md).

## <a name="next-steps"></a>Próximas etapas

Explore recursos [e recursos adicionais de proteção](m365-enterprise-test-lab-guides.md#information-protection) de informações em seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](/microsoft-365-enterprise/)