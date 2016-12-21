---
title: "CComCoClass Class | Microsoft Docs"
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
  - "CComCoClass"
  - "ATL.CComCoClass"
  - "ATL::CComCoClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregation [C++], aggregation models"
  - "CComCoClass class"
ms.assetid: 67cfefa4-8df9-47fa-ad58-2d1a1ae25762
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComCoClass Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 클래스의 인스턴스를 만들고 해당 속성을 가져오는 방법을 제공 합니다.  
  
## 구문  
  
```  
  
      template<  
   class T,  
   const CLSID* pclsid = &CLSID_NULL  
>  
class CComCoClass  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `CComCoClass`.  
  
 *pclsid*  
 개체의 CLSID에 대 한 포인터입니다.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComCoClass::CreateInstance](../Topic/CComCoClass::CreateInstance.md)|\(정적\) 인스턴스 클래스 및 인터페이스에 대 한 쿼리를 만듭니다.|  
|[CComCoClass::Error](../Topic/CComCoClass::Error.md)|\(정적\) 풍부한 오류 정보를 반환 합니다.|  
|[CComCoClass::GetObjectCLSID](../Topic/CComCoClass::GetObjectCLSID.md)|\(정적\) 개체의 클래스 식별자를 반환합니다.|  
|[CComCoClass::GetObjectDescription](../Topic/CComCoClass::GetObjectDescription.md)|\(정적\) 재정의 하 여 개체의 설명을 반환 합니다.|  
  
## 설명  
 `CComCoClass`개체의 CLSID를 검색 오류 정보를 설정 하 고 클래스의 인스턴스를 만드는 데에 대 한 메서드를 제공 합니다.  등록 된 모든 클래스는  [개체 맵](http://msdn.microsoft.com/ko-kr/b57619cc-534f-4b8f-bfd4-0c12f937202f) 을 에서 파생 될 `CComCoClass`.  
  
 `CComCoClass`또한 개체에 대 한 기본 클래스 팩터리 및 집계 모델을 정의합니다.  `CComCoClass`다음 두 개의 매크로 사용합니다.  
  
-   [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md) 를 선언 하는 클래스 팩터리  [CComClassFactory](../../atl/reference/ccomclassfactory-class.md).  
  
-   [DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md) 개체가 집계 될 수 있도록 선언 합니다.  
  
 이러한 기본값 중 하나를 클래스 정의에 다른 매크로 지정 하 여 재정의할 수 있습니다.  사용 방법에 대 한  [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) 대신 `CComClassFactory`에서 지정 된  [DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md) 매크로:  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/CPP/ccomcoclass-class_1.h)]  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)