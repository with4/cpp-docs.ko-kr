---
title: "IThreadPoolConfig Interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IThreadPoolConfig"
  - "ATL::IThreadPoolConfig"
  - "ATL.IThreadPoolConfig"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IThreadPoolConfig interface"
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# IThreadPoolConfig Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 인터페이스는 스레드 풀을 구성 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      __interface  
__declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660"))  
IThreadPoolConfig :  
public IUnknown  
```  
  
## Members  
  
### 메서드  
  
|||  
|-|-|  
|[GetSize](../Topic/IThreadPoolConfig::GetSize.md)|스레드 풀에서 가져오도록이 메서드를 호출 합니다.|  
|[GetTimeout](../Topic/IThreadPoolConfig::GetTimeout.md)|스레드 풀 스레드 종료 대기 하는 밀리초 단위의 최대 시간이이 메서드를 호출 합니다.|  
|[SetSize](../Topic/IThreadPoolConfig::SetSize.md)|풀에서 스레드 수를 설정 하려면이 메서드를 호출 합니다.|  
|[SetTimeout](../Topic/IThreadPoolConfig::SetTimeout.md)|스레드 풀 스레드 종료 대기 하는 밀리초 단위의 최대 시간을 설정 하려면이 메서드를 호출 합니다.|  
  
## 설명  
 이 인터페이스에 의해 구현 된  [CThreadPool](../../atl/reference/cthreadpool-class.md).  
  
## 요구 사항  
 **헤더:** atlutil.h  
  
## 참고 항목  
 [클래스](../../atl/reference/atl-classes.md)   
 [CThreadPool Class](../../atl/reference/cthreadpool-class.md)