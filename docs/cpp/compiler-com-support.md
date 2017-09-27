---
title: "컴파일러 COM 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
caps.latest.revision: 7
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
ms.openlocfilehash: d81c54f7af604024da852999ca78fa5ee55079ef
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="compiler-com-support"></a>컴파일러 COM 지원
## <a name="microsoft-specific"></a>Microsoft 전용  
 Visual C++ 컴파일러는 직접 COM(구성 요소 개체 모델) 형식 라이브러리를 읽고 해당 콘텐츠를 컴파일에 포함될 수 있는 C++ 소스 코드로 변환할 수 있습니다. 언어 확장은 클라이언트 쪽에서 COM 프로그래밍을 용이하게 하는 데 사용할 수 있습니다.  
  
 사용 하 여는 [#import 전처리기 지시문](../preprocessor/hash-import-directive-cpp.md), 컴파일러에서 형식 라이브러리를 읽을 수 있습니다 및 클래스를 COM에 설명 하는 c + + 헤더 파일에 인터페이스를로 변환 합니다. `#import` 특성 집합은 결과 형식 라이브러리 헤더 파일에 대한 콘텐츠를 사용자가 제어하는 데 사용할 수 있습니다.  
  
 사용할 수는 [__declspec](../cpp/declspec.md) 확장된 특성 [uuid](../cpp/uuid-cpp.md) COM 개체에 전역 고유 식별자 (GUID)를 할당할 수 있습니다. 키워드 [__uuidof](../cpp/uuidof-operator.md) COM 개체와 연결 된 GUID를 추출 하는 데 사용할 수 있습니다. 다른 `__declspec` 특성 [속성](../cpp/property-cpp.md)는 지정 하는 데 사용할 수는 **가져오기** 및 **설정** COM 개체의 데이터 멤버에 대 한 메서드.  
  
 COM 전역 함수 및 클래스의 집합을 지원 하기 위해 제공 되는 **VARIANT** 및 `BSTR` 형식 스마트 포인터 구현 및에서 throw 된 오류 개체를 캡슐화 `_com_raise_error`:  
  
-   [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)  
  
-   [_bstr_t](../cpp/bstr-t-class.md)  
  
-   [_com_error](../cpp/com-error-class.md)  
  
-   [_com_ptr_t](../cpp/com-ptr-t-class.md)  
  
-   [_variant_t](../cpp/variant-t-class.md)  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 COM 지원 클래스](../cpp/compiler-com-support-classes.md)   
 [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)
