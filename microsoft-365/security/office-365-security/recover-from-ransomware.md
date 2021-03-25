---
title: Recuperar de um ataque de ransomware
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os administradores do Microsoft 365 podem aprender a se recuperar de um ataque de ransomware.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 242a4a2f43bd91d75caeaeaa0488f23a5ba4319d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203061"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Recuperar de um ataque de ransomware no Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Mesmo que você tome todas as precauções para proteger sua organização, ainda poderá ser vítima de um ataque [de ransomware.](/windows/security/threat-protection/intelligence/ransomware-malware) O ransomware é uma grande empresa e os ataques são muito sofisticados.

As etapas deste artigo darão a você a melhor chance de recuperar dados e interromper a propagação interna da infecção. Antes de começar, considere os seguintes itens:

- Não há garantias de que pagar o resgate retornará o acesso aos arquivos. Na verdade, pagar o resgate pode torná-lo um alvo para mais ransomware.

  Se você já pagou, mas se recuperou sem usar a solução do invasor, entre em contato com seu banco para ver se ele pode bloquear a transação.

  Também recomendamos que você reporte o ataque de ransomware à aplicação da lei, aos sites de relatórios de fraude e à Microsoft, conforme descrito posteriormente neste artigo.

- É importante que você responda rapidamente ao ataque e suas consequências. Quanto mais tempo você esperar, menor será a probabilidade de recuperar os dados afetados.

## <a name="step-1-verify-your-backups"></a>Etapa 1: Verificar seus backups

Se você tiver backups offline, provavelmente poderá  restaurar os dados criptografados depois de remover a carga de ransomware (malware) do seu ambiente.

Se você não tiver backups ou se seus backups também foram afetados pelo ransomware, você pode ignorar esta etapa.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>Etapa 2: Desabilitar Exchange ActiveSync sincronização do OneDrive

O ponto chave aqui é parar a propagação da criptografia de dados pelo ransomware.

Se você suspeitar de email como um destino da criptografia de ransomware, desabilite temporariamente o acesso do usuário às caixas de correio. Exchange ActiveSync sincroniza dados entre dispositivos e caixas de correio do Exchange Online.

