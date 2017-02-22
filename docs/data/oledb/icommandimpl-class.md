---
title: "ICommandImpl 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ICommandImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandImpl 클래스"
ms.assetid: ef285fef-0d66-45e6-a762-b03357098e3b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ICommandImpl 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Provides implementation for the [ICommand](https://msdn.microsoft.com/en-us/library/ms709737.aspx) interface.  
  
## 구문  
  
```  
template <class T, class CommandBase = ICommand>   
class ATL_NO_VTABLE ICommandImpl : public CommandBase  
```  
  
#### 매개 변수  
 `T`  
 Your class, derived from `ICommandImpl`.  
  
 `CommandBase`  
 A command interface.  기본값은 `ICommand`입니다.  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)|Cancels the current command execution.|  
|[취소](../../data/oledb/icommandimpl-cancel.md)|Cancels the current command execution.|  
|[CreateRowset](../../data/oledb/icommandimpl-createrowset.md)|Creates a rowset object.|  
|[Execute](../../data/oledb/icommandimpl-execute.md)|명령을 실행합니다.|  
|[GetDBSession](../../data/oledb/icommandimpl-getdbsession.md)|Returns an interface pointer to the session that created the command.|  
|[ICommandImpl](../../data/oledb/icommandimpl-icommandimpl.md)|생성자입니다.|  
  
### 데이터 멤버  
  
|||  
|-|-|  
|[m\_bCancel](../../data/oledb/icommandimpl-m-bcancel.md)|Indicates whether the command is to be canceled.|  
|[m\_bCancelWhenExecuting](../../data/oledb/icommandimpl-m-bcancelwhenexecuting.md)|Indicates whether the command is to be canceled when executing.|  
|[m\_bIsExecuting](../../data/oledb/icommandimpl-m-bisexecuting.md)|Indicates whether the command is currently executing.|  
  
## 설명  
 A mandatory interface on the command object.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)