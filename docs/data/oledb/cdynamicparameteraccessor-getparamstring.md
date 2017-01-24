---
title: "CDynamicParameterAccessor::GetParamString | Microsoft Docs"
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
  - "CDynamicParameterAccessor.GetParamString"
  - "GetParamString"
  - "CDynamicParameterAccessor::GetParamString"
  - "ATL.CDynamicParameterAccessor.GetParamString"
  - "ATL::CDynamicParameterAccessor::GetParamString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParamString 메서드"
ms.assetid: 078c2b1c-7072-47c1-a203-f47e75363f91
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicParameterAccessor::GetParamString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 매개 변수는 버퍼에 저장된 문자열 데이터를 검색 합니다.  
  
## 구문  
  
```  
  
      bool GetParamString(  
   DBORDINAL nParam,  
   CSimpleStringA& strOutput  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   CSimpleStringW& strOutput  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   CHAR* pBuffer,  
   size_t* pMaxLen  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   WCHAR* pBuffer,  
   size_t* pMaxLen  
) throw( );  
```  
  
#### 매개 변수  
 `nParam`  
 \[in\] 매개 변수 번호 \(1에서 오프셋\)입니다.  매개 변수 0은 반환 값으로 예약 됩니다.  매개 변수 번호는 SQL 또는 저장된 프로시저 호출의 순서에 따라 매개 변수의 인덱스입니다.  예제를 보려면 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 를 참조하십시오.  
  
 `strOutput`  
 \[out\] 지정된 매개 변수의 ANSI \(**CSimpleStringA**\) 또는 유니코드 \(**CSimpleStringW**\) 문자열 데이터 입니다.  `CString` 형식의 매개 변수를 전달해야 합니다. 예를 들어:  
  
 [!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/CPP/cdynamicparameteraccessor-getparamstring_1.cpp)]  
  
 `pBuffer`  
 \[out\] 지정된 매개 변수의 ANSI\(**CHAR**\) 또는 유니코드 \(**WCHAR**\) 문자열 데이터에 대한 포인터 입니다.  
  
 `pMaxLen`  
 \[out\] `pBuffer` \(문자에서 종료 NULL 포함\)가 가르키는 버퍼의 사이즈에 대한 포인터입니다.  
  
## 설명  
 성공하면 **true**를 반환하고 또는 실패하면 **false**를 반환합니다.  
  
 이 메서드는 `pMaxLen` 가 가르키는 메모리에서 요구되는 버퍼 사이즈를 설정하고 데이터 복사 없이 **true** 를 반환합니다. `pBuffer` 는 NULL 입니다.  
  
 `pBuffer` 가 전체 문자열을 포함할 수 없을 정도로 작다면 이 메서드는 실패합니다.  
  
 버퍼에서 문자열 매개 변수 데이터를 추적하기 위해 `GetParamString`를 사용하십시오.  [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) 를 사용하여 버퍼에서 문자열이 아닌 매개 변수 데이터를 검사합니다.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)