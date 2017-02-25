---
title: "IPropertyPageImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IPropertyPageImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPropertyPage ATL implementation"
  - "IPropertyPageImpl class"
  - "속성 페이지"
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# IPropertyPageImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스를 구현 합니다.  **IUnknown** 의 기본 구현을 제공 하 고 있는  [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) 인터페이스.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template< class   
      T  
      >  
class IPropertyPageImpl  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IPropertyPageImpl`.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[IPropertyPageImpl::IPropertyPageImpl](../Topic/IPropertyPageImpl::IPropertyPageImpl.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IPropertyPageImpl::Activate](../Topic/IPropertyPageImpl::Activate.md)|대화 상자 창에 대 한 속성 페이지를 만듭니다.|  
|[IPropertyPageImpl::Apply](../Topic/IPropertyPageImpl::Apply.md)|속성 페이지의 현재 값을 통해 지정 된 내부 개체가 적용 `SetObjects`.  ATL 구현을 반환 `S_OK`.|  
|[IPropertyPageImpl::Deactivate](../Topic/IPropertyPageImpl::Deactivate.md)|작성 창을 소멸  **활성화**.|  
|[IPropertyPageImpl::GetPageInfo](../Topic/IPropertyPageImpl::GetPageInfo.md)|속성 페이지에 대 한 정보를 검색합니다.|  
|[IPropertyPageImpl::Help](../Topic/IPropertyPageImpl::Help.md)|속성 페이지에 대 한 Windows 도움말을 호출합니다.|  
|[IPropertyPageImpl::IsPageDirty](../Topic/IPropertyPageImpl::IsPageDirty.md)|활성화 된 후 속성 페이지를 변경 했는지 여부를 나타냅니다.|  
|[IPropertyPageImpl::Move](../Topic/IPropertyPageImpl::Move.md)|배치 및 속성 페이지 대화 상자 크기를 조정 합니다.|  
|[IPropertyPageImpl::SetDirty](../Topic/IPropertyPageImpl::SetDirty.md)|속성 페이지의 상태가 변경 되거나 변경 되지 않은 플래그를 지정 합니다.|  
|[IPropertyPageImpl::SetObjects](../Topic/IPropertyPageImpl::SetObjects.md)|배열을 제공  **IUnknown** 속성 페이지와 관련 된 개체에 대 한 포인터입니다.  현재 페이지 값 속성 호출을 통해 이러한 개체를 받을  **적용**.|  
|[IPropertyPageImpl::SetPageSite](../Topic/IPropertyPageImpl::SetPageSite.md)|속성 페이지에서 제공 된 `IPropertyPageSite` 포인터 속성 페이지 통신 속성 프레임을 통해.|  
|[IPropertyPageImpl::Show](../Topic/IPropertyPageImpl::Show.md)|속성 페이지 대화 상자를 표시 하거나 숨길 수 있습니다.|  
|[IPropertyPageImpl::TranslateAccelerator](../Topic/IPropertyPageImpl::TranslateAccelerator.md)|지정 된 키 입력을 처리합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[IPropertyPageImpl::m\_bDirty](../Topic/IPropertyPageImpl::m_bDirty.md)|속성 페이지의 상태가 변경 되었는지 여부를 지정 합니다.|  
|[IPropertyPageImpl::m\_dwDocString](../Topic/IPropertyPageImpl::m_dwDocString.md)|속성 페이지를 설명 하는 텍스트 문자열을 연결 하는 리소스 식별자를 저장 합니다.|  
|[IPropertyPageImpl::m\_dwHelpContext](../Topic/IPropertyPageImpl::m_dwHelpContext.md)|속성 페이지와 관련 된 도움말 컨텍스트 식별자를 저장 합니다.|  
|[IPropertyPageImpl::m\_dwHelpFile](../Topic/IPropertyPageImpl::m_dwHelpFile.md)|속성 페이지를 설명 하는 도움말 파일의 이름에 연결 하는 리소스 식별자를 저장 합니다.|  
|[IPropertyPageImpl::m\_dwTitle](../Topic/IPropertyPageImpl::m_dwTitle.md)|속성 페이지의 탭에 표시 되는 텍스트 문자열을 연결 하는 리소스 식별자를 저장 합니다.|  
|[IPropertyPageImpl::m\_nObjects](../Topic/IPropertyPageImpl::m_nObjects.md)|속성 페이지와 관련 된 개체를 저장 합니다.|  
|[IPropertyPageImpl::m\_pPageSite](../Topic/IPropertyPageImpl::m_pPageSite.md)|가리키는 있는 `IPropertyPageSite` 인터페이스 속성 페이지 통신 속성 프레임을 통해.|  
|[IPropertyPageImpl::m\_ppUnk](../Topic/IPropertyPageImpl::m_ppUnk.md)|배열을 가리키는  **IUnknown** 속성 페이지와 관련 된 개체에 대 한 포인터입니다.|  
|[IPropertyPageImpl::m\_size](../Topic/IPropertyPageImpl::m_size.md)|높이 너비의 속성 페이지 대화 상자에서 픽셀 단위로 저장 됩니다.|  
  
## 설명  
 [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) 인터페이스 개체 속성 시트 내에서 특정 속성 페이지를 관리할 수 있습니다.  클래스 `IPropertyPageImpl` 는이 인터페이스의 기본 구현을 제공 하 고 구현  **IUnknown** 덤프에 정보를 전송 하 여 장치에서 디버그 빌드.  
  
 **관련된 기사** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md),  [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## 상속 계층 구조  
 `IPropertyPage`  
  
 `IPropertyPageImpl`  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [IPropertyPage2Impl Class](../../atl/reference/ipropertypage2impl-class.md)   
 [IPerPropertyBrowsingImpl Class](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl Class](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)