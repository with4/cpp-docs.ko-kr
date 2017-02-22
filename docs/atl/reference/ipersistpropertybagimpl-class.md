---
title: "IPersistPropertyBagImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IPersistPropertyBagImpl"
  - "ATL.IPersistPropertyBagImpl<T>"
  - "ATL::IPersistPropertyBagImpl"
  - "ATL::IPersistPropertyBagImpl<T>"
  - "ATL.IPersistPropertyBagImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPersistPropertyBagImpl class"
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IPersistPropertyBagImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스를 구현 합니다.  **IUnknown** 및 해당 속성을 클라이언트가 제공한 속성 모음에 저장 하도록 합니다.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template <   
class T   
>  
class ATL_NO_VTABLE IPersistPropertyBagImpl :  
public IPersistPropertyBag  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IPersistPropertyBagImpl`.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IPersistPropertyBagImpl::GetClassID](../Topic/IPersistPropertyBagImpl::GetClassID.md)|개체의 CLSID를 검색합니다.|  
|[IPersistPropertyBagImpl::InitNew](../Topic/IPersistPropertyBagImpl::InitNew.md)|새로 만든된 개체를 초기화합니다.  ATL 구현을 반환 `S_OK`.|  
|[IPersistPropertyBagImpl::Load](../Topic/IPersistPropertyBagImpl::Load.md)|클라이언트가 제공한 속성 모음에서 개체의 속성을 로드합니다.|  
|[IPersistPropertyBagImpl::Save](../Topic/IPersistPropertyBagImpl::Save.md)|개체의 속성을 클라이언트가 제공한 속성 모음에 저장 됩니다.|  
  
## 설명  
 [IPersistPropertyBag](https://msdn.microsoft.com/en-us/library/aa768205.aspx) 인터페이스 속성을 클라이언트가 제공한 속성 모음에 저장 하는 개체 수 있습니다.  클래스 `IPersistPropertyBagImpl` 는이 인터페이스의 기본 구현을 제공 하 고 구현  **IUnknown** 덤프에 정보를 전송 하 여 장치에서 디버그 빌드.  
  
 **IPersistPropertyBag** 함께  [IPropertyBag](https://msdn.microsoft.com/en-us/library/aa768196.aspx) 및  [IErrorLog](https://msdn.microsoft.com/en-us/library/aa768231.aspx).  이러한 후자의 두 가지 인터페이스는 클라이언트에 의해 구현 되어야 합니다.  \- `IPropertyBag`, 클라이언트 저장 하 고 개체의 개별 속성을 로드 합니다.  \-  **IErrorLog**, 개체와 클라이언트 모두에 발생 한 오류를 보고할 수 있습니다.  
  
 **관련된 기사** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md),  [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## 상속 계층 구조  
 `IPersistPropertyBag`  
  
 `IPersistPropertyBagImpl`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [BEGIN\_PROP\_MAP](../Topic/BEGIN_PROP_MAP.md)   
 [Class Overview](../../atl/atl-class-overview.md)