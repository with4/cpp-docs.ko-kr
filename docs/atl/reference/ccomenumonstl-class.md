---
title: "CComEnumOnSTL Class | Microsoft Docs"
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
  - "CComEnumOnSTL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComEnumOnSTL class"
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComEnumOnSTL Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 STL 컬렉션에 따라 COM 열거자 개체를 정의 합니다.  
  
## 구문  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy,  
   class CollType,  
   class ThreadModel = CComObjectThreadModel  
>  
class ATL_NO_VTABLE CComEnumOnSTL :  
   public IEnumOnSTLImpl<Base, piid, T, Copy, CollType>,  
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
 A  [정책을 복사 하는](../../atl/atl-copy-policy-classes.md) 클래스입니다.  
  
 `CollType`  
 STL 컨테이너 클래스입니다.  
  
## 설명  
 `CComEnumOnSTL`STL 컬렉션에 따라 COM 열거자 개체를 정의 합니다.  이 클래스는 자체적으로 또는 함께에서 사용할 수 있습니다  [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md).  이 클래스를 사용 하는 일반적인 단계는 다음과 같습니다.  자세한 내용은  [ATL 컬렉션 및 열거자](../../atl/atl-collections-and-enumerators.md).  
  
## ICollectionOnSTLImpl 함께이 클래스를 사용.  
  
-   `typedef`이 클래스의 특수화입니다.  
  
-   사용 된 `typedef` 의 특수화에 최종 템플릿 인수로 `ICollectionOnSTLImpl`.  
  
 참조  [ATL 컬렉션 및 열거자](../../atl/atl-collections-and-enumerators.md) 예입니다.  
  
## ICollectionOnSTLImpl 독립적으로이 클래스를 사용 하는 방법  
  
-   `typedef`이 클래스의 특수화입니다.  
  
-   사용 된 `typedef` 의 특수화에 템플릿 인수로 `CComObject`.  
  
-   인스턴스를 만들는 `CComObject` 특수화입니다.  
  
-   열거자 개체를 호출 하 여 초기화  [IEnumOnSTLImpl::Init](../Topic/IEnumOnSTLImpl::Init.md).  
  
-   열거자 인터페이스를 클라이언트에 반환 합니다.  
  
## 상속 계층 구조  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)  
  
 `CComEnumOnSTL`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 예제  
 아래 표시 된 코드를 생성 및 초기화 하는 열거자 개체를 처리 하는 제네릭 함수를 제공 합니다.  
  
 [!code-cpp[NVC_ATL_COM#34](../../atl/codesnippet/CPP/ccomenumonstl-class_1.h)]  
  
 이 템플릿 함수를 사용 하 여 구현할 수 있습니다는 `_NewEnum` 아래와 같이 컬렉션 인터페이스의 속성:  
  
 [!code-cpp[NVC_ATL_COM#35](../../atl/codesnippet/CPP/ccomenumonstl-class_2.h)]  
  
 만들고이 코드는 `typedef` 에 대 한 `CComEnumOnSTL` 의 벡터를 노출 `CComVariant`통해 s는  **IEnumVariant** 인터페이스.  **CVariantCollection** 클래스는 단순히 전문  **CreateSTLEnumerator** 이 형식의 열거자 개체를 사용 합니다.  
  
## 참고 항목  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)   
 [ATLCollections 샘플: ICollectionOnSTLImpl, CComEnumOnSTL, 및 사용자 지정 복사 정책 클래스를 보여 줍니다.](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComObjectThreadModel](../Topic/CComObjectThreadModel.md)   
 [IEnumOnSTLImpl Class](../../atl/reference/ienumonstlimpl-class.md)