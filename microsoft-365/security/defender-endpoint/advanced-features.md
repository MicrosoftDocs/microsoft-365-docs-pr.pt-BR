---
title: Configurar recursos avançados no Microsoft Defender para Ponto de Extremidade
description: A ativar recursos avançados, como o arquivo de bloqueio no Microsoft Defender para Ponto de Extremidade.
keywords: recursos avançados, configurações, arquivo de bloqueio, investigação automatizada, resolução automática, skype, microsoft defender para identidade, office 365, proteção de informações do azure, intune
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
ms.openlocfilehash: 684025441c8400775f469515df1bcd0423d6460b
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394741"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a>Configurar recursos avançados no Defender para Ponto de Extremidade

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

Dependendo dos produtos de segurança da Microsoft que você usa, alguns recursos avançados podem estar disponíveis para integrar o Defender para o Ponto de Extremidade.

## <a name="enable-advanced-features"></a>Habilitar recursos avançados

1. No painel de navegação, selecione **Configuração de preferências**  >  **Recursos avançados**.
2. Selecione o recurso avançado que você deseja configurar e alterne a configuração entre **On** e **Off**.
3. Clique **em Salvar preferências**.

Use os recursos avançados a seguir para se proteger melhor de arquivos potencialmente mal-intencionados e obter informações melhores durante investigações de segurança.

## <a name="automated-investigation"></a>Investigação automatizada

A ativar esse recurso para aproveitar os recursos automatizados de investigação e correção do serviço. Para obter mais informações, consulte [Investigação automatizada](automated-investigations.md).

## <a name="live-response"></a>Resposta ao vivo

A turn on this feature so that users with the appropriate permissions can start a live response session on devices.

Para obter mais informações sobre atribuições de função, consulte [Create and manage roles](user-roles.md).

## <a name="live-response-for-servers"></a>Resposta ao vivo para servidores
A turn on this feature so that users with the appropriate permissions can start a live response session on servers.

Para obter mais informações sobre atribuições de função, consulte [Create and manage roles](user-roles.md).


## <a name="live-response-unsigned-script-execution"></a>Execução de script não assinado de resposta ao vivo

A habilitação desse recurso permite executar scripts não assinados em uma sessão de resposta ao vivo.


## <a name="restrict-correlation-to-within-scoped-device-groups"></a>Restringir a correlação para dentro de grupos de dispositivos com escopo
Quando essa configuração é acionada, os alertas são correlacionados em incidentes separados com base no grupo de dispositivos com escopo. Por padrão, a correlação de incidentes ocorre em todo o escopo do locatário.

>[!NOTE]
>Alterar essa configuração afeta apenas as futuras correlações de alerta.


## <a name="autoresolve-remediated-alerts"></a>Autoresolve correção de alertas

Para locatários criados em ou após o Windows 10, versão 1809, o recurso de investigação e correção automatizado é configurado por padrão para resolver alertas em que o status do resultado da análise automatizada é "Nenhuma ameaça encontrada" ou "Correção".  Se você não quiser ter alertas resolvidos automaticamente, será necessário desativar manualmente o recurso.

