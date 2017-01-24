---
title: "IQuickActivateImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::IQuickActivateImpl"
  - "ATL::IQuickActivateImpl<T>"
  - "ATL.IQuickActivateImpl"
  - "ATL.IQuickActivateImpl<T>"
  - "IQuickActivateImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "activating ATL controls"
  - "컨트롤[ATL], 활성화"
  - "IQuickActivate ATL implementation"
  - "IQuickActivateImpl class"
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IQuickActivateImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스 컨테이너의 컨트롤 초기화에 대 한 단일 호출을 결합합니다.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template<   
class T   
>  
class ATL_NO_VTABLE IQuickActivateImpl :  
public IQuickActivate  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IQuickActivateImpl`.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IQuickActivateImpl::GetContentExtent](../Topic/IQuickActivateImpl::GetContentExtent.md)|실행 중인 컨트롤의 현재 화면 크기를 검색합니다.|  
|[IQuickActivateImpl::QuickActivate](../Topic/IQuickActivateImpl::QuickActivate.md)|빠른 컨트롤을 로드 하 고 초기화를 수행 합니다.|  
|[IQuickActivateImpl::SetContentExtent](../Topic/IQuickActivateImpl::SetContentExtent.md)|컨트롤을의 컨테이너에 할당 된 디스플레이 공간을 알립니다.|  
  
## 설명  
 [IQuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms690146) 인터페이스 컨테이너 초기화에 대 한 단일 호출을 결합 하 여 컨트롤을 로드 하는 동안 지연 되지 않도록 도와줍니다.  `QuickActivate` 메서드는 컨테이너에 대 한 포인터를 전달할 수는  [QACONTAINER](http://msdn.microsoft.com/library/windows/desktop/ms688630) 컨트롤에 모든 인터페이스 포인터를 보유 하는 구조를 필요로 합니다.  반환, 컨트롤에 대 한 포인터를 다시 전달 된  [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) 컨테이너에서 사용 되는 자체 인터페이스 포인터를 보유 하는 구조입니다.  클래스 `IQuickActivateImpl` 의 기본 구현을 제공 합니다.  **IQuickActivate** 및 구현  **IUnknown** 덤프에 정보를 전송 하 여 장치에서 디버그 빌드.  
  
 **관련된 기사** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md),  [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## 상속 계층 구조  
 `IQuickActivate`  
  
 `IQuickActivateImpl`  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)