---
title: uuid (c + +) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- uuid_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 80975b751b6e167573a038e55042b3546821c68f
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="uuid-c"></a>uuid (C++)
**Microsoft 전용**  
  
 컴파일러는 `uuid` 특성을 사용하여 선언되거나 정의된(전체 COM 개체 정의만 해당) 클래스 또는 구조체에 GUID를 연결합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
__declspec( uuid("  
ComObjectGUID  
") ) declarator  
```  
  
## <a name="remarks"></a>설명  
 `uuid` 특성은 문자열을 인수로 사용합니다. 이 문자열 이름을 지정 하거나 사용 하지 않고 일반 레지스트리 형식에서 GUID는 **{}** 구분 기호입니다. 예:  
  
```  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;  
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;  
```  
  
 재선언에서 이 특성을 적용할 수 있습니다. 이렇게 하면와 같은 인터페이스의 정의 제공 하는 시스템 헤더 **IUnknown**, (예: COMDEF 일부 다른 헤더의 재선언. H)를 GUID를 제공 합니다.  
  
 키워드 [__uuidof](../cpp/uuidof-operator.md) 사용자 정의 형식에 연결 된 GUID 상수를 검색에 적용할 수 있습니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__declspec](../cpp/declspec.md)   
 [키워드](../cpp/keywords-cpp.md)
