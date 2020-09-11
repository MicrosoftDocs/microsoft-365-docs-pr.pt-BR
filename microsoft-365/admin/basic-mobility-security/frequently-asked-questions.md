---
title: Perguntas frequentes sobre mobilidade básica e segurança (FAQ)
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
description: Perguntas frequentes sobre mobilidade básica e segurança.
ms.openlocfilehash: e05815392510ad54bb530457d7f0f6490ece4a95
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430068"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>Perguntas frequentes sobre mobilidade básica e segurança (FAQ)

Este artigo contém perguntas frequentes sobre mobilidade e segurança básicas, um recurso que ajuda a gerenciar e proteger dispositivos móveis no Microsoft 365. Se você não conseguir encontrar uma resposta para a sua pergunta, deixe um comentário na página para que possamos adicionar a pergunta a este artigo.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>Como posso obter mobilidade básica e segurança? Não consigo vê-lo no centro de administração do Microsoft 365

1.  Ative a mobilidade básica e a segurança indo para a página de [conformidade & segurança do Office 365](https://protection.office.com/) .   

2.  Vá para prevenção de perda de dados > gerenciamento de dispositivos.   

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>Como posso começar a usar o gerenciamento de dispositivos na mobilidade básica e segurança?

Há quatro etapas para introdução à mobilidade básica e segurança: 

1. Ative a mobilidade básica e a segurança indo para a [conformidade do Office 365 Security &](https://protection.office.com/).
    
2. Vá para prevenção de perda de dados > gerenciamento de dispositivos > políticas de dispositivos.
    
3. Crie políticas de gerenciamento de dispositivos e aplique-as a grupos de usuários configurados em grupos de segurança. Recomendamos que você comece implantando as políticas para um pequeno grupo de teste. Para obter mais informações, consulte [Create Device Security Policies in Basic Mobility and Security](create-device-security-policies.md).      

4. Os usuários que tiverem uma política aplicada a eles serão solicitados a registrar seus dispositivos quando tentarem acessar os dados do Microsoft 365. Para saber mais, confira [registrar seu dispositivo móvel usando mobilidade básica e segurança](enroll-your-mobile-device.md).

Para obter mais detalhes, consulte [Configurar mobilidade básica e segurança](set-up.md).

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Estou tentando configurar mobilidade básica e segurança, mas parece estar presa. A integridade do serviço Microsoft 365 tem mostrado "provisionamento" por algum tempo. O que posso fazer?

Pode levar algum tempo para que o serviço seja preparado para você. Quando o provisionamento estiver concluído, você verá a página Gerenciamento de dispositivo móvel para o Microsoft 365. Se você aguardou 24 horas e o status ainda estiver Provisionando, entre em contato com o suporte e ajudaremos a descobrir o problema. Para obter opções de suporte, consulte [ainda precisa de ajuda?](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp) 

## <a name="what-can-i-do-if-device-enrollment-fails"></a>O que posso fazer se o registro do dispositivo falhar?

Se você estiver tendo problemas para obter um dispositivo inscrito, primeiro verifique o seguinte:

- Certifique-se de que o dispositivo ainda não está inscrito com outro provedor de gerenciamento de dispositivo móvel, como o Intune.
    
- Certifique-se de que o dispositivo está definido para a data e hora corretas.
    
- Alterne para uma rede WIFI ou de celular diferente no dispositivo.
    
- Para dispositivos Android ou iOS, desinstale e reinstale o aplicativo portal da empresa do Intune no dispositivo.
    
Se o registro ainda não funcionar, confira [solucionar problemas de mobilidade básica e segurança](troubleshoot.md).

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Qual é a diferença entre o Intune e a mobilidade básica e a segurança?

A mobilidade básica e a segurança são hospedadas pelo serviço do Intune. É um subconjunto de serviços do Intune fornecido como um benefício adicionado para o Microsoft 365 e é uma solução interna baseada em nuvem para gerenciamento de dispositivos em sua organização. Para uma comparação lado a lado dos dois serviços para ajudá-lo a decidir se usar o Intune ou mobilidade básica e a segurança do Microsoft 365 é o melhor ajuste para você, consulte [escolher entre a segurança de mobilidade básica e o Intune](choose-between-basic-mobility-and-security-and-intune.md).

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>Como as políticas funcionam para mobilidade básica e segurança? Como faço para configurá-los? Desabilitá-los?

Depois de concluir a configuração inicial para mobilidade básica e segurança, você cria políticas e as aplica a grupos de usuários no centro de conformidade e segurança &. As políticas exigem que os usuários das políticas registrem seus dispositivos em mobilidade básica e segurança antes que o dispositivo possa ser usado para acessar os dados do Microsoft 365. As políticas definidas determinam as configurações para dispositivos móveis, por exemplo, com que frequência as senhas devem ser redefinidas ou se a criptografia de dados é necessária. Para obter mais informações, consulte [criar políticas de segurança de dispositivo em mobilidade básica e segurança](create-device-security-policies.md)   e [centro de conformidade da Microsoft 365](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8).

Para obter instruções detalhadas sobre como criar e implantar políticas de dispositivo, consulte [Create Device Security Policies in Basic Mobility and Security](create-device-security-policies.md).

Se você deseja excluir um grupo específico de usuários de ser afetado por políticas, você pode adicionar um grupo ao grupo de exclusão.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>Posso mudar do gerenciamento de dispositivos do Exchange ActiveSync para a mobilidade básica e segurança do Microsoft 365?

Se você já estiver usando políticas do Exchange ActiveSync para gerenciar dispositivos móveis, poderá começar a usar mobilidade básica e segurança seguindo as etapas para configurar a mobilidade e a segurança básica. Para obter mais informações, consulte [proteger o acesso de usuário e dispositivo](https://go.microsoft.com/fwlink/?LinkId=615145) e [Configurar a mobilidade e a segurança básica](set-up.md).

Ao aplicar as políticas que você cria em mobilidade básica e segurança a grupos de usuários, essas políticas substituem as políticas de caixa de correio de dispositivo móvel do Exchange ActiveSync e as regras de acesso de dispositivo que você criou anteriormente no centro de administração do Exchange para esses usuários.

Após um dispositivo ser inscrito em mobilidade básica e segurança, qualquer política de caixa de correio de dispositivo móvel do Exchange ActiveSync ou regra de acesso de dispositivo aplicada ao dispositivo é ignorada.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>Configure mobilidade básica e segurança, mas agora desejo removê-la. Quais são as etapas?

Infelizmente, não é possível simplesmente "desconfigurar" a mobilidade básica e a segurança após configurá-la. Mas você pode removê-lo para grupos de usuários, removendo grupos de segurança do usuário das políticas de dispositivo que você criou. Ou você pode desabilitá-lo para todos, removendo as políticas de dispositivo para que elas não estejam vigentes e não sejam aplicadas. Para obter mais informações, consulte [desative a mobilidade básica e a segurança](turn-off.md).

