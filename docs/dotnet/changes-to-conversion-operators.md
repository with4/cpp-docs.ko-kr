---
title: 변환 연산자를 변경 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- conversion operators
- operators [C++], explicit type conversion
- type conversion, explicit conversions
- conversions, explicit
- explicit keyword [C++]
ms.assetid: 9b83925c-71b7-4bd3-ac2e-843dd7c7f184
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 750d16bc6fee86d8a3f8b912cdc4c251221dffb2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110874"
---
# <a name="changes-to-conversion-operators"></a>변환 연산자의 변경 내용
변환 연산자를 포함 하는 구문은 Visual c + + Managed Extensions for c + + 변경 되었습니다.  
  
 작성 하는 한 가지 예로 `op_Implicit` 변환을 지정할 수 있습니다. 다음에 대 한 정의은 `MyDouble` 언어 사양에서 가져옵니다.  
  
```  
__gc struct MyDouble {  
   static MyDouble* op_Implicit( int i );   
   static int op_Explicit( MyDouble* val );  
   static String* op_Explicit( MyDouble* val );   
};  
```  
  
 이 코드는 정수를 해당 정수를 변환 하기 위한 알고리즘을 지정 하는 `MyDouble` 에서 제공 되는 `op_Implicit` 연산자입니다. 또한 해당 변환은 컴파일러에 의해 암시적으로 수행 됩니다. 마찬가지로, 한 `MyDouble` 개체, 두 개의 `op_Explicit` 연산자는 정수 또는 관리 되는 해당 개체를 변환 하기 위한 알고리즘을 각각 제공 `String` 엔터티. 그러나 컴파일러는 사용자가 명시적으로 요청 하지 않는 변환을 수행 하지 않습니다.  
  
 C#에서이 모양은 다음과 같습니다.  
  
```  
class MyDouble {  
   public static implicit operator MyDouble( int i );   
   public static explicit operator int( MyDouble val );  
   public static explicit operator string( MyDouble val );   
};  
```  
  
 C# 코드 Managed Extensions for c + + 보다 c + + 같이 더 표시 합니다. 새 구문에서 대/소문자 아닙니다.  
  
 ISO c + + committee 키워드를 도입 `explicit`,-예를 들어 의도 하지 않은 결과 완화 하는 `Array` 차원에서는에 임의의 정수를 암시적으로 변환 하는 대로 단일 정수 인수를 사용 하는 클래스는 `Array` 개체는 원하는 되지 않습니다. 이 방지 하기 위해 한 가지 방법은 생성자에 더미 두 번째 인수의 디자인 방식  
  
 반면에 c + + 어셈블리 내에서 클래스 형식을 디자인 하는 경우 변환 쌍을 제공 해야 합니다. 예를 들어는 표준 문자열 클래스입니다. 암시적 변환은 C 스타일 문자열을 사용 하는 단일 인수 생성자입니다. 그러나 변환 하는 문자열 개체를 C 스타일 문자열 대신 명시적으로 경우 명명 된 함수를 호출 하도록 요청 해당 암시적 변환 연산자-를 제공 하지 않는 `c_str()`합니다.  
  
 따라서 암시적/명시적 변환 연산자에 (및 선언의 단일 형식으로 변환 집합을 캡슐화) 동작을 연결 될 것 이므로 결국는 변환연산자에대한원래c++지원기능이향상`explicit` 키워드입니다. 변환 연산자에 대 한 Visual c + + 언어 지원을는 변환 알고리즘의 암시적인 응용 프로그램을 지 원하는 연산자의 기본 동작 때문에 C# 보다 약간 덜 자세한는 모양은 다음과 같습니다.  
  
```  
ref struct MyDouble {  
public:  
   static operator MyDouble^ ( int i );  
   static explicit operator int ( MyDouble^ val );  
   static explicit operator String^ ( MyDouble^ val );  
};  
```  
  
 단일 인수 생성자는로 선언 된 것 처럼 처리 하는 또 다른 변경 사항은 `explicit`합니다. 즉, 해당 호출을 트리거하기 위해 명시적 캐스트는 필요 합니다. 그러나 Note, 하는 명시적 변환 연산자가 정의 하 고 단일 인수 생성자 호출 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 또는 인터페이스 내에서 멤버 선언(C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)