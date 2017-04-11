---
title: "진단 서비스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- diagnosis, diagnostic services
- diagnostic macros, list of general MFC
- services, diagnostic
- MFC, diagnostic services
- general diagnostic functions and variables
- diagnostics, diagnostic functions and variables
- diagnostics, list of general MFC
- diagnosis, diagnostic functions and variables
- diagnosis, list of general MFC
- general diagnostic macros in MFC
- diagnostic macros
- diagnostic services
- object diagnostic functions in MFC
- diagnostics, diagnostic services
- diagnostic functions and variables
ms.assetid: 8d78454f-9fae-49c2-88c9-d3fabd5393e8
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: 0e83114e2e6f062b9cb2164cf71bb25792304de0
ms.lasthandoff: 04/04/2017

---
# <a name="diagnostic-services"></a>진단 서비스
MFC 라이브러리는 프로그램을 더 쉽게 디버그할 수 있는 많은 진단 서비스를 제공합니다. 이러한 진단 서비스에는 매크로 및 전역 함수가 포함되며, 이러한 함수를 통해 프로그램의 메모리 할당을 추적하고 런타임 중 개체의 내용을 덤프하고 런타임 중 디버깅 메시지를 인쇄할 수 있습니다. 진단 서비스의 매크로 및 전역 함수는 다음과 같은 범주로 그룹화됩니다.  
  
-   일반 진단 매크로  
  
-   일반 진단 함수 및 변수  
  
