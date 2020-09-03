---
title: Configurar a Mobilidade Básica e a Segurança
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
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
description: Configurar mobilidade básica e segurança para proteger e gerenciar os dispositivos móveis dos seus usuários.
ms.openlocfilehash: 0d62c209d4eb9d0da9096ccd5ca2d4a387becf95
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336706"
---
# <a name="set-up-basic-mobility-and-security"></a>Configurar a Mobilidade Básica e a Segurança

A mobilidade básica e a segurança interna do Microsoft 365 ajudam a proteger e gerenciar os dispositivos móveis dos usuários, como iPhones, iPads, Androids e Windows phones. Você pode criar e gerenciar políticas de segurança de dispositivo, apagar remotamente um dispositivo e exibir relatórios detalhados de dispositivos.

Have questions? Para obter perguntas FREQUENTEs para ajudar a resolver perguntas comuns, consulte [Basic Mobility and Security Frequently Questions (FAQ)](basic-mobility-and-security-frequently-asked-questions.md). Lembre-se de que não é possível usar uma conta de administrador delegada para gerenciar a mobilidade e a segurança básica. Para obter mais informações, consulte [parceiros: oferecer administração delegada](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e). 

O gerenciamento de dispositivos faz parte do centro de conformidade & segurança para que você precise ir para lá para começar a configuração do MDM.

## <a name="activate-the-basic-mobility-and-security-service"></a>Ativar o serviço de segurança e mobilidade básica

1. Entre no Microsoft 365 com sua conta de administrador global.
    

2. Vá para [ativar a mobilidade básica e a segurança](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).
    
    Pode levar algum tempo para ativar a mobilidade básica e a segurança. Quando terminar, você receberá um email que explica as próximas etapas a serem executadas.

## <a name="set-up-mobile-device-management"></a>Configurar o gerenciamento de dispositivos móveis

Quando o serviço estiver pronto, complete as etapas a seguir para concluir a instalação.

### <a name="step-1-required-configure-domains-for-mdm"></a>Etapa 1: (obrigatório) configurar domínios para o MDM

Se você não tiver um domínio personalizado associado ao Microsoft 365 ou se não estiver gerenciando dispositivos do Windows, ignore esta seção. Caso contrário, você precisará adicionar registros DNS para o domínio no seu host DNS. Se você já tiver adicionado os registros, como parte da configuração do seu domínio com o Microsoft 365, tudo pronto. Depois de adicionar os registros, os usuários do Microsoft 365 em sua organização que entram no seu dispositivo Windows com um endereço de email que usa seu domínio personalizado são redirecionados para se inscrever na mobilidade básica e segurança.

Precisa de ajuda para configurar os registros? Encontre seu registrador de domínios e selecione o nome do registrador para ir para a ajuda passo a passo para criar um registro DNS na lista fornecida em [adicionar registros DNS para conectar seu domínio](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider). Use essas instruções para criar registros CNAME descritos em [simplificar o registro do Windows sem o Azure ad Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).

Após adicionar os dois registros CNAME, volte para o centro de conformidade de & de segurança e vá para gerenciamento de dispositivo de **prevenção de perda de dados**  >  **Device management**   para concluir a próxima etapa.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Etapa 2: (obrigatório) configurar um certificado APNs para dispositivos iOS

Para gerenciar dispositivos iOS como iPad e iPhone, você precisa criar um certificado APNs.

1. Entre no Microsoft 365 com sua conta de administrador global.   

