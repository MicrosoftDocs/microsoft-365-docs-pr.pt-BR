---
title: Recuperar de um ataque de ransomware
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.article: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os administradores do Microsoft 365 podem aprender a se recuperar de um ataque de ransomware.
ms.openlocfilehash: 753171578dc7b76aefadf4b8587e84320d98b912
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794443"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Recuperar-se de um ataque de ransomware no Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Mesmo que você tome todas as precauções para proteger sua organização, ainda poderá ser vítima de um ataque [de ransomware.](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) Ransomware é uma grande empresa e os ataques são muito sofisticados.

As etapas neste artigo lhe darão a melhor chance de recuperar dados e parar a propagação interna da infecção. Antes de começar, considere os seguintes itens:

- Não há garantia de que pagar o resgate retornará o acesso aos seus arquivos. Na verdade, pagar o resgate pode fazer de você um alvo para mais ransomware.

  Se você já tiver pago, mas se recuperou sem usar a solução do invasor, entre em contato com seu banco para ver se ele pode bloquear a transação.

  Também recomendamos que você reporte o ataque de ransomware às autoridades, a sites de relatórios de esquema e a Microsoft, conforme descrito mais adiante neste artigo.

- É importante que você responda rapidamente ao ataque e suas consequências. Quanto mais tempo você aguardar, menos provável será que você possa recuperar os dados afetados.

## <a name="step-1-verify-your-backups"></a>Etapa 1: verificar seus backups

Se você tiver backups offline, provavelmente poderá  restaurar os dados criptografados depois de remover a carga de ransomware (malware) do seu ambiente.

Se você não tiver backups ou se os backups também foram afetados pelo ransomware, ignore esta etapa.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>Etapa 2: Desabilitar a sincronização do Exchange ActiveSync e do OneDrive

O ponto-chave aqui é interromper a propagação da criptografia de dados pelo ransomware.

Se você suspeitar de email como um destino da criptografia ransomware, desabilite temporariamente o acesso do usuário às caixas de correio. O Exchange ActiveSync sincroniza dados entre dispositivos e caixas de correio do Exchange Online.

