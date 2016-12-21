---
title: "IProvideClassInfo2Impl Class | Microsoft Docs"
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
  - "IProvideClassInfo2"
  - "ATL.IProvideClassInfo2Impl"
  - "IProvideClassInfo2Impl"
  - "ATL::IProvideClassInfo2Impl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "class information, ATL"
  - "IProvideClassInfo2 ATL implementation"
  - "IProvideClassInfo2Impl class"
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IProvideClassInfo2Impl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스의 기본 구현을 제공 된  [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) 및  [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) 방법.  
  
## 구문  
  
```  
  
      template <  
   const CLSID* pcoclsid,  
   const IID* psrcid,  
   const GUID* plibid = &CAtlModule::m_libid,  
   WORD wMajor = 1,  
   WORD wMinor = 0,  
   class tihclass = CComTypeInfoHolder   
>  
class ATL_NO_VTABLE IProvideClassInfo2Impl :  
   public IProvideClassInfo2  
```  
  
#### 매개 변수  
 *pcoclsid*  
 Coclass의 식별자에 대 한 포인터입니다.  
  
 *psrcid*  
 Dispinterface 나가는 coclass의 기본 식별자에 대 한 포인터입니다.  
  
 `plibid`  
 LIBID 인터페이스에 대 한 정보를 포함 하는 형식 라이브러리에 대 한 포인터입니다.  기본적으로 서버 형식 라이브러리에 전달 됩니다.  
  
 `wMajor`  
 형식 라이브러리의 주 버전입니다.  기본값은 1입니다.  
  
 `wMinor`  
 형식 라이브러리의 부 버전입니다.  기본값은 0입니다.  
  
 `tihclass`  
 Coclass의 형식 정보를 관리 하는 데 사용 되는 클래스입니다.  기본값은 `CComTypeInfoHolder`입니다.  
  
## Members  
  
### 생성자  
  
|Name|설명|  
|----------|--------|  
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](../Topic/IProvideClassInfo2Impl::IProvideClassInfo2Impl.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IProvideClassInfo2Impl::GetClassInfo](../Topic/IProvideClassInfo2Impl::GetClassInfo.md)|검색 된  **ITypeInfo** coclass의 형식 정보에 대 한 포인터입니다.|  
|[IProvideClassInfo2Impl::GetGUID](../Topic/IProvideClassInfo2Impl::GetGUID.md)|개체의 나가는 dispinterface의 GUID를 검색합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[IProvideClassInfo2Impl::\_tih](../Topic/IProvideClassInfo2Impl::_tih.md)|Coclass에 대 한 형식 정보를 관리합니다.|  
  
## 설명  
 [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) 인터페이스 확장  [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) 추가 된 `GetGUID` 메서드.  이 메서드는 클라이언트를 개체의 나가는 인터페이스 IID는 기본 이벤트 집합을 검색할 수 있습니다.  클래스 `IProvideClassInfo2Impl` 의 기본 구현을 제공 된  **IProvideClassInfo** 및 `IProvideClassInfo2` 방법.  
  
 `IProvideClassInfo2Impl`형식의 정적 멤버를 포함 `CComTypeInfoHolder` 하는 coclass에 대 한 형식 정보를 관리 합니다.  
  
## 상속 계층 구조  
 `IProvideClassInfo2`  
  
 `IProvideClassInfo2Impl`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)