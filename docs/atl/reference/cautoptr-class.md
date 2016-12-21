---
title: "CAutoPtr Class | Microsoft Docs"
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
  - "CAutoPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoPtr class"
ms.assetid: 08988d53-4fb0-4711-bdfc-8ac29c63f410
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAutoPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 스마트 포인터가 개체를 나타냅니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template<   
typename T  
>  
class CAutoPtr  
```  
  
#### 매개 변수  
 `T`  
 포인터 형식입니다.  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CAutoPtr::CAutoPtr](../Topic/CAutoPtr::CAutoPtr.md)|생성자입니다.|  
|[CAutoPtr::~CAutoPtr](../Topic/CAutoPtr::~CAutoPtr.md)|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CAutoPtr::Attach](../Topic/CAutoPtr::Attach.md)|기존 포인터의 소유권을 가져오려면이 메서드를 호출 합니다.|  
|[CAutoPtr::Detach](../Topic/CAutoPtr::Detach.md)|소유권에 대 한 포인터를 해제 하려면이 메서드를 호출 합니다.|  
|[CAutoPtr::Free](../Topic/CAutoPtr::Free.md)|가리키는 개체를 삭제 하려면이 메서드를 호출 하는 `CAutoPtr`.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[CAutoPtr::operator T\*](../Topic/CAutoPtr::operator%20T*.md)|캐스트 연산자입니다.|  
|[CAutoPtr::operator \=](../Topic/CAutoPtr::operator%20=.md)|할당 연산자입니다.|  
|[CAutoPtr::operator \-\>](../Topic/CAutoPtr::operator%20-%3E.md)|포인터 멤버 연산자입니다.|  
  
### 공용 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CAutoPtr::m\_p](../Topic/CAutoPtr::m_p.md)|포인터 데이터 멤버 변수입니다.|  
  
## 설명  
 이 클래스 만들기 및 관리 범위를 벗어난 작아지면 리소스를 자동으로 해제 하 여 메모리 누수를 방지 하는 데 도움이 되는 스마트 포인터에 대 한 메서드를 제공 합니다.  
  
 추가로, `CAutoPtr`의 복사 생성자와 할당 연산자 소유권의 포인터가 원본 포인터 포인터를 대상 복사 및 원본 포인터를 NULL로 설정 합니다.  따라서 둘 수 없는 `CAutoPtr` 각각 동일한 포인터를 저장 하는 개체 및이 동일한 포인터를 두 번 삭제의 가능성을 줄여줍니다.  
  
 `CAutoPtr`또한 포인터 컬렉션 만들기를 단순화합니다.  컬렉션 클래스를 파생 및 소멸자를 재정의 하는 대신 컬렉션을 확인 하는 것입니다 `CAutoPtr` 개체입니다.  컬렉션이 삭제 될 때의 `CAutoPtr` 개체가 범위를 벗어나면 서 자신을 자동으로 삭제 합니다.  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md) 및 변형 작업을 동일한 방식으로 `CAutoPtr`, 할당 하 고 다른 힙 함수 대신 C\+\+를 사용 하 여 메모리를 확보 된다는 점을 제외 하 고  **새** 및  **삭제** 연산자.  [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md) 유사 합니다 `CAutoPtr`, 사용 하도록 하는 유일한 차이점은  **벡터 new** 및  **벡터 delete** 할당 하 고 메모리를 해제 합니다.  
  
 참고  [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) 및  [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) 배열 또는 목록 스마트 포인터의 경우 필요 합니다.  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 예제  
 [!code-cpp[NVC_ATL_Utilities#74](../../atl/codesnippet/CPP/cautoptr-class_1.cpp)]  
  
## 참고 항목  
 [CHeapPtr Class](../../atl/reference/cheapptr-class.md)   
 [CAutoVectorPtr Class](../../atl/reference/cautovectorptr-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)