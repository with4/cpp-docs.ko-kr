---
title: "CTypedPtrMap Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTypedPtrMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTypedPtrMap class"
  - "맵"
  - "pointer maps"
  - "template classes, CTypedPtrMap class"
  - "type-safe collections"
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CTypedPtrMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 안전 "래퍼" 개체에 대 한 포인터 맵 클래스를 제공 합니다. `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, 및 `CMapStringToPtr`.  
  
## 구문  
  
```  
template< class BASE_CLASS, class KEY, class VALUE >  
class CTypedPtrMap : public BASE_CLASS  
```  
  
#### 매개 변수  
 `BASE_CLASS`  
 형식화 된 포인터 맵 클래스의 기본 클래스입니다. must be a pointer map class \(`CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, or `CMapStringToPtr`\).  
  
 `KEY`  
 지도 키로 사용 되는 개체의 클래스입니다.  
  
 `VALUE`  
 클래스 맵에 저장 된 개체입니다.  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CTypedPtrMap::GetNextAssoc](../Topic/CTypedPtrMap::GetNextAssoc.md)|반복에 대 한 다음 요소를 가져옵니다.|  
|[CTypedPtrMap::Lookup](../Topic/CTypedPtrMap::Lookup.md)|반환 된 `KEY` 기준으로 `VALUE`.|  
|[CTypedPtrMap::RemoveKey](../Topic/CTypedPtrMap::RemoveKey.md)|키에 지정 된 요소를 제거 합니다.|  
|[CTypedPtrMap::SetAt](../Topic/CTypedPtrMap::SetAt.md)|지도에 요소를 삽입합니다. 일치 하는 키가 없는 경우 기존 요소를 대체 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CTypedPtrMap::operator](../Topic/CTypedPtrMap::operator.md)|지도에 요소를 삽입합니다.|  
  
## 설명  
 사용 하는 경우 `CTypedPtrMap`, 형식 검사를 C\+\+ 기능이 일치 하지 않는 포인터 형식에 의해 발생 하는 오류를 제거 하는 데 도움이 됩니다.  
  
 때문에 모든 `CTypedPtrMap` 함수는 인라인, 사용이 크게 미치지 않습니다 크기나 코드 속도.  
  
 사용에 대 한 자세한 내용은 `CTypedPtrMap`, 문서를 참조 하십시오.  [컬렉션](../../mfc/collections.md) 및  [템플릿 기반 클래스](../../mfc/template-based-classes.md).  
  
## 상속 계층 구조  
 `BASE_CLASS`  
  
 `CTypedPtrMap`  
  
## 요구 사항  
 **헤더:**  afxtempl.h  
  
## 참고 항목  
 [MFC 샘플 수집](../../top/visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr Class](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord Class](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapWordToPtr Class](../../mfc/reference/cmapwordtoptr-class.md)   
 [CMapStringToPtr Class](../../mfc/reference/cmapstringtoptr-class.md)