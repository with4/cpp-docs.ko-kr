---
title: "컴파일러 COM 지원 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_raise_error
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
caps.latest.revision: 6
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
ms.openlocfilehash: 48540910db97e7662eeaa7e8a7febf7e44df653b
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="compiler-com-support-classes"></a>컴파일러 COM 지원 클래스
**Microsoft 전용**  
  
 표준 클래스는 COM 형식 중 일부를 지원하는 데 사용됩니다. 클래스는 comdef.h 및 형식 라이브러리에서 생성된 헤더 파일에 정의됩니다.  
  
|클래스|용도|  
|-----------|-------------|  
|[_bstr_t](../cpp/bstr-t-class.md)|`BSTR` 형식을 래핑하여 유용한 연산자와 메서드를 제공합니다.|  
|[_com_error](../cpp/com-error-class.md)|throw 된 오류 개체를 정의 [_com_raise_error](../cpp/com-raise-error.md) 대부분 오류가 발생에서 합니다.|  
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|COM 인터페이스 포인터를 캡슐화 하 고 필수 호출을 자동화 `AddRef`, **릴리스**, 및 `QueryInterface`합니다.|  
|[_variant_t](../cpp/variant-t-class.md)|래핑하는 **VARIANT** 형식 유용한 연산자와 메서드를 제공 합니다.|  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 COM 지원](../cpp/compiler-com-support.md)   
 [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)   
 [C++ 언어 참조](../cpp/cpp-language-reference.md)
