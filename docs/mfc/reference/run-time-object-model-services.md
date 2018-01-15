---
title: "런타임 개체 모델 서비스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros
dev_langs: C++
helpviewer_keywords: run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 986657681dabf1136b072f65b2df76b63f216504
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="run-time-object-model-services"></a>런타임 개체 모델 서비스
클래스 [CObject](../../mfc/reference/cobject-class.md) 및 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 런타임 클래스 정보, serialization 및 동적 개체 만들기에 대 한 액세스를 포함 한 몇 가지 개체 서비스를 캡슐화 합니다. 모든 클래스에서 파생 된 `CObject` 이 기능을 상속 합니다.  
  
 런타임 클래스 정보에 대 한 액세스를 사용 하면 런타임에 개체의 클래스에 대 한 정보를 확인할 수 있습니다. 런타임 시 개체의 클래스를 결정 하는 기능 추가 형식 검사 함수 인수 및 개체의 클래스를 기반으로 하는 특수 한 용도의 코드를 작성 해야 할 때 유용 합니다. 런타임 클래스 정보는 c + + 언어에서 직접 지원 되지 않습니다.  
  
 Serialization은 프로세스를 작성 하거나 또는 개체의 내용을 읽는 파일에서입니다. 응용 프로그램이 종료 후에 개체의 내용을 저장 하 serialization을 사용할 수 있습니다. 응용 프로그램 다시 시작 되 면에 다음 개체 파일에서 읽을 수 있습니다. 이러한 데이터 개체를 "영구." 라고 합니다.  
  
 동적 개체 만들기를 사용 하면 런타임 시 지정된 된 클래스의 개체를 만들 수 있습니다. 예를 들어, 문서, 뷰 및 프레임 개체 지원 해야 동적 생성 프레임 워크 동적으로 만들어야 하기 때문에 합니다.  
  
 다음 표에서 런타임 클래스 정보, serialization 및 동적 생성을 지 원하는 MFC 매크로 나열 합니다.  
  
 이러한 런타임 개체 서비스와 serialization에 대 한 자세한 내용은 문서 참조 [CObject 클래스: 런타임 클래스 정보 액세스](../../mfc/accessing-run-time-class-information.md)합니다.  
  
### <a name="run-time-object-model-services-macros"></a>런타임 개체 모델 서비스 매크로  
  


