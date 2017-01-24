---
title: "ICommandTextImpl::GetCommandText | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetCommandText"
  - "ICommandTextImpl.GetCommandText"
  - "ICommandTextImpl::GetCommandText"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCommandText 메서드"
ms.assetid: 0f8da470-b1c3-4573-974f-1acc111e3984
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandTextImpl::GetCommandText
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

마지막 호출로부터 설정된 텍스트 명령을 [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)로 반환합니다.  
  
## 구문  
  
```  
  
      STDMETHOD(GetCommandText)(   
   GUID * pguidDialect,   
   LPOLESTR * ppwszCommand    
);  
```  
  
#### 매개 변수  
 *OLE DB Programmer's Reference*의 [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx)를 참조하세요.  *pguidDialect* 매개 변수는 기본적으로 무시됩니다.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [ICommandTextImpl 클래스](../../data/oledb/icommandtextimpl-class.md)