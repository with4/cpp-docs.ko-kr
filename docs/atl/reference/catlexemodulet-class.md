---
title: "CAtlExeModuleT 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::InitializeCom
- ATLBASE/ATL::CAtlExeModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlExeModuleT::PostMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::RegisterClassObjects
- ATLBASE/ATL::CAtlExeModuleT::RevokeClassObjects
- ATLBASE/ATL::CAtlExeModuleT::Run
- ATLBASE/ATL::CAtlExeModuleT::RunMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::UninitializeCom
- ATLBASE/ATL::CAtlExeModuleT::Unlock
- ATLBASE/ATL::CAtlExeModuleT::WinMain
- ATLBASE/ATL::CAtlExeModuleT::m_bDelayShutdown
- ATLBASE/ATL::CAtlExeModuleT::m_dwPause
- ATLBASE/ATL::CAtlExeModuleT::m_dwTimeOut
dev_langs:
- C++
helpviewer_keywords:
- CAtlExeModuleT class
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c45b1f95aba4f11e6995bf5c4c1cfff00627e4b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="catlexemodulet-class"></a>CAtlExeModuleT 클래스
이 클래스는 응용 프로그램에 대 한 모듈을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlExeModuleT : public CAtlModuleT<T>
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 클래스에서 파생 된 `CAtlExeModuleT`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlExeModuleT::CAtlExeModuleT](#catlexemodulet)|생성자입니다.|  
|[CAtlExeModuleT:: ~ CAtlExeModuleT](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlExeModuleT::InitializeCom](#initializecom)|COM.를 초기화합니다.|  
|[CAtlExeModuleT::ParseCommandLine](#parsecommandline)|명령줄 구문 분석 하 고 필요한 경우 등록을 수행 합니다.|  
|[CAtlExeModuleT::PostMessageLoop](#postmessageloop)|이 메서드는 메시지 루프 종료 된 후에 즉시 호출 됩니다.|  
|[CAtlExeModuleT::PreMessageLoop](#premessageloop)|이 메서드는 메시지 루프에 들어가기 전에 바로 호출 됩니다.|  
|[CAtlExeModuleT::RegisterClassObjects](#registerclassobjects)|클래스 개체를 등록합니다.|  
|[CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects)|클래스 개체를 취소합니다.|  
|[CAtlExeModuleT::Run](#run)|이 메서드는 초기화 메시지 루프를 실행 하는 EXE 모듈의 코드를 실행 하 고 정리 합니다.|  
|[CAtlExeModuleT::RunMessageLoop](#runmessageloop)|이 메서드는 메시지 루프를 실행 합니다.|  
|[CAtlExeModuleT::UninitializeCom](#uninitializecom)|COM. 초기화를 취소합니다|  
|[CAtlExeModuleT::Unlock](#unlock)|모듈의 잠금 횟수를 줄입니다.|  
|[CAtlExeModuleT::WinMain](#winmain)|이 메서드는 EXE를 실행 하는 데 필요한 코드를 구현 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown)|모듈을 종료 하는 지연 없어야 나타내는 플래그입니다.|  
|[CAtlExeModuleT::m_dwPause](#m_dwpause)|모든 개체를 종료 하기 전에 해제 되도록 하는 데 사용 되는 일시 중지 값입니다.|  
|[CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout)|모듈 언로드를 지연 하는 데 사용 되는 시간 제한 값입니다.|  
  
## <a name="remarks"></a>설명  
 `CAtlExeModuleT`응용 프로그램 (EXE)에 대 한 모듈을 나타내며 종료 시 EXE 만들기, 명령줄을 처리, 클래스 개체를 등록, 메시지 루프를 실행 및 정리를 지원 되는 코드를 포함 합니다.  
  
 이 클래스는 COM 개체 EXE 서버에서 지속적으로 생성 되 고 삭제 하는 경우 성능 향상을 위해 설계 되었습니다. 로 지정 된 기간에 대 한 EXE 대기 마지막 COM 개체가 해제 된 후의 [CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout) 데이터 멤버입니다. 이 기간 동안 활동이 없을 경우 (즉, COM 개체가 만들어지면) 종료 프로세스가 시작 됩니다.  
  
 [CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown) 데이터 멤버는 EXE 위에 정의 된 메커니즘을 사용 해야 하는 경우를 결정 하는 데 사용 하는 플래그입니다. False로 설정 됩니다 모듈 즉시 종료 됩니다.  
  
 ATL에서 모듈에 대 한 자세한 내용은 참조 하십시오. [ATL 모듈 클래스](../../atl/atl-module-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  

  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlExeModuleT`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="catlexemodulet"></a>CAtlExeModuleT::CAtlExeModuleT  
 생성자입니다.  
  
```
CAtlExeModuleT() throw();
```  
  
### <a name="remarks"></a>설명  
 EXE 모듈을 초기화할 수 있는 경우 WinMain 더 이상 처리 하지 않고 즉시 반환 합니다.  
  
##  <a name="dtor"></a>CAtlExeModuleT:: ~ CAtlExeModuleT  
 소멸자입니다.  
  
```
~CAtlExeModuleT() throw();
```  
  
### <a name="remarks"></a>설명  
 할당 된 모든 리소스를 해제합니다.  
  
##  <a name="initializecom"></a>CAtlExeModuleT::InitializeCom  
 COM.를 초기화합니다.  
  
```
static HRESULT InitializeCom() throw();
```  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 생성자에서 호출 되 고 기본 구현과에서 다른 방식으로 COM을 초기화 하기 위해 재정의할 수 있습니다. 기본 구현에서는 호출 하거나 **CoInitializeEx (NULL, COINIT_MULTITHREADED)** 또는 **CoInitialize(NULL)** 프로젝트 구성에 따라 합니다.  
  
 일반적으로이 메서드를 재정의 무시 해야 [CAtlExeModuleT::UninitializeCom](#uninitializecom)합니다.  
  
##  <a name="m_bdelayshutdown"></a>CAtlExeModuleT::m_bDelayShutdown  
 모듈을 종료 하는 지연 없어야 나타내는 플래그입니다.  
  
```
bool m_bDelayShutdown;
```  
  
### <a name="remarks"></a>설명  
 참조는 [CAtlExeModuleT 개요](../../atl/reference/catlexemodulet-class.md) 대 한 자세한 내용은 합니다.  
  
##  <a name="m_dwpause"></a>CAtlExeModuleT::m_dwPause  
 모든 개체는 종료 하기 전에 완료를 확인 하는 데 사용 되는 일시 중지 값입니다.  
  
```
DWORD m_dwPause;
```  
  
### <a name="remarks"></a>설명  
 이 값을 호출한 후 변경 [CAtlExeModuleT::InitializeCom](#initializecom) 서버 종료에 대 한 일시 중지 값으로 사용 하는 시간 (밀리초)의 수를 설정 합니다. 기본값은 1000 밀리초입니다.  
  
##  <a name="m_dwtimeout"></a>CAtlExeModuleT::m_dwTimeOut  
 모듈 언로드를 지연 하는 데 사용 되는 시간 제한 값입니다.  
  
```
DWORD m_dwTimeOut;
```  
  
### <a name="remarks"></a>설명  
 이 값을 호출한 후 변경 [CAtlExeModuleT::InitializeCom](#initializecom) 서버 종료에 대 한 제한 시간 값으로 사용 하는 시간 (밀리초)의 수를 정의 합니다. 기본값은 5000밀리초입니다. 참조는 [CAtlExeModuleT 개요](../../atl/reference/catlexemodulet-class.md) 내용을 확인 합니다.  
  
##  <a name="parsecommandline"></a>CAtlExeModuleT::ParseCommandLine  
 명령줄 구문 분석 하 고 필요한 경우 등록을 수행 합니다.  
  
```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpCmdLine`  
 명령줄 응용 프로그램에 전달 합니다.  
  
 `pnRetCode`  
 (전체 걸리는) 하는 경우 해당 등록 하는 HRESULT입니다.  
  
### <a name="return-value"></a>반환 값  
 응용 프로그램 실행, 그렇지 않으면 false를 계속 하면 true를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 [CAtlExeModuleT::WinMain](#winmain) 명령줄 스위치를 처리 하는 재정의 될 수 있습니다. 기본 구현에 대 한 확인 **/RegServer** 및 **프로그램이 /UnRegServer** 명령줄 인수 하 고 등록 또는 등록 취소를 수행 합니다.  
  
##  <a name="postmessageloop"></a>CAtlExeModuleT::PostMessageLoop  
 이 메서드는 메시지 루프 종료 된 후에 즉시 호출 됩니다.  
  
```
HRESULT PostMessageLoop() throw();
```  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 사용자 지정 응용 프로그램 정리를 수행 하도록이 메서드를 재정의 합니다. 기본 구현 호출 [CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects)합니다.  
  
##  <a name="premessageloop"></a>CAtlExeModuleT::PreMessageLoop  
 이 메서드는 메시지 루프에 들어가기 전에 바로 호출 됩니다.  
  
```
HRESULT PreMessageLoop(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nShowCmd`  
 로 전달 되는 값은 `nShowCmd` WinMain의 매개 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 응용 프로그램에 대 한 사용자 지정 초기화 코드를 추가 하려면이 메서드를 재정의 합니다. 기본 구현은 클래스 개체를 등록합니다.  
  
##  <a name="registerclassobjects"></a>CAtlExeModuleT::RegisterClassObjects  
 다른 응용 프로그램 데이터베이스에 연결할 수 있도록 ole 클래스 개체를 등록 합니다.  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *dwClsContext*  
 클래스 개체를 실행할의 컨텍스트를 지정 합니다. 가능한 값은 위해 CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER, 또는 CLSCTX_LOCAL_SERVER입니다.  
  
 `dwFlags`  
 클래스 개체에 연결 형식을 결정합니다. 가능한 값은 REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE, 또는 REGCLS_MULTI_SEPARATE입니다.  
  
### <a name="return-value"></a>반환 값  
 성공, S_FALSE를 등록 하려면 클래스가 있는 경우 또는 실패 시 오류 HRESULT에 S_OK를 반환 합니다.  
  
##  <a name="revokeclassobjects"></a>CAtlExeModuleT::RevokeClassObjects  
 클래스 개체를 제거합니다.  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>반환 값  
 성공, S_FALSE를 등록 하려면 클래스가 있는 경우 또는 실패 시 오류 HRESULT에 S_OK를 반환 합니다.  
  
##  <a name="run"></a>CAtlExeModuleT::Run  
 이 메서드는 초기화 메시지 루프를 실행 하는 EXE 모듈의 코드를 실행 하 고 정리 합니다.  
  
```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nShowCmd`  
 창 표시 방법을 지정 합니다. 이 매개 변수에서 설명 하는 값 중 하나일 수 있습니다는 [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) 섹션. SW_HIDE 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 재정의할 수 있습니다. 그러나 실제로 하는 것이 더 잘 재정의 [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](#runmessageloop), 또는 [CAtlExeModuleT::PostMessageLoop](#postmessageloop) 대신 합니다.  
  
##  <a name="runmessageloop"></a>CAtlExeModuleT::RunMessageLoop  
 이 메서드는 메시지 루프를 실행 합니다.  
  
```
void RunMessageLoop() throw();
```  
  
### <a name="remarks"></a>설명  
 메시지 루프의 동작을 변경 하려면이 메서드를 재정의할 수 있습니다.  
  
##  <a name="uninitializecom"></a>CAtlExeModuleT::UninitializeCom  
 COM. 초기화를 취소합니다  
  
```
static void UninitializeCom() throw();
```  
  
### <a name="remarks"></a>설명  
 기본적으로이 메서드를 호출 [CoUninitialize](http://msdn.microsoft.com/library/windows/desktop/ms688715) 소멸자에서 호출 됩니다. 이 메서드를 재정의 하는 경우 재정의 [CAtlExeModuleT::InitializeCom](#initializecom)합니다.  
  
##  <a name="unlock"></a>CAtlExeModuleT::Unlock  
 모듈의 잠금 횟수를 줄입니다.  
  
```
LONG Unlock() throw();
```  
  
### <a name="return-value"></a>반환 값  
 진단에 대 한 유용한 또는 테스트 값을 반환 합니다.  
  
##  <a name="winmain"></a>CAtlExeModuleT::WinMain  
 이 메서드는 EXE를 실행 하는 데 필요한 코드를 구현 합니다.  
  
```
int WinMain(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nShowCmd`  
 창 표시 방법을 지정 합니다. 이 매개 변수에서 설명 하는 값 중 하나일 수 있습니다는 [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) 섹션.  
  
### <a name="return-value"></a>반환 값  
 실행 파일의 반환 값을 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 재정의할 수 있습니다. 재정의 하는 경우 [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::PostMessageLoop](#postmessageloop), 또는 [CAtlExeModuleT::RunMessageLoop](#runmessageloop) 에 충분 한 유연성을 제공 하지 않습니다 를 재정의할 수는 `WinMain` 이 메서드를 사용 하 여 작동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATLDuck 샘플](../../visual-cpp-samples.md)   
 [CAtlModuleT 클래스](../../atl/reference/catlmodulet-class.md)   
 [CAtlDllModuleT 클래스](../../atl/reference/catldllmodulet-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
