---
title: "CComEnum Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComEnum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComEnum class"
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CComEnum Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 COM 열거자 개체 배열을 기반으로 정의 합니다.  
  
## 구문  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy,  
   class ThreadModel = CcomObjectThreadModel  
>  
class ATL_NO_VTABLE CComEnum :  
   public CComEnumImpl<Base, piid, T, Copy>,  
   public CComObjectRootEx< ThreadModel >  
```  
  
#### 매개 변수  
 `Base`  
 COM 열거자 \([IEnumXXXX](https://msdn.microsoft.com/en-us/library/ms680089.aspx)\) 인터페이스.  
  
 `piid`  
 열거자 인터페이스의 인터페이스 ID에 대 한 포인터입니다.  
  
 `T`  
 열거자 인터페이스에 의해 노출 되는 항목의 형식입니다.  
  
 `Copy`  
 동종의  [복사 정책 클래스](../../atl/atl-copy-policy-classes.md).  
  
 `ThreadModel`  
 클래스의 스레딩 모델입니다.  프로젝트에 사용 되는 전역 개체 스레드 모델이 매개이 변수의 기본값입니다.  
  
## 설명  
 `CComEnum`배열을 기반으로 하는 COM 열거자 개체를 정의 합니다.  이 클래스와 유사 합니다  [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) 는 STL 컨테이너를 기반으로 하는 열거자를 구현 합니다.  이 클래스를 사용 하는 일반적인 단계는 다음과 같습니다.  자세한 내용은  [ATL 컬렉션 및 열거자](../../atl/atl-collections-and-enumerators.md).  
  
## 이 클래스를 사용.  
  
-   `typedef`이 클래스의 특수화입니다.  
  
-   사용 된 `typedef` 의 특수화에 템플릿 인수로 `CComObject`.  
  
-   인스턴스를 만들는 `CComObject` 특수화입니다.  
  
-   열거자 개체를 호출 하 여 초기화  [CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md).  
  
-   열거자 인터페이스를 클라이언트에 반환 합니다.  
  
## 상속 계층 구조  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)  
  
 `CComEnum`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 예제  
 아래 표시 된 코드를 만들고이 열거자 개체를 초기화 하 고 다시 사용할 수 있는 함수를 제공 합니다.  
  
 [!code-cpp[NVC_ATL_COM#32](../../atl/codesnippet/CPP/ccomenum-class_1.h)]  
  
 이 템플릿 함수를 사용 하 여 구현할 수 있습니다는 `_NewEnum` 아래와 같이 컬렉션 인터페이스의 속성:  
  
 [!code-cpp[NVC_ATL_COM#33](../../atl/codesnippet/CPP/ccomenum-class_2.h)]  
  
 이 코드를 만듭니다는 `typedef` 의 `CComEnum` 의 벡터를 노출  **변형**통해 s의  **IEnumVariant** 인터페이스.  **CVariantArrayCollection** 단순히 클래스를 전문으로  **CreateEnumerator** 의이 유형 및 가공에 필요한 인수를 열거자 개체를 사용 합니다.  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComObjectThreadModel](../Topic/CComObjectThreadModel.md)   
 [CComEnumImpl Class](../../atl/reference/ccomenumimpl-class.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)