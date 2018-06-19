---
title: CDebugReportHook 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHookProc
- ATLUTIL/ATL::CDebugReportHook::RemoveHook
- ATLUTIL/ATL::CDebugReportHook::SetHook
- ATLUTIL/ATL::CDebugReportHook::SetPipeName
- ATLUTIL/ATL::CDebugReportHook::SetTimeout
dev_langs:
- C++
helpviewer_keywords:
- CDebugReportHook class
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d84b2da8a347833513e0725695bb9d2bacd2951d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360252"
---
# <a name="cdebugreporthook-class"></a>CDebugReportHook 클래스
이 클래스를 사용 하 여 명명된 된 파이프에 디버그 보고서를 보내도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class CDebugReportHook
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDebugReportHook::CDebugReportHook](#cdebugreporthook)|호출 [SetPipeName](#setpipename), [SetTimeout](#settimeout), 및 [SetHook](#sethook)합니다.|  
|[CDebugReportHook:: ~ CDebugReportHook](#dtor)|호출 [CDebugReportHook::RemoveHook](#removehook)합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDebugReportHook::CDebugReportHookProc](#cdebugreporthookproc)|(정적) C 런타임 디버그 보고 프로세스에 연결 되는 사용자 지정 보고 함수입니다.|  
|[CDebugReportHook::RemoveHook](#removehook)|명명된 된 파이프에 디버그 보고서를 전달 하지 않도록 하려면이 메서드를 호출 하 고 이전 보고서 후크를 복원 합니다.|  
|[CDebugReportHook::SetHook](#sethook)|명명된 된 파이프로 디버그 보고서를 보내기 시작 하도록이 메서드를 호출 합니다.|  
|[CDebugReportHook::SetPipeName](#setpipename)|컴퓨터 및 디버그 보고서를 보내지 파이프의 이름을 설정 하려면이 메서드를 호출 합니다.|  
|[CDebugReportHook::SetTimeout](#settimeout)|이 클래스는 명명 된 파이프를 사용할 수 있을 때까지 대기 하는 시간 (밀리초)의 시간을 설정 하려면이 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>설명  
 서비스 또는 명명된 된 파이프에 디버그 보고서를 보내도록 응용 프로그램의 디버그 빌드에이 클래스의 인스턴스를 만듭니다. 호출 하 여 생성 된 디버그 보고 [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) 또는 같은이 함수에 대 한 래퍼를 사용 하는 [ATLTRACE](debugging-and-error-reporting-macros.md#atltrace) 및 [ATLASSERT](debugging-and-error-reporting-macros.md#atlassert) 매크로입니다.  
  
 이 클래스의 사용을 사용 하면 비 대화형 데스크톱에서 실행 하는 구성 요소를 대화형으로 디버깅 하 [창 스테이션](http://msdn.microsoft.com/library/windows/desktop/ms687096)합니다.  
  
 Note 스레드의 기본 보안 컨텍스트를 사용 하 여 디버그 보고서가 전송 합니다. 가장은 여기서 가장 낮은 권한의 사용자의 조치가 발생 하는와 같은 웹 응용 프로그램의 경우 디버그 보고서를 볼 수 없도록 일시적으로 비활성화 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlutil.h  
  
##  <a name="cdebugreporthook"></a>  CDebugReportHook::CDebugReportHook  
 호출 [SetPipeName](#setpipename), [SetTimeout](#settimeout), 및 [SetHook](#sethook)합니다.  
  
```
CDebugReportHook(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe",
    DWORD dwTimeout = 20000) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `szMachineName`  
 디버그 출력을 전송 해야 하는 컴퓨터의 이름입니다. 로컬 컴퓨터에 대 한 기본값입니다.  
  
 `szPipeName`  
 디버그 출력을 전송 해야 하는 명명된 된 파이프의 이름입니다.  
  
 `dwTimeout`  
 시간 (밀리초)는이 클래스는 명명 된 파이프를 사용할 수 있을 때까지 대기 합니다.  
  
##  <a name="dtor"></a>  CDebugReportHook:: ~ CDebugReportHook  
 호출 [CDebugReportHook::RemoveHook](#removehook)합니다.  
  
```
~CDebugReportHook() throw();
```  
  
##  <a name="cdebugreporthookproc"></a>  CDebugReportHook::CDebugReportHookProc  
 C 런타임 디버그 보고 프로세스에 연결 되는 사용자 지정 보고 함수입니다.  
  
```
static int __cdecl CDebugReportHookProc(
    int reportType,
    char* message,
    int* returnValue) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `reportType`  
 (_CRT_WARN, _CRT_ERROR, 또는 _CRT_ASSERT) 보고서의 형식입니다.  
  
 `message`  
 메시지 문자열입니다.  
  
 *ReturnValue*  
 반환 해야 하는 값 [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)합니다.  
  
### <a name="return-value"></a>반환 값  
 더 이상 보고 하지 않으려면 검사가 필요 하도록 후크 요청한 메시지를 완전히 처리 하는 경우 FALSE를 반환 합니다. TRUE를 반환 합니다 `_CrtDbgReport` 일반적인 방법으로 메시지를 보고 해야 합니다.  
  
### <a name="remarks"></a>설명  
 보고 함수를 명명된 된 파이프를 열고 다른 쪽 끝에서 프로세스와 통신 하려고 합니다. 파이프 사용 중인 경우 보고 함수는 파이프는 무료 또는 제한 시간이 만료 될 때까지 대기 합니다. 호출이 생성자 나 여 제한 시간을 설정할 수 있습니다 [CDebugReportHook::SetTimeout](#settimeout)합니다.  
  
 이 함수에서 코드 호출 스레드의 기본 보안 컨텍스트에서 실행 되 고,이 함수의 지속 시간에 대 한 가장을 사용할 수 없습니다, 합니다.  
  
##  <a name="removehook"></a>  CDebugReportHook::RemoveHook  
 명명된 된 파이프에 디버그 보고서를 전달 하지 않도록 하려면이 메서드를 호출 하 고 이전 보고서 후크를 복원 합니다.  
  
```
void RemoveHook() throw();
```  
  
### <a name="remarks"></a>설명  
 호출 [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) 이전 보고서 후크를 복원 합니다.  
  
##  <a name="sethook"></a>  CDebugReportHook::SetHook  
 명명된 된 파이프로 디버그 보고서를 보내기 시작 하도록이 메서드를 호출 합니다.  
  
```
void SetHook() throw();
```  
  
### <a name="remarks"></a>설명  
 호출 [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) 디버그 보고서를 통해 라우팅될가 있어야 [CDebugReportHookProc](#cdebugreporthookproc) 의 명명 된 파이프 합니다. 이 클래스는 추적 하는 이전 보고서 후크 될 수 있도록 복원할 때 [RemoveHook](#removehook) 호출 됩니다.  
  
##  <a name="setpipename"></a>  CDebugReportHook::SetPipeName  
 컴퓨터 및 디버그 보고서를 보내지 파이프의 이름을 설정 하려면이 메서드를 호출 합니다.  
  
```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `szMachineName`  
 디버그 출력을 전송 해야 하는 컴퓨터의 이름입니다.  
  
 `szPipeName`  
 디버그 출력을 전송 해야 하는 명명된 된 파이프의 이름입니다.  
  
### <a name="return-value"></a>반환 값  
 성공할 경우 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
##  <a name="settimeout"></a>  CDebugReportHook::SetTimeout  
 이 클래스는 명명 된 파이프를 사용할 수 있을 때까지 대기 하는 시간 (밀리초)의 시간을 설정 하려면이 메서드를 호출 합니다.  
  
```
void SetTimeout(DWORD dwTimeout);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwTimeout`  
 시간 (밀리초)는이 클래스는 명명 된 파이프를 사용할 수 있을 때까지 대기 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../atl/reference/atl-classes.md)
