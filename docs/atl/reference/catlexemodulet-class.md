---
title: "CAtlExeModuleT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAtlExeModuleT<T>"
  - "CAtlExeModuleT"
  - "ATL.CAtlExeModuleT<T>"
  - "ATL::CAtlExeModuleT"
  - "ATL.CAtlExeModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlExeModuleT class"
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CAtlExeModuleT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스 모듈을 대 한 응용 프로그램을 나타냅니다.  
  
## 구문  
  
```  
  
      template <  
   class T   
>  
class ATL_NO_VTABLE CAtlExeModuleT :  
   public CAtlModuleT< T >  
```  
  
#### 매개 변수  
 `T`  
 클래스에서 파생 된 `CAtlExeModuleT`.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAtlExeModuleT::CAtlExeModuleT](../Topic/CAtlExeModuleT::CAtlExeModuleT.md)|생성자입니다.|  
|[CAtlExeModuleT::~CAtlExeModuleT](../Topic/CAtlExeModuleT::~CAtlExeModuleT.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAtlExeModuleT::InitializeCom](../Topic/CAtlExeModuleT::InitializeCom.md)|COM을 초기화|  
|[CAtlExeModuleT::ParseCommandLine](../Topic/CAtlExeModuleT::ParseCommandLine.md)|명령줄을 구문 분석 하 고 필요한 경우 등록이 수행 합니다.|  
|[CAtlExeModuleT::PostMessageLoop](../Topic/CAtlExeModuleT::PostMessageLoop.md)|메시지 루프를 즉시 종료 후이 메서드를 호출 합니다.|  
|[CAtlExeModuleT::PreMessageLoop](../Topic/CAtlExeModuleT::PreMessageLoop.md)|이 메서드는 메시지 루프를 입력 하기 전에 즉시 호출 됩니다.|  
|[CAtlExeModuleT::RegisterClassObjects](../Topic/CAtlExeModuleT::RegisterClassObjects.md)|클래스 개체를 등록합니다.|  
|[CAtlExeModuleT::RevokeClassObjects](../Topic/CAtlExeModuleT::RevokeClassObjects.md)|클래스 개체를 해지합니다.|  
|[CAtlExeModuleT::Run](../Topic/CAtlExeModuleT::Run.md)|이 메서드는 초기화, 메시지 루프를 실행 하려면 EXE 모듈에서 코드를 실행 하 고 정리.|  
|[CAtlExeModuleT::RunMessageLoop](../Topic/CAtlExeModuleT::RunMessageLoop.md)|이 메서드는 메시지 루프가 실행 됩니다.|  
|[CAtlExeModuleT::UninitializeCom](../Topic/CAtlExeModuleT::UninitializeCom.md)|COM.를 초기화 하지 않습니다.|  
|[CAtlExeModuleT::Unlock](../Topic/CAtlExeModuleT::Unlock.md)|모듈의 잠금 횟수를 줄입니다.|  
|[CAtlExeModuleT::WinMain](../Topic/CAtlExeModuleT::WinMain.md)|이 메서드는 EXE를 실행 하는 데 필요한 코드를 구현 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAtlExeModuleT::m\_bDelayShutdown](../Topic/CAtlExeModuleT::m_bDelayShutdown.md)|모듈 아래로 종료 지연 있어야 나타내는 플래그입니다.|  
|[CAtlExeModuleT::m\_dwPause](../Topic/CAtlExeModuleT::m_dwPause.md)|종료 하기 전에 모든 객체를 릴리즈 하는 일시 중지 값입니다.|  
|[CAtlExeModuleT::m\_dwTimeOut](../Topic/CAtlExeModuleT::m_dwTimeOut.md)|시간 제한 값의 모듈 언로드를 지연 하는 데 사용 합니다.|  
  
## 설명  
 `CAtlExeModuleT`모듈 응용 프로그램 \(EXE\)을 나타내며 EXE 만들기, 명령줄을 처리, 클래스 개체를 등록 하 고 메시지 루프를 실행 정리 끝내기에서 지 원하는 코드를 포함 합니다.  
  
 이 클래스는 COM 개체에 EXE 서버를 지속적으로 만들어 소멸 때 성능을 향상 시키기 위해 설계 되었습니다.  마지막으로 COM 개체를 해제 한 후 지정 된 기간 동안 EXE 대기는  [CAtlExeModuleT::m\_dwTimeOut](../Topic/CAtlExeModuleT::m_dwTimeOut.md) 데이터 멤버입니다.  이 기간 동안 활동이 없으면 \(즉, COM 개체가 만들어지는\) 종료 프로세스를 시작 합니다.  
  
 [CAtlExeModuleT::m\_bDelayShutdown](../Topic/CAtlExeModuleT::m_bDelayShutdown.md) 데이터 멤버 EXE 위에 정의 된 메커니즘을 사용 해야 하는지 결정 하는 데 사용 되는 플래그입니다.  False로 설정 된 경우 모듈은 즉시 종료 됩니다.  
  
 Atl에서 모듈에 대 한 자세한 내용은  [ATL 모듈 클래스](../../atl/atl-module-classes.md).  
  
## 상속 계층 구조  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlExeModuleT`  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 참고 항목  
 [ATLDuck 샘플](../../top/visual-cpp-samples.md)   
 [CAtlModuleT Class](../../atl/reference/catlmodulet-class.md)   
 [CAtlDllModuleT Class](../../atl/reference/catldllmodulet-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)