---
title: "런타임 개체 모델 서비스 | Microsoft 문서"
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
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
caps.latest.revision: 15
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 8739201489644b0f1695a70d0dc12d04ca47aa68
ms.lasthandoff: 02/24/2017

---
# <a name="run-time-object-model-services"></a>런타임 개체 모델 서비스
클래스 [CObject](../../mfc/reference/cobject-class.md) 및 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 런타임 클래스 정보, serialization 및 동적 개체 만들기에 대 한 액세스를 포함 한 몇 가지 개체 서비스를 캡슐화 합니다. 모든 클래스에서 파생 된 `CObject` 이 기능을 상속 합니다.  
  
 런타임 클래스 정보에 대 한 액세스를 사용 하면 런타임에 개체의 클래스에 대 한 정보를 확인할 수 있습니다. 런타임 시 개체의 클래스를 확인 하는 기능 추가 형식 검사 함수 인수 및 개체의 클래스를 기반으로 하는 특수 한 용도의 코드를 작성 해야 할 때 유용 합니다. 런타임 클래스 정보는 c + + 언어에서 직접 지원 되지 않습니다.  
  
 Serialization은 파일에서 작성 하거나 또는 개체의 콘텐츠를 읽기는 프로세스입니다. 응용 프로그램이 종료 후에 개체의 내용을 저장 하려면 serialization을 사용할 수 있습니다. 응용 프로그램 다시 시작 되 면 개체는 파일에 다음 읽을 수 있습니다. 이러한 데이터 개체를 "영구." 라고 합니다.  
  
 동적 개체 만들기를 사용 하면 런타임 시 지정된 된 클래스의 개체를 만들 수 있습니다. 예를 들어, 문서, 뷰 및 프레임 개체 지원 해야 동적 생성 프레임 워크 동적으로 만들어야 하기 때문에 합니다.  
  
 다음 표에서 런타임 클래스 정보, serialization 및 동적 생성을 지 원하는 MFC 매크로 나열 합니다.  
  
 이러한 런타임 개체 서비스와 serialization에 대 한 자세한 내용은 문서를 참조 하십시오. [CObject 클래스: 런타임 클래스 정보 액세스](../../mfc/accessing-run-time-class-information.md)합니다.  
  
### <a name="run-time-object-model-services-macros"></a>런타임 개체 모델 서비스 매크로  
  
