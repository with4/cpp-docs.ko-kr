---
title: "CAtlServiceModuleT Class | Microsoft Docs"
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
  - "ATL::CAtlServiceModuleT"
  - "ATL.CAtlServiceModuleT"
  - "CAtlServiceModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlServiceModuleT class"
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlServiceModuleT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 서비스를 구현합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template <  
class T,  
UINT nServiceNameID   
>  
class ATL_NO_VTABLE CAtlServiceModuleT :  
public CAtlExeModuleT< T>  
```  
  
#### 매개 변수  
 `T`  
 클래스에서 파생 된 `CAtlServiceModuleT`.  
  
 *nServiceNameID*  
 서비스의 리소스 식별자입니다.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAtlServiceModuleT::CAtlServiceModuleT](../Topic/CAtlServiceModuleT::CAtlServiceModuleT.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAtlServiceModuleT::Handler](../Topic/CAtlServiceModuleT::Handler.md)|서비스에 대 한 처리기 루틴입니다.|  
|[CAtlServiceModuleT::InitializeSecurity](../Topic/CAtlServiceModuleT::InitializeSecurity.md)|기본 보안 설정에 대 한 서비스를 제공합니다.|  
|[CAtlServiceModuleT::Install](../Topic/CAtlServiceModuleT::Install.md)|설치 및 서비스를 만듭니다.|  
|[CAtlServiceModuleT::IsInstalled](../Topic/CAtlServiceModuleT::IsInstalled.md)|서비스가 설치 되어 있는지 확인 합니다.|  
|[CAtlServiceModuleT::LogEvent](../Topic/CAtlServiceModuleT::LogEvent.md)|이벤트 로그에 씁니다.|  
|[CAtlServiceModuleT::OnContinue](../Topic/CAtlServiceModuleT::OnContinue.md)|서비스를 계속 하려면이 메서드를 재정의 합니다.|  
|[CAtlServiceModuleT::OnInterrogate](../Topic/CAtlServiceModuleT::OnInterrogate.md)|서비스를 검색 하려면이 메서드를 재정의 합니다.|  
|[CAtlServiceModuleT::OnPause](../Topic/CAtlServiceModuleT::OnPause.md)|서비스를 일시 중지 하려면이 메서드를 재정의 합니다.|  
|[CAtlServiceModuleT::OnShutdown](../Topic/CAtlServiceModuleT::OnShutdown.md)|서비스를 종료 하려면이 메서드를 재정의 합니다.|  
|[CAtlServiceModuleT::OnStop](../Topic/CAtlServiceModuleT::OnStop.md)|서비스를 중지 하려면이 메서드를 재정의 합니다.|  
|[CAtlServiceModuleT::OnUnknownRequest](../Topic/CAtlServiceModuleT::OnUnknownRequest.md)|서비스에 알 수 없는 요청을 처리 하려면이 메서드를 재정의 합니다.|  
|[CAtlServiceModuleT::ParseCommandLine](../Topic/CAtlServiceModuleT::ParseCommandLine.md)|명령줄을 구문 분석 하 고 필요한 경우 등록이 수행 합니다.|  
|[CAtlServiceModuleT::PreMessageLoop](../Topic/CAtlServiceModuleT::PreMessageLoop.md)|이 메서드는 메시지 루프를 입력 하기 전에 즉시 호출 됩니다.|  
|[CAtlServiceModuleT::RegisterAppId](../Topic/CAtlServiceModuleT::RegisterAppId.md)|서비스를 등록합니다.|  
|[CAtlServiceModuleT::Run](../Topic/CAtlServiceModuleT::Run.md)|서비스를 실행합니다.|  
|[CAtlServiceModuleT::ServiceMain](../Topic/CAtlServiceModuleT::ServiceMain.md)|서비스 제어 관리자에 의해 호출 되는 메서드.|  
|[CAtlServiceModuleT::SetServiceStatus](../Topic/CAtlServiceModuleT::SetServiceStatus.md)|서비스 상태를 업데이트합니다.|  
|[CAtlServiceModuleT::Start](../Topic/CAtlServiceModuleT::Start.md)|호출 하 `CAtlServiceModuleT::WinMain` 서비스를 시작할 때.|  
|[CAtlServiceModuleT::Uninstall](../Topic/CAtlServiceModuleT::Uninstall.md)|중지 하 고 서비스를 제거 합니다.|  
|[CAtlServiceModuleT::Unlock](../Topic/CAtlServiceModuleT::Unlock.md)|서비스의 잠금 횟수를 줄입니다.|  
|[CAtlServiceModuleT::UnregisterAppId](../Topic/CAtlServiceModuleT::UnregisterAppId.md)|서비스를 제거합니다.|  
|[CAtlServiceModuleT::WinMain](../Topic/CAtlServiceModuleT::WinMain.md)|이 메서드는 서비스를 실행 하는 데 필요한 코드를 구현 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAtlServiceModuleT::m\_bService](../Topic/CAtlServiceModuleT::m_bService.md)|프로그램을 서비스로 실행을 나타내는 플래그입니다.|  
|[CAtlServiceModuleT::m\_dwThreadID](../Topic/CAtlServiceModuleT::m_dwThreadID.md)|멤버 변수에 스레드 id를 저장 합니다.|  
|[CAtlServiceModuleT::m\_hServiceStatus](../Topic/CAtlServiceModuleT::m_hServiceStatus.md)|멤버 변수를 현재 서비스 상태 정보 구조에 대 한 핸들을 저장 합니다.|  
|[CAtlServiceModuleT::m\_status](../Topic/CAtlServiceModuleT::m_status.md)|현재 서비스 상태 정보 구조를 저장할 멤버 변수입니다.|  
|[CAtlServiceModuleT::m\_szServiceName](../Topic/CAtlServiceModuleT::m_szServiceName.md)|등록 하는 서비스의 이름입니다.|  
  
## 설명  
 `CAtlServiceModuleT`에서 파생 된  [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), ATL 서비스 모듈을 구현 합니다.  `CAtlServiceModuleT`명령줄 처리, 설치, 등록 및 제거에 대 한 메서드를 제공 합니다.  이러한 메서드와 다른 추가 기능이 필요한 경우 재정의할 수 있습니다.  
  
 이 클래스는 사용 되지 않는 대체  [CComModule 클래스](../../atl/reference/ccommodule-class.md) ATL.의 이전 버전에서 사용  참조  [ATL 모듈 클래스](../../atl/atl-module-classes.md) 에 대 한 자세한 내용은.  
  
## 상속 계층 구조  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)  
  
 `CAtlServiceModuleT`  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 참고 항목  
 [CAtlExeModuleT Class](../../atl/reference/catlexemodulet-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)