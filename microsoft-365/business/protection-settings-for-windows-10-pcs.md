---
title: Defina configurações de proteção de dispositivos para PCs com Windows 10
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Saiba mais sobre o padrão e outras configurações disponíveis no Microsoft 365 Business para proteger dispositivos Windows 10.
ms.openlocfilehash: b286eb417a8e723b01838c16286ceb612d497c7d
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593507"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a>Defina configurações de proteção de dispositivos para PCs com Windows 10

## <a name="secure-windows-10-devices"></a>Proteger dispositivos Windows 10

Exibir um vídeo sobre como proteger dispositivos Windows 10 com o Microsoft 365 Business:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
    
2. No painel de navegação esquerdo, escolha **Adicionar** **políticas** \> de **dispositivos** \> .
  
3. No painel **Adicionar política**, insira um nome exclusivo para essa política. 
    
4. Em **Tipo de política**, escolha **Configuração de Dispositivo Windows 10**.
    
5. Expanda **Proteger dispositivos Windows 10** \> defina as configurações como desejar. Para obter mais informações, consulte [Available Settings](#available-settings). 
    
    Você sempre poderá usar o link **Redefinir as configurações padrão** para voltar para a configuração padrão. 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. Em seguida, decida **Quem receberá estas configurações?** Se não quiser usar o grupo de segurança padrão **Todos os usuários**, escolha **Alterar**, pesquise o grupo de segurança que deverá receber essas configurações \> **Selecionar**.
    
7. Por fim, escolha **Concluído** para salvar a política e atribui-la a dispositivos. 
    
## <a name="available-settings"></a>Configurações disponíveis

Todas as configurações são **Ativadas** por padrão. As configurações a seguir estão disponíveis.
  
Para saber mais, confira [Como os recursos de proteção no Microsoft 365 Business são mapeados para as configurações do Intune](map-protection-features-to-intune-settings.md). 
  
|||
|:-----|:-----|
|Setting  <br/> |Descrição  <br/> |
|Ajudar a proteger PCs contra vírus e outras ameaças usando o Windows Defender Antivirus  <br/> |Exige que o Windows Defender Antivírus esteja ativado para proteger computadores contra os riscos de estar conectado à Internet.  <br/> |
|Ajudar a proteger PCs contra ameaças baseadas na Web no Microsoft Edge  <br/> |Ativa as configurações do Microsoft Edge que ajudam a proteger os usuários contra sites e downloads mal-intencionados.  <br/> |
|Usar regras que reduzem a superfície de ataque de dispositivos  <br/> |Quando ativada, a redução da superfície de ataque ajuda a bloquear ações e aplicativos normalmente usados por malware para infectar dispositivos. Esta configuração só estará disponível se o Windows Defender Antivírus for definido como ativado. Confira [Reduzir superfícies de ataque](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) para saber mais.  <br/> |
|Proteger pastas de ameaças como ransomware  <br/> |Essa configuração usa o acesso a pastas controladas para proteger os dados da empresa contra modificações feitas por aplicativos suspeitos ou maliciosos, como ransomware. Esses tipos de aplicativos são impedidos de fazer alterações em pastas protegidas. Esta configuração só estará disponível se o Windows Defender Antivírus for definido como ativado. Consulte [proteger pastas com acesso controlado a pastas](https://docs.microsoft.com/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) para saber mais.  <br/> |
|Impedir o acesso da rede a conteúdo potencialmente malicioso na Internet  <br/> |Use essa configuração para bloquear as conexões de usuário de saída para locais de Internet de baixa reputação que podem hospedar golpes de phishing, exploits ou outros conteúdos mal-intencionados. Essa configuração só estará disponível se o Windows Defender antivírus estiver definido como **ativado**. Para obter mais informações, consulte [proteger sua rede](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus).  <br/> |
|Ajudar a proteger os arquivos e pastas em computadores contra acesso não autorizado com o BitLocker  <br/> |O BitLocker protege os dados por meio da criptografia das unidades de disco do computador e da proteção contra exposição de dados caso um computador seja perdido ou roubado. Para obter mais informações, consulte [perguntas frequentes sobre BitLocker](https://go.microsoft.com/fwlink/?linkid=871000).  <br/> |
|Permitir que os usuários baixem aplicativos da Microsoft Store  <br/> |Permite aos usuários baixar e instalar os aplicativos da Microsoft Store. Aplicativos incluem desde jogos a ferramentas de produtividade, portanto, deixamos essa configuração **Ativada**, mas você pode desativá-la para obter mais segurança.  <br/> |
|Permitir que os usuários acessem a Cortana  <br/> |A Cortana pode ser muito útil! A Cortana pode ativar ou desativar as configurações para você, dar orientações e certificar-se de que você está no horário dos compromissos, para que **essa configuração seja** mantida por padrão.  <br/> |
|Permitir que os usuários recebam anúncios e dicas sobre o Windows da Microsoft  <br/> |Dicas sobre o Windows podem ser úteis e ajudar a orientar os usuários quando novos recursos forem lançados.  <br/> |
|Manter dispositivos Windows 10 atualizados automaticamente  <br/> |Garante que os dispositivos Windows 10 recebam automaticamente as atualizações mais recentes.  <br/> |
|Desligar a tela do dispositivo quando ele ficar ocioso durante este período  <br/> |Garante que os dados da empresa estejam protegidos se um usuário ficar ocioso. Um usuário pode estar trabalhando em um local público, como um café, e se distanciar ou distrair por um momento, deixando seu dispositivo vulnerável a olhares aleatórios. Essa configuração permite que você controle quanto tempo o usuário pode ficar ocioso antes que a tela seja desligada.  <br/> |
