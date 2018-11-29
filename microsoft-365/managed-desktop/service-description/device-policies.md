---
title: Configuração de dispositivo
description: Saiba mais sobre as políticas padrão aplicadas aos dispositivos Microsoft Desktop gerenciados.
keywords: Serviço Microsoft Managed Desktop, 365 da Microsoft, documentação
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 5a97f44641ac38a8785bde66819dbfffffee946d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865126"
---
# <a name="device-configuration"></a>Configuração de dispositivo


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Quando um novo dispositivo de área de trabalho gerenciada do Microsoft está sendo provisionado, garantimos a configuração correta, otimizada para Microsoft Desktop gerenciados, está no lugar. Isso inclui um conjunto de políticas padrão que estão configurados como parte do processo de inclusão. Para evitar conflitos, essas políticas não devem ser alteradas. 

Dispositivos chegarem com uma imagem da assinatura, e ingressar em domínio do Windows Azure Active Directory quando o primeiro usuário fizer logon. O dispositivo instalará automaticamente políticas necessárias e aplicativos sem qualquer intervenção de TI necessárias.

## <a name="why-mdm-over-group-policy"></a>Por que MDM sobre diretiva de grupo

Há poucos motivos para usar o gerenciamento de dispositivos móveis (MDM) em vez de diretiva de grupo:

- Segurança – MDM políticas são mais seguras do mundo moderno. Diretiva de grupo é projetado para funcionar melhor com a identidade do local. MDM projetado para funcionar melhor com o gerenciamento de identidades de nuvem (Azure Active Directory (AD Azure)).
- Confiabilidade - políticas MDM fornecem mais confiável implantação da diretiva. Configurações de MDM substituir as políticas de objeto de diretiva de grupo (GPO). Começando com Windows 10, versão 1803, configurações de MDM terão prioridade sobre os valores da diretiva de grupo. Isso oferece suporte a clientes que estejam mudando para gerenciamento moderno. 
- Alinha com a visão da Microsoft Desktop gerenciados - melhor monitoramento na implantação da diretiva. Suporte a abordagem baseada em ligar para alterações de diretiva de distribuição gradualmente com capacidade para pausar / continuar a implantação quando necessário.

## <a name="default-policies"></a>Políticas padrão

Este destaques tabela a políticas padrão que são aplicados a todos os dispositivos de área de trabalho do Microsoft gerenciados durante o provisionamento de dispositivo. Para evitar conflitos, essas políticas não devem ser alteradas. Todos os detectados alterações não aprovadas pela equipe de operações de área de trabalho gerenciada do Microsoft aos objetos gerenciados pelo Microsoft Desktop gerenciados serão revertidas.