2. No seu navegador, digite:  [https://protection.office.com](https://protection.office.com/) .  

3. Selecione gerenciamento de dispositivo de **prevenção contra perda de dados**   >  **Device management**e escolha **certificado APNs para dispositivos IOS**.   

4. Na página Configurações de certificado de notificação por push da Apple, escolha **Avançar**.  

5. Selecione **baixar seu arquivo CSR**   e salvar a solicitação de assinatura de certificado em algum lugar no seu computador que você se lembrará. Selecione **Avançar**.
    
6. Na página criar um certificado APNs:
    
    - Selecione portal Apple APNS para abrir o portal Apple Push Certificates.
    - Sign in with an Apple ID.

    >[!IMPORTANT]
    >Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    - Selecione criar um certificado e aceitar os termos de uso.
    
    - Navegue para a solicitação de assinatura de certificado que você baixou para seu computador do Microsoft 365 e do selectUpload.
    
    - Downloadthe certificado APN criado pelo portal de certificado por push da Apple para seu computador.

    >[!TIP]
    >If you're having trouble downloading the certificate, refresh your browser.

7. Volte para o Microsoft 365 e selecione **Avançar**.   

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.   

9. Selecione  **concluir**.  

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Etapa 3: (recomendado) configurar a autenticação multifator

A MFA ajuda a proteger a entrada no Microsoft 365 para registro de dispositivos móveis exigindo uma segunda forma de autenticação. Os usuários precisam confirmar uma chamada telefônica, uma mensagem de texto ou uma notificação de aplicativo no dispositivo móvel depois de inserir corretamente a senha da conta de trabalho. Eles podem registrar o dispositivo somente após a conclusão da segunda forma de autenticação. Após os dispositivos de usuário serem registrados na mobilidade e segurança básica, os usuários podem acessar os recursos do Microsoft 365 com apenas suas contas de trabalho.

Para saber como ativar a MFA no portal do Azure AD, confira [Configurar a autenticação multifator](https://go.microsoft.com/fwlink/p/?LinkId=519255).

Depois de configurar a MFA, volte para o centro de conformidade de & de segurança e navegue até políticas de dispositivo de gerenciamento de **perda de dados**   >  **Device management**   >  **Device policies**   para concluir a próxima etapa.

### <a name="step-4-recommended-manage-device-security-policies"></a>Etapa 4: (recomendado) gerenciar políticas de segurança de dispositivos

A próxima etapa é criar e implantar políticas de segurança de dispositivo para ajudar a proteger seus dados de organização do Microsoft 365. Por exemplo, você pode ajudar a evitar a perda de dados se um usuário perder seu dispositivo criando uma política para bloquear dispositivos após cinco minutos de inatividade e apagar dispositivos após três falhas de entrada.

1. Entre no Microsoft 365 com sua conta de administrador global. 

2. Selecione [Ativar gerenciamento de dispositivo móvel](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx). Se o serviço for ativado, em vez disso, as etapas de ativação você verá um link para [gerenciar dispositivos](https://admin.microsoft.com/adminportal/home#/MifoDevices)   .
    
3. Vá para **políticas de dispositivo**.

     :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configurações básicas de política de segurança e mobilidade":::

4. Criar e implantar políticas de segurança de dispositivo apropriadas para sua organização seguindo as etapas em [criar políticas de segurança de dispositivo na mobilidade básica e segurança](create-device-security-policies-in-basic-mmobility-and-security.md).

>[!TIP]
    - Ao criar uma nova política, convém definir a política para permitir o acesso e a violação de política de relatório onde um dispositivo de usuário não está em conformidade com a política. Isso permite que você veja quantos dispositivos móveis são afetados pela política sem bloquear o acesso ao Microsoft 365.<br/>– Antes de implantar uma nova política para todas as pessoas em sua organização, recomendamos que você a teste nos dispositivos usados por um pequeno número de usuários.<br/>– Além disso, antes de implantar as políticas, permita que sua organização Conheça os possíveis impactos da inscrição de um dispositivo na mobilidade e segurança básica. Dependendo de como você configura as políticas, os dispositivos que não estão em conformidade com as políticas (dispositivos não compatíveis) podem ser impedidos de acessar o Microsoft 365. Dispositivos não compatíveis também podem ter aplicativos instalados, Fotos e outras informações pessoais que, em um dispositivo inscrito, podem ser excluídas se o dispositivo for apagado. Para obter mais informações, consulte [apagar um dispositivo móvel em mobilidade básica e segurança](wipe-mobile-device.md).
    
## <a name="make-sure-users-enroll-their-devices"></a>Certifique-se de que os usuários registrem seus dispositivos

Depois de criar e implantar uma política de gerenciamento de dispositivo móvel, cada usuário licenciado do Microsoft 365 em sua organização que a política de dispositivo aplica recebe uma mensagem de registro na próxima vez que entrar no Microsoft 365 a partir de seu dispositivo móvel. Eles devem concluir as etapas de registro e ativação antes que possam acessar o email e os documentos do Microsoft 365. Para saber mais, confira [registrar seu dispositivo móvel usando mobilidade básica e segurança](enroll-your-mobile-device-using-basic-mobility-and-security.md).

>[!IMPORTANT]
>Se o idioma preferencial de um usuário não for compatível com o processo de registro, os usuários poderão receber a notificação de registro e as etapas em seus dispositivos móveis em outro idioma. Nem todos os idiomas com suporte no Microsoft 365 têm suporte no momento para o processo de registro em dispositivos móveis.

Os usuários com dispositivos Android ou iOS são necessários para instalar o aplicativo do portal da empresa como parte do processo de registro.

## <a name="related-topics"></a>Tópicos Relacionados

[Recursos de mobilidade básica e segurança](capabilities-of-basic-mobility-and-secruity.md)<br/>
[Criar políticas de segurança de dispositivo na mobilidade básica e segurança](create-device-security-policies-in-basic-mmobility-and-security.md)