---
title: "ICommandImpl::Execute | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ICommandImpl::Execute"
  - "ICommandImpl.Execute"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Execute 메서드"
ms.assetid: 033e0d4e-256b-4eed-9215-70e0bebb768c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ICommandImpl::Execute
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

명령을 실행합니다.  
  
## 구문  
  
```  
  
      HRESULT Execute(  
   IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset   
);  
```  
  
#### 매개 변수  
 *OLE DB Programmer's Reference*에 있는[ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx)를 참조하십시오.  
  
## 설명  
 요청 보내기 인터페이스에 만들어지는이 함수는 행 집합 개체에서 얻은 인터페이스 될 것입니다.  
  
 **실행** 전화 [CreateRowset](../../data/oledb/icommandimpl-createrowset.md)를 부릅니다.  둘 이상의 행 집합을 만들 수 또는 다른 행 집합을 만들기 위한 조건을 직접 제공 하도록 기본 구현을 재정의 합니다.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [ICommandImpl 클래스](../../data/oledb/icommandimpl-class.md)   
 [ICommandImpl::CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)