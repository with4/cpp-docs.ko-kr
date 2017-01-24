---
title: "IOleInPlaceActiveObjectImpl Class | Microsoft Docs"
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
  - "IOleInPlaceActiveObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤[C++], communication between container and control"
  - "IOleInPlaceActiveObject, ATL 구현"
  - "IOleInPlaceActiveObjectImpl class"
ms.assetid: 44e6cc6d-a2dc-4187-98e3-73cf0320dea9
caps.latest.revision: 22
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IOleInPlaceActiveObjectImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스 내부 컨트롤과 컨테이너 사이의 통신을 지원 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template< class   
      T  
      >  
class IOleInPlaceActiveObjectImpl  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IOleInPlaceActiveObjectImpl`.  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[IOleInPlaceActiveObjectImpl::ContextSensitiveHelp](../Topic/IOleInPlaceActiveObjectImpl::ContextSensitiveHelp.md)|상황에 맞는 도움말이 있습니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IOleInPlaceActiveObjectImpl::EnableModeless](../Topic/IOleInPlaceActiveObjectImpl::EnableModeless.md)|모덜리스 대화 상자를 활성화 합니다.  ATL 구현을 반환 `S_OK`.|  
|[IOleInPlaceActiveObjectImpl::GetWindow](../Topic/IOleInPlaceActiveObjectImpl::GetWindow.md)|창 핸들을 가져옵니다.|  
|[IOleInPlaceActiveObjectImpl::OnDocWindowActivate](../Topic/IOleInPlaceActiveObjectImpl::OnDocWindowActivate.md)|컨테이너 문서 창 활성화 또는 비활성화 되 면 컨트롤을 알립니다.  ATL 구현을 반환 `S_OK`.|  
|[IOleInPlaceActiveObjectImpl::OnFrameWindowActivate](../Topic/IOleInPlaceActiveObjectImpl::OnFrameWindowActivate.md)|컨테이너의 최상위 수준 프레임 창이 활성화 또는 비활성화 되 면 컨트롤을 알립니다.  ATL 구현을 반환합니다.|  
|[IOleInPlaceActiveObjectImpl::ResizeBorder](../Topic/IOleInPlaceActiveObjectImpl::ResizeBorder.md)|테두리의 크기를 조정 하는 데 필요한 컨트롤에 알립니다.  ATL 구현을 반환 `S_OK`.|  
|[IOleInPlaceActiveObjectImpl::TranslateAccelerator](../Topic/IOleInPlaceActiveObjectImpl::TranslateAccelerator.md)|컨테이너 메뉴 액셀러레이터 키 메시지를 처리합니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
  
## 설명  
 [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299) 인터페이스 지원 통신 간의 전체 컨트롤과 해당 컨테이너. 예를 들어, 컨테이너에서 컨트롤의 활성 상태를 통신 하 고 컨트롤에 알리는 것 자체 크기를 조정 해야 합니다.  클래스 `IOleInPlaceActiveObjectImpl` 의 기본 구현을 제공 합니다. `IOleInPlaceActiveObject` 한 지원  **IUnknown** 덤프에 정보를 전송 하 여 장치에서 디버그 빌드.  
  
 **관련된 기사** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md),  [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## 상속 계층 구조  
 `IOleInPlaceActiveObject`  
  
 `IOleInPlaceActiveObjectImpl`  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX Controls Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Class Overview](../../atl/atl-class-overview.md)