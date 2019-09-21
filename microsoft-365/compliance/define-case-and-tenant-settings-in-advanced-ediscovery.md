---
title: Definir configurações de caso e de locatário na descoberta eletrônica avançada do Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 383809de-7f5e-4a1d-9098-c525f67b7a9a
description: 'Saiba mais sobre as configurações de rótulos, módulos cruzados e locatários que você pode definir no nível do caso na descoberta eletrônica avançada do Office 365.  '
ms.openlocfilehash: 69e6e824a7c6a5698e9dc25095d4fab49e369490
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071970"
---
# <a name="define-case-and-tenant-settings-in-office-365-advanced-ediscovery"></a>Definir configurações de caso e de locatário na descoberta eletrônica avançada do Office 365

> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
As configurações de caixa de descoberta eletrônica avançada e locatário são descritas neste tópico.
  
## <a name="case-settings"></a>Configurações de caso

Estas seções descrevem as configurações que podem ser definidas no nível de caso.
  
> [!NOTE]
> Se nenhum caso estiver selecionado no momento na descoberta eletrônica avançada, a guia **configurações de caso** está inativa. 
  
### <a name="cross-module"></a>Módulo cruzado

As configurações de módulo cruzado a seguir são opções de caixa que se aplicam a módulos de descoberta eletrônica avançados.
  
- Página padrão após o logon: define a página padrão a ser exibida ao iniciar a descoberta eletrônica avançada.
    
- Nome de exibição do arquivo: identificador de arquivo que será exibido em toda a descoberta eletrônica avançada para identificar o arquivo, como uma alternativa para o nome de exibição de descoberta eletrônica avançada do título/caminho do arquivo ou assunto do email.
    
1. Abra **configurações e utilitários** clicando no ícone **engrenagem** . Abra **configurações e utilitários \> caixa de** guia \> configurações do **módulo cruzado**. 
    
2. Selecione na **página padrão após** as opções de logon: 
    
  - **Última página do logon anterior**
    
  - **Página de casos**
    
3. Clique em **Salvar**.
    
## <a name="tenant-settings"></a>Configurações de locatário

As configurações avançadas do locatário de descoberta eletrônica são descritas nesta seção.
  
### <a name="user-administration"></a>Administração do usuário

As opções de administração do usuário são descritas em [configuração de usuários e casos](set-up-users-and-cases-in-advanced-ediscovery.md).
  
### <a name="event-log"></a>Log de eventos

O log de eventos fornece metadados sobre o processamento de descoberta eletrônica avançado a qualquer momento durante a operação de descoberta eletrônica avançada. Por exemplo, ele inclui a hora de início dos principais processos de descoberta eletrônica avançada (importação, análise, relevância e exportação), bem como a hora e o status de término. Esse log pode ser usado para controlar e solucionar problemas de atividades de processamento de dados e para endereçar erros e avisos.
  
1. Abra **configurações e utilitários** clicando no ícone **engrenagem** . 
    
2. Na guia **configurações do locatário \> configurações e utilitários** , selecione **log de eventos**. Os dados do log de eventos são exibidos.
    
  - Para filtrar a saída de log por um caso, selecione o caso na lista **ocorrências** . 
    
  - Para classificar o log por colunas, clique no cabeçalho de uma coluna. 
    
  - Para modificar a ordem das colunas, clique e arraste o cabeçalho da coluna.
    
  - Para mover entre páginas de log, **\>** clique **\<** e ícones. 
    
### <a name="system-information"></a>Informações do sistema

As informações de sistema de versão de descoberta eletrônica avançada e tarefas ativas são exibidas na guia Configurações de locatário.
  
1. Abra **configurações e utilitários** clicando no ícone **engrenagem** . 
    
2. Na guia **configurações do locatário \> configurações e utilitários** , selecione **informações do sistema**. As informações de versão são exibidas.
    
A exibição pode ser atualizada clicando no ícone **Atualizar** abaixo das informações do locatário. 
  
## <a name="see-also"></a>Confira também

[Descoberta Eletrônica Avançada do Office 365](office-365-advanced-ediscovery.md)
  
[Usando utilitários](use-advanced-ediscovery-utilities.md)

