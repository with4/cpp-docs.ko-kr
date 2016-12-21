---
title: "CArray Class | Microsoft Docs"
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
  - "CArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "배열[C++], 클래스"
  - "CArray class"
  - "컬렉션 클래스, template-based"
  - "템플릿, 컬렉션 클래스"
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
caps.latest.revision: 33
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C 배열과 마찬가지로 수 있지만 동적으로 줄이고 수 만큼 증가 하는 배열을 지원 합니다.  
  
## 구문  
  
```  
template < class TYPE, class ARG_TYPE = const TYPE& >   
class CArray :   
   public CObject  
```  
  
#### 매개 변수  
 `TYPE`  
 템플릿 매개 변수 배열에 저장 된 개체의 형식을 지정 합니다.  `TYPE`반환 되는 매개 변수입니다 `CArray`.  
  
 `ARG` *\_* `TYPE`  
 템플릿 매개 변수 배열에 저장 된 개체에 액세스 하는 데 사용 되는 인수 형식을 지정 합니다.  참조 하는 `TYPE`.  `ARG_TYPE`전달 되는 매개 변수입니다 `CArray`.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CArray::CArray](../Topic/CArray::CArray.md)|빈 배열을 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CArray::Add](../Topic/CArray::Add.md)|배열의 끝에 요소를 추가합니다. 배열에 필요한 경우 확장 됩니다.|  
|[CArray::Append](../Topic/CArray::Append.md)|다른 배열 배열에 추가 합니다. 필요한 경우 배열의 증가|  
|[CArray::Copy](../Topic/CArray::Copy.md)|다른 배열 배열에 복사 합니다. 배열에 필요한 경우 확장 됩니다.|  
|[CArray::ElementAt](../Topic/CArray::ElementAt.md)|임시 참조 배열 내의 요소 포인터를 반환합니다.|  
|[CArray::FreeExtra](../Topic/CArray::FreeExtra.md)|현재 상한 위의 모든 사용 되지 않는 메모리를 해제합니다.|  
|[CArray::GetAt](../Topic/CArray::GetAt.md)|지정 된 인덱스의 값을 반환합니다.|  
|[CArray::GetCount](../Topic/CArray::GetCount.md)|이 배열의 요소 수를 가져옵니다.|  
|[CArray::GetData](../Topic/CArray::GetData.md)|배열 요소에 액세스할 수 있습니다.  수  **NULL**.|  
|[CArray::GetSize](../Topic/CArray::GetSize.md)|이 배열의 요소 수를 가져옵니다.|  
|[CArray::GetUpperBound](../Topic/CArray::GetUpperBound.md)|가장 큰 올바른 인덱스를 반환합니다.|  
|[CArray::InsertAt](../Topic/CArray::InsertAt.md)|요소를 다른 배열의 모든 요소는 지정 된 인덱스에 삽입합니다.|  
|[CArray::IsEmpty](../Topic/CArray::IsEmpty.md)|배열이 비어 있는지 여부를 결정 합니다.|  
|[CArray::RemoveAll](../Topic/CArray::RemoveAll.md)|이 배열에서 모든 요소를 제거합니다.|  
|[CArray::RemoveAt](../Topic/CArray::RemoveAt.md)|특정 인덱스에 있는 요소를 제거합니다.|  
|[CArray::SetAt](../Topic/CArray::SetAt.md)|지정 된 인덱스 값으로 설정합니다. 배열 증가할 수 없습니다.|  
|[CArray::SetAtGrow](../Topic/CArray::SetAtGrow.md)|지정 된 인덱스 값으로 설정합니다. 배열에 필요한 경우 확장 됩니다.|  
|[CArray::SetSize](../Topic/CArray::SetSize.md)|이 배열에 포함 될 수 있는 요소를 설정 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CArray::operator](../Topic/CArray::operator.md)|설정 하거나 지정 된 인덱스에 있는 요소를 가져옵니다.|  
  
## 설명  
 배열 인덱스는 항상 0 위치에서 시작합니다.  상한 수정 또는 확장 과거 현재 바인딩 요소를 추가 하면 배열에 사용 여부를 결정할 수 있습니다.  일부 요소가 null 인 경우에 상한에 연속적으로 메모리를 할당 합니다.  
  
> [!NOTE]
>  크기를 조정 하는 대부분의 메서드는 `CArray` 개체 또는 추가 요소를 사용 하 여  [memcpy\_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) 요소를 이동 합니다.  이 문제는 때문입니다 `memcpy_s` 호출 하는 생성자가 필요한 모든 개체와 호환 되지 않습니다.  경우 항목에는 `CArray` 와 호환 되지 않는 `memcpy_s`를 새로 만들어야 `CArray` 적절 한 크기의.  다음 사용 해야 [CArray::Copy](../Topic/CArray::Copy.md) 및 [CArray::SetAt](../Topic/CArray::SetAt.md) 할당 연산자 대신 이러한 메서드를 사용 하기 때문에 새 배열을 채우려면 `memcpy_s`.  
  
 C 배열의 액세스 때와 마찬가지로 `CArray` 인덱스 요소 상수 이며 배열 크기에 독립적입니다.  
  
> [!TIP]
>  배열을 사용 하기 전에 사용  [SetSize](../Topic/CArray::SetSize.md) 크기를 설정 하 고 메모리를 할당 합니다.  사용 하지 않는 경우 `SetSize`, 배열에 요소를 추가 하면 자주 재할당 되 고 복사 될 수 있습니다.  자주 재할당 및 복사 비효율적입니다 및 메모리를 조각 낼 수 있습니다.  
  
 배열의 개별 요소를 덤프 해야 하는 경우의 깊이 설정에서  [CDumpContext](../../mfc/reference/cdumpcontext-class.md) 1 또는 큰.  
  
 특정 멤버 함수 전역 도우미 함수는이 클래스 호출의 대부분의 사용에 대해 사용자 지정 해야 합니다의 `CArray` 클래스입니다.  항목을 참조 하십시오.  [컬렉션 클래스 도우미](../../mfc/reference/collection-class-helpers.md) MFC 매크로 전역 변수 섹션에서 합니다.  
  
 배열 클래스 파생 목록 파생 처럼입니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CArray`, 문서를 참조 하십시오.  [컬렉션](../../mfc/collections.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CArray`  
  
## 요구 사항  
 `Header:`afxtempl.h  
  
## 참고 항목  
 [MFC 샘플 수집](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CObArray Class](../../mfc/reference/cobarray-class.md)   
 [컬렉션 클래스 도우미](../../mfc/reference/collection-class-helpers.md)