---
title: Recuperar de um ataque de ransomware
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Os administradores do Microsoft 365 podem aprender a se recuperar de um ataque de ransomware.
ms.openlocfilehash: 29afb66dd90be3917d576a7533900e21a91966c0
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224704"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Recuperar de um ataque de ransomware no Microsoft 365

Mesmo que você tenha cuidado para proteger sua organização, ainda pode ser vítima de um ataque de [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) . O ransomware é grande negócio, e os ataques são sofisticados.

As etapas deste tópico lhe dão a melhor chance de recuperar os dados que foram criptografados pelo ransomware e ajudarão a parar a disseminação da infecção em sua organização. Antes de começar, considere os seguintes itens:

- Não há garantias de que o pagamento do resgate retornará o acesso aos seus arquivos. Na verdade, o pagamento do resgate pode ser um alvo para mais ransomware. Se você já pagou, mas você conseguiu recuperar seus arquivos com êxito sem precisar usar a resolução do invasor, ligue para o seu banco para ver se eles podem bloquear a transação. Recomendamos também que você informe o ataque de ransomware à imposição de leis, sites de relatórios de scam e a Microsoft, conforme descrito mais adiante neste tópico.

- É muito importante que você responda rapidamente ao ataque e às suas conseqüências. Quanto mais tempo você espera, menos provável é que você possa recuperar os dados afetados.

## <a name="step-1-verify-your-backups"></a>Etapa 1: verificar seus backups

Se você tiver backups offline, provavelmente poderá restaurar os dados criptografados **depois** de ter removido a carga de ransomware (malware) de seu ambiente.

Se você não tiver backups ou se os backups também foram afetados pelo ransomware, ignore esta etapa.

## <a name="step-2-disable-activesync-and-onedrive-sync"></a>Etapa 2: desabilitar a sincronização do ActiveSync e do OneDrive

O ponto principal aqui é interromper a propagação da criptografia de dados pelo ransomware.

Se você suspeita que o email é um destino, você deve desabilitar temporariamente o acesso do usuário às caixas de correio. O Exchange ActiveSync é usado por dispositivos móveis para sincronizar dados entre o dispositivo e a caixa de correio do Exchange Online.

Para desabilitar o ActiveSync para uma caixa de correio, confira [como desabilitar o Exchange ActiveSync para usuários no Exchange Online](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365).

Para desabilitar outros tipos de acesso a uma caixa de correio, confira:

- [Habilitar ou desabilitar o MAPI para uma caixa de correio](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).

