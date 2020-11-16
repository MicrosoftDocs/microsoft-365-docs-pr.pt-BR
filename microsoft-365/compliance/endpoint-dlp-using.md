---
title: Usando a prevenção contra perda de dados do Ponto de extremidade
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Saiba como configurar as políticas de prevenção contra perda de dados (DLP) para usar os locais de prevenção contra perda de dados do Ponto de extremidade (EPDLP) do Microsoft 365.
ms.openlocfilehash: 64cdfeab4b527dd3b84e7586d1419e5bf8b383df
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073100"
---
# <a name="using-endpoint-data-loss-prevention"></a>Usando a prevenção contra perda de dados do Endpoint

Este artigo o conduz por três cenários em que você cria e modifica uma política DLP que usa dispositivos como um local.

## <a name="dlp-settings"></a>Configurações de DLP

Antes de começar, defina suas configurações de DLP, aplicadas a todas as políticas DLP para dispositivos. Configure-as se pretende criar políticas que impõem:

- restrições de saída de nuvem
- restrições de aplicativos não permitidos

Ou

- Se você deseja excluir os caminhos de arquivo barulhentos do monitoramento

  > [!div class="mx-imgBorder"]
  > ![Configurações de DLP](../media/endpoint-dlp-1-using-dlp-settings.png)

### <a name="file-path-exclusions"></a>Exclusões de caminho de arquivo

Talvez você queira excluir certos caminhos do monitoramento DLP, alertas DLP e aplicações de política DLP de seus dispositivos porque eles são muito ruidosos ou não contêm arquivos de seu interesse. Os arquivos nesses locais não serão auditados e todos os arquivos criados ou modificados nesses locais não estarão sujeitos à aplicação da política DLP. É possível configurar exclusões de caminho nas configurações de DLP.

Use essa lógica para construir seus caminhos de exclusão:

- Caminho de arquivo válido que termina com "\", o que significa somente os arquivos da pasta. <br/>Por exemplo: C:\Temp\

- Caminho de arquivo válido que termina com “\*”, o que significa somente os arquivos em subpastas, além dos arquivos diretamente na pasta. <br/>Por exemplo: C:\Temp\*

- Caminho de arquivo válido que termina com "\" ou “\*”, o que significa somente os arquivos da pasta e todas as subpastas. <br/>Por exemplo: C:\Temp

- Um caminho com o curinga entre "\" de cada lado. <br/>Por exemplo: C:\Users\*\Desktop\

- Um caminho com curinga entre "\" de cada lado e com '(número)' para atribuir um número exato de subpastas. <br/>Por exemplo: C:\Users\*(1) \Downloads\

- Um caminho com variáveis de ambiente do sistema. <br/>Por exemplo: %SystemDrive%\Test\*

- Uma mistura de todas as acima. <br/>Por exemplo: %SystemDrive%\Users\*\Documents\*(2)\Sub\

### <a name="service-domains"></a>Domínios de serviço

Adicione domínios a esta lista aos quais o Edge Chromium se referirá ao aplicar a restrição de acesso de carregamento na nuvem da política DLP de Ponto de Extremidade. 

Se o modo de lista for definido como **Bloquear** , o usuário não poderá carregar itens confidenciais para esses domínios. Quando uma ação de carregamento for bloqueada devido a um item corresponde a uma política DLP, a DLP irá gerar um aviso ou bloqueará o carregamento do item confidencial.

Se o modo de lista estiver definido como **Permitir** , os usuários poderão carregar itens confidenciais * *_apenas_* _ a esses domínios, e carregar o acesso a todos os outros domínios não será permitido.

### <a name="unallowed-apps"></a>Aplicativos não permitidos

Quando a configuração de _ *Acesso por navegadores e aplicativos não permitidos* * de uma política estiver ativada e os usuários tentarem usar esses aplicativos para acessar um arquivo protegido, a atividade será permitida ou bloqueada, ou bloqueada com os usuários podendo ignorar a restrição. Todas as atividades são auditadas e disponibilizadas para revisão no explorador de atividades.

### <a name="unallowed-browsers"></a>Navegadores não permitidos

Adicione navegadores, identificados por seus nomes executáveis, que serão impedidos de acessar arquivos que correspondam às condições de uma política DLP aplicada quando a restrição de carregamento para serviços em nuvem estiver definida para bloquear ou ignorar o bloqueio. Quando esses navegadores são impedidos de acessar um arquivo, os usuários finais verão uma notificação do sistema solicitando que abram o arquivo através do Edge Chromium.