|||  
|-|-|  
|[DECLARE_DYNAMIC](#declare_dynamic)|(클래스 선언에 사용 해야 합니다) 런타임 클래스 정보에 액세스할 수 있도록 합니다.|  
|[DECLARE_DYNCREATE](#declare_dyncreate)|동적 만들고 (클래스 선언에 사용 해야 합니다) 런타임 클래스 정보에 대 한 액세스를 사용할 수 있습니다.|  
|[DECLARE_SERIAL](#declare_serial)|Serialization 및 (클래스 선언에 사용 해야 합니다) 런타임 클래스 정보에 액세스할 수 있습니다.|  
|[IMPLEMENT_DYNAMIC](#implement_dynamic)|(클래스 구현에 사용 해야 합니다) 런타임 클래스 정보에 액세스할 수 있도록 합니다.|  
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|동적 만들기 및 실행 시간 정보 (클래스 구현에 사용 해야 합니다)에 액세스할 수 있도록 합니다.|  
|[IMPLEMENT_SERIAL](#implement_serial)|Serialization 및 런타임 클래스 정보 (클래스 구현에 사용 해야 합니다)에 대 한 액세스를 허용 합니다.|  
|[RUNTIME_CLASS](#runtime_class)|반환 된 `CRuntimeClass` 명명된 된 클래스에 해당 합니다.|  


 OLE는 런타임 시 개체의 동적 생성 자주 필요합니다. 예를 들어 OLE 서버 응용 프로그램의 클라이언트에서 요청에 대 한 응답으로 동적으로 OLE 항목을 만들 수 있어야 합니다. 마찬가지로, 자동화 서버 자동화 클라이언트에서 요청에 따라에서 항목을 만들 수 있어야 합니다.  
  
 Microsoft Foundation Class 라이브러리를 OLE 특정 두 매크로 제공합니다.  
  
### <a name="dynamic-creation-of-ole-objects"></a>OLE 개체의 동적 만들기  

 






|||  
|-|-|  
|[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)|공용 컨트롤 라이브러리 지정된 된 API를 구현 하는지 여부를 결정 합니다.|
|[AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)|공용 컨트롤 라이브러리 지정된 된 API를 구현 하는지 여부를 결정 합니다.|
|[DECLARE_OLECREATE](#declare_olecreate)|개체를를 OLE 자동화를 통해 만들 수 있습니다.|  
|[DECLARE_OLECTLTYPE](#declare_olectltype)|선언 된 **GetUserTypeNameID** 및 `GetMiscStatus` 컨트롤 클래스의 멤버 함수입니다.|
|[DECLARE_PROPPAGEIDS](#declare_proppageids)|OLE 컨트롤에는 해당 속성을 표시 하도록 이러한 속성 페이지 목록이 선언 합니다.|
|[IMPLEMENT_OLECREATE](#implement_olecreate)|개체를를 OLE 시스템에서 만들 수 있습니다.|  
|[IMPLEMENT_OLECTLTYPE](#implement_olectltype)|구현 된 **GetUserTypeNameID** 및 `GetMiscStatus` 컨트롤 클래스의 멤버 함수입니다.|  
|[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)|이 매크로 중 하나 또는 [IMPLEMENT_OLECREATE](#implement_olecreate) 클래스를 사용 하는 모든 클래스에 대 한 구현 파일에 표시 되어야 `DECLARE_OLECREATE`합니다. |

## <a name="afx_comctl32_if_exists"></a>AFX_COMCTL32_IF_EXISTS
공용 컨트롤 라이브러리 지정된 된 API를 구현 하는지 여부를 결정 합니다.  
   
### <a name="syntax"></a>구문  
  ```  
AFX_COMCTL32_IF_EXISTS(  proc );  
```
### <a name="parameters"></a>매개 변수  
 `proc`  
 함수 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터 또는 함수의 서 수 값을 지정 합니다. 하위 단어;에 있어야 하는 경우이 매개 변수는 서 수 값을 상위 단어에는 0 이어야 합니다. 이 매개 변수는 유니코드 여야 합니다.  
   
### <a name="remarks"></a>설명  
 이 매크로 사용 하 여 지정 되었는지 여부를 공용 컨트롤 라이브러리 함수에서 결정 `proc` (호출 하는 대신 [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212)합니다.  
   
### <a name="requirements"></a>요구 사항  
 afxcomctl32.h, afxcomctl32.inl  
   
### <a name="see-also"></a>참고 항목  
 [MFC 일반 격리 제어 라이브러리](../isolation-of-the-mfc-common-controls-library.md) [AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)
 
## <a name="afx_comctl32_if_exists2"></a>AFX_COMCTL32_IF_EXISTS2
공용 컨트롤 라이브러리 지정된 된 API를 구현 하는지 여부를 결정 합니다. (이 유니코드 버전을 [AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)).  
   
### <a name="syntax"></a>구문    
```  
AFX_COMCTL32_IF_EXISTS2( proc );  
```
### <a name="parameters"></a>매개 변수  
 `proc`  
 함수 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터 또는 함수의 서 수 값을 지정 합니다. 하위 단어;에 있어야 하는 경우이 매개 변수는 서 수 값을 상위 단어에는 0 이어야 합니다. 이 매개 변수는 유니코드 여야 합니다.  
   
### <a name="remarks"></a>설명  
 이 매크로 사용 하 여 지정 되었는지 여부를 공용 컨트롤 라이브러리 함수에서 결정 `proc` (호출 하는 대신 [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212)합니다. 이 매크로 유니코드 버전을 `AFX_COMCTL32_IF_EXISTS`합니다.  
   
### <a name="requirements"></a>요구 사항  
 afxcomctl32.h, afxcomctl32.inl  
   
### <a name="see-also"></a>참고 항목  
 [MFC 일반 격리 제어 라이브러리](../isolation-of-the-mfc-common-controls-library.md) [AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)



##  <a name="declare_dynamic"></a>DECLARE_DYNAMIC  
 클래스를 파생 하는 경우 개체의 클래스에 대 한 런타임 정보에 액세스할 수 있는 기능을 추가 `CObject`합니다.  
  
```
DECLARE_DYNAMIC(class_name) 
```  
  
### <a name="parameters"></a>매개 변수  
 *class_name*  
 클래스의 실제 이름입니다.  
  
### <a name="remarks"></a>설명  
 추가 된 `DECLARE_DYNAMIC` 매크로 클래스에 대 한 헤더 (.h) 모듈에이 클래스의 개체에 액세스 해야 하는 모든.cpp 모듈에 해당 모듈이 포함 됩니다.  
  
 사용 하는 경우는 **DECLARE**_ **동적** 및 `IMPLEMENT_DYNAMIC` 설명 된 대로 매크로 사용할 수 있습니다는 `RUNTIME_CLASS` 매크로 및 `CObject::IsKindOf` 런타임에 개체의 클래스를 결정 하는 함수 시간입니다.  
  
 경우 `DECLARE_DYNAMIC` 다음 클래스 선언에 포함 된 `IMPLEMENT_DYNAMIC` 클래스 구현에 포함 되어야 합니다.  
  
 대 한 자세한 내용은 `DECLARE_DYNAMIC` 매크로 참조 [CObject 클래스 항목이](../../mfc/using-cobject.md)합니다.  
  
### <a name="example"></a>예  
 예를 참조 [IMPLEMENT_DYNAMIC](#implement_dynamic)합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="declare_dyncreate"></a>DECLARE_DYNCREATE  
 개체를 사용 하면 `CObject`-런타임 시 동적으로 생성 하기 위해 파생 클래스입니다.  
  
```
DECLARE_DYNCREATE(class_name)   
```  
  
### <a name="parameters"></a>매개 변수  
 *class_name*  
 클래스의 실제 이름입니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크는이 기능을 사용 하 여 새 개체를 동적으로 만듭니다. 예를 들어 새 보기 새 문서를 열 때 생성 됩니다. 문서, 뷰 및 프레임 클래스는 프레임 워크 동적으로 만들어야 하기 때문에 동적 만들기를 지원 해야 합니다.  
  
 추가 된 `DECLARE_DYNCREATE` 매크로 클래스에 대 한.h 모듈에서이 클래스의 개체에 액세스 해야 하는 모든.cpp 모듈에 해당 모듈이 포함 됩니다.  
  
 경우 `DECLARE_DYNCREATE` 다음 클래스 선언에 포함 된 `IMPLEMENT_DYNCREATE` 클래스 구현에 포함 되어야 합니다.  
  
 대 한 자세한 내용은 `DECLARE_DYNCREATE` 매크로 참조 [CObject 클래스 항목이](../../mfc/using-cobject.md)합니다.  
  
> [!NOTE]
>  `DECLARE_DYNCREATE` 의 모든 기능을 포함 하는 매크로 `DECLARE_DYNAMIC`합니다.  
  
### <a name="example"></a>예  
 예를 참조 [IMPLEMENT_DYNCREATE](#implement_dyncreate)합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

 
## <a name="declareolectltype"></a>DECLARE_OLECTLTYPE
선언 된 **GetUserTypeNameID** 및 `GetMiscStatus` 컨트롤 클래스의 멤버 함수입니다.  
   
### <a name="syntax"></a>구문    
```
DECLARE_OLECTLTYPE( class_name )  
```
### <a name="parameters"></a>매개 변수  
 *class_name*  
 컨트롤 클래스의 이름입니다.  
   
### <a name="remarks"></a>설명  
 **GetUserTypeNameID** 및 `GetMiscStatus` 에 선언 된 순수 가상 함수는 `COleControl`합니다. 이러한 함수는 순수 이므로 가상, 이러한 재정의 되어야 컨트롤 클래스에 있습니다. 외에 **DECLARE_OLECTLTYPE**를 추가 해야 합니다는 `IMPLEMENT_OLECTLTYPE` 컨트롤 클래스 선언에는 매크로입니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxctl.h  
   
### <a name="see-also"></a>참고 항목  
 [IMPLEMENT_OLECTLTYPE](#implement_olectltype)
 

## <a name="declareproppageids"></a>DECLARE_PROPPAGEIDS
OLE 컨트롤에는 해당 속성을 표시 하도록 이러한 속성 페이지 목록이 선언 합니다.  
   
### <a name="syntax"></a>구문    
```
DECLARE_PROPPAGEIDS( class_name )  
```
### <a name="parameters"></a>매개 변수  
 *class_name*  
 속성 페이지를 소유 하는 컨트롤 클래스의 이름입니다.  
   
### <a name="remarks"></a>설명  
 사용 하 여는 `DECLARE_PROPPAGEIDS` 끝 클래스 선언에는 매크로입니다. 그런 다음 클래스에 대 한 멤버 함수를 정의 하는.cpp 파일에서 사용 하는 `BEGIN_PROPPAGEIDS` 매크로, 각 컨트롤의 속성 페이지에 대해 매크로 항목 및 `END_PROPPAGEIDS` 속성 페이지 목록의 끝을 선언 하는 매크로입니다.  
  
 속성 페이지에 대 한 자세한 내용은 문서 참조 [ActiveX 컨트롤: 속성 페이지](../mfc-activex-controls-property-pages.md)합니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxctl.h  
   
### <a name="see-also"></a>참고 항목   
 [BEGIN_PROPPAGEIDS](#begin_proppageids)   
 [END_PROPPAGEIDS](#end_proppageids)

##  <a name="declare_serial"></a>DECLARE_SERIAL  
 C + + 헤더는 데 필요한 코드를 생성 한 `CObject`-serialize 할 수 있는 클래스를 파생 합니다.  
  
```
DECLARE_SERIAL(class_name)   
```  
  
### <a name="parameters"></a>매개 변수  
 *class_name*  
 클래스의 실제 이름입니다.  
  
### <a name="remarks"></a>설명  
 Serialization은 프로세스 작성 하거나 하 고 개체의 내용의 읽을 파일에서입니다.  
  
 사용 하 여는 `DECLARE_SERIAL` .h 모듈에서는 매크로 한 후이 클래스의 개체에 액세스 해야 하는 모든.cpp 모듈에 해당 모듈을 포함 합니다.  
  
 경우 `DECLARE_SERIAL` 다음 클래스 선언에 포함 된 `IMPLEMENT_SERIAL` 클래스 구현에 포함 되어야 합니다.  
  
 `DECLARE_SERIAL` 의 모든 기능을 포함 하는 매크로 `DECLARE_DYNAMIC` 및 `DECLARE_DYNCREATE`합니다.  
  
 사용할 수 있습니다는 **AFX_API** 를 자동으로 내보낼 매크로 `CArchive` 추출 연산자를 사용 하는 클래스는 `DECLARE_SERIAL` 및 `IMPLEMENT_SERIAL` 매크로입니다. 대괄호를 다음 코드로 클래스 선언 (.h 파일에 있음):  
  
 [!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 대 한 자세한 내용은 `DECLARE_SERIAL` 매크로 참조 [CObject 클래스 항목이](../../mfc/using-cobject.md)합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCCObjectSample#21](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="implement_dynamic"></a>IMPLEMENT_DYNAMIC  
 동적에 필요한 c + + 코드를 생성 `CObject`-클래스 이름 및 계층 구조 내에서 위치에 대 한 런타임 액세스를 사용 하 여 클래스를 파생 합니다.  
  
```
IMPLEMENT_DYNAMIC(class_name, base_class_name)  
```  
  
### <a name="parameters"></a>매개 변수  
 *class_name*  
 클래스의 실제 이름입니다.  
  
 `base_class_name`  
 기본 클래스의 이름입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여는 `IMPLEMENT_DYNAMIC` 는.cpp 모듈과 다음 링크는 결과 개체를 한 번만 코드에 매크로입니다.  
  
 자세한 내용은 참조 [CObject 클래스 항목이](../../mfc/using-cobject.md)합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCCObjectSample#2](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample#3](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="implement_dyncreate"></a>IMPLEMENT_DYNCREATE  
 개체를 사용 하면 `CObject`-런타임에 동적으로 생성 하기 위해 파생 클래스와 함께 사용할 경우 시간는 `DECLARE_DYNCREATE` 매크로입니다.  
  
```
IMPLEMENT_DYNCREATE(class_name, base_class_name)   
```  
  
### <a name="parameters"></a>매개 변수  
 *class_name*  
 클래스의 실제 이름입니다.  
  
 `base_class_name`  
 기본 클래스의 실제 이름입니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크는이 기능을 사용 하 여 새 개체를 동적으로 만들거나 예를 들어 직렬화 하는 동안 디스크에서 개체를 읽을 경우. 추가 된 `IMPLEMENT_DYNCREATE` 클래스 구현 파일에는 매크로입니다. 자세한 내용은 참조 [CObject 클래스 항목이](../../mfc/using-cobject.md)합니다.  
  
 사용 하는 경우는 `DECLARE_DYNCREATE` 및 `IMPLEMENT_DYNCREATE` 매크로 사용할 수 있습니다는 `RUNTIME_CLASS` 매크로 및 `CObject::IsKindOf` 멤버 함수를 런타임 시 개체의 클래스를 확인 합니다.  
  
 경우 `DECLARE_DYNCREATE` 다음 클래스 선언에 포함 된 `IMPLEMENT_DYNCREATE` 클래스 구현에 포함 되어야 합니다.  
  
 참고가 매크로 정의 클래스에 대 한 기본 생성자를 호출 합니다. 특수 한 생성자는 클래스에 의해 명시적으로 구현 되는 경우 기본 생성자도 명시적으로 구현 해야 합니다. 기본 생성자는 클래스에 추가할 수 **개인** 또는 **보호** 멤버 섹션 클래스 구현 외부에서 호출 되 고 하지 못하도록 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCCObjectSample#22](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample#23](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

## <a name="implement_olecreate_flags"></a>IMPLEMENT_OLECREATE_FLAGS
이 매크로 중 하나 또는 [IMPLEMENT_OLECREATE](#implement_olecreate) 클래스를 사용 하는 모든 클래스에 대 한 구현 파일에 표시 되어야 `DECLARE_OLECREATE`합니다.  
   
### <a name="syntax"></a>구문    
```
IMPLEMENT_OLECREATE_FLAGS( class_name, external_name, nFlags, 
    l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)  
  
```
### <a name="parameters"></a>매개 변수  
 *class_name*  
 클래스의 실제 이름입니다.  
  
 *external_name*  
 (따옴표에 포함) 다른 응용 프로그램에 노출 되는 개체 이름입니다.  
  
 `nFlags`  
 다음과 같은 플래그 중 하나 이상을 포함 되어 있습니다.  
  
-   `afxRegInsertable`OLE 개체에 대 한 개체 삽입 대화 상자에 표시를 제어할 수 있습니다.    
-   `afxRegApartmentThreading`ThreadingModel 레지스트리에서 설정 하는 스레딩 모델이 아파트 = 합니다.    
-   **afxRegFreeThreading** ThreadingModel 레지스트리에서 스레딩 모델을 설정 합니다. 무료 = 합니다.  
  
     두 플래그를 결합할 수 있습니다 `afxRegApartmentThreading` 및 `afxRegFreeThreading` ThreadingModel 설정할 = Both입니다. 참조 [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) 스레딩 모델 등록에 대 한 자세한 내용은 Windows sdk입니다.    
 *l*, *w1*, *w2*, *b1*, *b 2*, *b3*, *b4*, *b5*, *b6*, *b7*, *b8*  
 클래스의의 구성 요소 **CLSID**합니다.  
   
### <a name="remarks"></a>설명  
  
> [!NOTE]
>  사용 하는 경우 `IMPLEMENT_OLECREATE_FLAGS`를 사용 하 여 개체가 지 원하는 스레딩 모델을 지정할 수 있습니다는 `nFlags` 매개 변수입니다. 사용 하 여 단일 스레딩 모델만 지원 하려는 경우 `IMPLEMENT_OLECREATE`합니다.  
  
 외부 이름에는 다른 응용 프로그램에 노출 된 식별자입니다. 자동화 서버에서이 클래스의 개체를 요청 하려면 외부 이름을 사용 하는 클라이언트 응용 프로그램.  
  
 OLE 클래스 ID가 개체에 대 한 고유 128 비트 식별자입니다. 하나 이루어져 **긴**, 두 개의 **단어**s 및 8 **바이트**s에 의해 표시 된 대로 *l*, *w1*, *w2*, 및 *b1* 통해 *b8* 구문 설명에 있습니다. 응용 프로그램 마법사 및 코드 마법사를 필요에 따라 고유한 OLE 클래스 Id를 만듭니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  
   
### <a name="see-also"></a>참고 항목  
 [매크로 및 전역](mfc-macros-and-globals.md)   
 [DECLARE_OLECREATE](#declare_olecreate)   
 [CLSID 키](http://msdn.microsoft.com/library/windows/desktop/ms691424)


## <a name="implement_olecreate"></a>IMPLEMENT_OLECTLTYPE
구현 된 **GetUserTypeNameID** 및 `GetMiscStatus` 컨트롤 클래스의 멤버 함수입니다.  
   
### <a name="syntax"></a>구문    
```
DECLARE_OLECTLTYPE( class_name, idsUserTypeName, dwOleMisc )  
```
### <a name="parameters"></a>매개 변수  
 *class_name*  
 컨트롤 클래스의 이름입니다.  
  
 *idsUserTypeName*  
 컨트롤의 외부 이름을 포함 하는 문자열의 리소스 ID입니다.  
  
 *dwOleMisc*  
 하나 이상의 플래그를 포함 하는 열거형입니다. 이 열거형에 대 한 자세한 내용은 참조 하십시오. [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) Windows sdk에서입니다.  
   
### <a name="remarks"></a>설명  
 외에 `IMPLEMENT_OLECTLTYPE`를 추가 해야 합니다는 **DECLARE_OLECTLTYPE** 컨트롤 클래스 선언에는 매크로입니다.  
  
 **GetUserTypeNameID** 멤버 함수가 컨트롤 클래스를 식별 하는 리소스 문자열을 반환 합니다. `GetMiscStatus`반환 된 **OLEMISC** 컨트롤에 대 한 비트입니다. 이 열거형에는 컨트롤의 기타 특징을 설명 하는 설정의 컬렉션을 지정 합니다. 에 대 한 전체 설명은 **OLEMISC** 설정을 참조 [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) Windows sdk에서입니다.  
  
> [!NOTE]
>  ActiveX 컨트롤에서 사용 하는 기본 설정이: **OLEMISC_ACTIVATEWHENVISIBLE**, **OLEMISC_SETCLIENTSITEFIRST**, **OLEMISC_INSIDEOUT**, **OLEMISC_CANTLINKINSIDE**, 및 **OLEMISC_RECOMPOSEONRESIZE**합니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxctl.h  
   
### <a name="see-also"></a>참고 항목  
 [매크로 및 전역](mfc-macros-and-globals.md)   
 [DECLARE_OLECTLTYPE](#declare_olectltype)

##  <a name="implement_serial"></a>IMPLEMENT_SERIAL  
 동적에 필요한 c + + 코드를 생성 `CObject`-클래스 이름 및 계층 구조 내에서 위치에 대 한 런타임 액세스를 사용 하 여 클래스를 파생 합니다.  
  
```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)  
```  
  
### <a name="parameters"></a>매개 변수  
 *class_name*  
 클래스의 실제 이름입니다.  
  
 `base_class_name`  
 기본 클래스의 이름입니다.  
  
 *wSchema*  
 A **UINT** 식별 하 고 처리 하 여 만든 데이터 역직렬화 프로그램을 허용 하도록 보관 파일에 인코딩될 "버전 번호" 이전 버전을 프로그래밍 합니다. 클래스 스키마 번호가-1 수 없습니다.  
  
### <a name="remarks"></a>설명  
 사용 된 `IMPLEMENT_SERIAL` 매크로.cpp 모듈에 다음 결과 개체 코드를 한 번만 연결 합니다.  
  
 사용할 수 있습니다는 **AFX_API** 를 자동으로 내보낼 매크로 `CArchive` 추출 연산자를 사용 하는 클래스는 `DECLARE_SERIAL` 및 `IMPLEMENT_SERIAL` 매크로입니다. 대괄호를 다음 코드로 클래스 선언 (.h 파일에 있음):  
  
 [!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 자세한 내용은 참조는 [CObject 클래스 항목이](../../mfc/using-cobject.md)합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCCObjectSample#24](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="runtime_class"></a>RUNTIME_CLASS  
 C + + 클래스의 이름에서 런타임에 클래스 구조를 가져옵니다.  
  
```
RUNTIME_CLASS(class_name)  
```  
  
### <a name="parameters"></a>매개 변수  
 *class_name*  
 (인용 부호로 묶지) 클래스의 실제 이름입니다.  
  
### <a name="remarks"></a>설명  
 `RUNTIME_CLASS`에 대 한 포인터를 반환 합니다.는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 에서 지정 된 클래스에 대 한 구조 *class_name*합니다. 만 `CObject`-파생 된 클래스를 사용 하 여 선언 `DECLARE_DYNAMIC`, `DECLARE_DYNCREATE`, 또는 `DECLARE_SERIAL` 에 대 한 포인터를 반환 합니다는 `CRuntimeClass` 구조입니다.  
  
 자세한 내용은 참조 [CObject 클래스 항목이](../../mfc/using-cobject.md)합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCCObjectSample#25](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 
   
##  <a name="declare_olecreate"></a>DECLARE_OLECREATE  
 개체를 사용 하면 `CCmdTarget`-OLE 자동화를 통해 생성 되는 클래스를 파생 합니다.  
  
```
DECLARE_OLECREATE(class_name) 
```  
  
### <a name="parameters"></a>매개 변수  
 *class_name*  
 클래스의 실제 이름입니다.  
  
### <a name="remarks"></a>설명  
 이 매크로 다른 OLE 지원 응용 프로그램을이 형식의 개체를 만들 수 있습니다.  
  
 추가 된 `DECLARE_OLECREATE` 매크로 클래스에 대 한.h 모듈에서 한 후이 클래스의 개체에 액세스 해야 하는 모든.cpp 모듈에 해당 모듈을 포함 합니다.  
  
 경우 `DECLARE_OLECREATE` 다음 클래스 선언에 포함 된 `IMPLEMENT_OLECREATE` 클래스 구현에 포함 되어야 합니다. 사용 하는 클래스 선언 `DECLARE_OLECREATE` 사용 하 여 해야 `DECLARE_DYNCREATE` 또는 `DECLARE_SERIAL`합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더**: afxdisp.h  

##  <a name="implement_olecreate"></a>IMPLEMENT_OLECREATE  
 이 매크로 중 하나 또는 [IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags) 클래스를 사용 하는 모든 클래스에 대 한 구현 파일에 표시 되어야 `DECLARE_OLECREATE`합니다.  
  
```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)  
```  
  
### <a name="parameters"></a>매개 변수  
 *class_name*  
 클래스의 실제 이름입니다.  
  
 *external_name*  
 (따옴표에 포함) 다른 응용 프로그램에 노출 되는 개체 이름입니다.  
  
 *l*, *w1*, *w2*, *b1*, *b 2*, *b3*, *b4*, *b5*, *b6*, *b7*, *b8*  
 클래스의의 구성 요소 **CLSID**합니다.  
  
### <a name="remarks"></a>설명  
  
> [!NOTE]
>  사용 하는 경우 `IMPLEMENT_OLECREATE`, 단일 스레딩 모델 기본적으로 지원 합니다. 사용 하는 경우 `IMPLEMENT_OLECREATE_FLAGS`를 사용 하 여 개체가 지 원하는 스레딩 모델을 지정할 수 있습니다는 `nFlags` 매개 변수입니다.  
  
 외부 이름에는 다른 응용 프로그램에 노출 된 식별자입니다. 자동화 서버에서이 클래스의 개체를 요청 하려면 외부 이름을 사용 하는 클라이언트 응용 프로그램.  
  
 OLE 클래스 ID가 개체에 대 한 고유 128 비트 식별자입니다. 하나 이루어져 **긴**, 두 개의 **단어**s 및 8 **바이트**s에 의해 표시 된 대로 *l*, *w1*, *w2*, 및 *b1* 통해 *b8* 구문 설명에 있습니다. 응용 프로그램 마법사 및 코드 마법사를 필요에 따라 고유한 OLE 클래스 Id를 만듭니다.  

### <a name="requirements"></a>요구 사항  
 **헤더**: afxdisp.h 

## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)

