---
title: Perguntas frequentes sobre mobilidade básica e segurança (perguntas frequentes)
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
ms.openlocfilehash: a538c0b3f9fa6a4bf1861734fc9dea94030760a3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906259"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>Perguntas frequentes sobre mobilidade básica e segurança (perguntas frequentes)

Este artigo contém perguntas frequentes sobre Mobilidade Básica e Segurança, um recurso que ajuda você a gerenciar e proteger dispositivos móveis no Microsoft 365. Se você não conseguir encontrar uma resposta para sua pergunta, nos avise deixando um comentário na página para que possamos considerar adicionar sua pergunta a este artigo.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>Como posso obter Mobilidade Básica e Segurança? Não o vejo no centro de administração do Microsoft 365

1.  Ative a Mobilidade Básica e a Segurança indo para a página Conformidade & [Segurança do Office 365.](https://protection.office.com/)

2.  Vá para Prevenção contra perda de dados > Gerenciamento de dispositivos.

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>Como começar a usar o gerenciamento de dispositivos em Mobilidade Básica e Segurança?

Há quatro etapas para começar com o Basic Mobility and Security: 

1. Ative a Mobilidade Básica e a Segurança indo para o [Office 365 Security & Compliance.](https://protection.office.com/)

2. Vá para Prevenção contra perda de dados > Gerenciamento de dispositivos > Políticas de dispositivo.
    
3. Crie políticas de gerenciamento de dispositivos e aplique-as a grupos de usuários que estão definidos em grupos de segurança. Recomendamos que você comece implantando as políticas em um pequeno grupo de teste. Para obter mais informações, consulte [Create device security policies in Basic Mobility and Security](create-device-security-policies.md).

4. Os usuários que tiveram uma política aplicada a eles são solicitados a registrar seus dispositivos quando tentarem acessar dados do Microsoft 365. Para obter mais informações, consulte [Registrar seu dispositivo móvel usando o Basic Mobility and Security](enroll-your-mobile-device.md).

Para obter mais detalhes, [consulte Set up Basic Mobility and Security](set-up.md).

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Estou tentando configurar o Basic Mobility and Security, mas parece travado. A Saúde do Serviço do Microsoft 365 mostra "provisionamento" há algum tempo. O que posso fazer?

Pode levar algum tempo para preparar o serviço para você. Quando o provisionamento for concluído, você verá a página Mobilidade Básica e Segurança. Se você tiver esperado 24 horas e o status ainda estiver provisionando, entre em contato com o Suporte e ajudaremos a descobrir qual é o problema. Para opções de suporte, consulte [Still need help?](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp).

## <a name="what-can-i-do-if-device-enrollment-fails"></a>O que posso fazer se o registro do dispositivo falhar?

Se você estiver com problemas para registrar um dispositivo, primeiro verifique o seguinte:

- Certifique-se de que o dispositivo ainda não está inscrito em outro provedor de gerenciamento de dispositivo móvel, como o Intune.

- Certifique-se de que o dispositivo está definido como a data e a hora corretas.

- Alternar para uma rede WIFI ou celular diferente no dispositivo.

- Para dispositivos Android ou iOS, desinstale e reinstale o aplicativo do Portal da Empresa do Intune no dispositivo.
    
Se o registro ainda não estiver funcionando, consulte [Troubleshoot Basic Mobility and Security](troubleshoot.md).

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Qual é a diferença entre o Intune e o Basic Mobility and Security?

A Mobilidade Básica e Segurança é hospedada pelo serviço do Intune. É um subconjunto de serviços do Intune fornecidos como um benefício adicionado ao Microsoft 365 e é uma solução baseada em nuvem integrada para gerenciar dispositivos em sua organização. Para uma comparação lado a lado dos dois serviços para ajudá-lo a decidir se usar o Intune ou o Basic Mobility and Security para o Microsoft 365 é o melhor ajuste para você, consulte [Choose between Basic Mobility Security and Intune](choose-between-basic-mobility-and-security-and-intune.md).

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>Como as políticas funcionam para Mobilidade Básica e Segurança? Como faço para defini-los? Desabilitá-los?

Depois de concluir a configuração inicial para Mobilidade Básica e Segurança, crie políticas e aplique-as a grupos de usuários no Centro de Conformidade & Segurança. As políticas exigem que os usuários das políticas inscrevam seus dispositivos no Basic Mobility and Security antes que o dispositivo possa ser usado para acessar dados do Microsoft 365. As políticas configuradas determinam as configurações para dispositivos móveis, por exemplo, com que frequência as senhas devem ser redefinidas ou se a criptografia de dados é necessária. Para obter mais informações, [consulte Create device security policies in Basic Mobility and Security](create-device-security-policies.md)and Microsoft   [365 compliance center](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8).

Para obter instruções passo a passo para criar e implantar políticas de dispositivo, consulte [Create device security policies in Basic Mobility and Security](create-device-security-policies.md).

Se você quiser excluir um grupo específico de usuários de serem afetados por políticas, você pode adicionar um grupo ao grupo de exclusão.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>Posso alternar do gerenciamento de Exchange ActiveSync para o Basic Mobility and Security para o Microsoft 365?

Se você já estiver usando políticas Exchange ActiveSync para gerenciar dispositivos móveis, comece a usar a Mobilidade Básica e a Segurança seguindo as etapas para configurar a Mobilidade Básica e a Segurança. Para obter mais informações, consulte [Protect user and device access](../../compliance/protect-access-to-data-and-services.md) and Set up Basic [Mobility and Security](set-up.md).

Quando você aplica as políticas criadas no Basic Mobility and Security a grupos de usuários Exchange ActiveSync, essas políticas substituem as políticas de caixa de correio de dispositivo móvel e as regras de acesso a dispositivos que você criou anteriormente no Centro de administração do Exchange para esses usuários.

Depois que um dispositivo é inscrito no Basic Mobility and Security Exchange ActiveSync, qualquer política de caixa de correio de dispositivo móvel ou regra de acesso de dispositivo móvel aplicada ao dispositivo é ignorada.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>Eu configurar o Basic Mobility and Security, mas agora quero removê-lo. Quais são as etapas?

Infelizmente, você não pode simplesmente "desprovisionar" Basic Mobility and Security depois de configurar. Mas você pode removê-lo para grupos de usuários removendo grupos de segurança do usuário das políticas de dispositivo criadas. Ou, você pode desabilitá-lo para todos removendo as políticas de dispositivo para que elas não sejam aplicadas e não sejam impostas. Para obter mais informações, [consulte Desativar Mobilidade Básica e Segurança.](turn-off.md)