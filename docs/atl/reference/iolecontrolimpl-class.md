---
title: "IOleControlImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IOleControlImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IOleControlImpl class"
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# IOleControlImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스의 기본 구현을 제공 된  **IOleControl** 인터페이스를 구현 하 고  **IUnknown**.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template< class   
      T  
      >  
class IOleControlImpl  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IOleControlImpl`.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IOleControlImpl::FreezeEvents](../Topic/IOleControlImpl::FreezeEvents.md)|컨테이너 무시 또는 컨트롤에서 이벤트를 수락 하는지 여부를 나타냅니다.|  
|[IOleControlImpl::GetControlInfo](../Topic/IOleControlImpl::GetControlInfo.md)|컨트롤의 키보드 동작에 대 한 정보를 채웁니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IOleControlImpl::OnAmbientPropertyChange](../Topic/IOleControlImpl::OnAmbientPropertyChange.md)|컨트롤 컨테이너의 앰비언트 속성 중 하나 이상이 변경 되었음을 알립니다.  ATL 구현을 반환 `S_OK`.|  
|[IOleControlImpl::OnMnemonic](../Topic/IOleControlImpl::OnMnemonic.md)|컨트롤은 사용자가 지정 된 키를 눌렀음을 알립니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
  
## 설명  
 클래스 `IOleControlImpl` 의 기본 구현을 제공은  [IOleControl](http://msdn.microsoft.com/library/windows/desktop/ms694320) 인터페이스를 구현 하 고  **IUnknown** 덤프에 정보를 전송 하 여 장치에서 디버그 빌드.  
  
 **관련된 기사** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md),  [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## 상속 계층 구조  
 `IOleControl`  
  
 `IOleControlImpl`  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [IOleObjectImpl Class](../../atl/reference/ioleobjectimpl-class.md)   
 [ActiveX Controls Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Class Overview](../../atl/atl-class-overview.md)