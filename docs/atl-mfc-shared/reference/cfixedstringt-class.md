---
title: "CFixedStringT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFixedStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFixedStringT class"
  - "shared classes, CFixedStringT"
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CFixedStringT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 고정 된 문자 버퍼를 문자열 개체를 나타냅니다.  
  
## 구문  
  
```  
  
      template< class   
      StringType  
      , int   
      t_nChars  
       >    
class CFixedStringT : private CFixedStringMgr, public StringType  
```  
  
#### 매개 변수  
 `StringType`  
 고정된 문자열 개체에 대 한 기본 클래스로 사용 하는 `CStringT`\-형식을 기반으로 합니다.  Some examples include `CString`, `CStringA`, and `CStringW`.  
  
 *t\_nChars*  
 버퍼에 저장 되는 문자 수입니다.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CFixedStringT::CFixedStringT](../Topic/CFixedStringT::CFixedStringT.md)|문자열 개체의 생성자입니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CFixedStringT::operator \=](../Topic/CFixedStringT::operator%20=.md)|새 값에 지정 된 `CFixedStringT` 개체.|  
  
## 설명  
 이 클래스를 기반으로 사용자 지정 문자열 클래스 예제입니다 `CStringT`.  매우 유사 하지만, 두 클래스 구현에서 다릅니다.  주요 차이점 사이 `CFixedStringT` 및 `CStringT` 입니다.  
  
-   초기 문자 버퍼 개체의 일부로 할당 되 고 크기가  *t\_nChars*.  이로써는  **CFixedString** 개체에서 성능 향상을 위한 연속 메모리 청크를 차지 합니다.  그러나 경우 내용에 `CFixedStringT` 개체 증가 외  *t\_nChars*, 버퍼를 동적으로 할당 됩니다.  
  
-   문자 버퍼에 있는 `CFixedStringT` 개체는 항상 동일한 길이 \(*t\_nChars*\).  버퍼 크기에 제한이 없습니다 `CStringT` 개체입니다.  
  
-   메모리 관리자에 대 한 `CFixedStringT` 공유 하도록 사용자 지정 되는  [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) 사이의 두 개 이상의 개체 `CFixedStringT` objectsis 허용 되지 않습니다.  `CStringT`개체가 제한이 없습니다.  
  
 사용자 지정에 대 한 자세한 내용은 `CFixedStringT` 및 일반적으로 string 개체에 대 한 메모리 관리를 참조 하십시오  [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## 상속 계층 구조  
 `IAtlStringMgr`  
  
 `StringType`  
  
 `CFixedStringMgr`  
  
 `CFixedStringT`  
  
## 요구 사항  
 **헤더:** cstringt.h  
  
## 참고 항목  
 [CStringT Class](../../atl-mfc-shared/reference/cstringt-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)