-   개체 진단 함수  
  
 이러한 매크로 함수에 사용할 수 있는 모든 클래스에서 파생 된 `CObject` 디버그 및 릴리스 버전의 MFC 합니다. 그러나를 제외한 모든 `DEBUG_NEW` 및 **확인** 릴리스 버전에서 아무 작업도 수행 합니다.  
  
 디버그 라이브러리에서, 할당된 모든 메모리 블록은 일련의 "보호 바이트"와 함께 묶입니다. 이러한 바이트가 잘못된 메모리 쓰기로 인해 교란되면 진단 루틴이 문제를 보고할 수 있습니다. 다음 줄을 포함하는 경우  
  
 [!code-cpp[NVC_MFCCObjectSample # 14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 구현 파일에서 모두에 대 한 호출이 **새** 메모리 할당이 발생 파일 이름과 줄 번호를 저장 합니다. 함수 [cmemorystate:: Dumpallobjectssince](cmemorystate-structure.md#dumpallobjectssince) 메모리 누수를 식별할 수 있도록이 추가 정보를 표시 됩니다. 클래스에도 참조 [CDumpContext](../../mfc/reference/cdumpcontext-class.md) 진단 출력에 대 한 자세한 내용은 합니다.  
  
 또한 C 런타임 라이브러리는 응용 프로그램을 디버그하는 데 사용할 수 있는 진단 함수 집합도 지원합니다. 자세한 내용은 참조 [루틴 디버깅](../../c-runtime-library/debug-routines.md) 런타임 라이브러리 참조에서.  
  
### <a name="mfc-general-diagnostic-macros"></a>MFC 일반 진단 매크로  
  
|||  
|-|-|  
|[어설션](#assert)|메시지를 출력 한 후 프로그램을 중단 하는 경우 지정 된 식이 **FALSE** 라이브러리의 디버그 버전에 있습니다.|  
|[ASSERT_KINDOF](#assert_kindof)|개체가 지정된 클래스의 개체인지 아니면 지정된 클래스에서 파생된 클래스의 개체인지 테스트합니다.|  
|[ASSERT_VALID](#assert_valid)|호출 하 여 개체의 내부 유효성을 테스트 해당 `AssertValid` 멤버 함수;에서 일반적으로 재정의 `CObject`합니다.|
|[DEBUG_NEW](#debug_new)|메모리 누수를 쉽게 찾을 수 있도록 디버그 모드에서 모든 개체 할당에 파일 이름과 줄 번호를 제공합니다.|  
|[DEBUG_ONLY](#debug_only)|비슷한 **ASSERT** , 식의 값을 테스트 하지 않지만 디버그 모드에서 실행 해야 하는 코드에 유용 합니다.|  
|[확인 및 ENSURE_VALID](#ensure)|데이터 정확성의 유효성을 검사 하려면 사용 합니다.|
|[THIS_FILE](#this_file)|컴파일되는 파일의 이름으로 확장 됩니다.|
|[TRACE](#trace)|제공 `printf`-라이브러리의 디버그 버전에서 기능을 선택 합니다.|  
|[확인](#verify)|비슷한 **ASSERT** 있지만 디버그 버전에 라이브러리의 릴리스 버전의 식을 계산 합니다.|  
  
### <a name="mfc-general-diagnostic-variables-and-functions"></a>MFC 일반 진단 변수 및 함수  
  
|||  
|-|-|  
|[afxDump](#afxdump)|보내는 전역 변수 [CDumpContext](../../mfc/reference/cdumpcontext-class.md) 를 디버거 출력 창 또는 디버그 터미널 정보입니다.|  
|[afxMemDF](#afxmemdf)|디버깅 메모리 할당자의 동작을 제어하는 전역 변수입니다.|  
|[AfxCheckError](#afxcheckerror)|테스트는 통과 하는 데 사용 되는 전역 변수 **SCODE** 에 오류가 발생 한,이 경우 적절 한 오류를 throw 합니다.|  
|[AfxCheckMemory](#afxcheckmemory)|현재 할당된 모든 메모리의 무결성을 검사합니다.|  
|[AfxDebugBreak](#afxdebugbreak)|실행 하면 됩니다.|
|[AfxDump](#cdumpcontext_in_mfc)|디버거 내에 있는 동안 호출되는 경우 디버그하는 동안 개체의 상태를 덤프합니다.|  
|[AfxDump](#afxdump)|디버깅 하는 동안 개체의 상태를 덤프 하는 내부 함수입니다.|
|[AfxDumpStack](#afxdumpstack)|현재 스택의 이미지를 생성합니다. 이 함수는 항상 정적으로 연결됩니다.|  
|[AfxEnableMemoryLeakDump](#afxenablememoryleakdump)|메모리 누수 덤프를 사용하도록 설정합니다.|  
|[AfxEnableMemoryTracking](#afxenablememorytracking)|메모리 추적을 켜고 끕니다.|  
|[AfxIsMemoryBlock](#afxismemoryblock)|메모리 블록이 제대로 할당되었는지 확인합니다.|  
|[AfxIsValidAddress](#afxisvalidaddress)|메모리 주소 범위가 프로그램의 경계 내에 있는지 확인합니다.|  
|[AfxIsValidString](#afxisvalidstring)|문자열에 대한 포인터가 유효한지 여부를 결정합니다.|  
|[AfxSetAllocHook](#afxsetallochook)|각 메모리 할당에서 함수 호출을 사용하도록 설정합니다.|  
  
### <a name="mfc-object-diagnostic-functions"></a>MFC 개체 진단 함수  
  
|||  
|-|-|  
|[AfxDoForAllClasses](#afxdoforallclasses)|지정 된 기능을 수행 하 여 모든 `CObject`-런타임 형식 검사를 지 원하는 클래스를 파생 합니다.|  
|[AfxDoForAllObjects](#afxdoforallobjects)|지정 된 기능을 수행 하 여 모든 `CObject`-파생 개체와 함께 할당 된 **새**합니다.|  

### <a name="mfc-compilation-macros"></a>MFC 컴파일 매크로
|||
|-|-|
|[_AFX_SECURE_NO_WARNINGS](#afx_secure_no_warnings)|사용 되지 않는 MFC 함수 사용에 대 한 컴파일러 경고를 표시 하지 않습니다.|  


## <a name="afx_secure_no_warnings"></a>_AFX_SECURE_NO_WARNINGS
사용 되지 않는 MFC 함수 사용에 대 한 컴파일러 경고를 표시 하지 않습니다.  
   
### <a name="syntax"></a>구문   
```  
_AFX_SECURE_NO_WARNINGS  
```     
### <a name="example"></a>예제  
 이 코드 샘플 _AFX_SECURE_NO_WARNINGS 정의 되지 않은 경우 컴파일러에서 경고로 인해 합니다.  
  
 ```cpp
// define this before including any afx files in stdafx.h
#define _AFX_SECURE_NO_WARNINGS
```
```cpp
CRichEditCtrl* pRichEdit = new CRichEditCtrl;
pRichEdit->Create(WS_CHILD|WS_VISIBLE|WS_BORDER|ES_MULTILINE,
   CRect(10,10,100,200), pParentWnd, 1);
char sz[256];
pRichEdit->GetSelText(sz);
```

## <a name="afxdebugbreak"></a>AfxDebugBreak
중단 하려면이 함수를 호출 (위치에 대 한 호출에서 `AfxDebugBreak`) MFC 응용 프로그램의 디버그 버전을 실행 합니다.  

### <a name="syntax"></a>구문    
```
void AfxDebugBreak( );    
```  
   
### <a name="remarks"></a>설명  
 `AfxDebugBreak`MFC 응용 프로그램의 릴리스 버전에서는 아무 효과가 제거 해야 합니다. 이 함수는 MFC 응용 프로그램에만 사용 해야 합니다. Win32 API 버전을 사용 하 여 **DebugBreak**, 비 MFC 응용 프로그램에서 중단이 발생할 수 있습니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxver_.h   

##  <a name="assert"></a>어설션
 해당 인수를 평가합니다.  
  
```   
ASSERT(booleanExpression)   
```  
  
### <a name="parameters"></a>매개 변수  
 `booleanExpression`  
 0이 아닌 값 또는 0으로 계산 되는 식 (포인터 값 포함)를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 결과가 0 인 경우 매크로가 진단 메시지를 출력 하 고 프로그램을 중단 합니다. 0이 아니면 조건이 이면 아무 작업도 수행 하지 않습니다.  
  
 진단 메시지의 형식은 다음과 같습니다.  
  
 `assertion failed in file <name> in line <num>`  
  
 여기서 *이름* 소스 파일의 이름 및 *num* 는 소스 파일에서 실패 한 어설션의 줄 번호입니다.  
  
 MFC의 릴리스 버전에서 **ASSERT** 는 식을 평가 하지 않습니다 및 따라서 프로그램은 중단 되지 것입니다. 사용 하 여 환경에 관계 없이 식은 반드시 평가 되어야 하는 경우는 **확인** 대신에 매크로 **ASSERT**합니다.  
  
> [!NOTE]
>  이 기능은 MFC의 디버그 버전 에서만 사용할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities # 44](../../mfc/codesnippet/cpp/diagnostic-services_2.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="assert_kindof"></a>ASSERT_KINDOF  
 이 매크로 가리키는 개체는 지정된 된 클래스의 개체 또는 지정된 된 클래스에서 파생 된 클래스의 개체를 어설션 합니다.  
  
```   
ASSERT_KINDOF(classname, pobject)  
```  
  
### <a name="parameters"></a>매개 변수  
 *응용 프로그램 이름*  
 이름을 `CObject`-클래스를 파생 합니다.  
  
 *pobject*  
 클래스 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 *pobject* 매개 변수 개체에 대 한 포인터 이어야 하며 수 **const**합니다. 개체를 가리키는 및 클래스를 지원 해야 합니다 `CObject` 런타임 클래스 정보입니다. 예를 들어 되도록 `pDocument` 의 개체에 대 한 포인터는 `CMyDoc` 클래스 또는 해당 파생 항목 중 하나를 코딩할 수 있습니다.  
  
 [!code-cpp[NVC_MFCDocView # 194](../../mfc/codesnippet/cpp/diagnostic-services_3.cpp)]  
  
 사용 하는 `ASSERT_KINDOF` 매크로 정확 하 게 코딩와 동일 합니다.  
  
 [!code-cpp[NVC_MFCDocView # 195](../../mfc/codesnippet/cpp/diagnostic-services_4.cpp)]  
  
 으로 선언 된 클래스에 대해서만 작동 하는이 함수는 [DECLARE_DYNAMIC] (#declare_dynamic 실행-시간-개체-모델-services.md 또는 [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) 매크로입니다.  
  
> [!NOTE]
>  이 기능은 MFC의 디버그 버전 에서만 사용할 수 있습니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="assert_valid"></a>ASSERT_VALID  
 사용 하 여 개체의 내부 상태의 유효성을 검사 하는 방법에 대 한 가정을 테스트할 수 있습니다.  
  
```   
ASSERT_VALID(pObject)   
```  
  
### <a name="parameters"></a>매개 변수  
 `pObject`  
 파생 된 클래스의 개체를 지정 `CObject` 의 재정의 버전을 보유 하는 `AssertValid` 멤버 함수입니다.  
  
### <a name="remarks"></a>설명  
 `ASSERT_VALID`호출 된 `AssertValid` 개체의 멤버 함수는 인수로 전달 합니다.  
  
 MFC의 릴리스 버전에서 `ASSERT_VALID` 는 아무 작업도 수행 합니다. 디버그 버전에서 확인 하 고 포인터에 대 한 검사 **NULL**, 호출 개체의 고유 `AssertValid` 멤버 함수입니다. 경고 메시지와 같은 방식으로 표시 됩니다 테스트 실패에 이러한 경우 [ASSERT](#assert)합니다.  
  
> [!NOTE]
>  이 기능은 MFC의 디버그 버전 에서만 사용할 수 있습니다.  
  
 자세한 내용 및 예제에 대 한 참조 [MFC 응용 프로그램 디버깅](/visualstudio/debugger/mfc-debugging-techniques)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCObjectSample # 19](../../mfc/codesnippet/cpp/diagnostic-services_5.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h

##  <a name="debug_new"></a>DEBUG_NEW  
 메모리 누수를 찾는 데 유용 합니다.  
  
```   
#define  new DEBUG_NEW   
```  
  
### <a name="remarks"></a>주의  
 사용할 수 있습니다 `DEBUG_NEW` 일반적으로 사용 하는 프로그램의 모든 위치에서 **새** 힙 저장소를 할당 하는 연산자입니다.  
  
 디버그 모드에서 (때는 **_DEBUG** 기호가 정의), `DEBUG_NEW` 할당 된 각 개체에 대 한 파일 이름과 줄 번호는 추적 합니다. 그런 다음 사용 하는 경우는 [cmemorystate:: Dumpallobjectssince](cmemorystate-structure.md#dumpallobjectssince) 멤버 함수를 사용 하 여 할당 된 각 개체 `DEBUG_NEW` 할당 된 파일 이름과 줄 번호와 함께 표시 됩니다.  
  
 사용 하도록 `DEBUG_NEW`, 소스 파일에 다음 지시문을 삽입 합니다.  
  
 [!code-cpp[NVC_MFCCObjectSample # 14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 전처리기는 삽입이 지시문을 삽입 하면 `DEBUG_NEW` 사용 하는 아무 곳에 나 **새**, MFC 나머지 작업을 수행 하 고 있습니다. 프로그램의 릴리스 버전을 컴파일할 때 `DEBUG_NEW` 확인 되는 간단한 **새** 작업과 파일 이름과 줄 번호 정보가 생성 되지 않습니다.  
  
> [!NOTE]
>  배치 하는 데 필요한 이전 버전의 MFC (4.1 및 이전 버전)는 `#define` 문을 호출 하는 모든 문은 한 후의 `IMPLEMENT_DYNCREATE` 또는 `IMPLEMENT_SERIAL` 매크로입니다. 이 작업이 필요 없습니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h

##  <a name="debug_only"></a>DEBUG_ONLY  
 디버그 모드에서 (때는 **_DEBUG** 기호가 정의), `DEBUG_ONLY` 해당 인수를 계산 합니다.  
  
```   
DEBUG_ONLY(expression)   
```  
  
### <a name="remarks"></a>설명  
 릴리스 빌드에서 **DEBUG_ONLY** 해당 인수를 평가 하지 않습니다. 디버그 빌드에서만에서 실행 해야 하는 코드가 있는 경우에 유용 합니다.  
  
 `DEBUG_ONLY` 매크로 주변에 해당 하는 *식* 와 **#ifdef _DEBUG** 및 `#endif`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities # 32](../../mfc/codesnippet/cpp/diagnostic-services_6.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h

 ### <a name="ensure"></a>확인 및 ENSURE_VALID
데이터 정확성의 유효성을 검사 하려면 사용 합니다.  
   
### <a name="syntax"></a>구문    
```
ENSURE(  booleanExpression )  
ENSURE_VALID( booleanExpression  )  
```
### <a name="parameters"></a>매개 변수  
 `booleanExpression`  
 테스트할 부울 식을 지정 합니다.  
   
### <a name="remarks"></a>주의  
 이러한 매크로의 목적은 매개 변수의 유효성 검사를 개선 하기 위해입니다. 매크로 코드에 잘못 된 매개 변수 추가 처리를 방지 합니다. 달리는 **ASSERT** 매크로 **확인** 매크로 어설션을 생성 하는 것 외에도 예외를 throw 합니다.  
  
 매크로는 프로젝트 구성에 따라 두 가지 방법으로 작동합니다. 매크로 호출이 **ASSERT** 어설션이 실패 하는 경우 다음 예외를 throw 합니다. 디버그 구성에 따라서 (즉, **_DEBUG** 정의)는 어설션 및 릴리스 구성에 있는 동안 예외 매크로 생성, 매크로 예외를 생성 (**ASSERT** 릴리스 구성에 대 한 식을 평가 하지 않습니다).  
  
 매크로 **ENSURE_ARG** 처럼 동작은 **확인** 매크로입니다.  
  
 **ENSURE_VALID** 호출의 `ASSERT_VALID` 매크로 (디버그 빌드에서만에서 효과가). 또한 **ENSURE_VALID** 포인터가 NULL 이면 예외가 발생 합니다. NULL 테스트 모두 디버그 및 릴리스 구성에서 수행 됩니다.  
  
 경고 메시지와 같은 방식으로 표시 됩니다 테스트 실패에 이러한 경우 **ASSERT**합니다. 매크로 필요에 따라 잘못 된 인수 예외를 throw 합니다.  
### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
   
### <a name="see-also"></a>참고 항목  
 [매크로 및 전역](mfc-macros-and-globals.md)   
 [확인](#verify)   
 [ATLENSURE](#altensure)

## <a name="this_file"></a>THIS_FILE
컴파일되는 파일의 이름으로 확장 됩니다.  
   
### <a name="syntax"></a>구문    
```
THIS_FILE    
```  
   
### <a name="remarks"></a>설명  
 정보는 사용 되는 **ASSERT** 및 **확인** 매크로입니다. 응용 프로그램 마법사 및 코드 마법사 작성 한 소스 코드 파일에 매크로 배치 합니다.  
   
### <a name="example"></a>예제  
```cpp
#ifdef _DEBUG
#undef THIS_FILE
static char THIS_FILE[] = __FILE__;
#endif

// __FILE__ is one of the six predefined ANSI C macros that the 
// compiler recognizes. 
```
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
   
### <a name="see-also"></a>참고 항목  
 [매크로 및 전역](mfc-macros-and-globals.md)   
 [어설션](#assert)   
 [확인](#verify)


##  <a name="trace"></a>추적  
 현재 응용 프로그램의 디버거를 지정된 된 문자열을 보냅니다.  
  
```   
TRACE(exp)  
TRACE(DWORD  category,  UINT  level, LPCSTR lpszFormat, ...)   
```  
  
### <a name="remarks"></a>설명  
 참조 [ATLTRACE2](http://msdn.microsoft.com/library/467ff555-e7a5-4f94-bdd9-50ee27ab9986) 에 대 한 설명은 **추적**합니다. **추적** 및 `ATLTRACE2` 동일 하 게 동작 합니다.  
  
 MFC의 디버그 버전에서이 매크로 현재 응용 프로그램의 디버거를 지정된 된 문자열을 보냅니다. 릴리스 빌드에서이 매크로 (코드 없이 전혀 생성) nothing으로 컴파일합니다.  
  
 자세한 내용은 참조 [MFC 응용 프로그램 디버깅](/visualstudio/debugger/mfc-debugging-techniques)합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h

##  <a name="verify"></a>확인  
 MFC의 디버그 버전에서 해당 인수를 평가합니다.  
  
```   
VERIFY(booleanExpression)   
```  
  
### <a name="parameters"></a>매개 변수  
 `booleanExpression`  
 0이 아닌 값 또는 0으로 계산 되는 식 (포인터 값 포함)를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 결과가 0 인 경우 매크로가 진단 메시지를 출력 하 고 프로그램을 중단 합니다. 0이 아니면 조건이 이면 아무 작업도 수행 하지 않습니다.  
  
 진단 메시지의 형식은 다음과 같습니다.  
  
 `assertion failed in file <name> in line <num>`  
  
 여기서 *이름* 소스 파일의 이름 및 *num* 는 소스 파일에서 실패 한 어설션의 줄 번호입니다.  
  
 MFC의 릴리스 버전에서 **확인** expression을 계산 하지만 인쇄 않거나에 프로그램을 중단 합니다. 예를 들어 식이 함수 호출 이면는 전화 걸 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView # 198](../../mfc/codesnippet/cpp/diagnostic-services_7.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h

##  <a name="cdumpcontext_in_mfc"></a>afxDump (MFC의 CDumpContext)  
 응용 프로그램에서 기본 개체를 덤프 하는 기능을 제공 합니다.  
  
```   
CDumpContext  afxDump;   
```  
  
### <a name="remarks"></a>설명  
 `afxDump`미리 정의 된 [CDumpContext](../../mfc/reference/cdumpcontext-class.md) 보낼 수 있도록 개체 `CDumpContext` 정보 또는 디버그 터미널 디버거 출력 창에 있습니다. 일반적으로 제공 `afxDump` 매개 변수로 `CObject::Dump`합니다.  
  
 Windows NT 및 모든 버전의 Windows에서는 아래 `afxDump` 출력은 응용 프로그램을 디버깅할 때 Visual c + + 디버그 출력 창에 전송 됩니다.  
  
 이 변수는 MFC의 디버그 버전에만 정의 됩니다. 대 한 자세한 내용은 `afxDump`, 참조 [MFC 응용 프로그램 디버깅](/visualstudio/debugger/mfc-debugging-techniques)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities # 23](../../mfc/codesnippet/cpp/diagnostic-services_8.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h


## <a name="afxdump"></a>AfxDump (내부)
MFC를 사용 하 여 디버깅 하는 동안 개체의 상태를 덤프 내부 함수입니다.  

### <a name="syntax"></a>구문    
```
void AfxDump(const CObject* pOb);   
```
### <a name="parameters"></a>매개 변수  
 `pOb`  
 파생 된 클래스의 개체에 대 한 포인터 `CObject`합니다.  
   
### <a name="remarks"></a>주의  
 **AfxDump** 개체의 호출 `Dump` 멤버 함수와 보냅니다에 의해 지정 된 위치에 대 한 정보는 `afxDump` 변수입니다. **AfxDump** MFC의 디버그 버전 에서만 사용할 수 있습니다.  
  
 프로그램 코드를 호출 해서는 안 **AfxDump**를 대신 호출 해야 하지만 `Dump` 적절 한 개체의 멤버 함수입니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
   
### <a name="see-also"></a>참고 항목  
 [CObject::Dump](cobject-class.md#dump)   



##  <a name="afxmemdf"></a>afxMemDF  
 이 변수를 액세스할 수는 디버거 또는 프로그램에서 할당 진단 튜닝할 수 있습니다.  
  
```   
int  afxMemDF;  
```  
  
### <a name="remarks"></a>설명  
 `afxMemDF`열거형에 지정 된 대로 다음 값을 가질 수 `afxMemDF`:  
  
- **allocMemDF** 디버깅 할당자 (디버그 라이브러리의 기본 설정)을 설정 합니다.  
  
- **delayFreeMemDF** 메모리 해제를 지연 합니다. 메모리 블록을 해제 하는 프로그램, 동안 할당자는 기본 운영 체제 메모리는 반환 하지 않습니다. 프로그램의 최대 메모리 내 스트레스를 정렬은 합니다.  
  
- **checkAlwaysMemDF** 호출 `AfxCheckMemory` 될 때마다 메모리를 할당 하거나 해제 합니다. 크게 메모리 할당 및 할당 취소 속도가 느려집니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities # 30](../../mfc/codesnippet/cpp/diagnostic-services_9.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h

##  <a name="afxcheckerror"></a>AfxCheckError  
 이 함수는 전달 된 테스트 **SCODE** 를 오류가 있는지 확인 하십시오.  
  
```   
void AFXAPI AfxCheckError(SCODE sc);
throw CMemoryException* 
throw COleException*  
```  
  
### <a name="remarks"></a>주의  
 오류가 있으면 함수는 예외가 throw 됩니다. 경우 전달 된 `SCODE` 은 **E_OUTOFMEMORY**, throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 호출 하 여 [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception)합니다. 그렇지 않으면 함수가 throw 한 [COleException](../../mfc/reference/coleexception-class.md) 호출 하 여 [AfxThrowOleException](exception-processing.md#afxthrowoleexception)합니다.  
  
 응용 프로그램에서 OLE 함수 호출의 반환 값을 확인 하려면이 함수를 사용할 수 있습니다. 응용 프로그램에서이 함수의 반환 값을 테스트 함으로써 제대로 최소한의 코드만 사용 하 여 오류 조건을에 반응할 수 있습니다.  
  
> [!NOTE]
>  이 함수는 디버그에서 같습니다 및 디버그가 아닌 빌드합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer # 33](../../mfc/codesnippet/cpp/diagnostic-services_10.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h

##  <a name="afxcheckmemory"></a>AfxCheckMemory  
 이 함수는 사용 가능한 메모리 풀의 유효성을 검사 하 고 필요에 따라 오류 메시지를 인쇄 합니다.  
  
```   
BOOL  AfxCheckMemory(); 
```  
  
### <a name="return-value"></a>반환 값  
 메모리 오류가 없거나; 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 함수에서 메모리 손상이 없는지를 발견 하면 아무 것도 표시 됩니다.  
  
 힙에 현재 할당 된 모든 메모리 블록에 의해 할당 하는 것을 포함 하 여 확인 되므로 **새** 는 없음와 같은 기본 메모리 할당자를 직접 호출 하 여 할당 된는 `malloc` 함수 또는 **GlobalAlloc** Windows 함수입니다. 손상 된 것으로 발견 되는 블록 디버거 출력에 메시지가 인쇄 됩니다.  
  
 줄을 포함 하는 경우  
  
 [!code-cpp[NVC_MFCCObjectSample # 14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 프로그램 모듈에 대 한 다음 후속 호출에서 `AfxCheckMemory` 메모리가 할당 된 파일 이름과 줄 번호를 표시 합니다.  
  
> [!NOTE]
>  모듈에는 하나 이상의 serializable 클래스 구현 다음 삽입 해야 하는 경우는 `#define` 마지막 뒤에 줄 `IMPLEMENT_SERIAL` 매크로 호출 합니다.  
  
 이 함수는 MFC의 디버그 버전 에서만에서 작동합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCObjectSample # 26](../../mfc/codesnippet/cpp/diagnostic-services_11.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
 
##  <a name="afxdump"></a>AfxDump (MFC)  
 디버거를 디버깅 하는 동안 개체의 상태를 덤프에 있는 동안이 함수를 호출 합니다.  
  
```   
void AfxDump(const CObject* pOb); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pOb`  
 파생 된 클래스의 개체에 대 한 포인터 `CObject`합니다.  
  
### <a name="remarks"></a>설명  
 **AfxDump** 개체의 호출 `Dump` 멤버 함수와 보냅니다에 의해 지정 된 위치에 대 한 정보는 `afxDump` 변수입니다. **AfxDump** MFC의 디버그 버전 에서만 사용할 수 있습니다.  
  
 프로그램 코드를 호출 해서는 안 **AfxDump**를 대신 호출 해야 하지만 `Dump` 적절 한 개체의 멤버 함수입니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  

### <a name="see-also"></a>참고 항목  
 [CObject::Dump](cobject-class.md#dump)   


  
##  <a name="afxdumpstack"></a>AfxDumpStack  
 현재 스택의 이미지를 생성할지이 전역 함수를 사용할 수 있습니다.  
  
```   
void AFXAPI AfxDumpStack(DWORD dwTarget = AFX_STACK_DUMP_TARGET_DEFAULT); 
```  
  
### <a name="parameters"></a>매개 변수  
 *dwTarget*  
 덤프 출력의 대상을 나타냅니다. 비트 OR를 사용 하 여 결합할 수 있는 가능한 값 ( **|**) 연산자는 다음과 같습니다.  
  
- **AFX_STACK_DUMP_TARGET_TRACE** 방법으로 출력 보냅니다는 [추적](#trace) 매크로입니다. **추적** 디버그 빌드에서 출력을 생성 하는 매크로, 릴리스 빌드에 없는 출력을 생성 합니다. 또한 **추적** 디버거 외에도 다른 대상으로 리디렉션할 수 있습니다.  
  
- **AFX_STACK_DUMP_TARGET_DEFAULT** 보냅니다 덤프 기본 대상에 출력 합니다. 디버그 빌드에 대 한 출력 되는지는 **추적** 매크로입니다. 릴리스 빌드에서 출력 클립보드로 이동합니다.  
  
- **AFX_STACK_DUMP_TARGET_CLIPBOARD** 만 클립보드에 출력을 보냅니다. 일반 텍스트를 사용 하 여 클립보드에 데이터를 붙여넣습니다는 **CF_TEXT** 클립보드 형식입니다.  
  
- **AFX_STACK_DUMP_TARGET_BOTH** 클립보드로 및 출력 보냅니다는 **추적** 매크로 동시에 합니다.  
  
- **AFX_STACK_DUMP_TARGET_ODS** Win32 함수를 사용 하 여 디버거에 직접 출력을 보내는 **OutputDebugString()**합니다. 이 옵션은 디버그에서 디버거 출력을 생성 하 고 릴리스 빌드 프로세스에 디버거를 연결 합니다. **AFX_STACK_DUMP_TARGET_ODS** 항상 (연결) 하는 경우 디버거 큐에 도달 하 고 리디렉션할 수 없습니다.  
  
### <a name="remarks"></a>주의  
 다음 예제에서는 호출에서 생성 된 출력을 전혀 반영 `AfxDumpStack` MFC 대화 상자 응용 프로그램의 단추 처리기에서:  
  
 `=== begin AfxDumpStack output ===`  
  
 `00427D55: DUMP2\DEBUG\DUMP2.EXE! void AfxDumpStack(unsigned long) + 181 bytes`  
  
 `0040160B: DUMP2\DEBUG\DUMP2.EXE! void CDump2Dlg::OnClipboard(void) + 14 bytes`  
  
 `0044F884: DUMP2\DEBUG\DUMP2.EXE! int _AfxDispatchCmdMsg(class CCmdTarget *,`  
  
 `unsigned int,int,void ( CCmdTarget::*)(void),void *,unsigned int,struct AFX_CMDHANDLE`  
  
 `0044FF7B: DUMP2\DEBUG\DUMP2.EXE! virtual int CCmdTarget::OnCmdMsg(unsigned`  
  
 `int,int,void *,struct AFX_CMDHANDLERINFO *) + 626 bytes`  
  
 `00450C71: DUMP2\DEBUG\DUMP2.EXE! virtual int CDialog::OnCmdMsg(unsigned`  
  
 `int,int,void *,struct AFX_CMDHANDLERINFO *) + 36 bytes`  
  
 `00455B27: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnCommand(unsigned`  
  
 `int,long) + 312 bytes`  
  
 `00454D3D: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnWndMsg(unsigned`  
  
 `int,unsigned int,long,long *) + 83 bytes`  
  
 `00454CC0: DUMP2\DEBUG\DUMP2.EXE! virtual long CWnd::WindowProc(unsigned`  
  
 `int,unsigned int,long) + 46 bytes`  
  
 `004528D9: DUMP2\DEBUG\DUMP2.EXE! long AfxCallWndProc(class CWnd *,struct`  
  
 `HWND__ *,unsigned int,unsigned int,long) + 237 bytes`  
  
 `00452D34: DUMP2\DEBUG\DUMP2.EXE! long AfxWndProc(struct HWND__ *,unsigned`  
  
 `int,unsigned int,long) + 129 bytes`  
  
 `BFF73663: WINDOWS\SYSTEM\KERNEL32.DLL! ThunkConnect32 + 2148 bytes`  
  
 `BFF928E0: WINDOWS\SYSTEM\KERNEL32.DLL! UTUnRegister + 2492 bytes`  
  
 `=== end AfxDumpStack() output ===`  
  
 위의 출력의 각 줄은 마지막 함수 호출을 호출 하는 함수 프로토타입 및 함수 호출을 포함 하는 모듈의 전체 경로 이름의 주소를 나타냅니다. 함수 호출 스택에 있는 함수의 정확한 주소에서 발생 하지 않습니다, 바이트 오프셋 표시 됩니다.  
  
 예를 들어 다음 표에서 위 출력의 첫 번째 줄을 설명합니다.  
  
|출력|설명|  
|------------|-----------------|  
|`00427D55:`|마지막 함수 호출의 반환 주소입니다.|  
|`DUMP2\DEBUG\DUMP2.EXE!`|함수 호출을 포함 하는 모듈의 전체 경로 이름입니다.|  
|`void AfxDumpStack(unsigned long)`|함수 프로토타입 호출 됩니다.|  
|`+ 181 bytes`|함수 프로토타입의 주소에서 바이트에서 오프셋 (이 경우 `void AfxDumpStack(unsigned long)`)에서 반환 주소로 (이 경우 `00427D55`).|  
  
 `AfxDumpStack`MFC 라이브러리;의 디버그 빌드와 버전에서는 사용할 수 그러나 함수는 항상 정적으로 연결, 실행 파일 공유 DLL에서 MFC를 사용 하는 경우에 합니다. 공유 라이브러리 구현에서는 함수는 MFCS42에 있습니다. LIB 라이브러리 (및 그 변형)입니다.  
  
 이 함수를 사용 했습니다.  
  
-   IMAGEHLP 파일입니다. DLL 경로에 있어야 합니다. 이 DLL이 없으면 함수는 오류 메시지가 표시 됩니다. 참조 [이미지 도움말 라이브러리](http://msdn.microsoft.com/library/windows/desktop/ms680321) IMAGEHLP에서 제공 하는 함수 집합에 대 한 내용은 합니다.  
  
-   스택에 프레임 하는 모듈 디버깅 정보를 포함 해야 합니다. 디버깅 정보를 포함 하지 않습니다 상태 함수에서 스택 추적을 생성 하지만 추적 덜 자세하게 표시 됩니다.  
### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="afxenablememoryleakdump"></a>AfxEnableMemoryLeakDump  
 `AFX_DEBUG_STATE` 소멸자에서 메모리 누수 덤프를 사용하거나 사용하지 않도록 설정합니다.  
  
```  
BOOL AFXAPI AfxEnableMemoryLeakDump(BOOL bDump);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bDump`  
 `TRUE`는 메모리 누수 덤프가 사용됨을 나타내고, `FALSE`는 메모리 누수 덤프가 사용되지 않음을 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 이 플래그에 대한 이전 값입니다.  
  
### <a name="remarks"></a>설명  
 응용 프로그램이 MFC 라이브러리를 언로드하면 MFC 라이브러리는 메모리 누수를 확인합니다. 메모리 누수를 모두를 통해 사용자에 게 보고 되는 시점에서 **디버그** 의 창 [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]합니다.  
  
 응용 프로그램이 MFC 라이브러리 전에 다른 라이브러리를 로드하는 경우, 해당 라이브러리의 일부 메모리 할당이 메모리 누수로 잘못 보고됩니다. 거짓 메모리 누수가 발생하면 MFC 라이브러리에서 이를 보고하므로 응용 프로그램이 느리게 종료될 수 있습니다. 이 경우 메모리 누수 덤프를 사용하지 않으려면 `AfxEnableMemoryLeakDump` 를 사용합니다.  
  
> [!NOTE]
>  이 방법을 사용하여 메모리 누수 덤프를 끄는 경우, 응용 프로그램에서 발생하는 유효한 메모리 누수의 보고서를 받지 못합니다. 메모리 누수 보고서에 거짓 메모리 누수가 포함되어 있다고 확신하는 경우에만 이 방법을 사용해야 합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="afxenablememorytracking"></a>AfxEnableMemoryTracking  
 진단 메모리 추적이 MFC의 디버그 버전에서는 일반적으로 사용 됩니다.  
  
```   
BOOL AfxEnableMemoryTracking(BOOL bTrack); 
```  
  
### <a name="parameters"></a>매개 변수  
 *bTrack*  
 이 값을 설정 **TRUE** 추적; 메모리 설정 **FALSE** 해제 합니다.  
  
### <a name="return-value"></a>반환 값  
 추적 기능을 사용 하도록 플래그의 이전 설정입니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 사용 하 여 블록을 올바르게 할당은 사용자가 알고 있는 코드의 섹션에서 추적을 사용 하지 않도록 설정 합니다.  
  
 대 한 자세한 내용은 `AfxEnableMemoryTracking`, 참조 [MFC 응용 프로그램 디버깅](/visualstudio/debugger/mfc-debugging-techniques)합니다.  
  
> [!NOTE]
>  이 함수는 MFC의 디버그 버전 에서만에서 작동합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities # 24](../../mfc/codesnippet/cpp/diagnostic-services_12.cpp)]  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="afxismemoryblock"></a>AfxIsMemoryBlock  
 진단 버전에서 할당 된 현재 사용 중인 메모리 블록을 나타내는 되도록 메모리 주소 테스트 **새**합니다.  
  
```   
BOOL AfxIsMemoryBlock(
    const void* p,  
    UINT nBytes,  
    LONG* plRequestNumber = NULL); 
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 테스트할 메모리 블록을 가리킵니다.  
  
 `nBytes`  
 바이트의 메모리 블록의 길이 포함합니다.  
  
 `plRequestNumber`  
 가리키는 **긴** 정수 시퀀스 번호를 할당 하는 메모리 블록, 채워질 또는 현재 활성 메모리 블록을 나타내지 않는 경우 0입니다.  
  
### <a name="return-value"></a>반환 값  
 메모리 블록은 현재 할당 된이 고 길이 올바른; 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 또한 원래 할당 된 크기에 대해 지정된 된 크기를 확인합니다. 함수가 0이 아닌 값을 반환 하는 경우에 할당 순서 번호가 반환 `plRequestNumber`합니다. 이 숫자는 블록은 다른 모든를 기준으로 할당 된 순서를 나타내는 **새** 할당 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities # 27](../../mfc/codesnippet/cpp/diagnostic-services_13.cpp)]  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="afxisvalidaddress"></a>AfxIsValidAddress  
 프로그램의 메모리 공간 내에 완전히 포함 되어 있음을 확인 하는 메모리 주소를 테스트 합니다.  
  
```   
BOOL AfxIsValidAddress(
    const void* lp,  
    UINT nBytes,  
    BOOL bReadWrite = TRUE); 
```  
  
### <a name="parameters"></a>매개 변수  
 `lp`  
 테스트할 메모리 주소를 가리킵니다.  
  
 `nBytes`  
 테스트할 메모리의 바이트 수를 포함 합니다.  
  
 *bReadWrite*  
 메모리 읽기 및 쓰기를 위해 모두 인지를 지정 ( **TRUE**) 읽어서 또는 ( **FALSE**).  
  
### <a name="return-value"></a>반환 값  
 디버그 빌드에서 지정된 된 메모리를 차단 하는 경우 0이 아닌 내에 포함 된 완전히 프로그램의 메모리 공간입니다. 그렇지 않으면 0입니다.  
  
 디버그가 아닌 빌드에서 경우 0이 아닌 `lp` NULL이 고, 그렇지 않으면 0을 않습니다.  
  
### <a name="remarks"></a>주의  
 주소에 의해 할당 된 블록에 제한 되지 않습니다. **새**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities # 28](../../mfc/codesnippet/cpp/diagnostic-services_14.cpp)]  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="afxisvalidstring"></a>AfxIsValidString  
 문자열에 대 한 포인터 올바른지 여부를 확인 하려면이 함수를 사용 합니다.  
  
```   
BOOL  AfxIsValidString(
    LPCSTR lpsz,  
    int nLength = -1); 
```  
  
### <a name="parameters"></a>매개 변수  
 `lpsz`  
 테스트에 대 한 포인터입니다.  
  
 `nLength`  
 바이트 단위로 테스트할 문자열의 길이 지정 합니다. 값이-1 문자열이 null로 끝나는 않을 있는지 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 디버그 빌드에서 지정된 된 포인터; 지정된 된 크기의 문자열을 가리키는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
 디버그가 아닌 빌드에서 경우 0이 아닌 `lpsz` NULL이 고, 그렇지 않으면 0을 않습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities # 29](../../mfc/codesnippet/cpp/diagnostic-services_15.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="afxsetallochook"></a>AfxSetAllocHook  
 각 메모리 블록을 할당 하기 전에 지정 된 함수 호출 수 있도록 하는 후크를 설정 합니다.  
  
```   
AFX_ALLOC_HOOK AfxSetAllocHook(AFX_ALLOC_HOOK pfnAllocHook); 
```  
  
### <a name="parameters"></a>매개 변수  
 *pfnAllocHook*  
 호출할 함수의 이름을 지정 합니다. 할당 함수 프로토타입에 대 한 설명을 참조 하세요.  
  
### <a name="return-value"></a>반환 값  
 할당을 허용 하려는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 Microsoft Foundation Class 라이브러리 디버그 메모리 할당자는 사용자 메모리 할당을 모니터링 하 고 할당이 허용 되는지 여부를 제어할 수 있도록 허용 하는 사용자 정의 후크 함수를 호출할 수 있습니다. 할당 후크 함수는 프로토타입화 다음과 같습니다.  
  
 **BOOL AFXAPI AllocHook( size_t** `nSize`**, BOOL** `bObject`**, LONG** `lRequestNumber` **);**  
  
 `nSize`  
 제안 된 메모리 할당의 크기입니다.  
  
 `bObject`  
 **True 이면** 할당에 대 한 경우는 `CObject`-파생 된 개체, 그렇지 않으면 **FALSE**합니다.  
  
 `lRequestNumber`  
 메모리 할당의 시퀀스 번호입니다.  
  
 **AFXAPI** 호출 규칙은 의미 호출 수신자가 스택에서 매개 변수를 제거 해야 합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="afxdoforallclasses"></a>AfxDoForAllClasses  
 지정 된 반복 함수에 대 한 모든 직렬화 가능 호출 `CObject`-응용 프로그램의 메모리 공간에서 파생 된 클래스가 있습니다.  
  
```   
void  
AFXAPI AfxDoForAllClasses(
    void (* pfn)(const CRuntimeClass* pClass, void* pContext),  
    void* pContext); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pfn`  
 각 클래스에 대해 호출 되는 반복 함수를 가리킵니다. 함수 인수는에 대 한 포인터는 `CRuntimeClass` 개체와 호출자가 함수에 제공 하는 추가 데이터에 대 한 void 포인터입니다.  
  
 `pContext`  
 반복 함수에 호출자에 게 제공할 수 있는 데이터를 가리킵니다. 이 포인터 수 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 직렬화 가능 `CObject`-파생 된 클래스는 사용 하 여 파생 클래스는 `DECLARE_SERIAL` 매크로입니다. 에 전달 되는 포인터 `AfxDoForAllClasses` 에 `pContext` 가 호출 될 때마다 지정 된 반복 함수에 전달 됩니다.  
  
> [!NOTE]
>  이 함수는 MFC의 디버그 버전 에서만에서 작동합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections # 113](../../mfc/codesnippet/cpp/diagnostic-services_16.cpp)]  
  
 [!code-cpp[NVC_MFCCollections # 114](../../mfc/codesnippet/cpp/diagnostic-services_17.cpp)]  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="afxdoforallobjects"></a>AfxDoForAllObjects  
 파생 된 모든 개체에 대 한 지정 된 반복 함수를 실행 `CObject` 할당할 수 있는 **새**합니다.  
  
```   
void AfxDoForAllObjects(
    void (* pfn)(CObject* pObject, void* pContext),  
    void* pContext); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pfn`  
 각 개체에 대해 실행 하는 반복 함수를 가리킵니다. 함수 인수는에 대 한 포인터는 `CObject` 및 함수에 호출자에 게 제공 하는 추가 데이터에 대 한 void 포인터입니다.  
  
 `pContext`  
 반복 함수에 호출자에 게 제공할 수 있는 데이터를 가리킵니다. 이 포인터 수 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 전역, 스택 또는 포함 된 개체가 열거 되지 않습니다. 에 전달 된 포인터 `AfxDoForAllObjects` 에 `pContext` 가 호출 될 때마다 지정 된 반복 함수에 전달 됩니다.  
  
> [!NOTE]
>  이 함수는 MFC의 디버그 버전 에서만에서 작동합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections # 115](../../mfc/codesnippet/cpp/diagnostic-services_18.cpp)]  
  
 [!code-cpp[NVC_MFCCollections # 116](../../mfc/codesnippet/cpp/diagnostic-services_19.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
