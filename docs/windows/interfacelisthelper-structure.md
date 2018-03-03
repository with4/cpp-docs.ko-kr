---
title: "InterfaceListHelper 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceListHelper
dev_langs:
- C++
helpviewer_keywords:
- InterfaceListHelper structure
ms.assetid: 4297e419-c96b-45df-8a00-7568062125ba
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 241613f94431903c7d9e3957cece46844dc67ad9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="interfacelisthelper-structure"></a>InterfaceListHelper 구조체
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   typename T0,  
   typename T1 = Nil,  
   typename T2 = Nil,  
   typename T3 = Nil,  
   typename T4 = Nil,  
   typename T5 = Nil,  
   typename T6 = Nil,  
   typename T7 = Nil,  
   typename T8 = Nil,  
   typename T9 = Nil  
>  
struct InterfaceListHelper;  
  
template <  
   typename T0  
>  
struct InterfaceListHelper<T0, Nil, Nil, Nil, Nil, Nil, Nil, Nil, Nil>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T0`  
 템플릿 매개 변수 0는 반드시 필요 합니다.  
  
 `T1`  
 템플릿 매개 변수 1에는 기본적으로 지정 되지 않았습니다.  
  
 `T2`  
 템플릿 매개 변수 2는 기본적으로 지정 되지 않았습니다. 세 번째 템플릿 매개 변수입니다.  
  
 `T3`  
 템플릿 매개 변수 3, 기본적으로이 지정 되지 않았습니다.  
  
 `T4`  
 템플릿 매개 변수 4는 기본적으로 지정 되지 않았습니다.  
  
 `T5`  
 템플릿 매개 변수 5는 기본적으로 지정 되지 않았습니다.  
  
 `T6`  
 템플릿 매개 변수 6, 기본적으로이 지정 되지 않았습니다.  
  
 `T7`  
 템플릿 매개 변수 7, 기본적으로이 지정 되지 않았습니다.  
  
 `T8`  
 템플릿 매개 변수 8, 기본적으로이 지정 되지 않았습니다.  
  
 `T9`  
 템플릿 매개 변수 9, 기본적으로이 지정 되지 않았습니다.  
  
## <a name="remarks"></a>설명  
 InterfaceList 유형을 재귀적으로 지정 된 템플릿 매개 변수 인수를 적용 하 여 빌드합니다.  
  
 InterfaceListHelper 템플릿 템플릿 매개 변수를 사용 하 여 `T0` 첫 번째 데이터를 정의 하는 InterfaceList 구조체 한 다음 재귀적으로 멤버 나머지 템플릿 매개 변수를 InterfaceListHelper 서식 파일을 적용 합니다. InterfaceListHelper 나머지 템플릿 매개 변수가 없는 경우 중지 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`TypeT`|InterfaceList 형식에 대 한 동의어입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `InterfaceListHelper`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)