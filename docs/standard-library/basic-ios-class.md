---
title: "basic_ios 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.basic_ios"
  - "ios/std::basic_ios"
  - "basic_ios"
  - "std::basic_ios"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ios 클래스"
ms.assetid: 4fdcd8e1-62d2-4611-8a70-1e4f58434007
caps.latest.revision: 24
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# basic_ios 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 템플릿 클래스는 템플릿 매개 변수에 따라 달라지는 입력 스트림\(템플릿 클래스 [basic\_istream](../standard-library/basic-istream-class.md)\) 및 출력 스트림\(템플릿 클래스 [basic\_ostream](../standard-library/basic-ostream-class.md)\)에 공통된 저장소 및 멤버 함수를 설명합니다.  [ios\_base](../standard-library/ios-base-class.md) 클래스는 일반적이고 템플릿 매개 변수에 따라 달라지지 않는 사항을 설명합니다. **basic\_ios\<class Elem, class Traits\>** 클래스의 개체는 **Elem** 형식의 요소가 포함된 스트림을 제어하는 데 도움이 됩니다. 해당 문자 특성은 **Traits** 클래스에 의해 결정됩니다.  
  
## 구문  
  
```  
  
     template <class   
     Elem  
     , class   
     Traits  
     >  
class basic_ios : public ios_base  
```  
  
#### 매개 변수  
 `Elem`  
 형식입니다.  
  
 `Traits`  
 `char_traits` 형식의 변수입니다.  
  
## 설명  
 **basic\_ios\<class Elem, class Traits\>** 클래스의 개체는 다음을 저장합니다.  
  
-   [basic\_istream](../standard-library/basic-istream-class.md) **\<Elem, Traits\>** 형식의 개체에 대한 동률 포인터  
  
-   [basic\_streambuf](../standard-library/basic-streambuf-class.md) **\<Elem, Traits \>** 형식의 개체에 대한 스트림 버퍼 포인터  
  
-   [서식 정보](../standard-library/ios-base-class.md)  
  
-   [ios\_base](../standard-library/ios-base-class.md) 형식의 기준 개체에 있는 [스트림 상태 정보](../standard-library/ios-base-class.md)  
  
-   `char_type` 형식의 개체에 있는 채우기 문자  
  
### 생성자  
  
|||  
|-|-|  
|[basic\_ios](../Topic/basic_ios::basic_ios.md)|`basic_ios` 클래스를 생성합니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/basic_ios::char_type.md)|템플릿 매개 변수 `Elem`의 동의어.|  
|[int\_type](../Topic/basic_ios::int_type.md)|`Traits::int_type`의 동의어입니다.|  
|[off\_type](../Topic/basic_ios::off_type.md)|`Traits::off_type`의 동의어입니다.|  
|[pos\_type](../Topic/basic_ios::pos_type.md)|`Traits::pos_type`의 동의어입니다.|  
|[traits\_type](../Topic/basic_ios::traits_type.md)|템플릿 매개 변수 `Traits`의 동의어.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[bad](../Topic/basic_ios::bad.md)|스트림 버퍼의 무결성 손실을 나타냅니다.|  
|[지우기](../Topic/basic_ios::clear.md)|오류 플래그를 모두 지웁니다.|  
|[copyfmt](../Topic/basic_ios::copyfmt.md)|스트림 간에 플래그를 복사합니다.|  
|[eof](../Topic/basic_ios::eof.md)|스트림의 끝에 도달했는지 여부를 나타냅니다.|  
|[예외](../Topic/basic_ios::exceptions.md)|스트림에서 발생하는 예외를 나타냅니다.|  
|[실패](../Topic/basic_ios::fail.md)|스트림에서 유효한 필드 추출 실패를 나타냅니다.|  
|[fill](../Topic/basic_ios::fill.md)|텍스트가 스트림만큼 넓지 않을 경우 사용할 문자를 지정하거나 반환합니다.|  
|[good](../Topic/basic_ios::good.md)|스트림 상태가 양호함을 나타냅니다.|  
|[imbue](../Topic/basic_ios::imbue.md)|로캘을 변경합니다.|  
|[init](../Topic/basic_ios::init.md)|`basic_ios` 생성자에 의해 호출됩니다.|  
|[move](../Topic/basic_ios::move.md)|스트림 버퍼에 대한 포인터를 제외하고 매개 변수의 모든 값을 현재 개체로 이동합니다.|  
|[narrow](../Topic/basic_ios::narrow.md)|지정된 `char_type`에 해당하는 char를 찾습니다.|  
|[rdbuf](../Topic/basic_ios::rdbuf.md)|스트림을 지정된 버퍼로 라우트합니다.|  
|[rdstate](../Topic/basic_ios::rdstate.md)|플래그에 대한 비트 상태를 읽습니다.|  
|[set\_rdbuf](../Topic/basic_ios::set_rdbuf.md)|이 스트림 개체에 대한 읽기 버퍼로 사용할 스트림 버퍼를 할당합니다.|  
|[setstate](../Topic/basic_ios::setstate.md)|추가 플래그를 설정합니다.|  
|[스왑](../Topic/basic_ios::swap.md)|이 `basic_ios` 개체의 값을 다른 `basic_ios` 개체의 값으로 교환합니다.  스트림 버퍼에 대한 포인터는 교환되지 않습니다.|  
|[tie](../Topic/basic_ios::tie.md)|한 스트림이 다른 스트림보다 먼저 처리되도록 합니다.|  
|[widen](../Topic/basic_ios::widen.md)|지정된 char에 해당하는 `char_type`을 찾습니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[explicit operator bool](../Topic/basic_ios::operator%20bool.md)|`basic_ios` 개체를 `bool`로 사용할 수 있도록 합니다.  일반적이고 의도하지 않은 부작용을 방지하기 위해 자동 형식 변환이 사용되지 않습니다.|  
|[operator void \*](../Topic/basic_ios::operator%20void%20*.md)|스트림 상태가 여전히 양호한지 여부를 나타냅니다.|  
|[operator \!](../Topic/basic_ios::operator!.md)|스트림 상태가 불량이 아닌지 여부를 나타냅니다.|  
  
## 요구 사항  
 **헤더:** \<ios\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)