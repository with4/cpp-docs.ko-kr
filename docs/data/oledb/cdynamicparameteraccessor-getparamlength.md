---
title: "CDynamicParameterAccessor::GetParamLength | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDynamicParameterAccessor::GetParamLength"
  - "ATL.CDynamicParameterAccessor.GetParamLength"
  - "CDynamicParameterAccessor.GetParamLength"
  - "CDynamicParameterAccessor::GetParamLength"
  - "GetParamLength"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParamLength 메서드"
ms.assetid: 04d76931-911a-4915-9c2c-ad585a9f3854
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicParameterAccessor::GetParamLength
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

버퍼에 저장 하는 지정된 된 매개 변수의 길이 검색 합니다.  
  
## 구문  
  
```  
  
      bool GetParamLength(  
   DBORDINAL nParam,  
   DBLENGTH* pLength  
);  
DBLENGTH* GetParamLength(   
   DBORDINAL nParam    
) const throw( );  
```  
  
#### 매개 변수  
 `nParam`  
 \[in\] 매개 변수 번호 \(1에서 오프셋\)입니다.  매개 변수 0은 반환 값으로 예약 됩니다.  매개 변수 번호는 SQL 또는 저장된 프로시저 호출의 순서에 따라 매개 변수의 인덱스입니다.  예제를 보려면 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 를 참조하십시오.  
  
 `pLength`  
 \[out\] 지정된 된 매개 변수의 길이 \(바이트\)를 포함 하는 변수에 대한 포인터입니다.  
  
## 설명  
 첫 번째 오버라이드는 실패 시 **false** 를, 성공 시 **true** 를 반환합니다.  두 번째 오버라이드는 매개 변수의 길이를 포함하는 메모리를 가르킵니다.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)