[!IMPORTANT]
Não inclua o caminho para o executável, apenas o nome do executável (por exemplo, browser.exe).

## <a name="tying-dlp-settings-together"></a>Como ligar as configurações de DLP

Com a DLP de Ponto de Extremidade e o navegador da Web Edge Chromium, restrinja o compartilhamento não intencional de itens confidenciais a aplicativos e serviços em nuvem não permitidos. O Edge Chromium entende quando um item é restringido por uma política DLP de Ponto de Extremidade e impõe restrições de acesso.

Ao usar a DLP de Ponto de Extremidade, como um local em uma política DLP configurada corretamente, e o navegador Edge Chromium, os navegadores não permitidos definidos nessas configurações serão impedidos de acessar os itens confidenciais que correspondem aos seus controles de política DLP. Em vez disso, os usuários serão redirecionados para usar o Edge Chromium, que com o entendimento das restrições impostas pela DLP, poderá bloquear ou restringir atividades quando as condições da política de DLP forem atendidas.

Para usar essa restrição, será necessário configurar três partes importantes:

1. Especifique os locais (serviços, domínios e endereços IP) que deseja impedir que os itens confidenciais sejam compartilhados.

2. Adicione os navegadores que não têm permissão para acessar determinados itens confidenciais quando ocorre uma correspondência de política DLP.

3. Configure as políticas DLP para definir os tipos de itens confidenciais para os quais o carregamento deve ser restrito a esses lugares, ativando **Carregar nos serviços de nuvem** e **Acesso a partir do navegador não permitido**.

Você pode continuar a adicionar novos serviços, aplicativos e políticas para estender e aprimorar suas restrições para atender às suas necessidades de negócios e proteger dados confidenciais. 

Essa configuração ajudará a garantir a segurança dos seus dados, além de evitar restrições desnecessárias, que impedem ou impedem que os usuários acessem e compartilhem itens não confidenciais.

## <a name="endpoint-dlp-policy-scenarios"></a>Cenários de política da DLP de Ponto de Extremidade

Para ajudar a se familiarizar com os recursos da DLP de Ponto de Extremidade e como eles aparecem nas políticas DLP, reunimos alguns cenários para você seguir. Todo o conteúdo da DLP de Ponto de Extremidade será incluído no conteúdo principal da DLP definido quando a DLP de Ponto de Extremidade estiver disponível em geral.

