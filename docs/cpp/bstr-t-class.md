---
title: "_bstr_t 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t
dev_langs:
- C++
helpviewer_keywords:
- BSTR object
- _bstr_t class
- BSTR object [C++], COM encapsulation
ms.assetid: 58841fef-fe21-4a84-aab9-780262b5201f
caps.latest.revision: 9
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: ce63f8243bc46d77116dbacdf82f821333cba785
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="bstrt-class"></a>_bstr_t 클래스
**Microsoft 전용**  
  
 A `_bstr_t` 개체에서 캡슐화 된 [BSTR 데이터 형식](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228)합니다. 클래스 리소스 할당 및 할당 해제 함수 호출을 통해 관리 **SysAllocString** 및 **SysFreeString** 및 기타 `BSTR` Api입니다. `_bstr_t` 클래스는 과도한 오버헤드를 방지하기 위해 참조 가산을 사용합니다.  
  
### <a name="construction"></a>생성  
  
|||  
|-|-|  
|[_bstr_t](../cpp/bstr-t-bstr-t.md)|`_bstr_t` 개체를 생성합니다.|  
  
### <a name="operations"></a>작업  
  
|||  
|-|-|  
|[할당](../cpp/bstr-t-assign.md)|`BSTR`을 `BSTR`로 래핑된 `_bstr_t`로 복사합니다.|  
|[Attach](../cpp/bstr-t-attach.md)|`_bstr_t` 래퍼를 `BSTR`에 연결합니다.|  
|[copy](../cpp/bstr-t-copy.md)|캡슐화된 `BSTR`의 복사본을 구성합니다.|  
|[Detach](../cpp/bstr-t-detach.md)|`BSTR`로 래핑된 `_bstr_t`을 반환하고 `BSTR`을 `_bstr_t`에서 분리합니다.|  
|[GetAddress](../cpp/bstr-t-getaddress.md)|`BSTR`로 래핑된 `_bstr_t`을 가리킵니다.|  
|[GetBSTR](../cpp/bstr-t-getbstr.md)|`BSTR`에 의해 래핑되는 `_bstr_t`의 시작 부분을 가리킵니다.|  
|[length](../cpp/bstr-t-length.md)|`_bstr_t`에 있는 문자의 수를 반환합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[연산자 =](../cpp/bstr-t-operator-equal.md)|기존 `_bstr_t` 개체에 새 값을 할당합니다.|  
|[+ = 연산자](../cpp/bstr-t-operator-add-equal-plus.md)|`_bstr_t` 개체의 끝 부분에 문자를 추가합니다.|  
|[연산자 +](../cpp/bstr-t-operator-add-equal-plus.md)|두 문자열을 연결합니다.|  
|[연산자 !](../cpp/bstr-t-operator-logical-not.md)|확인 캡슐화 된 `BSTR` 는 **NULL** 문자열입니다.|  
|[연산자 = =,! =, \<, >, \<=, > =](../cpp/bstr-t-relational-operators.md)|두 `_bstr_t` 개체를 비교합니다.|  
|[연산자 wchar_t * &#124; char\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)|캡슐화된 유니코드 또는 멀티바이트 `BSTR` 개체에 대한 포인터를 추출합니다.|  
  
**Microsoft 전용 종료**  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** comutil.h  
  
 **Lib:** 에서는 comsuppw.lib 또는 comsuppwd.lib (참조 [/zc: wchar_t (wchar_t는 네이티브 형식임)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 자세한 내용은)  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 COM 지원 클래스](../cpp/compiler-com-support-classes.md)