Para desabilitar o Exchange ActiveSync para uma caixa de correio, confira Como desabilitar o [Exchange ActiveSync para usuários no Exchange Online.](https://support.microsoft.com/help/2795303)

Para desabilitar outros tipos de acesso a uma caixa de correio, confira:

- [Habilitar ou desabilitar MAPI para uma caixa de correio.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)

- [Habilitar ou desabilitar o acesso POP3 ou IMAP4 para um usuário](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Pausar a sincronização do OneDrive ajudará a proteger seus dados de nuvem contra a atualização por dispositivos potencialmente infectados. Para saber mais, confira [Como pausar e retomar a sincronização no OneDrive.](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Etapa 3: Remover o malware dos dispositivos afetados

Execute uma verificação antivírus completa e atual em todos os computadores e dispositivos suspeitos para detectar e remover a carga associada ao ransomware.

Não se esqueça de verificar dispositivos que estão sincronizando dados ou os destinos de unidades de rede mapeadas.

Você pode usar [o Windows Defender](https://www.microsoft.com/windows/comprehensive-security) ou (para clientes mais antigos) Microsoft Security [Essentials](https://www.microsoft.com/download/details.aspx?id=5201).

Uma alternativa que também ajudará você a remover ransomware ou malware é a [MSRT (Ferramenta](https://www.microsoft.com/download/details.aspx?id=9905)de Remoção de Software Mal-intencionado).

Se essas opções não funcionarem, você poderá experimentar o [Windows Defender Offline](https://support.microsoft.com/help/17466) ou solucionar problemas de detecção e [remoção de malware.](https://support.microsoft.com/help/4466982)

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Etapa 4: Recuperar arquivos em um computador ou dispositivo limpo

Depois de concluir a etapa anterior para remover a carga de ransomware do seu ambiente (o que impedirá que o ransomware criptografe ou remova seus arquivos), você poderá usar o Histórico de Arquivos no Windows 10 e no Windows 8.1 ou na Proteção do Sistema no Windows 7 para tentar recuperar seus arquivos e pastas locais. [](https://support.microsoft.com/help/17128)

**Observações**:

- Alguns ransomware também criptografarão ou excluirão as versões de backup, para que você não possa usar o Histórico de Arquivos ou a Proteção do Sistema para restaurar arquivos. Se isso acontecer, você precisará usar backups em unidades externas ou dispositivos que não foram afetados pelo ransomware ou pelo OneDrive, conforme descrito na próxima seção.

- Se uma pasta estiver sincronizada com o OneDrive e você não estiver usando a versão mais recente do Windows, poderá haver algumas limitações usando o Histórico de Arquivos.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Etapa 5: Recuperar seus arquivos no OneDrive for Business

A restauração de arquivos no OneDrive for Business permite que você restaure todo o OneDrive para um momento anterior nos últimos 30 dias. Para saber mais, confira [Restaurar o OneDrive.](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="step-6-recover-deleted-email"></a>Etapa 6: Recuperar emails excluídos

No caso raro de o ransomware ter excluído todos os seus emails, você provavelmente poderá recuperar os itens excluídos. Para saber mais, confira:

- [Recuperar mensagens excluídas na caixa de correio de um usuário](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Recuperar itens excluídos no Outlook para Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Etapa 7: Reabilitar a sincronização do Exchange ActiveSync e do OneDrive

Depois de limpar seus computadores e dispositivos e recuperar seus dados, você poderá reabilitar a sincronização do Exchange ActiveSync e do OneDrive que você desabilitou anteriormente na [Etapa 2.](#step-2-disable-exchange-activesync-and-onedrive-sync)

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Etapa 8 (Opcional): Bloquear a sincronização do OneDrive para extensões de arquivo específicas

Depois de recuperar, você pode impedir que os clientes do OneDrive for Business sincroniem os tipos de arquivo que foram afetados por esse ransomware. Para obter mais informações, [consulte Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Relatar o ataque

### <a name="contact-law-enforcement"></a>Contatar a aplicação da lei

Entre em contato com as agências locais ou federais. Por exemplo, se você estiver nos Estados Unidos, entre em contato com o escritório de campo [local do FEDERAL,](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) ou [Serviço Secreto.](http://www.secretservice.gov/)

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Enviar um relatório para o site de relatórios de esquema do seu país

Os sites de relatórios de esquema fornecem informações sobre como evitar e evitar fraudes. Eles também fornecem mecanismos para relatar se você foi vítima de um esquema.

- Austrália: [SCAMwatch](http://www.scamwatch.gov.au/)

- Canadá: [Centro de Antifalsidade do Canadá](http://www.antifraudcentre-centreantifraude.ca/)

- França: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- Alemanha: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Irlanda: [an Garda Vouochána](http://www.garda.ie/)

- Nova Zelândia: [esquemas de assuntos do consumidor](http://www.consumeraffairs.govt.nz/scams)

- Reino Unido: [Fraude de Ação](http://www.actionfraud.police.uk/)

- Estados Unidos: [On Guard Online](http://www.onguardonline.gov/)

Se o seu país não estiver listado, peça às agências de aplicação da lei local ou federal.

### <a name="submit-email-messages-to-microsoft"></a>Enviar mensagens de email para a Microsoft

Você pode relatar mensagens de phishing que contêm ransomware usando um dos vários métodos. Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>Confira também

- [Ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [Resposta a ransomware : para pagar ou não pagar?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Ransomware responde a um ataque de ransomware com transparência](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Detecção de ransomware e recuperação de arquivos no OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Relatório de Inteligência de Segurança da Microsoft](https://www.microsoft.com/securityinsights/)

- [Habilitar ou desabilitar macros em arquivos do Office](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Configurações recomendadas para o EOP e o Microsoft Defender para segurança do Office 365](recommended-settings-for-eop-and-office365-atp.md)

- [Uma atualização valiosa: a segurança da próxima geração no Windows 10 prova a resiliência contra ataques de ransomware em 2017](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [No mas, Samas: What's in this ransomware's mmodo operandi?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Malware locky, para evitar](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT julho de 2016: Ransomware cerber](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [Os três heads of the Cerberus-like Cerber ransomware](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Ransomware Trol ransomware influenciado por (o) código Da Vinci](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
