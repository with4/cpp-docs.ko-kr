---
title: CDumpContext 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDumpContext
- AFX/CDumpContext
- AFX/CDumpContext::CDumpContext
- AFX/CDumpContext::DumpAsHex
- AFX/CDumpContext::Flush
- AFX/CDumpContext::GetDepth
- AFX/CDumpContext::HexDump
- AFX/CDumpContext::SetDepth
dev_langs:
- C++
helpviewer_keywords:
- CDumpContext [MFC], CDumpContext
- CDumpContext [MFC], DumpAsHex
- CDumpContext [MFC], Flush
- CDumpContext [MFC], GetDepth
- CDumpContext [MFC], HexDump
- CDumpContext [MFC], SetDepth
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7acd7e94dbb45439a1812f8572ef442e43f9dab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367395"
---
# <a name="cdumpcontext-class"></a>CDumpContext 클래스
사용자가 읽을 수 있는 텍스트 형식으로 스트림 지향 진단 출력을 지원합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDumpContext  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDumpContext::CDumpContext](#cdumpcontext)|`CDumpContext` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDumpContext::DumpAsHex](#dumpashex)|16 진수 형식으로 표시 된 항목으로 덤프합니다.|  
|[CDumpContext::Flush](#flush)|덤프 컨텍스트 버퍼의 모든 데이터를 지웁니다.|  
|[CDumpContext::GetDepth](#getdepth)|해당 하는 덤프의 깊이 정수를 가져옵니다.|  
|[CDumpContext::HexDump](#hexdump)|16 진수 형식의 배열에 포함 된 바이트를 덤프 합니다.|  
|[CDumpContext::SetDepth](#setdepth)|덤프의 깊이 가져오거나 설정 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CDumpContext::operator &lt;&lt;](#operator_lt_lt)|에 덤프 컨텍스트 변수 및 개체를 삽입합니다.|  
  
## <a name="remarks"></a>설명  
 `CDumpContext` 기본 클래스는 없습니다.  
  
 사용할 수 있습니다 [afxDump](diagnostic-services.md#afxdump)는 미리 선언 된 `CDumpContext` 대부분의 프로그램 덤프에 대 한 개체입니다. `afxDump` 개체는 Microsoft Foundation Class 라이브러리의 디버그 버전에만 사용할 수 있습니다.  
  
 메모리의 여러 [진단 서비스](../../mfc/reference/diagnostic-services.md) 사용 `afxDump` 출력에 대 한 합니다.  
  
 Windows 환경에서 미리 정의 된 출력에서 `afxDump` 개념적으로 유사한 개체는 `cerr` 스트림, Windows 함수를 통해 디버거에 라우팅 된다고 **OutputDebugString**합니다.  
  
 `CDumpContext` 클래스에 오버 로드 된 삽입 ( **<<**)에 대 한 연산자 `CObject` 개체의 데이터를 덤프 하는 포인터입니다. 파생된 된 개체에 대 한 사용자 지정 덤프 형식 해야 하는 경우 재정의 [CObject::Dump](../../mfc/reference/cobject-class.md#dump)합니다. 대부분 Microsoft Foundation 클래스에서 재정의 된 구현 `Dump` 멤버 함수입니다.  
  
 클래스에서 파생 되지 않은 `CObject`와 같은 `CString`, `CTime`, 및 `CTimeSpan`, 자신의 오버 로드 된가 `CDumpContext` 삽입 연산자와 같은 자주 사용 하는 do 구조체로 **CFileStatus**, `CPoint`, 및 `CRect`합니다.  
  
 사용 하는 경우는 [IMPLEMENT_DYNAMIC](../../mfc/reference/run-time-object-model-services.md#implement_dynamic) 또는 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) 매크로 클래스의 구현에서 `CObject::Dump` 의 이름을 인쇄 프로그램 `CObject`-클래스를 파생 합니다. 그렇지 않은 경우 인쇄 됩니다 `CObject`합니다.  
  
 `CDumpContext` 클래스 라이브러리의 디버그와 릴리스 버전을 사용할 수는 있지만 `Dump` 멤버 함수는 디버그 버전 에서만에서 정의 됩니다. 사용 하 여 **#ifdef _DEBUG**  /  `#endif` 을 사용자 지정을 비롯 하 여 진단 코드 문을 `Dump` 멤버 함수입니다.  
  
 직접 만들기 전에 `CDumpContext` 개체를 만들어야 합니다는 `CFile` 덤프 대상으로 사용 되는 개체입니다.  
  
 대 한 자세한 내용은 `CDumpContext`, 참조 [MFC 응용 프로그램 디버깅](/visualstudio/debugger/mfc-debugging-techniques)합니다.  
  
 **#define _DEBUG**  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CDumpContext`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
##  <a name="cdumpcontext"></a>  CDumpContext::CDumpContext  
 클래스의 개체를 생성 `CDumpContext`합니다.  
  
```  
CDumpContext(CFile* pFile = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFile`  
 에 대 한 포인터는 `CFile` 덤프 대상인 개체입니다.  
  
### <a name="remarks"></a>설명  
 `afxDump` 개체는 자동으로 만들어집니다.  
  
 내부에 쓰지 않아도 `CFile` 덤프 컨텍스트 활성 상태가 아니면 동안 덤프를 방해할 수 있습니다. Windows 환경에서 출력 하 고 디버거 Windows 함수를 통해 라우팅됩니다 **OutputDebugString**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities#12](../../mfc/codesnippet/cpp/cdumpcontext-class_1.cpp)]  
  
##  <a name="dumpashex"></a>  CDumpContext::DumpAsHex  
 16 진수 숫자로 지정된 된 형식으로 덤프 합니다.  
  
```  
CDumpContext& DumpAsHex(BYTE b);  
CDumpContext& DumpAsHex(DWORD dw);  
CDumpContext& DumpAsHex(int n);  
CDumpContext& DumpAsHex(LONG l);  
CDumpContext& DumpAsHex(LONGLONG n);  
CDumpContext& DumpAsHex(UINT u);  
CDumpContext& DumpAsHex(ULONGLONG n);  
CDumpContext& DumpAsHex(WORD w);
```  
  
### <a name="return-value"></a>반환 값  
 `CDumpContext` 개체에 대한 참조입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 16 진수 숫자로 지정 된 형식의 항목을 덤프를 호출 합니다. 배열 덤프 하려면 호출 [CDumpContext::HexDump](#hexdump)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities#13](../../mfc/codesnippet/cpp/cdumpcontext-class_2.cpp)]  
  
##  <a name="flush"></a>  CDumpContext::Flush  
 덤프 컨텍스트에 연결 된 파일에 기록 하는 버퍼에 남아 있는 모든 데이터를 수행 하도록 합니다.  
  
```  
void Flush();
```  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities#14](../../mfc/codesnippet/cpp/cdumpcontext-class_3.cpp)]  
  
##  <a name="getdepth"></a>  CDumpContext::GetDepth  
 프로세스에서 전체 또는 단순 덤프 인지 확인 합니다.  
  
```  
int GetDepth() const;  
```  
  
### <a name="return-value"></a>반환 값  
 설정한 대로 덤프의 깊이 `SetDepth`합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [SetDepth](#setdepth)합니다.  
  
##  <a name="hexdump"></a>  CDumpContext::HexDump  
 덤프를 16 진수로 서식이 지정 된 바이트 배열입니다.  
  
```  
void HexDump(
    LPCTSTR lpszLine,  
    BYTE* pby,  
    int nBytes,  
    int nWidth);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszLine*  
 새 줄의 시작 부분에 출력 하는 문자열입니다.  
  
 *pby*  
 바이트 덤프를 포함 하는 버퍼에 대 한 포인터입니다.  
  
 `nBytes`  
 덤프 하는 바이트 수입니다.  
  
 `nWidth`  
 최대 바이트 수입니다 (하지 출력 줄 너비) 줄당 덤프.  
  
### <a name="remarks"></a>설명  
 16 진수를 나타내는 단일, 특정 항목 형식을 덤프 하려면 호출 [CDumpContext::DumpAsHex](#dumpashex)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities#15](../../mfc/codesnippet/cpp/cdumpcontext-class_4.cpp)]  
  
##  <a name="operator_lt_lt"></a>  CDumpContext::operator &lt;&lt;  
 덤프 컨텍스트를 지정된 된 데이터를 출력합니다.  
  
```  
CDumpContext& operator<<(const CObject* pOb);  
CDumpContext& operator<<(const CObject& ob);  
CDumpContext& operator<<(LPCTSTR lpsz);  
CDumpContext& operator<<(const void* lp);  
CDumpContext& operator<<(BYTE by);  
CDumpContext& operator<<(WORD w);  
CDumpContext& operator<<(DWORD dw);  
CDumpContext& operator<<(int n);  
CDumpContext& operator<<(double d);  
CDumpContext& operator<<(float f);  
CDumpContext& operator<<(LONG l);  
CDumpContext& operator<<(UINT u);  
CDumpContext& operator<<(LPCWSTR lpsz);  
CDumpContext& operator<<(LPCSTR lpsz);  
CDumpContext& operator<<(LONGLONG n);  
CDumpContext& operator<<(ULONGLONG n);  
CDumpContext& operator<<(HWND h);  
CDumpContext& operator<<(HDC h);  
CDumpContext& operator<<(HMENU h);  
CDumpContext& operator<<(HACCEL h);  
CDumpContext& operator<<(HFONT h);
```  
  
### <a name="return-value"></a>반환 값  
 A `CDumpContext` 참조 합니다. 반환 값을 사용 하 여 소스 코드의 한 줄에 여러 개의 삽입을 작성할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 삽입 연산자는 오버 로드 `CObject` 와 대부분의 기본 형식 뿐만 아니라 포인터입니다. 문자열 내용의; 덤프에 문자 결과에 대 한 포인터 에 대 한 포인터 `void` 만 주소의 16 진수 덤프 합니다. A **LONGLONG** 64 비트 부호 있는 정수; 덤프 A **ULONGLONG** 64 비트 부호 없는 정수의 덤프 합니다.  
  
 사용 하는 경우는 `IMPLEMENT_DYNAMIC` 또는 `IMPLEMENT_SERIAL` 클래스에 다음 삽입 연산자의 구현에서 매크로 통해 `CObject::Dump`의 이름을 인쇄 프로그램 `CObject`-클래스를 파생 합니다. 그렇지 않은 경우 인쇄 됩니다 `CObject`합니다. 재정의 하는 경우는 `Dump` 함수 클래스에 다음의 16 진수 덤프 하는 대신 개체의 내용의 좀 더 의미 있는 출력을 제공할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities#17](../../mfc/codesnippet/cpp/cdumpcontext-class_5.cpp)]  
  
##  <a name="setdepth"></a>  CDumpContext::SetDepth  
 덤프에 대 한 깊이 가져오거나 설정 합니다.  
  
```  
void SetDepth(int nNewDepth);
```  
  
### <a name="parameters"></a>매개 변수  
 *nNewDepth*  
 새 깊이 값입니다.  
  
### <a name="remarks"></a>설명  
 기본 형식 또는 단순을 덤프 하는 경우 `CObject` 에 다른 개체에 대 한 포인터 없이 포함 된 값이 0은 충분 합니다. 모든 개체가 된 상태 였던 전체 덤프를 지정 하는 0 보다 큰 값이 재귀적으로 덤프 합니다. 예를 들어 컬렉션의 전체 덤프는 컬렉션의 모든 요소를 덤프 합니다. 파생된 클래스에서 다른 특정 깊이 값을 사용할 수 있습니다.  
  
> [!NOTE]
>  순환 참조는 전체 덤프에서 찾을 수 없습니다 및 무한 루프가 발생할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities#16](../../mfc/codesnippet/cpp/cdumpcontext-class_6.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFile 클래스](../../mfc/reference/cfile-class.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)
