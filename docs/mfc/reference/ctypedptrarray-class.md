---
title: "CTypedPtrArray Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTypedPtrArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTypedPtrArray class"
  - "pointer arrays"
ms.assetid: e3ecdf1a-a889-4156-92dd-ddbd36ccd919
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTypedPtrArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 안전 "래퍼" 클래스의 개체에 대 한 제공 `CPtrArray` 또는 `CObArray`.  
  
## 구문  
  
```  
template< class BASE_CLASS, class TYPE >  
class CTypedPtrArray : public BASE_CLASS  
```  
  
#### 매개 변수  
 `BASE_CLASS`  
 형식화 된 포인터 배열 클래스의 기본 클래스입니다. 배열 클래스 여야 합니다 \(`CObArray` 또는 `CPtrArray`\).  
  
 `TYPE`  
 기본 클래스 배열에 저장 된 요소의 형식입니다.  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CTypedPtrArray::Add](../Topic/CTypedPtrArray::Add.md)|배열의 끝에 새 요소를 추가합니다.  필요한 경우 배열의 증가|  
|[CTypedPtrArray::Append](../Topic/CTypedPtrArray::Append.md)|한 배열의 내용을 다른 끝에 추가합니다.  필요한 경우 배열의 증가|  
|[CTypedPtrArray::Copy](../Topic/CTypedPtrArray::Copy.md)|다른 배열 배열에 복사 합니다. 배열에 필요한 경우 확장 됩니다.|  
|[CTypedPtrArray::ElementAt](../Topic/CTypedPtrArray::ElementAt.md)|임시 참조 배열 내의 요소 포인터를 반환합니다.|  
|[CTypedPtrArray::GetAt](../Topic/CTypedPtrArray::GetAt.md)|지정 된 인덱스의 값을 반환합니다.|  
|[CTypedPtrArray::InsertAt](../Topic/CTypedPtrArray::InsertAt.md)|요소를 다른 배열의 모든 요소는 지정 된 인덱스에 삽입합니다.|  
|[CTypedPtrArray::SetAt](../Topic/CTypedPtrArray::SetAt.md)|지정 된 인덱스 값으로 설정합니다. 배열 증가할 수 없습니다.|  
|[CTypedPtrArray::SetAtGrow](../Topic/CTypedPtrArray::SetAtGrow.md)|지정 된 인덱스 값으로 설정합니다. 배열에 필요한 경우 확장 됩니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CTypedPtrArray::operator](../Topic/CTypedPtrArray::operator.md)|설정 하거나 지정 된 인덱스에 있는 요소를 가져옵니다.|  
  
## 설명  
 사용 하는 경우 `CTypedPtrArray` 대신 `CPtrArray` 또는 `CObArray`, 형식 검사를 C\+\+ 기능이 일치 하지 않는 포인터 형식에 의해 발생 하는 오류를 제거 하는 데 도움이 됩니다.  
  
 또한는 `CTypedPtrArray` 래퍼를 사용한 경우 해야 하는 캐스팅에 많은 수행 `CObArray` 또는 `CPtrArray`.  
  
 때문에 모든 `CTypedPtrArray` 함수는 인라인, 사용이 크게 미치지 않습니다 크기나 코드 속도.  
  
 사용에 대 한 자세한 내용은 `CTypedPtrArray`, 문서를 참조 하십시오.  [컬렉션](../../mfc/collections.md) 및  [템플릿 기반 클래스](../../mfc/template-based-classes.md).  
  
## 상속 계층 구조  
 `BASE_CLASS`  
  
 `CTypedPtrArray`  
  
## 요구 사항  
 **헤더:**  afxtempl.h  
  
## 참고 항목  
 [MFC 샘플 수집](../../top/visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CPtrArray Class](../../mfc/reference/cptrarray-class.md)   
 [CObArray Class](../../mfc/reference/cobarray-class.md)