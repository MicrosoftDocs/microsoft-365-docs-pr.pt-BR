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
ms.openlocfilehash: 2448b95e5c5c5da25a916b659f6b49d04ba8f0c1
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339569"
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

## <a name="always-remediate-pua"></a>Sempre remediar PUA
Aplicativos potencialmente indesejados (PUA) são uma categoria de software que pode fazer com que seu computador seja executado lentamente, exibir anúncios inesperados ou, na pior das hipóteses, instalar outros softwares que podem ser inesperados ou indesejados. 

A turn on this feature so that potentially unwanted applications (PUA) are remediated on all devices in your tenant, even if PUA protection is not configured on the devices. Isso ajudará a proteger os usuários contra a instalação inadvertida de aplicativos indesejados em seus dispositivos. Quando desligado, a correção depende da configuração do dispositivo. 


## <a name="restrict-correlation-to-within-scoped-device-groups"></a>Restringir a correlação para dentro de grupos de dispositivos com escopo
Essa configuração pode ser usada para cenários em que as operações SOC locais gostaria de limitar as correlações de alerta apenas aos grupos de dispositivos que eles podem acessar. Ao ligar essa configuração, um incidente composto por alertas que cruzam grupos de dispositivos não será mais considerado um único incidente. O SOC local pode, em seguida, tomar medidas sobre o incidente porque eles têm acesso a um dos grupos de dispositivos envolvidos. No entanto, o SOC global verá vários incidentes diferentes por grupo de dispositivos em vez de um incidente. Não recomendamos a adoção dessa configuração, a menos que isso supere os benefícios da correlação de incidentes em toda a organização
>[!NOTE]
>Alterar essa configuração afeta apenas as futuras correlações de alerta.

## <a name="enable-edr-in-block-mode"></a>Habilitar EDR no modo de bloqueio
A detecção e a resposta do ponto de extremidade (EDR) no modo de bloqueio fornece proteção contra artefatos mal-intencionados, mesmo quando o Microsoft Defender Antivírus está sendo executado no modo passivo. Quando ligado, EDR no modo de bloqueio bloqueia artefatos mal-intencionados ou comportamentos detectados em um dispositivo. EDR no modo de bloqueio funciona nos bastidores para correção de artefatos mal-intencionados detectados após a violação.


## <a name="autoresolve-remediated-alerts"></a>Autoresolve correção de alertas

Para locatários criados em ou após Windows 10, versão 1809, o recurso de investigação e correção automatizado é configurado por padrão para resolver alertas em que o status de resultado de análise automatizada é "Nenhuma ameaça encontrada" ou "Correção".  Se você não quiser ter alertas resolvidos automaticamente, será necessário desativar manualmente o recurso.

