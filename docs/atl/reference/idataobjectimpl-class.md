---
title: "IDataObjectImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDataObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "data transfer [C++]"
  - "data transfer [C++], Uniform Data Transfer"
  - "IDataObject, ATL 구현"
  - "IDataObjectImpl class"
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IDataObjectImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 단일형 데이터 전송 지원 하 고 연결을 관리 하는 방법을 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template< class   
      T  
      >  
class IDataObjectImpl  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IDataObjectImpl`.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IDataObjectImpl::DAdvise](../Topic/IDataObjectImpl::DAdvise.md)|데이터 개체와 advise 싱크 간의 연결을 설정합니다.  따라서 advise 싱크에 개체에서 변경 알림을 받을 수 있습니다.|  
|[IDataObjectImpl::DUnadvise](../Topic/IDataObjectImpl::DUnadvise.md)|통해 이전에 설정 된 연결을 종료 `DAdvise`.|  
|[IDataObjectImpl::EnumDAdvise](../Topic/IDataObjectImpl::EnumDAdvise.md)|현재 advise 연결을 반복할 열거자를 만듭니다.|  
|[IDataObjectImpl::EnumFormatEtc](../Topic/IDataObjectImpl::EnumFormatEtc.md)|반복 하는 열거자를 만듭니다는  **FORMATETC** 데이터 개체에서 지 원하는 구조입니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IDataObjectImpl::FireDataChange](../Topic/IDataObjectImpl::FireDataChange.md)|변경 알림을 각 advise 싱크에 보냅니다.|  
|[IDataObjectImpl::GetCanonicalFormatEtc](../Topic/IDataObjectImpl::GetCanonicalFormatEtc.md)|논리적으로 같은 검색  **FORMATETC** 하나 더 복잡 한 구조.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IDataObjectImpl::GetData](../Topic/IDataObjectImpl::GetData.md)|데이터 개체의 데이터를 클라이언트에 전송합니다.  데이터에 설명 되어 있는  **FORMATETC** 구조 및 통해 전송 되는  **STGMEDIUM** 구조.|  
|[IDataObjectImpl::GetDataHere](../Topic/IDataObjectImpl::GetDataHere.md)|비슷한 `GetData`, 클라이언트에 할당 해야 하는 점을 제외 하 고는  **STGMEDIUM** 구조.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IDataObjectImpl::QueryGetData](../Topic/IDataObjectImpl::QueryGetData.md)|특정 데이터 개체를 지원 하는지 여부를 결정 합니다.  **FORMATETC** 구조에 데이터를 전송 합니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IDataObjectImpl::SetData](../Topic/IDataObjectImpl::SetData.md)|클라이언트의 데이터를 데이터 개체에 전송합니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
  
## 설명  
 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) 인터페이스는 단일형 데이터 전송를 지 원하는 메서드를 제공 합니다.  `IDataObject`표준 형식 구조를 사용 하 여  [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 및  [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 검색 하 고 데이터를 저장 합니다.  
  
 `IDataObject`또한 데이터 변경 알림을 처리 하는 싱크를 알리기 위해 연결을 관리 합니다.  데이터 개체에서 데이터 변경 알림을 수신 하는 클라이언트에 대 한 순서로 클라이언트 구현 해야는  [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) 인터페이스 advise 싱크 라는 개체의.  다음 클라이언트를 호출 하면  **IDataObject::DAdvise**, 데이터 개체와 advise 싱크 간의 연결입니다.  
  
 클래스 `IDataObjectImpl` 의 기본 구현을 제공 합니다. `IDataObject` 및 구현  **IUnknown** 덤프에 정보를 전송 하 여 장치에서 디버그 빌드.  
  
 **관련된 기사** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md),  [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## 상속 계층 구조  
 `IDataObject`  
  
 `IDataObjectImpl`  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)