---
title: "디버깅 및 오류 보고 매크로 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- macros, error reporting
ms.assetid: 4da9b87f-ec5c-4a32-ab93-637780909b9d
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: f59c09b7eb1621094b170d3bed31b5891081194e
ms.lasthandoff: 03/31/2017

---
# <a name="debugging-and-error-reporting-macros"></a>디버깅 및 오류 보고 매크로
이러한 매크로 유용한 디버깅 및 추적 기능을 제공 합니다.  
  
|||  
|-|-|  
|[_ATL_DEBUG_INTERFACES](#_atl_debug_interfaces)|모든 인터페이스는 누수 출력 창에 기록 때 검색 된 `_Module.Term` 라고 합니다.|  
|[_ATL_DEBUG_QI](#_atl_debug_qi)|에 대 한 모든 호출을 기록 `QueryInterface` 출력 합니다.|  
|[ATLASSERT](#atlassert)|와 동일한 기능을 수행는 [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 매크로 C 런타임 라이브러리에서 찾을 수 있습니다.|  
|[ATLENSURE](#atlensure)|매개 변수 유효성 검사를 수행합니다. 호출 `AtlThrow` 필요한 경우|  
|[ATLTRACENOTIMPL](#atltracenotimpl)|지정된 된 함수를 구현 하는 덤프 장치에 메시지를 보냅니다.|  
|[ATLTRACE](#alttrace)|출력 장치 디버거 창 표시 플래그 및 수준에 따라 같은 경고를 보고 합니다. 이전 버전과 호환성을 위해 포함 됩니다.|  
|[ATLTRACE2](#atltrace2)|출력 장치 디버거 창 표시 플래그 및 수준에 따라 같은 경고를 보고 합니다.|  
  
##  <a name="_atl_debug_interfaces"></a>_ATL_DEBUG_INTERFACES  
 ATL 헤더 파일을 모두 추적에 포함 하기 전에이 매크로 정의할 `AddRef` 및 **릴리스** 출력 창에 사용자 구성 요소 인터페이스를 호출 합니다.  
  
```
#define _ATL_DEBUG_INTERFACES
```  
  
### <a name="remarks"></a>설명  
 추적 출력은 다음과 같이 표시 됩니다.  
  
 `ATL: QIThunk - 2008         AddRef  :   Object = 0x00d81ba0   Refcount = 1   CBug - IBug`  
  
 각 추적의 첫 번째 부분은 항상 `ATL: QIThunk`합니다. 다음 특정을 식별 하는 값에는 *썽크 인터페이스* 사용 하 고 있습니다. 인터페이스 썽크는 참조 횟수를 유지 관리 하 고 여기에 추적 기능을 제공 하는 데 사용 되는 개체입니다. 새 인터페이스 썽크를 호출할 때마다 만들어집니다 `QueryInterface` 요청에 대 한 제외 하 고는 **IUnknown** 인터페이스 (이 경우 동일한 썽크 값이 반환 될 때마다 COM의 식별 규칙을 준수 하도록).  
  
 표시 다음 `AddRef` 또는 **릴리스** 나타내는 메서드를 호출 했습니다. 그런 다음, 해당 인터페이스 참조 횟수 변경 된 개체를 식별 하는 값이 표시 됩니다. 추적 된 값이 고 **이** 개체의 포인터입니다.  
  
 추적 참조 개수는 해당 썽크 후의 참조 횟수가 `AddRef` 또는 **릴리스** 호출 되었습니다. 참고가 참조 카운트는 개체에 대 한 참조 수와 일치 하지 않을 수 있습니다. 각 썽크 완전히 COM의 참조 횟수 규칙을 따를 수 있도록 참조 횟수를 유지 관리 합니다.  
  
 정보 추적의 마지막 부분 개체와의 영향을 받지 인터페이스의 이름인는 `AddRef` 또는 **릴리스** 호출 합니다.  
  
 누수 서버 종료 될 때 검색 되는 모든 인터페이스 및 `_Module.Term` 됩니다 라고 다음과 같이 기록:  
  
 `ATL: QIThunk - 2005         LEAK    :   Object = 0x00d81ca0   Refcount = 1   MaxRefCount = 1   CBug - IBug`  
  
 정보 여기에 제공 된 이전 추적 문을에 제공 된 정보로 직접 매핑됩니다, 인터페이스 썽크의 전체 수명 동안 내내 참조 카운트를 검사할 수 있도록 합니다. 또한 해당 인터페이스 썽크에 최대 참조 수를 나타내는 값을 가져옵니다.  
  
> [!NOTE]
> `_ATL_DEBUG_INTERFACES`일반 정품 빌드에 사용할 수 있습니다.  
  
##  <a name="_atl_debug_qi"></a>_ATL_DEBUG_QI  
 에 대 한 모든 호출을 기록 `QueryInterface` 출력 합니다.  
  
```
#define _ATL_DEBUG_QI
```  
  
### <a name="remarks"></a>주의  
 호출 하는 경우 `QueryInterface` 실패, 출력 창 표시 됩니다.  
  
 *인터페이스 이름* - `failed`  
  
##  <a name="atlassert"></a>ATLASSERT  
 `ATLASSERT` 와 동일한 기능을 수행 하는 매크로 [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 매크로 C 런타임 라이브러리에서 찾을 수 있습니다.  
  
```
ATLASSERT(booleanExpression);
```  
  
### <a name="parameters"></a>매개 변수  
 `booleanExpression`  
 0이 아닌 값 또는 0으로 계산되는 식(포인터 포함)입니다.  
  
### <a name="remarks"></a>주의  
 디버그 빌드에서 `ATLASSERT` 평가 `booleanExpression` 결과 false 디버그 보고서를 생성 합니다.  

## <a name="requirements"></a>요구 사항  
 **헤더:** atldef.h  
    
##  <a name="atlensure"></a>ATLENSURE  
 이 매크로 함수에 전달 된 매개 변수 유효성 검사에 사용 됩니다.  
  
```
ATLENSURE(booleanExpression);
ATLENSURE_THROW(booleanExpression, hr);
```  
  
### <a name="parameters"></a>매개 변수  
 `booleanExpression`  
 테스트할 부울 식을 지정 합니다.  
  
 `hr`  
 반환할 오류 코드를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 이러한 매크로 감지 하 여 잘못 된 매개 변수 사용의 사용자에 게 알리는 메커니즘을 제공 합니다.  
  
 매크로 호출이 `ATLASSERT` 고 조건이 호출에 실패 하면 `AtlThrow`합니다.  
  
 에 **ATLENSURE** 경우 `AtlThrow` E_FAIL을 사용 하 여 호출 됩니다.  
  
 에 **ATLENSURE_THROW** 경우 `AtlThrow` 지정된 된 HRESULT를 사용 하 여 호출 됩니다.  
  
 차이 **ATLENSURE** 및 `ATLASSERT` 은 **ATLENSURE** 릴리스에서 예외 디버그 빌드 에서처럼도 빌드 throw 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities # 108](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_1.cpp)]  

## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  

##  <a name="atltracenotimpl"></a>ATLTRACENOTIMPL  
 ATL의 디버그 빌드에 문자열을 보냅니다 " `funcname` 구현 되지 않음" 덤프 장치 및 반환 **E_NOTIMPL**합니다.  
  
```
ATLTRACENOTIMPL(funcname);
```  
  
### <a name="parameters"></a>매개 변수  
 `funcname`  
 [in] 구현 되지 않은 함수 이름을 포함 하는 문자열입니다.  
  
### <a name="remarks"></a>설명  
 릴리스 빌드에서 반환 **E_NOTIMPL**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities # 127](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_2.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atltrace.h 

##  <a name="atltrace"></a>ATLTRACE
 출력 장치 디버거 창 표시 플래그 및 수준에 따라 같은 경고를 보고 합니다. 이전 버전과 호환성을 위해 포함 됩니다.  
  
```
ATLTRACE(exp);

ATLTRACE(  
    DWORD category,
    UINT  level,
    LPCSTR lpszFormat, ...);
```  
  
### <a name="parameters"></a>매개 변수  
 `exp`  
 [in] 문자열 및 Visual c + + 출력 창 또는 이러한 메시지를 트래핑 하는 모든 응용 프로그램에 보낼 변수입니다.  
  
 `category`  
 [in] 보고서를 메서드 또는 이벤트의 형식입니다. 범주 목록에 대 한 설명을 참조 하세요.  
  
 `level`  
 [in] 보고서에 대 한 추적 수준입니다. 자세한 내용은 설명 부분을 참조 하십시오.  
  
 `lpszFormat`  
 [in] 덤프 장치에 보내도록 서식이 지정 된 문자열입니다.  
  
### <a name="remarks"></a>주의  
 참조 [ATLTRACE2](#atltrace2) 에 대 한 설명은 **ATLTRACE**합니다. **ATLTRACE** 및 `ATLTRACE2` 동일한 동작 **ATLTRACE** 이전 버전과 호환성을 위해 포함 되었습니다.  
  
##  <a name="atltrace2"></a>ATLTRACE2  
 출력 장치 디버거 창 표시 플래그 및 수준에 따라 같은 경고를 보고 합니다.  
  
```
ATLTRACE2(exp);

ATLTRACE2(
    DWORD category,
    UINT level,
    LPCSTRlpszFormat,  ...);
```  
  
### <a name="parameters"></a>매개 변수  
 `exp`  
 [in] Visual c + + 출력 창 또는 이러한 메시지를 트래핑 하는 모든 응용 프로그램에 보내도록 문자열입니다.  
  
 `category`  
 [in] 보고서를 메서드 또는 이벤트의 형식입니다. 범주 목록에 대 한 설명을 참조 하세요.  
  
 `level`  
 [in] 보고서에 대 한 추적 수준입니다. 자세한 내용은 설명 부분을 참조 하십시오.  
  
 `lpszFormat`  
 [in] `printf`-덤프 장치에 보내도록 문자열을 만드는 데 사용할 형식 문자열 스타일입니다.  
  
### <a name="remarks"></a>설명  
 약식 형태는 `ATLTRACE2` 디버거에 문자열의 창 출력을 씁니다. 두 번째 형식의 `ATLTRACE2` 또한 디버거의 출력 창에 출력을 기록 하지만 ATL/MFC 추적 도구의 설정에 따라는 (참조 [ATLTraceTool 샘플](../../visual-cpp-samples.md)). 예를 들어, 설정한 경우 `level` 4 및 ATL/MFC 추적 도구를 수준 0 하지는 메시지가 나타납니다. *수준* 0, 1, 2, 3 또는 4 일 수 있습니다. 기본값 0으로 가장 심각한 문제만 보고합니다.  
  
 `category` 매개 변수 설정 하는 추적 플래그를 나열 합니다. 이러한 플래그를 보고 하려는 메서드의 유형에 해당 합니다. 다음 표에서 목록에 사용할 수는 올바른 추적 플래그는 `category` 매개 변수입니다.  
  
### <a name="atl-trace-flags"></a>ATL 추적 플래그  
  
|ATL 범주|설명|  
|------------------|-----------------|  
|`atlTraceGeneral`|모든 ATL 응용 프로그램에 대해 보고 합니다. 기본값입니다.|  
|`atlTraceCOM`|COM 메서드 보고 합니다.|  
|`atlTraceQI`|QueryInterface 호출에 대해 보고 합니다.|  
|`atlTraceRegistrar`|개체의 등록에 대해 보고 합니다.|  
|`atlTraceRefcount`|참조 횟수를 변경 하는 방법에 대 한 보고서입니다.|  
|`atlTraceWindowing`|Windows 방법;에 대 한 보고서 예를 들어 잘못 된 메시지 맵 ID를 보고합니다.|  
|`atlTraceControls`|제어;에 대 한 보고서 예를 들어 컨트롤이 나 해당 창을 소멸 될 때 보고 합니다.|  
|`atlTraceHosting`|보고서 호스팅 메시지; 예를 들어 클라이언트는 컨테이너에 활성화 될 때 보고 합니다.|  
|`atlTraceDBClient`|OLE DB 소비자 템플릿;에 대 한 보고서 예를 들어 때 GetData 실패에 대 한 호출, 출력 HRESULT를 포함할 수 있습니다.|  
|`atlTraceDBProvider`|OLE DB 공급자 템플릿;에 대 한 보고서 예를 들어 열 생성에 실패 하는 경우를 보고 합니다.|  
|`atlTraceSnapin`|MMC 스냅인 응용 프로그램에 대 한 보고서입니다.|  
|`atlTraceNotImpl`|보고서는 지정 된 함수가 구현 되지 않았습니다.|  
|**atlTraceAllocation**|Atldbgmem.h에서 도구 디버깅 메모리에 의해 인쇄 되는 메시지를 보고 합니다.|  
  
### <a name="mfc-trace-flags"></a>MFC 추적 플래그  
  
|MFC 범주|설명|  
|------------------|-----------------|  
|**traceAppMsg**|일반 용도, MFC 메시지입니다. 항상 것이 좋습니다.|  
|**traceDumpContext**|메시지를 [CDumpContext](../../mfc/reference/cdumpcontext-class.md)합니다.|  
|**traceWinMsg**|MFC의 메시지 처리 코드에서에서 메시지입니다.|  
|**traceMemory**|MFC의 메모리 관리 코드에서 메시지입니다.|  
|**traceCmdRouting**|MFC의 Windows에서 메시지 라우팅 코드를 명령입니다.|  
|**traceHtml**|MFC의 DHTML 대화 지원 웹 사이트에서 메시지입니다.|  
|**traceSocket**|MFC의 소켓 지원 웹 사이트에서 메시지입니다.|  
|**traceOle**|MFC의 OLE 지원 웹 사이트에서 메시지입니다.|  
|**traceDatabase**|MFC 데이터베이스 지원 웹 사이트에서 메시지입니다.|  
|**traceInternet**|MFC의 인터넷에서 메시지를 지원 합니다.|  
  
 사용자 지정 추적 범주를 선언 하려면의 전역 인스턴스를 선언에서 `CTraceCategory` 클래스를 다음과 같이 합니다.  
  
 [!code-cpp[NVC_ATL_Utilities # 109](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_3.cpp)]  
  
 범주 이름 `MY_CATEGORY` 이 예제는 이름을 지정 하는 `category` 매개 변수입니다. 첫 번째 매개 변수는 ATL/MFC 추적 도구에 표시 되는 범주 이름입니다. 두 번째 매개 변수는 기본 추적 수준입니다. 이 매개 변수는 선택적 이며 기본 추적 수준은 0입니다.  
  
 사용 하려면 사용자 정의 범주:  
  
 [!code-cpp[NVC_ATL_Utilities # 110](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_4.cpp)]  
  
 추적 메시지를 필터링 하려면를 지정 하려면 이러한 매크로 대 한 정의 하기 전에 Stdafx.h에 삽입 된 `#include <atlbase.h>` 문.  
  
 또는의 전처리기 지시문에서 필터를 설정할 수는 **속성 페이지** 대화 상자. 클릭는 **전처리기** 탭 한 다음에 전역 삽입는 **전처리기 정의** 편집 상자입니다.  
  
 기본 정의 포함 하는 Atlbase.h는 `ATLTRACE2` 매크로 및 이러한 정의 atlbase.h 처리 하기 전에 이러한 기호를 정의 하지 않은 경우.  
  
 릴리스 빌드에서 `ATLTRACE2` 컴파일함으로써 `(void) 0`합니다.  
  
 `ATLTRACE2`포맷 후 1, 024 개 이하의 자로 덤프 장치에 전송 하는 데 사용할 문자열의 내용을 제한 합니다.  
  
 **ATLTRACE** 및 `ATLTRACE2` 동일한 동작 **ATLTRACE** 이전 버전과 호환성을 위해 포함 되었습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities # 111](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_5.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [매크로](../../atl/reference/atl-macros.md)   
 [디버깅 및 오류 보고 전역 함수](../../atl/reference/debugging-and-error-reporting-global-functions.md)