Política | Descrição
--- | ---
Linha de base de segurança | O [Microsoft baseline de segurança](https://docs.microsoft.com/windows/device-security/windows-security-baselines) para MDM é configurado para todos os dispositivos de área de trabalho do Microsoft gerenciados. Essa linha de base é a configuração padrão do setor. Ele for lançado publicamente, bem testados e foi analisado por especialistas de segurança da Microsoft para manter os dispositivos de área de trabalho gerenciada do Microsoft e seguro de aplicativos no local de trabalho moderno.<br><br>Para atenuar as ameaças no cenário das ameaças de segurança-evoluem, a linha de base de segurança do Microsoft será atualizada e implantada nos dispositivos Microsoft Desktop gerenciados com cada atualização de recurso do Windows 10.<br><br>Para obter mais informações, consulte [Security baseline para Windows 10](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/).
Microsoft Desktop gerenciados recomendado de modelo de segurança | Um conjunto de alterações na linha de base de segurança recomendadas que otimizar a experiência do usuário.  Essas alterações são documentadas nos [Addendum a segurança](#security-addendum). Atualizações para o addendum política ocorrerem em conforme necessário.  
Conformidade de dispositivo | Essas diretivas são configuradas por padrão para todos os dispositivos de área de trabalho do Microsoft gerenciados. Um dispositivo é relatado como incompatíveis quando uma das seguintes condições de segurança não for atendida:<br>-Criptografia de dispositivo BitLocker habilitado, para proteger os dados em dispositivos. Para obter mais informações, consulte [Visão geral do dispositivo de disco BitLocker no Windows 10.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)<br>-Inicialização segura habilitada e imposto para validar as imagens do firmware em dispositivos antes que eles podem executar. Para obter mais informações, consulte [overview segura de criptografia de inicialização e o dispositivo.](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)<br>-Senha necessária para acessar os dispositivos Microsoft Desktop gerenciados.
Implantação da atualização | Use o Windows Update para negócios (WUfB) para executar a implantação gradual de atualizações de software. Administradores de TI não podem modificar as configurações de diretivas de ligar para a implantação. Para obter mais informações sobre implantação baseada em anel, consulte [como as atualizações são manipuladas](../working-with-managed-desktop/updates.md).
Telemetria | Forneça dados de diagnóstico avançada à Microsoft sob um identificador comercial conhecido dispositivos serão definidos. Para os clientes em geral regiões de regulamentação de proteção de dados (GDPR), os usuários finais podem reduzir o nível de dados de diagnóstico que são fornecidos. Você pode personalizá-la, mas haverá uma redução no serviço. Para obter mais informações, consulte [dados de diagnóstico de configurar o Windows em sua organização.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="advanced-policies"></a>Diretivas avançadas

 Estas são as políticas adicionais que podem ser configuradas para um ambiente mais seguro/bloqueado, para setores altamente regulamentado.

 Política | Descrição
 --- | ---
 Recursos avançados | Proteção de informações do Windows (WIP) & proteção de informações do Windows Azure (AIP) são usados para proteger os dados corporativos, permitindo apenas o acesso a determinados indivíduos ou um subconjunto dos aplicativos/serviços. Para obter mais informações, consulte<br>- [Proteger os dados da sua empresa usando a proteção de informações do Windows](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)<br>- [Guia do administrador de cliente Information Protection Azure](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)<br>- [Microsoft gerenciados Addendum de segurança da área de trabalho](#security-addendum)

 ## <a name="security-addendum"></a>Addendum de segurança

 Esta seção descreve as políticas que serão implantadas como adicionais com as políticas padrão do Microsoft Desktop gerenciados. Políticas padrão são listadas nas [políticas padrão](#default-policies). Essa configuração foi projetada com serviços financeiros e altamente regulamentado setores em mente: otimização para a posição mais segura, enquanto preservam a produtividade do usuário.

Em uma alteração ao publicado **Security baseline**, a configuração [**não exibe a seleção de rede da interface do usuário**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowslogon#windowslogon-dontdisplaynetworkselectionui) será desabilitada.

 ### <a name="additional-security-policies"></a>Diretivas de segurança adicionais

 Essas diretivas são adicionadas para aumentar a segurança para setores altamente regulamentado. 
 - **Lista de permissões do aplicativo**: aplicativos devem ser confiáveis pela organização para executar em dispositivos Microsoft Desktop gerenciados. Isso oferece um ambiente bloqueado. Quaisquer aplicativos que precisam ser onboarded devem ser comunicados para a equipe de operações de área de trabalho gerenciada do Microsoft. Para obter mais informações, consulte [Windows Defender dispositivo Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide).
 - **Monitoramento de segurança**: Microsoft monitorará dispositivos usando [A proteção de ameaça avançado do Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Se uma ameaça ser detectada, Microsoft notificará o cliente, isolar o dispositivo e corrigir o problema remotamente. 
 - **Explorar Guard**: estamos garantirá que dispositivos Microsoft Desktop gerenciados sempre são protegidos com a atualização de segurança mais recente, sistema operacional e aplicativos, usando o [Windows Update para negócios](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb). Será configurado exploração Guard com estas configurações:

 Configuração | Política
 --- | ---
 Sinalizar credencial roubar do subsistema de autoridade de segurança local do Windows | Somente auditoria
 Aplicativos Office injeção aos outros processos | Somente auditoria
 Office apps/macros, criação de conteúdo executável | Bloquear
 Aplicativos Office launching processos filho | Somente auditoria
 Win32 importa do código de macro do Office | Bloquear
 Ofuscados código js/vbs/ps/macro | Bloquear
 Executá-lo carga js/vbs baixados da internet (sem exceções) | Bloquear
 Criação do processo de comandos PSExec e WMI | Somente auditoria
 Processos assinados e não confiáveis que executam o USB | Bloquear
 Executáveis que não atendem aos critérios de listas confiáveis, idade ou uma chamadas | Somente auditoria
 A execução de conteúdo executável descartados do email | Bloquear
 Proteção avançada ransomware | Somente auditoria