> [!TIP]
> Para locatários criados antes dessa versão, você precisará ativar manualmente esse recurso na página [Recursos Avançados.](https://securitycenter.windows.com/preferences2/integration)

> [!NOTE]
>
> - O resultado da ação de resolução automática pode influenciar o cálculo do nível de risco do dispositivo que se baseia nos alertas ativos encontrados em um dispositivo.
> - Se um analista de operações de segurança define manualmente o status de um alerta como "Em andamento" ou "Resolvido" o recurso de resolução automática não o substituirá.

## <a name="allow-or-block-file"></a>Permitir ou bloquear arquivo

O bloqueio só estará disponível se sua organização atender a esses requisitos:

- Usa Microsoft Defender Antivírus como a solução antimalware ativa e,
- O recurso de proteção baseada em nuvem está habilitado

Esse recurso permite bloquear arquivos potencialmente mal-intencionados em sua rede. Bloquear um arquivo impedirá que ele seja lido, gravado ou executado em dispositivos em sua organização.

Para ativar **Permitir ou bloquear** arquivos:

1. No painel de navegação, selecione Configurações Pontos **de** Extremidade Gerais Recursos Avançados  >    >    >    >  **Gerais Permitir ou bloquear arquivo**.

1. Alterne a configuração **entre On** e **Off**.

    ![Imagem das configurações avançadas para o recurso de arquivo de bloqueio](images/atp-preferences-setup.png)

1. Selecione **Salvar preferências** na parte inferior da página.

Depois de acioná-lo, você pode [bloquear arquivos](respond-file-alerts.md#allow-or-block-file) por meio da guia **Adicionar Indicador** na página de perfil de um arquivo.

## <a name="custom-network-indicators"></a>Indicadores de rede personalizados

A ação desse recurso permite que você crie indicadores para endereços IP, domínios ou URLs, que determinam se eles serão permitidos ou bloqueados com base em sua lista de indicadores personalizados.

Para usar esse recurso, os dispositivos devem estar executando Windows 10 versão 1709 ou posterior. Eles também devem ter proteção de rede no modo de bloqueio e versão 4.18.1906.3 ou posterior da plataforma antimalware consulte [KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).

Para obter mais informações, consulte [Gerenciar indicadores](manage-indicators.md).

> [!NOTE]
> A proteção de rede aproveita os serviços de reputação que processam solicitações em locais que podem estar fora do local selecionado para seus dados do Defender para o Ponto de Extremidade.

## <a name="tamper-protection"></a>Proteção contra adulteração
Durante alguns tipos de ataques cibernéticos, os atores ruins tentam desabilitar recursos de segurança, como proteção antivírus, em seus computador. Os atores ruins gostam de desabilitar seus recursos de segurança para obter acesso mais fácil aos seus dados, instalar malware ou explorar seus dados, identidade e dispositivos.

A proteção contra violações essencialmente bloqueia Microsoft Defender Antivírus e impede que suas configurações de segurança seja alterada por meio de aplicativos e métodos.

Esse recurso estará disponível se sua organização usar Microsoft Defender Antivírus e a proteção baseada em nuvem estiver habilitada. Para obter mais informações, [consulte Use next-generation technologies in Microsoft Defender Antivírus through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md).

Mantenha a proteção contra adulteração 24h para evitar alterações indesejadas em sua solução de segurança e seus recursos essenciais.


## <a name="show-user-details"></a>Mostrar detalhes do usuário

A turn on this feature so that you can see user details stored in Azure Active Directory. Os detalhes incluem informações de imagem, nome, título e departamento de um usuário ao investigar entidades de conta de usuário. Você pode encontrar informações de conta de usuário nos seguintes exibições:

- Painel de operações de segurança
- Fila de alertas
- Página de detalhes do dispositivo

Para obter mais informações, consulte [Investigar uma conta de usuário](investigate-user.md).


## <a name="skype-for-business-integration"></a>Skype for Business integração

A habilitação da integração Skype for Business oferece a capacidade de se comunicar com os usuários usando Skype for Business, email ou telefone. Isso pode ser útil quando você precisa se comunicar com o usuário e reduzir riscos.

> [!NOTE]
> Quando um dispositivo está sendo isolado da rede, há um pop-up em que você pode optar por habilitar as comunicações Outlook e Skype que permitem comunicações com o usuário enquanto eles estão desconectados da rede. Essa configuração se aplica Skype e Outlook comunicação quando os dispositivos estão em modo de isolamento.

## <a name="microsoft-defender-for-identity-integration"></a>Integração do Microsoft Defender para Identidade

A integração com o Microsoft Defender para Identidade permite que você pivote diretamente em outro produto de segurança da Microsoft Identity. O Microsoft Defender for Identity aumenta uma investigação com informações adicionais sobre uma conta suspeita comprometida e recursos relacionados. Habilitando esse recurso, você enriquecerá o recurso de investigação baseado em dispositivo, girando em toda a rede de um ponto de vista de identificação.

> [!NOTE]
> Você precisará ter a licença apropriada para habilitar esse recurso.

## <a name="office-365-threat-intelligence-connection"></a>Office 365 Conexão de Inteligência contra Ameaças

Esse recurso só estará disponível se você tiver um Office 365 E5 ou o complemento Threat Intelligence. Para obter mais informações, consulte a página Office 365 Enterprise produto E5.

Ao ativar esse recurso, você poderá incorporar dados do Microsoft Defender para Office 365 no Microsoft 365 Defender para conduzir uma investigação abrangente de segurança em caixas de correio Office 365 e dispositivos Windows.

> [!NOTE]
> Você precisará ter a licença apropriada para habilitar esse recurso.

Para receber a integração de dispositivos contextuais Office 365 Inteligência contra Ameaças, você precisará habilitar as configurações do Defender para Ponto de Extremidade no painel Segurança & Conformidade. Para obter mais informações, consulte [Investigação e resposta contra ameaças.](/microsoft-365/security/office-365-security/office-365-ti)

## <a name="microsoft-threat-experts---targeted-attack-notifications"></a>Especialistas em Ameaças da Microsoft - Notificações de Ataque Direcionado

Dos dois componentes do Microsoft Threat Expert, a notificação de ataque direcionada está em disponibilidade geral. A funcionalidade especialistas sob demanda ainda está em visualização. Você só poderá usar o recurso especialistas sob demanda se tiver se aplicado à visualização e seu aplicativo tiver sido aprovado. Você pode receber notificações de ataque direcionadas Especialistas em Ameaças da Microsoft por meio do painel de alertas do portal do Defender para Ponto de Extremidade e por email se configurá-lo.

> [!NOTE]
> A Especialistas em Ameaças da Microsoft funcionalidade do Defender para Ponto de Extremidade está disponível com uma licença E5 para [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security).
## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

A habilitação dessa configuração encaminha os sinais do Defender para o Ponto de Extremidade para Microsoft Cloud App Security fornecer uma visibilidade mais profunda sobre o uso do aplicativo na nuvem. Os dados encaminhados são armazenados e processados no mesmo local que seus Cloud App Security dados.

> [!NOTE]
> Esse recurso estará disponível com uma licença E5 para Enterprise Mobility + Security [em](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) dispositivos que executam Windows 10, versão 1709 (build 16299.1085 com [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, versão 1803 (com build 17134.704 do sistema operacional com [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, versão 1809 (build do sistema operacional 17763.379 com [KB4489899 )](https://support.microsoft.com/help/4489899)ou versões posteriores Windows 10.

## <a name="microsoft-secure-score"></a>Microsoft Secure Score

Encaminha os sinais do Microsoft Defender para o Ponto de Extremidade para a Pontuação Segura da Microsoft no Microsoft 365 de segurança. A ação desse recurso dá visibilidade à Pontuação Segura da Microsoft na postura de segurança do dispositivo. Os dados encaminhados são armazenados e processados no mesmo local que seus dados de Pontuação Segura da Microsoft.


### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a>Habilitar a integração do Microsoft Defender para Ponto de Extremidade no portal do Microsoft Defender for Identity

Para receber a integração de dispositivo contextual no Microsoft Defender para Identidade, você também precisará habilitar o recurso no portal do Microsoft Defender para Identidade.

1. Faça logoff no [portal do Microsoft Defender for Identity](https://portal.atp.azure.com/) com uma função de Administrador Global ou Administrador de Segurança.

2. Clique **em Criar sua instância**.

3. Alterne a configuração Integração **para On** e clique em **Salvar**.

Após concluir as etapas de integração em ambos os portais, você poderá ver alertas relevantes na página detalhes do dispositivo ou detalhes do usuário.

## <a name="web-content-filtering"></a>Filtragem de conteúdo da Web
Bloqueie o acesso a sites que contêm conteúdo indesejado e acompanhe a atividade da Web em todos os domínios. Para especificar as categorias de conteúdo da Web que você deseja bloquear, crie uma política de [filtragem de conteúdo da Web.](https://security.microsoft.com/preferences2/web_content_filtering_policy) Verifique se você tem proteção de rede no modo de bloqueio ao implantar a linha de base de segurança do [Microsoft Defender para Ponto de Extremidade.](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2)


## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a>Compartilhar alertas de ponto de extremidade com o Centro de Conformidade da Microsoft
Encaminha alertas de segurança do ponto de extremidade e seu status de triagem para o Centro de Conformidade da Microsoft, permitindo que você aprimora as políticas de gerenciamento de riscos internos com alertas e correção de riscos internos antes que causem danos. Os dados encaminhados são processados e armazenados no mesmo local que seus Office 365 dados.

Depois de configurar os [indicadores](/microsoft-365/compliance/insider-risk-management-settings#indicators) de violação de política de segurança nas configurações de gerenciamento de riscos insider, os alertas do Defender para Ponto de Extremidade serão compartilhados com o gerenciamento de riscos insider para usuários aplicáveis.



## <a name="microsoft-intune-connection"></a>Microsoft Intune conexão

O Defender para Ponto de Extremidade pode ser integrado ao [Microsoft Intune](/intune/what-is-intune) para [habilitar o](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)acesso condicional baseado em risco do dispositivo. Ao ativar [esse recurso,](configure-conditional-access.md)você poderá compartilhar informações do dispositivo Defender for Endpoint com o Intune, aprimorando a aplicação da política.

> [!IMPORTANT]
> Você precisará habilitar a integração no Intune e no Defender for Endpoint para usar esse recurso. Para obter mais informações sobre etapas específicas, consulte [Configure Conditional Access in Defender for Endpoint](configure-conditional-access.md).

Esse recurso só estará disponível se você tiver o seguinte:

- Um locatário licenciado para Enterprise Mobility + Security E3 e Windows E5 (ou Microsoft 365 Enterprise E5)
- Um ambiente Microsoft Intune ativo, com os dispositivos Windows 10 do [Azure AD ingressados no](/azure/active-directory/devices/concept-azure-ad-join/)Intune.


### <a name="conditional-access-policy"></a>Política de Acesso Condicional

Ao habilitar a integração com o Intune, o Intune criará automaticamente uma política clássica de Acesso Condicional (CA). Essa política de AC clássica é um pré-requisito para configurar relatórios de status no Intune. Ele não deve ser excluído.

> [!NOTE]
> A política de AC clássica criada pelo Intune é distinta das políticas modernas de [Acesso](/azure/active-directory/conditional-access/overview/)Condicional , que são usadas para configurar pontos de extremidade.


## <a name="device-discovery"></a>Descoberta de dispositivo
Ajuda você a encontrar dispositivos não administrativos conectados à sua rede corporativa sem a necessidade de dispositivos extras ou alterações de processo complicadas. Usando dispositivos conectados, você pode encontrar dispositivos nãomanageados em sua rede e avaliar vulnerabilidades e riscos. Para obter mais informações, consulte [Descoberta de dispositivo](device-discovery.md).

> [!NOTE]
> Você sempre pode aplicar filtros para excluir dispositivos não gerenciamento da lista de inventário de dispositivos. Você também pode usar a coluna de status de integração em consultas de API para filtrar dispositivos não-gerenciamento. 

## <a name="preview-features"></a>Recursos de visualização

Saiba mais sobre os novos recursos na versão de visualização do Defender for Endpoint. Experimente os recursos futuros ao ligar a experiência de visualização.

Você terá acesso aos recursos futuros, nos quais você pode fornecer comentários para ajudar a melhorar a experiência geral antes que os recursos geralmente sejam disponibilizados.




## <a name="related-topics"></a>Tópicos relacionados

- [Atualizar configurações de retenção de dados](data-retention-settings.md)
- [Configurar notificações de alerta](configure-email-notifications.md)
