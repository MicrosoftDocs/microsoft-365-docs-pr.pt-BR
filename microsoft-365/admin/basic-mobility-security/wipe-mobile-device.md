---
title: Apagar um dispositivo móvel em Mobilidade e Segurança Básica
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
description: Use a Mobilidade Básica e a Segurança interna para remover informações de dispositivos inscritos.
ms.openlocfilehash: 3bb9bfe55653b021ce5a86dd5d3dbc3de45ed19a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876823"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Apagar um dispositivo móvel em Mobilidade e Segurança Básica

Você pode usar o Basic Mobility and Security integrado para o Microsoft 365 para remover apenas informações organizacionais ou para executar uma redefinição de fábrica para excluir todas as informações de um dispositivo móvel e restaurá-la para as configurações de fábrica.

## <a name="before-you-begin"></a>Antes de começar

Os dispositivos móveis podem armazenar informações organizacionais confidenciais e fornecer acesso aos recursos do Microsoft 365 da sua organização. Para ajudar a proteger as informações da sua organização, você pode fazer a redefinição de fábrica ou remover dados da empresa:

- **Redefinição de** fábrica: exclui todos os dados no dispositivo móvel de um usuário, incluindo aplicativos instalados, fotos e informações pessoais. Quando a limpeza for concluída, o dispositivo será restaurado para suas configurações de fábrica.

- **Remover dados da** empresa: remove somente os dados da organização e deixa aplicativos, fotos e informações pessoais instalados no dispositivo móvel de um usuário.

- **Quando um dispositivo é apagado (redefinição** de fábrica ou remover dados da empresa), o dispositivo é removido da lista de dispositivos gerenciados.
    
- **Redefinir** automaticamente um dispositivo: você pode configurar uma política básica de mobilidade e segurança que redefine automaticamente um dispositivo de fábrica depois que o usuário tenta inserir a senha do dispositivo várias vezes. Para fazer isso, siga as etapas em [Criar políticas de segurança de dispositivos em mobilidade e segurança básicas.](create-device-security-policies.md)
    
- **Se você quiser saber a experiência do usuário** ao apagar o dispositivo, veja O que é o impacto do usuário e do   [dispositivo?](#whats-the-user-and-device-impact).

## <a name="wipe-a-mobile-device"></a>Apagar um dispositivo móvel

1. Vá para o [Centro de administração do Microsoft 365.](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)

2. Digite Gerenciamento de Dispositivo Móvel no campo de pesquisa e selecione Gerenciamento de Dispositivo **Móvel** na lista de resultados.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opção de gerenciamento de dispositivo móvel Basic Mobility e Secruity":::

3. Selecione **Gerenciar dispositivos.**

4. Selecione o dispositivo que deseja apagar.

5. Selecione **Gerenciar**.

6. Selecione o tipo de apagamento remoto que deseja executar.

    - Para fazer uma limpeza completa e restaurar o dispositivo para suas configurações de fábrica, selecione **Redefinição de fábrica.**
    - Para fazer uma limpeza seletiva e excluir apenas informações da organização do Microsoft 365, selecione **Remover dados da empresa.**
    - Para remover o dispositivo da sua organização, selecione **Remover dispositivo.**

7. Selecione **Sim** para confirmar.

## <a name="how-do-i-know-it-worked"></a>Como saber se funcionou?

Você não verá mais o dispositivo móvel na lista de dispositivos gerenciados.

## <a name="why-would-you-want-to-wipe-a-device"></a>Por que você deseja apagar um dispositivo?

Limpe um dispositivo por estes motivos:

- Dispositivos móveis, como smartphones e tablets, estão se tornando mais completos o tempo todo. Isso significa que é mais fácil para os usuários armazenar informações corporativas confidenciais, como identificação pessoal ou comunicações confidenciais, e acessá-la em qualquer lugar. Se um desses dispositivos móveis for perdido ou roubado, apagar o dispositivo pode ajudar a impedir que as informações da sua organização acabarem em mãos erradas.
- Quando um usuário deixa a organização com um dispositivo pessoal que está inscrito no Basic Mobility and Security, você pode ajudar a impedir que as informações organizacionais vão com esse usuário executando uma redefinição de fábrica.
- Se sua organização fornece dispositivos móveis aos usuários, talvez seja necessário reatribuir dispositivos de tempos em tempos. Fazer uma redefinição de fábrica em um dispositivo antes de atribuí-la a um novo usuário ajuda a garantir que qualquer informação sensível do proprietário anterior seja excluída.

## <a name="whats-the-user-and-device-impact"></a>Qual é o impacto do usuário e do dispositivo?

O apagamento é enviado imediatamente para o dispositivo móvel e o dispositivo é marcado como não compatível no Azure Active Directory. Embora todos os dados são removidos quando um dispositivo é redefinido para os padrões de fábrica, a tabela a seguir descreve qual conteúdo é removido para cada tipo de dispositivo quando um dispositivo é removido.

|**Impace de conteúdo**|**iOS 10 e posterior**|**Android 5 e posterior**|
|:-----|:-----|:-----|
|Os dados de aplicativo do Microsoft 365 serão apagados se o dispositivo estiver protegido pelas políticas de Proteção de Aplicativos do Intune. Os aplicativos não são removidos. Para dispositivos não protegidos por políticas de Gerenciamento de Aplicativo Móvel (MAM), o Outlook e o OneDrive não removerão dados armazenados em cache.<br/>**Observação** Para aplicar políticas de proteção de aplicativos do Intune, você deve ter uma licença do Intune.|Sim|Sim|
|As configurações de política aplicadas pela Mobilidade Básica e Segurança aos dispositivos não são mais impostas; os usuários podem alterar as configurações.|Sim|Sim|
|Os perfis de email criados pela Mobilidade Básica e Segurança são removidos e o email armazenado em cache no dispositivo é excluído.|Sim|N/D|
>[!NOTE]
>O aplicativo portal da empresa está disponível na App Store para iOS e na Play Store para dispositivos Android.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar a Mobilidade Básica e a Segurança](set-up.md)