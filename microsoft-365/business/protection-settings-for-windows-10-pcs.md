---
title: Editar ou criar configurações de proteção de dispositivo para computadores Windows 10
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Saiba mais sobre as configurações disponíveis no Microsoft 365 para empresas para proteger dispositivos Windows 10.
ms.openlocfilehash: acfb27b2e4592d4ed1e446a63c9495ae07d916de
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578218"
---
# <a name="edit-or-create-device-protection-settings-for-windows-10-pcs"></a>Editar ou criar configurações de proteção de dispositivo para computadores Windows 10

Este artigo se aplica ao Microsoft 365 Business Premium.

Depois de configurar as configurações padrão de proteção do Windows na página Instalação, você pode adicionar novas que se aplicam a todos os usuários ou a um conjunto de usuários. Você também pode editar qualquer um dos que você criou.

## <a name="create-protection-settings-for-windows-10-devices"></a>Criar configurações de proteção para dispositivos Windows 10

Exibir um vídeo sobre como proteger dispositivos Windows 10 com o Microsoft 365 Business Premium:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
2. À esquerda, escolha  Políticas de \>  \> **Dispositivos Adicionar**.
3. No painel **Adicionar política**, insira um nome exclusivo para essa política. 
4. Em **Tipo de política**, escolha **Configuração de Dispositivo Windows 10**.
5. Expanda **Proteger dispositivos Windows 10** \> defina as configurações como desejar. Para obter mais informações, consulte [Configurações disponíveis](#available-settings). 
    
    Você sempre poderá usar o link **Redefinir as configurações padrão** para voltar para a configuração padrão. 
    
    ![Add policy pane with Windows 10 Device configuration selected](../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. Em seguida, decida **Quem receberá estas configurações?** Se não quiser usar o grupo de segurança padrão **Todos os usuários**, escolha **Alterar**, pesquise o grupo de segurança que deverá receber essas configurações \> **Selecionar**.
7. Por fim, escolha **Concluído** para salvar a política e atribui-la a dispositivos. 

## <a name="edit-windows-10-protection-settings"></a>Editar configurações de proteção do Windows 10
 
1. Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.     
2. À esquerda, escolha **Políticas** de \> **Dispositivos** .
1. Escolha uma política de dispositivo Windows existente e **edite**.
1. Escolha **Editar** ao lado de uma configuração que você deseja alterar e, em seguida, **Salvar**.

## <a name="available-settings"></a>Configurações disponíveis

Todas as configurações são **Ativadas** por padrão. As configurações a seguir estão disponíveis.
  
Para obter mais informações, consulte [Como os recursos de proteção no Microsoft 365 Premium mapeiam para configurações do Intune.](map-protection-features-to-intune-settings.md) 
  
|||
|:-----|:-----|
|Setting  <br/> |Descrição  <br/> |
|Ajudar a proteger PCs contra vírus e outras ameaças usando o Windows Defender Antivirus  <br/> |Exige que o Windows Defender Antivírus esteja ativado para proteger computadores contra os riscos de estar conectado à Internet.  <br/> |
|Ajudar a proteger PCs contra ameaças baseadas na Web no Microsoft Edge  <br/> |Ativa as configurações do Microsoft Edge que ajudam a proteger os usuários contra sites e downloads mal-intencionados.  <br/> |
|Usar regras que reduzem a superfície de ataque de dispositivos  <br/> |Quando ativada, a redução da superfície de ataque ajuda a bloquear ações e aplicativos normalmente usados por malware para infectar dispositivos. Esta configuração só estará disponível se o Windows Defender Antivírus for definido como ativado. Confira [Reduzir superfícies de ataque](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) para saber mais.  <br/> |
|Proteger pastas de ameaças como ransomware  <br/> |Essa configuração usa o acesso a pastas controladas para proteger os dados da empresa contra modificações feitas por aplicativos suspeitos ou maliciosos, como ransomware. Esses tipos de aplicativos são impedidos de fazer alterações em pastas protegidas. Esta configuração só estará disponível se o Windows Defender Antivírus for definido como ativado. Consulte [Proteger pastas com acesso controlado a pastas](/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) para saber mais.  <br/> |
|Impedir o acesso da rede a conteúdo potencialmente malicioso na Internet  <br/> |Use essa configuração para bloquear conexões de usuário de saída para locais da Internet de baixa reputação que podem hospedar esquemas de phishing, explorações ou outro conteúdo mal-intencionado. Essa configuração só estará disponível se Windows Defender Antivírus estiver definido como **On**. Para obter mais informações, consulte [Protect your network](/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus).  <br/> |
|Ajudar a proteger os arquivos e pastas em computadores contra acesso não autorizado com o BitLocker  <br/> |O BitLocker protege os dados por meio da criptografia das unidades de disco do computador e da proteção contra exposição de dados caso um computador seja perdido ou roubado. Para obter mais informações, consulte [Perguntas frequentes do Bitlocker](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).  <br/> |
|Permitir que os usuários baixem aplicativos da Microsoft Store  <br/> |Permite aos usuários baixar e instalar os aplicativos da Microsoft Store. Aplicativos incluem desde jogos a ferramentas de produtividade, portanto, deixamos essa configuração **Ativada**, mas você pode desativá-la para obter mais segurança.  <br/> |
|Permitir que os usuários acessem a Cortana  <br/> |A Cortana pode ser muito útil! A Cortana pode ativar ou desativar as configurações para você, dar instruções e garantir que você esteja na hora dos compromissos, portanto, mantenha essa configuração on **por** padrão.  <br/> |
|Permitir que os usuários recebam anúncios e dicas sobre o Windows da Microsoft  <br/> |Dicas sobre o Windows podem ser úteis e ajudar a orientar os usuários quando novos recursos forem lançados.  <br/> |
|Manter dispositivos Windows 10 atualizados automaticamente  <br/> |Garante que os dispositivos Windows 10 recebam automaticamente as atualizações mais recentes.  <br/> |
|Desligar a tela do dispositivo quando ele ficar ocioso durante este período  <br/> |Garante que os dados da empresa estejam protegidos se um usuário ficar ocioso. Um usuário pode estar trabalhando em um local público, como um café, e se distanciar ou distrair por um momento, deixando seu dispositivo vulnerável a olhares aleatórios. Essa configuração permite que você controle quanto tempo o usuário pode ficar ocioso antes que a tela seja desligada.  <br/> |