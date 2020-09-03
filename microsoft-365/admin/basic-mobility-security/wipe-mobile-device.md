---
title: Apagar um dispositivo móvel em mobilidade básica e segurança
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
description: Usar mobilidade básica e segurança interna para remover informações de dispositivos registrados.
ms.openlocfilehash: 4d854c7d4d81cd0b49ec7f81a49de5478b08f049
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336701"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Apagar um dispositivo móvel em mobilidade básica e segurança

Você pode usar a mobilidade básica e a segurança interna do Microsoft 365 para remover apenas as informações organizacionais ou executar uma redefinição de fábrica para excluir todas as informações de um dispositivo móvel e restaurá-las às configurações de fábrica.

## <a name="before-you-begin"></a>Antes de começar

Os dispositivos móveis podem armazenar informações organizacionais confidenciais e fornecer acesso aos recursos do Microsoft 365 da sua organização. Para ajudar a proteger as informações da sua organização, você pode reconfigurar fábrica ou remover dados da empresa:
    
- **Redefinição de fábrica**: exclui todos os dados do dispositivo móvel de um usuário, incluindo aplicativos instalados, Fotos e informações pessoais. Quando o apagamento é concluído, o dispositivo é restaurado para suas configurações de fábrica.
    
- **Remover dados da empresa**: remove apenas os dados da organização e deixa aplicativos instalados, Fotos e informações pessoais no dispositivo móvel de um usuário.   

- **Quando um dispositivo é apagado (reinicialização de fábrica ou remover dados da empresa)**, o dispositivo é removido da lista de dispositivos gerenciados.
    
- **Redefinir automaticamente um dispositivo**: você pode configurar uma política de segurança e mobilidade básica que redefine automaticamente um dispositivo depois que o usuário tenta inserir a senha do dispositivo por um número específico de vezes. Para fazer isso, siga as etapas em [criar políticas de segurança de dispositivo em mobilidade básica e segurança](create-device-security-policies-in-basic-mmobility-and-security.md).
    
- **Se você quiser saber a experiência do usuário** ao apagar o dispositivo, confira o  [que é o impacto do usuário e do dispositivo?](#whats-the-user-and-device-impact).   

## <a name="wipe-a-mobile-device"></a>Apagar um dispositivo móvel

1. Vá para o [centro de administração do Microsoft 365](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).
    
2. Digite gerenciamento de dispositivo móvel no campo de pesquisa e selecione **Gerenciamento de dispositivo móvel** na lista de resultados. 

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Mobilidade básica e opção de gerenciamento de dispositivo móvel do secruity":::

3. Selecione **gerenciar dispositivos**.

4. Selecione o dispositivo que deseja apagar.

5. Selecione **gerenciar**.

6. Selecione o tipo de apagamento remoto que deseja executar.

    - Para fazer um apagamento completo e restaurar o dispositivo para suas configurações de fábrica, selecione **redefinição de fábrica**.
    - Para fazer uma limpeza seletiva e excluir apenas as informações da organização 365 da Microsoft, selecione **remover dados da empresa**.
    - Para remover o dispositivo da sua organização, selecione **remover dispositivo**.

7. Selecione **Sim** para confirmar.

## <a name="how-do-i-know-it-worked"></a>Como saber se funcionou?

Você não vê mais o dispositivo móvel na lista de dispositivos gerenciados.

## <a name="why-would-you-want-to-wipe-a-device"></a>Por que você gostaria de apagar um dispositivo?

Limpe um dispositivo por estes motivos:

- Dispositivos móveis como smartphones e tablets estão ficando mais repletos de tempo todo. Isso significa que é mais fácil para os usuários armazenarem informações confidenciais corporativas, como a identificação pessoal ou comunicações confidenciais e o acesso em trânsito. Se um desses dispositivos móveis for perdido ou roubado, a limpeza do dispositivo poderá ajudar a impedir que as informações da sua organização sejam terminadas nas mãos erradas.
- Quando um usuário deixa a organização com um dispositivo pessoal que está inscrito em mobilidade básica e segurança, você pode ajudar a evitar que as informações organizacionais entrem em um usuário executando uma redefinição de fábrica.
- Se sua organização fornece dispositivos móveis aos usuários, talvez seja necessário reatribuir dispositivos de tempos em tempos. Fazer uma redefinição de fábrica em um dispositivo antes de atribuí-lo a um novo usuário ajuda a garantir que qualquer informação confidencial do proprietário anterior seja excluída.

## <a name="whats-the-user-and-device-impact"></a>Qual é o impacto do usuário e do dispositivo?

O apagamento é enviado imediatamente para o dispositivo móvel e o dispositivo é marcado como não compatível no Azure Active Directory. Embora todos os dados sejam removidos quando um dispositivo é redefinido para os padrões de fábrica, a tabela a seguir descreve qual conteúdo é removido para cada tipo de dispositivo quando um dispositivo é removido quando você remove os dados da empresa.

|**Ritmo do conteúdo**|**iOS 10 e posterior**|**Android 5 e posterior**|
|:-----|:-----|:-----|
|Os dados do aplicativo Microsoft 365 serão apagados se o dispositivo estiver protegido pelas políticas de proteção de aplicativos do Intune. Os aplicativos não são removidos. Para dispositivos não protegidos por políticas de gerenciamento de aplicativo móvel (MAM), o Outlook e o OneDrive não removerão os dados armazenados em cache.<br/>**Observação** Para aplicar as políticas de proteção de aplicativos do Intune, você deve ter uma licença do Intune.|Sim|Sim|
|As configurações de política aplicadas pela mobilidade básica e segurança para dispositivos não são mais impostas; os usuários podem alterar as configurações.|Sim|Sim|
|Os perfis de email criados pela mobilidade básica e segurança são removidos e o email em cache no dispositivo é excluído.|Sim|N/D|
>[!NOTE] 
>O aplicativo do portal da empresa está disponível na App Store para iOS e no repositório de reprodução para dispositivos Android.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar a Mobilidade Básica e a Segurança](set-up-basic-mobility-and-security.md)