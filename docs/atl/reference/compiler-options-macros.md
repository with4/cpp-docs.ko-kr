---
title: "컴파일러 옵션의 매크로 | Microsoft 문서"
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
- compiler options, macros
ms.assetid: a869adc6-b3de-4299-b040-9ae20b45f82c
caps.latest.revision: 17
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
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: dbce962873194c1bdcb063537247650cff568e35
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-options-macros"></a>컴파일러 옵션의 매크로
이러한 매크로 특정 컴파일러 기능을 제어 합니다.  
  
|||  
|-|-|  
|[_ATL_ALL_WARNINGS](#_atl_all_warnings)|이전 버전의 ATL.에서 변환 된 프로젝트에서 오류를 활성화 하는 기호|  
|[_ATL_APARTMENT_THREADED](#_atl_apartment_threaded)|하나 이상의 개체 아파트 스레딩을 사용 하는 경우를 정의 합니다.|  
|[_ATL_CSTRING_EXPLICIT_CONSTRUCTORS](#_atl_cstring_explicit_constructors)|어느 `CString` 있는 의도 하지 않은 변환을 방지 명시적 생성자입니다.|  
|[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning)|C + + 표준 규격 구문을 사용 하는 멤버 함수에 대 한 포인터를 초기화 하는 비표준 구문을 사용할 때 c&4867;이 발생 컴파일러 오류를 생성 하는 데이 매크로 정의 합니다.|  
|[_ATL_FREE_THREADED](#_atl_free_threaded)|개체의 하나 이상의 무료 또는 중립 스레딩을 사용 하는 경우를 정의 합니다.|  
|[_ATL_MULTI_THREADED](#_atl_multi_threaded)|프로젝트를 나타내는 기호가 모두 무료 또는 중립으로 표시 된 개체를 갖습니다. 매크로 [_ATL_FREE_THREADED](#_atl_free_threaded) 를 대신 사용 해야 합니다.|  
|[_ATL_NO_AUTOMATIC_NAMESPACE](#_atl_no_automatic_namespace)|ATL.로 네임 스페이스의 기본 사용을 방지 하는 기호|  
|[_ATL_NO_COM_SUPPORT](#_atl_no_com_support)|COM 관련 코드 프로젝트를 컴파일할 수 없도록 기호입니다.|  
|[ATL_NO_VTABLE](#atl_no_vtable)|Vtable 포인터는 클래스의 생성자와 소멸자에서 초기화 되지 못하도록 하는 기호입니다.|  
|[ATL_NOINLINE](#atl_noinline)|인라인 함수를 나타내는 기호 되지 않아야 합니다.|  
|[_ATL_SINGLE_THREADED](#_atl_single_threaded)|단일 스레딩 모델을 사용 하 여 모든 개체를 정의 합니다.|  
  
##  <a name="a-nameatlallwarningsa--atlallwarnings"></a><a name="_atl_all_warnings"></a>_ATL_ALL_WARNINGS  
 이전 버전의 ATL.에서 변환 된 프로젝트에서 오류를 활성화 하는 기호  
  
```
#define _ATL_ALL_WARNINGS
```  
  
### <a name="remarks"></a>주의  
 Visual c + +.NET 2002 년 이전 ATL 다양 한 경고를 비활성화 하 고 내리지 않도록은 하지 나타난 사용자 코드에서. 구체적으로는 다음과 같습니다.  
  
-   C4127 조건식은 상수  
  
-   C4786 'identifier': 식별자 디버그 정보의 'number' 문자로 잘렸습니다.  
  
-   비표준 확장이 사용 됨 C4201: 이름이 없는 구조체/공용 구조체  
  
-   C4103 'filename': 맞춤을 변경 하려면 #pragma 팩 사용  
  
-   C4291 'declaration': 그렇지 않으면 delete 연산자 없는 일치 하는 초기화는 예외를 throw 하는 경우 메모리를 해제 되지 않습니다.  
  
-   C4268 'identifier': 컴파일러에서 생성 된 기본 생성자를 사용 하 여 초기화 하는 'const' 정적/전역 데이터 개체를&0;으로 채우기  
  
-   C4702 접근할 수 없는 코드  
  
 이전 버전에서 변환 된 프로젝트에서는 이러한 경고가 여전히 라이브러리 헤더에 의해 비활성화 됩니다.  
  
 라이브러리 헤더를 포함 하기 전에 stdafx.h 파일에 다음 줄을 추가, 하 여이 동작을 변경할 수 있습니다.  
  
 [!code-cpp[NVC_ATL_Utilities #&97;](../../atl/codesnippet/cpp/compiler-options-macros_1.h)]  
  
 이 경우 `#define` ATL 헤더는 전역적으로 사용할 수 있도록 (또는 사용자에 사용 하도록 설정 하지 개별 경고를 명시적으로 비활성화 하는 경우) 이러한 경고의 상태를 유지 하기 위해 신중 하 게 추가 됩니다.  
  
 새 프로젝트를 Visual c + +.NET 2002를 사용 하 여 생성 됩니다 이걸 `#define` stdafx.h에 기본적으로 설정 합니다.  
  
##  <a name="a-nameatlapartmentthreadeda--atlapartmentthreaded"></a><a name="_atl_apartment_threaded"></a>_ATL_APARTMENT_THREADED  
 하나 이상의 개체 아파트 스레딩을 사용 하는 경우를 정의 합니다.  
  
```
_ATL_APARTMENT_THREADED
```  
  
### <a name="remarks"></a>주의  
 아파트 스레딩 지정합니다. 참조 [프로젝트의 스레딩 모델 지정](../../atl/specifying-the-threading-model-for-a-project-atl.md) 다른 옵션, 스레딩 및 [옵션, ATL 단순 개체 마법사](../../atl/reference/options-atl-simple-object-wizard.md) 에 대 한 설명은 스레딩 모델 ATL 개체에 사용할 수 있습니다.  
  
##  <a name="a-nameatlcstringexplicitconstructorsa--atlcstringexplicitconstructors"></a><a name="_atl_cstring_explicit_constructors"></a>_ATL_CSTRING_EXPLICIT_CONSTRUCTORS  
 어느 `CString` 있는 의도 하지 않은 변환을 방지 명시적 생성자입니다.  
  
```
_ATL_CSTRING_EXPLICIT_CONSTRUCTORS
```  
  
### <a name="remarks"></a>주의  
 이 정의 하는 경우 단일 매개 변수를 사용 하는 모든 CString 생성자 입력된 인수를 암시적으로 변환할 수 없는 explicit 키워드를 사용 하 여 컴파일됩니다. 즉, 예를 들어 _UNICODE가 정의 된 경우 사용 하려는 경우 char * 문자열을 CString 생성자 인수로 컴파일러 오류가 발생 합니다. 좁은 및 와이드 문자열 형식 간의 암시적 변환을 방지 해야 하는 경우에이 매크로 사용 합니다.  
  
 _T 매크로 모든 생성자 문자열 인수를 사용 하 여 _ATL_CSTRING_EXPLICIT_CONSTRUCTORS를 정의 하 고 _UNICODE 정의 여부에 관계 없이 컴파일 오류를 방지할 수 있습니다.  
  
##  <a name="a-nameatlenableptmwarninga--atlenableptmwarning"></a><a name="_atl_enable_ptm_warning"></a>_ATL_ENABLE_PTM_WARNING  
 멤버 함수에 대 한 포인터에 대 한 ANSI c + + 표준 규격 구문을 사용 하도록 하기 위해이 매크로 정의 합니다. 이 매크로 사용 하 여 비표준 구문을 사용 하는 멤버 함수에 대 한 포인터를 초기화 하는 경우 생성 되는 c&4867;이 발생 컴파일러 오류가 발생 합니다.  
  
```
#define _ATL_ENABLE_PTM_WARNING
```  
  
### <a name="remarks"></a>주의  
 ATL 및 MFC 라이브러리는 Visual c + + 컴파일러의 향상 된 표준 c + + 규격 일치 하도록 변경 되었습니다. 클래스 멤버 함수에 대 한 포인터의 구문은 ANSI c + + 표준에 따라 해야 `&CMyClass::MyFunc`합니다.  
  
 때 [_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning) 정의 되어 있지 않습니다 (기본 경우), ATL/MFC 사용 하지 않도록 설정 (특히 메시지 맵) 매크로 맵에서 c&4867;이 발생 오류 이전 버전에서 생성 된 코드를 계속 이전 처럼 빌드할 수 있도록 합니다. 정의 하는 경우 **_ATL_ENABLE_PTM_WARNING**, 사용자 코드는 c + + 표준 준수 해야 합니다.  
  
 그러나 비표준 폼은 사용 되지, c + + 표준 규격 구문으로 기존 코드를 이동 해야 합니다. 예를 들어, 다음:  
  
 [!code-cpp[NVC_MFCListView #&14;](../../atl/reference/codesnippet/cpp/compiler-options-macros_2.cpp)]  
  
 로 변경 합니다.  
  
 [!code-cpp[NVC_MFCListView #&11;](../../atl/reference/codesnippet/cpp/compiler-options-macros_3.cpp)]  
  
 Note는 '/' 문자를 추가 하는 맵 매크로 대 한 추가 하면 안 것 다시 코드에 있습니다.  
  
##  <a name="a-nameatlfreethreadeda--atlfreethreaded"></a><a name="_atl_free_threaded"></a>_ATL_FREE_THREADED  
 개체의 하나 이상의 무료 또는 중립 스레딩을 사용 하는 경우를 정의 합니다.  
  
```
_ATL_FREE_THREADED
```  
  
### <a name="remarks"></a>주의  
 자유 스레딩 지정합니다. 자유 스레딩 하는 것은 다중 스레드 아파트 모델과 동일 합니다. 참조 [프로젝트의 스레딩 모델 지정](../../atl/specifying-the-threading-model-for-a-project-atl.md) 다른 옵션, 스레딩 및 [옵션, ATL 단순 개체 마법사](../../atl/reference/options-atl-simple-object-wizard.md) 에 대 한 설명은 스레딩 모델 ATL 개체에 사용할 수 있습니다.  
  
##  <a name="a-nameatlmultithreadeda--atlmultithreaded"></a><a name="_atl_multi_threaded"></a>_ATL_MULTI_THREADED  
 프로젝트를 나타내는 기호가 모두 무료 또는 중립으로 표시 된 개체를 갖습니다.  
  
```
_ATL_MULTI_THREADED
```  
  
### <a name="remarks"></a>주의  
 이 기호가 정의 된 ATL는 전역 데이터에 대 한 액세스를 동기화 할 올바르게 하는 코드에서 끌어옵니다. 새 코드는 해당 하는 매크로 사용 해야 [_ATL_FREE_THREADED](#_atl_free_threaded) 대신 합니다.  
  
##  <a name="a-nameatlnoautomaticnamespacea--atlnoautomaticnamespace"></a><a name="_atl_no_automatic_namespace"></a>_ATL_NO_AUTOMATIC_NAMESPACE  
 ATL.로 네임 스페이스의 기본 사용을 방지 하는 기호  
  
```
_ATL_NO_AUTOMATIC_NAMESPACE
```  
  
### <a name="remarks"></a>주의  
 이 기호를 정의 하지 않은 경우 atlbase.h를 포함 하 여 수행 합니다 **ATL 네임 스페이스를 사용 하 여** 기본적으로 이름 충돌을 될 수 있습니다. 이 방지 하려면이 기호를 정의 합니다.  
  
##  <a name="a-nameatlnocomsupporta--atlnocomsupport"></a><a name="_atl_no_com_support"></a>_ATL_NO_COM_SUPPORT  
 COM 관련 코드 프로젝트를 컴파일할 수 없도록 기호입니다.  
  
```
_ATL_NO_COM_SUPPORT```  
  
##  <a name="atl_no_vtable"></a>  ATL_NO_VTABLE  
 A symbol that prevents the vtable pointer from being initialized in the class's constructor and destructor.  
  
```
ATL_NO_VTABLE
```  
  
### Remarks  
 If the vtable pointer is prevented from being initialized in the class's constructor and destructor, the linker can eliminate the vtable and all of the functions to which it points. Expands to **__declspec(novtable)**.  
  
### Example  
 [!code-cpp[NVC_ATL_COM#53](../../atl/codesnippet/cpp/compiler-options-macros_4.h)]  
  
##  <a name="atl_noinline"></a>  ATL_NOINLINE  
 A symbol that indicates a function should not be inlined.  
  
```
    ATL_NOINLINE inline
    myfunction
 { ... }
```  
  
### Parameters  
 *myfunction*  
 The function that should not be inlined.  
  
### Remarks  
 Use this symbol if you want to ensure a function does not get inlined by the compiler, even though it must be declared as inline so that it can be placed in a header file. Expands to **__declspec(noinline)**.  
  
##  <a name="_atl_single_threaded"></a>  _ATL_SINGLE_THREADED  
 Define if all of your objects use the single threading model  
  
```
_ATL_SINGLE_THREADED
```  
  
### Remarks  
 Specifies that the object always runs in the primary COM thread. See [Specifying the Project's Threading Model](../../atl/specifying-the-threading-model-for-a-project-atl.md) for other threading options, and [Options, ATL Simple Object Wizard](../../atl/reference/options-atl-simple-object-wizard.md) for a description of the threading models available for an ATL object.  
  
## See Also  
 [Macros](../../atl/reference/atl-macros.md)