Para desabilitar Exchange ActiveSync para uma caixa de correio, consulte [Como desabilitar](https://support.microsoft.com/help/2795303)o Exchange ActiveSync para usuários no Exchange Online .

Para desabilitar outros tipos de acesso a uma caixa de correio, consulte:

- [Habilitar ou desabilitar MAPI para uma caixa de correio](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).

- [Habilitar ou desabilitar o acesso POP3 ou IMAP4 para um usuário](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Pausar a sincronização do OneDrive ajudará a proteger seus dados de nuvem contra serem atualizados por dispositivos potencialmente infectados. Para obter mais informações, [consulte Como pausar e retomar a sincronização no OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Etapa 3: Remover o malware dos dispositivos afetados

Execute uma verificação completa e atual do antivírus em todos os computadores e dispositivos suspeitos para detectar e remover a carga associada ao ransomware.

Não se esqueça de examinar dispositivos que estão sincronizando dados ou os destinos de unidades de rede mapeadas.

Você pode usar [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) ou (para clientes mais antigos) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).

Uma alternativa que também ajudará você a remover ransomware ou malware é a Ferramenta de Remoção de Software Mal-Intencionado [(MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)

Se essas opções não funcionarem, você poderá tentar Windows Defender [offline](https://support.microsoft.com/help/17466) ou solucionar problemas com a detecção e [a remoção de malware.](https://support.microsoft.com/help/4466982)

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Etapa 4: Recuperar arquivos em um computador ou dispositivo limpo

Depois de concluir a etapa anterior para remover a carga de ransomware do seu ambiente (o que impedirá que o ransomware criptografe ou remova seus arquivos), você pode usar o Histórico de Arquivos no Windows 10 e no Windows 8.1 ou na Proteção do Sistema no Windows 7 para tentar recuperar seus arquivos e pastas locais. [](https://support.microsoft.com/help/17128)

**Observações**:

- Alguns ransomware também criptografarão ou excluirão as versões de backup, para que você não possa usar o Histórico de Arquivos ou a Proteção do Sistema para restaurar arquivos. Se isso acontecer, você precisará usar backups em unidades externas ou dispositivos que não foram afetados pelo ransomware ou pelo OneDrive, conforme descrito na próxima seção.

- Se uma pasta for sincronizada com o OneDrive e você não estiver usando a versão mais recente do Windows, pode haver algumas limitações usando o Histórico de Arquivos.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Etapa 5: Recuperar seus arquivos no OneDrive for Business

A restauração de arquivos no OneDrive for Business permite que você restaure todo o OneDrive para um ponto anterior no tempo nos últimos 30 dias. Para obter mais informações, consulte [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).

## <a name="step-6-recover-deleted-email"></a>Etapa 6: Recuperar emails excluídos

No caso raro de o ransomware ter excluído todos os emails, você provavelmente poderá recuperar os itens excluídos. Para mais informações, confira:

- [Recuperar mensagens excluídas na caixa de correio de um usuário](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Recuperar itens excluídos no Outlook para Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Etapa 7: Habilitar Exchange ActiveSync sincronização do OneDrive

Depois de limpar seus computadores e dispositivos e recuperar seus dados, você poderá habilitar Exchange ActiveSync sincronização do OneDrive e do OneDrive que você desabilitou anteriormente na [Etapa 2](#step-2-disable-exchange-activesync-and-onedrive-sync).

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Etapa 8 (Opcional): Bloquear a sincronização do OneDrive para extensões de arquivo específicas

Após a recuperação, você pode impedir que os clientes do OneDrive for Business sincronem os tipos de arquivo afetados por esse ransomware. Para obter mais informações, [consulte Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Relatar o ataque

### <a name="contact-law-enforcement"></a>Contatar a aplicação da lei

Entre em contato com suas agências de aplicação da lei local ou federal. Por exemplo, se você estiver nos Estados Unidos, poderá entrar em contato com o escritório de campo local do [FBI,](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) ou [Serviço Secreto.](http://www.secretservice.gov/)

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Enviar um relatório para o site de relatórios de fraude do seu país

Os sites de relatórios de fraude fornecem informações sobre como evitar e evitar fraudes. Eles também fornecem mecanismos para relatar se você foi vítima de fraude.

- Austrália: [SCAMwatch](http://www.scamwatch.gov.au/)

- Canadá: [Centro Antifrafra do Canadá](http://www.antifraudcentre-centreantifraude.ca/)

- França: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- Alemanha: [Bundesamt für Sicherheit no der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Irlanda: [An Garda Síochána](http://www.garda.ie/)

- Nova Zelândia: [Esquemas de Casos de Consumidor](http://www.consumeraffairs.govt.nz/scams)

- Reino Unido: [Fraude de Ação](http://www.actionfraud.police.uk/)

- Estados Unidos: [On Guard Online](http://www.onguardonline.gov/)

Se seu país não estiver listado, pergunte às agências de aplicação da lei local ou federal.

### <a name="submit-email-messages-to-microsoft"></a>Enviar mensagens de email para a Microsoft

Você pode relatar mensagens de phishing que contêm ransomware usando um dos vários métodos. Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>Confira também

- [Ransomware](/windows/security/threat-protection/intelligence/ransomware-malware)

- [Resposta ao ransomware para pagar ou não pagar?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [O Norsk Hydro responde ao ataque de ransomware com transparência](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Detecção de ransomware e recuperação de arquivos no OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Relatório de Inteligência de Segurança da Microsoft](https://www.microsoft.com/securityinsights/)

- [Habilitar ou desabilitar macros em arquivos do Office](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Configurações recomendadas para segurança do EOP e do Microsoft Defender para Office 365](recommended-settings-for-eop-and-office365.md)

- [Uma atualização valiosa: a segurança de próxima geração no Windows 10 se mostra resiliente contra surtos de ransomware em 2017](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [Sem massa, Samas: O que há no modus operandi desse ransomware?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Malware locky, sorte de evitá-lo](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT julho de 2016: ransomware cerber](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [As três cabeças do ransomware Cerberus-like](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Ransomware Troldesh influenciado pelo (o) código Da Vinci](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)