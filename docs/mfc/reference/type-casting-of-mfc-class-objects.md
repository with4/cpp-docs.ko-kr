---
title: 형식 캐스팅 MFC 클래스 개체의 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- macros [MFC], type casting
- pointers [MFC], type casting
- type casts [MFC]
- casting types [MFC]
- macros [MFC], casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 217be53a78a65a0f617438127b922b20c950853d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="type-casting-of-mfc-class-objects"></a>MFC 클래스 개체의 형식 캐스팅
형식 캐스팅 매크로 또는 캐스트가 법적 확인 하지 않고 특정 클래스의 개체를 가리키는 포인터에 대 한 지정 된 포인터를 캐스팅 하는 방법을 제공 합니다.  
  
 다음 표에서 MFC 형식 캐스팅 매크로 나열합니다.  
  
### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>MFC 클래스 개체에 대 한 포인터를 캐스팅 하는 매크로  
  
|||  
|-|-|  
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|캐스팅 법적가 있는지 확인 하는 동안 클래스 개체에 대 한 포인터에 대 한 포인터를 캐스팅 합니다.|  
|[STATIC_DOWNCAST](#static_downcast)|관련 된 형식의 포인터에 하나의 클래스에서 개체에 대 한 포인터를 캐스팅합니다. 디버그 빌드를이 인해는 **ASSERT** 개체가 없는 경우는 "일종의" 대상 유형입니다.|  
  
##  <a name="dynamic_downcast"></a>  DYNAMIC_DOWNCAST  
 캐스팅 법적가 있는지 확인 하는 동안 클래스 개체에 대 한 포인터에 대 한 포인터를 캐스팅 하는 편리한 방법을 제공 합니다.  
  
```   
DYNAMIC_DOWNCAST(class, pointer)  
```  
  
### <a name="parameters"></a>매개 변수  
 `class`  
 클래스의 이름입니다.  
  
 `pointer`  
 형식의 개체에 대 한 포인터로 캐스팅할 수에 대 한 포인터 `class`합니다.  
  
### <a name="remarks"></a>설명  
 매크로 캐스팅는 `pointer` 의 개체에 대 한 포인터를 매개 변수는 `class` 매개 변수의 형식입니다.  
  
 포인터에 의해 참조 되는 개체가 하는 경우는 식별 된 클래스가 "일종의" 매크로 적절 한 포인터를 반환 합니다. 매크로 반환 하는 경우 유효한 캐스트 않습니다, **NULL**합니다.  
  
##  <a name="static_downcast"></a>  STATIC_DOWNCAST  
 캐스트 *pobject* 에 대 한 포인터로 *class_name* 개체입니다.  
  
```   
STATIC_DOWNCAST(class_name, pobject)   
```  
  
### <a name="parameters"></a>매개 변수  
 *class_name*  
 으로 캐스팅 되는 클래스의 이름입니다.  
  
 *pobject*  
 에 대 한 포인터로 캐스팅할 수에 대 한 포인터는 *class_name* 개체입니다.  
  
### <a name="remarks"></a>설명  
 *pobject* 반드시 **NULL**, 직접 파생 되는 클래스 또는 간접적으로 개체를 가리키고 또는 *class_name*합니다. 응용 프로그램의 빌드에는 **_DEBUG** 매크로 전처리기 기호를 정의 하면 **ASSERT** 경우 *pobject* 않습니다 **NULL**, 또는 없는 개체를 가리키는 경우는에 지정 된 클래스 "일종의"는 *class_name* 매개 변수 (참조 [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)). 비- **_DEBUG** 빌드, 매크로 어떠한 형식 검사 없이 캐스팅을 수행 합니다.  
  
 에 지정 된 클래스는 *class_name* 매개 변수에서 파생 되어야 합니다 `CObject` 사용 해야 합니다는 `DECLARE_DYNAMIC` 및 `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` 및 `IMPLEMENT_DYNCREATE`, 또는 `DECLARE_SERIAL` 및 `IMPLEMENT_SERIAL`매크로 문서에 설명 된 대로 [CObject 클래스: CObject에서 클래스를 파생](../../mfc/deriving-a-class-from-cobject.md)합니다.  
  
 에 대 한 포인터를 캐스팅할 수는 예를 들어 `CMyDoc`라는 `pMyDoc`에 대 한 포인터로 **CDocument** 이 식을 사용 하 여:  
  
 [!code-cpp[NVC_MFCDocView#197](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]  
  
 경우 `pMyDoc` 에서 직접 또는 간접적으로 파생 된 개체를 가리키지 않습니다 **CDocument**, 매크로 **ASSERT**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
