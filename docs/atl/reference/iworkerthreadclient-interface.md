---
title: "IWorkerThreadClient Interface | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.IWorkerThreadClient"
  - "ATL::IWorkerThreadClient"
  - "IWorkerThreadClient"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IWorkerThreadClient interface"
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
caps.latest.revision: 24
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IWorkerThreadClient Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`IWorkerThreadClient`클라이언트에 의해 구현 된 인터페이스의  [CWorkerThread](../../atl/reference/cworkerthread-class.md) 클래스입니다.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
__interface IWorkerThreadClient  
  
```  
  
## Members  
  
### 메서드  
  
|||  
|-|-|  
|[CloseHandle](../Topic/IWorkerThreadClient::CloseHandle.md)|이 개체와 연관 된 처리 하려면이 메서드를 구현 합니다.|  
|[Execute](../Topic/IWorkerThreadClient::Execute.md)|이 개체와 연결 된 핸들 신호 때 코드를 실행 하려면이 메서드를 구현 합니다.|  
  
## 설명  
 작업자 스레드에서 핸들에 신호가 전달 되는 것에 대 한 응답으로 실행 해야 하는 코드가 있는 경우이 인터페이스를 구현 합니다.  
  
## 요구 사항  
 **헤더:** atlutil.h  
  
## 참고 항목  
 [클래스](../../atl/reference/atl-classes.md)   
 [CWorkerThread Class](../../atl/reference/cworkerthread-class.md)