> [!TIP]
> Para locatários criados antes dessa versão, você precisará ativar manualmente esse recurso na página [Recursos Avançados.](https://securitycenter.windows.com/preferences2/integration)

> [!NOTE]
>
> - O resultado da ação de resolução automática pode influenciar o cálculo do nível de risco do dispositivo que se baseia nos alertas ativos encontrados em um dispositivo.
> - Se um analista de operações de segurança define manualmente o status de um alerta como "Em andamento" ou "Resolvido" o recurso de resolução automática não o substituirá.

## <a name="allow-or-block-file"></a>Permitir ou bloquear arquivo

O bloqueio só estará disponível se sua organização atender a esses requisitos:

- Usa o Microsoft Defender Antivírus como a solução antimalware ativa e,
- O recurso de proteção baseada em nuvem está habilitado

Esse recurso permite bloquear arquivos potencialmente mal-intencionados em sua rede. Bloquear um arquivo impedirá que ele seja lido, gravado ou executado em dispositivos em sua organização.

Para ativar **Permitir ou bloquear** arquivos:

1. No painel de navegação, selecione **Configurações**  >  **Recursos avançados** Permitir ou bloquear  >  **arquivo**.

1. Alterne a configuração **entre On** e **Off**.

    ![Imagem das configurações avançadas para o recurso de arquivo de bloqueio](images/atp-preferences-setup.png)

1. Selecione **Salvar preferências** na parte inferior da página.

Depois de acioná-lo, você pode [bloquear arquivos](respond-file-alerts.md#allow-or-block-file) por meio da guia **Adicionar Indicador** na página de perfil de um arquivo.

## <a name="custom-network-indicators"></a>Indicadores de rede personalizados

A ação desse recurso permite que você crie indicadores para endereços IP, domínios ou URLs, que determinam se eles serão permitidos ou bloqueados com base em sua lista de indicadores personalizados.

Para usar esse recurso, os dispositivos devem estar executando o Windows 10 versão 1709 ou posterior. Eles também devem ter proteção de rede no modo de bloqueio e versão 4.18.1906.3 ou posterior da plataforma antimalware consulte [KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).

Para obter mais informações, consulte [Gerenciar indicadores](manage-indicators.md).

> [!NOTE]
> A proteção de rede aproveita os serviços de reputação que processam solicitações em locais que podem estar fora do local selecionado para seus dados do Defender para o Ponto de Extremidade.

## <a name="show-user-details"></a>Mostrar detalhes do usuário

A active this feature so that you can see user details stored in Azure Active Directory. Os detalhes incluem informações de imagem, nome, título e departamento de um usuário ao investigar entidades de conta de usuário. Você pode encontrar informações de conta de usuário nos seguintes exibições:

- Painel de operações de segurança
- Fila de alertas
- Página de detalhes do dispositivo

Para obter mais informações, consulte [Investigar uma conta de usuário](investigate-user.md).

## <a name="skype-for-business-integration"></a>Integração do Skype for Business

A habilitação da integração do Skype for Business oferece a capacidade de se comunicar com usuários usando o Skype for Business, email ou telefone. Isso pode ser útil quando você precisa se comunicar com o usuário e reduzir riscos.

> [!NOTE]
> Quando um dispositivo está sendo isolado da rede, há um pop-up em que você pode optar por habilitar as comunicações do Outlook e do Skype que permitem comunicações com o usuário enquanto eles estão desconectados da rede. Essa configuração se aplica à comunicação do Skype e do Outlook quando os dispositivos estão no modo de isolamento.

## <a name="azure-advanced-threat-protection-integration"></a>Integração da Proteção Avançada contra Ameaças do Azure

A integração com a Proteção Avançada contra Ameaças do Azure permite que você pivote diretamente em outro produto de segurança da Microsoft Identity. A Proteção Avançada contra Ameaças do Azure aumenta uma investigação com informações adicionais sobre uma conta suspeita comprometida e recursos relacionados. Habilitando esse recurso, você enriquecerá o recurso de investigação baseado em dispositivo, girando em toda a rede de um ponto de vista de identificação.

> [!NOTE]
> Você precisará ter a licença apropriada para habilitar esse recurso.

## <a name="office-365-threat-intelligence-connection"></a>Conexão de Inteligência de Ameaças do Office 365

Esse recurso só estará disponível se você tiver um Office 365 E5 ativo ou o complemento threat Intelligence. Para obter mais informações, consulte a página de produtos do Office 365 Enterprise E5.

Ao ativar esse recurso, você poderá incorporar dados da Proteção Avançada contra Ameaças do Office 365 no Centro de Segurança do Microsoft Defender para conduzir uma investigação abrangente de segurança em caixas de correio do Office 365 e dispositivos Windows.

> [!NOTE]
> Você precisará ter a licença apropriada para habilitar esse recurso.

Para receber a integração de dispositivo contextual no Office 365 Threat Intelligence, você precisará habilitar as configurações do Defender para Ponto de Extremidade no painel Segurança & Conformidade. Para obter mais informações, consulte [Investigação e resposta contra ameaças.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)

## <a name="microsoft-threat-experts"></a>Especialistas em Ameaças da Microsoft

Dos dois componentes do Microsoft Threat Expert, a notificação de ataque direcionada está em disponibilidade geral. A funcionalidade especialistas sob demanda ainda está em visualização. Você só poderá usar o recurso especialistas sob demanda se tiver se aplicado à visualização e seu aplicativo tiver sido aprovado. Você pode receber notificações de ataque direcionadas dos Especialistas em Ameaças da Microsoft por meio do painel de alertas do portal do Defender para Pontos de Extremidade e por email se você configurá-lo.

> [!NOTE]
> O recurso Especialistas em Ameaças da Microsoft no Defender para Ponto de Extremidade está disponível com uma licença E5 para [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security).

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

A habilitação dessa configuração encaminha sinais do Defender para o Ponto de Extremidade para o Microsoft Cloud App Security para fornecer uma visibilidade mais profunda sobre o uso de aplicativos na nuvem. Os dados encaminhados são armazenados e processados no mesmo local que seus dados de Segurança do Aplicativo na Nuvem.

> [!NOTE]
> Esse recurso estará disponível com uma licença E5 para [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) em dispositivos que executam o Windows 10, versão 1709 (Com build do sistema operacional 16299.1085 com [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, versão 1803 (build 17134.704 do sistema operacional com [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, versão 1809 (build 17763.379 do sistema operacional com [KB4489899 )](https://support.microsoft.com/help/4489899)ou versões posteriores do Windows 10.

## <a name="azure-information-protection"></a>Proteção de Informações do Azure

A ação dessa configuração permite que os sinais sejam encaminhados para a Proteção de Informações do Azure. Ele dá aos proprietários de dados e aos administradores visibilidade dos dados protegidos em dispositivos e classificações de risco de dispositivos.

## <a name="microsoft-secure-score"></a>Microsoft Secure Score

Encaminha os sinais do Microsoft Defender para o Ponto de Extremidade para a Pontuação Segura da Microsoft no centro de segurança do Microsoft 365. A ação desse recurso dá visibilidade à Pontuação Segura da Microsoft na postura de segurança do dispositivo. Os dados encaminhados são armazenados e processados no mesmo local que seus dados de Pontuação Segura da Microsoft.

### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a>Habilitar a integração do Microsoft Defender para Ponto de Extremidade no portal do Microsoft Defender for Identity

Para receber a integração de dispositivo contextual no Microsoft Defender para Identidade, você também precisará habilitar o recurso no portal do Microsoft Defender para Identidade.

1. Faça logoff no [portal do Microsoft Defender for Identity](https://portal.atp.azure.com/) com uma função de Administrador Global ou Administrador de Segurança.

2. Clique **em Criar sua instância**.

3. Alterne a configuração Integração **para On** e clique em **Salvar**.

Após concluir as etapas de integração em ambos os portais, você poderá ver alertas relevantes na página detalhes do dispositivo ou detalhes do usuário.

## <a name="microsoft-intune-connection"></a>Conexão do Microsoft Intune

O Defender for Endpoint pode ser integrado ao [Microsoft Intune](https://docs.microsoft.com/intune/what-is-intune) para [habilitar o](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)acesso condicional baseado em risco de dispositivo. Ao ativar [esse recurso,](configure-conditional-access.md)você poderá compartilhar informações do dispositivo Defender for Endpoint com o Intune, aprimorando a aplicação da política.

> [!IMPORTANT]
> Você precisará habilitar a integração no Intune e no Defender for Endpoint para usar esse recurso. Para obter mais informações sobre etapas específicas, consulte [Configure Conditional Access in Defender for Endpoint](configure-conditional-access.md).

Esse recurso só estará disponível se você tiver o seguinte:

- Um locatário licenciado para Enterprise Mobility + Security E3 e Windows E5 (ou Microsoft 365 Enterprise E5)
- Um ambiente ativo do Microsoft Intune, com dispositivos Windows 10 gerenciados pelo Intune [Azure AD ingressado](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/).

### <a name="conditional-access-policy"></a>Política de acesso condicional

Ao habilitar a integração com o Intune, o Intune criará automaticamente uma política clássica de Acesso Condicional (CA). Essa política de AC clássica é um pré-requisito para configurar relatórios de status no Intune. Ele não deve ser excluído.

> [!NOTE]
> A política de AC clássica criada pelo Intune é distinta das políticas modernas de [Acesso](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/)Condicional , que são usadas para configurar pontos de extremidade.

## <a name="preview-features"></a>Recursos de pré-visualização

Saiba mais sobre os novos recursos na versão de visualização do Defender para Ponto de Extremidade e entre os primeiros a experimentar os recursos futuros, ligando a experiência de visualização.

Você terá acesso aos recursos futuros, nos quais você pode fornecer comentários para ajudar a melhorar a experiência geral antes que os recursos geralmente sejam disponibilizados.

## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a>Compartilhar alertas de ponto de extremidade com o Centro de Conformidade da Microsoft

Encaminha alertas de segurança do ponto de extremidade e seu status de triagem para o Centro de Conformidade da Microsoft, permitindo que você aprimora as políticas de gerenciamento de riscos internos com alertas e correção de riscos internos antes que causem danos. Os dados encaminhados são processados e armazenados no mesmo local que seus dados do Office 365.

Depois de configurar os [indicadores](/microsoft-365/compliance/insider-risk-management-settings#indicators) de violação de política de segurança nas configurações de gerenciamento de riscos insider, os alertas do Defender para Ponto de Extremidade serão compartilhados com o gerenciamento de riscos insider para usuários aplicáveis.

## <a name="related-topics"></a>Tópicos relacionados

- [Atualizar configurações de retenção de dados](data-retention-settings.md)
- [Configurar notificações de alerta](configure-email-notifications.md)
