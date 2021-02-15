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
description: Use este Guia de Laboratório de Teste para habilitar configurações de segurança adicionais do Microsoft 365 em seu ambiente de teste do Microsoft 365 para empresas.
ms.openlocfilehash: d385688a6e59ee500442bcf1b815dfd165102242
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846995"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>Maior segurança do Microsoft 365 para seu ambiente de teste do Microsoft 365 para empresas

*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

Com as instruções neste artigo, você define configurações adicionais do Microsoft 365 para aumentar a segurança em seu ambiente de teste do Microsoft 365 para empresas.

![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Clique [aqui](../downloads/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos na pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas

Se você quiser apenas configurar a segurança aumentada do Microsoft 365 de maneira leve com os requisitos mínimos, siga as instruções na configuração [de base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se você quiser configurar maior segurança do Microsoft 365 em uma empresa simulada, siga as instruções na autenticação [de passagem.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> O teste de maior segurança do Microsoft 365 não exige o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta do AD DS (Serviços de Domínio Active Directory). Ele é fornecido aqui como uma opção para que você possa testar licenciamento automatizado e associação de grupo e experimentar com ele em um ambiente que representa uma organização típica. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fase 2: Configurar maior segurança do Microsoft 365

Nesta fase, você habilita maior segurança do Microsoft 365 para seu ambiente de teste do Microsoft 365 para empresas. Para obter mais detalhes e configurações, consulte [Configurar seu locatário para aumentar a segurança.](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Configurar o SharePoint Online para bloquear aplicativos que não suportam autenticação moderna

Os aplicativos que não suportam a autenticação moderna não podem ter configurações de acesso de dispositivo e identidade [aplicadas](../security/office-365-security/microsoft-365-policies-configurations.md) a eles, o que é um elemento importante para proteger sua assinatura do Microsoft 365 e seus ativos digitais. 

1. Vá para o Centro de administração do Microsoft 365 ( ) e entre em sua assinatura de laboratório de teste do [https://portal.microsoft.com](https://portal.microsoft.com) Microsoft 365 com sua conta de administrador global.
    
  - Se você estiver usando o ambiente de teste leve do Microsoft 365, entre no computador local.
    
  - Se você estiver usando o ambiente de teste corporativo simulado do Microsoft 365, use o portal do [Azure](https://portal.azure.com) para se conectar à máquina virtual CLIENT1 e entre no CLIENT1.
 
2. Na nova guia centro de administração do **Microsoft 365,** em **Centros** de administração no painel de navegação esquerdo, clique **em SharePoint**.
3. Na nova guia centro **de administração do SharePoint,** clique em **Políticas > controle de acesso.**
4. Clique **em Aplicativos que não suportam autenticação moderna,** selecione **Bloquear acesso** e clique em **Salvar.**


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Habilitar o Defender para Office 365 para SharePoint, OneDrive for Business e Microsoft Teams

O Defender para Office 365 para SharePoint, OneDrive e Microsoft Teams protege sua organização contra o compartilhamento inadvertido de arquivos mal-intencionados.

1. Vá para o [Centro de Conformidade & segurança](https://protection.office.com) e entre com sua conta de administrador global.

2. No painel de navegação esquerdo, em **Gerenciamento de ameaças,** clique em **Política** e em **Anexos Seguros.** 

3. Em **Proteger arquivos no SharePoint, OneDrive e Microsoft Teams.** selecione **Ativar ATP para SharePoint, OneDrive e Microsoft Teams.**

4. Clique em **Salvar**.


### <a name="enable-anti-malware"></a>Habilitar anti-malware

Malware é composto por vírus e spywares. Os vírus infectam outros programas e dados e se espalham em todo o computador em busca de programas para infectar. Spyware é um tipo de malware que coleta suas informações pessoais, como informações de logon e dados pessoais, e as envia de volta ao seu autor. 

O Microsoft 365 tem recursos integrados de filtragem de malware e spam que ajudam a proteger mensagens de entrada e de saída contra softwares mal-intencionados e ajudam a protegê-lo contra spam. Para obter mais informações, [consulte Anti-spam & proteção anti-malware.](../security/office-365-security/anti-spam-and-anti-malware-protection.md)

Para garantir que o processamento anti-malware está sendo executado em arquivos com tipos de arquivo de anexo comuns:

1. Clique no botão Voltar no navegador para voltar à **página Política.**
2. Clique **em Anti-malware.**
3. Clique duas vezes na política chamada **Padrão.**
4. Na janela **política anti-malware,** clique em **Configurações.**
4. Under **Common Attachment Types filter**, select **On**, and then click **Save**.


## <a name="phase-3-examine-the-security-dashboard"></a>Fase 3: Examinar o painel de segurança

O gerenciamento de ameaças no Microsoft 365 pode ajudá-lo a controlar e gerenciar o acesso de dispositivos móveis aos dados da sua organização, ajudar a proteger sua organização contra perda de dados e ajudar a proteger mensagens de entrada e de saída contra software e spam mal-intencionados. Você também usa o gerenciamento de ameaças para proteger a reputação do seu domínio e para determinar se os envios são ou não contas maliciosamente spoofing de seu domínio. 

Para ver o painel de segurança:

1. Se necessário, vá para o [Centro de Conformidade & segurança](https://protection.office.com) e entre com sua conta de administrador global.

2. No painel de navegação esquerdo, em Gerenciamento **de ameaças,** clique em **Painel.**

Dê uma olhada em todos os cartões no painel para se familiarizar com as informações fornecidas.

Para obter mais informações, consulte [o Painel de Segurança.](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard)


## <a name="phase-4-examine-microsoft-secure-score"></a>Fase 4: Examinar o Microsoft Secure Score

O Microsoft Secure Score mostra a postura de segurança como um número, o que indica seu nível atual em relação aos recursos disponíveis em sua assinatura. Ele também fornece uma lista de ações de melhoria que você pode tomar para melhorar sua pontuação.

1. Crie uma nova guia no navegador e vá para a central de segurança do [Microsoft 365](https://security.microsoft.com/)e clique em **Classificação de segurança.**
2. Na guia **Visão geral,**  anote sua Classificação de Segurança atual e como ela se compara com a média global e as assinaturas com um número semelhante de licenças.
3. Na guia **Ações de aperfeiçoamento,** leia a lista de ações que você pode tomar para aumentar sua pontuação.

Para obter mais informações, consulte [o Microsoft Secure Score.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)

## <a name="next-steps"></a>Próximas etapas

Explore recursos [e funcionalidades adicionais](m365-enterprise-test-lab-guides.md#information-protection) de proteção de informações em seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
