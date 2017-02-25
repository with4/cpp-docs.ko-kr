---
title: "CComPtr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComPtr class"
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

COM 인터페이스 포인터를 관리 하는 스마트 포인터 클래스입니다.  
  
## 구문  
  
```  
  
      template<  
   class T   
>  
class CComPtr  
```  
  
#### 매개 변수  
 `T`  
 저장 되는 포인터 유형을 지정 하는 COM 인터페이스입니다.  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CComPtr::CComPtr](../Topic/CComPtr::CComPtr.md)|생성자입니다.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[CComPtr::operator \=](../Topic/CComPtr::operator%20=.md)|포인터 멤버 포인터를 할당합니다.|  
  
## 설명  
 ATL을 사용 하 여 `CComPtr` 및  [CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM 인터페이스 포인터를 관리 합니다.  둘 다에서 파생 된  [CComPtrBase](../../atl/reference/ccomptrbase-class.md), 및 둘 다 자동으로 계산이 수행 됩니다.  
  
 **CComPtr** 및  [CComQIPtr](../../atl/reference/ccomqiptr-class.md) 통해 자동 참조 카운트를 수행 하 여 메모리 누수를 없애는 클래스 수.  다음 두 함수는 동일한 논리 연산을 수행 합니다. 그러나 어떻게 두 번째 버전을 사용 하 여 오류가 발생할 가능성이 수 있습니다는  **CComPtr** 클래스:  
  
 [!code-cpp[NVC_ATL_Utilities#130](../../atl/codesnippet/CPP/ccomptr-class_1.cpp)]  
  
 [!code-cpp[NVC_ATL_Utilities#131](../../atl/codesnippet/CPP/ccomptr-class_2.cpp)]  
  
 디버그 빌드에서 atlsd.lib를 추적 코드를 연결 합니다.  
  
## 상속 계층 구조  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 `CComPtr`  
  
## 요구 사항  
 **헤더:**  atlbase.h  
  
## 참고 항목  
 [CComPtr::CComPtr](../Topic/CComPtr::CComPtr.md)   
 [CComQIPtr::CComQIPtr](../Topic/CComQIPtr::CComQIPtr.md)   
 [Class Overview](../../atl/atl-class-overview.md)