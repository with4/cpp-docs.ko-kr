---
title: 컴파일러 COM 지원 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a21b7dd00aa0bb0894da4cc13cf0f6f40078ee1b
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941829"
---
# <a name="compiler-com-support"></a>컴파일러 COM 지원
## <a name="microsoft-specific"></a>Microsoft 전용  
 Visual C++ 컴파일러는 직접 COM(구성 요소 개체 모델) 형식 라이브러리를 읽고 해당 콘텐츠를 컴파일에 포함될 수 있는 C++ 소스 코드로 변환할 수 있습니다. 언어 확장은 클라이언트 쪽에서 COM 프로그래밍을 용이하게 하는 데 사용할 수 있습니다.  
  
 사용 하 여 합니다 [#import 전처리기 지시문](../preprocessor/hash-import-directive-cpp.md), 컴파일러는 형식 라이브러리를 읽을 수 있습니다 및 클래스를 COM을 설명 하는 c + + 헤더 파일에 인터페이스를로 변환 합니다. `#import` 특성 집합은 결과 형식 라이브러리 헤더 파일에 대한 콘텐츠를 사용자가 제어하는 데 사용할 수 있습니다.  
  
 사용할 수는 [__declspec](../cpp/declspec.md) 확장 된 특성 [uuid](../cpp/uuid-cpp.md) COM 개체를 전역적으로 고유 식별자 (GUID)를 할당 하려면. 키워드 [__uuidof](../cpp/uuidof-operator.md) COM 개체에 연결 된 GUID를 추출 하 사용할 수 있습니다. 다른 `__declspec` 특성을 [속성](../cpp/property-cpp.md)를 지정 하려면 사용할 수는 **가져오기** 및 **설정** COM 개체의 데이터 멤버에 대 한 메서드.  
  
 COM 전역 함수 및 클래스 집합을 지원 하기 위해 제공 되는 `VARIANT` 하 고 `BSTR` 형식 스마트 포인터를 구현 및에서 throw 된 오류 개체를 캡슐화 `_com_raise_error`:  
  
-   [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)  
  
-   [_bstr_t](../cpp/bstr-t-class.md)  
  
-   [_com_error](../cpp/com-error-class.md)  
  
-   [_com_ptr_t](../cpp/com-ptr-t-class.md)  
  
-   [_variant_t](../cpp/variant-t-class.md)  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 COM 지원 클래스](../cpp/compiler-com-support-classes.md)   
 [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)