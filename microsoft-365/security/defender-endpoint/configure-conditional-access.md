---
title: Configurar o Acesso Condicional no Microsoft Defender para Ponto de Extremidade
description: Saiba mais sobre as etapas que você precisa fazer no Intune, Microsoft 365 Defender e no Azure para implementar o acesso condicional
keywords: acesso condicional, condicional, acesso, risco de dispositivo, nível de risco, integração, integração do intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2c9462fa0d4be4d6ff78ba3e5db2cd4fa71fef0b
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339509"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a>Configurar o Acesso Condicional no Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Esta seção orienta você por todas as etapas necessárias para implementar corretamente o Acesso Condicional.

### <a name="before-you-begin"></a>Antes de começar
>[!WARNING]
>É importante observar que não há suporte para dispositivos registrados no Azure AD neste cenário.</br>
>Somente dispositivos inscritos do Intune têm suporte.


Você precisa se certificar de que todos os seus dispositivos estão inscritos no Intune. Você pode usar qualquer uma das seguintes opções para registrar dispositivos no Intune:


- Administrador de IT: Para obter mais informações sobre como habilcar o registro automático, [consulte Windows Registro](/intune/windows-enroll#enable-windows-10-automatic-enrollment)
- Usuário final: para obter mais informações sobre como registrar seu dispositivo Windows 10 no Intune, consulte Registrar seu dispositivo [Windows 10 no Intune](/intune/quickstart-enroll-windows-device)
- Alternativa para o usuário final: para obter mais informações sobre como ingressar em um domínio do Azure AD, consulte Como: Planejar a implementação de junção do [Azure AD](/azure/active-directory/devices/azureadjoin-plan).



Há etapas que você precisará seguir no Microsoft 365 Defender, no portal do Intune e no portal do Azure AD.

É importante observar as funções necessárias para acessar esses portais e implementar o acesso condicional:
- **Microsoft 365 Defender** - Você precisará entrar no portal com uma função de administrador global para ativar a integração.
- **Intune** - Você precisará entrar no portal com direitos de administrador de segurança com permissões de gerenciamento. 
- **Portal do Azure AD** - Você precisará entrar como administrador global, administrador de segurança ou administrador de Acesso Condicional.


> [!NOTE]
> Você precisará de um ambiente Microsoft Intune, com o Intune gerenciado e o Azure AD ingressado Windows 10 dispositivos.

Tome as seguintes etapas para habilitar o Acesso Condicional:
- Etapa 1: Ativar a conexão Microsoft Intune de Microsoft 365 Defender
- Etapa 2: Ativar a integração do Defender para Ponto de Extremidade no Intune
- Etapa 3: Criar a política de conformidade no Intune
- Etapa 4: Atribuir a política 
- Etapa 5: Criar uma política de Acesso Condicional do Azure AD


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a>Etapa 1: ativar a Microsoft Intune conexão
1. No painel de navegação, **selecione** Configurações Recursos Avançados Gerais dos Pontos de Extremidade  >    >    >  **Microsoft Intune**  >  **conexão**.
2. Alterne a configuração Microsoft Intune para **On**.
3. Clique **em Salvar preferências**.


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a>Etapa 2: Ativar a integração do Defender para Ponto de Extremidade no Intune
1. Entre no [portal do Azure](https://portal.azure.com).
2. Selecione **Conformidade de dispositivo** Microsoft Defender  >  **ATP**.
3. De **Conexão Windows 10.0.15063+ dispositivos** para Proteção Avançada contra Ameaças do Microsoft Defender como **On**.
4. Clique em **Salvar**.


### <a name="step-3-create-the-compliance-policy-in-intune"></a>Etapa 3: Criar a política de conformidade no Intune
1. No portal [do Azure,](https://portal.azure.com)selecione **Todos os serviços,** filtre no **Intune** e selecione **Microsoft Intune**.
2. Selecione **Políticas de conformidade de**  >  **dispositivo** Criar  >  **política**.
3. Insira um **Nome e** **Descrição.**
4. Em **Plataforma,** selecione **Windows 10 e posterior.**
5. Nas **configurações de Saúde** do Dispositivo, desempate Exigir que o dispositivo seja **ou sob** o Nível de Ameaça de Dispositivo para o nível preferencial:

   - **Protegido**: esse nível é o mais seguro. O dispositivo não pode ter ameaças existentes e ainda acessar recursos da empresa. Se alguma ameaça for encontrada, o dispositivo será avaliado como não compatível.
   - **Baixo**: o dispositivo é compatível se existirem apenas ameaças de baixo nível. Dispositivos com níveis médios ou altos de ameaça não são compatíveis.
   - **Médio**: o dispositivo é compatível se as ameaças encontradas no dispositivo são baixas ou médias. Se ameaças de alto nível são detectadas, o dispositivo é determinado como não compatível.
   - **Alto**: esse nível é o menos seguro e permite todos os níveis de ameaça. Portanto, dispositivos que com níveis de ameaça altos, médios ou baixos são considerados compatíveis.

6. Selecione **OK** e **Criar para** salvar suas alterações (e criar a política).

### <a name="step-4-assign-the-policy"></a>Etapa 4: Atribuir a política
1. No portal [do Azure,](https://portal.azure.com)selecione **Todos os serviços,** filtre no **Intune** e selecione **Microsoft Intune**.
2. Selecione **Políticas de conformidade**  >  **de** dispositivo> sua política de conformidade do Microsoft Defender para Ponto de Extremidade.
3. Selecione **Atribuições**.
4. Inclua ou exclua seus grupos do Azure AD para atribuir a política a eles.
5. Para implantar a política nos grupos, selecione **Salvar**. Os dispositivos de usuário direcionados pela política são avaliados para conformidade.

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a>Etapa 5: Criar uma política de Acesso Condicional do Azure AD
1. No portal [do Azure,](https://portal.azure.com)abra **Azure Active Directory** nova política  >  **de Acesso**  >  **Condicional.**
2. Insira um nome **de política** e selecione Usuários **e grupos.** Use as opções Incluir ou Excluir para adicionar seus grupos para a política e selecione **Feito**.
3. Selecione **Aplicativos de nuvem** e escolha quais aplicativos proteger. Por exemplo, escolha **Selecionar aplicativos** e selecione **Office 365 SharePoint Online** e **Office 365 Exchange Online**. Selecione **Concluído** para salvar as alterações.

4. Selecione **Condições**  >  **Aplicativos de cliente** para aplicar a política a aplicativos e navegadores. Por exemplo, selecione **Sim** e, em seguida, habilitar **aplicativos** de navegador e **móveis e clientes de área de trabalho.** Selecione **Concluído** para salvar as alterações.

5. Selecione **Conceder para** aplicar o Acesso Condicional com base na conformidade do dispositivo. Por exemplo, selecione **Conceder acesso** Exigir que o dispositivo seja marcado  >  **como compatível**. Escolha **Selecionar** para salvar suas alterações.

6. Selecione **Habilitar política** e, em **seguida, Criar** para salvar suas alterações.

Para obter mais informações, [consulte Enforce compliance for Microsoft Defender for Endpoint with Conditional Access in Intune](/intune/advanced-threat-protection).

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
