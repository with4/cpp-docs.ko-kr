---
title: "IPropertyPage2Impl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IPropertyPage2Impl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPropertyPage2 ATL implementation"
  - "IPropertyPage2Impl class"
  - "속성 페이지"
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IPropertyPage2Impl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 구현  **IUnknown** 의 기본 구현에서 상속 하 고  [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md).  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template< class   
      T  
      >  
class IPropertyPage2Impl : public IPropertyPageImpl< T>  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IPropertyPage2Impl`.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IPropertyPage2Impl::EditProperty](../Topic/IPropertyPage2Impl::EditProperty.md)|속성 컨트롤 속성 페이지에서 활성화 될 때 포커스를 받을지 지정 합니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
  
## 설명  
 [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) 인터페이스 확장  [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) 추가 된 `EditProperty` 메서드.  이 메서드는 클라이언트를 속성 페이지 개체에 특정 속성을 선택할 수 있습니다.  
  
 클래스 `IPropertyPage2Impl` 단순히 반환  **E\_NOTIMPL** 의  **IPropertyPage2::EditProperty**.  그러나 기본 구현을 상속  [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) 및 구현  **IUnknown** 덤프에 정보를 전송 하 여 장치에서 디버그 빌드.  
  
 속성 페이지를 만들 때 클래스 일반적으로에서 파생 된 `IPropertyPageImpl`.  추가 지원을 제공 하기  **IPropertyPage2**, 클래스 정의 수정 하 고 재정의 `EditProperty` 메서드.  
  
 **관련된 기사** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md),  [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## 상속 계층 구조  
 `IPropertyPage`  
  
 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)  
  
 `IPropertyPage2Impl`  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [IPerPropertyBrowsingImpl Class](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl Class](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)