> [!IMPORTANT]
> Esses cenários DLP de Ponto de Extremidade não são os procedimentos oficiais para criar e ajustar políticas DLP. Confira os tópicos a seguir quando precisar trabalhar com as políticas DLP em situações gerais:
>- [Visão geral da prevenção contra perda de dados](data-loss-prevention-policies.md)
>- [Introdução à política DLP padrão](get-started-with-the-default-dlp-policy.md)
>- [Criar uma política DLP a partir de um modelo](create-a-dlp-policy-from-a-template.md)
>- [Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a>Cenário 1: Criar uma política a partir de um modelo, somente auditoria

Esses cenários exigem que você já tenha dispositivos integrados e relatórios no Explorador de atividades. Se você ainda não integrou dispositivos, confira [Introdução à prevenção contra perda de dados do Ponto de Extremidade](endpoint-dlp-getting-started.md).

1. Abra a página [Prevenção contra perda de dados](https://compliance.microsoft.com/datalossprevention?viewid=policies).

2. Escolha **Criar política**.

3. Para esse cenário, escolha **Privacidade** , em seguida, **Dados de Informações de Identificação Pessoal (PII) dos EUA** e escolha **Próximo**.

4. Alterne o campo **Status** para desativado em todos os locais, exceto em **Dispositivos**. Escolha **Próximo**.

5. Aceite a seleção padrão **Revisar e personalizar as configurações do modelo** e escolha **Próximo**.

6. Aceite os valores padrão de **Ações de proteção** e escolha **Próximo**.

7. Selecione **Auditoria ou restringir atividades em dispositivos de Windows** e deixe as ações definidas como **Somente auditar**. Escolha **Próximo**.

8. Aceite o valor padrão **Eu quero testá-lo primeiro** e escolha **Mostrar dicas de política enquanto estiver no modo de teste**. Escolha **Próximo**.

9. Examine as configurações e escolha **Enviar**.

10. A nova política DLP será exibida na lista de políticas.

11. Verifique o Explorador de atividades para dados dos pontos de extremidade monitorados. Defina o filtro de localização para dispositivos e adicione a política, em seguida, filtre por nome de política para ver o impacto desta política. Se necessário, confira, [Introdução ao explorador de atividades](data-classification-activity-explorer.md).

12. Tente compartilhar um teste que contenha o conteúdo que acionará a condição de Dados de Informações de Identificação Pessoal (PII) dos EUA com alguém de fora da sua organização. Isso deve acionar a política.

13. Verifique o Explorador de atividades para obter o evento.

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a>Cenário 2: Modificar a política existente, definir um alerta

1. Abra a página [Prevenção de perda de dados](https://compliance.microsoft.com/datalossprevention?viewid=policies).

2. Escolha as políticas de **Dados de Informações de Identificação Pessoal (PII) dos EUA** criadas cenário 1.

3. Escolha **Editar política**.

4. Vá para a página **Regras avançadas de DLP** e edite o **Baixo volume de conteúdo detectado nas Informações de Identificação Pessoal dos EUA**.

5. Role para baixo até a seção **Relatórios de incidentes** e defina **Enviar um alerta aos administradores quando ocorrer uma correspondência de regra** como **Ativado**. Os Alertas de email serão enviados automaticamente ao administrador e a qualquer pessoa que você adicionar à lista de destinatários. 

   > [!div class="mx-imgBorder"]
   > ![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)
   
6. Para fins deste cenário, escolha **Enviar alerta sempre que uma atividade corresponder à regra**.

7. Escolha **Salvar**.

8. Mantenha todas as suas configurações anteriores escolhendo **Próximo** e **Enviar** as alterações de política.

9. Tente compartilhar um teste que contenha o conteúdo que acionará a condição de Dados de Informações de Identificação Pessoal (PII) dos EUA com alguém de fora da sua organização. Isso deve acionar a política.

10. Verifique o Explorador de atividades para obter o evento.

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a>Cenário 3: Modificar a política existente, bloquear a ação com permitir substituição

1. Abra a página [Prevenção de perda de dados](https://compliance.microsoft.com/datalossprevention?viewid=policies).

2. Escolha as políticas de **Dados de Informações de Identificação Pessoal (PII) dos EUA** criadas cenário 1.

3. Escolha **Editar política**.

4. Vá para a página **Regras avançadas de DLP** e edite o **Baixo volume de conteúdo detectado nas Informações de Identificação Pessoal dos EUA**.

5. Role a tela para baixo até a seção **Auditoria ou restringir atividades nos dispositivos do Windows** e para cada atividade defina a ação correspondente para **Bloquear com substituir**.

   > [!div class="mx-imgBorder"]
   > ![definir o bloco com substituir ação](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)
   
6. Escolha **Salvar**.

7. Repita as etapas 4-7 para o **Alto volume de conteúdo detectado nas Informações de Identificação Pessoal dos EUA**.

8. Mantenha todas as suas configurações anteriores escolhendo **Próximo** e **Enviar** as alterações de política.

9. Tente compartilhar um teste que contenha o conteúdo que acionará a condição de Dados de Informações de Identificação Pessoal (PII) dos EUA com alguém de fora da sua organização. Isso deve acionar a política.

   Você verá um pop-up desse tipo no dispositivo do cliente:

   > [!div class="mx-imgBorder"]
   > ![cliente dlp do ponto de extremidade bloqueado na notificação de substituição](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)

10. Verifique o Explorador de atividades para obter o evento.

## <a name="see-also"></a>Confira também

- [Saiba mais sobre a Prevenção contra perda de dados do ponto de extremidade](endpoint-dlp-learn-about.md)
- [Introdução à Prevenção contra perda de dados do ponto de extremidade](endpoint-dlp-getting-started.md)
- [Visão geral da prevenção contra perda de dados](data-loss-prevention-policies.md)
- [Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)
- [Começar a usar o Explorador de atividades](data-classification-activity-explorer.md)
- [Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/)
- [Ferramentas e métodos de integração para computadores Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Associados a Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [Baixar o novo Microsoft Edge baseado em Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [Introdução à política DLP padrão](get-started-with-the-default-dlp-policy.md)
- [Criar uma política DLP a partir de um modelo](create-a-dlp-policy-from-a-template.md)
