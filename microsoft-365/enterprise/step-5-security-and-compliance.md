---
title: 'Etapa 5: Considerações de segurança e conformidade'
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Saiba mais sobre as considerações importantes de conformidade e segurança do Windows e do Office.
ms.openlocfilehash: cefab9cfd1b61f37559d88c5625c512d33595395
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400235"
---
# <a name="step-5-security-and-compliance-considerations"></a>Etapa 5: Considerações de segurança e conformidade

![](media/step-5-security-and-compliance-media/step-5-security-and-compliance-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-8.png" alt="Step 5" height="135" width="135" /></td>
<td><p><strong>Etapa 5: Considerações de segurança e conformidade</strong></p>
<p>O Windows 10 e o Office 365 ProPlus oferecem novas formas de proteger dados, dispositivos e usuários e de detectar e responder rapidamente a ameaças. Além disso, aprenda a lidar com problemas comuns associados a criptografia de discos, aplicativos antimalware e políticas ao migrar para o Windows 10.</p></td>
<td><a href="https://aka.ms/ddev5" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-18.png" alt="Step 5" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Segurança e Conformidade é a quinta etapa do nosso processo recomendado de implantação que abrange as considerações de segurança e conformidade do Windows 10 e do Office 365 ProPlus. Para ver o processo completo de implantação de desktop, visite o [Centro de Implantação do Computador](https://aka.ms/HowToShift).
>

Chegou o momento de examinar suas opções de direcionamento de novos recursos de segurança e conformidade como parte da implantação do Windows 10 e do Office 365 ProPlus, juntamente com as considerações e bloqueios comuns ao migrar de versões anteriores do Windows e do Office. Muitos dos recursos relacionados à segurança no Windows 10 são os responsáveis pela migração para a plataforma mais recente. Além disso, a integração com os serviços em nuvem no Office 365 e as opções de identidade usando o Azure Active Directory dão acesso a proteções novas e continuamente atualizadas de dados, dispositivos e usuários.

## <a name="overcoming-potential-security-related-deployment-blockers"></a>Superar bloqueios em potencial relacionados à segurança

Antes de explicar os novos recursos que podem ser adicionados na sua migração para o Windows 10 e o Office 365 ProPlus e conectar essas experiências à nuvem, vamos começar com algumas tendências que estamos vendo e que frequentemente podem interromper o andamento da implantação.

### <a name="disk-encryption"></a>Criptografia de disco

Primeiro, um dos desafios iniciais que você pode enfrentar é a criptografia de disco rígido. Muitas soluções para a criptografia de disco rígido não podem ser atualizadas com facilidade de uma versão anterior do Windows para uma versão mais recente do Windows.

Algumas soluções de criptografia de disco permitem que você execute as atualizações quando estiver usando a opção ‘/reflectdrivers’ na Instalação do Windows em determinadas versões das plataformas, mas outras poderão precisar que você descriptografe a unidade antes de criptografar novamente após a instalação do Windows 10. Algumas soluções também não permitem que você migre do Master Boot Record (MBR, registro mestre de inicialização), usando BIOS herdado, para GUID Partition Table (GPT, tabela de partição de GUID), obrigatório para UEFI. Isso é importante porque uma versão de 64 bits do Windows 10 com UEFI é necessária para os novos recursos de segurança baseados em virtualização no Windows 10, e eles são explicados abaixo.

Uma opção para resolver esses problemas é usar o BitLocker no Windows 10, que está incluído no Windows 10 Pro e em versões superiores. O BitLocker permite que você suspenda a proteção de atualizações do sistema operacional e de atualizações de recursos como parte do processo.

[Implantação básica do Bitlocker](https://docs.microsoft.com/pt-BR/windows/security/information-protection/bitlocker/bitlocker-basic-deployment)

### <a name="antivirus-and-antimalware-application-compatibility"></a>Compatibilidade de aplicativos antivírus e antimalware

Em segundo lugar, ainda que tenhamos visto que mais de [99% dos aplicativos do Windows são compatíveis](https://www.microsoft.com/pt-BR/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/) entre o Windows 7 e o Windows 10, as exceções são frequentemente aplicativos antivírus (AV) ou clientes VPN (Virtual Private Network, rede privada virtual). Esses aplicativos frequentemente implementam práticas de desenvolvimento não padrão e APIs, usando com frequência formas não documentadas de proteger seu sistema ou conectá-lo aos recursos de rede.

Como resultado, esses aplicativos, por natureza, podem ser frágeis a alterações ao migrar para uma nova versão do Windows. Caso seu software AV ou VPN não funcione no Windows 10 ou depois da atualização, a correção normalmente é substituir o aplicativo que está usando por um com suporte e testado no Windows 10.

### <a name="security-policies"></a>Políticas de segurança

As configurações da Política de Grupo do Active Directory usadas para versões mais antigas do Windows e do Office poderão não serem convertidas diretamente para o Windows 10 e o Office 365 ProPlus, e há diferentes considerações com recursos de conformidade e segurança mais recentes. É uma boa ideia usar o Kit de Ferramentas de Conformidade e Segurança da Microsoft para obter uma linha de base das políticas de segurança para versões atuais do Windows e do Office. Além disso, vale a pena ler as políticas de Gerenciamento de Dispositivos Móveis como parte do Microsoft Intune.

![](media/step-5-security-and-compliance-media/step-5-security-and-compliance-media-3.png)

## 

## <a name="new-security-and-compliance-capabilities-in-microsoft-365"></a>Novos recursos de segurança e conformidade no Microsoft 365

Essas foram as considerações para migrar suas proteções atuais e itens a saber antes da migração. Agora observaremos os novos recursos que você pode aproveitar ao migrar para o Windows 10, Office 365 ProPlus e opções baseadas em nuvem do EMS e além.

### <a name="identity-and-access-management"></a>Gerenciamento de identidades e acesso

Começando com o gerenciamento de identidades e acesso. O Azure Active Directory é o plano de controle de identidade para aplicativos, dispositivos e serviços em nuvem e é a forma moderna de se conectar ao Office 365 e a outros serviços em nuvem. O acesso condicional permite que você defina diferentes requisitos de autenticação de acordo com o local do qual está acessando, qual dispositivo está usando, além de casos como comportamentos anômalos.

No nível do dispositivo, a biometria pode fornecer identificadores únicos para oferecer um acesso mais seguro para seus dispositivos e aplicativos, conforme você segue na direção da meta de eliminar senhas. O Windows Hello oferece autenticação multifator baseada em dispositivo. Ela confia no próprio dispositivo, em seu PIN ou no identificador biométrico exclusivo, como seu rosto ou sua impressão digital, que você pode aplicar por política.

[Noções básicas do gerenciamento de identidade do Azure](https://docs.microsoft.com/pt-BR/azure/active-directory/fundamentals/identity-fundamentals)

[Entender as soluções de identidade do Azure](https://docs.microsoft.com/pt-BR/azure/active-directory/fundamentals/understand-azure-identity-solutions)

[Acesso condicional do Azure Active Directory](https://docs.microsoft.com/pt-BR/azure/active-directory/conditional-access/overview)

[Windows Hello para Empresas](https://docs.microsoft.com/pt-BR/windows/security/identity-protection/hello-for-business/hello-identity-verification)

### <a name="virtualization-based-security"></a>Segurança baseada em virtualização

Agora, além da identidade, você também pode habilitar a proteção contínua contra ameaças conhecidas ou não. Para fazer isso, o Windows 10 usa a segurança baseada em virtualização no núcleo para assegurar a integridade da inicialização e do código usando a Inicialização Segura. Também podemos ajudar a evitar o roubo de credenciais com a Proteção de Credenciais, ao manter os segredos do usuário isolados do Windows. E a Proteção de Aplicativos pode isolar e reduzir as ameaças baseadas em navegador ao executá-lo em um contêiner isolado. Todas essas tecnologias usam segurança baseada em virtualização no Windows 10 e são alterações fundamentais que não podem ser replicadas em um sistema Windows 7. Isso também precisa do UEFI, do Windows de 64 bits e de suporte a extensão de virtualização com SLAT no nível do hardware.

[Saiba mais sobre a segurança baseada em virtualização](https://docs.microsoft.com/pt-BR/windows-hardware/design/device-experiences/oem-vbs)

### <a name="security-enhancements-from-cloud-services"></a>Aprimoramentos de segurança de serviços em nuvem

Os serviços em nuvem oferecem outra camada de proteção opcional para melhorar a segurança do Windows e do Office. Isso pode oferecer um novo nível de controle frequente em tempo real que pode detectar, resistir e responder instantaneamente a novos ataques e tipos de ataques, especialmente comparados à atualização tradicional de software e arquivos de assinatura de AV, nos quais os tempos de implantação de atualização e de resposta são inerentemente mais lentos.

Com o Gráfico de Segurança Inteligente da Microsoft, você tem acesso mais rápido a informações e proteções de novas ameaças. Você pode aproveitar algumas dessas vantagens, começando pelo Office.

**[Prevenção contra perda de dados](https://docs.microsoft.com/pt-BR/office365/securitycompliance/data-loss-prevention-policies)** integrada ao Office 365 ProPlus ajuda a informar os usuários de políticas de segurança quando conteúdo de alto risco, como números de cartão de crédito ou de identificação, são detectados. As políticas podem informar ou bloquear o envio e o compartilhamento depois de notificar os usuários.

A **[Proteção de Informações do Azure](https://docs.microsoft.com/pt-BR/azure/information-protection/rms-client/client-admin-guide)** é um serviço complementar que pode ser usado com o Office, permitindo aos usuários classificar e rotular com facilidade os arquivos do Office. Ela pode acionar uma ação automática em arquivos rotulados, como criptografia ou bloquear o compartilhamento.

Também apresentamos a proteção **[Links Seguros](https://docs.microsoft.com/pt-BR/office365/securitycompliance/atp-safe-links)** em aplicativos do Office para protegê-lo contra uma lista dinâmica de sites mal-intencionados conhecidos.

Além disso, os **[Anexos Seguros](https://docs.microsoft.com/pt-BR/office365/securitycompliance/atp-safe-attachments)** no Outlook, e como parte do Exchange Online, vão além da filtragem de emails para inspecionar anexos. Se um anexo de alto risco for identificado, os Anexos Seguros informarão ao usuário sobre anexos mal-intencionados conhecidos e os removerá do email.

A **[Criptografia de Mensagens do Office 365](https://docs.microsoft.com/pt-BR/office365/securitycompliance/encryption)** (OME) também pode se usada para proteger o email e os anexos enviados, assegurando que apenas os destinatários desejados possam ver o conteúdo do email. O OME funciona de forma simples com autenticação de conta de cliente Google, Yahoo e Microsoft, e senhas para uso único permitem aos usuários de outros serviços de email receberem emails também.

#### <a name="additional-windows-10-protections"></a>Outras proteções do Windows 10

O **[Controle de Aplicativos do Windows Defender](https://docs.microsoft.com/pt-BR/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)** no Windows 10 opera de acordo com uma lista de permissões e negações que a Microsoft verificou para fins de segurança e tudo que é gerenciado pelas políticas de proteção de endpoint usando o Microsoft Intune.

A **[Proteção Avançada Contra Ameaças do Windows Defender](https://docs.microsoft.com/pt-BR/windows/security/threat-protection/windows-defender-atp/overview)** é uma plataforma unificada para proteção preventiva, detecção pós-violação, investigação automatizada e resposta. Ela protege os pontos de extremidade de ameaças cibernéticas, detecta ataques avançados e violações de dados, automatiza os incidentes de segurança e melhora a postura de segurança.

A **[Proteção contra Exploração](https://docs.microsoft.com/pt-BR/windows/security/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)** ajuda a reduzir a superfície de ataques de aplicativos em execução evitando que o malware entre no Windows e impedindo que processos não confiáveis acessem as pastas protegidas.

#### <a name="microsoft-intune"></a>Microsoft Intune

O [Microsoft Intune](https://docs.microsoft.com/pt-BR/intune/introduction-intune) serve como um serviço de gerenciamento em nuvem para cenários móveis, inclusive dispositivos IOS, Android e Windows, e agora pode ser configurado para o gerenciamento conjunto de forma a complementar e ampliar os controles de cargas de trabalho específicas gerenciadas pelo System Center Configuration Manager. Uma vantagem aqui é que os dispositivos que acessam os recursos protegidos podem ser solicitados a inscrever-se no gerenciamento de dispositivos, mesmo nos dispositivos não gerenciados e que não entraram no domínio ou no Azure AD. Você também pode aproveitar a configuração granular e a aplicação de política de conformidade no nível do aplicativo e do sistema operacional. As políticas e as configurações de aplicativos podem ser configuradas de forma central e aplicadas no Office 365 ProPlus e em aplicativos da Store no Windows 10 usando o Microsoft Intune.

## <a name="next-step"></a>Próxima etapa

## <a name="step-6-os-deployment-and-feature-updateshttpsakamsmdd6"></a>[Etapa 6: Implantação de sistema operacional e atualizações de recursos](https://aka.ms/mdd6)

## <a name="previous-step"></a>Etapa anterior 

## <a name="step-4-user-files-and-settingshttpsakamsmdd4"></a>[Etapa 4: Arquivos e configurações de usuários](https://aka.ms/mdd4)