- [Habilitar ou desabilitar o acesso POP3 ou IMAP4 para um usuário](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Pausar o OneDrive Sync ajudará a proteger os dados da nuvem contra a atualização de dispositivos potencialmente infectados. Para obter mais informações, consulte [como pausar e retomar a sincronização no onedrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Etapa 3: remover o malware dos dispositivos afetados

Execute uma verificação antivírus completa com as atualizações mais recentes em todos os computadores e dispositivos suspeitos para detectar e remover a carga associada ao ransomware. Não esqueça dispositivos que estão sincronizando dados ou o destino de unidades de rede mapeadas (esses computadores e dispositivos precisam ser verificados também).

Você pode usar o [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) ou (para clientes mais antigos) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).

Uma alternativa que também ajudará você a remover o ransomware ou malware é a [ferramenta de remoção de software mal-intencionado (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).

Se essas opções não funcionarem, você poderá experimentar o [Windows Defender offline](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) ou [solucionar problemas com a detecção e remoção de malware](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware).

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Etapa 4: recuperar arquivos em um computador ou dispositivo limpo

Após concluir a etapa anterior para remover a carga de ransomware do seu ambiente (que impedirá que o ransomware Criptografe ou remova seus arquivos), você poderá usar o histórico de [arquivos](https://support.microsoft.com/help/17128/windows-8-file-history) no Windows 10 e no Windows 8,1 ou na proteção do sistema no Windows 7 para tentar recuperar seus arquivos e pastas locais.

**Observações**:

- Um ransomware também criptografará ou excluirá as versões de backup, portanto, não será possível usar o histórico de arquivos ou a proteção do sistema para restaurar arquivos. Se isso acontecer, você precisará usar backups em unidades ou dispositivos externos que não foram afetados pelo ransomware ou pelo OneDrive, conforme descrito na próxima seção.

- Se uma pasta for sincronizada com o OneDrive e você não estiver usando a versão mais recente do Windows, pode haver algumas limitações usando o histórico de arquivos.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Etapa 5: recuperar seus arquivos no OneDrive for Business

Arquivos Restore in OneDrive for Business permite restaurar todo o OneDrive para um ponto anterior no tempo nos últimos 30 dias. Para obter mais informações, consulte [Restore Your onedrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15).

## <a name="step-6-recover-deleted-email"></a>Etapa 6: recuperar emails excluídos

No caso raro em que o ransomware excluiu todos os seus emails, provavelmente você poderá recuperar os itens excluídos. Para saber mais, confira:

- [Recuperar mensagens excluídas na caixa de correio de um usuário](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Recuperar itens excluídos no Outlook para Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Etapa 7: reabilitar a sincronização do Exchange ActiveSync e do OneDrive

Depois de limpar seus computadores e dispositivos e recuperar seus dados, você pode reabilitar o ActiveSync e a sincronização do OneDrive que você desabilitou anteriormente na [etapa 2](#step-2-disable-activesync-and-onedrive-sync).

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Etapa 8 (opcional): bloquear a sincronização do OneDrive para extensões de arquivo específicas

Após a recuperação, você pode impedir que clientes do OneDrive for Business sincronizem os tipos de arquivo que foram afetados por esse ransomware. Para obter mais informações, consulte [set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Relatar o ataque

### <a name="contact-law-enforcement"></a>Cumprimento de leis de contato

Você deve entrar em contato com suas agências de cumprimento de leis local ou federal. Por exemplo, se estiver nos Estados Unidos, você pode entrar em contato com o [campo local do FBI](https://www.fbi.gov/contact-us/field), o [ic3](http://www.ic3.gov/complaint/default.aspx) ou o [serviço secreto](http://www.secretservice.gov/).

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Enviar um relatório para o site de relatório de scam do seu país

Os sites de relatórios de scam fornecem informações sobre como prevenir e evitar golpes. Eles também fornecem mecanismos para relatar se você é vítima de scam.

- Austrália: [SCAMwatch](http://www.scamwatch.gov.au/)

- Canadá: [Centro antifraude canadense](http://www.antifraudcentre-centreantifraude.ca/)

- França: [Agence Nationale de la Sécurité des Systèmes d'information](http://www.ssi.gouv.fr/)

- Alemanha: [Bundesamt für Sicherheit em der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Irlanda: [um Garda Síochána](http://www.garda.ie/)

- Nova Zelândia: [golpes do consumidor](http://www.consumeraffairs.govt.nz/scams)

- Reino Unido: [fraude de ação](http://www.actionfraud.police.uk/)

- Estados Unidos: [no protetor online](http://www.onguardonline.gov/)

Se o seu país não estiver listado, pergunte às agências de cumprimento de leis local ou federal.

### <a name="submit-email-messages-to-microsoft"></a>Enviar mensagens de email para a Microsoft

É possível relatar mensagens de phishing que contenham ransomware usando um dos vários métodos. Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>Confira também

- [Ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [Resposta de ransomware — para pagar ou não?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Hydro responde a ataques de ransomware com transparência](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Detecção de ransomware e recuperação de seus arquivos no OneDrive](https://support.microsoft.com/en-us/office/ransomware-detection-and-recovering-your-files-0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Relatório de inteligência de segurança da Microsoft](https://www.microsoft.com/securityinsights/)

- [Habilitar ou desabilitar macros em arquivos do Office](https://support.office.com/article/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Configurações recomendadas para o EOP e a segurança ATP do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [Uma atualização valioso: a segurança da próxima geração no Windows 10 comprova resistente contra epidemias de ransomware no 2017](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [Nenhum mas, Samas: o que há no modus operando do ransomware?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Malware com proteção, sorte de evitá-la](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT de julho de 2016: cerber ransomware](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [Os três cabeçalhos do ransomware Cerberus-like cerber](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Ransomware Troldesh influenciado por (o) da Vinci de código](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
