---
title: Perguntas frequentes sobre Mobilidade Básica e Segurança (FAQ)
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Perguntas frequentes sobre Mobilidade Básica e Segurança.
ms.openlocfilehash: 5651b9f9742c45f1229e55b298cf78532c835c9a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876871"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>Perguntas frequentes sobre Mobilidade Básica e Segurança (FAQ)

Este artigo contém perguntas frequentes sobre Mobilidade Básica e Segurança, um recurso que ajuda você a gerenciar e proteger dispositivos móveis no Microsoft 365. Se você não encontrar uma resposta para sua pergunta, deixe um comentário na página para que possamos considerar adicionar sua pergunta a este artigo.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>Como posso obter o Basic Mobility and Security? Não consigo vê-lo no centro de administração do Microsoft 365

1.  Ative a Mobilidade e a Segurança Básica indo para a página de Conformidade e Segurança do [Office 365 &](https://protection.office.com/) Segurança.

2.  Vá para Prevenção contra perda de dados > Gerenciamento de dispositivos.

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>Como posso começar a usar o gerenciamento de dispositivos no Basic Mobility and Security?

Há quatro etapas para começar a trabalhar com Mobilidade Básica e Segurança: 

1. Activate Basic Mobility and Security by going to the [Office 365 Security & Compliance](https://protection.office.com/).

2. Vá para Prevenção contra perda de > gerenciamento de dispositivos > políticas de dispositivo.
    
3. Crie políticas de gerenciamento de dispositivos e aplique-as a grupos de usuários que estão definidos em grupos de segurança. Recomendamos que você comece implantando as políticas em um pequeno grupo de teste. Para obter mais informações, [consulte Criar políticas de segurança de dispositivos em Mobilidade Básica e Segurança.](create-device-security-policies.md)

4. Os usuários que tiveram uma política aplicada a eles serão solicitados a registrar seus dispositivos quando tentarem acessar os dados do Microsoft 365. Para obter mais informações, consulte [Registrar seu dispositivo móvel usando Mobilidade Básica e Segurança.](enroll-your-mobile-device.md)

Para obter mais detalhes, [consulte Set up Basic Mobility and Security](set-up.md).

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Estou tentando configurar o Basic Mobility and Security, mas parece que ele está travado. A Microsoft 365 Service Health tem mostrado "provisionamento" há algum tempo. O que posso fazer?

Pode levar algum tempo para preparar o serviço para você. Quando o provisionamento for concluído, você verá a página Mobilidade Básica e Segurança. Se você tiver esperado 24 horas e o status ainda estiver sendo provisionado, entre em contato com o Suporte e ajudaremos a descobrir qual é o problema. Para opções de suporte, [confira Ainda precisa de ajuda?](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp).

## <a name="what-can-i-do-if-device-enrollment-fails"></a>O que posso fazer se o registro de dispositivo falhar?

Se você estiver tendo problemas para registrar um dispositivo, primeiro verifique o seguinte:

- Certifique-se de que o dispositivo ainda não está inscrito em outro provedor de gerenciamento de dispositivo móvel, como o Intune.

- Certifique-se de que o dispositivo está definido para a data e a hora corretas.

- Alternar para uma rede WIFI ou celular diferente no dispositivo.

- Para dispositivos Android ou iOS, desinstale e reinstale o aplicativo do Portal da Empresa do Intune no dispositivo.
    
Se o registro ainda não estiver funcionando, consulte [Troubleshoot Basic Mobility and Security](troubleshoot.md).

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Qual é a diferença entre o Intune e a Mobilidade Básica e Segurança?

A Mobilidade Básica e Segurança é hospedada pelo serviço do Intune. É um subconjunto dos serviços do Intune fornecidos como um benefício agregado ao Microsoft 365 e é uma solução integrada baseada em nuvem para gerenciar dispositivos em sua organização. Para uma comparação lado a lado dos dois serviços para ajudá-lo a decidir se usar o Intune ou a Mobilidade Básica e Segurança para o Microsoft 365 é a melhor opção para você, confira Escolher entre o Basic Mobility Security e o [Intune.](choose-between-basic-mobility-and-security-and-intune.md)

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>Como as políticas funcionam para Mobilidade Básica e Segurança? Como faço para configura-los? Desabilitá-los?

Depois de concluir a configuração inicial do Basic Mobility and Security, crie políticas e aplique-as a grupos de usuários no Centro de Conformidade e & Segurança. As políticas exigem que os usuários das políticas inscrevam seus dispositivos na Mobilidade Básica e Segurança antes que o dispositivo possa ser usado para acessar dados do Microsoft 365. As políticas definidas determinam as configurações de dispositivos móveis, por exemplo, a frequência com que as senhas devem ser redefinidas ou se a criptografia de dados é necessária. Para saber mais, confira [Criar políticas de segurança de dispositivos](create-device-security-policies.md)no Centro de conformidade do Microsoft   [365 e](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)Mobilidade Básica.

Para obter instruções passo a passo para criar e implantar políticas de dispositivo, consulte Criar políticas de segurança do dispositivo [em Mobilidade e Segurança Básica.](create-device-security-policies.md)

Se quiser excluir um grupo específico de usuários de serem afetados por políticas, você pode adicionar um grupo ao grupo de exclusão.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>Posso alternar do gerenciamento de dispositivos do Exchange ActiveSync para o Basic Mobility and Security para o Microsoft 365?

Se você já estiver usando políticas do Exchange ActiveSync para gerenciar dispositivos móveis, poderá começar a usar o Basic Mobility and Security seguindo as etapas para configurar o Basic Mobility and Security. Para obter mais informações, [consulte Proteger o acesso de usuários e dispositivos](https://go.microsoft.com/fwlink/?LinkId=615145) e configurar a Mobilidade Básica e [Segurança.](set-up.md)

Quando você aplica as políticas criadas no Basic Mobility and Security a grupos de usuários, essas políticas substituem as políticas de caixa de correio de dispositivo móvel do Exchange ActiveSync e as regras de acesso a dispositivos que você criou anteriormente no Centro de administração do Exchange para esses usuários.

Depois que um dispositivo é inscrito no Basic Mobility and Security, qualquer política de caixa de correio de dispositivo móvel do Exchange ActiveSync ou regra de acesso ao dispositivo aplicada ao dispositivo é ignorada.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>Eu configurar o Basic Mobility and Security, mas agora quero removê-lo. Quais são as etapas?

Infelizmente, você não pode simplesmente "desprovisionar" a Mobilidade e a Segurança Básica após a configuração. Mas você pode removê-lo para grupos de usuários removendo grupos de segurança de usuários das políticas de dispositivo que você criou. Ou você pode desabilitá-lo para todos removendo as políticas de dispositivo para que elas não sejam aplicadas e não sejam impostas. Para obter mais informações, [consulte Desativar Mobilidade Básica e Segurança.](turn-off.md)