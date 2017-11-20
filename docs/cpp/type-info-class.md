---
title: "type_info 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: type_info
dev_langs: C++
helpviewer_keywords:
- class type_info
- type_info class
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 61e26b60916712e10c1c0fa5b255aa7bf2bc1fd9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="typeinfo-class"></a>type_info 클래스
**type_info** 클래스 컴파일러가 프로그램 안에 생성 하는 형식 정보를 설명 합니다. 이 클래스의 개체는 형식의 이름에 대한 포인터를 효과적으로 저장합니다. **type_info** 클래스도 두 형식의 비교 또는 정렬 순서에 대 한 적합 한 인코딩된 값을 저장 합니다. 형식의 인코딩 규칙 및 정렬 시퀀스는 지정되지 않으며 프로그램 간에 다를 수 있습니다.  
  
 `<typeinfo>` 헤더 파일을 사용 하려면 포함 되어야 합니다는 **type_info** 클래스입니다. 에 대 한 인터페이스는 **type_info** 클래스는:  
  
```cpp
class type_info {  
public:  
    virtual ~type_info();  
    size_t hash_code() const  
    _CRTIMP_PURE bool operator==(const type_info& rhs) const;  
    _CRTIMP_PURE bool operator!=(const type_info& rhs) const;  
    _CRTIMP_PURE int before(const type_info& rhs) const;  
    _CRTIMP_PURE const char* name() const;  
    _CRTIMP_PURE const char* raw_name() const;  
};  
```  
  
 개체를 인스턴스화할 수 없습니다는 **type_info** 클래스에 전용 복사 생성자만 있기 때문에 클래스를 직접 합니다. (임시)를 생성 하는 유일한 방법은 **type_info** 는 사용 하 여 [typeid](../cpp/typeid-operator.md) 연산자입니다. 복사 하거나 클래스의 개체를 할당할 수 없습니다 이므로 대입 연산자, 개인도 **type_info**합니다.  
  
 **type_info:: hash_code** 형식의 값을 매핑하기에 적합 한 해시 함수를 정의 **typeinfo** 인덱스 값의 분포를 합니다.  
  
 연산자 `==` 및 `!=` 다른 같음 또는 같지 않음 비교에 사용할 수 **type_info** 각각 개체입니다.  
  
 형식의 정렬 순서와 상속 관계 간에 링크가 없습니다. 사용 하 여 **type_info:: before** 형식의 정렬 시퀀스를 결정 하는 멤버 함수입니다. 보장 되지 않습니다는 **type_info:: before** 에서 서로 다른 프로그램 또는 같은 프로그램의 다른 실행에서 동일한 결과 생성 합니다. 이러한 방식으로 **type_info:: before** 의 주소 유사한 **(&)** 연산자입니다.  
  
 **type_info:: name** 멤버 함수가 반환 하는 **const char\***  형식의 이해 하기 쉬운 이름을 나타내는 null로 끝나는 문자열에 있습니다. 가리키는 메모리는 캐시되며 직접 할당 해지되면 안 됩니다.  
  
 **raw_name** 멤버 함수가 반환 하는 **const char\***  개체 유형의 데코 레이트 된 이름을 나타내는 null로 끝나는 문자열에 있습니다. 공간을 절약하기 위해 이름은 실제로 데코레이팅된 형식으로 저장됩니다. 따라서이 함수는 보다 빠르게 **type_info:: name** 이름을 이름의 데코레이팅을 취소할 필요가 없기 때문에 있습니다. 반환 된 문자열의 **raw_name** 함수는 비교 연산에 유용 하지만 읽을 수 없습니다. 사람이 읽을 수는 문자열을 필요한 경우 사용 된 **type_info:: name** 함수를 대신 합니다.  
  
 경우에만 다형 클래스에 대 한 형식 정보가 생성 됩니다는 [/GR (런타임 형식 정보 사용)](../build/reference/gr-enable-run-time-type-information.md) 컴파일러 옵션을 지정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [런타임 형식 정보](../cpp/run-time-type-information.md)
