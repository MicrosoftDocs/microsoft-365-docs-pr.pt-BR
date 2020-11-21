---
title: Ameaças detectadas pelo Microsoft Defender Antivirus
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Saiba como o Microsoft Defender Antivirus protege seus dispositivos Windows contra ameaças de software, como vírus, malware e spyware.
ms.openlocfilehash: e3c8a1071625bba41af5f3cccd50f8484acac18d
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376673"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Ameaças detectadas pelo Microsoft Defender Antivirus

O Microsoft Defender Antivirus protege seus dispositivos Windows contra ameaças de software, como vírus, malware e spyware.

- Os vírus geralmente se espalham anexando seus códigos a outros arquivos em seu dispositivo ou rede e podem fazer com que programas infectados funcionem incorretamente.
- O malware inclui arquivos, aplicativos e códigos mal-intencionados que podem causar danos e interromper o uso normal de dispositivos. Além disso, o malware pode permitir acesso não autorizado, usar recursos do sistema, roubar senhas e informações de conta, bloquear seu computador e solicitar resgate e muito mais.
- O Spyware coleta dados, como atividades de navegação na Web e envia os dados para servidores remotos.
 
Para oferecer proteção contra ameaças, o Microsoft Defender Antivirus usa vários métodos. Esses métodos incluem proteção oferecida em nuvem, proteção em tempo real e atualizações de proteção dedicadas.

- A proteção oferecida pela nuvem ajuda a fornecer detecção e bloqueio quase instantâneos de ameaças novas e emergentes.
- A verificação contínua usa o monitoramento de comportamento de arquivo e de processo e outras técnicas (também conhecida como *proteção em tempo real*).
- As atualizações de proteção dedicadas são baseadas no aprendizado de máquina, análises de grandes dados automatizadas e humanas e pesquisa de resistência de ameaças aprofundadas. 

Para saber mais sobre malware e o Microsoft Defender Antivirus, consulte os seguintes artigos: 

- [Noções básicas sobre malware & outras ameaças](/windows/security/threat-protection/intelligence/understanding-malware)
- [Como a Microsoft identifica malware e aplicativos potencialmente indesejados](/windows/security/threat-protection/intelligence/criteria)
- [Proteção de próxima geração no Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>O que acontece quando uma solução antivírus não-Microsoft é usada? 

O Microsoft Defender Antivirus faz parte do sistema operacional e está habilitado em dispositivos que executam o Windows 10. No entanto, se você estiver usando uma solução antivírus não-Microsoft e não estiver usando [o Microsoft defender para ponto de extremidade](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection), o Microsoft Defender Antivirus entrará automaticamente no modo desabilitado.  

Quando no modo desabilitado, os usuários e clientes ainda podem usar o Microsoft defender antivírus para verificações programadas ou sob demanda para identificar ameaças; no entanto, o Microsoft defender antivírus não terá mais:

- ser usado como o aplicativo antivírus padrão.
- examinar ativamente os arquivos em busca de ameaças.
- corrigir, ou resolver, ameaças.

Se você desinstalar a solução antivírus não-Microsoft, o Microsoft defender antivírus entrará automaticamente no modo ativo para proteger seus dispositivos Windows contra ameaças.

> [!TIP]
> - Se você estiver usando o Microsoft 365, considere o uso do Microsoft defender antivírus como sua solução antivírus principal. A integração pode oferecer melhor proteção. Veja [melhor juntos: Microsoft Defender Antivirus e Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).
> - Certifique-se de manter o Microsoft defender antivírus atualizado, mesmo que você esteja usando uma solução antivírus que não seja da Microsoft.

## <a name="what-to-expect-when-threats-are-detected"></a>O que esperar quando ameaças são detectadas

Quando as ameaças são detectadas pelo Microsoft Defender Antivirus, acontece o seguinte:

- Os usuários recebem [notificações no Windows](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e). 
- As detecções são listadas no [aplicativo de segurança do Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) na página **histórico de proteção** .  
- Se você [protegeu seus dispositivos Windows 10](secure-win-10-pcs.md) e [os registrou no Intune](/mem/intune/enrollment/windows-enrollment-methods), verá as detecções de ameaças e os insights no centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Administração do Microsoft 365</a> na página **de ameaças ativas** , que você pode acessar da placa do **Microsoft defender antivírus** na **Home** Page (ou no painel de navegação, selecionando ameaças de **integridade**  >  **& antivírus**).
    > [!NOTE]
    > A página do **Microsoft Defender Antivirus** e as **ameaças ativas** estão sendo distribuídas em fases, portanto, talvez você não tenha acesso imediato a elas.

Na maioria dos casos, os usuários não precisam executar mais ações. Assim que um programa ou arquivo mal-intencionado é detectado em um dispositivo, o Microsoft Defender Antivirus o bloqueia e impede sua execução. Além disso, ameaças recentemente detectadas são adicionadas ao mecanismo antivírus e antimalware para que outros dispositivos e usuários também estejam protegidos.  

Se houver uma ação que um usuário precisa tomar, como aprovar a remoção de um arquivo mal-intencionado, ele verá que na notificação receberá. Para saber mais sobre as ações que o Microsoft Defender Antivirus assume em nome de um usuário ou ações que os usuários podem precisar executar, consulte [histórico de proteção](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708). Para saber como gerenciar as detecções de ameaças como um profissional/administrador de ti, consulte [revisar ameaças detectadas e executar ações](review-threats-take-action.md).

Para saber mais sobre diferentes ameaças, visite o <a href="https://www.microsoft.com/wdsi/threats" target="_blank">site Microsoft Security Intelligence threats</a>, onde você pode executar as seguintes ações: 

- Exibir informações atuais sobre as principais ameaças.
- Exibir as ameaças mais recentes para uma região específica.
- Pesquise a enciclopédia de ameaças para obter detalhes sobre uma ameaça específica.

## <a name="related-content"></a>Conteúdo relacionado

[Proteger dispositivos Windows 10](secure-windows-10-devices.md) (artigo) \
[Avalie o Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (artigo) \
[Como ativar a proteção antivírus em tempo real e na nuvem](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (artigo) \
[Como ativar e usar o Microsoft defender antivírus no aplicativo de segurança do Windows](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (artigo) \
[Como ativar o Microsoft defender antivírus usando a política de grupo](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (artigo) \
[Como atualizar suas definições de antivírus](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (artigo) \
[Como enviar malware e não malware para a Microsoft para análise](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (artigo)