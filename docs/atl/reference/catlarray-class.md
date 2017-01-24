---
title: "CAtlArray Class | Microsoft Docs"
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
  - "ATL::CAtlArray"
  - "ATL.CAtlArray"
  - "CAtlArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlArray class"
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 array 개체를 구현합니다.  
  
## 구문  
  
```  
  
      template<   
   typename E,  
   class ETraits = CElementTraits< E >   
>  
class CAtlArray  
```  
  
#### 매개 변수  
 *E*  
 배열에 저장 될 데이터의 형식입니다.  
  
 *ETraits*  
 복사 또는 이동 요소를 사용 하는 코드입니다.  
  
## Members  
  
### 메서드  
  
|||  
|-|-|  
|[Add](../Topic/CAtlArray::Add.md)|Array 개체에 요소를 추가 하려면이 메서드를 호출 합니다.|  
|[Append](../Topic/CAtlArray::Append.md)|한 배열의 내용을 다른 끝에 추가 하려면이 메서드를 호출 합니다.|  
|[AssertValid](../Topic/CAtlArray::AssertValid.md)|Array 개체를 사용할 수 있는지 확인 하려면이 메서드를 호출 합니다.|  
|[CAtlArray](../Topic/CAtlArray::CAtlArray.md)|생성자입니다.|  
|[~ CAtlArray](../Topic/CAtlArray::~CAtlArray.md)|소멸자|  
|[복사](../Topic/CAtlArray::Copy.md)|한 배열의 요소를 복사 하려면이 메서드를 호출 합니다.|  
|[FreeExtra](../Topic/CAtlArray::FreeExtra.md)|배열에서 비어 있는 요소를 제거 하려면이 메서드를 호출 합니다.|  
|[GetAt](../Topic/CAtlArray::GetAt.md)|Array 개체에서 단일 요소를 검색 하려면이 메서드를 호출 합니다.|  
|[GetCount](../Topic/CAtlArray::GetCount.md)|배열에 저장 된 요소의 개수를 반환 하려면이 메서드를 호출 합니다.|  
|[GetData](../Topic/CAtlArray::GetData.md)|배열의 첫 번째 요소에 대 한 포인터를 반환 하려면이 메서드를 호출 합니다.|  
|[InsertArrayAt](../Topic/CAtlArray::InsertArrayAt.md)|한 배열에 다른 삽입 하려면이 메서드를 호출 합니다.|  
|[InsertAt](../Topic/CAtlArray::InsertAt.md)|Array 개체에 새 요소를 요소의 여러 복사본을 삽입 하려면이 메서드를 호출 합니다.|  
|[IsEmpty](../Topic/CAtlArray::IsEmpty.md)|배열이 비어 있는 경우 테스트 하기 위해이 메서드를 호출 합니다.|  
|[RemoveAll](../Topic/CAtlArray::RemoveAll.md)|Array 개체에서 모든 요소를 제거 하려면이 메서드를 호출 합니다.|  
|[RemoveAt](../Topic/CAtlArray::RemoveAt.md)|배열에서 하나 이상의 요소를 제거 하려면이 메서드를 호출 합니다.|  
|[SetAt](../Topic/CAtlArray::SetAt.md)|Array 개체에서 요소의 값을 설정 하려면이 메서드를 호출 합니다.|  
|[SetAtGrow](../Topic/CAtlArray::SetAtGrow.md)|배열 필요에 따라 확장 하는 array 개체에서 요소의 값을 설정 하려면이 메서드를 호출 합니다.|  
|[SetCount](../Topic/CAtlArray::SetCount.md)|배열 개체의 크기를 설정 하려면이 메서드를 호출 합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator&#93;](../Topic/CAtlArray::operator.md)|배열 요소에 대 한 참조를 반환 합니다.이 연산자를 호출 합니다.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[INARGTYPE](../Topic/CAtlArray::INARGTYPE.md)|배열에 요소를 추가 하는 데 사용 하는 데이터 형식입니다.|  
|[OUTARGTYPE](../Topic/CAtlArray::OUTARGTYPE.md)|배열에서 요소를 검색 하는 데 사용 하는 데이터 형식입니다.|  
  
## 설명  
 **CAtlArray** 만들기 및 관리 요소를 사용자 정의 형식의 배열을 위한 메서드를 제공 합니다.  유사 하지만 표준 C 배열에는  **CAtlArray** 개체는 동적으로 축소 및 필요에 따라 증가 합니다.  배열 인덱스는 항상 0 위치에서 시작 하 고 상한 수정, 또는 새 요소가 추가 되 면 확장 될 수 있습니다.  
  
 적은 수의 요소를 ATL 클래스와 배열에 대 한  [CSimpleArray](../../atl/reference/csimplearray-class.md) 사용할 수 있습니다.  
  
 **CAtlArray** MFC에 밀접 하 게 관련 된  **CArray** 클래스 및 까다롭기 serialization 지원 하지 않는 MFC 프로젝트에서 작동 합니다.  
  
 자세한 내용은  [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md).  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [MMXSwarm 샘플](../../top/visual-cpp-samples.md)   
 [DynamicConsumer 샘플](../../top/visual-cpp-samples.md)   
 [UpdatePV 샘플](../../top/visual-cpp-samples.md)   
 [Marquee 샘플](../../top/visual-cpp-samples.md)   
 [CArray Class](../../mfc/reference/carray-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)