|||  
|-|-|  
|[DECLARE_DYNAMIC](#declare_dynamic)|런타임 클래스 정보 (클래스 선언에 사용 해야 합니다)에 액세스할 수 있도록 합니다.|  
|[DECLARE_DYNCREATE](#declare_dyncreate)|동적 생성 및 런타임 클래스 정보 (클래스 선언에 사용 해야 합니다)에 액세스할 수 있습니다.|  
|[DECLARE_SERIAL](#declare_serial)|Serialization 및 (클래스 선언에 사용 해야 합니다) 런타임 클래스 정보에 액세스할 수 있습니다.|  
|[IMPLEMENT_DYNAMIC](#implement_dynamic)|런타임 클래스 정보 (클래스 구현에 사용 해야 합니다)에 액세스할 수 있도록 합니다.|  
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|동적 생성 및 실행 시간 정보 (클래스 구현에 사용 해야 합니다)에 액세스할 수 있습니다.|  
|[IMPLEMENT_SERIAL](#implement_serial)|Serialization 및 런타임 클래스 정보 (클래스 구현에 사용 해야 합니다)에 대 한 액세스를 허용 합니다.|  
|[RUNTIME_CLASS](#runtime_class)|반환 된 `CRuntimeClass` 명명된 된 클래스에 해당 합니다.|  


 OLE는 런타임 시 개체의 동적 생성 자주 필요합니다. 예를 들어 OLE 서버 응용 프로그램 클라이언트의 요청에 응답에서 OLE 항목을 동적으로 만들 수 있어야 합니다. 마찬가지로, 자동화 서버는 자동화 클라이언트 요청에 대 한 응답에 항목을 만들 수 있어야 합니다.  
  
 Microsoft Foundation Class 라이브러리 ole 특정 두 매크로 제공합니다.  
  
### <a name="dynamic-creation-of-ole-objects"></a>OLE 개체의 동적 생성  
  
|||  
|-|-|  
|[DECLARE_OLECREATE](#declare_olecreate)|개체를를 OLE 자동화를 통해 만들 수 있습니다.|  
|[IMPLEMENT_OLECREATE](#implement_olecreate)|개체를를 OLE 시스템에서 만들 수 있습니다.|  
  
##  <a name="a-namedeclaredynamica--declaredynamic"></a><a name="declare_dynamic"></a>DECLARE_DYNAMIC  
 클래스를 파생 하는 경우 개체의 클래스에 대 한 런타임 정보에 액세스 하는 기능을 추가 `CObject`합니다.  
  
```
DECLARE_DYNAMIC(class_name) 
```  
  
### <a name="parameters"></a>매개 변수  
 *눈여겨 보십시오*  
 클래스의 실제 이름입니다.  
  
### <a name="remarks"></a>주의  
 추가 된 `DECLARE_DYNAMIC` 매크로 클래스에 대 한 헤더 (.h) 모듈에이 클래스의 개체에 액세스 해야 하는 모든.cpp 모듈에 해당 모듈이 포함 됩니다.  
  
 사용 하는 경우는 **DECLARE**_ **동적** 및 `IMPLEMENT_DYNAMIC` 설명 된 대로 매크로 사용할 수는 `RUNTIME_CLASS` 매크로 및 `CObject::IsKindOf` 런타임에 개체의 클래스를 확인 하는 함수입니다.  
  
 경우 `DECLARE_DYNAMIC` 다음 클래스 선언에 포함 된 `IMPLEMENT_DYNAMIC` 클래스 구현에 포함 되어야 합니다.  
  
 대 한 자세한 내용은 `DECLARE_DYNAMIC` 매크로 참조 [CObject 클래스 항목](../../mfc/using-cobject.md)합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [IMPLEMENT_DYNAMIC](#implement_dynamic)합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="a-namedeclaredyncreatea--declaredyncreate"></a><a name="declare_dyncreate"></a>DECLARE_DYNCREATE  
 개체를 사용 하면 `CObject`-런타임에 동적으로 생성 하기 위해 파생 클래스입니다.  
  
```
DECLARE_DYNCREATE(class_name)   
```  
  
### <a name="parameters"></a>매개 변수  
 *눈여겨 보십시오*  
 클래스의 실제 이름입니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는이 기능을 사용 하 여 새 개체를 동적으로 만듭니다. 예를 들어 새 보기는 새 문서를 열었을 때 생성 됩니다. 문서, 뷰 및 프레임 클래스는 프레임 워크 동적으로 만들어야 하기 때문에 동적 만들기를 지원 해야 합니다.  
  
 추가 된 `DECLARE_DYNCREATE` 매크로 클래스에 대 한.h 모듈에서이 클래스의 개체에 액세스 해야 하는 모든.cpp 모듈에 해당 모듈이 포함 됩니다.  
  
 경우 `DECLARE_DYNCREATE` 다음 클래스 선언에 포함 된 `IMPLEMENT_DYNCREATE` 클래스 구현에 포함 되어야 합니다.  
  
 대 한 자세한 내용은 `DECLARE_DYNCREATE` 매크로 참조 [CObject 클래스 항목](../../mfc/using-cobject.md)합니다.  
  
> [!NOTE]
>  `DECLARE_DYNCREATE` 의 모든 기능을 포함 하는 매크로 `DECLARE_DYNAMIC`합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [IMPLEMENT_DYNCREATE](#implement_dyncreate)합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="a-namedeclareseriala--declareserial"></a><a name="declare_serial"></a>DECLARE_SERIAL  
 C + + 헤더는 데 필요한 코드를 생성 한 `CObject`-serialize 할 수 있는 클래스를 파생 합니다.  
  
```
DECLARE_SERIAL(class_name)   
```  
  
### <a name="parameters"></a>매개 변수  
 *눈여겨 보십시오*  
 클래스의 실제 이름입니다.  
  
### <a name="remarks"></a>주의  
 Serialization은 하는 프로세스를 작성 하 고 개체의 내용을 읽는 파일 또는입니다.  
  
 사용 하는 `DECLARE_SERIAL` 매크로.h 모듈에서 다음이 클래스의 개체에 액세스 해야 하는 모든.cpp 모듈에 해당 모듈을 포함 합니다.  
  
 경우 `DECLARE_SERIAL` 다음 클래스 선언에 포함 된 `IMPLEMENT_SERIAL` 클래스 구현에 포함 되어야 합니다.  
  
 `DECLARE_SERIAL` 의 모든 기능을 포함 하는 매크로 `DECLARE_DYNAMIC` 및 `DECLARE_DYNCREATE`합니다.  
  
 사용할 수는 **AFX_API** 매크로를 자동으로 내보낼는 `CArchive` 추출 연산자를 사용 하는 클래스는 `DECLARE_SERIAL` 및 `IMPLEMENT_SERIAL` 매크로입니다. 대괄호를 다음 코드로 클래스 선언 (.h 파일에 있음).  
  
 [!code-cpp[NVC_MFCCObjectSample #&20;](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 대 한 자세한 내용은 `DECLARE_SERIAL` 매크로 참조 [CObject 클래스 항목](../../mfc/using-cobject.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCObjectSample #&21;](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="a-nameimplementdynamica--implementdynamic"></a><a name="implement_dynamic"></a>IMPLEMENT_DYNAMIC  
 동적 하는 데 필요한 c + + 코드를 생성 `CObject`-클래스 이름 및 계층 내 위치에 대 한 런타임 액세스를 사용 하 여 클래스를 파생 합니다.  
  
```
IMPLEMENT_DYNAMIC(class_name, base_class_name)  
```  
  
### <a name="parameters"></a>매개 변수  
 *눈여겨 보십시오*  
 클래스의 실제 이름입니다.  
  
 `base_class_name`  
 기본 클래스의 이름입니다.  
  
### <a name="remarks"></a>주의  
 사용 된 `IMPLEMENT_DYNAMIC` 매크로.cpp 모듈을 한 다음 링크는 결과 개체 코드를 한 번만 합니다.  
  
 자세한 내용은 참조 [CObject 클래스 항목](../../mfc/using-cobject.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCObjectSample #&2;](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample #&3;](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="a-nameimplementdyncreatea--implementdyncreate"></a><a name="implement_dyncreate"></a>IMPLEMENT_DYNCREATE  
 개체를 사용 하면 `CObject`-런타임에 동적으로 생성 하기 위해 파생 클래스와 함께 사용할 경우 시간는 `DECLARE_DYNCREATE` 매크로입니다.  
  
```
IMPLEMENT_DYNCREATE(class_name, base_class_name)   
```  
  
### <a name="parameters"></a>매개 변수  
 *눈여겨 보십시오*  
 클래스의 실제 이름입니다.  
  
 `base_class_name`  
 기본 클래스의 실제 이름입니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는이 기능을 사용 하 여 새 개체를 동적으로 만들거나 예를 들어 직렬화 하는 동안 디스크에서 개체를 읽을 경우. 추가 `IMPLEMENT_DYNCREATE` 클래스 구현 파일에는 매크로입니다. 자세한 내용은 참조 [CObject 클래스 항목](../../mfc/using-cobject.md)합니다.  
  
 사용 하는 경우는 `DECLARE_DYNCREATE` 및 `IMPLEMENT_DYNCREATE` 매크로 사용할 수는 `RUNTIME_CLASS` 매크로 및 `CObject::IsKindOf` 멤버 함수를 런타임 시 개체의 클래스를 확인 합니다.  
  
 경우 `DECLARE_DYNCREATE` 다음 클래스 선언에 포함 된 `IMPLEMENT_DYNCREATE` 클래스 구현에 포함 되어야 합니다.  
  
 참고가 매크로 정의 클래스에 대 한 기본 생성자를 호출 합니다. 특수 생성자는 클래스에 의해 명시적으로 구현 하는 경우 기본 생성자를 사용할 경우에 명시적으로 구현 해야 합니다. 기본 생성자는 클래스에 추가할 수 있습니다 **개인** 또는 **보호** 멤버 섹션 클래스 구현 외부에서 호출 되 고 하지 못하도록 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCObjectSample #&22;](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample&23;](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="a-nameimplementseriala--implementserial"></a><a name="implement_serial"></a>IMPLEMENT_SERIAL  
 동적 하는 데 필요한 c + + 코드를 생성 `CObject`-클래스 이름 및 계층 내 위치에 대 한 런타임 액세스를 사용 하 여 클래스를 파생 합니다.  
  
```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)  
```  
  
### <a name="parameters"></a>매개 변수  
 *눈여겨 보십시오*  
 클래스의 실제 이름입니다.  
  
 `base_class_name`  
 기본 클래스의 이름입니다.  
  
 *wSchema*  
 A **UINT** deserializing 프로그램을 식별 하 여에서 생성 된 데이터를 처리할 수 있도록 보관 파일에 인코딩될 "버전 번호" 이전 버전을 프로그래밍 합니다. 클래스 스키마 번호가 â € 수 없습니다 "1.  
  
### <a name="remarks"></a>주의  
 사용 된 `IMPLEMENT_SERIAL` 매크로.cpp 모듈에 다음 결과 개체 코드를 한 번만 연결 합니다.  
  
 사용할 수는 **AFX_API** 매크로를 자동으로 내보낼는 `CArchive` 추출 연산자를 사용 하는 클래스는 `DECLARE_SERIAL` 및 `IMPLEMENT_SERIAL` 매크로입니다. 대괄호를 다음 코드로 클래스 선언 (.h 파일에 있음).  
  
 [!code-cpp[NVC_MFCCObjectSample #&20;](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 자세한 내용은 참조는 [CObject 클래스 항목](../../mfc/using-cobject.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCObjectSample #&24;](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 

##  <a name="a-nameruntimeclassa--runtimeclass"></a><a name="runtime_class"></a>RUNTIME_CLASS  
 C + + 클래스의 이름에서 런타임 클래스 구조를 가져옵니다.  
  
```
RUNTIME_CLASS(class_name)  
```  
  
### <a name="parameters"></a>매개 변수  
 *눈여겨 보십시오*  
 (인용 부호로 묶지) 클래스의 실제 이름입니다.  
  
### <a name="remarks"></a>주의  
 `RUNTIME_CLASS`에 대 한 포인터를 반환 합니다.는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 에서 지정한 클래스에 대 한 구조 *눈여겨 보십시오*합니다. 만 `CObject`-파생 된 클래스를 사용 하 여 선언 `DECLARE_DYNAMIC`, `DECLARE_DYNCREATE`, 또는 `DECLARE_SERIAL` 에 대 한 포인터를 반환 합니다는 `CRuntimeClass` 구조입니다.  
  
 자세한 내용은 참조 [CObject 클래스 항목](../../mfc/using-cobject.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCObjectSample #&25;](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h 
   
##  <a name="a-namedeclareolecreatea--declareolecreate"></a><a name="declare_olecreate"></a>DECLARE_OLECREATE  
 개체를 사용 하면 `CCmdTarget`-OLE 자동화를 통해 생성 되는 클래스를 파생 합니다.  
  
```
DECLARE_OLECREATE(class_name) 
```  
  
### <a name="parameters"></a>매개 변수  
 *눈여겨 보십시오*  
 클래스의 실제 이름입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 다른 OLE 지원 응용 프로그램을을이 형식의 개체를 만들 수 있습니다.  
  
 추가 `DECLARE_OLECREATE` 매크로 클래스에 대 한.h 모듈에 다음이 클래스의 개체에 액세스 해야 하는 모든.cpp 모듈에 해당 모듈을 포함 합니다.  
  
 경우 `DECLARE_OLECREATE` 다음 클래스 선언에 포함 된 `IMPLEMENT_OLECREATE` 클래스 구현에 포함 되어야 합니다. 사용 하 여 클래스 선언 `DECLARE_OLECREATE` 도 사용 해야 `DECLARE_DYNCREATE` 또는 `DECLARE_SERIAL`합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더**: afxdisp.h  

##  <a name="a-nameimplementolecreatea--implementolecreate"></a><a name="implement_olecreate"></a>IMPLEMENT_OLECREATE  
 이 매크로 중 하나 또는 [IMPLEMENT_OLECREATE_FLAGS](http://msdn.microsoft.com/library/d1589f6a-5a69-4742-b07c-4c621cfd040d) 되는 클래스를 사용 하는 구현 파일에 표시 되어야 `DECLARE_OLECREATE`합니다.  
  
```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)  
```  
  
### <a name="parameters"></a>매개 변수  
 *눈여겨 보십시오*  
 클래스의 실제 이름입니다.  
  
 *external_name*  
 (인용 부호 안에 포함 됨) 다른 응용 프로그램에 노출 되는 개체 이름입니다.  
  
 *l*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4*, *b5*, *b6*, *b7*, *b8*  
 구성 요소는 클래스의 **CLSID**합니다.  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  사용 하는 경우 `IMPLEMENT_OLECREATE`, 단일 스레딩 모델 기본적으로 지원 합니다. 사용 하는 경우 `IMPLEMENT_OLECREATE_FLAGS`를 사용 하 여 개체가 지 원하는 어떤 스레딩 모델을 지정할 수는 `nFlags` 매개 변수입니다.  
  
 외부 이름에는 다른 응용 프로그램에 노출 된 식별자입니다. 클라이언트 응용 프로그램에서는 외부 이름을 사용 하 여 자동화 서버에서이 클래스의 개체를 요청 합니다.  
  
 OLE 클래스 ID는 개체에 대 한 고유 128 비트 식별자입니다. 하나 이루어져 **긴**, 두 개의 **WORD**s 및&8; **바이트**s에 표시 된 대로 *l*, *w1*, *w2*, 및 *b1* 통해 *b&8;* 구문 설명에 있습니다. 응용 프로그램 마법사 및 코드 마법사를 필요에 따라 고유한 OLE 클래스 Id를 만듭니다.  

### <a name="requirements"></a>요구 사항  
 **헤더**: afxdisp.h 

## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)

